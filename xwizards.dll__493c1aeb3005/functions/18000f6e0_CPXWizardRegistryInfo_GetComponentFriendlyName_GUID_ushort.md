# CPXWizardRegistryInfo::GetComponentFriendlyName(_GUID *,ushort * *)

- ea: `0x18000f6e0`
- end: `0x18000f7d9`
- name: `?GetComponentFriendlyName@CPXWizardRegistryInfo@@UEAAJPEAU_GUID@@PEAPEAG@Z`
- size: `249`
- prototype: `int(CPXWizardRegistryInfo *__hidden this, struct _GUID *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000ae04`
- `0x18000ae44`
- `0x18000c9a8`
- `0x18000f6e0`
- `0x180032a02`
- `0x180032a30`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000f72f`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000f72f`

## pseudocode

```c
__int64 __fastcall CPXWizardRegistryInfo::GetComponentFriendlyName(
        CPXWizardRegistryInfo *this,
        struct _GUID *a2,
        unsigned __int16 **a3)
{
  unsigned int v5; // eax
  unsigned int WizardComponentFriendlyName; // ebx
  PVOID *v7; // rcx
  OLECHAR sz[40]; // [rsp+30h] [rbp-68h] BYREF

  memset_0(sz, 0, sizeof(sz));
  *a3 = 0;
  v5 = StringFromGUID2(a2, sz, 40);
  if ( v5 == 39 )
  {
    WizardComponentFriendlyName = HrGetWizardComponentFriendlyName(sz, a3);
    goto LABEL_6;
  }
  WizardComponentFriendlyName = -2147467259;
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return WizardComponentFriendlyName;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_570e759f7cb039e76d6863e9d2dbbc56_Traceguids, v5, -2147467259);
LABEL_6:
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x10) != 0 )
    WPP_SF_d(v7[2], 16, WPP_570e759f7cb039e76d6863e9d2dbbc56_Traceguids, WizardComponentFriendlyName);
  return WizardComponentFriendlyName;
}

```

## disassembly

```asm
0x18000f6e0  mov     [rsp+arg_0], rbx
0x18000f6e5  mov     [rsp+arg_18], rsi
0x18000f6ea  push    rdi
0x18000f6eb  sub     rsp, 90h
0x18000f6f2  mov     rax, cs:__security_cookie
0x18000f6f9  xor     rax, rsp
0x18000f6fc  mov     [rsp+98h+var_18], rax
0x18000f704  mov     rbx, rdx
0x18000f707  lea     rcx, [rsp+98h+sz]; void *
0x18000f70c  xor     edx, edx; Val
0x18000f70e  mov     rdi, r8
0x18000f711  lea     r8d, [rdx+50h]; Size
0x18000f715  call    memset_0
0x18000f71a  mov     r8d, 28h ; '('; cchMax
0x18000f720  mov     qword ptr [rdi], 0
0x18000f727  lea     rdx, [rsp+98h+sz]; lpsz
0x18000f72c  mov     rcx, rbx; rguid
0x18000f72f  call    cs:__imp_StringFromGUID2
0x18000f735  lea     rsi, WPP_GLOBAL_Control
0x18000f73c  cmp     eax, 27h ; '''
0x18000f73f  jz      short loc_18000F77A
0x18000f741  mov     ebx, 80004005h
0x18000f746  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f74d  cmp     rcx, rsi
0x18000f750  jz      short loc_18000F7B2
0x18000f752  test    byte ptr [rcx+1Ch], 4
0x18000f756  jz      short loc_18000F790
0x18000f758  mov     rcx, [rcx+10h]
0x18000f75c  lea     r8, WPP_570e759f7cb039e76d6863e9d2dbbc56_Traceguids
0x18000f763  mov     edx, 0Fh
0x18000f768  mov     [rsp+98h+var_78], 80004005h
0x18000f770  mov     r9d, eax
0x18000f773  call    WPP_SF_DD
0x18000f778  jmp     short loc_18000F789
0x18000f77a  mov     rdx, rdi; unsigned __int16 **
0x18000f77d  lea     rcx, [rsp+98h+sz]; unsigned __int16 *
0x18000f782  call    ?HrGetWizardComponentFriendlyName@@YAJQEAGPEAPEAG@Z; HrGetWizardComponentFriendlyName(ushort * const,ushort * *)
0x18000f787  mov     ebx, eax
0x18000f789  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f790  cmp     rcx, rsi
0x18000f793  jz      short loc_18000F7B2
0x18000f795  mov     edx, 10h
0x18000f79a  test    [rcx+1Ch], dl
0x18000f79d  jz      short loc_18000F7B2
0x18000f79f  mov     rcx, [rcx+10h]
0x18000f7a3  lea     r8, WPP_570e759f7cb039e76d6863e9d2dbbc56_Traceguids
0x18000f7aa  mov     r9d, ebx
0x18000f7ad  call    WPP_SF_d
0x18000f7b2  mov     eax, ebx
0x18000f7b4  mov     rcx, [rsp+98h+var_18]
0x18000f7bc  xor     rcx, rsp; StackCookie
0x18000f7bf  call    __security_check_cookie
0x18000f7c4  lea     r11, [rsp+98h+var_8]
0x18000f7cc  mov     rbx, [r11+10h]
0x18000f7d0  mov     rsi, [r11+28h]
0x18000f7d4  mov     rsp, r11
0x18000f7d7  pop     rdi
0x18000f7d8  retn
```
