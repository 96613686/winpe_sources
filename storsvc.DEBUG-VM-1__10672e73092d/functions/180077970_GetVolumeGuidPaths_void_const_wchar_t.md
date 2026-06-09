# GetVolumeGuidPaths(void * const,wchar_t * *)

- ea: `0x180077970`
- end: `0x180077d5f`
- name: `?GetVolumeGuidPaths@@YAJQEAXPEAPEA_W@Z`
- size: `1007`
- prototype: `__int64 __fastcall(void *const, wchar_t **)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x180075974`

## callees

- `0x18000d030`
- `0x18000d400`
- `0x18000d5a4`
- `0x18000ddb0`
- `0x180012714`
- `0x180012734`
- `0x180019210`
- `0x18001bea0`
- `0x180072288`
- `0x180072720`
- `0x1800771e4`
- `0x180077254`
- `0x180077970`
- `0x18007d4f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077b79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077b79`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180077b6f`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180077b6f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180077b11`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180077b11`

## string_xrefs

- `0x180077b0a`: `\\.\MountPointManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetVolumeGuidPaths(void *const a1, wchar_t **a2)
{
  int DeviceObjectPath; // eax
  HRESULT v3; // ebx
  unsigned __int64 v4; // r9
  __int64 v5; // rdx
  __int64 v6; // rsi
  __int64 v7; // rbx
  DWORD v8; // r13d
  _DWORD *v9; // rax
  _DWORD *v10; // r14
  size_t *v11; // r8
  wchar_t *v12; // rcx
  HANDLE FileW; // rax
  const struct std::nothrow_t *v15; // rdx
  const char *v16; // r9
  HANDLE v17; // rbx
  DWORD v18; // r15d
  unsigned __int64 i; // rcx
  DWORD v20; // eax
  const struct std::nothrow_t *v21; // rdx
  _DWORD *v22; // rdi
  __int64 v23; // r9
  __int64 v24; // rdx
  int LastError; // eax
  int v26; // r14d
  unsigned int v27; // edx
  const wchar_t *v28; // r12
  size_t v29; // rbx
  unsigned __int64 v30; // rax
  wchar_t *v31; // rax
  size_t *v32; // r8
  HRESULT v33; // eax
  wchar_t *v34; // rbx
  const struct std::nothrow_t *v35; // rdx
  int cchToCopy; // [rsp+20h] [rbp-79h]
  unsigned int cchToCopya; // [rsp+20h] [rbp-79h]
  HANDLE hDevice; // [rsp+40h] [rbp-59h] BYREF
  wchar_t **v39; // [rsp+48h] [rbp-51h]
  char v40[8]; // [rsp+50h] [rbp-49h] BYREF
  void **v41; // [rsp+58h] [rbp-41h]
  void **v42; // [rsp+60h] [rbp-39h]
  STRSAFE_PCNZWCH *p_pszSrc; // [rsp+68h] [rbp-31h]
  wchar_t **p_String1; // [rsp+70h] [rbp-29h]
  wchar_t **v45; // [rsp+78h] [rbp-21h]
  wchar_t *v46; // [rsp+80h] [rbp-19h] BYREF
  void *v47; // [rsp+88h] [rbp-11h] BYREF
  wchar_t *String1; // [rsp+90h] [rbp-9h] BYREF
  STRSAFE_PCNZWCH pszSrc; // [rsp+98h] [rbp-1h] BYREF
  char *v50; // [rsp+A0h] [rbp+7h] BYREF
  DWORD BytesReturned; // [rsp+A8h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v39 = a2;
  v50 = 0;
  v47 = 0;
  pszSrc = 0;
  v46 = 0;
  String1 = 0;
  BytesReturned = 0;
  v40[0] = 1;
  v41 = (void **)&v50;
  v42 = &v47;
  p_pszSrc = &pszSrc;
  p_String1 = &String1;
  v45 = &v46;
  DeviceObjectPath = GetDeviceObjectPath(a1, (wchar_t **)&pszSrc);
  v3 = DeviceObjectPath;
  if ( DeviceObjectPath < 0 )
  {
    v4 = (unsigned int)DeviceObjectPath;
    v5 = 48;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\base\\wcp\\storage\\storagehelper\\volumefunctions.cpp",
      (const char *)v4,
      cchToCopy);
    goto LABEL_14;
  }
  v6 = -1;
  v7 = -1;
  do
    ++v7;
  while ( pszSrc[v7] );
  v8 = 2 * v7 + 26;
  v9 = operator new[](v8, (const struct std::nothrow_t *)std::nothrow);
  v10 = v9;
  v50 = (char *)v9;
  if ( !v9 )
  {
    v3 = -2147024882;
    v5 = 56;
LABEL_12:
    v4 = (unsigned int)v3;
    goto LABEL_13;
  }
  memset_0(v9, 0, v8);
  v10[4] = 24;
  *((_WORD *)v10 + 10) = 2 * v7;
  if ( !((unsigned __int64)(unsigned int)(2 * v7 + 2) >> 1) )
    goto LABEL_10;
  v12 = (wchar_t *)(v50 + 24);
  if ( (unsigned int)v7 > 0x7FFFFFFEuLL )
  {
    *v12 = 0;
LABEL_10:
    v3 = -2147024809;
LABEL_11:
    v5 = 69;
    goto LABEL_12;
  }
  v3 = StringCopyWorkerW_0(v12, (unsigned __int64)(unsigned int)(2 * v7 + 2) >> 1, v11, pszSrc, (unsigned int)v7);
  if ( v3 < 0 )
    goto LABEL_11;
  hDevice = 0;
  FileW = CreateFileW(L"\\\\.\\MountPointManager", 0, 3u, 0, 3u, 0x80u, 0);
  Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(
    &hDevice,
    FileW);
  v17 = hDevice;
  if ( (char *)hDevice - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x54,
                  (unsigned int)"onecore\\base\\wcp\\storage\\storagehelper\\volumefunctions.cpp",
                  v16);
    goto LABEL_47;
  }
  operator delete(v47, v15);
  v18 = 768;
  for ( i = 768; ; i = v18 )
  {
    v47 = operator new[](i, (const struct std::nothrow_t *)std::nothrow);
    v22 = v47;
    if ( !v47 )
    {
      v3 = -2147024882;
      v23 = 2147942414LL;
      v24 = 94;
      goto LABEL_40;
    }
    if ( DeviceIoControl(v17, 0x6D0008u, v10, v8, v47, v18, &BytesReturned, 0) )
      break;
    v20 = GetLastError();
    if ( v20 == 2 )
      goto LABEL_45;
    if ( v20 != 234 )
    {
      if ( v20 )
      {
        LastError = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)0x77,
                      (unsigned int)"onecore\\base\\wcp\\storage\\storagehelper\\volumefunctions.cpp",
                      (const char *)v20,
                      cchToCopya);
LABEL_47:
        v3 = LastError;
        goto LABEL_48;
      }
