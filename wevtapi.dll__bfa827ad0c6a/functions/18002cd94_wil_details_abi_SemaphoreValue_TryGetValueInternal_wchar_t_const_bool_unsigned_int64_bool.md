# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x18002cd94`
- end: `0x18002cf30`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18002cd20`

## callees

- `0x180024a50`
- `0x180029c48`
- `0x18002aeb8`
- `0x18002c3ec`
- `0x18002c40c`
- `0x18002c8ac`
- `0x18002c98c`
- `0x18002cd94`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002cdf8`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002ce88`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002cdf8`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002ce88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ce08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ce08`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        STRSAFE_PCNZWCH pszSrc,
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
  size_t v19; // [rsp+20h] [rbp-E0h]
  int v20; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+30h] [rbp-D0h] BYREF
  int v22; // [rsp+34h] [rbp-CCh] BYREF
  HANDLE v23; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE v24[2]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCopyWorkerW(pszDest, 0x104u, a3, pszSrc, v19);
  StringCchCatW(pszDest, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v24[0] = v6;
  if ( v6 )
  {
    v22 = 0;
    v21 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v22);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v12, (const char *)(unsigned int)ValueFromSemaphore, v20);
      goto LABEL_13;
    }
    StringCchCatW(pszDest, v11, L"h");
    v13 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
    v23 = v13;
    if ( v13 )
    {
      v16 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v13, &v21);
      LastError = v16;
      if ( v16 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
        *a3 = v22 | (unsigned __int64)((__int64)v21 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v17, (const char *)(unsigned int)v16, v20);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v14, v15);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v24);
  return LastError;
}

```

## disassembly

```asm
0x18002cd94  mov     [rsp-8+arg_8], rbx
0x18002cd99  mov     [rsp-8+arg_18], rdi
0x18002cd9e  push    rbp
0x18002cd9f  lea     rbp, [rsp-170h]
0x18002cda7  sub     rsp, 270h
0x18002cdae  mov     rax, cs:__security_cookie
0x18002cdb5  xor     rax, rsp
0x18002cdb8  mov     [rbp+170h+var_10], rax
0x18002cdbf  mov     r9, rcx; pszSrc
0x18002cdc2  mov     qword ptr [r8], 0
0x18002cdc9  lea     rcx, [rsp+270h+pszDest]; pszDest
0x18002cdce  mov     edx, 104h; cchDest
0x18002cdd3  mov     rdi, r8
0x18002cdd6  call    StringCopyWorkerW
0x18002cddb  lea     r8, aP0; "_p0"
0x18002cde2  lea     rcx, [rsp+270h+pszDest]; wchar_t *
0x18002cde7  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18002cdec  lea     r8, [rsp+270h+pszDest]; lpName
0x18002cdf1  xor     edx, edx; bInheritHandle
0x18002cdf3  mov     ecx, 1F0003h; dwDesiredAccess
0x18002cdf8  call    cs:__imp_OpenSemaphoreW
0x18002cdfe  mov     [rsp+270h+var_230], rax
0x18002ce03  test    rax, rax
0x18002ce06  jnz     short loc_18002CE2F
0x18002ce08  call    cs:__imp_GetLastError
0x18002ce0e  cmp     eax, 2
0x18002ce11  jz      loc_18002CEFE
0x18002ce17  mov     rcx, [rbp+178h]; this
0x18002ce1e  mov     edx, 0D0h; void *
0x18002ce23  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002ce28  mov     ebx, eax
0x18002ce2a  jmp     loc_18002CF00
0x18002ce2f  lea     rdx, [rsp+270h+var_23C]; int *
0x18002ce34  mov     [rsp+270h+var_23C], 0
0x18002ce3c  mov     rcx, rax; hHandle
0x18002ce3f  mov     [rsp+270h+var_240], 0
0x18002ce47  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18002ce4c  mov     ebx, eax
0x18002ce4e  test    eax, eax
0x18002ce50  jns     short loc_18002CE6B
0x18002ce52  mov     rcx, [rbp+178h]; this
0x18002ce59  mov     r9d, eax; char *
0x18002ce5c  mov     edx, 0D6h; void *
0x18002ce61  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ce66  jmp     loc_18002CF00
0x18002ce6b  lea     r8, asc_1800418F0; "h"
0x18002ce72  lea     rcx, [rsp+270h+pszDest]; wchar_t *
0x18002ce77  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18002ce7c  lea     r8, [rsp+270h+pszDest]; lpName
0x18002ce81  xor     edx, edx; bInheritHandle
0x18002ce83  mov     ecx, 1F0003h; dwDesiredAccess
0x18002ce88  call    cs:__imp_OpenSemaphoreW
0x18002ce8e  mov     [rsp+270h+var_238], rax
0x18002ce93  test    rax, rax
0x18002ce96  jnz     short loc_18002CEB7
0x18002ce98  mov     rcx, [rbp+178h]; this
0x18002ce9f  mov     edx, 0DCh; void *
0x18002cea4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002cea9  mov     ebx, eax
0x18002ceab  lea     rcx, [rsp+270h+var_238]
0x18002ceb0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002ceb5  jmp     short loc_18002CF00
0x18002ceb7  lea     rdx, [rsp+270h+var_240]; int *
0x18002cebc  mov     rcx, rax; hHandle
0x18002cebf  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18002cec4  mov     ebx, eax
0x18002cec6  test    eax, eax
0x18002cec8  jns     short loc_18002CEE0
0x18002ceca  mov     rcx, [rbp+178h]; this
0x18002ced1  mov     r9d, eax; char *
0x18002ced4  mov     edx, 0DEh; void *
0x18002ced9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cede  jmp     short loc_18002CEAB
0x18002cee0  lea     rcx, [rsp+270h+var_238]
0x18002cee5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002ceea  movsxd  rcx, [rsp+270h+var_240]
0x18002ceef  movsxd  rax, [rsp+270h+var_23C]
0x18002cef4  shl     rcx, 1Fh
0x18002cef8  or      rcx, rax
0x18002cefb  mov     [rdi], rcx
0x18002cefe  xor     ebx, ebx
0x18002cf00  lea     rcx, [rsp+270h+var_230]
0x18002cf05  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002cf0a  mov     eax, ebx
0x18002cf0c  mov     rcx, [rbp+170h+var_10]
0x18002cf13  xor     rcx, rsp; StackCookie
0x18002cf16  call    __security_check_cookie
0x18002cf1b  lea     r11, [rsp+270h+var_s0]
0x18002cf23  mov     rbx, [r11+18h]
0x18002cf27  mov     rdi, [r11+28h]
0x18002cf2b  mov     rsp, r11
0x18002cf2e  pop     rbp
0x18002cf2f  retn
```
