# CSWbemHiPerfObjectSet::CSWbemHiPerfObjectSet(CSWbemServices *,IWbemHiPerfEnum *)

- ea: `0x1800307ac`
- end: `0x1800308e7`
- name: `??0CSWbemHiPerfObjectSet@@QEAA@PEAVCSWbemServices@@PEAUIWbemHiPerfEnum@@@Z`
- size: `315`
- prototype: `CSWbemHiPerfObjectSet *__fastcall(struct IDispatch *this, struct CSWbemServices *, struct IWbemHiPerfEnum *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1800308f0`

## callees

- `0x180003170`
- `0x180011b50`
- `0x1800126c0`
- `0x1800307ac`
- `0x180036010`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003089e`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003089e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct IDispatch *__fastcall CSWbemHiPerfObjectSet::CSWbemHiPerfObjectSet(
        struct IDispatch *this,
        struct IDispatchVtbl *a2,
        struct IDispatchVtbl *a3)
{
  struct IDispatch *v4; // rcx
  struct IDispatchVtbl *lpVtbl; // rcx
  struct IDispatchVtbl *v6; // rcx
  struct CSWbemSecurity *SecurityInfo; // rdi
  CSWbemSecurity *v8; // rax
  GUID v10; // [rsp+30h] [rbp-28h] BYREF
  GUID v11; // [rsp+40h] [rbp-18h] BYREF

  this->lpVtbl = (struct IDispatchVtbl *)&CSWbemHiPerfObjectSet::`vftable'{for `ISWbemObjectSet'};
  this[1].lpVtbl = (struct IDispatchVtbl *)&CSWbemHiPerfObjectSet::`vftable'{for `ISupportErrorInfo'};
  this[2].lpVtbl = (struct IDispatchVtbl *)&CSWbemHiPerfObjectSet::`vftable'{for `IProvideClassInfo'};
  this[3].lpVtbl = a2;
  v4 = this + 4;
  v4->lpVtbl = (struct IDispatchVtbl *)&CDispatchHelp::`vftable';
  v4[3].lpVtbl = 0;
  v4[4].lpVtbl = 0;
  v4[5].lpVtbl = 0;
  v4[1].lpVtbl = 0;
  LODWORD(v4[2].lpVtbl) = 0;
  this[14].lpVtbl = 0;
  this[15].lpVtbl = a3;
  LODWORD(this[16].lpVtbl) = 0;
  v10 = CLSID_SWbemObjectSet;
  v11 = IID_ISWbemObjectSet;
  CDispatchHelp::SetObj((CDispatchHelp *)v4, this, &v11, &v10, (OLECHAR *)L"SWbemObjectSet");
  lpVtbl = this[15].lpVtbl;
  if ( lpVtbl )
    (*((void (__fastcall **)(struct IDispatchVtbl *))lpVtbl->QueryInterface + 1))(lpVtbl);
  v6 = this[3].lpVtbl;
  if ( v6 )
  {
    (*((void (__fastcall **)(struct IDispatchVtbl *))v6->QueryInterface + 1))(v6);
    SecurityInfo = CSWbemServices::GetSecurityInfo((CSWbemServices *)this[3].lpVtbl);
    v8 = (CSWbemSecurity *)CWin32DefaultArena::WbemMemAlloc(0x90u);
    if ( v8 )
      v8 = CSWbemSecurity::CSWbemSecurity(v8, SecurityInfo);
    this[14].lpVtbl = (struct IDispatchVtbl *)v8;
    if ( SecurityInfo )
      (*(void (__fastcall **)(struct CSWbemSecurity *))(*(_QWORD *)SecurityInfo + 16LL))(SecurityInfo);
  }
  _InterlockedIncrement(&g_cObj);
  return this;
}

```

## disassembly

