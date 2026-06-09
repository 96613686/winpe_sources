# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180006558`
- end: `0x180006710`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180001980`

## callees

- `0x180001b44`
- `0x180001b68`
- `0x180001f64`
- `0x1800024e0`
- `0x180004ea8`
- `0x180006314`
- `0x180006450`
- `0x180006558`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800065bc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000665a`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800065bc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000665a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800065cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800065cc`

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
  const char *v7; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned __int64 v10; // rdx
  HANDLE v11; // rax
  const char *v12; // r9
  int v13; // eax
  size_t v15; // [rsp+20h] [rbp-E0h]
  int v16; // [rsp+20h] [rbp-E0h]
  int v17; // [rsp+30h] [rbp-D0h] BYREF
  int v18; // [rsp+34h] [rbp-CCh] BYREF
  HANDLE v19; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE v20[2]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCopyWorkerW(pszDest, 0x104u, a3, pszSrc, v15);
  StringCchCatW(pszDest, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v20[0] = v6;
  if ( v6 )
  {
    v18 = 0;
    v17 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v18);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v16);
      goto LABEL_13;
    }
    StringCchCatW(pszDest, v10, L"h");
    v11 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
    v19 = v11;
    if ( v11 )
    {
      v13 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v11, &v17);
      LastError = v13;
      if ( v13 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
        *a3 = v18 | (unsigned __int64)((__int64)v17 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v13,
        v16);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v12);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v7);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v20);
  return LastError;
}

```

## disassembly

```asm
0x180006558  mov     [rsp-8+arg_8], rbx
0x18000655d  mov     [rsp-8+arg_18], rdi
0x180006562  push    rbp
0x180006563  lea     rbp, [rsp-170h]
0x18000656b  sub     rsp, 270h
0x180006572  mov     rax, cs:__security_cookie
0x180006579  xor     rax, rsp
0x18000657c  mov     [rbp+170h+var_10], rax
0x180006583  mov     r9, rcx; pszSrc
0x180006586  mov     qword ptr [r8], 0
0x18000658d  lea     rcx, [rsp+270h+pszDest]; pszDest
0x180006592  mov     edx, 104h; cchDest
0x180006597  mov     rdi, r8
0x18000659a  call    StringCopyWorkerW
0x18000659f  lea     r8, aP0; "_p0"
0x1800065a6  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x1800065ab  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800065b0  lea     r8, [rsp+270h+pszDest]; lpName
0x1800065b5  xor     edx, edx; bInheritHandle
0x1800065b7  mov     ecx, 1F0003h; dwDesiredAccess
0x1800065bc  call    cs:__imp_OpenSemaphoreW
0x1800065c2  mov     [rsp+270h+var_230], rax
0x1800065c7  test    rax, rax
0x1800065ca  jnz     short loc_1800065FA
0x1800065cc  call    cs:__imp_GetLastError
0x1800065d2  cmp     eax, 2
0x1800065d5  jz      loc_1800066DE
0x1800065db  mov     rcx, [rbp+178h]; this
0x1800065e2  lea     r8, aWil; "wil"
0x1800065e9  mov     edx, 0D0h; void *
0x1800065ee  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800065f3  mov     ebx, eax
0x1800065f5  jmp     loc_1800066E0
0x1800065fa  lea     rdx, [rsp+270h+var_23C]; int *
0x1800065ff  mov     [rsp+270h+var_23C], 0
0x180006607  mov     rcx, rax; hHandle
0x18000660a  mov     [rsp+270h+var_240], 0
0x180006612  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180006617  mov     ebx, eax
0x180006619  test    eax, eax
0x18000661b  jns     short loc_18000663D
0x18000661d  mov     rcx, [rbp+178h]; this
0x180006624  lea     r8, aWil; "wil"
0x18000662b  mov     r9d, eax; char *
0x18000662e  mov     edx, 0D6h; void *
0x180006633  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006638  jmp     loc_1800066E0
0x18000663d  lea     r8, asc_180009A98; "h"
0x180006644  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x180006649  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000664e  lea     r8, [rsp+270h+pszDest]; lpName
0x180006653  xor     edx, edx; bInheritHandle
0x180006655  mov     ecx, 1F0003h; dwDesiredAccess
0x18000665a  call    cs:__imp_OpenSemaphoreW
0x180006660  mov     [rsp+270h+var_238], rax
0x180006665  test    rax, rax
0x180006668  jnz     short loc_180006690
0x18000666a  mov     rcx, [rbp+178h]; this
0x180006671  lea     r8, aWil; "wil"
0x180006678  mov     edx, 0DCh; void *
0x18000667d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180006682  mov     ebx, eax
0x180006684  lea     rcx, [rsp+270h+var_238]
0x180006689  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000668e  jmp     short loc_1800066E0
0x180006690  lea     rdx, [rsp+270h+var_240]; int *
0x180006695  mov     rcx, rax; hHandle
0x180006698  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000669d  mov     ebx, eax
0x18000669f  test    eax, eax
0x1800066a1  jns     short loc_1800066C0
0x1800066a3  mov     rcx, [rbp+178h]; this
0x1800066aa  lea     r8, aWil; "wil"
0x1800066b1  mov     r9d, eax; char *
0x1800066b4  mov     edx, 0DEh; void *
0x1800066b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800066be  jmp     short loc_180006684
0x1800066c0  lea     rcx, [rsp+270h+var_238]
0x1800066c5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800066ca  movsxd  rcx, [rsp+270h+var_240]
0x1800066cf  movsxd  rax, [rsp+270h+var_23C]
0x1800066d4  shl     rcx, 1Fh
0x1800066d8  or      rcx, rax
0x1800066db  mov     [rdi], rcx
0x1800066de  xor     ebx, ebx
0x1800066e0  lea     rcx, [rsp+270h+var_230]
0x1800066e5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800066ea  mov     eax, ebx
0x1800066ec  mov     rcx, [rbp+170h+var_10]
0x1800066f3  xor     rcx, rsp; StackCookie
0x1800066f6  call    __security_check_cookie
0x1800066fb  lea     r11, [rsp+270h+var_s0]
0x180006703  mov     rbx, [r11+18h]
0x180006707  mov     rdi, [r11+28h]
0x18000670b  mov     rsp, r11
0x18000670e  pop     rbp
0x18000670f  retn
```
