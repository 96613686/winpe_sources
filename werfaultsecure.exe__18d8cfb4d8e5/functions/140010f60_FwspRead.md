# FwspRead

- ea: `0x140010f60`
- end: `0x140010fa0`
- name: `FwspRead`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x140010f60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010f7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010f7f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x140010f71`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x140010f71`

## pseudocode

```c
signed int __fastcall FwspRead(__int64 a1, void *a2, DWORD a3, DWORD *a4)
{
  signed int result; // eax

  if ( ReadFile(*(HANDLE *)(a1 + 8), a2, a3, a4, 0) )
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
0x140010f60  sub     rsp, 38h
0x140010f64  mov     rcx, [rcx+8]; hFile
0x140010f68  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x140010f71  call    cs:__imp_ReadFile
0x140010f77  test    eax, eax
0x140010f79  jz      short loc_140010F7F
0x140010f7b  xor     eax, eax
0x140010f7d  jmp     short loc_140010F9B
0x140010f7f  call    cs:__imp_GetLastError
0x140010f85  test    eax, eax
0x140010f87  jle     short loc_140010F91
0x140010f89  movzx   eax, ax
0x140010f8c  or      eax, 80070000h
0x140010f91  test    eax, eax
0x140010f93  mov     ecx, 80004005h
0x140010f98  cmovns  eax, ecx
0x140010f9b  add     rsp, 38h
0x140010f9f  retn
```
