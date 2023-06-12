---
publish: true
---

# Task Properties

<span class="related-pages">#feature/scripting</span>

> [!released]
> Task Properties were introduced in Tasks X.Y.Z.

## Introduction

In a growing number of locations, Tasks allows programmatic/scripting access to values in your Tasks:

- [[Grouping#Group by Function - Custom Groups]]

This documents all the available pieces of information in Tasks that you can access.

> [!warning]
> Tasks does store other data, but we only guarantee future support for the data items listed here without warning.

## Values for Task Statuses

For more information, including adding your own customised statuses, see [[Statuses]].

<!-- placeholder to force blank line before included text --> <!-- include: TaskProperties.test.task_status.approved.md -->

| Field | Type 1 | Example 1 | Type 2 | Example 2 |
| ----- | ----- | ----- | ----- | ----- |
| `task.isDone` | `boolean` | `false` | `boolean` | `false` |
| `task.status.name` | `string` | `'Todo'` | `string` | `'In Progress'` |
| `task.status.type` | `string` | `'TODO'` | `string` | `'IN_PROGRESS'` |
| `task.status.symbol` | `string` | `' '` | `string` | `'/'` |
| `task.status.nextSymbol` | `string` | `'x'` | `string` | `'x'` |

<!-- placeholder to force blank line after included text --> <!-- endInclude -->

---

## Values for Dates in Tasks

<!-- placeholder to force blank line before included text --> <!-- include: TaskProperties.test.task_dates.approved.md -->

| Field | Type 1 | Example 1 | Type 2 | Example 2 |
| ----- | ----- | ----- | ----- | ----- |
| `task.created` | `TasksDate` | `2023-07-01 00:00` | `TasksDate` | `` |
| `task.start` | `TasksDate` | `2023-07-02 00:00` | `TasksDate` | `` |
| `task.scheduled` | `TasksDate` | `2023-07-03 00:00` | `TasksDate` | `` |
| `task.due` | `TasksDate` | `2023-07-04 00:00` | `TasksDate` | `` |
| `task.done` | `TasksDate` | `2023-07-05 00:00` | `TasksDate` | `` |
| `task.happens` | `TasksDate` | `2023-07-02 00:00` | `TasksDate` | `` |

<!-- placeholder to force blank line after included text --> <!-- endInclude -->

1. Note that currently all stored dates have no time, or rather, their time is midnight at the start of the day, local time.
1. For example uses of date properties, see [[Grouping#Due Date]].
1. `task.happens` is the earlier of `task.due`, `task.scheduled` and `task.start`.

---

## Values for Other Task Properties

<!-- placeholder to force blank line before included text --> <!-- include: TaskProperties.test.task_other_fields.approved.md -->

| Field | Type 1 | Example 1 | Type 2 | Example 2 |
| ----- | ----- | ----- | ----- | ----- |
| `task.description` | `string` | `'Do exercises #todo #health'` | `string` | `'minimal task'` |
| `task.urgency` | `number` | `3.3000000000000007` | `number` | `1.9500000000000002` |
| `task.isRecurring` | `boolean` | `true` | `boolean` | `false` |
| `task.recurrenceRule` | `string` | `'every day when done'` | `string` | `''` |
| `task.tags` | `string[]` | `['#todo', '#health']` | `any[]` | `[]` |

<!-- placeholder to force blank line after included text --> <!-- endInclude -->

1. `task.description` has spaces at the start and end stripped off.
1. `task.description` includes any tags.
1. Note that if there is a [[Global Filter]] enabled in settings, and the filter is a tag, it will be removed from `task.tags`.
1. In a future release we will provide access to the task priority.

---

## Values for File Properties - commented out until precedingHeader renamed to heading

<!-- placeholder to force blank line before included text --> <!-- include: TaskProperties.test.task_file_properties.approved.md -->

| Field | Type 1 | Example 1 | Type 2 | Example 2 |
| ----- | ----- | ----- | ----- | ----- |
| `task.file.path` | `string` | `'some/folder/fileName.md'` | `string` | `''` |
| `task.file.root` | `string` | `'some/'` | `string` | `'/'` |
| `task.file.folder` | `string` | `'some/folder/'` | `string` | `'/'` |
| `task.file.filename` | `string` | `'fileName.md'` | `string` | `''` |
| `task.hasHeading` | `boolean` | `true` | `boolean` | `false` |
| `task.heading` | `string` | `'My Header'` | `null` | `null` |

<!-- placeholder to force blank line after included text --> <!-- endInclude -->

1. Access to file properties will be added soon.