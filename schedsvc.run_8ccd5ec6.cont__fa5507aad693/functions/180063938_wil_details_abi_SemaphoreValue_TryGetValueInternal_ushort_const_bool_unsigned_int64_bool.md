# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180063938`
- end: `0x180063aed`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `437`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800638c0`

## callees

- `0x180001e10`
- `0x1800301f0`
- `0x180058804`
- `0x18005f350`
- `0x180060bf0`
- `0x18006271c`
- `0x180063938`
- `0x180082a40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800639b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800639b7`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800639a1`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180063a3f`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800639a1`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180063a3f`

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
0x180063938  mov     [rsp-8+arg_8], rbx
0x18006393d  push    rbp
0x18006393e  push    rdi
0x18006393f  push    r14
0x180063941  lea     rbp, [rsp-160h]
0x180063949  sub     rsp, 260h
0x180063950  mov     rax, cs:__security_cookie
0x180063957  xor     rax, rsp
0x18006395a  mov     [rbp+170h+var_20], rax
0x180063961  mov     rdi, r8
0x180063964  mov     qword ptr [r8], 0
0x18006396b  mov     r8, rcx; unsigned __int16 *
0x18006396e  mov     r14d, 104h
0x180063974  mov     edx, r14d; unsigned __int64
0x180063977  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18006397c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180063981  lea     r8, aP0; "_p0"
0x180063988  mov     edx, r14d; unsigned __int64
0x18006398b  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180063990  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180063995  lea     r8, [rsp+270h+Name]; lpName
0x18006399a  xor     edx, edx; bInheritHandle
0x18006399c  mov     ecx, 1F0003h; dwDesiredAccess
0x1800639a1  call    cs:__imp_OpenSemaphoreW
0x1800639a8  nop     dword ptr [rax+rax+00h]
0x1800639ad  mov     [rsp+270h+var_240], rax
0x1800639b2  test    rax, rax
0x1800639b5  jnz     short loc_1800639E3
0x1800639b7  call    cs:__imp_GetLastError
0x1800639be  nop     dword ptr [rax+rax+00h]
0x1800639c3  cmp     eax, 2
0x1800639c6  jz      loc_180063ABB
0x1800639cc  mov     rcx, [rbp+178h]; this
0x1800639d3  lea     edx, [r14-34h]; void *
0x1800639d7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800639dc  mov     ebx, eax
0x1800639de  jmp     loc_180063ABD
0x1800639e3  lea     rdx, [rsp+270h+var_24C]; int *
0x1800639e8  mov     [rsp+270h+var_24C], 0
0x1800639f0  mov     rcx, rax; hHandle
0x1800639f3  mov     [rsp+270h+var_250], 0; int
0x1800639fb  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180063a00  mov     ebx, eax
0x180063a02  test    eax, eax
0x180063a04  jns     short loc_180063A1F
0x180063a06  mov     rcx, [rbp+178h]; this
0x180063a0d  mov     r9d, eax; char *
0x180063a10  mov     edx, 0D6h; void *
0x180063a15  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180063a1a  jmp     loc_180063ABD
0x180063a1f  lea     r8, asc_1800AA6C8; "h"
0x180063a26  mov     rdx, r14; unsigned __int64
0x180063a29  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180063a2e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180063a33  lea     r8, [rsp+270h+Name]; lpName
0x180063a38  xor     edx, edx; bInheritHandle
0x180063a3a  mov     ecx, 1F0003h; dwDesiredAccess
0x180063a3f  call    cs:__imp_OpenSemaphoreW
0x180063a46  nop     dword ptr [rax+rax+00h]
0x180063a4b  mov     [rsp+270h+var_248], rax
0x180063a50  test    rax, rax
0x180063a53  jnz     short loc_180063A74
0x180063a55  mov     rcx, [rbp+178h]; this
0x180063a5c  mov     edx, 0DCh; void *
0x180063a61  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180063a66  mov     ebx, eax
0x180063a68  lea     rcx, [rsp+270h+var_248]
0x180063a6d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180063a72  jmp     short loc_180063ABD
0x180063a74  lea     rdx, [rsp+270h+var_250]; int *
0x180063a79  mov     rcx, rax; hHandle
0x180063a7c  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180063a81  mov     ebx, eax
0x180063a83  test    eax, eax
0x180063a85  jns     short loc_180063A9D
0x180063a87  mov     rcx, [rbp+178h]; this
0x180063a8e  mov     r9d, eax; char *
0x180063a91  mov     edx, 0DEh; void *
0x180063a96  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180063a9b  jmp     short loc_180063A68
0x180063a9d  lea     rcx, [rsp+270h+var_248]
0x180063aa2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180063aa7  movsxd  rcx, [rsp+270h+var_250]
0x180063aac  movsxd  rax, [rsp+270h+var_24C]
0x180063ab1  shl     rcx, 1Fh
0x180063ab5  or      rcx, rax
0x180063ab8  mov     [rdi], rcx
0x180063abb  xor     ebx, ebx
0x180063abd  lea     rcx, [rsp+270h+var_240]
0x180063ac2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180063ac7  mov     eax, ebx
0x180063ac9  mov     rcx, [rbp+170h+var_20]
0x180063ad0  xor     rcx, rsp; StackCookie
0x180063ad3  call    __security_check_cookie
0x180063ad8  mov     rbx, [rsp+270h+arg_8]
0x180063ae0  add     rsp, 260h
0x180063ae7  pop     r14
0x180063ae9  pop     rdi
0x180063aea  pop     rbp
0x180063aeb  retn
```
