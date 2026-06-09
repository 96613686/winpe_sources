# CSWbemObjectObjectPathSecurity::CSWbemObjectObjectPathSecurity(CSWbemServices *)

- ea: `0x1800017fc`
- end: `0x180001993`
- name: `??0CSWbemObjectObjectPathSecurity@@QEAA@PEAVCSWbemServices@@@Z`
- size: `407`
- prototype: `CSWbemObjectObjectPathSecurity *(CSWbemObjectObjectPathSecurity *__hidden this, struct CSWbemServices *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180001448`

## callees

- `0x1800017fc`
- `0x180003170`
- `0x18000d950`
- `0x1800103c0`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180001893`
- `OLEAUT32!__imp_SysAllocString` at `0x180001927`
- `OLEAUT32!__imp_SysAllocString` at `0x180001893`
- `OLEAUT32!__imp_SysAllocString` at `0x180001927`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180001954`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180001954`

## string_xrefs

- `0x18000188c`: `SWbemSecurity`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
CSWbemObjectObjectPathSecurity *__fastcall CSWbemObjectObjectPathSecurity::CSWbemObjectObjectPathSecurity(
        CSWbemObjectObjectPathSecurity *this,
        struct CSWbemServices *a2)
{
  struct CSWbemSecurity *SecurityInfo; // rax
  CSWbemSecurity *v5; // rbx
  __int64 v7; // rcx
  const struct CSWbemPrivilegeSet *PrivilegeSet; // rsi
  CSWbemPrivilegeSet *v9; // rax

  *(_QWORD *)this = &CSWbemObjectObjectPathSecurity::`vftable'{for `ISWbemSecurity'};
  *((_QWORD *)this + 1) = &CWbemLocatorSecurity::`vftable'{for `ISupportErrorInfo'};
  *((_QWORD *)this + 2) = &CWbemLocatorSecurity::`vftable'{for `IProvideClassInfo'};
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = &CDispatchHelp::`vftable';
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_DWORD *)this + 12) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 9) = this;
  *((GUID *)this + 5) = IID_ISWbemSecurity;
  *((GUID *)this + 6) = CLSID_SWbemSecurity;
  *((_QWORD *)this + 5) = SysAllocString(L"SWbemSecurity");
  *((_DWORD *)this + 32) = 1;
  _InterlockedIncrement(&g_cObj);
  if ( a2 )
  {
    SecurityInfo = CSWbemServices::GetSecurityInfo(a2);
    v5 = SecurityInfo;
    if ( SecurityInfo )
    {
      (*(void (__fastcall **)(struct CSWbemSecurity *, char *))(*(_QWORD *)SecurityInfo + 72LL))(
        SecurityInfo,
        (char *)this + 116);
      (*(void (__fastcall **)(CSWbemSecurity *, char *))(*(_QWORD *)v5 + 56LL))(v5, (char *)this + 112);
      v7 = *((_QWORD *)v5 + 15);
      if ( v7 )
        v7 = *(_QWORD *)(v7 + 296);
      *((_QWORD *)this + 15) = SysAllocString((const OLECHAR *)v7);
      PrivilegeSet = CSWbemSecurity::GetPrivilegeSet(v5);
      if ( PrivilegeSet )
      {
        v9 = (CSWbemPrivilegeSet *)CWin32DefaultArena::WbemMemAlloc(0x88u);
        if ( v9 )
          v9 = CSWbemPrivilegeSet::CSWbemPrivilegeSet(v9, PrivilegeSet, 0);
        *((_QWORD *)this + 3) = v9;
      }
      if ( PrivilegeSet )
        (*(void (__fastcall **)(const struct CSWbemPrivilegeSet *))(*(_QWORD *)PrivilegeSet + 16LL))(PrivilegeSet);
    }
    if ( v5 )
      (*(void (__fastcall **)(CSWbemSecurity *))(*(_QWORD *)v5 + 16LL))(v5);
  }
  return this;
}

```

## disassembly

