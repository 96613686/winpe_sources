# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000cc5c`
- end: `0x18000ce1a`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `446`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000cbd8`

## callees

- `0x180007440`
- `0x18000aa20`
- `0x18000b738`
- `0x18000c3b4`
- `0x18000c3d4`
- `0x18000c8f0`
- `0x18000c9e4`
- `0x18000cc5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000ccc5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000cd65`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000ccc5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000cd65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ccd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ccd5`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  HANDLE v5; // rax
  const char *v6; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  HANDLE v9; // rax
  const char *v10; // r9
  int v11; // eax
  int v13; // [rsp+20h] [rbp-E0h] BYREF
  int v14; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v15; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v16[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, 0x104u, L"_p0");
  v5 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v16[0] = v5;
  if ( v5 )
  {
    v14 = 0;
    v13 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &v14);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v13);
      goto LABEL_13;
    }
    StringCchCatW(Name, 0x104u, L"h");
    v9 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v15 = v9;
    if ( v9 )
    {
      v11 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, &v13);
      LastError = v11;
      if ( v11 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v15);
        *a3 = v14 | (unsigned __int64)((__int64)v13 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v11,
        v13);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v10);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v15);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v6);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v16);
  return LastError;
}

```

## disassembly

```asm
0x18000cc5c  mov     [rsp-8+arg_8], rbx
0x18000cc61  push    rbp
0x18000cc62  push    rdi
0x18000cc63  push    r14
0x18000cc65  lea     rbp, [rsp-160h]
0x18000cc6d  sub     rsp, 260h
0x18000cc74  mov     rax, cs:__security_cookie
0x18000cc7b  xor     rax, rsp
0x18000cc7e  mov     [rbp+170h+var_20], rax
0x18000cc85  mov     rdi, r8
0x18000cc88  mov     qword ptr [r8], 0
0x18000cc8f  mov     r8, rcx; unsigned __int16 *
0x18000cc92  mov     r14d, 104h
0x18000cc98  mov     edx, r14d; unsigned __int64
0x18000cc9b  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000cca0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000cca5  lea     r8, aP0; "_p0"
0x18000ccac  mov     edx, r14d; unsigned __int64
0x18000ccaf  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000ccb4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000ccb9  lea     r8, [rsp+270h+Name]; lpName
0x18000ccbe  xor     edx, edx; bInheritHandle
0x18000ccc0  mov     ecx, 1F0003h; dwDesiredAccess
0x18000ccc5  call    cs:__imp_OpenSemaphoreW
0x18000cccb  mov     [rsp+270h+var_240], rax
0x18000ccd0  test    rax, rax
0x18000ccd3  jnz     short loc_18000CD02
0x18000ccd5  call    cs:__imp_GetLastError
0x18000ccdb  cmp     eax, 2
0x18000ccde  jz      loc_18000CDE9
0x18000cce4  mov     rcx, [rbp+178h]; this
0x18000cceb  lea     r8, aWil; "wil"
0x18000ccf2  lea     edx, [r14-34h]; void *
0x18000ccf6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000ccfb  mov     ebx, eax
0x18000ccfd  jmp     loc_18000CDEB
0x18000cd02  lea     rdx, [rsp+270h+var_24C]; int *
0x18000cd07  mov     [rsp+270h+var_24C], 0
0x18000cd0f  mov     rcx, rax; hHandle
0x18000cd12  mov     [rsp+270h+var_250], 0; int
0x18000cd1a  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000cd1f  mov     ebx, eax
0x18000cd21  test    eax, eax
0x18000cd23  jns     short loc_18000CD45
0x18000cd25  mov     rcx, [rbp+178h]; this
0x18000cd2c  lea     r8, aWil; "wil"
0x18000cd33  mov     r9d, eax; char *
0x18000cd36  mov     edx, 0D6h; void *
0x18000cd3b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cd40  jmp     loc_18000CDEB
0x18000cd45  lea     r8, asc_18009A678; "h"
0x18000cd4c  mov     rdx, r14; unsigned __int64
0x18000cd4f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000cd54  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000cd59  lea     r8, [rsp+270h+Name]; lpName
0x18000cd5e  xor     edx, edx; bInheritHandle
0x18000cd60  mov     ecx, 1F0003h; dwDesiredAccess
0x18000cd65  call    cs:__imp_OpenSemaphoreW
0x18000cd6b  mov     [rsp+270h+var_248], rax
0x18000cd70  test    rax, rax
0x18000cd73  jnz     short loc_18000CD9B
0x18000cd75  mov     rcx, [rbp+178h]; this
0x18000cd7c  lea     r8, aWil; "wil"
0x18000cd83  mov     edx, 0DCh; void *
0x18000cd88  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000cd8d  mov     ebx, eax
0x18000cd8f  lea     rcx, [rsp+270h+var_248]
0x18000cd94  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000cd99  jmp     short loc_18000CDEB
0x18000cd9b  lea     rdx, [rsp+270h+var_250]; int *
0x18000cda0  mov     rcx, rax; hHandle
0x18000cda3  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000cda8  mov     ebx, eax
0x18000cdaa  test    eax, eax
0x18000cdac  jns     short loc_18000CDCB
0x18000cdae  mov     rcx, [rbp+178h]; this
0x18000cdb5  lea     r8, aWil; "wil"
0x18000cdbc  mov     r9d, eax; char *
0x18000cdbf  mov     edx, 0DEh; void *
0x18000cdc4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cdc9  jmp     short loc_18000CD8F
0x18000cdcb  lea     rcx, [rsp+270h+var_248]
0x18000cdd0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000cdd5  movsxd  rcx, [rsp+270h+var_250]
0x18000cdda  movsxd  rax, [rsp+270h+var_24C]
0x18000cddf  shl     rcx, 1Fh
0x18000cde3  or      rcx, rax
0x18000cde6  mov     [rdi], rcx
0x18000cde9  xor     ebx, ebx
0x18000cdeb  lea     rcx, [rsp+270h+var_240]
0x18000cdf0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000cdf5  mov     eax, ebx
0x18000cdf7  mov     rcx, [rbp+170h+var_20]
0x18000cdfe  xor     rcx, rsp; StackCookie
0x18000ce01  call    __security_check_cookie
0x18000ce06  mov     rbx, [rsp+270h+arg_8]
0x18000ce0e  add     rsp, 260h
0x18000ce15  pop     r14
0x18000ce17  pop     rdi
0x18000ce18  pop     rbp
0x18000ce19  retn
```
