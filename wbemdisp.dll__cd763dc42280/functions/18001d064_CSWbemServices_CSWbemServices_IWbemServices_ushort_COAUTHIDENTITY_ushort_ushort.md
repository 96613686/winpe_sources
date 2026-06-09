# CSWbemServices::CSWbemServices(IWbemServices *,ushort *,_COAUTHIDENTITY *,ushort *,ushort *)

- ea: `0x18001d064`
- end: `0x18001d1d6`
- name: `??0CSWbemServices@@QEAA@PEAUIWbemServices@@PEAGPEAU_COAUTHIDENTITY@@11@Z`
- size: `370`
- prototype: `CSWbemServices *__usercall@<rax>(struct IDispatch *this@<rcx>, struct IWbemServices *@<rdx>, unsigned __int16 *@<r8>, struct _COAUTHIDENTITY *@<r9>, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18001e408`

## callees

- `0x1800126c0`
- `0x180017ce0`
- `0x18001d064`
- `0x18001e8bc`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001d16e`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001d16e`

## string_xrefs

- `0x18001d14e`: `SWbemServicesEx`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
struct IDispatch *__fastcall CSWbemServices::CSWbemServices(
        struct IDispatch *this,
        struct IUnknown *a2,
        unsigned __int16 *a3,
        struct _COAUTHIDENTITY *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6)
{
  struct IDispatch *v10; // rcx
  struct IDispatch *v11; // rax
  GUID v13; // [rsp+30h] [rbp-38h] BYREF
  GUID v14; // [rsp+40h] [rbp-28h] BYREF

