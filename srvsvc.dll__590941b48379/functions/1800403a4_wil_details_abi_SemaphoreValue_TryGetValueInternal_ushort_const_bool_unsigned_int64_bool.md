# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800403a4`
- end: `0x180040540`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180040330`

## callees

- `0x18001deb0`
- `0x180026880`
- `0x18003cbc4`
- `0x18003dfa4`
- `0x18003fa84`
- `0x18003faa4`
- `0x18003ff1c`
- `0x1800403a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040418`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040418`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180040408`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180040498`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180040408`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180040498`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        STRSAFE_PCNZWCH pszSrc,
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
  size_t v22; // [rsp+20h] [rbp-E0h]
  int v23; // [rsp+30h] [rbp-D0h] BYREF
  int v24; // [rsp+34h] [rbp-CCh] BYREF
  wil::details *v25; // [rsp+38h] [rbp-C8h] BYREF
  wil::details *v26; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCopyWorkerW(pszDest, 0x104u, a3, pszSrc, v22);
  StringCchCatW(pszDest, v5, L"_p0");
  v6 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v26 = v6;
  if ( v6 )
  {
    v24 = 0;
    v23 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v24);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v13, (const char *)(unsigned int)ValueFromSemaphore);
      goto LABEL_13;
    }
    StringCchCatW(pszDest, v12, L"h");
    v14 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, pszDest);
    v25 = v14;
    if ( v14 )
    {
      v18 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v14, &v23);
      LastError = v18;
      if ( v18 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
          &v25,
          v19);
        *a3 = v24 | (unsigned __int64)((__int64)v23 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v20, (const char *)(unsigned int)v18);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v15, v16);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v25,
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
    &v26,
    v7);
  return LastError;
}

```

## disassembly

```asm
0x1800403a4  mov     [rsp-8+arg_8], rbx
0x1800403a9  mov     [rsp-8+arg_18], rdi
0x1800403ae  push    rbp
0x1800403af  lea     rbp, [rsp-170h]
0x1800403b7  sub     rsp, 270h
0x1800403be  mov     rax, cs:__security_cookie
0x1800403c5  xor     rax, rsp
0x1800403c8  mov     [rbp+170h+var_10], rax
0x1800403cf  mov     r9, rcx; pszSrc
0x1800403d2  mov     qword ptr [r8], 0
0x1800403d9  lea     rcx, [rsp+270h+pszDest]; pszDest
0x1800403de  mov     edx, 104h; cchDest
0x1800403e3  mov     rdi, r8
0x1800403e6  call    StringCopyWorkerW
0x1800403eb  lea     r8, aP0; "_p0"
0x1800403f2  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x1800403f7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800403fc  lea     r8, [rsp+270h+pszDest]; lpName
0x180040401  xor     edx, edx; bInheritHandle
0x180040403  mov     ecx, 1F0003h; dwDesiredAccess
0x180040408  call    cs:__imp_OpenSemaphoreW
0x18004040e  mov     [rsp+270h+var_230], rax
0x180040413  test    rax, rax
0x180040416  jnz     short loc_18004043F
0x180040418  call    cs:__imp_GetLastError
0x18004041e  cmp     eax, 2
0x180040421  jz      loc_18004050E
0x180040427  mov     rcx, [rbp+178h]; this
0x18004042e  mov     edx, 0D0h; void *
0x180040433  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180040438  mov     ebx, eax
0x18004043a  jmp     loc_180040510
0x18004043f  lea     rdx, [rsp+270h+var_23C]; int *
0x180040444  mov     [rsp+270h+var_23C], 0
0x18004044c  mov     rcx, rax; hHandle
0x18004044f  mov     [rsp+270h+var_240], 0
0x180040457  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18004045c  mov     ebx, eax
0x18004045e  test    eax, eax
0x180040460  jns     short loc_18004047B
0x180040462  mov     rcx, [rbp+178h]; this
0x180040469  mov     r9d, eax; char *
0x18004046c  mov     edx, 0D6h; void *
0x180040471  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040476  jmp     loc_180040510
0x18004047b  lea     r8, asc_180054E48; "h"
0x180040482  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x180040487  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004048c  lea     r8, [rsp+270h+pszDest]; lpName
0x180040491  xor     edx, edx; bInheritHandle
0x180040493  mov     ecx, 1F0003h; dwDesiredAccess
0x180040498  call    cs:__imp_OpenSemaphoreW
0x18004049e  mov     [rsp+270h+var_238], rax
0x1800404a3  test    rax, rax
0x1800404a6  jnz     short loc_1800404C7
0x1800404a8  mov     rcx, [rbp+178h]; this
0x1800404af  mov     edx, 0DCh; void *
0x1800404b4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800404b9  mov     ebx, eax
0x1800404bb  lea     rcx, [rsp+270h+var_238]
0x1800404c0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800404c5  jmp     short loc_180040510
0x1800404c7  lea     rdx, [rsp+270h+var_240]; int *
0x1800404cc  mov     rcx, rax; hHandle
0x1800404cf  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800404d4  mov     ebx, eax
0x1800404d6  test    eax, eax
0x1800404d8  jns     short loc_1800404F0
0x1800404da  mov     rcx, [rbp+178h]; this
0x1800404e1  mov     r9d, eax; char *
0x1800404e4  mov     edx, 0DEh; void *
0x1800404e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800404ee  jmp     short loc_1800404BB
0x1800404f0  lea     rcx, [rsp+270h+var_238]
0x1800404f5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800404fa  movsxd  rcx, [rsp+270h+var_240]
0x1800404ff  movsxd  rax, [rsp+270h+var_23C]
0x180040504  shl     rcx, 1Fh
0x180040508  or      rcx, rax
0x18004050b  mov     [rdi], rcx
0x18004050e  xor     ebx, ebx
0x180040510  lea     rcx, [rsp+270h+var_230]
0x180040515  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004051a  mov     eax, ebx
0x18004051c  mov     rcx, [rbp+170h+var_10]
0x180040523  xor     rcx, rsp; StackCookie
0x180040526  call    __security_check_cookie
0x18004052b  lea     r11, [rsp+270h+var_s0]
0x180040533  mov     rbx, [r11+18h]
0x180040537  mov     rdi, [r11+28h]
0x18004053b  mov     rsp, r11
0x18004053e  pop     rbp
0x18004053f  retn
```