LABEL_45:
      Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&hDevice);
      Windows::Detail::OnBlockExitImpl__GetVolumeGuidPaths_::_2_::_lambda_1___::_OnBlockExitImpl__GetVolumeGuidPaths_::_2_::_lambda_1___(v40);
      return 0;
    }
    v18 += 256;
    operator delete(v47, v21);
  }
  v26 = 0;
  if ( !v22[1] )
  {
LABEL_35:
    v34 = v46;
LABEL_36:
    if ( !v34 )
    {
      v3 = -2147024893;
      v23 = 2147942403LL;
      v24 = 160;
      goto LABEL_40;
    }
    do
      ++v6;
    while ( v34[v6] );
    v34[1] = 92;
    v46[v6] = 92;
    v46[v6 + 1] = 0;
    if ( v39 )
    {
      *v39 = v46;
      v46 = 0;
    }
    goto LABEL_45;
  }
  while ( 1 )
  {
    v27 = LOWORD(v22[6 * v26 + 3]);
    if ( !(_WORD)v27 )
      goto LABEL_34;
    v28 = (const wchar_t *)((char *)v47 + (unsigned int)v22[6 * v26 + 2]);
    v29 = v27 >> 1;
    v30 = 2LL * (unsigned int)(v29 + 2);
    if ( !is_mul_ok((unsigned int)(v29 + 2), 2u) )
      v30 = -1;
    v31 = (wchar_t *)operator new[](v30, (const struct std::nothrow_t *)std::nothrow);
    String1 = v31;
    if ( !v31 )
      break;
    v33 = StringCopyWorkerW_0(v31, (unsigned int)(v29 + 2), v32, v28, v29);
    v3 = v33;
    if ( v33 < 0 )
    {
      v23 = (unsigned int)v33;
      v24 = 146;
      goto LABEL_40;
    }
    v34 = String1;
    if ( !wcsncmp_0(String1, L"\\??\\Volume{", 0xBu) )
    {
      v46 = v34;
      String1 = 0;
      goto LABEL_36;
    }
    operator delete(v34, v35);
    String1 = 0;
LABEL_34:
    if ( (unsigned int)++v26 >= v22[1] )
      goto LABEL_35;
  }
  v3 = -2147024882;
  v23 = 2147942414LL;
  v24 = 144;
