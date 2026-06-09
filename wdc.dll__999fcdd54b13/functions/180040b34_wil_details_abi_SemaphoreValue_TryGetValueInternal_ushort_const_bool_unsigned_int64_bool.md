# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180040b34`
- end: `0x180040ce4`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `432`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180040ab0`

## callees

- `0x18001cb20`
- `0x18003a3c0`
- `0x18003da4c`
- `0x18003ecb4`
- `0x180040268`
- `0x180040288`
- `0x180040730`
- `0x180040b34`

## import_xrefs

- `KERNEL32!OpenSemaphoreW` at `0x180040b9d`
- `KERNEL32!OpenSemaphoreW` at `0x180040c36`
- `KERNEL32!OpenSemaphoreW` at `0x180040b9d`
- `KERNEL32!OpenSemaphoreW` at `0x180040c36`
- `KERNEL32!GetLastError` at `0x180040bad`
- `KERNEL32!GetLastError` at `0x180040bad`

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
  HANDLE v10; // rax
  unsigned int v11; // r8d
  const char *v12; // r9
  int v13; // eax
  int v15; // [rsp+20h] [rbp-E0h] BYREF
  int v16; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v17; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v18[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, 0x104u, L"_p0");
  v5 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v18[0] = v5;
  if ( v5 )
  {
    v16 = 0;
    v15 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &v16);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v15);
      goto LABEL_13;
    }
    StringCchCatW(Name, 0x104u, L"h");
    v10 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v17 = v10;
    if ( v10 )
    {
      v13 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v10, &v15);
      LastError = v13;
      if ( v13 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
        *a3 = v16 | (unsigned __int64)((__int64)v15 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v13,
        v15);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v11, v12);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v18);
  return LastError;
}

```

## disassembly

```asm
0x180040b34  mov     [rsp-8+arg_8], rbx
0x180040b39  push    rbp
0x180040b3a  push    rdi
0x180040b3b  push    r14
0x180040b3d  lea     rbp, [rsp-160h]
0x180040b45  sub     rsp, 260h
0x180040b4c  mov     rax, cs:__security_cookie
0x180040b53  xor     rax, rsp
0x180040b56  mov     [rbp+170h+var_20], rax
0x180040b5d  mov     rdi, r8
0x180040b60  mov     qword ptr [r8], 0
0x180040b67  mov     r8, rcx; unsigned __int16 *
0x180040b6a  mov     r14d, 104h
0x180040b70  mov     edx, r14d; unsigned __int64
0x180040b73  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180040b78  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180040b7d  lea     r8, aP0; "_p0"
0x180040b84  mov     edx, r14d; unsigned __int64
0x180040b87  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180040b8c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180040b91  lea     r8, [rsp+270h+Name]; lpName
0x180040b96  xor     edx, edx; bInheritHandle
0x180040b98  mov     ecx, 1F0003h; dwDesiredAccess
0x180040b9d  call    cs:__imp_OpenSemaphoreW
0x180040ba3  mov     [rsp+270h+var_240], rax
0x180040ba8  test    rax, rax
0x180040bab  jnz     short loc_180040BD3
0x180040bad  call    cs:__imp_GetLastError
0x180040bb3  cmp     eax, 2
0x180040bb6  jz      loc_180040CB3
0x180040bbc  mov     rcx, [rbp+178h]; this
0x180040bc3  lea     edx, [r14-34h]; void *
0x180040bc7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180040bcc  mov     ebx, eax
0x180040bce  jmp     loc_180040CB5
0x180040bd3  lea     rdx, [rsp+270h+var_24C]; int *
0x180040bd8  mov     [rsp+270h+var_24C], 0
0x180040be0  mov     rcx, rax; hHandle
0x180040be3  mov     [rsp+270h+var_250], 0; int
0x180040beb  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180040bf0  mov     ebx, eax
0x180040bf2  test    eax, eax
0x180040bf4  jns     short loc_180040C16
0x180040bf6  mov     rcx, [rbp+178h]; this
0x180040bfd  lea     r8, aWil; "wil"
0x180040c04  mov     r9d, eax; char *
0x180040c07  mov     edx, 0D6h; void *
0x180040c0c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040c11  jmp     loc_180040CB5
0x180040c16  lea     r8, asc_1800909A0; "h"
0x180040c1d  mov     rdx, r14; unsigned __int64
0x180040c20  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180040c25  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180040c2a  lea     r8, [rsp+270h+Name]; lpName
0x180040c2f  xor     edx, edx; bInheritHandle
0x180040c31  mov     ecx, 1F0003h; dwDesiredAccess
0x180040c36  call    cs:__imp_OpenSemaphoreW
0x180040c3c  mov     [rsp+270h+var_248], rax
0x180040c41  test    rax, rax
0x180040c44  jnz     short loc_180040C65
0x180040c46  mov     rcx, [rbp+178h]; this
0x180040c4d  mov     edx, 0DCh; void *
0x180040c52  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180040c57  mov     ebx, eax
0x180040c59  lea     rcx, [rsp+270h+var_248]
0x180040c5e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180040c63  jmp     short loc_180040CB5
0x180040c65  lea     rdx, [rsp+270h+var_250]; int *
0x180040c6a  mov     rcx, rax; hHandle
0x180040c6d  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180040c72  mov     ebx, eax
0x180040c74  test    eax, eax
0x180040c76  jns     short loc_180040C95
0x180040c78  mov     rcx, [rbp+178h]; this
0x180040c7f  lea     r8, aWil; "wil"
0x180040c86  mov     r9d, eax; char *
0x180040c89  mov     edx, 0DEh; void *
0x180040c8e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040c93  jmp     short loc_180040C59
0x180040c95  lea     rcx, [rsp+270h+var_248]
0x180040c9a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180040c9f  movsxd  rcx, [rsp+270h+var_250]
0x180040ca4  movsxd  rax, [rsp+270h+var_24C]
0x180040ca9  shl     rcx, 1Fh
0x180040cad  or      rcx, rax
0x180040cb0  mov     [rdi], rcx
0x180040cb3  xor     ebx, ebx
0x180040cb5  lea     rcx, [rsp+270h+var_240]
0x180040cba  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180040cbf  mov     eax, ebx
0x180040cc1  mov     rcx, [rbp+170h+var_20]
0x180040cc8  xor     rcx, rsp; StackCookie
0x180040ccb  call    __security_check_cookie
0x180040cd0  mov     rbx, [rsp+270h+arg_8]
0x180040cd8  add     rsp, 260h
0x180040cdf  pop     r14
0x180040ce1  pop     rdi
0x180040ce2  pop     rbp
0x180040ce3  retn
```
