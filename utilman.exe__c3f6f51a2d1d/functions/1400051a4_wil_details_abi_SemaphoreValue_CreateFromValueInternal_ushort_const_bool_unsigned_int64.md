# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1400051a4`
- end: `0x1400052c3`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `287`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140006a94`
- `0x140006bf8`

## callees

- `0x140002480`
- `0x1400051a4`
- `0x14000815c`
- `0x14000884c`
- `0x14000897c`
- `0x140009694`
- `0x14000986c`

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
0x1400051a4  mov     [rsp+arg_10], rbx
0x1400051a9  push    rbp
0x1400051aa  push    rsi
0x1400051ab  push    rdi
0x1400051ac  sub     rsp, 260h
0x1400051b3  mov     rax, cs:__security_cookie
0x1400051ba  xor     rax, rsp
0x1400051bd  mov     [rsp+278h+var_28], rax
0x1400051c5  mov     rax, 0C000000000000000h
0x1400051cf  mov     rbx, r9
0x1400051d2  mov     rbp, rcx
0x1400051d5  test    rax, r9
0x1400051d8  jz      short loc_1400051E0
0x1400051da  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1400051e0  mov     r9, rdx; pszSrc
0x1400051e3  lea     rcx, [rsp+278h+pszDest]; pszDest
0x1400051e8  mov     edx, 104h; cchDest
0x1400051ed  call    StringCopyWorkerW
0x1400051f2  lea     r8, aP0; "_p0"
0x1400051f9  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x1400051fe  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140005203  mov     edx, ebx
0x140005205  lea     r9, [rsp+278h+pszDest]
0x14000520a  and     edx, 7FFFFFFFh
0x140005210  mov     esi, 1
0x140005215  mov     r8d, esi
0x140005218  mov     rcx, rbp
0x14000521b  cmova   r8d, edx
0x14000521f  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x140005224  mov     edi, eax
0x140005226  test    eax, eax
0x140005228  jns     short loc_14000524A
0x14000522a  mov     rcx, [rsp+278h]; this
0x140005232  lea     r8, aWil; "wil"
0x140005239  mov     r9d, eax; char *
0x14000523c  mov     edx, 8Bh; void *
0x140005241  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005246  mov     eax, edi
0x140005248  jmp     short loc_14000529F
0x14000524a  lea     r8, asc_14002C850; "h"
0x140005251  shr     rbx, 1Fh
0x140005255  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x14000525a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000525f  test    ebx, ebx
0x140005261  lea     rcx, [rbp+8]
0x140005265  lea     r9, [rsp+278h+pszDest]
0x14000526a  mov     edx, ebx
0x14000526c  cmovnz  esi, ebx
0x14000526f  mov     r8d, esi
0x140005272  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x140005277  mov     ebx, eax
0x140005279  test    eax, eax
0x14000527b  jns     short loc_14000529D
0x14000527d  mov     rcx, [rsp+278h]; this
0x140005285  lea     r8, aWil; "wil"
0x14000528c  mov     r9d, eax; char *
0x14000528f  mov     edx, 90h; void *
0x140005294  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005299  mov     eax, ebx
0x14000529b  jmp     short loc_14000529F
0x14000529d  xor     eax, eax
0x14000529f  mov     rcx, [rsp+278h+var_28]
0x1400052a7  xor     rcx, rsp; StackCookie
0x1400052aa  call    __security_check_cookie
0x1400052af  mov     rbx, [rsp+278h+arg_10]
0x1400052b7  add     rsp, 260h
0x1400052be  pop     rdi
0x1400052bf  pop     rsi
0x1400052c0  pop     rbp
0x1400052c1  retn
```
