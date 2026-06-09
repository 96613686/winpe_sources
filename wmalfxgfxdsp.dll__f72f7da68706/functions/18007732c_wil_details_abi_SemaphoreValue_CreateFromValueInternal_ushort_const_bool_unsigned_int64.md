# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18007732c`
- end: `0x18007744a`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `286`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180078694`

## callees

- `0x180014d58`
- `0x180015190`
- `0x18007732c`
- `0x180079344`
- `0x180079424`
- `0x1800798f0`
- `0x1800799ac`

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
0x18007732c  mov     [rsp+arg_10], rbx
0x180077331  push    rbp
0x180077332  push    rsi
0x180077333  push    rdi
0x180077334  sub     rsp, 260h
0x18007733b  mov     rax, cs:__security_cookie
0x180077342  xor     rax, rsp
0x180077345  mov     [rsp+278h+var_28], rax
0x18007734d  mov     rax, 0C000000000000000h
0x180077357  mov     rbx, r9
0x18007735a  mov     rbp, rcx
0x18007735d  test    rax, r9
0x180077360  jz      short loc_180077368
0x180077362  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180077368  mov     r9, rdx; pszSrc
0x18007736b  lea     rcx, [rsp+278h+pszDest]; pszDest
0x180077370  mov     edx, 104h; cchDest
0x180077375  call    StringCopyWorkerW
0x18007737a  lea     r8, aP0; "_p0"
0x180077381  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x180077386  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18007738b  mov     edx, ebx
0x18007738d  lea     r9, [rsp+278h+pszDest]
0x180077392  and     edx, 7FFFFFFFh
0x180077398  mov     esi, 1
0x18007739d  mov     r8d, esi
0x1800773a0  mov     rcx, rbp
0x1800773a3  cmova   r8d, edx
0x1800773a7  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800773ac  mov     edi, eax
0x1800773ae  test    eax, eax
0x1800773b0  jns     short loc_1800773D2
0x1800773b2  mov     rcx, [rsp+278h]; this
0x1800773ba  lea     r8, aWil; "wil"
0x1800773c1  mov     r9d, eax; char *
0x1800773c4  mov     edx, 8Bh; void *
0x1800773c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800773ce  mov     eax, edi
0x1800773d0  jmp     short loc_180077427
0x1800773d2  lea     r8, asc_1801AFEC0; "h"
0x1800773d9  shr     rbx, 1Fh
0x1800773dd  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x1800773e2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800773e7  test    ebx, ebx
0x1800773e9  lea     rcx, [rbp+8]
0x1800773ed  lea     r9, [rsp+278h+pszDest]
0x1800773f2  mov     edx, ebx
0x1800773f4  cmovnz  esi, ebx
0x1800773f7  mov     r8d, esi
0x1800773fa  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800773ff  mov     ebx, eax
0x180077401  test    eax, eax
0x180077403  jns     short loc_180077425
0x180077405  mov     rcx, [rsp+278h]; this
0x18007740d  lea     r8, aWil; "wil"
0x180077414  mov     r9d, eax; char *
0x180077417  mov     edx, 90h; void *
0x18007741c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180077421  mov     eax, ebx
0x180077423  jmp     short loc_180077427
0x180077425  xor     eax, eax
0x180077427  mov     rcx, [rsp+278h+var_28]
0x18007742f  xor     rcx, rsp; StackCookie
0x180077432  call    __security_check_cookie
0x180077437  mov     rbx, [rsp+278h+arg_10]
0x18007743f  add     rsp, 260h
0x180077446  pop     rdi
0x180077447  pop     rsi
0x180077448  pop     rbp
0x180077449  retn
```
