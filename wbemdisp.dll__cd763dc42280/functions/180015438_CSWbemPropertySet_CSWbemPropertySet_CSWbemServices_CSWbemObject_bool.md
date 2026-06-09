# CSWbemPropertySet::CSWbemPropertySet(CSWbemServices *,CSWbemObject *,bool)

- ea: `0x180015438`
- end: `0x18001559f`
- name: `??0CSWbemPropertySet@@QEAA@PEAVCSWbemServices@@PEAVCSWbemObject@@_N@Z`
- size: `359`
- prototype: `CSWbemPropertySet *__fastcall(CSWbemPropertySet *__hidden this, struct CSWbemServices *, struct CSWbemObject *, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18002c790`

## callees

- `0x180015438`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800154d1`
- `OLEAUT32!__imp_SysAllocString` at `0x1800154d1`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001550f`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001550f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
CSWbemPropertySet *__fastcall CSWbemPropertySet::CSWbemPropertySet(
        CSWbemPropertySet *this,
        struct CSWbemServices *a2,
        struct CSWbemObject *a3,
        char a4)
{
  __int64 v7; // rbx
  _DWORD *v8; // rax
  _DWORD *v9; // rbx
  __int64 v10; // rcx

  *(_QWORD *)this = &CSWbemPropertySet::`vftable'{for `ISWbemPropertySet'};
  *((_QWORD *)this + 1) = &CSWbemPropertySet::`vftable'{for `ISupportErrorInfo'};
  *((_QWORD *)this + 2) = &CSWbemPropertySet::`vftable'{for `IProvideClassInfo'};
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_DWORD *)this + 16) = 0;
  *((_QWORD *)this + 6) = &CSWbemPropertySet::CPropertySetDispatchHelp::`vftable';
  *((_BYTE *)this + 136) = a4;
  *((_QWORD *)this + 11) = this;
  *((GUID *)this + 6) = IID_ISWbemPropertySet;
  *((GUID *)this + 7) = CLSID_SWbemPropertySet;
  *((_QWORD *)this + 7) = SysAllocString(L"SWbemPropertySet");
  *((_QWORD *)this + 4) = a3;
  (*(void (__fastcall **)(struct CSWbemObject *))(*(_QWORD *)a3 + 8LL))(a3);
  v7 = *((_QWORD *)this + 4);
  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v7 + 64) + 8LL))(*(_QWORD *)(v7 + 64));
  *((_QWORD *)this + 5) = *(_QWORD *)(v7 + 64);
  v8 = CWin32DefaultArena::WbemMemAlloc(0x18u);
  v9 = v8;
  if ( v8 )
  {
    v10 = (*((_QWORD *)this + 4) + 16LL) & -(__int64)(*((_QWORD *)this + 4) != 0);
    v8[2] = 1;
    *(_QWORD *)v8 = &CWbemObjectSite::`vftable';
    *((_QWORD *)v8 + 2) = v10;
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10);
  }
  else
  {
    v9 = 0;
  }
  *((_QWORD *)this + 16) = v9;
  *((_QWORD *)this + 3) = a2;
  if ( a2 )
    (*(void (__fastcall **)(struct CSWbemServices *))(*(_QWORD *)a2 + 8LL))(a2);
  *((_DWORD *)this + 35) = 1;
  _InterlockedIncrement(&g_cObj);
  return this;
}

