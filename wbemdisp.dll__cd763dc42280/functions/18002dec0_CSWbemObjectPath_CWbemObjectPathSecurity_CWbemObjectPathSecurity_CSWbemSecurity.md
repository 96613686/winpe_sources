# CSWbemObjectPath::CWbemObjectPathSecurity::CWbemObjectPathSecurity(CSWbemSecurity *)

- ea: `0x18002dec0`
- end: `0x18002e051`
- name: `??0CWbemObjectPathSecurity@CSWbemObjectPath@@QEAA@PEAVCSWbemSecurity@@@Z`
- size: `401`
- prototype: `__int64 __fastcall(struct IDispatch *this, struct CSWbemSecurity *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800112fc`

## callees

- `0x18000d950`
- `0x18000fd64`
- `0x1800103c0`
- `0x1800126c0`
- `0x18002dec0`
- `0x180036010`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18002df97`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18002dfcb`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18002e015`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18002df97`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18002dfcb`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18002e015`

## string_xrefs

- `0x18002df5e`: `SWbemSecurity`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct IDispatch *__fastcall CSWbemObjectPath::CWbemObjectPathSecurity::CWbemObjectPathSecurity(
        struct IDispatch *this,
        struct CSWbemSecurity *a2)
{
  struct IDispatch *v4; // rcx
  char v5; // di
  const struct CSWbemPrivilegeSet *PrivilegeSet; // rsi
  CSWbemPrivilegeSet *v7; // rax
  CSWbemPrivilegeSet *v8; // rax
  CSWbemPrivilegeSet *v9; // rax
  GUID v11; // [rsp+30h] [rbp-38h] BYREF
  GUID v12; // [rsp+40h] [rbp-28h] BYREF

