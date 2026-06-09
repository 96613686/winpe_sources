# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18001ebc0`
- end: `0x18001ed78`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18001eb3c`

## callees

- `0x180003110`
- `0x18000e5ac`
- `0x18001b6cc`
- `0x18001c888`
- `0x18001e06c`
- `0x18001e724`
- `0x18001e7a0`
- `0x18001ebc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001ec24`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001ecc2`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001ec24`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001ecc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ec34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ec34`

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
  const char *v7; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned __int64 v10; // rdx
  HANDLE v11; // rax
  const char *v12; // r9
  int v13; // eax
  int v15; // [rsp+20h] [rbp-E0h] BYREF
  int v16; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v17; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v18[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v18[0] = v6;
  if ( v6 )
  {
    v16 = 0;
    v15 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v16);
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
    StringCchCatW(Name, v10, L"h");
    v11 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v17 = v11;
    if ( v11 )
    {
      v13 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v11, &v15);
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
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v12);
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
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v7);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v18);
  return LastError;
}

```

## disassembly

```asm
0x18001ebc0  mov     [rsp-8+arg_8], rbx
0x18001ebc5  mov     [rsp-8+arg_18], rdi
0x18001ebca  push    rbp
0x18001ebcb  lea     rbp, [rsp-160h]
0x18001ebd3  sub     rsp, 260h
0x18001ebda  mov     rax, cs:__security_cookie
0x18001ebe1  xor     rax, rsp
0x18001ebe4  mov     [rbp+160h+var_10], rax
0x18001ebeb  mov     rdi, r8
0x18001ebee  mov     qword ptr [r8], 0
0x18001ebf5  mov     r8, rcx; unsigned __int16 *
0x18001ebf8  mov     edx, 104h; unsigned __int64
0x18001ebfd  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18001ec02  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001ec07  lea     r8, aP0; "_p0"
0x18001ec0e  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18001ec13  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001ec18  lea     r8, [rsp+260h+Name]; lpName
0x18001ec1d  xor     edx, edx; bInheritHandle
0x18001ec1f  mov     ecx, 1F0003h; dwDesiredAccess
0x18001ec24  call    cs:__imp_OpenSemaphoreW
0x18001ec2a  mov     [rsp+260h+var_230], rax
0x18001ec2f  test    rax, rax
0x18001ec32  jnz     short loc_18001EC62
0x18001ec34  call    cs:__imp_GetLastError
0x18001ec3a  cmp     eax, 2
0x18001ec3d  jz      loc_18001ED46
0x18001ec43  mov     rcx, [rbp+168h]; this
0x18001ec4a  lea     r8, aWil; "wil"
0x18001ec51  mov     edx, 0D0h; void *
0x18001ec56  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001ec5b  mov     ebx, eax
0x18001ec5d  jmp     loc_18001ED48
0x18001ec62  lea     rdx, [rsp+260h+var_23C]; int *
0x18001ec67  mov     [rsp+260h+var_23C], 0
0x18001ec6f  mov     rcx, rax; hHandle
0x18001ec72  mov     [rsp+260h+var_240], 0; int
0x18001ec7a  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001ec7f  mov     ebx, eax
0x18001ec81  test    eax, eax
0x18001ec83  jns     short loc_18001ECA5
0x18001ec85  mov     rcx, [rbp+168h]; this
0x18001ec8c  lea     r8, aWil; "wil"
0x18001ec93  mov     r9d, eax; char *
0x18001ec96  mov     edx, 0D6h; void *
0x18001ec9b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001eca0  jmp     loc_18001ED48
0x18001eca5  lea     r8, asc_180060170; "h"
0x18001ecac  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18001ecb1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001ecb6  lea     r8, [rsp+260h+Name]; lpName
0x18001ecbb  xor     edx, edx; bInheritHandle
0x18001ecbd  mov     ecx, 1F0003h; dwDesiredAccess
0x18001ecc2  call    cs:__imp_OpenSemaphoreW
0x18001ecc8  mov     [rsp+260h+var_238], rax
0x18001eccd  test    rax, rax
0x18001ecd0  jnz     short loc_18001ECF8
0x18001ecd2  mov     rcx, [rbp+168h]; this
0x18001ecd9  lea     r8, aWil; "wil"
0x18001ece0  mov     edx, 0DCh; void *
0x18001ece5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001ecea  mov     ebx, eax
0x18001ecec  lea     rcx, [rsp+260h+var_238]
0x18001ecf1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001ecf6  jmp     short loc_18001ED48
0x18001ecf8  lea     rdx, [rsp+260h+var_240]; int *
0x18001ecfd  mov     rcx, rax; hHandle
0x18001ed00  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001ed05  mov     ebx, eax
0x18001ed07  test    eax, eax
0x18001ed09  jns     short loc_18001ED28
0x18001ed0b  mov     rcx, [rbp+168h]; this
0x18001ed12  lea     r8, aWil; "wil"
0x18001ed19  mov     r9d, eax; char *
0x18001ed1c  mov     edx, 0DEh; void *
0x18001ed21  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ed26  jmp     short loc_18001ECEC
0x18001ed28  lea     rcx, [rsp+260h+var_238]
0x18001ed2d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001ed32  movsxd  rcx, [rsp+260h+var_240]
0x18001ed37  movsxd  rax, [rsp+260h+var_23C]
0x18001ed3c  shl     rcx, 1Fh
0x18001ed40  or      rcx, rax
0x18001ed43  mov     [rdi], rcx
0x18001ed46  xor     ebx, ebx
0x18001ed48  lea     rcx, [rsp+260h+var_230]
0x18001ed4d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001ed52  mov     eax, ebx
0x18001ed54  mov     rcx, [rbp+160h+var_10]
0x18001ed5b  xor     rcx, rsp; StackCookie
0x18001ed5e  call    __security_check_cookie
0x18001ed63  lea     r11, [rsp+260h+var_s0]
0x18001ed6b  mov     rbx, [r11+18h]
0x18001ed6f  mov     rdi, [r11+28h]
0x18001ed73  mov     rsp, r11
0x18001ed76  pop     rbp
0x18001ed77  retn
```
