# URL_AUTHZ_META_STORED_CONTEXT::Initialize(IHttpContext *,INativeSectionException * *)

- ea: `0x180002768`
- end: `0x180002b5d`
- name: `?Initialize@URL_AUTHZ_META_STORED_CONTEXT@@AEAAJPEAVIHttpContext@@PEAPEAVINativeSectionException@@@Z`
- size: `1013`
- prototype: `__int64 __fastcall(URL_AUTHZ_META_STORED_CONTEXT *__hidden this, struct IHttpContext *, struct INativeSectionException **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000223c`

## callees

- `0x180001008`
- `0x180001048`
- `0x180002588`
- `0x180002768`
- `0x1800032f8`
- `0x180004010`

## string_xrefs

- `0x18000281a`: `system.webServer/security/authorization`
- `0x180002904`: `accessType`

## pseudocode

```c
__int64 __fastcall URL_AUTHZ_META_STORED_CONTEXT::Initialize(
        URL_AUTHZ_META_STORED_CONTEXT *this,
        struct IHttpContext *a2,
        struct INativeSectionException **a3)
{
  __int64 v3; // rax
  __int64 (__fastcall *v6)(struct IHttpContext *); // rax
  __int64 (__fastcall ***v7)(_QWORD); // rax
  __int64 v8; // rsi
  __int64 (__fastcall ***v9)(_QWORD, GUID *, __int64 *); // rax
  int v10; // edi
  __int64 v11; // rcx
  unsigned int v12; // esi
  URL_AUTHZ_RULE_ENTRY *v13; // rax
  URL_AUTHZ_RULE_ENTRY *v14; // rbx
  char *v15; // rdi
  char **v16; // rax
  __int64 v17; // rax
  _DWORD *v19; // rax
  int v20; // [rsp+40h] [rbp-40h] BYREF
  __int64 v21; // [rsp+48h] [rbp-38h] BYREF
  __int64 v22; // [rsp+50h] [rbp-30h] BYREF
  __int64 v23; // [rsp+58h] [rbp-28h] BYREF
  __int64 v24; // [rsp+60h] [rbp-20h] BYREF
  __int64 v25; // [rsp+68h] [rbp-18h] BYREF
  __int64 v26; // [rsp+70h] [rbp-10h] BYREF
  __int64 v27; // [rsp+78h] [rbp-8h] BYREF
  unsigned int v28; // [rsp+B8h] [rbp+38h] BYREF
  unsigned int v29; // [rsp+C8h] [rbp+48h] BYREF

  v3 = *(_QWORD *)a2;
  v24 = 0;
  v23 = 0;
  v22 = 0;
  v6 = *(__int64 (__fastcall **)(struct IHttpContext *))(v3 + 160);
  v21 = 0;
  v28 = 0;
  v27 = 0;
  v26 = 0;
  v25 = 0;
  v7 = (__int64 (__fastcall ***)(_QWORD))v6(a2);
  v8 = (**v7)(v7);
  v20 = 1;
  v9 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))(*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 56LL))(g_pGlobalInfo);
  v10 = (**v9)(v9, &IID_INativeConfigurationSystem, &v24);
  if ( v10 < 0 )
    goto LABEL_23;
  v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, __int64 *, struct INativeSectionException **, _QWORD))(*(_QWORD *)v24 + 24LL))(
          v24,
          L"system.webServer/security/authorization",
          v8,
          &v23,
          a3,
          0);
  if ( v10 < 0
    || (v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v23 + 72LL))(
                v23,
                L"bypassLoginPages",
                &v20,
                0,
                0),
        v10 < 0)
    || (v11 = v23,
        *((_DWORD *)this + 6) = v20,
        v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v11 + 40LL))(v11, &v22),
        v10 < 0)
    || ((*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23),
        v23 = 0,
        v10 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v22 + 24LL))(v22, &v28),
        v10 < 0) )
  {
LABEL_23:
    if ( v21 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      v21 = 0;
    }
    if ( v22 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
      v22 = 0;
    }
    if ( v23 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
      v23 = 0;
    }
    if ( v24 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    return (unsigned int)v10;
  }
  v12 = 0;
  if ( v28 )
  {
    while ( 1 )
    {
      v29 = 0;
      v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v22 + 32LL))(v22, v12, &v21);
      if ( v10 < 0 )
        goto LABEL_23;
      v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned int *, _QWORD, _QWORD))(*(_QWORD *)v21 + 48LL))(
              v21,
              L"accessType",
              &v29,
              0,
              0);
      if ( v10 < 0 )
        goto LABEL_23;
      v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *, _QWORD, _QWORD))(*(_QWORD *)v21 + 64LL))(
              v21,
              L"users",
              &v27,
              0,
              0);
      if ( v10 < 0 )
        goto LABEL_23;
      v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *, _QWORD, _QWORD))(*(_QWORD *)v21 + 64LL))(
              v21,
              L"roles",
              &v26,
              0,
              0);
      if ( v10 < 0 )
        goto LABEL_23;
      v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *, _QWORD, _QWORD))(*(_QWORD *)v21 + 64LL))(
              v21,
              L"verbs",
              &v25,
              0,
              0);
      if ( v10 < 0 )
        goto LABEL_23;
      v13 = (URL_AUTHZ_RULE_ENTRY *)operator new(0x60u);
      v14 = v13;
      if ( !v13 )
      {
        v10 = -2147024888;
        goto LABEL_23;
      }
      *((_DWORD *)v13 + 4) = 2;
      *((_QWORD *)v13 + 3) = 0;
      *((_DWORD *)v13 + 8) = 0;
      *((_QWORD *)v13 + 5) = 0;
      *((_DWORD *)v13 + 12) = 0;
      *((_DWORD *)v13 + 13) = 0;
      *((_QWORD *)v13 + 7) = 0;
      *((_DWORD *)v13 + 16) = 0;
      *((_QWORD *)v13 + 9) = 0;
      *((_QWORD *)v13 + 10) = 0;
      *((_DWORD *)v13 + 22) = 0;
      v10 = URL_AUTHZ_RULE_ENTRY::InitializeInstance(v13, v29, v27, v26, v25);
      if ( v10 < 0 )
      {
        URL_AUTHZ_RULE_ENTRY::~URL_AUTHZ_RULE_ENTRY(v14);
        operator delete(v14);
        goto LABEL_23;
      }
      v15 = (char *)this + 8;
      if ( v29 )
      {
        v17 = *(_QWORD *)v15;
        if ( *(char **)(*(_QWORD *)v15 + 8LL) != v15 )
LABEL_21:
          __fastfail(3u);
        *(_QWORD *)v14 = v17;
        *((_QWORD *)v14 + 1) = v15;
        *(_QWORD *)(v17 + 8) = v14;
        *(_QWORD *)v15 = v14;
      }
      else
      {
        v16 = (char **)*((_QWORD *)this + 2);
        if ( *v16 != v15 )
          goto LABEL_21;
        *(_QWORD *)v14 = v15;
        *((_QWORD *)v14 + 1) = v16;
        *v16 = (char *)v14;
        *((_QWORD *)this + 2) = v14;
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      ++v12;
      v21 = 0;
      if ( v12 >= v28 )
        goto LABEL_34;
    }
  }
  v15 = (char *)this + 8;
LABEL_34:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  v22 = 0;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  v24 = 0;
  if ( v28 == 1 )
  {
    v19 = *(_DWORD **)v15;
    if ( !*(_DWORD *)(*(_QWORD *)v15 + 80LL) && (v19[21] || v19[22]) && !v19[4] )
      *((_DWORD *)this + 8) = 1;
  }
  return 0;
}

```