```asm
0x1800307ac  mov     r11, rsp
0x1800307af  mov     [r11+18h], rbx
0x1800307b3  mov     [r11+8], rcx
0x1800307b7  push    rdi
0x1800307b8  sub     rsp, 50h
0x1800307bc  mov     rbx, rcx
0x1800307bf  lea     rax, ??_7CSWbemHiPerfObjectSet@@6BISWbemObjectSet@@@; const CSWbemHiPerfObjectSet::`vftable'{for `ISWbemObjectSet'}
0x1800307c6  mov     [rcx], rax
0x1800307c9  lea     rax, ??_7CSWbemHiPerfObjectSet@@6BISupportErrorInfo@@@; const CSWbemHiPerfObjectSet::`vftable'{for `ISupportErrorInfo'}
0x1800307d0  mov     [rcx+8], rax
0x1800307d4  lea     rax, ??_7CSWbemHiPerfObjectSet@@6BIProvideClassInfo@@@; const CSWbemHiPerfObjectSet::`vftable'{for `IProvideClassInfo'}
0x1800307db  mov     [rcx+10h], rax
0x1800307df  mov     [rcx+18h], rdx
0x1800307e3  add     rcx, 20h ; ' '; this
0x1800307e7  lea     rax, ??_7CDispatchHelp@@6B@; const CDispatchHelp::`vftable'
0x1800307ee  mov     [rcx], rax
0x1800307f1  mov     qword ptr [rcx+18h], 0
0x1800307f9  mov     qword ptr [rcx+20h], 0
0x180030801  mov     qword ptr [rcx+28h], 0
0x180030809  mov     qword ptr [rcx+8], 0
0x180030811  mov     dword ptr [rcx+10h], 0
0x180030818  mov     qword ptr [rbx+70h], 0
0x180030820  mov     [rbx+78h], r8
0x180030824  mov     dword ptr [rbx+80h], 0
0x18003082e  movups  xmm0, xmmword ptr cs:CLSID_SWbemObjectSet.Data1
0x180030835  movdqu  [rsp+58h+var_28], xmm0
0x18003083b  movups  xmm1, xmmword ptr cs:IID_ISWbemObjectSet.Data1
0x180030842  movdqu  xmmword ptr [rsp+58h+var_18.Data1], xmm1
0x180030848  lea     rax, aSwbemobjectset; "SWbemObjectSet"
0x18003084f  mov     [r11-38h], rax
0x180030853  lea     r9, [r11-28h]; struct _GUID *
0x180030857  lea     r8, [r11-18h]; struct _GUID *
0x18003085b  mov     rdx, rbx; struct IDispatch *
0x18003085e  call    ?SetObj@CDispatchHelp@@QEAAXPEAUIDispatch@@U_GUID@@1PEAG@Z; CDispatchHelp::SetObj(IDispatch *,_GUID,_GUID,ushort *)
0x180030863  mov     rcx, [rbx+78h]
0x180030867  test    rcx, rcx
0x18003086a  jz      short loc_180030878
0x18003086c  mov     rax, [rcx]
0x18003086f  mov     rax, [rax+8]
0x180030873  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030878  mov     rcx, [rbx+18h]
0x18003087c  test    rcx, rcx
0x18003087f  jz      short loc_1800308D2
0x180030881  mov     rax, [rcx]
0x180030884  mov     rax, [rax+8]
0x180030888  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003088d  mov     rcx, [rbx+18h]; this
0x180030891  call    ?GetSecurityInfo@CSWbemServices@@QEAAPEAVCSWbemSecurity@@XZ; CSWbemServices::GetSecurityInfo(void)
0x180030896  mov     rdi, rax
0x180030899  mov     ecx, 90h
0x18003089e  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800308a4  mov     [rsp+58h+arg_8], rax
0x1800308a9  test    rax, rax
0x1800308ac  jz      short loc_1800308BA
0x1800308ae  mov     rdx, rdi; struct CSWbemSecurity *
0x1800308b1  mov     rcx, rax; this
0x1800308b4  call    ??0CSWbemSecurity@@QEAA@PEAV0@@Z; CSWbemSecurity::CSWbemSecurity(CSWbemSecurity *)
0x1800308b9  nop
0x1800308ba  mov     [rbx+70h], rax
0x1800308be  test    rdi, rdi
0x1800308c1  jz      short loc_1800308D2
0x1800308c3  mov     rax, [rdi]
0x1800308c6  mov     rcx, rdi
0x1800308c9  mov     rax, [rax+10h]
0x1800308cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800308d2  lock inc cs:?g_cObj@@3JA; long g_cObj
0x1800308d9  mov     rax, rbx
0x1800308dc  mov     rbx, [rsp+58h+arg_10]
0x1800308e1  add     rsp, 50h
0x1800308e5  pop     rdi
0x1800308e6  retn
```
