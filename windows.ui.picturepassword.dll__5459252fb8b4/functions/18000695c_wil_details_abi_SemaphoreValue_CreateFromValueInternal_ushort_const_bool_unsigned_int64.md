# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18000695c`
- end: `0x180006a7a`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `286`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const unsigned __int16 *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800083f8`
- `0x18001b6f4`

## callees

- `0x180002610`
- `0x18000695c`
- `0x18000934c`
- `0x18000a07c`
- `0x18000a1c8`
- `0x18000b068`
- `0x18000b6ac`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        const unsigned __int16 *a2,
        __int64 a3,
        unsigned __int64 a4)
{
  unsigned __int64 v6; // rdx
  LONG v7; // esi
  LONG v8; // r8d
  int semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  unsigned __int64 v10; // rdx
  unsigned int v11; // edi
  unsigned __int64 v13; // rbx
  int v14; // eax
  unsigned int v15; // ebx
  int v16; // [rsp+20h] [rbp-258h]
  unsigned __int16 v17[264]; // [rsp+40h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  StringCchCopyW(v17, 0x104u, a2);
  StringCchCatW(v17, v6, L"_p0");
  v7 = 1;
  v8 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v8 = a4 & 0x7FFFFFFF;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this, a4 & 0x7FFFFFFF, v8, v17);
  v11 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    v13 = a4 >> 31;
    StringCchCatW(v17, v10, L"h");
    if ( (_DWORD)v13 )
      v7 = v13;
    v14 = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
            (__int64)this + 8,
            v13,
            v7,
            v17);
    v15 = v14;
    if ( v14 >= 0 )
    {
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x90,
        (unsigned int)"wil",
        (const char *)(unsigned int)v14,
        v16);
      return v15;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8B,
      (unsigned int)"wil",
      (const char *)(unsigned int)semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      v16);
    return v11;
  }
}

```

## disassembly

```asm
0x18000695c  mov     [rsp+arg_10], rbx
0x180006961  push    rbp
0x180006962  push    rsi
0x180006963  push    rdi
0x180006964  sub     rsp, 260h
0x18000696b  mov     rax, cs:__security_cookie
0x180006972  xor     rax, rsp
0x180006975  mov     [rsp+278h+var_28], rax
0x18000697d  mov     rax, 0C000000000000000h
0x180006987  mov     rbx, r9
0x18000698a  mov     rbp, rcx
0x18000698d  test    rax, r9
0x180006990  jz      short loc_180006998
0x180006992  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180006998  mov     r8, rdx; unsigned __int16 *
0x18000699b  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x1800069a0  mov     edx, 104h; unsigned __int64
0x1800069a5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800069aa  lea     r8, aP0; "_p0"
0x1800069b1  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x1800069b6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800069bb  mov     edx, ebx
0x1800069bd  lea     r9, [rsp+278h+var_238]
0x1800069c2  and     edx, 7FFFFFFFh
0x1800069c8  mov     esi, 1
0x1800069cd  mov     r8d, esi
0x1800069d0  mov     rcx, rbp
0x1800069d3  cmova   r8d, edx
0x1800069d7  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800069dc  mov     edi, eax
0x1800069de  test    eax, eax
0x1800069e0  jns     short loc_180006A02
0x1800069e2  mov     rcx, [rsp+278h]; this
0x1800069ea  lea     r8, aWil; "wil"
0x1800069f1  mov     r9d, eax; char *
0x1800069f4  mov     edx, 8Bh; void *
0x1800069f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800069fe  mov     eax, edi
0x180006a00  jmp     short loc_180006A57
0x180006a02  lea     r8, asc_1800227B8; "h"
0x180006a09  shr     rbx, 1Fh
0x180006a0d  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x180006a12  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006a17  test    ebx, ebx
0x180006a19  lea     rcx, [rbp+8]
0x180006a1d  lea     r9, [rsp+278h+var_238]
0x180006a22  mov     edx, ebx
0x180006a24  cmovnz  esi, ebx
0x180006a27  mov     r8d, esi
0x180006a2a  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180006a2f  mov     ebx, eax
0x180006a31  test    eax, eax
0x180006a33  jns     short loc_180006A55
0x180006a35  mov     rcx, [rsp+278h]; this
0x180006a3d  lea     r8, aWil; "wil"
0x180006a44  mov     r9d, eax; char *
0x180006a47  mov     edx, 90h; void *
0x180006a4c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006a51  mov     eax, ebx
0x180006a53  jmp     short loc_180006A57
0x180006a55  xor     eax, eax
0x180006a57  mov     rcx, [rsp+278h+var_28]
0x180006a5f  xor     rcx, rsp; StackCookie
0x180006a62  call    __security_check_cookie
0x180006a67  mov     rbx, [rsp+278h+arg_10]
0x180006a6f  add     rsp, 260h
0x180006a76  pop     rdi
0x180006a77  pop     rsi
0x180006a78  pop     rbp
0x180006a79  retn
```
