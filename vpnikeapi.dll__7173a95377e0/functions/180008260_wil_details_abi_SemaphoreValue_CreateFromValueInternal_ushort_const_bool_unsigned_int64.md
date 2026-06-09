# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180008260`
- end: `0x180008374`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `276`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const unsigned __int16 *, size_t *, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009a80`
- `0x180009ba8`

## callees

- `0x180008260`
- `0x18000ada8`
- `0x18000bc9c`
- `0x18000be04`
- `0x18000c65c`
- `0x18000c7a4`
- `0x18000cff0`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        const unsigned __int16 *a2,
        size_t *a3,
        unsigned __int64 a4)
{
  size_t v6; // rdx
  LONG v7; // esi
  LONG v8; // r8d
  int semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  size_t v10; // rdx
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
0x180008260  mov     [rsp+arg_10], rbx
0x180008265  push    rbp
0x180008266  push    rsi
0x180008267  push    rdi
0x180008268  sub     rsp, 260h
0x18000826f  mov     rax, cs:__security_cookie
0x180008276  xor     rax, rsp
0x180008279  mov     [rsp+278h+var_28], rax
0x180008281  mov     rax, 0C000000000000000h
0x18000828b  mov     rbx, r9
0x18000828e  mov     rbp, rcx
0x180008291  test    rax, r9
0x180008294  jnz     loc_18000836E
0x18000829a  mov     r9, rdx; pszSrc
0x18000829d  lea     rcx, [rsp+278h+pszDest]; pszDest
0x1800082a2  mov     edx, 104h; cchDest
0x1800082a7  call    StringCopyWorkerW
0x1800082ac  lea     r8, aP0; "_p0"
0x1800082b3  lea     rcx, [rsp+278h+pszDest]; pszDest
0x1800082b8  call    StringCchCatW
0x1800082bd  mov     edx, ebx
0x1800082bf  lea     r9, [rsp+278h+pszDest]
0x1800082c4  and     edx, 7FFFFFFFh
0x1800082ca  mov     esi, 1
0x1800082cf  mov     r8d, esi
0x1800082d2  mov     rcx, rbp
0x1800082d5  cmova   r8d, edx
0x1800082d9  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800082de  mov     edi, eax
0x1800082e0  test    eax, eax
0x1800082e2  jns     short loc_1800082FD
0x1800082e4  mov     rcx, [rsp+278h]; this
0x1800082ec  mov     r9d, eax; char *
0x1800082ef  mov     edx, 8Bh; void *
0x1800082f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800082f9  mov     eax, edi
0x1800082fb  jmp     short loc_18000834B
0x1800082fd  lea     r8, asc_180012C78; "h"
0x180008304  shr     rbx, 1Fh
0x180008308  lea     rcx, [rsp+278h+pszDest]; pszDest
0x18000830d  call    StringCchCatW
0x180008312  test    ebx, ebx
0x180008314  lea     rcx, [rbp+8]
0x180008318  lea     r9, [rsp+278h+pszDest]
0x18000831d  mov     edx, ebx
0x18000831f  cmovnz  esi, ebx
0x180008322  mov     r8d, esi
0x180008325  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000832a  mov     ebx, eax
0x18000832c  test    eax, eax
0x18000832e  jns     short loc_180008349
0x180008330  mov     rcx, [rsp+278h]; this
0x180008338  mov     r9d, eax; char *
0x18000833b  mov     edx, 90h; void *
0x180008340  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008345  mov     eax, ebx
0x180008347  jmp     short loc_18000834B
0x180008349  xor     eax, eax
0x18000834b  mov     rcx, [rsp+278h+var_28]
0x180008353  xor     rcx, rsp; StackCookie
0x180008356  call    __security_check_cookie
0x18000835b  mov     rbx, [rsp+278h+arg_10]
0x180008363  add     rsp, 260h
0x18000836a  pop     rdi
0x18000836b  pop     rsi
0x18000836c  pop     rbp
0x18000836d  retn
0x18000836e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
