# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180026c30`
- end: `0x180026dcc`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180023ea8`

## callees

- `0x180023ce0`
- `0x1800249f0`
- `0x180025a64`
- `0x180025a84`
- `0x180026aa4`
- `0x180026b84`
- `0x180026c30`
- `0x18002a590`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180026ca4`
- `KERNEL32!GetLastError` at `0x180026ca4`
- `KERNEL32!OpenSemaphoreW` at `0x180026c94`
- `KERNEL32!OpenSemaphoreW` at `0x180026d24`
- `KERNEL32!OpenSemaphoreW` at `0x180026c94`
- `KERNEL32!OpenSemaphoreW` at `0x180026d24`

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
0x180026c30  mov     [rsp-8+arg_8], rbx
0x180026c35  mov     [rsp-8+arg_18], rdi
0x180026c3a  push    rbp
0x180026c3b  lea     rbp, [rsp-170h]
0x180026c43  sub     rsp, 270h
0x180026c4a  mov     rax, cs:__security_cookie
0x180026c51  xor     rax, rsp
0x180026c54  mov     [rbp+170h+var_10], rax
0x180026c5b  mov     r9, rcx; pszSrc
0x180026c5e  mov     qword ptr [r8], 0
0x180026c65  lea     rcx, [rsp+270h+pszDest]; pszDest
0x180026c6a  mov     edx, 104h; cchDest
0x180026c6f  mov     rdi, r8
0x180026c72  call    StringCopyWorkerW
0x180026c77  lea     r8, aP0; "_p0"
0x180026c7e  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x180026c83  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180026c88  lea     r8, [rsp+270h+pszDest]; lpName
0x180026c8d  xor     edx, edx; bInheritHandle
0x180026c8f  mov     ecx, 1F0003h; dwDesiredAccess
0x180026c94  call    cs:__imp_OpenSemaphoreW
0x180026c9a  mov     [rsp+270h+var_230], rax
0x180026c9f  test    rax, rax
0x180026ca2  jnz     short loc_180026CCB
0x180026ca4  call    cs:__imp_GetLastError
0x180026caa  cmp     eax, 2
0x180026cad  jz      loc_180026D9A
0x180026cb3  mov     rcx, [rbp+178h]; this
0x180026cba  mov     edx, 0D0h; void *
0x180026cbf  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180026cc4  mov     ebx, eax
0x180026cc6  jmp     loc_180026D9C
0x180026ccb  lea     rdx, [rsp+270h+var_23C]; int *
0x180026cd0  mov     [rsp+270h+var_23C], 0
0x180026cd8  mov     rcx, rax; hHandle
0x180026cdb  mov     [rsp+270h+var_240], 0
0x180026ce3  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180026ce8  mov     ebx, eax
0x180026cea  test    eax, eax
0x180026cec  jns     short loc_180026D07
0x180026cee  mov     rcx, [rbp+178h]; this
0x180026cf5  mov     r9d, eax; char *
0x180026cf8  mov     edx, 0D6h; void *
0x180026cfd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026d02  jmp     loc_180026D9C
0x180026d07  lea     r8, asc_18002CCD8; "h"
0x180026d0e  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x180026d13  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180026d18  lea     r8, [rsp+270h+pszDest]; lpName
0x180026d1d  xor     edx, edx; bInheritHandle
0x180026d1f  mov     ecx, 1F0003h; dwDesiredAccess
0x180026d24  call    cs:__imp_OpenSemaphoreW
0x180026d2a  mov     [rsp+270h+var_238], rax
0x180026d2f  test    rax, rax
0x180026d32  jnz     short loc_180026D53
0x180026d34  mov     rcx, [rbp+178h]; this
0x180026d3b  mov     edx, 0DCh; void *
0x180026d40  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180026d45  mov     ebx, eax
0x180026d47  lea     rcx, [rsp+270h+var_238]
0x180026d4c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180026d51  jmp     short loc_180026D9C
0x180026d53  lea     rdx, [rsp+270h+var_240]; int *
0x180026d58  mov     rcx, rax; hHandle
0x180026d5b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180026d60  mov     ebx, eax
0x180026d62  test    eax, eax
0x180026d64  jns     short loc_180026D7C
0x180026d66  mov     rcx, [rbp+178h]; this
0x180026d6d  mov     r9d, eax; char *
0x180026d70  mov     edx, 0DEh; void *
0x180026d75  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026d7a  jmp     short loc_180026D47
0x180026d7c  lea     rcx, [rsp+270h+var_238]
0x180026d81  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180026d86  movsxd  rcx, [rsp+270h+var_240]
0x180026d8b  movsxd  rax, [rsp+270h+var_23C]
0x180026d90  shl     rcx, 1Fh
0x180026d94  or      rcx, rax
0x180026d97  mov     [rdi], rcx
0x180026d9a  xor     ebx, ebx
0x180026d9c  lea     rcx, [rsp+270h+var_230]
0x180026da1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180026da6  mov     eax, ebx
0x180026da8  mov     rcx, [rbp+170h+var_10]
0x180026daf  xor     rcx, rsp; StackCookie
0x180026db2  call    __security_check_cookie
0x180026db7  lea     r11, [rsp+270h+var_s0]
0x180026dbf  mov     rbx, [r11+18h]
0x180026dc3  mov     rdi, [r11+28h]
0x180026dc7  mov     rsp, r11
0x180026dca  pop     rbp
0x180026dcb  retn
```
