# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180015f90`
- end: `0x180016148`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180015f0c`

## callees

- `0x1800050f0`
- `0x180010484`
- `0x180012d94`
- `0x1800152b4`
- `0x1800152d4`
- `0x180015b30`
- `0x180015c10`
- `0x180015f90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016004`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016004`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180015ff4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180016092`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180015ff4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180016092`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
  int v16; // [rsp+20h] [rbp-E0h]
  int v17; // [rsp+30h] [rbp-D0h] BYREF
  int v18; // [rsp+34h] [rbp-CCh] BYREF
  HANDLE v19; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE v20[2]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCopyWorkerW(pszDest, 0x104u, a3, pszSrc, v15);
  StringCchCatW(pszDest, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v20[0] = v6;
  if ( v6 )
  {
    v18 = 0;
    v17 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v18);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v16);
      goto LABEL_13;
    }
    StringCchCatW(pszDest, v10, L"h");
    v11 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
    v19 = v11;
    if ( v11 )
    {
      v13 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v11, &v17);
      LastError = v13;
      if ( v13 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
        *a3 = v18 | (unsigned __int64)((__int64)v17 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v13,
        v16);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v12);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v20);
  return LastError;
}

```

## disassembly

```asm
0x180015f90  mov     [rsp-8+arg_8], rbx
0x180015f95  mov     [rsp-8+arg_18], rdi
0x180015f9a  push    rbp
0x180015f9b  lea     rbp, [rsp-170h]
0x180015fa3  sub     rsp, 270h
0x180015faa  mov     rax, cs:__security_cookie
0x180015fb1  xor     rax, rsp
0x180015fb4  mov     [rbp+170h+var_10], rax
0x180015fbb  mov     rdi, r8
0x180015fbe  mov     qword ptr [r8], 0
0x180015fc5  mov     r9, rcx; pszSrc
0x180015fc8  mov     edx, 104h; cchDest
0x180015fcd  lea     rcx, [rsp+270h+pszDest]; pszDest
0x180015fd2  call    StringCopyWorkerW
0x180015fd7  lea     r8, aP0; "_p0"
0x180015fde  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x180015fe3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180015fe8  lea     r8, [rsp+270h+pszDest]; lpName
0x180015fed  xor     edx, edx; bInheritHandle
0x180015fef  mov     ecx, 1F0003h; dwDesiredAccess
0x180015ff4  call    cs:__imp_OpenSemaphoreW
0x180015ffa  mov     [rsp+270h+var_230], rax
0x180015fff  test    rax, rax
0x180016002  jnz     short loc_180016032
0x180016004  call    cs:__imp_GetLastError
0x18001600a  cmp     eax, 2
0x18001600d  jz      loc_180016116
0x180016013  mov     rcx, [rbp+178h]; this
0x18001601a  lea     r8, aWil; "wil"
0x180016021  mov     edx, 0D0h; void *
0x180016026  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001602b  mov     ebx, eax
0x18001602d  jmp     loc_180016118
0x180016032  mov     [rsp+270h+var_23C], 0
0x18001603a  mov     [rsp+270h+var_240], 0
0x180016042  lea     rdx, [rsp+270h+var_23C]; int *
0x180016047  mov     rcx, rax; hHandle
0x18001604a  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001604f  mov     ebx, eax
0x180016051  test    eax, eax
0x180016053  jns     short loc_180016075
0x180016055  mov     rcx, [rbp+178h]; this
0x18001605c  mov     r9d, eax; char *
0x18001605f  lea     r8, aWil; "wil"
0x180016066  mov     edx, 0D6h; void *
0x18001606b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016070  jmp     loc_180016118
0x180016075  lea     r8, asc_180032170; "h"
0x18001607c  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x180016081  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180016086  lea     r8, [rsp+270h+pszDest]; lpName
0x18001608b  xor     edx, edx; bInheritHandle
0x18001608d  mov     ecx, 1F0003h; dwDesiredAccess
0x180016092  call    cs:__imp_OpenSemaphoreW
0x180016098  mov     [rsp+270h+var_238], rax
0x18001609d  test    rax, rax
0x1800160a0  jnz     short loc_1800160C8
0x1800160a2  mov     rcx, [rbp+178h]; this
0x1800160a9  lea     r8, aWil; "wil"
0x1800160b0  mov     edx, 0DCh; void *
0x1800160b5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800160ba  mov     ebx, eax
0x1800160bc  lea     rcx, [rsp+270h+var_238]
0x1800160c1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800160c6  jmp     short loc_180016118
0x1800160c8  lea     rdx, [rsp+270h+var_240]; int *
0x1800160cd  mov     rcx, rax; hHandle
0x1800160d0  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800160d5  mov     ebx, eax
0x1800160d7  test    eax, eax
0x1800160d9  jns     short loc_1800160F8
0x1800160db  mov     rcx, [rbp+178h]; this
0x1800160e2  mov     r9d, eax; char *
0x1800160e5  lea     r8, aWil; "wil"
0x1800160ec  mov     edx, 0DEh; void *
0x1800160f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800160f6  jmp     short loc_1800160BC
0x1800160f8  lea     rcx, [rsp+270h+var_238]
0x1800160fd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180016102  movsxd  rcx, [rsp+270h+var_240]
0x180016107  shl     rcx, 1Fh
0x18001610b  movsxd  rax, [rsp+270h+var_23C]
0x180016110  or      rcx, rax
0x180016113  mov     [rdi], rcx
0x180016116  xor     ebx, ebx
0x180016118  lea     rcx, [rsp+270h+var_230]
0x18001611d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180016122  mov     eax, ebx
0x180016124  mov     rcx, [rbp+170h+var_10]
0x18001612b  xor     rcx, rsp; StackCookie
0x18001612e  call    __security_check_cookie
0x180016133  lea     r11, [rsp+270h+var_s0]
0x18001613b  mov     rbx, [r11+18h]
0x18001613f  mov     rdi, [r11+28h]
0x180016143  mov     rsp, r11
0x180016146  pop     rbp
0x180016147  retn
```
