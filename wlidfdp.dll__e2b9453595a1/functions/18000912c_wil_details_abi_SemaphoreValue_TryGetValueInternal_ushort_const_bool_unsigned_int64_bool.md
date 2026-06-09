# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000912c`
- end: `0x1800092df`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `435`
- prototype: `__int64 __fastcall(const unsigned __int16 *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800059e8`

## callees

- `0x1800027f0`
- `0x180005734`
- `0x180006d78`
- `0x1800085f4`
- `0x180008614`
- `0x180008c7c`
- `0x180008cc8`
- `0x18000912c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000918b`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009229`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000918b`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009229`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000919b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000919b`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  unsigned __int64 v5; // rdx
  wil::details *v6; // rax
  void *v7; // rdx
  const char *v8; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned __int64 v11; // rdx
  wil::details *v12; // rax
  const char *v13; // r9
  void *v14; // rdx
  int v15; // eax
  void *v16; // rdx
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+24h] [rbp-DCh] BYREF
  wil::details *v20; // [rsp+28h] [rbp-D8h] BYREF
  wil::details *v21; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  *a3 = 0;
  StringCchCopyW(Name, a2, a1);
  StringCchCatW(Name, v5, L"_p0");
  v6 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v21 = v6;
  if ( v6 )
  {
    v19 = 0;
    v18 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v19);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore);
      goto LABEL_13;
    }
    StringCchCatW(Name, v11, L"h");
    v12 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
    v20 = v12;
    if ( v12 )
    {
      v15 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v12, &v18);
      LastError = v15;
      if ( v15 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
          &v20,
          v16);
        *a3 = v19 | (unsigned __int64)((__int64)v18 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v15);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v13);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v20,
      v14);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v8);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v21,
    v7);
  return LastError;
}

```

## disassembly

```asm
0x18000912c  mov     [rsp-8+arg_8], rbx
0x180009131  mov     [rsp-8+arg_18], rdi
0x180009136  push    rbp
0x180009137  lea     rbp, [rsp-160h]
0x18000913f  sub     rsp, 260h
0x180009146  mov     rax, cs:__security_cookie
0x18000914d  xor     rax, rsp
0x180009150  mov     [rbp+160h+var_10], rax
0x180009157  mov     rdi, r8
0x18000915a  mov     qword ptr [r8], 0
0x180009161  mov     r8, rcx; unsigned __int16 *
0x180009164  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180009169  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000916e  lea     r8, aP0; "_p0"
0x180009175  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000917a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000917f  lea     r8, [rsp+260h+Name]; lpName
0x180009184  xor     edx, edx; bInheritHandle
0x180009186  mov     ecx, 1F0003h; dwDesiredAccess
0x18000918b  call    cs:__imp_OpenSemaphoreW
0x180009191  mov     [rsp+260h+var_230], rax
0x180009196  test    rax, rax
0x180009199  jnz     short loc_1800091C9
0x18000919b  call    cs:__imp_GetLastError
0x1800091a1  cmp     eax, 2
0x1800091a4  jz      loc_1800092AD
0x1800091aa  mov     rcx, [rbp+168h]; this
0x1800091b1  lea     r8, aWil; "wil"
0x1800091b8  mov     edx, 0D0h; void *
0x1800091bd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800091c2  mov     ebx, eax
0x1800091c4  jmp     loc_1800092AF
0x1800091c9  lea     rdx, [rsp+260h+var_23C]; int *
0x1800091ce  mov     [rsp+260h+var_23C], 0
0x1800091d6  mov     rcx, rax; hHandle
0x1800091d9  mov     [rsp+260h+var_240], 0; int
0x1800091e1  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800091e6  mov     ebx, eax
0x1800091e8  test    eax, eax
0x1800091ea  jns     short loc_18000920C
0x1800091ec  mov     rcx, [rbp+168h]; this
0x1800091f3  lea     r8, aWil; "wil"
0x1800091fa  mov     r9d, eax; char *
0x1800091fd  mov     edx, 0D6h; void *
0x180009202  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009207  jmp     loc_1800092AF
0x18000920c  lea     r8, asc_180017F88; "h"
0x180009213  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180009218  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000921d  lea     r8, [rsp+260h+Name]; lpName
0x180009222  xor     edx, edx; bInheritHandle
0x180009224  mov     ecx, 1F0003h; dwDesiredAccess
0x180009229  call    cs:__imp_OpenSemaphoreW
0x18000922f  mov     [rsp+260h+var_238], rax
0x180009234  test    rax, rax
0x180009237  jnz     short loc_18000925F
0x180009239  mov     rcx, [rbp+168h]; this
0x180009240  lea     r8, aWil; "wil"
0x180009247  mov     edx, 0DCh; void *
0x18000924c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009251  mov     ebx, eax
0x180009253  lea     rcx, [rsp+260h+var_238]
0x180009258  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000925d  jmp     short loc_1800092AF
0x18000925f  lea     rdx, [rsp+260h+var_240]; int *
0x180009264  mov     rcx, rax; hHandle
0x180009267  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000926c  mov     ebx, eax
0x18000926e  test    eax, eax
0x180009270  jns     short loc_18000928F
0x180009272  mov     rcx, [rbp+168h]; this
0x180009279  lea     r8, aWil; "wil"
0x180009280  mov     r9d, eax; char *
0x180009283  mov     edx, 0DEh; void *
0x180009288  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000928d  jmp     short loc_180009253
0x18000928f  lea     rcx, [rsp+260h+var_238]
0x180009294  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180009299  movsxd  rcx, [rsp+260h+var_240]
0x18000929e  movsxd  rax, [rsp+260h+var_23C]
0x1800092a3  shl     rcx, 1Fh
0x1800092a7  or      rcx, rax
0x1800092aa  mov     [rdi], rcx
0x1800092ad  xor     ebx, ebx
0x1800092af  lea     rcx, [rsp+260h+var_230]
0x1800092b4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800092b9  mov     eax, ebx
0x1800092bb  mov     rcx, [rbp+160h+var_10]
0x1800092c2  xor     rcx, rsp; StackCookie
0x1800092c5  call    __security_check_cookie
0x1800092ca  lea     r11, [rsp+260h+var_s0]
0x1800092d2  mov     rbx, [r11+18h]
0x1800092d6  mov     rdi, [r11+28h]
0x1800092da  mov     rsp, r11
0x1800092dd  pop     rbp
0x1800092de  retn
```
