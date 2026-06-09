# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180087574`
- end: `0x180087716`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `418`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180084fac`

## callees

- `0x1800107e8`
- `0x1800391cc`
- `0x180084f4c`
- `0x18008618c`
- `0x180086918`
- `0x180086938`
- `0x180087574`
- `0x18009a520`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800875ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800875ed`
- `KERNEL32!OpenSemaphoreW` at `0x1800875dd`
- `KERNEL32!OpenSemaphoreW` at `0x18008766f`
- `KERNEL32!OpenSemaphoreW` at `0x1800875dd`
- `KERNEL32!OpenSemaphoreW` at `0x18008766f`

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
0x180087574  mov     [rsp-8+arg_8], rbx
0x180087579  push    rbp
0x18008757a  push    rdi
0x18008757b  push    r14
0x18008757d  lea     rbp, [rsp-160h]
0x180087585  sub     rsp, 260h
0x18008758c  mov     rax, cs:__security_cookie
0x180087593  xor     rax, rsp
0x180087596  mov     [rbp+170h+var_20], rax
0x18008759d  mov     rdi, r8
0x1800875a0  mov     qword ptr [r8], 0
0x1800875a7  mov     r8, rcx; unsigned __int16 *
0x1800875aa  mov     r14d, 104h
0x1800875b0  mov     edx, r14d; unsigned __int64
0x1800875b3  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800875b8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800875bd  lea     r8, aP0; "_p0"
0x1800875c4  mov     edx, r14d; unsigned __int64
0x1800875c7  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800875cc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800875d1  lea     r8, [rsp+270h+Name]; lpName
0x1800875d6  xor     edx, edx; bInheritHandle
0x1800875d8  mov     ecx, 1F0003h; dwDesiredAccess
0x1800875dd  call    cs:__imp_OpenSemaphoreW
0x1800875e3  mov     [rsp+270h+var_240], rax
0x1800875e8  test    rax, rax
0x1800875eb  jnz     short loc_180087613
0x1800875ed  call    cs:__imp_GetLastError
0x1800875f3  cmp     eax, 2
0x1800875f6  jz      loc_1800876E5
0x1800875fc  mov     rcx, [rbp+178h]; this
0x180087603  lea     edx, [r14-34h]; void *
0x180087607  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18008760c  mov     ebx, eax
0x18008760e  jmp     loc_1800876E7
0x180087613  lea     rdx, [rsp+270h+var_24C]; int *
0x180087618  mov     [rsp+270h+var_24C], 0
0x180087620  mov     rcx, rax; hHandle
0x180087623  mov     [rsp+270h+var_250], 0; int
0x18008762b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180087630  mov     ebx, eax
0x180087632  test    eax, eax
0x180087634  jns     short loc_18008764F
0x180087636  mov     rcx, [rbp+178h]; this
0x18008763d  mov     r9d, eax; char *
0x180087640  mov     edx, 0D6h; void *
0x180087645  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008764a  jmp     loc_1800876E7
0x18008764f  lea     r8, asc_1800BB6B8; "h"
0x180087656  mov     rdx, r14; unsigned __int64
0x180087659  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18008765e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180087663  lea     r8, [rsp+270h+Name]; lpName
0x180087668  xor     edx, edx; bInheritHandle
0x18008766a  mov     ecx, 1F0003h; dwDesiredAccess
0x18008766f  call    cs:__imp_OpenSemaphoreW
0x180087675  mov     [rsp+270h+var_248], rax
0x18008767a  test    rax, rax
0x18008767d  jnz     short loc_18008769E
0x18008767f  mov     rcx, [rbp+178h]; this
0x180087686  mov     edx, 0DCh; void *
0x18008768b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180087690  mov     ebx, eax
0x180087692  lea     rcx, [rsp+270h+var_248]
0x180087697  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18008769c  jmp     short loc_1800876E7
0x18008769e  lea     rdx, [rsp+270h+var_250]; int *
0x1800876a3  mov     rcx, rax; hHandle
0x1800876a6  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800876ab  mov     ebx, eax
0x1800876ad  test    eax, eax
0x1800876af  jns     short loc_1800876C7
0x1800876b1  mov     rcx, [rbp+178h]; this
0x1800876b8  mov     r9d, eax; char *
0x1800876bb  mov     edx, 0DEh; void *
0x1800876c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800876c5  jmp     short loc_180087692
0x1800876c7  lea     rcx, [rsp+270h+var_248]
0x1800876cc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800876d1  movsxd  rcx, [rsp+270h+var_250]
0x1800876d6  movsxd  rax, [rsp+270h+var_24C]
0x1800876db  shl     rcx, 1Fh
0x1800876df  or      rcx, rax
0x1800876e2  mov     [rdi], rcx
0x1800876e5  xor     ebx, ebx
0x1800876e7  lea     rcx, [rsp+270h+var_240]
0x1800876ec  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800876f1  mov     eax, ebx
0x1800876f3  mov     rcx, [rbp+170h+var_20]
0x1800876fa  xor     rcx, rsp; StackCookie
0x1800876fd  call    __security_check_cookie
0x180087702  mov     rbx, [rsp+270h+arg_8]
0x18008770a  add     rsp, 260h
0x180087711  pop     r14
0x180087713  pop     rdi
0x180087714  pop     rbp
0x180087715  retn
```
