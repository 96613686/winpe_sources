# CSWbemLocator::CSWbemLocator(CSWbemPrivilegeSet *)

- ea: `0x180010590`
- end: `0x18001078c`
- name: `??0CSWbemLocator@@QEAA@PEAVCSWbemPrivilegeSet@@@Z`
- size: `508`
- prototype: `CSWbemLocator *(CSWbemLocator *__hidden this, struct CSWbemPrivilegeSet *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180010c90`

## callees

- `0x18000fd64`
- `0x1800103c0`
- `0x180010590`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001065e`
- `OLEAUT32!__imp_SysAllocString` at `0x1800106f8`
- `OLEAUT32!__imp_SysAllocString` at `0x18001065e`
- `OLEAUT32!__imp_SysAllocString` at `0x1800106f8`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180010671`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001070c`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180010671`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001070c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180010635`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180010635`

## string_xrefs

- `0x1800106f1`: `SWbemSecurity`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
CSWbemLocator *__fastcall CSWbemLocator::CSWbemLocator(CSWbemLocator *this, struct CSWbemPrivilegeSet *a2)
{
  _QWORD *v4; // rax
  _QWORD *v5; // rbx
  CSWbemPrivilegeSet *v6; // rax
  CSWbemPrivilegeSet *v7; // rax

  *(_QWORD *)this = &CSWbemLocator::`vftable'{for `ISWbemLocator'};
  *((_QWORD *)this + 1) = &CSWbemLocator::`vftable'{for `IDispatchEx'};
  *((_QWORD *)this + 2) = &CSWbemLocator::`vftable'{for `IObjectSafety'};
  *((_QWORD *)this + 3) = &CSWbemLocator::`vftable'{for `ISupportErrorInfo'};
  *((_QWORD *)this + 4) = &CSWbemLocator::`vftable'{for `IProvideClassInfo'};
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = &CDispatchHelp::`vftable';
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_DWORD *)this + 18) = 0;
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 18) = 0;
  *((_DWORD *)this + 38) = 0;
  CoCreateInstance(&CLSID_WbemLocator, 0, 1u, &IID_IWbemLocator, (LPVOID *)this + 6);
  *((_QWORD *)this + 12) = this;
  *(GUID *)((char *)this + 104) = IID_ISWbemLocator;
  *(GUID *)((char *)this + 120) = CLSID_SWbemLocator;
  *((_QWORD *)this + 8) = SysAllocString(L"SWbemLocator");
  v4 = CWin32DefaultArena::WbemMemAlloc(0x88u);
  v5 = v4;
  if ( v4 )
  {
    *v4 = &CWbemLocatorSecurity::`vftable'{for `ISWbemSecurity'};
    v4[1] = &CWbemLocatorSecurity::`vftable'{for `ISupportErrorInfo'};
    v4[2] = &CWbemLocatorSecurity::`vftable'{for `IProvideClassInfo'};
    v4[3] = 0;
    v4[4] = &CDispatchHelp::`vftable';
    v4[7] = 0;
    v4[8] = 0;
    v4[9] = 0;
    v4[5] = 0;
    *((_DWORD *)v4 + 12) = 0;
    *((_BYTE *)v4 + 112) = 0;
    *((_BYTE *)v4 + 120) = 0;
    *((_DWORD *)v4 + 32) = 1;
    v4[9] = v4;
    *((GUID *)v4 + 5) = IID_ISWbemSecurity;
    *((GUID *)v4 + 6) = CLSID_SWbemSecurity;
    v4[5] = SysAllocString(L"SWbemSecurity");
    _InterlockedIncrement(&g_cObj);
    v6 = (CSWbemPrivilegeSet *)CWin32DefaultArena::WbemMemAlloc(0x88u);
    if ( a2 )
    {
      if ( v6 )
        v7 = CSWbemPrivilegeSet::CSWbemPrivilegeSet(v6, a2, 1);
      else
        v7 = 0;
    }
    else if ( v6 )
    {
      v7 = CSWbemPrivilegeSet::CSWbemPrivilegeSet(v6);
    }
    else
    {
      v7 = 0;
    }
    v5[3] = v7;
  }
  else
  {
    v5 = 0;
  }
  *((_QWORD *)this + 5) = v5;
  if ( v5 )
    (*(void (__fastcall **)(_QWORD *, _QWORD))(*v5 + 64LL))(
      v5,
      (unsigned int)CSWbemSecurity::s_dwDefaultImpersonationLevel);
  _InterlockedIncrement(&g_cObj);
  return this;
}

```

