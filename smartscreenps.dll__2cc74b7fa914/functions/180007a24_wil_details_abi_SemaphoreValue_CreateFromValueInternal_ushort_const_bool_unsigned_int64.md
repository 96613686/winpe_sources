# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180007a24`
- end: `0x180007b42`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `286`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008acc`

## callees

- `0x180001590`
- `0x180007a24`
- `0x180009094`
- `0x180009570`
- `0x180009664`
- `0x180009a84`
- `0x180009b48`

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
0x180007a24  mov     [rsp+arg_10], rbx
0x180007a29  push    rbp
0x180007a2a  push    rsi
0x180007a2b  push    rdi
0x180007a2c  sub     rsp, 260h
0x180007a33  mov     rax, cs:__security_cookie
0x180007a3a  xor     rax, rsp
0x180007a3d  mov     [rsp+278h+var_28], rax
0x180007a45  mov     rax, 0C000000000000000h
0x180007a4f  mov     rbx, r9
0x180007a52  mov     rbp, rcx
0x180007a55  test    rax, r9
0x180007a58  jz      short loc_180007A60
0x180007a5a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180007a60  mov     r9, rdx; pszSrc
0x180007a63  lea     rcx, [rsp+278h+pszDest]; pszDest
0x180007a68  mov     edx, 104h; cchDest
0x180007a6d  call    StringCopyWorkerW
0x180007a72  lea     r8, aP0; "_p0"
0x180007a79  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x180007a7e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007a83  mov     edx, ebx
0x180007a85  lea     r9, [rsp+278h+pszDest]
0x180007a8a  and     edx, 7FFFFFFFh
0x180007a90  mov     esi, 1
0x180007a95  mov     r8d, esi
0x180007a98  mov     rcx, rbp
0x180007a9b  cmova   r8d, edx
0x180007a9f  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180007aa4  mov     edi, eax
0x180007aa6  test    eax, eax
0x180007aa8  jns     short loc_180007ACA
0x180007aaa  mov     rcx, [rsp+278h]; this
0x180007ab2  lea     r8, aWil; "wil"
0x180007ab9  mov     r9d, eax; char *
0x180007abc  mov     edx, 8Bh; void *
0x180007ac1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007ac6  mov     eax, edi
0x180007ac8  jmp     short loc_180007B1F
0x180007aca  lea     r8, asc_180014A48; "h"
0x180007ad1  shr     rbx, 1Fh
0x180007ad5  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x180007ada  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007adf  test    ebx, ebx
0x180007ae1  lea     rcx, [rbp+8]
0x180007ae5  lea     r9, [rsp+278h+pszDest]
0x180007aea  mov     edx, ebx
0x180007aec  cmovnz  esi, ebx
0x180007aef  mov     r8d, esi
0x180007af2  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180007af7  mov     ebx, eax
0x180007af9  test    eax, eax
0x180007afb  jns     short loc_180007B1D
0x180007afd  mov     rcx, [rsp+278h]; this
0x180007b05  lea     r8, aWil; "wil"
0x180007b0c  mov     r9d, eax; char *
0x180007b0f  mov     edx, 90h; void *
0x180007b14  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007b19  mov     eax, ebx
0x180007b1b  jmp     short loc_180007B1F
0x180007b1d  xor     eax, eax
0x180007b1f  mov     rcx, [rsp+278h+var_28]
0x180007b27  xor     rcx, rsp; StackCookie
0x180007b2a  call    __security_check_cookie
0x180007b2f  mov     rbx, [rsp+278h+arg_10]
0x180007b37  add     rsp, 260h
0x180007b3e  pop     rdi
0x180007b3f  pop     rsi
0x180007b40  pop     rbp
0x180007b41  retn
```
