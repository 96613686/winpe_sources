# CControlPanelPage::LayoutInitialized(void)

- ea: `0x180018400`
- end: `0x1800185ae`
- name: `?LayoutInitialized@CControlPanelPage@@UEAAJXZ`
- size: `430`
- prototype: `__int64 __fastcall(CControlPanelPage *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task`

## callers

- `0x180013490`

## callees

- `0x180001d60`
- `0x180018400`
- `0x18001e010`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_QueryService` at `0x1800184f4`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x1800184f4`
- `SHLWAPI!__imp_IUnknown_ProfferService` at `0x18001847d`
- `SHLWAPI!__imp_IUnknown_ProfferService` at `0x18001847d`

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
0x180018400  mov     [rsp-8+arg_8], rbx
0x180018405  push    rbp
0x180018406  lea     rbp, [rsp-170h]
0x18001840e  sub     rsp, 270h
0x180018415  mov     rax, cs:__security_cookie
0x18001841c  xor     rax, rsp
0x18001841f  mov     [rbp+170h+var_10], rax
0x180018426  mov     rbx, rcx
0x180018429  add     rcx, 0FFFFFFFFFFFFFF20h
0x180018430  cmp     dword ptr [rcx+0E8h], 0
0x180018437  jnz     loc_18001858C
0x18001843d  mov     rax, [rcx]
0x180018440  lea     r8, [rsp+270h+var_240]
0x180018445  lea     rdx, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa
0x18001844c  mov     [rsp+270h+var_240], 0
0x180018455  mov     rax, [rax+170h]
0x18001845c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018461  test    eax, eax
0x180018463  js      loc_18001858C
0x180018469  mov     r8, [rsp+270h+var_240]
0x18001846e  lea     r9, [rbx+8]
0x180018472  mov     rcx, [rbx-8]
0x180018476  lea     rdx, IID_IShellSearchTargetServices
0x18001847d  call    cs:__imp_IUnknown_ProfferService
0x180018483  mov     rcx, [rsp+270h+var_240]
0x180018488  lea     r8, [rsp+270h+var_228]
0x18001848d  mov     [rsp+270h+var_228], 0
0x180018496  lea     rdx, _GUID_dda3a58a_43da_4a43_a5f2_f7abf6e3c026
0x18001849d  mov     rax, [rcx]
0x1800184a0  mov     rax, [rax]
0x1800184a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800184a8  test    eax, eax
0x1800184aa  js      loc_18001857B
0x1800184b0  mov     rcx, [rsp+270h+var_228]
0x1800184b5  lea     rdx, [rsp+270h+var_220]
0x1800184ba  mov     r8d, 104h
0x1800184c0  mov     rax, [rcx]
0x1800184c3  mov     rax, [rax+18h]
0x1800184c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800184cc  test    eax, eax
0x1800184ce  js      loc_18001856A
0x1800184d4  mov     rcx, [rbx-8]; punk
0x1800184d8  lea     r9, [rsp+270h+ppvOut]; ppvOut
0x1800184dd  lea     r8, _GUID_a6087428_3be3_4d73_b308_7c04a540bf1a; riid
0x1800184e4  mov     [rsp+270h+ppvOut], 0
0x1800184ed  lea     rdx, SID_SNavBar; guidService
0x1800184f4  call    cs:__imp_IUnknown_QueryService
0x1800184fa  test    eax, eax
0x1800184fc  js      short loc_18001856A
0x1800184fe  mov     rcx, [rsp+270h+ppvOut]
0x180018503  lea     r9, [rsp+270h+var_238]
0x180018508  mov     [rsp+270h+var_238], 0
0x180018511  lea     r8, _GUID_111f7c32_0546_4227_8b7f_c53a0b114a0f
0x180018518  lea     rdx, OID_OSearchControl
0x18001851f  mov     rax, [rcx]
0x180018522  mov     rax, [rax+18h]
0x180018526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001852b  test    eax, eax
0x18001852d  js      short loc_180018559
0x18001852f  mov     rcx, [rsp+270h+var_238]
0x180018534  lea     rdx, [rsp+270h+var_220]
0x180018539  xor     r8d, r8d
0x18001853c  mov     rax, [rcx]
0x18001853f  mov     rax, [rax+40h]
0x180018543  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018548  mov     rcx, [rsp+270h+var_238]
0x18001854d  mov     rax, [rcx]
0x180018550  mov     rax, [rax+10h]
0x180018554  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018559  mov     rcx, [rsp+270h+ppvOut]
0x18001855e  mov     rax, [rcx]
0x180018561  mov     rax, [rax+10h]
0x180018565  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001856a  mov     rcx, [rsp+270h+var_228]
0x18001856f  mov     rax, [rcx]
0x180018572  mov     rax, [rax+10h]
0x180018576  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001857b  mov     rcx, [rsp+270h+var_240]
0x180018580  mov     rax, [rcx]
0x180018583  mov     rax, [rax+10h]
0x180018587  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001858c  xor     eax, eax
0x18001858e  mov     rcx, [rbp+170h+var_10]
0x180018595  xor     rcx, rsp; StackCookie
0x180018598  call    __security_check_cookie
0x18001859d  mov     rbx, [rsp+270h+arg_8]
0x1800185a5  add     rsp, 270h
0x1800185ac  pop     rbp
0x1800185ad  retn
```
