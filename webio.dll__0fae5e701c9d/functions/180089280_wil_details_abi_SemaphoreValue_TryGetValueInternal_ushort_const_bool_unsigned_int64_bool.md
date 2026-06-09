# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180089280`
- end: `0x18008942f`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `431`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180089208`

## callees

- `0x180065660`
- `0x1800722f0`
- `0x1800861fc`
- `0x1800875fc`
- `0x180088c20`
- `0x180088c40`
- `0x180089280`
- `0x180089d34`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800892fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800892fa`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800892e4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180089380`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800892e4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180089380`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        STRSAFE_LPCWSTR pszSrc,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  size_t v5; // rdx
  HANDLE v6; // rax
  unsigned int v7; // r8d
  const char *v8; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  size_t v11; // rdx
  unsigned int v12; // r8d
  HANDLE v13; // rax
  unsigned int v14; // r8d
  const char *v15; // r9
  int v16; // eax
  unsigned int v17; // r8d
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  int v20; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v21; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v22[2]; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t pszDest[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  *a3 = 0;
  StringCchCopyW(pszDest, 0x104u, pszSrc);
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
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v12, (const char *)(unsigned int)ValueFromSemaphore, v19);
      goto LABEL_13;
    }
    StringCchCatW(pszDest, v11, L"h");
    v13 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
    v21 = v13;
    if ( v13 )
    {
      v16 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v13, &v19);
      LastError = v16;
      if ( v16 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
        *a3 = v20 | (unsigned __int64)((__int64)v19 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v17, (const char *)(unsigned int)v16, v19);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v14, v15);
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
0x180089280  mov     [rsp-8+arg_8], rbx
0x180089285  mov     [rsp-8+arg_18], rdi
0x18008928a  push    rbp
0x18008928b  lea     rbp, [rsp-160h]
0x180089293  sub     rsp, 260h
0x18008929a  mov     rax, cs:__security_cookie
0x1800892a1  xor     rax, rsp
0x1800892a4  mov     [rbp+160h+var_10], rax
0x1800892ab  mov     rdi, r8
0x1800892ae  mov     qword ptr [r8], 0
0x1800892b5  mov     r8, rcx; pszSrc
0x1800892b8  mov     edx, 104h; cchDest
0x1800892bd  lea     rcx, [rsp+260h+pszDest]; pszDest
0x1800892c2  call    StringCchCopyW
0x1800892c7  lea     r8, aP0; "_p0"
0x1800892ce  lea     rcx, [rsp+260h+pszDest]; pszDest
0x1800892d3  call    StringCchCatW
0x1800892d8  lea     r8, [rsp+260h+pszDest]; lpName
0x1800892dd  xor     edx, edx; bInheritHandle
0x1800892df  mov     ecx, 1F0003h; dwDesiredAccess
0x1800892e4  call    cs:__imp_OpenSemaphoreW
0x1800892eb  nop     dword ptr [rax+rax+00h]
0x1800892f0  mov     [rsp+260h+var_230], rax
0x1800892f5  test    rax, rax
0x1800892f8  jnz     short loc_180089327
0x1800892fa  call    cs:__imp_GetLastError
0x180089301  nop     dword ptr [rax+rax+00h]
0x180089306  cmp     eax, 2
0x180089309  jz      loc_1800893FC
0x18008930f  mov     rcx, [rbp+168h]; this
0x180089316  mov     edx, 0D0h; void *
0x18008931b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180089320  mov     ebx, eax
0x180089322  jmp     loc_1800893FE
0x180089327  lea     rdx, [rsp+260h+var_23C]; int *
0x18008932c  mov     [rsp+260h+var_23C], 0
0x180089334  mov     rcx, rax; hHandle
0x180089337  mov     [rsp+260h+var_240], 0; int
0x18008933f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180089344  mov     ebx, eax
0x180089346  test    eax, eax
0x180089348  jns     short loc_180089363
0x18008934a  mov     rcx, [rbp+168h]; this
0x180089351  mov     r9d, eax; char *
0x180089354  mov     edx, 0D6h; void *
0x180089359  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008935e  jmp     loc_1800893FE
0x180089363  lea     r8, asc_1800A0570; "h"
0x18008936a  lea     rcx, [rsp+260h+pszDest]; pszDest
0x18008936f  call    StringCchCatW
0x180089374  lea     r8, [rsp+260h+pszDest]; lpName
0x180089379  xor     edx, edx; bInheritHandle
0x18008937b  mov     ecx, 1F0003h; dwDesiredAccess
0x180089380  call    cs:__imp_OpenSemaphoreW
0x180089387  nop     dword ptr [rax+rax+00h]
0x18008938c  mov     [rsp+260h+var_238], rax
0x180089391  test    rax, rax
0x180089394  jnz     short loc_1800893B5
0x180089396  mov     rcx, [rbp+168h]; this
0x18008939d  mov     edx, 0DCh; void *
0x1800893a2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800893a7  mov     ebx, eax
0x1800893a9  lea     rcx, [rsp+260h+var_238]
0x1800893ae  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800893b3  jmp     short loc_1800893FE
0x1800893b5  lea     rdx, [rsp+260h+var_240]; int *
0x1800893ba  mov     rcx, rax; hHandle
0x1800893bd  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800893c2  mov     ebx, eax
0x1800893c4  test    eax, eax
0x1800893c6  jns     short loc_1800893DE
0x1800893c8  mov     rcx, [rbp+168h]; this
0x1800893cf  mov     r9d, eax; char *
0x1800893d2  mov     edx, 0DEh; void *
0x1800893d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800893dc  jmp     short loc_1800893A9
0x1800893de  lea     rcx, [rsp+260h+var_238]
0x1800893e3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800893e8  movsxd  rcx, [rsp+260h+var_240]
0x1800893ed  movsxd  rax, [rsp+260h+var_23C]
0x1800893f2  shl     rcx, 1Fh
0x1800893f6  or      rcx, rax
0x1800893f9  mov     [rdi], rcx
0x1800893fc  xor     ebx, ebx
0x1800893fe  lea     rcx, [rsp+260h+var_230]
0x180089403  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180089408  mov     eax, ebx
0x18008940a  mov     rcx, [rbp+160h+var_10]
0x180089411  xor     rcx, rsp; StackCookie
0x180089414  call    __security_check_cookie
0x180089419  lea     r11, [rsp+260h+var_s0]
0x180089421  mov     rbx, [r11+18h]
0x180089425  mov     rdi, [r11+28h]
0x180089429  mov     rsp, r11
0x18008942c  pop     rbp
0x18008942d  retn
```
