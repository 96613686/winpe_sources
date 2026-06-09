# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18002c518`
- end: `0x18002c636`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `286`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const unsigned __int16 *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180029408`
- `0x18002956c`

## callees

- `0x180002db0`
- `0x18001b3a0`
- `0x1800296d4`
- `0x18002c518`
- `0x18002eae4`
- `0x18002ee5c`
- `0x18003fc30`

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
0x18002c518  mov     [rsp+arg_10], rbx
0x18002c51d  push    rbp
0x18002c51e  push    rsi
0x18002c51f  push    rdi
0x18002c520  sub     rsp, 260h
0x18002c527  mov     rax, cs:__security_cookie
0x18002c52e  xor     rax, rsp
0x18002c531  mov     [rsp+278h+var_28], rax
0x18002c539  mov     rax, 0C000000000000000h
0x18002c543  mov     rbx, r9
0x18002c546  mov     rbp, rcx
0x18002c549  test    rax, r9
0x18002c54c  jz      short loc_18002C554
0x18002c54e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18002c554  mov     r8, rdx; unsigned __int16 *
0x18002c557  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x18002c55c  mov     edx, 104h; unsigned __int64
0x18002c561  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002c566  lea     r8, aP0; "_p0"
0x18002c56d  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x18002c572  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002c577  mov     edx, ebx
0x18002c579  lea     r9, [rsp+278h+var_238]
0x18002c57e  and     edx, 7FFFFFFFh
0x18002c584  mov     esi, 1
0x18002c589  mov     r8d, esi
0x18002c58c  mov     rcx, rbp
0x18002c58f  cmova   r8d, edx
0x18002c593  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18002c598  mov     edi, eax
0x18002c59a  test    eax, eax
0x18002c59c  jns     short loc_18002C5BE
0x18002c59e  mov     rcx, [rsp+278h]; this
0x18002c5a6  lea     r8, aWil; "wil"
0x18002c5ad  mov     r9d, eax; char *
0x18002c5b0  mov     edx, 8Bh; void *
0x18002c5b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c5ba  mov     eax, edi
0x18002c5bc  jmp     short loc_18002C613
0x18002c5be  lea     r8, asc_1800466C8; "h"
0x18002c5c5  shr     rbx, 1Fh
0x18002c5c9  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x18002c5ce  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002c5d3  test    ebx, ebx
0x18002c5d5  lea     rcx, [rbp+8]
0x18002c5d9  lea     r9, [rsp+278h+var_238]
0x18002c5de  mov     edx, ebx
0x18002c5e0  cmovnz  esi, ebx
0x18002c5e3  mov     r8d, esi
0x18002c5e6  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18002c5eb  mov     ebx, eax
0x18002c5ed  test    eax, eax
0x18002c5ef  jns     short loc_18002C611
0x18002c5f1  mov     rcx, [rsp+278h]; this
0x18002c5f9  lea     r8, aWil; "wil"
0x18002c600  mov     r9d, eax; char *
0x18002c603  mov     edx, 90h; void *
0x18002c608  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c60d  mov     eax, ebx
0x18002c60f  jmp     short loc_18002C613
0x18002c611  xor     eax, eax
0x18002c613  mov     rcx, [rsp+278h+var_28]
0x18002c61b  xor     rcx, rsp; StackCookie
0x18002c61e  call    __security_check_cookie
0x18002c623  mov     rbx, [rsp+278h+arg_10]
0x18002c62b  add     rsp, 260h
0x18002c632  pop     rdi
0x18002c633  pop     rsi
0x18002c634  pop     rbp
0x18002c635  retn
```
