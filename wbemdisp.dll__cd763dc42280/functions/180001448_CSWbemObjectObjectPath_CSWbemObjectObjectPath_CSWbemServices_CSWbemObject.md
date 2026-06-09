# CSWbemObjectObjectPath::CSWbemObjectObjectPath(CSWbemServices *,CSWbemObject *)

- ea: `0x180001448`
- end: `0x1800015e5`
- name: `??0CSWbemObjectObjectPath@@QEAA@PEAVCSWbemServices@@PEAVCSWbemObject@@@Z`
- size: `413`
- prototype: `CSWbemObjectObjectPath *(CSWbemObjectObjectPath *__hidden this, struct CSWbemServices *, struct CSWbemObject *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180001370`

## callees

- `0x180001448`
- `0x1800017d0`
- `0x1800017fc`
- `0x18001fbfc`
- `0x18001fc10`
- `0x1800204ac`
- `0x1800204c0`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800015a3`
- `OLEAUT32!__imp_SysAllocString` at `0x1800015a3`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800014f0`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000155d`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800014f0`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000155d`

## string_xrefs

- `0x18000159c`: `SWbemObjectPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
CSWbemObjectObjectPath *__fastcall CSWbemObjectObjectPath::CSWbemObjectObjectPath(
        CSWbemObjectObjectPath *this,
        struct CSWbemServices *a2,
        struct CSWbemObject *a3)
{
  CSWbemObject *v6; // r8
  _DWORD *v7; // rax
  _DWORD *v8; // rdi
  __int64 v9; // rcx
  CSWbemObjectObjectPathSecurity *v10; // rax
  char v12; // [rsp+48h] [rbp+10h] BYREF
  CSWbemObjectObjectPathSecurity *v13; // [rsp+50h] [rbp+18h]

  *(_QWORD *)this = &CSWbemObjectObjectPath::`vftable'{for `ISWbemObjectPath'};
  *((_QWORD *)this + 1) = &CSWbemObjectObjectPath::`vftable'{for `ISupportErrorInfo'};
  *((_QWORD *)this + 2) = &CSWbemObjectObjectPath::`vftable'{for `IProvideClassInfo'};
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = a2;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_DWORD *)this + 14) = 0;
  *((_QWORD *)this + 5) = &CSWbemObjectObjectPath::CObjectObjectPathDispatchHelp::`vftable';
  *((_QWORD *)this + 15) = 0;
  _InterlockedIncrement(&g_cObj);
  std::unique_ptr<CWbemSite>::unique_ptr<CWbemSite>(&v12);
  if ( v6 )
  {
    *((_QWORD *)this + 3) = CSWbemObject::GetIWbemClassObject(v6);
    v7 = CWin32DefaultArena::WbemMemAlloc(0x18u);
    v8 = v7;
    v13 = (CSWbemObjectObjectPathSecurity *)v7;
    if ( v7 )
    {
      v7[2] = 1;
      *(_QWORD *)v7 = &CWbemObjectSite::`vftable';
      *((_QWORD *)v7 + 2) = (char *)a3 + 16;
      if ( a3 != (struct CSWbemObject *)-16LL )
        (*(void (__fastcall **)(char *))(*((_QWORD *)a3 + 2) + 8LL))((char *)a3 + 16);
    }
    else
    {
      v8 = 0;
    }
    *((_QWORD *)this + 15) = v8;
    std::unique_ptr<CWbemSite>::reset(&v12, v8);
  }
  v9 = *((_QWORD *)this + 4);
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
  v10 = (CSWbemObjectObjectPathSecurity *)CWin32DefaultArena::WbemMemAlloc(0x88u);
  v13 = v10;
  if ( v10 )
    v10 = CSWbemObjectObjectPathSecurity::CSWbemObjectObjectPathSecurity(v10, a2);
  *((_QWORD *)this + 16) = v10;
  *((_QWORD *)this + 10) = this;
  *(GUID *)((char *)this + 88) = IID_ISWbemObjectPath;
  *(GUID *)((char *)this + 104) = CLSID_SWbemObjectPath;
  *((_QWORD *)this + 6) = SysAllocString(L"SWbemObjectPath");
  *((_DWORD *)this + 34) = 0;
  std::unique_ptr<CWbemSite>::release(&v12);
  std::unique_ptr<CWbemSite>::~unique_ptr<CWbemSite>(&v12);
  return this;
}

