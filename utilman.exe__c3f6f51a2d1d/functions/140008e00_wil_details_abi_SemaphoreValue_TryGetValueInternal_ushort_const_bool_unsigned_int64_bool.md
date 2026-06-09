# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x140008e00`
- end: `0x140008fcb`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `459`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x140008d7c`

## callees

- `0x140002480`
- `0x1400048c4`
- `0x1400060f4`
- `0x14000813c`
- `0x14000815c`
- `0x14000884c`
- `0x14000897c`
- `0x140008e00`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140008e7a`
- `KERNEL32!GetLastError` at `0x140008e7a`
- `KERNEL32!OpenSemaphoreW` at `0x140008e64`
- `KERNEL32!OpenSemaphoreW` at `0x140008f0e`
- `KERNEL32!OpenSemaphoreW` at `0x140008e64`
- `KERNEL32!OpenSemaphoreW` at `0x140008f0e`

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
  const char *v7; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned __int64 v10; // rdx
  HANDLE v11; // rax
  const char *v12; // r9
  int v13; // eax
  size_t v15; // [rsp+20h] [rbp-E0h]
  int v16; // [rsp+20h] [rbp-E0h]
  int v17; // [rsp+30h] [rbp-D0h] BYREF
  int v18; // [rsp+34h] [rbp-CCh] BYREF
  HANDLE v19; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE v20[2]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCopyWorkerW(pszDest, 0x104u, a3, pszSrc, v15);
  StringCchCatW(pszDest, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v20[0] = v6;
  if ( v6 )
  {
    v18 = 0;
    v17 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v18);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v16);
      goto LABEL_13;
    }
    StringCchCatW(pszDest, v10, L"h");
    v11 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
    v19 = v11;
    if ( v11 )
    {
      v13 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v11, &v17);
      LastError = v13;
      if ( v13 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
        *a3 = v18 | (unsigned __int64)((__int64)v17 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v13,
        v16);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v12);
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
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v7);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v20);
  return LastError;
}

```

## disassembly

```asm
0x140008e00  mov     [rsp-8+arg_8], rbx
0x140008e05  mov     [rsp-8+arg_18], rdi
0x140008e0a  push    rbp
0x140008e0b  lea     rbp, [rsp-170h]
0x140008e13  sub     rsp, 270h
0x140008e1a  mov     rax, cs:__security_cookie
0x140008e21  xor     rax, rsp
0x140008e24  mov     [rbp+170h+var_10], rax
0x140008e2b  mov     r9, rcx; pszSrc
0x140008e2e  mov     qword ptr [r8], 0
0x140008e35  lea     rcx, [rsp+270h+pszDest]; pszDest
0x140008e3a  mov     edx, 104h; cchDest
0x140008e3f  mov     rdi, r8
0x140008e42  call    StringCopyWorkerW
0x140008e47  lea     r8, aP0; "_p0"
0x140008e4e  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x140008e53  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140008e58  lea     r8, [rsp+270h+pszDest]; lpName
0x140008e5d  xor     edx, edx; bInheritHandle
0x140008e5f  mov     ecx, 1F0003h; dwDesiredAccess
0x140008e64  call    cs:__imp_OpenSemaphoreW
0x140008e6b  nop     dword ptr [rax+rax+00h]
0x140008e70  mov     [rsp+270h+var_230], rax
0x140008e75  test    rax, rax
0x140008e78  jnz     short loc_140008EAE
0x140008e7a  call    cs:__imp_GetLastError
0x140008e81  nop     dword ptr [rax+rax+00h]
0x140008e86  cmp     eax, 2
0x140008e89  jz      loc_140008F98
0x140008e8f  mov     rcx, [rbp+178h]; this
0x140008e96  lea     r8, aWil; "wil"
0x140008e9d  mov     edx, 0D0h; void *
0x140008ea2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140008ea7  mov     ebx, eax
0x140008ea9  jmp     loc_140008F9A
0x140008eae  lea     rdx, [rsp+270h+var_23C]; int *
0x140008eb3  mov     [rsp+270h+var_23C], 0
0x140008ebb  mov     rcx, rax; hHandle
0x140008ebe  mov     [rsp+270h+var_240], 0
0x140008ec6  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140008ecb  mov     ebx, eax
0x140008ecd  test    eax, eax
0x140008ecf  jns     short loc_140008EF1
0x140008ed1  mov     rcx, [rbp+178h]; this
0x140008ed8  lea     r8, aWil; "wil"
0x140008edf  mov     r9d, eax; char *
0x140008ee2  mov     edx, 0D6h; void *
0x140008ee7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008eec  jmp     loc_140008F9A
0x140008ef1  lea     r8, asc_14002C850; "h"
0x140008ef8  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x140008efd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140008f02  lea     r8, [rsp+270h+pszDest]; lpName
0x140008f07  xor     edx, edx; bInheritHandle
0x140008f09  mov     ecx, 1F0003h; dwDesiredAccess
0x140008f0e  call    cs:__imp_OpenSemaphoreW
0x140008f15  nop     dword ptr [rax+rax+00h]
0x140008f1a  mov     [rsp+270h+var_238], rax
0x140008f1f  test    rax, rax
0x140008f22  jnz     short loc_140008F4A
0x140008f24  mov     rcx, [rbp+178h]; this
0x140008f2b  lea     r8, aWil; "wil"
0x140008f32  mov     edx, 0DCh; void *
0x140008f37  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140008f3c  mov     ebx, eax
0x140008f3e  lea     rcx, [rsp+270h+var_238]
0x140008f43  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140008f48  jmp     short loc_140008F9A
0x140008f4a  lea     rdx, [rsp+270h+var_240]; int *
0x140008f4f  mov     rcx, rax; hHandle
0x140008f52  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140008f57  mov     ebx, eax
0x140008f59  test    eax, eax
0x140008f5b  jns     short loc_140008F7A
0x140008f5d  mov     rcx, [rbp+178h]; this
0x140008f64  lea     r8, aWil; "wil"
0x140008f6b  mov     r9d, eax; char *
0x140008f6e  mov     edx, 0DEh; void *
0x140008f73  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008f78  jmp     short loc_140008F3E
0x140008f7a  lea     rcx, [rsp+270h+var_238]
0x140008f7f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140008f84  movsxd  rcx, [rsp+270h+var_240]
0x140008f89  movsxd  rax, [rsp+270h+var_23C]
0x140008f8e  shl     rcx, 1Fh
0x140008f92  or      rcx, rax
0x140008f95  mov     [rdi], rcx
0x140008f98  xor     ebx, ebx
0x140008f9a  lea     rcx, [rsp+270h+var_230]
0x140008f9f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140008fa4  mov     eax, ebx
0x140008fa6  mov     rcx, [rbp+170h+var_10]
0x140008fad  xor     rcx, rsp; StackCookie
0x140008fb0  call    __security_check_cookie
0x140008fb5  lea     r11, [rsp+270h+var_s0]
0x140008fbd  mov     rbx, [r11+18h]
0x140008fc1  mov     rdi, [r11+28h]
0x140008fc5  mov     rsp, r11
0x140008fc8  pop     rbp
0x140008fc9  retn
```
