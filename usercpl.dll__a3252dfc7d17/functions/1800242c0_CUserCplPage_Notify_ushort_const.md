# CUserCplPage::Notify(ushort const *)

- ea: `0x1800242c0`
- end: `0x180024386`
- name: `?Notify@CUserCplPage@@UEAAJPEBG@Z`
- size: `198`
- prototype: `__int64 __fastcall(CUserCplPage *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800242c0`
- `0x180067c20`
- `0x180078010`

## import_xrefs

- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x18002435a`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x18002435a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800242e8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800242e8`
- `PROPSYS!PSPropertyBag_ReadInt` at `0x180024336`
- `PROPSYS!PSPropertyBag_ReadInt` at `0x180024336`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x180024313`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x180024313`

## string_xrefs

- `0x1800242d8`: `ControlPanelNavLinkClicked`
- `0x180024327`: `ControlPanelNavLinkClicked`

## pseudocode

```c
int __fastcall CUserCplPage::Notify(CUserCplPage *this, const unsigned __int16 *a2)
{
  IUnknown *v4; // rcx
  INT value; // [rsp+40h] [rbp+8h] BYREF
  void *ppvOut; // [rsp+50h] [rbp+18h] BYREF

  if ( CompareStringOrdinal(a2, -1, L"ControlPanelNavLinkClicked", -1, 1) == 2 )
  {
    v4 = (IUnknown *)*((_QWORD *)this - 1);
    ppvOut = 0;
    if ( IUnknown_QueryService(
           v4,
           (const GUID *const)&SID_PerLayoutPropertyBag,
           &GUID_55272a00_42cb_11ce_8135_00aa004bb851,
           &ppvOut) >= 0 )
    {
      value = 0;
      if ( PSPropertyBag_ReadInt((IPropertyBag *)ppvOut, L"ControlPanelNavLinkClicked", &value) >= 0 && value == 230 )
        SHCreateThread((LPTHREAD_START_ROUTINE)_ShowResetEASPoliciesUIThreadProc, 0, 0x18u, 0);
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
    }
  }
  return CControlPanelPage::Notify(this, a2);
}

```

## disassembly

```asm
0x1800242c0  mov     [rsp+arg_8], rbx
0x1800242c5  push    rdi
0x1800242c6  sub     rsp, 30h
0x1800242ca  mov     rdi, rdx
0x1800242cd  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x1800242d5  or      edx, 0FFFFFFFFh; cchCount1
0x1800242d8  lea     r8, aControlpanelna_0; "ControlPanelNavLinkClicked"
0x1800242df  mov     rbx, rcx
0x1800242e2  mov     r9d, edx; cchCount2
0x1800242e5  mov     rcx, rdi; lpString1
0x1800242e8  call    cs:__imp_CompareStringOrdinal
0x1800242ee  cmp     eax, 2
0x1800242f1  jnz     short loc_180024371
0x1800242f3  mov     rcx, [rbx-8]; punk
0x1800242f7  lea     r9, [rsp+38h+ppvOut]; ppvOut
0x1800242fc  lea     r8, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x180024303  mov     [rsp+38h+ppvOut], 0
0x18002430c  lea     rdx, SID_PerLayoutPropertyBag; guidService
0x180024313  call    cs:__imp_IUnknown_QueryService
0x180024319  test    eax, eax
0x18002431b  js      short loc_180024371
0x18002431d  mov     rcx, [rsp+38h+ppvOut]; propBag
0x180024322  lea     r8, [rsp+38h+value]; value
0x180024327  lea     rdx, aControlpanelna_0; "ControlPanelNavLinkClicked"
0x18002432e  mov     [rsp+38h+value], 0
0x180024336  call    cs:__imp_PSPropertyBag_ReadInt
0x18002433c  test    eax, eax
0x18002433e  js      short loc_180024360
0x180024340  cmp     [rsp+38h+value], 0E6h
0x180024348  jnz     short loc_180024360
0x18002434a  xor     r9d, r9d; pfnCallback
0x18002434d  lea     rcx, ?_ShowResetEASPoliciesUIThreadProc@@YAKPEAX@Z; pfnThreadProc
0x180024354  xor     edx, edx; pData
0x180024356  lea     r8d, [r9+18h]; flags
0x18002435a  call    cs:__imp_SHCreateThread
0x180024360  mov     rcx, [rsp+38h+ppvOut]
0x180024365  mov     rax, [rcx]
0x180024368  mov     rax, [rax+10h]
0x18002436c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024371  mov     rdx, rdi; unsigned __int16 *
0x180024374  mov     rcx, rbx; this
0x180024377  mov     rbx, [rsp+38h+arg_8]
0x18002437c  add     rsp, 30h
0x180024380  pop     rdi
0x180024381  jmp     ?Notify@CControlPanelPage@@UEAAJPEBG@Z; CControlPanelPage::Notify(ushort const *)
```
