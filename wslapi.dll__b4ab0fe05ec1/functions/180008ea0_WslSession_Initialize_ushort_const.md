# WslSession::_Initialize(ushort const *)

- ea: `0x180008ea0`
- end: `0x180009051`
- name: `?_Initialize@WslSession@@AEAAJPEBG@Z`
- size: `433`
- prototype: `__int64 __fastcall(WslSession *this, char *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180009190`

## callees

- `0x180004fd4`
- `0x18000698c`
- `0x180006ba4`
- `0x180008454`
- `0x180008678`
- `0x180008944`
- `0x180008a24`
- `0x180008ea0`
- `0x18000a054`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180008f6d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180008f6d`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x180008efa`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x180008efa`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180008fcd`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000902d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180009038`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180008fcd`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000902d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180009038`

## pseudocode

```c
__int64 __fastcall WslSession::_Initialize(WslSession *this, char *a2)
{
  char *v4; // rdi
  HRESULT v5; // eax
  const char *v6; // r9
  __int64 v8; // rcx
  HRESULT Instance; // eax
  wsl::util *v10; // rcx
  const char *v11; // r9
  unsigned int v12; // ebx
  int v13; // eax
  __int64 v14; // rdx
  char v16; // al
  int dwAuthnLevel; // [rsp+20h] [rbp-58h]
  char v18; // [rsp+50h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  char v20; // [rsp+80h] [rbp+8h] BYREF
  void *v21; // [rsp+90h] [rbp+18h] BYREF

  v4 = (char *)this + 8;
  *((_BYTE *)this + 8) = 0;
  wil::CoInitializeEx_failfast(&v20);
  v5 = CoInitializeSecurity(0, -1, 0, 0, 0, 3u, 0, 0x20u, 0);
  if ( (int)(v5 + 0x80000000) >= 0 && v5 != -2147417831 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x4F,
      (unsigned int)"onecore\\vm\\wsl\\lxss\\wslapi\\wslsession.cpp",
      v6);
  v8 = *((_QWORD *)this + 2);
  *((_QWORD *)this + 2) = 0;
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  Instance = CoCreateInstance(&rclsid, 0, 4u, &GUID_46f3c96d_ffa3_42f0_b052_52f5e7ecbb08, (LPVOID *)this + 2);
  v12 = Instance;
  if ( Instance == -2147221164 )
  {
    v13 = wsl::util::TryLaunchLiftedWslInstall(v10);
    if ( v13 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x54,
        (unsigned int)"onecore\\vm\\wsl\\lxss\\wslapi\\wslsession.cpp",
        (const char *)(unsigned int)v13,
        dwAuthnLevel);
    v12 = -2147024482;
    goto LABEL_14;
  }
  if ( Instance < 0 )
  {
LABEL_14:
    v14 = 88;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\vm\\wsl\\lxss\\wslapi\\wslsession.cpp",
      (const char *)v12,
      dwAuthnLevel);
    if ( v20 )
      CoUninitialize();
    return v12;
  }
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &v21,
    a2,
    0xFFFFFFFFFFFFFFFFuLL,
    v11);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
    this,
    &v21);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v21);
  if ( !*(_QWORD *)this )
  {
    v12 = -2147024882;
    v14 = 91;
    goto LABEL_15;
  }
  if ( v4 == &v18 )
  {
    CoUninitialize();
  }
  else
  {
    v16 = *v4;
    *v4 = 0;
    if ( v16 )
      CoUninitialize();
    *v4 = 1;
  }
  return 0;
}

