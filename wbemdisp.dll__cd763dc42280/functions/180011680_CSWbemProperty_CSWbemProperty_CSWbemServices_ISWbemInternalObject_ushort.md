# CSWbemProperty::CSWbemProperty(CSWbemServices *,ISWbemInternalObject *,ushort *)

- ea: `0x180011680`
- end: `0x1800117d6`
- name: `??0CSWbemProperty@@QEAA@PEAVCSWbemServices@@PEAUISWbemInternalObject@@PEAG@Z`
- size: `342`
- prototype: `CSWbemProperty *(CSWbemProperty *__hidden this, struct CSWbemServices *, struct ISWbemInternalObject *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180011590`
- `0x180021d10`

## callees

- `0x180011680`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180011706`
- `OLEAUT32!__imp_SysAllocString` at `0x1800117a6`
- `OLEAUT32!__imp_SysAllocString` at `0x180011706`
- `OLEAUT32!__imp_SysAllocString` at `0x1800117a6`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180011746`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180011746`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
CSWbemProperty *__fastcall CSWbemProperty::CSWbemProperty(
        CSWbemProperty *this,
        struct CSWbemServices *a2,
        struct ISWbemInternalObject *a3,
        unsigned __int16 *a4)
{
  _DWORD *v8; // rax
  _DWORD *v9; // rbx
  __int64 v10; // rcx

  *(_QWORD *)this = &CSWbemProperty::`vftable'{for `ISWbemProperty'};
  *((_QWORD *)this + 1) = &CSWbemProperty::`vftable'{for `ISupportErrorInfo'};
  *((_QWORD *)this + 2) = &CSWbemProperty::`vftable'{for `IProvideClassInfo'};
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_DWORD *)this + 16) = 0;
  *((_QWORD *)this + 6) = &CSWbemProperty::CPropertyDispatchHelp::`vftable';
  *((_QWORD *)this + 11) = this;
  *((GUID *)this + 6) = IID_ISWbemProperty;
  *((GUID *)this + 7) = CLSID_SWbemProperty;
  *((_QWORD *)this + 7) = SysAllocString(L"SWbemProperty");
  *((_DWORD *)this + 36) = 1;
  *((_QWORD *)this + 4) = a3;
  (*(void (__fastcall **)(struct ISWbemInternalObject *))(*(_QWORD *)a3 + 8LL))(a3);
  (*(void (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 4) + 24LL))(*((_QWORD *)this + 4), (char *)this + 40);
  v8 = CWin32DefaultArena::WbemMemAlloc(0x18u);
  v9 = v8;
  if ( v8 )
  {
    v10 = *((_QWORD *)this + 4);
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
  *((_QWORD *)this + 17) = v9;
  *((_QWORD *)this + 3) = a2;
  if ( a2 )
    (*(void (__fastcall **)(struct CSWbemServices *))(*(_QWORD *)a2 + 8LL))(a2);
  *((_QWORD *)this + 16) = SysAllocString(a4);
  _InterlockedIncrement(&g_cObj);
  return this;
}

```

## disassembly

