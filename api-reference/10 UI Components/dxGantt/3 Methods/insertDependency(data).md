---
id: dxGantt.insertDependency(data)
---
---
##### shortDescription
Inserts a new dependency.

##### param(data): Object
The dependency data.

---

---

##### jQuery

    <!-- tab: index.js -->
    var gantt = $("#ganttContainer").dxGantt("instance");
    gantt.insertDependency({ predecessorId: 1, successorId: 3, type: 3 });

---

#####See Also#####
- [dependencyInserting](/Documentation/ApiReference/UI_Components/dxGantt/Events/#dependencyInserting)
- [Gantt Elements](/Documentation/Guide/UI_Components/Gantt/Gantt_Elements/)