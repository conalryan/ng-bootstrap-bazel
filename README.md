# Ng-Bootstrap Bazel Ivy

1. Init new project with Bazel and Ivy
```bash
ng new ng-bootstrap-bazel-ivy --collection=@angular/bazel --enable-ivy
```

2. ng build
```bash
ng build --leaveBazelFilesOnDisk
```

3. Add ng-bootstrap
```bash
yarn add @ng-bootstrap/ng-bootstrap
```

Add ng-alert to app.component.html
```html
<ngb-alert [dismissible]="false">
  <strong>Warning!</strong> Better check yourself, you're not looking too good.
</ngb-alert>
```

Add NgbModule to app.module.ts
```typescript
import {NgbAlertModule} from '@ng-bootstrap/ng-bootstrap';
// ...
imports: [
  //...
  NgbAlertModule,
  //...
]
```

Add ng-bootstrap to BUILD.bazel
```bazel
ng_module(
  # ...
  deps = [
    # ...
    "@npm//@ng-bootstrap/ng-bootstrap",
  ]
)
```

$ bazel build //src:src
INFO: Call stack for the definition of repository 'npm' which is a npm_install (rule definition at /private/var/tmp/_bazel_cryan/cc699828ad36a3b5e8f265dafc60a906/external/build_bazel_rules_nodejs/internal/npm_install/npm_install.bzl:294:15):
 - /private/var/tmp/_bazel_cryan/cc699828ad36a3b5e8f265dafc60a906/external/build_bazel_rules_nodejs/defs.bzl:77:5
 - /Users/cryan/code/p/ng-bootstrap-bazel/WORKSPACE:64:1
ERROR: An error occurred during the fetch of repository 'npm':
   Traceback (most recent call last):
	File "/private/var/tmp/_bazel_cryan/cc699828ad36a3b5e8f265dafc60a906/external/build_bazel_rules_nodejs/internal/npm_install/npm_install.bzl", line 292
		_create_build_files(repository_ctx, "npm_install", node, r...)
	File "/private/var/tmp/_bazel_cryan/cc699828ad36a3b5e8f265dafc60a906/external/build_bazel_rules_nodejs/internal/npm_install/npm_install.bzl", line 146, in _create_build_files
		fail(("generate_build_file.js failed:...)))
generate_build_file.js failed:
STDOUT:

STDERR:
npm package 'rxjs' from @npm npm_install rule
has a Bazel BUILD file 'src/BUILD.bazel'. Use the @bazel/hide-bazel-files utility to hide these files.
See https://github.com/bazelbuild/rules_nodejs/blob/master/packages/hide-bazel-files/README.md
for installation instructions.
ERROR: no such package '@npm//': Traceback (most recent call last):
	File "/private/var/tmp/_bazel_cryan/cc699828ad36a3b5e8f265dafc60a906/external/build_bazel_rules_nodejs/internal/npm_install/npm_install.bzl", line 292
		_create_build_files(repository_ctx, "npm_install", node, r...)
	File "/private/var/tmp/_bazel_cryan/cc699828ad36a3b5e8f265dafc60a906/external/build_bazel_rules_nodejs/internal/npm_install/npm_install.bzl", line 146, in _create_build_files
		fail(("generate_build_file.js failed:...)))
generate_build_file.js failed:
STDOUT:

STDERR:
npm package 'rxjs' from @npm npm_install rule
has a Bazel BUILD file 'src/BUILD.bazel'. Use the @bazel/hide-bazel-files utility to hide these files.
See https://github.com/bazelbuild/rules_nodejs/blob/master/packages/hide-bazel-files/README.md
for installation instructions.
ERROR: no such package '@npm//': Traceback (most recent call last):
	File "/private/var/tmp/_bazel_cryan/cc699828ad36a3b5e8f265dafc60a906/external/build_bazel_rules_nodejs/internal/npm_install/npm_install.bzl", line 292
		_create_build_files(repository_ctx, "npm_install", node, r...)
	File "/private/var/tmp/_bazel_cryan/cc699828ad36a3b5e8f265dafc60a906/external/build_bazel_rules_nodejs/internal/npm_install/npm_install.bzl", line 146, in _create_build_files
		fail(("generate_build_file.js failed:...)))
generate_build_file.js failed:
STDOUT:

STDERR:
npm package 'rxjs' from @npm npm_install rule
has a Bazel BUILD file 'src/BUILD.bazel'. Use the @bazel/hide-bazel-files utility to hide these files.
See https://github.com/bazelbuild/rules_nodejs/blob/master/packages/hide-bazel-files/README.md
for installation instructions.
INFO: Elapsed time: 153.158s
INFO: 0 processes.
FAILED: Build did NOT complete successfully (0 packages loaded)
