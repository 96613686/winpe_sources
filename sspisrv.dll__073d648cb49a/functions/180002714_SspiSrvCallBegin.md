# SspiSrvCallBegin

- ea: `0x180002714`
- end: `0x180002737`
- name: `SspiSrvCallBegin`
- size: `35`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180002950`
- `0x180002a20`
- `0x180002a70`
- `0x180002ad0`
- `0x180002b20`
- `0x180002c40`
- `0x180002d20`
- `0x180002f20`

## callees

- `0x180002714`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x180002725`
- `ntdll!EtwEventActivityIdControl` at `0x180002725`

## pseudocode

```c
__int64 __fastcall SspiSrvCallBegin(__int64 a1)
{
  __int64 result; // rax

  if ( a1 )
    return EtwEventActivityIdControl(2, a1);
  return result;
}

```

## disassembly

```asm
0x180002714  sub     rsp, 28h
0x180002718  test    rcx, rcx
0x18000271b  jz      short loc_180002731
0x18000271d  mov     rdx, rcx
0x180002720  mov     ecx, 2
0x180002725  call    cs:__imp_EtwEventActivityIdControl
0x18000272c  nop     dword ptr [rax+rax+00h]
0x180002731  add     rsp, 28h
0x180002735  retn
```
