# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180024070`
- end: `0x180024180`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `272`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180025070`

## callees

- `0x180024070`
- `0x180025a84`
- `0x180026aa4`
- `0x180026b84`
- `0x180026fc4`
- `0x180027044`
- `0x18002a590`

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
0x180024070  mov     [rsp+arg_10], rbx
0x180024075  push    rbp
0x180024076  push    rsi
0x180024077  push    rdi
0x180024078  sub     rsp, 260h
0x18002407f  mov     rax, cs:__security_cookie
0x180024086  xor     rax, rsp
0x180024089  mov     [rsp+278h+var_28], rax
0x180024091  mov     rax, 0C000000000000000h
0x18002409b  mov     rbx, r9
0x18002409e  mov     rbp, rcx
0x1800240a1  test    rax, r9
0x1800240a4  jz      short loc_1800240AC
0x1800240a6  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800240ac  mov     r9, rdx; pszSrc
0x1800240af  lea     rcx, [rsp+278h+pszDest]; pszDest
0x1800240b4  mov     edx, 104h; cchDest
0x1800240b9  call    StringCopyWorkerW
0x1800240be  lea     r8, aP0; "_p0"
0x1800240c5  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x1800240ca  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800240cf  mov     edx, ebx
0x1800240d1  lea     r9, [rsp+278h+pszDest]
0x1800240d6  and     edx, 7FFFFFFFh
0x1800240dc  mov     esi, 1
0x1800240e1  mov     r8d, esi
0x1800240e4  mov     rcx, rbp
0x1800240e7  cmova   r8d, edx
0x1800240eb  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800240f0  mov     edi, eax
0x1800240f2  test    eax, eax
0x1800240f4  jns     short loc_18002410F
0x1800240f6  mov     rcx, [rsp+278h]; this
0x1800240fe  mov     r9d, eax; char *
0x180024101  mov     edx, 8Bh; void *
0x180024106  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002410b  mov     eax, edi
0x18002410d  jmp     short loc_18002415D
0x18002410f  lea     r8, asc_18002CCD8; "h"
0x180024116  shr     rbx, 1Fh
0x18002411a  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x18002411f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180024124  test    ebx, ebx
0x180024126  lea     rcx, [rbp+8]
0x18002412a  lea     r9, [rsp+278h+pszDest]
0x18002412f  mov     edx, ebx
0x180024131  cmovnz  esi, ebx
0x180024134  mov     r8d, esi
0x180024137  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18002413c  mov     ebx, eax
0x18002413e  test    eax, eax
0x180024140  jns     short loc_18002415B
0x180024142  mov     rcx, [rsp+278h]; this
0x18002414a  mov     r9d, eax; char *
0x18002414d  mov     edx, 90h; void *
0x180024152  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024157  mov     eax, ebx
0x180024159  jmp     short loc_18002415D
0x18002415b  xor     eax, eax
0x18002415d  mov     rcx, [rsp+278h+var_28]
0x180024165  xor     rcx, rsp; StackCookie
0x180024168  call    __security_check_cookie
0x18002416d  mov     rbx, [rsp+278h+arg_10]
0x180024175  add     rsp, 260h
0x18002417c  pop     rdi
0x18002417d  pop     rsi
0x18002417e  pop     rbp
0x18002417f  retn
```
