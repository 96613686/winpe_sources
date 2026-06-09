# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18000cb2c`
- end: `0x18000cc3d`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `273`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e240`
- `0x18000e39c`

## callees

- `0x180005280`
- `0x180008a90`
- `0x18000cb2c`
- `0x18000fdc0`
- `0x1800101f4`
- `0x180010c64`
- `0x180010d3c`

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
0x18000cb2c  mov     [rsp+arg_10], rbx
0x18000cb31  push    rbp
0x18000cb32  push    rsi
0x18000cb33  push    rdi
0x18000cb34  sub     rsp, 260h
0x18000cb3b  mov     rax, cs:__security_cookie
0x18000cb42  xor     rax, rsp
0x18000cb45  mov     [rsp+278h+var_28], rax
0x18000cb4d  mov     rax, 0C000000000000000h
0x18000cb57  mov     rbx, r9
0x18000cb5a  mov     rbp, rcx
0x18000cb5d  test    rax, r9
0x18000cb60  jz      short loc_18000CB68
0x18000cb62  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000cb68  mov     r8, rdx; unsigned __int16 *
0x18000cb6b  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x18000cb70  mov     edx, 104h; unsigned __int64
0x18000cb75  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000cb7a  lea     r8, aP0; "_p0"
0x18000cb81  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x18000cb86  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000cb8b  mov     edx, ebx
0x18000cb8d  lea     r9, [rsp+278h+var_238]
0x18000cb92  and     edx, 7FFFFFFFh
0x18000cb98  mov     esi, 1
0x18000cb9d  mov     r8d, esi
0x18000cba0  mov     rcx, rbp
0x18000cba3  cmova   r8d, edx
0x18000cba7  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000cbac  mov     edi, eax
0x18000cbae  test    eax, eax
0x18000cbb0  jns     short loc_18000CBCB
0x18000cbb2  mov     rcx, [rsp+278h]; this
0x18000cbba  mov     r9d, eax; char *
0x18000cbbd  mov     edx, 8Bh; void *
0x18000cbc2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cbc7  mov     eax, edi
0x18000cbc9  jmp     short loc_18000CC19
0x18000cbcb  lea     r8, asc_180022420; "h"
0x18000cbd2  shr     rbx, 1Fh
0x18000cbd6  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x18000cbdb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000cbe0  test    ebx, ebx
0x18000cbe2  lea     rcx, [rbp+8]
0x18000cbe6  lea     r9, [rsp+278h+var_238]
0x18000cbeb  mov     edx, ebx
0x18000cbed  cmovnz  esi, ebx
0x18000cbf0  mov     r8d, esi
0x18000cbf3  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000cbf8  mov     ebx, eax
0x18000cbfa  test    eax, eax
0x18000cbfc  jns     short loc_18000CC17
0x18000cbfe  mov     rcx, [rsp+278h]; this
0x18000cc06  mov     r9d, eax; char *
0x18000cc09  mov     edx, 90h; void *
0x18000cc0e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cc13  mov     eax, ebx
0x18000cc15  jmp     short loc_18000CC19
0x18000cc17  xor     eax, eax
0x18000cc19  mov     rcx, [rsp+278h+var_28]
0x18000cc21  xor     rcx, rsp; StackCookie
0x18000cc24  call    __security_check_cookie
0x18000cc29  mov     rbx, [rsp+278h+arg_10]
0x18000cc31  add     rsp, 260h
0x18000cc38  pop     rdi
0x18000cc39  pop     rsi
0x18000cc3a  pop     rbp
0x18000cc3b  retn
```
