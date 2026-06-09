# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18001eeb0`
- end: `0x18001f052`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `418`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18001ee3c`

## callees

- `0x180016284`
- `0x180018f04`
- `0x18001e06c`
- `0x18001e08c`
- `0x18001eeb0`
- `0x180020b24`
- `0x180020ba4`
- `0x180077590`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ef29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ef29`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001ef19`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001efab`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001ef19`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001efab`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        STRSAFE_LPCWSTR pszSrc,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  HANDLE v5; // rax
  unsigned int v6; // r8d
  const char *v7; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  int v10; // r8d
  HANDLE v11; // rax
  unsigned int v12; // r8d
  const char *v13; // r9
  int v14; // eax
  int v15; // r8d
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v19; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v20[2]; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t pszDest[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCchCopyW(pszDest, 0x104u, pszSrc);
  StringCchCatW(pszDest, 0x104u, L"_p0");
  v5 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v20[0] = v5;
  if ( v5 )
  {
    v18 = 0;
    v17 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &v18);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v10, (const char *)(unsigned int)ValueFromSemaphore);
      goto LABEL_13;
    }
    StringCchCatW(pszDest, 0x104u, L"h");
    v11 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
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
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v15, (const char *)(unsigned int)v14);
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
0x18001eeb0  mov     [rsp-8+arg_8], rbx
0x18001eeb5  push    rbp
0x18001eeb6  push    rdi
0x18001eeb7  push    r14
0x18001eeb9  lea     rbp, [rsp-160h]
0x18001eec1  sub     rsp, 260h
0x18001eec8  mov     rax, cs:__security_cookie
0x18001eecf  xor     rax, rsp
0x18001eed2  mov     [rbp+170h+var_20], rax
0x18001eed9  mov     rdi, r8
0x18001eedc  mov     qword ptr [r8], 0
0x18001eee3  mov     r8, rcx; pszSrc
0x18001eee6  mov     r14d, 104h
0x18001eeec  mov     edx, r14d; cchDest
0x18001eeef  lea     rcx, [rsp+270h+pszDest]; pszDest
0x18001eef4  call    StringCchCopyW
0x18001eef9  lea     r8, aP0; "_p0"
0x18001ef00  mov     edx, r14d; cchDest
0x18001ef03  lea     rcx, [rsp+270h+pszDest]; pszDest
0x18001ef08  call    StringCchCatW
0x18001ef0d  lea     r8, [rsp+270h+pszDest]; lpName
0x18001ef12  xor     edx, edx; bInheritHandle
0x18001ef14  mov     ecx, 1F0003h; dwDesiredAccess
0x18001ef19  call    cs:__imp_OpenSemaphoreW
0x18001ef1f  mov     [rsp+270h+var_240], rax
0x18001ef24  test    rax, rax
0x18001ef27  jnz     short loc_18001EF4F
0x18001ef29  call    cs:__imp_GetLastError
0x18001ef2f  cmp     eax, 2
0x18001ef32  jz      loc_18001F021
0x18001ef38  mov     rcx, [rbp+178h]; this
0x18001ef3f  lea     edx, [r14-34h]; void *
0x18001ef43  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001ef48  mov     ebx, eax
0x18001ef4a  jmp     loc_18001F023
0x18001ef4f  lea     rdx, [rsp+270h+var_24C]; int *
0x18001ef54  mov     [rsp+270h+var_24C], 0
0x18001ef5c  mov     rcx, rax; hHandle
0x18001ef5f  mov     [rsp+270h+var_250], 0; int
0x18001ef67  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001ef6c  mov     ebx, eax
0x18001ef6e  test    eax, eax
0x18001ef70  jns     short loc_18001EF8B
0x18001ef72  mov     rcx, [rbp+178h]; this
0x18001ef79  mov     r9d, eax; char *
0x18001ef7c  mov     edx, 0D6h; void *
0x18001ef81  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ef86  jmp     loc_18001F023
0x18001ef8b  lea     r8, asc_180084520; "h"
0x18001ef92  mov     rdx, r14; cchDest
0x18001ef95  lea     rcx, [rsp+270h+pszDest]; pszDest
0x18001ef9a  call    StringCchCatW
0x18001ef9f  lea     r8, [rsp+270h+pszDest]; lpName
0x18001efa4  xor     edx, edx; bInheritHandle
0x18001efa6  mov     ecx, 1F0003h; dwDesiredAccess
0x18001efab  call    cs:__imp_OpenSemaphoreW
0x18001efb1  mov     [rsp+270h+var_248], rax
0x18001efb6  test    rax, rax
0x18001efb9  jnz     short loc_18001EFDA
0x18001efbb  mov     rcx, [rbp+178h]; this
0x18001efc2  mov     edx, 0DCh; void *
0x18001efc7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001efcc  mov     ebx, eax
0x18001efce  lea     rcx, [rsp+270h+var_248]
0x18001efd3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001efd8  jmp     short loc_18001F023
0x18001efda  lea     rdx, [rsp+270h+var_250]; int *
0x18001efdf  mov     rcx, rax; hHandle
0x18001efe2  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001efe7  mov     ebx, eax
0x18001efe9  test    eax, eax
0x18001efeb  jns     short loc_18001F003
0x18001efed  mov     rcx, [rbp+178h]; this
0x18001eff4  mov     r9d, eax; char *
0x18001eff7  mov     edx, 0DEh; void *
0x18001effc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f001  jmp     short loc_18001EFCE
0x18001f003  lea     rcx, [rsp+270h+var_248]
0x18001f008  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001f00d  movsxd  rcx, [rsp+270h+var_250]
0x18001f012  movsxd  rax, [rsp+270h+var_24C]
0x18001f017  shl     rcx, 1Fh
0x18001f01b  or      rcx, rax
0x18001f01e  mov     [rdi], rcx
0x18001f021  xor     ebx, ebx
0x18001f023  lea     rcx, [rsp+270h+var_240]
0x18001f028  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001f02d  mov     eax, ebx
0x18001f02f  mov     rcx, [rbp+170h+var_20]
0x18001f036  xor     rcx, rsp; StackCookie
0x18001f039  call    __security_check_cookie
0x18001f03e  mov     rbx, [rsp+270h+arg_8]
0x18001f046  add     rsp, 260h
0x18001f04d  pop     r14
0x18001f04f  pop     rdi
0x18001f050  pop     rbp
0x18001f051  retn
```
