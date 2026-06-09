# CreateArchiveWizard::Browse(HWND__ *)

- ea: `0x180050b40`
- end: `0x180050f1a`
- name: `?Browse@CreateArchiveWizard@@AEAAJPEAUHWND__@@@Z`
- size: `986`
- prototype: `int(CreateArchiveWizard *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180050fe4`

## callees

- `0x180024a24`
- `0x180030a3c`
- `0x180031e94`
- `0x180033aa8`
- `0x180035728`
- `0x180036f50`
- `0x180037958`
- `0x180041470`
- `0x180050b40`
- `0x180071010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180050cea`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180050cea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050e22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050ebc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050e22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050ebc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180050be6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180050be6`
- `USER32!SetDlgItemTextW` at `0x180050e89`
- `USER32!SetDlgItemTextW` at `0x180050e89`

## string_xrefs

- `0x180050bad`: `shell\ext\zip\archive\createarchivewizard.cpp`
- `0x180050c01`: `shell\ext\zip\archive\createarchivewizard.cpp`
- `0x180050e05`: `shell\ext\zip\archive\createarchivewizard.cpp`
- `0x180050e9a`: `shell\ext\zip\archive\createarchivewizard.cpp`

## pseudocode

```c
__int64 __fastcall CreateArchiveWizard::Browse(CreateArchiveWizard *this, HWND a2)
{
  int v4; // eax
  int LastError; // ebx
  HRESULT v6; // eax
  __int64 v7; // rdx
  __int64 v8; // rdx
  _WORD *v9; // r8
  __int64 v10; // r10
  __int64 v11; // r9
  __int16 v12; // ax
  __int64 v13; // r8
  _WORD *v14; // rcx
  __int64 v15; // r9
  __int64 v16; // rdx
  __int16 v17; // ax
  WCHAR *v18; // rcx
  WCHAR *p_Buffer; // rdx
  WCHAR v20; // ax
  int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, __int64, LPVOID *); // rbx
  const char *v25; // r9
  _BYTE v27[32]; // [rsp+0h] [rbp-100h] BYREF
  _QWORD v28[3]; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v29[2]; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v31; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-98h] BYREF
  int v33; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v34[28]; // [rsp+74h] [rbp-8Ch] BYREF
  WCHAR Buffer; // [rsp+90h] [rbp-70h] BYREF
  char v36[526]; // [rsp+92h] [rbp-6Eh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  memset(v28, 0, sizeof(v28));
  v4 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(
         v28,
         &_ImageBase,
         10613);
  LastError = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x21B,
      (unsigned int)"shell\\ext\\zip\\archive\\createarchivewizard.cpp",
      (const char *)(unsigned int)v4);
    goto LABEL_50;
  }
  ppv = 0;
  v6 = CoCreateInstance(&CLSID_FileSaveDialog, 0, 3u, &GUID_42f85136_db7e_439c_85f1_e4075d135fc8, &ppv);
  LastError = v6;
  if ( v6 < 0 )
  {
    v7 = 542;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"shell\\ext\\zip\\archive\\createarchivewizard.cpp",
      (const char *)(unsigned int)v6);
    goto LABEL_6;
  }
  v6 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 136LL))(ppv, v28[0]);
  LastError = v6;
  if ( v6 < 0 )
  {
    v7 = 543;
    goto LABEL_5;
  }
  v6 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 72LL))(ppv, 32834);
  LastError = v6;
  if ( v6 < 0 )
  {
    v7 = 544;
    goto LABEL_5;
  }
  Buffer = 0;
  memset_0(v36, 0, 0x206u);
  v33 = 42;
  memset(v34, 0, sizeof(v34));
  v8 = *((_QWORD *)this + 9);
  if ( (_UNKNOWN *)v8 != &g_rawFormatData )
  {
    v9 = &v27[110];
    do
      ++v9;
    while ( *v9 );
    v10 = *(_QWORD *)(v8 + 8);
    v11 = 0;
    do
    {
      v12 = *(_WORD *)(v10 + 2 * v11);
      v9[v11++] = v12;
    }
    while ( v12 );
    LoadStringW(&_ImageBase, *(_DWORD *)(v8 + 4), &Buffer, 260);
  }
  if ( !*(_QWORD *)(*((_QWORD *)this + 9) + 40LL) )
  {
    v13 = *((_QWORD *)this + 10);
    if ( v13 )
    {
      v14 = &v27[110];
      do
        ++v14;
      while ( *v14 );
      v15 = *(_QWORD *)(v13 + 24);
      v16 = 0;
      do
      {
        v17 = *(_WORD *)(v15 + 2 * v16);
        v14[v16++] = v17;
      }
      while ( v17 );
      if ( !Buffer )
      {
        v18 = *(WCHAR **)(v13 + 8);
        p_Buffer = &Buffer;
        do
        {
          v20 = *v18;
          *p_Buffer++ = *v18++;
        }
        while ( v20 );
      }
    }
  }
  v29[0] = &Buffer;
  v29[1] = &v33;
  v6 = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD *))(*(_QWORD *)ppv + 32LL))(ppv, 1, v29);
  LastError = v6;
  if ( v6 < 0 )
  {
    v7 = 564;
    goto LABEL_5;
  }
  v6 = (*(__int64 (__fastcall **)(LPVOID, _BYTE *))(*(_QWORD *)ppv + 176LL))(ppv, v34);
  LastError = v6;
  if ( v6 < 0 )
  {
    v7 = 567;
    goto LABEL_5;
  }
  LastError = (*(__int64 (__fastcall **)(LPVOID, HWND))(*(_QWORD *)ppv + 24LL))(ppv, a2);
  if ( LastError < 0 )
  {
LABEL_6:
    if ( ppv )
      winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&ppv);
    goto LABEL_50;
  }
  v31 = 0;
  pv = 0;
  v21 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 160LL))(ppv, &v31);
  LastError = v21;
  if ( v21 < 0 )
  {
    v22 = 576;
LABEL_34:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v22,
      (unsigned int)"shell\\ext\\zip\\archive\\createarchivewizard.cpp",
      (const char *)(unsigned int)v21);
