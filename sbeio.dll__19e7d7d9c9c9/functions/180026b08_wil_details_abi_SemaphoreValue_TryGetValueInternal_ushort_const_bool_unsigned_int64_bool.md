# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180026b08`
- end: `0x180026ca4`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18001721c`

## callees

- `0x1800015f0`
- `0x18000774c`
- `0x18001583c`
- `0x18001cb70`
- `0x18002442c`
- `0x18002444c`
- `0x180026898`
- `0x180026b08`

## import_xrefs

- `KERNEL32!OpenSemaphoreW` at `0x180026b6c`
- `KERNEL32!OpenSemaphoreW` at `0x180026bfc`
- `KERNEL32!OpenSemaphoreW` at `0x180026b6c`
- `KERNEL32!OpenSemaphoreW` at `0x180026bfc`
- `KERNEL32!GetLastError` at `0x180026b7c`
- `KERNEL32!GetLastError` at `0x180026b7c`

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
0x180026b08  mov     [rsp-8+arg_8], rbx
0x180026b0d  mov     [rsp-8+arg_18], rdi
0x180026b12  push    rbp
0x180026b13  lea     rbp, [rsp-160h]
0x180026b1b  sub     rsp, 260h
0x180026b22  mov     rax, cs:__security_cookie
0x180026b29  xor     rax, rsp
0x180026b2c  mov     [rbp+160h+var_10], rax
0x180026b33  mov     rdi, r8
0x180026b36  mov     qword ptr [r8], 0
0x180026b3d  mov     r8, rcx; unsigned __int16 *
0x180026b40  mov     edx, 104h; unsigned __int64
0x180026b45  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180026b4a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180026b4f  lea     r8, aP0; "_p0"
0x180026b56  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180026b5b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180026b60  lea     r8, [rsp+260h+Name]; lpName
0x180026b65  xor     edx, edx; bInheritHandle
0x180026b67  mov     ecx, 1F0003h; dwDesiredAccess
0x180026b6c  call    cs:__imp_OpenSemaphoreW
0x180026b72  mov     [rsp+260h+var_230], rax
0x180026b77  test    rax, rax
0x180026b7a  jnz     short loc_180026BA3
0x180026b7c  call    cs:__imp_GetLastError
0x180026b82  cmp     eax, 2
0x180026b85  jz      loc_180026C72
0x180026b8b  mov     rcx, [rbp+168h]; this
0x180026b92  mov     edx, 0D0h; void *
0x180026b97  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180026b9c  mov     ebx, eax
0x180026b9e  jmp     loc_180026C74
0x180026ba3  lea     rdx, [rsp+260h+var_23C]; int *
0x180026ba8  mov     [rsp+260h+var_23C], 0
0x180026bb0  mov     rcx, rax; hHandle
0x180026bb3  mov     [rsp+260h+var_240], 0; int
0x180026bbb  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180026bc0  mov     ebx, eax
0x180026bc2  test    eax, eax
0x180026bc4  jns     short loc_180026BDF
0x180026bc6  mov     rcx, [rbp+168h]; this
0x180026bcd  mov     r9d, eax; char *
0x180026bd0  mov     edx, 0D6h; void *
0x180026bd5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026bda  jmp     loc_180026C74
0x180026bdf  lea     r8, asc_18002F1A0; "h"
0x180026be6  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180026beb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180026bf0  lea     r8, [rsp+260h+Name]; lpName
0x180026bf5  xor     edx, edx; bInheritHandle
0x180026bf7  mov     ecx, 1F0003h; dwDesiredAccess
0x180026bfc  call    cs:__imp_OpenSemaphoreW
0x180026c02  mov     [rsp+260h+var_238], rax
0x180026c07  test    rax, rax
0x180026c0a  jnz     short loc_180026C2B
0x180026c0c  mov     rcx, [rbp+168h]; this
0x180026c13  mov     edx, 0DCh; void *
0x180026c18  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180026c1d  mov     ebx, eax
0x180026c1f  lea     rcx, [rsp+260h+var_238]
0x180026c24  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180026c29  jmp     short loc_180026C74
0x180026c2b  lea     rdx, [rsp+260h+var_240]; int *
0x180026c30  mov     rcx, rax; hHandle
0x180026c33  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180026c38  mov     ebx, eax
0x180026c3a  test    eax, eax
0x180026c3c  jns     short loc_180026C54
0x180026c3e  mov     rcx, [rbp+168h]; this
0x180026c45  mov     r9d, eax; char *
0x180026c48  mov     edx, 0DEh; void *
0x180026c4d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026c52  jmp     short loc_180026C1F
0x180026c54  lea     rcx, [rsp+260h+var_238]
0x180026c59  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180026c5e  movsxd  rcx, [rsp+260h+var_240]
0x180026c63  movsxd  rax, [rsp+260h+var_23C]
0x180026c68  shl     rcx, 1Fh
0x180026c6c  or      rcx, rax
0x180026c6f  mov     [rdi], rcx
0x180026c72  xor     ebx, ebx
0x180026c74  lea     rcx, [rsp+260h+var_230]
0x180026c79  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180026c7e  mov     eax, ebx
0x180026c80  mov     rcx, [rbp+160h+var_10]
0x180026c87  xor     rcx, rsp; StackCookie
0x180026c8a  call    __security_check_cookie
0x180026c8f  lea     r11, [rsp+260h+var_s0]
0x180026c97  mov     rbx, [r11+18h]
0x180026c9b  mov     rdi, [r11+28h]
0x180026c9f  mov     rsp, r11
0x180026ca2  pop     rbp
0x180026ca3  retn
```
