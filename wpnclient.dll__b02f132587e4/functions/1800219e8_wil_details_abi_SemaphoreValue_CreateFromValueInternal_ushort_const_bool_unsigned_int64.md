# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1800219e8`
- end: `0x180021b06`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `286`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180021fa8`
- `0x18002aa90`

## callees

- `0x1800070e8`
- `0x18001203c`
- `0x18001356c`
- `0x18001ff00`
- `0x1800219e8`
- `0x180022a80`
- `0x180022af0`

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
  unsigned int v11; // edi
  unsigned __int64 v13; // rbx
  int v14; // eax
  unsigned int v15; // ebx
  size_t v16; // [rsp+20h] [rbp-258h]
  int v17; // [rsp+20h] [rbp-258h]
  wchar_t pszDest[264]; // [rsp+40h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  StringCopyWorkerW(pszDest, 0x104u, a3, a2, v16);
  StringCchCatW(pszDest, v6, L"_p0");
  v7 = 1;
  v8 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v8 = a4 & 0x7FFFFFFF;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this, a4 & 0x7FFFFFFF, v8, pszDest);
  v11 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    v13 = a4 >> 31;
    StringCchCatW(pszDest, v10, L"h");
    if ( (_DWORD)v13 )
      v7 = v13;
    v14 = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
            (__int64)this + 8,
            v13,
            v7,
            pszDest);
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
        v17);
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
      v17);
    return v11;
  }
}

```

## disassembly

```asm
0x1800219e8  mov     [rsp+arg_10], rbx
0x1800219ed  push    rbp
0x1800219ee  push    rsi
0x1800219ef  push    rdi
0x1800219f0  sub     rsp, 260h
0x1800219f7  mov     rax, cs:__security_cookie
0x1800219fe  xor     rax, rsp
0x180021a01  mov     [rsp+278h+var_28], rax
0x180021a09  mov     rax, 0C000000000000000h
0x180021a13  mov     rbx, r9
0x180021a16  mov     rbp, rcx
0x180021a19  test    rax, r9
0x180021a1c  jz      short loc_180021A24
0x180021a1e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180021a24  mov     r9, rdx; pszSrc
0x180021a27  lea     rcx, [rsp+278h+pszDest]; pszDest
0x180021a2c  mov     edx, 104h; cchDest
0x180021a31  call    StringCopyWorkerW
0x180021a36  lea     r8, aP0; "_p0"
0x180021a3d  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x180021a42  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180021a47  mov     edx, ebx
0x180021a49  lea     r9, [rsp+278h+pszDest]
0x180021a4e  and     edx, 7FFFFFFFh
0x180021a54  mov     esi, 1
0x180021a59  mov     r8d, esi
0x180021a5c  mov     rcx, rbp
0x180021a5f  cmova   r8d, edx
0x180021a63  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180021a68  mov     edi, eax
0x180021a6a  test    eax, eax
0x180021a6c  jns     short loc_180021A8E
0x180021a6e  mov     rcx, [rsp+278h]; this
0x180021a76  lea     r8, aWil; "wil"
0x180021a7d  mov     r9d, eax; char *
0x180021a80  mov     edx, 8Bh; void *
0x180021a85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021a8a  mov     eax, edi
0x180021a8c  jmp     short loc_180021AE3
0x180021a8e  lea     r8, asc_1800387D0; "h"
0x180021a95  shr     rbx, 1Fh
0x180021a99  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x180021a9e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180021aa3  test    ebx, ebx
0x180021aa5  lea     rcx, [rbp+8]
0x180021aa9  lea     r9, [rsp+278h+pszDest]
0x180021aae  mov     edx, ebx
0x180021ab0  cmovnz  esi, ebx
0x180021ab3  mov     r8d, esi
0x180021ab6  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180021abb  mov     ebx, eax
0x180021abd  test    eax, eax
0x180021abf  jns     short loc_180021AE1
0x180021ac1  mov     rcx, [rsp+278h]; this
0x180021ac9  lea     r8, aWil; "wil"
0x180021ad0  mov     r9d, eax; char *
0x180021ad3  mov     edx, 90h; void *
0x180021ad8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021add  mov     eax, ebx
0x180021adf  jmp     short loc_180021AE3
0x180021ae1  xor     eax, eax
0x180021ae3  mov     rcx, [rsp+278h+var_28]
0x180021aeb  xor     rcx, rsp; StackCookie
0x180021aee  call    __security_check_cookie
0x180021af3  mov     rbx, [rsp+278h+arg_10]
0x180021afb  add     rsp, 260h
0x180021b02  pop     rdi
0x180021b03  pop     rsi
0x180021b04  pop     rbp
0x180021b05  retn
```
