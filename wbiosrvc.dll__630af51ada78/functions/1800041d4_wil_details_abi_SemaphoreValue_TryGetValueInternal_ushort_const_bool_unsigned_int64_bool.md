# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800041d4`
- end: `0x18000441b`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `583`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180004db4`
- `0x18005338c`

## callees

- `0x180003c20`
- `0x180004014`
- `0x1800041d4`
- `0x180004d04`
- `0x180005a68`
- `0x18005388c`
- `0x180056358`
- `0x180060150`
- `0x180068f60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180004290`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180004352`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180004290`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180004352`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800042a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800042a3`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  __int64 v5; // r9
  __int64 v7; // r10
  WCHAR *v8; // rcx
  __int64 v9; // r8
  WCHAR *v10; // rax
  __int64 v11; // r9
  wil::details *v12; // rax
  wil::details *v13; // rbx
  const char *v14; // r9
  int ValueFromSemaphore; // eax
  unsigned __int64 v17; // rdx
  unsigned int v18; // edi
  void *v19; // rdx
  HANDLE v20; // rax
  const char *v21; // r9
  unsigned int LastError; // ebx
  int v23; // eax
  size_t v24; // [rsp+20h] [rbp-E0h]
  int v25; // [rsp+30h] [rbp-D0h] BYREF
  int v26; // [rsp+34h] [rbp-CCh] BYREF
  HANDLE v27; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v28[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  v4 = Name;
  *a3 = 0;
  v5 = 260;
  v7 = 2147483646;
  do
  {
    if ( !v7 )
      break;
    if ( !*a1 )
      break;
    *v4++ = *a1++;
    --v7;
    --v5;
  }
  while ( v5 );
  v8 = v4 - 1;
  v9 = 260;
  if ( v5 )
    v8 = v4;
  v10 = Name;
  *v8 = 0;
  do
  {
    if ( !*v10 )
      break;
    ++v10;
    --v9;
  }
  while ( v9 );
  if ( v9 )
  {
    v11 = (260 - v9) & -(__int64)(v9 != 0);
    StringCopyWorkerW(&Name[v11], 260 - v11, (size_t *)v9, L"_p0", v24);
  }
  v12 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v28[0] = v12;
  v13 = v12;
  if ( !v12 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v14);
    LastError = 0;
    goto LABEL_20;
  }
  v26 = 0;
  v25 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v12, &v26);
  v18 = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v24);
    wil::details::CloseHandle(v13, v19);
    return v18;
  }
  StringCchCatW(Name, v17, L"h");
  v20 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v27 = v20;
  if ( !v20 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v21);
LABEL_19:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v27);
LABEL_20:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v28);
    return LastError;
  }
  v23 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v20, &v25);
  LastError = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v23, v24);
    goto LABEL_19;
  }
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v27);
  *a3 = v26 | (unsigned __int64)((__int64)v25 << 31);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v28);
  return 0;
}

```

## disassembly

