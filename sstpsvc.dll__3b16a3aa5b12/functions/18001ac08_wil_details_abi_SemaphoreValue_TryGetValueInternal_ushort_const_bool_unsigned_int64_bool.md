# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18001ac08`
- end: `0x18001ad9f`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `407`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18001ab94`

## callees

- `0x1800164bc`
- `0x18001754c`
- `0x180018944`
- `0x18001a334`
- `0x18001a354`
- `0x18001a804`
- `0x18001ac08`
- `0x18001bcf0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001ac67`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001acf7`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001ac67`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001acf7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ac77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ac77`

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
  StringCchCopyW(Name, a2, a1);
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
0x18001ac08  mov     [rsp-8+arg_8], rbx
0x18001ac0d  mov     [rsp-8+arg_18], rdi
0x18001ac12  push    rbp
0x18001ac13  lea     rbp, [rsp-160h]
0x18001ac1b  sub     rsp, 260h
0x18001ac22  mov     rax, cs:__security_cookie
0x18001ac29  xor     rax, rsp
0x18001ac2c  mov     [rbp+160h+var_10], rax
0x18001ac33  mov     rdi, r8
0x18001ac36  mov     qword ptr [r8], 0
0x18001ac3d  mov     r8, rcx; unsigned __int16 *
0x18001ac40  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18001ac45  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001ac4a  lea     r8, aP0; "_p0"
0x18001ac51  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18001ac56  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001ac5b  lea     r8, [rsp+260h+Name]; lpName
0x18001ac60  xor     edx, edx; bInheritHandle
0x18001ac62  mov     ecx, 1F0003h; dwDesiredAccess
0x18001ac67  call    cs:__imp_OpenSemaphoreW
0x18001ac6d  mov     [rsp+260h+var_230], rax
0x18001ac72  test    rax, rax
0x18001ac75  jnz     short loc_18001AC9E
0x18001ac77  call    cs:__imp_GetLastError
0x18001ac7d  cmp     eax, 2
0x18001ac80  jz      loc_18001AD6D
0x18001ac86  mov     rcx, [rbp+168h]; this
0x18001ac8d  mov     edx, 0D0h; void *
0x18001ac92  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001ac97  mov     ebx, eax
0x18001ac99  jmp     loc_18001AD6F
0x18001ac9e  lea     rdx, [rsp+260h+var_23C]; int *
0x18001aca3  mov     [rsp+260h+var_23C], 0
0x18001acab  mov     rcx, rax; hHandle
0x18001acae  mov     [rsp+260h+var_240], 0; int
0x18001acb6  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001acbb  mov     ebx, eax
0x18001acbd  test    eax, eax
0x18001acbf  jns     short loc_18001ACDA
0x18001acc1  mov     rcx, [rbp+168h]; this
0x18001acc8  mov     r9d, eax; char *
0x18001accb  mov     edx, 0D6h; void *
0x18001acd0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001acd5  jmp     loc_18001AD6F
0x18001acda  lea     r8, asc_180027B20; "h"
0x18001ace1  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18001ace6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001aceb  lea     r8, [rsp+260h+Name]; lpName
0x18001acf0  xor     edx, edx; bInheritHandle
0x18001acf2  mov     ecx, 1F0003h; dwDesiredAccess
0x18001acf7  call    cs:__imp_OpenSemaphoreW
0x18001acfd  mov     [rsp+260h+var_238], rax
0x18001ad02  test    rax, rax
0x18001ad05  jnz     short loc_18001AD26
0x18001ad07  mov     rcx, [rbp+168h]; this
0x18001ad0e  mov     edx, 0DCh; void *
0x18001ad13  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001ad18  mov     ebx, eax
0x18001ad1a  lea     rcx, [rsp+260h+var_238]
0x18001ad1f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001ad24  jmp     short loc_18001AD6F
0x18001ad26  lea     rdx, [rsp+260h+var_240]; int *
0x18001ad2b  mov     rcx, rax; hHandle
0x18001ad2e  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001ad33  mov     ebx, eax
0x18001ad35  test    eax, eax
0x18001ad37  jns     short loc_18001AD4F
0x18001ad39  mov     rcx, [rbp+168h]; this
0x18001ad40  mov     r9d, eax; char *
0x18001ad43  mov     edx, 0DEh; void *
0x18001ad48  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ad4d  jmp     short loc_18001AD1A
0x18001ad4f  lea     rcx, [rsp+260h+var_238]
0x18001ad54  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001ad59  movsxd  rcx, [rsp+260h+var_240]
0x18001ad5e  movsxd  rax, [rsp+260h+var_23C]
0x18001ad63  shl     rcx, 1Fh
0x18001ad67  or      rcx, rax
0x18001ad6a  mov     [rdi], rcx
0x18001ad6d  xor     ebx, ebx
0x18001ad6f  lea     rcx, [rsp+260h+var_230]
0x18001ad74  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001ad79  mov     eax, ebx
0x18001ad7b  mov     rcx, [rbp+160h+var_10]
0x18001ad82  xor     rcx, rsp; StackCookie
0x18001ad85  call    __security_check_cookie
0x18001ad8a  lea     r11, [rsp+260h+var_s0]
0x18001ad92  mov     rbx, [r11+18h]
0x18001ad96  mov     rdi, [r11+28h]
0x18001ad9a  mov     rsp, r11
0x18001ad9d  pop     rbp
0x18001ad9e  retn
```
