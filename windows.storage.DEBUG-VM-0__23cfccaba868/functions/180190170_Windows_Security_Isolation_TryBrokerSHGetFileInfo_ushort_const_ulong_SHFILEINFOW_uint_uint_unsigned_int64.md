# Windows::Security::Isolation::TryBrokerSHGetFileInfo(ushort const *,ulong,_SHFILEINFOW *,uint,uint,unsigned __int64 *)

- ea: `0x180190170`
- end: `0x1801903cf`
- name: `?TryBrokerSHGetFileInfo@Isolation@Security@Windows@@YAJPEBGKPEAU_SHFILEINFOW@@IIPEA_K@Z`
- size: `607`
- prototype: `__int64 __fastcall(Windows::Security::Isolation *__hidden this, const unsigned __int16 *, unsigned int, struct _SHFILEINFOW *, unsigned int, unsigned int, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18018fe50`

## callees

- `0x18000ee84`
- `0x18001c14c`
- `0x1800432f0`
- `0x1800a3080`
- `0x1800d13a0`
- `0x180190170`
- `0x1801903e0`
- `0x180190990`
- `0x180396394`
- `0x180396568`
- `0x1803a4cb0`
- `0x1805c85e0`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019039d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019039d`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1801901e1`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1801903b0`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1801901e1`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1801903b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180190219`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019022d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180190284`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180190298`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801902ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180190303`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180190338`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019034e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180190219`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019022d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180190284`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180190298`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801902ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180190303`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180190338`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019034e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18019024d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1801902b8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180190323`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18019036e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18019024d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1801902b8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180190323`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18019036e`
- `ext-ms-win-ntuser-gui-l1-1-0!DestroyIcon` at `0x180190388`
- `ext-ms-win-ntuser-gui-l1-1-0!DestroyIcon` at `0x180190388`

## string_xrefs

- `0x1801901fa`: `onecoreuap\shell\windows.storage\sharedstoragesources\filesystembrokering.cpp`
- `0x180190265`: `onecoreuap\shell\windows.storage\sharedstoragesources\filesystembrokering.cpp`
- `0x1801902d0`: `onecoreuap\shell\windows.storage\sharedstoragesources\filesystembrokering.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Windows::Security::Isolation::TryBrokerSHGetFileInfo(
        Windows::Security::Isolation *this,
        const unsigned __int16 *a2,
        __int64 a3,
        struct _SHFILEINFOW *a4,
        unsigned int a5,
        unsigned int a6)
{
  unsigned int v7; // r15d
  HRESULT v10; // eax
  Windows::Security::Isolation *v11; // rcx
  unsigned __int16 *v12; // rax
  struct IShellObjectBroker *ShellObjectBroker; // rax
  __int64 v14; // rsi
  HICON v15; // rdi
  int v16; // edi
  HICON v17; // rax
  int v18; // eax
  void *v19; // rdx
  int v20; // eax
  unsigned int v21; // ebx
  int v22; // [rsp+20h] [rbp-D8h]
  __int64 v23; // [rsp+68h] [rbp-90h] BYREF
  _BYTE v24[4]; // [rsp+70h] [rbp-88h] BYREF
  DWORD dwErrCode; // [rsp+74h] [rbp-84h]
  __int64 v26; // [rsp+78h] [rbp-80h]
  __int64 (__fastcall *v27)(__int64, Windows::Security::Isolation *, _QWORD, _QWORD); // [rsp+80h] [rbp-78h]
  int v28; // [rsp+88h] [rbp-70h]
  HICON hIcon; // [rsp+90h] [rbp-68h] BYREF
  unsigned __int16 *v30; // [rsp+98h] [rbp-60h] BYREF
  LPVOID pv; // [rsp+A0h] [rbp-58h] BYREF
  int v32; // [rsp+A8h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  v7 = (unsigned int)a2;
  if ( !Windows::Security::Isolation::IsAppSiloProcess(this) )
    return 2147942450LL;
  if ( CoInitializeEx(0, 2u) < 0 )
  {
    v10 = CoInitializeEx(0, 0);
    v11 = retaddr;
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x9A,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\sharedstoragesources\\filesystembrokering.cpp",
        (const char *)(unsigned int)v10,
        v22);
  }
  ShellObjectBroker = Windows::Security::Isolation::GetShellObjectBroker(v11);
  wil::com_ptr_t<IShellObjectBroker,wil::err_exception_policy>::com_ptr_t<IShellObjectBroker,wil::err_exception_policy>(
    &v23,
    ShellObjectBroker);
  hIcon = 0;
  v32 = *(_DWORD *)(a3 + 8);
  v28 = *(_DWORD *)(a3 + 12);
  v30 = 0;
  pv = 0;
  v14 = v23;
  v27 = *(__int64 (__fastcall **)(__int64, Windows::Security::Isolation *, _QWORD, _QWORD))(*(_QWORD *)v23 + 40LL);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pv);
  v26 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&v30);
  v15 = hIcon;
  if ( hIcon )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v24);
    DestroyIcon(v15);
    if ( !v24[0] )
      SetLastError(dwErrCode);
  }
  hIcon = 0;
  v16 = v27(v14, this, v7, a5);
  if ( v16 < 0 )
  {
    if ( pv )
      CoTaskMemFree(pv);
    if ( v30 )
      CoTaskMemFree(v30);
    goto LABEL_9;
  }
  v17 = hIcon;
  hIcon = 0;
  *(_QWORD *)a3 = v17;
  *(_DWORD *)(a3 + 8) = v32;
  *(_DWORD *)(a3 + 12) = v28;
  v12 = v30;
  if ( !v30 )
    goto LABEL_33;
  v18 = StringCchCopyW((unsigned __int16 *)(a3 + 16), 0x104u, v30);
  v16 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBB,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\sharedstoragesources\\filesystembrokering.cpp",
      (const char *)(unsigned int)v18,
      a6);
    if ( pv )
      CoTaskMemFree(pv);
    if ( v30 )
      CoTaskMemFree(v30);
