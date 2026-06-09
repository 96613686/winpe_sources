# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180005f40`
- end: `0x180006059`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `281`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const unsigned __int16 *, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800077d0`

## callees

- `0x1800027f0`
- `0x180005f40`
- `0x180008614`
- `0x180008c7c`
- `0x180008cc8`
- `0x1800095c4`
- `0x180009688`

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
  unsigned int v11; // edi
  unsigned __int64 v13; // rbx
  int v14; // eax
  unsigned int v15; // ebx
  int v16; // [rsp+20h] [rbp-258h]
  unsigned __int16 v17[264]; // [rsp+40h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  StringCchCopyW(v17, (unsigned __int64)a2, a2);
  StringCchCatW(v17, v6, L"_p0");
  v7 = 1;
  v8 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v8 = a4 & 0x7FFFFFFF;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this, a4 & 0x7FFFFFFF, v8, v17);
  v11 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    v13 = a4 >> 31;
    StringCchCatW(v17, v10, L"h");
    if ( (_DWORD)v13 )
      v7 = v13;
    v14 = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
            (__int64)this + 8,
            v13,
            v7,
            v17);
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
        v16);
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
      v16);
    return v11;
  }
}

```

## disassembly

```asm
0x180005f40  mov     [rsp+arg_10], rbx
0x180005f45  push    rbp
0x180005f46  push    rsi
0x180005f47  push    rdi
0x180005f48  sub     rsp, 260h
0x180005f4f  mov     rax, cs:__security_cookie
0x180005f56  xor     rax, rsp
0x180005f59  mov     [rsp+278h+var_28], rax
0x180005f61  mov     rax, 0C000000000000000h
0x180005f6b  mov     rbx, r9
0x180005f6e  mov     rbp, rcx
0x180005f71  test    rax, r9
0x180005f74  jz      short loc_180005F7C
0x180005f76  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180005f7c  mov     r8, rdx; unsigned __int16 *
0x180005f7f  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x180005f84  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180005f89  lea     r8, aP0; "_p0"
0x180005f90  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x180005f95  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005f9a  mov     edx, ebx
0x180005f9c  lea     r9, [rsp+278h+var_238]
0x180005fa1  and     edx, 7FFFFFFFh
0x180005fa7  mov     esi, 1
0x180005fac  mov     r8d, esi
0x180005faf  mov     rcx, rbp
0x180005fb2  cmova   r8d, edx
0x180005fb6  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180005fbb  mov     edi, eax
0x180005fbd  test    eax, eax
0x180005fbf  jns     short loc_180005FE1
0x180005fc1  mov     rcx, [rsp+278h]; this
0x180005fc9  lea     r8, aWil; "wil"
0x180005fd0  mov     r9d, eax; char *
0x180005fd3  mov     edx, 8Bh; void *
0x180005fd8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005fdd  mov     eax, edi
0x180005fdf  jmp     short loc_180006036
0x180005fe1  lea     r8, asc_180017F88; "h"
0x180005fe8  shr     rbx, 1Fh
0x180005fec  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x180005ff1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005ff6  test    ebx, ebx
0x180005ff8  lea     rcx, [rbp+8]
0x180005ffc  lea     r9, [rsp+278h+var_238]
0x180006001  mov     edx, ebx
0x180006003  cmovnz  esi, ebx
0x180006006  mov     r8d, esi
0x180006009  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000600e  mov     ebx, eax
0x180006010  test    eax, eax
0x180006012  jns     short loc_180006034
0x180006014  mov     rcx, [rsp+278h]; this
0x18000601c  lea     r8, aWil; "wil"
0x180006023  mov     r9d, eax; char *
0x180006026  mov     edx, 90h; void *
0x18000602b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006030  mov     eax, ebx
0x180006032  jmp     short loc_180006036
0x180006034  xor     eax, eax
0x180006036  mov     rcx, [rsp+278h+var_28]
0x18000603e  xor     rcx, rsp; StackCookie
0x180006041  call    __security_check_cookie
0x180006046  mov     rbx, [rsp+278h+arg_10]
0x18000604e  add     rsp, 260h
0x180006055  pop     rdi
0x180006056  pop     rsi
0x180006057  pop     rbp
0x180006058  retn
```
