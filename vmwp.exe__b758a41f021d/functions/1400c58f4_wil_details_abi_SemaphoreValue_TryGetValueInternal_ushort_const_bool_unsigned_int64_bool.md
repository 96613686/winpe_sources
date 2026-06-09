# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1400c58f4`
- end: `0x1400c5ac5`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `465`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x140124d8c`

## callees

- `0x140027fdc`
- `0x14006d540`
- `0x1400c58f4`
- `0x1400c5acc`
- `0x1400c5b58`
- `0x1400c5bf4`
- `0x14011ea40`
- `0x140122fb8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1400c595d`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1400c5a09`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1400c595d`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1400c5a09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400c5973`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400c5973`

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
0x1400c58f4  mov     [rsp-8+arg_8], rbx
0x1400c58f9  push    rbp
0x1400c58fa  push    rdi
0x1400c58fb  push    r14
0x1400c58fd  lea     rbp, [rsp-160h]
0x1400c5905  sub     rsp, 260h
0x1400c590c  mov     rax, cs:__security_cookie
0x1400c5913  xor     rax, rsp
0x1400c5916  mov     [rbp+170h+var_20], rax
0x1400c591d  mov     rdi, r8
0x1400c5920  mov     qword ptr [r8], 0
0x1400c5927  mov     r8, rcx; unsigned __int16 *
0x1400c592a  mov     r14d, 104h
0x1400c5930  mov     edx, r14d; unsigned __int64
0x1400c5933  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1400c5938  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400c593d  lea     r8, aP0; "_p0"
0x1400c5944  mov     edx, r14d; unsigned __int64
0x1400c5947  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1400c594c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400c5951  lea     r8, [rsp+270h+Name]; lpName
0x1400c5956  xor     edx, edx; bInheritHandle
0x1400c5958  mov     ecx, 1F0003h; dwDesiredAccess
0x1400c595d  call    cs:__imp_OpenSemaphoreW
0x1400c5964  nop     dword ptr [rax+rax+00h]
0x1400c5969  mov     [rsp+270h+var_240], rax
0x1400c596e  test    rax, rax
0x1400c5971  jnz     short loc_1400C59A6
0x1400c5973  call    cs:__imp_GetLastError
0x1400c597a  nop     dword ptr [rax+rax+00h]
0x1400c597f  cmp     eax, 2
0x1400c5982  jz      loc_1400C5A93
0x1400c5988  mov     rcx, [rbp+178h]; this
0x1400c598f  lea     r8, aWil; "wil"
0x1400c5996  lea     edx, [r14-34h]; void *
0x1400c599a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400c599f  mov     ebx, eax
0x1400c59a1  jmp     loc_1400C5A95
0x1400c59a6  lea     rdx, [rsp+270h+var_24C]; int *
0x1400c59ab  mov     [rsp+270h+var_24C], 0
0x1400c59b3  mov     rcx, rax; hHandle
0x1400c59b6  mov     [rsp+270h+var_250], 0; int
0x1400c59be  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1400c59c3  mov     ebx, eax
0x1400c59c5  test    eax, eax
0x1400c59c7  jns     short loc_1400C59E9
0x1400c59c9  mov     rcx, [rbp+178h]; this
0x1400c59d0  lea     r8, aWil; "wil"
0x1400c59d7  mov     r9d, eax; char *
0x1400c59da  mov     edx, 0D6h; void *
0x1400c59df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400c59e4  jmp     loc_1400C5A95
0x1400c59e9  lea     r8, asc_1402F3FD0; "h"
0x1400c59f0  mov     rdx, r14; unsigned __int64
0x1400c59f3  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1400c59f8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400c59fd  lea     r8, [rsp+270h+Name]; lpName
0x1400c5a02  xor     edx, edx; bInheritHandle
0x1400c5a04  mov     ecx, 1F0003h; dwDesiredAccess
0x1400c5a09  call    cs:__imp_OpenSemaphoreW
0x1400c5a10  nop     dword ptr [rax+rax+00h]
0x1400c5a15  mov     [rsp+270h+var_248], rax
0x1400c5a1a  test    rax, rax
0x1400c5a1d  jnz     short loc_1400C5A45
0x1400c5a1f  mov     rcx, [rbp+178h]; this
0x1400c5a26  lea     r8, aWil; "wil"
0x1400c5a2d  mov     edx, 0DCh; void *
0x1400c5a32  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400c5a37  mov     ebx, eax
0x1400c5a39  lea     rcx, [rsp+270h+var_248]
0x1400c5a3e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400c5a43  jmp     short loc_1400C5A95
0x1400c5a45  lea     rdx, [rsp+270h+var_250]; int *
0x1400c5a4a  mov     rcx, rax; hHandle
0x1400c5a4d  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1400c5a52  mov     ebx, eax
0x1400c5a54  test    eax, eax
0x1400c5a56  jns     short loc_1400C5A75
0x1400c5a58  mov     rcx, [rbp+178h]; this
0x1400c5a5f  lea     r8, aWil; "wil"
0x1400c5a66  mov     r9d, eax; char *
0x1400c5a69  mov     edx, 0DEh; void *
0x1400c5a6e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400c5a73  jmp     short loc_1400C5A39
0x1400c5a75  lea     rcx, [rsp+270h+var_248]
0x1400c5a7a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400c5a7f  movsxd  rcx, [rsp+270h+var_250]
0x1400c5a84  movsxd  rax, [rsp+270h+var_24C]
0x1400c5a89  shl     rcx, 1Fh
0x1400c5a8d  or      rcx, rax
0x1400c5a90  mov     [rdi], rcx
0x1400c5a93  xor     ebx, ebx
0x1400c5a95  lea     rcx, [rsp+270h+var_240]
0x1400c5a9a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400c5a9f  mov     eax, ebx
0x1400c5aa1  mov     rcx, [rbp+170h+var_20]
0x1400c5aa8  xor     rcx, rsp; StackCookie
0x1400c5aab  call    __security_check_cookie
0x1400c5ab0  mov     rbx, [rsp+270h+arg_8]
0x1400c5ab8  add     rsp, 260h
0x1400c5abf  pop     r14
0x1400c5ac1  pop     rdi
0x1400c5ac2  pop     rbp
0x1400c5ac3  retn
```
