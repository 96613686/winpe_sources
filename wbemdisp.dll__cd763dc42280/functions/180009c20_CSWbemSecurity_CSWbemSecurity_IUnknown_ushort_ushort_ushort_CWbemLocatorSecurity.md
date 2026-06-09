# CSWbemSecurity::CSWbemSecurity(IUnknown *,ushort *,ushort *,ushort *,CWbemLocatorSecurity *)

- ea: `0x180009c20`
- end: `0x180009fbc`
- name: `??0CSWbemSecurity@@QEAA@PEAUIUnknown@@PEAG11PEAVCWbemLocatorSecurity@@@Z`
- size: `924`
- prototype: `CSWbemSecurity *(CSWbemSecurity *__hidden this, struct IUnknown *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, struct CWbemLocatorSecurity *)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180003cb0`
- `0x18000b580`

## callees

- `0x180006550`
- `0x180008de0`
- `0x180009c20`
- `0x18000a7b0`
- `0x18000b008`
- `0x18000fd64`
- `0x1800103c0`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180009cc3`
- `OLEAUT32!__imp_SysAllocString` at `0x180009d4d`
- `OLEAUT32!__imp_SysAllocString` at `0x180009d5d`
- `OLEAUT32!__imp_SysAllocString` at `0x180009d6e`
- `OLEAUT32!__imp_SysAllocString` at `0x180009cc3`
- `OLEAUT32!__imp_SysAllocString` at `0x180009d4d`
- `OLEAUT32!__imp_SysAllocString` at `0x180009d5d`
- `OLEAUT32!__imp_SysAllocString` at `0x180009d6e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009e23`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009e23`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180009d06`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180009d06`
- `wbemcomn!_ThrowMemoryException_` at `0x180009d10`
- `wbemcomn!_ThrowMemoryException_` at `0x180009d10`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180009cdc`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180009e59`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180009f96`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180009cdc`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180009e59`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180009f96`

## string_xrefs

- `0x180009cbc`: `SWbemSecurity`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
CSWbemSecurity *__fastcall CSWbemSecurity::CSWbemSecurity(
        CSWbemSecurity *this,
        struct IUnknown *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *psz,
        struct ISWbemSecurity *a6)
{
  char *v10; // rbx
  __int64 v12; // rcx
  char v13; // al
  bool v14; // al
  bool v15; // r9
  __int64 v16; // r13
  __int64 v17; // rdi
  __int64 v18; // r12
  struct IUnknown *v19; // rdi
  const struct CSWbemPrivilegeSet *lpVtbl; // rbx
  CSWbemPrivilegeSet *v21; // rax
  CSWbemPrivilegeSet *v22; // rax
  unsigned int (__fastcall ***v24)(_QWORD, GUID *, __int64 *); // r15
  struct IUnknown *v25; // rcx
  __int64 v26; // rax
  bool v27; // zf
  CSWbemPrivilegeSet *v28; // rax
  CSWbemPrivilegeSet *v29; // rax
  struct IUnknown *v30; // [rsp+30h] [rbp-28h] BYREF
  __int64 v31; // [rsp+38h] [rbp-20h] BYREF
  LPCRITICAL_SECTION lpCriticalSection[3]; // [rsp+40h] [rbp-18h] BYREF
  enum WbemAuthenticationLevelEnum v33; // [rsp+C8h] [rbp+70h]

  *(_QWORD *)this = &CSWbemSecurity::`vftable'{for `ISWbemSecurity'};
  *((_QWORD *)this + 1) = &CSWbemSecurity::`vftable'{for `ISupportErrorInfo'};
  *((_QWORD *)this + 2) = &CSWbemSecurity::`vftable'{for `ISWbemInternalSecurity'};
  *((_QWORD *)this + 3) = &CSWbemSecurity::`vftable'{for `IProvideClassInfo'};
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = &CDispatchHelp::`vftable';
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_DWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 10) = this;
  *(GUID *)((char *)this + 88) = IID_ISWbemSecurity;
  *(GUID *)((char *)this + 104) = CLSID_SWbemSecurity;
  *((_QWORD *)this + 6) = SysAllocString(L"SWbemSecurity");
  *((_DWORD *)this + 34) = 1;
  v10 = (char *)CWin32DefaultArena::WbemMemAlloc(0x150u);
  lpCriticalSection[0] = (LPCRITICAL_SECTION)v10;
  if ( v10 )
  {
    *(_QWORD *)v10 = &CSWbemProxyCache::`vftable';
    if ( !InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)(v10 + 16), 0) )
      _ThrowMemoryException_();
    *((_DWORD *)v10 + 2) = 1;
    *((_QWORD *)v10 + 35) = 0;
    *((_QWORD *)v10 + 36) = 0;
    *((_QWORD *)v10 + 37) = 0;
    *((_QWORD *)v10 + 38) = 0;
    *((_QWORD *)v10 + 39) = 0;
    *((_WORD *)v10 + 160) = 1;
    *((_QWORD *)v10 + 38) = SysAllocString(a4);
    *((_QWORD *)v10 + 37) = SysAllocString(a3);
    *((_QWORD *)v10 + 39) = SysAllocString(psz);
    v12 = *((_QWORD *)v10 + 38);
    if ( !v12 )
      goto LABEL_5;
    v26 = -1;
    do
      ++v26;
    while ( *(_WORD *)(v12 + 2 * v26) );
    v27 = v26 == 0;
    v13 = 1;
    if ( v27 )
