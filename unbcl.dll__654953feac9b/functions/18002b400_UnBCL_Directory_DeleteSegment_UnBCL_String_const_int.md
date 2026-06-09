# UnBCL::Directory::DeleteSegment(UnBCL::String const *,int)

- ea: `0x18002b400`
- end: `0x18002b9f8`
- name: `?DeleteSegment@Directory@UnBCL@@CAXPEBVString@2@H@Z`
- size: `1528`
- prototype: `void __fastcall(LPCWSTR *, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x180029b30`

## callees

- `0x1800015ac`
- `0x18000225c`
- `0x180009e7c`
- `0x18002b400`
- `0x1800477d0`
- `0x18005b790`
- `0x18005b9f0`
- `0x180064090`
- `0x180069020`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002b5a6`
- `msvcrt!_wcsicmp` at `0x18002b5a6`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002b5b7`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002b91d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002b94c`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002b5b7`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002b91d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002b94c`
- `ntdll!NtSetInformationFile` at `0x18002b65a`
- `ntdll!NtSetInformationFile` at `0x18002b689`
- `ntdll!NtSetInformationFile` at `0x18002b65a`
- `ntdll!NtSetInformationFile` at `0x18002b689`
- `ntdll!RtlNtStatusToDosError` at `0x18002b6d7`
- `ntdll!RtlNtStatusToDosError` at `0x18002b6d7`
- `KERNEL32!CloseHandle` at `0x18002b492`
- `KERNEL32!CloseHandle` at `0x18002b69b`
- `KERNEL32!CloseHandle` at `0x18002b492`
- `KERNEL32!CloseHandle` at `0x18002b69b`
- `KERNEL32!SetFileInformationByHandle` at `0x18002b626`
- `KERNEL32!SetFileInformationByHandle` at `0x18002b626`
- `KERNEL32!GetLastError` at `0x18002b482`
- `KERNEL32!GetLastError` at `0x18002b72e`
- `KERNEL32!GetLastError` at `0x18002b785`
- `KERNEL32!GetLastError` at `0x18002b82a`
- `KERNEL32!GetLastError` at `0x18002b9b8`
- `KERNEL32!GetLastError` at `0x18002b482`
- `KERNEL32!GetLastError` at `0x18002b72e`
- `KERNEL32!GetLastError` at `0x18002b785`
- `KERNEL32!GetLastError` at `0x18002b82a`
- `KERNEL32!GetLastError` at `0x18002b9b8`
- `KERNEL32!GetFileInformationByHandleEx` at `0x18002b605`
- `KERNEL32!GetFileInformationByHandleEx` at `0x18002b605`
- `KERNEL32!GetFileInformationByHandle` at `0x18002b5e6`
- `KERNEL32!GetFileInformationByHandle` at `0x18002b5e6`
- `KERNEL32!RemoveDirectoryW` at `0x18002b4d6`
- `KERNEL32!RemoveDirectoryW` at `0x18002b4d6`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x18002b4fc`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x18002b539`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x18002b4fc`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x18002b539`
- `KERNEL32!CreateFileW` at `0x18002b46b`
- `KERNEL32!CreateFileW` at `0x18002b46b`

## string_xrefs

- `0x18002b6f1`: `void __cdecl UnBCL::Directory::DeleteSegment(const class UnBCL::String *,int)`
- `0x18002b748`: `void __cdecl UnBCL::Directory::DeleteSegment(const class UnBCL::String *,int)`
- `0x18002b79f`: `void __cdecl UnBCL::Directory::DeleteSegment(const class UnBCL::String *,int)`
- `0x18002b7ed`: `void __cdecl UnBCL::Directory::DeleteSegment(const class UnBCL::String *,int)`
- `0x18002b844`: `void __cdecl UnBCL::Directory::DeleteSegment(const class UnBCL::String *,int)`
- `0x18002b893`: `void __cdecl UnBCL::Directory::DeleteSegment(const class UnBCL::String *,int)`
- `0x18002b923`: `void __cdecl UnBCL::Directory::DeleteSegment(const class UnBCL::String *,int)`
- `0x18002b97b`: `void __cdecl UnBCL::Directory::DeleteSegment(const class UnBCL::String *,int)`
- `0x18002b9d2`: `void __cdecl UnBCL::Directory::DeleteSegment(const class UnBCL::String *,int)`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
void __fastcall UnBCL::Directory::DeleteSegment(LPCWSTR *a1, int a2)
{
  int v4; // r14d
  HANDLE FileW; // rax
  void *v6; // rbx
  DWORD LastError; // edi
  DWORD FinalPathNameByHandleW; // eax
  DWORD v9; // r15d
  WCHAR *v10; // rax
  WCHAR *v11; // rdi
  DWORD v12; // eax
  const wchar_t *v13; // rcx
  LPCWSTR v14; // rdx
  int v15; // edi
  NTSTATUS v16; // eax
  UnBCL::Win32Exception *v17; // rax
  UnBCL::Win32Exception *v18; // rbx
  ULONG v19; // eax
  UnBCL::Win32Exception *v20; // rax
  UnBCL::Win32Exception *v21; // rbx
  DWORD v22; // eax
  UnBCL::Win32Exception *v23; // rax
  UnBCL::Win32Exception *v24; // rbx
  DWORD v25; // eax
  UnBCL::Win32Exception *v26; // rax
  UnBCL::Win32Exception *v27; // rax
  UnBCL::Win32Exception *v28; // rbx
  DWORD v29; // eax
  UnBCL::Win32Exception *v30; // rax
  UnBCL::Win32Exception *v31; // rbx
  const struct UnBCL::String *v32; // rax
  __int64 v33; // rbx
  UnBCL::Win32Exception *v34; // rax
  UnBCL::Win32Exception *v35; // rax
  UnBCL::Win32Exception *v36; // rbx
  DWORD v37; // eax
  __int64 v38; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v39; // [rsp+50h] [rbp-B8h] BYREF
  __int64 pExceptionObject; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v41; // [rsp+60h] [rbp-A8h]
  HANDLE v42; // [rsp+68h] [rbp-A0h]
  _QWORD IoStatusBlock[4]; // [rsp+70h] [rbp-98h] BYREF
  _BYTE v44[24]; // [rsp+90h] [rbp-78h] BYREF
  int v45; // [rsp+A8h] [rbp-60h] BYREF
  __int128 v46; // [rsp+ACh] [rbp-5Ch]
  __int128 v47; // [rsp+BCh] [rbp-4Ch]
  int v48; // [rsp+CCh] [rbp-3Ch]
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+D0h] [rbp-38h] BYREF

  IoStatusBlock[3] = -2;
  v4 = 0;
  LODWORD(v41) = 0;
  v42 = 0;
  FileW = CreateFileW(a1[2], 0x10180u, 7u, 0, 3u, 0x2200000u, 0);
  v6 = FileW;
  v42 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    if ( LastError != 2 )
    {
      if ( LastError != 5 )
      {
        v26 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
        pExceptionObject = (__int64)v26;
        if ( v26 )
          v26 = (UnBCL::Win32Exception *)UnBCL::Win32Exception::Win32Exception(
                                           v26,
                                           LastError,
                                           1,
                                           (const struct UnBCL::String *)a1);
        v39 = AddStackTraceToException<UnBCL::InvalidOperationException>(
                v26,
                "void __cdecl UnBCL::Directory::DeleteSegment(const class UnBCL::String *,int)");
        throw (UnBCL::Win32Exception **)&v39;
      }
      if ( !RemoveDirectoryW(a1[2]) )
      {
        v23 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
        v24 = v23;
        pExceptionObject = (__int64)v23;
        if ( v23 )
        {
          v25 = GetLastError();
          v23 = (UnBCL::Win32Exception *)UnBCL::Win32Exception::Win32Exception(
                                           v24,
                                           v25,
                                           1,
                                           (const struct UnBCL::String *)a1);
        }
        v39 = AddStackTraceToException<UnBCL::InvalidOperationException>(
                v23,
                "void __cdecl UnBCL::Directory::DeleteSegment(const class UnBCL::String *,int)");
        throw (UnBCL::Win32Exception **)&v39;
      }
    }
    CloseHandle((HANDLE)0xFFFFFFFFFFFFFFFFLL);
    v42 = 0;
  }
  else
  {
    if ( a2 )
    {
      FinalPathNameByHandleW = GetFinalPathNameByHandleW(FileW, 0, 0, 0);
      v9 = FinalPathNameByHandleW;
      if ( !FinalPathNameByHandleW )
      {
        v27 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
        v28 = v27;
        pExceptionObject = (__int64)v27;
        if ( v27 )
        {
          v29 = GetLastError();
          v27 = (UnBCL::Win32Exception *)UnBCL::Win32Exception::Win32Exception(
                                           v28,
                                           v29,
                                           1,
                                           (const struct UnBCL::String *)a1);
        }
        v39 = AddStackTraceToException<UnBCL::InvalidOperationException>(
                v27,
                "void __cdecl UnBCL::Directory::DeleteSegment(const class UnBCL::String *,int)");
        throw (UnBCL::Win32Exception **)&v39;
      }
      v10 = (WCHAR *)operator new[](saturated_mul(FinalPathNameByHandleW, 2u));
      v11 = v10;
      if ( !v10 )
      {
        v30 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
        pExceptionObject = (__int64)v30;
        if ( v30 )
          v30 = (UnBCL::Win32Exception *)UnBCL::Win32Exception::Win32Exception(
                                           v30,
                                           8u,
                                           1,
                                           (const struct UnBCL::String *)a1);
        v39 = AddStackTraceToException<UnBCL::InvalidOperationException>(
                v30,
                "void __cdecl UnBCL::Directory::DeleteSegment(const class UnBCL::String *,int)");
        throw (UnBCL::Win32Exception **)&v39;
      }
      v12 = GetFinalPathNameByHandleW(v6, v10, v9, 0);
      if ( !v12 || v12 >= v9 )
      {
        operator delete[](v11);
        v34 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
        pExceptionObject = (__int64)v34;
        if ( v34 )
          v34 = (UnBCL::Win32Exception *)UnBCL::Win32Exception::Win32Exception(
                                           v34,
                                           0x7Au,
                                           1,
                                           (const struct UnBCL::String *)a1);
        v39 = AddStackTraceToException<UnBCL::InvalidOperationException>(
                v34,
                "void __cdecl UnBCL::Directory::DeleteSegment(const class UnBCL::String *,int)");
        throw (UnBCL::Win32Exception **)&v39;
      }
      v13 = v11;
      if ( *v11 == 92 && (v11[1] == 92 || v11[1] == 63) && v11[2] == 63 && v11[3] == 92 )
        v13 = v11 + 4;
      v14 = a1[2];
      if ( *v14 == 92 && (v14[1] == 92 || v14[1] == 63) && v14[2] == 63 && v14[3] == 92 )
        v14 += 4;
      if ( _wcsicmp(v13, v14) )
      {
        v31 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
        pExceptionObject = (__int64)v31;
        if ( v31 )
        {
          v32 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v44, v11);
          v4 = 1;
          LODWORD(v41) = 1;
          v33 = UnBCL::Win32Exception::Win32Exception(v31, 0x2A9u, 1, v32);
        }
        else
        {
          v33 = 0;
        }
        if ( (v4 & 1) != 0 )
        {
          LODWORD(v41) = v4 & 0xFFFFFFFE;
          UnBCL::String::~String((UnBCL::String *)v44);
        }
        operator delete[](v11);
        v39 = AddStackTraceToException<UnBCL::InvalidOperationException>(
                v33,
                "void __cdecl UnBCL::Directory::DeleteSegment(const class UnBCL::String *,int)");
        throw (UnBCL::Win32Exception **)&v39;
      }
      operator delete[](v11);
    }
    memset(&FileInformation, 0, sizeof(FileInformation));
    v45 = 0;
    v46 = 0;
    v47 = 0;
    v48 = 0;
    if ( !GetFileInformationByHandle(v6, &FileInformation)
      || !GetFileInformationByHandleEx(v6, FileBasicInfo, &v45, 0x28u) )
    {
      v20 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
      v21 = v20;
      IoStatusBlock[0] = v20;
      if ( v20 )
      {
        v22 = GetLastError();
        v20 = (UnBCL::Win32Exception *)UnBCL::Win32Exception::Win32Exception(
                                         v21,
                                         v22,
                                         1,
                                         (const struct UnBCL::String *)a1);
      }
      pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                           v20,
                           "void __cdecl UnBCL::Directory::DeleteSegment(const class UnBCL::String *,int)");
      throw (UnBCL::Win32Exception **)&pExceptionObject;
    }
    HIDWORD(v47) = 0x2000;
    if ( !SetFileInformationByHandle(v6, FileBasicInfo, &v45, 0x28u) )
    {
      v35 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
      v36 = v35;
      pExceptionObject = (__int64)v35;
      if ( v35 )
      {
        v37 = GetLastError();
        v35 = (UnBCL::Win32Exception *)UnBCL::Win32Exception::Win32Exception(
                                         v36,
                                         v37,
                                         1,
                                         (const struct UnBCL::String *)a1);
      }
      v39 = AddStackTraceToException<UnBCL::InvalidOperationException>(
              v35,
              "void __cdecl UnBCL::Directory::DeleteSegment(const class UnBCL::String *,int)");
      throw (UnBCL::Win32Exception **)&v39;
    }
    LOBYTE(v38) = 1;
    *(_OWORD *)&IoStatusBlock[1] = 0;
    v15 = NtSetInformationFile(v6, (PIO_STATUS_BLOCK)&IoStatusBlock[1], &v38, 1u, FileDispositionInformation);
    if ( v15 < 0 )
    {
      LODWORD(v39) = 1;
      v16 = NtSetInformationFile(v6, (PIO_STATUS_BLOCK)&IoStatusBlock[1], &v39, 4u, (FILE_INFORMATION_CLASS)64);
      if ( v16 < 0 )
      {
        if ( v16 != -1073741821 )
          v15 = v16;
        v17 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
        v18 = v17;
        IoStatusBlock[0] = v17;
        if ( v17 )
        {
          v19 = RtlNtStatusToDosError(v15);
          v17 = (UnBCL::Win32Exception *)UnBCL::Win32Exception::Win32Exception(
                                           v18,
                                           v19,
                                           1,
                                           (const struct UnBCL::String *)a1);
        }
        pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                             v17,
                             "void __cdecl UnBCL::Directory::DeleteSegment(const class UnBCL::String *,int)");
        throw (UnBCL::Win32Exception **)&pExceptionObject;
      }
    }
    if ( v6 )
    {
      CloseHandle(v6);
      v42 = 0;
    }
  }
}

```

