# CSWbemEventSource::CSWbemEventSource(CSWbemServices *,IEnumWbemClassObject *)

- ea: `0x18001f078`
- end: `0x18001f1a8`
- name: `??0CSWbemEventSource@@QEAA@PEAVCSWbemServices@@PEAUIEnumWbemClassObject@@@Z`
- size: `304`
- prototype: `CSWbemEventSource *__fastcall(struct IDispatch *this, struct CSWbemServices *, struct IEnumWbemClassObject *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18001d830`

## callees

- `0x180003170`
- `0x18000a270`
- `0x1800126c0`
- `0x18001f078`
- `0x180036010`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001f15c`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001f15c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct IDispatch *__fastcall CSWbemEventSource::CSWbemEventSource(
        struct IDispatch *this,
        struct IDispatchVtbl *a2,
        struct IUnknown *a3)
{
  struct IDispatch *v6; // rcx
  struct ISWbemSecurity *SecurityInfo; // rdi
  CSWbemSecurity *v8; // rax
  GUID v10; // [rsp+30h] [rbp-28h] BYREF
  GUID v11; // [rsp+40h] [rbp-18h] BYREF

  this->lpVtbl = (struct IDispatchVtbl *)&CSWbemEventSource::`vftable'{for `ISWbemEventSource'};
  this[1].lpVtbl = (struct IDispatchVtbl *)&CSWbemEventSource::`vftable'{for `ISupportErrorInfo'};
  this[2].lpVtbl = (struct IDispatchVtbl *)&CSWbemEventSource::`vftable'{for `IProvideClassInfo'};
  v6 = this + 4;
  v6->lpVtbl = (struct IDispatchVtbl *)&CDispatchHelp::`vftable';
  v6[3].lpVtbl = 0;
  v6[4].lpVtbl = 0;
  v6[5].lpVtbl = 0;
  v6[1].lpVtbl = 0;
  LODWORD(v6[2].lpVtbl) = 0;
  this[14].lpVtbl = 0;
  v10 = CLSID_SWbemEventSource;
  v11 = IID_ISWbemEventSource;
  CDispatchHelp::SetObj((CDispatchHelp *)v6, this, &v11, &v10, L"SWbemEventSource");
  LODWORD(this[15].lpVtbl) = 0;
  this[3].lpVtbl = a2;
  if ( a2 )
  {
    (*((void (__fastcall **)(struct IDispatchVtbl *))a2->QueryInterface + 1))(a2);
    SecurityInfo = (struct ISWbemSecurity *)CSWbemServices::GetSecurityInfo((CSWbemServices *)this[3].lpVtbl);
    if ( SecurityInfo )
    {
      v8 = (CSWbemSecurity *)CWin32DefaultArena::WbemMemAlloc(0x90u);
      if ( v8 )
        v8 = CSWbemSecurity::CSWbemSecurity(v8, a3, SecurityInfo);
      this[14].lpVtbl = (struct IDispatchVtbl *)v8;
      ((void (__fastcall *)(struct ISWbemSecurity *))SecurityInfo->lpVtbl->Release)(SecurityInfo);
    }
  }
  _InterlockedIncrement(&g_cObj);
  return this;
}

```

## disassembly

