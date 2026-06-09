# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800224bc`
- end: `0x180022674`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180022438`

## callees

- `0x180016758`
- `0x180016ea0`
- `0x18001a0d0`
- `0x18002070c`
- `0x180021514`
- `0x180021e84`
- `0x180022360`
- `0x1800224bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180022520`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800225be`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180022520`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800225be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022530`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022530`

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
0x1800224bc  mov     [rsp-8+arg_8], rbx
0x1800224c1  mov     [rsp-8+arg_18], rdi
0x1800224c6  push    rbp
0x1800224c7  lea     rbp, [rsp-160h]
0x1800224cf  sub     rsp, 260h
0x1800224d6  mov     rax, cs:__security_cookie
0x1800224dd  xor     rax, rsp
0x1800224e0  mov     [rbp+160h+var_10], rax
0x1800224e7  mov     rdi, r8
0x1800224ea  mov     qword ptr [r8], 0
0x1800224f1  mov     r8, rcx; unsigned __int16 *
0x1800224f4  mov     edx, 104h; unsigned __int64
0x1800224f9  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x1800224fe  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180022503  lea     r8, aP0; "_p0"
0x18002250a  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18002250f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180022514  lea     r8, [rsp+260h+Name]; lpName
0x180022519  xor     edx, edx; bInheritHandle
0x18002251b  mov     ecx, 1F0003h; dwDesiredAccess
0x180022520  call    cs:__imp_OpenSemaphoreW
0x180022526  mov     [rsp+260h+var_230], rax
0x18002252b  test    rax, rax
0x18002252e  jnz     short loc_18002255E
0x180022530  call    cs:__imp_GetLastError
0x180022536  cmp     eax, 2
0x180022539  jz      loc_180022642
0x18002253f  mov     rcx, [rbp+168h]; this
0x180022546  lea     r8, aWil; "wil"
0x18002254d  mov     edx, 0D0h; void *
0x180022552  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180022557  mov     ebx, eax
0x180022559  jmp     loc_180022644
0x18002255e  lea     rdx, [rsp+260h+var_23C]; int *
0x180022563  mov     [rsp+260h+var_23C], 0
0x18002256b  mov     rcx, rax; hHandle
0x18002256e  mov     [rsp+260h+var_240], 0; int
0x180022576  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18002257b  mov     ebx, eax
0x18002257d  test    eax, eax
0x18002257f  jns     short loc_1800225A1
0x180022581  mov     rcx, [rbp+168h]; this
0x180022588  lea     r8, aWil; "wil"
0x18002258f  mov     r9d, eax; char *
0x180022592  mov     edx, 0D6h; void *
0x180022597  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002259c  jmp     loc_180022644
0x1800225a1  lea     r8, asc_1800669D8; "h"
0x1800225a8  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x1800225ad  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800225b2  lea     r8, [rsp+260h+Name]; lpName
0x1800225b7  xor     edx, edx; bInheritHandle
0x1800225b9  mov     ecx, 1F0003h; dwDesiredAccess
0x1800225be  call    cs:__imp_OpenSemaphoreW
0x1800225c4  mov     [rsp+260h+var_238], rax
0x1800225c9  test    rax, rax
0x1800225cc  jnz     short loc_1800225F4
0x1800225ce  mov     rcx, [rbp+168h]; this
0x1800225d5  lea     r8, aWil; "wil"
0x1800225dc  mov     edx, 0DCh; void *
0x1800225e1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800225e6  mov     ebx, eax
0x1800225e8  lea     rcx, [rsp+260h+var_238]
0x1800225ed  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800225f2  jmp     short loc_180022644
0x1800225f4  lea     rdx, [rsp+260h+var_240]; int *
0x1800225f9  mov     rcx, rax; hHandle
0x1800225fc  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180022601  mov     ebx, eax
0x180022603  test    eax, eax
0x180022605  jns     short loc_180022624
0x180022607  mov     rcx, [rbp+168h]; this
0x18002260e  lea     r8, aWil; "wil"
0x180022615  mov     r9d, eax; char *
0x180022618  mov     edx, 0DEh; void *
0x18002261d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022622  jmp     short loc_1800225E8
0x180022624  lea     rcx, [rsp+260h+var_238]
0x180022629  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002262e  movsxd  rcx, [rsp+260h+var_240]
0x180022633  movsxd  rax, [rsp+260h+var_23C]
0x180022638  shl     rcx, 1Fh
0x18002263c  or      rcx, rax
0x18002263f  mov     [rdi], rcx
0x180022642  xor     ebx, ebx
0x180022644  lea     rcx, [rsp+260h+var_230]
0x180022649  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002264e  mov     eax, ebx
0x180022650  mov     rcx, [rbp+160h+var_10]
0x180022657  xor     rcx, rsp; StackCookie
0x18002265a  call    __security_check_cookie
0x18002265f  lea     r11, [rsp+260h+var_s0]
0x180022667  mov     rbx, [r11+18h]
0x18002266b  mov     rdi, [r11+28h]
0x18002266f  mov     rsp, r11
0x180022672  pop     rbp
0x180022673  retn
```
