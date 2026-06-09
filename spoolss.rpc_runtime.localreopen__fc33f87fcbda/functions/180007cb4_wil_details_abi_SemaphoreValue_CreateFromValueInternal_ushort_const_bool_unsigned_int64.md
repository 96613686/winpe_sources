# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180007cb4`
- end: `0x180007dc5`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `273`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800041a8`
- `0x180004300`

## callees

- `0x180004728`
- `0x180004a64`
- `0x180005680`
- `0x180007cb4`
- `0x18000b710`
- `0x18000c3c0`
- `0x18000c598`

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
  unsigned int v11; // r8d
  unsigned int v12; // edi
  unsigned __int64 v14; // rbx
  int v15; // eax
  unsigned int v16; // r8d
  unsigned int v17; // ebx
  int v18; // [rsp+20h] [rbp-258h]
  unsigned __int16 v19[264]; // [rsp+40h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  StringCchCopyW(v19, 0x104u, a2);
  StringCchCatW(v19, v6, L"_p0");
  v7 = 1;
  v8 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v8 = a4 & 0x7FFFFFFF;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this, a4 & 0x7FFFFFFF, v8, v19);
  v12 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    v14 = a4 >> 31;
    StringCchCatW(v19, v10, L"h");
    if ( (_DWORD)v14 )
      v7 = v14;
    v15 = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
            (__int64)this + 8,
            v14,
            v7,
            v19);
    v17 = v15;
    if ( v15 >= 0 )
    {
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x90, v16, (const char *)(unsigned int)v15, v18);
      return v17;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8B,
      v11,
      (const char *)(unsigned int)semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      v18);
    return v12;
  }
}

```

## disassembly

```asm
0x180007cb4  mov     [rsp+arg_10], rbx
0x180007cb9  push    rbp
0x180007cba  push    rsi
0x180007cbb  push    rdi
0x180007cbc  sub     rsp, 260h
0x180007cc3  mov     rax, cs:__security_cookie
0x180007cca  xor     rax, rsp
0x180007ccd  mov     [rsp+278h+var_28], rax
0x180007cd5  mov     rax, 0C000000000000000h
0x180007cdf  mov     rbx, r9
0x180007ce2  mov     rbp, rcx
0x180007ce5  test    rax, r9
0x180007ce8  jz      short loc_180007CF0
0x180007cea  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180007cf0  mov     r8, rdx; unsigned __int16 *
0x180007cf3  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x180007cf8  mov     edx, 104h; unsigned __int64
0x180007cfd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180007d02  lea     r8, aP0; "_p0"
0x180007d09  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x180007d0e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007d13  mov     edx, ebx
0x180007d15  lea     r9, [rsp+278h+var_238]
0x180007d1a  and     edx, 7FFFFFFFh
0x180007d20  mov     esi, 1
0x180007d25  mov     r8d, esi
0x180007d28  mov     rcx, rbp
0x180007d2b  cmova   r8d, edx
0x180007d2f  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180007d34  mov     edi, eax
0x180007d36  test    eax, eax
0x180007d38  jns     short loc_180007D53
0x180007d3a  mov     rcx, [rsp+278h]; this
0x180007d42  mov     r9d, eax; char *
0x180007d45  mov     edx, 8Bh; void *
0x180007d4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007d4f  mov     eax, edi
0x180007d51  jmp     short loc_180007DA1
0x180007d53  lea     r8, asc_180019630; "h"
0x180007d5a  shr     rbx, 1Fh
0x180007d5e  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x180007d63  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007d68  test    ebx, ebx
0x180007d6a  lea     rcx, [rbp+8]
0x180007d6e  lea     r9, [rsp+278h+var_238]
0x180007d73  mov     edx, ebx
0x180007d75  cmovnz  esi, ebx
0x180007d78  mov     r8d, esi
0x180007d7b  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180007d80  mov     ebx, eax
0x180007d82  test    eax, eax
0x180007d84  jns     short loc_180007D9F
0x180007d86  mov     rcx, [rsp+278h]; this
0x180007d8e  mov     r9d, eax; char *
0x180007d91  mov     edx, 90h; void *
0x180007d96  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007d9b  mov     eax, ebx
0x180007d9d  jmp     short loc_180007DA1
0x180007d9f  xor     eax, eax
0x180007da1  mov     rcx, [rsp+278h+var_28]
0x180007da9  xor     rcx, rsp; StackCookie
0x180007dac  call    __security_check_cookie
0x180007db1  mov     rbx, [rsp+278h+arg_10]
0x180007db9  add     rsp, 260h
0x180007dc0  pop     rdi
0x180007dc1  pop     rsi
0x180007dc2  pop     rbp
0x180007dc3  retn
```
