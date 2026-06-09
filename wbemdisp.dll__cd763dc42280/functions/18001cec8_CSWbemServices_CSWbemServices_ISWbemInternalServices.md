# CSWbemServices::CSWbemServices(ISWbemInternalServices *)

- ea: `0x18001cec8`
- end: `0x18001d05e`
- name: `??0CSWbemServices@@QEAA@PEAUISWbemInternalServices@@@Z`
- size: `406`
- prototype: `CSWbemServices *__fastcall(struct IDispatch *this, struct ISWbemInternalServices *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1800308f0`

## callees

- `0x18000c0b0`
- `0x1800126c0`
- `0x18001cec8`
- `0x18001e5dc`
- `0x180036010`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001d008`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001d008`

## string_xrefs

- `0x18001cf80`: `SWbemServicesEx`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
struct IDispatch *__fastcall CSWbemServices::CSWbemServices(struct IDispatch *this, struct ISWbemInternalServices *a2)
{
  struct IDispatch *v4; // rcx
  struct IDispatch *v5; // rax
  struct IDispatch *v6; // rax
  struct _GUID v8; // [rsp+30h] [rbp-28h] BYREF
  struct _GUID v9; // [rsp+40h] [rbp-18h] BYREF
  struct ISWbemInternalSecurity *v10; // [rsp+98h] [rbp+40h] BYREF
  struct IUnknown *v11; // [rsp+A0h] [rbp+48h] BYREF
  struct IDispatch *v12; // [rsp+A8h] [rbp+50h]

