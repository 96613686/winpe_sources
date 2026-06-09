# VmUnloadExtensionDriver(void *)

- ea: `0x14000fbe0`
- end: `0x14000fbef`
- name: `?VmUnloadExtensionDriver@@YAXPEAX@Z`
- size: `15`
- prototype: `void __fastcall(void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140003ef0`

## pseudocode

```c
void __fastcall VmUnloadExtensionDriver(__int64 a1)
{
  VmpPageExtensionDriver(a1);
}

```

## disassembly

```asm
0x14000fbe0  sub     rsp, 28h
0x14000fbe4  call    VmpPageExtensionDriver
0x14000fbe9  add     rsp, 28h
0x14000fbed  retn
```
