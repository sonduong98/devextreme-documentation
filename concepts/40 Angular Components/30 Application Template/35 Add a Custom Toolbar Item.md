The application template uses the DevExtreme [Toolbar](/api-reference/10%20UI%20Widgets/dxToolbar '/Documentation/ApiReference/UI_Components/dxToolbar/') component. The Toolbar is part of the `HeaderComponent` whose configuration is in the `src\app\shared\components\header` directory. To add a custom toolbar item, open the `header.component.html` file in this directory and add a `dxi-item` element inside `dx-toolbar`. Refer to the [items](/api-reference/10%20UI%20Widgets/dxToolbar/1%20Configuration/items '/Documentation/ApiReference/UI_Components/dxToolbar/Configuration/items/') help section for information on `dxi-item` attributes.

The following code adds a search button to the toolbar:

    <!-- tab: header.component.html -->
    <header>
        <dx-toolbar class="header-toolbar">
            <!-- ... -->
            <dxi-item
                location="after"
                widget="dxButton"
                [options]="{
                    icon: 'search',
                    onClick: startSearch
                }">
            </dxi-item>
            <!-- ... -->
        </dx-toolbar>
    </header>

    <!-- tab: header.component.ts -->
    export class HeaderComponent {
        // ...
        @Output()
        search = new EventEmitter<void>();

        startSearch = () => {
            this.search.emit();
        }
    }

    <!-- tab: side-nav-outer-toolbar.component.html -->
    <app-header ... 
        (search)="search()">
    </app-header>
    <!-- ... -->

    <!-- tab: side-nav-outer-toolbar.component.ts -->
    export class SideNavOuterToolbarComponent implements OnInit {
        // ...
        search() {
            console.log("search");
        }
    }

In the code above, the button click handler is declared in the `SideNavOuterToolbarComponent`. This component is applied when the outer toolbar [layout](/Documentation/Guide/Angular_Components/Application_Template/#Layouts) is used. If the application uses the inner toolbar layout, add the same code to the `SideNavInnerToolbarComponent`.
