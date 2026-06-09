# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18000a500`
- end: `0x18000a621`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `289`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b2c4`
- `0x18000f0a8`

## callees

- `0x180008320`
- `0x18000a500`
- `0x18000b924`
- `0x18000be40`
- `0x18000bf34`
- `0x18000c45c`
- `0x18000c520`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        size_t *a2,
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
0x18000a500  push    rbx
0x18000a502  push    rbp
0x18000a503  push    rsi
0x18000a504  push    rdi
0x18000a505  push    r14
0x18000a507  sub     rsp, 260h
0x18000a50e  mov     rax, cs:__security_cookie
0x18000a515  xor     rax, rsp
0x18000a518  mov     [rsp+288h+var_38], rax
0x18000a520  mov     rax, 0C000000000000000h
0x18000a52a  mov     rbx, r9
0x18000a52d  mov     rbp, rcx
0x18000a530  test    rax, r9
0x18000a533  jz      short loc_18000A53B
0x18000a535  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000a53b  mov     r8, rdx; unsigned __int16 *
0x18000a53e  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x18000a543  mov     r14d, 104h
0x18000a549  mov     edx, r14d; unsigned __int64
0x18000a54c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000a551  lea     r8, aP0; "_p0"
0x18000a558  mov     edx, r14d; unsigned __int64
0x18000a55b  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x18000a560  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a565  mov     edx, ebx
0x18000a567  lea     r9, [rsp+288h+var_248]
0x18000a56c  and     edx, 7FFFFFFFh
0x18000a572  mov     esi, 1
0x18000a577  mov     r8d, esi
0x18000a57a  mov     rcx, rbp
0x18000a57d  cmova   r8d, edx
0x18000a581  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000a586  mov     edi, eax
0x18000a588  test    eax, eax
0x18000a58a  jns     short loc_18000A5AB
0x18000a58c  mov     rcx, [rsp+288h]; this
0x18000a594  lea     r8, aWil; "wil"
0x18000a59b  mov     r9d, eax; char *
0x18000a59e  lea     edx, [r14-79h]; void *
0x18000a5a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a5a7  mov     eax, edi
0x18000a5a9  jmp     short loc_18000A603
0x18000a5ab  lea     r8, asc_18002C6E0; "h"
0x18000a5b2  shr     rbx, 1Fh
0x18000a5b6  mov     rdx, r14; unsigned __int64
0x18000a5b9  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x18000a5be  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a5c3  test    ebx, ebx
0x18000a5c5  lea     rcx, [rbp+8]
0x18000a5c9  lea     r9, [rsp+288h+var_248]
0x18000a5ce  mov     edx, ebx
0x18000a5d0  cmovnz  esi, ebx
0x18000a5d3  mov     r8d, esi
0x18000a5d6  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000a5db  mov     ebx, eax
0x18000a5dd  test    eax, eax
0x18000a5df  jns     short loc_18000A601
0x18000a5e1  mov     rcx, [rsp+288h]; this
0x18000a5e9  lea     r8, aWil; "wil"
0x18000a5f0  mov     r9d, eax; char *
0x18000a5f3  mov     edx, 90h; void *
0x18000a5f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a5fd  mov     eax, ebx
0x18000a5ff  jmp     short loc_18000A603
0x18000a601  xor     eax, eax
0x18000a603  mov     rcx, [rsp+288h+var_38]
0x18000a60b  xor     rcx, rsp; StackCookie
0x18000a60e  call    __security_check_cookie
0x18000a613  add     rsp, 260h
0x18000a61a  pop     r14
0x18000a61c  pop     rdi
0x18000a61d  pop     rsi
0x18000a61e  pop     rbp
0x18000a61f  pop     rbx
0x18000a620  retn
```
