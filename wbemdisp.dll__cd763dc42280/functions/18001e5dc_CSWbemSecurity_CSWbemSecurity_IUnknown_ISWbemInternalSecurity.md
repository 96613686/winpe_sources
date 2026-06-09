# CSWbemSecurity::CSWbemSecurity(IUnknown *,ISWbemInternalSecurity *)

- ea: `0x18001e5dc`
- end: `0x18001e8b3`
- name: `??0CSWbemSecurity@@QEAA@PEAUIUnknown@@PEAUISWbemInternalSecurity@@@Z`
- size: `727`
- prototype: `CSWbemSecurity *__fastcall(struct IDispatch *this, struct IUnknown *, struct ISWbemInternalSecurity *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18001cec8`

## callees

- `0x180006710`
- `0x1800126c0`
- `0x18001c274`
- `0x18001cc78`
- `0x18001e5dc`
- `0x180033b34`
- `0x180033d68`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18001e817`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e826`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e835`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e844`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e853`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e817`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e826`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e835`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e844`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e853`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001e6e7`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001e7ce`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001e6e7`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001e7ce`

## string_xrefs

- `0x18001e66e`: `SWbemSecurity`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct IDispatch *__fastcall CSWbemSecurity::CSWbemSecurity(
        struct IDispatch *this,
        struct IUnknown *a2,
        struct ISWbemInternalSecurity *a3)
{
  struct IDispatch *v6; // rcx
  CSWbemPrivilegeSet *v7; // rax
  struct IDispatchVtbl *v8; // rax
  struct _COAUTHIDENTITY *v9; // rdi
  __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rcx
  CSWbemProxyCache *v13; // rax
  struct IDispatchVtbl *v14; // rax
  struct IDispatchVtbl *lpVtbl; // rcx
  BSTR v17; // [rsp+30h] [rbp-40h] BYREF
  BSTR v18; // [rsp+38h] [rbp-38h] BYREF
  BSTR v19; // [rsp+40h] [rbp-30h] BYREF
  struct ISWbemPrivilegeSet *v20; // [rsp+48h] [rbp-28h] BYREF
  struct _GUID v21; // [rsp+50h] [rbp-20h] BYREF
  struct _GUID v22; // [rsp+60h] [rbp-10h] BYREF
  BSTR bstrString; // [rsp+B0h] [rbp+40h] BYREF
  BSTR v24; // [rsp+B8h] [rbp+48h] BYREF

