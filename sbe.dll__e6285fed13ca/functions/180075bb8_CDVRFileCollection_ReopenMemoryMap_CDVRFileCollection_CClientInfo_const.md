# CDVRFileCollection::ReopenMemoryMap(CDVRFileCollection::CClientInfo const *)

- ea: `0x180075bb8`
- end: `0x180075fa2`
- name: `?ReopenMemoryMap@CDVRFileCollection@@IEAAJPEBUCClientInfo@1@@Z`
- size: `1002`
- prototype: `__int64 __fastcall(CDVRFileCollection *__hidden this, const struct CDVRFileCollection::CClientInfo *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180074ec4`

## callees

- `0x180001c00`
- `0x180073368`
- `0x180073bd8`
- `0x180073ebc`
- `0x180075bb8`
- `0x18007721c`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180075e68`
- `KERNEL32!CloseHandle` at `0x180075ebd`
- `KERNEL32!CloseHandle` at `0x180075f58`
- `KERNEL32!CloseHandle` at `0x180075f66`
- `KERNEL32!CloseHandle` at `0x1800b56f8`
- `KERNEL32!CloseHandle` at `0x1800b5708`
- `KERNEL32!CloseHandle` at `0x180075e68`
- `KERNEL32!CloseHandle` at `0x180075ebd`
- `KERNEL32!CloseHandle` at `0x180075f58`
- `KERNEL32!CloseHandle` at `0x180075f66`
- `KERNEL32!CloseHandle` at `0x1800b56f8`
- `KERNEL32!CloseHandle` at `0x1800b5708`
- `KERNEL32!GetLastError` at `0x180075c39`
- `KERNEL32!GetLastError` at `0x180075c98`
- `KERNEL32!GetLastError` at `0x180075e47`
- `KERNEL32!GetLastError` at `0x180075c39`
- `KERNEL32!GetLastError` at `0x180075c98`
- `KERNEL32!GetLastError` at `0x180075e47`
- `KERNEL32!GetFileInformationByHandle` at `0x180075c8e`
- `KERNEL32!GetFileInformationByHandle` at `0x180075c8e`
- `KERNEL32!OpenFileMappingW` at `0x180075e08`
- `KERNEL32!OpenFileMappingW` at `0x180075e08`
- `KERNEL32!MapViewOfFile` at `0x180075e9d`
- `KERNEL32!MapViewOfFile` at `0x180075e9d`
- `KERNEL32!CreateFileMappingW` at `0x180075e39`
- `KERNEL32!CreateFileMappingW` at `0x180075e39`
- `KERNEL32!UnmapViewOfFile` at `0x180075ef7`
- `KERNEL32!UnmapViewOfFile` at `0x180075f4a`
- `KERNEL32!UnmapViewOfFile` at `0x1800b56e8`
- `KERNEL32!UnmapViewOfFile` at `0x180075ef7`
- `KERNEL32!UnmapViewOfFile` at `0x180075f4a`
- `KERNEL32!UnmapViewOfFile` at `0x1800b56e8`
- `KERNEL32!CreateFileW` at `0x180075c25`
- `KERNEL32!CreateFileW` at `0x180075c25`

## pseudocode

```c
__int64 __fastcall CDVRFileCollection::ReopenMemoryMap(
        CDVRFileCollection *this,
        const struct CDVRFileCollection::CClientInfo *a2)
{
  HANDLE FileMappingW; // rsi
  char *v5; // r15
  HANDLE FileW; // r14
  signed int LastError; // eax
  signed int SectionName; // ebx
  signed int v9; // eax
  bool v10; // cc
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // r12
  enum _ACCESS_MODE v13; // r8d
  ULONG v14; // ecx
  struct _SECURITY_ATTRIBUTES *p_FileMappingAttributes; // rbx
  void *v16; // rcx
  __int64 v17; // rcx
  enum _ACCESS_MODE dwCreationDisposition; // [rsp+20h] [rbp-158h]
  unsigned int dwFlagsAndAttributes; // [rsp+28h] [rbp-150h]
  void *v21; // [rsp+58h] [rbp-120h] BYREF
  char *v22; // [rsp+60h] [rbp-118h]
  struct _ACL *v23; // [rsp+68h] [rbp-110h] BYREF
  struct _SECURITY_ATTRIBUTES FileMappingAttributes; // [rsp+70h] [rbp-108h] BYREF
  struct _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+88h] [rbp-F0h] BYREF
  WCHAR Name[64]; // [rsp+C0h] [rbp-B8h] BYREF

  FileMappingW = 0;
  v5 = 0;
  v22 = 0;
  FileW = CreateFileW(*((LPCWSTR *)this + 14), 0xC0000000, 7u, 0, 3u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    SectionName = LastError;
    if ( LastError > 0 )
      SectionName = (unsigned __int16)LastError | 0x80070000;
    FileW = 0;
    goto LABEL_38;
  }
  memset(&FileInformation, 0, sizeof(FileInformation));
  if ( !GetFileInformationByHandle(FileW, &FileInformation) )
    goto LABEL_6;
  if ( FileInformation.nFileSizeHigh
    || FileInformation.nFileSizeLow < 568 * (unsigned __int64)*((unsigned int *)this + 2) + 1912 )
  {
    SectionName = -2147467259;
    goto LABEL_38;
  }
  if ( FileInformation.nFileSizeLow <= 0x778
    || (v11 = FileInformation.nFileSizeLow - 1912LL, v12 = v11 / 0x238, v11 != 568 * (v11 / 0x238))
    || (unsigned int)v12 > 0xFFFE )
  {
    SectionName = -2147024883;
    goto LABEL_38;
  }
  SectionName = CDVRFileCollection::CreateSectionName(
                  this,
                  FileInformation.dwVolumeSerialNumber,
                  FileInformation.nFileIndexHigh,
                  FileInformation.nFileIndexLow,
                  *(_DWORD *)(*((_QWORD *)this + 4) + 80LL),
                  dwFlagsAndAttributes,
                  Name);
  if ( SectionName >= 0 )
  {
    v23 = 0;
    v21 = 0;
    memset(&FileMappingAttributes, 0, sizeof(FileMappingAttributes));
    v14 = *((_DWORD *)a2 + 4);
    if ( v14 )
    {
      v9 = CreateACL(v14, *((void ***)a2 + 3), v13, 983047, dwCreationDisposition, 7u, &v23, &v21);
      SectionName = v9;
      v10 = v9 <= 0;
      if ( v9 )
        goto LABEL_7;
      FileMappingAttributes.nLength = 24;
      FileMappingAttributes.lpSecurityDescriptor = v21;
      FileMappingAttributes.bInheritHandle = 0;
      p_FileMappingAttributes = &FileMappingAttributes;
    }
    else
    {
      p_FileMappingAttributes = 0;
    }
    FileMappingW = OpenFileMappingW(6u, 0, Name);
    if ( !FileMappingW )
      FileMappingW = CreateFileMappingW(FileW, p_FileMappingAttributes, 4u, 0, 0, Name);
    SectionName = GetLastError();
    if ( *((_DWORD *)a2 + 4) )
      FreeSecurityDescriptors(&v23, &v21);
    CloseHandle(FileW);
    FileW = 0;
    if ( !FileMappingW )
    {
      if ( SectionName <= 0 )
        goto LABEL_38;
      SectionName = (unsigned __int16)SectionName;
LABEL_9:
      SectionName |= 0x80070000;
      goto LABEL_38;
    }
    v5 = (char *)MapViewOfFile(FileMappingW, 6u, 0, 0, 0);
    v22 = v5;
    if ( !v5 )
    {
LABEL_6:
      v9 = GetLastError();
      SectionName = v9;
      v10 = v9 <= 0;
LABEL_7:
      if ( v10 )
        goto LABEL_38;
      SectionName = (unsigned __int16)v9;
      goto LABEL_9;
    }
    v16 = (void *)*((_QWORD *)this + 6);
    if ( v16 )
      CloseHandle(v16);
    *((_QWORD *)this + 6) = FileMappingW;
    FileMappingW = 0;
    if ( *((char *)this + 172) >= 0
      || (SectionName = CDVRFileCollection::ValidateSharedMemory(
                          (CDVRFileCollection *)v16,
                          (struct CDVRFileCollection::CSharedData *)v5,
                          (struct CDVRFileCollection::CSharedData::CFileInfo *)(v5 + 1912),
                          v12),
          SectionName >= 0) )
    {
      UnmapViewOfFile(*((LPCVOID *)this + 4));
      *((_QWORD *)this + 4) = v5;
      v5 = 0;
      v22 = 0;
      v17 = *((_QWORD *)this + 4);
      *((_QWORD *)this + 5) = v17 + 1912;
      if ( *((char *)this + 172) < 0 )
        *((_DWORD *)this + 2) = v12;
      *((_DWORD *)this + 35) = *(_DWORD *)(v17 + 80);
      SectionName = 0;
    }
  }
