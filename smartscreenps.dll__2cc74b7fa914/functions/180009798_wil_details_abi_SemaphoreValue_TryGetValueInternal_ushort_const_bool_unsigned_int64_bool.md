# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180009798`
- end: `0x180009942`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `426`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180007848`

## callees

- `0x180001590`
- `0x1800076fc`
- `0x1800083ec`
- `0x180009074`
- `0x180009094`
- `0x180009570`
- `0x180009664`
- `0x180009798`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800097fc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009893`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800097fc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009893`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000980c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000980c`

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
  HANDLE v12; // rax
  unsigned int v13; // r8d
  const char *v14; // r9
  int v15; // eax
  size_t v17; // [rsp+20h] [rbp-E0h]
  int v18; // [rsp+20h] [rbp-E0h]
  int v19; // [rsp+30h] [rbp-D0h] BYREF
  int v20; // [rsp+34h] [rbp-CCh] BYREF
  HANDLE v21; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE v22[2]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCopyWorkerW(pszDest, 0x104u, a3, pszSrc, v17);
  StringCchCatW(pszDest, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v22[0] = v6;
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
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v18);
      goto LABEL_13;
    }
    StringCchCatW(pszDest, v11, L"h");
    v12 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
    v21 = v12;
    if ( v12 )
    {
      v15 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v12, &v19);
      LastError = v15;
      if ( v15 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
        *a3 = v20 | (unsigned __int64)((__int64)v19 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v15,
        v18);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v13, v14);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v22);
  return LastError;
}

```

## disassembly

```asm
0x180009798  mov     [rsp-8+arg_8], rbx
0x18000979d  mov     [rsp-8+arg_18], rdi
0x1800097a2  push    rbp
0x1800097a3  lea     rbp, [rsp-170h]
0x1800097ab  sub     rsp, 270h
0x1800097b2  mov     rax, cs:__security_cookie
0x1800097b9  xor     rax, rsp
0x1800097bc  mov     [rbp+170h+var_10], rax
0x1800097c3  mov     r9, rcx; pszSrc
0x1800097c6  mov     qword ptr [r8], 0
0x1800097cd  lea     rcx, [rsp+270h+pszDest]; pszDest
0x1800097d2  mov     edx, 104h; cchDest
0x1800097d7  mov     rdi, r8
0x1800097da  call    StringCopyWorkerW
0x1800097df  lea     r8, aP0; "_p0"
0x1800097e6  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x1800097eb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800097f0  lea     r8, [rsp+270h+pszDest]; lpName
0x1800097f5  xor     edx, edx; bInheritHandle
0x1800097f7  mov     ecx, 1F0003h; dwDesiredAccess
0x1800097fc  call    cs:__imp_OpenSemaphoreW
0x180009802  mov     [rsp+270h+var_230], rax
0x180009807  test    rax, rax
0x18000980a  jnz     short loc_180009833
0x18000980c  call    cs:__imp_GetLastError
0x180009812  cmp     eax, 2
0x180009815  jz      loc_180009910
0x18000981b  mov     rcx, [rbp+178h]; this
0x180009822  mov     edx, 0D0h; void *
0x180009827  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000982c  mov     ebx, eax
0x18000982e  jmp     loc_180009912
0x180009833  lea     rdx, [rsp+270h+var_23C]; int *
0x180009838  mov     [rsp+270h+var_23C], 0
0x180009840  mov     rcx, rax; hHandle
0x180009843  mov     [rsp+270h+var_240], 0
0x18000984b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180009850  mov     ebx, eax
0x180009852  test    eax, eax
0x180009854  jns     short loc_180009876
0x180009856  mov     rcx, [rbp+178h]; this
0x18000985d  lea     r8, aWil; "wil"
0x180009864  mov     r9d, eax; char *
0x180009867  mov     edx, 0D6h; void *
0x18000986c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009871  jmp     loc_180009912
0x180009876  lea     r8, asc_180014A48; "h"
0x18000987d  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x180009882  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009887  lea     r8, [rsp+270h+pszDest]; lpName
0x18000988c  xor     edx, edx; bInheritHandle
0x18000988e  mov     ecx, 1F0003h; dwDesiredAccess
0x180009893  call    cs:__imp_OpenSemaphoreW
0x180009899  mov     [rsp+270h+var_238], rax
0x18000989e  test    rax, rax
0x1800098a1  jnz     short loc_1800098C2
0x1800098a3  mov     rcx, [rbp+178h]; this
0x1800098aa  mov     edx, 0DCh; void *
0x1800098af  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800098b4  mov     ebx, eax
0x1800098b6  lea     rcx, [rsp+270h+var_238]
0x1800098bb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800098c0  jmp     short loc_180009912
0x1800098c2  lea     rdx, [rsp+270h+var_240]; int *
0x1800098c7  mov     rcx, rax; hHandle
0x1800098ca  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800098cf  mov     ebx, eax
0x1800098d1  test    eax, eax
0x1800098d3  jns     short loc_1800098F2
0x1800098d5  mov     rcx, [rbp+178h]; this
0x1800098dc  lea     r8, aWil; "wil"
0x1800098e3  mov     r9d, eax; char *
0x1800098e6  mov     edx, 0DEh; void *
0x1800098eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800098f0  jmp     short loc_1800098B6
0x1800098f2  lea     rcx, [rsp+270h+var_238]
0x1800098f7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800098fc  movsxd  rcx, [rsp+270h+var_240]
0x180009901  movsxd  rax, [rsp+270h+var_23C]
0x180009906  shl     rcx, 1Fh
0x18000990a  or      rcx, rax
0x18000990d  mov     [rdi], rcx
0x180009910  xor     ebx, ebx
0x180009912  lea     rcx, [rsp+270h+var_230]
0x180009917  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000991c  mov     eax, ebx
0x18000991e  mov     rcx, [rbp+170h+var_10]
0x180009925  xor     rcx, rsp; StackCookie
0x180009928  call    __security_check_cookie
0x18000992d  lea     r11, [rsp+270h+var_s0]
0x180009935  mov     rbx, [r11+18h]
0x180009939  mov     rdi, [r11+28h]
0x18000993d  mov     rsp, r11
0x180009940  pop     rbp
0x180009941  retn
```
