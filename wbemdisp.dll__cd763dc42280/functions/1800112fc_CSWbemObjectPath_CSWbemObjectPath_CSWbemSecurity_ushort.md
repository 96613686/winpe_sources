# CSWbemObjectPath::CSWbemObjectPath(CSWbemSecurity *,ushort *)

- ea: `0x1800112fc`
- end: `0x180011485`
- name: `??0CSWbemObjectPath@@QEAA@PEAVCSWbemSecurity@@PEAG@Z`
- size: `393`
- prototype: `CSWbemObjectPath *(CSWbemObjectPath *__hidden this, struct CSWbemSecurity *, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180010c90`
- `0x18001dc50`
- `0x1800292f0`
- `0x18002b880`

## callees

- `0x1800112fc`
- `0x1800114f0`
- `0x18002dec0`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800113d0`
- `OLEAUT32!__imp_SysAllocString` at `0x18001142f`
- `OLEAUT32!__imp_SysAllocString` at `0x180011468`
- `OLEAUT32!__imp_SysAllocString` at `0x1800113d0`
- `OLEAUT32!__imp_SysAllocString` at `0x18001142f`
- `OLEAUT32!__imp_SysAllocString` at `0x180011468`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800113df`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180011445`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800113df`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180011445`

## string_xrefs

- `0x1800113c9`: `SWbemObjectPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
CSWbemObjectPath *__fastcall CSWbemObjectPath::CSWbemObjectPath(
        CSWbemObjectPath *this,
        struct CSWbemSecurity *a2,
        unsigned __int16 *a3)
{
  CWbemPathCracker *v6; // rax
  CWbemPathCracker *v7; // rcx
  __int64 v8; // rax
  const OLECHAR *v9; // rcx
  BSTR v10; // rax
  struct IDispatch *v11; // rax

  *(_QWORD *)this = &CSWbemObjectPath::`vftable'{for `ISWbemObjectPath'};
  *((_QWORD *)this + 1) = &CSWbemObjectPath::`vftable'{for `IObjectSafety'};
  *((_QWORD *)this + 2) = &CSWbemObjectPath::`vftable'{for `ISupportErrorInfo'};
  *((_QWORD *)this + 3) = &CSWbemObjectPath::`vftable'{for `IProvideClassInfo'};
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_DWORD *)this + 12) = 0;
  *((_QWORD *)this + 4) = &CSWbemObjectObjectPath::CObjectObjectPathDispatchHelp::`vftable';
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = 0;
  *((_DWORD *)this + 34) = 0;
  *((_QWORD *)this + 18) = 0;
  _InterlockedIncrement(&g_cObj);
  *((_QWORD *)this + 9) = this;
  *((GUID *)this + 5) = IID_ISWbemObjectPath;
  *((GUID *)this + 6) = CLSID_SWbemObjectPath;
  *((_QWORD *)this + 5) = SysAllocString(L"SWbemObjectPath");
  v6 = (CWbemPathCracker *)CWin32DefaultArena::WbemMemAlloc(0x20u);
  if ( v6 )
    v7 = CWbemPathCracker::CWbemPathCracker(v6);
  else
    v7 = 0;
  *((_QWORD *)this + 18) = v7;
  if ( v7 )
    (*(void (__fastcall **)(CWbemPathCracker *))(*(_QWORD *)v7 + 8LL))(v7);
  if ( a2 )
  {
    v8 = *((_QWORD *)a2 + 15);
    if ( v8 )
      v9 = *(const OLECHAR **)(v8 + 296);
    else
      v9 = 0;
    v10 = SysAllocString(v9);
  }
  else
  {
    v10 = 0;
  }
  *((_QWORD *)this + 16) = v10;
  v11 = (struct IDispatch *)CWin32DefaultArena::WbemMemAlloc(0x80u);
  if ( v11 )
    v11 = (struct IDispatch *)CSWbemObjectPath::CWbemObjectPathSecurity::CWbemObjectPathSecurity(v11, a2);
  *((_QWORD *)this + 14) = v11;
  *((_QWORD *)this + 15) = SysAllocString(a3);
  return this;
}

```

## disassembly