```

## disassembly

```asm
0x180008ea0  mov     rax, rsp
0x180008ea3  mov     [rax+10h], rbx
0x180008ea7  push    rbp
0x180008ea8  push    rsi
0x180008ea9  push    rdi
0x180008eaa  sub     rsp, 60h
0x180008eae  mov     rbp, rdx
0x180008eb1  mov     rsi, rcx
0x180008eb4  lea     rdi, [rcx+8]
0x180008eb8  mov     byte ptr [rdi], 0
0x180008ebb  lea     rcx, [rax+8]
0x180008ebf  call    ?CoInitializeEx_failfast@wil@@YA?AV?$unique_call@P6AXXZ$1?CoUninitialize@@YAXXZ$00@1@K@Z; wil::CoInitializeEx_failfast(ulong)
0x180008ec4  nop
0x180008ec5  mov     [rsp+78h+pReserved3], 0; pReserved3
0x180008ece  mov     [rsp+78h+dwCapabilities], 20h ; ' '; dwCapabilities
0x180008ed6  mov     [rsp+78h+pAuthList], 0; pAuthList
0x180008edf  mov     [rsp+78h+dwImpLevel], 3; dwImpLevel
0x180008ee7  mov     [rsp+78h+dwAuthnLevel], 0; dwAuthnLevel
0x180008eef  xor     r9d, r9d; pReserved1
0x180008ef2  xor     r8d, r8d; asAuthSvc
0x180008ef5  or      edx, 0FFFFFFFFh; cAuthSvc
0x180008ef8  xor     ecx, ecx; pSecDesc
0x180008efa  call    cs:__imp_CoInitializeSecurity
0x180008f00  mov     edx, 80000000h
0x180008f05  lea     ecx, [rax+rdx]
0x180008f08  test    edx, ecx
0x180008f0a  jnz     short loc_180008F17
0x180008f0c  cmp     eax, 80010119h
0x180008f11  jz      short loc_180008F17
0x180008f13  mov     al, 1
0x180008f15  jmp     short loc_180008F19
0x180008f17  xor     al, al
0x180008f19  mov     rcx, [rsp+78h]; this
0x180008f1e  test    al, al
0x180008f20  jz      short loc_180008F34
0x180008f22  lea     r8, aOnecoreVmWslLx_3; "onecore\\vm\\wsl\\lxss\\wslapi\\wslsess"...
0x180008f29  mov     edx, 4Fh ; 'O'; void *
0x180008f2e  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180008f34  lea     rbx, [rsi+10h]
0x180008f38  mov     rcx, [rbx]
0x180008f3b  mov     qword ptr [rbx], 0
0x180008f42  test    rcx, rcx
0x180008f45  jz      short loc_180008F54
0x180008f47  mov     rax, [rcx]
0x180008f4a  mov     rax, [rax+10h]
0x180008f4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f53  nop
0x180008f54  mov     qword ptr [rsp+78h+dwAuthnLevel], rbx; int
0x180008f59  lea     r9, _GUID_46f3c96d_ffa3_42f0_b052_52f5e7ecbb08; riid
0x180008f60  xor     edx, edx; pUnkOuter
0x180008f62  lea     r8d, [rdx+4]; dwClsContext
0x180008f66  lea     rcx, rclsid; rclsid
0x180008f6d  call    cs:__imp_CoCreateInstance
0x180008f73  mov     ebx, eax
0x180008f75  cmp     eax, 80040154h
0x180008f7a  jnz     short loc_180008FA5
0x180008f7c  call    ?TryLaunchLiftedWslInstall@util@wsl@@YAJXZ; wsl::util::TryLaunchLiftedWslInstall(void)
0x180008f81  mov     rcx, [rsp+78h]; this
0x180008f86  test    eax, eax
0x180008f88  jns     short loc_180008F9E
0x180008f8a  mov     r9d, eax; char *
0x180008f8d  lea     r8, aOnecoreVmWslLx_3; "onecore\\vm\\wsl\\lxss\\wslapi\\wslsess"...
0x180008f94  mov     edx, 54h ; 'T'; void *
0x180008f99  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180008f9e  mov     ebx, 8007019Eh
0x180008fa3  jmp     short loc_180008FA9
0x180008fa5  test    eax, eax
0x180008fa7  jns     short loc_180008FD7
0x180008fa9  mov     edx, 58h ; 'X'; void *
0x180008fae  lea     r8, aOnecoreVmWslLx_3; "onecore\\vm\\wsl\\lxss\\wslapi\\wslsess"...
0x180008fb5  mov     r9d, ebx; char *
0x180008fb8  mov     rcx, [rsp+78h]; this
0x180008fbd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008fc2  nop
0x180008fc3  cmp     [rsp+78h+arg_0], 0
0x180008fcb  jz      short loc_180008FD3
0x180008fcd  call    cs:__imp_CoUninitialize
0x180008fd3  mov     eax, ebx
0x180008fd5  jmp     short loc_180009041
0x180008fd7  or      r8, 0FFFFFFFFFFFFFFFFh
0x180008fdb  mov     rdx, rbp
0x180008fde  lea     rcx, [rsp+78h+arg_10]
0x180008fe6  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180008feb  lea     rdx, [rsp+78h+arg_10]
0x180008ff3  mov     rcx, rsi
0x180008ff6  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180008ffb  lea     rcx, [rsp+78h+arg_10]
0x180009003  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180009008  cmp     qword ptr [rsi], 0
0x18000900c  jnz     short loc_18000901A
0x18000900e  mov     ebx, 8007000Eh
0x180009013  mov     edx, 5Bh ; '['
0x180009018  jmp     short loc_180008FAE
0x18000901a  lea     rax, [rsp+78h+var_28]
0x18000901f  cmp     rdi, rax
0x180009022  jz      short loc_180009038
0x180009024  mov     al, [rdi]
0x180009026  mov     byte ptr [rdi], 0
0x180009029  test    al, al
0x18000902b  jz      short loc_180009033
0x18000902d  call    cs:__imp_CoUninitialize
0x180009033  mov     byte ptr [rdi], 1
0x180009036  jmp     short loc_18000903F
0x180009038  call    cs:__imp_CoUninitialize
0x18000903e  nop
0x18000903f  xor     eax, eax
0x180009041  mov     rbx, [rsp+78h+arg_8]
0x180009049  add     rsp, 60h
0x18000904d  pop     rdi
0x18000904e  pop     rsi
0x18000904f  pop     rbp
0x180009050  retn
```
