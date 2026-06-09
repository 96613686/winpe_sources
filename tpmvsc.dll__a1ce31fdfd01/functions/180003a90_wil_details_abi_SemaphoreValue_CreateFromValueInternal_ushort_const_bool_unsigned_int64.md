# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180003a90`
- end: `0x180003ba0`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `272`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const unsigned __int16 *, size_t *, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004b24`

## callees

- `0x180001ec0`
- `0x180003a90`
- `0x1800051b4`
- `0x18000568c`
- `0x18000576c`
- `0x180005be0`
- `0x180005ca4`

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
0x180003a90  mov     [rsp+arg_10], rbx
0x180003a95  push    rbp
0x180003a96  push    rsi
0x180003a97  push    rdi
0x180003a98  sub     rsp, 260h
0x180003a9f  mov     rax, cs:__security_cookie
0x180003aa6  xor     rax, rsp
0x180003aa9  mov     [rsp+278h+var_28], rax
0x180003ab1  mov     rax, 0C000000000000000h
0x180003abb  mov     rbx, r9
0x180003abe  mov     rbp, rcx
0x180003ac1  test    rax, r9
0x180003ac4  jz      short loc_180003ACC
0x180003ac6  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003acc  mov     r9, rdx; pszSrc
0x180003acf  lea     rcx, [rsp+278h+pszDest]; pszDest
0x180003ad4  mov     edx, 104h; cchDest
0x180003ad9  call    StringCopyWorkerW
0x180003ade  lea     r8, aP0; "_p0"
0x180003ae5  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x180003aea  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003aef  mov     edx, ebx
0x180003af1  lea     r9, [rsp+278h+pszDest]
0x180003af6  and     edx, 7FFFFFFFh
0x180003afc  mov     esi, 1
0x180003b01  mov     r8d, esi
0x180003b04  mov     rcx, rbp
0x180003b07  cmova   r8d, edx
0x180003b0b  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180003b10  mov     edi, eax
0x180003b12  test    eax, eax
0x180003b14  jns     short loc_180003B2F
0x180003b16  mov     rcx, [rsp+278h]; this
0x180003b1e  mov     r9d, eax; char *
0x180003b21  mov     edx, 8Bh; void *
0x180003b26  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003b2b  mov     eax, edi
0x180003b2d  jmp     short loc_180003B7D
0x180003b2f  lea     r8, asc_180039F60; "h"
0x180003b36  shr     rbx, 1Fh
0x180003b3a  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x180003b3f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003b44  test    ebx, ebx
0x180003b46  lea     rcx, [rbp+8]
0x180003b4a  lea     r9, [rsp+278h+pszDest]
0x180003b4f  mov     edx, ebx
0x180003b51  cmovnz  esi, ebx
0x180003b54  mov     r8d, esi
0x180003b57  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180003b5c  mov     ebx, eax
0x180003b5e  test    eax, eax
0x180003b60  jns     short loc_180003B7B
0x180003b62  mov     rcx, [rsp+278h]; this
0x180003b6a  mov     r9d, eax; char *
0x180003b6d  mov     edx, 90h; void *
0x180003b72  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003b77  mov     eax, ebx
0x180003b79  jmp     short loc_180003B7D
0x180003b7b  xor     eax, eax
0x180003b7d  mov     rcx, [rsp+278h+var_28]
0x180003b85  xor     rcx, rsp; StackCookie
0x180003b88  call    __security_check_cookie
0x180003b8d  mov     rbx, [rsp+278h+arg_10]
0x180003b95  add     rsp, 260h
0x180003b9c  pop     rdi
0x180003b9d  pop     rsi
0x180003b9e  pop     rbp
0x180003b9f  retn
```
