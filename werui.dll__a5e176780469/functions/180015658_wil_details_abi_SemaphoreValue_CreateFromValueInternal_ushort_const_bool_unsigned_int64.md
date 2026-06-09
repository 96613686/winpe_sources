# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180015658`
- end: `0x180015768`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `272`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015fd8`

## callees

- `0x180007cdc`
- `0x180015658`
- `0x180016340`
- `0x180016578`
- `0x1800168cc`
- `0x18001694c`
- `0x180016c50`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        unsigned __int16 *a2,
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
0x180015658  mov     [rsp+arg_10], rbx
0x18001565d  push    rbp
0x18001565e  push    rsi
0x18001565f  push    rdi
0x180015660  sub     rsp, 260h
0x180015667  mov     rax, cs:__security_cookie
0x18001566e  xor     rax, rsp
0x180015671  mov     [rsp+278h+var_28], rax
0x180015679  mov     rax, 0C000000000000000h
0x180015683  mov     rbx, r9
0x180015686  mov     rbp, rcx
0x180015689  test    rax, r9
0x18001568c  jz      short loc_180015694
0x18001568e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180015694  mov     r8, rdx; unsigned __int16 *
0x180015697  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x18001569c  mov     edx, 104h; unsigned __int64
0x1800156a1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800156a6  lea     r8, aP0; "_p0"
0x1800156ad  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x1800156b2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800156b7  mov     edx, ebx
0x1800156b9  lea     r9, [rsp+278h+var_238]
0x1800156be  and     edx, 7FFFFFFFh
0x1800156c4  mov     esi, 1
0x1800156c9  mov     r8d, esi
0x1800156cc  mov     rcx, rbp
0x1800156cf  cmova   r8d, edx
0x1800156d3  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800156d8  mov     edi, eax
0x1800156da  test    eax, eax
0x1800156dc  jns     short loc_1800156F7
0x1800156de  mov     rcx, [rsp+278h]; this
0x1800156e6  mov     r9d, eax; char *
0x1800156e9  mov     edx, 8Bh; void *
0x1800156ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800156f3  mov     eax, edi
0x1800156f5  jmp     short loc_180015745
0x1800156f7  lea     r8, asc_18001BA80; "h"
0x1800156fe  shr     rbx, 1Fh
0x180015702  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x180015707  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001570c  test    ebx, ebx
0x18001570e  lea     rcx, [rbp+8]
0x180015712  lea     r9, [rsp+278h+var_238]
0x180015717  mov     edx, ebx
0x180015719  cmovnz  esi, ebx
0x18001571c  mov     r8d, esi
0x18001571f  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180015724  mov     ebx, eax
0x180015726  test    eax, eax
0x180015728  jns     short loc_180015743
0x18001572a  mov     rcx, [rsp+278h]; this
0x180015732  mov     r9d, eax; char *
0x180015735  mov     edx, 90h; void *
0x18001573a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001573f  mov     eax, ebx
0x180015741  jmp     short loc_180015745
0x180015743  xor     eax, eax
0x180015745  mov     rcx, [rsp+278h+var_28]
0x18001574d  xor     rcx, rsp; StackCookie
0x180015750  call    __security_check_cookie
0x180015755  mov     rbx, [rsp+278h+arg_10]
0x18001575d  add     rsp, 260h
0x180015764  pop     rdi
0x180015765  pop     rsi
0x180015766  pop     rbp
0x180015767  retn
```
