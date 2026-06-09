# CControlPanelPage::LayoutInitialized(void)

- ea: `0x180052ff8`
- end: `0x1800531b3`
- name: `?LayoutInitialized@CControlPanelPage@@UEAAJXZ`
- size: `443`
- prototype: `__int64 __fastcall(CControlPanelPage *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, service_task`

## callers

- `0x18000ddb0`
- `0x180038de0`
- `0x180044280`

## callees

- `0x180002280`
- `0x180052ff8`
- `0x180057010`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_QueryService` at `0x1800530f2`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x1800530f2`
- `SHLWAPI!__imp_IUnknown_ProfferService` at `0x180053075`
- `SHLWAPI!__imp_IUnknown_ProfferService` at `0x180053075`

## pseudocode

```c
__int64 __fastcall CControlPanelPage::LayoutInitialized(CControlPanelPage *this)
{
  char *v2; // rcx
  __int64 v3; // rax
  IUnknown *v4; // rcx
  __int64 v6; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v7; // [rsp+38h] [rbp-C8h] BYREF
  void *ppvOut; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v9; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v10[528]; // [rsp+50h] [rbp-B0h] BYREF

  v2 = (char *)this - 224;
  if ( !*((_DWORD *)v2 + 58) )
  {
    v3 = *(_QWORD *)v2;
    v6 = 0;
    if ( (*(int (__fastcall **)(char *, GUID *, __int64 *))(v3 + 368))(
           v2,
           &GUID_6d5140c1_7436_11ce_8034_00aa006009fa,
           &v6) >= 0 )
    {
      IUnknown_ProfferService(*((_QWORD *)this - 1), &IID_IShellSearchTargetServices, v6, (char *)this + 8);
      v9 = 0;
      if ( (**(int (__fastcall ***)(__int64, GUID *, __int64 *))v6)(v6, &GUID_dda3a58a_43da_4a43_a5f2_f7abf6e3c026, &v9) >= 0 )
      {
        if ( (*(int (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)v9 + 24LL))(v9, v10, 260) >= 0 )
        {
          v4 = (IUnknown *)*((_QWORD *)this - 1);
          ppvOut = 0;
          if ( IUnknown_QueryService(
                 v4,
                 (const GUID *const)&SID_SNavBar,
                 &GUID_a6087428_3be3_4d73_b308_7c04a540bf1a,
                 &ppvOut) >= 0 )
          {
            v7 = 0;
            if ( (*(int (__fastcall **)(void *, __int64 *, GUID *, __int64 *))(*(_QWORD *)ppvOut + 24LL))(
                   ppvOut,
                   OID_OSearchControl,
                   &GUID_111f7c32_0546_4227_8b7f_c53a0b114a0f,
                   &v7) >= 0 )
            {
              (*(void (__fastcall **)(__int64, _BYTE *, _QWORD))(*(_QWORD *)v7 + 64LL))(v7, v10, 0);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
            }
            (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
          }
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180052ff8  mov     [rsp-8+arg_8], rbx
0x180052ffd  push    rbp
0x180052ffe  lea     rbp, [rsp-170h]
0x180053006  sub     rsp, 270h
0x18005300d  mov     rax, cs:__security_cookie
0x180053014  xor     rax, rsp
0x180053017  mov     [rbp+170h+var_10], rax
0x18005301e  mov     rbx, rcx
0x180053021  add     rcx, 0FFFFFFFFFFFFFF20h
0x180053028  cmp     dword ptr [rcx+0E8h], 0
0x18005302f  jnz     loc_180053190
0x180053035  mov     rax, [rcx]
0x180053038  lea     r8, [rsp+270h+var_240]
0x18005303d  lea     rdx, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa
0x180053044  mov     [rsp+270h+var_240], 0
0x18005304d  mov     rax, [rax+170h]
0x180053054  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053059  test    eax, eax
0x18005305b  js      loc_180053190
0x180053061  mov     r8, [rsp+270h+var_240]
0x180053066  lea     r9, [rbx+8]
0x18005306a  mov     rcx, [rbx-8]
0x18005306e  lea     rdx, IID_IShellSearchTargetServices
0x180053075  call    cs:__imp_IUnknown_ProfferService
0x18005307c  nop     dword ptr [rax+rax+00h]
0x180053081  mov     rcx, [rsp+270h+var_240]
0x180053086  lea     r8, [rsp+270h+var_228]
0x18005308b  mov     [rsp+270h+var_228], 0
0x180053094  lea     rdx, _GUID_dda3a58a_43da_4a43_a5f2_f7abf6e3c026
0x18005309b  mov     rax, [rcx]
0x18005309e  mov     rax, [rax]
0x1800530a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800530a6  test    eax, eax
0x1800530a8  js      loc_18005317F
0x1800530ae  mov     rcx, [rsp+270h+var_228]
0x1800530b3  lea     rdx, [rsp+270h+var_220]
0x1800530b8  mov     r8d, 104h
0x1800530be  mov     rax, [rcx]
0x1800530c1  mov     rax, [rax+18h]
0x1800530c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800530ca  test    eax, eax
0x1800530cc  js      loc_18005316E
0x1800530d2  mov     rcx, [rbx-8]; punk
0x1800530d6  lea     r9, [rsp+270h+ppvOut]; ppvOut
0x1800530db  lea     r8, _GUID_a6087428_3be3_4d73_b308_7c04a540bf1a; riid
0x1800530e2  mov     [rsp+270h+ppvOut], 0
0x1800530eb  lea     rdx, SID_SNavBar; guidService
0x1800530f2  call    cs:__imp_IUnknown_QueryService
0x1800530f9  nop     dword ptr [rax+rax+00h]
0x1800530fe  test    eax, eax
0x180053100  js      short loc_18005316E
0x180053102  mov     rcx, [rsp+270h+ppvOut]
0x180053107  lea     r9, [rsp+270h+var_238]
0x18005310c  mov     [rsp+270h+var_238], 0
0x180053115  lea     r8, _GUID_111f7c32_0546_4227_8b7f_c53a0b114a0f
0x18005311c  lea     rdx, OID_OSearchControl
0x180053123  mov     rax, [rcx]
0x180053126  mov     rax, [rax+18h]
0x18005312a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005312f  test    eax, eax
0x180053131  js      short loc_18005315D
0x180053133  mov     rcx, [rsp+270h+var_238]
0x180053138  lea     rdx, [rsp+270h+var_220]
0x18005313d  xor     r8d, r8d
0x180053140  mov     rax, [rcx]
0x180053143  mov     rax, [rax+40h]
0x180053147  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005314c  mov     rcx, [rsp+270h+var_238]
0x180053151  mov     rax, [rcx]
0x180053154  mov     rax, [rax+10h]
0x180053158  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005315d  mov     rcx, [rsp+270h+ppvOut]
0x180053162  mov     rax, [rcx]
0x180053165  mov     rax, [rax+10h]
0x180053169  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005316e  mov     rcx, [rsp+270h+var_228]
0x180053173  mov     rax, [rcx]
0x180053176  mov     rax, [rax+10h]
0x18005317a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005317f  mov     rcx, [rsp+270h+var_240]
0x180053184  mov     rax, [rcx]
0x180053187  mov     rax, [rax+10h]
0x18005318b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053190  xor     eax, eax
0x180053192  mov     rcx, [rbp+170h+var_10]
0x180053199  xor     rcx, rsp; StackCookie
0x18005319c  call    __security_check_cookie
0x1800531a1  mov     rbx, [rsp+270h+arg_8]
0x1800531a9  add     rsp, 270h
0x1800531b0  pop     rbp
0x1800531b1  retn
```
