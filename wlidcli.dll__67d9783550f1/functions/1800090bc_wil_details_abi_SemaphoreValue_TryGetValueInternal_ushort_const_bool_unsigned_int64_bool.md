# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800090bc`
- end: `0x180009274`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180009038`

## callees

- `0x180002da0`
- `0x180005130`
- `0x1800067ac`
- `0x1800083ac`
- `0x1800083cc`
- `0x180008a8c`
- `0x180008b70`
- `0x1800090bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009120`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800091be`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009120`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800091be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009130`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009130`

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
0x1800090bc  mov     [rsp-8+arg_8], rbx
0x1800090c1  mov     [rsp-8+arg_18], rdi
0x1800090c6  push    rbp
0x1800090c7  lea     rbp, [rsp-160h]
0x1800090cf  sub     rsp, 260h
0x1800090d6  mov     rax, cs:__security_cookie
0x1800090dd  xor     rax, rsp
0x1800090e0  mov     [rbp+160h+var_10], rax
0x1800090e7  mov     rdi, r8
0x1800090ea  mov     qword ptr [r8], 0
0x1800090f1  mov     r8, rcx; unsigned __int16 *
0x1800090f4  mov     edx, 104h; unsigned __int64
0x1800090f9  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x1800090fe  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180009103  lea     r8, aP0; "_p0"
0x18000910a  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000910f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009114  lea     r8, [rsp+260h+Name]; lpName
0x180009119  xor     edx, edx; bInheritHandle
0x18000911b  mov     ecx, 1F0003h; dwDesiredAccess
0x180009120  call    cs:__imp_OpenSemaphoreW
0x180009126  mov     [rsp+260h+var_230], rax
0x18000912b  test    rax, rax
0x18000912e  jnz     short loc_18000915E
0x180009130  call    cs:__imp_GetLastError
0x180009136  cmp     eax, 2
0x180009139  jz      loc_180009242
0x18000913f  mov     rcx, [rbp+168h]; this
0x180009146  lea     r8, aWil; "wil"
0x18000914d  mov     edx, 0D0h; void *
0x180009152  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009157  mov     ebx, eax
0x180009159  jmp     loc_180009244
0x18000915e  lea     rdx, [rsp+260h+var_23C]; int *
0x180009163  mov     [rsp+260h+var_23C], 0
0x18000916b  mov     rcx, rax; hHandle
0x18000916e  mov     [rsp+260h+var_240], 0; int
0x180009176  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000917b  mov     ebx, eax
0x18000917d  test    eax, eax
0x18000917f  jns     short loc_1800091A1
0x180009181  mov     rcx, [rbp+168h]; this
0x180009188  lea     r8, aWil; "wil"
0x18000918f  mov     r9d, eax; char *
0x180009192  mov     edx, 0D6h; void *
0x180009197  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000919c  jmp     loc_180009244
0x1800091a1  lea     r8, asc_18006C270; "h"
0x1800091a8  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x1800091ad  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800091b2  lea     r8, [rsp+260h+Name]; lpName
0x1800091b7  xor     edx, edx; bInheritHandle
0x1800091b9  mov     ecx, 1F0003h; dwDesiredAccess
0x1800091be  call    cs:__imp_OpenSemaphoreW
0x1800091c4  mov     [rsp+260h+var_238], rax
0x1800091c9  test    rax, rax
0x1800091cc  jnz     short loc_1800091F4
0x1800091ce  mov     rcx, [rbp+168h]; this
0x1800091d5  lea     r8, aWil; "wil"
0x1800091dc  mov     edx, 0DCh; void *
0x1800091e1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800091e6  mov     ebx, eax
0x1800091e8  lea     rcx, [rsp+260h+var_238]
0x1800091ed  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800091f2  jmp     short loc_180009244
0x1800091f4  lea     rdx, [rsp+260h+var_240]; int *
0x1800091f9  mov     rcx, rax; hHandle
0x1800091fc  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180009201  mov     ebx, eax
0x180009203  test    eax, eax
0x180009205  jns     short loc_180009224
0x180009207  mov     rcx, [rbp+168h]; this
0x18000920e  lea     r8, aWil; "wil"
0x180009215  mov     r9d, eax; char *
0x180009218  mov     edx, 0DEh; void *
0x18000921d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009222  jmp     short loc_1800091E8
0x180009224  lea     rcx, [rsp+260h+var_238]
0x180009229  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000922e  movsxd  rcx, [rsp+260h+var_240]
0x180009233  movsxd  rax, [rsp+260h+var_23C]
0x180009238  shl     rcx, 1Fh
0x18000923c  or      rcx, rax
0x18000923f  mov     [rdi], rcx
0x180009242  xor     ebx, ebx
0x180009244  lea     rcx, [rsp+260h+var_230]
0x180009249  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000924e  mov     eax, ebx
0x180009250  mov     rcx, [rbp+160h+var_10]
0x180009257  xor     rcx, rsp; StackCookie
0x18000925a  call    __security_check_cookie
0x18000925f  lea     r11, [rsp+260h+var_s0]
0x180009267  mov     rbx, [r11+18h]
0x18000926b  mov     rdi, [r11+28h]
0x18000926f  mov     rsp, r11
0x180009272  pop     rbp
0x180009273  retn
```
