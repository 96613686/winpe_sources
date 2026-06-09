# SIPObjectPE_::PutMessageInFile(SIP_SUBJECTINFO_ *,_WIN_CERTIFICATE *,ulong *)

- ea: `0x18003dec0`
- end: `0x18003dfca`
- name: `?PutMessageInFile@SIPObjectPE_@@MEAAHPEAUSIP_SUBJECTINFO_@@PEAU_WIN_CERTIFICATE@@PEAK@Z`
- size: `266`
- prototype: `__int64 __fastcall(SIPObjectPE_ *this, struct SIP_SUBJECTINFO_ *, struct _WIN_CERTIFICATE *, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x18003dec0`
- `0x18004de6a`
- `0x18004deb0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18003df0b`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18003df0b`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18003df63`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18003df63`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003df9e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003df9e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003def7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003def7`
- `imagehlp!ImageAddCertificate` at `0x18003df41`
- `imagehlp!ImageAddCertificate` at `0x18003df41`

## pseudocode

```c
__int64 __fastcall SIPObjectPE_::PutMessageInFile(
        SIPObjectPE_ *this,
        struct SIP_SUBJECTINFO_ *a2,
        struct _WIN_CERTIFICATE *a3,
        unsigned int *a4)
{
  bool v4; // zf
  DWORD LowPart; // edi
  DWORD v9; // ebx
  unsigned int v10; // esi
  DWORD v11; // ebx
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-48h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+38h] [rbp-40h] BYREF
  _BYTE Buffer[8]; // [rsp+40h] [rbp-38h] BYREF

  v4 = *((_DWORD *)this + 14) == 0;
  FileSize.QuadPart = 0;
  if ( !v4 )
  {
    SetLastError(0x80092025);
    return 0;
  }
  if ( !GetFileSizeEx(*((HANDLE *)this + 1), &FileSize) )
    return 0;
  if ( FileSize.HighPart )
    return 0;
  LowPart = FileSize.LowPart;
  v9 = FileSize.LowPart + 7;
  if ( FileSize.LowPart + 7 < FileSize.LowPart )
    return 0;
  if ( FileSize.LowPart + a3->dwLength < FileSize.LowPart )
    return 0;
  v10 = ImageAddCertificate(*((HANDLE *)this + 1), a3, a4);
  if ( v10 )
  {
    v11 = (v9 & 0xFFFFFFF8) - LowPart;
    if ( v11 )
    {
      if ( !SetFilePointerEx(*((HANDLE *)this + 1), FileSize, 0, 0) )
        return 0;
      NumberOfBytesWritten = 0;
      memset_0(Buffer, 0, v11);
      if ( !WriteFile(*((HANDLE *)this + 1), Buffer, v11, &NumberOfBytesWritten, 0) || NumberOfBytesWritten != v11 )
        return 0;
    }
  }
  return v10;
}

```

## disassembly

```asm
0x18003dec0  push    rbx
0x18003dec2  push    rbp
0x18003dec3  push    rsi
0x18003dec4  push    rdi
0x18003dec5  push    r14
0x18003dec7  sub     rsp, 50h
0x18003decb  mov     rax, cs:__security_cookie
0x18003ded2  xor     rax, rsp
0x18003ded5  mov     [rsp+78h+var_30], rax
0x18003deda  cmp     dword ptr [rcx+38h], 0
0x18003dede  mov     r14, r9
0x18003dee1  mov     rsi, r8
0x18003dee4  mov     qword ptr [rsp+78h+FileSize], 0
0x18003deed  mov     rbp, rcx
0x18003def0  jz      short loc_18003DF02
0x18003def2  mov     ecx, 80092025h; dwErrCode
0x18003def7  call    cs:__imp_SetLastError
0x18003defd  jmp     loc_18003DFAE
0x18003df02  mov     rcx, [rcx+8]; hFile
0x18003df06  lea     rdx, [rsp+78h+FileSize]; lpFileSize
0x18003df0b  call    cs:__imp_GetFileSizeEx
0x18003df11  test    eax, eax
0x18003df13  jz      loc_18003DFAE
0x18003df19  cmp     dword ptr [rsp+78h+FileSize+4], 0
0x18003df1e  jnz     loc_18003DFAE
0x18003df24  mov     edi, dword ptr [rsp+78h+FileSize]
0x18003df28  lea     ebx, [rdi+7]
0x18003df2b  cmp     ebx, edi
0x18003df2d  jb      short loc_18003DFAE
0x18003df2f  mov     ecx, [rsi]
0x18003df31  add     ecx, edi
0x18003df33  cmp     ecx, edi
0x18003df35  jb      short loc_18003DFAE
0x18003df37  mov     rcx, [rbp+8]; FileHandle
0x18003df3b  mov     r8, r14; Index
0x18003df3e  mov     rdx, rsi; Certificate
0x18003df41  call    cs:__imp_ImageAddCertificate
0x18003df47  mov     esi, eax
0x18003df49  test    eax, eax
0x18003df4b  jz      short loc_18003DFB0
0x18003df4d  and     ebx, 0FFFFFFF8h
0x18003df50  sub     ebx, edi
0x18003df52  jz      short loc_18003DFB0
0x18003df54  mov     rdx, qword ptr [rsp+78h+FileSize]; liDistanceToMove
0x18003df59  xor     r9d, r9d; dwMoveMethod
0x18003df5c  mov     rcx, [rbp+8]; hFile
0x18003df60  xor     r8d, r8d; lpNewFilePointer
0x18003df63  call    cs:__imp_SetFilePointerEx
0x18003df69  test    eax, eax
0x18003df6b  jz      short loc_18003DFAE
0x18003df6d  mov     r8d, ebx; Size
0x18003df70  lea     rcx, [rsp+78h+Buffer]; void *
0x18003df75  xor     edx, edx; Val
0x18003df77  mov     [rsp+78h+NumberOfBytesWritten], 0
0x18003df7f  call    memset_0
0x18003df84  mov     rcx, [rbp+8]; hFile
0x18003df88  lea     r9, [rsp+78h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18003df8d  mov     r8d, ebx; nNumberOfBytesToWrite
0x18003df90  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x18003df99  lea     rdx, [rsp+78h+Buffer]; lpBuffer
0x18003df9e  call    cs:__imp_WriteFile
0x18003dfa4  test    eax, eax
0x18003dfa6  jz      short loc_18003DFAE
0x18003dfa8  cmp     [rsp+78h+NumberOfBytesWritten], ebx
0x18003dfac  jz      short loc_18003DFB0
0x18003dfae  xor     esi, esi
0x18003dfb0  mov     eax, esi
0x18003dfb2  mov     rcx, [rsp+78h+var_30]
0x18003dfb7  xor     rcx, rsp; StackCookie
0x18003dfba  call    __security_check_cookie
0x18003dfbf  add     rsp, 50h
0x18003dfc3  pop     r14
0x18003dfc5  pop     rdi
0x18003dfc6  pop     rsi
0x18003dfc7  pop     rbp
0x18003dfc8  pop     rbx
0x18003dfc9  retn
```