  this->lpVtbl = (struct IDispatchVtbl *)&CSWbemServices::`vftable'{for `ISWbemServicesEx'};
  this[1].lpVtbl = (struct IDispatchVtbl *)&CSWbemServices::`vftable'{for `IDispatchEx'};
  this[2].lpVtbl = (struct IDispatchVtbl *)&CSWbemServices::`vftable'{for `ISupportErrorInfo'};
  this[3].lpVtbl = (struct IDispatchVtbl *)&CSWbemServices::`vftable'{for `ISWbemInternalServices'};
  this[4].lpVtbl = (struct IDispatchVtbl *)&CSWbemServices::`vftable'{for `IProvideClassInfo'};
  this[5].lpVtbl = 0;
  this[6].lpVtbl = 0;
  v4 = this + 7;
  v4->lpVtbl = (struct IDispatchVtbl *)&CDispatchHelp::`vftable';
  v4[3].lpVtbl = 0;
  v4[4].lpVtbl = 0;
  v4[5].lpVtbl = 0;
  v4[1].lpVtbl = 0;
  LODWORD(v4[2].lpVtbl) = 0;
  this[17].lpVtbl = 0;
  this[18].lpVtbl = 0;
  this[19].lpVtbl = 0;
  LODWORD(this[20].lpVtbl) = 0;
  _InterlockedIncrement(&g_cObj);
  v8 = CLSID_SWbemServicesEx;
  v9 = IID_ISWbemServicesEx;
  CDispatchHelp::SetObj((CDispatchHelp *)v4, this, &v9, &v8, (OLECHAR *)L"SWbemServicesEx");
  if ( a2 )
  {
    (*(void (__fastcall **)(struct ISWbemInternalServices *, struct IDispatch *))(*(_QWORD *)a2 + 40LL))(a2, this + 6);
    (*(void (__fastcall **)(struct ISWbemInternalServices *, struct IDispatch *))(*(_QWORD *)a2 + 32LL))(a2, this + 5);
    v10 = 0;
    (*(void (__fastcall **)(struct ISWbemInternalServices *, struct ISWbemInternalSecurity **))(*(_QWORD *)a2 + 48LL))(
      a2,
      &v10);
    if ( v10 )
    {
      v11 = 0;
      if ( (*(int (__fastcall **)(struct ISWbemInternalServices *, struct IUnknown **))(*(_QWORD *)a2 + 24LL))(a2, &v11) >= 0 )
      {
        v5 = (struct IDispatch *)CWin32DefaultArena::WbemMemAlloc(0x90u);
        v12 = v5;
        if ( v5 )
          v6 = CSWbemSecurity::CSWbemSecurity(v5, v11, v10);
        else
          v6 = 0;
        this[17].lpVtbl = (struct IDispatchVtbl *)v6;
        (*(void (__fastcall **)(struct ISWbemInternalSecurity *))(*(_QWORD *)v10 + 16LL))(v10);
      }
      ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::~CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>(&v11);
    }
  }
  return this;
}

```

## disassembly

```asm
0x18001cec8  mov     [rsp-30h+arg_0], rcx
0x18001cecd  push    rbp
0x18001cece  push    rbx
0x18001cecf  push    rsi
0x18001ced0  push    rdi
0x18001ced1  push    r14
0x18001ced3  push    r15
0x18001ced5  mov     rbp, rsp
0x18001ced8  sub     rsp, 58h
0x18001cedc  mov     rdi, rdx
0x18001cedf  mov     rbx, rcx
0x18001cee2  lea     rax, ??_7CSWbemServices@@6BISWbemServicesEx@@@; const CSWbemServices::`vftable'{for `ISWbemServicesEx'}
0x18001cee9  mov     [rcx], rax
0x18001ceec  lea     rax, ??_7CSWbemServices@@6BIDispatchEx@@@; const CSWbemServices::`vftable'{for `IDispatchEx'}
0x18001cef3  mov     [rcx+8], rax
0x18001cef7  lea     rax, ??_7CSWbemServices@@6BISupportErrorInfo@@@; const CSWbemServices::`vftable'{for `ISupportErrorInfo'}
0x18001cefe  mov     [rcx+10h], rax
0x18001cf02  lea     rax, ??_7CSWbemServices@@6BISWbemInternalServices@@@; const CSWbemServices::`vftable'{for `ISWbemInternalServices'}
0x18001cf09  mov     [rcx+18h], rax
0x18001cf0d  lea     rax, ??_7CSWbemServices@@6BIProvideClassInfo@@@; const CSWbemServices::`vftable'{for `IProvideClassInfo'}
0x18001cf14  mov     [rcx+20h], rax
0x18001cf18  xor     r15d, r15d
0x18001cf1b  mov     [rcx+28h], r15
0x18001cf1f  mov     [rcx+30h], r15
0x18001cf23  add     rcx, 38h ; '8'; this
0x18001cf27  lea     rax, ??_7CDispatchHelp@@6B@; const CDispatchHelp::`vftable'
0x18001cf2e  mov     [rcx], rax
0x18001cf31  mov     [rcx+18h], r15
0x18001cf35  mov     [rcx+20h], r15
0x18001cf39  mov     [rcx+28h], r15
0x18001cf3d  mov     [rcx+8], r15
0x18001cf41  mov     [rcx+10h], r15d
0x18001cf45  mov     [rbx+88h], r15
0x18001cf4c  mov     [rbx+90h], r15
0x18001cf53  mov     [rbx+98h], r15
0x18001cf5a  mov     [rbx+0A0h], r15d
0x18001cf61  lock inc cs:?g_cObj@@3JA; long g_cObj
0x18001cf68  movups  xmm0, xmmword ptr cs:CLSID_SWbemServicesEx.Data1
0x18001cf6f  movdqu  xmmword ptr [rbp+var_28.Data1], xmm0
0x18001cf74  movups  xmm1, xmmword ptr cs:IID_ISWbemServicesEx.Data1
0x18001cf7b  movdqu  xmmword ptr [rbp+var_18.Data1], xmm1
0x18001cf80  lea     rax, aSwbemservicese; "SWbemServicesEx"
0x18001cf87  mov     [rsp+58h+psz], rax; psz
0x18001cf8c  lea     r9, [rbp+var_28]; struct _GUID *
0x18001cf90  lea     r8, [rbp+var_18]; struct _GUID *
0x18001cf94  mov     rdx, rbx; struct IDispatch *
0x18001cf97  call    ?SetObj@CDispatchHelp@@QEAAXPEAUIDispatch@@U_GUID@@1PEAG@Z; CDispatchHelp::SetObj(IDispatch *,_GUID,_GUID,ushort *)
0x18001cf9c  test    rdi, rdi
0x18001cf9f  jz      loc_18001D04E
0x18001cfa5  mov     rax, [rdi]
0x18001cfa8  lea     rdx, [rbx+30h]
0x18001cfac  mov     rcx, rdi
0x18001cfaf  mov     rax, [rax+28h]
0x18001cfb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cfb8  mov     rax, [rdi]
0x18001cfbb  lea     rdx, [rbx+28h]
0x18001cfbf  mov     rcx, rdi
0x18001cfc2  mov     rax, [rax+20h]
0x18001cfc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cfcb  mov     [rbp+arg_8], r15
0x18001cfcf  mov     rax, [rdi]
0x18001cfd2  lea     rdx, [rbp+arg_8]
0x18001cfd6  mov     rcx, rdi
0x18001cfd9  mov     rax, [rax+30h]
0x18001cfdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cfe2  cmp     [rbp+arg_8], r15
0x18001cfe6  jz      short loc_18001D04E
0x18001cfe8  mov     [rbp+arg_10], r15
0x18001cfec  mov     rax, [rdi]
0x18001cfef  lea     rdx, [rbp+arg_10]
0x18001cff3  mov     rcx, rdi
0x18001cff6  mov     rax, [rax+18h]
0x18001cffa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cfff  test    eax, eax
0x18001d001  js      short loc_18001D044
0x18001d003  mov     ecx, 90h
0x18001d008  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18001d00e  mov     [rbp+arg_18], rax
0x18001d012  test    rax, rax
0x18001d015  jz      short loc_18001D029
0x18001d017  mov     r8, [rbp+arg_8]; struct ISWbemInternalSecurity *
0x18001d01b  mov     rdx, [rbp+arg_10]; struct IUnknown *
0x18001d01f  mov     rcx, rax; this
0x18001d022  call    ??0CSWbemSecurity@@QEAA@PEAUIUnknown@@PEAUISWbemInternalSecurity@@@Z; CSWbemSecurity::CSWbemSecurity(IUnknown *,ISWbemInternalSecurity *)
0x18001d027  jmp     short loc_18001D02C
0x18001d029  mov     rax, r15
0x18001d02c  mov     [rbx+88h], rax
0x18001d033  mov     rcx, [rbp+arg_8]
0x18001d037  mov     rax, [rcx]
0x18001d03a  mov     rax, [rax+10h]
0x18001d03e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d043  nop
0x18001d044  lea     rcx, [rbp+arg_10]
0x18001d048  call    ??1?$CComQIPtr@UISWbemObject@@$1?_GUID_76a6415a_cb41_11d1_8b02_00600806d9b6@@3U__s_GUID@@B@ATL@@QEAA@XZ; ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::~CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>(void)
0x18001d04d  nop
0x18001d04e  mov     rax, rbx
0x18001d051  add     rsp, 58h
0x18001d055  pop     r15
0x18001d057  pop     r14
0x18001d059  pop     rdi
0x18001d05a  pop     rsi
0x18001d05b  pop     rbx
0x18001d05c  pop     rbp
0x18001d05d  retn
```