LABEL_38:
  if ( v5 )
    UnmapViewOfFile(v5);
  if ( FileMappingW )
    CloseHandle(FileMappingW);
  if ( FileW )
    CloseHandle(FileW);
  return (unsigned int)SectionName;
}

```

## disassembly

```asm
0x180075bb8  mov     [rsp+arg_10], rbx
0x180075bbd  mov     [rsp+arg_18], rsi
0x180075bc2  push    rdi
0x180075bc3  push    r12
0x180075bc5  push    r13
0x180075bc7  push    r14
0x180075bc9  push    r15
0x180075bcb  sub     rsp, 150h
0x180075bd2  mov     rax, cs:__security_cookie
0x180075bd9  xor     rax, rsp
0x180075bdc  mov     [rsp+178h+var_38], rax
0x180075be4  mov     r13, rdx
0x180075be7  mov     rdi, rcx
0x180075bea  xor     ebx, ebx
0x180075bec  mov     [rsp+178h+var_128], rbx
0x180075bf1  mov     esi, ebx
0x180075bf3  mov     [rsp+178h+var_130], rbx
0x180075bf8  mov     r15d, ebx
0x180075bfb  mov     [rsp+178h+var_118], rbx
0x180075c00  mov     [rsp+178h+hTemplateFile], rbx; hTemplateFile
0x180075c05  mov     [rsp+178h+dwFlagsAndAttributes], 80h; unsigned int
0x180075c0d  mov     [rsp+178h+dwCreationDisposition], 3; dwCreationDisposition
0x180075c15  xor     r9d, r9d; lpSecurityAttributes
0x180075c18  mov     edx, 0C0000000h; dwDesiredAccess
0x180075c1d  lea     r8d, [rbx+7]; dwShareMode
0x180075c21  mov     rcx, [rcx+70h]; lpFileName
0x180075c25  call    cs:__imp_CreateFileW
0x180075c2b  mov     r14, rax
0x180075c2e  mov     [rsp+178h+var_128], rax
0x180075c33  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180075c37  jnz     short loc_180075C5F
0x180075c39  call    cs:__imp_GetLastError
0x180075c3f  mov     ebx, eax
0x180075c41  test    eax, eax
0x180075c43  jle     short loc_180075C4E
0x180075c45  movzx   ebx, ax
0x180075c48  or      ebx, 80070000h
0x180075c4e  mov     [rsp+178h+var_138], ebx
0x180075c52  xor     r14d, r14d
0x180075c55  mov     [rsp+178h+var_128], r14
0x180075c5a  jmp     loc_180075F42
0x180075c5f  xorps   xmm0, xmm0
0x180075c62  xor     eax, eax
0x180075c64  movups  xmmword ptr [rsp+178h+FileInformation.dwFileAttributes], xmm0
0x180075c6c  movups  xmmword ptr [rsp+178h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x180075c74  movups  xmmword ptr [rsp+178h+FileInformation.nFileSizeHigh], xmm0
0x180075c7c  mov     [rsp+178h+FileInformation.nFileIndexLow], eax
0x180075c83  lea     rdx, [rsp+178h+FileInformation]; lpFileInformation
0x180075c8b  mov     rcx, r14; hFile
0x180075c8e  call    cs:__imp_GetFileInformationByHandle
0x180075c94  test    eax, eax
0x180075c96  jnz     short loc_180075CB6
0x180075c98  call    cs:__imp_GetLastError
0x180075c9e  mov     ebx, eax
0x180075ca0  test    eax, eax
0x180075ca2  jle     loc_180075F3E
0x180075ca8  movzx   ebx, ax
0x180075cab  or      ebx, 80070000h
0x180075cb1  jmp     loc_180075F3E
0x180075cb6  cmp     [rsp+178h+FileInformation.nFileSizeHigh], ebx
0x180075cbd  ja      loc_180075F39
0x180075cc3  mov     eax, [rdi+8]
0x180075cc6  imul    rcx, rax, 238h
0x180075ccd  mov     r8d, 778h
0x180075cd3  add     rcx, r8
0x180075cd6  mov     edx, [rsp+178h+FileInformation.nFileSizeLow]
0x180075cdd  mov     eax, edx
0x180075cdf  cmp     rdx, rcx
0x180075ce2  jb      loc_180075F39
0x180075ce8  cmp     edx, r8d
0x180075ceb  jbe     loc_180075F32
0x180075cf1  lea     rcx, [rdx-778h]
0x180075cf8  mov     rax, 0CD85689039B0AD13h
0x180075d02  mul     rcx
0x180075d05  mov     r12, rcx
0x180075d08  sub     r12, rdx
0x180075d0b  shr     r12, 1
0x180075d0e  add     r12, rdx
0x180075d11  shr     r12, 9
0x180075d15  imul    rax, r12, 238h
0x180075d1c  cmp     rcx, rax
0x180075d1f  jnz     loc_180075F32
0x180075d25  cmp     r12d, 0FFFEh
0x180075d2c  ja      loc_180075F32
0x180075d32  mov     rax, [rdi+20h]
0x180075d36  lea     rcx, [rsp+178h+Name]
0x180075d3e  mov     [rsp+178h+hTemplateFile], rcx; Buffer
0x180075d43  mov     eax, [rax+50h]
0x180075d46  mov     [rsp+178h+dwCreationDisposition], eax; enum _ACCESS_MODE
0x180075d4a  mov     r9d, [rsp+178h+FileInformation.nFileIndexLow]; unsigned int
0x180075d52  mov     r8d, [rsp+178h+FileInformation.nFileIndexHigh]; unsigned int
0x180075d5a  mov     edx, [rsp+178h+FileInformation.dwVolumeSerialNumber]; unsigned int
0x180075d61  mov     rcx, rdi; this
0x180075d64  call    ?CreateSectionName@CDVRFileCollection@@AEAAJKKKKKPEAG@Z; CDVRFileCollection::CreateSectionName(ulong,ulong,ulong,ulong,ulong,ushort *)
0x180075d69  mov     ebx, eax
0x180075d6b  test    eax, eax
0x180075d6d  jns     short loc_180075D78
0x180075d6f  mov     [rsp+178h+var_138], eax
0x180075d73  jmp     loc_180075F42
0x180075d78  mov     [rsp+178h+var_110], 0
0x180075d81  mov     [rsp+178h+var_120], 0
0x180075d8a  xorps   xmm0, xmm0
0x180075d8d  xor     eax, eax
0x180075d8f  movups  xmmword ptr [rsp+178h+FileMappingAttributes.nLength], xmm0
0x180075d94  mov     qword ptr [rsp+178h+FileMappingAttributes.bInheritHandle], rax
0x180075d9c  mov     ecx, [r13+10h]; cCountOfExplicitEntries
0x180075da0  test    ecx, ecx
0x180075da2  jz      short loc_180075DF9
0x180075da4  lea     rax, [rsp+178h+var_120]
0x180075da9  mov     [rsp+178h+var_140], rax; void **
0x180075dae  lea     rax, [rsp+178h+var_110]
0x180075db3  mov     [rsp+178h+hTemplateFile], rax; struct _ACL **
0x180075db8  mov     [rsp+178h+dwFlagsAndAttributes], 7; unsigned int
0x180075dc0  mov     r9d, 0F0007h; unsigned int
0x180075dc6  mov     rdx, [r13+18h]; void **
0x180075dca  call    ?CreateACL@@YAKKPEAPEAXW4_ACCESS_MODE@@K1KAEAPEAU_ACL@@AEAPEAX@Z; CreateACL(ulong,void * *,_ACCESS_MODE,ulong,_ACCESS_MODE,ulong,_ACL * &,void * &)
0x180075dcf  mov     ebx, eax
0x180075dd1  test    eax, eax
0x180075dd3  jnz     loc_180075CA2
0x180075dd9  mov     [rsp+178h+FileMappingAttributes.nLength], 18h
0x180075de1  mov     rax, [rsp+178h+var_120]
0x180075de6  mov     [rsp+178h+FileMappingAttributes.lpSecurityDescriptor], rax
0x180075deb  mov     [rsp+178h+FileMappingAttributes.bInheritHandle], ebx
0x180075df2  lea     rbx, [rsp+178h+FileMappingAttributes]
0x180075df7  jmp     short loc_180075DFB
0x180075df9  xor     ebx, ebx
0x180075dfb  lea     r8, [rsp+178h+Name]; lpName
0x180075e03  xor     edx, edx; bInheritHandle
0x180075e05  lea     ecx, [rdx+6]; dwDesiredAccess
0x180075e08  call    cs:__imp_OpenFileMappingW
0x180075e0e  mov     rsi, rax
0x180075e11  mov     [rsp+178h+var_130], rax
0x180075e16  test    rax, rax
0x180075e19  jnz     short loc_180075E47
0x180075e1b  lea     rax, [rsp+178h+Name]
0x180075e23  mov     qword ptr [rsp+178h+dwFlagsAndAttributes], rax; lpName
0x180075e28  mov     [rsp+178h+dwCreationDisposition], esi; dwMaximumSizeLow
0x180075e2c  xor     r9d, r9d; dwMaximumSizeHigh
0x180075e2f  lea     r8d, [rsi+4]; flProtect
0x180075e33  mov     rdx, rbx; lpFileMappingAttributes
0x180075e36  mov     rcx, r14; hFile
0x180075e39  call    cs:__imp_CreateFileMappingW
0x180075e3f  mov     rsi, rax
0x180075e42  mov     [rsp+178h+var_130], rax
0x180075e47  call    cs:__imp_GetLastError
0x180075e4d  mov     ebx, eax
0x180075e4f  cmp     dword ptr [r13+10h], 0
0x180075e54  jbe     short loc_180075E65
0x180075e56  lea     rdx, [rsp+178h+var_120]; void **
0x180075e5b  lea     rcx, [rsp+178h+var_110]; struct _ACL **
0x180075e60  call    ?FreeSecurityDescriptors@@YAXAEAPEAU_ACL@@AEAPEAX@Z; FreeSecurityDescriptors(_ACL * &,void * &)
0x180075e65  mov     rcx, r14; hObject
0x180075e68  call    cs:__imp_CloseHandle
0x180075e6e  xor     r14d, r14d
0x180075e71  mov     [rsp+178h+var_128], r14
0x180075e76  test    rsi, rsi
0x180075e79  jnz     short loc_180075E8B
0x180075e7b  test    ebx, ebx
0x180075e7d  jle     loc_180075F3E
0x180075e83  movzx   ebx, bx
0x180075e86  jmp     loc_180075CAB
0x180075e8b  mov     qword ptr [rsp+178h+dwCreationDisposition], r14; dwNumberOfBytesToMap
0x180075e90  xor     r9d, r9d; dwFileOffsetLow
0x180075e93  xor     r8d, r8d; dwFileOffsetHigh
0x180075e96  lea     edx, [r9+6]; dwDesiredAccess
0x180075e9a  mov     rcx, rsi; hFileMappingObject
0x180075e9d  call    cs:__imp_MapViewOfFile
0x180075ea3  mov     r15, rax
0x180075ea6  mov     [rsp+178h+var_118], rax
0x180075eab  test    rax, rax
0x180075eae  jz      loc_180075C98
0x180075eb4  mov     rcx, [rdi+30h]; hObject
0x180075eb8  test    rcx, rcx
0x180075ebb  jz      short loc_180075EC3
0x180075ebd  call    cs:__imp_CloseHandle
0x180075ec3  mov     [rdi+30h], rsi
0x180075ec7  xor     esi, esi
0x180075ec9  mov     [rsp+178h+var_130], rsi
0x180075ece  test    byte ptr [rdi+0ACh], 80h
0x180075ed5  jz      short loc_180075EF3
0x180075ed7  lea     r8, [r15+778h]; struct CDVRFileCollection::CSharedData::CFileInfo *
0x180075ede  mov     r9d, r12d; unsigned int
0x180075ee1  mov     rdx, r15; struct CDVRFileCollection::CSharedData *
0x180075ee4  call    ?ValidateSharedMemory@CDVRFileCollection@@IEAAJPEAUCSharedData@1@PEAUCFileInfo@21@K@Z; CDVRFileCollection::ValidateSharedMemory(CDVRFileCollection::CSharedData *,CDVRFileCollection::CSharedData::CFileInfo *,ulong)
0x180075ee9  mov     ebx, eax
0x180075eeb  test    eax, eax
0x180075eed  js      loc_180075D6F
0x180075ef3  mov     rcx, [rdi+20h]; lpBaseAddress
0x180075ef7  call    cs:__imp_UnmapViewOfFile
0x180075efd  mov     [rdi+20h], r15
0x180075f01  xor     r15d, r15d
0x180075f04  mov     [rsp+178h+var_118], r15
0x180075f09  mov     rcx, [rdi+20h]
0x180075f0d  lea     rax, [rcx+778h]
0x180075f14  mov     [rdi+28h], rax
0x180075f18  test    byte ptr [rdi+0ACh], 80h
0x180075f1f  jz      short loc_180075F25
0x180075f21  mov     [rdi+8], r12d
0x180075f25  mov     eax, [rcx+50h]
0x180075f28  mov     [rdi+8Ch], eax
0x180075f2e  xor     ebx, ebx
0x180075f30  jmp     short loc_180075F3E
0x180075f32  mov     ebx, 8007000Dh
0x180075f37  jmp     short loc_180075F3E
0x180075f39  mov     ebx, 80004005h
0x180075f3e  mov     [rsp+178h+var_138], ebx
0x180075f42  test    r15, r15
0x180075f45  jz      short loc_180075F50
0x180075f47  mov     rcx, r15; lpBaseAddress
0x180075f4a  call    cs:__imp_UnmapViewOfFile
0x180075f50  test    rsi, rsi
0x180075f53  jz      short loc_180075F5E
0x180075f55  mov     rcx, rsi; hObject
0x180075f58  call    cs:__imp_CloseHandle
0x180075f5e  test    r14, r14
0x180075f61  jz      short loc_180075F6C
0x180075f63  mov     rcx, r14; hObject
0x180075f66  call    cs:__imp_CloseHandle
0x180075f6c  jmp     short loc_180075F73
0x180075f6e  mov     ebx, 0C0000005h
0x180075f73  mov     eax, ebx
0x180075f75  mov     rcx, [rsp+178h+var_38]
0x180075f7d  xor     rcx, rsp; StackCookie
0x180075f80  call    __security_check_cookie
0x180075f85  lea     r11, [rsp+178h+var_28]
0x180075f8d  mov     rbx, [r11+40h]
0x180075f91  mov     rsi, [r11+48h]
0x180075f95  mov     rsp, r11
0x180075f98  pop     r15
0x180075f9a  pop     r14
0x180075f9c  pop     r13
0x180075f9e  pop     r12
0x180075fa0  pop     rdi
0x180075fa1  retn
0x1800b56d6  push    rbp
0x1800b56d8  sub     rsp, 40h
0x1800b56dc  mov     rbp, rdx
0x1800b56df  mov     rcx, [rbp+60h]; lpBaseAddress
0x1800b56e3  test    rcx, rcx
0x1800b56e6  jz      short loc_1800B56EF
0x1800b56e8  call    cs:__imp_UnmapViewOfFile
0x1800b56ee  nop
0x1800b56ef  mov     rcx, [rbp+48h]; hObject
0x1800b56f3  test    rcx, rcx
0x1800b56f6  jz      short loc_1800B56FF
0x1800b56f8  call    cs:__imp_CloseHandle
0x1800b56fe  nop
0x1800b56ff  mov     rcx, [rbp+50h]; hObject
0x1800b5703  test    rcx, rcx
0x1800b5706  jz      short loc_1800B570F
0x1800b5708  call    cs:__imp_CloseHandle
0x1800b570e  nop
0x1800b570f  add     rsp, 40h
0x1800b5713  pop     rbp
0x1800b5714  retn
0x1800b5716  push    rbp
0x1800b5718  sub     rsp, 40h
0x1800b571c  mov     rbp, rdx
0x1800b571f  mov     rax, [rcx]
0x1800b5722  xor     ecx, ecx
0x1800b5724  cmp     dword ptr [rax], 0C0000005h
0x1800b572a  setz    cl
0x1800b572d  mov     eax, ecx
0x1800b572f  add     rsp, 40h
0x1800b5733  pop     rbp
0x1800b5734  retn
```
