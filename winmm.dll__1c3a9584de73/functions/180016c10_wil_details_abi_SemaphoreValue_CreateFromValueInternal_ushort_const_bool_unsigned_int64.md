# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180016c10`
- end: `0x180016d20`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `272`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018290`
- `0x1800183b4`

## callees

- `0x180003a2c`
- `0x1800098f0`
- `0x18000a3b0`
- `0x18000c990`
- `0x180016c10`
- `0x180019718`
- `0x1800197f0`

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
0x180016c10  mov     [rsp+arg_10], rbx
0x180016c15  push    rbp
0x180016c16  push    rsi
0x180016c17  push    rdi
0x180016c18  sub     rsp, 260h
0x180016c1f  mov     rax, cs:__security_cookie
0x180016c26  xor     rax, rsp
0x180016c29  mov     [rsp+278h+var_28], rax
0x180016c31  mov     rax, 0C000000000000000h
0x180016c3b  mov     rbx, r9
0x180016c3e  mov     rbp, rcx
0x180016c41  test    rax, r9
0x180016c44  jz      short loc_180016C4C
0x180016c46  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180016c4c  mov     r8, rdx; unsigned __int16 *
0x180016c4f  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x180016c54  mov     edx, 104h; unsigned __int64
0x180016c59  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180016c5e  lea     r8, aP0; "_p0"
0x180016c65  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x180016c6a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180016c6f  mov     edx, ebx
0x180016c71  lea     r9, [rsp+278h+var_238]
0x180016c76  and     edx, 7FFFFFFFh
0x180016c7c  mov     esi, 1
0x180016c81  mov     r8d, esi
0x180016c84  mov     rcx, rbp
0x180016c87  cmova   r8d, edx
0x180016c8b  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180016c90  mov     edi, eax
0x180016c92  test    eax, eax
0x180016c94  jns     short loc_180016CAF
0x180016c96  mov     rcx, [rsp+278h]; this
0x180016c9e  mov     r9d, eax; char *
0x180016ca1  mov     edx, 8Bh; void *
0x180016ca6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016cab  mov     eax, edi
0x180016cad  jmp     short loc_180016CFD
0x180016caf  lea     r8, asc_18001D200; "h"
0x180016cb6  shr     rbx, 1Fh
0x180016cba  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x180016cbf  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180016cc4  test    ebx, ebx
0x180016cc6  lea     rcx, [rbp+8]
0x180016cca  lea     r9, [rsp+278h+var_238]
0x180016ccf  mov     edx, ebx
0x180016cd1  cmovnz  esi, ebx
0x180016cd4  mov     r8d, esi
0x180016cd7  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180016cdc  mov     ebx, eax
0x180016cde  test    eax, eax
0x180016ce0  jns     short loc_180016CFB
0x180016ce2  mov     rcx, [rsp+278h]; this
0x180016cea  mov     r9d, eax; char *
0x180016ced  mov     edx, 90h; void *
0x180016cf2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016cf7  mov     eax, ebx
0x180016cf9  jmp     short loc_180016CFD
0x180016cfb  xor     eax, eax
0x180016cfd  mov     rcx, [rsp+278h+var_28]
0x180016d05  xor     rcx, rsp; StackCookie
0x180016d08  call    __security_check_cookie
0x180016d0d  mov     rbx, [rsp+278h+arg_10]
0x180016d15  add     rsp, 260h
0x180016d1c  pop     rdi
0x180016d1d  pop     rsi
0x180016d1e  pop     rbp
0x180016d1f  retn
```
