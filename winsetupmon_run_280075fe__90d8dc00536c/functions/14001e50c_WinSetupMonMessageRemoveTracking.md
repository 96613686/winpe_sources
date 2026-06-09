# WinSetupMonMessageRemoveTracking

- ea: `0x14001e50c`
- end: `0x14001e51b`
- name: `WinSetupMonMessageRemoveTracking`
- size: `15`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140007668`

## callees

- `0x140006f78`

## pseudocode

```c
__int64 WinSetupMonMessageRemoveTracking()
{
  return RemoveTracking();
}

```

## disassembly

```asm
0x14001e50c  sub     rsp, 28h
0x14001e510  call    ?RemoveTracking@@YAJXZ; RemoveTracking(void)
0x14001e515  add     rsp, 28h
0x14001e519  retn
```
