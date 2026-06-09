# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000a49c`
- end: `0x18000a646`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `426`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000a418`

## callees

- `0x180002610`
- `0x180005cd8`
- `0x180007a80`
- `0x18000932c`
- `0x18000934c`
- `0x18000a07c`
- `0x18000a1c8`
- `0x18000a49c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000a500`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000a597`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000a500`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000a597`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a510`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a510`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  unsigned __int64 v5; // rdx
  wil::details *v6; // rax
  void *v7; // rdx
  unsigned int v8; // r8d
  const char *v9; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned __int64 v12; // rdx
  wil::details *v13; // rax
  unsigned int v14; // r8d
  const char *v15; // r9
  void *v16; // rdx
  int v17; // eax
  void *v18; // rdx
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh] BYREF
  wil::details *v22; // [rsp+28h] [rbp-D8h] BYREF
  wil::details *v23; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, v5, L"_p0");
  v6 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v23 = v6;
  if ( v6 )
  {
    v21 = 0;
    v20 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v21);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore);
      goto LABEL_13;
    }
    StringCchCatW(Name, v12, L"h");
    v13 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
    v22 = v13;
    if ( v13 )
    {
      v17 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v13, &v20);
      LastError = v17;
      if ( v17 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
          &v22,
          v18);
        *a3 = v21 | (unsigned __int64)((__int64)v20 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v17);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v14, v15);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v22,
      v16);
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
    &v23,
    v7);
  return LastError;
}

```

## disassembly

```asm
0x18000a49c  mov     [rsp-8+arg_8], rbx
0x18000a4a1  mov     [rsp-8+arg_18], rdi
0x18000a4a6  push    rbp
0x18000a4a7  lea     rbp, [rsp-160h]
0x18000a4af  sub     rsp, 260h
0x18000a4b6  mov     rax, cs:__security_cookie
0x18000a4bd  xor     rax, rsp
0x18000a4c0  mov     [rbp+160h+var_10], rax
0x18000a4c7  mov     rdi, r8
0x18000a4ca  mov     qword ptr [r8], 0
0x18000a4d1  mov     r8, rcx; unsigned __int16 *
0x18000a4d4  mov     edx, 104h; unsigned __int64
0x18000a4d9  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000a4de  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000a4e3  lea     r8, aP0; "_p0"
0x18000a4ea  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000a4ef  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a4f4  lea     r8, [rsp+260h+Name]; lpName
0x18000a4f9  xor     edx, edx; bInheritHandle
0x18000a4fb  mov     ecx, 1F0003h; dwDesiredAccess
0x18000a500  call    cs:__imp_OpenSemaphoreW
0x18000a506  mov     [rsp+260h+var_230], rax
0x18000a50b  test    rax, rax
0x18000a50e  jnz     short loc_18000A537
0x18000a510  call    cs:__imp_GetLastError
0x18000a516  cmp     eax, 2
0x18000a519  jz      loc_18000A614
0x18000a51f  mov     rcx, [rbp+168h]; this
0x18000a526  mov     edx, 0D0h; void *
0x18000a52b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000a530  mov     ebx, eax
0x18000a532  jmp     loc_18000A616
0x18000a537  lea     rdx, [rsp+260h+var_23C]; int *
0x18000a53c  mov     [rsp+260h+var_23C], 0
0x18000a544  mov     rcx, rax; hHandle
0x18000a547  mov     [rsp+260h+var_240], 0; int
0x18000a54f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000a554  mov     ebx, eax
0x18000a556  test    eax, eax
0x18000a558  jns     short loc_18000A57A
0x18000a55a  mov     rcx, [rbp+168h]; this
0x18000a561  lea     r8, aWil; "wil"
0x18000a568  mov     r9d, eax; char *
0x18000a56b  mov     edx, 0D6h; void *
0x18000a570  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a575  jmp     loc_18000A616
0x18000a57a  lea     r8, asc_1800227B8; "h"
0x18000a581  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000a586  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a58b  lea     r8, [rsp+260h+Name]; lpName
0x18000a590  xor     edx, edx; bInheritHandle
0x18000a592  mov     ecx, 1F0003h; dwDesiredAccess
0x18000a597  call    cs:__imp_OpenSemaphoreW
0x18000a59d  mov     [rsp+260h+var_238], rax
0x18000a5a2  test    rax, rax
0x18000a5a5  jnz     short loc_18000A5C6
0x18000a5a7  mov     rcx, [rbp+168h]; this
0x18000a5ae  mov     edx, 0DCh; void *
0x18000a5b3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000a5b8  mov     ebx, eax
0x18000a5ba  lea     rcx, [rsp+260h+var_238]
0x18000a5bf  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a5c4  jmp     short loc_18000A616
0x18000a5c6  lea     rdx, [rsp+260h+var_240]; int *
0x18000a5cb  mov     rcx, rax; hHandle
0x18000a5ce  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000a5d3  mov     ebx, eax
0x18000a5d5  test    eax, eax
0x18000a5d7  jns     short loc_18000A5F6
0x18000a5d9  mov     rcx, [rbp+168h]; this
0x18000a5e0  lea     r8, aWil; "wil"
0x18000a5e7  mov     r9d, eax; char *
0x18000a5ea  mov     edx, 0DEh; void *
0x18000a5ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a5f4  jmp     short loc_18000A5BA
0x18000a5f6  lea     rcx, [rsp+260h+var_238]
0x18000a5fb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a600  movsxd  rcx, [rsp+260h+var_240]
0x18000a605  movsxd  rax, [rsp+260h+var_23C]
0x18000a60a  shl     rcx, 1Fh
0x18000a60e  or      rcx, rax
0x18000a611  mov     [rdi], rcx
0x18000a614  xor     ebx, ebx
0x18000a616  lea     rcx, [rsp+260h+var_230]
0x18000a61b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a620  mov     eax, ebx
0x18000a622  mov     rcx, [rbp+160h+var_10]
0x18000a629  xor     rcx, rsp; StackCookie
0x18000a62c  call    __security_check_cookie
0x18000a631  lea     r11, [rsp+260h+var_s0]
0x18000a639  mov     rbx, [r11+18h]
0x18000a63d  mov     rdi, [r11+28h]
0x18000a641  mov     rsp, r11
0x18000a644  pop     rbp
0x18000a645  retn
```
