# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800218b0`
- end: `0x180021a6e`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `446`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18002182c`

## callees

- `0x1800140f0`
- `0x180017308`
- `0x18001d6f8`
- `0x18001ee70`
- `0x180020d80`
- `0x180020da0`
- `0x1800218b0`
- `0x180032c90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021929`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021929`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180021919`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800219b9`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180021919`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800219b9`

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
0x1800218b0  mov     [rsp-8+arg_8], rbx
0x1800218b5  push    rbp
0x1800218b6  push    rdi
0x1800218b7  push    r14
0x1800218b9  lea     rbp, [rsp-160h]
0x1800218c1  sub     rsp, 260h
0x1800218c8  mov     rax, cs:__security_cookie
0x1800218cf  xor     rax, rsp
0x1800218d2  mov     [rbp+170h+var_20], rax
0x1800218d9  mov     rdi, r8
0x1800218dc  mov     qword ptr [r8], 0
0x1800218e3  mov     r8, rcx; unsigned __int16 *
0x1800218e6  mov     r14d, 104h
0x1800218ec  mov     edx, r14d; unsigned __int64
0x1800218ef  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800218f4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800218f9  lea     r8, aP0; "_p0"
0x180021900  mov     edx, r14d; unsigned __int64
0x180021903  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180021908  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002190d  lea     r8, [rsp+270h+Name]; lpName
0x180021912  xor     edx, edx; bInheritHandle
0x180021914  mov     ecx, 1F0003h; dwDesiredAccess
0x180021919  call    cs:__imp_OpenSemaphoreW
0x18002191f  mov     [rsp+270h+var_240], rax
0x180021924  test    rax, rax
0x180021927  jnz     short loc_180021956
0x180021929  call    cs:__imp_GetLastError
0x18002192f  cmp     eax, 2
0x180021932  jz      loc_180021A3D
0x180021938  mov     rcx, [rbp+178h]; this
0x18002193f  lea     r8, aWil; "wil"
0x180021946  lea     edx, [r14-34h]; void *
0x18002194a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002194f  mov     ebx, eax
0x180021951  jmp     loc_180021A3F
0x180021956  lea     rdx, [rsp+270h+var_24C]; int *
0x18002195b  mov     [rsp+270h+var_24C], 0
0x180021963  mov     rcx, rax; hHandle
0x180021966  mov     [rsp+270h+var_250], 0; int
0x18002196e  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180021973  mov     ebx, eax
0x180021975  test    eax, eax
0x180021977  jns     short loc_180021999
0x180021979  mov     rcx, [rbp+178h]; this
0x180021980  lea     r8, aWil; "wil"
0x180021987  mov     r9d, eax; char *
0x18002198a  mov     edx, 0D6h; void *
0x18002198f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021994  jmp     loc_180021A3F
0x180021999  lea     r8, asc_180037768; "h"
0x1800219a0  mov     rdx, r14; unsigned __int64
0x1800219a3  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800219a8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800219ad  lea     r8, [rsp+270h+Name]; lpName
0x1800219b2  xor     edx, edx; bInheritHandle
0x1800219b4  mov     ecx, 1F0003h; dwDesiredAccess
0x1800219b9  call    cs:__imp_OpenSemaphoreW
0x1800219bf  mov     [rsp+270h+var_248], rax
0x1800219c4  test    rax, rax
0x1800219c7  jnz     short loc_1800219EF
0x1800219c9  mov     rcx, [rbp+178h]; this
0x1800219d0  lea     r8, aWil; "wil"
0x1800219d7  mov     edx, 0DCh; void *
0x1800219dc  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800219e1  mov     ebx, eax
0x1800219e3  lea     rcx, [rsp+270h+var_248]
0x1800219e8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800219ed  jmp     short loc_180021A3F
0x1800219ef  lea     rdx, [rsp+270h+var_250]; int *
0x1800219f4  mov     rcx, rax; hHandle
0x1800219f7  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800219fc  mov     ebx, eax
0x1800219fe  test    eax, eax
0x180021a00  jns     short loc_180021A1F
0x180021a02  mov     rcx, [rbp+178h]; this
0x180021a09  lea     r8, aWil; "wil"
0x180021a10  mov     r9d, eax; char *
0x180021a13  mov     edx, 0DEh; void *
0x180021a18  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021a1d  jmp     short loc_1800219E3
0x180021a1f  lea     rcx, [rsp+270h+var_248]
0x180021a24  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180021a29  movsxd  rcx, [rsp+270h+var_250]
0x180021a2e  movsxd  rax, [rsp+270h+var_24C]
0x180021a33  shl     rcx, 1Fh
0x180021a37  or      rcx, rax
0x180021a3a  mov     [rdi], rcx
0x180021a3d  xor     ebx, ebx
0x180021a3f  lea     rcx, [rsp+270h+var_240]
0x180021a44  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180021a49  mov     eax, ebx
0x180021a4b  mov     rcx, [rbp+170h+var_20]
0x180021a52  xor     rcx, rsp; StackCookie
0x180021a55  call    __security_check_cookie
0x180021a5a  mov     rbx, [rsp+270h+arg_8]
0x180021a62  add     rsp, 260h
0x180021a69  pop     r14
0x180021a6b  pop     rdi
0x180021a6c  pop     rbp
0x180021a6d  retn
```