LABEL_40:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v24,
    (unsigned int)"onecore\\base\\wcp\\storage\\storagehelper\\volumefunctions.cpp",
    (const char *)v23,
    cchToCopya);
LABEL_48:
  Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&hDevice);
LABEL_14:
  Windows::Detail::OnBlockExitImpl__GetVolumeGuidPaths_::_2_::_lambda_1___::_OnBlockExitImpl__GetVolumeGuidPaths_::_2_::_lambda_1___(v40);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180077970  mov     [rsp-8+arg_10], rbx
0x180077975  push    rbp
0x180077976  push    rsi
0x180077977  push    rdi
0x180077978  push    r12
0x18007797a  push    r13
0x18007797c  push    r14
0x18007797e  push    r15
0x180077980  lea     rbp, [rsp-27h]
0x180077985  sub     rsp, 0C0h
0x18007798c  mov     rax, cs:__security_cookie
0x180077993  xor     rax, rsp
0x180077996  mov     [rbp+57h+var_40], rax
0x18007799a  mov     [rbp+57h+var_A8], rdx
0x18007799e  xor     r12d, r12d
0x1800779a1  mov     [rbp+57h+var_50], r12
0x1800779a5  mov     [rbp+57h+var_68], r12
0x1800779a9  mov     [rbp+57h+pszSrc], r12
0x1800779ad  mov     [rbp+57h+var_70], r12
0x1800779b1  mov     [rbp+57h+String1], r12
0x1800779b5  mov     [rbp+57h+BytesReturned], r12d
0x1800779b9  mov     [rbp+57h+var_A0], 1
0x1800779bd  lea     rax, [rbp+57h+var_50]
0x1800779c1  mov     [rbp+57h+var_98], rax
0x1800779c5  lea     rax, [rbp+57h+var_68]
0x1800779c9  mov     [rbp+57h+var_90], rax
0x1800779cd  lea     rax, [rbp+57h+pszSrc]
0x1800779d1  mov     [rbp+57h+var_88], rax
0x1800779d5  lea     rax, [rbp+57h+String1]
0x1800779d9  mov     [rbp+57h+var_80], rax
0x1800779dd  lea     rax, [rbp+57h+var_70]
0x1800779e1  mov     [rbp+57h+var_78], rax
0x1800779e5  lea     rdx, [rbp+57h+pszSrc]; wchar_t **
0x1800779e9  call    ?GetDeviceObjectPath@@YAJQEAXPEAPEA_W@Z; GetDeviceObjectPath(void * const,wchar_t * *)
0x1800779ee  mov     ebx, eax
0x1800779f0  test    eax, eax
0x1800779f2  jns     short loc_180077A01
0x1800779f4  mov     r9d, eax
0x1800779f7  lea     edx, [r12+30h]
0x1800779fc  jmp     loc_180077A92
0x180077a01  mov     rax, [rbp+57h+pszSrc]
0x180077a05  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180077a09  mov     rbx, rsi
0x180077a0c  inc     rbx
0x180077a0f  cmp     [rax+rbx*2], r12w
0x180077a14  jnz     short loc_180077A0C
0x180077a16  lea     r13d, ds:1Ah[rbx*2]
0x180077a1e  mov     edi, r13d
0x180077a21  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180077a28  mov     ecx, r13d; unsigned __int64
0x180077a2b  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180077a30  mov     r14, rax
0x180077a33  mov     [rbp+57h+var_50], rax
0x180077a37  test    rax, rax
0x180077a3a  jnz     short loc_180077A46
0x180077a3c  mov     ebx, 8007000Eh
0x180077a41  lea     edx, [rax+38h]
0x180077a44  jmp     short loc_180077A8F
0x180077a46  mov     r8, rdi; Size
0x180077a49  xor     edx, edx; Val
0x180077a4b  mov     rcx, r14; void *
0x180077a4e  call    memset_0
0x180077a53  mov     dword ptr [r14+10h], 18h
0x180077a5b  movzx   eax, bx
0x180077a5e  add     ax, ax
0x180077a61  mov     [r14+14h], ax
0x180077a66  lea     edx, [r13-18h]
0x180077a6a  shr     rdx, 1; cchDest
0x180077a6d  jz      short loc_180077A85
0x180077a6f  mov     rcx, [rbp+57h+var_50]
0x180077a73  add     rcx, 18h; pszDest
0x180077a77  mov     eax, ebx
0x180077a79  cmp     rax, 7FFFFFFEh
0x180077a7f  jbe     short loc_180077AD5
0x180077a81  mov     [rcx], r12w
0x180077a85  mov     ebx, 80070057h
0x180077a8a  mov     edx, 45h ; 'E'; void *
0x180077a8f  mov     r9d, ebx; char *
0x180077a92  lea     r8, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\storage\\storagehel"...
0x180077a99  mov     rcx, [rbp+5Fh]; this
0x180077a9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180077aa2  nop
0x180077aa3  lea     rcx, [rbp+57h+var_A0]
0x180077aa7  call    Windows__Detail__OnBlockExitImpl__GetVolumeGuidPaths____2____lambda_1______OnBlockExitImpl__GetVolumeGuidPaths____2____lambda_1___
0x180077aac  mov     eax, ebx
0x180077aae  mov     rcx, [rbp+57h+var_40]
0x180077ab2  xor     rcx, rsp; StackCookie
0x180077ab5  call    __security_check_cookie
0x180077aba  mov     rbx, [rsp+0F0h+arg_10]
0x180077ac2  add     rsp, 0C0h
0x180077ac9  pop     r15
0x180077acb  pop     r14
0x180077acd  pop     r13
0x180077acf  pop     r12
0x180077ad1  pop     rdi
0x180077ad2  pop     rsi
0x180077ad3  pop     rbp
0x180077ad4  retn
0x180077ad5  mov     [rsp+0F0h+cchToCopy], rax; cchToCopy
0x180077ada  mov     r9, [rbp+57h+pszSrc]; pszSrc
0x180077ade  call    StringCopyWorkerW_0
0x180077ae3  mov     ebx, eax
0x180077ae5  test    eax, eax
0x180077ae7  js      short loc_180077A8A
0x180077ae9  mov     [rbp+57h+hDevice], r12
0x180077aed  mov     [rsp+0F0h+hTemplateFile], r12; hTemplateFile
0x180077af2  mov     [rsp+0F0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180077afa  mov     r8d, 3; dwShareMode
0x180077b00  mov     dword ptr [rsp+0F0h+cchToCopy], r8d; dwCreationDisposition
0x180077b05  xor     r9d, r9d; lpSecurityAttributes
0x180077b08  xor     edx, edx; dwDesiredAccess
0x180077b0a  lea     rcx, aMountpointmana; "\\\\.\\MountPointManager"
0x180077b11  call    cs:__imp_CreateFileW
0x180077b17  mov     rdx, rax
0x180077b1a  lea     rcx, [rbp+57h+hDevice]
0x180077b1e  call    ?TakeOwnership@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXPEAX@Z; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(void *)
0x180077b23  mov     rbx, [rbp+57h+hDevice]
0x180077b27  lea     rax, [rbx-1]
0x180077b2b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180077b2f  ja      loc_180077D39
0x180077b35  mov     rcx, [rbp+57h+var_68]; void *
0x180077b39  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180077b3e  mov     r15d, 300h
0x180077b44  mov     ecx, r15d
0x180077b47  jmp     short loc_180077BA2
0x180077b49  mov     [rsp+0F0h+lpOverlapped], r12; lpOverlapped
0x180077b4e  lea     rax, [rbp+57h+BytesReturned]
0x180077b52  mov     [rsp+0F0h+hTemplateFile], rax; lpBytesReturned
0x180077b57  mov     [rsp+0F0h+dwFlagsAndAttributes], r15d; nOutBufferSize
0x180077b5c  mov     [rsp+0F0h+cchToCopy], rdi; unsigned int
0x180077b61  mov     r9d, r13d; nInBufferSize
0x180077b64  mov     r8, r14; lpInBuffer
0x180077b67  mov     edx, 6D0008h; dwIoControlCode
0x180077b6c  mov     rcx, rbx; hDevice
0x180077b6f  call    cs:__imp_DeviceIoControl
0x180077b75  test    eax, eax
0x180077b77  jnz     short loc_180077BF1
0x180077b79  call    cs:__imp_GetLastError
0x180077b7f  cmp     eax, 2
0x180077b82  jz      loc_180077D1F
0x180077b88  cmp     eax, 0EAh
0x180077b8d  jnz     short loc_180077BCC
0x180077b8f  add     r15d, 100h
0x180077b96  mov     rcx, [rbp+57h+var_68]; void *
0x180077b9a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180077b9f  mov     ecx, r15d; unsigned __int64
0x180077ba2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180077ba9  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180077bae  test    rax, rax
0x180077bb1  mov     [rbp+57h+var_68], rax
0x180077bb5  mov     rdi, rax
0x180077bb8  jnz     short loc_180077B49
0x180077bba  mov     ebx, 8007000Eh
0x180077bbf  mov     r9d, ebx
0x180077bc2  mov     edx, 5Eh ; '^'
0x180077bc7  jmp     loc_180077CC5
0x180077bcc  test    eax, eax
0x180077bce  jz      loc_180077D1F
0x180077bd4  mov     rcx, [rbp+5Fh]; this
0x180077bd8  mov     r9d, eax; char *
0x180077bdb  lea     r8, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\storage\\storagehel"...
0x180077be2  mov     edx, 77h ; 'w'; void *
0x180077be7  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180077bec  jmp     loc_180077D4E
0x180077bf1  mov     r14d, r12d
0x180077bf4  cmp     [rdi+4], r12d
0x180077bf8  jbe     loc_180077C9B
0x180077bfe  mov     eax, r14d
0x180077c01  lea     rcx, [rax+rax*2]
0x180077c05  movzx   edx, word ptr [rdi+rcx*8+0Ch]
0x180077c0a  test    dx, dx
0x180077c0d  jz      short loc_180077C8E
0x180077c0f  mov     r12d, [rdi+rcx*8+8]
0x180077c14  add     r12, [rbp+57h+var_68]
0x180077c18  mov     eax, edx
0x180077c1a  shr     eax, 1
0x180077c1c  mov     ebx, eax
0x180077c1e  lea     r15d, [rax+2]
0x180077c22  mov     eax, 2
0x180077c27  mul     r15
0x180077c2a  cmovb   rax, rsi
0x180077c2e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180077c35  mov     rcx, rax; unsigned __int64
0x180077c38  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180077c3d  mov     [rbp+57h+String1], rax
0x180077c41  test    rax, rax
0x180077c44  jz      loc_180077CD7
0x180077c4a  mov     [rsp+0F0h+cchToCopy], rbx; int
0x180077c4f  mov     r9, r12; pszSrc
0x180077c52  mov     edx, r15d; cchDest
0x180077c55  mov     rcx, rax; pszDest
0x180077c58  call    StringCopyWorkerW_0
0x180077c5d  mov     ebx, eax
0x180077c5f  xor     r12d, r12d
0x180077c62  test    eax, eax
0x180077c64  js      short loc_180077CBD
0x180077c66  lea     r8d, [r12+0Bh]; MaxCount
0x180077c6b  lea     rdx, aVolume; "\\??\\Volume{"
0x180077c72  mov     rbx, [rbp+57h+String1]
0x180077c76  mov     rcx, rbx; String1
0x180077c79  call    wcsncmp_0
0x180077c7e  test    eax, eax
0x180077c80  jz      short loc_180077CB3
0x180077c82  mov     rcx, rbx; void *
0x180077c85  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180077c8a  mov     [rbp+57h+String1], r12
0x180077c8e  inc     r14d
0x180077c91  cmp     r14d, [rdi+4]
0x180077c95  jb      loc_180077BFE
0x180077c9b  mov     rbx, [rbp+57h+var_70]
0x180077c9f  test    rbx, rbx
0x180077ca2  jnz     short loc_180077CE6
0x180077ca4  mov     ebx, 80070003h
0x180077ca9  mov     r9d, ebx
0x180077cac  mov     edx, 0A0h
0x180077cb1  jmp     short loc_180077CC5
0x180077cb3  mov     [rbp+57h+var_70], rbx
0x180077cb7  mov     [rbp+57h+String1], r12
0x180077cbb  jmp     short loc_180077C9F
0x180077cbd  mov     r9d, eax; char *
0x180077cc0  mov     edx, 92h; void *
0x180077cc5  lea     r8, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\storage\\storagehel"...
0x180077ccc  mov     rcx, [rbp+5Fh]; this
0x180077cd0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180077cd5  jmp     short loc_180077D50
0x180077cd7  mov     ebx, 8007000Eh
0x180077cdc  mov     r9d, ebx
0x180077cdf  mov     edx, 90h
0x180077ce4  jmp     short loc_180077CC5
0x180077ce6  inc     rsi
0x180077ce9  cmp     [rbx+rsi*2], r12w
0x180077cee  jnz     short loc_180077CE6
0x180077cf0  mov     ecx, 5Ch ; '\'
0x180077cf5  mov     [rbx+2], cx
0x180077cf9  mov     rax, [rbp+57h+var_70]
0x180077cfd  mov     [rax+rsi*2], cx
0x180077d01  mov     rax, [rbp+57h+var_70]
0x180077d05  mov     [rax+rsi*2+2], r12w
0x180077d0b  mov     rcx, [rbp+57h+var_A8]
0x180077d0f  test    rcx, rcx
0x180077d12  jz      short loc_180077D1F
0x180077d14  mov     rax, [rbp+57h+var_70]
0x180077d18  mov     [rcx], rax
0x180077d1b  mov     [rbp+57h+var_70], r12
0x180077d1f  lea     rcx, [rbp+57h+hDevice]
0x180077d23  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x180077d28  nop
0x180077d29  lea     rcx, [rbp+57h+var_A0]
0x180077d2d  call    Windows__Detail__OnBlockExitImpl__GetVolumeGuidPaths____2____lambda_1______OnBlockExitImpl__GetVolumeGuidPaths____2____lambda_1___
0x180077d32  xor     eax, eax
0x180077d34  jmp     loc_180077AAE
0x180077d39  mov     rcx, [rbp+5Fh]; this
0x180077d3d  lea     r8, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\storage\\storagehel"...
0x180077d44  mov     edx, 54h ; 'T'; void *
0x180077d49  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180077d4e  mov     ebx, eax
0x180077d50  lea     rcx, [rbp+57h+hDevice]
0x180077d54  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x180077d59  jmp     loc_180077AA3
```
