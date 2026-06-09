# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18003ba20`
- end: `0x18003bbbc`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18003b9ac`

## callees

- `0x180001600`
- `0x180036338`
- `0x180038d70`
- `0x18003acd8`
- `0x18003acf8`
- `0x18003ba20`
- `0x18003d2f8`
- `0x18003d440`

## import_xrefs

- `KERNEL32!OpenSemaphoreW` at `0x18003ba84`
- `KERNEL32!OpenSemaphoreW` at `0x18003bb14`
- `KERNEL32!OpenSemaphoreW` at `0x18003ba84`
- `KERNEL32!OpenSemaphoreW` at `0x18003bb14`
- `KERNEL32!GetLastError` at `0x18003ba94`
- `KERNEL32!GetLastError` at `0x18003ba94`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        STRSAFE_PCNZWCH pszSrc,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  size_t v5; // rdx
  HANDLE v6; // rax
  unsigned int v7; // r8d
  const char *v8; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  size_t v11; // rdx
  int v12; // r8d
  HANDLE v13; // rax
  unsigned int v14; // r8d
  const char *v15; // r9
  int v16; // eax
  int v17; // r8d
  size_t v19; // [rsp+20h] [rbp-E0h]
  int v20; // [rsp+30h] [rbp-D0h] BYREF
  int v21; // [rsp+34h] [rbp-CCh] BYREF
  HANDLE v22; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE v23[2]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCopyWorkerW_0(pszDest, 0x104u, a3, pszSrc, v19);
  StringCchCatW(pszDest, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v23[0] = v6;
  if ( v6 )
  {
    v21 = 0;
    v20 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v21);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v12, (const char *)(unsigned int)ValueFromSemaphore);
      goto LABEL_13;
    }
    StringCchCatW(pszDest, v11, L"h");
    v13 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
    v22 = v13;
    if ( v13 )
    {
      v16 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v13, &v20);
      LastError = v16;
      if ( v16 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v22);
        *a3 = v21 | (unsigned __int64)((__int64)v20 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v17, (const char *)(unsigned int)v16);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v14, v15);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v22);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v23);
  return LastError;
}

```

## disassembly

```asm
0x18003ba20  mov     [rsp-8+arg_8], rbx
0x18003ba25  mov     [rsp-8+arg_18], rdi
0x18003ba2a  push    rbp
0x18003ba2b  lea     rbp, [rsp-170h]
0x18003ba33  sub     rsp, 270h
0x18003ba3a  mov     rax, cs:__security_cookie
0x18003ba41  xor     rax, rsp
0x18003ba44  mov     [rbp+170h+var_10], rax
0x18003ba4b  mov     r9, rcx; pszSrc
0x18003ba4e  mov     qword ptr [r8], 0
0x18003ba55  lea     rcx, [rsp+270h+pszDest]; pszDest
0x18003ba5a  mov     edx, 104h; cchDest
0x18003ba5f  mov     rdi, r8
0x18003ba62  call    StringCopyWorkerW_0
0x18003ba67  lea     r8, aP0; "_p0"
0x18003ba6e  lea     rcx, [rsp+270h+pszDest]; pszDest
0x18003ba73  call    StringCchCatW
0x18003ba78  lea     r8, [rsp+270h+pszDest]; lpName
0x18003ba7d  xor     edx, edx; bInheritHandle
0x18003ba7f  mov     ecx, 1F0003h; dwDesiredAccess
0x18003ba84  call    cs:__imp_OpenSemaphoreW
0x18003ba8a  mov     [rsp+270h+var_230], rax
0x18003ba8f  test    rax, rax
0x18003ba92  jnz     short loc_18003BABB
0x18003ba94  call    cs:__imp_GetLastError
0x18003ba9a  cmp     eax, 2
0x18003ba9d  jz      loc_18003BB8A
0x18003baa3  mov     rcx, [rbp+178h]; this
0x18003baaa  mov     edx, 0D0h; void *
0x18003baaf  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003bab4  mov     ebx, eax
0x18003bab6  jmp     loc_18003BB8C
0x18003babb  lea     rdx, [rsp+270h+var_23C]; int *
0x18003bac0  mov     [rsp+270h+var_23C], 0
0x18003bac8  mov     rcx, rax; hHandle
0x18003bacb  mov     [rsp+270h+var_240], 0
0x18003bad3  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18003bad8  mov     ebx, eax
0x18003bada  test    eax, eax
0x18003badc  jns     short loc_18003BAF7
0x18003bade  mov     rcx, [rbp+178h]; this
0x18003bae5  mov     r9d, eax; char *
0x18003bae8  mov     edx, 0D6h; void *
0x18003baed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003baf2  jmp     loc_18003BB8C
0x18003baf7  lea     r8, asc_18004B258; "h"
0x18003bafe  lea     rcx, [rsp+270h+pszDest]; pszDest
0x18003bb03  call    StringCchCatW
0x18003bb08  lea     r8, [rsp+270h+pszDest]; lpName
0x18003bb0d  xor     edx, edx; bInheritHandle
0x18003bb0f  mov     ecx, 1F0003h; dwDesiredAccess
0x18003bb14  call    cs:__imp_OpenSemaphoreW
0x18003bb1a  mov     [rsp+270h+var_238], rax
0x18003bb1f  test    rax, rax
0x18003bb22  jnz     short loc_18003BB43
0x18003bb24  mov     rcx, [rbp+178h]; this
0x18003bb2b  mov     edx, 0DCh; void *
0x18003bb30  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003bb35  mov     ebx, eax
0x18003bb37  lea     rcx, [rsp+270h+var_238]
0x18003bb3c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003bb41  jmp     short loc_18003BB8C
0x18003bb43  lea     rdx, [rsp+270h+var_240]; int *
0x18003bb48  mov     rcx, rax; hHandle
0x18003bb4b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18003bb50  mov     ebx, eax
0x18003bb52  test    eax, eax
0x18003bb54  jns     short loc_18003BB6C
0x18003bb56  mov     rcx, [rbp+178h]; this
0x18003bb5d  mov     r9d, eax; char *
0x18003bb60  mov     edx, 0DEh; void *
0x18003bb65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003bb6a  jmp     short loc_18003BB37
0x18003bb6c  lea     rcx, [rsp+270h+var_238]
0x18003bb71  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003bb76  movsxd  rcx, [rsp+270h+var_240]
0x18003bb7b  movsxd  rax, [rsp+270h+var_23C]
0x18003bb80  shl     rcx, 1Fh
0x18003bb84  or      rcx, rax
0x18003bb87  mov     [rdi], rcx
0x18003bb8a  xor     ebx, ebx
0x18003bb8c  lea     rcx, [rsp+270h+var_230]
0x18003bb91  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003bb96  mov     eax, ebx
0x18003bb98  mov     rcx, [rbp+170h+var_10]
0x18003bb9f  xor     rcx, rsp; StackCookie
0x18003bba2  call    __security_check_cookie
0x18003bba7  lea     r11, [rsp+270h+var_s0]
0x18003bbaf  mov     rbx, [r11+18h]
0x18003bbb3  mov     rdi, [r11+28h]
0x18003bbb7  mov     rsp, r11
0x18003bbba  pop     rbp
0x18003bbbb  retn
```