  this->lpVtbl = (struct IDispatchVtbl *)&CSWbemSecurity::`vftable'{for `ISWbemSecurity'};
  this[1].lpVtbl = (struct IDispatchVtbl *)&CSWbemSecurity::`vftable'{for `ISupportErrorInfo'};
  this[2].lpVtbl = (struct IDispatchVtbl *)&CSWbemSecurity::`vftable'{for `ISWbemInternalSecurity'};
  this[3].lpVtbl = (struct IDispatchVtbl *)&CSWbemSecurity::`vftable'{for `IProvideClassInfo'};
  this[4].lpVtbl = 0;
  v6 = this + 5;
  v6->lpVtbl = (struct IDispatchVtbl *)&CDispatchHelp::`vftable';
  v6[3].lpVtbl = 0;
  v6[4].lpVtbl = 0;
  v6[5].lpVtbl = 0;
  v6[1].lpVtbl = 0;
  LODWORD(v6[2].lpVtbl) = 0;
  this[15].lpVtbl = 0;
  this[16].lpVtbl = 0;
  v22 = CLSID_SWbemSecurity;
  v21 = IID_ISWbemSecurity;
  CDispatchHelp::SetObj((CDispatchHelp *)v6, this, &v21, &v22, (OLECHAR *)L"SWbemSecurity");
  LODWORD(this[17].lpVtbl) = 1;
  if ( a3 )
  {
    *(_QWORD *)&v21.Data1 = 0;
    if ( (**(int (__fastcall ***)(struct ISWbemInternalSecurity *, GUID *, struct _GUID *))a3)(
           a3,
           &IID_ISWbemSecurity,
           &v21) >= 0 )
    {
      v20 = 0;
      if ( (*(int (__fastcall **)(_QWORD, struct ISWbemPrivilegeSet **))(**(_QWORD **)&v21.Data1 + 88LL))(
             *(_QWORD *)&v21.Data1,
             &v20) >= 0 )
      {
        v7 = (CSWbemPrivilegeSet *)CWin32DefaultArena::WbemMemAlloc(0x88u);
        *(_QWORD *)&v22.Data1 = v7;
        if ( v7 )
          v8 = (struct IDispatchVtbl *)CSWbemPrivilegeSet::CSWbemPrivilegeSet(v7, v20);
        else
          v8 = 0;
        this[4].lpVtbl = v8;
        bstrString = 0;
        v24 = 0;
        v17 = 0;
        v18 = 0;
        v19 = 0;
        (*(void (__fastcall **)(struct ISWbemInternalSecurity *, BSTR *))(*(_QWORD *)a3 + 24LL))(a3, &bstrString);
        (*(void (__fastcall **)(struct ISWbemInternalSecurity *, BSTR *))(*(_QWORD *)a3 + 40LL))(a3, &v24);
        (*(void (__fastcall **)(struct ISWbemInternalSecurity *, BSTR *, BSTR *, BSTR *))(*(_QWORD *)a3 + 32LL))(
          a3,
          &v17,
          &v18,
          &v19);
        v9 = 0;
        *(_QWORD *)&v22.Data1 = 0;
        v10 = -1;
        if ( v17 )
        {
          v11 = -1;
          do
            ++v11;
          while ( v17[v11] );
          if ( v11 )
            goto LABEL_18;
        }
        if ( v18 )
        {
          v12 = -1;
          do
            ++v12;
          while ( v18[v12] );
          if ( v12 )
            goto LABEL_18;
        }
        if ( v19 )
        {
          do
            ++v10;
          while ( v19[v10] );
          if ( v10 )
          {
LABEL_18:
            WbemAllocAuthIdentity(v17, v18, v19, (struct _COAUTHIDENTITY **)&v22);
            v9 = *(struct _COAUTHIDENTITY **)&v22.Data1;
          }
        }
        v13 = (CSWbemProxyCache *)CWin32DefaultArena::WbemMemAlloc(0x150u);
        *(_QWORD *)&v22.Data1 = v13;
        if ( v13 )
          v14 = (struct IDispatchVtbl *)CSWbemProxyCache::CSWbemProxyCache(v13, a2, v9, v24, bstrString);
        else
          v14 = 0;
        this[15].lpVtbl = v14;
        if ( v9 )
          WbemFreeAuthIdentity(v9);
        if ( bstrString )
          SysFreeString(bstrString);
        if ( v24 )
          SysFreeString(v24);
        if ( v17 )
          SysFreeString(v17);
        if ( v18 )
          SysFreeString(v18);
        if ( v19 )
          SysFreeString(v19);
        lpVtbl = this[15].lpVtbl;
        if ( lpVtbl )
          this[16].lpVtbl = (struct IDispatchVtbl *)CSWbemProxyCache::GetProxy(
                                                      (CSWbemProxyCache *)lpVtbl,
                                                      (enum WbemAuthenticationLevelEnum)HIDWORD(lpVtbl[5].GetIDsOfNames),
                                                      (enum WbemImpersonationLevelEnum)LODWORD(lpVtbl[5].Invoke),
                                                      0);
        ((void (__fastcall *)(struct ISWbemPrivilegeSet *))v20->lpVtbl->Release)(v20);
      }
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v21.Data1 + 16LL))(*(_QWORD *)&v21.Data1);
    }
  }
  _InterlockedIncrement(&g_cObj);
  return this;
}

```

## disassembly

```asm
0x18001e5dc  mov     [rsp-28h+arg_0], rcx
0x18001e5e1  push    rbp
0x18001e5e2  push    rbx
0x18001e5e3  push    rsi
0x18001e5e4  push    rdi
0x18001e5e5  push    r14
0x18001e5e7  mov     rbp, rsp
0x18001e5ea  sub     rsp, 70h
0x18001e5ee  mov     rdi, r8
0x18001e5f1  mov     rsi, rdx
0x18001e5f4  mov     rbx, rcx
0x18001e5f7  lea     rax, ??_7CSWbemSecurity@@6BISWbemSecurity@@@; const CSWbemSecurity::`vftable'{for `ISWbemSecurity'}
0x18001e5fe  mov     [rcx], rax
0x18001e601  lea     rax, ??_7CSWbemSecurity@@6BISupportErrorInfo@@@; const CSWbemSecurity::`vftable'{for `ISupportErrorInfo'}
0x18001e608  mov     [rcx+8], rax
0x18001e60c  lea     rax, ??_7CSWbemSecurity@@6BISWbemInternalSecurity@@@; const CSWbemSecurity::`vftable'{for `ISWbemInternalSecurity'}
0x18001e613  mov     [rcx+10h], rax
0x18001e617  lea     rax, ??_7CSWbemSecurity@@6BIProvideClassInfo@@@; const CSWbemSecurity::`vftable'{for `IProvideClassInfo'}
0x18001e61e  mov     [rcx+18h], rax
0x18001e622  xor     r14d, r14d
0x18001e625  mov     [rcx+20h], r14
0x18001e629  add     rcx, 28h ; '('; this
0x18001e62d  lea     rax, ??_7CDispatchHelp@@6B@; const CDispatchHelp::`vftable'
0x18001e634  mov     [rcx], rax
0x18001e637  mov     [rcx+18h], r14
0x18001e63b  mov     [rcx+20h], r14
0x18001e63f  mov     [rcx+28h], r14
0x18001e643  mov     [rcx+8], r14
0x18001e647  mov     [rcx+10h], r14d
0x18001e64b  mov     [rbx+78h], r14
0x18001e64f  mov     [rbx+80h], r14
0x18001e656  movups  xmm0, xmmword ptr cs:CLSID_SWbemSecurity.Data1
0x18001e65d  movdqu  xmmword ptr [rbp+var_10.Data1], xmm0
0x18001e662  movups  xmm1, xmmword ptr cs:IID_ISWbemSecurity.Data1
0x18001e669  movdqu  xmmword ptr [rbp+var_20.Data1], xmm1
0x18001e66e  lea     rax, aSwbemsecurity; "SWbemSecurity"
0x18001e675  mov     [rsp+70h+psz], rax; psz
0x18001e67a  lea     r9, [rbp+var_10]; struct _GUID *
0x18001e67e  lea     r8, [rbp+var_20]; struct _GUID *
0x18001e682  mov     rdx, rbx; struct IDispatch *
0x18001e685  call    ?SetObj@CDispatchHelp@@QEAAXPEAUIDispatch@@U_GUID@@1PEAG@Z; CDispatchHelp::SetObj(IDispatch *,_GUID,_GUID,ushort *)
0x18001e68a  mov     dword ptr [rbx+88h], 1
0x18001e694  test    rdi, rdi
0x18001e697  jz      loc_18001E89E
0x18001e69d  mov     qword ptr [rbp+var_20.Data1], r14
0x18001e6a1  mov     rax, [rdi]
0x18001e6a4  lea     r8, [rbp+var_20]
0x18001e6a8  lea     rdx, IID_ISWbemSecurity
0x18001e6af  mov     rcx, rdi
0x18001e6b2  mov     rax, [rax]
0x18001e6b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e6ba  test    eax, eax
0x18001e6bc  js      loc_18001E89E
0x18001e6c2  mov     [rbp+var_28], r14
0x18001e6c6  mov     rcx, qword ptr [rbp+var_20.Data1]
0x18001e6ca  mov     rax, [rcx]
0x18001e6cd  lea     rdx, [rbp+var_28]
0x18001e6d1  mov     rax, [rax+58h]
0x18001e6d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e6da  test    eax, eax
0x18001e6dc  js      loc_18001E88E
0x18001e6e2  mov     ecx, 88h
0x18001e6e7  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18001e6ed  mov     qword ptr [rbp+var_10.Data1], rax
0x18001e6f1  test    rax, rax
0x18001e6f4  jz      short loc_18001E704
0x18001e6f6  mov     rdx, [rbp+var_28]; struct ISWbemPrivilegeSet *
0x18001e6fa  mov     rcx, rax; this
0x18001e6fd  call    ??0CSWbemPrivilegeSet@@QEAA@PEAUISWbemPrivilegeSet@@@Z; CSWbemPrivilegeSet::CSWbemPrivilegeSet(ISWbemPrivilegeSet *)
0x18001e702  jmp     short loc_18001E707
0x18001e704  mov     rax, r14
0x18001e707  mov     [rbx+20h], rax
0x18001e70b  mov     [rbp+bstrString], r14
0x18001e70f  mov     [rbp+arg_18], r14
0x18001e713  mov     [rbp+var_40], r14
0x18001e717  mov     [rbp+var_38], r14
0x18001e71b  mov     [rbp+var_30], r14
0x18001e71f  mov     rax, [rdi]
0x18001e722  lea     rdx, [rbp+bstrString]
0x18001e726  mov     rcx, rdi
0x18001e729  mov     rax, [rax+18h]
0x18001e72d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e732  mov     rax, [rdi]
0x18001e735  lea     rdx, [rbp+arg_18]
0x18001e739  mov     rcx, rdi
0x18001e73c  mov     rax, [rax+28h]
0x18001e740  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e745  mov     rax, [rdi]
0x18001e748  lea     r9, [rbp+var_30]
0x18001e74c  lea     r8, [rbp+var_38]
0x18001e750  lea     rdx, [rbp+var_40]
0x18001e754  mov     rcx, rdi
0x18001e757  mov     rax, [rax+20h]
0x18001e75b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e760  mov     rdi, r14
0x18001e763  mov     qword ptr [rbp+var_10.Data1], r14
0x18001e767  mov     rdx, [rbp+var_38]; unsigned __int16 *
0x18001e76b  mov     r8, [rbp+var_30]; unsigned __int16 *
0x18001e76f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001e773  mov     r10, [rbp+var_40]
0x18001e777  test    r10, r10
0x18001e77a  jz      short loc_18001E78E
0x18001e77c  mov     rcx, rax
0x18001e77f  inc     rcx
0x18001e782  cmp     [r10+rcx*2], r14w
0x18001e787  jnz     short loc_18001E77F
0x18001e789  test    rcx, rcx
0x18001e78c  jnz     short loc_18001E7B9
0x18001e78e  test    rdx, rdx
0x18001e791  jz      short loc_18001E7A5
0x18001e793  mov     rcx, rax
0x18001e796  inc     rcx
0x18001e799  cmp     [rdx+rcx*2], r14w
0x18001e79e  jnz     short loc_18001E796
0x18001e7a0  test    rcx, rcx
0x18001e7a3  jnz     short loc_18001E7B9
0x18001e7a5  test    r8, r8
0x18001e7a8  jz      short loc_18001E7C9
0x18001e7aa  inc     rax
0x18001e7ad  cmp     [r8+rax*2], r14w
0x18001e7b2  jnz     short loc_18001E7AA
0x18001e7b4  test    rax, rax
0x18001e7b7  jz      short loc_18001E7C9
0x18001e7b9  lea     r9, [rbp+var_10]; struct _COAUTHIDENTITY **
0x18001e7bd  mov     rcx, r10; unsigned __int16 *
0x18001e7c0  call    ?WbemAllocAuthIdentity@@YAJPEBG00PEAPEAU_COAUTHIDENTITY@@@Z; WbemAllocAuthIdentity(ushort const *,ushort const *,ushort const *,_COAUTHIDENTITY * *)
0x18001e7c5  mov     rdi, qword ptr [rbp+var_10.Data1]
0x18001e7c9  mov     ecx, 150h
0x18001e7ce  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18001e7d4  mov     qword ptr [rbp+var_10.Data1], rax
0x18001e7d8  test    rax, rax
0x18001e7db  jz      short loc_18001E7FA
0x18001e7dd  mov     rcx, [rbp+bstrString]
0x18001e7e1  mov     [rsp+70h+psz], rcx; unsigned __int16 *
0x18001e7e6  mov     r9, [rbp+arg_18]; unsigned __int16 *
0x18001e7ea  mov     r8, rdi; struct _COAUTHIDENTITY *
0x18001e7ed  mov     rdx, rsi; struct IUnknown *
0x18001e7f0  mov     rcx, rax; this
0x18001e7f3  call    ??0CSWbemProxyCache@@QEAA@PEAUIUnknown@@PEAU_COAUTHIDENTITY@@PEAG2@Z; CSWbemProxyCache::CSWbemProxyCache(IUnknown *,_COAUTHIDENTITY *,ushort *,ushort *)
0x18001e7f8  jmp     short loc_18001E7FD
0x18001e7fa  mov     rax, r14
0x18001e7fd  mov     [rbx+78h], rax
0x18001e801  test    rdi, rdi
0x18001e804  jz      short loc_18001E80E
0x18001e806  mov     rcx, rdi; pv
0x18001e809  call    ?WbemFreeAuthIdentity@@YAJPEAU_COAUTHIDENTITY@@@Z; WbemFreeAuthIdentity(_COAUTHIDENTITY *)
0x18001e80e  mov     rcx, [rbp+bstrString]; bstrString
0x18001e812  test    rcx, rcx
0x18001e815  jz      short loc_18001E81D
0x18001e817  call    cs:__imp_SysFreeString
0x18001e81d  mov     rcx, [rbp+arg_18]; bstrString
0x18001e821  test    rcx, rcx
0x18001e824  jz      short loc_18001E82C
0x18001e826  call    cs:__imp_SysFreeString
0x18001e82c  mov     rcx, [rbp+var_40]; bstrString
0x18001e830  test    rcx, rcx
0x18001e833  jz      short loc_18001E83B
0x18001e835  call    cs:__imp_SysFreeString
0x18001e83b  mov     rcx, [rbp+var_38]; bstrString
0x18001e83f  test    rcx, rcx
0x18001e842  jz      short loc_18001E84A
0x18001e844  call    cs:__imp_SysFreeString
0x18001e84a  mov     rcx, [rbp+var_30]; bstrString
0x18001e84e  test    rcx, rcx
0x18001e851  jz      short loc_18001E859
0x18001e853  call    cs:__imp_SysFreeString
0x18001e859  mov     rcx, [rbx+78h]; this
0x18001e85d  test    rcx, rcx
0x18001e860  jz      short loc_18001E87E
0x18001e862  xor     r9d, r9d; bool
0x18001e865  mov     r8d, [rcx+148h]; enum WbemImpersonationLevelEnum
0x18001e86c  mov     edx, [rcx+144h]; enum WbemAuthenticationLevelEnum
0x18001e872  call    ?GetProxy@CSWbemProxyCache@@QEAAPEAUIUnknown@@W4WbemAuthenticationLevelEnum@@W4WbemImpersonationLevelEnum@@_N@Z; CSWbemProxyCache::GetProxy(WbemAuthenticationLevelEnum,WbemImpersonationLevelEnum,bool)
0x18001e877  mov     [rbx+80h], rax
0x18001e87e  mov     rcx, [rbp+var_28]
0x18001e882  mov     rax, [rcx]
0x18001e885  mov     rax, [rax+10h]
0x18001e889  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e88e  mov     rcx, qword ptr [rbp+var_20.Data1]
0x18001e892  mov     rax, [rcx]
0x18001e895  mov     rax, [rax+10h]
0x18001e899  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e89e  lock inc cs:?g_cObj@@3JA; long g_cObj
0x18001e8a5  mov     rax, rbx
0x18001e8a8  add     rsp, 70h
0x18001e8ac  pop     r14
0x18001e8ae  pop     rdi
0x18001e8af  pop     rsi
0x18001e8b0  pop     rbx
0x18001e8b1  pop     rbp
0x18001e8b2  retn
```
