# CSWbemObjectSet::CSWbemObjectSet(CSWbemServices *,IEnumWbemClassObject *,CSWbemSecurity *)

- ea: `0x180009fd0`
- end: `0x18000a13c`
- name: `??0CSWbemObjectSet@@QEAA@PEAVCSWbemServices@@PEAUIEnumWbemClassObject@@PEAVCSWbemSecurity@@@Z`
- size: `364`
- prototype: `CSWbemObjectSet *(CSWbemObjectSet *__hidden this, struct CSWbemServices *, struct IEnumWbemClassObject *, struct CSWbemSecurity *)`
- caller_count: `6`
- callee_count: `3`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180001e14`
- `0x180001f70`
- `0x1800031b0`
- `0x18001d250`
- `0x18001e010`
- `0x18001e260`

## callees

- `0x180009fd0`
- `0x18000a270`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000a05e`
- `OLEAUT32!__imp_SysAllocString` at `0x18000a05e`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000a0b4`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000a10d`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000a0b4`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000a10d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
CSWbemObjectSet *__fastcall CSWbemObjectSet::CSWbemObjectSet(
        CSWbemObjectSet *this,
        struct CSWbemServices *a2,
        struct IUnknown *a3,
        struct ISWbemSecurity *a4)
{
  struct ISWbemSecurity *v8; // rbx
  __int64 v9; // rax
  __int64 v10; // rcx
  CSWbemSecurity *v11; // rax
  CSWbemSecurity *v12; // rax
  CSWbemSecurity *v14; // rax
  CSWbemSecurity *v15; // rax

  *(_QWORD *)this = &CSWbemObjectSet::`vftable'{for `ISWbemObjectSet'};
  *((_QWORD *)this + 1) = &CSWbemObjectSet::`vftable'{for `ISupportErrorInfo'};
  *((_QWORD *)this + 2) = &CSWbemObjectSet::`vftable'{for `IProvideClassInfo'};
  *((_QWORD *)this + 4) = &CDispatchHelp::`vftable';
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_DWORD *)this + 12) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_BYTE *)this + 121) = 0;
  *((_QWORD *)this + 9) = this;
  *((GUID *)this + 5) = IID_ISWbemObjectSet;
  *((GUID *)this + 6) = CLSID_SWbemObjectSet;
  *((_QWORD *)this + 5) = SysAllocString(L"SWbemObjectSet");
  *((_DWORD *)this + 31) = 0;
  *((_BYTE *)this + 120) = 1;
  *((_QWORD *)this + 3) = a2;
  if ( a2 )
  {
    (*(void (__fastcall **)(struct CSWbemServices *))(*(_QWORD *)a2 + 8LL))(a2);
    if ( a4 )
    {
      v14 = (CSWbemSecurity *)CWin32DefaultArena::WbemMemAlloc(0x90u);
      if ( v14 )
        v15 = CSWbemSecurity::CSWbemSecurity(v14, a3, a4);
      else
        v15 = 0;
      *((_QWORD *)this + 14) = v15;
    }
    else
    {
      v8 = 0;
      v9 = *((_QWORD *)this + 3);
      v10 = *(_QWORD *)(v9 + 136);
      if ( v10 )
      {
        v8 = *(struct ISWbemSecurity **)(v9 + 136);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10);
      }
      v11 = (CSWbemSecurity *)CWin32DefaultArena::WbemMemAlloc(0x90u);
      if ( v11 )
        v12 = CSWbemSecurity::CSWbemSecurity(v11, a3, v8);
      else
        v12 = 0;
      *((_QWORD *)this + 14) = v12;
      if ( v8 )
        ((void (__fastcall *)(struct ISWbemSecurity *))v8->lpVtbl->Release)(v8);
    }
  }
  _InterlockedIncrement(&g_cObj);
  return this;
}

```

## disassembly

