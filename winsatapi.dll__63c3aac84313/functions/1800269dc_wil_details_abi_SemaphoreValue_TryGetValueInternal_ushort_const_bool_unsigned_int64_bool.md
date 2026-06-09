# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800269dc`
- end: `0x180026b7e`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `418`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180026968`

## callees

- `0x18000bc50`
- `0x18000febc`
- `0x18001233c`
- `0x180022f4c`
- `0x180024bfc`
- `0x180025fdc`
- `0x1800269dc`
- `0x18002dec0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026a55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026a55`
- `KERNEL32!OpenSemaphoreW` at `0x180026a45`
- `KERNEL32!OpenSemaphoreW` at `0x180026ad7`
- `KERNEL32!OpenSemaphoreW` at `0x180026a45`
- `KERNEL32!OpenSemaphoreW` at `0x180026ad7`

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
  unsigned int v10; // r8d
  HANDLE v11; // rax
  unsigned int v12; // r8d
  const char *v13; // r9
  int v14; // eax
  unsigned int v15; // r8d
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v19; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v20[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, 0x104u, L"_p0");
  v5 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v20[0] = v5;
  if ( v5 )
  {
    v18 = 0;
    v17 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &v18);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v10, (const char *)(unsigned int)ValueFromSemaphore, v17);
      goto LABEL_13;
    }
    StringCchCatW(Name, 0x104u, L"h");
    v11 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v19 = v11;
    if ( v11 )
    {
      v14 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v11, &v17);
      LastError = v14;
      if ( v14 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
        *a3 = v18 | (unsigned __int64)((__int64)v17 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v15, (const char *)(unsigned int)v14, v17);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v12, v13);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v20);
  return LastError;
}

```

## disassembly

```asm
0x1800269dc  mov     [rsp-8+arg_8], rbx
0x1800269e1  push    rbp
0x1800269e2  push    rdi
0x1800269e3  push    r14
0x1800269e5  lea     rbp, [rsp-160h]
0x1800269ed  sub     rsp, 260h
0x1800269f4  mov     rax, cs:__security_cookie
0x1800269fb  xor     rax, rsp
0x1800269fe  mov     [rbp+170h+var_20], rax
0x180026a05  mov     rdi, r8
0x180026a08  mov     qword ptr [r8], 0
0x180026a0f  mov     r8, rcx; unsigned __int16 *
0x180026a12  mov     r14d, 104h
0x180026a18  mov     edx, r14d; unsigned __int64
0x180026a1b  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180026a20  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180026a25  lea     r8, aP0; "_p0"
0x180026a2c  mov     edx, r14d; unsigned __int64
0x180026a2f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180026a34  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180026a39  lea     r8, [rsp+270h+Name]; lpName
0x180026a3e  xor     edx, edx; bInheritHandle
0x180026a40  mov     ecx, 1F0003h; dwDesiredAccess
0x180026a45  call    cs:__imp_OpenSemaphoreW
0x180026a4b  mov     [rsp+270h+var_240], rax
0x180026a50  test    rax, rax
0x180026a53  jnz     short loc_180026A7B
0x180026a55  call    cs:__imp_GetLastError
0x180026a5b  cmp     eax, 2
0x180026a5e  jz      loc_180026B4D
0x180026a64  mov     rcx, [rbp+178h]; this
0x180026a6b  lea     edx, [r14-34h]; void *
0x180026a6f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180026a74  mov     ebx, eax
0x180026a76  jmp     loc_180026B4F
0x180026a7b  lea     rdx, [rsp+270h+var_24C]; int *
0x180026a80  mov     [rsp+270h+var_24C], 0
0x180026a88  mov     rcx, rax; hHandle
0x180026a8b  mov     [rsp+270h+var_250], 0; int
0x180026a93  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180026a98  mov     ebx, eax
0x180026a9a  test    eax, eax
0x180026a9c  jns     short loc_180026AB7
0x180026a9e  mov     rcx, [rbp+178h]; this
0x180026aa5  mov     r9d, eax; char *
0x180026aa8  mov     edx, 0D6h; void *
0x180026aad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026ab2  jmp     loc_180026B4F
0x180026ab7  lea     r8, asc_180038F68; "h"
0x180026abe  mov     rdx, r14; unsigned __int64
0x180026ac1  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180026ac6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180026acb  lea     r8, [rsp+270h+Name]; lpName
0x180026ad0  xor     edx, edx; bInheritHandle
0x180026ad2  mov     ecx, 1F0003h; dwDesiredAccess
0x180026ad7  call    cs:__imp_OpenSemaphoreW
0x180026add  mov     [rsp+270h+var_248], rax
0x180026ae2  test    rax, rax
0x180026ae5  jnz     short loc_180026B06
0x180026ae7  mov     rcx, [rbp+178h]; this
0x180026aee  mov     edx, 0DCh; void *
0x180026af3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180026af8  mov     ebx, eax
0x180026afa  lea     rcx, [rsp+270h+var_248]
0x180026aff  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180026b04  jmp     short loc_180026B4F
0x180026b06  lea     rdx, [rsp+270h+var_250]; int *
0x180026b0b  mov     rcx, rax; hHandle
0x180026b0e  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180026b13  mov     ebx, eax
0x180026b15  test    eax, eax
0x180026b17  jns     short loc_180026B2F
0x180026b19  mov     rcx, [rbp+178h]; this
0x180026b20  mov     r9d, eax; char *
0x180026b23  mov     edx, 0DEh; void *
0x180026b28  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026b2d  jmp     short loc_180026AFA
0x180026b2f  lea     rcx, [rsp+270h+var_248]
0x180026b34  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180026b39  movsxd  rcx, [rsp+270h+var_250]
0x180026b3e  movsxd  rax, [rsp+270h+var_24C]
0x180026b43  shl     rcx, 1Fh
0x180026b47  or      rcx, rax
0x180026b4a  mov     [rdi], rcx
0x180026b4d  xor     ebx, ebx
0x180026b4f  lea     rcx, [rsp+270h+var_240]
0x180026b54  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180026b59  mov     eax, ebx
0x180026b5b  mov     rcx, [rbp+170h+var_20]
0x180026b62  xor     rcx, rsp; StackCookie
0x180026b65  call    __security_check_cookie
0x180026b6a  mov     rbx, [rsp+270h+arg_8]
0x180026b72  add     rsp, 260h
0x180026b79  pop     r14
0x180026b7b  pop     rdi
0x180026b7c  pop     rbp
0x180026b7d  retn
```
