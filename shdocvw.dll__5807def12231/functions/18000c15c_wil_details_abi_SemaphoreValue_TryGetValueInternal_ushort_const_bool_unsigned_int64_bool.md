# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000c15c`
- end: `0x18000c31a`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `446`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000c0d8`

## callees

- `0x180008320`
- `0x18000a240`
- `0x18000ae20`
- `0x18000b904`
- `0x18000b924`
- `0x18000be40`
- `0x18000bf34`
- `0x18000c15c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000c1c5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000c265`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000c1c5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000c265`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c1d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c1d5`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  HANDLE v5; // rax
  const char *v6; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  HANDLE v9; // rax
  const char *v10; // r9
  int v11; // eax
  int v13; // [rsp+20h] [rbp-E0h] BYREF
  int v14; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v15; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v16[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, 0x104u, L"_p0");
  v5 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v16[0] = v5;
  if ( v5 )
  {
    v14 = 0;
    v13 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &v14);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v13);
      goto LABEL_13;
    }
    StringCchCatW(Name, 0x104u, L"h");
    v9 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v15 = v9;
    if ( v9 )
    {
      v11 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, &v13);
      LastError = v11;
      if ( v11 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v15);
        *a3 = v14 | (unsigned __int64)((__int64)v13 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v11,
        v13);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v10);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v15);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v6);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v16);
  return LastError;
}

```

## disassembly

```asm
0x18000c15c  mov     [rsp-8+arg_8], rbx
0x18000c161  push    rbp
0x18000c162  push    rdi
0x18000c163  push    r14
0x18000c165  lea     rbp, [rsp-160h]
0x18000c16d  sub     rsp, 260h
0x18000c174  mov     rax, cs:__security_cookie
0x18000c17b  xor     rax, rsp
0x18000c17e  mov     [rbp+170h+var_20], rax
0x18000c185  mov     rdi, r8
0x18000c188  mov     qword ptr [r8], 0
0x18000c18f  mov     r8, rcx; unsigned __int16 *
0x18000c192  mov     r14d, 104h
0x18000c198  mov     edx, r14d; unsigned __int64
0x18000c19b  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000c1a0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000c1a5  lea     r8, aP0; "_p0"
0x18000c1ac  mov     edx, r14d; unsigned __int64
0x18000c1af  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000c1b4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000c1b9  lea     r8, [rsp+270h+Name]; lpName
0x18000c1be  xor     edx, edx; bInheritHandle
0x18000c1c0  mov     ecx, 1F0003h; dwDesiredAccess
0x18000c1c5  call    cs:__imp_OpenSemaphoreW
0x18000c1cb  mov     [rsp+270h+var_240], rax
0x18000c1d0  test    rax, rax
0x18000c1d3  jnz     short loc_18000C202
0x18000c1d5  call    cs:__imp_GetLastError
0x18000c1db  cmp     eax, 2
0x18000c1de  jz      loc_18000C2E9
0x18000c1e4  mov     rcx, [rbp+178h]; this
0x18000c1eb  lea     r8, aWil; "wil"
0x18000c1f2  lea     edx, [r14-34h]; void *
0x18000c1f6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000c1fb  mov     ebx, eax
0x18000c1fd  jmp     loc_18000C2EB
0x18000c202  lea     rdx, [rsp+270h+var_24C]; int *
0x18000c207  mov     [rsp+270h+var_24C], 0
0x18000c20f  mov     rcx, rax; hHandle
0x18000c212  mov     [rsp+270h+var_250], 0; int
0x18000c21a  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000c21f  mov     ebx, eax
0x18000c221  test    eax, eax
0x18000c223  jns     short loc_18000C245
0x18000c225  mov     rcx, [rbp+178h]; this
0x18000c22c  lea     r8, aWil; "wil"
0x18000c233  mov     r9d, eax; char *
0x18000c236  mov     edx, 0D6h; void *
0x18000c23b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c240  jmp     loc_18000C2EB
0x18000c245  lea     r8, asc_18002C6E0; "h"
0x18000c24c  mov     rdx, r14; unsigned __int64
0x18000c24f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000c254  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000c259  lea     r8, [rsp+270h+Name]; lpName
0x18000c25e  xor     edx, edx; bInheritHandle
0x18000c260  mov     ecx, 1F0003h; dwDesiredAccess
0x18000c265  call    cs:__imp_OpenSemaphoreW
0x18000c26b  mov     [rsp+270h+var_248], rax
0x18000c270  test    rax, rax
0x18000c273  jnz     short loc_18000C29B
0x18000c275  mov     rcx, [rbp+178h]; this
0x18000c27c  lea     r8, aWil; "wil"
0x18000c283  mov     edx, 0DCh; void *
0x18000c288  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000c28d  mov     ebx, eax
0x18000c28f  lea     rcx, [rsp+270h+var_248]
0x18000c294  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000c299  jmp     short loc_18000C2EB
0x18000c29b  lea     rdx, [rsp+270h+var_250]; int *
0x18000c2a0  mov     rcx, rax; hHandle
0x18000c2a3  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000c2a8  mov     ebx, eax
0x18000c2aa  test    eax, eax
0x18000c2ac  jns     short loc_18000C2CB
0x18000c2ae  mov     rcx, [rbp+178h]; this
0x18000c2b5  lea     r8, aWil; "wil"
0x18000c2bc  mov     r9d, eax; char *
0x18000c2bf  mov     edx, 0DEh; void *
0x18000c2c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c2c9  jmp     short loc_18000C28F
0x18000c2cb  lea     rcx, [rsp+270h+var_248]
0x18000c2d0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000c2d5  movsxd  rcx, [rsp+270h+var_250]
0x18000c2da  movsxd  rax, [rsp+270h+var_24C]
0x18000c2df  shl     rcx, 1Fh
0x18000c2e3  or      rcx, rax
0x18000c2e6  mov     [rdi], rcx
0x18000c2e9  xor     ebx, ebx
0x18000c2eb  lea     rcx, [rsp+270h+var_240]
0x18000c2f0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000c2f5  mov     eax, ebx
0x18000c2f7  mov     rcx, [rbp+170h+var_20]
0x18000c2fe  xor     rcx, rsp; StackCookie
0x18000c301  call    __security_check_cookie
0x18000c306  mov     rbx, [rsp+270h+arg_8]
0x18000c30e  add     rsp, 260h
0x18000c315  pop     r14
0x18000c317  pop     rdi
0x18000c318  pop     rbp
0x18000c319  retn
```
