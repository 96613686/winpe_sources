# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18000c760`
- end: `0x18000c87e`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `286`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d9d4`

## callees

- `0x18000c760`
- `0x18000dfb8`
- `0x18000e26c`
- `0x18000e2e8`
- `0x18000e75c`
- `0x18000eb6c`
- `0x1800155c0`

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
0x18000c760  mov     [rsp+arg_10], rbx
0x18000c765  push    rbp
0x18000c766  push    rsi
0x18000c767  push    rdi
0x18000c768  sub     rsp, 260h
0x18000c76f  mov     rax, cs:__security_cookie
0x18000c776  xor     rax, rsp
0x18000c779  mov     [rsp+278h+var_28], rax
0x18000c781  mov     rax, 0C000000000000000h
0x18000c78b  mov     rbx, r9
0x18000c78e  mov     rbp, rcx
0x18000c791  test    rax, r9
0x18000c794  jz      short loc_18000C79C
0x18000c796  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000c79c  mov     r8, rdx; unsigned __int16 *
0x18000c79f  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x18000c7a4  mov     edx, 104h; unsigned __int64
0x18000c7a9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000c7ae  lea     r8, aP0; "_p0"
0x18000c7b5  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x18000c7ba  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000c7bf  mov     edx, ebx
0x18000c7c1  lea     r9, [rsp+278h+var_238]
0x18000c7c6  and     edx, 7FFFFFFFh
0x18000c7cc  mov     esi, 1
0x18000c7d1  mov     r8d, esi
0x18000c7d4  mov     rcx, rbp
0x18000c7d7  cmova   r8d, edx
0x18000c7db  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000c7e0  mov     edi, eax
0x18000c7e2  test    eax, eax
0x18000c7e4  jns     short loc_18000C806
0x18000c7e6  mov     rcx, [rsp+278h]; this
0x18000c7ee  lea     r8, aWil; "wil"
0x18000c7f5  mov     r9d, eax; char *
0x18000c7f8  mov     edx, 8Bh; void *
0x18000c7fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c802  mov     eax, edi
0x18000c804  jmp     short loc_18000C85B
0x18000c806  lea     r8, asc_1800183E8; "h"
0x18000c80d  shr     rbx, 1Fh
0x18000c811  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x18000c816  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000c81b  test    ebx, ebx
0x18000c81d  lea     rcx, [rbp+8]
0x18000c821  lea     r9, [rsp+278h+var_238]
0x18000c826  mov     edx, ebx
0x18000c828  cmovnz  esi, ebx
0x18000c82b  mov     r8d, esi
0x18000c82e  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000c833  mov     ebx, eax
0x18000c835  test    eax, eax
0x18000c837  jns     short loc_18000C859
0x18000c839  mov     rcx, [rsp+278h]; this
0x18000c841  lea     r8, aWil; "wil"
0x18000c848  mov     r9d, eax; char *
0x18000c84b  mov     edx, 90h; void *
0x18000c850  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c855  mov     eax, ebx
0x18000c857  jmp     short loc_18000C85B
0x18000c859  xor     eax, eax
0x18000c85b  mov     rcx, [rsp+278h+var_28]
0x18000c863  xor     rcx, rsp; StackCookie
0x18000c866  call    __security_check_cookie
0x18000c86b  mov     rbx, [rsp+278h+arg_10]
0x18000c873  add     rsp, 260h
0x18000c87a  pop     rdi
0x18000c87b  pop     rsi
0x18000c87c  pop     rbp
0x18000c87d  retn
```
