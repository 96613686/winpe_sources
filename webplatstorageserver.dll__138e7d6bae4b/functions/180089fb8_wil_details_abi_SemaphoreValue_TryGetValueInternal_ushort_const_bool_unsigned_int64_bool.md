# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180089fb8`
- end: `0x18008a16b`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `435`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180089f34`

## callees

- `0x18004448c`
- `0x180063500`
- `0x180071508`
- `0x180080fb0`
- `0x180089038`
- `0x1800895dc`
- `0x180089eb8`
- `0x180089fb8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18008a017`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18008a0b5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18008a017`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18008a0b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a027`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a027`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
        unsigned __int64 a2,
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
  StringCchCopyW(Name, a2, a1);
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
0x180089fb8  mov     [rsp-8+arg_8], rbx
0x180089fbd  mov     [rsp-8+arg_18], rdi
0x180089fc2  push    rbp
0x180089fc3  lea     rbp, [rsp-160h]
0x180089fcb  sub     rsp, 260h
0x180089fd2  mov     rax, cs:__security_cookie
0x180089fd9  xor     rax, rsp
0x180089fdc  mov     [rbp+160h+var_10], rax
0x180089fe3  mov     rdi, r8
0x180089fe6  mov     qword ptr [r8], 0
0x180089fed  mov     r8, rcx; unsigned __int16 *
0x180089ff0  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180089ff5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180089ffa  lea     r8, aP0; "_p0"
0x18008a001  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18008a006  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18008a00b  lea     r8, [rsp+260h+Name]; lpName
0x18008a010  xor     edx, edx; bInheritHandle
0x18008a012  mov     ecx, 1F0003h; dwDesiredAccess
0x18008a017  call    cs:__imp_OpenSemaphoreW
0x18008a01d  mov     [rsp+260h+var_230], rax
0x18008a022  test    rax, rax
0x18008a025  jnz     short loc_18008A055
0x18008a027  call    cs:__imp_GetLastError
0x18008a02d  cmp     eax, 2
0x18008a030  jz      loc_18008A139
0x18008a036  mov     rcx, [rbp+168h]; this
0x18008a03d  lea     r8, aWil; "wil"
0x18008a044  mov     edx, 0D0h; void *
0x18008a049  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18008a04e  mov     ebx, eax
0x18008a050  jmp     loc_18008A13B
0x18008a055  lea     rdx, [rsp+260h+var_23C]; int *
0x18008a05a  mov     [rsp+260h+var_23C], 0
0x18008a062  mov     rcx, rax; hHandle
0x18008a065  mov     [rsp+260h+var_240], 0; int
0x18008a06d  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18008a072  mov     ebx, eax
0x18008a074  test    eax, eax
0x18008a076  jns     short loc_18008A098
0x18008a078  mov     rcx, [rbp+168h]; this
0x18008a07f  lea     r8, aWil; "wil"
0x18008a086  mov     r9d, eax; char *
0x18008a089  mov     edx, 0D6h; void *
0x18008a08e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008a093  jmp     loc_18008A13B
0x18008a098  lea     r8, asc_1800D9878; "h"
0x18008a09f  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18008a0a4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18008a0a9  lea     r8, [rsp+260h+Name]; lpName
0x18008a0ae  xor     edx, edx; bInheritHandle
0x18008a0b0  mov     ecx, 1F0003h; dwDesiredAccess
0x18008a0b5  call    cs:__imp_OpenSemaphoreW
0x18008a0bb  mov     [rsp+260h+var_238], rax
0x18008a0c0  test    rax, rax
0x18008a0c3  jnz     short loc_18008A0EB
0x18008a0c5  mov     rcx, [rbp+168h]; this
0x18008a0cc  lea     r8, aWil; "wil"
0x18008a0d3  mov     edx, 0DCh; void *
0x18008a0d8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18008a0dd  mov     ebx, eax
0x18008a0df  lea     rcx, [rsp+260h+var_238]
0x18008a0e4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18008a0e9  jmp     short loc_18008A13B
0x18008a0eb  lea     rdx, [rsp+260h+var_240]; int *
0x18008a0f0  mov     rcx, rax; hHandle
0x18008a0f3  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18008a0f8  mov     ebx, eax
0x18008a0fa  test    eax, eax
0x18008a0fc  jns     short loc_18008A11B
0x18008a0fe  mov     rcx, [rbp+168h]; this
0x18008a105  lea     r8, aWil; "wil"
0x18008a10c  mov     r9d, eax; char *
0x18008a10f  mov     edx, 0DEh; void *
0x18008a114  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008a119  jmp     short loc_18008A0DF
0x18008a11b  lea     rcx, [rsp+260h+var_238]
0x18008a120  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18008a125  movsxd  rcx, [rsp+260h+var_240]
0x18008a12a  movsxd  rax, [rsp+260h+var_23C]
0x18008a12f  shl     rcx, 1Fh
0x18008a133  or      rcx, rax
0x18008a136  mov     [rdi], rcx
0x18008a139  xor     ebx, ebx
0x18008a13b  lea     rcx, [rsp+260h+var_230]
0x18008a140  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18008a145  mov     eax, ebx
0x18008a147  mov     rcx, [rbp+160h+var_10]
0x18008a14e  xor     rcx, rsp; StackCookie
0x18008a151  call    __security_check_cookie
0x18008a156  lea     r11, [rsp+260h+var_s0]
0x18008a15e  mov     rbx, [r11+18h]
0x18008a162  mov     rdi, [r11+28h]
0x18008a166  mov     rsp, r11
0x18008a169  pop     rbp
0x18008a16a  retn
```