LABEL_35:
    if ( pv )
      CoTaskMemFree(pv);
    if ( v31 )
      winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v31);
    goto LABEL_6;
  }
  v23 = v31;
  v24 = *(__int64 (__fastcall **)(__int64, __int64, LPVOID *))(*(_QWORD *)v31 + 40LL);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &pv,
    0);
  v21 = v24(v23, 2147844096LL, &pv);
  LastError = v21;
  if ( v21 < 0 )
  {
    v22 = 577;
    goto LABEL_34;
  }
  if ( !SetDlgItemTextW(a2, 10650, (LPCWSTR)pv) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x242,
                  (unsigned int)"shell\\ext\\zip\\archive\\createarchivewizard.cpp",
                  v25);
    goto LABEL_35;
  }
  if ( pv )
    CoTaskMemFree(pv);
  if ( v31 )
    winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v31);
  if ( ppv )
    winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&ppv);
  LastError = 0;
LABEL_50:
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v28);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180050b40  mov     [rsp-8+arg_10], rbx
0x180050b45  mov     [rsp-8+arg_18], rsi
0x180050b4a  push    rbp
0x180050b4b  push    rdi
0x180050b4c  push    r14
0x180050b4e  lea     rbp, [rsp-1B0h]
0x180050b56  sub     rsp, 2B0h
0x180050b5d  mov     rax, cs:__security_cookie
0x180050b64  xor     rax, rsp
0x180050b67  mov     [rbp+1C0h+var_20], rax
0x180050b6e  mov     rsi, rdx
0x180050b71  mov     rdi, rcx
0x180050b74  xor     r14d, r14d
0x180050b77  mov     [rsp+2C0h+var_290], r14
0x180050b7c  mov     [rsp+2C0h+var_288], r14
0x180050b81  mov     [rsp+2C0h+var_280], r14
0x180050b86  mov     r8d, 2975h
0x180050b8c  lea     rdx, __ImageBase
0x180050b93  lea     rcx, [rsp+2C0h+var_290]
0x180050b98  call    ?Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@IG@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Initialize(HINSTANCE__ *,uint,ushort)
0x180050b9d  mov     ebx, eax
0x180050b9f  test    eax, eax
0x180050ba1  jns     short loc_180050BC3
0x180050ba3  mov     rcx, [rbp+1C8h]
0x180050baa  mov     r9d, eax
0x180050bad  lea     r8, aShellExtZipArc_1; "shell\\ext\\zip\\archive\\createarchive"...
0x180050bb4  mov     edx, 21Bh
0x180050bb9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050bbe  jmp     loc_180050EE7
0x180050bc3  mov     [rsp+2C0h+var_268], r14
0x180050bc8  lea     rax, [rsp+2C0h+var_268]
0x180050bcd  mov     [rsp+2C0h+ppv], rax; ppv
0x180050bd2  lea     r9, _GUID_42f85136_db7e_439c_85f1_e4075d135fc8; riid
0x180050bd9  xor     edx, edx; pUnkOuter
0x180050bdb  lea     r8d, [rdx+3]; dwClsContext
0x180050bdf  lea     rcx, CLSID_FileSaveDialog; rclsid
0x180050be6  call    cs:__imp_CoCreateInstance
0x180050bec  mov     ebx, eax
0x180050bee  test    eax, eax
0x180050bf0  jns     short loc_180050C27
0x180050bf2  mov     edx, 21Eh
0x180050bf7  mov     rcx, [rbp+1C8h]
0x180050bfe  mov     r9d, eax
0x180050c01  lea     r8, aShellExtZipArc_1; "shell\\ext\\zip\\archive\\createarchive"...
0x180050c08  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050c0d  cmp     [rsp+2C0h+var_268], r14
0x180050c12  jz      loc_180050EE7
0x180050c18  lea     rcx, [rsp+2C0h+var_268]
0x180050c1d  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x180050c22  jmp     loc_180050EE7
0x180050c27  mov     rcx, [rsp+2C0h+var_268]
0x180050c2c  mov     rax, [rcx]
0x180050c2f  mov     rdx, [rsp+2C0h+var_290]
0x180050c34  mov     rax, [rax+88h]
0x180050c3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050c40  mov     ebx, eax
0x180050c42  test    eax, eax
0x180050c44  jns     short loc_180050C4D
0x180050c46  mov     edx, 21Fh
0x180050c4b  jmp     short loc_180050BF7
0x180050c4d  mov     rcx, [rsp+2C0h+var_268]
0x180050c52  mov     rax, [rcx]
0x180050c55  mov     edx, 8042h
0x180050c5a  mov     rax, [rax+48h]
0x180050c5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050c63  mov     ebx, eax
0x180050c65  test    eax, eax
0x180050c67  jns     short loc_180050C70
0x180050c69  mov     edx, 220h
0x180050c6e  jmp     short loc_180050BF7
0x180050c70  mov     [rbp+1C0h+Buffer], r14w
0x180050c75  xor     edx, edx; Val
0x180050c77  mov     r8d, 206h; Size
0x180050c7d  lea     rcx, [rbp+1C0h+var_22E]; void *
0x180050c81  call    memset_0
0x180050c86  mov     [rsp+2C0h+var_250], 2Ah ; '*'
0x180050c8e  xorps   xmm0, xmm0
0x180050c91  movups  xmmword ptr [rsp+2C0h+var_24C], xmm0
0x180050c96  movups  xmmword ptr [rbp+1C0h+var_24C+0Ch], xmm0
0x180050c9a  mov     rdx, [rdi+48h]
0x180050c9e  lea     rax, ?g_rawFormatData@@3UArchiveFormatSupportData@@B; ArchiveFormatSupportData const g_rawFormatData
0x180050ca5  cmp     rdx, rax
0x180050ca8  jz      short loc_180050CF0
0x180050caa  lea     r8, [rsp+2C0h+var_250]
0x180050caf  sub     r8, 2
0x180050cb3  lea     r8, [r8+2]
0x180050cb7  cmp     [r8], r14w
0x180050cbb  jnz     short loc_180050CB3
0x180050cbd  mov     r10, [rdx+8]
0x180050cc1  xor     r9d, r9d
0x180050cc4  movzx   eax, word ptr [r10+r9*2]
0x180050cc9  mov     [r8+r9*2], ax
0x180050cce  inc     r9
0x180050cd1  test    ax, ax
0x180050cd4  jnz     short loc_180050CC4
0x180050cd6  mov     r9d, 104h; cchBufferMax
0x180050cdc  lea     r8, [rbp+1C0h+Buffer]; lpBuffer
0x180050ce0  mov     edx, [rdx+4]; uID
0x180050ce3  lea     rcx, __ImageBase; hInstance
0x180050cea  call    cs:__imp_LoadStringW
0x180050cf0  mov     rax, [rdi+48h]
0x180050cf4  cmp     [rax+28h], r14
0x180050cf8  ja      short loc_180050D4F
0x180050cfa  mov     r8, [rdi+50h]
0x180050cfe  test    r8, r8
0x180050d01  jz      short loc_180050D4F
0x180050d03  lea     rcx, [rsp+2C0h+var_250]
0x180050d08  sub     rcx, 2
0x180050d0c  lea     rcx, [rcx+2]
0x180050d10  cmp     [rcx], r14w
0x180050d14  jnz     short loc_180050D0C
0x180050d16  mov     r9, [r8+18h]
0x180050d1a  xor     edx, edx
0x180050d1c  movzx   eax, word ptr [r9+rdx*2]
0x180050d21  mov     [rcx+rdx*2], ax
0x180050d25  inc     rdx
0x180050d28  test    ax, ax
0x180050d2b  jnz     short loc_180050D1C
0x180050d2d  cmp     [rbp+1C0h+Buffer], r14w
0x180050d32  jnz     short loc_180050D4F
0x180050d34  mov     rcx, [r8+8]
0x180050d38  lea     rdx, [rbp+1C0h+Buffer]
0x180050d3c  movzx   eax, word ptr [rcx]
0x180050d3f  mov     [rdx], ax
0x180050d42  lea     rcx, [rcx+2]
0x180050d46  lea     rdx, [rdx+2]
0x180050d4a  test    ax, ax
0x180050d4d  jnz     short loc_180050D3C
0x180050d4f  lea     rax, [rbp+1C0h+Buffer]
0x180050d53  mov     [rsp+2C0h+var_278], rax
0x180050d58  lea     rax, [rsp+2C0h+var_250]
0x180050d5d  mov     [rsp+2C0h+var_270], rax
0x180050d62  mov     rcx, [rsp+2C0h+var_268]
0x180050d67  mov     rax, [rcx]
0x180050d6a  lea     r8, [rsp+2C0h+var_278]
0x180050d6f  mov     edx, 1
0x180050d74  mov     rax, [rax+20h]
0x180050d78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050d7d  mov     ebx, eax
0x180050d7f  test    eax, eax
0x180050d81  jns     short loc_180050D8D
0x180050d83  mov     edx, 234h
0x180050d88  jmp     loc_180050BF7
0x180050d8d  mov     rcx, [rsp+2C0h+var_268]
0x180050d92  mov     rax, [rcx]
0x180050d95  lea     rdx, [rsp+2C0h+var_24C]
0x180050d9a  mov     rax, [rax+0B0h]
0x180050da1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050da6  mov     ebx, eax
0x180050da8  test    eax, eax
0x180050daa  jns     short loc_180050DB6
0x180050dac  mov     edx, 237h
0x180050db1  jmp     loc_180050BF7
0x180050db6  mov     rcx, [rsp+2C0h+var_268]
0x180050dbb  mov     rax, [rcx]
0x180050dbe  mov     rdx, rsi
0x180050dc1  mov     rax, [rax+18h]
0x180050dc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050dca  mov     ebx, eax
0x180050dcc  test    eax, eax
0x180050dce  js      loc_180050C0D
0x180050dd4  mov     [rsp+2C0h+var_260], r14
0x180050dd9  mov     [rsp+2C0h+pv], r14
0x180050dde  mov     rcx, [rsp+2C0h+var_268]
0x180050de3  mov     rax, [rcx]
0x180050de6  lea     rdx, [rsp+2C0h+var_260]
0x180050deb  mov     rax, [rax+0A0h]
0x180050df2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050df7  mov     ebx, eax
0x180050df9  test    eax, eax
0x180050dfb  jns     short loc_180050E42
0x180050dfd  mov     edx, 240h
0x180050e02  mov     r9d, eax
0x180050e05  lea     r8, aShellExtZipArc_1; "shell\\ext\\zip\\archive\\createarchive"...
0x180050e0c  mov     rcx, [rbp+1C8h]
0x180050e13  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050e18  mov     rcx, [rsp+2C0h+pv]; pv
0x180050e1d  test    rcx, rcx
0x180050e20  jz      short loc_180050E28
0x180050e22  call    cs:__imp_CoTaskMemFree
0x180050e28  cmp     [rsp+2C0h+var_260], r14
0x180050e2d  jz      loc_180050C0D
0x180050e33  lea     rcx, [rsp+2C0h+var_260]
0x180050e38  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x180050e3d  jmp     loc_180050C0D
0x180050e42  mov     rdi, [rsp+2C0h+var_260]
0x180050e47  mov     rax, [rdi]
0x180050e4a  mov     rbx, [rax+28h]
0x180050e4e  xor     edx, edx
0x180050e50  lea     rcx, [rsp+2C0h+pv]
0x180050e55  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180050e5a  lea     r8, [rsp+2C0h+pv]
0x180050e5f  mov     edx, 80058000h
0x180050e64  mov     rcx, rdi
0x180050e67  mov     rax, rbx
0x180050e6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050e6f  mov     ebx, eax
0x180050e71  test    eax, eax
0x180050e73  jns     short loc_180050E7C
0x180050e75  mov     edx, 241h
0x180050e7a  jmp     short loc_180050E02
0x180050e7c  mov     r8, [rsp+2C0h+pv]; lpString
0x180050e81  mov     edx, 299Ah; nIDDlgItem
0x180050e86  mov     rcx, rsi; hDlg
0x180050e89  call    cs:__imp_SetDlgItemTextW
0x180050e8f  test    eax, eax
0x180050e91  jnz     short loc_180050EB2
0x180050e93  mov     rcx, [rbp+1C8h]; this
0x180050e9a  lea     r8, aShellExtZipArc_1; "shell\\ext\\zip\\archive\\createarchive"...
0x180050ea1  mov     edx, 242h; void *
0x180050ea6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180050eab  mov     ebx, eax
0x180050ead  jmp     loc_180050E18
0x180050eb2  mov     rcx, [rsp+2C0h+pv]; pv
0x180050eb7  test    rcx, rcx
0x180050eba  jz      short loc_180050EC2
0x180050ebc  call    cs:__imp_CoTaskMemFree
0x180050ec2  cmp     [rsp+2C0h+var_260], r14
0x180050ec7  jz      short loc_180050ED3
0x180050ec9  lea     rcx, [rsp+2C0h+var_260]
0x180050ece  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x180050ed3  cmp     [rsp+2C0h+var_268], r14
0x180050ed8  jz      short loc_180050EE4
0x180050eda  lea     rcx, [rsp+2C0h+var_268]
0x180050edf  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x180050ee4  mov     ebx, r14d
0x180050ee7  lea     rcx, [rsp+2C0h+var_290]
0x180050eec  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180050ef1  mov     eax, ebx
0x180050ef3  mov     rcx, [rbp+1C0h+var_20]
0x180050efa  xor     rcx, rsp; StackCookie
0x180050efd  call    __security_check_cookie
0x180050f02  lea     r11, [rsp+2C0h+var_10]
0x180050f0a  mov     rbx, [r11+30h]
0x180050f0e  mov     rsi, [r11+38h]
0x180050f12  mov     rsp, r11
0x180050f15  pop     r14
0x180050f17  pop     rdi
0x180050f18  pop     rbp
0x180050f19  retn
```
