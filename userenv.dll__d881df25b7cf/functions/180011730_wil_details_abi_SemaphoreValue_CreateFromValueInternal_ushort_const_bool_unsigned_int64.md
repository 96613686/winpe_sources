# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180011730`
- end: `0x180011852`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `290`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011efc`
- `0x180017180`

## callees

- `0x18000778c`
- `0x18000db08`
- `0x18000db88`
- `0x18000e640`
- `0x180011730`
- `0x180012780`
- `0x180012804`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        const unsigned __int16 *a2,
        __int64 a3,
        unsigned __int64 a4)
{
  LONG v6; // esi
  LONG v7; // r8d
  int semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  unsigned int v9; // edi
  unsigned __int64 v11; // rbx
  int v12; // eax
  unsigned int v13; // ebx
  int v14; // [rsp+20h] [rbp-268h]
  unsigned __int16 v15[264]; // [rsp+40h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  StringCchCopyW(v15, 0x104u, a2);
  StringCchCatW(v15, 0x104u, L"_p0");
  v6 = 1;
  v7 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v7 = a4 & 0x7FFFFFFF;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this, a4 & 0x7FFFFFFF, v7, v15);
  v9 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    v11 = a4 >> 31;
    StringCchCatW(v15, 0x104u, L"h");
    if ( (_DWORD)v11 )
      v6 = v11;
    v12 = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
            (__int64)this + 8,
            v11,
            v6,
            v15);
    v13 = v12;
    if ( v12 >= 0 )
    {
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x90,
        (unsigned int)"wil",
        (const char *)(unsigned int)v12,
        v14);
      return v13;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8B,
      (unsigned int)"wil",
      (const char *)(unsigned int)semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      v14);
    return v9;
  }
}

```

## disassembly

```asm
0x180011730  push    rbx
0x180011732  push    rbp
0x180011733  push    rsi
0x180011734  push    rdi
0x180011735  push    r14
0x180011737  sub     rsp, 260h
0x18001173e  mov     rax, cs:__security_cookie
0x180011745  xor     rax, rsp
0x180011748  mov     [rsp+288h+var_38], rax
0x180011750  mov     rax, 0C000000000000000h
0x18001175a  mov     rbx, r9
0x18001175d  mov     rbp, rcx
0x180011760  test    rax, r9
0x180011763  jz      short loc_18001176B
0x180011765  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18001176b  mov     r8, rdx; unsigned __int16 *
0x18001176e  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x180011773  mov     r14d, 104h
0x180011779  mov     edx, r14d; unsigned __int64
0x18001177c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180011781  lea     r8, aP0; "_p0"
0x180011788  mov     edx, r14d; unsigned __int64
0x18001178b  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x180011790  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180011795  mov     edx, ebx
0x180011797  lea     r9, [rsp+288h+var_248]
0x18001179c  and     edx, 7FFFFFFFh
0x1800117a2  mov     esi, 1
0x1800117a7  mov     r8d, esi
0x1800117aa  mov     rcx, rbp
0x1800117ad  cmova   r8d, edx
0x1800117b1  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800117b6  mov     edi, eax
0x1800117b8  test    eax, eax
0x1800117ba  jns     short loc_1800117DB
0x1800117bc  mov     rcx, [rsp+288h]; this
0x1800117c4  lea     r8, aWil; "wil"
0x1800117cb  mov     r9d, eax; char *
0x1800117ce  lea     edx, [r14-79h]; void *
0x1800117d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800117d7  mov     eax, edi
0x1800117d9  jmp     short loc_180011833
0x1800117db  lea     r8, asc_1800202F8; "h"
0x1800117e2  shr     rbx, 1Fh
0x1800117e6  mov     rdx, r14; unsigned __int64
0x1800117e9  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x1800117ee  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800117f3  test    ebx, ebx
0x1800117f5  lea     rcx, [rbp+8]
0x1800117f9  lea     r9, [rsp+288h+var_248]
0x1800117fe  mov     edx, ebx
0x180011800  cmovnz  esi, ebx
0x180011803  mov     r8d, esi
0x180011806  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18001180b  mov     ebx, eax
0x18001180d  test    eax, eax
0x18001180f  jns     short loc_180011831
0x180011811  mov     rcx, [rsp+288h]; this
0x180011819  lea     r8, aWil; "wil"
0x180011820  mov     r9d, eax; char *
0x180011823  mov     edx, 90h; void *
0x180011828  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001182d  mov     eax, ebx
0x18001182f  jmp     short loc_180011833
0x180011831  xor     eax, eax
0x180011833  mov     rcx, [rsp+288h+var_38]
0x18001183b  xor     rcx, rsp; StackCookie
0x18001183e  call    __security_check_cookie
0x180011843  add     rsp, 260h
0x18001184a  pop     r14
0x18001184c  pop     rdi
0x18001184d  pop     rsi
0x18001184e  pop     rbp
0x18001184f  pop     rbx
0x180011850  retn
```
