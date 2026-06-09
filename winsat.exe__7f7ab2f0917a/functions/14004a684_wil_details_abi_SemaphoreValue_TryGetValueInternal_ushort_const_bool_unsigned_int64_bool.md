# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x14004a684`
- end: `0x14004a826`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `418`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x14004a610`

## callees

- `0x14003527c`
- `0x140040bf0`
- `0x1400451c8`
- `0x140047da8`
- `0x140049adc`
- `0x140049afc`
- `0x14004a684`
- `0x140113220`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14004a6fd`
- `KERNEL32!GetLastError` at `0x14004a6fd`
- `KERNEL32!OpenSemaphoreW` at `0x14004a6ed`
- `KERNEL32!OpenSemaphoreW` at `0x14004a77f`
- `KERNEL32!OpenSemaphoreW` at `0x14004a6ed`
- `KERNEL32!OpenSemaphoreW` at `0x14004a77f`

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
0x14004a684  mov     [rsp-8+arg_8], rbx
0x14004a689  push    rbp
0x14004a68a  push    rdi
0x14004a68b  push    r14
0x14004a68d  lea     rbp, [rsp-160h]
0x14004a695  sub     rsp, 260h
0x14004a69c  mov     rax, cs:__security_cookie
0x14004a6a3  xor     rax, rsp
0x14004a6a6  mov     [rbp+170h+var_20], rax
0x14004a6ad  mov     rdi, r8
0x14004a6b0  mov     qword ptr [r8], 0
0x14004a6b7  mov     r8, rcx; unsigned __int16 *
0x14004a6ba  mov     r14d, 104h
0x14004a6c0  mov     edx, r14d; unsigned __int64
0x14004a6c3  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x14004a6c8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14004a6cd  lea     r8, aP0; "_p0"
0x14004a6d4  mov     edx, r14d; unsigned __int64
0x14004a6d7  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x14004a6dc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14004a6e1  lea     r8, [rsp+270h+Name]; lpName
0x14004a6e6  xor     edx, edx; bInheritHandle
0x14004a6e8  mov     ecx, 1F0003h; dwDesiredAccess
0x14004a6ed  call    cs:__imp_OpenSemaphoreW
0x14004a6f3  mov     [rsp+270h+var_240], rax
0x14004a6f8  test    rax, rax
0x14004a6fb  jnz     short loc_14004A723
0x14004a6fd  call    cs:__imp_GetLastError
0x14004a703  cmp     eax, 2
0x14004a706  jz      loc_14004A7F5
0x14004a70c  mov     rcx, [rbp+178h]; this
0x14004a713  lea     edx, [r14-34h]; void *
0x14004a717  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14004a71c  mov     ebx, eax
0x14004a71e  jmp     loc_14004A7F7
0x14004a723  lea     rdx, [rsp+270h+var_24C]; int *
0x14004a728  mov     [rsp+270h+var_24C], 0
0x14004a730  mov     rcx, rax; hHandle
0x14004a733  mov     [rsp+270h+var_250], 0; int
0x14004a73b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14004a740  mov     ebx, eax
0x14004a742  test    eax, eax
0x14004a744  jns     short loc_14004A75F
0x14004a746  mov     rcx, [rbp+178h]; this
0x14004a74d  mov     r9d, eax; char *
0x14004a750  mov     edx, 0D6h; void *
0x14004a755  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004a75a  jmp     loc_14004A7F7
0x14004a75f  lea     r8, asc_14013B0B8; "h"
0x14004a766  mov     rdx, r14; unsigned __int64
0x14004a769  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x14004a76e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14004a773  lea     r8, [rsp+270h+Name]; lpName
0x14004a778  xor     edx, edx; bInheritHandle
0x14004a77a  mov     ecx, 1F0003h; dwDesiredAccess
0x14004a77f  call    cs:__imp_OpenSemaphoreW
0x14004a785  mov     [rsp+270h+var_248], rax
0x14004a78a  test    rax, rax
0x14004a78d  jnz     short loc_14004A7AE
0x14004a78f  mov     rcx, [rbp+178h]; this
0x14004a796  mov     edx, 0DCh; void *
0x14004a79b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14004a7a0  mov     ebx, eax
0x14004a7a2  lea     rcx, [rsp+270h+var_248]
0x14004a7a7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14004a7ac  jmp     short loc_14004A7F7
0x14004a7ae  lea     rdx, [rsp+270h+var_250]; int *
0x14004a7b3  mov     rcx, rax; hHandle
0x14004a7b6  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14004a7bb  mov     ebx, eax
0x14004a7bd  test    eax, eax
0x14004a7bf  jns     short loc_14004A7D7
0x14004a7c1  mov     rcx, [rbp+178h]; this
0x14004a7c8  mov     r9d, eax; char *
0x14004a7cb  mov     edx, 0DEh; void *
0x14004a7d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004a7d5  jmp     short loc_14004A7A2
0x14004a7d7  lea     rcx, [rsp+270h+var_248]
0x14004a7dc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14004a7e1  movsxd  rcx, [rsp+270h+var_250]
0x14004a7e6  movsxd  rax, [rsp+270h+var_24C]
0x14004a7eb  shl     rcx, 1Fh
0x14004a7ef  or      rcx, rax
0x14004a7f2  mov     [rdi], rcx
0x14004a7f5  xor     ebx, ebx
0x14004a7f7  lea     rcx, [rsp+270h+var_240]
0x14004a7fc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14004a801  mov     eax, ebx
0x14004a803  mov     rcx, [rbp+170h+var_20]
0x14004a80a  xor     rcx, rsp; StackCookie
0x14004a80d  call    __security_check_cookie
0x14004a812  mov     rbx, [rsp+270h+arg_8]
0x14004a81a  add     rsp, 260h
0x14004a821  pop     r14
0x14004a823  pop     rdi
0x14004a824  pop     rbp
0x14004a825  retn
```