```asm
0x18001f078  mov     r11, rsp
0x18001f07b  mov     [r11+18h], rbx
0x18001f07f  mov     [r11+20h], rsi
0x18001f083  mov     [r11+8], rcx
0x18001f087  push    rdi
0x18001f088  sub     rsp, 50h
0x18001f08c  mov     rsi, r8
0x18001f08f  mov     rdi, rdx
0x18001f092  mov     rbx, rcx
0x18001f095  lea     rax, ??_7CSWbemEventSource@@6BISWbemEventSource@@@; const CSWbemEventSource::`vftable'{for `ISWbemEventSource'}
0x18001f09c  mov     [rcx], rax
0x18001f09f  lea     rax, ??_7CSWbemEventSource@@6BISupportErrorInfo@@@; const CSWbemEventSource::`vftable'{for `ISupportErrorInfo'}
0x18001f0a6  mov     [rcx+8], rax
0x18001f0aa  lea     rax, ??_7CSWbemEventSource@@6BIProvideClassInfo@@@; const CSWbemEventSource::`vftable'{for `IProvideClassInfo'}
0x18001f0b1  mov     [rcx+10h], rax
0x18001f0b5  add     rcx, 20h ; ' '; this
0x18001f0b9  lea     rax, ??_7CDispatchHelp@@6B@; const CDispatchHelp::`vftable'
0x18001f0c0  mov     [rcx], rax
0x18001f0c3  mov     qword ptr [rcx+18h], 0
0x18001f0cb  mov     qword ptr [rcx+20h], 0
0x18001f0d3  mov     qword ptr [rcx+28h], 0
0x18001f0db  mov     qword ptr [rcx+8], 0
0x18001f0e3  mov     dword ptr [rcx+10h], 0
0x18001f0ea  mov     qword ptr [rbx+70h], 0
0x18001f0f2  movups  xmm0, xmmword ptr cs:CLSID_SWbemEventSource.Data1
0x18001f0f9  movdqu  [rsp+58h+var_28], xmm0
0x18001f0ff  movups  xmm1, xmmword ptr cs:IID_ISWbemEventSource.Data1
0x18001f106  movdqu  xmmword ptr [rsp+58h+var_18.Data1], xmm1
0x18001f10c  lea     rax, aSwbemeventsour; "SWbemEventSource"
0x18001f113  mov     [r11-38h], rax
0x18001f117  lea     r9, [r11-28h]; struct _GUID *
0x18001f11b  lea     r8, [r11-18h]; struct _GUID *
0x18001f11f  mov     rdx, rbx; struct IDispatch *
0x18001f122  call    ?SetObj@CDispatchHelp@@QEAAXPEAUIDispatch@@U_GUID@@1PEAG@Z; CDispatchHelp::SetObj(IDispatch *,_GUID,_GUID,ushort *)
0x18001f127  mov     dword ptr [rbx+78h], 0
0x18001f12e  mov     [rbx+18h], rdi
0x18001f132  test    rdi, rdi
0x18001f135  jz      short loc_18001F18E
0x18001f137  mov     rax, [rdi]
0x18001f13a  mov     rcx, rdi
0x18001f13d  mov     rax, [rax+8]
0x18001f141  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f146  mov     rcx, [rbx+18h]; this
0x18001f14a  call    ?GetSecurityInfo@CSWbemServices@@QEAAPEAVCSWbemSecurity@@XZ; CSWbemServices::GetSecurityInfo(void)
0x18001f14f  mov     rdi, rax
0x18001f152  test    rax, rax
0x18001f155  jz      short loc_18001F18E
0x18001f157  mov     ecx, 90h
0x18001f15c  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18001f162  mov     [rsp+58h+arg_8], rax
0x18001f167  test    rax, rax
0x18001f16a  jz      short loc_18001F17B
0x18001f16c  mov     r8, rdi; struct CSWbemSecurity *
0x18001f16f  mov     rdx, rsi; struct IUnknown *
0x18001f172  mov     rcx, rax; this
0x18001f175  call    ??0CSWbemSecurity@@QEAA@PEAUIUnknown@@PEAV0@@Z; CSWbemSecurity::CSWbemSecurity(IUnknown *,CSWbemSecurity *)
0x18001f17a  nop
0x18001f17b  mov     [rbx+70h], rax
0x18001f17f  mov     rax, [rdi]
0x18001f182  mov     rcx, rdi
0x18001f185  mov     rax, [rax+10h]
0x18001f189  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f18e  lock inc cs:?g_cObj@@3JA; long g_cObj
0x18001f195  mov     rax, rbx
0x18001f198  mov     rbx, [rsp+58h+arg_10]
0x18001f19d  mov     rsi, [rsp+58h+arg_18]
0x18001f1a2  add     rsp, 50h
0x18001f1a6  pop     rdi
0x18001f1a7  retn
```
