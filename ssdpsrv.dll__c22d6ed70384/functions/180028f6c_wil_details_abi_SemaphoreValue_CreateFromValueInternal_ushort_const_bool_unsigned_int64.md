# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180028f6c`
- end: `0x18002907f`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `275`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const unsigned __int16 *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002a2f8`
- `0x18002a41c`

## callees

- `0x18001bbec`
- `0x18001c724`
- `0x180026a30`
- `0x180028f6c`
- `0x18002b410`
- `0x18002c348`
- `0x18002c418`

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
  unsigned __int16 v17[264]; // [rsp+40h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  StringCchCopyW(v17, 0x104u, a2);
  StringCchCatW(v17, 0x104u, L"_p0");
  v6 = 1;
  v7 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v7 = a4 & 0x7FFFFFFF;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this, a4 & 0x7FFFFFFF, v7, v17);
  v10 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    v12 = a4 >> 31;
    StringCchCatW(v17, 0x104u, L"h");
    if ( (_DWORD)v12 )
      v6 = v12;
    v13 = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
            (__int64)this + 8,
            v12,
            v6,
            v17);
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
0x180028f6c  push    rbx
0x180028f6e  push    rbp
0x180028f6f  push    rsi
0x180028f70  push    rdi
0x180028f71  push    r14
0x180028f73  sub     rsp, 260h
0x180028f7a  mov     rax, cs:__security_cookie
0x180028f81  xor     rax, rsp
0x180028f84  mov     [rsp+288h+var_38], rax
0x180028f8c  mov     rax, 0C000000000000000h
0x180028f96  mov     rbx, r9
0x180028f99  mov     rbp, rcx
0x180028f9c  test    rax, r9
0x180028f9f  jz      short loc_180028FA7
0x180028fa1  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180028fa7  mov     r8, rdx; unsigned __int16 *
0x180028faa  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x180028faf  mov     r14d, 104h
0x180028fb5  mov     edx, r14d; unsigned __int64
0x180028fb8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180028fbd  lea     r8, aP0; "_p0"
0x180028fc4  mov     edx, r14d; unsigned __int64
0x180028fc7  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x180028fcc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180028fd1  mov     edx, ebx
0x180028fd3  lea     r9, [rsp+288h+var_248]
0x180028fd8  and     edx, 7FFFFFFFh
0x180028fde  mov     esi, 1
0x180028fe3  mov     r8d, esi
0x180028fe6  mov     rcx, rbp
0x180028fe9  cmova   r8d, edx
0x180028fed  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180028ff2  mov     edi, eax
0x180028ff4  test    eax, eax
0x180028ff6  jns     short loc_180029010
0x180028ff8  mov     rcx, [rsp+288h]; this
0x180029000  lea     edx, [r14-79h]; void *
0x180029004  mov     r9d, eax; char *
0x180029007  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002900c  mov     eax, edi
0x18002900e  jmp     short loc_180029061
0x180029010  lea     r8, asc_18003A508; "h"
0x180029017  shr     rbx, 1Fh
0x18002901b  mov     rdx, r14; unsigned __int64
0x18002901e  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x180029023  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180029028  test    ebx, ebx
0x18002902a  lea     rcx, [rbp+8]
0x18002902e  lea     r9, [rsp+288h+var_248]
0x180029033  mov     edx, ebx
0x180029035  cmovnz  esi, ebx
0x180029038  mov     r8d, esi
0x18002903b  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180029040  mov     ebx, eax
0x180029042  test    eax, eax
0x180029044  jns     short loc_18002905F
0x180029046  mov     rcx, [rsp+288h]; this
0x18002904e  mov     r9d, eax; char *
0x180029051  mov     edx, 90h; void *
0x180029056  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002905b  mov     eax, ebx
0x18002905d  jmp     short loc_180029061
0x18002905f  xor     eax, eax
0x180029061  mov     rcx, [rsp+288h+var_38]
0x180029069  xor     rcx, rsp; StackCookie
0x18002906c  call    __security_check_cookie
0x180029071  add     rsp, 260h
0x180029078  pop     r14
0x18002907a  pop     rdi
0x18002907b  pop     rsi
0x18002907c  pop     rbp
0x18002907d  pop     rbx
0x18002907e  retn
```
