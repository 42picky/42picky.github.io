# JSON Validation Schemas

As the [mkdocs][1] project does not publish its own [JSON Schema][2] for its
configuration, you can use the one we create from [`mkdocs.schema.json`][3].

We are fully aware that the schema also depends on plugins so it will never be
very comprehensive. However, it is a good starting point for spotting errors,
providing autocompletion or documentation tooltips. Feel free to contribute your
improvements.

If you are using [vscode][4] with [yaml extension][5], the schema validation
functionality will be automatically enabled.

[1]: https://www.mkdocs.org/
[2]: https://json-schema.org/
[3]: https://42picky.com/assets/f/schemas/mkdocs.schema.json
[4]: https://code.visualstudio.com/
[5]: https://marketplace.visualstudio.com/items?itemName=redhat.vscode-yaml
