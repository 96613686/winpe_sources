# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x140002af4`
- end: `0x140002d2e`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `570`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400031bc`

## callees

- `0x140002af4`
- `0x140002d34`
- `0x14000d580`
- `0x1400184f0`
- `0x140018538`
- `0x140018600`
- `0x140026c20`
- `0x14002f7fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140002c20`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140002c20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002c62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002c62`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        WCHAR *a2,
        __int64 a3,
        unsigned __int64 a4)
{
  WCHAR *v7; // rax
  __int64 v8; // r9
  __int64 v9; // rcx
  __int64 v10; // rdx
  unsigned int v11; // edi
  bool v12; // zf
  WCHAR *v13; // rcx
  __int64 v14; // rdx
  WCHAR *v15; // rax
  __int64 v16; // r8
  const wchar_t *v17; // rcx
  WCHAR *v18; // rdx
  __int64 v19; // rax
  WCHAR *v20; // rcx
  LONG v21; // r8d
  wil::details *v22; // rcx
  HANDLE Semaphore; // rsi
  int LastErrorFailHr; // eax
  unsigned int v25; // esi
  unsigned __int64 v27; // rbp
  WCHAR *v28; // rax
  __int64 v29; // rdx
  __int64 v30; // r8
  int semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  unsigned int v32; // ebx
  size_t dwFlags; // [rsp+20h] [rbp-268h]
  WCHAR Name[264]; // [rsp+40h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  v7 = Name;
  v8 = 2147483646;
  v9 = 2147483646;
  v10 = 260;
  v11 = 1;
  do
  {
    if ( !v9 )
      break;
    if ( !*a2 )
      break;
    *v7++ = *a2++;
    --v9;
    --v10;
  }
  while ( v10 );
  v12 = v10 == 0;
  v13 = v7 - 1;
  v14 = 260;
  if ( !v12 )
    v13 = v7;
  v15 = Name;
  *v13 = 0;
  do
  {
    if ( !*v15 )
      break;
    ++v15;
    --v14;
  }
  while ( v14 );
  v16 = (260 - v14) & -(__int64)(v14 != 0);
  if ( v14 )
  {
    v17 = L"_p0";
    v18 = &Name[v16];
    v19 = 260 - v16;
    if ( v16 != 260 )
    {
      do
      {
        if ( !v8 )
          break;
        if ( !*v17 )
          break;
        *v18++ = *v17++;
        --v8;
        --v19;
      }
      while ( v19 );
    }
    v20 = v18 - 1;
    if ( v19 )
      v20 = v18;
    *v20 = 0;
  }
  v21 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v21 = a4 & 0x7FFFFFFF;
  Semaphore = CreateSemaphoreExW(0, a4 & 0x7FFFFFFF, v21, Name, 0, 0x1F0003u);
  if ( Semaphore )
  {
    GetLastError();
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      this,
      Semaphore);
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v22);
    v25 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8B,
        (unsigned int)"wil",
        (const char *)(unsigned int)LastErrorFailHr,
        dwFlags);
      return v25;
    }
  }
  v27 = a4 >> 31;
  v28 = Name;
  v29 = 260;
  do
  {
    if ( !*v28 )
      break;
    ++v28;
    --v29;
  }
  while ( v29 );
  if ( v29 )
  {
    v30 = (260 - v29) & -(__int64)(v29 != 0);
    StringCopyWorkerW(&Name[v30], 260 - v30, (size_t *)v30, L"h", dwFlags);
  }
  if ( (_DWORD)v27 )
    v11 = v27;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((char *)this + 8, (unsigned int)v27, v11, Name);
  v32 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x90,
    (unsigned int)"wil",
    (const char *)(unsigned int)semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
    dwFlags);
  return v32;
}

