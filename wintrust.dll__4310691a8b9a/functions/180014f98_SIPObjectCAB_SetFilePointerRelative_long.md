# SIPObjectCAB_::SetFilePointerRelative(long)

- ea: `0x180014f98`
- end: `0x180014fbe`
- name: `?SetFilePointerRelative@SIPObjectCAB_@@AEAAHJ@Z`
- size: `38`
- prototype: `_BOOL8 __fastcall(HANDLE *this, LONG)`
- caller_count: `2`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x1800151a8`
- `0x180015308`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180014fa9`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180014fa9`

## pseudocode

```c
_BOOL8 __fastcall SIPObjectCAB_::SetFilePointerRelative(HANDLE *this, LONG a2)
{
  return SetFilePointer(this[1], a2, 0, 1u) != -1;
}

```

## disassembly

```asm
0x180014f98  sub     rsp, 28h
0x180014f9c  mov     rcx, [rcx+8]; hFile
0x180014fa0  mov     r9d, 1; dwMoveMethod
0x180014fa6  xor     r8d, r8d; lpDistanceToMoveHigh
0x180014fa9  call    cs:__imp_SetFilePointer
0x180014faf  xor     ecx, ecx
0x180014fb1  cmp     eax, 0FFFFFFFFh
0x180014fb4  setnz   cl
0x180014fb7  mov     eax, ecx
0x180014fb9  add     rsp, 28h
0x180014fbd  retn
```
