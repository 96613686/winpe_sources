# FwspWrite

- ea: `0x1400110e0`
- end: `0x140011120`
- name: `FwspWrite`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x1400110e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400110ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400110ff`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400110f1`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400110f1`

## pseudocode

```c
signed int __fastcall FwspWrite(__int64 a1, const void *a2, DWORD a3, DWORD *a4)
{
  signed int result; // eax

  if ( WriteFile(*(HANDLE *)(a1 + 8), a2, a3, a4, 0) )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    result = (unsigned __int16)result | 0x80070000;
  if ( result >= 0 )
    return -2147467259;
  return result;
}

```

## disassembly

```asm
0x1400110e0  sub     rsp, 38h
0x1400110e4  mov     rcx, [rcx+8]; hFile
0x1400110e8  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x1400110f1  call    cs:__imp_WriteFile
0x1400110f7  test    eax, eax
0x1400110f9  jz      short loc_1400110FF
0x1400110fb  xor     eax, eax
0x1400110fd  jmp     short loc_14001111B
0x1400110ff  call    cs:__imp_GetLastError
0x140011105  test    eax, eax
0x140011107  jle     short loc_140011111
0x140011109  movzx   eax, ax
0x14001110c  or      eax, 80070000h
0x140011111  test    eax, eax
0x140011113  mov     ecx, 80004005h
0x140011118  cmovns  eax, ecx
0x14001111b  add     rsp, 38h
0x14001111f  retn
```
