# CWebWizardErrorPage::OnSetActive(void)

- ea: `0x18003eb50`
- end: `0x18003ecdc`
- name: `?OnSetActive@CWebWizardErrorPage@@UEAAJXZ`
- size: `396`
- prototype: `__int64 __fastcall(CWebWizardErrorPage *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18000d9a4`
- `0x18003eb50`
- `0x180063d40`
- `0x1800772c0`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ebbe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ec67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ebbe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ec67`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18003ec98`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18003ec98`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x18003ec33`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x18003ec33`
- `DUI70!?SetAccName@Element@DirectUI@@QEAAJPEBG@Z` at `0x18003ec46`
- `DUI70!?SetAccName@Element@DirectUI@@QEAAJPEBG@Z` at `0x18003ec46`

## pseudocode

```c
__int64 __fastcall CWebWizardErrorPage::OnSetActive(CWebWizardErrorPage *this)
{
  int v2; // edi
  __int64 v3; // rcx
  const unsigned __int16 **v4; // rbx
  __int64 v5; // rcx
  int v6; // ebx
  int v7; // edx
  __int64 v8; // rcx
  __int64 v9; // r8
  unsigned int v11; // [rsp+30h] [rbp-48h] BYREF
  int v12; // [rsp+34h] [rbp-44h] BYREF
  _BYTE v13[16]; // [rsp+38h] [rbp-40h] BYREF

  v2 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this - 1) + 112LL))((char *)this - 8);
  if ( v2 >= 0 )
  {
    v3 = *((_QWORD *)this + 5);
    v11 = 0;
    (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v3 + 24LL))(v3, &v11);
    (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 5) + 64LL))(*((_QWORD *)this + 5), v11);
    v4 = (const unsigned __int16 **)((char *)this + 56);
    CoTaskMemFree(*((LPVOID *)this + 7));
    v2 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 5) + 32LL))(
           *((_QWORD *)this + 5),
           (char *)this + 56);
    if ( v2 == -2147023728 )
    {
      v5 = *((_QWORD *)this + 5);
      v12 = 0;
      (*(void (__fastcall **)(__int64, int *, _QWORD, _QWORD))(*(_QWORD *)v5 + 56LL))(v5, &v12, 0, 0);
      v2 = ResourceStringCoAllocFormatMessage(
             g_hinst,
             *((unsigned int *)`CWebWizardErrorPage::OnSetActive'::`8'::rguPageTextResIds + v12),
             (_QWORD *)this + 7,
             v11);
    }
    if ( v2 >= 0 )
    {
      v2 = DirectUI::Element::SetContentString(*((DirectUI::Element **)this + 6), *v4);
      if ( v2 >= 0 )
        v2 = DirectUI::Element::SetAccName(*((DirectUI::Element **)this + 6), *v4);
    }
    v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 48LL))(*((_QWORD *)this + 5));
    CoTaskMemFree(*((LPVOID *)this + 9));
    (*(void (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 5) + 40LL))(*((_QWORD *)this + 5), (char *)this + 72);
    if ( !v6 || *((_QWORD *)this + 9) )
      v7 = -1;
    else
      v7 = -3;
    DirectUI::Element::SetLayoutPos(*((DirectUI::Element **)this + 8), v7);
    if ( (Microsoft_Windows_User_ControlPanelEnableBits & 2) != 0 )
      McGenEventWrite_EventWriteTransfer(v8, UserAccount_Taskflow_WebErrorPage_Active, v9, 1, v13);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18003eb50  push    rbx