## disassembly

```asm
0x180010590  mov     [rsp+arg_8], rbx
0x180010595  mov     [rsp+arg_0], rcx
0x18001059a  push    rbp
0x18001059b  push    rsi
0x18001059c  push    rdi
0x18001059d  push    r12
0x18001059f  push    r15
0x1800105a1  sub     rsp, 30h
0x1800105a5  mov     rsi, rdx
0x1800105a8  mov     rdi, rcx
0x1800105ab  lea     rax, ??_7CSWbemLocator@@6BISWbemLocator@@@; const CSWbemLocator::`vftable'{for `ISWbemLocator'}
0x1800105b2  mov     [rcx], rax
0x1800105b5  lea     rax, ??_7CSWbemLocator@@6BIDispatchEx@@@; const CSWbemLocator::`vftable'{for `IDispatchEx'}
0x1800105bc  mov     [rcx+8], rax
0x1800105c0  lea     rax, ??_7CSWbemLocator@@6BIObjectSafety@@@; const CSWbemLocator::`vftable'{for `IObjectSafety'}
0x1800105c7  mov     [rcx+10h], rax
0x1800105cb  lea     rax, ??_7CSWbemLocator@@6BISupportErrorInfo@@@; const CSWbemLocator::`vftable'{for `ISupportErrorInfo'}
0x1800105d2  mov     [rcx+18h], rax
0x1800105d6  lea     rax, ??_7CSWbemLocator@@6BIProvideClassInfo@@@; const CSWbemLocator::`vftable'{for `IProvideClassInfo'}
0x1800105dd  mov     [rcx+20h], rax
0x1800105e1  lea     rax, [rcx+30h]
0x1800105e5  xor     ebp, ebp
0x1800105e7  mov     [rax], rbp
0x1800105ea  lea     r12, ??_7CDispatchHelp@@6B@; const CDispatchHelp::`vftable'
0x1800105f1  mov     [rcx+38h], r12
0x1800105f5  mov     [rcx+50h], rbp
0x1800105f9  mov     [rcx+58h], rbp
0x1800105fd  mov     [rcx+60h], rbp
0x180010601  mov     [rcx+40h], rbp
0x180010605  mov     [rcx+48h], ebp
0x180010608  mov     [rcx+88h], rbp
0x18001060f  mov     [rcx+90h], rbp
0x180010616  mov     [rcx+98h], ebp
0x18001061c  mov     [rsp+58h+ppv], rax; ppv
0x180010621  lea     r9, IID_IWbemLocator; riid
0x180010628  xor     edx, edx; pUnkOuter
0x18001062a  lea     r8d, [rbp+1]; dwClsContext
0x18001062e  lea     rcx, CLSID_WbemLocator; rclsid
0x180010635  call    cs:__imp_CoCreateInstance
0x18001063b  movups  xmm1, xmmword ptr cs:CLSID_SWbemLocator.Data1
0x180010642  movups  xmm0, xmmword ptr cs:IID_ISWbemLocator.Data1
0x180010649  mov     [rdi+60h], rdi
0x18001064d  movdqu  xmmword ptr [rdi+68h], xmm0
0x180010652  movdqu  xmmword ptr [rdi+78h], xmm1
0x180010657  lea     rcx, aSwbemlocator; "SWbemLocator"
0x18001065e  call    cs:__imp_SysAllocString
0x180010664  mov     [rdi+40h], rax
0x180010668  mov     r15d, 88h
0x18001066e  mov     ecx, r15d
0x180010671  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180010677  mov     rbx, rax
0x18001067a  mov     [rsp+58h+arg_10], rax
0x18001067f  test    rax, rax
0x180010682  jz      loc_180010777
0x180010688  lea     rax, ??_7CWbemLocatorSecurity@@6BISWbemSecurity@@@; const CWbemLocatorSecurity::`vftable'{for `ISWbemSecurity'}
0x18001068f  mov     [rbx], rax
0x180010692  lea     rax, ??_7CWbemLocatorSecurity@@6BISupportErrorInfo@@@; const CWbemLocatorSecurity::`vftable'{for `ISupportErrorInfo'}
0x180010699  mov     [rbx+8], rax
0x18001069d  lea     rax, ??_7CWbemLocatorSecurity@@6BIProvideClassInfo@@@; const CWbemLocatorSecurity::`vftable'{for `IProvideClassInfo'}
0x1800106a4  mov     [rbx+10h], rax
0x1800106a8  mov     [rbx+18h], rbp
0x1800106ac  mov     [rbx+20h], r12
0x1800106b0  mov     [rbx+38h], rbp
0x1800106b4  mov     [rbx+40h], rbp
0x1800106b8  mov     [rbx+48h], rbp
0x1800106bc  mov     [rbx+28h], rbp
0x1800106c0  mov     [rbx+30h], ebp
0x1800106c3  mov     [rbx+70h], bpl
0x1800106c7  mov     [rbx+78h], bpl
0x1800106cb  mov     dword ptr [rbx+80h], 1
0x1800106d5  movups  xmm1, xmmword ptr cs:CLSID_SWbemSecurity.Data1
0x1800106dc  movups  xmm0, xmmword ptr cs:IID_ISWbemSecurity.Data1
0x1800106e3  mov     [rbx+48h], rbx
0x1800106e7  movdqu  xmmword ptr [rbx+50h], xmm0
0x1800106ec  movdqu  xmmword ptr [rbx+60h], xmm1
0x1800106f1  lea     rcx, aSwbemsecurity; "SWbemSecurity"
0x1800106f8  call    cs:__imp_SysAllocString
0x1800106fe  mov     [rbx+28h], rax
0x180010702  lock inc cs:?g_cObj@@3JA; long g_cObj
0x180010709  mov     ecx, r15d
0x18001070c  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180010712  mov     [rsp+58h+arg_18], rax
0x180010717  test    rsi, rsi
0x18001071a  jz      short loc_18001076D
0x18001071c  test    rax, rax
0x18001071f  jz      short loc_18001077C
0x180010721  mov     r8b, 1; bool
0x180010724  mov     rdx, rsi; struct CSWbemPrivilegeSet *
0x180010727  mov     rcx, rax; this
0x18001072a  call    ??0CSWbemPrivilegeSet@@QEAA@AEBV0@_N@Z; CSWbemPrivilegeSet::CSWbemPrivilegeSet(CSWbemPrivilegeSet const &,bool)
0x18001072f  nop
0x180010730  mov     [rbx+18h], rax
0x180010734  mov     [rdi+28h], rbx
0x180010738  test    rbx, rbx
0x18001073b  jz      short loc_180010752
0x18001073d  mov     rax, [rbx]
0x180010740  mov     edx, cs:?s_dwDefaultImpersonationLevel@CSWbemSecurity@@0W4WbemImpersonationLevelEnum@@A; WbemImpersonationLevelEnum CSWbemSecurity::s_dwDefaultImpersonationLevel
0x180010746  mov     rcx, rbx
0x180010749  mov     rax, [rax+40h]
0x18001074d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010752  lock inc cs:?g_cObj@@3JA; long g_cObj
0x180010759  mov     rax, rdi
0x18001075c  mov     rbx, [rsp+58h+arg_8]
0x180010761  add     rsp, 30h
0x180010765  pop     r15
0x180010767  pop     r12
0x180010769  pop     rdi
0x18001076a  pop     rsi
0x18001076b  pop     rbp
0x18001076c  retn
0x18001076d  test    rax, rax
0x180010770  jnz     short loc_180010781
0x180010772  mov     rax, rbp
0x180010775  jmp     short loc_180010730
0x180010777  mov     rbx, rbp
0x18001077a  jmp     short loc_180010734
0x18001077c  mov     rax, rbp
0x18001077f  jmp     short loc_180010730
0x180010781  mov     rcx, rax; this
0x180010784  call    ??0CSWbemPrivilegeSet@@QEAA@XZ; CSWbemPrivilegeSet::CSWbemPrivilegeSet(void)
0x180010789  jmp     short loc_180010775
```
