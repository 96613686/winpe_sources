# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000e36c`
- end: `0x18000e63a`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `718`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18001f014`

## callees

- `0x18000e350`
- `0x18000e36c`
- `0x18000e640`
- `0x18000e7a4`
- `0x18001f1bc`
- `0x18001f89c`
- `0x18002fe40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e564`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e564`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000e478`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000e530`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000e478`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000e530`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  __int64 v5; // r14
  __int64 v6; // r9
  __int64 v7; // rdx
  bool v9; // zf
  WCHAR *v10; // rcx
  __int64 v11; // rdx
  WCHAR *v12; // rax
  __int64 v13; // r8
  const unsigned __int16 *v14; // r9
  __int64 v15; // rcx
  WCHAR *v16; // rdx
  __int64 v17; // rax
  WCHAR *v18; // rcx
  wil::details *v19; // rax
  wil::details *v20; // rdi
  int ValueFromSemaphore; // eax
  unsigned int v22; // r8d
  unsigned int LastError; // esi
  __int64 v24; // rdx
  WCHAR *v25; // rax
  __int64 v26; // r8
  WCHAR *v27; // rax
  const unsigned __int16 *v28; // rcx
  __int64 v29; // rbx
  WCHAR *v30; // rdx
  wil::details *v31; // rax
  const char *v32; // r9
  wil::details *v33; // rbx
  void *v34; // rdx
  const char *v36; // r9
  int v37; // eax
  void *v38; // rdx
  unsigned int v39; // r8d
  void *v40; // rdx
  void *v41; // rdx
  int v42; // [rsp+20h] [rbp-E0h] BYREF
  int v43; // [rsp+24h] [rbp-DCh] BYREF
  wil::details *v44; // [rsp+28h] [rbp-D8h] BYREF
  WCHAR Name[264]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  v4 = Name;
  v5 = 2147483646;
  *a3 = 0;
  v6 = 2147483646;
  v7 = 260;
  do
  {
    if ( !v6 )
      break;
    if ( !*a1 )
      break;
    *v4++ = *a1++;
    --v6;
    --v7;
  }
  while ( v7 );
  v9 = v7 == 0;
  v10 = v4 - 1;
  v11 = 260;
  if ( !v9 )
    v10 = v4;
  v12 = Name;
  *v10 = 0;
  do
  {
    if ( !*v12 )
      break;
    ++v12;
    --v11;
  }
  while ( v11 );
  v13 = (260 - v11) & -(__int64)(v11 != 0);
  if ( v11 )
  {
    v14 = L"_p0";
    v15 = 2147483646;
    v16 = &Name[v13];
    v17 = 260 - v13;
    if ( v13 != 260 )
    {
      do
      {
        if ( !v15 )
          break;
        if ( !*v14 )
          break;
        *v16++ = *v14++;
        --v15;
        --v17;
      }
      while ( v17 );
    }
    v18 = v16 - 1;
    if ( v17 )
      v18 = v16;
    *v18 = 0;
  }
  v19 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v44 = v19;
  v20 = v19;
  if ( !v19 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v36);
    LastError = 0;
LABEL_42:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v44);
    return LastError;
  }
  v43 = 0;
  v42 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v19, &v43);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v22, (const char *)(unsigned int)ValueFromSemaphore, v42);
    goto LABEL_42;
  }
  v24 = 260;
  v25 = Name;
  do
  {
    if ( !*v25 )
      break;
    ++v25;
    --v24;
  }
  while ( v24 );
  v26 = (260 - v24) & -(__int64)(v24 != 0);
  if ( v24 )
  {
    v27 = &Name[v26];
    v28 = L"h";
    v29 = 260 - v26;
    if ( 260 != v26 )
    {
      do
      {
        if ( !v5 )
          break;
        if ( !*v28 )
          break;
        *v27++ = *v28++;
        --v5;
        --v29;
      }
      while ( v29 );
    }
    v30 = v27 - 1;
    if ( v29 )
      v30 = v27;
    *v30 = 0;
  }
  v31 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v33 = v31;
  if ( !v31 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v32);
LABEL_33:
    wil::details::CloseHandle(v20, v34);
    return LastError;
  }
  v37 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v31, &v42);
  LastError = v37;
  if ( v37 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v39, (const char *)(unsigned int)v37, v42);
    wil::details::CloseHandle(v33, v41);
    goto LABEL_33;
  }
  wil::details::CloseHandle(v33, v38);
  *a3 = v43 | (unsigned __int64)((__int64)v42 << 31);
  wil::details::CloseHandle(v20, v40);
  return 0;
}

