# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180005878`
- end: `0x180005a14`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800038c8`

## callees

- `0x180001ec0`
- `0x180003778`
- `0x1800044ac`
- `0x180005194`
- `0x1800051b4`
- `0x18000568c`
- `0x18000576c`
- `0x180005878`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800058dc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000596c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800058dc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000596c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800058ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800058ec`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180005878  mov     [rsp-8+arg_8], rbx
0x18000587d  mov     [rsp-8+arg_18], rdi
0x180005882  push    rbp
0x180005883  lea     rbp, [rsp-170h]
0x18000588b  sub     rsp, 270h
0x180005892  mov     rax, cs:__security_cookie
0x180005899  xor     rax, rsp
0x18000589c  mov     [rbp+170h+var_10], rax
0x1800058a3  mov     r9, rcx; pszSrc
0x1800058a6  mov     qword ptr [r8], 0
0x1800058ad  lea     rcx, [rsp+270h+pszDest]; pszDest
0x1800058b2  mov     edx, 104h; cchDest
0x1800058b7  mov     rdi, r8
0x1800058ba  call    StringCopyWorkerW
0x1800058bf  lea     r8, aP0; "_p0"
0x1800058c6  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x1800058cb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800058d0  lea     r8, [rsp+270h+pszDest]; lpName
0x1800058d5  xor     edx, edx; bInheritHandle
0x1800058d7  mov     ecx, 1F0003h; dwDesiredAccess
0x1800058dc  call    cs:__imp_OpenSemaphoreW
0x1800058e2  mov     [rsp+270h+var_230], rax
0x1800058e7  test    rax, rax
0x1800058ea  jnz     short loc_180005913
0x1800058ec  call    cs:__imp_GetLastError
0x1800058f2  cmp     eax, 2
0x1800058f5  jz      loc_1800059E2
0x1800058fb  mov     rcx, [rbp+178h]; this
0x180005902  mov     edx, 0D0h; void *
0x180005907  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000590c  mov     ebx, eax
0x18000590e  jmp     loc_1800059E4
0x180005913  lea     rdx, [rsp+270h+var_23C]; int *
0x180005918  mov     [rsp+270h+var_23C], 0
0x180005920  mov     rcx, rax; hHandle
0x180005923  mov     [rsp+270h+var_240], 0
0x18000592b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180005930  mov     ebx, eax
0x180005932  test    eax, eax
0x180005934  jns     short loc_18000594F
0x180005936  mov     rcx, [rbp+178h]; this
0x18000593d  mov     r9d, eax; char *
0x180005940  mov     edx, 0D6h; void *
0x180005945  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000594a  jmp     loc_1800059E4
0x18000594f  lea     r8, asc_180039F60; "h"
0x180005956  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x18000595b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005960  lea     r8, [rsp+270h+pszDest]; lpName
0x180005965  xor     edx, edx; bInheritHandle
0x180005967  mov     ecx, 1F0003h; dwDesiredAccess
0x18000596c  call    cs:__imp_OpenSemaphoreW
0x180005972  mov     [rsp+270h+var_238], rax
0x180005977  test    rax, rax
0x18000597a  jnz     short loc_18000599B
0x18000597c  mov     rcx, [rbp+178h]; this
0x180005983  mov     edx, 0DCh; void *
0x180005988  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000598d  mov     ebx, eax
0x18000598f  lea     rcx, [rsp+270h+var_238]
0x180005994  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005999  jmp     short loc_1800059E4
0x18000599b  lea     rdx, [rsp+270h+var_240]; int *
0x1800059a0  mov     rcx, rax; hHandle
0x1800059a3  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800059a8  mov     ebx, eax
0x1800059aa  test    eax, eax
0x1800059ac  jns     short loc_1800059C4
0x1800059ae  mov     rcx, [rbp+178h]; this
0x1800059b5  mov     r9d, eax; char *
0x1800059b8  mov     edx, 0DEh; void *
0x1800059bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800059c2  jmp     short loc_18000598F
0x1800059c4  lea     rcx, [rsp+270h+var_238]
0x1800059c9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800059ce  movsxd  rcx, [rsp+270h+var_240]
0x1800059d3  movsxd  rax, [rsp+270h+var_23C]
0x1800059d8  shl     rcx, 1Fh
0x1800059dc  or      rcx, rax
0x1800059df  mov     [rdi], rcx
0x1800059e2  xor     ebx, ebx
0x1800059e4  lea     rcx, [rsp+270h+var_230]
0x1800059e9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800059ee  mov     eax, ebx
0x1800059f0  mov     rcx, [rbp+170h+var_10]
0x1800059f7  xor     rcx, rsp; StackCookie
0x1800059fa  call    __security_check_cookie
0x1800059ff  lea     r11, [rsp+270h+var_s0]
0x180005a07  mov     rbx, [r11+18h]
0x180005a0b  mov     rdi, [r11+28h]
0x180005a0f  mov     rsp, r11
0x180005a12  pop     rbp
0x180005a13  retn
```