LABEL_5:
      v13 = 0;
    v10[321] = v13;
    if ( a6 && LOBYTE(a6[14].lpVtbl) )
    {
      v14 = 1;
    }
    else
    {
      v14 = 0;
      if ( !a6 )
      {
LABEL_8:
        v15 = 0;
LABEL_9:
        CSWbemProxyCache::InitializeCache((CSWbemProxyCache *)v10, a2, a6, v15, v14);
        CSWbemProxyCache::ClearCredentials((CSWbemProxyCache *)v10);
        goto LABEL_10;
      }
    }
    v15 = 1;
    if ( LOBYTE(a6[15].lpVtbl) )
      goto LABEL_9;
    goto LABEL_8;
  }
  v10 = 0;
LABEL_10:
  *((_QWORD *)this + 15) = v10;
  if ( !v10 )
    goto LABEL_15;
  v16 = *((int *)v10 + 82);
  v17 = *((int *)v10 + 81);
  v33 = *((_DWORD *)v10 + 81);
  CInCritSec::CInCritSec((CInCritSec *)lpCriticalSection, (struct _RTL_CRITICAL_SECTION *)(v10 + 16));
  v18 = v16 + 4 * v17;
  v19 = *(struct IUnknown **)&v10[8 * v18 + 48];
  v30 = v19;
  if ( v19 )
  {
    ((void (__fastcall *)(struct IUnknown *))v19->lpVtbl->AddRef)(v19);
  }
  else
  {
    v24 = *(unsigned int (__fastcall ****)(_QWORD, GUID *, __int64 *))&v10[32 * *((int *)v10 + 81)
                                                                         + 48
                                                                         + 8 * *((int *)v10 + 82)];
    if ( !v24 )
      goto LABEL_14;
    v31 = 0;
    if ( !(**v24)(v24, &IID_IClientSecurity, &v31) )
    {
      if ( !(*(unsigned int (__fastcall **)(__int64, _QWORD, struct IUnknown **))(*(_QWORD *)v31 + 40LL))(
              v31,
              v24,
              &v30) )
      {
        CSWbemProxyCache::SecureProxy((CSWbemProxyCache *)v10, v30, v33, (enum WbemImpersonationLevelEnum)v16);
        v25 = v30;
        *(_QWORD *)&v10[8 * v18 + 48] = v30;
        ((void (__fastcall *)(struct IUnknown *))v25->lpVtbl->AddRef)(v25);
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    }
  }
  v19 = v30;
LABEL_14:
  LeaveCriticalSection(lpCriticalSection[0]);
  *((_QWORD *)this + 16) = v19;
LABEL_15:
  if ( a6 )
  {
    lpVtbl = (const struct CSWbemPrivilegeSet *)a6[3].lpVtbl;
    if ( lpVtbl )
    {
      (*(void (__fastcall **)(struct ISWbemSecurityVtbl *))(*(_QWORD *)lpVtbl + 8LL))(a6[3].lpVtbl);
      v21 = (CSWbemPrivilegeSet *)CWin32DefaultArena::WbemMemAlloc(0x88u);
      if ( v21 )
        v22 = CSWbemPrivilegeSet::CSWbemPrivilegeSet(v21, lpVtbl, 1);
      else
        v22 = 0;
      *((_QWORD *)this + 4) = v22;
      (*(void (__fastcall **)(const struct CSWbemPrivilegeSet *))(*(_QWORD *)lpVtbl + 16LL))(lpVtbl);
    }
  }
  else
  {
    v28 = (CSWbemPrivilegeSet *)CWin32DefaultArena::WbemMemAlloc(0x88u);
    if ( v28 )
      v29 = CSWbemPrivilegeSet::CSWbemPrivilegeSet(v28);
    else
      v29 = 0;
    *((_QWORD *)this + 4) = v29;
  }
  _InterlockedIncrement(&g_cObj);
  return this;
}

