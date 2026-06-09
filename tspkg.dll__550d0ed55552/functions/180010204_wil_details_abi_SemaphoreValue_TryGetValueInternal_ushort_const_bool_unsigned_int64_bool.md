# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180010204`
- end: `0x1800103a0`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180010190`

## callees

- `0x18000a9b4`
- `0x18000b550`
- `0x18000d554`
- `0x18000e73c`
- `0x18000f9e0`
- `0x18000fe80`
- `0x18000ff60`
- `0x180010204`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180010268`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800102f8`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180010268`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800102f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010278`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010278`

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
0x180010204  mov     [rsp-8+arg_8], rbx
0x180010209  mov     [rsp-8+arg_18], rdi
0x18001020e  push    rbp
0x18001020f  lea     rbp, [rsp-170h]
0x180010217  sub     rsp, 270h
0x18001021e  mov     rax, cs:__security_cookie
0x180010225  xor     rax, rsp
0x180010228  mov     [rbp+170h+var_10], rax
0x18001022f  mov     r9, rcx; pszSrc
0x180010232  mov     qword ptr [r8], 0
0x180010239  lea     rcx, [rsp+270h+pszDest]; pszDest
0x18001023e  mov     edx, 104h; cchDest
0x180010243  mov     rdi, r8
0x180010246  call    StringCopyWorkerW
0x18001024b  lea     r8, aP0; "_p0"
0x180010252  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x180010257  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001025c  lea     r8, [rsp+270h+pszDest]; lpName
0x180010261  xor     edx, edx; bInheritHandle
0x180010263  mov     ecx, 1F0003h; dwDesiredAccess
0x180010268  call    cs:__imp_OpenSemaphoreW
0x18001026e  mov     [rsp+270h+var_230], rax
0x180010273  test    rax, rax
0x180010276  jnz     short loc_18001029F
0x180010278  call    cs:__imp_GetLastError
0x18001027e  cmp     eax, 2
0x180010281  jz      loc_18001036E
0x180010287  mov     rcx, [rbp+178h]; this
0x18001028e  mov     edx, 0D0h; void *
0x180010293  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180010298  mov     ebx, eax
0x18001029a  jmp     loc_180010370
0x18001029f  lea     rdx, [rsp+270h+var_23C]; int *
0x1800102a4  mov     [rsp+270h+var_23C], 0
0x1800102ac  mov     rcx, rax; hHandle
0x1800102af  mov     [rsp+270h+var_240], 0
0x1800102b7  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800102bc  mov     ebx, eax
0x1800102be  test    eax, eax
0x1800102c0  jns     short loc_1800102DB
0x1800102c2  mov     rcx, [rbp+178h]; this
0x1800102c9  mov     r9d, eax; char *
0x1800102cc  mov     edx, 0D6h; void *
0x1800102d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800102d6  jmp     loc_180010370
0x1800102db  lea     r8, asc_18001FB20; "h"
0x1800102e2  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x1800102e7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800102ec  lea     r8, [rsp+270h+pszDest]; lpName
0x1800102f1  xor     edx, edx; bInheritHandle
0x1800102f3  mov     ecx, 1F0003h; dwDesiredAccess
0x1800102f8  call    cs:__imp_OpenSemaphoreW
0x1800102fe  mov     [rsp+270h+var_238], rax
0x180010303  test    rax, rax
0x180010306  jnz     short loc_180010327
0x180010308  mov     rcx, [rbp+178h]; this
0x18001030f  mov     edx, 0DCh; void *
0x180010314  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180010319  mov     ebx, eax
0x18001031b  lea     rcx, [rsp+270h+var_238]
0x180010320  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180010325  jmp     short loc_180010370
0x180010327  lea     rdx, [rsp+270h+var_240]; int *
0x18001032c  mov     rcx, rax; hHandle
0x18001032f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180010334  mov     ebx, eax
0x180010336  test    eax, eax
0x180010338  jns     short loc_180010350
0x18001033a  mov     rcx, [rbp+178h]; this
0x180010341  mov     r9d, eax; char *
0x180010344  mov     edx, 0DEh; void *
0x180010349  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001034e  jmp     short loc_18001031B
0x180010350  lea     rcx, [rsp+270h+var_238]
0x180010355  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001035a  movsxd  rcx, [rsp+270h+var_240]
0x18001035f  movsxd  rax, [rsp+270h+var_23C]
0x180010364  shl     rcx, 1Fh
0x180010368  or      rcx, rax
0x18001036b  mov     [rdi], rcx
0x18001036e  xor     ebx, ebx
0x180010370  lea     rcx, [rsp+270h+var_230]
0x180010375  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001037a  mov     eax, ebx
0x18001037c  mov     rcx, [rbp+170h+var_10]
0x180010383  xor     rcx, rsp; StackCookie
0x180010386  call    __security_check_cookie
0x18001038b  lea     r11, [rsp+270h+var_s0]
0x180010393  mov     rbx, [r11+18h]
0x180010397  mov     rdi, [r11+28h]
0x18001039b  mov     rsp, r11
0x18001039e  pop     rbp
0x18001039f  retn
```
