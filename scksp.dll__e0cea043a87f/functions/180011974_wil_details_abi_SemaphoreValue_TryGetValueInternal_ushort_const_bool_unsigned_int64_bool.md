# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180011974`
- end: `0x180011b10`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180011900`

## callees

- `0x18000cc00`
- `0x18000e7d8`
- `0x180010c6c`
- `0x180010c8c`
- `0x1800113c8`
- `0x180011444`
- `0x180011974`
- `0x18003c240`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800119e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800119e8`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800119d8`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180011a68`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800119d8`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180011a68`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x180011974  mov     [rsp-8+arg_8], rbx
0x180011979  mov     [rsp-8+arg_18], rdi
0x18001197e  push    rbp
0x18001197f  lea     rbp, [rsp-160h]
0x180011987  sub     rsp, 260h
0x18001198e  mov     rax, cs:__security_cookie
0x180011995  xor     rax, rsp
0x180011998  mov     [rbp+160h+var_10], rax
0x18001199f  mov     rdi, r8
0x1800119a2  mov     qword ptr [r8], 0
0x1800119a9  mov     r8, rcx; unsigned __int16 *
0x1800119ac  mov     edx, 104h; unsigned __int64
0x1800119b1  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x1800119b6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800119bb  lea     r8, aP0; "_p0"
0x1800119c2  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x1800119c7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800119cc  lea     r8, [rsp+260h+Name]; lpName
0x1800119d1  xor     edx, edx; bInheritHandle
0x1800119d3  mov     ecx, 1F0003h; dwDesiredAccess
0x1800119d8  call    cs:__imp_OpenSemaphoreW
0x1800119de  mov     [rsp+260h+var_230], rax
0x1800119e3  test    rax, rax
0x1800119e6  jnz     short loc_180011A0F
0x1800119e8  call    cs:__imp_GetLastError
0x1800119ee  cmp     eax, 2
0x1800119f1  jz      loc_180011ADE
0x1800119f7  mov     rcx, [rbp+168h]; this
0x1800119fe  mov     edx, 0D0h; void *
0x180011a03  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180011a08  mov     ebx, eax
0x180011a0a  jmp     loc_180011AE0
0x180011a0f  mov     [rsp+260h+var_23C], 0
0x180011a17  mov     [rsp+260h+var_240], 0; int
0x180011a1f  lea     rdx, [rsp+260h+var_23C]; int *
0x180011a24  mov     rcx, rax; hHandle
0x180011a27  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180011a2c  mov     ebx, eax
0x180011a2e  test    eax, eax
0x180011a30  jns     short loc_180011A4B
0x180011a32  mov     rcx, [rbp+168h]; this
0x180011a39  mov     r9d, eax; char *
0x180011a3c  mov     edx, 0D6h; void *
0x180011a41  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011a46  jmp     loc_180011AE0
0x180011a4b  lea     r8, asc_180043BD8; "h"
0x180011a52  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180011a57  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180011a5c  lea     r8, [rsp+260h+Name]; lpName
0x180011a61  xor     edx, edx; bInheritHandle
0x180011a63  mov     ecx, 1F0003h; dwDesiredAccess
0x180011a68  call    cs:__imp_OpenSemaphoreW
0x180011a6e  mov     [rsp+260h+var_238], rax
0x180011a73  test    rax, rax
0x180011a76  jnz     short loc_180011A97
0x180011a78  mov     rcx, [rbp+168h]; this
0x180011a7f  mov     edx, 0DCh; void *
0x180011a84  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180011a89  mov     ebx, eax
0x180011a8b  lea     rcx, [rsp+260h+var_238]
0x180011a90  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180011a95  jmp     short loc_180011AE0
0x180011a97  lea     rdx, [rsp+260h+var_240]; int *
0x180011a9c  mov     rcx, rax; hHandle
0x180011a9f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180011aa4  mov     ebx, eax
0x180011aa6  test    eax, eax
0x180011aa8  jns     short loc_180011AC0
0x180011aaa  mov     rcx, [rbp+168h]; this
0x180011ab1  mov     r9d, eax; char *
0x180011ab4  mov     edx, 0DEh; void *
0x180011ab9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011abe  jmp     short loc_180011A8B
0x180011ac0  lea     rcx, [rsp+260h+var_238]
0x180011ac5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180011aca  movsxd  rcx, [rsp+260h+var_240]
0x180011acf  shl     rcx, 1Fh
0x180011ad3  movsxd  rax, [rsp+260h+var_23C]
0x180011ad8  or      rcx, rax
0x180011adb  mov     [rdi], rcx
0x180011ade  xor     ebx, ebx
0x180011ae0  lea     rcx, [rsp+260h+var_230]
0x180011ae5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180011aea  mov     eax, ebx
0x180011aec  mov     rcx, [rbp+160h+var_10]
0x180011af3  xor     rcx, rsp; StackCookie
0x180011af6  call    __security_check_cookie
0x180011afb  lea     r11, [rsp+260h+var_s0]
0x180011b03  mov     rbx, [r11+18h]
0x180011b07  mov     rdi, [r11+28h]
0x180011b0b  mov     rsp, r11
0x180011b0e  pop     rbp
0x180011b0f  retn
```
