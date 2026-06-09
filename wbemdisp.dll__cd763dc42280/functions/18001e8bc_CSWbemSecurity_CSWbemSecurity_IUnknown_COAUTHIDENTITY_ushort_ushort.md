# CSWbemSecurity::CSWbemSecurity(IUnknown *,_COAUTHIDENTITY *,ushort *,ushort *)

- ea: `0x18001e8bc`
- end: `0x18001ea22`
- name: `??0CSWbemSecurity@@QEAA@PEAUIUnknown@@PEAU_COAUTHIDENTITY@@PEAG2@Z`
- size: `358`
- prototype: `CSWbemSecurity *__fastcall(struct IDispatch *this, struct IUnknown *, struct _COAUTHIDENTITY *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18001d064`

## callees

- `0x180006710`
- `0x18000fd64`
- `0x1800126c0`
- `0x18001cc78`
- `0x18001e8bc`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001e996`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001e9f2`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001e996`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001e9f2`

## string_xrefs

- `0x18001e96c`: `SWbemSecurity`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct IDispatch *__fastcall CSWbemSecurity::CSWbemSecurity(
        struct IDispatch *this,
        struct IUnknown *a2,
        struct _COAUTHIDENTITY *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5)
{
  struct IDispatch *v9; // rcx
  CSWbemProxyCache *v10; // rax
  CSWbemPrivilegeSet *v11; // rax
  GUID v13; // [rsp+30h] [rbp-48h] BYREF
  GUID v14; // [rsp+40h] [rbp-38h] BYREF