  this->lpVtbl = (struct IDispatchVtbl *)&CSWbemObjectPath::CWbemObjectPathSecurity::`vftable'{for `ISWbemSecurity'};
  this[1].lpVtbl = (struct IDispatchVtbl *)&CSWbemObjectPath::CWbemObjectPathSecurity::`vftable'{for `ISupportErrorInfo'};
  this[2].lpVtbl = (struct IDispatchVtbl *)&CSWbemObjectPath::CWbemObjectPathSecurity::`vftable'{for `IProvideClassInfo'};
  v4 = this + 3;
  v4->lpVtbl = (struct IDispatchVtbl *)&CDispatchHelp::`vftable';
  v4[3].lpVtbl = 0;
  v4[4].lpVtbl = 0;
  v4[5].lpVtbl = 0;
  v4[1].lpVtbl = 0;
  LODWORD(v4[2].lpVtbl) = 0;
  v5 = 1;
  LODWORD(this[13].lpVtbl) = 1;
  WORD2(this[13].lpVtbl) = 0;
  this[15].lpVtbl = 0;
  v11 = CLSID_SWbemSecurity;
  v12 = IID_ISWbemSecurity;
  CDispatchHelp::SetObj((CDispatchHelp *)v4, this, &v12, &v11, (OLECHAR *)L"SWbemSecurity");
  if ( a2 )
  {
    PrivilegeSet = CSWbemSecurity::GetPrivilegeSet(a2);
    if ( PrivilegeSet )
    {
      v7 = (CSWbemPrivilegeSet *)CWin32DefaultArena::WbemMemAlloc(0x88u);
      if ( v7 )
        v7 = CSWbemPrivilegeSet::CSWbemPrivilegeSet(v7, PrivilegeSet, 1);
      this[15].lpVtbl = (struct IDispatchVtbl *)v7;
      (*(void (__fastcall **)(const struct CSWbemPrivilegeSet *))(*(_QWORD *)PrivilegeSet + 16LL))(PrivilegeSet);
    }
    else
    {
      v8 = (CSWbemPrivilegeSet *)CWin32DefaultArena::WbemMemAlloc(0x88u);
      if ( v8 )
        v8 = CSWbemPrivilegeSet::CSWbemPrivilegeSet(v8);
      this[15].lpVtbl = (struct IDispatchVtbl *)v8;
    }
    (*(void (__fastcall **)(struct CSWbemSecurity *, struct IDispatch *))(*(_QWORD *)a2 + 72LL))(a2, this + 14);
    (*(void (__fastcall **)(struct CSWbemSecurity *, char *))(*(_QWORD *)a2 + 56LL))(a2, (char *)&this[14].lpVtbl + 4);
  }
  else
  {
    v9 = (CSWbemPrivilegeSet *)CWin32DefaultArena::WbemMemAlloc(0x88u);
    if ( v9 )
      v9 = CSWbemPrivilegeSet::CSWbemPrivilegeSet(v9);
    this[15].lpVtbl = (struct IDispatchVtbl *)v9;
    v5 = 0;
  }
  BYTE4(this[13].lpVtbl) = v5;
  BYTE5(this[13].lpVtbl) = v5;
  return this;
}

```

## disassembly

```asm
0x18002dec0  mov     r11, rsp
0x18002dec3  mov     [r11+18h], rbx
0x18002dec7  mov     [r11+8], rcx
0x18002decb  push    rsi
0x18002decc  push    rdi
0x18002decd  push    r14
0x18002decf  sub     rsp, 50h
0x18002ded3  mov     r14, rdx
0x18002ded6  mov     rbx, rcx
0x18002ded9  lea     rax, ??_7CWbemObjectPathSecurity@CSWbemObjectPath@@6BISWbemSecurity@@@; const CSWbemObjectPath::CWbemObjectPathSecurity::`vftable'{for `ISWbemSecurity'}
0x18002dee0  mov     [rcx], rax
0x18002dee3  lea     rax, ??_7CWbemObjectPathSecurity@CSWbemObjectPath@@6BISupportErrorInfo@@@; const CSWbemObjectPath::CWbemObjectPathSecurity::`vftable'{for `ISupportErrorInfo'}
0x18002deea  mov     [rcx+8], rax
0x18002deee  lea     rax, ??_7CWbemObjectPathSecurity@CSWbemObjectPath@@6BIProvideClassInfo@@@; const CSWbemObjectPath::CWbemObjectPathSecurity::`vftable'{for `IProvideClassInfo'}
0x18002def5  mov     [rcx+10h], rax
0x18002def9  add     rcx, 18h; this
0x18002defd  lea     rax, ??_7CDispatchHelp@@6B@; const CDispatchHelp::`vftable'
0x18002df04  mov     [rcx], rax
0x18002df07  mov     qword ptr [rcx+18h], 0
0x18002df0f  mov     qword ptr [rcx+20h], 0
0x18002df17  mov     qword ptr [rcx+28h], 0
0x18002df1f  mov     qword ptr [rcx+8], 0
0x18002df27  mov     dword ptr [rcx+10h], 0
0x18002df2e  mov     edi, 1
0x18002df33  mov     [rbx+68h], edi
0x18002df36  mov     word ptr [rbx+6Ch], 0
0x18002df3c  mov     qword ptr [rbx+78h], 0
0x18002df44  movups  xmm0, xmmword ptr cs:CLSID_SWbemSecurity.Data1
0x18002df4b  movdqu  [rsp+68h+var_38], xmm0
0x18002df51  movups  xmm1, xmmword ptr cs:IID_ISWbemSecurity.Data1
0x18002df58  movdqu  [rsp+68h+var_28], xmm1
0x18002df5e  lea     rax, aSwbemsecurity; "SWbemSecurity"
0x18002df65  mov     [r11-48h], rax
0x18002df69  lea     r9, [r11-38h]; struct _GUID *
0x18002df6d  lea     r8, [r11-28h]; struct _GUID *
0x18002df71  mov     rdx, rbx; struct IDispatch *
0x18002df74  call    ?SetObj@CDispatchHelp@@QEAAXPEAUIDispatch@@U_GUID@@1PEAG@Z; CDispatchHelp::SetObj(IDispatch *,_GUID,_GUID,ushort *)
0x18002df79  test    r14, r14
0x18002df7c  jz      loc_18002E010
0x18002df82  mov     rcx, r14; this
0x18002df85  call    ?GetPrivilegeSet@CSWbemSecurity@@QEAAPEAVCSWbemPrivilegeSet@@XZ; CSWbemSecurity::GetPrivilegeSet(void)
0x18002df8a  mov     rsi, rax
0x18002df8d  mov     ecx, 88h
0x18002df92  test    rax, rax
0x18002df95  jz      short loc_18002DFCB
0x18002df97  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18002df9d  mov     [rsp+68h+arg_8], rax
0x18002dfa2  test    rax, rax
0x18002dfa5  jz      short loc_18002DFB6
0x18002dfa7  mov     r8b, dil; bool
0x18002dfaa  mov     rdx, rsi; struct CSWbemPrivilegeSet *
0x18002dfad  mov     rcx, rax; this
0x18002dfb0  call    ??0CSWbemPrivilegeSet@@QEAA@AEBV0@_N@Z; CSWbemPrivilegeSet::CSWbemPrivilegeSet(CSWbemPrivilegeSet const &,bool)
0x18002dfb5  nop
0x18002dfb6  mov     [rbx+78h], rax
0x18002dfba  mov     rax, [rsi]
0x18002dfbd  mov     rcx, rsi
0x18002dfc0  mov     rax, [rax+10h]
0x18002dfc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dfc9  jmp     short loc_18002DFE8
0x18002dfcb  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18002dfd1  mov     [rsp+68h+arg_8], rax
0x18002dfd6  test    rax, rax
0x18002dfd9  jz      short loc_18002DFE4
0x18002dfdb  mov     rcx, rax; this
0x18002dfde  call    ??0CSWbemPrivilegeSet@@QEAA@XZ; CSWbemPrivilegeSet::CSWbemPrivilegeSet(void)
0x18002dfe3  nop
0x18002dfe4  mov     [rbx+78h], rax
0x18002dfe8  mov     rax, [r14]
0x18002dfeb  lea     rdx, [rbx+70h]
0x18002dfef  mov     rcx, r14
0x18002dff2  mov     rax, [rax+48h]
0x18002dff6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dffb  mov     rax, [r14]
0x18002dffe  lea     rdx, [rbx+74h]
0x18002e002  mov     rcx, r14
0x18002e005  mov     rax, [rax+38h]
0x18002e009  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e00e  jmp     short loc_18002E035
0x18002e010  mov     ecx, 88h
0x18002e015  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18002e01b  mov     [rsp+68h+arg_8], rax
0x18002e020  test    rax, rax
0x18002e023  jz      short loc_18002E02E
0x18002e025  mov     rcx, rax; this
0x18002e028  call    ??0CSWbemPrivilegeSet@@QEAA@XZ; CSWbemPrivilegeSet::CSWbemPrivilegeSet(void)
0x18002e02d  nop
0x18002e02e  mov     [rbx+78h], rax
0x18002e032  xor     dil, dil
0x18002e035  mov     [rbx+6Ch], dil
0x18002e039  mov     [rbx+6Dh], dil
0x18002e03d  mov     rax, rbx
0x18002e040  mov     rbx, [rsp+68h+arg_10]
0x18002e048  add     rsp, 50h
0x18002e04c  pop     r14
0x18002e04e  pop     rdi
0x18002e04f  pop     rsi
0x18002e050  retn
```
