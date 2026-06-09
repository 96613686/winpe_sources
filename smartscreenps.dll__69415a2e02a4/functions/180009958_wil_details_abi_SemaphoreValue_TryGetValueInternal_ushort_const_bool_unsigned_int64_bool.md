# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180009958`
- end: `0x180009b15`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `445`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000781c`

## callees

- `0x180001590`
- `0x1800076c4`
- `0x1800084c0`
- `0x1800091e4`
- `0x180009204`
- `0x180009700`
- `0x1800097f8`
- `0x180009958`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800099bc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009a5f`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800099bc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009a5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800099d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800099d2`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        STRSAFE_PCNZWCH pszSrc,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  unsigned __int64 v5; // rdx
  HANDLE v6; // rax
  unsigned int v7; // r8d
  const char *v8; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned __int64 v11; // rdx
  HANDLE v12; // rax
  unsigned int v13; // r8d
  const char *v14; // r9
  int v15; // eax
  size_t v17; // [rsp+20h] [rbp-E0h]
  int v18; // [rsp+20h] [rbp-E0h]
  int v19; // [rsp+30h] [rbp-D0h] BYREF
  int v20; // [rsp+34h] [rbp-CCh] BYREF
  HANDLE v21; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE v22[2]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCopyWorkerW(pszDest, 0x104u, a3, pszSrc, v17);
  StringCchCatW(pszDest, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v22[0] = v6;
  if ( v6 )
  {
    v20 = 0;
    v19 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v20);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v18);
      goto LABEL_13;
    }
    StringCchCatW(pszDest, v11, L"h");
    v12 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
    v21 = v12;
    if ( v12 )
    {
      v15 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v12, &v19);
      LastError = v15;
      if ( v15 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
        *a3 = v20 | (unsigned __int64)((__int64)v19 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v15,
        v18);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v13, v14);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v7, v8);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v22);
  return LastError;
}

```

## disassembly

```asm
0x180009958  mov     [rsp-8+arg_8], rbx
0x18000995d  mov     [rsp-8+arg_18], rdi
0x180009962  push    rbp
0x180009963  lea     rbp, [rsp-170h]
0x18000996b  sub     rsp, 270h
0x180009972  mov     rax, cs:__security_cookie
0x180009979  xor     rax, rsp
0x18000997c  mov     [rbp+170h+var_10], rax
0x180009983  mov     r9, rcx; pszSrc
0x180009986  mov     qword ptr [r8], 0
0x18000998d  lea     rcx, [rsp+270h+pszDest]; pszDest
0x180009992  mov     edx, 104h; cchDest
0x180009997  mov     rdi, r8
0x18000999a  call    StringCopyWorkerW
0x18000999f  lea     r8, aP0; "_p0"
0x1800099a6  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x1800099ab  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800099b0  lea     r8, [rsp+270h+pszDest]; lpName
0x1800099b5  xor     edx, edx; bInheritHandle
0x1800099b7  mov     ecx, 1F0003h; dwDesiredAccess
0x1800099bc  call    cs:__imp_OpenSemaphoreW
0x1800099c3  nop     dword ptr [rax+rax+00h]
0x1800099c8  mov     [rsp+270h+var_230], rax
0x1800099cd  test    rax, rax
0x1800099d0  jnz     short loc_1800099FF
0x1800099d2  call    cs:__imp_GetLastError
0x1800099d9  nop     dword ptr [rax+rax+00h]
0x1800099de  cmp     eax, 2
0x1800099e1  jz      loc_180009AE2
0x1800099e7  mov     rcx, [rbp+178h]; this
0x1800099ee  mov     edx, 0D0h; void *
0x1800099f3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800099f8  mov     ebx, eax
0x1800099fa  jmp     loc_180009AE4
0x1800099ff  lea     rdx, [rsp+270h+var_23C]; int *
0x180009a04  mov     [rsp+270h+var_23C], 0
0x180009a0c  mov     rcx, rax; hHandle
0x180009a0f  mov     [rsp+270h+var_240], 0
0x180009a17  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180009a1c  mov     ebx, eax
0x180009a1e  test    eax, eax
0x180009a20  jns     short loc_180009A42
0x180009a22  mov     rcx, [rbp+178h]; this
0x180009a29  lea     r8, aWil; "wil"
0x180009a30  mov     r9d, eax; char *
0x180009a33  mov     edx, 0D6h; void *
0x180009a38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009a3d  jmp     loc_180009AE4
0x180009a42  lea     r8, asc_180014A48; "h"
0x180009a49  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x180009a4e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009a53  lea     r8, [rsp+270h+pszDest]; lpName
0x180009a58  xor     edx, edx; bInheritHandle
0x180009a5a  mov     ecx, 1F0003h; dwDesiredAccess
0x180009a5f  call    cs:__imp_OpenSemaphoreW
0x180009a66  nop     dword ptr [rax+rax+00h]
0x180009a6b  mov     [rsp+270h+var_238], rax
0x180009a70  test    rax, rax
0x180009a73  jnz     short loc_180009A94
0x180009a75  mov     rcx, [rbp+178h]; this
0x180009a7c  mov     edx, 0DCh; void *
0x180009a81  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009a86  mov     ebx, eax
0x180009a88  lea     rcx, [rsp+270h+var_238]
0x180009a8d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180009a92  jmp     short loc_180009AE4
0x180009a94  lea     rdx, [rsp+270h+var_240]; int *
0x180009a99  mov     rcx, rax; hHandle
0x180009a9c  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180009aa1  mov     ebx, eax
0x180009aa3  test    eax, eax
0x180009aa5  jns     short loc_180009AC4
0x180009aa7  mov     rcx, [rbp+178h]; this
0x180009aae  lea     r8, aWil; "wil"
0x180009ab5  mov     r9d, eax; char *
0x180009ab8  mov     edx, 0DEh; void *
0x180009abd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009ac2  jmp     short loc_180009A88
0x180009ac4  lea     rcx, [rsp+270h+var_238]
0x180009ac9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180009ace  movsxd  rcx, [rsp+270h+var_240]
0x180009ad3  movsxd  rax, [rsp+270h+var_23C]
0x180009ad8  shl     rcx, 1Fh
0x180009adc  or      rcx, rax
0x180009adf  mov     [rdi], rcx
0x180009ae2  xor     ebx, ebx
0x180009ae4  lea     rcx, [rsp+270h+var_230]
0x180009ae9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180009aee  mov     eax, ebx
0x180009af0  mov     rcx, [rbp+170h+var_10]
0x180009af7  xor     rcx, rsp; StackCookie
0x180009afa  call    __security_check_cookie
0x180009aff  lea     r11, [rsp+270h+var_s0]
0x180009b07  mov     rbx, [r11+18h]
0x180009b0b  mov     rdi, [r11+28h]
0x180009b0f  mov     rsp, r11
0x180009b12  pop     rbp
0x180009b13  retn
```
