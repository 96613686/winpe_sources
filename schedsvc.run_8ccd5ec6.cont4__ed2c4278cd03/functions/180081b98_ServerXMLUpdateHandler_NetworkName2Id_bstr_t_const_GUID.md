# ServerXMLUpdateHandler::NetworkName2Id(_bstr_t const &,_GUID &)

- ea: `0x180081b98`
- end: `0x18008204a`
- name: `?NetworkName2Id@ServerXMLUpdateHandler@@AEAAJAEBV_bstr_t@@AEAU_GUID@@@Z`
- size: `1202`
- prototype: `int(ServerXMLUpdateHandler *__hidden this, const struct _bstr_t *, struct _GUID *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18004cfa0`

## callees

- `0x180011e40`
- `0x180030620`
- `0x180032c30`
- `0x180056954`
- `0x180081b98`
- `0x180088010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180081daf`
- `msvcrt!_wcsicmp` at `0x180081daf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180081d76`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180081d76`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180081c42`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180081c42`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
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
0x180081b98  mov     [rsp-18h+arg_8], rbx
0x180081b9d  mov     [rsp-18h+arg_10], rsi
0x180081ba2  mov     [rsp-18h+arg_0], rcx
0x180081ba7  push    rbp
0x180081ba8  push    rdi
0x180081ba9  push    r14
0x180081bab  mov     rbp, rsp
0x180081bae  sub     rsp, 50h
0x180081bb2  mov     rsi, r8
0x180081bb5  mov     rdi, rdx
0x180081bb8  xor     r14d, r14d
0x180081bbb  mov     [rbp+var_18], r14
0x180081bbf  mov     [rbp+arg_18], r14
0x180081bc3  mov     [rbp+var_20], r14
0x180081bc7  mov     rcx, rdx; this
0x180081bca  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x180081bcf  test    eax, eax
0x180081bd1  jnz     short loc_180081C25
0x180081bd3  mov     rcx, [rbp+var_20]
0x180081bd7  test    rcx, rcx
0x180081bda  jz      short loc_180081BE8
0x180081bdc  mov     rax, [rcx]
0x180081bdf  mov     rax, [rax+10h]
0x180081be3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081be8  mov     [rbp+var_20], r14
0x180081bec  mov     rcx, [rbp+arg_18]
0x180081bf0  test    rcx, rcx
0x180081bf3  jz      short loc_180081C01
0x180081bf5  mov     rax, [rcx]
0x180081bf8  mov     rax, [rax+10h]
0x180081bfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081c01  mov     [rbp+arg_18], r14
0x180081c05  mov     rcx, [rbp+var_18]
0x180081c09  test    rcx, rcx
0x180081c0c  jz      short loc_180081C1B
0x180081c0e  mov     rax, [rcx]
0x180081c11  mov     rax, [rax+10h]
0x180081c15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081c1a  nop
0x180081c1b  mov     eax, 80041318h
0x180081c20  jmp     loc_180082034
0x180081c25  lea     rax, [rbp+var_18]
0x180081c29  mov     [rsp+50h+ppv], rax; ppv
0x180081c2e  lea     r9, IID_INetworkListManagerPrivate; riid
0x180081c35  xor     edx, edx; pUnkOuter
0x180081c37  lea     r8d, [rdx+4]; dwClsContext
0x180081c3b  lea     rcx, CLSID_CNetworkListManager; rclsid
0x180081c42  call    cs:__imp_CoCreateInstance
0x180081c49  nop     dword ptr [rax+rax+00h]
0x180081c4e  mov     ebx, eax
0x180081c50  test    eax, eax
0x180081c52  jns     loc_180081CDD
0x180081c58  lea     rdx, WPP_GLOBAL_Control
0x180081c5f  mov     rcx, cs:WPP_GLOBAL_Control
0x180081c66  cmp     rcx, rdx
0x180081c69  jz      short loc_180081C90
0x180081c6b  test    byte ptr [rcx+1Ch], 80h
0x180081c6f  jz      short loc_180081C90
0x180081c71  cmp     byte ptr [rcx+19h], 2
0x180081c75  jb      short loc_180081C90
0x180081c77  mov     edx, 10h
0x180081c7c  mov     r9d, eax
0x180081c7f  lea     r8, WPP_6a02f12a6b2c3ac58024ebcfa94f3c9a_Traceguids
0x180081c86  mov     rcx, [rcx+10h]
0x180081c8a  call    WPP_SF_d
0x180081c8f  nop
0x180081c90  mov     rcx, [rbp+var_20]
0x180081c94  test    rcx, rcx
0x180081c97  jz      short loc_180081CA5
0x180081c99  mov     rax, [rcx]
0x180081c9c  mov     rax, [rax+10h]
0x180081ca0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081ca5  mov     [rbp+var_20], r14
0x180081ca9  mov     rcx, [rbp+arg_18]
0x180081cad  test    rcx, rcx
0x180081cb0  jz      short loc_180081CBE
0x180081cb2  mov     rax, [rcx]
0x180081cb5  mov     rax, [rax+10h]
0x180081cb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081cbe  mov     [rbp+arg_18], r14
0x180081cc2  mov     rcx, [rbp+var_18]
0x180081cc6  test    rcx, rcx
0x180081cc9  jz      short loc_180081CD8
0x180081ccb  mov     rax, [rcx]
0x180081cce  mov     rax, [rax+10h]
0x180081cd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081cd7  nop
0x180081cd8  jmp     loc_180082032
0x180081cdd  mov     rcx, [rbp+var_18]
0x180081ce1  mov     rax, [rcx]
0x180081ce4  lea     r8, [rbp+var_20]
0x180081ce8  mov     edx, 3
0x180081ced  mov     rax, [rax+20h]
0x180081cf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081cf6  mov     ebx, eax
0x180081cf8  mov     rcx, [rbp+var_20]
0x180081cfc  test    eax, eax
0x180081cfe  js      loc_180081FB3
0x180081d04  test    rcx, rcx
0x180081d07  jz      loc_180081FB3
0x180081d0d  mov     dword ptr [rbp+arg_0], r14d
0x180081d11  mov     [rbp+pv], r14
0x180081d15  mov     [rbp+var_10], r14
0x180081d19  mov     rax, [rcx]
0x180081d1c  lea     r9, [rbp+arg_0]
0x180081d20  lea     r8, [rbp+arg_18]
0x180081d24  mov     edx, 1
0x180081d29  mov     rax, [rax+18h]
0x180081d2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081d32  mov     ebx, eax
0x180081d34  test    eax, eax
0x180081d36  js      loc_180081F5F
0x180081d3c  cmp     eax, 1
0x180081d3f  jz      loc_180081F03
0x180081d45  cmp     dword ptr [rbp+arg_0], r14d
0x180081d49  jz      loc_180081F03
0x180081d4f  mov     rcx, [rbp+arg_18]
0x180081d53  mov     rax, [rcx]
0x180081d56  lea     rdx, [rbp+pv]
0x180081d5a  mov     rax, [rax+18h]
0x180081d5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081d63  mov     ebx, eax
0x180081d65  mov     rdx, [rbp+pv]
0x180081d69  lea     rcx, [rbp+var_10]
0x180081d6d  call    ??4_bstr_t@@QEAAAEAV0@PEBG@Z; _bstr_t::operator=(ushort const *)
0x180081d72  mov     rcx, [rbp+pv]; pv
0x180081d76  call    cs:__imp_CoTaskMemFree
0x180081d7d  nop     dword ptr [rax+rax+00h]
0x180081d82  mov     [rbp+pv], r14
0x180081d86  test    ebx, ebx
0x180081d88  js      loc_180081E74
0x180081d8e  mov     rax, [rbp+var_10]
0x180081d92  test    rax, rax
0x180081d95  jz      short loc_180081D9C
0x180081d97  mov     rdx, [rax]
0x180081d9a  jmp     short loc_180081D9F
0x180081d9c  mov     rdx, r14; String2
0x180081d9f  mov     rax, [rdi]
0x180081da2  test    rax, rax
0x180081da5  jz      short loc_180081DAC
0x180081da7  mov     rcx, [rax]
0x180081daa  jmp     short loc_180081DAF
0x180081dac  mov     rcx, r14; String1
0x180081daf  call    cs:__imp__wcsicmp
0x180081db6  nop     dword ptr [rax+rax+00h]
0x180081dbb  test    eax, eax
0x180081dbd  jz      short loc_180081DC8
0x180081dbf  mov     rcx, [rbp+var_20]
0x180081dc3  jmp     loc_180081D19
0x180081dc8  mov     rcx, [rbp+arg_18]
0x180081dcc  mov     rax, [rcx]
0x180081dcf  mov     rdx, rsi
0x180081dd2  mov     rax, [rax+30h]
0x180081dd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081ddb  mov     ebx, eax
0x180081ddd  test    eax, eax
0x180081ddf  jns     loc_180081F5F
0x180081de5  lea     rdx, WPP_GLOBAL_Control
0x180081dec  mov     rcx, cs:WPP_GLOBAL_Control
0x180081df3  cmp     rcx, rdx
0x180081df6  jz      short loc_180081E1D
0x180081df8  test    byte ptr [rcx+1Ch], 80h
0x180081dfc  jz      short loc_180081E1D
0x180081dfe  cmp     byte ptr [rcx+19h], 2
0x180081e02  jb      short loc_180081E1D
0x180081e04  mov     edx, 13h
0x180081e09  mov     r9d, eax
0x180081e0c  lea     r8, WPP_6a02f12a6b2c3ac58024ebcfa94f3c9a_Traceguids
0x180081e13  mov     rcx, [rcx+10h]
0x180081e17  call    WPP_SF_d
0x180081e1c  nop
0x180081e1d  lea     rcx, [rbp+var_10]; this
0x180081e21  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180081e26  nop
0x180081e27  mov     rcx, [rbp+var_20]
0x180081e2b  test    rcx, rcx
0x180081e2e  jz      short loc_180081E3C
0x180081e30  mov     rax, [rcx]
0x180081e33  mov     rax, [rax+10h]
0x180081e37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081e3c  mov     [rbp+var_20], r14
0x180081e40  mov     rcx, [rbp+arg_18]
0x180081e44  test    rcx, rcx
0x180081e47  jz      short loc_180081E55
0x180081e49  mov     rax, [rcx]
0x180081e4c  mov     rax, [rax+10h]
0x180081e50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081e55  mov     [rbp+arg_18], r14
0x180081e59  mov     rcx, [rbp+var_18]
0x180081e5d  test    rcx, rcx
0x180081e60  jz      short loc_180081E6F
0x180081e62  mov     rax, [rcx]
0x180081e65  mov     rax, [rax+10h]
0x180081e69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081e6e  nop
0x180081e6f  jmp     loc_180082032
0x180081e74  lea     rdx, WPP_GLOBAL_Control
0x180081e7b  mov     rcx, cs:WPP_GLOBAL_Control
0x180081e82  cmp     rcx, rdx
0x180081e85  jz      short loc_180081EAC
0x180081e87  test    byte ptr [rcx+1Ch], 80h
0x180081e8b  jz      short loc_180081EAC
0x180081e8d  cmp     byte ptr [rcx+19h], 2
0x180081e91  jb      short loc_180081EAC
0x180081e93  mov     edx, 12h
0x180081e98  mov     r9d, ebx
0x180081e9b  lea     r8, WPP_6a02f12a6b2c3ac58024ebcfa94f3c9a_Traceguids
0x180081ea2  mov     rcx, [rcx+10h]
0x180081ea6  call    WPP_SF_d
0x180081eab  nop
0x180081eac  lea     rcx, [rbp+var_10]; this
0x180081eb0  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180081eb5  nop
0x180081eb6  mov     rcx, [rbp+var_20]
0x180081eba  test    rcx, rcx
0x180081ebd  jz      short loc_180081ECB
0x180081ebf  mov     rax, [rcx]
0x180081ec2  mov     rax, [rax+10h]
0x180081ec6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081ecb  mov     [rbp+var_20], r14
0x180081ecf  mov     rcx, [rbp+arg_18]
0x180081ed3  test    rcx, rcx
0x180081ed6  jz      short loc_180081EE4
0x180081ed8  mov     rax, [rcx]
0x180081edb  mov     rax, [rax+10h]
0x180081edf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081ee4  mov     [rbp+arg_18], r14
0x180081ee8  mov     rcx, [rbp+var_18]
0x180081eec  test    rcx, rcx
0x180081eef  jz      short loc_180081EFE
0x180081ef1  mov     rax, [rcx]
0x180081ef4  mov     rax, [rax+10h]
0x180081ef8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081efd  nop
0x180081efe  jmp     loc_180082032
0x180081f03  lea     rcx, [rbp+var_10]; this
0x180081f07  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180081f0c  nop
0x180081f0d  mov     rcx, [rbp+var_20]
0x180081f11  test    rcx, rcx
0x180081f14  jz      short loc_180081F22
0x180081f16  mov     rax, [rcx]
0x180081f19  mov     rax, [rax+10h]
0x180081f1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081f22  mov     [rbp+var_20], r14
0x180081f26  mov     rcx, [rbp+arg_18]
0x180081f2a  test    rcx, rcx
0x180081f2d  jz      short loc_180081F3B
0x180081f2f  mov     rax, [rcx]
0x180081f32  mov     rax, [rax+10h]
0x180081f36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081f3b  mov     [rbp+arg_18], r14
0x180081f3f  mov     rcx, [rbp+var_18]
0x180081f43  test    rcx, rcx
0x180081f46  jz      short loc_180081F55
0x180081f48  mov     rdx, [rcx]
0x180081f4b  mov     rax, [rdx+10h]
0x180081f4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081f54  nop
0x180081f55  mov     eax, 1
0x180081f5a  jmp     loc_180082034
0x180081f5f  lea     rcx, [rbp+var_10]; this
0x180081f63  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180081f68  nop
0x180081f69  mov     rcx, [rbp+var_20]
0x180081f6d  test    rcx, rcx
0x180081f70  jz      short loc_180081F7E
0x180081f72  mov     rax, [rcx]
0x180081f75  mov     rax, [rax+10h]
0x180081f79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081f7e  mov     [rbp+var_20], r14
0x180081f82  mov     rcx, [rbp+arg_18]
0x180081f86  test    rcx, rcx
0x180081f89  jz      short loc_180081F97
0x180081f8b  mov     rax, [rcx]
0x180081f8e  mov     rax, [rax+10h]
0x180081f92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081f97  mov     [rbp+arg_18], r14
0x180081f9b  mov     rcx, [rbp+var_18]
0x180081f9f  test    rcx, rcx
0x180081fa2  jz      short loc_180081FB1
0x180081fa4  mov     rax, [rcx]
0x180081fa7  mov     rax, [rax+10h]
0x180081fab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081fb0  nop
0x180081fb1  jmp     short loc_180082032
0x180081fb3  lea     rdx, WPP_GLOBAL_Control
0x180081fba  mov     rax, cs:WPP_GLOBAL_Control
0x180081fc1  cmp     rax, rdx
0x180081fc4  jz      short loc_180081FEE
0x180081fc6  test    byte ptr [rax+1Ch], 80h
0x180081fca  jz      short loc_180081FEE
0x180081fcc  cmp     byte ptr [rax+19h], 2
0x180081fd0  jb      short loc_180081FEE
0x180081fd2  mov     edx, 11h
0x180081fd7  mov     r9d, ebx
0x180081fda  lea     r8, WPP_6a02f12a6b2c3ac58024ebcfa94f3c9a_Traceguids
0x180081fe1  mov     rcx, [rax+10h]
0x180081fe5  call    WPP_SF_d
0x180081fea  mov     rcx, [rbp+var_20]
  ... truncated ...
```
