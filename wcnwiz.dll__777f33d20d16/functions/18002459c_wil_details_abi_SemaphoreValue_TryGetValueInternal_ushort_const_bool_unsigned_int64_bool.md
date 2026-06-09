# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18002459c`
- end: `0x180024738`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180024528`

## callees

- `0x180001820`
- `0x1800132e0`
- `0x1800222f8`
- `0x18002304c`
- `0x180023cc4`
- `0x180023ce4`
- `0x180024418`
- `0x18002459c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024610`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024610`
- `KERNEL32!OpenSemaphoreW` at `0x180024600`
- `KERNEL32!OpenSemaphoreW` at `0x180024690`
- `KERNEL32!OpenSemaphoreW` at `0x180024600`
- `KERNEL32!OpenSemaphoreW` at `0x180024690`

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
0x18002459c  mov     [rsp-8+arg_8], rbx
0x1800245a1  mov     [rsp-8+arg_18], rdi
0x1800245a6  push    rbp
0x1800245a7  lea     rbp, [rsp-160h]
0x1800245af  sub     rsp, 260h
0x1800245b6  mov     rax, cs:__security_cookie
0x1800245bd  xor     rax, rsp
0x1800245c0  mov     [rbp+160h+var_10], rax
0x1800245c7  mov     rdi, r8
0x1800245ca  mov     qword ptr [r8], 0
0x1800245d1  mov     r8, rcx; unsigned __int16 *
0x1800245d4  mov     edx, 104h; unsigned __int64
0x1800245d9  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x1800245de  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800245e3  lea     r8, aP0; "_p0"
0x1800245ea  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x1800245ef  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800245f4  lea     r8, [rsp+260h+Name]; lpName
0x1800245f9  xor     edx, edx; bInheritHandle
0x1800245fb  mov     ecx, 1F0003h; dwDesiredAccess
0x180024600  call    cs:__imp_OpenSemaphoreW
0x180024606  mov     [rsp+260h+var_230], rax
0x18002460b  test    rax, rax
0x18002460e  jnz     short loc_180024637
0x180024610  call    cs:__imp_GetLastError
0x180024616  cmp     eax, 2
0x180024619  jz      loc_180024706
0x18002461f  mov     rcx, [rbp+168h]; this
0x180024626  mov     edx, 0D0h; void *
0x18002462b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180024630  mov     ebx, eax
0x180024632  jmp     loc_180024708
0x180024637  lea     rdx, [rsp+260h+var_23C]; int *
0x18002463c  mov     [rsp+260h+var_23C], 0
0x180024644  mov     rcx, rax; hHandle
0x180024647  mov     [rsp+260h+var_240], 0; int
0x18002464f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180024654  mov     ebx, eax
0x180024656  test    eax, eax
0x180024658  jns     short loc_180024673
0x18002465a  mov     rcx, [rbp+168h]; this
0x180024661  mov     r9d, eax; char *
0x180024664  mov     edx, 0D6h; void *
0x180024669  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002466e  jmp     loc_180024708
0x180024673  lea     r8, asc_1800376D0; "h"
0x18002467a  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18002467f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180024684  lea     r8, [rsp+260h+Name]; lpName
0x180024689  xor     edx, edx; bInheritHandle
0x18002468b  mov     ecx, 1F0003h; dwDesiredAccess
0x180024690  call    cs:__imp_OpenSemaphoreW
0x180024696  mov     [rsp+260h+var_238], rax
0x18002469b  test    rax, rax
0x18002469e  jnz     short loc_1800246BF
0x1800246a0  mov     rcx, [rbp+168h]; this
0x1800246a7  mov     edx, 0DCh; void *
0x1800246ac  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800246b1  mov     ebx, eax
0x1800246b3  lea     rcx, [rsp+260h+var_238]
0x1800246b8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800246bd  jmp     short loc_180024708
0x1800246bf  lea     rdx, [rsp+260h+var_240]; int *
0x1800246c4  mov     rcx, rax; hHandle
0x1800246c7  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800246cc  mov     ebx, eax
0x1800246ce  test    eax, eax
0x1800246d0  jns     short loc_1800246E8
0x1800246d2  mov     rcx, [rbp+168h]; this
0x1800246d9  mov     r9d, eax; char *
0x1800246dc  mov     edx, 0DEh; void *
0x1800246e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800246e6  jmp     short loc_1800246B3
0x1800246e8  lea     rcx, [rsp+260h+var_238]
0x1800246ed  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800246f2  movsxd  rcx, [rsp+260h+var_240]
0x1800246f7  movsxd  rax, [rsp+260h+var_23C]
0x1800246fc  shl     rcx, 1Fh
0x180024700  or      rcx, rax
0x180024703  mov     [rdi], rcx
0x180024706  xor     ebx, ebx
0x180024708  lea     rcx, [rsp+260h+var_230]
0x18002470d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180024712  mov     eax, ebx
0x180024714  mov     rcx, [rbp+160h+var_10]
0x18002471b  xor     rcx, rsp; StackCookie
0x18002471e  call    __security_check_cookie
0x180024723  lea     r11, [rsp+260h+var_s0]
0x18002472b  mov     rbx, [r11+18h]
0x18002472f  mov     rdi, [r11+28h]
0x180024733  mov     rsp, r11
0x180024736  pop     rbp
0x180024737  retn
```
