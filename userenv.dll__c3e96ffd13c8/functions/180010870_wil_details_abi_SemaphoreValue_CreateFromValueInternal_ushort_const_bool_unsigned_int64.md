# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180010870`
- end: `0x180010991`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `289`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const unsigned __int16 *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010fec`
- `0x1800159c8`

## callees

- `0x1800080b4`
- `0x18000cea0`
- `0x18000cf1c`
- `0x18000d9b0`
- `0x180010870`
- `0x18001182c`
- `0x1800118ac`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        const unsigned __int16 *a2,
        __int64 a3,
        unsigned __int64 a4)
{
  LONG v6; // esi
  LONG v7; // r8d
  int semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  unsigned int v9; // edi
  unsigned __int64 v11; // rbx
  int v12; // eax
  unsigned int v13; // ebx
  int v14; // [rsp+20h] [rbp-268h]
  unsigned __int16 v15[264]; // [rsp+40h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  StringCchCopyW(v15, 0x104u, a2);
  StringCchCatW(v15, 0x104u, L"_p0");
  v6 = 1;
  v7 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v7 = a4 & 0x7FFFFFFF;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this, a4 & 0x7FFFFFFF, v7, v15);
  v9 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    v11 = a4 >> 31;
    StringCchCatW(v15, 0x104u, L"h");
    if ( (_DWORD)v11 )
      v6 = v11;
    v12 = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
            (__int64)this + 8,
            v11,
            v6,
            v15);
    v13 = v12;
    if ( v12 >= 0 )
    {
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x90,
        (unsigned int)"wil",
        (const char *)(unsigned int)v12,
        v14);
      return v13;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8B,
      (unsigned int)"wil",
      (const char *)(unsigned int)semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      v14);
    return v9;
  }
}

```

## disassembly

```asm
0x180010870  push    rbx
0x180010872  push    rbp
0x180010873  push    rsi
0x180010874  push    rdi
0x180010875  push    r14
0x180010877  sub     rsp, 260h
0x18001087e  mov     rax, cs:__security_cookie
0x180010885  xor     rax, rsp
0x180010888  mov     [rsp+288h+var_38], rax
0x180010890  mov     rax, 0C000000000000000h
0x18001089a  mov     rbx, r9
0x18001089d  mov     rbp, rcx
0x1800108a0  test    rax, r9
0x1800108a3  jz      short loc_1800108AB
0x1800108a5  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800108ab  mov     r8, rdx; unsigned __int16 *
0x1800108ae  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x1800108b3  mov     r14d, 104h
0x1800108b9  mov     edx, r14d; unsigned __int64
0x1800108bc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800108c1  lea     r8, aP0; "_p0"
0x1800108c8  mov     edx, r14d; unsigned __int64
0x1800108cb  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x1800108d0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800108d5  mov     edx, ebx
0x1800108d7  lea     r9, [rsp+288h+var_248]
0x1800108dc  and     edx, 7FFFFFFFh
0x1800108e2  mov     esi, 1
0x1800108e7  mov     r8d, esi
0x1800108ea  mov     rcx, rbp
0x1800108ed  cmova   r8d, edx
0x1800108f1  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800108f6  mov     edi, eax
0x1800108f8  test    eax, eax
0x1800108fa  jns     short loc_18001091B
0x1800108fc  mov     rcx, [rsp+288h]; this
0x180010904  lea     r8, aWil; "wil"
0x18001090b  mov     r9d, eax; char *
0x18001090e  lea     edx, [r14-79h]; void *
0x180010912  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010917  mov     eax, edi
0x180010919  jmp     short loc_180010973
0x18001091b  lea     r8, asc_18001F2E8; "h"
0x180010922  shr     rbx, 1Fh
0x180010926  mov     rdx, r14; unsigned __int64
0x180010929  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x18001092e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180010933  test    ebx, ebx
0x180010935  lea     rcx, [rbp+8]
0x180010939  lea     r9, [rsp+288h+var_248]
0x18001093e  mov     edx, ebx
0x180010940  cmovnz  esi, ebx
0x180010943  mov     r8d, esi
0x180010946  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18001094b  mov     ebx, eax
0x18001094d  test    eax, eax
0x18001094f  jns     short loc_180010971
0x180010951  mov     rcx, [rsp+288h]; this
0x180010959  lea     r8, aWil; "wil"
0x180010960  mov     r9d, eax; char *
0x180010963  mov     edx, 90h; void *
0x180010968  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001096d  mov     eax, ebx
0x18001096f  jmp     short loc_180010973
0x180010971  xor     eax, eax
0x180010973  mov     rcx, [rsp+288h+var_38]
0x18001097b  xor     rcx, rsp; StackCookie
0x18001097e  call    __security_check_cookie
0x180010983  add     rsp, 260h
0x18001098a  pop     r14
0x18001098c  pop     rdi
0x18001098d  pop     rsi
0x18001098e  pop     rbp
0x18001098f  pop     rbx
0x180010990  retn
```
