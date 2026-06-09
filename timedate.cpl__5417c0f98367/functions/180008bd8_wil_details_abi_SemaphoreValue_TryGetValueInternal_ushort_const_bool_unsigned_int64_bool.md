# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180008bd8`
- end: `0x180008d7a`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `418`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180008b64`

## callees

- `0x1800051f0`
- `0x1800064e4`
- `0x180007d04`
- `0x180007d24`
- `0x18000893c`
- `0x1800089c8`
- `0x180008bd8`
- `0x180028f60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008c41`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008cd3`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008c41`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008cd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008c51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008c51`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  HANDLE v5; // rax
  unsigned int v6; // r8d
  const char *v7; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned int v10; // r8d
  HANDLE v11; // rax
  unsigned int v12; // r8d
  const char *v13; // r9
  int v14; // eax
  unsigned int v15; // r8d
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v19; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v20[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, 0x104u, L"_p0");
  v5 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v20[0] = v5;
  if ( v5 )
  {
    v18 = 0;
    v17 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &v18);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v10, (const char *)(unsigned int)ValueFromSemaphore, v17);
      goto LABEL_13;
    }
    StringCchCatW(Name, 0x104u, L"h");
    v11 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v19 = v11;
    if ( v11 )
    {
      v14 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v11, &v17);
      LastError = v14;
      if ( v14 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
        *a3 = v18 | (unsigned __int64)((__int64)v17 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v15, (const char *)(unsigned int)v14, v17);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v12, v13);
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
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v6, v7);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v20);
  return LastError;
}

```

## disassembly

```asm
0x180008bd8  mov     [rsp-8+arg_8], rbx
0x180008bdd  push    rbp
0x180008bde  push    rdi
0x180008bdf  push    r14
0x180008be1  lea     rbp, [rsp-160h]
0x180008be9  sub     rsp, 260h
0x180008bf0  mov     rax, cs:__security_cookie
0x180008bf7  xor     rax, rsp
0x180008bfa  mov     [rbp+170h+var_20], rax
0x180008c01  mov     rdi, r8
0x180008c04  mov     qword ptr [r8], 0
0x180008c0b  mov     r8, rcx; unsigned __int16 *
0x180008c0e  mov     r14d, 104h
0x180008c14  mov     edx, r14d; unsigned __int64
0x180008c17  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180008c1c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180008c21  lea     r8, aP0; "_p0"
0x180008c28  mov     edx, r14d; unsigned __int64
0x180008c2b  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180008c30  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008c35  lea     r8, [rsp+270h+Name]; lpName
0x180008c3a  xor     edx, edx; bInheritHandle
0x180008c3c  mov     ecx, 1F0003h; dwDesiredAccess
0x180008c41  call    cs:__imp_OpenSemaphoreW
0x180008c47  mov     [rsp+270h+var_240], rax
0x180008c4c  test    rax, rax
0x180008c4f  jnz     short loc_180008C77
0x180008c51  call    cs:__imp_GetLastError
0x180008c57  cmp     eax, 2
0x180008c5a  jz      loc_180008D49
0x180008c60  mov     rcx, [rbp+178h]; this
0x180008c67  lea     edx, [r14-34h]; void *
0x180008c6b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180008c70  mov     ebx, eax
0x180008c72  jmp     loc_180008D4B
0x180008c77  lea     rdx, [rsp+270h+var_24C]; int *
0x180008c7c  mov     [rsp+270h+var_24C], 0
0x180008c84  mov     rcx, rax; hHandle
0x180008c87  mov     [rsp+270h+var_250], 0; int
0x180008c8f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180008c94  mov     ebx, eax
0x180008c96  test    eax, eax
0x180008c98  jns     short loc_180008CB3
0x180008c9a  mov     rcx, [rbp+178h]; this
0x180008ca1  mov     r9d, eax; char *
0x180008ca4  mov     edx, 0D6h; void *
0x180008ca9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008cae  jmp     loc_180008D4B
0x180008cb3  lea     r8, asc_18002E708; "h"
0x180008cba  mov     rdx, r14; unsigned __int64
0x180008cbd  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180008cc2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008cc7  lea     r8, [rsp+270h+Name]; lpName
0x180008ccc  xor     edx, edx; bInheritHandle
0x180008cce  mov     ecx, 1F0003h; dwDesiredAccess
0x180008cd3  call    cs:__imp_OpenSemaphoreW
0x180008cd9  mov     [rsp+270h+var_248], rax
0x180008cde  test    rax, rax
0x180008ce1  jnz     short loc_180008D02
0x180008ce3  mov     rcx, [rbp+178h]; this
0x180008cea  mov     edx, 0DCh; void *
0x180008cef  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180008cf4  mov     ebx, eax
0x180008cf6  lea     rcx, [rsp+270h+var_248]
0x180008cfb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008d00  jmp     short loc_180008D4B
0x180008d02  lea     rdx, [rsp+270h+var_250]; int *
0x180008d07  mov     rcx, rax; hHandle
0x180008d0a  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180008d0f  mov     ebx, eax
0x180008d11  test    eax, eax
0x180008d13  jns     short loc_180008D2B
0x180008d15  mov     rcx, [rbp+178h]; this
0x180008d1c  mov     r9d, eax; char *
0x180008d1f  mov     edx, 0DEh; void *
0x180008d24  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008d29  jmp     short loc_180008CF6
0x180008d2b  lea     rcx, [rsp+270h+var_248]
0x180008d30  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008d35  movsxd  rcx, [rsp+270h+var_250]
0x180008d3a  movsxd  rax, [rsp+270h+var_24C]
0x180008d3f  shl     rcx, 1Fh
0x180008d43  or      rcx, rax
0x180008d46  mov     [rdi], rcx
0x180008d49  xor     ebx, ebx
0x180008d4b  lea     rcx, [rsp+270h+var_240]
0x180008d50  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008d55  mov     eax, ebx
0x180008d57  mov     rcx, [rbp+170h+var_20]
0x180008d5e  xor     rcx, rsp; StackCookie
0x180008d61  call    __security_check_cookie
0x180008d66  mov     rbx, [rsp+270h+arg_8]
0x180008d6e  add     rsp, 260h
0x180008d75  pop     r14
0x180008d77  pop     rdi
0x180008d78  pop     rbp
0x180008d79  retn
```
