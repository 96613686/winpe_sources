# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000e43c`
- end: `0x18000e5e6`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `426`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000c584`

## callees

- `0x18000bf8c`
- `0x18000d19c`
- `0x18000df98`
- `0x18000dfb8`
- `0x18000e26c`
- `0x18000e2e8`
- `0x18000e43c`
- `0x1800155c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e4b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e4b0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000e4a0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000e537`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000e4a0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000e537`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
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
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v19; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v20[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, Name);
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
        v17);
      goto LABEL_13;
    }
    StringCchCatW(Name, v11, L"h");
    v12 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v19 = v12;
    if ( v12 )
    {
      v15 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v12, &v17);
      LastError = v15;
      if ( v15 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
        *a3 = v18 | (unsigned __int64)((__int64)v17 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v15,
        v17);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v13, v14);
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
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v7, v8);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v20);
  return LastError;
}

```

## disassembly

```asm
0x18000e43c  mov     [rsp-8+arg_8], rbx
0x18000e441  mov     [rsp-8+arg_18], rdi
0x18000e446  push    rbp
0x18000e447  lea     rbp, [rsp-160h]
0x18000e44f  sub     rsp, 260h
0x18000e456  mov     rax, cs:__security_cookie
0x18000e45d  xor     rax, rsp
0x18000e460  mov     [rbp+160h+var_10], rax
0x18000e467  mov     rdi, r8
0x18000e46a  mov     qword ptr [r8], 0
0x18000e471  mov     r8, rcx; unsigned __int16 *
0x18000e474  mov     edx, 104h; unsigned __int64
0x18000e479  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000e47e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000e483  lea     r8, aP0; "_p0"
0x18000e48a  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000e48f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000e494  lea     r8, [rsp+260h+Name]; lpName
0x18000e499  xor     edx, edx; bInheritHandle
0x18000e49b  mov     ecx, 1F0003h; dwDesiredAccess
0x18000e4a0  call    cs:__imp_OpenSemaphoreW
0x18000e4a6  mov     [rsp+260h+var_230], rax
0x18000e4ab  test    rax, rax
0x18000e4ae  jnz     short loc_18000E4D7
0x18000e4b0  call    cs:__imp_GetLastError
0x18000e4b6  cmp     eax, 2
0x18000e4b9  jz      loc_18000E5B4
0x18000e4bf  mov     rcx, [rbp+168h]; this
0x18000e4c6  mov     edx, 0D0h; void *
0x18000e4cb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000e4d0  mov     ebx, eax
0x18000e4d2  jmp     loc_18000E5B6
0x18000e4d7  lea     rdx, [rsp+260h+var_23C]; int *
0x18000e4dc  mov     [rsp+260h+var_23C], 0
0x18000e4e4  mov     rcx, rax; hHandle
0x18000e4e7  mov     [rsp+260h+var_240], 0; int
0x18000e4ef  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000e4f4  mov     ebx, eax
0x18000e4f6  test    eax, eax
0x18000e4f8  jns     short loc_18000E51A
0x18000e4fa  mov     rcx, [rbp+168h]; this
0x18000e501  lea     r8, aWil; "wil"
0x18000e508  mov     r9d, eax; char *
0x18000e50b  mov     edx, 0D6h; void *
0x18000e510  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e515  jmp     loc_18000E5B6
0x18000e51a  lea     r8, asc_1800183E8; "h"
0x18000e521  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000e526  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000e52b  lea     r8, [rsp+260h+Name]; lpName
0x18000e530  xor     edx, edx; bInheritHandle
0x18000e532  mov     ecx, 1F0003h; dwDesiredAccess
0x18000e537  call    cs:__imp_OpenSemaphoreW
0x18000e53d  mov     [rsp+260h+var_238], rax
0x18000e542  test    rax, rax
0x18000e545  jnz     short loc_18000E566
0x18000e547  mov     rcx, [rbp+168h]; this
0x18000e54e  mov     edx, 0DCh; void *
0x18000e553  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000e558  mov     ebx, eax
0x18000e55a  lea     rcx, [rsp+260h+var_238]
0x18000e55f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000e564  jmp     short loc_18000E5B6
0x18000e566  lea     rdx, [rsp+260h+var_240]; int *
0x18000e56b  mov     rcx, rax; hHandle
0x18000e56e  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000e573  mov     ebx, eax
0x18000e575  test    eax, eax
0x18000e577  jns     short loc_18000E596
0x18000e579  mov     rcx, [rbp+168h]; this
0x18000e580  lea     r8, aWil; "wil"
0x18000e587  mov     r9d, eax; char *
0x18000e58a  mov     edx, 0DEh; void *
0x18000e58f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e594  jmp     short loc_18000E55A
0x18000e596  lea     rcx, [rsp+260h+var_238]
0x18000e59b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000e5a0  movsxd  rcx, [rsp+260h+var_240]
0x18000e5a5  movsxd  rax, [rsp+260h+var_23C]
0x18000e5aa  shl     rcx, 1Fh
0x18000e5ae  or      rcx, rax
0x18000e5b1  mov     [rdi], rcx
0x18000e5b4  xor     ebx, ebx
0x18000e5b6  lea     rcx, [rsp+260h+var_230]
0x18000e5bb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000e5c0  mov     eax, ebx
0x18000e5c2  mov     rcx, [rbp+160h+var_10]
0x18000e5c9  xor     rcx, rsp; StackCookie
0x18000e5cc  call    __security_check_cookie
0x18000e5d1  lea     r11, [rsp+260h+var_s0]
0x18000e5d9  mov     rbx, [r11+18h]
0x18000e5dd  mov     rdi, [r11+28h]
0x18000e5e1  mov     rsp, r11
0x18000e5e4  pop     rbp
0x18000e5e5  retn
```
