# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18003651c`
- end: `0x180036630`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `276`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180037864`
- `0x180037988`

## callees

- `0x180026730`
- `0x1800267b0`
- `0x180034510`
- `0x18003651c`
- `0x18003860c`
- `0x1800395f8`
- `0x1800396cc`

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
  unsigned int v9; // r8d
  unsigned int v10; // edi
  unsigned __int64 v12; // rbx
  int v13; // eax
  unsigned int v14; // r8d
  unsigned int v15; // ebx
  int v16; // [rsp+20h] [rbp-268h]
  wchar_t pszDest[264]; // [rsp+40h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  StringCchCopyW(pszDest, 0x104u, a2);
  StringCchCatW(pszDest, 0x104u, L"_p0");
  v6 = 1;
  v7 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v7 = a4 & 0x7FFFFFFF;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this, a4 & 0x7FFFFFFF, v7, pszDest);
  v10 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    v12 = a4 >> 31;
    StringCchCatW(pszDest, 0x104u, L"h");
    if ( (_DWORD)v12 )
      v6 = v12;
    v13 = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
            (__int64)this + 8,
            v12,
            v6,
            pszDest);
    v15 = v13;
    if ( v13 >= 0 )
    {
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x90, v14, (const char *)(unsigned int)v13, v16);
      return v15;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8B,
      v9,
      (const char *)(unsigned int)semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      v16);
    return v10;
  }
}

```

## disassembly

```asm
0x18003651c  push    rbx
0x18003651e  push    rbp
0x18003651f  push    rsi
0x180036520  push    rdi
0x180036521  push    r14
0x180036523  sub     rsp, 260h
0x18003652a  mov     rax, cs:__security_cookie
0x180036531  xor     rax, rsp
0x180036534  mov     [rsp+288h+var_38], rax
0x18003653c  mov     rax, 0C000000000000000h
0x180036546  mov     rbx, r9
0x180036549  mov     rbp, rcx
0x18003654c  test    rax, r9
0x18003654f  jz      short loc_180036557
0x180036551  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180036557  mov     r8, rdx; pszSrc
0x18003655a  lea     rcx, [rsp+288h+pszDest]; pszDest
0x18003655f  mov     r14d, 104h
0x180036565  mov     edx, r14d; cchDest
0x180036568  call    StringCchCopyW
0x18003656d  lea     r8, aP0; "_p0"
0x180036574  mov     edx, r14d; cchDest
0x180036577  lea     rcx, [rsp+288h+pszDest]; pszDest
0x18003657c  call    StringCchCatW
0x180036581  mov     edx, ebx
0x180036583  lea     r9, [rsp+288h+pszDest]
0x180036588  and     edx, 7FFFFFFFh
0x18003658e  mov     esi, 1
0x180036593  mov     r8d, esi
0x180036596  mov     rcx, rbp
0x180036599  cmova   r8d, edx
0x18003659d  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800365a2  mov     edi, eax
0x1800365a4  test    eax, eax
0x1800365a6  jns     short loc_1800365C0
0x1800365a8  mov     rcx, [rsp+288h]; this
0x1800365b0  lea     edx, [r14-79h]; void *
0x1800365b4  mov     r9d, eax; char *
0x1800365b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800365bc  mov     eax, edi
0x1800365be  jmp     short loc_180036611
0x1800365c0  lea     r8, asc_18004F838; "h"
0x1800365c7  shr     rbx, 1Fh
0x1800365cb  mov     rdx, r14; cchDest
0x1800365ce  lea     rcx, [rsp+288h+pszDest]; pszDest
0x1800365d3  call    StringCchCatW
0x1800365d8  test    ebx, ebx
0x1800365da  lea     rcx, [rbp+8]
0x1800365de  lea     r9, [rsp+288h+pszDest]
0x1800365e3  mov     edx, ebx
0x1800365e5  cmovnz  esi, ebx
0x1800365e8  mov     r8d, esi
0x1800365eb  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800365f0  mov     ebx, eax
0x1800365f2  test    eax, eax
0x1800365f4  jns     short loc_18003660F
0x1800365f6  mov     rcx, [rsp+288h]; this
0x1800365fe  mov     r9d, eax; char *
0x180036601  mov     edx, 90h; void *
0x180036606  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003660b  mov     eax, ebx
0x18003660d  jmp     short loc_180036611
0x18003660f  xor     eax, eax
0x180036611  mov     rcx, [rsp+288h+var_38]
0x180036619  xor     rcx, rsp; StackCookie
0x18003661c  call    __security_check_cookie
0x180036621  add     rsp, 260h
0x180036628  pop     r14
0x18003662a  pop     rdi
0x18003662b  pop     rsi
0x18003662c  pop     rbp
0x18003662d  pop     rbx
0x18003662e  retn
```
