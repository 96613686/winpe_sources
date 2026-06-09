# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800056a8`
- end: `0x180005860`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180003638`

## callees

- `0x180001dc0`
- `0x1800034e4`
- `0x180004200`
- `0x180004fb4`
- `0x180004fd4`
- `0x1800054b0`
- `0x1800055a4`
- `0x1800056a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000570c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800057aa`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000570c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800057aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000571c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000571c`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        STRSAFE_PCNZWCH pszSrc,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  unsigned __int64 v5; // rdx
  wil::details *v6; // rax
  void *v7; // rdx
  const char *v8; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned __int64 v11; // rdx
  wil::details *v12; // rax
  const char *v13; // r9
  void *v14; // rdx
  int v15; // eax
  void *v16; // rdx
  size_t v18; // [rsp+20h] [rbp-E0h]
  int v19; // [rsp+30h] [rbp-D0h] BYREF
  int v20; // [rsp+34h] [rbp-CCh] BYREF
  wil::details *v21; // [rsp+38h] [rbp-C8h] BYREF
  wil::details *v22; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCopyWorkerW(pszDest, 0x104u, a3, pszSrc, v18);
  StringCchCatW(pszDest, v5, L"_p0");
  v6 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v22 = v6;
  if ( v6 )
  {
    v20 = 0;
    v19 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v20);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore);
      goto LABEL_13;
    }
    StringCchCatW(pszDest, v11, L"h");
    v12 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, pszDest);
    v21 = v12;
    if ( v12 )
    {
      v15 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v12, &v19);
      LastError = v15;
      if ( v15 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
          &v21,
          v16);
        *a3 = v20 | (unsigned __int64)((__int64)v19 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v15);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (int)"wil", v13);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v21,
      v14);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (int)"wil", v8);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v22,
    v7);
  return LastError;
}

```

## disassembly

```asm
0x1800056a8  mov     [rsp-8+arg_8], rbx
0x1800056ad  mov     [rsp-8+arg_18], rdi
0x1800056b2  push    rbp
0x1800056b3  lea     rbp, [rsp-170h]
0x1800056bb  sub     rsp, 270h
0x1800056c2  mov     rax, cs:__security_cookie
0x1800056c9  xor     rax, rsp
0x1800056cc  mov     [rbp+170h+var_10], rax
0x1800056d3  mov     r9, rcx; pszSrc
0x1800056d6  mov     qword ptr [r8], 0
0x1800056dd  lea     rcx, [rsp+270h+pszDest]; pszDest
0x1800056e2  mov     edx, 104h; cchDest
0x1800056e7  mov     rdi, r8
0x1800056ea  call    StringCopyWorkerW
0x1800056ef  lea     r8, aP0; "_p0"
0x1800056f6  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x1800056fb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005700  lea     r8, [rsp+270h+pszDest]; lpName
0x180005705  xor     edx, edx; bInheritHandle
0x180005707  mov     ecx, 1F0003h; dwDesiredAccess
0x18000570c  call    cs:__imp_OpenSemaphoreW
0x180005712  mov     [rsp+270h+var_230], rax
0x180005717  test    rax, rax
0x18000571a  jnz     short loc_18000574A
0x18000571c  call    cs:__imp_GetLastError
0x180005722  cmp     eax, 2
0x180005725  jz      loc_18000582E
0x18000572b  mov     rcx, [rbp+178h]; this
0x180005732  lea     r8, aWil; "wil"
0x180005739  mov     edx, 0D0h; void *
0x18000573e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180005743  mov     ebx, eax
0x180005745  jmp     loc_180005830
0x18000574a  lea     rdx, [rsp+270h+var_23C]; int *
0x18000574f  mov     [rsp+270h+var_23C], 0
0x180005757  mov     rcx, rax; hHandle
0x18000575a  mov     [rsp+270h+var_240], 0
0x180005762  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180005767  mov     ebx, eax
0x180005769  test    eax, eax
0x18000576b  jns     short loc_18000578D
0x18000576d  mov     rcx, [rbp+178h]; this
0x180005774  lea     r8, aWil; "wil"
0x18000577b  mov     r9d, eax; char *
0x18000577e  mov     edx, 0D6h; void *
0x180005783  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005788  jmp     loc_180005830
0x18000578d  lea     r8, asc_18000EDE0; "h"
0x180005794  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x180005799  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000579e  lea     r8, [rsp+270h+pszDest]; lpName
0x1800057a3  xor     edx, edx; bInheritHandle
0x1800057a5  mov     ecx, 1F0003h; dwDesiredAccess
0x1800057aa  call    cs:__imp_OpenSemaphoreW
0x1800057b0  mov     [rsp+270h+var_238], rax
0x1800057b5  test    rax, rax
0x1800057b8  jnz     short loc_1800057E0
0x1800057ba  mov     rcx, [rbp+178h]; this
0x1800057c1  lea     r8, aWil; "wil"
0x1800057c8  mov     edx, 0DCh; void *
0x1800057cd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800057d2  mov     ebx, eax
0x1800057d4  lea     rcx, [rsp+270h+var_238]
0x1800057d9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800057de  jmp     short loc_180005830
0x1800057e0  lea     rdx, [rsp+270h+var_240]; int *
0x1800057e5  mov     rcx, rax; hHandle
0x1800057e8  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800057ed  mov     ebx, eax
0x1800057ef  test    eax, eax
0x1800057f1  jns     short loc_180005810
0x1800057f3  mov     rcx, [rbp+178h]; this
0x1800057fa  lea     r8, aWil; "wil"
0x180005801  mov     r9d, eax; char *
0x180005804  mov     edx, 0DEh; void *
0x180005809  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000580e  jmp     short loc_1800057D4
0x180005810  lea     rcx, [rsp+270h+var_238]
0x180005815  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000581a  movsxd  rcx, [rsp+270h+var_240]
0x18000581f  movsxd  rax, [rsp+270h+var_23C]
0x180005824  shl     rcx, 1Fh
0x180005828  or      rcx, rax
0x18000582b  mov     [rdi], rcx
0x18000582e  xor     ebx, ebx
0x180005830  lea     rcx, [rsp+270h+var_230]
0x180005835  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000583a  mov     eax, ebx
0x18000583c  mov     rcx, [rbp+170h+var_10]
0x180005843  xor     rcx, rsp; StackCookie
0x180005846  call    __security_check_cookie
0x18000584b  lea     r11, [rsp+270h+var_s0]
0x180005853  mov     rbx, [r11+18h]
0x180005857  mov     rdi, [r11+28h]
0x18000585b  mov     rsp, r11
0x18000585e  pop     rbp
0x18000585f  retn
```
