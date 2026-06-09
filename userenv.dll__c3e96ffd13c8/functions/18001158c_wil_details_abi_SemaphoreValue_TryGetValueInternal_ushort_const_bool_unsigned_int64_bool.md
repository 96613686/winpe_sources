# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18001158c`
- end: `0x18001174a`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `446`
- prototype: `__int64 __fastcall(const unsigned __int16 *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180011508`

## callees

- `0x1800080b4`
- `0x18000cea0`
- `0x18000cf1c`
- `0x18000cfc4`
- `0x18000d9b0`
- `0x180010658`
- `0x180010b90`
- `0x18001158c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800115f5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180011695`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800115f5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180011695`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011605`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011605`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  wil::details *v5; // rax
  void *v6; // rdx
  const char *v7; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  wil::details *v10; // rax
  const char *v11; // r9
  void *v12; // rdx
  int v13; // eax
  void *v14; // rdx
  int v16; // [rsp+20h] [rbp-E0h] BYREF
  int v17; // [rsp+24h] [rbp-DCh] BYREF
  wil::details *v18; // [rsp+28h] [rbp-D8h] BYREF
  wil::details *v19; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, 0x104u, L"_p0");
  v5 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v19 = v5;
  if ( v5 )
  {
    v17 = 0;
    v16 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &v17);
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
    StringCchCatW(Name, 0x104u, L"h");
    v10 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
    v18 = v10;
    if ( v10 )
    {
      v13 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v10, &v16);
      LastError = v13;
      if ( v13 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
          &v18,
          v14);
        *a3 = v17 | (unsigned __int64)((__int64)v16 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v13);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (int)"wil", v11);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v18,
      v12);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (int)"wil", v7);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v19,
    v6);
  return LastError;
}

```

## disassembly

```asm
0x18001158c  mov     [rsp-8+arg_8], rbx
0x180011591  push    rbp
0x180011592  push    rdi
0x180011593  push    r14
0x180011595  lea     rbp, [rsp-160h]
0x18001159d  sub     rsp, 260h
0x1800115a4  mov     rax, cs:__security_cookie
0x1800115ab  xor     rax, rsp
0x1800115ae  mov     [rbp+170h+var_20], rax
0x1800115b5  mov     rdi, r8
0x1800115b8  mov     qword ptr [r8], 0
0x1800115bf  mov     r8, rcx; unsigned __int16 *
0x1800115c2  mov     r14d, 104h
0x1800115c8  mov     edx, r14d; unsigned __int64
0x1800115cb  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800115d0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800115d5  lea     r8, aP0; "_p0"
0x1800115dc  mov     edx, r14d; unsigned __int64
0x1800115df  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800115e4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800115e9  lea     r8, [rsp+270h+Name]; lpName
0x1800115ee  xor     edx, edx; bInheritHandle
0x1800115f0  mov     ecx, 1F0003h; dwDesiredAccess
0x1800115f5  call    cs:__imp_OpenSemaphoreW
0x1800115fb  mov     [rsp+270h+var_240], rax
0x180011600  test    rax, rax
0x180011603  jnz     short loc_180011632
0x180011605  call    cs:__imp_GetLastError
0x18001160b  cmp     eax, 2
0x18001160e  jz      loc_180011719
0x180011614  mov     rcx, [rbp+178h]; this
0x18001161b  lea     r8, aWil; "wil"
0x180011622  lea     edx, [r14-34h]; void *
0x180011626  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001162b  mov     ebx, eax
0x18001162d  jmp     loc_18001171B
0x180011632  lea     rdx, [rsp+270h+var_24C]; int *
0x180011637  mov     [rsp+270h+var_24C], 0
0x18001163f  mov     rcx, rax; hHandle
0x180011642  mov     [rsp+270h+var_250], 0; int
0x18001164a  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001164f  mov     ebx, eax
0x180011651  test    eax, eax
0x180011653  jns     short loc_180011675
0x180011655  mov     rcx, [rbp+178h]; this
0x18001165c  lea     r8, aWil; "wil"
0x180011663  mov     r9d, eax; char *
0x180011666  mov     edx, 0D6h; void *
0x18001166b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011670  jmp     loc_18001171B
0x180011675  lea     r8, asc_18001F2E8; "h"
0x18001167c  mov     rdx, r14; unsigned __int64
0x18001167f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180011684  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180011689  lea     r8, [rsp+270h+Name]; lpName
0x18001168e  xor     edx, edx; bInheritHandle
0x180011690  mov     ecx, 1F0003h; dwDesiredAccess
0x180011695  call    cs:__imp_OpenSemaphoreW
0x18001169b  mov     [rsp+270h+var_248], rax
0x1800116a0  test    rax, rax
0x1800116a3  jnz     short loc_1800116CB
0x1800116a5  mov     rcx, [rbp+178h]; this
0x1800116ac  lea     r8, aWil; "wil"
0x1800116b3  mov     edx, 0DCh; void *
0x1800116b8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800116bd  mov     ebx, eax
0x1800116bf  lea     rcx, [rsp+270h+var_248]
0x1800116c4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800116c9  jmp     short loc_18001171B
0x1800116cb  lea     rdx, [rsp+270h+var_250]; int *
0x1800116d0  mov     rcx, rax; hHandle
0x1800116d3  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800116d8  mov     ebx, eax
0x1800116da  test    eax, eax
0x1800116dc  jns     short loc_1800116FB
0x1800116de  mov     rcx, [rbp+178h]; this
0x1800116e5  lea     r8, aWil; "wil"
0x1800116ec  mov     r9d, eax; char *
0x1800116ef  mov     edx, 0DEh; void *
0x1800116f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800116f9  jmp     short loc_1800116BF
0x1800116fb  lea     rcx, [rsp+270h+var_248]
0x180011700  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180011705  movsxd  rcx, [rsp+270h+var_250]
0x18001170a  movsxd  rax, [rsp+270h+var_24C]
0x18001170f  shl     rcx, 1Fh
0x180011713  or      rcx, rax
0x180011716  mov     [rdi], rcx
0x180011719  xor     ebx, ebx
0x18001171b  lea     rcx, [rsp+270h+var_240]
0x180011720  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180011725  mov     eax, ebx
0x180011727  mov     rcx, [rbp+170h+var_20]
0x18001172e  xor     rcx, rsp; StackCookie
0x180011731  call    __security_check_cookie
0x180011736  mov     rbx, [rsp+270h+arg_8]
0x18001173e  add     rsp, 260h
0x180011745  pop     r14
0x180011747  pop     rdi
0x180011748  pop     rbp
0x180011749  retn
```
