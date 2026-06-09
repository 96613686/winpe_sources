# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180021bec`
- end: `0x180021d88`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180021b78`

## callees

- `0x180002600`
- `0x180015290`
- `0x18001e080`
- `0x18001f528`
- `0x18002100c`
- `0x18002102c`
- `0x1800216ec`
- `0x180021bec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021c60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021c60`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180021c50`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180021ce0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180021c50`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180021ce0`

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
0x180021bec  mov     [rsp-8+arg_8], rbx
0x180021bf1  mov     [rsp-8+arg_18], rdi
0x180021bf6  push    rbp
0x180021bf7  lea     rbp, [rsp-160h]
0x180021bff  sub     rsp, 260h
0x180021c06  mov     rax, cs:__security_cookie
0x180021c0d  xor     rax, rsp
0x180021c10  mov     [rbp+160h+var_10], rax
0x180021c17  mov     rdi, r8
0x180021c1a  mov     qword ptr [r8], 0
0x180021c21  mov     r8, rcx; unsigned __int16 *
0x180021c24  mov     edx, 104h; unsigned __int64
0x180021c29  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180021c2e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180021c33  lea     r8, aP0; "_p0"
0x180021c3a  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180021c3f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180021c44  lea     r8, [rsp+260h+Name]; lpName
0x180021c49  xor     edx, edx; bInheritHandle
0x180021c4b  mov     ecx, 1F0003h; dwDesiredAccess
0x180021c50  call    cs:__imp_OpenSemaphoreW
0x180021c56  mov     [rsp+260h+var_230], rax
0x180021c5b  test    rax, rax
0x180021c5e  jnz     short loc_180021C87
0x180021c60  call    cs:__imp_GetLastError
0x180021c66  cmp     eax, 2
0x180021c69  jz      loc_180021D56
0x180021c6f  mov     rcx, [rbp+168h]; this
0x180021c76  mov     edx, 0D0h; void *
0x180021c7b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180021c80  mov     ebx, eax
0x180021c82  jmp     loc_180021D58
0x180021c87  lea     rdx, [rsp+260h+var_23C]; int *
0x180021c8c  mov     [rsp+260h+var_23C], 0
0x180021c94  mov     rcx, rax; hHandle
0x180021c97  mov     [rsp+260h+var_240], 0; int
0x180021c9f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180021ca4  mov     ebx, eax
0x180021ca6  test    eax, eax
0x180021ca8  jns     short loc_180021CC3
0x180021caa  mov     rcx, [rbp+168h]; this
0x180021cb1  mov     r9d, eax; char *
0x180021cb4  mov     edx, 0D6h; void *
0x180021cb9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021cbe  jmp     loc_180021D58
0x180021cc3  lea     r8, asc_180074AE8; "h"
0x180021cca  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180021ccf  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180021cd4  lea     r8, [rsp+260h+Name]; lpName
0x180021cd9  xor     edx, edx; bInheritHandle
0x180021cdb  mov     ecx, 1F0003h; dwDesiredAccess
0x180021ce0  call    cs:__imp_OpenSemaphoreW
0x180021ce6  mov     [rsp+260h+var_238], rax
0x180021ceb  test    rax, rax
0x180021cee  jnz     short loc_180021D0F
0x180021cf0  mov     rcx, [rbp+168h]; this
0x180021cf7  mov     edx, 0DCh; void *
0x180021cfc  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180021d01  mov     ebx, eax
0x180021d03  lea     rcx, [rsp+260h+var_238]
0x180021d08  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180021d0d  jmp     short loc_180021D58
0x180021d0f  lea     rdx, [rsp+260h+var_240]; int *
0x180021d14  mov     rcx, rax; hHandle
0x180021d17  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180021d1c  mov     ebx, eax
0x180021d1e  test    eax, eax
0x180021d20  jns     short loc_180021D38
0x180021d22  mov     rcx, [rbp+168h]; this
0x180021d29  mov     r9d, eax; char *
0x180021d2c  mov     edx, 0DEh; void *
0x180021d31  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021d36  jmp     short loc_180021D03
0x180021d38  lea     rcx, [rsp+260h+var_238]
0x180021d3d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180021d42  movsxd  rcx, [rsp+260h+var_240]
0x180021d47  movsxd  rax, [rsp+260h+var_23C]
0x180021d4c  shl     rcx, 1Fh
0x180021d50  or      rcx, rax
0x180021d53  mov     [rdi], rcx
0x180021d56  xor     ebx, ebx
0x180021d58  lea     rcx, [rsp+260h+var_230]
0x180021d5d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180021d62  mov     eax, ebx
0x180021d64  mov     rcx, [rbp+160h+var_10]
0x180021d6b  xor     rcx, rsp; StackCookie
0x180021d6e  call    __security_check_cookie
0x180021d73  lea     r11, [rsp+260h+var_s0]
0x180021d7b  mov     rbx, [r11+18h]
0x180021d7f  mov     rdi, [r11+28h]
0x180021d83  mov     rsp, r11
0x180021d86  pop     rbp
0x180021d87  retn
```
