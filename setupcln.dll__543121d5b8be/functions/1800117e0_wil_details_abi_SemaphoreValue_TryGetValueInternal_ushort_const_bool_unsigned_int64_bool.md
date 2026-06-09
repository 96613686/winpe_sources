# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800117e0`
- end: `0x18001197c`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18001176c`

## callees

- `0x180007f14`
- `0x18000d998`
- `0x18000f204`
- `0x180010cbc`
- `0x180010cdc`
- `0x1800113a4`
- `0x1800117e0`
- `0x1800131e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011854`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011854`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180011844`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800118d4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180011844`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800118d4`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        unsigned __int16 *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  unsigned __int64 v5; // rdx
  wil::details *v6; // rax
  void *v7; // rdx
  unsigned int v8; // r8d
  const char *v9; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned __int64 v12; // rdx
  int v13; // r8d
  wil::details *v14; // rax
  unsigned int v15; // r8d
  const char *v16; // r9
  void *v17; // rdx
  int v18; // eax
  void *v19; // rdx
  int v20; // r8d
  int v22; // [rsp+20h] [rbp-E0h] BYREF
  int v23; // [rsp+24h] [rbp-DCh] BYREF
  wil::details *v24; // [rsp+28h] [rbp-D8h] BYREF
  wil::details *v25; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, v5, L"_p0");
  v6 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v25 = v6;
  if ( v6 )
  {
    v23 = 0;
    v22 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v23);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v13, (const char *)(unsigned int)ValueFromSemaphore);
      goto LABEL_13;
    }
    StringCchCatW(Name, v12, L"h");
    v14 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
    v24 = v14;
    if ( v14 )
    {
      v18 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v14, &v22);
      LastError = v18;
      if ( v18 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
          &v24,
          v19);
        *a3 = v23 | (unsigned __int64)((__int64)v22 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v20, (const char *)(unsigned int)v18);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v15, v16);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v24,
      v17);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v8, v9);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v25,
    v7);
  return LastError;
}

```

## disassembly

```asm
0x1800117e0  mov     [rsp-8+arg_8], rbx
0x1800117e5  mov     [rsp-8+arg_18], rdi
0x1800117ea  push    rbp
0x1800117eb  lea     rbp, [rsp-160h]
0x1800117f3  sub     rsp, 260h
0x1800117fa  mov     rax, cs:__security_cookie
0x180011801  xor     rax, rsp
0x180011804  mov     [rbp+160h+var_10], rax
0x18001180b  mov     rdi, r8
0x18001180e  mov     qword ptr [r8], 0
0x180011815  mov     r8, rcx; unsigned __int16 *
0x180011818  mov     edx, 104h; unsigned __int64
0x18001181d  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180011822  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180011827  lea     r8, aP0; "_p0"
0x18001182e  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180011833  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180011838  lea     r8, [rsp+260h+Name]; lpName
0x18001183d  xor     edx, edx; bInheritHandle
0x18001183f  mov     ecx, 1F0003h; dwDesiredAccess
0x180011844  call    cs:__imp_OpenSemaphoreW
0x18001184a  mov     [rsp+260h+var_230], rax
0x18001184f  test    rax, rax
0x180011852  jnz     short loc_18001187B
0x180011854  call    cs:__imp_GetLastError
0x18001185a  cmp     eax, 2
0x18001185d  jz      loc_18001194A
0x180011863  mov     rcx, [rbp+168h]; this
0x18001186a  mov     edx, 0D0h; void *
0x18001186f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180011874  mov     ebx, eax
0x180011876  jmp     loc_18001194C
0x18001187b  mov     [rsp+260h+var_23C], 0
0x180011883  mov     [rsp+260h+var_240], 0; int
0x18001188b  lea     rdx, [rsp+260h+var_23C]; int *
0x180011890  mov     rcx, rax; hHandle
0x180011893  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180011898  mov     ebx, eax
0x18001189a  test    eax, eax
0x18001189c  jns     short loc_1800118B7
0x18001189e  mov     rcx, [rbp+168h]; this
0x1800118a5  mov     r9d, eax; char *
0x1800118a8  mov     edx, 0D6h; void *
0x1800118ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800118b2  jmp     loc_18001194C
0x1800118b7  lea     r8, asc_18001A9F8; "h"
0x1800118be  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x1800118c3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800118c8  lea     r8, [rsp+260h+Name]; lpName
0x1800118cd  xor     edx, edx; bInheritHandle
0x1800118cf  mov     ecx, 1F0003h; dwDesiredAccess
0x1800118d4  call    cs:__imp_OpenSemaphoreW
0x1800118da  mov     [rsp+260h+var_238], rax
0x1800118df  test    rax, rax
0x1800118e2  jnz     short loc_180011903
0x1800118e4  mov     rcx, [rbp+168h]; this
0x1800118eb  mov     edx, 0DCh; void *
0x1800118f0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800118f5  mov     ebx, eax
0x1800118f7  lea     rcx, [rsp+260h+var_238]
0x1800118fc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180011901  jmp     short loc_18001194C
0x180011903  lea     rdx, [rsp+260h+var_240]; int *
0x180011908  mov     rcx, rax; hHandle
0x18001190b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180011910  mov     ebx, eax
0x180011912  test    eax, eax
0x180011914  jns     short loc_18001192C
0x180011916  mov     rcx, [rbp+168h]; this
0x18001191d  mov     r9d, eax; char *
0x180011920  mov     edx, 0DEh; void *
0x180011925  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001192a  jmp     short loc_1800118F7
0x18001192c  lea     rcx, [rsp+260h+var_238]
0x180011931  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180011936  movsxd  rcx, [rsp+260h+var_240]
0x18001193b  shl     rcx, 1Fh
0x18001193f  movsxd  rax, [rsp+260h+var_23C]
0x180011944  or      rcx, rax
0x180011947  mov     [rdi], rcx
0x18001194a  xor     ebx, ebx
0x18001194c  lea     rcx, [rsp+260h+var_230]
0x180011951  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180011956  mov     eax, ebx
0x180011958  mov     rcx, [rbp+160h+var_10]
0x18001195f  xor     rcx, rsp; StackCookie
0x180011962  call    __security_check_cookie
0x180011967  lea     r11, [rsp+260h+var_s0]
0x18001196f  mov     rbx, [r11+18h]
0x180011973  mov     rdi, [r11+28h]
0x180011977  mov     rsp, r11
0x18001197a  pop     rbp
0x18001197b  retn
```