## disassembly

```asm
0x18002b400  mov     rax, rsp
0x18002b403  push    rbp
0x18002b404  push    rdi
0x18002b405  push    r13
0x18002b407  push    r14
0x18002b409  push    r15
0x18002b40b  lea     rbp, [rax-38h]
0x18002b40f  sub     rsp, 110h
0x18002b416  mov     [rbp+30h+var_B0], 0FFFFFFFFFFFFFFFEh
0x18002b41e  mov     [rax+10h], rbx
0x18002b422  mov     [rax+18h], rsi
0x18002b426  mov     rax, cs:__security_cookie
0x18002b42d  xor     rax, rsp
0x18002b430  mov     [rbp+30h+var_30], rax
0x18002b434  mov     edi, edx
0x18002b436  mov     rsi, rcx
0x18002b439  xor     r14d, r14d
0x18002b43c  mov     dword ptr [rsp+130h+var_D8], r14d
0x18002b441  mov     [rsp+130h+var_D0], r14
0x18002b446  mov     [rsp+130h+hTemplateFile], r14; hTemplateFile
0x18002b44b  mov     [rsp+130h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x18002b453  mov     [rsp+130h+dwCreationDisposition], 3; dwCreationDisposition
0x18002b45b  xor     r9d, r9d; lpSecurityAttributes
0x18002b45e  mov     edx, 10180h; dwDesiredAccess
0x18002b463  lea     r8d, [r14+7]; dwShareMode
0x18002b467  mov     rcx, [rcx+10h]; lpFileName
0x18002b46b  call    cs:__imp_CreateFileW
0x18002b471  mov     rbx, rax
0x18002b474  mov     [rsp+130h+var_D0], rax
0x18002b479  or      r13, 0FFFFFFFFFFFFFFFFh
0x18002b47d  cmp     rax, r13
0x18002b480  jnz     short loc_18002B4E9
0x18002b482  call    cs:__imp_GetLastError
0x18002b488  mov     edi, eax
0x18002b48a  cmp     eax, 2
0x18002b48d  jnz     short loc_18002B4C9
0x18002b48f  mov     rcx, r13; hObject
0x18002b492  call    cs:__imp_CloseHandle
0x18002b498  mov     [rsp+130h+var_D0], 0
0x18002b4a1  mov     rcx, [rbp+30h+var_30]
0x18002b4a5  xor     rcx, rsp; StackCookie
0x18002b4a8  call    __security_check_cookie
0x18002b4ad  lea     r11, [rsp+130h+var_20]
0x18002b4b5  mov     rbx, [r11+38h]
0x18002b4b9  mov     rsi, [r11+40h]
0x18002b4bd  mov     rsp, r11
0x18002b4c0  pop     r15
0x18002b4c2  pop     r14
0x18002b4c4  pop     r13
0x18002b4c6  pop     rdi
0x18002b4c7  pop     rbp
0x18002b4c8  retn
0x18002b4c9  cmp     edi, 5
0x18002b4cc  jnz     loc_18002B7C5
0x18002b4d2  mov     rcx, [rsi+10h]; lpPathName
0x18002b4d6  call    cs:__imp_RemoveDirectoryW
0x18002b4dc  test    eax, eax
0x18002b4de  jz      loc_18002B76E
0x18002b4e4  mov     rcx, rbx
0x18002b4e7  jmp     short loc_18002B492
0x18002b4e9  test    edi, edi
0x18002b4eb  jz      loc_18002B5BD
0x18002b4f1  xor     r9d, r9d; dwFlags
0x18002b4f4  xor     r8d, r8d; cchFilePath
0x18002b4f7  xor     edx, edx; lpszFilePath
0x18002b4f9  mov     rcx, rbx; hFile
0x18002b4fc  call    cs:__imp_GetFinalPathNameByHandleW
0x18002b502  mov     r15d, eax
0x18002b505  test    eax, eax
0x18002b507  jz      loc_18002B813
0x18002b50d  mov     eax, 2
0x18002b512  mul     r15
0x18002b515  cmovb   rax, r13
0x18002b519  mov     rcx, rax; unsigned __int64
0x18002b51c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002b521  mov     rdi, rax
0x18002b524  test    rax, rax
0x18002b527  jz      loc_18002B86A
0x18002b52d  xor     r9d, r9d; dwFlags
0x18002b530  mov     r8d, r15d; cchFilePath
0x18002b533  mov     rdx, rax; lpszFilePath
0x18002b536  mov     rcx, rbx; hFile
0x18002b539  call    cs:__imp_GetFinalPathNameByHandleW
0x18002b53f  test    eax, eax
0x18002b541  jz      loc_18002B949
0x18002b547  cmp     eax, r15d
0x18002b54a  jnb     loc_18002B949
0x18002b550  mov     rcx, rdi
0x18002b553  mov     r8w, 3Fh ; '?'
0x18002b558  mov     ax, 5Ch ; '\'
0x18002b55c  cmp     [rdi], ax
0x18002b55f  jnz     short loc_18002B57F
0x18002b561  cmp     [rdi+2], ax
0x18002b565  jz      short loc_18002B56E
0x18002b567  cmp     [rdi+2], r8w
0x18002b56c  jnz     short loc_18002B57F
0x18002b56e  cmp     [rdi+4], r8w
0x18002b573  jnz     short loc_18002B57F
0x18002b575  cmp     [rdi+6], ax
0x18002b579  jnz     short loc_18002B57F
0x18002b57b  lea     rcx, [rdi+8]; String1
0x18002b57f  mov     rdx, [rsi+10h]
0x18002b583  cmp     [rdx], ax
0x18002b586  jnz     short loc_18002B5A6
0x18002b588  cmp     [rdx+2], ax
0x18002b58c  jz      short loc_18002B595
0x18002b58e  cmp     [rdx+2], r8w
0x18002b593  jnz     short loc_18002B5A6
0x18002b595  cmp     [rdx+4], r8w
0x18002b59a  jnz     short loc_18002B5A6
0x18002b59c  cmp     [rdx+6], ax
0x18002b5a0  jnz     short loc_18002B5A6
0x18002b5a2  add     rdx, 8; String2
0x18002b5a6  call    cs:__imp__wcsicmp
0x18002b5ac  test    eax, eax
0x18002b5ae  jnz     loc_18002B8B9
0x18002b5b4  mov     rcx, rdi
0x18002b5b7  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18002b5bd  xorps   xmm0, xmm0
0x18002b5c0  xor     eax, eax
0x18002b5c2  movups  xmmword ptr [rbp+30h+FileInformation.dwFileAttributes], xmm0
0x18002b5c6  movups  xmmword ptr [rbp+30h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x18002b5ca  movups  xmmword ptr [rbp+30h+FileInformation.nFileSizeHigh], xmm0
0x18002b5ce  mov     [rbp+30h+FileInformation.nFileIndexLow], eax
0x18002b5d1  mov     [rbp+30h+var_90], eax
0x18002b5d4  movups  [rbp+30h+var_8C], xmm0
0x18002b5d8  movups  [rbp+30h+var_7C], xmm0
0x18002b5dc  mov     [rbp+30h+var_6C], eax
0x18002b5df  lea     rdx, [rbp+30h+FileInformation]; lpFileInformation
0x18002b5e3  mov     rcx, rbx; hFile
0x18002b5e6  call    cs:__imp_GetFileInformationByHandle
0x18002b5ec  test    eax, eax
0x18002b5ee  jz      loc_18002B717
0x18002b5f4  mov     edi, 28h ; '('
0x18002b5f9  mov     r9d, edi; dwBufferSize
0x18002b5fc  lea     r8, [rbp+30h+var_90]; lpFileInformation
0x18002b600  xor     edx, edx; FileInformationClass
0x18002b602  mov     rcx, rbx; hFile
0x18002b605  call    cs:__imp_GetFileInformationByHandleEx
0x18002b60b  test    eax, eax
0x18002b60d  jz      loc_18002B717
0x18002b613  mov     dword ptr [rbp+30h+var_7C+0Ch], 2000h
0x18002b61a  mov     r9d, edi; dwBufferSize
0x18002b61d  lea     r8, [rbp+30h+var_90]; lpFileInformation
0x18002b621  xor     edx, edx; FileInformationClass
0x18002b623  mov     rcx, rbx; hFile
0x18002b626  call    cs:__imp_SetFileInformationByHandle
0x18002b62c  test    eax, eax
0x18002b62e  jz      loc_18002B9A1
0x18002b634  mov     byte ptr [rsp+130h+var_F0], 1
0x18002b639  xorps   xmm0, xmm0
0x18002b63c  movups  xmmword ptr [rsp+130h+IoStatusBlock+8], xmm0
0x18002b641  mov     [rsp+130h+dwCreationDisposition], 0Dh; FileInformationClass
0x18002b649  lea     r9d, [rdi-27h]; Length
0x18002b64d  lea     r8, [rsp+130h+var_F0]; FileInformation
0x18002b652  lea     rdx, [rsp+130h+IoStatusBlock+8]; IoStatusBlock
0x18002b657  mov     rcx, rbx; FileHandle
0x18002b65a  call    cs:__imp_NtSetInformationFile
0x18002b660  mov     edi, eax
0x18002b662  test    eax, eax
0x18002b664  jns     short loc_18002B693
0x18002b666  mov     dword ptr [rsp+130h+var_E8], 1
0x18002b66e  mov     [rsp+130h+dwCreationDisposition], 40h ; '@'; FileInformationClass
0x18002b676  mov     r9d, 4; Length
0x18002b67c  lea     r8, [rsp+130h+var_E8]; FileInformation
0x18002b681  lea     rdx, [rsp+130h+IoStatusBlock+8]; IoStatusBlock
0x18002b686  mov     rcx, rbx; FileHandle
0x18002b689  call    cs:__imp_NtSetInformationFile
0x18002b68f  test    eax, eax
0x18002b691  js      short loc_18002B6B6
0x18002b693  test    rbx, rbx
0x18002b696  jz      short loc_18002B6A8
0x18002b698  mov     rcx, rbx; hObject
0x18002b69b  call    cs:__imp_CloseHandle
0x18002b6a1  xor     ebx, ebx
0x18002b6a3  mov     [rsp+130h+var_D0], rbx
0x18002b6a8  test    rbx, rbx
0x18002b6ab  jz      loc_18002B4A1
0x18002b6b1  jmp     loc_18002B4E4
0x18002b6b6  cmp     eax, 0C0000003h
0x18002b6bb  cmovnz  edi, eax
0x18002b6be  mov     ecx, 40h ; '@'; unsigned __int64
0x18002b6c3  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18002b6c8  mov     rbx, rax
0x18002b6cb  mov     qword ptr [rsp+130h+IoStatusBlock], rax
0x18002b6d0  test    rax, rax
0x18002b6d3  jz      short loc_18002B6F1
0x18002b6d5  mov     ecx, edi; Status
0x18002b6d7  call    cs:__imp_RtlNtStatusToDosError
0x18002b6dd  mov     r9, rsi; struct UnBCL::String *
0x18002b6e0  mov     r8d, 1; int
0x18002b6e6  mov     edx, eax; dwMessageId
0x18002b6e8  mov     rcx, rbx; this
0x18002b6eb  call    ??0Win32Exception@UnBCL@@QEAA@KHPEBVString@1@@Z; UnBCL::Win32Exception::Win32Exception(ulong,int,UnBCL::String const *)
0x18002b6f0  nop
0x18002b6f1  lea     rdx, aVoidCdeclUnbcl_67; "void __cdecl UnBCL::Directory::DeleteSe"...
0x18002b6f8  mov     rcx, rax
0x18002b6fb  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18002b700  mov     [rsp+130h+pExceptionObject], rax
0x18002b705  lea     rdx, _TI6PEAVWin32Exception@UnBCL@@; pThrowInfo
0x18002b70c  lea     rcx, [rsp+130h+pExceptionObject]; pExceptionObject
0x18002b711  call    _CxxThrowException_0
0x18002b717  mov     ecx, 40h ; '@'; unsigned __int64
0x18002b71c  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18002b721  mov     rbx, rax
0x18002b724  mov     qword ptr [rsp+130h+IoStatusBlock], rax
0x18002b729  test    rax, rax
0x18002b72c  jz      short loc_18002B748
0x18002b72e  call    cs:__imp_GetLastError
0x18002b734  mov     r9, rsi; struct UnBCL::String *
0x18002b737  mov     r8d, 1; int
0x18002b73d  mov     edx, eax; dwMessageId
0x18002b73f  mov     rcx, rbx; this
0x18002b742  call    ??0Win32Exception@UnBCL@@QEAA@KHPEBVString@1@@Z; UnBCL::Win32Exception::Win32Exception(ulong,int,UnBCL::String const *)
0x18002b747  nop
0x18002b748  lea     rdx, aVoidCdeclUnbcl_67; "void __cdecl UnBCL::Directory::DeleteSe"...
0x18002b74f  mov     rcx, rax
0x18002b752  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18002b757  mov     [rsp+130h+pExceptionObject], rax
0x18002b75c  lea     rdx, _TI6PEAVWin32Exception@UnBCL@@; pThrowInfo
0x18002b763  lea     rcx, [rsp+130h+pExceptionObject]; pExceptionObject
0x18002b768  call    _CxxThrowException_0
0x18002b76e  mov     ecx, 40h ; '@'; unsigned __int64
0x18002b773  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18002b778  mov     rbx, rax
0x18002b77b  mov     [rsp+130h+pExceptionObject], rax
0x18002b780  test    rax, rax
0x18002b783  jz      short loc_18002B79F
0x18002b785  call    cs:__imp_GetLastError
0x18002b78b  mov     r9, rsi; struct UnBCL::String *
0x18002b78e  mov     r8d, 1; int
0x18002b794  mov     edx, eax; dwMessageId
0x18002b796  mov     rcx, rbx; this
0x18002b799  call    ??0Win32Exception@UnBCL@@QEAA@KHPEBVString@1@@Z; UnBCL::Win32Exception::Win32Exception(ulong,int,UnBCL::String const *)
0x18002b79e  nop
0x18002b79f  lea     rdx, aVoidCdeclUnbcl_67; "void __cdecl UnBCL::Directory::DeleteSe"...
0x18002b7a6  mov     rcx, rax
0x18002b7a9  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18002b7ae  mov     [rsp+130h+var_E8], rax
0x18002b7b3  lea     rdx, _TI6PEAVWin32Exception@UnBCL@@; pThrowInfo
0x18002b7ba  lea     rcx, [rsp+130h+var_E8]; pExceptionObject
0x18002b7bf  call    _CxxThrowException_0
0x18002b7c5  mov     ecx, 40h ; '@'; unsigned __int64
0x18002b7ca  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18002b7cf  mov     [rsp+130h+pExceptionObject], rax
0x18002b7d4  test    rax, rax
0x18002b7d7  jz      short loc_18002B7ED
0x18002b7d9  mov     r9, rsi; struct UnBCL::String *
0x18002b7dc  mov     r8d, 1; int
0x18002b7e2  mov     edx, edi; dwMessageId
0x18002b7e4  mov     rcx, rax; this
0x18002b7e7  call    ??0Win32Exception@UnBCL@@QEAA@KHPEBVString@1@@Z; UnBCL::Win32Exception::Win32Exception(ulong,int,UnBCL::String const *)
0x18002b7ec  nop
0x18002b7ed  lea     rdx, aVoidCdeclUnbcl_67; "void __cdecl UnBCL::Directory::DeleteSe"...
0x18002b7f4  mov     rcx, rax
0x18002b7f7  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18002b7fc  mov     [rsp+130h+var_E8], rax
0x18002b801  lea     rdx, _TI6PEAVWin32Exception@UnBCL@@; pThrowInfo
0x18002b808  lea     rcx, [rsp+130h+var_E8]; pExceptionObject
0x18002b80d  call    _CxxThrowException_0
0x18002b813  mov     ecx, 40h ; '@'; unsigned __int64
0x18002b818  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18002b81d  mov     rbx, rax
0x18002b820  mov     [rsp+130h+pExceptionObject], rax
0x18002b825  test    rax, rax
0x18002b828  jz      short loc_18002B844
0x18002b82a  call    cs:__imp_GetLastError
0x18002b830  mov     r9, rsi; struct UnBCL::String *
0x18002b833  mov     r8d, 1; int
0x18002b839  mov     edx, eax; dwMessageId
0x18002b83b  mov     rcx, rbx; this
0x18002b83e  call    ??0Win32Exception@UnBCL@@QEAA@KHPEBVString@1@@Z; UnBCL::Win32Exception::Win32Exception(ulong,int,UnBCL::String const *)
0x18002b843  nop
0x18002b844  lea     rdx, aVoidCdeclUnbcl_67; "void __cdecl UnBCL::Directory::DeleteSe"...
0x18002b84b  mov     rcx, rax
0x18002b84e  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18002b853  mov     [rsp+130h+var_E8], rax
0x18002b858  lea     rdx, _TI6PEAVWin32Exception@UnBCL@@; pThrowInfo
0x18002b85f  lea     rcx, [rsp+130h+var_E8]; pExceptionObject
0x18002b864  call    _CxxThrowException_0
0x18002b86a  mov     ecx, 40h ; '@'; unsigned __int64
0x18002b86f  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18002b874  mov     [rsp+130h+pExceptionObject], rax
0x18002b879  test    rax, rax
0x18002b87c  jz      short loc_18002B893
0x18002b87e  mov     r9, rsi; struct UnBCL::String *
0x18002b881  mov     edx, 8; dwMessageId
0x18002b886  lea     r8d, [rdx-7]; int
0x18002b88a  mov     rcx, rax; this
0x18002b88d  call    ??0Win32Exception@UnBCL@@QEAA@KHPEBVString@1@@Z; UnBCL::Win32Exception::Win32Exception(ulong,int,UnBCL::String const *)
0x18002b892  nop
0x18002b893  lea     rdx, aVoidCdeclUnbcl_67; "void __cdecl UnBCL::Directory::DeleteSe"...
0x18002b89a  mov     rcx, rax
0x18002b89d  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18002b8a2  mov     [rsp+130h+var_E8], rax
0x18002b8a7  lea     rdx, _TI6PEAVWin32Exception@UnBCL@@; pThrowInfo
0x18002b8ae  lea     rcx, [rsp+130h+var_E8]; pExceptionObject
0x18002b8b3  call    _CxxThrowException_0
0x18002b8b9  mov     ecx, 40h ; '@'; unsigned __int64
0x18002b8be  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
  ... truncated ...
```
