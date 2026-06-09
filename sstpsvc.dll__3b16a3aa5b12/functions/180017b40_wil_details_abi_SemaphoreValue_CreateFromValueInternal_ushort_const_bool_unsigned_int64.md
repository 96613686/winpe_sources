# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180017b40`
- end: `0x180017c4f`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `271`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800191a8`
- `0x1800192d0`

## callees

- `0x1800164bc`
- `0x180017b40`
- `0x18001a354`
- `0x18001a804`
- `0x18001b1ec`
- `0x18001b354`
- `0x18001bcf0`

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
0x180017b40  mov     [rsp+arg_10], rbx
0x180017b45  push    rbp
0x180017b46  push    rsi
0x180017b47  push    rdi
0x180017b48  sub     rsp, 260h
0x180017b4f  mov     rax, cs:__security_cookie
0x180017b56  xor     rax, rsp
0x180017b59  mov     [rsp+278h+var_28], rax
0x180017b61  mov     rax, 0C000000000000000h
0x180017b6b  mov     rbx, r9
0x180017b6e  mov     rbp, rcx
0x180017b71  test    rax, r9
0x180017b74  jnz     loc_180017C49
0x180017b7a  mov     r8, rdx; unsigned __int16 *
0x180017b7d  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x180017b82  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180017b87  lea     r8, aP0; "_p0"
0x180017b8e  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x180017b93  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180017b98  mov     edx, ebx
0x180017b9a  lea     r9, [rsp+278h+var_238]
0x180017b9f  and     edx, 7FFFFFFFh
0x180017ba5  mov     esi, 1
0x180017baa  mov     r8d, esi
0x180017bad  mov     rcx, rbp
0x180017bb0  cmova   r8d, edx
0x180017bb4  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180017bb9  mov     edi, eax
0x180017bbb  test    eax, eax
0x180017bbd  jns     short loc_180017BD8
0x180017bbf  mov     rcx, [rsp+278h]; this
0x180017bc7  mov     r9d, eax; char *
0x180017bca  mov     edx, 8Bh; void *
0x180017bcf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017bd4  mov     eax, edi
0x180017bd6  jmp     short loc_180017C26
0x180017bd8  lea     r8, asc_180027B20; "h"
0x180017bdf  shr     rbx, 1Fh
0x180017be3  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x180017be8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180017bed  test    ebx, ebx
0x180017bef  lea     rcx, [rbp+8]
0x180017bf3  lea     r9, [rsp+278h+var_238]
0x180017bf8  mov     edx, ebx
0x180017bfa  cmovnz  esi, ebx
0x180017bfd  mov     r8d, esi
0x180017c00  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180017c05  mov     ebx, eax
0x180017c07  test    eax, eax
0x180017c09  jns     short loc_180017C24
0x180017c0b  mov     rcx, [rsp+278h]; this
0x180017c13  mov     r9d, eax; char *
0x180017c16  mov     edx, 90h; void *
0x180017c1b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017c20  mov     eax, ebx
0x180017c22  jmp     short loc_180017C26
0x180017c24  xor     eax, eax
0x180017c26  mov     rcx, [rsp+278h+var_28]
0x180017c2e  xor     rcx, rsp; StackCookie
0x180017c31  call    __security_check_cookie
0x180017c36  mov     rbx, [rsp+278h+arg_10]
0x180017c3e  add     rsp, 260h
0x180017c45  pop     rdi
0x180017c46  pop     rsi
0x180017c47  pop     rbp
0x180017c48  retn
0x180017c49  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
