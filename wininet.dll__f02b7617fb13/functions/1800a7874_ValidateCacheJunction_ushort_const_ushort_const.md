# ValidateCacheJunction(ushort const *,ushort const *)

- ea: `0x1800a7874`
- end: `0x1800a7e20`
- name: `?ValidateCacheJunction@@YAJPEBG0@Z`
- size: `1452`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1800a74e8`

## callees

- `0x180017454`
- `0x1800701d0`
- `0x1800a7874`
- `0x1800e0d10`
- `0x18014a7a0`
- `0x18019fc3c`
- `0x18019fd4c`
- `0x18019fe4c`
- `0x18019ffec`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a7c46`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a7c46`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a7db2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a7dce`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a7de7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a7db2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a7dce`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a7de7`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800a7926`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800a7996`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800a7926`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800a7996`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a79ed`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a79ed`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800a7d73`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800a7d73`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800a78ff`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800a7917`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800a795d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800a78ff`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800a7917`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800a795d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a7df0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a7df0`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800a7d3a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800a7d3a`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x1800a7c00`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x1800a7c00`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800a7bc0`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800a7bc0`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorControl` at `0x1800a7b7f`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorControl` at `0x1800a7b7f`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x1800a7b2f`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x1800a7b2f`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800a7aef`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800a7aef`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800a7a57`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800a7a57`

## pseudocode