  this->lpVtbl = (struct IDispatchVtbl *)&CSWbemServices::`vftable'{for `ISWbemServicesEx'};
  this[1].lpVtbl = (struct IDispatchVtbl *)&CSWbemServices::`vftable'{for `IDispatchEx'};
  this[2].lpVtbl = (struct IDispatchVtbl *)&CSWbemServices::`vftable'{for `ISupportErrorInfo'};
  this[3].lpVtbl = (struct IDispatchVtbl *)&CSWbemServices::`vftable'{for `ISWbemInternalServices'};
  this[4].lpVtbl = (struct IDispatchVtbl *)&CSWbemServices::`vftable'{for `IProvideClassInfo'};
  this[5].lpVtbl = 0;
  this[6].lpVtbl = 0;
  v10 = this + 7;
  v10->lpVtbl = (struct IDispatchVtbl *)&CDispatchHelp::`vftable';
  v10[3].lpVtbl = 0;
  v10[4].lpVtbl = 0;
  v10[5].lpVtbl = 0;
  v10[1].lpVtbl = 0;
  LODWORD(v10[2].lpVtbl) = 0;
  this[17].lpVtbl = 0;
  this[18].lpVtbl = 0;
  this[19].lpVtbl = 0;
  LODWORD(this[20].lpVtbl) = 0;
  _InterlockedIncrement(&g_cObj);
  v13 = CLSID_SWbemServicesEx;
  v14 = IID_ISWbemServicesEx;
  CDispatchHelp::SetObj((CDispatchHelp *)v10, this, &v14, &v13, (OLECHAR *)L"SWbemServicesEx");
  v11 = (struct IDispatch *)CWin32DefaultArena::WbemMemAlloc(0x90u);
  if ( v11 )
    v11 = CSWbemSecurity::CSWbemSecurity(v11, a2, a4, a5, a6);
  this[17].lpVtbl = (struct IDispatchVtbl *)v11;
  if ( a3 )
    ATL::CComBSTR::operator=(&this[5]);
  return this;
}

```

## disassembly

```asm
0x18001d064  mov     r11, rsp
0x18001d067  mov     [r11+10h], rbx
0x18001d06b  mov     [r11+20h], rbp
0x18001d06f  mov     [r11+8], rcx
0x18001d073  push    rsi
0x18001d074  push    rdi
0x18001d075  push    r14
0x18001d077  sub     rsp, 50h
0x18001d07b  mov     rbp, r9
0x18001d07e  mov     rdi, r8
0x18001d081  mov     r14, rdx
0x18001d084  mov     rbx, rcx
0x18001d087  lea     rax, ??_7CSWbemServices@@6BISWbemServicesEx@@@; const CSWbemServices::`vftable'{for `ISWbemServicesEx'}
0x18001d08e  mov     [rcx], rax
0x18001d091  lea     rax, ??_7CSWbemServices@@6BIDispatchEx@@@; const CSWbemServices::`vftable'{for `IDispatchEx'}
0x18001d098  mov     [rcx+8], rax
0x18001d09c  lea     rax, ??_7CSWbemServices@@6BISupportErrorInfo@@@; const CSWbemServices::`vftable'{for `ISupportErrorInfo'}
0x18001d0a3  mov     [rcx+10h], rax
0x18001d0a7  lea     rax, ??_7CSWbemServices@@6BISWbemInternalServices@@@; const CSWbemServices::`vftable'{for `ISWbemInternalServices'}
0x18001d0ae  mov     [rcx+18h], rax
0x18001d0b2  lea     rax, ??_7CSWbemServices@@6BIProvideClassInfo@@@; const CSWbemServices::`vftable'{for `IProvideClassInfo'}
0x18001d0b9  mov     [rcx+20h], rax
0x18001d0bd  mov     qword ptr [rcx+28h], 0
0x18001d0c5  mov     qword ptr [rcx+30h], 0
0x18001d0cd  add     rcx, 38h ; '8'; this
0x18001d0d1  lea     rax, ??_7CDispatchHelp@@6B@; const CDispatchHelp::`vftable'
0x18001d0d8  mov     [rcx], rax
0x18001d0db  mov     qword ptr [rcx+18h], 0
0x18001d0e3  mov     qword ptr [rcx+20h], 0
0x18001d0eb  mov     qword ptr [rcx+28h], 0
0x18001d0f3  mov     qword ptr [rcx+8], 0
0x18001d0fb  mov     dword ptr [rcx+10h], 0
0x18001d102  mov     qword ptr [rbx+88h], 0
0x18001d10d  mov     qword ptr [rbx+90h], 0
0x18001d118  mov     qword ptr [rbx+98h], 0
0x18001d123  mov     dword ptr [rbx+0A0h], 0
0x18001d12d  lock inc cs:?g_cObj@@3JA; long g_cObj
0x18001d134  movups  xmm0, xmmword ptr cs:CLSID_SWbemServicesEx.Data1
0x18001d13b  movdqu  [rsp+68h+var_38], xmm0
0x18001d141  movups  xmm1, xmmword ptr cs:IID_ISWbemServicesEx.Data1
0x18001d148  movdqu  [rsp+68h+var_28], xmm1
0x18001d14e  lea     rax, aSwbemservicese; "SWbemServicesEx"
0x18001d155  mov     [r11-48h], rax
0x18001d159  lea     r9, [r11-38h]; struct _GUID *
0x18001d15d  lea     r8, [r11-28h]; struct _GUID *
0x18001d161  mov     rdx, rbx; struct IDispatch *
0x18001d164  call    ?SetObj@CDispatchHelp@@QEAAXPEAUIDispatch@@U_GUID@@1PEAG@Z; CDispatchHelp::SetObj(IDispatch *,_GUID,_GUID,ushort *)
0x18001d169  mov     ecx, 90h
0x18001d16e  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18001d174  mov     [rsp+68h+arg_10], rax
0x18001d17c  test    rax, rax
0x18001d17f  jz      short loc_18001D1A5
0x18001d181  mov     rcx, [rsp+68h+arg_28]
0x18001d189  mov     [rsp+68h+var_48], rcx; unsigned __int16 *
0x18001d18e  mov     r9, [rsp+68h+arg_20]; unsigned __int16 *
0x18001d196  mov     r8, rbp; struct _COAUTHIDENTITY *
0x18001d199  mov     rdx, r14; struct IUnknown *
0x18001d19c  mov     rcx, rax; this
0x18001d19f  call    ??0CSWbemSecurity@@QEAA@PEAUIUnknown@@PEAU_COAUTHIDENTITY@@PEAG2@Z; CSWbemSecurity::CSWbemSecurity(IUnknown *,_COAUTHIDENTITY *,ushort *,ushort *)
0x18001d1a4  nop
0x18001d1a5  mov     [rbx+88h], rax
0x18001d1ac  test    rdi, rdi
0x18001d1af  jz      short loc_18001D1BE
0x18001d1b1  mov     rdx, rdi
0x18001d1b4  lea     rcx, [rbx+28h]
0x18001d1b8  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18001d1bd  nop
0x18001d1be  mov     rax, rbx
0x18001d1c1  lea     r11, [rsp+68h+var_18]
0x18001d1c6  mov     rbx, [r11+28h]
0x18001d1ca  mov     rbp, [r11+38h]
0x18001d1ce  mov     rsp, r11
0x18001d1d1  pop     r14
0x18001d1d3  pop     rdi
0x18001d1d4  pop     rsi
0x18001d1d5  retn
```
