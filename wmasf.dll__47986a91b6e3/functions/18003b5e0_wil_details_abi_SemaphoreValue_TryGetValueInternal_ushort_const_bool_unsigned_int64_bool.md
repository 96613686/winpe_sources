# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18003b5e0`
- end: `0x18003b77c`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180033b64`

## callees

- `0x1800015d0`
- `0x18000ff88`
- `0x1800336c8`
- `0x1800381b4`
- `0x18003a91c`
- `0x18003a93c`
- `0x18003b3cc`
- `0x18003b5e0`

## import_xrefs

- `KERNEL32!OpenSemaphoreW` at `0x18003b644`
- `KERNEL32!OpenSemaphoreW` at `0x18003b6d4`
- `KERNEL32!OpenSemaphoreW` at `0x18003b644`
- `KERNEL32!OpenSemaphoreW` at `0x18003b6d4`
- `KERNEL32!GetLastError` at `0x18003b654`
- `KERNEL32!GetLastError` at `0x18003b654`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
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
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  int v20; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v21; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v22[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v22[0] = v6;
  if ( v6 )
  {
    v20 = 0;
    v19 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v20);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v12, (const char *)(unsigned int)ValueFromSemaphore, v19);
      goto LABEL_13;
    }
    StringCchCatW(Name, v11, L"h");
    v13 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v21 = v13;
    if ( v13 )
    {
      v16 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v13, &v19);
      LastError = v16;
      if ( v16 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
        *a3 = v20 | (unsigned __int64)((__int64)v19 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v17, (const char *)(unsigned int)v16, v19);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v14, v15);
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
0x18003b5e0  mov     [rsp-8+arg_8], rbx
0x18003b5e5  mov     [rsp-8+arg_18], rdi
0x18003b5ea  push    rbp
0x18003b5eb  lea     rbp, [rsp-160h]
0x18003b5f3  sub     rsp, 260h
0x18003b5fa  mov     rax, cs:__security_cookie
0x18003b601  xor     rax, rsp
0x18003b604  mov     [rbp+160h+var_10], rax
0x18003b60b  mov     rdi, r8
0x18003b60e  mov     qword ptr [r8], 0
0x18003b615  mov     r8, rcx; unsigned __int16 *
0x18003b618  mov     edx, 104h; unsigned __int64
0x18003b61d  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18003b622  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003b627  lea     r8, aP0; "_p0"
0x18003b62e  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18003b633  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003b638  lea     r8, [rsp+260h+Name]; lpName
0x18003b63d  xor     edx, edx; bInheritHandle
0x18003b63f  mov     ecx, 1F0003h; dwDesiredAccess
0x18003b644  call    cs:__imp_OpenSemaphoreW
0x18003b64a  mov     [rsp+260h+var_230], rax
0x18003b64f  test    rax, rax
0x18003b652  jnz     short loc_18003B67B
0x18003b654  call    cs:__imp_GetLastError
0x18003b65a  cmp     eax, 2
0x18003b65d  jz      loc_18003B74A
0x18003b663  mov     rcx, [rbp+168h]; this
0x18003b66a  mov     edx, 0D0h; void *
0x18003b66f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003b674  mov     ebx, eax
0x18003b676  jmp     loc_18003B74C
0x18003b67b  lea     rdx, [rsp+260h+var_23C]; int *
0x18003b680  mov     [rsp+260h+var_23C], 0
0x18003b688  mov     rcx, rax; hHandle
0x18003b68b  mov     [rsp+260h+var_240], 0; int
0x18003b693  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18003b698  mov     ebx, eax
0x18003b69a  test    eax, eax
0x18003b69c  jns     short loc_18003B6B7
0x18003b69e  mov     rcx, [rbp+168h]; this
0x18003b6a5  mov     r9d, eax; char *
0x18003b6a8  mov     edx, 0D6h; void *
0x18003b6ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b6b2  jmp     loc_18003B74C
0x18003b6b7  lea     r8, asc_180046FE0; "h"
0x18003b6be  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18003b6c3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003b6c8  lea     r8, [rsp+260h+Name]; lpName
0x18003b6cd  xor     edx, edx; bInheritHandle
0x18003b6cf  mov     ecx, 1F0003h; dwDesiredAccess
0x18003b6d4  call    cs:__imp_OpenSemaphoreW
0x18003b6da  mov     [rsp+260h+var_238], rax
0x18003b6df  test    rax, rax
0x18003b6e2  jnz     short loc_18003B703
0x18003b6e4  mov     rcx, [rbp+168h]; this
0x18003b6eb  mov     edx, 0DCh; void *
0x18003b6f0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003b6f5  mov     ebx, eax
0x18003b6f7  lea     rcx, [rsp+260h+var_238]
0x18003b6fc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003b701  jmp     short loc_18003B74C
0x18003b703  lea     rdx, [rsp+260h+var_240]; int *
0x18003b708  mov     rcx, rax; hHandle
0x18003b70b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18003b710  mov     ebx, eax
0x18003b712  test    eax, eax
0x18003b714  jns     short loc_18003B72C
0x18003b716  mov     rcx, [rbp+168h]; this
0x18003b71d  mov     r9d, eax; char *
0x18003b720  mov     edx, 0DEh; void *
0x18003b725  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b72a  jmp     short loc_18003B6F7
0x18003b72c  lea     rcx, [rsp+260h+var_238]
0x18003b731  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003b736  movsxd  rcx, [rsp+260h+var_240]
0x18003b73b  movsxd  rax, [rsp+260h+var_23C]
0x18003b740  shl     rcx, 1Fh
0x18003b744  or      rcx, rax
0x18003b747  mov     [rdi], rcx
0x18003b74a  xor     ebx, ebx
0x18003b74c  lea     rcx, [rsp+260h+var_230]
0x18003b751  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003b756  mov     eax, ebx
0x18003b758  mov     rcx, [rbp+160h+var_10]
0x18003b75f  xor     rcx, rsp; StackCookie
0x18003b762  call    __security_check_cookie
0x18003b767  lea     r11, [rsp+260h+var_s0]
0x18003b76f  mov     rbx, [r11+18h]
0x18003b773  mov     rdi, [r11+28h]
0x18003b777  mov     rsp, r11
0x18003b77a  pop     rbp
0x18003b77b  retn
```
