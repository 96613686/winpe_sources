# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180012f70`
- end: `0x180013137`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `455`
- prototype: `__int64 __fastcall(wchar_t *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180012eec`

## callees

- `0x18000d030`
- `0x180010b08`
- `0x180011a34`
- `0x180012714`
- `0x180012734`
- `0x180012c50`
- `0x180012c9c`
- `0x180012f70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180012fd4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180013074`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180012fd4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180013074`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012fe4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012fe4`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        wchar_t *a1,
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
      goto LABEL_12;
    }
    StringCchCatW(Name, v10, L"h");
    v11 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v17 = v11;
    if ( !v11 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v12);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
      goto LABEL_12;
    }
    v13 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v11, &v15);
    LastError = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v13,
        v15);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
      goto LABEL_12;
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
    *a3 = v16 | (unsigned __int64)((__int64)v15 << 31);
LABEL_11:
    LastError = 0;
    goto LABEL_12;
  }
  if ( GetLastError() == 2 )
    goto LABEL_11;
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v7);
LABEL_12:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v18);
  return LastError;
}

```

## disassembly

```asm
0x180012f70  mov     [rsp-8+arg_8], rbx
0x180012f75  mov     [rsp-8+arg_18], rdi
0x180012f7a  push    rbp
0x180012f7b  lea     rbp, [rsp-160h]
0x180012f83  sub     rsp, 260h
0x180012f8a  mov     rax, cs:__security_cookie
0x180012f91  xor     rax, rsp
0x180012f94  mov     [rbp+160h+var_10], rax
0x180012f9b  mov     rdi, r8
0x180012f9e  mov     qword ptr [r8], 0
0x180012fa5  mov     r8, rcx; wchar_t *
0x180012fa8  mov     edx, 104h; unsigned __int64
0x180012fad  lea     rcx, [rsp+260h+Name]; wchar_t *
0x180012fb2  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180012fb7  lea     r8, aP0; "_p0"
0x180012fbe  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180012fc3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180012fc8  lea     r8, [rsp+260h+Name]; lpName
0x180012fcd  xor     edx, edx; bInheritHandle
0x180012fcf  mov     ecx, 1F0003h; dwDesiredAccess
0x180012fd4  call    cs:__imp_OpenSemaphoreW
0x180012fda  mov     [rsp+260h+var_230], rax
0x180012fdf  test    rax, rax
0x180012fe2  jnz     short loc_180013013
0x180012fe4  call    cs:__imp_GetLastError
0x180012fea  cmp     eax, 2
0x180012fed  jnz     short loc_180012FF4
0x180012fef  jmp     loc_180013105
0x180012ff4  mov     rcx, [rbp+168h]; this
0x180012ffb  lea     r8, aWil; "wil"
0x180013002  mov     edx, 0D0h; void *
0x180013007  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001300c  mov     ebx, eax
0x18001300e  jmp     loc_180013107
0x180013013  mov     [rsp+260h+var_23C], 0
0x18001301b  mov     [rsp+260h+var_240], 0; int
0x180013023  lea     rdx, [rsp+260h+var_23C]; int *
0x180013028  mov     rcx, rax; hHandle
0x18001302b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180013030  mov     ebx, eax
0x180013032  test    eax, eax
0x180013034  jns     short loc_180013057
0x180013036  mov     rcx, [rbp+168h]; this
0x18001303d  mov     r9d, eax; char *
0x180013040  lea     r8, aWil; "wil"
0x180013047  mov     edx, 0D6h; void *
0x18001304c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013051  nop
0x180013052  jmp     loc_180013107
0x180013057  lea     r8, asc_180092A98; "h"
0x18001305e  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180013063  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180013068  lea     r8, [rsp+260h+Name]; lpName
0x18001306d  xor     edx, edx; bInheritHandle
0x18001306f  mov     ecx, 1F0003h; dwDesiredAccess
0x180013074  call    cs:__imp_OpenSemaphoreW
0x18001307a  mov     [rsp+260h+var_238], rax
0x18001307f  test    rax, rax
0x180013082  jnz     short loc_1800130AB
0x180013084  mov     rcx, [rbp+168h]; this
0x18001308b  lea     r8, aWil; "wil"
0x180013092  mov     edx, 0DCh; void *
0x180013097  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001309c  mov     ebx, eax
0x18001309e  lea     rcx, [rsp+260h+var_238]
0x1800130a3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800130a8  nop
0x1800130a9  jmp     short loc_180013107
0x1800130ab  lea     rdx, [rsp+260h+var_240]; int *
0x1800130b0  mov     rcx, rax; hHandle
0x1800130b3  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800130b8  mov     ebx, eax
0x1800130ba  test    eax, eax
0x1800130bc  jns     short loc_1800130E7
0x1800130be  mov     rcx, [rbp+168h]; this
0x1800130c5  mov     r9d, eax; char *
0x1800130c8  lea     r8, aWil; "wil"
0x1800130cf  mov     edx, 0DEh; void *
0x1800130d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800130d9  nop
0x1800130da  lea     rcx, [rsp+260h+var_238]
0x1800130df  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800130e4  nop
0x1800130e5  jmp     short loc_180013107
0x1800130e7  lea     rcx, [rsp+260h+var_238]
0x1800130ec  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800130f1  movsxd  rcx, [rsp+260h+var_240]
0x1800130f6  shl     rcx, 1Fh
0x1800130fa  movsxd  rax, [rsp+260h+var_23C]
0x1800130ff  or      rcx, rax
0x180013102  mov     [rdi], rcx
0x180013105  xor     ebx, ebx
0x180013107  lea     rcx, [rsp+260h+var_230]
0x18001310c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180013111  mov     eax, ebx
0x180013113  mov     rcx, [rbp+160h+var_10]
0x18001311a  xor     rcx, rsp; StackCookie
0x18001311d  call    __security_check_cookie
0x180013122  lea     r11, [rsp+260h+var_s0]
0x18001312a  mov     rbx, [r11+18h]
0x18001312e  mov     rdi, [r11+28h]
0x180013132  mov     rsp, r11
0x180013135  pop     rbp
0x180013136  retn
```