```

## disassembly

```asm
0x180009c20  mov     [rsp-40h+arg_0], rcx
0x180009c25  push    rbp
0x180009c26  push    rbx
0x180009c27  push    rsi
0x180009c28  push    rdi
0x180009c29  push    r12
0x180009c2b  push    r13
0x180009c2d  push    r14
0x180009c2f  push    r15
0x180009c31  mov     rbp, rsp
0x180009c34  sub     rsp, 58h
0x180009c38  mov     rdi, r9
0x180009c3b  mov     r15, r8
0x180009c3e  mov     r12, rdx
0x180009c41  mov     rsi, rcx
0x180009c44  lea     rax, ??_7CSWbemSecurity@@6BISWbemSecurity@@@; const CSWbemSecurity::`vftable'{for `ISWbemSecurity'}
0x180009c4b  mov     [rcx], rax
0x180009c4e  lea     rax, ??_7CSWbemSecurity@@6BISupportErrorInfo@@@; const CSWbemSecurity::`vftable'{for `ISupportErrorInfo'}
0x180009c55  mov     [rcx+8], rax
0x180009c59  lea     rax, ??_7CSWbemSecurity@@6BISWbemInternalSecurity@@@; const CSWbemSecurity::`vftable'{for `ISWbemInternalSecurity'}
0x180009c60  mov     [rcx+10h], rax
0x180009c64  lea     rax, ??_7CSWbemSecurity@@6BIProvideClassInfo@@@; const CSWbemSecurity::`vftable'{for `IProvideClassInfo'}
0x180009c6b  mov     [rcx+18h], rax
0x180009c6f  xor     r13d, r13d
0x180009c72  mov     [rcx+20h], r13
0x180009c76  lea     rax, ??_7CDispatchHelp@@6B@; const CDispatchHelp::`vftable'
0x180009c7d  mov     [rcx+28h], rax
0x180009c81  mov     [rcx+40h], r13
0x180009c85  mov     [rcx+48h], r13
0x180009c89  mov     [rcx+50h], r13
0x180009c8d  mov     [rcx+30h], r13
0x180009c91  mov     [rcx+38h], r13d
0x180009c95  mov     [rcx+78h], r13
0x180009c99  mov     [rcx+80h], r13
0x180009ca0  movups  xmm1, xmmword ptr cs:CLSID_SWbemSecurity.Data1
0x180009ca7  movups  xmm0, xmmword ptr cs:IID_ISWbemSecurity.Data1
0x180009cae  mov     [rcx+50h], rcx
0x180009cb2  movdqu  xmmword ptr [rcx+58h], xmm0
0x180009cb7  movdqu  xmmword ptr [rcx+68h], xmm1
0x180009cbc  lea     rcx, aSwbemsecurity; "SWbemSecurity"
0x180009cc3  call    cs:__imp_SysAllocString
0x180009cc9  mov     [rsi+30h], rax
0x180009ccd  mov     dword ptr [rsi+88h], 1
0x180009cd7  mov     ecx, 150h
0x180009cdc  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180009ce2  mov     rbx, rax
0x180009ce5  mov     [rbp+lpCriticalSection], rax
0x180009ce9  mov     r14, qword ptr [rbp+arg_28]
0x180009ced  test    rax, rax
0x180009cf0  jz      loc_180009F6B
0x180009cf6  lea     rax, ??_7CSWbemProxyCache@@6B@; const CSWbemProxyCache::`vftable'
0x180009cfd  mov     [rbx], rax
0x180009d00  lea     rcx, [rbx+10h]; lpCriticalSection
0x180009d04  xor     edx, edx; dwSpinCount
0x180009d06  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180009d0c  test    eax, eax
0x180009d0e  jnz     short loc_180009D17
0x180009d10  call    cs:__imp_?_ThrowMemoryException_@@YAXXZ; _ThrowMemoryException_(void)
0x180009d16  nop
0x180009d17  mov     dword ptr [rbx+8], 1
0x180009d1e  mov     [rbx+118h], r13
0x180009d25  mov     [rbx+120h], r13
0x180009d2c  mov     [rbx+128h], r13
0x180009d33  mov     [rbx+130h], r13
0x180009d3a  mov     [rbx+138h], r13
0x180009d41  mov     word ptr [rbx+140h], 1
0x180009d4a  mov     rcx, rdi; psz
0x180009d4d  call    cs:__imp_SysAllocString
0x180009d53  mov     [rbx+130h], rax
0x180009d5a  mov     rcx, r15; psz
0x180009d5d  call    cs:__imp_SysAllocString
0x180009d63  mov     [rbx+128h], rax
0x180009d6a  mov     rcx, [rbp+psz]; psz
0x180009d6e  call    cs:__imp_SysAllocString
0x180009d74  mov     [rbx+138h], rax
0x180009d7b  mov     rcx, [rbx+130h]
0x180009d82  test    rcx, rcx
0x180009d85  jnz     loc_180009F73
0x180009d8b  mov     al, r13b
0x180009d8e  mov     [rbx+141h], al
0x180009d94  test    r14, r14
0x180009d97  jnz     loc_180009EA9
0x180009d9d  mov     al, r13b
0x180009da0  test    r14, r14
0x180009da3  jnz     loc_180009EB5
0x180009da9  mov     r9b, r13b; bool
0x180009dac  mov     [rsp+58h+var_38], al; bool
0x180009db0  mov     r8, r14; struct ISWbemSecurity *
0x180009db3  mov     rdx, r12; struct IUnknown *
0x180009db6  mov     rcx, rbx; this
0x180009db9  call    ?InitializeCache@CSWbemProxyCache@@AEAAXPEAUIUnknown@@PEAUISWbemSecurity@@_N2@Z; CSWbemProxyCache::InitializeCache(IUnknown *,ISWbemSecurity *,bool,bool)
0x180009dbe  mov     rcx, rbx; this
0x180009dc1  call    ?ClearCredentials@CSWbemProxyCache@@AEAAXXZ; CSWbemProxyCache::ClearCredentials(void)
0x180009dc6  nop
0x180009dc7  mov     [rsi+78h], rbx
0x180009dcb  test    rbx, rbx
0x180009dce  jz      short loc_180009E33
0x180009dd0  movsxd  r13, dword ptr [rbx+148h]
0x180009dd7  movsxd  rdi, dword ptr [rbx+144h]
0x180009dde  mov     [rbp+arg_28], edi
0x180009de1  lea     rdx, [rbx+10h]; struct _RTL_CRITICAL_SECTION *
0x180009de5  lea     rcx, [rbp+lpCriticalSection]; this
0x180009de9  call    ??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x180009dee  nop
0x180009def  lea     r12, ds:0[rdi*4]
0x180009df7  add     r12, r13
0x180009dfa  mov     rdi, [rbx+r12*8+30h]
0x180009dff  mov     [rbp+var_28], rdi
0x180009e03  test    rdi, rdi
0x180009e06  jz      loc_180009EC7
0x180009e0c  mov     rax, [rdi]
0x180009e0f  mov     rcx, rdi
0x180009e12  mov     rax, [rax+8]
0x180009e16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e1b  mov     rdi, [rbp+var_28]
0x180009e1f  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x180009e23  call    cs:__imp_LeaveCriticalSection
0x180009e29  mov     [rsi+80h], rdi
0x180009e30  xor     r13d, r13d
0x180009e33  test    r14, r14
0x180009e36  jz      loc_180009F91
0x180009e3c  mov     rbx, [r14+18h]
0x180009e40  test    rbx, rbx
0x180009e43  jz      short loc_180009E8E
0x180009e45  mov     rax, [rbx]
0x180009e48  mov     rcx, rbx
0x180009e4b  mov     rax, [rax+8]
0x180009e4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e54  mov     ecx, 88h
0x180009e59  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180009e5f  mov     qword ptr [rbp+arg_28], rax
0x180009e63  test    rax, rax
0x180009e66  jz      loc_180009F63
0x180009e6c  mov     r8b, 1; bool
0x180009e6f  mov     rdx, rbx; struct CSWbemPrivilegeSet *
0x180009e72  mov     rcx, rax; this
0x180009e75  call    ??0CSWbemPrivilegeSet@@QEAA@AEBV0@_N@Z; CSWbemPrivilegeSet::CSWbemPrivilegeSet(CSWbemPrivilegeSet const &,bool)
0x180009e7a  nop
0x180009e7b  mov     [rsi+20h], rax
0x180009e7f  mov     rax, [rbx]
0x180009e82  mov     rcx, rbx
0x180009e85  mov     rax, [rax+10h]
0x180009e89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e8e  lock inc cs:?g_cObj@@3JA; long g_cObj
0x180009e95  mov     rax, rsi
0x180009e98  add     rsp, 58h
0x180009e9c  pop     r15
0x180009e9e  pop     r14
0x180009ea0  pop     r13
0x180009ea2  pop     r12
0x180009ea4  pop     rdi
0x180009ea5  pop     rsi
0x180009ea6  pop     rbx
0x180009ea7  pop     rbp
0x180009ea8  retn
0x180009ea9  cmp     [r14+70h], r13b
0x180009ead  jz      loc_180009D9D
0x180009eb3  mov     al, 1
0x180009eb5  cmp     [r14+78h], r13b
0x180009eb9  mov     r9b, 1
0x180009ebc  jnz     loc_180009DAC
0x180009ec2  jmp     loc_180009DA9
0x180009ec7  movsxd  rcx, dword ptr [rbx+144h]
0x180009ece  movsxd  rax, dword ptr [rbx+148h]
0x180009ed5  lea     rcx, [rax+rcx*4]
0x180009ed9  mov     r15, [rbx+rcx*8+30h]
0x180009ede  test    r15, r15
0x180009ee1  jz      loc_180009E1F
0x180009ee7  mov     [rbp+var_20], 0
0x180009eef  mov     rax, [r15]
0x180009ef2  lea     r8, [rbp+var_20]
0x180009ef6  lea     rdx, IID_IClientSecurity
0x180009efd  mov     rcx, r15
0x180009f00  mov     rax, [rax]
0x180009f03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f08  test    eax, eax
0x180009f0a  jnz     loc_180009E1B
0x180009f10  mov     rcx, [rbp+var_20]
0x180009f14  mov     rax, [rcx]
0x180009f17  lea     r8, [rbp+var_28]
0x180009f1b  mov     rdx, r15
0x180009f1e  mov     rax, [rax+28h]
0x180009f22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f27  test    eax, eax
0x180009f29  jnz     short loc_180009F53
0x180009f2b  mov     r9d, r13d; enum WbemImpersonationLevelEnum
0x180009f2e  mov     r8d, [rbp+arg_28]; enum WbemAuthenticationLevelEnum
0x180009f32  mov     rdx, [rbp+var_28]; struct IUnknown *
0x180009f36  mov     rcx, rbx; this
0x180009f39  call    ?SecureProxy@CSWbemProxyCache@@QEAAXPEAUIUnknown@@W4WbemAuthenticationLevelEnum@@W4WbemImpersonationLevelEnum@@@Z; CSWbemProxyCache::SecureProxy(IUnknown *,WbemAuthenticationLevelEnum,WbemImpersonationLevelEnum)
0x180009f3e  mov     rcx, [rbp+var_28]
0x180009f42  mov     [rbx+r12*8+30h], rcx
0x180009f47  mov     rax, [rcx]
0x180009f4a  mov     rax, [rax+8]
0x180009f4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f53  mov     rcx, [rbp+var_20]
0x180009f57  mov     rax, [rcx]
0x180009f5a  mov     rax, [rax+10h]
0x180009f5e  jmp     loc_180009E16
0x180009f63  mov     rax, r13
0x180009f66  jmp     loc_180009E7B
0x180009f6b  mov     rbx, r13
0x180009f6e  jmp     loc_180009DC7
0x180009f73  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009f77  inc     rax
0x180009f7a  cmp     [rcx+rax*2], r13w
0x180009f7f  jnz     short loc_180009F77
0x180009f81  test    rax, rax
0x180009f84  mov     al, 1
0x180009f86  jnz     loc_180009D8E
0x180009f8c  jmp     loc_180009D8B
0x180009f91  mov     ecx, 88h
0x180009f96  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180009f9c  mov     qword ptr [rbp+arg_28], rax
0x180009fa0  test    rax, rax
0x180009fa3  jz      short loc_180009FAF
0x180009fa5  mov     rcx, rax; this
0x180009fa8  call    ??0CSWbemPrivilegeSet@@QEAA@XZ; CSWbemPrivilegeSet::CSWbemPrivilegeSet(void)
0x180009fad  jmp     short loc_180009FB2
0x180009faf  mov     rax, r13
0x180009fb2  mov     [rsi+20h], rax
0x180009fb6  jmp     loc_180009E8E
```