```

## disassembly

```asm
0x18000e36c  mov     [rsp-8+arg_0], rbx
0x18000e371  mov     [rsp-8+arg_8], rsi
0x18000e376  push    rbp
0x18000e377  push    rdi
0x18000e378  push    r12
0x18000e37a  push    r14
0x18000e37c  push    r15
0x18000e37e  lea     rbp, [rsp-150h]
0x18000e386  sub     rsp, 250h
0x18000e38d  mov     rax, cs:__security_cookie
0x18000e394  xor     rax, rsp
0x18000e397  mov     [rbp+170h+var_30], rax
0x18000e39e  xor     r12d, r12d
0x18000e3a1  lea     rax, [rsp+270h+Name]
0x18000e3a6  mov     r14d, 7FFFFFFEh
0x18000e3ac  mov     [r8], r12
0x18000e3af  mov     ebx, 104h
0x18000e3b4  mov     r9d, r14d
0x18000e3b7  mov     edx, ebx
0x18000e3b9  mov     r15, r8
0x18000e3bc  test    r9, r9
0x18000e3bf  jz      short loc_18000E3E0
0x18000e3c1  movzx   r8d, word ptr [rcx]
0x18000e3c5  test    r8w, r8w
0x18000e3c9  jz      short loc_18000E3E0
0x18000e3cb  mov     [rax], r8w
0x18000e3cf  add     rcx, 2
0x18000e3d3  add     rax, 2
0x18000e3d7  dec     r9
0x18000e3da  sub     rdx, 1
0x18000e3de  jnz     short loc_18000E3BC
0x18000e3e0  test    rdx, rdx
0x18000e3e3  lea     rcx, [rax-2]
0x18000e3e7  mov     rdx, rbx
0x18000e3ea  cmovnz  rcx, rax
0x18000e3ee  lea     rax, [rsp+270h+Name]
0x18000e3f3  mov     [rcx], r12w
0x18000e3f7  cmp     [rax], r12w
0x18000e3fb  jz      short loc_18000E407
0x18000e3fd  add     rax, 2
0x18000e401  sub     rdx, 1
0x18000e405  jnz     short loc_18000E3F7
0x18000e407  mov     rcx, rbx
0x18000e40a  mov     rax, rdx
0x18000e40d  sub     rcx, rdx
0x18000e410  neg     rax
0x18000e413  sbb     r8, r8
0x18000e416  and     r8, rcx
0x18000e419  test    rdx, rdx
0x18000e41c  jz      short loc_18000E46C
0x18000e41e  mov     rax, rbx
0x18000e421  lea     rdx, [rsp+270h+Name]
0x18000e426  lea     r9, aP0; "_p0"
0x18000e42d  mov     rcx, r14
0x18000e430  lea     rdx, [rdx+r8*2]
0x18000e434  sub     rax, r8
0x18000e437  jz      short loc_18000E45D
0x18000e439  test    rcx, rcx
0x18000e43c  jz      short loc_18000E45D
0x18000e43e  movzx   r8d, word ptr [r9]
0x18000e442  test    r8w, r8w
0x18000e446  jz      short loc_18000E45D
0x18000e448  mov     [rdx], r8w
0x18000e44c  add     r9, 2
0x18000e450  add     rdx, 2
0x18000e454  dec     rcx
0x18000e457  sub     rax, 1
0x18000e45b  jnz     short loc_18000E439
0x18000e45d  test    rax, rax
0x18000e460  lea     rcx, [rdx-2]
0x18000e464  cmovnz  rcx, rdx
0x18000e468  mov     [rcx], r12w
0x18000e46c  lea     r8, [rsp+270h+Name]; lpName
0x18000e471  xor     edx, edx; bInheritHandle
0x18000e473  mov     ecx, 1F0003h; dwDesiredAccess
0x18000e478  call    cs:__imp_OpenSemaphoreW
0x18000e47e  mov     [rsp+270h+var_248], rax
0x18000e483  mov     rdi, rax
0x18000e486  test    rax, rax
0x18000e489  jz      loc_18000E564
0x18000e48f  lea     rdx, [rsp+270h+var_24C]; int *
0x18000e494  mov     [rsp+270h+var_24C], r12d
0x18000e499  mov     rcx, rax; hHandle
0x18000e49c  mov     [rsp+270h+var_250], r12d; int
0x18000e4a1  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000e4a6  mov     esi, eax
0x18000e4a8  test    eax, eax
0x18000e4aa  js      loc_18000E612
0x18000e4b0  mov     rdx, rbx
0x18000e4b3  lea     rax, [rsp+270h+Name]
0x18000e4b8  cmp     [rax], r12w
0x18000e4bc  jz      short loc_18000E4C8
0x18000e4be  add     rax, 2
0x18000e4c2  sub     rdx, 1
0x18000e4c6  jnz     short loc_18000E4B8
0x18000e4c8  mov     rcx, rbx
0x18000e4cb  mov     rax, rdx
0x18000e4ce  sub     rcx, rdx
0x18000e4d1  neg     rax
0x18000e4d4  sbb     r8, r8
0x18000e4d7  and     r8, rcx
0x18000e4da  test    rdx, rdx
0x18000e4dd  jz      short loc_18000E524
0x18000e4df  lea     rax, [rsp+270h+Name]
0x18000e4e4  lea     rax, [rax+r8*2]
0x18000e4e8  lea     rcx, asc_18003E878; "h"
0x18000e4ef  sub     rbx, r8
0x18000e4f2  jz      short loc_18000E515
0x18000e4f4  test    r14, r14
0x18000e4f7  jz      short loc_18000E515
0x18000e4f9  movzx   edx, word ptr [rcx]
0x18000e4fc  test    dx, dx
0x18000e4ff  jz      short loc_18000E515
0x18000e501  mov     [rax], dx
0x18000e504  add     rcx, 2
0x18000e508  add     rax, 2
0x18000e50c  dec     r14
0x18000e50f  sub     rbx, 1
0x18000e513  jnz     short loc_18000E4F4
0x18000e515  test    rbx, rbx
0x18000e518  lea     rdx, [rax-2]
0x18000e51c  cmovnz  rdx, rax
0x18000e520  mov     [rdx], r12w
0x18000e524  lea     r8, [rsp+270h+Name]; lpName
0x18000e529  xor     edx, edx; bInheritHandle
0x18000e52b  mov     ecx, 1F0003h; dwDesiredAccess
0x18000e530  call    cs:__imp_OpenSemaphoreW
0x18000e536  mov     rbx, rax
0x18000e539  test    rax, rax
0x18000e53c  jnz     short loc_18000E5B6
0x18000e53e  mov     rcx, [rbp+178h]; this
0x18000e545  lea     r8, aWil; "wil"
0x18000e54c  mov     edx, 0DCh; void *
0x18000e551  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000e556  mov     esi, eax
0x18000e558  mov     rcx, rdi; this
0x18000e55b  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000e560  mov     eax, esi
0x18000e562  jmp     short loc_18000E58B
0x18000e564  call    cs:__imp_GetLastError
0x18000e56a  cmp     eax, 2
0x18000e56d  jz      loc_18000E628
0x18000e573  mov     rcx, [rbp+178h]; this
0x18000e57a  lea     r8, aWil; "wil"
0x18000e581  mov     edx, 0D0h; void *
0x18000e586  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000e58b  mov     rcx, [rbp+170h+var_30]
0x18000e592  xor     rcx, rsp; StackCookie
0x18000e595  call    __security_check_cookie
0x18000e59a  lea     r11, [rsp+270h+var_20]
0x18000e5a2  mov     rbx, [r11+30h]
0x18000e5a6  mov     rsi, [r11+38h]
0x18000e5aa  mov     rsp, r11
0x18000e5ad  pop     r15
0x18000e5af  pop     r14
0x18000e5b1  pop     r12
0x18000e5b3  pop     rdi
0x18000e5b4  pop     rbp
0x18000e5b5  retn
0x18000e5b6  lea     rdx, [rsp+270h+var_250]; int *
0x18000e5bb  mov     rcx, rbx; hHandle
0x18000e5be  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000e5c3  mov     esi, eax
0x18000e5c5  test    eax, eax
0x18000e5c7  js      short loc_18000E5F1
0x18000e5c9  mov     rcx, rbx; this
0x18000e5cc  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000e5d1  movsxd  rax, [rsp+270h+var_24C]
0x18000e5d6  movsxd  rcx, [rsp+270h+var_250]
0x18000e5db  shl     rcx, 1Fh
0x18000e5df  or      rcx, rax
0x18000e5e2  mov     [r15], rcx
0x18000e5e5  mov     rcx, rdi; this
0x18000e5e8  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000e5ed  xor     eax, eax
0x18000e5ef  jmp     short loc_18000E58B
0x18000e5f1  mov     rcx, [rbp+178h]; this
0x18000e5f8  mov     r9d, eax; char *
0x18000e5fb  mov     edx, 0DEh; void *
0x18000e600  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e605  mov     rcx, rbx; this
0x18000e608  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000e60d  jmp     loc_18000E558
0x18000e612  mov     rcx, [rbp+178h]; this
0x18000e619  mov     r9d, eax; char *
0x18000e61c  mov     edx, 0D6h; void *
0x18000e621  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e626  jmp     short loc_18000E62B
0x18000e628  mov     esi, r12d
0x18000e62b  lea     rcx, [rsp+270h+var_248]
0x18000e630  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000e635  jmp     loc_18000E560
```
