# Terminal-Todo

A command-line driven TODO list manager.

# SYNPOSIS

Terminal-Todo: Maintain a list of tasks with priorities. The tasklist is
resolved as follows:

- If a tasklist exists in $HOME it will be used,
- If a tasklist exists in $PWD, then it will be used instead of the
  tasklist in $HOME.
- If no tasklist is found, then one is created in $PWD.

To create a tasklist in $HOME, simply change directory to $HOME and run any
`todo` command.

Usage is as follows:

- `todo <command> [options]`
- `todo <command> [options] <command-arguments>`
- `todo [options] <command> <command-arguments>`
- `todo <command> <command-arguments> [options]`

#Commands

`list`

> Display all tasks. The list can be sorted with "--sort-by=`<column>`"
> or "-s `<column>`" where `<column>` is a column name. Use the option
> "-r" or "--reverse" to reverse the sort order.
> If no sort column is specified the list is sorted by the task IDs.

`add <title> [message-body]`

> Add a new task to the list. The `<title>` is mandatory. If a `[message-
> body]` is not specified then an editor will be started to prompt for a
> message. Use "--editor=`<editor>`" or "-e `<editor>`" to specify an editor.
> If no editor is specified then the $EDITOR environment variable will be
> used.

`show <task-id>`

> Display all fields of the specified task.

`set-priority <task-id> <new-priority>`

> Sets the priority for task `<task-id>` to `<new-priority>`.

`set-title <task-id> <new-title>`

> Sets the title for task `<task-id>` to `<new-title>`.

`set-message <task-id> <new-message-body>`

> Sets the message body for task `<task-id>` to `<new-message-body>`.

`search <search-term> [<search-term>]`

> Searches all task's title and message body fields for the specified
> search terms. By default the search matches ANY of the terms specified.
> To match ALL the terms specified use "-a" or "-all".

`prune`

> Removes all tasks from the list that are at priority -1 or lower. This
> is a convenient way to mark tasks that must be removed without actually
> removing the task. Tasks that are at priority -1 can later be re-
> prioritised.

`delete <task-id>`

> Permanently removes a task from the list. There is no way to resurrect
> a deleted task. To temporarily mark a task for deletion set the priority
> to -1. If you later change your mind about the task AND you haven't
> pruned the task list, you can re-prioritise the task to a positive number.
> Deletion will prompt the user. To force deletion without a prompt use
> "-f" or "--force".

