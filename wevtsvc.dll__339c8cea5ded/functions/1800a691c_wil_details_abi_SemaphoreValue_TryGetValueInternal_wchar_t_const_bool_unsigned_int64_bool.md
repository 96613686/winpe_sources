# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800a691c`
- end: `0x1800a6ab8`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800a68a8`

## callees

- `0x18009540c`
- `0x18009aee0`
- `0x1800a1df4`
- `0x1800a4ba8`
- `0x1800a6250`
- `0x1800a6270`
- `0x1800a6774`
- `0x1800a691c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800a6980`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800a6a10`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800a6980`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800a6a10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a6990`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a6990`

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
  unsigned int v12; // r8d
  HANDLE v13; // rax
  unsigned int v14; // r8d
  const char *v15; // r9
  int v16; // eax
  unsigned int v17; // r8d
  size_t v19; // [rsp+20h] [rbp-E0h]
  int v20; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+30h] [rbp-D0h] BYREF
  int v22; // [rsp+34h] [rbp-CCh] BYREF
  HANDLE v23; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE v24[2]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCopyWorkerW(pszDest, 0x104u, a3, pszSrc, v19);
  StringCchCatW(pszDest, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v24[0] = v6;
  if ( v6 )
  {
    v22 = 0;
    v21 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v22);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v12, (const char *)(unsigned int)ValueFromSemaphore, v20);
      goto LABEL_13;
    }
    StringCchCatW(pszDest, v11, L"h");
    v13 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
    v23 = v13;
    if ( v13 )
    {
      v16 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v13, &v21);
      LastError = v16;
      if ( v16 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
        *a3 = v22 | (unsigned __int64)((__int64)v21 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v17, (const char *)(unsigned int)v16, v20);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v14, v15);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v24);
  return LastError;
}

```

## disassembly

```asm
0x1800a691c  mov     [rsp-8+arg_8], rbx
0x1800a6921  mov     [rsp-8+arg_18], rdi
0x1800a6926  push    rbp
0x1800a6927  lea     rbp, [rsp-170h]
0x1800a692f  sub     rsp, 270h
0x1800a6936  mov     rax, cs:__security_cookie
0x1800a693d  xor     rax, rsp
0x1800a6940  mov     [rbp+170h+var_10], rax
0x1800a6947  mov     r9, rcx; pszSrc
0x1800a694a  mov     qword ptr [r8], 0
0x1800a6951  lea     rcx, [rsp+270h+pszDest]; pszDest
0x1800a6956  mov     edx, 104h; cchDest
0x1800a695b  mov     rdi, r8
0x1800a695e  call    StringCopyWorkerW
0x1800a6963  lea     r8, aP0; "_p0"
0x1800a696a  lea     rcx, [rsp+270h+pszDest]; wchar_t *
0x1800a696f  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800a6974  lea     r8, [rsp+270h+pszDest]; lpName
0x1800a6979  xor     edx, edx; bInheritHandle
0x1800a697b  mov     ecx, 1F0003h; dwDesiredAccess
0x1800a6980  call    cs:__imp_OpenSemaphoreW
0x1800a6986  mov     [rsp+270h+var_230], rax
0x1800a698b  test    rax, rax
0x1800a698e  jnz     short loc_1800A69B7
0x1800a6990  call    cs:__imp_GetLastError
0x1800a6996  cmp     eax, 2
0x1800a6999  jz      loc_1800A6A86
0x1800a699f  mov     rcx, [rbp+178h]; this
0x1800a69a6  mov     edx, 0D0h; void *
0x1800a69ab  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a69b0  mov     ebx, eax
0x1800a69b2  jmp     loc_1800A6A88
0x1800a69b7  lea     rdx, [rsp+270h+var_23C]; int *
0x1800a69bc  mov     [rsp+270h+var_23C], 0
0x1800a69c4  mov     rcx, rax; hHandle
0x1800a69c7  mov     [rsp+270h+var_240], 0
0x1800a69cf  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800a69d4  mov     ebx, eax
0x1800a69d6  test    eax, eax
0x1800a69d8  jns     short loc_1800A69F3
0x1800a69da  mov     rcx, [rbp+178h]; this
0x1800a69e1  mov     r9d, eax; char *
0x1800a69e4  mov     edx, 0D6h; void *
0x1800a69e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a69ee  jmp     loc_1800A6A88
0x1800a69f3  lea     r8, asc_1800EFA88; "h"
0x1800a69fa  lea     rcx, [rsp+270h+pszDest]; wchar_t *
0x1800a69ff  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800a6a04  lea     r8, [rsp+270h+pszDest]; lpName
0x1800a6a09  xor     edx, edx; bInheritHandle
0x1800a6a0b  mov     ecx, 1F0003h; dwDesiredAccess
0x1800a6a10  call    cs:__imp_OpenSemaphoreW
0x1800a6a16  mov     [rsp+270h+var_238], rax
0x1800a6a1b  test    rax, rax
0x1800a6a1e  jnz     short loc_1800A6A3F
0x1800a6a20  mov     rcx, [rbp+178h]; this
0x1800a6a27  mov     edx, 0DCh; void *
0x1800a6a2c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a6a31  mov     ebx, eax
0x1800a6a33  lea     rcx, [rsp+270h+var_238]
0x1800a6a38  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800a6a3d  jmp     short loc_1800A6A88
0x1800a6a3f  lea     rdx, [rsp+270h+var_240]; int *
0x1800a6a44  mov     rcx, rax; hHandle
0x1800a6a47  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800a6a4c  mov     ebx, eax
0x1800a6a4e  test    eax, eax
0x1800a6a50  jns     short loc_1800A6A68
0x1800a6a52  mov     rcx, [rbp+178h]; this
0x1800a6a59  mov     r9d, eax; char *
0x1800a6a5c  mov     edx, 0DEh; void *
0x1800a6a61  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6a66  jmp     short loc_1800A6A33
0x1800a6a68  lea     rcx, [rsp+270h+var_238]
0x1800a6a6d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800a6a72  movsxd  rcx, [rsp+270h+var_240]
0x1800a6a77  movsxd  rax, [rsp+270h+var_23C]
0x1800a6a7c  shl     rcx, 1Fh
0x1800a6a80  or      rcx, rax
0x1800a6a83  mov     [rdi], rcx
0x1800a6a86  xor     ebx, ebx
0x1800a6a88  lea     rcx, [rsp+270h+var_230]
0x1800a6a8d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800a6a92  mov     eax, ebx
0x1800a6a94  mov     rcx, [rbp+170h+var_10]
0x1800a6a9b  xor     rcx, rsp; StackCookie
0x1800a6a9e  call    __security_check_cookie
0x1800a6aa3  lea     r11, [rsp+270h+var_s0]
0x1800a6aab  mov     rbx, [r11+18h]
0x1800a6aaf  mov     rdi, [r11+28h]
0x1800a6ab3  mov     rsp, r11
0x1800a6ab6  pop     rbp
0x1800a6ab7  retn
```
