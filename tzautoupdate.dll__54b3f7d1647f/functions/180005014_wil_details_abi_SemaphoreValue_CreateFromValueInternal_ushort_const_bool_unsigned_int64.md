# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180005014`
- end: `0x180005132`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `286`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const unsigned __int16 *, size_t *, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006eec`
- `0x18000704c`

## callees

- `0x180005014`
- `0x18000885c`
- `0x180008f74`
- `0x18000909c`
- `0x18000ad50`
- `0x18000b264`
- `0x18001b150`

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
0x180005014  mov     [rsp+arg_10], rbx
0x180005019  push    rbp
0x18000501a  push    rsi
0x18000501b  push    rdi
0x18000501c  sub     rsp, 260h
0x180005023  mov     rax, cs:__security_cookie
0x18000502a  xor     rax, rsp
0x18000502d  mov     [rsp+278h+var_28], rax
0x180005035  mov     rax, 0C000000000000000h
0x18000503f  mov     rbx, r9
0x180005042  mov     rbp, rcx
0x180005045  test    rax, r9
0x180005048  jz      short loc_180005050
0x18000504a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180005050  mov     r9, rdx; pszSrc
0x180005053  lea     rcx, [rsp+278h+pszDest]; pszDest
0x180005058  mov     edx, 104h; cchDest
0x18000505d  call    StringCopyWorkerW
0x180005062  lea     r8, aP0; "_p0"
0x180005069  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x18000506e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005073  mov     edx, ebx
0x180005075  lea     r9, [rsp+278h+pszDest]
0x18000507a  and     edx, 7FFFFFFFh
0x180005080  mov     esi, 1
0x180005085  mov     r8d, esi
0x180005088  mov     rcx, rbp
0x18000508b  cmova   r8d, edx
0x18000508f  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180005094  mov     edi, eax
0x180005096  test    eax, eax
0x180005098  jns     short loc_1800050BA
0x18000509a  mov     rcx, [rsp+278h]; this
0x1800050a2  lea     r8, aWil; "wil"
0x1800050a9  mov     r9d, eax; char *
0x1800050ac  mov     edx, 8Bh; void *
0x1800050b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800050b6  mov     eax, edi
0x1800050b8  jmp     short loc_18000510F
0x1800050ba  lea     r8, asc_180022048; "h"
0x1800050c1  shr     rbx, 1Fh
0x1800050c5  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x1800050ca  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800050cf  test    ebx, ebx
0x1800050d1  lea     rcx, [rbp+8]
0x1800050d5  lea     r9, [rsp+278h+pszDest]
0x1800050da  mov     edx, ebx
0x1800050dc  cmovnz  esi, ebx
0x1800050df  mov     r8d, esi
0x1800050e2  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800050e7  mov     ebx, eax
0x1800050e9  test    eax, eax
0x1800050eb  jns     short loc_18000510D
0x1800050ed  mov     rcx, [rsp+278h]; this
0x1800050f5  lea     r8, aWil; "wil"
0x1800050fc  mov     r9d, eax; char *
0x1800050ff  mov     edx, 90h; void *
0x180005104  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005109  mov     eax, ebx
0x18000510b  jmp     short loc_18000510F
0x18000510d  xor     eax, eax
0x18000510f  mov     rcx, [rsp+278h+var_28]
0x180005117  xor     rcx, rsp; StackCookie
0x18000511a  call    __security_check_cookie
0x18000511f  mov     rbx, [rsp+278h+arg_10]
0x180005127  add     rsp, 260h
0x18000512e  pop     rdi
0x18000512f  pop     rsi
0x180005130  pop     rbp
0x180005131  retn
```
