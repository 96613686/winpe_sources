# VmLoadExtensionDriver(void *)

- ea: `0x14000fb00`
- end: `0x14000fb0f`
- name: `?VmLoadExtensionDriver@@YAXPEAX@Z`
- size: `15`
- prototype: `void __fastcall(void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140003e70`

## pseudocode

```c
void __fastcall VmLoadExtensionDriver(__int64 a1)
{
  VmpRestoreExtensionDriver(a1);
}

```

## disassembly

```asm
0x14000fb00  sub     rsp, 28h
0x14000fb04  call    VmpRestoreExtensionDriver
0x14000fb09  add     rsp, 28h
0x14000fb0d  retn
```