```

## disassembly

```asm
0x180015438  mov     [rsp+arg_10], rbx
0x18001543d  mov     [rsp+arg_18], rsi
0x180015442  mov     [rsp+arg_0], rcx
0x180015447  push    rdi
0x180015448  sub     rsp, 20h
0x18001544c  mov     rbx, r8
0x18001544f  mov     rsi, rdx
0x180015452  mov     rdi, rcx
0x180015455  lea     rax, ??_7CSWbemPropertySet@@6BISWbemPropertySet@@@; const CSWbemPropertySet::`vftable'{for `ISWbemPropertySet'}
0x18001545c  mov     [rcx], rax
0x18001545f  lea     rax, ??_7CSWbemPropertySet@@6BISupportErrorInfo@@@; const CSWbemPropertySet::`vftable'{for `ISupportErrorInfo'}
0x180015466  mov     [rcx+8], rax
0x18001546a  lea     rax, ??_7CSWbemPropertySet@@6BIProvideClassInfo@@@; const CSWbemPropertySet::`vftable'{for `IProvideClassInfo'}
0x180015471  mov     [rcx+10h], rax
0x180015475  mov     qword ptr [rcx+48h], 0
0x18001547d  mov     qword ptr [rcx+50h], 0
0x180015485  mov     qword ptr [rcx+58h], 0
0x18001548d  mov     qword ptr [rcx+38h], 0
0x180015495  mov     dword ptr [rcx+40h], 0
0x18001549c  lea     rax, ??_7CPropertySetDispatchHelp@CSWbemPropertySet@@6B@; const CSWbemPropertySet::CPropertySetDispatchHelp::`vftable'
0x1800154a3  mov     [rcx+30h], rax
0x1800154a7  mov     [rcx+88h], r9b
0x1800154ae  movups  xmm1, xmmword ptr cs:CLSID_SWbemPropertySet.Data1
0x1800154b5  movups  xmm0, xmmword ptr cs:IID_ISWbemPropertySet.Data1
0x1800154bc  mov     [rcx+58h], rcx
0x1800154c0  movdqu  xmmword ptr [rcx+60h], xmm0
0x1800154c5  movdqu  xmmword ptr [rcx+70h], xmm1
0x1800154ca  lea     rcx, aSwbempropertys; "SWbemPropertySet"
0x1800154d1  call    cs:__imp_SysAllocString
0x1800154d7  mov     [rdi+38h], rax
0x1800154db  mov     [rdi+20h], rbx
0x1800154df  mov     rax, [rbx]
0x1800154e2  mov     rcx, rbx
0x1800154e5  mov     rax, [rax+8]
0x1800154e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154ee  mov     rbx, [rdi+20h]
0x1800154f2  mov     rcx, [rbx+40h]
0x1800154f6  mov     rax, [rcx]
0x1800154f9  mov     rax, [rax+8]
0x1800154fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015502  mov     rax, [rbx+40h]
0x180015506  mov     [rdi+28h], rax
0x18001550a  mov     ecx, 18h
0x18001550f  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180015515  mov     rbx, rax
0x180015518  mov     [rsp+28h+arg_8], rax
0x18001551d  test    rax, rax
0x180015520  jz      short loc_18001559A
0x180015522  mov     rcx, [rdi+20h]
0x180015526  lea     rdx, [rcx+10h]
0x18001552a  neg     rcx
0x18001552d  sbb     rcx, rcx
0x180015530  and     rcx, rdx
0x180015533  mov     dword ptr [rax+8], 1
0x18001553a  lea     rax, ??_7CWbemObjectSite@@6B@; const CWbemObjectSite::`vftable'
0x180015541  mov     [rbx], rax
0x180015544  mov     [rbx+10h], rcx
0x180015548  jz      short loc_180015557
0x18001554a  mov     rax, [rcx]
0x18001554d  mov     rax, [rax+8]
0x180015551  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015556  nop
0x180015557  mov     [rdi+80h], rbx
0x18001555e  mov     [rdi+18h], rsi
0x180015562  test    rsi, rsi
0x180015565  jz      short loc_180015576
0x180015567  mov     rax, [rsi]
0x18001556a  mov     rcx, rsi
0x18001556d  mov     rax, [rax+8]
0x180015571  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015576  mov     dword ptr [rdi+8Ch], 1
0x180015580  lock inc cs:?g_cObj@@3JA; long g_cObj
0x180015587  mov     rax, rdi
0x18001558a  mov     rbx, [rsp+28h+arg_10]
0x18001558f  mov     rsi, [rsp+28h+arg_18]
0x180015594  add     rsp, 20h
0x180015598  pop     rdi
0x180015599  retn
0x18001559a  xor     ebx, ebx
0x18001559c  jmp     short loc_180015557
```
