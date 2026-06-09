# PortAllowIrpFromPdoToFdo

- ea: `0x1401b7ffc`
- end: `0x1401b80ef`
- name: `PortAllowIrpFromPdoToFdo`
- size: `243`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x1401935e0`

## import_xrefs

- `ntoskrnl!SeReleaseSubjectContext` at `0x1401b80c8`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1401b80c8`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1401b80b8`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1401b80b8`
- `ntoskrnl!SeLockSubjectContext` at `0x1401b8041`
- `ntoskrnl!SeLockSubjectContext` at `0x1401b8041`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1401b8031`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1401b8031`
- `ntoskrnl!SeAccessCheck` at `0x1401b80a6`
- `ntoskrnl!SeAccessCheck` at `0x1401b80a6`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1401b805e`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1401b805e`

## pseudocode

```c

```