```c
__int64 __fastcall ValidateCacheJunction(LPCWSTR lpFileName, const unsigned __int16 *a2)
{
  signed int CurrentSd; // ebx
  __int64 v5; // rdx
  __int64 v6; // rcx
  int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // rcx
  int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // rcx
  int v13; // eax
  HANDLE FileW; // rax
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rsi
  void *v18; // r13
  int LastError; // eax
  __int64 v20; // rdx
  __int64 v21; // rcx
  unsigned int v22; // r8d
  int v23; // eax
  __int64 v24; // rdx
  __int64 v25; // rcx
  int v26; // eax
  __int64 v27; // rdx
  __int64 v28; // rcx
  int v29; // eax
  __int64 v30; // rdx
  __int64 v31; // rcx
  int v32; // eax
  __int64 v33; // rdx
  __int64 v34; // rcx
  int v35; // eax
  __int64 v36; // rdx
  __int64 v37; // rcx
  int v38; // eax
  _WORD *v39; // rax
  _WORD *v40; // r14
  __int64 v41; // rax
  __int16 v42; // r10
  __int64 v43; // r11
  unsigned __int16 v44; // r10
  __int64 v45; // rdx
  __int64 v46; // rcx
  int v47; // eax
  __int64 v48; // rdx
  __int64 v49; // rcx
  int v50; // eax
  PACL v52; // [rsp+48h] [rbp-21h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+50h] [rbp-19h] BYREF
  PACL pDacl; // [rsp+58h] [rbp-11h] BYREF
  WORD pControl[2]; // [rsp+60h] [rbp-9h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+64h] [rbp-5h] BYREF
  WINBOOL bDaclPresent; // [rsp+68h] [rbp-1h] BYREF
  DWORD dwRevision; // [rsp+6Ch] [rbp+3h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+70h] [rbp+7h] BYREF
  __int64 v60; // [rsp+90h] [rbp+27h]

  v52 = 0;
  pDacl = 0;
  bDaclDefaulted = 0;
  bDaclPresent = 0;
  pSecurityDescriptor = 0;
  v60 = 0;
  pControl[0] = 0;
  dwRevision = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  if ( lpFileName && a2 )
  {
    if ( GetFileAttributesW(lpFileName) == -1 )
    {
      if ( GetFileAttributesW(a2) != -1 || CreateDirectoryW(a2, 0) )
      {
        if ( (GetFileAttributesW(a2) & 0x10) != 0 )
        {
          if ( CreateDirectoryW(lpFileName, 0) )
          {
            FileW = CreateFileW(lpFileName, 0x40040000u, 0, 0, 3u, 0x2200000u, 0);
            v17 = -1;
            v18 = FileW;
            if ( FileW == (HANDLE)-1LL )
            {
              LastError = WxGetLastError(v16, v15);
              CurrentSd = LastError;
              if ( LastError > 0 )
                CurrentSd = (unsigned __int16)LastError | 0x80070000;
              if ( CurrentSd >= 0 )
                return (unsigned int)-2147418113;
            }
            else
            {
              CurrentSd = GetCurrentSd(FileW, &pSecurityDescriptor);
              if ( CurrentSd >= 0 )
              {
                if ( GetSecurityDescriptorDacl(pSecurityDescriptor, &bDaclPresent, &pDacl, &bDaclDefaulted) )
                {
                  CurrentSd = AllocNewAcl(pDacl, &v52, v22);
                  if ( CurrentSd >= 0 )
                  {
                    CurrentSd = AddJunctionAce(v52);
                    if ( CurrentSd >= 0 )
                    {
                      CurrentSd = CopyAces(pDacl, v52);
                      if ( CurrentSd >= 0 )
                      {
                        if ( InitializeSecurityDescriptor(SecurityDescriptor, 1u) )
                        {
                          if ( GetSecurityDescriptorControl(pSecurityDescriptor, pControl, &dwRevision) )
                          {
                            if ( SetSecurityDescriptorControl(SecurityDescriptor, 0x1540u, pControl[0] & 0x40 | 0x500) )
                            {
                              if ( SetSecurityDescriptorDacl(SecurityDescriptor, 1, v52, 0) )
                              {
                                if ( SetKernelObjectSecurity(v18, 4u, SecurityDescriptor) )
                                {
                                  v39 = HeapAlloc(g_hWxProcessHeap, 8u, 0x428u);
                                  v40 = v39;
                                  if ( v39 )
                                  {
                                    *(_DWORD *)v39 = -1610612733;
                                    CurrentSd = StringCchPrintfW(v39 + 8, 0x104u, L"\\??\\%s", a2);
                                    if ( CurrentSd >= 0 )
                                    {
                                      v41 = -1;
                                      do
                                        ++v41;
                                      while ( v40[v41 + 8] );
                                      CurrentSd = StringCchCopyW(&v40[(unsigned __int16)v41 + 9], 0x104u, a2);
                                      if ( CurrentSd >= 0 )
                                      {
                                        do
                                          ++v17;
                                        while ( *(_WORD *)(v43 + 2 * v17 + 18) );
                                        v40[5] = 2 * v42;
                                        v40[6] = 2 * v42 + 2;
                                        v44 = 2 * (v17 + v42 + 6);
                                        v40[4] = 0;
                                        v40[2] = v44;
                                        v40[7] = 2 * v17;
                                        if ( DeviceIoControl(v18, 0x900A4u, v40, v44 + 8, 0, 0, 0, 0) )
                                        {
                                          if ( SetFileAttributesW(lpFileName, 0x2006u) )
                                          {
                                            CurrentSd = 0;
                                          }
                                          else
                                          {
                                            v50 = WxGetLastError(v49, v48);
                                            CurrentSd = v50;
                                            if ( v50 > 0 )
                                              CurrentSd = (unsigned __int16)v50 | 0x80070000;
                                            if ( CurrentSd >= 0 )
                                              CurrentSd = -2147418113;
                                          }
                                        }
                                        else
                                        {
                                          v47 = WxGetLastError(v46, v45);
                                          CurrentSd = v47;
                                          if ( v47 > 0 )
                                            CurrentSd = (unsigned __int16)v47 | 0x80070000;
                                          if ( CurrentSd >= 0 )
                                            CurrentSd = -2147418113;
                                        }
                                      }
                                    }
                                    HeapFree(g_hWxProcessHeap, 0, v40);
                                  }
                                  else
                                  {
                                    CurrentSd = -2147024882;
                                  }
                                }
                                else
                                {
                                  v38 = WxGetLastError(v37, v36);
                                  CurrentSd = v38;
                                  if ( v38 > 0 )
                                    CurrentSd = (unsigned __int16)v38 | 0x80070000;
                                  if ( CurrentSd >= 0 )
                                    CurrentSd = -2147418113;
                                }
                              }
                              else
                              {
                                v35 = WxGetLastError(v34, v33);
                                CurrentSd = v35;
                                if ( v35 > 0 )
                                  CurrentSd = (unsigned __int16)v35 | 0x80070000;
                                if ( CurrentSd >= 0 )
                                  CurrentSd = -2147418113;
                              }
                            }
                            else
                            {
                              v32 = WxGetLastError(v31, v30);
                              CurrentSd = v32;
                              if ( v32 > 0 )
                                CurrentSd = (unsigned __int16)v32 | 0x80070000;
                              if ( CurrentSd >= 0 )
                                CurrentSd = -2147418113;
                            }
                          }
                          else
                          {
                            v29 = WxGetLastError(v28, v27);
                            CurrentSd = v29;
                            if ( v29 > 0 )
                              CurrentSd = (unsigned __int16)v29 | 0x80070000;
                            if ( CurrentSd >= 0 )
                              CurrentSd = -2147418113;
                          }
                        }
                        else
                        {
                          v26 = WxGetLastError(v25, v24);
                          CurrentSd = v26;
                          if ( v26 > 0 )
                            CurrentSd = (unsigned __int16)v26 | 0x80070000;
                          if ( CurrentSd >= 0 )
                            CurrentSd = -2147418113;
                        }
                      }
                    }
                  }
                  if ( v52 )
                    HeapFree(g_hWxProcessHeap, 0, v52);
                }
                else
                {
                  v23 = WxGetLastError(v21, v20);
                  CurrentSd = v23;
                  if ( v23 > 0 )
                    CurrentSd = (unsigned __int16)v23 | 0x80070000;
                  if ( CurrentSd >= 0 )
                    CurrentSd = -2147418113;
                }
              }
              if ( pSecurityDescriptor )
                HeapFree(g_hWxProcessHeap, 0, pSecurityDescriptor);
              CloseHandle(v18);
            }
          }
          else
          {
            v13 = WxGetLastError(v12, v11);
            CurrentSd = v13;
            if ( v13 > 0 )
              CurrentSd = (unsigned __int16)v13 | 0x80070000;
            if ( CurrentSd >= 0 )
              return (unsigned int)-2147418113;
          }
        }
        else
        {
          v10 = WxGetLastError(v9, v8);
          CurrentSd = v10;
          if ( v10 > 0 )
            CurrentSd = (unsigned __int16)v10 | 0x80070000;
          if ( CurrentSd >= 0 )
            return (unsigned int)-2147418113;
        }
      }
      else
      {
        v7 = WxGetLastError(v6, v5);
        CurrentSd = v7;
        if ( v7 > 0 )
          CurrentSd = (unsigned __int16)v7 | 0x80070000;
        if ( CurrentSd >= 0 )
          return (unsigned int)-2147418113;
      }
    }
    else
    {
      return 0;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)CurrentSd;
}

```