```asm
0x1800041d4  mov     [rsp-8+arg_0], rbx
0x1800041d9  mov     [rsp-8+arg_8], rsi
0x1800041de  push    rbp
0x1800041df  push    rdi
0x1800041e0  push    r14
0x1800041e2  lea     rbp, [rsp-170h]
0x1800041ea  sub     rsp, 270h
0x1800041f1  mov     rax, cs:__security_cookie
0x1800041f8  xor     rax, rsp
0x1800041fb  mov     [rbp+180h+var_20], rax
0x180004202  xor     r14d, r14d
0x180004205  lea     rax, [rsp+280h+Name]
0x18000420a  mov     edx, 104h
0x18000420f  mov     [r8], r14
0x180004212  mov     r9d, edx
0x180004215  mov     rsi, r8
0x180004218  mov     r10d, 7FFFFFFEh
0x18000421e  test    r10, r10
0x180004221  jz      short loc_180004242
0x180004223  movzx   r8d, word ptr [rcx]
0x180004227  test    r8w, r8w
0x18000422b  jz      short loc_180004242
0x18000422d  mov     [rax], r8w
0x180004231  add     rcx, 2
0x180004235  add     rax, 2
0x180004239  dec     r10
0x18000423c  sub     r9, 1
0x180004240  jnz     short loc_18000421E
0x180004242  lea     rcx, [rax-2]
0x180004246  test    r9, r9
0x180004249  mov     r8, rdx
0x18000424c  cmovnz  rcx, rax
0x180004250  lea     rax, [rsp+280h+Name]
0x180004255  mov     [rcx], r14w
0x180004259  cmp     [rax], r14w
0x18000425d  jz      short loc_180004269
0x18000425f  add     rax, 2
0x180004263  sub     r8, 1; pcchNewDestLength
0x180004267  jnz     short loc_180004259
0x180004269  mov     rcx, rdx
0x18000426c  mov     rax, r8
0x18000426f  sub     rcx, r8
0x180004272  neg     rax
0x180004275  sbb     r9, r9
0x180004278  and     r9, rcx
0x18000427b  test    r8, r8
0x18000427e  jnz     loc_180004397
0x180004284  lea     r8, [rsp+280h+Name]; lpName
0x180004289  xor     edx, edx; bInheritHandle
0x18000428b  mov     ecx, 1F0003h; dwDesiredAccess
0x180004290  call    cs:__imp_OpenSemaphoreW
0x180004296  mov     [rsp+280h+var_240], rax
0x18000429b  mov     rbx, rax
0x18000429e  test    rax, rax
0x1800042a1  jnz     short loc_1800042F1
0x1800042a3  call    cs:__imp_GetLastError
0x1800042a9  cmp     eax, 2
0x1800042ac  jz      loc_180004413
0x1800042b2  mov     rcx, [rbp+188h]; this
0x1800042b9  lea     r8, aWil; "wil"
0x1800042c0  mov     edx, 0D0h; void *
0x1800042c5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800042ca  mov     rcx, [rbp+180h+var_20]
0x1800042d1  xor     rcx, rsp; StackCookie
0x1800042d4  call    __security_check_cookie
0x1800042d9  lea     r11, [rsp+280h+var_10]
0x1800042e1  mov     rbx, [r11+20h]
0x1800042e5  mov     rsi, [r11+28h]
0x1800042e9  mov     rsp, r11
0x1800042ec  pop     r14
0x1800042ee  pop     rdi
0x1800042ef  pop     rbp
0x1800042f0  retn
0x1800042f1  lea     rdx, [rsp+280h+var_24C]; int *
0x1800042f6  mov     [rsp+280h+var_24C], r14d
0x1800042fb  mov     rcx, rbx; hHandle
0x1800042fe  mov     [rsp+280h+var_250], r14d
0x180004303  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180004308  mov     edi, eax
0x18000430a  test    eax, eax
0x18000430c  jns     short loc_180004335
0x18000430e  mov     rcx, [rbp+188h]; this
0x180004315  lea     r8, aWil; "wil"
0x18000431c  mov     r9d, eax; char *
0x18000431f  mov     edx, 0D6h; void *
0x180004324  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004329  mov     rcx, rbx; this
0x18000432c  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180004331  mov     eax, edi
0x180004333  jmp     short loc_1800042CA
0x180004335  lea     r8, asc_1800DCDDC; "h"
0x18000433c  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180004341  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004346  lea     r8, [rsp+280h+Name]; lpName
0x18000434b  xor     edx, edx; bInheritHandle
0x18000434d  mov     ecx, 1F0003h; dwDesiredAccess
0x180004352  call    cs:__imp_OpenSemaphoreW
0x180004358  mov     [rsp+280h+var_248], rax
0x18000435d  test    rax, rax
0x180004360  jnz     short loc_1800043B4
0x180004362  mov     rcx, [rbp+188h]; this
0x180004369  lea     r8, aWil; "wil"
0x180004370  mov     edx, 0DCh; void *
0x180004375  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000437a  mov     ebx, eax
0x18000437c  lea     rcx, [rsp+280h+var_248]
0x180004381  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180004386  lea     rcx, [rsp+280h+var_240]
0x18000438b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180004390  mov     eax, ebx
0x180004392  jmp     loc_1800042CA
0x180004397  sub     rdx, r9; cchDest
0x18000439a  lea     rcx, [rsp+280h+Name]
0x18000439f  lea     rcx, [rcx+r9*2]; pszDest
0x1800043a3  lea     r9, aP0; "_p0"
0x1800043aa  call    StringCopyWorkerW
0x1800043af  jmp     loc_180004284
0x1800043b4  lea     rdx, [rsp+280h+var_250]; int *
0x1800043b9  mov     rcx, rax; hHandle
0x1800043bc  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800043c1  mov     ebx, eax
0x1800043c3  test    eax, eax
0x1800043c5  jns     short loc_1800043E4
0x1800043c7  mov     rcx, [rbp+188h]; this
0x1800043ce  lea     r8, aWil; "wil"
0x1800043d5  mov     r9d, eax; char *
0x1800043d8  mov     edx, 0DEh; void *
0x1800043dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800043e2  jmp     short loc_18000437C
0x1800043e4  lea     rcx, [rsp+280h+var_248]
0x1800043e9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800043ee  movsxd  rax, [rsp+280h+var_24C]
0x1800043f3  movsxd  rcx, [rsp+280h+var_250]
0x1800043f8  shl     rcx, 1Fh
0x1800043fc  or      rcx, rax
0x1800043ff  mov     [rsi], rcx
0x180004402  lea     rcx, [rsp+280h+var_240]
0x180004407  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000440c  xor     eax, eax
0x18000440e  jmp     loc_1800042CA
0x180004413  mov     ebx, r14d
0x180004416  jmp     loc_180004386
```
