# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180055168`
- end: `0x180055304`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180067904`

## callees

- `0x18002ebc0`
- `0x180055168`
- `0x18005530c`
- `0x180055388`
- `0x180055494`
- `0x1800597b0`
- `0x1800626ec`
- `0x18006388c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800551dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800551dc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800551cc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18005525c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800551cc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18005525c`

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
0x180055168  mov     [rsp-8+arg_8], rbx
0x18005516d  mov     [rsp-8+arg_18], rdi
0x180055172  push    rbp
0x180055173  lea     rbp, [rsp-160h]
0x18005517b  sub     rsp, 260h
0x180055182  mov     rax, cs:__security_cookie
0x180055189  xor     rax, rsp
0x18005518c  mov     [rbp+160h+var_10], rax
0x180055193  mov     rdi, r8
0x180055196  mov     qword ptr [r8], 0
0x18005519d  mov     r8, rcx; unsigned __int16 *
0x1800551a0  mov     edx, 104h; unsigned __int64
0x1800551a5  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x1800551aa  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800551af  lea     r8, aP0; "_p0"
0x1800551b6  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x1800551bb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800551c0  lea     r8, [rsp+260h+Name]; lpName
0x1800551c5  xor     edx, edx; bInheritHandle
0x1800551c7  mov     ecx, 1F0003h; dwDesiredAccess
0x1800551cc  call    cs:__imp_OpenSemaphoreW
0x1800551d2  mov     [rsp+260h+var_230], rax
0x1800551d7  test    rax, rax
0x1800551da  jnz     short loc_180055203
0x1800551dc  call    cs:__imp_GetLastError
0x1800551e2  cmp     eax, 2
0x1800551e5  jz      loc_1800552D2
0x1800551eb  mov     rcx, [rbp+168h]; this
0x1800551f2  mov     edx, 0D0h; void *
0x1800551f7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800551fc  mov     ebx, eax
0x1800551fe  jmp     loc_1800552D4
0x180055203  lea     rdx, [rsp+260h+var_23C]; int *
0x180055208  mov     [rsp+260h+var_23C], 0
0x180055210  mov     rcx, rax; hHandle
0x180055213  mov     [rsp+260h+var_240], 0; int
0x18005521b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180055220  mov     ebx, eax
0x180055222  test    eax, eax
0x180055224  jns     short loc_18005523F
0x180055226  mov     rcx, [rbp+168h]; this
0x18005522d  mov     r9d, eax; char *
0x180055230  mov     edx, 0D6h; void *
0x180055235  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005523a  jmp     loc_1800552D4
0x18005523f  lea     r8, asc_180098C68; "h"
0x180055246  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18005524b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180055250  lea     r8, [rsp+260h+Name]; lpName
0x180055255  xor     edx, edx; bInheritHandle
0x180055257  mov     ecx, 1F0003h; dwDesiredAccess
0x18005525c  call    cs:__imp_OpenSemaphoreW
0x180055262  mov     [rsp+260h+var_238], rax
0x180055267  test    rax, rax
0x18005526a  jnz     short loc_18005528B
0x18005526c  mov     rcx, [rbp+168h]; this
0x180055273  mov     edx, 0DCh; void *
0x180055278  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005527d  mov     ebx, eax
0x18005527f  lea     rcx, [rsp+260h+var_238]
0x180055284  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180055289  jmp     short loc_1800552D4
0x18005528b  lea     rdx, [rsp+260h+var_240]; int *
0x180055290  mov     rcx, rax; hHandle
0x180055293  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180055298  mov     ebx, eax
0x18005529a  test    eax, eax
0x18005529c  jns     short loc_1800552B4
0x18005529e  mov     rcx, [rbp+168h]; this
0x1800552a5  mov     r9d, eax; char *
0x1800552a8  mov     edx, 0DEh; void *
0x1800552ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800552b2  jmp     short loc_18005527F
0x1800552b4  lea     rcx, [rsp+260h+var_238]
0x1800552b9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800552be  movsxd  rcx, [rsp+260h+var_240]
0x1800552c3  movsxd  rax, [rsp+260h+var_23C]
0x1800552c8  shl     rcx, 1Fh
0x1800552cc  or      rcx, rax
0x1800552cf  mov     [rdi], rcx
0x1800552d2  xor     ebx, ebx
0x1800552d4  lea     rcx, [rsp+260h+var_230]
0x1800552d9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800552de  mov     eax, ebx
0x1800552e0  mov     rcx, [rbp+160h+var_10]
0x1800552e7  xor     rcx, rsp; StackCookie
0x1800552ea  call    __security_check_cookie
0x1800552ef  lea     r11, [rsp+260h+var_s0]
0x1800552f7  mov     rbx, [r11+18h]
0x1800552fb  mov     rdi, [r11+28h]
0x1800552ff  mov     rsp, r11
0x180055302  pop     rbp
0x180055303  retn
```
