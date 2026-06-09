# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180016754`
- end: `0x1800168f0`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800166e0`

## callees

- `0x180012880`
- `0x1800143d8`
- `0x180015318`
- `0x1800160a0`
- `0x1800160c0`
- `0x1800163ac`
- `0x18001648c`
- `0x180016754`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800167b8`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180016848`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800167b8`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180016848`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800167c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800167c8`

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
0x180016754  mov     [rsp-8+arg_8], rbx
0x180016759  mov     [rsp-8+arg_18], rdi
0x18001675e  push    rbp
0x18001675f  lea     rbp, [rsp-170h]
0x180016767  sub     rsp, 270h
0x18001676e  mov     rax, cs:__security_cookie
0x180016775  xor     rax, rsp
0x180016778  mov     [rbp+170h+var_10], rax
0x18001677f  mov     r9, rcx; pszSrc
0x180016782  mov     qword ptr [r8], 0
0x180016789  lea     rcx, [rsp+270h+pszDest]; pszDest
0x18001678e  mov     edx, 104h; cchDest
0x180016793  mov     rdi, r8
0x180016796  call    StringCopyWorkerW
0x18001679b  lea     r8, aP0; "_p0"
0x1800167a2  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x1800167a7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800167ac  lea     r8, [rsp+270h+pszDest]; lpName
0x1800167b1  xor     edx, edx; bInheritHandle
0x1800167b3  mov     ecx, 1F0003h; dwDesiredAccess
0x1800167b8  call    cs:__imp_OpenSemaphoreW
0x1800167be  mov     [rsp+270h+var_230], rax
0x1800167c3  test    rax, rax
0x1800167c6  jnz     short loc_1800167EF
0x1800167c8  call    cs:__imp_GetLastError
0x1800167ce  cmp     eax, 2
0x1800167d1  jz      loc_1800168BE
0x1800167d7  mov     rcx, [rbp+178h]; this
0x1800167de  mov     edx, 0D0h; void *
0x1800167e3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800167e8  mov     ebx, eax
0x1800167ea  jmp     loc_1800168C0
0x1800167ef  lea     rdx, [rsp+270h+var_23C]; int *
0x1800167f4  mov     [rsp+270h+var_23C], 0
0x1800167fc  mov     rcx, rax; hHandle
0x1800167ff  mov     [rsp+270h+var_240], 0
0x180016807  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001680c  mov     ebx, eax
0x18001680e  test    eax, eax
0x180016810  jns     short loc_18001682B
0x180016812  mov     rcx, [rbp+178h]; this
0x180016819  mov     r9d, eax; char *
0x18001681c  mov     edx, 0D6h; void *
0x180016821  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016826  jmp     loc_1800168C0
0x18001682b  lea     r8, asc_18003BD70; "h"
0x180016832  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x180016837  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001683c  lea     r8, [rsp+270h+pszDest]; lpName
0x180016841  xor     edx, edx; bInheritHandle
0x180016843  mov     ecx, 1F0003h; dwDesiredAccess
0x180016848  call    cs:__imp_OpenSemaphoreW
0x18001684e  mov     [rsp+270h+var_238], rax
0x180016853  test    rax, rax
0x180016856  jnz     short loc_180016877
0x180016858  mov     rcx, [rbp+178h]; this
0x18001685f  mov     edx, 0DCh; void *
0x180016864  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180016869  mov     ebx, eax
0x18001686b  lea     rcx, [rsp+270h+var_238]
0x180016870  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180016875  jmp     short loc_1800168C0
0x180016877  lea     rdx, [rsp+270h+var_240]; int *
0x18001687c  mov     rcx, rax; hHandle
0x18001687f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180016884  mov     ebx, eax
0x180016886  test    eax, eax
0x180016888  jns     short loc_1800168A0
0x18001688a  mov     rcx, [rbp+178h]; this
0x180016891  mov     r9d, eax; char *
0x180016894  mov     edx, 0DEh; void *
0x180016899  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001689e  jmp     short loc_18001686B
0x1800168a0  lea     rcx, [rsp+270h+var_238]
0x1800168a5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800168aa  movsxd  rcx, [rsp+270h+var_240]
0x1800168af  movsxd  rax, [rsp+270h+var_23C]
0x1800168b4  shl     rcx, 1Fh
0x1800168b8  or      rcx, rax
0x1800168bb  mov     [rdi], rcx
0x1800168be  xor     ebx, ebx
0x1800168c0  lea     rcx, [rsp+270h+var_230]
0x1800168c5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800168ca  mov     eax, ebx
0x1800168cc  mov     rcx, [rbp+170h+var_10]
0x1800168d3  xor     rcx, rsp; StackCookie
0x1800168d6  call    __security_check_cookie
0x1800168db  lea     r11, [rsp+270h+var_s0]
0x1800168e3  mov     rbx, [r11+18h]
0x1800168e7  mov     rdi, [r11+28h]
0x1800168eb  mov     rsp, r11
0x1800168ee  pop     rbp
0x1800168ef  retn
```