LABEL_9:
    wil::details::unique_storage<wil::details::resource_policy<HICON__ *,int (*)(HICON__ *),&int DestroyIcon(HICON__ *),wistd::integral_constant<unsigned __int64,0>,HICON__ *,HICON__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HICON__ *,int (*)(HICON__ *),&int DestroyIcon(HICON__ *),wistd::integral_constant<unsigned __int64,0>,HICON__ *,HICON__ *,0,std::nullptr_t>>(&hIcon);
    wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v23);
    CoUninitialize();
    return (unsigned int)v16;
  }
  v12 = v30;
LABEL_33:
  v19 = pv;
  if ( !pv )
  {
LABEL_20:
    if ( v19 )
    {
      CoTaskMemFree(v19);
      v12 = v30;
    }
    if ( v12 )
      CoTaskMemFree(v12);
    wil::details::unique_storage<wil::details::resource_policy<HICON__ *,int (*)(HICON__ *),&int DestroyIcon(HICON__ *),wistd::integral_constant<unsigned __int64,0>,HICON__ *,HICON__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HICON__ *,int (*)(HICON__ *),&int DestroyIcon(HICON__ *),wistd::integral_constant<unsigned __int64,0>,HICON__ *,HICON__ *,0,std::nullptr_t>>(&hIcon);
    wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v23);
    CoUninitialize();
    return 0;
  }
  v20 = StringCchCopyW((unsigned __int16 *)(a3 + 536), 0x50u, (const unsigned __int16 *)pv);
  v21 = v20;
  if ( v20 >= 0 )
  {
    v12 = v30;
    v19 = pv;
    goto LABEL_20;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xC0,
    (unsigned int)"onecoreuap\\shell\\windows.storage\\sharedstoragesources\\filesystembrokering.cpp",
    (const char *)(unsigned int)v20,
    a6);
  if ( pv )
    CoTaskMemFree(pv);
  if ( v30 )
    CoTaskMemFree(v30);
  wil::details::unique_storage<wil::details::resource_policy<HICON__ *,int (*)(HICON__ *),&int DestroyIcon(HICON__ *),wistd::integral_constant<unsigned __int64,0>,HICON__ *,HICON__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HICON__ *,int (*)(HICON__ *),&int DestroyIcon(HICON__ *),wistd::integral_constant<unsigned __int64,0>,HICON__ *,HICON__ *,0,std::nullptr_t>>(&hIcon);
  wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v23);
  CoUninitialize();
  return v21;
}

