# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000d4b8`
- end: `0x18000d65a`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `418`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000b998`

## callees

- `0x180005d40`
- `0x1800097d0`
- `0x18000b870`
- `0x18000c554`
- `0x18000ce34`
- `0x18000ce54`
- `0x18000d32c`
- `0x18000d4b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000d521`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000d5b3`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000d521`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000d5b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d531`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d531`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        unsigned __int16 *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  wil::details *v5; // rax
  void *v6; // rdx
  unsigned int v7; // r8d
  const char *v8; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  int v11; // r8d
  wil::details *v12; // rax
  unsigned int v13; // r8d
  const char *v14; // r9
  void *v15; // rdx
  int v16; // eax
  void *v17; // rdx
  int v18; // r8d
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh] BYREF
  wil::details *v22; // [rsp+28h] [rbp-D8h] BYREF
  wil::details *v23; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, 0x104u, L"_p0");
  v5 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v23 = v5;
  if ( v5 )
  {
    v21 = 0;
    v20 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &v21);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v11, (const char *)(unsigned int)ValueFromSemaphore);
      goto LABEL_13;
    }
    StringCchCatW(Name, 0x104u, L"h");
    v12 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
    v22 = v12;
    if ( v12 )
    {
      v16 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v12, &v20);
      LastError = v16;
      if ( v16 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
          &v22,
          v17);
        *a3 = v21 | (unsigned __int64)((__int64)v20 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v18, (const char *)(unsigned int)v16);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v13, v14);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v22,
      v15);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v23,
    v6);
  return LastError;
}

```

## disassembly

```asm
0x18000d4b8  mov     [rsp-8+arg_8], rbx
0x18000d4bd  push    rbp
0x18000d4be  push    rdi
0x18000d4bf  push    r14
0x18000d4c1  lea     rbp, [rsp-160h]
0x18000d4c9  sub     rsp, 260h
0x18000d4d0  mov     rax, cs:__security_cookie
0x18000d4d7  xor     rax, rsp
0x18000d4da  mov     [rbp+170h+var_20], rax
0x18000d4e1  mov     rdi, r8
0x18000d4e4  mov     qword ptr [r8], 0
0x18000d4eb  mov     r8, rcx; unsigned __int16 *
0x18000d4ee  mov     r14d, 104h
0x18000d4f4  mov     edx, r14d; unsigned __int64
0x18000d4f7  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000d4fc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000d501  lea     r8, aP0; "_p0"
0x18000d508  mov     edx, r14d; unsigned __int64
0x18000d50b  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000d510  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000d515  lea     r8, [rsp+270h+Name]; lpName
0x18000d51a  xor     edx, edx; bInheritHandle
0x18000d51c  mov     ecx, 1F0003h; dwDesiredAccess
0x18000d521  call    cs:__imp_OpenSemaphoreW
0x18000d527  mov     [rsp+270h+var_240], rax
0x18000d52c  test    rax, rax
0x18000d52f  jnz     short loc_18000D557
0x18000d531  call    cs:__imp_GetLastError
0x18000d537  cmp     eax, 2
0x18000d53a  jz      loc_18000D629
0x18000d540  mov     rcx, [rbp+178h]; this
0x18000d547  lea     edx, [r14-34h]; void *
0x18000d54b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000d550  mov     ebx, eax
0x18000d552  jmp     loc_18000D62B
0x18000d557  lea     rdx, [rsp+270h+var_24C]; int *
0x18000d55c  mov     [rsp+270h+var_24C], 0
0x18000d564  mov     rcx, rax; hHandle
0x18000d567  mov     [rsp+270h+var_250], 0; int
0x18000d56f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000d574  mov     ebx, eax
0x18000d576  test    eax, eax
0x18000d578  jns     short loc_18000D593
0x18000d57a  mov     rcx, [rbp+178h]; this
0x18000d581  mov     r9d, eax; char *
0x18000d584  mov     edx, 0D6h; void *
0x18000d589  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d58e  jmp     loc_18000D62B
0x18000d593  lea     r8, asc_180018610; "h"
0x18000d59a  mov     rdx, r14; unsigned __int64
0x18000d59d  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000d5a2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000d5a7  lea     r8, [rsp+270h+Name]; lpName
0x18000d5ac  xor     edx, edx; bInheritHandle
0x18000d5ae  mov     ecx, 1F0003h; dwDesiredAccess
0x18000d5b3  call    cs:__imp_OpenSemaphoreW
0x18000d5b9  mov     [rsp+270h+var_248], rax
0x18000d5be  test    rax, rax
0x18000d5c1  jnz     short loc_18000D5E2
0x18000d5c3  mov     rcx, [rbp+178h]; this
0x18000d5ca  mov     edx, 0DCh; void *
0x18000d5cf  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000d5d4  mov     ebx, eax
0x18000d5d6  lea     rcx, [rsp+270h+var_248]
0x18000d5db  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000d5e0  jmp     short loc_18000D62B
0x18000d5e2  lea     rdx, [rsp+270h+var_250]; int *
0x18000d5e7  mov     rcx, rax; hHandle
0x18000d5ea  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000d5ef  mov     ebx, eax
0x18000d5f1  test    eax, eax
0x18000d5f3  jns     short loc_18000D60B
0x18000d5f5  mov     rcx, [rbp+178h]; this
0x18000d5fc  mov     r9d, eax; char *
0x18000d5ff  mov     edx, 0DEh; void *
0x18000d604  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d609  jmp     short loc_18000D5D6
0x18000d60b  lea     rcx, [rsp+270h+var_248]
0x18000d610  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000d615  movsxd  rcx, [rsp+270h+var_250]
0x18000d61a  movsxd  rax, [rsp+270h+var_24C]
0x18000d61f  shl     rcx, 1Fh
0x18000d623  or      rcx, rax
0x18000d626  mov     [rdi], rcx
0x18000d629  xor     ebx, ebx
0x18000d62b  lea     rcx, [rsp+270h+var_240]
0x18000d630  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000d635  mov     eax, ebx
0x18000d637  mov     rcx, [rbp+170h+var_20]
0x18000d63e  xor     rcx, rsp; StackCookie
0x18000d641  call    __security_check_cookie
0x18000d646  mov     rbx, [rsp+270h+arg_8]
0x18000d64e  add     rsp, 260h
0x18000d655  pop     r14
0x18000d657  pop     rdi
0x18000d658  pop     rbp
0x18000d659  retn
```
