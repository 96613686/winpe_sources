# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18001f378`
- end: `0x18001f514`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18001dbec`

## callees

- `0x18000a17c`
- `0x18001db6c`
- `0x18001e700`
- `0x18001f024`
- `0x18001f044`
- `0x18001f2fc`
- `0x18001f378`
- `0x18004fa50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f3ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f3ec`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001f3dc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001f46c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001f3dc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001f46c`

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
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, Name);
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
    StringCchCatW(Name, v11, L"h");
    v13 = OpenSemaphoreW(0x1F0003u, 0, Name);
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
0x18001f378  mov     [rsp-8+arg_8], rbx
0x18001f37d  mov     [rsp-8+arg_18], rdi
0x18001f382  push    rbp
0x18001f383  lea     rbp, [rsp-160h]
0x18001f38b  sub     rsp, 260h
0x18001f392  mov     rax, cs:__security_cookie
0x18001f399  xor     rax, rsp
0x18001f39c  mov     [rbp+160h+var_10], rax
0x18001f3a3  mov     rdi, r8
0x18001f3a6  mov     qword ptr [r8], 0
0x18001f3ad  mov     r8, rcx; unsigned __int16 *
0x18001f3b0  mov     edx, 104h; unsigned __int64
0x18001f3b5  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18001f3ba  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001f3bf  lea     r8, aP0; "_p0"
0x18001f3c6  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18001f3cb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001f3d0  lea     r8, [rsp+260h+Name]; lpName
0x18001f3d5  xor     edx, edx; bInheritHandle
0x18001f3d7  mov     ecx, 1F0003h; dwDesiredAccess
0x18001f3dc  call    cs:__imp_OpenSemaphoreW
0x18001f3e2  mov     [rsp+260h+var_230], rax
0x18001f3e7  test    rax, rax
0x18001f3ea  jnz     short loc_18001F413
0x18001f3ec  call    cs:__imp_GetLastError
0x18001f3f2  cmp     eax, 2
0x18001f3f5  jz      loc_18001F4E2
0x18001f3fb  mov     rcx, [rbp+168h]; this
0x18001f402  mov     edx, 0D0h; void *
0x18001f407  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001f40c  mov     ebx, eax
0x18001f40e  jmp     loc_18001F4E4
0x18001f413  lea     rdx, [rsp+260h+var_23C]; int *
0x18001f418  mov     [rsp+260h+var_23C], 0
0x18001f420  mov     rcx, rax; hHandle
0x18001f423  mov     [rsp+260h+var_240], 0; int
0x18001f42b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001f430  mov     ebx, eax
0x18001f432  test    eax, eax
0x18001f434  jns     short loc_18001F44F
0x18001f436  mov     rcx, [rbp+168h]; this
0x18001f43d  mov     r9d, eax; char *
0x18001f440  mov     edx, 0D6h; void *
0x18001f445  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f44a  jmp     loc_18001F4E4
0x18001f44f  lea     r8, asc_180061FC8; "h"
0x18001f456  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18001f45b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001f460  lea     r8, [rsp+260h+Name]; lpName
0x18001f465  xor     edx, edx; bInheritHandle
0x18001f467  mov     ecx, 1F0003h; dwDesiredAccess
0x18001f46c  call    cs:__imp_OpenSemaphoreW
0x18001f472  mov     [rsp+260h+var_238], rax
0x18001f477  test    rax, rax
0x18001f47a  jnz     short loc_18001F49B
0x18001f47c  mov     rcx, [rbp+168h]; this
0x18001f483  mov     edx, 0DCh; void *
0x18001f488  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001f48d  mov     ebx, eax
0x18001f48f  lea     rcx, [rsp+260h+var_238]
0x18001f494  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001f499  jmp     short loc_18001F4E4
0x18001f49b  lea     rdx, [rsp+260h+var_240]; int *
0x18001f4a0  mov     rcx, rax; hHandle
0x18001f4a3  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001f4a8  mov     ebx, eax
0x18001f4aa  test    eax, eax
0x18001f4ac  jns     short loc_18001F4C4
0x18001f4ae  mov     rcx, [rbp+168h]; this
0x18001f4b5  mov     r9d, eax; char *
0x18001f4b8  mov     edx, 0DEh; void *
0x18001f4bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f4c2  jmp     short loc_18001F48F
0x18001f4c4  lea     rcx, [rsp+260h+var_238]
0x18001f4c9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001f4ce  movsxd  rcx, [rsp+260h+var_240]
0x18001f4d3  movsxd  rax, [rsp+260h+var_23C]
0x18001f4d8  shl     rcx, 1Fh
0x18001f4dc  or      rcx, rax
0x18001f4df  mov     [rdi], rcx
0x18001f4e2  xor     ebx, ebx
0x18001f4e4  lea     rcx, [rsp+260h+var_230]
0x18001f4e9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001f4ee  mov     eax, ebx
0x18001f4f0  mov     rcx, [rbp+160h+var_10]
0x18001f4f7  xor     rcx, rsp; StackCookie
0x18001f4fa  call    __security_check_cookie
0x18001f4ff  lea     r11, [rsp+260h+var_s0]
0x18001f507  mov     rbx, [r11+18h]
0x18001f50b  mov     rdi, [r11+28h]
0x18001f50f  mov     rsp, r11
0x18001f512  pop     rbp
0x18001f513  retn
```
