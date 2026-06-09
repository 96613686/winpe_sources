# ArchiveExtractWizard::Browse(HWND__ *)

- ea: `0x180064800`
- end: `0x180064a53`
- name: `?Browse@ArchiveExtractWizard@@CAJPEAUHWND__@@@Z`
- size: `595`
- prototype: `__int64 __fastcall(HWND hDlg)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180028d64`

## callees

- `0x180024a24`
- `0x180030a3c`
- `0x180031e94`
- `0x180033aa8`
- `0x180035728`
- `0x180036f50`
- `0x180041470`
- `0x180064800`
- `0x180071010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180064970`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180064a00`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180064970`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180064a00`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006488f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006488f`
- `USER32!SetDlgItemTextW` at `0x1800649d1`
- `USER32!SetDlgItemTextW` at `0x1800649d1`

## pseudocode

```c
__int64 __fastcall ArchiveExtractWizard::Browse(HWND hDlg)
{
  int v2; // eax
  int LastError; // ebx
  HRESULT v4; // eax
  __int64 v5; // rdx
  int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, __int64, LPVOID *); // rbx
  const char *v10; // r9
  LPVOID v12[3]; // [rsp+30h] [rbp-40h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-28h] BYREF
  __int64 v14; // [rsp+50h] [rbp-20h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  memset(v12, 0, sizeof(v12));
  v2 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(
         v12,
         &_ImageBase,
         10520);
  LastError = v2;
  if ( v2 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6D3,
      (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
      (const char *)(unsigned int)v2);
    goto LABEL_31;
  }
  ppv = 0;
  v4 = CoCreateInstance(&CLSID_FileOpenDialog, 0, 3u, &GUID_42f85136_db7e_439c_85f1_e4075d135fc8, &ppv);
  LastError = v4;
  if ( v4 < 0 )
  {
    v5 = 1750;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
      (const char *)(unsigned int)v4);
    goto LABEL_6;
  }
  v4 = (*(__int64 (__fastcall **)(LPVOID, LPVOID))(*(_QWORD *)ppv + 136LL))(ppv, v12[0]);
  LastError = v4;
  if ( v4 < 0 )
  {
    v5 = 1751;
    goto LABEL_5;
  }
  v4 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 72LL))(ppv, 2144);
  LastError = v4;
  if ( v4 < 0 )
  {
    v5 = 1752;
    goto LABEL_5;
  }
  LastError = (*(__int64 (__fastcall **)(LPVOID, HWND))(*(_QWORD *)ppv + 24LL))(ppv, hDlg);
  if ( LastError < 0 )
  {
LABEL_6:
    if ( ppv )
      winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&ppv);
    goto LABEL_31;
  }
  v14 = 0;
  pv = 0;
  v6 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 160LL))(ppv, &v14);
  LastError = v6;
  if ( v6 < 0 )
  {
    v7 = 1757;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
      (const char *)(unsigned int)v6);
LABEL_16:
    if ( pv )
      CoTaskMemFree(pv);
    if ( v14 )
      winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v14);
    goto LABEL_6;
  }
  v8 = v14;
  v9 = *(__int64 (__fastcall **)(__int64, __int64, LPVOID *))(*(_QWORD *)v14 + 40LL);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &pv,
    0);
  v6 = v9(v8, 2147844096LL, &pv);
  LastError = v6;
  if ( v6 < 0 )
  {
    v7 = 1758;
    goto LABEL_15;
  }
  if ( !SetDlgItemTextW(hDlg, 1045, (LPCWSTR)pv) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x6DF,
                  (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
                  v10);
    goto LABEL_16;
  }
  if ( pv )
    CoTaskMemFree(pv);
  if ( v14 )
    winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v14);
  if ( ppv )
    winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&ppv);
  LastError = 0;
LABEL_31:
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v12);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180064800  mov     [rsp-18h+arg_8], rbx
0x180064805  mov     [rsp-18h+arg_10], rsi
0x18006480a  push    rbp
0x18006480b  push    rdi
0x18006480c  push    r14
0x18006480e  mov     rbp, rsp
0x180064811  sub     rsp, 70h
0x180064815  mov     rax, cs:__security_cookie
0x18006481c  xor     rax, rsp
0x18006481f  mov     [rbp+var_10], rax
0x180064823  mov     rsi, rcx
0x180064826  xor     r14d, r14d
0x180064829  mov     [rbp+var_40], r14
0x18006482d  mov     [rbp+var_38], r14
0x180064831  mov     [rbp+var_30], r14
0x180064835  mov     r8d, 2918h
0x18006483b  lea     rdx, __ImageBase
0x180064842  lea     rcx, [rbp+var_40]
0x180064846  call    ?Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@IG@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Initialize(HINSTANCE__ *,uint,ushort)
0x18006484b  mov     ebx, eax
0x18006484d  test    eax, eax
0x18006484f  jns     short loc_18006486E
0x180064851  mov     rcx, [rbp+18h]
0x180064855  mov     r9d, eax
0x180064858  lea     r8, aShellExtZipArc_8; "shell\\ext\\zip\\archive\\archiveextrac"...
0x18006485f  mov     edx, 6D3h
0x180064864  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180064869  jmp     loc_180064A27
0x18006486e  mov     [rbp+var_28], r14
0x180064872  lea     rax, [rbp+var_28]
0x180064876  mov     [rsp+70h+ppv], rax; ppv
0x18006487b  lea     r9, _GUID_42f85136_db7e_439c_85f1_e4075d135fc8; riid
0x180064882  xor     edx, edx; pUnkOuter
0x180064884  lea     r8d, [rdx+3]; dwClsContext
0x180064888  lea     rcx, CLSID_FileOpenDialog; rclsid
0x18006488f  call    cs:__imp_CoCreateInstance
0x180064895  mov     ebx, eax
0x180064897  test    eax, eax
0x180064899  jns     short loc_1800648CB
0x18006489b  mov     edx, 6D6h
0x1800648a0  mov     rcx, [rbp+18h]
0x1800648a4  mov     r9d, eax
0x1800648a7  lea     r8, aShellExtZipArc_8; "shell\\ext\\zip\\archive\\archiveextrac"...
0x1800648ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800648b3  cmp     [rbp+var_28], r14
0x1800648b7  jz      loc_180064A27
0x1800648bd  lea     rcx, [rbp+var_28]
0x1800648c1  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x1800648c6  jmp     loc_180064A27
0x1800648cb  mov     rcx, [rbp+var_28]
0x1800648cf  mov     rax, [rcx]
0x1800648d2  mov     rdx, [rbp+var_40]
0x1800648d6  mov     rax, [rax+88h]
0x1800648dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800648e2  mov     ebx, eax
0x1800648e4  test    eax, eax
0x1800648e6  jns     short loc_1800648EF
0x1800648e8  mov     edx, 6D7h
0x1800648ed  jmp     short loc_1800648A0
0x1800648ef  mov     rcx, [rbp+var_28]
0x1800648f3  mov     rax, [rcx]
0x1800648f6  mov     edx, 860h
0x1800648fb  mov     rax, [rax+48h]
0x1800648ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064904  mov     ebx, eax
0x180064906  test    eax, eax
0x180064908  jns     short loc_180064911
0x18006490a  mov     edx, 6D8h
0x18006490f  jmp     short loc_1800648A0
0x180064911  mov     rcx, [rbp+var_28]
0x180064915  mov     rax, [rcx]
0x180064918  mov     rdx, rsi
0x18006491b  mov     rax, [rax+18h]
0x18006491f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064924  mov     ebx, eax
0x180064926  test    eax, eax
0x180064928  js      short loc_1800648B3
0x18006492a  mov     [rbp+var_20], r14
0x18006492e  mov     [rbp+pv], r14
0x180064932  mov     rcx, [rbp+var_28]
0x180064936  mov     rax, [rcx]
0x180064939  lea     rdx, [rbp+var_20]
0x18006493d  mov     rax, [rax+0A0h]
0x180064944  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064949  mov     ebx, eax
0x18006494b  test    eax, eax
0x18006494d  jns     short loc_18006498E
0x18006494f  mov     edx, 6DDh
0x180064954  mov     r9d, eax
0x180064957  lea     r8, aShellExtZipArc_8; "shell\\ext\\zip\\archive\\archiveextrac"...
0x18006495e  mov     rcx, [rbp+18h]
0x180064962  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180064967  mov     rcx, [rbp+pv]; pv
0x18006496b  test    rcx, rcx
0x18006496e  jz      short loc_180064976
0x180064970  call    cs:__imp_CoTaskMemFree
0x180064976  cmp     [rbp+var_20], r14
0x18006497a  jz      loc_1800648B3
0x180064980  lea     rcx, [rbp+var_20]
0x180064984  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x180064989  jmp     loc_1800648B3
0x18006498e  mov     rdi, [rbp+var_20]
0x180064992  mov     rax, [rdi]
0x180064995  mov     rbx, [rax+28h]
0x180064999  xor     edx, edx
0x18006499b  lea     rcx, [rbp+pv]
0x18006499f  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800649a4  lea     r8, [rbp+pv]
0x1800649a8  mov     edx, 80058000h
0x1800649ad  mov     rcx, rdi
0x1800649b0  mov     rax, rbx
0x1800649b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800649b8  mov     ebx, eax
0x1800649ba  test    eax, eax
0x1800649bc  jns     short loc_1800649C5
0x1800649be  mov     edx, 6DEh
0x1800649c3  jmp     short loc_180064954
0x1800649c5  mov     r8, [rbp+pv]; lpString
0x1800649c9  mov     edx, 415h; nIDDlgItem
0x1800649ce  mov     rcx, rsi; hDlg
0x1800649d1  call    cs:__imp_SetDlgItemTextW
0x1800649d7  test    eax, eax
0x1800649d9  jnz     short loc_1800649F7
0x1800649db  mov     rcx, [rbp+18h]; this
0x1800649df  lea     r8, aShellExtZipArc_8; "shell\\ext\\zip\\archive\\archiveextrac"...
0x1800649e6  mov     edx, 6DFh; void *
0x1800649eb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800649f0  mov     ebx, eax
0x1800649f2  jmp     loc_180064967
0x1800649f7  mov     rcx, [rbp+pv]; pv
0x1800649fb  test    rcx, rcx
0x1800649fe  jz      short loc_180064A06
0x180064a00  call    cs:__imp_CoTaskMemFree
0x180064a06  cmp     [rbp+var_20], r14
0x180064a0a  jz      short loc_180064A15
0x180064a0c  lea     rcx, [rbp+var_20]
0x180064a10  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x180064a15  cmp     [rbp+var_28], r14
0x180064a19  jz      short loc_180064A24
0x180064a1b  lea     rcx, [rbp+var_28]
0x180064a1f  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x180064a24  mov     ebx, r14d
0x180064a27  lea     rcx, [rbp+var_40]
0x180064a2b  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180064a30  mov     eax, ebx
0x180064a32  mov     rcx, [rbp+var_10]
0x180064a36  xor     rcx, rsp; StackCookie
0x180064a39  call    __security_check_cookie
0x180064a3e  lea     r11, [rsp+70h+var_s0]
0x180064a43  mov     rbx, [r11+28h]
0x180064a47  mov     rsi, [r11+30h]
0x180064a4b  mov     rsp, r11
0x180064a4e  pop     r14
0x180064a50  pop     rdi
0x180064a51  pop     rbp
0x180064a52  retn
```
