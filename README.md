# pdftk-java-native

A Heroku [Buildpack][buildpacks] to install [`pdftk-java` as a Native Image][prebuilt-bins] in your Slug.

## How to use it

Add this Buildpack as the first Buildpack in your App.
Or, at least before other Buildpacks that might need it.

```console
$ heroku buildpacks:add --index=1 stevenharman/pdftk-java-native --app=<YOUR-APP-NAME>
```

On the next deploy a `pdftk-java` Native Image (`x86_64`) will be downloaded and added to your Slug.
The binary (`pdftk`) will be placed in `app/bin`, which is already on the `$PATH`.
Meaning the binary will be available as `pdftk`.

## License

This work is licensed under [MIT License](./LICENSE).

Copyright (c) 2023 Steven Harman

[buildpacks]: https://devcenter.heroku.com/articles/buildpacks "Heroku Buildpacks"
[config-vars]: https://devcenter.heroku.com/articles/config-vars "Configuration and Config Vars"
[prebuilt-bins]: https://gitlab.com/pdftk-java/pdftk#pre-built-binaries "Pre-built binaries for pdftk-java"