```asm
0x1800112fc  mov     [rsp+arg_10], rbx
0x180011301  mov     [rsp+arg_18], rsi
0x180011306  mov     [rsp+arg_0], rcx
0x18001130b  push    rdi
0x18001130c  sub     rsp, 20h
0x180011310  mov     rsi, r8
0x180011313  mov     rdi, rdx
0x180011316  mov     rbx, rcx
0x180011319  lea     rax, ??_7CSWbemObjectPath@@6BISWbemObjectPath@@@; const CSWbemObjectPath::`vftable'{for `ISWbemObjectPath'}
0x180011320  mov     [rcx], rax
0x180011323  lea     rax, ??_7CSWbemObjectPath@@6BIObjectSafety@@@; const CSWbemObjectPath::`vftable'{for `IObjectSafety'}
0x18001132a  mov     [rcx+8], rax
0x18001132e  lea     rax, ??_7CSWbemObjectPath@@6BISupportErrorInfo@@@; const CSWbemObjectPath::`vftable'{for `ISupportErrorInfo'}
0x180011335  mov     [rcx+10h], rax
0x180011339  lea     rax, ??_7CSWbemObjectPath@@6BIProvideClassInfo@@@; const CSWbemObjectPath::`vftable'{for `IProvideClassInfo'}
0x180011340  mov     [rcx+18h], rax
0x180011344  mov     qword ptr [rcx+38h], 0
0x18001134c  mov     qword ptr [rcx+40h], 0
0x180011354  mov     qword ptr [rcx+48h], 0
0x18001135c  mov     qword ptr [rcx+28h], 0
0x180011364  mov     dword ptr [rcx+30h], 0
0x18001136b  lea     rax, ??_7CObjectObjectPathDispatchHelp@CSWbemObjectObjectPath@@6B@; const CSWbemObjectObjectPath::CObjectObjectPathDispatchHelp::`vftable'
0x180011372  mov     [rcx+20h], rax
0x180011376  mov     qword ptr [rcx+70h], 0
0x18001137e  mov     qword ptr [rcx+78h], 0
0x180011386  mov     qword ptr [rcx+80h], 0
0x180011391  mov     dword ptr [rcx+88h], 0
0x18001139b  mov     qword ptr [rcx+90h], 0
0x1800113a6  lock inc cs:?g_cObj@@3JA; long g_cObj
0x1800113ad  movups  xmm1, xmmword ptr cs:CLSID_SWbemObjectPath.Data1
0x1800113b4  movups  xmm0, xmmword ptr cs:IID_ISWbemObjectPath.Data1
0x1800113bb  mov     [rcx+48h], rcx
0x1800113bf  movdqu  xmmword ptr [rcx+50h], xmm0
0x1800113c4  movdqu  xmmword ptr [rcx+60h], xmm1
0x1800113c9  lea     rcx, aSwbemobjectpat; "SWbemObjectPath"
0x1800113d0  call    cs:__imp_SysAllocString
0x1800113d6  mov     [rbx+28h], rax
0x1800113da  mov     ecx, 20h ; ' '
0x1800113df  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800113e5  mov     [rsp+28h+arg_8], rax
0x1800113ea  test    rax, rax
0x1800113ed  jz      short loc_1800113FC
0x1800113ef  mov     rcx, rax; this
0x1800113f2  call    ??0CWbemPathCracker@@QEAA@XZ; CWbemPathCracker::CWbemPathCracker(void)
0x1800113f7  mov     rcx, rax
0x1800113fa  jmp     short loc_1800113FE
0x1800113fc  xor     ecx, ecx
0x1800113fe  mov     [rbx+90h], rcx
0x180011405  test    rcx, rcx
0x180011408  jz      short loc_180011416
0x18001140a  mov     rax, [rcx]
0x18001140d  mov     rax, [rax+8]
0x180011411  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011416  test    rdi, rdi
0x180011419  jz      short loc_180011437
0x18001141b  mov     rax, [rdi+78h]
0x18001141f  test    rax, rax
0x180011422  jz      short loc_18001142D
0x180011424  mov     rcx, [rax+128h]
0x18001142b  jmp     short loc_18001142F
0x18001142d  xor     ecx, ecx; psz
0x18001142f  call    cs:__imp_SysAllocString
0x180011435  jmp     short loc_180011439
0x180011437  xor     eax, eax
0x180011439  mov     [rbx+80h], rax
0x180011440  mov     ecx, 80h
0x180011445  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18001144b  mov     [rsp+28h+arg_8], rax
0x180011450  test    rax, rax
0x180011453  jz      short loc_180011461
0x180011455  mov     rdx, rdi; struct CSWbemSecurity *
0x180011458  mov     rcx, rax; this
0x18001145b  call    ??0CWbemObjectPathSecurity@CSWbemObjectPath@@QEAA@PEAVCSWbemSecurity@@@Z; CSWbemObjectPath::CWbemObjectPathSecurity::CWbemObjectPathSecurity(CSWbemSecurity *)
0x180011460  nop
0x180011461  mov     [rbx+70h], rax
0x180011465  mov     rcx, rsi; psz
0x180011468  call    cs:__imp_SysAllocString
0x18001146e  mov     [rbx+78h], rax
0x180011472  mov     rax, rbx
0x180011475  mov     rbx, [rsp+28h+arg_10]
0x18001147a  mov     rsi, [rsp+28h+arg_18]
0x18001147f  add     rsp, 20h
0x180011483  pop     rdi
0x180011484  retn
```
