# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180018eec`
- end: `0x180018ffc`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `272`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001a624`
- `0x18001a74c`

## callees

- `0x1800176e8`
- `0x180018eec`
- `0x18001b87c`
- `0x18001bd3c`
- `0x18001c710`
- `0x18001c7f0`
- `0x18001d210`

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
  StringCchCopyW(v19, (unsigned __int64)a2, a2);
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
0x180018eec  mov     [rsp+arg_10], rbx
0x180018ef1  push    rbp
0x180018ef2  push    rsi
0x180018ef3  push    rdi
0x180018ef4  sub     rsp, 260h
0x180018efb  mov     rax, cs:__security_cookie
0x180018f02  xor     rax, rsp
0x180018f05  mov     [rsp+278h+var_28], rax
0x180018f0d  mov     rax, 0C000000000000000h
0x180018f17  mov     rbx, r9
0x180018f1a  mov     rbp, rcx
0x180018f1d  test    rax, r9
0x180018f20  jnz     loc_180018FF6
0x180018f26  mov     r8, rdx; unsigned __int16 *
0x180018f29  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x180018f2e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180018f33  lea     r8, aP0; "_p0"
0x180018f3a  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x180018f3f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180018f44  mov     edx, ebx
0x180018f46  lea     r9, [rsp+278h+var_238]
0x180018f4b  and     edx, 7FFFFFFFh
0x180018f51  mov     esi, 1
0x180018f56  mov     r8d, esi
0x180018f59  mov     rcx, rbp
0x180018f5c  cmova   r8d, edx
0x180018f60  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180018f65  mov     edi, eax
0x180018f67  test    eax, eax
0x180018f69  jns     short loc_180018F84
0x180018f6b  mov     rcx, [rsp+278h]; this
0x180018f73  mov     r9d, eax; char *
0x180018f76  mov     edx, 8Bh; void *
0x180018f7b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018f80  mov     eax, edi
0x180018f82  jmp     short loc_180018FD2
0x180018f84  lea     r8, asc_180028B20; "h"
0x180018f8b  shr     rbx, 1Fh
0x180018f8f  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x180018f94  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180018f99  test    ebx, ebx
0x180018f9b  lea     rcx, [rbp+8]
0x180018f9f  lea     r9, [rsp+278h+var_238]
0x180018fa4  mov     edx, ebx
0x180018fa6  cmovnz  esi, ebx
0x180018fa9  mov     r8d, esi
0x180018fac  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180018fb1  mov     ebx, eax
0x180018fb3  test    eax, eax
0x180018fb5  jns     short loc_180018FD0
0x180018fb7  mov     rcx, [rsp+278h]; this
0x180018fbf  mov     r9d, eax; char *
0x180018fc2  mov     edx, 90h; void *
0x180018fc7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018fcc  mov     eax, ebx
0x180018fce  jmp     short loc_180018FD2
0x180018fd0  xor     eax, eax
0x180018fd2  mov     rcx, [rsp+278h+var_28]
0x180018fda  xor     rcx, rsp; StackCookie
0x180018fdd  call    __security_check_cookie
0x180018fe2  mov     rbx, [rsp+278h+arg_10]
0x180018fea  add     rsp, 260h
0x180018ff1  pop     rdi
0x180018ff2  pop     rsi
0x180018ff3  pop     rbp
0x180018ff4  retn
0x180018ff6  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
