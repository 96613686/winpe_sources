# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000b290`
- end: `0x18000b42c`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000b21c`

## callees

- `0x180004410`
- `0x180004734`
- `0x180005320`
- `0x180007310`
- `0x180008bfc`
- `0x18000a39c`
- `0x18000ae10`
- `0x18000b290`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b2f4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b384`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b2f4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b384`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b304`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b304`

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
0x18000b290  mov     [rsp-8+arg_8], rbx
0x18000b295  mov     [rsp-8+arg_18], rdi
0x18000b29a  push    rbp
0x18000b29b  lea     rbp, [rsp-160h]
0x18000b2a3  sub     rsp, 260h
0x18000b2aa  mov     rax, cs:__security_cookie
0x18000b2b1  xor     rax, rsp
0x18000b2b4  mov     [rbp+160h+var_10], rax
0x18000b2bb  mov     rdi, r8
0x18000b2be  mov     qword ptr [r8], 0
0x18000b2c5  mov     r8, rcx; unsigned __int16 *
0x18000b2c8  mov     edx, 104h; unsigned __int64
0x18000b2cd  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000b2d2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000b2d7  lea     r8, aP0; "_p0"
0x18000b2de  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000b2e3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000b2e8  lea     r8, [rsp+260h+Name]; lpName
0x18000b2ed  xor     edx, edx; bInheritHandle
0x18000b2ef  mov     ecx, 1F0003h; dwDesiredAccess
0x18000b2f4  call    cs:__imp_OpenSemaphoreW
0x18000b2fa  mov     [rsp+260h+var_230], rax
0x18000b2ff  test    rax, rax
0x18000b302  jnz     short loc_18000B32B
0x18000b304  call    cs:__imp_GetLastError
0x18000b30a  cmp     eax, 2
0x18000b30d  jz      loc_18000B3FA
0x18000b313  mov     rcx, [rbp+168h]; this
0x18000b31a  mov     edx, 0D0h; void *
0x18000b31f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b324  mov     ebx, eax
0x18000b326  jmp     loc_18000B3FC
0x18000b32b  lea     rdx, [rsp+260h+var_23C]; int *
0x18000b330  mov     [rsp+260h+var_23C], 0
0x18000b338  mov     rcx, rax; hHandle
0x18000b33b  mov     [rsp+260h+var_240], 0; int
0x18000b343  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000b348  mov     ebx, eax
0x18000b34a  test    eax, eax
0x18000b34c  jns     short loc_18000B367
0x18000b34e  mov     rcx, [rbp+168h]; this
0x18000b355  mov     r9d, eax; char *
0x18000b358  mov     edx, 0D6h; void *
0x18000b35d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b362  jmp     loc_18000B3FC
0x18000b367  lea     r8, asc_180018620; "h"
0x18000b36e  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000b373  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000b378  lea     r8, [rsp+260h+Name]; lpName
0x18000b37d  xor     edx, edx; bInheritHandle
0x18000b37f  mov     ecx, 1F0003h; dwDesiredAccess
0x18000b384  call    cs:__imp_OpenSemaphoreW
0x18000b38a  mov     [rsp+260h+var_238], rax
0x18000b38f  test    rax, rax
0x18000b392  jnz     short loc_18000B3B3
0x18000b394  mov     rcx, [rbp+168h]; this
0x18000b39b  mov     edx, 0DCh; void *
0x18000b3a0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b3a5  mov     ebx, eax
0x18000b3a7  lea     rcx, [rsp+260h+var_238]
0x18000b3ac  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000b3b1  jmp     short loc_18000B3FC
0x18000b3b3  lea     rdx, [rsp+260h+var_240]; int *
0x18000b3b8  mov     rcx, rax; hHandle
0x18000b3bb  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000b3c0  mov     ebx, eax
0x18000b3c2  test    eax, eax
0x18000b3c4  jns     short loc_18000B3DC
0x18000b3c6  mov     rcx, [rbp+168h]; this
0x18000b3cd  mov     r9d, eax; char *
0x18000b3d0  mov     edx, 0DEh; void *
0x18000b3d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b3da  jmp     short loc_18000B3A7
0x18000b3dc  lea     rcx, [rsp+260h+var_238]
0x18000b3e1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000b3e6  movsxd  rcx, [rsp+260h+var_240]
0x18000b3eb  movsxd  rax, [rsp+260h+var_23C]
0x18000b3f0  shl     rcx, 1Fh
0x18000b3f4  or      rcx, rax
0x18000b3f7  mov     [rdi], rcx
0x18000b3fa  xor     ebx, ebx
0x18000b3fc  lea     rcx, [rsp+260h+var_230]
0x18000b401  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000b406  mov     eax, ebx
0x18000b408  mov     rcx, [rbp+160h+var_10]
0x18000b40f  xor     rcx, rsp; StackCookie
0x18000b412  call    __security_check_cookie
0x18000b417  lea     r11, [rsp+260h+var_s0]
0x18000b41f  mov     rbx, [r11+18h]
0x18000b423  mov     rdi, [r11+28h]
0x18000b427  mov     rsp, r11
0x18000b42a  pop     rbp
0x18000b42b  retn
```