  this->lpVtbl = (struct IDispatchVtbl *)&CSWbemSecurity::`vftable'{for `ISWbemSecurity'};
  this[1].lpVtbl = (struct IDispatchVtbl *)&CSWbemSecurity::`vftable'{for `ISupportErrorInfo'};
  this[2].lpVtbl = (struct IDispatchVtbl *)&CSWbemSecurity::`vftable'{for `ISWbemInternalSecurity'};
  this[3].lpVtbl = (struct IDispatchVtbl *)&CSWbemSecurity::`vftable'{for `IProvideClassInfo'};
  this[4].lpVtbl = 0;
  v9 = this + 5;
  v9->lpVtbl = (struct IDispatchVtbl *)&CDispatchHelp::`vftable';
  v9[3].lpVtbl = 0;
  v9[4].lpVtbl = 0;
  v9[5].lpVtbl = 0;
  v9[1].lpVtbl = 0;
  LODWORD(v9[2].lpVtbl) = 0;
  this[15].lpVtbl = 0;
  this[16].lpVtbl = 0;
  v13 = CLSID_SWbemSecurity;
  v14 = IID_ISWbemSecurity;
  CDispatchHelp::SetObj((CDispatchHelp *)v9, this, &v14, &v13, (OLECHAR *)L"SWbemSecurity");
  LODWORD(this[17].lpVtbl) = 1;
  v10 = (CSWbemProxyCache *)CWin32DefaultArena::WbemMemAlloc(0x150u);
  *(_QWORD *)&v13.Data1 = v10;
  if ( v10 )
    v10 = CSWbemProxyCache::CSWbemProxyCache(v10, a2, a3, a4, a5);
  this[15].lpVtbl = (struct IDispatchVtbl *)v10;
  if ( v10 )
    this[16].lpVtbl = (struct IDispatchVtbl *)CSWbemProxyCache::GetProxy(
                                                v10,
                                                (enum WbemAuthenticationLevelEnum)*((_DWORD *)v10 + 81),
                                                (enum WbemImpersonationLevelEnum)*((_DWORD *)v10 + 82),
                                                0);
  v11 = (CSWbemPrivilegeSet *)CWin32DefaultArena::WbemMemAlloc(0x88u);
  *(_QWORD *)&v13.Data1 = v11;
  if ( v11 )
    v11 = CSWbemPrivilegeSet::CSWbemPrivilegeSet(v11);
  this[4].lpVtbl = (struct IDispatchVtbl *)v11;
  _InterlockedIncrement(&g_cObj);
  return this;
}

```

## disassembly

```asm
0x18001e8bc  mov     r11, rsp
0x18001e8bf  mov     [r11+8], rcx
0x18001e8c3  push    rbx
0x18001e8c4  push    rbp
0x18001e8c5  push    rsi
0x18001e8c6  push    rdi
0x18001e8c7  sub     rsp, 58h
0x18001e8cb  mov     rdi, r9
0x18001e8ce  mov     rsi, r8
0x18001e8d1  mov     rbp, rdx
0x18001e8d4  mov     rbx, rcx
0x18001e8d7  lea     rax, ??_7CSWbemSecurity@@6BISWbemSecurity@@@; const CSWbemSecurity::`vftable'{for `ISWbemSecurity'}
0x18001e8de  mov     [rcx], rax
0x18001e8e1  lea     rax, ??_7CSWbemSecurity@@6BISupportErrorInfo@@@; const CSWbemSecurity::`vftable'{for `ISupportErrorInfo'}
0x18001e8e8  mov     [rcx+8], rax
0x18001e8ec  lea     rax, ??_7CSWbemSecurity@@6BISWbemInternalSecurity@@@; const CSWbemSecurity::`vftable'{for `ISWbemInternalSecurity'}
0x18001e8f3  mov     [rcx+10h], rax
0x18001e8f7  lea     rax, ??_7CSWbemSecurity@@6BIProvideClassInfo@@@; const CSWbemSecurity::`vftable'{for `IProvideClassInfo'}
0x18001e8fe  mov     [rcx+18h], rax
0x18001e902  mov     qword ptr [rcx+20h], 0
0x18001e90a  add     rcx, 28h ; '('; this
0x18001e90e  lea     rax, ??_7CDispatchHelp@@6B@; const CDispatchHelp::`vftable'
0x18001e915  mov     [rcx], rax
0x18001e918  mov     qword ptr [rcx+18h], 0
0x18001e920  mov     qword ptr [rcx+20h], 0
0x18001e928  mov     qword ptr [rcx+28h], 0
0x18001e930  mov     qword ptr [rcx+8], 0
0x18001e938  mov     dword ptr [rcx+10h], 0
0x18001e93f  mov     qword ptr [rbx+78h], 0
0x18001e947  mov     qword ptr [rbx+80h], 0
0x18001e952  movups  xmm0, xmmword ptr cs:CLSID_SWbemSecurity.Data1
0x18001e959  movdqu  [rsp+78h+var_48], xmm0
0x18001e95f  movups  xmm1, xmmword ptr cs:IID_ISWbemSecurity.Data1
0x18001e966  movdqu  [rsp+78h+var_38], xmm1
0x18001e96c  lea     rax, aSwbemsecurity; "SWbemSecurity"
0x18001e973  mov     [r11-58h], rax
0x18001e977  lea     r9, [r11-48h]; struct _GUID *
0x18001e97b  lea     r8, [r11-38h]; struct _GUID *
0x18001e97f  mov     rdx, rbx; struct IDispatch *
0x18001e982  call    ?SetObj@CDispatchHelp@@QEAAXPEAUIDispatch@@U_GUID@@1PEAG@Z; CDispatchHelp::SetObj(IDispatch *,_GUID,_GUID,ushort *)
0x18001e987  mov     dword ptr [rbx+88h], 1
0x18001e991  mov     ecx, 150h
0x18001e996  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18001e99c  mov     qword ptr [rsp+78h+var_48], rax
0x18001e9a1  test    rax, rax
0x18001e9a4  jz      short loc_18001E9C5
0x18001e9a6  mov     rcx, [rsp+78h+arg_20]
0x18001e9ae  mov     [rsp+78h+var_58], rcx; unsigned __int16 *
0x18001e9b3  mov     r9, rdi; unsigned __int16 *
0x18001e9b6  mov     r8, rsi; struct _COAUTHIDENTITY *
0x18001e9b9  mov     rdx, rbp; struct IUnknown *
0x18001e9bc  mov     rcx, rax; this
0x18001e9bf  call    ??0CSWbemProxyCache@@QEAA@PEAUIUnknown@@PEAU_COAUTHIDENTITY@@PEAG2@Z; CSWbemProxyCache::CSWbemProxyCache(IUnknown *,_COAUTHIDENTITY *,ushort *,ushort *)
0x18001e9c4  nop
0x18001e9c5  mov     [rbx+78h], rax
0x18001e9c9  test    rax, rax
0x18001e9cc  jz      short loc_18001E9ED
0x18001e9ce  xor     r9d, r9d; bool
0x18001e9d1  mov     r8d, [rax+148h]; enum WbemImpersonationLevelEnum
0x18001e9d8  mov     edx, [rax+144h]; enum WbemAuthenticationLevelEnum
0x18001e9de  mov     rcx, rax; this
0x18001e9e1  call    ?GetProxy@CSWbemProxyCache@@QEAAPEAUIUnknown@@W4WbemAuthenticationLevelEnum@@W4WbemImpersonationLevelEnum@@_N@Z; CSWbemProxyCache::GetProxy(WbemAuthenticationLevelEnum,WbemImpersonationLevelEnum,bool)
0x18001e9e6  mov     [rbx+80h], rax
0x18001e9ed  mov     ecx, 88h
0x18001e9f2  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18001e9f8  mov     qword ptr [rsp+78h+var_48], rax
0x18001e9fd  test    rax, rax
0x18001ea00  jz      short loc_18001EA0B
0x18001ea02  mov     rcx, rax; this
0x18001ea05  call    ??0CSWbemPrivilegeSet@@QEAA@XZ; CSWbemPrivilegeSet::CSWbemPrivilegeSet(void)
0x18001ea0a  nop
0x18001ea0b  mov     [rbx+20h], rax
0x18001ea0f  lock inc cs:?g_cObj@@3JA; long g_cObj
0x18001ea16  mov     rax, rbx
0x18001ea19  add     rsp, 58h
0x18001ea1d  pop     rdi
0x18001ea1e  pop     rsi
0x18001ea1f  pop     rbp
0x18001ea20  pop     rbx
0x18001ea21  retn
```
