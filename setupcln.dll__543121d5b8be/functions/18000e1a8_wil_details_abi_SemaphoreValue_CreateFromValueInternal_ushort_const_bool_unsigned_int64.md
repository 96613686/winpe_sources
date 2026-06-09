# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18000e1a8`
- end: `0x18000e2bc`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `276`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const unsigned __int16 *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000fa94`
- `0x18000fbbc`

## callees

- `0x180007f14`
- `0x18000e1a8`
- `0x180010cdc`
- `0x1800113a4`
- `0x180011dcc`
- `0x180011f78`
- `0x1800131e0`

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
0x18000e1a8  mov     [rsp+arg_10], rbx
0x18000e1ad  push    rbp
0x18000e1ae  push    rsi
0x18000e1af  push    rdi
0x18000e1b0  sub     rsp, 260h
0x18000e1b7  mov     rax, cs:__security_cookie
0x18000e1be  xor     rax, rsp
0x18000e1c1  mov     [rsp+278h+var_28], rax
0x18000e1c9  mov     rax, 0C000000000000000h
0x18000e1d3  mov     rbx, r9
0x18000e1d6  mov     rbp, rcx
0x18000e1d9  test    rax, r9
0x18000e1dc  jnz     loc_18000E2B6
0x18000e1e2  mov     r8, rdx; unsigned __int16 *
0x18000e1e5  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x18000e1ea  mov     edx, 104h; unsigned __int64
0x18000e1ef  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000e1f4  lea     r8, aP0; "_p0"
0x18000e1fb  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x18000e200  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000e205  mov     edx, ebx
0x18000e207  lea     r9, [rsp+278h+var_238]
0x18000e20c  and     edx, 7FFFFFFFh
0x18000e212  mov     esi, 1
0x18000e217  mov     r8d, esi
0x18000e21a  mov     rcx, rbp
0x18000e21d  cmova   r8d, edx
0x18000e221  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000e226  mov     edi, eax
0x18000e228  test    eax, eax
0x18000e22a  jns     short loc_18000E245
0x18000e22c  mov     rcx, [rsp+278h]; this
0x18000e234  mov     r9d, eax; char *
0x18000e237  mov     edx, 8Bh; void *
0x18000e23c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e241  mov     eax, edi
0x18000e243  jmp     short loc_18000E293
0x18000e245  lea     r8, asc_18001A9F8; "h"
0x18000e24c  shr     rbx, 1Fh
0x18000e250  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x18000e255  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000e25a  test    ebx, ebx
0x18000e25c  lea     rcx, [rbp+8]
0x18000e260  lea     r9, [rsp+278h+var_238]
0x18000e265  mov     edx, ebx
0x18000e267  cmovnz  esi, ebx
0x18000e26a  mov     r8d, esi
0x18000e26d  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000e272  mov     ebx, eax
0x18000e274  test    eax, eax
0x18000e276  jns     short loc_18000E291
0x18000e278  mov     rcx, [rsp+278h]; this
0x18000e280  mov     r9d, eax; char *
0x18000e283  mov     edx, 90h; void *
0x18000e288  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e28d  mov     eax, ebx
0x18000e28f  jmp     short loc_18000E293
0x18000e291  xor     eax, eax
0x18000e293  mov     rcx, [rsp+278h+var_28]
0x18000e29b  xor     rcx, rsp; StackCookie
0x18000e29e  call    __security_check_cookie
0x18000e2a3  mov     rbx, [rsp+278h+arg_10]
0x18000e2ab  add     rsp, 260h
0x18000e2b2  pop     rdi
0x18000e2b3  pop     rsi
0x18000e2b4  pop     rbp
0x18000e2b5  retn
0x18000e2b6  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
