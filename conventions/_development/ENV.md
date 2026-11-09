# ENV

- Use `.env` as the template and `.env.local` for local values by default.
  - Add `.env.local` to `.gitignore`.
  - Include secret variable names in the template, but leave their values empty.
- Configure each web service's externally exposed port through an environment variable.
  - Name port variables in uppercase with the `_PORT` suffix, such as `API_PORT`.
  - Reuse each value wherever the same port is needed.
