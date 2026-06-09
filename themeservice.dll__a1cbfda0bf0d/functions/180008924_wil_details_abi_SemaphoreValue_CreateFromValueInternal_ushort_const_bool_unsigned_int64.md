# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180008924`
- end: `0x180008a34`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `272`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const unsigned __int16 *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800096fc`
- `0x18000b6cc`

## callees

- `0x180006a08`
- `0x180008924`
- `0x180009b20`
- `0x180009e24`
- `0x18000a25c`
- `0x18000a2dc`
- `0x18000fa00`

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
0x180008924  mov     [rsp+arg_10], rbx
0x180008929  push    rbp
0x18000892a  push    rsi
0x18000892b  push    rdi
0x18000892c  sub     rsp, 260h
0x180008933  mov     rax, cs:__security_cookie
0x18000893a  xor     rax, rsp
0x18000893d  mov     [rsp+278h+var_28], rax
0x180008945  mov     rax, 0C000000000000000h
0x18000894f  mov     rbx, r9
0x180008952  mov     rbp, rcx
0x180008955  test    rax, r9
0x180008958  jz      short loc_180008960
0x18000895a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180008960  mov     r8, rdx; unsigned __int16 *
0x180008963  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x180008968  mov     edx, 104h; unsigned __int64
0x18000896d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180008972  lea     r8, aP0; "_p0"
0x180008979  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x18000897e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008983  mov     edx, ebx
0x180008985  lea     r9, [rsp+278h+var_238]
0x18000898a  and     edx, 7FFFFFFFh
0x180008990  mov     esi, 1
0x180008995  mov     r8d, esi
0x180008998  mov     rcx, rbp
0x18000899b  cmova   r8d, edx
0x18000899f  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800089a4  mov     edi, eax
0x1800089a6  test    eax, eax
0x1800089a8  jns     short loc_1800089C3
0x1800089aa  mov     rcx, [rsp+278h]; this
0x1800089b2  mov     r9d, eax; char *
0x1800089b5  mov     edx, 8Bh; void *
0x1800089ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800089bf  mov     eax, edi
0x1800089c1  jmp     short loc_180008A11
0x1800089c3  lea     r8, asc_1800121D8; "h"
0x1800089ca  shr     rbx, 1Fh
0x1800089ce  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x1800089d3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800089d8  test    ebx, ebx
0x1800089da  lea     rcx, [rbp+8]
0x1800089de  lea     r9, [rsp+278h+var_238]
0x1800089e3  mov     edx, ebx
0x1800089e5  cmovnz  esi, ebx
0x1800089e8  mov     r8d, esi
0x1800089eb  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800089f0  mov     ebx, eax
0x1800089f2  test    eax, eax
0x1800089f4  jns     short loc_180008A0F
0x1800089f6  mov     rcx, [rsp+278h]; this
0x1800089fe  mov     r9d, eax; char *
0x180008a01  mov     edx, 90h; void *
0x180008a06  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008a0b  mov     eax, ebx
0x180008a0d  jmp     short loc_180008A11
0x180008a0f  xor     eax, eax
0x180008a11  mov     rcx, [rsp+278h+var_28]
0x180008a19  xor     rcx, rsp; StackCookie
0x180008a1c  call    __security_check_cookie
0x180008a21  mov     rbx, [rsp+278h+arg_10]
0x180008a29  add     rsp, 260h
0x180008a30  pop     rdi
0x180008a31  pop     rsi
0x180008a32  pop     rbp
0x180008a33  retn
```