```asm
0x1800017fc  mov     [rsp+arg_0], rcx
0x180001801  push    rbx
0x180001802  push    rsi
0x180001803  push    rdi
0x180001804  sub     rsp, 20h
0x180001808  mov     rbx, rdx
0x18000180b  mov     rdi, rcx
0x18000180e  lea     rax, ??_7CSWbemObjectObjectPathSecurity@@6BISWbemSecurity@@@; const CSWbemObjectObjectPathSecurity::`vftable'{for `ISWbemSecurity'}
0x180001815  mov     [rcx], rax
0x180001818  lea     rax, ??_7CWbemLocatorSecurity@@6BISupportErrorInfo@@@; const CWbemLocatorSecurity::`vftable'{for `ISupportErrorInfo'}
0x18000181f  mov     [rcx+8], rax
0x180001823  lea     rax, ??_7CWbemLocatorSecurity@@6BIProvideClassInfo@@@; const CWbemLocatorSecurity::`vftable'{for `IProvideClassInfo'}
0x18000182a  mov     [rcx+10h], rax
0x18000182e  mov     qword ptr [rcx+18h], 0
0x180001836  lea     rax, ??_7CDispatchHelp@@6B@; const CDispatchHelp::`vftable'
0x18000183d  mov     [rcx+20h], rax
0x180001841  mov     qword ptr [rcx+38h], 0
0x180001849  mov     qword ptr [rcx+40h], 0
0x180001851  mov     qword ptr [rcx+48h], 0
0x180001859  mov     qword ptr [rcx+28h], 0
0x180001861  mov     dword ptr [rcx+30h], 0
0x180001868  mov     qword ptr [rcx+78h], 0
0x180001870  movups  xmm1, xmmword ptr cs:CLSID_SWbemSecurity.Data1
0x180001877  movups  xmm0, xmmword ptr cs:IID_ISWbemSecurity.Data1
0x18000187e  mov     [rcx+48h], rcx
0x180001882  movdqu  xmmword ptr [rcx+50h], xmm0
0x180001887  movdqu  xmmword ptr [rcx+60h], xmm1
0x18000188c  lea     rcx, aSwbemsecurity; "SWbemSecurity"
0x180001893  call    cs:__imp_SysAllocString
0x180001899  mov     [rdi+28h], rax
0x18000189d  mov     dword ptr [rdi+80h], 1
0x1800018a7  lock inc cs:?g_cObj@@3JA; long g_cObj
0x1800018ae  test    rbx, rbx
0x1800018b1  jz      short loc_1800018E6
0x1800018b3  mov     [rsp+38h+arg_8], 0
0x1800018bc  mov     rcx, rbx; this
0x1800018bf  call    ?GetSecurityInfo@CSWbemServices@@QEAAPEAVCSWbemSecurity@@XZ; CSWbemServices::GetSecurityInfo(void)
0x1800018c4  mov     rbx, rax
0x1800018c7  mov     [rsp+38h+arg_8], rax
0x1800018cc  test    rax, rax
0x1800018cf  jnz     short loc_1800018F1
0x1800018d1  test    rbx, rbx
0x1800018d4  jz      short loc_1800018E6
0x1800018d6  mov     rax, [rbx]
0x1800018d9  mov     rcx, rbx
0x1800018dc  mov     rax, [rax+10h]
0x1800018e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800018e5  nop
0x1800018e6  mov     rax, rdi
0x1800018e9  add     rsp, 20h
0x1800018ed  pop     rdi
0x1800018ee  pop     rsi
0x1800018ef  pop     rbx
0x1800018f0  retn
0x1800018f1  mov     rcx, [rax]
0x1800018f4  lea     rdx, [rdi+74h]
0x1800018f8  mov     rax, [rcx+48h]
0x1800018fc  mov     rcx, rbx
0x1800018ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001904  mov     rcx, [rbx]
0x180001907  lea     rdx, [rdi+70h]
0x18000190b  mov     rax, [rcx+38h]
0x18000190f  mov     rcx, rbx
0x180001912  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001917  mov     rcx, [rbx+78h]
0x18000191b  test    rcx, rcx
0x18000191e  jz      short loc_180001927
0x180001920  mov     rcx, [rcx+128h]; psz
0x180001927  call    cs:__imp_SysAllocString
0x18000192d  mov     [rdi+78h], rax
0x180001931  mov     [rsp+38h+arg_10], 0
0x18000193a  mov     rcx, rbx; this
0x18000193d  call    ?GetPrivilegeSet@CSWbemSecurity@@QEAAPEAVCSWbemPrivilegeSet@@XZ; CSWbemSecurity::GetPrivilegeSet(void)
0x180001942  mov     rsi, rax
0x180001945  mov     [rsp+38h+arg_10], rax
0x18000194a  test    rax, rax
0x18000194d  jz      short loc_180001968
0x18000194f  mov     ecx, 88h
0x180001954  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000195a  mov     [rsp+38h+arg_18], rax
0x18000195f  test    rax, rax
0x180001962  jnz     short loc_180001982
0x180001964  mov     [rdi+18h], rax
0x180001968  test    rsi, rsi
0x18000196b  jz      short loc_18000197D
0x18000196d  mov     rax, [rsi]
0x180001970  mov     rcx, rsi
0x180001973  mov     rax, [rax+10h]
0x180001977  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000197c  nop
0x18000197d  jmp     loc_1800018D1
0x180001982  xor     r8d, r8d; bool
0x180001985  mov     rdx, rsi; struct CSWbemPrivilegeSet *
0x180001988  mov     rcx, rax; this
0x18000198b  call    ??0CSWbemPrivilegeSet@@QEAA@AEBV0@_N@Z; CSWbemPrivilegeSet::CSWbemPrivilegeSet(CSWbemPrivilegeSet const &,bool)
0x180001990  jmp     short loc_180001964
```
