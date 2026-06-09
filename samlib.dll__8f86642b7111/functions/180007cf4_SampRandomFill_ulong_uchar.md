# SampRandomFill(ulong,uchar *)

- ea: `0x180007cf4`
- end: `0x180007d16`
- name: `?SampRandomFill@@YAJKPEAE@Z`
- size: `34`
- prototype: `__int64 __fastcall(ULONG RandomBufferLength, PVOID RandomBuffer)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180007e00`
- `0x180009a34`
- `0x180009b38`
- `0x180009fe8`

## import_xrefs

- `CRYPTBASE!SystemFunction036` at `0x180007d00`
- `CRYPTBASE!SystemFunction036` at `0x180007d00`

## pseudocode

```c
__int64 __fastcall SampRandomFill(ULONG RandomBufferLength, PVOID RandomBuffer)
{
  return SystemFunction036(RandomBuffer, RandomBufferLength) == 0 ? 0xC0000001 : 0;
}

```

## disassembly

```asm
0x180007cf4  sub     rsp, 28h
0x180007cf8  mov     rax, rdx
0x180007cfb  mov     edx, ecx; RandomBufferLength
0x180007cfd  mov     rcx, rax; RandomBuffer
0x180007d00  call    cs:__imp_SystemFunction036
0x180007d06  neg     al
0x180007d08  sbb     eax, eax
0x180007d0a  not     eax
0x180007d0c  and     eax, 0C0000001h
0x180007d11  add     rsp, 28h
0x180007d15  retn
```
