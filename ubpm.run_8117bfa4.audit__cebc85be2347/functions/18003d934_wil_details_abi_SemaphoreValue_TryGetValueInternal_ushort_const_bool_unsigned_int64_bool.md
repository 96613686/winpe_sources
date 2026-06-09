# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18003d934`
- end: `0x18003daf7`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `451`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18003d8b0`

## callees

- `0x180023780`
- `0x180023800`
- `0x1800361e4`
- `0x180039b50`
- `0x18003bba0`
- `0x18003d174`
- `0x18003d934`
- `0x180040260`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d9b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d9b3`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18003d99d`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18003da42`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18003d99d`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18003da42`

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
  HANDLE v10; // rax
  unsigned int v11; // r8d
  const char *v12; // r9
  int v13; // eax
  int v15; // [rsp+20h] [rbp-E0h] BYREF
  int v16; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v17; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v18[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, 0x104u, L"_p0");
  v5 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v18[0] = v5;
  if ( v5 )
  {
    v16 = 0;
    v15 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &v16);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v15);
      goto LABEL_13;
    }
    StringCchCatW(Name, 0x104u, L"h");
    v10 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v17 = v10;
    if ( v10 )
    {
      v13 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v10, &v15);
      LastError = v13;
      if ( v13 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
        *a3 = v16 | (unsigned __int64)((__int64)v15 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v13,
        v15);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v11, v12);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v18);
  return LastError;
}

```

## disassembly

```asm
0x18003d934  mov     [rsp-8+arg_8], rbx
0x18003d939  push    rbp
0x18003d93a  push    rdi
0x18003d93b  push    r14
0x18003d93d  lea     rbp, [rsp-160h]
0x18003d945  sub     rsp, 260h
0x18003d94c  mov     rax, cs:__security_cookie
0x18003d953  xor     rax, rsp
0x18003d956  mov     [rbp+170h+var_20], rax
0x18003d95d  mov     rdi, r8
0x18003d960  mov     qword ptr [r8], 0
0x18003d967  mov     r8, rcx; unsigned __int16 *
0x18003d96a  mov     r14d, 104h
0x18003d970  mov     edx, r14d; unsigned __int64
0x18003d973  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18003d978  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003d97d  lea     r8, aP0; "_p0"
0x18003d984  mov     edx, r14d; unsigned __int64
0x18003d987  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18003d98c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003d991  lea     r8, [rsp+270h+Name]; lpName
0x18003d996  xor     edx, edx; bInheritHandle
0x18003d998  mov     ecx, 1F0003h; dwDesiredAccess
0x18003d99d  call    cs:__imp_OpenSemaphoreW
0x18003d9a4  nop     dword ptr [rax+rax+00h]
0x18003d9a9  mov     [rsp+270h+var_240], rax
0x18003d9ae  test    rax, rax
0x18003d9b1  jnz     short loc_18003D9DF
0x18003d9b3  call    cs:__imp_GetLastError
0x18003d9ba  nop     dword ptr [rax+rax+00h]
0x18003d9bf  cmp     eax, 2
0x18003d9c2  jz      loc_18003DAC5
0x18003d9c8  mov     rcx, [rbp+178h]; this
0x18003d9cf  lea     edx, [r14-34h]; void *
0x18003d9d3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003d9d8  mov     ebx, eax
0x18003d9da  jmp     loc_18003DAC7
0x18003d9df  lea     rdx, [rsp+270h+var_24C]; int *
0x18003d9e4  mov     [rsp+270h+var_24C], 0
0x18003d9ec  mov     rcx, rax; hHandle
0x18003d9ef  mov     [rsp+270h+var_250], 0; int
0x18003d9f7  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18003d9fc  mov     ebx, eax
0x18003d9fe  test    eax, eax
0x18003da00  jns     short loc_18003DA22
0x18003da02  mov     rcx, [rbp+178h]; this
0x18003da09  lea     r8, aWil; "wil"
0x18003da10  mov     r9d, eax; char *
0x18003da13  mov     edx, 0D6h; void *
0x18003da18  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003da1d  jmp     loc_18003DAC7
0x18003da22  lea     r8, asc_1800450F0; "h"
0x18003da29  mov     rdx, r14; unsigned __int64
0x18003da2c  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18003da31  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003da36  lea     r8, [rsp+270h+Name]; lpName
0x18003da3b  xor     edx, edx; bInheritHandle
0x18003da3d  mov     ecx, 1F0003h; dwDesiredAccess
0x18003da42  call    cs:__imp_OpenSemaphoreW
0x18003da49  nop     dword ptr [rax+rax+00h]
0x18003da4e  mov     [rsp+270h+var_248], rax
0x18003da53  test    rax, rax
0x18003da56  jnz     short loc_18003DA77
0x18003da58  mov     rcx, [rbp+178h]; this
0x18003da5f  mov     edx, 0DCh; void *
0x18003da64  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003da69  mov     ebx, eax
0x18003da6b  lea     rcx, [rsp+270h+var_248]
0x18003da70  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003da75  jmp     short loc_18003DAC7
0x18003da77  lea     rdx, [rsp+270h+var_250]; int *
0x18003da7c  mov     rcx, rax; hHandle
0x18003da7f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18003da84  mov     ebx, eax
0x18003da86  test    eax, eax
0x18003da88  jns     short loc_18003DAA7
0x18003da8a  mov     rcx, [rbp+178h]; this
0x18003da91  lea     r8, aWil; "wil"
0x18003da98  mov     r9d, eax; char *
0x18003da9b  mov     edx, 0DEh; void *
0x18003daa0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003daa5  jmp     short loc_18003DA6B
0x18003daa7  lea     rcx, [rsp+270h+var_248]
0x18003daac  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003dab1  movsxd  rcx, [rsp+270h+var_250]
0x18003dab6  movsxd  rax, [rsp+270h+var_24C]
0x18003dabb  shl     rcx, 1Fh
0x18003dabf  or      rcx, rax
0x18003dac2  mov     [rdi], rcx
0x18003dac5  xor     ebx, ebx
0x18003dac7  lea     rcx, [rsp+270h+var_240]
0x18003dacc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003dad1  mov     eax, ebx
0x18003dad3  mov     rcx, [rbp+170h+var_20]
0x18003dada  xor     rcx, rsp; StackCookie
0x18003dadd  call    __security_check_cookie
0x18003dae2  mov     rbx, [rsp+270h+arg_8]
0x18003daea  add     rsp, 260h
0x18003daf1  pop     r14
0x18003daf3  pop     rdi
0x18003daf4  pop     rbp
0x18003daf5  retn
```
