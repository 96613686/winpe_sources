# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18000da54`
- end: `0x18000db64`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `272`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a704`
- `0x18000a858`

## callees

- `0x18000a9b4`
- `0x18000b550`
- `0x18000da54`
- `0x18000fe80`
- `0x18000ff60`
- `0x1800108b4`
- `0x180010988`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        const unsigned __int16 *a2,
        size_t *a3,
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
  size_t v18; // [rsp+20h] [rbp-258h]
  int v19; // [rsp+20h] [rbp-258h]
  wchar_t pszDest[264]; // [rsp+40h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  StringCopyWorkerW(pszDest, 0x104u, a3, a2, v18);
  StringCchCatW(pszDest, v6, L"_p0");
  v7 = 1;
  v8 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v8 = a4 & 0x7FFFFFFF;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this, a4 & 0x7FFFFFFF, v8, pszDest);
  v12 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    v14 = a4 >> 31;
    StringCchCatW(pszDest, v10, L"h");
    if ( (_DWORD)v14 )
      v7 = v14;
    v15 = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
            (__int64)this + 8,
            v14,
            v7,
            pszDest);
    v17 = v15;
    if ( v15 >= 0 )
    {
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x90, v16, (const char *)(unsigned int)v15, v19);
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
      v19);
    return v12;
  }
}

```

## disassembly

```asm
0x18000da54  mov     [rsp+arg_10], rbx
0x18000da59  push    rbp
0x18000da5a  push    rsi
0x18000da5b  push    rdi
0x18000da5c  sub     rsp, 260h
0x18000da63  mov     rax, cs:__security_cookie
0x18000da6a  xor     rax, rsp
0x18000da6d  mov     [rsp+278h+var_28], rax
0x18000da75  mov     rax, 0C000000000000000h
0x18000da7f  mov     rbx, r9
0x18000da82  mov     rbp, rcx
0x18000da85  test    rax, r9
0x18000da88  jz      short loc_18000DA90
0x18000da8a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000da90  mov     r9, rdx; pszSrc
0x18000da93  lea     rcx, [rsp+278h+pszDest]; pszDest
0x18000da98  mov     edx, 104h; cchDest
0x18000da9d  call    StringCopyWorkerW
0x18000daa2  lea     r8, aP0; "_p0"
0x18000daa9  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x18000daae  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000dab3  mov     edx, ebx
0x18000dab5  lea     r9, [rsp+278h+pszDest]
0x18000daba  and     edx, 7FFFFFFFh
0x18000dac0  mov     esi, 1
0x18000dac5  mov     r8d, esi
0x18000dac8  mov     rcx, rbp
0x18000dacb  cmova   r8d, edx
0x18000dacf  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000dad4  mov     edi, eax
0x18000dad6  test    eax, eax
0x18000dad8  jns     short loc_18000DAF3
0x18000dada  mov     rcx, [rsp+278h]; this
0x18000dae2  mov     r9d, eax; char *
0x18000dae5  mov     edx, 8Bh; void *
0x18000daea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000daef  mov     eax, edi
0x18000daf1  jmp     short loc_18000DB41
0x18000daf3  lea     r8, asc_18001FB20; "h"
0x18000dafa  shr     rbx, 1Fh
0x18000dafe  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x18000db03  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000db08  test    ebx, ebx
0x18000db0a  lea     rcx, [rbp+8]
0x18000db0e  lea     r9, [rsp+278h+pszDest]
0x18000db13  mov     edx, ebx
0x18000db15  cmovnz  esi, ebx
0x18000db18  mov     r8d, esi
0x18000db1b  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000db20  mov     ebx, eax
0x18000db22  test    eax, eax
0x18000db24  jns     short loc_18000DB3F
0x18000db26  mov     rcx, [rsp+278h]; this
0x18000db2e  mov     r9d, eax; char *
0x18000db31  mov     edx, 90h; void *
0x18000db36  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000db3b  mov     eax, ebx
0x18000db3d  jmp     short loc_18000DB41
0x18000db3f  xor     eax, eax
0x18000db41  mov     rcx, [rsp+278h+var_28]
0x18000db49  xor     rcx, rsp; StackCookie
0x18000db4c  call    __security_check_cookie
0x18000db51  mov     rbx, [rsp+278h+arg_10]
0x18000db59  add     rsp, 260h
0x18000db60  pop     rdi
0x18000db61  pop     rsi
0x18000db62  pop     rbp
0x18000db63  retn
```
