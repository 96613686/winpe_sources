# ServerXMLUpdateHandler::NetworkName2Id(_bstr_t const &,_GUID &)

- ea: `0x18007d85c`
- end: `0x18007dcfb`
- name: `?NetworkName2Id@ServerXMLUpdateHandler@@AEAAJAEBV_bstr_t@@AEAU_GUID@@@Z`
- size: `1183`
- prototype: `__int64 __fastcall(ServerXMLUpdateHandler *this, const struct _bstr_t *, struct _GUID *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18004ab10`

## callees

- `0x18000dc30`
- `0x180019130`
- `0x1800339c0`
- `0x180054084`
- `0x18007d85c`
- `0x180084010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18007da67`
- `msvcrt!_wcsicmp` at `0x18007da67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007da34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007da34`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007d906`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007d906`

## pseudocode

```c
__int64 __fastcall ServerXMLUpdateHandler::NetworkName2Id(
        ServerXMLUpdateHandler *this,
        const struct _bstr_t *a2,
        struct _GUID *a3)
{
  HRESULT v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rcx
  int v9; // eax
  const wchar_t *v10; // rdx
  const wchar_t *v11; // rcx
  int v12; // eax
  __int64 v13; // [rsp+30h] [rbp-20h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-18h] BYREF
  const wchar_t **v15; // [rsp+40h] [rbp-10h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-8h] BYREF
  ServerXMLUpdateHandler *v17; // [rsp+70h] [rbp+20h] BYREF
  __int64 v18; // [rsp+88h] [rbp+38h] BYREF

  v17 = this;
  ppv = 0;
  v18 = 0;
  v13 = 0;
  if ( !_bstr_t::length(a2) )
  {
    v13 = 0;
    if ( v18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    v18 = 0;
    return 2147750680LL;
  }
  v6 = CoCreateInstance(&CLSID_CNetworkListManager, 0, 4u, &IID_INetworkListManagerPrivate, &ppv);
  v7 = v6;
  if ( v6 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        WPP_6a02f12a6b2c3ac58024ebcfa94f3c9a_Traceguids,
        (unsigned int)v6);
    }
    v13 = 0;
    if ( v18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    v18 = 0;
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return v7;
  }
  v7 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)ppv + 32LL))(ppv, 3, &v13);
  v8 = v13;
  if ( (v7 & 0x80000000) != 0 || !v13 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_6a02f12a6b2c3ac58024ebcfa94f3c9a_Traceguids, v7);
      v8 = v13;
    }
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    v13 = 0;
    if ( v18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    v18 = 0;
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return v7;
  }
  LODWORD(v17) = 0;
  pv = 0;
  v15 = 0;
  while ( 1 )
  {
    v9 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, ServerXMLUpdateHandler **))(*(_QWORD *)v8 + 24LL))(
           v8,
           1,
           &v18,
           &v17);
    v7 = v9;
    if ( v9 < 0 )
      goto LABEL_60;
    if ( v9 == 1 || !(_DWORD)v17 )
      break;
    v7 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v18 + 24LL))(v18, &pv);
    _bstr_t::operator=(&v15, pv);
    CoTaskMemFree(pv);
    pv = 0;
    if ( (v7 & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_6a02f12a6b2c3ac58024ebcfa94f3c9a_Traceguids, v7);
      }
      _bstr_t::~_bstr_t((_bstr_t *)&v15);
      if ( v13 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      v13 = 0;
      if ( v18 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      v18 = 0;
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      return v7;
    }
    if ( v15 )
      v10 = *v15;
    else
      v10 = 0;
    if ( *(_QWORD *)a2 )
      v11 = **(const wchar_t ***)a2;
    else
      v11 = 0;
    if ( !_wcsicmp(v11, v10) )
    {
      v12 = (*(__int64 (__fastcall **)(__int64, struct _GUID *))(*(_QWORD *)v18 + 48LL))(v18, a3);
      v7 = v12;
      if ( v12 < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((char *)WPP_GLOBAL_Control + 28) < 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            19,
            WPP_6a02f12a6b2c3ac58024ebcfa94f3c9a_Traceguids,
            (unsigned int)v12);
        }
        _bstr_t::~_bstr_t((_bstr_t *)&v15);
        if ( v13 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
        v13 = 0;
        if ( v18 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
        v18 = 0;
        if ( ppv )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
        return v7;
      }
LABEL_60:
      _bstr_t::~_bstr_t((_bstr_t *)&v15);
      if ( v13 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      v13 = 0;
      if ( v18 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      v18 = 0;
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      return v7;
    }
    v8 = v13;
  }
  _bstr_t::~_bstr_t((_bstr_t *)&v15);
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  v13 = 0;
  if ( v18 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  v18 = 0;
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return 1;
}

```