```asm
0x180009fd0  mov     [rsp+arg_10], rbx
0x180009fd5  mov     [rsp+arg_18], rbp
0x180009fda  mov     [rsp+arg_0], rcx
0x180009fdf  push    rsi
0x180009fe0  push    rdi
0x180009fe1  push    r14
0x180009fe3  sub     rsp, 20h
0x180009fe7  mov     rsi, r9
0x180009fea  mov     rbp, r8
0x180009fed  mov     rbx, rdx
0x180009ff0  mov     rdi, rcx
0x180009ff3  lea     rax, ??_7CSWbemObjectSet@@6BISWbemObjectSet@@@; const CSWbemObjectSet::`vftable'{for `ISWbemObjectSet'}
0x180009ffa  mov     [rcx], rax
0x180009ffd  lea     rax, ??_7CSWbemObjectSet@@6BISupportErrorInfo@@@; const CSWbemObjectSet::`vftable'{for `ISupportErrorInfo'}
0x18000a004  mov     [rcx+8], rax
0x18000a008  lea     rax, ??_7CSWbemObjectSet@@6BIProvideClassInfo@@@; const CSWbemObjectSet::`vftable'{for `IProvideClassInfo'}
0x18000a00f  mov     [rcx+10h], rax
0x18000a013  lea     rax, ??_7CDispatchHelp@@6B@; const CDispatchHelp::`vftable'
0x18000a01a  mov     [rcx+20h], rax
0x18000a01e  xor     r14d, r14d
0x18000a021  mov     [rcx+38h], r14
0x18000a025  mov     [rcx+40h], r14
0x18000a029  mov     [rcx+48h], r14
0x18000a02d  mov     [rcx+28h], r14
0x18000a031  mov     [rcx+30h], r14d
0x18000a035  mov     [rcx+70h], r14
0x18000a039  mov     [rcx+79h], r14b
0x18000a03d  movups  xmm1, xmmword ptr cs:CLSID_SWbemObjectSet.Data1
0x18000a044  movups  xmm0, xmmword ptr cs:IID_ISWbemObjectSet.Data1
0x18000a04b  mov     [rcx+48h], rcx
0x18000a04f  movups  xmmword ptr [rcx+50h], xmm0
0x18000a053  movups  xmmword ptr [rcx+60h], xmm1
0x18000a057  lea     rcx, aSwbemobjectset; "SWbemObjectSet"
0x18000a05e  call    cs:__imp_SysAllocString
0x18000a064  mov     [rdi+28h], rax
0x18000a068  mov     [rdi+7Ch], r14d
0x18000a06c  mov     byte ptr [rdi+78h], 1
0x18000a070  mov     [rdi+18h], rbx
0x18000a074  test    rbx, rbx
0x18000a077  jz      short loc_18000A0EB
0x18000a079  mov     rax, [rbx]
0x18000a07c  mov     rcx, rbx
0x18000a07f  mov     rax, [rax+8]
0x18000a083  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a088  test    rsi, rsi
0x18000a08b  jnz     short loc_18000A108
0x18000a08d  mov     ebx, r14d
0x18000a090  mov     rax, [rdi+18h]
0x18000a094  mov     rcx, [rax+88h]
0x18000a09b  test    rcx, rcx
0x18000a09e  jz      short loc_18000A0AF
0x18000a0a0  mov     rbx, rcx
0x18000a0a3  mov     rax, [rcx]
0x18000a0a6  mov     rax, [rax+8]
0x18000a0aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0af  mov     ecx, 90h
0x18000a0b4  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000a0ba  mov     [rsp+38h+arg_8], rax
0x18000a0bf  test    rax, rax
0x18000a0c2  jz      short loc_18000A126
0x18000a0c4  mov     r8, rbx; struct CSWbemSecurity *
0x18000a0c7  mov     rdx, rbp; struct IUnknown *
0x18000a0ca  mov     rcx, rax; this
0x18000a0cd  call    ??0CSWbemSecurity@@QEAA@PEAUIUnknown@@PEAV0@@Z; CSWbemSecurity::CSWbemSecurity(IUnknown *,CSWbemSecurity *)
0x18000a0d2  nop
0x18000a0d3  mov     [rdi+70h], rax
0x18000a0d7  test    rbx, rbx
0x18000a0da  jz      short loc_18000A0EB
0x18000a0dc  mov     rax, [rbx]
0x18000a0df  mov     rcx, rbx
0x18000a0e2  mov     rax, [rax+10h]
0x18000a0e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0eb  lock inc cs:?g_cObj@@3JA; long g_cObj
0x18000a0f2  mov     rax, rdi
0x18000a0f5  mov     rbx, [rsp+38h+arg_10]
0x18000a0fa  mov     rbp, [rsp+38h+arg_18]
0x18000a0ff  add     rsp, 20h
0x18000a103  pop     r14
0x18000a105  pop     rdi
0x18000a106  pop     rsi
0x18000a107  retn
0x18000a108  mov     ecx, 90h
0x18000a10d  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000a113  mov     [rsp+38h+arg_8], rax
0x18000a118  test    rax, rax
0x18000a11b  jnz     short loc_18000A12B
0x18000a11d  mov     rax, r14
0x18000a120  mov     [rdi+70h], rax
0x18000a124  jmp     short loc_18000A0EB
0x18000a126  mov     rax, r14
0x18000a129  jmp     short loc_18000A0D3
0x18000a12b  mov     r8, rsi; struct CSWbemSecurity *
0x18000a12e  mov     rdx, rbp; struct IUnknown *
0x18000a131  mov     rcx, rax; this
0x18000a134  call    ??0CSWbemSecurity@@QEAA@PEAUIUnknown@@PEAV0@@Z; CSWbemSecurity::CSWbemSecurity(IUnknown *,CSWbemSecurity *)
0x18000a139  jmp     short loc_18000A120
```