```

## disassembly

```asm
0x180190170  push    rbx
0x180190172  push    rsi
0x180190173  push    rdi
0x180190174  push    r12
0x180190176  push    r13
0x180190178  push    r14
0x18019017a  push    r15
0x18019017c  sub     rsp, 0C0h
0x180190183  mov     rax, cs:__security_cookie
0x18019018a  xor     rax, rsp
0x18019018d  mov     [rsp+0F8h+var_48], rax
0x180190195  mov     rbx, r8
0x180190198  mov     r15d, edx
0x18019019b  mov     r14, rcx
0x18019019e  mov     r12, qword ptr [rsp+0F8h+arg_28]
0x1801901a6  call    ?IsAppSiloProcess@Isolation@Security@Windows@@YA_NXZ; Windows::Security::Isolation::IsAppSiloProcess(void)
0x1801901ab  xor     edi, edi
0x1801901ad  test    al, al
0x1801901af  jnz     loc_1801903A9
0x1801901b5  mov     eax, 80070032h
0x1801901ba  mov     rcx, [rsp+0F8h+var_48]
0x1801901c2  xor     rcx, rsp; StackCookie
0x1801901c5  call    __security_check_cookie
0x1801901ca  add     rsp, 0C0h
0x1801901d1  pop     r15
0x1801901d3  pop     r14
0x1801901d5  pop     r13
0x1801901d7  pop     r12
0x1801901d9  pop     rdi
0x1801901da  pop     rsi
0x1801901db  pop     rbx
0x1801901dc  retn
0x1801901dd  xor     edx, edx; dwCoInit
0x1801901df  xor     ecx, ecx; pvReserved
0x1801901e1  call    cs:__imp_CoInitializeEx
0x1801901e7  mov     rcx, [rsp+0F8h]; this
0x1801901ef  test    eax, eax
0x1801901f1  jns     loc_18064B49A
0x1801901f7  mov     r9d, eax; char *
0x1801901fa  lea     r8, aOnecoreuapShel_100; "onecoreuap\\shell\\windows.storage\\sha"...
0x180190201  mov     edx, 9Ah; void *
0x180190206  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18019020c  mov     rcx, [rsp+0F8h+pv]; pv
0x180190214  test    rcx, rcx
0x180190217  jz      short loc_180190220
0x180190219  call    cs:__imp_CoTaskMemFree
0x18019021f  nop
0x180190220  mov     rcx, [rsp+0F8h+var_60]; pv
0x180190228  test    rcx, rcx
0x18019022b  jz      short loc_180190234
0x18019022d  call    cs:__imp_CoTaskMemFree
0x180190233  nop
0x180190234  lea     rcx, [rsp+0F8h+hIcon]
0x18019023c  call    ??1?$unique_storage@U?$resource_policy@PEAUHICON__@@P6AHPEAU1@@Z$1?DestroyIcon@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HICON__ *,int (*)(HICON__ *),&DestroyIcon(HICON__ *),wistd::integral_constant<unsigned __int64,0>,HICON__ *,HICON__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HICON__ *,int (*)(HICON__ *),&DestroyIcon(HICON__ *),wistd::integral_constant<unsigned __int64,0>,HICON__ *,HICON__ *,0,std::nullptr_t>>(void)
0x180190241  nop
0x180190242  lea     rcx, [rsp+0F8h+var_90]
0x180190247  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x18019024c  nop
0x18019024d  call    cs:__imp_CoUninitialize
0x180190253  mov     eax, edi
0x180190255  jmp     loc_1801901BA
0x18019025a  mov     rcx, [rsp+0F8h]; this
0x180190262  mov     r9d, edi; char *
0x180190265  lea     r8, aOnecoreuapShel_100; "onecoreuap\\shell\\windows.storage\\sha"...
0x18019026c  mov     edx, 0BBh; void *
0x180190271  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180190276  nop
0x180190277  mov     rcx, [rsp+0F8h+pv]; pv
0x18019027f  test    rcx, rcx
0x180190282  jz      short loc_18019028B
0x180190284  call    cs:__imp_CoTaskMemFree
0x18019028a  nop
0x18019028b  mov     rcx, [rsp+0F8h+var_60]; pv
0x180190293  test    rcx, rcx
0x180190296  jz      short loc_18019029F
0x180190298  call    cs:__imp_CoTaskMemFree
0x18019029e  nop
0x18019029f  lea     rcx, [rsp+0F8h+hIcon]
0x1801902a7  call    ??1?$unique_storage@U?$resource_policy@PEAUHICON__@@P6AHPEAU1@@Z$1?DestroyIcon@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HICON__ *,int (*)(HICON__ *),&DestroyIcon(HICON__ *),wistd::integral_constant<unsigned __int64,0>,HICON__ *,HICON__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HICON__ *,int (*)(HICON__ *),&DestroyIcon(HICON__ *),wistd::integral_constant<unsigned __int64,0>,HICON__ *,HICON__ *,0,std::nullptr_t>>(void)
0x1801902ac  nop
0x1801902ad  lea     rcx, [rsp+0F8h+var_90]
0x1801902b2  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x1801902b7  nop
0x1801902b8  call    cs:__imp_CoUninitialize
0x1801902be  mov     eax, edi
0x1801902c0  jmp     loc_1801901BA
0x1801902c5  mov     rcx, [rsp+0F8h]; this
0x1801902cd  mov     r9d, ebx; char *
0x1801902d0  lea     r8, aOnecoreuapShel_100; "onecoreuap\\shell\\windows.storage\\sha"...
0x1801902d7  mov     edx, 0C0h; void *
0x1801902dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801902e1  nop
0x1801902e2  mov     rcx, [rsp+0F8h+pv]; pv
0x1801902ea  test    rcx, rcx
0x1801902ed  jz      short loc_1801902F6
0x1801902ef  call    cs:__imp_CoTaskMemFree
0x1801902f5  nop
0x1801902f6  mov     rcx, [rsp+0F8h+var_60]; pv
0x1801902fe  test    rcx, rcx
0x180190301  jz      short loc_18019030A
0x180190303  call    cs:__imp_CoTaskMemFree
0x180190309  nop
0x18019030a  lea     rcx, [rsp+0F8h+hIcon]
0x180190312  call    ??1?$unique_storage@U?$resource_policy@PEAUHICON__@@P6AHPEAU1@@Z$1?DestroyIcon@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HICON__ *,int (*)(HICON__ *),&DestroyIcon(HICON__ *),wistd::integral_constant<unsigned __int64,0>,HICON__ *,HICON__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HICON__ *,int (*)(HICON__ *),&DestroyIcon(HICON__ *),wistd::integral_constant<unsigned __int64,0>,HICON__ *,HICON__ *,0,std::nullptr_t>>(void)
0x180190317  nop
0x180190318  lea     rcx, [rsp+0F8h+var_90]
0x18019031d  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x180190322  nop
0x180190323  call    cs:__imp_CoUninitialize
0x180190329  mov     eax, ebx
0x18019032b  jmp     loc_1801901BA
0x180190330  test    rdx, rdx
0x180190333  jz      short loc_180190346
0x180190335  mov     rcx, rdx; pv
0x180190338  call    cs:__imp_CoTaskMemFree
0x18019033e  mov     rax, [rsp+0F8h+var_60]
0x180190346  test    rax, rax
0x180190349  jz      short loc_180190355
0x18019034b  mov     rcx, rax; pv
0x18019034e  call    cs:__imp_CoTaskMemFree
0x180190354  nop
0x180190355  lea     rcx, [rsp+0F8h+hIcon]
0x18019035d  call    ??1?$unique_storage@U?$resource_policy@PEAUHICON__@@P6AHPEAU1@@Z$1?DestroyIcon@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HICON__ *,int (*)(HICON__ *),&DestroyIcon(HICON__ *),wistd::integral_constant<unsigned __int64,0>,HICON__ *,HICON__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HICON__ *,int (*)(HICON__ *),&DestroyIcon(HICON__ *),wistd::integral_constant<unsigned __int64,0>,HICON__ *,HICON__ *,0,std::nullptr_t>>(void)
0x180190362  nop
0x180190363  lea     rcx, [rsp+0F8h+var_90]
0x180190368  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x18019036d  nop
0x18019036e  call    cs:__imp_CoUninitialize
0x180190374  xor     eax, eax
0x180190376  jmp     loc_1801901BA
0x18019037b  lea     rcx, [rsp+0F8h+var_88]; this
0x180190380  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180190385  mov     rcx, rdi; hIcon
0x180190388  call    cs:__imp_DestroyIcon
0x18019038e  cmp     [rsp+0F8h+var_88], 0
0x180190393  jnz     loc_18064B525
0x180190399  mov     ecx, [rsp+0F8h+dwErrCode]; dwErrCode
0x18019039d  call    cs:__imp_SetLastError
0x1801903a3  nop
0x1801903a4  jmp     loc_18064B525
0x1801903a9  mov     edx, 2; dwCoInit
0x1801903ae  xor     ecx, ecx; pvReserved
0x1801903b0  call    cs:__imp_CoInitializeEx
0x1801903b6  test    eax, eax
0x1801903b8  jns     loc_18064B49A
0x1801903be  jmp     loc_1801901DD
0x1801903c3  mov     eax, [rsp+0F8h+var_70]
0x1801903ca  jmp     loc_1801901BA
0x18064b49a  mov     [rsp+0F8h+var_98], 1
0x18064b49f  call    ?GetShellObjectBroker@Isolation@Security@Windows@@YAPEAUIShellObjectBroker@@XZ; Windows::Security::Isolation::GetShellObjectBroker(void)
0x18064b4a4  mov     rdx, rax
0x18064b4a7  lea     rcx, [rsp+0F8h+var_90]
0x18064b4ac  call    ??0?$com_ptr_t@UIShellObjectBroker@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAUIShellObjectBroker@@@Z; wil::com_ptr_t<IShellObjectBroker,wil::err_exception_policy>::com_ptr_t<IShellObjectBroker,wil::err_exception_policy>(IShellObjectBroker *)
0x18064b4b1  nop
0x18064b4b2  mov     [rsp+0F8h+hIcon], rdi
0x18064b4ba  mov     eax, [rbx+8]
0x18064b4bd  mov     [rsp+0F8h+var_50], eax
0x18064b4c4  mov     eax, [rbx+0Ch]
0x18064b4c7  mov     [rsp+0F8h+var_70], eax
0x18064b4ce  mov     [rsp+0F8h+var_60], rdi
0x18064b4d6  mov     [rsp+0F8h+pv], rdi
0x18064b4de  mov     rsi, [rsp+0F8h+var_90]
0x18064b4e3  mov     rax, [rsi]
0x18064b4e6  mov     rax, [rax+28h]
0x18064b4ea  mov     [rsp+0F8h+var_78], rax
0x18064b4f2  lea     rcx, [rsp+0F8h+pv]
0x18064b4fa  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x18064b4ff  mov     r13, rax
0x18064b502  lea     rcx, [rsp+0F8h+var_60]
0x18064b50a  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x18064b50f  mov     [rsp+0F8h+var_80], rax
0x18064b514  mov     rdi, [rsp+0F8h+hIcon]
0x18064b51c  test    rdi, rdi
0x18064b51f  jnz     loc_18019037B
0x18064b525  mov     [rsp+0F8h+hIcon], 0
0x18064b531  mov     [rsp+0F8h+var_B0], r13
0x18064b536  mov     rax, [rsp+0F8h+var_80]
0x18064b53b  mov     [rsp+0F8h+var_B8], rax
0x18064b540  lea     rax, [rsp+0F8h+var_70]
0x18064b548  mov     [rsp+0F8h+var_C0], rax
0x18064b54d  lea     rax, [rsp+0F8h+var_50]
0x18064b555  mov     [rsp+0F8h+var_C8], rax
0x18064b55a  lea     rax, [rsp+0F8h+hIcon]
0x18064b562  mov     [rsp+0F8h+var_D0], rax
0x18064b567  mov     qword ptr [rsp+0F8h+var_D8], r12; int
0x18064b56c  mov     r9d, [rsp+0F8h+arg_20]
0x18064b574  mov     r8d, r15d
0x18064b577  mov     rdx, r14
0x18064b57a  mov     rcx, rsi
0x18064b57d  mov     rax, [rsp+0F8h+var_78]
0x18064b585  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18064b58a  mov     edi, eax
0x18064b58c  test    eax, eax
0x18064b58e  js      loc_18019020C
0x18064b594  mov     rax, [rsp+0F8h+hIcon]
0x18064b59c  mov     [rsp+0F8h+hIcon], 0
0x18064b5a8  mov     [rbx], rax
0x18064b5ab  mov     eax, [rsp+0F8h+var_50]
0x18064b5b2  mov     [rbx+8], eax
0x18064b5b5  mov     eax, [rsp+0F8h+var_70]
0x18064b5bc  mov     [rbx+0Ch], eax
0x18064b5bf  mov     rax, [rsp+0F8h+var_60]
0x18064b5c7  test    rax, rax
0x18064b5ca  jz      short loc_18064B5EF
0x18064b5cc  lea     rcx, [rbx+10h]; unsigned __int16 *
0x18064b5d0  mov     r8, rax; unsigned __int16 *
0x18064b5d3  mov     edx, 104h; unsigned __int64
0x18064b5d8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18064b5dd  mov     edi, eax
0x18064b5df  test    eax, eax
0x18064b5e1  js      loc_18019025A
0x18064b5e7  mov     rax, [rsp+0F8h+var_60]
0x18064b5ef  mov     rdx, [rsp+0F8h+pv]
0x18064b5f7  test    rdx, rdx
0x18064b5fa  jz      loc_180190330
0x18064b600  lea     rcx, [rbx+218h]; unsigned __int16 *
0x18064b607  mov     r8, rdx; unsigned __int16 *
0x18064b60a  mov     edx, 50h ; 'P'; unsigned __int64
0x18064b60f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18064b614  mov     ebx, eax
0x18064b616  test    eax, eax
0x18064b618  js      loc_1801902C5
0x18064b61e  mov     rax, [rsp+0F8h+var_60]
0x18064b626  mov     rdx, [rsp+0F8h+pv]
0x18064b62e  jmp     loc_180190330
```