0x18003eb52  push    rsi
0x18003eb53  push    rdi
0x18003eb54  push    r14
0x18003eb56  sub     rsp, 58h
0x18003eb5a  mov     rax, cs:__security_cookie
0x18003eb61  xor     rax, rsp
0x18003eb64  mov     [rsp+78h+var_30], rax
0x18003eb69  mov     rsi, rcx
0x18003eb6c  add     rcx, 0FFFFFFFFFFFFFFF8h
0x18003eb70  mov     rax, [rcx]
0x18003eb73  mov     rax, [rax+70h]
0x18003eb77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eb7c  mov     edi, eax
0x18003eb7e  test    eax, eax
0x18003eb80  js      loc_18003ECC3
0x18003eb86  mov     rcx, [rsi+28h]
0x18003eb8a  lea     rdx, [rsp+78h+var_48]
0x18003eb8f  mov     [rsp+78h+var_48], 0
0x18003eb97  mov     rax, [rcx]
0x18003eb9a  mov     rax, [rax+18h]
0x18003eb9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eba3  mov     rcx, [rsi+28h]
0x18003eba7  mov     edx, [rsp+78h+var_48]
0x18003ebab  mov     rax, [rcx]
0x18003ebae  mov     rax, [rax+40h]
0x18003ebb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ebb7  lea     rbx, [rsi+38h]
0x18003ebbb  mov     rcx, [rbx]; pv
0x18003ebbe  call    cs:__imp_CoTaskMemFree
0x18003ebc4  mov     rcx, [rsi+28h]
0x18003ebc8  mov     rdx, rbx
0x18003ebcb  mov     rax, [rcx]
0x18003ebce  mov     rax, [rax+20h]
0x18003ebd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ebd7  mov     edi, eax
0x18003ebd9  cmp     eax, 80070490h
0x18003ebde  jnz     short loc_18003EC28
0x18003ebe0  mov     rcx, [rsi+28h]
0x18003ebe4  lea     rdx, [rsp+78h+var_44]
0x18003ebe9  mov     [rsp+78h+var_44], 0
0x18003ebf1  xor     r9d, r9d
0x18003ebf4  xor     r8d, r8d
0x18003ebf7  mov     rax, [rcx]
0x18003ebfa  mov     rax, [rax+38h]
0x18003ebfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ec03  movsxd  rdx, [rsp+78h+var_44]
0x18003ec08  lea     rax, ?rguPageTextResIds@?7??OnSetActive@CWebWizardErrorPage@@UEAAJXZ@4PAIA; uint near * `CWebWizardErrorPage::OnSetActive(void)'::`8'::rguPageTextResIds
0x18003ec0f  mov     r9d, [rsp+78h+var_48]
0x18003ec14  mov     r8, rbx
0x18003ec17  mov     rcx, cs:g_hinst
0x18003ec1e  mov     edx, [rax+rdx*4]
0x18003ec21  call    ResourceStringCoAllocFormatMessage
0x18003ec26  mov     edi, eax
0x18003ec28  test    edi, edi
0x18003ec2a  js      short loc_18003EC4E
0x18003ec2c  mov     rdx, [rbx]
0x18003ec2f  mov     rcx, [rsi+30h]
0x18003ec33  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x18003ec39  mov     edi, eax
0x18003ec3b  test    eax, eax
0x18003ec3d  js      short loc_18003EC4E
0x18003ec3f  mov     rdx, [rbx]
0x18003ec42  mov     rcx, [rsi+30h]
0x18003ec46  call    cs:__imp_?SetAccName@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetAccName(ushort const *)
0x18003ec4c  mov     edi, eax
0x18003ec4e  mov     rcx, [rsi+28h]
0x18003ec52  mov     rax, [rcx]
0x18003ec55  mov     rax, [rax+30h]
0x18003ec59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ec5e  lea     r14, [rsi+48h]
0x18003ec62  mov     ebx, eax
0x18003ec64  mov     rcx, [r14]; pv
0x18003ec67  call    cs:__imp_CoTaskMemFree
0x18003ec6d  mov     rcx, [rsi+28h]
0x18003ec71  mov     rdx, [rcx]
0x18003ec74  mov     rax, [rdx+28h]
0x18003ec78  mov     rdx, r14
0x18003ec7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ec80  test    ebx, ebx
0x18003ec82  jz      short loc_18003EC91
0x18003ec84  cmp     qword ptr [r14], 0
0x18003ec88  jnz     short loc_18003EC91
0x18003ec8a  mov     edx, 0FFFFFFFDh
0x18003ec8f  jmp     short loc_18003EC94
0x18003ec91  or      edx, 0FFFFFFFFh
0x18003ec94  mov     rcx, [rsi+40h]
0x18003ec98  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x18003ec9e  test    cs:Microsoft_Windows_User_ControlPanelEnableBits, 2
0x18003eca5  jz      short loc_18003ECC3
0x18003eca7  lea     rax, [rsp+78h+var_40]
0x18003ecac  mov     r9d, 1
0x18003ecb2  lea     rdx, UserAccount_Taskflow_WebErrorPage_Active
0x18003ecb9  mov     [rsp+78h+var_58], rax
0x18003ecbe  call    McGenEventWrite_EventWriteTransfer
0x18003ecc3  mov     eax, edi
0x18003ecc5  mov     rcx, [rsp+78h+var_30]
0x18003ecca  xor     rcx, rsp; StackCookie
0x18003eccd  call    __security_check_cookie
0x18003ecd2  add     rsp, 58h
0x18003ecd6  pop     r14
0x18003ecd8  pop     rdi
0x18003ecd9  pop     rsi
0x18003ecda  pop     rbx
0x18003ecdb  retn
```
