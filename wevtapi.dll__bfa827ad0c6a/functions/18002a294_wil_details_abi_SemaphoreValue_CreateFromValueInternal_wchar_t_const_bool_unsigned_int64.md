# wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)

- ea: `0x18002a294`
- end: `0x18002a3a4`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z`
- size: `272`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const wchar_t *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002b640`
- `0x18002b764`

## callees

- `0x180024a50`
- `0x18002a294`
- `0x18002c40c`
- `0x18002c8ac`
- `0x18002c98c`
- `0x18002d488`
- `0x18002d558`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        const wchar_t *a2,
        size_t *a3,
        unsigned __int64 a4)
{
  unsigned __int64 v6; // rdx
  LONG v7; // esi
  LONG v8; // r8d
  int semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
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
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this, a4 & 0x7FFFFFFF, v8, pszDest);
  v12 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    v14 = a4 >> 31;
    StringCchCatW(pszDest, v10, L"h");
    if ( (_DWORD)v14 )
      v7 = v14;
    v15 = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
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
      (const char *)(unsigned int)semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      v19);
    return v12;
  }
}

```

## disassembly

```asm
0x18002a294  mov     [rsp+arg_10], rbx
0x18002a299  push    rbp
0x18002a29a  push    rsi
0x18002a29b  push    rdi
0x18002a29c  sub     rsp, 260h
0x18002a2a3  mov     rax, cs:__security_cookie
0x18002a2aa  xor     rax, rsp
0x18002a2ad  mov     [rsp+278h+var_28], rax
0x18002a2b5  mov     rax, 0C000000000000000h
0x18002a2bf  mov     rbx, r9
0x18002a2c2  mov     rbp, rcx
0x18002a2c5  test    rax, r9
0x18002a2c8  jz      short loc_18002A2D0
0x18002a2ca  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18002a2d0  mov     r9, rdx; pszSrc
0x18002a2d3  lea     rcx, [rsp+278h+pszDest]; pszDest
0x18002a2d8  mov     edx, 104h; cchDest
0x18002a2dd  call    StringCopyWorkerW
0x18002a2e2  lea     r8, aP0; "_p0"
0x18002a2e9  lea     rcx, [rsp+278h+pszDest]; wchar_t *
0x18002a2ee  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18002a2f3  mov     edx, ebx
0x18002a2f5  lea     r9, [rsp+278h+pszDest]
0x18002a2fa  and     edx, 7FFFFFFFh
0x18002a300  mov     esi, 1
0x18002a305  mov     r8d, esi
0x18002a308  mov     rcx, rbp
0x18002a30b  cmova   r8d, edx
0x18002a30f  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18002a314  mov     edi, eax
0x18002a316  test    eax, eax
0x18002a318  jns     short loc_18002A333
0x18002a31a  mov     rcx, [rsp+278h]; this
0x18002a322  mov     r9d, eax; char *
0x18002a325  mov     edx, 8Bh; void *
0x18002a32a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a32f  mov     eax, edi
0x18002a331  jmp     short loc_18002A381
0x18002a333  lea     r8, asc_1800418F0; "h"
0x18002a33a  shr     rbx, 1Fh
0x18002a33e  lea     rcx, [rsp+278h+pszDest]; wchar_t *
0x18002a343  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18002a348  test    ebx, ebx
0x18002a34a  lea     rcx, [rbp+8]
0x18002a34e  lea     r9, [rsp+278h+pszDest]
0x18002a353  mov     edx, ebx
0x18002a355  cmovnz  esi, ebx
0x18002a358  mov     r8d, esi
0x18002a35b  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18002a360  mov     ebx, eax
0x18002a362  test    eax, eax
0x18002a364  jns     short loc_18002A37F
0x18002a366  mov     rcx, [rsp+278h]; this
0x18002a36e  mov     r9d, eax; char *
0x18002a371  mov     edx, 90h; void *
0x18002a376  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a37b  mov     eax, ebx
0x18002a37d  jmp     short loc_18002A381
0x18002a37f  xor     eax, eax
0x18002a381  mov     rcx, [rsp+278h+var_28]
0x18002a389  xor     rcx, rsp; StackCookie
0x18002a38c  call    __security_check_cookie
0x18002a391  mov     rbx, [rsp+278h+arg_10]
0x18002a399  add     rsp, 260h
0x18002a3a0  pop     rdi
0x18002a3a1  pop     rsi
0x18002a3a2  pop     rbp
0x18002a3a3  retn
```
