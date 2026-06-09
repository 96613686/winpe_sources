# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180009738`
- end: `0x1800098f0`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800096b4`

## callees

- `0x1800046b8`
- `0x1800064f8`
- `0x18000883c`
- `0x18000885c`
- `0x180008f74`
- `0x18000909c`
- `0x180009738`
- `0x18001b150`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000979c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000983a`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000979c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000983a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800097ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800097ac`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        STRSAFE_PCNZWCH pszSrc,
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
  size_t v15; // [rsp+20h] [rbp-E0h]
  int v16; // [rsp+30h] [rbp-D0h] BYREF
  int v17; // [rsp+34h] [rbp-CCh] BYREF
  HANDLE v18; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE v19[2]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCopyWorkerW(pszDest, 0x104u, a3, pszSrc, v15);
  StringCchCatW(pszDest, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v19[0] = v6;
  if ( v6 )
  {
    v17 = 0;
    v16 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v17);
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
    StringCchCatW(pszDest, v10, L"h");
    v11 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
    v18 = v11;
    if ( v11 )
    {
      v13 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v11, &v16);
      LastError = v13;
      if ( v13 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v18);
        *a3 = v17 | (unsigned __int64)((__int64)v16 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v13);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (int)"wil", v12);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v18);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (int)"wil", v7);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v19);
  return LastError;
}

```

## disassembly

```asm
0x180009738  mov     [rsp-8+arg_8], rbx
0x18000973d  mov     [rsp-8+arg_18], rdi
0x180009742  push    rbp
0x180009743  lea     rbp, [rsp-170h]
0x18000974b  sub     rsp, 270h
0x180009752  mov     rax, cs:__security_cookie
0x180009759  xor     rax, rsp
0x18000975c  mov     [rbp+170h+var_10], rax
0x180009763  mov     r9, rcx; pszSrc
0x180009766  mov     qword ptr [r8], 0
0x18000976d  lea     rcx, [rsp+270h+pszDest]; pszDest
0x180009772  mov     edx, 104h; cchDest
0x180009777  mov     rdi, r8
0x18000977a  call    StringCopyWorkerW
0x18000977f  lea     r8, aP0; "_p0"
0x180009786  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x18000978b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009790  lea     r8, [rsp+270h+pszDest]; lpName
0x180009795  xor     edx, edx; bInheritHandle
0x180009797  mov     ecx, 1F0003h; dwDesiredAccess
0x18000979c  call    cs:__imp_OpenSemaphoreW
0x1800097a2  mov     [rsp+270h+var_230], rax
0x1800097a7  test    rax, rax
0x1800097aa  jnz     short loc_1800097DA
0x1800097ac  call    cs:__imp_GetLastError
0x1800097b2  cmp     eax, 2
0x1800097b5  jz      loc_1800098BE
0x1800097bb  mov     rcx, [rbp+178h]; this
0x1800097c2  lea     r8, aWil; "wil"
0x1800097c9  mov     edx, 0D0h; void *
0x1800097ce  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800097d3  mov     ebx, eax
0x1800097d5  jmp     loc_1800098C0
0x1800097da  lea     rdx, [rsp+270h+var_23C]; int *
0x1800097df  mov     [rsp+270h+var_23C], 0
0x1800097e7  mov     rcx, rax; hHandle
0x1800097ea  mov     [rsp+270h+var_240], 0
0x1800097f2  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800097f7  mov     ebx, eax
0x1800097f9  test    eax, eax
0x1800097fb  jns     short loc_18000981D
0x1800097fd  mov     rcx, [rbp+178h]; this
0x180009804  lea     r8, aWil; "wil"
0x18000980b  mov     r9d, eax; char *
0x18000980e  mov     edx, 0D6h; void *
0x180009813  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009818  jmp     loc_1800098C0
0x18000981d  lea     r8, asc_180022048; "h"
0x180009824  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x180009829  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000982e  lea     r8, [rsp+270h+pszDest]; lpName
0x180009833  xor     edx, edx; bInheritHandle
0x180009835  mov     ecx, 1F0003h; dwDesiredAccess
0x18000983a  call    cs:__imp_OpenSemaphoreW
0x180009840  mov     [rsp+270h+var_238], rax
0x180009845  test    rax, rax
0x180009848  jnz     short loc_180009870
0x18000984a  mov     rcx, [rbp+178h]; this
0x180009851  lea     r8, aWil; "wil"
0x180009858  mov     edx, 0DCh; void *
0x18000985d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009862  mov     ebx, eax
0x180009864  lea     rcx, [rsp+270h+var_238]
0x180009869  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000986e  jmp     short loc_1800098C0
0x180009870  lea     rdx, [rsp+270h+var_240]; int *
0x180009875  mov     rcx, rax; hHandle
0x180009878  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000987d  mov     ebx, eax
0x18000987f  test    eax, eax
0x180009881  jns     short loc_1800098A0
0x180009883  mov     rcx, [rbp+178h]; this
0x18000988a  lea     r8, aWil; "wil"
0x180009891  mov     r9d, eax; char *
0x180009894  mov     edx, 0DEh; void *
0x180009899  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000989e  jmp     short loc_180009864
0x1800098a0  lea     rcx, [rsp+270h+var_238]
0x1800098a5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800098aa  movsxd  rcx, [rsp+270h+var_240]
0x1800098af  movsxd  rax, [rsp+270h+var_23C]
0x1800098b4  shl     rcx, 1Fh
0x1800098b8  or      rcx, rax
0x1800098bb  mov     [rdi], rcx
0x1800098be  xor     ebx, ebx
0x1800098c0  lea     rcx, [rsp+270h+var_230]
0x1800098c5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800098ca  mov     eax, ebx
0x1800098cc  mov     rcx, [rbp+170h+var_10]
0x1800098d3  xor     rcx, rsp; StackCookie
0x1800098d6  call    __security_check_cookie
0x1800098db  lea     r11, [rsp+270h+var_s0]
0x1800098e3  mov     rbx, [r11+18h]
0x1800098e7  mov     rdi, [r11+28h]
0x1800098eb  mov     rsp, r11
0x1800098ee  pop     rbp
0x1800098ef  retn
```
