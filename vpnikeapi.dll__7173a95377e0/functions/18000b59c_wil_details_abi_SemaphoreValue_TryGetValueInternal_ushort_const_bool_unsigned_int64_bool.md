# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000b59c`
- end: `0x18000b738`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000b528`

## callees

- `0x180007be8`
- `0x180009124`
- `0x18000ad88`
- `0x18000ada8`
- `0x18000b59c`
- `0x18000c65c`
- `0x18000c7a4`
- `0x18000cff0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b600`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b690`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b600`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b690`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b610`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b610`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        STRSAFE_PCNZWCH pszSrc,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  size_t v5; // rdx
  wil::details *v6; // rax
  void *v7; // rdx
  unsigned int v8; // r8d
  const char *v9; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  size_t v12; // rdx
  int v13; // r8d
  wil::details *v14; // rax
  unsigned int v15; // r8d
  const char *v16; // r9
  void *v17; // rdx
  int v18; // eax
  void *v19; // rdx
  int v20; // r8d
  size_t v22; // [rsp+20h] [rbp-E0h]
  int v23; // [rsp+30h] [rbp-D0h] BYREF
  int v24; // [rsp+34h] [rbp-CCh] BYREF
  wil::details *v25; // [rsp+38h] [rbp-C8h] BYREF
  wil::details *v26; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCopyWorkerW(pszDest, 0x104u, a3, pszSrc, v22);
  StringCchCatW(pszDest, v5, L"_p0");
  v6 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v26 = v6;
  if ( v6 )
  {
    v24 = 0;
    v23 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v24);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v13, (const char *)(unsigned int)ValueFromSemaphore);
      goto LABEL_13;
    }
    StringCchCatW(pszDest, v12, L"h");
    v14 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, pszDest);
    v25 = v14;
    if ( v14 )
    {
      v18 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v14, &v23);
      LastError = v18;
      if ( v18 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
          &v25,
          v19);
        *a3 = v24 | (unsigned __int64)((__int64)v23 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v20, (const char *)(unsigned int)v18);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v15, v16);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v25,
      v17);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v8, v9);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v26,
    v7);
  return LastError;
}

```

## disassembly

```asm
0x18000b59c  mov     [rsp-8+arg_8], rbx
0x18000b5a1  mov     [rsp-8+arg_18], rdi
0x18000b5a6  push    rbp
0x18000b5a7  lea     rbp, [rsp-170h]
0x18000b5af  sub     rsp, 270h
0x18000b5b6  mov     rax, cs:__security_cookie
0x18000b5bd  xor     rax, rsp
0x18000b5c0  mov     [rbp+170h+var_10], rax
0x18000b5c7  mov     r9, rcx; pszSrc
0x18000b5ca  mov     qword ptr [r8], 0
0x18000b5d1  lea     rcx, [rsp+270h+pszDest]; pszDest
0x18000b5d6  mov     edx, 104h; cchDest
0x18000b5db  mov     rdi, r8
0x18000b5de  call    StringCopyWorkerW
0x18000b5e3  lea     r8, aP0; "_p0"
0x18000b5ea  lea     rcx, [rsp+270h+pszDest]; pszDest
0x18000b5ef  call    StringCchCatW
0x18000b5f4  lea     r8, [rsp+270h+pszDest]; lpName
0x18000b5f9  xor     edx, edx; bInheritHandle
0x18000b5fb  mov     ecx, 1F0003h; dwDesiredAccess
0x18000b600  call    cs:__imp_OpenSemaphoreW
0x18000b606  mov     [rsp+270h+var_230], rax
0x18000b60b  test    rax, rax
0x18000b60e  jnz     short loc_18000B637
0x18000b610  call    cs:__imp_GetLastError
0x18000b616  cmp     eax, 2
0x18000b619  jz      loc_18000B706
0x18000b61f  mov     rcx, [rbp+178h]; this
0x18000b626  mov     edx, 0D0h; void *
0x18000b62b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b630  mov     ebx, eax
0x18000b632  jmp     loc_18000B708
0x18000b637  lea     rdx, [rsp+270h+var_23C]; int *
0x18000b63c  mov     [rsp+270h+var_23C], 0
0x18000b644  mov     rcx, rax; hHandle
0x18000b647  mov     [rsp+270h+var_240], 0
0x18000b64f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000b654  mov     ebx, eax
0x18000b656  test    eax, eax
0x18000b658  jns     short loc_18000B673
0x18000b65a  mov     rcx, [rbp+178h]; this
0x18000b661  mov     r9d, eax; char *
0x18000b664  mov     edx, 0D6h; void *
0x18000b669  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b66e  jmp     loc_18000B708
0x18000b673  lea     r8, asc_180012C78; "h"
0x18000b67a  lea     rcx, [rsp+270h+pszDest]; pszDest
0x18000b67f  call    StringCchCatW
0x18000b684  lea     r8, [rsp+270h+pszDest]; lpName
0x18000b689  xor     edx, edx; bInheritHandle
0x18000b68b  mov     ecx, 1F0003h; dwDesiredAccess
0x18000b690  call    cs:__imp_OpenSemaphoreW
0x18000b696  mov     [rsp+270h+var_238], rax
0x18000b69b  test    rax, rax
0x18000b69e  jnz     short loc_18000B6BF
0x18000b6a0  mov     rcx, [rbp+178h]; this
0x18000b6a7  mov     edx, 0DCh; void *
0x18000b6ac  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b6b1  mov     ebx, eax
0x18000b6b3  lea     rcx, [rsp+270h+var_238]
0x18000b6b8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000b6bd  jmp     short loc_18000B708
0x18000b6bf  lea     rdx, [rsp+270h+var_240]; int *
0x18000b6c4  mov     rcx, rax; hHandle
0x18000b6c7  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000b6cc  mov     ebx, eax
0x18000b6ce  test    eax, eax
0x18000b6d0  jns     short loc_18000B6E8
0x18000b6d2  mov     rcx, [rbp+178h]; this
0x18000b6d9  mov     r9d, eax; char *
0x18000b6dc  mov     edx, 0DEh; void *
0x18000b6e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b6e6  jmp     short loc_18000B6B3
0x18000b6e8  lea     rcx, [rsp+270h+var_238]
0x18000b6ed  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000b6f2  movsxd  rcx, [rsp+270h+var_240]
0x18000b6f7  movsxd  rax, [rsp+270h+var_23C]
0x18000b6fc  shl     rcx, 1Fh
0x18000b700  or      rcx, rax
0x18000b703  mov     [rdi], rcx
0x18000b706  xor     ebx, ebx
0x18000b708  lea     rcx, [rsp+270h+var_230]
0x18000b70d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000b712  mov     eax, ebx
0x18000b714  mov     rcx, [rbp+170h+var_10]
0x18000b71b  xor     rcx, rsp; StackCookie
0x18000b71e  call    __security_check_cookie
0x18000b723  lea     r11, [rsp+270h+var_s0]
0x18000b72b  mov     rbx, [r11+18h]
0x18000b72f  mov     rdi, [r11+28h]
0x18000b733  mov     rsp, r11
0x18000b736  pop     rbp
0x18000b737  retn
```
