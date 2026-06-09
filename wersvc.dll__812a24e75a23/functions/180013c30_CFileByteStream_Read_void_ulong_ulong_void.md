# CFileByteStream::Read(void *,ulong,ulong *,void *)

- ea: `0x180013c30`
- end: `0x180013c70`
- name: `?Read@CFileByteStream@@UEAAJPEAXKPEAK0@Z`
- size: `64`
- prototype: `signed int __fastcall(HANDLE *this, void *, DWORD, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180013c30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013c4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013c4f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180013c41`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180013c41`

## pseudocode

```c
signed int __fastcall CFileByteStream::Read(HANDLE *this, void *a2, DWORD a3, unsigned int *a4)
{
  signed int result; // eax

  if ( ReadFile(this[1], a2, a3, a4, 0) )
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
0x180013c30  sub     rsp, 38h
0x180013c34  mov     rcx, [rcx+8]; hFile
0x180013c38  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x180013c41  call    cs:__imp_ReadFile
0x180013c47  test    eax, eax
0x180013c49  jz      short loc_180013C4F
0x180013c4b  xor     eax, eax
0x180013c4d  jmp     short loc_180013C6B
0x180013c4f  call    cs:__imp_GetLastError
0x180013c55  test    eax, eax
0x180013c57  jle     short loc_180013C61
0x180013c59  movzx   eax, ax
0x180013c5c  or      eax, 80070000h
0x180013c61  test    eax, eax
0x180013c63  mov     ecx, 80004005h
0x180013c68  cmovns  eax, ecx
0x180013c6b  add     rsp, 38h
0x180013c6f  retn
```