```

## disassembly

```asm
0x140002af4  mov     [rsp+arg_8], rbx
0x140002af9  push    rbp
0x140002afa  push    rsi
0x140002afb  push    rdi
0x140002afc  push    r14
0x140002afe  push    r15
0x140002b00  sub     rsp, 260h
0x140002b07  mov     rax, cs:__security_cookie
0x140002b0e  xor     rax, rsp
0x140002b11  mov     [rsp+288h+var_38], rax
0x140002b19  mov     rax, 0C000000000000000h
0x140002b23  mov     rbp, r9
0x140002b26  mov     r8, rdx
0x140002b29  mov     r14, rcx
0x140002b2c  test    rax, r9
0x140002b2f  jz      short loc_140002B37
0x140002b31  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140002b37  xor     r15d, r15d
0x140002b3a  lea     rax, [rsp+288h+Name]
0x140002b3f  mov     r9d, 7FFFFFFEh
0x140002b45  mov     ebx, 104h
0x140002b4a  mov     ecx, r9d
0x140002b4d  mov     edx, ebx
0x140002b4f  lea     edi, [r15+1]
0x140002b53  test    rcx, rcx
0x140002b56  jz      short loc_140002B76
0x140002b58  movzx   r10d, word ptr [r8]
0x140002b5c  test    r10w, r10w
0x140002b60  jz      short loc_140002B76
0x140002b62  mov     [rax], r10w
0x140002b66  add     r8, 2
0x140002b6a  add     rax, 2
0x140002b6e  sub     rcx, rdi
0x140002b71  sub     rdx, rdi
0x140002b74  jnz     short loc_140002B53
0x140002b76  test    rdx, rdx
0x140002b79  lea     rcx, [rax-2]
0x140002b7d  mov     rdx, rbx
0x140002b80  cmovnz  rcx, rax
0x140002b84  lea     rax, [rsp+288h+Name]
0x140002b89  mov     [rcx], r15w
0x140002b8d  cmp     [rax], r15w
0x140002b91  jz      short loc_140002B9C
0x140002b93  add     rax, 2
0x140002b97  sub     rdx, rdi
0x140002b9a  jnz     short loc_140002B8D
0x140002b9c  mov     rcx, rbx
0x140002b9f  mov     rax, rdx
0x140002ba2  sub     rcx, rdx
0x140002ba5  neg     rax
0x140002ba8  sbb     r8, r8
0x140002bab  and     r8, rcx
0x140002bae  test    rdx, rdx
0x140002bb1  jz      short loc_140002BFD
0x140002bb3  mov     rax, rbx
0x140002bb6  lea     rdx, [rsp+288h+Name]
0x140002bbb  lea     rcx, aP0; "_p0"
0x140002bc2  lea     rdx, [rdx+r8*2]
0x140002bc6  sub     rax, r8
0x140002bc9  jz      short loc_140002BEE
0x140002bcb  test    r9, r9
0x140002bce  jz      short loc_140002BEE
0x140002bd0  movzx   r8d, word ptr [rcx]
0x140002bd4  test    r8w, r8w
0x140002bd8  jz      short loc_140002BEE
0x140002bda  mov     [rdx], r8w
0x140002bde  add     rcx, 2
0x140002be2  add     rdx, 2
0x140002be6  sub     r9, rdi
0x140002be9  sub     rax, rdi
0x140002bec  jnz     short loc_140002BCB
0x140002bee  test    rax, rax
0x140002bf1  lea     rcx, [rdx-2]
0x140002bf5  cmovnz  rcx, rdx
0x140002bf9  mov     [rcx], r15w
0x140002bfd  mov     edx, ebp
0x140002bff  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140002c07  and     edx, 7FFFFFFFh; lInitialCount
0x140002c0d  mov     dword ptr [rsp+288h+dwFlags], r15d; int
0x140002c12  mov     r8d, edi
0x140002c15  lea     r9, [rsp+288h+Name]; lpName
0x140002c1a  cmova   r8d, edx; lMaximumCount
0x140002c1e  xor     ecx, ecx; lpSemaphoreAttributes
0x140002c20  call    cs:__imp_CreateSemaphoreExW
0x140002c27  nop     dword ptr [rax+rax+00h]
0x140002c2c  mov     rsi, rax
0x140002c2f  test    rax, rax
0x140002c32  jnz     short loc_140002C62
0x140002c34  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140002c39  mov     esi, eax
0x140002c3b  test    eax, eax
0x140002c3d  jns     short loc_140002C79
0x140002c3f  mov     rcx, [rsp+288h]; this
0x140002c47  lea     r8, aWil; "wil"
0x140002c4e  mov     r9d, eax; char *
0x140002c51  mov     edx, 8Bh; void *
0x140002c56  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002c5b  mov     eax, esi
0x140002c5d  jmp     loc_140002D06
0x140002c62  call    cs:__imp_GetLastError
0x140002c69  nop     dword ptr [rax+rax+00h]
0x140002c6e  mov     rdx, rsi
0x140002c71  mov     rcx, r14
0x140002c74  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140002c79  shr     rbp, 1Fh
0x140002c7d  lea     rax, [rsp+288h+Name]
0x140002c82  mov     rdx, rbx
0x140002c85  cmp     [rax], r15w
0x140002c89  jz      short loc_140002C94
0x140002c8b  add     rax, 2
0x140002c8f  sub     rdx, rdi
0x140002c92  jnz     short loc_140002C85
0x140002c94  mov     rcx, rbx
0x140002c97  mov     rax, rdx
0x140002c9a  sub     rcx, rdx
0x140002c9d  neg     rax
0x140002ca0  sbb     r8, r8
0x140002ca3  and     r8, rcx; pcchNewDestLength
0x140002ca6  test    rdx, rdx
0x140002ca9  jz      short loc_140002CC6
0x140002cab  sub     rbx, r8
0x140002cae  lea     rcx, [rsp+288h+Name]
0x140002cb3  lea     rcx, [rcx+r8*2]; pszDest
0x140002cb7  mov     rdx, rbx; cchDest
0x140002cba  lea     r9, pszSrc; "h"
0x140002cc1  call    StringCopyWorkerW
0x140002cc6  test    ebp, ebp
0x140002cc8  lea     rcx, [r14+8]
0x140002ccc  lea     r9, [rsp+288h+Name]
0x140002cd1  mov     edx, ebp
0x140002cd3  cmovnz  edi, ebp
0x140002cd6  mov     r8d, edi
0x140002cd9  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x140002cde  mov     ebx, eax
0x140002ce0  test    eax, eax
0x140002ce2  jns     short loc_140002D04
0x140002ce4  mov     rcx, [rsp+288h]; this
0x140002cec  lea     r8, aWil; "wil"
0x140002cf3  mov     r9d, eax; char *
0x140002cf6  mov     edx, 90h; void *
0x140002cfb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002d00  mov     eax, ebx
0x140002d02  jmp     short loc_140002D06
0x140002d04  xor     eax, eax
0x140002d06  mov     rcx, [rsp+288h+var_38]
0x140002d0e  xor     rcx, rsp; StackCookie
0x140002d11  call    __security_check_cookie
0x140002d16  mov     rbx, [rsp+288h+arg_8]
0x140002d1e  add     rsp, 260h
0x140002d25  pop     r15
0x140002d27  pop     r14
0x140002d29  pop     rdi
0x140002d2a  pop     rsi
0x140002d2b  pop     rbp
0x140002d2c  retn
```
