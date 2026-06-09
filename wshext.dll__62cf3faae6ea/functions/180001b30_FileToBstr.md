# FileToBstr

- ea: `0x180001b30`
- end: `0x180001c0e`
- name: `FileToBstr`
- size: `222`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180001300`
- `0x180001490`
- `0x180009a90`
- `0x180009be0`

## callees

- `0x1800019e0`
- `0x180001b30`
- `0x1800031f4`
- `0x180003200`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180001bd5`
- `KERNEL32!GetLastError` at `0x180001bfd`
- `KERNEL32!GetLastError` at `0x180001bd5`
- `KERNEL32!GetLastError` at `0x180001bfd`
- `KERNEL32!ReadFile` at `0x180001ba0`
- `KERNEL32!ReadFile` at `0x180001ba0`
- `KERNEL32!SetFilePointer` at `0x180001b7f`
- `KERNEL32!SetFilePointer` at `0x180001b7f`
- `KERNEL32!GetFileSize` at `0x180001b50`
- `KERNEL32!GetFileSize` at `0x180001b50`
- `KERNEL32!SetLastError` at `0x180001be7`
- `KERNEL32!SetLastError` at `0x180001be7`

## pseudocode

```c
__int64 __fastcall FileToBstr(HANDLE hFile, __int64 a2)
{
  DWORD FileSize; // eax
  DWORD v5; // edi
  void *v6; // rbx
  DWORD LastError; // edi
  DWORD NumberOfBytesRead; // [rsp+80h] [rbp+18h] BYREF

  NumberOfBytesRead = 0;
  FileSize = GetFileSize(hFile, 0);
  v5 = FileSize;
  if ( FileSize == -1 )
  {
    LastError = GetLastError();
  }
  else
  {
    v6 = operator new(FileSize);
    if ( v6 )
    {
      if ( SetFilePointer(hFile, 0, 0, 0) != -1
        && ReadFile(hFile, v6, v5, &NumberOfBytesRead, 0)
        && (unsigned int)ConvertTextToUnicode(v6, v5, a2) )
      {
        operator delete(v6);
        return 1;
      }
      LastError = GetLastError();
      operator delete(v6);
    }
    else
    {
      LastError = 8;
    }
  }
  SetLastError(LastError);
  return 0;
}

```

## disassembly

```asm
0x180001b30  push    rbx
0x180001b32  push    rbp
0x180001b33  push    rsi
0x180001b34  push    rdi
0x180001b35  push    r14
0x180001b37  push    r15
0x180001b39  sub     rsp, 38h
0x180001b3d  mov     rbp, rdx
0x180001b40  xor     r15d, r15d
0x180001b43  xor     edx, edx; lpFileSizeHigh
0x180001b45  mov     [rsp+68h+NumberOfBytesRead], r15d
0x180001b4d  mov     rsi, rcx
0x180001b50  call    cs:__imp_GetFileSize
0x180001b56  mov     edi, eax
0x180001b58  cmp     eax, 0FFFFFFFFh
0x180001b5b  jz      loc_180001BFD
0x180001b61  mov     ecx, edi; Size
0x180001b63  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001b68  mov     rbx, rax
0x180001b6b  test    rax, rax
0x180001b6e  jz      loc_180001C07
0x180001b74  xor     r9d, r9d; dwMoveMethod
0x180001b77  xor     r8d, r8d; lpDistanceToMoveHigh
0x180001b7a  xor     edx, edx; lDistanceToMove
0x180001b7c  mov     rcx, rsi; hFile
0x180001b7f  call    cs:__imp_SetFilePointer
0x180001b85  cmp     eax, 0FFFFFFFFh
0x180001b88  jz      short loc_180001BD5
0x180001b8a  lea     r9, [rsp+68h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180001b92  mov     [rsp+68h+lpOverlapped], r15; lpOverlapped
0x180001b97  mov     r8d, edi; nNumberOfBytesToRead
0x180001b9a  mov     rdx, rbx; lpBuffer
0x180001b9d  mov     rcx, rsi; hFile
0x180001ba0  call    cs:__imp_ReadFile
0x180001ba6  test    eax, eax
0x180001ba8  jz      short loc_180001BD5
0x180001baa  mov     r8, rbp
0x180001bad  mov     edx, edi
0x180001baf  mov     rcx, rbx
0x180001bb2  call    ConvertTextToUnicode
0x180001bb7  test    eax, eax
0x180001bb9  jz      short loc_180001BD5
0x180001bbb  mov     rcx, rbx; Block
0x180001bbe  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001bc3  mov     eax, 1
0x180001bc8  add     rsp, 38h
0x180001bcc  pop     r15
0x180001bce  pop     r14
0x180001bd0  pop     rdi
0x180001bd1  pop     rsi
0x180001bd2  pop     rbp
0x180001bd3  pop     rbx
0x180001bd4  retn
0x180001bd5  call    cs:__imp_GetLastError
0x180001bdb  mov     rcx, rbx; Block
0x180001bde  mov     edi, eax
0x180001be0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001be5  mov     ecx, edi; dwErrCode
0x180001be7  call    cs:__imp_SetLastError
0x180001bed  mov     eax, r15d
0x180001bf0  add     rsp, 38h
0x180001bf4  pop     r15
0x180001bf6  pop     r14
0x180001bf8  pop     rdi
0x180001bf9  pop     rsi
0x180001bfa  pop     rbp
0x180001bfb  pop     rbx
0x180001bfc  retn
0x180001bfd  call    cs:__imp_GetLastError
0x180001c03  mov     edi, eax
0x180001c05  jmp     short loc_180001BE5
0x180001c07  mov     edi, 8
0x180001c0c  jmp     short loc_180001BE5
```