## disassembly

```asm
0x18007d85c  mov     [rsp-18h+arg_8], rbx
0x18007d861  mov     [rsp-18h+arg_10], rsi
0x18007d866  mov     [rsp-18h+arg_0], rcx
0x18007d86b  push    rbp
0x18007d86c  push    rdi
0x18007d86d  push    r14
0x18007d86f  mov     rbp, rsp
0x18007d872  sub     rsp, 50h
0x18007d876  mov     rsi, r8
0x18007d879  mov     rdi, rdx
0x18007d87c  xor     r14d, r14d
0x18007d87f  mov     [rbp+var_18], r14
0x18007d883  mov     [rbp+arg_18], r14
0x18007d887  mov     [rbp+var_20], r14
0x18007d88b  mov     rcx, rdx; this
0x18007d88e  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x18007d893  test    eax, eax
0x18007d895  jnz     short loc_18007D8E9
0x18007d897  mov     rcx, [rbp+var_20]
0x18007d89b  test    rcx, rcx
0x18007d89e  jz      short loc_18007D8AC
0x18007d8a0  mov     rax, [rcx]
0x18007d8a3  mov     rax, [rax+10h]
0x18007d8a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d8ac  mov     [rbp+var_20], r14
0x18007d8b0  mov     rcx, [rbp+arg_18]
0x18007d8b4  test    rcx, rcx
0x18007d8b7  jz      short loc_18007D8C5
0x18007d8b9  mov     rax, [rcx]
0x18007d8bc  mov     rax, [rax+10h]
0x18007d8c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d8c5  mov     [rbp+arg_18], r14
0x18007d8c9  mov     rcx, [rbp+var_18]
0x18007d8cd  test    rcx, rcx
0x18007d8d0  jz      short loc_18007D8DF
0x18007d8d2  mov     rax, [rcx]
0x18007d8d5  mov     rax, [rax+10h]
0x18007d8d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d8de  nop
0x18007d8df  mov     eax, 80041318h
0x18007d8e4  jmp     loc_18007DCE6
0x18007d8e9  lea     rax, [rbp+var_18]
0x18007d8ed  mov     [rsp+50h+ppv], rax; ppv
0x18007d8f2  lea     r9, IID_INetworkListManagerPrivate; riid
0x18007d8f9  xor     edx, edx; pUnkOuter
0x18007d8fb  lea     r8d, [rdx+4]; dwClsContext
0x18007d8ff  lea     rcx, CLSID_CNetworkListManager; rclsid
0x18007d906  call    cs:__imp_CoCreateInstance
0x18007d90c  mov     ebx, eax
0x18007d90e  test    eax, eax
0x18007d910  jns     loc_18007D99B
0x18007d916  lea     rdx, WPP_GLOBAL_Control
0x18007d91d  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d924  cmp     rcx, rdx
0x18007d927  jz      short loc_18007D94E
0x18007d929  test    byte ptr [rcx+1Ch], 80h
0x18007d92d  jz      short loc_18007D94E
0x18007d92f  cmp     byte ptr [rcx+19h], 2
0x18007d933  jb      short loc_18007D94E
0x18007d935  mov     edx, 10h
0x18007d93a  mov     r9d, eax
0x18007d93d  lea     r8, WPP_6a02f12a6b2c3ac58024ebcfa94f3c9a_Traceguids
0x18007d944  mov     rcx, [rcx+10h]
0x18007d948  call    WPP_SF_d
0x18007d94d  nop
0x18007d94e  mov     rcx, [rbp+var_20]
0x18007d952  test    rcx, rcx
0x18007d955  jz      short loc_18007D963
0x18007d957  mov     rax, [rcx]
0x18007d95a  mov     rax, [rax+10h]
0x18007d95e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d963  mov     [rbp+var_20], r14
0x18007d967  mov     rcx, [rbp+arg_18]
0x18007d96b  test    rcx, rcx
0x18007d96e  jz      short loc_18007D97C
0x18007d970  mov     rax, [rcx]
0x18007d973  mov     rax, [rax+10h]
0x18007d977  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d97c  mov     [rbp+arg_18], r14
0x18007d980  mov     rcx, [rbp+var_18]
0x18007d984  test    rcx, rcx
0x18007d987  jz      short loc_18007D996
0x18007d989  mov     rax, [rcx]
0x18007d98c  mov     rax, [rax+10h]
0x18007d990  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d995  nop
0x18007d996  jmp     loc_18007DCE4
0x18007d99b  mov     rcx, [rbp+var_18]
0x18007d99f  mov     rax, [rcx]
0x18007d9a2  lea     r8, [rbp+var_20]
0x18007d9a6  mov     edx, 3
0x18007d9ab  mov     rax, [rax+20h]
0x18007d9af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d9b4  mov     ebx, eax
0x18007d9b6  mov     rcx, [rbp+var_20]
0x18007d9ba  test    eax, eax
0x18007d9bc  js      loc_18007DC65
0x18007d9c2  test    rcx, rcx
0x18007d9c5  jz      loc_18007DC65
0x18007d9cb  mov     dword ptr [rbp+arg_0], r14d
0x18007d9cf  mov     [rbp+pv], r14
0x18007d9d3  mov     [rbp+var_10], r14
0x18007d9d7  mov     rax, [rcx]
0x18007d9da  lea     r9, [rbp+arg_0]
0x18007d9de  lea     r8, [rbp+arg_18]
0x18007d9e2  mov     edx, 1
0x18007d9e7  mov     rax, [rax+18h]
0x18007d9eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d9f0  mov     ebx, eax
0x18007d9f2  test    eax, eax
0x18007d9f4  js      loc_18007DC11
0x18007d9fa  cmp     eax, 1
0x18007d9fd  jz      loc_18007DBB5
0x18007da03  cmp     dword ptr [rbp+arg_0], r14d
0x18007da07  jz      loc_18007DBB5
0x18007da0d  mov     rcx, [rbp+arg_18]
0x18007da11  mov     rax, [rcx]
0x18007da14  lea     rdx, [rbp+pv]
0x18007da18  mov     rax, [rax+18h]
0x18007da1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007da21  mov     ebx, eax
0x18007da23  mov     rdx, [rbp+pv]
0x18007da27  lea     rcx, [rbp+var_10]
0x18007da2b  call    ??4_bstr_t@@QEAAAEAV0@PEBG@Z; _bstr_t::operator=(ushort const *)
0x18007da30  mov     rcx, [rbp+pv]; pv
0x18007da34  call    cs:__imp_CoTaskMemFree
0x18007da3a  mov     [rbp+pv], r14
0x18007da3e  test    ebx, ebx
0x18007da40  js      loc_18007DB26
0x18007da46  mov     rax, [rbp+var_10]
0x18007da4a  test    rax, rax
0x18007da4d  jz      short loc_18007DA54
0x18007da4f  mov     rdx, [rax]
0x18007da52  jmp     short loc_18007DA57
0x18007da54  mov     rdx, r14; String2
0x18007da57  mov     rax, [rdi]
0x18007da5a  test    rax, rax
0x18007da5d  jz      short loc_18007DA64
0x18007da5f  mov     rcx, [rax]
0x18007da62  jmp     short loc_18007DA67
0x18007da64  mov     rcx, r14; String1
0x18007da67  call    cs:__imp__wcsicmp
0x18007da6d  test    eax, eax
0x18007da6f  jz      short loc_18007DA7A
0x18007da71  mov     rcx, [rbp+var_20]
0x18007da75  jmp     loc_18007D9D7
0x18007da7a  mov     rcx, [rbp+arg_18]
0x18007da7e  mov     rax, [rcx]
0x18007da81  mov     rdx, rsi
0x18007da84  mov     rax, [rax+30h]
0x18007da88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007da8d  mov     ebx, eax
0x18007da8f  test    eax, eax
0x18007da91  jns     loc_18007DC11
0x18007da97  lea     rdx, WPP_GLOBAL_Control
0x18007da9e  mov     rcx, cs:WPP_GLOBAL_Control
0x18007daa5  cmp     rcx, rdx
0x18007daa8  jz      short loc_18007DACF
0x18007daaa  test    byte ptr [rcx+1Ch], 80h
0x18007daae  jz      short loc_18007DACF
0x18007dab0  cmp     byte ptr [rcx+19h], 2
0x18007dab4  jb      short loc_18007DACF
0x18007dab6  mov     edx, 13h
0x18007dabb  mov     r9d, eax
0x18007dabe  lea     r8, WPP_6a02f12a6b2c3ac58024ebcfa94f3c9a_Traceguids
0x18007dac5  mov     rcx, [rcx+10h]
0x18007dac9  call    WPP_SF_d
0x18007dace  nop
0x18007dacf  lea     rcx, [rbp+var_10]; this
0x18007dad3  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18007dad8  nop
0x18007dad9  mov     rcx, [rbp+var_20]
0x18007dadd  test    rcx, rcx
0x18007dae0  jz      short loc_18007DAEE
0x18007dae2  mov     rax, [rcx]
0x18007dae5  mov     rax, [rax+10h]
0x18007dae9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007daee  mov     [rbp+var_20], r14
0x18007daf2  mov     rcx, [rbp+arg_18]
0x18007daf6  test    rcx, rcx
0x18007daf9  jz      short loc_18007DB07
0x18007dafb  mov     rax, [rcx]
0x18007dafe  mov     rax, [rax+10h]
0x18007db02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007db07  mov     [rbp+arg_18], r14
0x18007db0b  mov     rcx, [rbp+var_18]
0x18007db0f  test    rcx, rcx
0x18007db12  jz      short loc_18007DB21
0x18007db14  mov     rax, [rcx]
0x18007db17  mov     rax, [rax+10h]
0x18007db1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007db20  nop
0x18007db21  jmp     loc_18007DCE4
0x18007db26  lea     rdx, WPP_GLOBAL_Control
0x18007db2d  mov     rcx, cs:WPP_GLOBAL_Control
0x18007db34  cmp     rcx, rdx
0x18007db37  jz      short loc_18007DB5E
0x18007db39  test    byte ptr [rcx+1Ch], 80h
0x18007db3d  jz      short loc_18007DB5E
0x18007db3f  cmp     byte ptr [rcx+19h], 2
0x18007db43  jb      short loc_18007DB5E
0x18007db45  mov     edx, 12h
0x18007db4a  mov     r9d, ebx
0x18007db4d  lea     r8, WPP_6a02f12a6b2c3ac58024ebcfa94f3c9a_Traceguids
0x18007db54  mov     rcx, [rcx+10h]
0x18007db58  call    WPP_SF_d
0x18007db5d  nop
0x18007db5e  lea     rcx, [rbp+var_10]; this
0x18007db62  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18007db67  nop
0x18007db68  mov     rcx, [rbp+var_20]
0x18007db6c  test    rcx, rcx
0x18007db6f  jz      short loc_18007DB7D
0x18007db71  mov     rax, [rcx]
0x18007db74  mov     rax, [rax+10h]
0x18007db78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007db7d  mov     [rbp+var_20], r14
0x18007db81  mov     rcx, [rbp+arg_18]
0x18007db85  test    rcx, rcx
0x18007db88  jz      short loc_18007DB96
0x18007db8a  mov     rax, [rcx]
0x18007db8d  mov     rax, [rax+10h]
0x18007db91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007db96  mov     [rbp+arg_18], r14
0x18007db9a  mov     rcx, [rbp+var_18]
0x18007db9e  test    rcx, rcx
0x18007dba1  jz      short loc_18007DBB0
0x18007dba3  mov     rax, [rcx]
0x18007dba6  mov     rax, [rax+10h]
0x18007dbaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007dbaf  nop
0x18007dbb0  jmp     loc_18007DCE4
0x18007dbb5  lea     rcx, [rbp+var_10]; this
0x18007dbb9  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18007dbbe  nop
0x18007dbbf  mov     rcx, [rbp+var_20]
0x18007dbc3  test    rcx, rcx
0x18007dbc6  jz      short loc_18007DBD4
0x18007dbc8  mov     rax, [rcx]
0x18007dbcb  mov     rax, [rax+10h]
0x18007dbcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007dbd4  mov     [rbp+var_20], r14
0x18007dbd8  mov     rcx, [rbp+arg_18]
0x18007dbdc  test    rcx, rcx
0x18007dbdf  jz      short loc_18007DBED
0x18007dbe1  mov     rax, [rcx]
0x18007dbe4  mov     rax, [rax+10h]
0x18007dbe8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007dbed  mov     [rbp+arg_18], r14
0x18007dbf1  mov     rcx, [rbp+var_18]
0x18007dbf5  test    rcx, rcx
0x18007dbf8  jz      short loc_18007DC07
0x18007dbfa  mov     rdx, [rcx]
0x18007dbfd  mov     rax, [rdx+10h]
0x18007dc01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007dc06  nop
0x18007dc07  mov     eax, 1
0x18007dc0c  jmp     loc_18007DCE6
0x18007dc11  lea     rcx, [rbp+var_10]; this
0x18007dc15  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18007dc1a  nop
0x18007dc1b  mov     rcx, [rbp+var_20]
0x18007dc1f  test    rcx, rcx
0x18007dc22  jz      short loc_18007DC30
0x18007dc24  mov     rax, [rcx]
0x18007dc27  mov     rax, [rax+10h]
0x18007dc2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007dc30  mov     [rbp+var_20], r14
0x18007dc34  mov     rcx, [rbp+arg_18]
0x18007dc38  test    rcx, rcx
0x18007dc3b  jz      short loc_18007DC49
0x18007dc3d  mov     rax, [rcx]
0x18007dc40  mov     rax, [rax+10h]
0x18007dc44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007dc49  mov     [rbp+arg_18], r14
0x18007dc4d  mov     rcx, [rbp+var_18]
0x18007dc51  test    rcx, rcx
0x18007dc54  jz      short loc_18007DC63
0x18007dc56  mov     rax, [rcx]
0x18007dc59  mov     rax, [rax+10h]
0x18007dc5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007dc62  nop
0x18007dc63  jmp     short loc_18007DCE4
0x18007dc65  lea     rdx, WPP_GLOBAL_Control
0x18007dc6c  mov     rax, cs:WPP_GLOBAL_Control
0x18007dc73  cmp     rax, rdx
0x18007dc76  jz      short loc_18007DCA0
0x18007dc78  test    byte ptr [rax+1Ch], 80h
0x18007dc7c  jz      short loc_18007DCA0
0x18007dc7e  cmp     byte ptr [rax+19h], 2
0x18007dc82  jb      short loc_18007DCA0
0x18007dc84  mov     edx, 11h
0x18007dc89  mov     r9d, ebx
0x18007dc8c  lea     r8, WPP_6a02f12a6b2c3ac58024ebcfa94f3c9a_Traceguids
0x18007dc93  mov     rcx, [rax+10h]
0x18007dc97  call    WPP_SF_d
0x18007dc9c  mov     rcx, [rbp+var_20]
0x18007dca0  test    rcx, rcx
0x18007dca3  jz      short loc_18007DCB1
0x18007dca5  mov     rax, [rcx]
  ... truncated ...
```