## disassembly

```asm
0x180002768  mov     [rsp-28h+arg_0], rbx
0x18000276d  push    rbp
0x18000276e  push    rsi
0x18000276f  push    rdi
0x180002770  push    r14
0x180002772  push    r15
0x180002774  mov     rbp, rsp
0x180002777  sub     rsp, 80h
0x18000277e  mov     rax, [rdx]
0x180002781  xor     r15d, r15d
0x180002784  mov     r14, rcx
0x180002787  mov     [rbp+var_20], r15
0x18000278b  mov     rcx, rdx
0x18000278e  mov     [rbp+var_28], r15
0x180002792  mov     rbx, r8
0x180002795  mov     [rbp+var_30], r15
0x180002799  mov     rax, [rax+0A0h]
0x1800027a0  mov     [rbp+var_38], r15
0x1800027a4  mov     [rbp+arg_8], r15d
0x1800027a8  mov     [rbp+var_8], r15
0x1800027ac  mov     [rbp+var_10], r15
0x1800027b0  mov     [rbp+var_18], r15
0x1800027b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027b9  mov     rdx, rax
0x1800027bc  mov     rcx, [rax]
0x1800027bf  mov     rax, [rcx]
0x1800027c2  mov     rcx, rdx
0x1800027c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027ca  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x1800027d1  mov     rsi, rax
0x1800027d4  mov     [rbp+var_40], 1
0x1800027db  mov     rdx, [rcx]
0x1800027de  mov     rax, [rdx+38h]
0x1800027e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027e7  mov     r9, rax
0x1800027ea  lea     r8, [rbp+var_20]
0x1800027ee  lea     rdx, IID_INativeConfigurationSystem
0x1800027f5  mov     rcx, [rax]
0x1800027f8  mov     rax, [rcx]
0x1800027fb  mov     rcx, r9
0x1800027fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002803  mov     edi, eax
0x180002805  test    eax, eax
0x180002807  js      loc_180002A84
0x18000280d  mov     rcx, [rbp+var_20]
0x180002811  lea     r9, [rbp+var_28]
0x180002815  mov     [rsp+80h+var_58], r15
0x18000281a  lea     rdx, aSystemWebserve; "system.webServer/security/authorization"
0x180002821  mov     r8, rsi
0x180002824  mov     [rsp+80h+var_60], rbx
0x180002829  mov     rax, [rcx]
0x18000282c  mov     rax, [rax+18h]
0x180002830  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002835  mov     edi, eax
0x180002837  test    eax, eax
0x180002839  js      loc_180002A84
0x18000283f  mov     rcx, [rbp+var_28]
0x180002843  lea     r8, [rbp+var_40]
0x180002847  xor     r9d, r9d
0x18000284a  mov     [rsp+80h+var_60], r15
0x18000284f  lea     rdx, aBypassloginpag; "bypassLoginPages"
0x180002856  mov     rax, [rcx]
0x180002859  mov     rax, [rax+48h]
0x18000285d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002862  mov     edi, eax
0x180002864  test    eax, eax
0x180002866  js      loc_180002A84
0x18000286c  mov     eax, [rbp+var_40]
0x18000286f  lea     rdx, [rbp+var_30]
0x180002873  mov     rcx, [rbp+var_28]
0x180002877  mov     [r14+18h], eax
0x18000287b  mov     rax, [rcx]
0x18000287e  mov     rax, [rax+28h]
0x180002882  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002887  mov     edi, eax
0x180002889  test    eax, eax
0x18000288b  js      loc_180002A84
0x180002891  mov     rcx, [rbp+var_28]
0x180002895  mov     rax, [rcx]
0x180002898  mov     rax, [rax+10h]
0x18000289c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028a1  mov     rcx, [rbp+var_30]
0x1800028a5  lea     rdx, [rbp+arg_8]
0x1800028a9  mov     [rbp+var_28], r15
0x1800028ad  mov     rax, [rcx]
0x1800028b0  mov     rax, [rax+18h]
0x1800028b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028b9  mov     edi, eax
0x1800028bb  test    eax, eax
0x1800028bd  js      loc_180002A84
0x1800028c3  mov     esi, r15d
0x1800028c6  cmp     [rbp+arg_8], r15d
0x1800028ca  jbe     loc_180002B04
0x1800028d0  mov     rcx, [rbp+var_30]
0x1800028d4  lea     r8, [rbp+var_38]
0x1800028d8  mov     [rbp+arg_18], r15d
0x1800028dc  mov     edx, esi
0x1800028de  mov     rax, [rcx]
0x1800028e1  mov     rax, [rax+20h]
0x1800028e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028ea  mov     edi, eax
0x1800028ec  test    eax, eax
0x1800028ee  js      loc_180002A84
0x1800028f4  mov     rcx, [rbp+var_38]
0x1800028f8  lea     r8, [rbp+arg_18]
0x1800028fc  xor     r9d, r9d
0x1800028ff  mov     [rsp+80h+var_60], r15
0x180002904  lea     rdx, aAccesstype; "accessType"
0x18000290b  mov     rax, [rcx]
0x18000290e  mov     rax, [rax+30h]
0x180002912  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002917  mov     edi, eax
0x180002919  test    eax, eax
0x18000291b  js      loc_180002A84
0x180002921  mov     rcx, [rbp+var_38]
0x180002925  lea     r8, [rbp+var_8]
0x180002929  xor     r9d, r9d
0x18000292c  mov     [rsp+80h+var_60], r15
0x180002931  lea     rdx, aUsers; "users"
0x180002938  mov     rax, [rcx]
0x18000293b  mov     rax, [rax+40h]
0x18000293f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002944  mov     edi, eax
0x180002946  test    eax, eax
0x180002948  js      loc_180002A84
0x18000294e  mov     rcx, [rbp+var_38]
0x180002952  lea     r8, [rbp+var_10]
0x180002956  xor     r9d, r9d
0x180002959  mov     [rsp+80h+var_60], r15
0x18000295e  lea     rdx, aRoles; "roles"
0x180002965  mov     rax, [rcx]
0x180002968  mov     rax, [rax+40h]
0x18000296c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002971  mov     edi, eax
0x180002973  test    eax, eax
0x180002975  js      loc_180002A84
0x18000297b  mov     rcx, [rbp+var_38]
0x18000297f  lea     r8, [rbp+var_18]
0x180002983  xor     r9d, r9d
0x180002986  mov     [rsp+80h+var_60], r15
0x18000298b  lea     rdx, aVerbs; "verbs"
0x180002992  mov     rax, [rcx]
0x180002995  mov     rax, [rax+40h]
0x180002999  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000299e  mov     edi, eax
0x1800029a0  test    eax, eax
0x1800029a2  js      loc_180002A84
0x1800029a8  mov     ecx, 60h ; '`'; Size
0x1800029ad  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800029b2  mov     rbx, rax
0x1800029b5  test    rax, rax
0x1800029b8  jz      loc_180002AFD
0x1800029be  mov     dword ptr [rax+10h], 2
0x1800029c5  mov     rcx, rbx
0x1800029c8  mov     [rax+18h], r15
0x1800029cc  mov     [rax+20h], r15d
0x1800029d0  mov     [rax+28h], r15
0x1800029d4  mov     [rax+30h], r15d
0x1800029d8  mov     [rax+34h], r15d
0x1800029dc  mov     [rax+38h], r15
0x1800029e0  mov     [rax+40h], r15d
0x1800029e4  mov     [rax+48h], r15
0x1800029e8  mov     [rax+50h], r15
0x1800029ec  mov     [rax+58h], r15d
0x1800029f0  mov     rax, [rbp+var_18]
0x1800029f4  mov     r9, [rbp+var_10]
0x1800029f8  mov     r8, [rbp+var_8]
0x1800029fc  mov     edx, [rbp+arg_18]
0x1800029ff  mov     [rsp+80h+var_60], rax
0x180002a04  call    ?InitializeInstance@URL_AUTHZ_RULE_ENTRY@@QEAAJW4AUTHORIZATION_ACCESS_TYPE@@PEBG11@Z; URL_AUTHZ_RULE_ENTRY::InitializeInstance(AUTHORIZATION_ACCESS_TYPE,ushort const *,ushort const *,ushort const *)
0x180002a09  mov     edi, eax
0x180002a0b  test    eax, eax
0x180002a0d  js      short loc_180002A74
0x180002a0f  lea     rdi, [r14+8]
0x180002a13  cmp     [rbp+arg_18], r15d
0x180002a17  jnz     short loc_180002A32
0x180002a19  mov     rax, [rdi+8]
0x180002a1d  cmp     [rax], rdi
0x180002a20  jnz     short loc_180002A6D
0x180002a22  mov     [rbx], rdi
0x180002a25  mov     [rbx+8], rax
0x180002a29  mov     [rax], rbx
0x180002a2c  mov     [rdi+8], rbx
0x180002a30  jmp     short loc_180002A49
0x180002a32  mov     rax, [rdi]
0x180002a35  cmp     [rax+8], rdi
0x180002a39  jnz     short loc_180002A6D
0x180002a3b  mov     [rbx], rax
0x180002a3e  mov     [rbx+8], rdi
0x180002a42  mov     [rax+8], rbx
0x180002a46  mov     [rdi], rbx
0x180002a49  mov     rcx, [rbp+var_38]
0x180002a4d  mov     rax, [rcx]
0x180002a50  mov     rax, [rax+10h]
0x180002a54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a59  inc     esi
0x180002a5b  mov     [rbp+var_38], r15
0x180002a5f  cmp     esi, [rbp+arg_8]
0x180002a62  jb      loc_1800028D0
0x180002a68  jmp     loc_180002B08
0x180002a6d  mov     ecx, 3
0x180002a72  int     29h; Win8: RtlFailFast(ecx)
0x180002a74  mov     rcx, rbx; this
0x180002a77  call    ??1URL_AUTHZ_RULE_ENTRY@@QEAA@XZ; URL_AUTHZ_RULE_ENTRY::~URL_AUTHZ_RULE_ENTRY(void)
0x180002a7c  mov     rcx, rbx; Block
0x180002a7f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002a84  mov     rcx, [rbp+var_38]
0x180002a88  test    rcx, rcx
0x180002a8b  jz      short loc_180002A9D
0x180002a8d  mov     rax, [rcx]
0x180002a90  mov     rax, [rax+10h]
0x180002a94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a99  mov     [rbp+var_38], r15
0x180002a9d  mov     rcx, [rbp+var_30]
0x180002aa1  test    rcx, rcx
0x180002aa4  jz      short loc_180002AB6
0x180002aa6  mov     rax, [rcx]
0x180002aa9  mov     rax, [rax+10h]
0x180002aad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ab2  mov     [rbp+var_30], r15
0x180002ab6  mov     rcx, [rbp+var_28]
0x180002aba  test    rcx, rcx
0x180002abd  jz      short loc_180002ACF
0x180002abf  mov     rax, [rcx]
0x180002ac2  mov     rax, [rax+10h]
0x180002ac6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002acb  mov     [rbp+var_28], r15
0x180002acf  mov     rcx, [rbp+var_20]
0x180002ad3  test    rcx, rcx
0x180002ad6  jz      short loc_180002AE4
0x180002ad8  mov     rax, [rcx]
0x180002adb  mov     rax, [rax+10h]
0x180002adf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ae4  mov     eax, edi
0x180002ae6  mov     rbx, [rsp+80h+arg_0]
0x180002aee  add     rsp, 80h
0x180002af5  pop     r15
0x180002af7  pop     r14
0x180002af9  pop     rdi
0x180002afa  pop     rsi
0x180002afb  pop     rbp
0x180002afc  retn
0x180002afd  mov     edi, 80070008h
0x180002b02  jmp     short loc_180002A84
0x180002b04  lea     rdi, [r14+8]
0x180002b08  mov     rcx, [rbp+var_30]
0x180002b0c  mov     rax, [rcx]
0x180002b0f  mov     rax, [rax+10h]
0x180002b13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b18  mov     rcx, [rbp+var_20]
0x180002b1c  mov     [rbp+var_30], r15
0x180002b20  mov     rax, [rcx]
0x180002b23  mov     rax, [rax+10h]
0x180002b27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b2c  cmp     [rbp+arg_8], 1
0x180002b30  mov     [rbp+var_20], r15
0x180002b34  jnz     short loc_180002B59
0x180002b36  mov     rax, [rdi]
0x180002b39  cmp     [rax+50h], r15d
0x180002b3d  jnz     short loc_180002B59
0x180002b3f  cmp     [rax+54h], r15d
0x180002b43  jnz     short loc_180002B4B
0x180002b45  cmp     [rax+58h], r15d
0x180002b49  jz      short loc_180002B59
0x180002b4b  cmp     [rax+10h], r15d
0x180002b4f  jnz     short loc_180002B59
0x180002b51  mov     dword ptr [r14+20h], 1
0x180002b59  xor     eax, eax
0x180002b5b  jmp     short loc_180002AE6
```
