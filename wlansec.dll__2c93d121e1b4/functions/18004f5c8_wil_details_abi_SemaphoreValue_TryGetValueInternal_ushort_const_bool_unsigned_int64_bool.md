# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18004f5c8`
- end: `0x18004f777`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `431`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18004f550`

## callees

- `0x180043a30`
- `0x18004c824`
- `0x18004d708`
- `0x18004ec9c`
- `0x18004ecbc`
- `0x18004f144`
- `0x18004f1c4`
- `0x18004f5c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18004f62c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18004f6c8`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18004f62c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18004f6c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f642`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f642`

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
0x18004f5c8  mov     [rsp-8+arg_8], rbx
0x18004f5cd  mov     [rsp-8+arg_18], rdi
0x18004f5d2  push    rbp
0x18004f5d3  lea     rbp, [rsp-170h]
0x18004f5db  sub     rsp, 270h
0x18004f5e2  mov     rax, cs:__security_cookie
0x18004f5e9  xor     rax, rsp
0x18004f5ec  mov     [rbp+170h+var_10], rax
0x18004f5f3  mov     r9, rcx; pszSrc
0x18004f5f6  mov     qword ptr [r8], 0
0x18004f5fd  lea     rcx, [rsp+270h+pszDest]; pszDest
0x18004f602  mov     edx, 104h; cchDest
0x18004f607  mov     rdi, r8
0x18004f60a  call    StringCopyWorkerW
0x18004f60f  lea     r8, aP0; "_p0"
0x18004f616  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x18004f61b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004f620  lea     r8, [rsp+270h+pszDest]; lpName
0x18004f625  xor     edx, edx; bInheritHandle
0x18004f627  mov     ecx, 1F0003h; dwDesiredAccess
0x18004f62c  call    cs:__imp_OpenSemaphoreW
0x18004f633  nop     dword ptr [rax+rax+00h]
0x18004f638  mov     [rsp+270h+var_230], rax
0x18004f63d  test    rax, rax
0x18004f640  jnz     short loc_18004F66F
0x18004f642  call    cs:__imp_GetLastError
0x18004f649  nop     dword ptr [rax+rax+00h]
0x18004f64e  cmp     eax, 2
0x18004f651  jz      loc_18004F744
0x18004f657  mov     rcx, [rbp+178h]; this
0x18004f65e  mov     edx, 0D0h; void *
0x18004f663  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004f668  mov     ebx, eax
0x18004f66a  jmp     loc_18004F746
0x18004f66f  lea     rdx, [rsp+270h+var_23C]; int *
0x18004f674  mov     [rsp+270h+var_23C], 0
0x18004f67c  mov     rcx, rax; hHandle
0x18004f67f  mov     [rsp+270h+var_240], 0
0x18004f687  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18004f68c  mov     ebx, eax
0x18004f68e  test    eax, eax
0x18004f690  jns     short loc_18004F6AB
0x18004f692  mov     rcx, [rbp+178h]; this
0x18004f699  mov     r9d, eax; char *
0x18004f69c  mov     edx, 0D6h; void *
0x18004f6a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f6a6  jmp     loc_18004F746
0x18004f6ab  lea     r8, asc_18009BA20; "h"
0x18004f6b2  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x18004f6b7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004f6bc  lea     r8, [rsp+270h+pszDest]; lpName
0x18004f6c1  xor     edx, edx; bInheritHandle
0x18004f6c3  mov     ecx, 1F0003h; dwDesiredAccess
0x18004f6c8  call    cs:__imp_OpenSemaphoreW
0x18004f6cf  nop     dword ptr [rax+rax+00h]
0x18004f6d4  mov     [rsp+270h+var_238], rax
0x18004f6d9  test    rax, rax
0x18004f6dc  jnz     short loc_18004F6FD
0x18004f6de  mov     rcx, [rbp+178h]; this
0x18004f6e5  mov     edx, 0DCh; void *
0x18004f6ea  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004f6ef  mov     ebx, eax
0x18004f6f1  lea     rcx, [rsp+270h+var_238]
0x18004f6f6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004f6fb  jmp     short loc_18004F746
0x18004f6fd  lea     rdx, [rsp+270h+var_240]; int *
0x18004f702  mov     rcx, rax; hHandle
0x18004f705  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18004f70a  mov     ebx, eax
0x18004f70c  test    eax, eax
0x18004f70e  jns     short loc_18004F726
0x18004f710  mov     rcx, [rbp+178h]; this
0x18004f717  mov     r9d, eax; char *
0x18004f71a  mov     edx, 0DEh; void *
0x18004f71f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f724  jmp     short loc_18004F6F1
0x18004f726  lea     rcx, [rsp+270h+var_238]
0x18004f72b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004f730  movsxd  rcx, [rsp+270h+var_240]
0x18004f735  movsxd  rax, [rsp+270h+var_23C]
0x18004f73a  shl     rcx, 1Fh
0x18004f73e  or      rcx, rax
0x18004f741  mov     [rdi], rcx
0x18004f744  xor     ebx, ebx
0x18004f746  lea     rcx, [rsp+270h+var_230]
0x18004f74b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004f750  mov     eax, ebx
0x18004f752  mov     rcx, [rbp+170h+var_10]
0x18004f759  xor     rcx, rsp; StackCookie
0x18004f75c  call    __security_check_cookie
0x18004f761  lea     r11, [rsp+270h+var_s0]
0x18004f769  mov     rbx, [r11+18h]
0x18004f76d  mov     rdi, [r11+28h]
0x18004f771  mov     rsp, r11
0x18004f774  pop     rbp
0x18004f775  retn
```
