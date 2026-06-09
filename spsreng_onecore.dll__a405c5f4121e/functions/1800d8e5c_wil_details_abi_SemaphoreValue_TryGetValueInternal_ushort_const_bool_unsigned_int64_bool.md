# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800d8e5c`
- end: `0x1800d8ffe`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `418`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800d72a8`

## callees

- `0x1800034b0`
- `0x18001406c`
- `0x1800141c0`
- `0x1800d7150`
- `0x1800d7e38`
- `0x1800d8904`
- `0x1800d8924`
- `0x1800d8e5c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d8ed5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d8ed5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800d8ec5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800d8f57`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800d8ec5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800d8f57`

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
0x1800d8e5c  mov     [rsp-8+arg_8], rbx
0x1800d8e61  push    rbp
0x1800d8e62  push    rdi
0x1800d8e63  push    r14
0x1800d8e65  lea     rbp, [rsp-160h]
0x1800d8e6d  sub     rsp, 260h
0x1800d8e74  mov     rax, cs:__security_cookie
0x1800d8e7b  xor     rax, rsp
0x1800d8e7e  mov     [rbp+170h+var_20], rax
0x1800d8e85  mov     rdi, r8
0x1800d8e88  mov     qword ptr [r8], 0
0x1800d8e8f  mov     r8, rcx; unsigned __int16 *
0x1800d8e92  mov     r14d, 104h
0x1800d8e98  mov     edx, r14d; unsigned __int64
0x1800d8e9b  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800d8ea0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800d8ea5  lea     r8, aP0; "_p0"
0x1800d8eac  mov     edx, r14d; unsigned __int64
0x1800d8eaf  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800d8eb4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800d8eb9  lea     r8, [rsp+270h+Name]; lpName
0x1800d8ebe  xor     edx, edx; bInheritHandle
0x1800d8ec0  mov     ecx, 1F0003h; dwDesiredAccess
0x1800d8ec5  call    cs:__imp_OpenSemaphoreW
0x1800d8ecb  mov     [rsp+270h+var_240], rax
0x1800d8ed0  test    rax, rax
0x1800d8ed3  jnz     short loc_1800D8EFB
0x1800d8ed5  call    cs:__imp_GetLastError
0x1800d8edb  cmp     eax, 2
0x1800d8ede  jz      loc_1800D8FCD
0x1800d8ee4  mov     rcx, [rbp+178h]; this
0x1800d8eeb  lea     edx, [r14-34h]; void *
0x1800d8eef  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800d8ef4  mov     ebx, eax
0x1800d8ef6  jmp     loc_1800D8FCF
0x1800d8efb  lea     rdx, [rsp+270h+var_24C]; int *
0x1800d8f00  mov     [rsp+270h+var_24C], 0
0x1800d8f08  mov     rcx, rax; hHandle
0x1800d8f0b  mov     [rsp+270h+var_250], 0; int
0x1800d8f13  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800d8f18  mov     ebx, eax
0x1800d8f1a  test    eax, eax
0x1800d8f1c  jns     short loc_1800D8F37
0x1800d8f1e  mov     rcx, [rbp+178h]; this
0x1800d8f25  mov     r9d, eax; char *
0x1800d8f28  mov     edx, 0D6h; void *
0x1800d8f2d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d8f32  jmp     loc_1800D8FCF
0x1800d8f37  lea     r8, asc_1801153E0; "h"
0x1800d8f3e  mov     rdx, r14; unsigned __int64
0x1800d8f41  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800d8f46  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800d8f4b  lea     r8, [rsp+270h+Name]; lpName
0x1800d8f50  xor     edx, edx; bInheritHandle
0x1800d8f52  mov     ecx, 1F0003h; dwDesiredAccess
0x1800d8f57  call    cs:__imp_OpenSemaphoreW
0x1800d8f5d  mov     [rsp+270h+var_248], rax
0x1800d8f62  test    rax, rax
0x1800d8f65  jnz     short loc_1800D8F86
0x1800d8f67  mov     rcx, [rbp+178h]; this
0x1800d8f6e  mov     edx, 0DCh; void *
0x1800d8f73  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800d8f78  mov     ebx, eax
0x1800d8f7a  lea     rcx, [rsp+270h+var_248]
0x1800d8f7f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800d8f84  jmp     short loc_1800D8FCF
0x1800d8f86  lea     rdx, [rsp+270h+var_250]; int *
0x1800d8f8b  mov     rcx, rax; hHandle
0x1800d8f8e  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800d8f93  mov     ebx, eax
0x1800d8f95  test    eax, eax
0x1800d8f97  jns     short loc_1800D8FAF
0x1800d8f99  mov     rcx, [rbp+178h]; this
0x1800d8fa0  mov     r9d, eax; char *
0x1800d8fa3  mov     edx, 0DEh; void *
0x1800d8fa8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d8fad  jmp     short loc_1800D8F7A
0x1800d8faf  lea     rcx, [rsp+270h+var_248]
0x1800d8fb4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800d8fb9  movsxd  rcx, [rsp+270h+var_250]
0x1800d8fbe  movsxd  rax, [rsp+270h+var_24C]
0x1800d8fc3  shl     rcx, 1Fh
0x1800d8fc7  or      rcx, rax
0x1800d8fca  mov     [rdi], rcx
0x1800d8fcd  xor     ebx, ebx
0x1800d8fcf  lea     rcx, [rsp+270h+var_240]
0x1800d8fd4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800d8fd9  mov     eax, ebx
0x1800d8fdb  mov     rcx, [rbp+170h+var_20]
0x1800d8fe2  xor     rcx, rsp; StackCookie
0x1800d8fe5  call    __security_check_cookie
0x1800d8fea  mov     rbx, [rsp+270h+arg_8]
0x1800d8ff2  add     rsp, 260h
0x1800d8ff9  pop     r14
0x1800d8ffb  pop     rdi
0x1800d8ffc  pop     rbp
0x1800d8ffd  retn
```
