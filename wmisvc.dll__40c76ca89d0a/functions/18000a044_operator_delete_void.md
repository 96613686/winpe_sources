# operator delete(void *)

- ea: `0x18000a044`
- end: `0x18000a054`
- name: `??3@YAXPEAX@Z`
- size: `16`
- prototype: `void __fastcall(void *)`
- caller_count: `23`
- callee_count: `0`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000eca0`
- `0x18000f8d0`
- `0x18000f900`
- `0x18000f940`
- `0x18000f978`
- `0x18000fa78`
- `0x18001d54c`
- `0x18001d582`
- `0x18001d92d`
- `0x18001d960`
- `0x18001d9f3`
- `0x18001da17`
- `0x18001da3b`
- `0x18001dba3`
- `0x18001dbeb`
- `0x18001ddb9`
- `0x18001df88`
- `0x18001e7f4`
- `0x18001e8e2`
- `0x18001edfe`
- `0x18001ef9b`
- `0x18001f017`
- `0x18001f075`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000a048`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000a048`

## pseudocode

```c
void __fastcall operator delete(void *a1)
{
  CWin32DefaultArena::WbemMemFree(a1);
}

```

## disassembly

```asm
0x18000a044  sub     rsp, 28h
0x18000a048  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18000a04e  nop
0x18000a04f  add     rsp, 28h
0x18000a053  retn
```
