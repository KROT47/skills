# CODE STRUCTURE

Rules for organizing modular code, including module interfaces and imports. A scope is one feature or area of responsibility.

## Files and folders

- Group files by scope. Keep code for the same scope in the same folder.
- Keep entry points small. Use them to read input, call the main process, and report the result.
- Keep related small functions together; extract a separate file when it clarifies responsibility or enables reuse.
- Keep a helper in its own scope unless another scope also needs it.
- Group shared code by purpose. Do not collect unrelated functions in a general utilities folder.
- Follow the naming conventions of the project.

## Module interfaces and imports

- Give each scope a clear public interface. Use an index file or the equivalent mechanism in the project's language.
- Export only the functions, types, and values that other scopes need.
- Access another scope through its public interface. Do not import its internal files directly.
- Within a scope, import the required internal module directly. Do not route internal imports through the scope's public interface.
- Keep public interface files free of startup actions. Importing a module must not start an application or background process.
- Do not create circular dependencies.

## Import paths

- Use a source-root alias or the language's equivalent for imports between different scopes.
- Use relative paths for imports within the same scope when the language supports them. This includes sibling files and files inside sibling folders.
- Choose the import form from the scope boundary, not only from folder depth.
- Follow an existing alias convention. If no convention exists, use one clear convention supported by the project's tools.
- Check that import paths work in all affected runtimes, test runners, and build tools. A successful static check is not enough.
