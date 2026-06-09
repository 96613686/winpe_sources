# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180009f7c`
- end: `0x18000a118`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(size_t *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180009f08`

## callees

- `0x180006a08`
- `0x180008730`
- `0x18000924c`
- `0x180009b00`
- `0x180009b20`
- `0x180009e24`
- `0x180009f7c`
- `0x18000fa00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009fe0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000a070`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009fe0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000a070`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009ff0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009ff0`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        size_t *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  unsigned __int64 v5; // rdx
  wil::details *v6; // rax
  void *v7; // rdx
  unsigned int v8; // r8d
  const char *v9; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned __int64 v12; // rdx
  int v13; // r8d
  wil::details *v14; // rax
  unsigned int v15; // r8d
  const char *v16; // r9
  void *v17; // rdx
  int v18; // eax
  void *v19; // rdx
  int v20; // r8d
  int v22; // [rsp+20h] [rbp-E0h] BYREF
  int v23; // [rsp+24h] [rbp-DCh] BYREF
  wil::details *v24; // [rsp+28h] [rbp-D8h] BYREF
  wil::details *v25; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, v5, L"_p0");
  v6 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v25 = v6;
  if ( v6 )
  {
    v23 = 0;
    v22 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v23);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v13, (const char *)(unsigned int)ValueFromSemaphore);
      goto LABEL_13;
    }
    StringCchCatW(Name, v12, L"h");
    v14 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
    v24 = v14;
    if ( v14 )
    {
      v18 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v14, &v22);
      LastError = v18;
      if ( v18 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
          &v24,
          v19);
        *a3 = v23 | (unsigned __int64)((__int64)v22 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v20, (const char *)(unsigned int)v18);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v15, v16);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v24,
      v17);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v8, v9);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v25,
    v7);
  return LastError;
}

```

## disassembly

```asm
0x180009f7c  mov     [rsp-8+arg_8], rbx
0x180009f81  mov     [rsp-8+arg_18], rdi
0x180009f86  push    rbp
0x180009f87  lea     rbp, [rsp-160h]
0x180009f8f  sub     rsp, 260h
0x180009f96  mov     rax, cs:__security_cookie
0x180009f9d  xor     rax, rsp
0x180009fa0  mov     [rbp+160h+var_10], rax
0x180009fa7  mov     rdi, r8
0x180009faa  mov     qword ptr [r8], 0
0x180009fb1  mov     r8, rcx; unsigned __int16 *
0x180009fb4  mov     edx, 104h; unsigned __int64
0x180009fb9  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180009fbe  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180009fc3  lea     r8, aP0; "_p0"
0x180009fca  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180009fcf  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009fd4  lea     r8, [rsp+260h+Name]; lpName
0x180009fd9  xor     edx, edx; bInheritHandle
0x180009fdb  mov     ecx, 1F0003h; dwDesiredAccess
0x180009fe0  call    cs:__imp_OpenSemaphoreW
0x180009fe6  mov     [rsp+260h+var_230], rax
0x180009feb  test    rax, rax
0x180009fee  jnz     short loc_18000A017
0x180009ff0  call    cs:__imp_GetLastError
0x180009ff6  cmp     eax, 2
0x180009ff9  jz      loc_18000A0E6
0x180009fff  mov     rcx, [rbp+168h]; this
0x18000a006  mov     edx, 0D0h; void *
0x18000a00b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000a010  mov     ebx, eax
0x18000a012  jmp     loc_18000A0E8
0x18000a017  lea     rdx, [rsp+260h+var_23C]; int *
0x18000a01c  mov     [rsp+260h+var_23C], 0
0x18000a024  mov     rcx, rax; hHandle
0x18000a027  mov     [rsp+260h+var_240], 0; int
0x18000a02f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000a034  mov     ebx, eax
0x18000a036  test    eax, eax
0x18000a038  jns     short loc_18000A053
0x18000a03a  mov     rcx, [rbp+168h]; this
0x18000a041  mov     r9d, eax; char *
0x18000a044  mov     edx, 0D6h; void *
0x18000a049  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a04e  jmp     loc_18000A0E8
0x18000a053  lea     r8, asc_1800121D8; "h"
0x18000a05a  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000a05f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a064  lea     r8, [rsp+260h+Name]; lpName
0x18000a069  xor     edx, edx; bInheritHandle
0x18000a06b  mov     ecx, 1F0003h; dwDesiredAccess
0x18000a070  call    cs:__imp_OpenSemaphoreW
0x18000a076  mov     [rsp+260h+var_238], rax
0x18000a07b  test    rax, rax
0x18000a07e  jnz     short loc_18000A09F
0x18000a080  mov     rcx, [rbp+168h]; this
0x18000a087  mov     edx, 0DCh; void *
0x18000a08c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000a091  mov     ebx, eax
0x18000a093  lea     rcx, [rsp+260h+var_238]
0x18000a098  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a09d  jmp     short loc_18000A0E8
0x18000a09f  lea     rdx, [rsp+260h+var_240]; int *
0x18000a0a4  mov     rcx, rax; hHandle
0x18000a0a7  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000a0ac  mov     ebx, eax
0x18000a0ae  test    eax, eax
0x18000a0b0  jns     short loc_18000A0C8
0x18000a0b2  mov     rcx, [rbp+168h]; this
0x18000a0b9  mov     r9d, eax; char *
0x18000a0bc  mov     edx, 0DEh; void *
0x18000a0c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a0c6  jmp     short loc_18000A093
0x18000a0c8  lea     rcx, [rsp+260h+var_238]
0x18000a0cd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a0d2  movsxd  rcx, [rsp+260h+var_240]
0x18000a0d7  movsxd  rax, [rsp+260h+var_23C]
0x18000a0dc  shl     rcx, 1Fh
0x18000a0e0  or      rcx, rax
0x18000a0e3  mov     [rdi], rcx
0x18000a0e6  xor     ebx, ebx
0x18000a0e8  lea     rcx, [rsp+260h+var_230]
0x18000a0ed  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a0f2  mov     eax, ebx
0x18000a0f4  mov     rcx, [rbp+160h+var_10]
0x18000a0fb  xor     rcx, rsp; StackCookie
0x18000a0fe  call    __security_check_cookie
0x18000a103  lea     r11, [rsp+260h+var_s0]
0x18000a10b  mov     rbx, [r11+18h]
0x18000a10f  mov     rdi, [r11+28h]
0x18000a113  mov     rsp, r11
0x18000a116  pop     rbp
0x18000a117  retn
```