```

## disassembly

```asm
0x180001448  mov     [rsp+arg_18], rbx
0x18000144d  mov     [rsp+arg_0], rcx
0x180001452  push    rbp
0x180001453  push    rsi
0x180001454  push    rdi
0x180001455  sub     rsp, 20h
0x180001459  mov     rsi, r8
0x18000145c  mov     rbp, rdx
0x18000145f  mov     rbx, rcx
0x180001462  lea     rax, ??_7CSWbemObjectObjectPath@@6BISWbemObjectPath@@@; const CSWbemObjectObjectPath::`vftable'{for `ISWbemObjectPath'}
0x180001469  mov     [rcx], rax
0x18000146c  lea     rax, ??_7CSWbemObjectObjectPath@@6BISupportErrorInfo@@@; const CSWbemObjectObjectPath::`vftable'{for `ISupportErrorInfo'}
0x180001473  mov     [rcx+8], rax
0x180001477  lea     rax, ??_7CSWbemObjectObjectPath@@6BIProvideClassInfo@@@; const CSWbemObjectObjectPath::`vftable'{for `IProvideClassInfo'}
0x18000147e  mov     [rcx+10h], rax
0x180001482  mov     qword ptr [rcx+18h], 0
0x18000148a  mov     [rcx+20h], rdx
0x18000148e  mov     qword ptr [rcx+40h], 0
0x180001496  mov     qword ptr [rcx+48h], 0
0x18000149e  mov     qword ptr [rcx+50h], 0
0x1800014a6  mov     qword ptr [rcx+30h], 0
0x1800014ae  mov     dword ptr [rcx+38h], 0
0x1800014b5  lea     rax, ??_7CObjectObjectPathDispatchHelp@CSWbemObjectObjectPath@@6B@; const CSWbemObjectObjectPath::CObjectObjectPathDispatchHelp::`vftable'
0x1800014bc  mov     [rcx+28h], rax
0x1800014c0  mov     qword ptr [rcx+78h], 0
0x1800014c8  lock inc cs:?g_cObj@@3JA; long g_cObj
0x1800014cf  lea     rcx, [rsp+38h+arg_8]
0x1800014d4  call    ??0?$unique_ptr@VCWbemSite@@U?$default_delete@VCWbemSite@@@std@@@std@@QEAA@XZ; std::unique_ptr<CWbemSite>::unique_ptr<CWbemSite>(void)
0x1800014d9  nop
0x1800014da  test    r8, r8
0x1800014dd  jz      short loc_180001543
0x1800014df  mov     rcx, r8; this
0x1800014e2  call    ?GetIWbemClassObject@CSWbemObject@@QEAAPEAUIWbemClassObject@@XZ; CSWbemObject::GetIWbemClassObject(void)
0x1800014e7  mov     [rbx+18h], rax
0x1800014eb  mov     ecx, 18h
0x1800014f0  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800014f6  mov     rdi, rax
0x1800014f9  mov     [rsp+38h+arg_10], rax
0x1800014fe  test    rax, rax
0x180001501  jz      loc_1800015DD
0x180001507  lea     rcx, [rsi+10h]
0x18000150b  mov     dword ptr [rax+8], 1
0x180001512  lea     rax, ??_7CWbemObjectSite@@6B@; const CWbemObjectSite::`vftable'
0x180001519  mov     [rdi], rax
0x18000151c  mov     [rdi+10h], rcx
0x180001520  test    rcx, rcx
0x180001523  jz      short loc_180001532
0x180001525  mov     rax, [rcx]
0x180001528  mov     rax, [rax+8]
0x18000152c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001531  nop
0x180001532  mov     [rbx+78h], rdi
0x180001536  mov     rdx, rdi
0x180001539  lea     rcx, [rsp+38h+arg_8]
0x18000153e  call    ?reset@?$unique_ptr@VCWbemSite@@U?$default_delete@VCWbemSite@@@std@@@std@@QEAAXPEAVCWbemSite@@@Z; std::unique_ptr<CWbemSite>::reset(CWbemSite *)
0x180001543  mov     rcx, [rbx+20h]
0x180001547  test    rcx, rcx
0x18000154a  jz      short loc_180001558
0x18000154c  mov     rax, [rcx]
0x18000154f  mov     rax, [rax+8]
0x180001553  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001558  mov     ecx, 88h
0x18000155d  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180001563  mov     [rsp+38h+arg_10], rax
0x180001568  test    rax, rax
0x18000156b  jz      short loc_180001579
0x18000156d  mov     rdx, rbp; struct CSWbemServices *
0x180001570  mov     rcx, rax; this
0x180001573  call    ??0CSWbemObjectObjectPathSecurity@@QEAA@PEAVCSWbemServices@@@Z; CSWbemObjectObjectPathSecurity::CSWbemObjectObjectPathSecurity(CSWbemServices *)
0x180001578  nop
0x180001579  mov     [rbx+80h], rax
0x180001580  movups  xmm1, xmmword ptr cs:CLSID_SWbemObjectPath.Data1
0x180001587  movups  xmm0, xmmword ptr cs:IID_ISWbemObjectPath.Data1
0x18000158e  mov     [rbx+50h], rbx
0x180001592  movdqu  xmmword ptr [rbx+58h], xmm0
0x180001597  movdqu  xmmword ptr [rbx+68h], xmm1
0x18000159c  lea     rcx, aSwbemobjectpat; "SWbemObjectPath"
0x1800015a3  call    cs:__imp_SysAllocString
0x1800015a9  mov     [rbx+30h], rax
0x1800015ad  mov     dword ptr [rbx+88h], 0
0x1800015b7  lea     rcx, [rsp+38h+arg_8]
0x1800015bc  call    ?release@?$unique_ptr@VCWbemSite@@U?$default_delete@VCWbemSite@@@std@@@std@@QEAAPEAVCWbemSite@@XZ; std::unique_ptr<CWbemSite>::release(void)
0x1800015c1  nop
0x1800015c2  lea     rcx, [rsp+38h+arg_8]
0x1800015c7  call    ??1?$unique_ptr@VCWbemSite@@U?$default_delete@VCWbemSite@@@std@@@std@@QEAA@XZ; std::unique_ptr<CWbemSite>::~unique_ptr<CWbemSite>(void)
0x1800015cc  nop
0x1800015cd  mov     rax, rbx
0x1800015d0  mov     rbx, [rsp+38h+arg_18]
0x1800015d5  add     rsp, 20h
0x1800015d9  pop     rdi
0x1800015da  pop     rsi
0x1800015db  pop     rbp
0x1800015dc  retn
0x1800015dd  xor     edi, edi
0x1800015df  jmp     loc_180001532
```