```asm
0x180011680  mov     [rsp+arg_10], rbx
0x180011685  mov     [rsp+arg_18], rbp
0x18001168a  mov     [rsp+arg_0], rcx
0x18001168f  push    rsi
0x180011690  push    rdi
0x180011691  push    r14
0x180011693  sub     rsp, 20h
0x180011697  mov     rbp, r9
0x18001169a  mov     rbx, r8
0x18001169d  mov     rsi, rdx
0x1800116a0  mov     rdi, rcx
0x1800116a3  lea     rax, ??_7CSWbemProperty@@6BISWbemProperty@@@; const CSWbemProperty::`vftable'{for `ISWbemProperty'}
0x1800116aa  mov     [rcx], rax
0x1800116ad  lea     rax, ??_7CSWbemProperty@@6BISupportErrorInfo@@@; const CSWbemProperty::`vftable'{for `ISupportErrorInfo'}
0x1800116b4  mov     [rcx+8], rax
0x1800116b8  lea     rax, ??_7CSWbemProperty@@6BIProvideClassInfo@@@; const CSWbemProperty::`vftable'{for `IProvideClassInfo'}
0x1800116bf  mov     [rcx+10h], rax
0x1800116c3  xor     r14d, r14d
0x1800116c6  mov     [rcx+48h], r14
0x1800116ca  mov     [rcx+50h], r14
0x1800116ce  mov     [rcx+58h], r14
0x1800116d2  mov     [rcx+38h], r14
0x1800116d6  mov     [rcx+40h], r14d
0x1800116da  lea     rax, ??_7CPropertyDispatchHelp@CSWbemProperty@@6B@; const CSWbemProperty::CPropertyDispatchHelp::`vftable'
0x1800116e1  mov     [rcx+30h], rax
0x1800116e5  movups  xmm1, xmmword ptr cs:CLSID_SWbemProperty.Data1
0x1800116ec  movups  xmm0, xmmword ptr cs:IID_ISWbemProperty.Data1
0x1800116f3  mov     [rcx+58h], rcx
0x1800116f7  movups  xmmword ptr [rcx+60h], xmm0
0x1800116fb  movups  xmmword ptr [rcx+70h], xmm1
0x1800116ff  lea     rcx, aSwbemproperty; "SWbemProperty"
0x180011706  call    cs:__imp_SysAllocString
0x18001170c  mov     [rdi+38h], rax
0x180011710  mov     dword ptr [rdi+90h], 1
0x18001171a  mov     [rdi+20h], rbx
0x18001171e  mov     rax, [rbx]
0x180011721  mov     rcx, rbx
0x180011724  mov     rax, [rax+8]
0x180011728  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001172d  mov     rcx, [rdi+20h]
0x180011731  mov     rax, [rcx]
0x180011734  lea     rdx, [rdi+28h]
0x180011738  mov     rax, [rax+18h]
0x18001173c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011741  mov     ecx, 18h
0x180011746  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18001174c  mov     rbx, rax
0x18001174f  mov     [rsp+38h+arg_8], rax
0x180011754  test    rax, rax
0x180011757  jz      short loc_1800117D0
0x180011759  mov     rcx, [rdi+20h]
0x18001175d  mov     dword ptr [rax+8], 1
0x180011764  lea     rax, ??_7CWbemObjectSite@@6B@; const CWbemObjectSite::`vftable'
0x18001176b  mov     [rbx], rax
0x18001176e  mov     [rbx+10h], rcx
0x180011772  test    rcx, rcx
0x180011775  jz      short loc_180011784
0x180011777  mov     rax, [rcx]
0x18001177a  mov     rax, [rax+8]
0x18001177e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011783  nop
0x180011784  mov     [rdi+88h], rbx
0x18001178b  mov     [rdi+18h], rsi
0x18001178f  test    rsi, rsi
0x180011792  jz      short loc_1800117A3
0x180011794  mov     rax, [rsi]
0x180011797  mov     rcx, rsi
0x18001179a  mov     rax, [rax+8]
0x18001179e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800117a3  mov     rcx, rbp; psz
0x1800117a6  call    cs:__imp_SysAllocString
0x1800117ac  mov     [rdi+80h], rax
0x1800117b3  lock inc cs:?g_cObj@@3JA; long g_cObj
0x1800117ba  mov     rax, rdi
0x1800117bd  mov     rbx, [rsp+38h+arg_10]
0x1800117c2  mov     rbp, [rsp+38h+arg_18]
0x1800117c7  add     rsp, 20h
0x1800117cb  pop     r14
0x1800117cd  pop     rdi
0x1800117ce  pop     rsi
0x1800117cf  retn
0x1800117d0  mov     rbx, r14
0x1800117d3  jmp     short loc_180011784
```