## disassembly

```asm
0x1800a7874  mov     [rsp-8+arg_10], rbx
0x1800a7879  mov     [rsp-8+arg_18], rsi
0x1800a787e  push    rbp
0x1800a787f  push    rdi
0x1800a7880  push    r13
0x1800a7882  push    r14
0x1800a7884  push    r15
0x1800a7886  lea     rbp, [rsp-37h]
0x1800a788b  sub     rsp, 0A0h
0x1800a7892  mov     rax, cs:__security_cookie
0x1800a7899  xor     rax, rsp
0x1800a789c  mov     [rbp+57h+var_28], rax
0x1800a78a0  xor     r14d, r14d
0x1800a78a3  xor     eax, eax
0x1800a78a5  mov     [rbp+57h+var_7C], r14d
0x1800a78a9  xorps   xmm0, xmm0
0x1800a78ac  mov     [rbp+57h+var_78], r14
0x1800a78b0  mov     rdi, rdx
0x1800a78b3  mov     [rbp+57h+pDacl], r14
0x1800a78b7  mov     r15, rcx
0x1800a78ba  mov     [rbp+57h+bDaclDefaulted], r14d
0x1800a78be  mov     [rbp+57h+bDaclPresent], r14d
0x1800a78c2  mov     [rbp+57h+pSecurityDescriptor], r14
0x1800a78c6  mov     [rbp+57h+var_30], rax
0x1800a78ca  mov     [rbp+57h+pControl], r14w
0x1800a78cf  mov     [rbp+57h+dwRevision], r14d
0x1800a78d3  movups  [rbp+57h+SecurityDescriptor], xmm0
0x1800a78d7  movups  [rbp+57h+var_40], xmm0
0x1800a78db  test    rcx, rcx
0x1800a78de  jnz     short loc_1800A78F1
0x1800a78e0  mov     [rbp+57h+var_7C], 24Fh
0x1800a78e7  mov     ebx, 80070057h
0x1800a78ec  jmp     loc_1800A7DF6
0x1800a78f1  test    rdi, rdi
0x1800a78f4  jnz     short loc_1800A78FF
0x1800a78f6  mov     [rbp+57h+var_7C], 250h
0x1800a78fd  jmp     short loc_1800A78E7
0x1800a78ff  call    cs:__imp_GetFileAttributesW
0x1800a7905  or      ebx, 0FFFFFFFFh
0x1800a7908  cmp     eax, ebx
0x1800a790a  jz      short loc_1800A7914
0x1800a790c  mov     ebx, r14d
0x1800a790f  jmp     loc_1800A7DF6
0x1800a7914  mov     rcx, rdi; lpFileName
0x1800a7917  call    cs:__imp_GetFileAttributesW
0x1800a791d  cmp     eax, ebx
0x1800a791f  jnz     short loc_1800A795A
0x1800a7921  xor     edx, edx; lpSecurityAttributes
0x1800a7923  mov     rcx, rdi; lpPathName
0x1800a7926  call    cs:__imp_CreateDirectoryW
0x1800a792c  test    eax, eax
0x1800a792e  jnz     short loc_1800A795A
0x1800a7930  call    WxGetLastError
0x1800a7935  mov     ebx, eax
0x1800a7937  test    eax, eax
0x1800a7939  jle     short loc_1800A7944
0x1800a793b  movzx   ebx, ax
0x1800a793e  or      ebx, 80070000h
0x1800a7944  test    ebx, ebx
0x1800a7946  mov     [rbp+57h+var_7C], 259h
0x1800a794d  mov     eax, 8000FFFFh
0x1800a7952  cmovns  ebx, eax
0x1800a7955  jmp     loc_1800A7DF6
0x1800a795a  mov     rcx, rdi; lpFileName
0x1800a795d  call    cs:__imp_GetFileAttributesW
0x1800a7963  test    al, 10h
0x1800a7965  jnz     short loc_1800A7991
0x1800a7967  call    WxGetLastError
0x1800a796c  mov     ebx, eax
0x1800a796e  test    eax, eax
0x1800a7970  jle     short loc_1800A797B
0x1800a7972  movzx   ebx, ax
0x1800a7975  or      ebx, 80070000h
0x1800a797b  test    ebx, ebx
0x1800a797d  mov     [rbp+57h+var_7C], 25Ch
0x1800a7984  mov     eax, 8000FFFFh
0x1800a7989  cmovns  ebx, eax
0x1800a798c  jmp     loc_1800A7DF6
0x1800a7991  xor     edx, edx; lpSecurityAttributes
0x1800a7993  mov     rcx, r15; lpPathName
0x1800a7996  call    cs:__imp_CreateDirectoryW
0x1800a799c  test    eax, eax
0x1800a799e  jnz     short loc_1800A79CA
0x1800a79a0  call    WxGetLastError
0x1800a79a5  mov     ebx, eax
0x1800a79a7  test    eax, eax
0x1800a79a9  jle     short loc_1800A79B4
0x1800a79ab  movzx   ebx, ax
0x1800a79ae  or      ebx, 80070000h
0x1800a79b4  test    ebx, ebx
0x1800a79b6  mov     [rbp+57h+var_7C], 25Dh
0x1800a79bd  mov     eax, 8000FFFFh
0x1800a79c2  cmovns  ebx, eax
0x1800a79c5  jmp     loc_1800A7DF6
0x1800a79ca  mov     [rsp+0C0h+hTemplateFile], r14; hTemplateFile
0x1800a79cf  xor     r9d, r9d; lpSecurityAttributes
0x1800a79d2  mov     [rsp+0C0h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x1800a79da  xor     r8d, r8d; dwShareMode
0x1800a79dd  mov     edx, 40040000h; dwDesiredAccess
0x1800a79e2  mov     [rsp+0C0h+dwCreationDisposition], 3; dwCreationDisposition
0x1800a79ea  mov     rcx, r15; lpFileName
0x1800a79ed  call    cs:__imp_CreateFileW
0x1800a79f3  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800a79f7  mov     r13, rax
0x1800a79fa  cmp     rax, rsi
0x1800a79fd  jnz     short loc_1800A7A29
0x1800a79ff  call    WxGetLastError
0x1800a7a04  mov     ebx, eax
0x1800a7a06  test    eax, eax
0x1800a7a08  jle     short loc_1800A7A13
0x1800a7a0a  movzx   ebx, ax
0x1800a7a0d  or      ebx, 80070000h
0x1800a7a13  test    ebx, ebx
0x1800a7a15  mov     [rbp+57h+var_7C], 266h
0x1800a7a1c  mov     eax, 8000FFFFh
0x1800a7a21  cmovns  ebx, eax
0x1800a7a24  jmp     loc_1800A7DF6
0x1800a7a29  lea     rdx, [rbp+57h+pSecurityDescriptor]; void **
0x1800a7a2d  mov     rcx, r13; Handle
0x1800a7a30  call    ?GetCurrentSd@@YAJPEAXPEAPEAX@Z; GetCurrentSd(void *,void * *)
0x1800a7a35  mov     ebx, eax
0x1800a7a37  test    eax, eax
0x1800a7a39  jns     short loc_1800A7A47
0x1800a7a3b  mov     [rbp+57h+var_7C], 268h
0x1800a7a42  jmp     loc_1800A7DD4
0x1800a7a47  mov     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x1800a7a4b  lea     r9, [rbp+57h+bDaclDefaulted]; lpbDaclDefaulted
0x1800a7a4f  lea     r8, [rbp+57h+pDacl]; pDacl
0x1800a7a53  lea     rdx, [rbp+57h+bDaclPresent]; lpbDaclPresent
0x1800a7a57  call    cs:__imp_GetSecurityDescriptorDacl
0x1800a7a5d  test    eax, eax
0x1800a7a5f  jnz     short loc_1800A7A8B
0x1800a7a61  call    WxGetLastError
0x1800a7a66  mov     ebx, eax
0x1800a7a68  test    eax, eax
0x1800a7a6a  jle     short loc_1800A7A75
0x1800a7a6c  movzx   ebx, ax
0x1800a7a6f  or      ebx, 80070000h
0x1800a7a75  test    ebx, ebx
0x1800a7a77  mov     [rbp+57h+var_7C], 26Dh
0x1800a7a7e  mov     eax, 8000FFFFh
0x1800a7a83  cmovns  ebx, eax
0x1800a7a86  jmp     loc_1800A7DD4
0x1800a7a8b  mov     rcx, [rbp+57h+pDacl]; struct _ACL *
0x1800a7a8f  lea     rdx, [rbp+57h+var_78]; struct _ACL **
0x1800a7a93  call    ?AllocNewAcl@@YAJPEAU_ACL@@PEAPEAU1@K@Z; AllocNewAcl(_ACL *,_ACL * *,ulong)
0x1800a7a98  mov     ebx, eax
0x1800a7a9a  test    eax, eax
0x1800a7a9c  jns     short loc_1800A7AAA
0x1800a7a9e  mov     [rbp+57h+var_7C], 26Fh
0x1800a7aa5  jmp     loc_1800A7DBB
0x1800a7aaa  mov     rcx, [rbp+57h+var_78]; struct _ACL *
0x1800a7aae  call    ?AddJunctionAce@@YAJPEAU_ACL@@@Z; AddJunctionAce(_ACL *)
0x1800a7ab3  mov     ebx, eax
0x1800a7ab5  test    eax, eax
0x1800a7ab7  jns     short loc_1800A7AC5
0x1800a7ab9  mov     [rbp+57h+var_7C], 270h
0x1800a7ac0  jmp     loc_1800A7DBB
0x1800a7ac5  mov     rdx, [rbp+57h+var_78]; struct _ACL *
0x1800a7ac9  mov     rcx, [rbp+57h+pDacl]; struct _ACL *
0x1800a7acd  call    ?CopyAces@@YAJPEAU_ACL@@0@Z; CopyAces(_ACL *,_ACL *)
0x1800a7ad2  mov     ebx, eax
0x1800a7ad4  test    eax, eax
0x1800a7ad6  jns     short loc_1800A7AE4
0x1800a7ad8  mov     [rbp+57h+var_7C], 271h
0x1800a7adf  jmp     loc_1800A7DBB
0x1800a7ae4  mov     ebx, 1
0x1800a7ae9  lea     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x1800a7aed  mov     edx, ebx; dwRevision
0x1800a7aef  call    cs:__imp_InitializeSecurityDescriptor
0x1800a7af5  test    eax, eax
0x1800a7af7  jnz     short loc_1800A7B23
0x1800a7af9  call    WxGetLastError
0x1800a7afe  mov     ebx, eax
0x1800a7b00  test    eax, eax
0x1800a7b02  jle     short loc_1800A7B0D
0x1800a7b04  movzx   ebx, ax
0x1800a7b07  or      ebx, 80070000h
0x1800a7b0d  test    ebx, ebx
0x1800a7b0f  mov     [rbp+57h+var_7C], 273h
0x1800a7b16  mov     eax, 8000FFFFh
0x1800a7b1b  cmovns  ebx, eax
0x1800a7b1e  jmp     loc_1800A7DBB
0x1800a7b23  mov     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x1800a7b27  lea     r8, [rbp+57h+dwRevision]; lpdwRevision
0x1800a7b2b  lea     rdx, [rbp+57h+pControl]; pControl
0x1800a7b2f  call    cs:__imp_GetSecurityDescriptorControl
0x1800a7b35  test    eax, eax
0x1800a7b37  jnz     short loc_1800A7B63
0x1800a7b39  call    WxGetLastError
0x1800a7b3e  mov     ebx, eax
0x1800a7b40  test    eax, eax
0x1800a7b42  jle     short loc_1800A7B4D
0x1800a7b44  movzx   ebx, ax
0x1800a7b47  or      ebx, 80070000h
0x1800a7b4d  test    ebx, ebx
0x1800a7b4f  mov     [rbp+57h+var_7C], 275h
0x1800a7b56  mov     eax, 8000FFFFh
0x1800a7b5b  cmovns  ebx, eax
0x1800a7b5e  jmp     loc_1800A7DBB
0x1800a7b63  movzx   r8d, [rbp+57h+pControl]
0x1800a7b68  lea     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x1800a7b6c  and     r8w, 40h
0x1800a7b71  mov     eax, 500h
0x1800a7b76  or      r8w, ax; ControlBitsToSet
0x1800a7b7a  mov     edx, 1540h; ControlBitsOfInterest
0x1800a7b7f  call    cs:__imp_SetSecurityDescriptorControl
0x1800a7b85  test    eax, eax
0x1800a7b87  jnz     short loc_1800A7BB3
0x1800a7b89  call    WxGetLastError
0x1800a7b8e  mov     ebx, eax
0x1800a7b90  test    eax, eax
0x1800a7b92  jle     short loc_1800A7B9D
0x1800a7b94  movzx   ebx, ax
0x1800a7b97  or      ebx, 80070000h
0x1800a7b9d  test    ebx, ebx
0x1800a7b9f  mov     [rbp+57h+var_7C], 27Bh
0x1800a7ba6  mov     eax, 8000FFFFh
0x1800a7bab  cmovns  ebx, eax
0x1800a7bae  jmp     loc_1800A7DBB
0x1800a7bb3  mov     r8, [rbp+57h+var_78]; pDacl
0x1800a7bb7  lea     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x1800a7bbb  xor     r9d, r9d; bDaclDefaulted
0x1800a7bbe  mov     edx, ebx; bDaclPresent
0x1800a7bc0  call    cs:__imp_SetSecurityDescriptorDacl
0x1800a7bc6  test    eax, eax
0x1800a7bc8  jnz     short loc_1800A7BF4
0x1800a7bca  call    WxGetLastError
0x1800a7bcf  mov     ebx, eax
0x1800a7bd1  test    eax, eax
0x1800a7bd3  jle     short loc_1800A7BDE
0x1800a7bd5  movzx   ebx, ax
0x1800a7bd8  or      ebx, 80070000h
0x1800a7bde  test    ebx, ebx
0x1800a7be0  mov     [rbp+57h+var_7C], 27Dh
0x1800a7be7  mov     eax, 8000FFFFh
0x1800a7bec  cmovns  ebx, eax
0x1800a7bef  jmp     loc_1800A7DBB
0x1800a7bf4  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1800a7bf8  mov     edx, 4; SecurityInformation
0x1800a7bfd  mov     rcx, r13; Handle
0x1800a7c00  call    cs:__imp_SetKernelObjectSecurity
0x1800a7c06  test    eax, eax
0x1800a7c08  jnz     short loc_1800A7C34
0x1800a7c0a  call    WxGetLastError
0x1800a7c0f  mov     ebx, eax
0x1800a7c11  test    eax, eax
0x1800a7c13  jle     short loc_1800A7C1E
0x1800a7c15  movzx   ebx, ax
0x1800a7c18  or      ebx, 80070000h
0x1800a7c1e  test    ebx, ebx
0x1800a7c20  mov     [rbp+57h+var_7C], 27Fh
0x1800a7c27  mov     eax, 8000FFFFh
0x1800a7c2c  cmovns  ebx, eax
0x1800a7c2f  jmp     loc_1800A7DBB
0x1800a7c34  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x1800a7c3b  mov     edx, 8; dwFlags
0x1800a7c40  mov     r8d, 428h; dwBytes
0x1800a7c46  call    cs:__imp_HeapAlloc
0x1800a7c4c  mov     r14, rax
0x1800a7c4f  test    rax, rax
0x1800a7c52  jnz     short loc_1800A7C65
0x1800a7c54  mov     ebx, 8007000Eh
0x1800a7c59  mov     [rbp+57h+var_7C], 282h
0x1800a7c60  jmp     loc_1800A7DB8
0x1800a7c65  lea     rcx, [rax+10h]; unsigned __int16 *
0x1800a7c69  mov     dword ptr [rax], 0A0000003h
0x1800a7c6f  mov     r9, rdi
0x1800a7c72  lea     r8, pszFormat; "\\??\\%s"
0x1800a7c79  mov     edx, 104h; unsigned __int64
0x1800a7c7e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a7c83  xor     ecx, ecx
0x1800a7c85  mov     ebx, eax
0x1800a7c87  test    eax, eax
0x1800a7c89  jns     short loc_1800A7C97
0x1800a7c8b  mov     [rbp+57h+var_7C], 286h
0x1800a7c92  jmp     loc_1800A7DA6
0x1800a7c97  mov     rax, rsi
0x1800a7c9a  inc     rax
0x1800a7c9d  cmp     [r14+rax*2+10h], cx
0x1800a7ca3  jnz     short loc_1800A7C9A
0x1800a7ca5  movzx   r10d, ax
0x1800a7ca9  mov     r8, rdi; unsigned __int16 *
0x1800a7cac  mov     edx, 104h; unsigned __int64
0x1800a7cb1  lea     r11, [r14+r10*2]
0x1800a7cb5  lea     rcx, [r11+12h]; unsigned __int16 *
0x1800a7cb9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800a7cbe  xor     edi, edi
0x1800a7cc0  mov     ebx, eax
0x1800a7cc2  test    eax, eax
0x1800a7cc4  jns     short loc_1800A7CD2
0x1800a7cc6  mov     [rbp+57h+var_7C], 28Ah
0x1800a7ccd  jmp     loc_1800A7DA6
0x1800a7cd2  inc     rsi
0x1800a7cd5  cmp     [r11+rsi*2+12h], di
0x1800a7cdb  jnz     short loc_1800A7CD2
0x1800a7cdd  movzx   eax, r10w
0x1800a7ce1  mov     [rsp+0C0h+lpOverlapped], rdi; lpOverlapped
0x1800a7ce6  add     ax, ax
0x1800a7ce9  mov     [rsp+0C0h+hTemplateFile], rdi; lpBytesReturned
  ... truncated ...
```
