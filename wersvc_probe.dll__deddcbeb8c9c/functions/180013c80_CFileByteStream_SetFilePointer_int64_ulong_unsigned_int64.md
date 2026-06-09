# CFileByteStream::SetFilePointer(__int64,ulong,unsigned __int64 *)

- ea: `0x180013c80`
- end: `0x180013cdb`
- name: `?SetFilePointer@CFileByteStream@@UEAAJ_JKPEA_K@Z`
- size: `91`
- prototype: `int(CFileByteStream *__hidden this, __int64, unsigned int, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180013c80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013ca8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013ca8`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180013c9e`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180013c9e`

## pseudocode

```c
int __fastcall CFileByteStream::SetFilePointer(
        CFileByteStream *this,
        LARGE_INTEGER a2,
        DWORD a3,
        union _LARGE_INTEGER *a4)
{
  void *v4; // rcx
  int result; // eax
  union _LARGE_INTEGER NewFilePointer; // [rsp+30h] [rbp+8h] BYREF

  v4 = (void *)*((_QWORD *)this + 1);
  NewFilePointer.QuadPart = 0;
  if ( SetFilePointerEx(v4, a2, &NewFilePointer, a3) )
  {
    if ( a4 )
      *a4 = NewFilePointer;
    return 0;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      result = (unsigned __int16)result | 0x80070000;
    if ( result >= 0 )
      return -2147467259;
  }
  return result;
}

```

## disassembly

```asm
0x180013c80  push    rbx
0x180013c82  sub     rsp, 20h
0x180013c86  mov     rcx, [rcx+8]; hFile
0x180013c8a  mov     rbx, r9
0x180013c8d  mov     r9d, r8d; dwMoveMethod
0x180013c90  mov     qword ptr [rsp+28h+NewFilePointer], 0
0x180013c99  lea     r8, [rsp+28h+NewFilePointer]; lpNewFilePointer
0x180013c9e  call    cs:__imp_SetFilePointerEx
0x180013ca4  test    eax, eax
0x180013ca6  jnz     short loc_180013CC6
0x180013ca8  call    cs:__imp_GetLastError
0x180013cae  test    eax, eax
0x180013cb0  jle     short loc_180013CBA
0x180013cb2  movzx   eax, ax
0x180013cb5  or      eax, 80070000h
0x180013cba  test    eax, eax
0x180013cbc  mov     ecx, 80004005h
0x180013cc1  cmovns  eax, ecx
0x180013cc4  jmp     short loc_180013CD5
0x180013cc6  test    rbx, rbx
0x180013cc9  jz      short loc_180013CD3
0x180013ccb  mov     rax, qword ptr [rsp+28h+NewFilePointer]
0x180013cd0  mov     [rbx], rax
0x180013cd3  xor     eax, eax
0x180013cd5  add     rsp, 20h
0x180013cd9  pop     rbx
0x180013cda  retn
```
