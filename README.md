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

### Configure `pdftk-java` version

The `pdftk-java` project currently publishes Native Images for versions `3.3.0` - `3.3.3`.
By default this Buildpack downloads and installs the `3.3.3` version.
if you'd like to pin to a specific version, or use newer version when they become available, set the `PDFTK_JAVA_NATIVE_VERSION` [Config Var][config-vars].
Like so:

```console
$ heroku config:set PDFTK_JAVA_NATIVE_VERSION=3.3.3
```

## License

This work is licensed under [MIT License](./LICENSE).

Copyright (c) 2023 Steven Harman

[buildpacks]: https://devcenter.heroku.com/articles/buildpacks "Heroku Buildpacks"
[config-vars]: https://devcenter.heroku.com/articles/config-vars "Configuration and Config Vars"
[prebuilt-bins]: https://gitlab.com/pdftk-java/pdftk#pre-built-binaries "Pre-built binaries for pdftk-java"
