# wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)

- ea: `0x18004029c`
- end: `0x180040533`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z`
- size: `663`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const wchar_t *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180044adc`
- `0x1802798c4`

## callees

- `0x18004029c`
- `0x18004053c`
- `0x1800e29a8`
- `0x1800e34bc`
- `0x180120584`
- `0x18015cb00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800403d0`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800404d8`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800403d0`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800404d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040433`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040514`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040433`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040514`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        WCHAR *a2,
        __int64 a3,
        unsigned __int64 a4)
{
  WCHAR *v7; // rax
  __int64 v8; // r14
  __int64 v9; // rcx
  __int64 v10; // rdx
  LONG v11; // edi
  bool v12; // zf
  WCHAR *v13; // rcx
  __int64 v14; // rdx
  WCHAR *v15; // rax
  __int64 v16; // r8
  const wchar_t *v17; // r9
  __int64 v18; // rcx
  WCHAR *v19; // rdx
  __int64 v20; // rax
  WCHAR *v21; // rcx
  LONG v22; // r8d
  wil::details *v23; // rcx
  HANDLE Semaphore; // rsi
  int LastErrorFailHr; // eax
  unsigned int v26; // esi
  unsigned __int64 v28; // rbp
  WCHAR *v29; // rax
  __int64 v30; // rdx
  __int64 v31; // r8
  WCHAR *v32; // rax
  const wchar_t *v33; // rcx
  __int64 v34; // rbx
  WCHAR *v35; // rcx
  wil::details *v36; // rcx
  HANDLE v37; // rbx
  int v38; // eax
  unsigned int v39; // ebx
  DWORD dwFlags; // [rsp+20h] [rbp-258h]
  DWORD dwFlagsa; // [rsp+20h] [rbp-258h]
  WCHAR Name[264]; // [rsp+30h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

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
    v18 = 2147483646;
    v19 = &Name[v16];
    v20 = 260 - v16;
    if ( v16 != 260 )
    {
      do
      {
        if ( !v18 )
          break;
        if ( !*v17 )
          break;
        *v19++ = *v17++;
        --v18;
        --v20;
      }
      while ( v20 );
    }
    v21 = v19 - 1;
    if ( v20 )
      v21 = v19;
    *v21 = 0;
  }
  v22 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v22 = a4 & 0x7FFFFFFF;
  Semaphore = CreateSemaphoreExW(0, a4 & 0x7FFFFFFF, v22, Name, 0, 0x1F0003u);
  if ( Semaphore )
  {
    GetLastError();
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      this,
      Semaphore);
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v23);
    v26 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8B,
        (unsigned int)"wil",
        (const char *)(unsigned int)LastErrorFailHr,
        dwFlags);
      return v26;
    }
  }
  v28 = a4 >> 31;
  v29 = Name;
  v30 = 260;
  do
  {
    if ( !*v29 )
      break;
    ++v29;
    --v30;
  }
  while ( v30 );
  v31 = (260 - v30) & -(__int64)(v30 != 0);
  if ( v30 )
  {
    v32 = &Name[v31];
    v33 = L"h";
    v34 = 260 - v31;
    if ( 260 != v31 )
    {
      do
      {
        if ( !v8 )
          break;
        if ( !*v33 )
          break;
        *v32++ = *v33++;
        --v8;
        --v34;
      }
      while ( v34 );
    }
    v35 = v32 - 1;
    if ( v34 )
      v35 = v32;
    *v35 = 0;
  }
  if ( (_DWORD)v28 )
    v11 = v28;
  v37 = CreateSemaphoreExW(0, v28, v11, Name, 0, 0x1F0003u);
  if ( v37 )
  {
    GetLastError();
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      (char *)this + 8,
      v37);
  }
  else
  {
    v38 = wil::details::GetLastErrorFailHr(v36);
    v39 = v38;
    if ( v38 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x90,
        (unsigned int)"wil",
        (const char *)(unsigned int)v38,
        dwFlagsa);
      return v39;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18004029c  mov     [rsp+arg_8], rbx
0x1800402a1  mov     [rsp+arg_10], rbp
0x1800402a6  push    rsi
0x1800402a7  push    rdi
0x1800402a8  push    r12
0x1800402aa  push    r14
0x1800402ac  push    r15
0x1800402ae  sub     rsp, 250h
0x1800402b5  mov     rax, cs:__security_cookie
0x1800402bc  xor     rax, rsp
0x1800402bf  mov     [rsp+278h+var_38], rax
0x1800402c7  mov     rax, 0C000000000000000h
0x1800402d1  mov     rbp, r9
0x1800402d4  mov     r8, rdx
0x1800402d7  mov     r15, rcx
0x1800402da  test    rax, r9
0x1800402dd  jnz     loc_18004052D
0x1800402e3  xor     r12d, r12d
0x1800402e6  lea     rax, [rsp+278h+Name]
0x1800402eb  mov     r14d, 7FFFFFFEh
0x1800402f1  mov     ebx, 104h
0x1800402f6  mov     ecx, r14d
0x1800402f9  mov     edx, ebx
0x1800402fb  lea     edi, [r12+1]
0x180040300  test    rcx, rcx
0x180040303  jz      short loc_180040323
0x180040305  movzx   r9d, word ptr [r8]
0x180040309  test    r9w, r9w
0x18004030d  jz      short loc_180040323
0x18004030f  mov     [rax], r9w
0x180040313  add     r8, 2
0x180040317  add     rax, 2
0x18004031b  sub     rcx, rdi
0x18004031e  sub     rdx, rdi
0x180040321  jnz     short loc_180040300
0x180040323  test    rdx, rdx
0x180040326  lea     rcx, [rax-2]
0x18004032a  mov     rdx, rbx
0x18004032d  cmovnz  rcx, rax
0x180040331  lea     rax, [rsp+278h+Name]
0x180040336  mov     [rcx], r12w
0x18004033a  cmp     [rax], r12w
0x18004033e  jz      short loc_180040349
0x180040340  add     rax, 2
0x180040344  sub     rdx, rdi
0x180040347  jnz     short loc_18004033A
0x180040349  mov     rcx, rbx
0x18004034c  mov     rax, rdx
0x18004034f  sub     rcx, rdx
0x180040352  neg     rax
0x180040355  sbb     r8, r8
0x180040358  and     r8, rcx
0x18004035b  test    rdx, rdx
0x18004035e  jz      short loc_1800403AD
0x180040360  mov     rax, rbx
0x180040363  lea     rdx, [rsp+278h+Name]
0x180040368  lea     r9, aP0; "_p0"
0x18004036f  mov     rcx, r14
0x180040372  lea     rdx, [rdx+r8*2]
0x180040376  sub     rax, r8
0x180040379  jz      short loc_18004039E
0x18004037b  test    rcx, rcx
0x18004037e  jz      short loc_18004039E
0x180040380  movzx   r8d, word ptr [r9]
0x180040384  test    r8w, r8w
0x180040388  jz      short loc_18004039E
0x18004038a  mov     [rdx], r8w
0x18004038e  add     r9, 2
0x180040392  add     rdx, 2
0x180040396  sub     rcx, rdi
0x180040399  sub     rax, rdi
0x18004039c  jnz     short loc_18004037B
0x18004039e  test    rax, rax
0x1800403a1  lea     rcx, [rdx-2]
0x1800403a5  cmovnz  rcx, rdx
0x1800403a9  mov     [rcx], r12w
0x1800403ad  mov     edx, ebp
0x1800403af  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800403b7  and     edx, 7FFFFFFFh; lInitialCount
0x1800403bd  mov     [rsp+278h+dwFlags], r12d; int
0x1800403c2  mov     r8d, edi
0x1800403c5  lea     r9, [rsp+278h+Name]; lpName
0x1800403ca  cmova   r8d, edx; lMaximumCount
0x1800403ce  xor     ecx, ecx; lpSemaphoreAttributes
0x1800403d0  call    cs:__imp_CreateSemaphoreExW
0x1800403d6  mov     rsi, rax
0x1800403d9  test    rax, rax
0x1800403dc  jnz     short loc_180040433
0x1800403de  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800403e3  mov     esi, eax
0x1800403e5  test    eax, eax
0x1800403e7  jns     short loc_180040444
0x1800403e9  mov     rcx, [rsp+278h]; this
0x1800403f1  lea     r8, aWil; "wil"
0x1800403f8  mov     r9d, eax; char *
0x1800403fb  mov     edx, 8Bh; void *
0x180040400  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040405  mov     eax, esi
0x180040407  mov     rcx, [rsp+278h+var_38]
0x18004040f  xor     rcx, rsp; StackCookie
0x180040412  call    __security_check_cookie
0x180040417  lea     r11, [rsp+278h+var_28]
0x18004041f  mov     rbx, [r11+38h]
0x180040423  mov     rbp, [r11+40h]
0x180040427  mov     rsp, r11
0x18004042a  pop     r15
0x18004042c  pop     r14
0x18004042e  pop     r12
0x180040430  pop     rdi
0x180040431  pop     rsi
0x180040432  retn
0x180040433  call    cs:__imp_GetLastError
0x180040439  mov     rdx, rsi
0x18004043c  mov     rcx, r15
0x18004043f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180040444  shr     rbp, 1Fh
0x180040448  lea     rax, [rsp+278h+Name]
0x18004044d  mov     rdx, rbx
0x180040450  cmp     [rax], r12w
0x180040454  jz      short loc_18004045F
0x180040456  add     rax, 2
0x18004045a  sub     rdx, rdi
0x18004045d  jnz     short loc_180040450
0x18004045f  mov     rcx, rbx
0x180040462  mov     rax, rdx
0x180040465  sub     rcx, rdx
0x180040468  neg     rax
0x18004046b  sbb     r8, r8
0x18004046e  and     r8, rcx
0x180040471  test    rdx, rdx
0x180040474  jz      short loc_1800404BA
0x180040476  lea     rax, [rsp+278h+Name]
0x18004047b  lea     rax, [rax+r8*2]
0x18004047f  lea     rcx, asc_18050452C; "h"
0x180040486  sub     rbx, r8
0x180040489  jz      short loc_1800404AB
0x18004048b  test    r14, r14
0x18004048e  jz      short loc_1800404AB
0x180040490  movzx   edx, word ptr [rcx]
0x180040493  test    dx, dx
0x180040496  jz      short loc_1800404AB
0x180040498  mov     [rax], dx
0x18004049b  add     rcx, 2
0x18004049f  add     rax, 2
0x1800404a3  sub     r14, rdi
0x1800404a6  sub     rbx, rdi
0x1800404a9  jnz     short loc_18004048B
0x1800404ab  test    rbx, rbx
0x1800404ae  lea     rcx, [rax-2]
0x1800404b2  cmovnz  rcx, rax
0x1800404b6  mov     [rcx], r12w
0x1800404ba  test    ebp, ebp
0x1800404bc  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800404c4  lea     r9, [rsp+278h+Name]; lpName
0x1800404c9  mov     [rsp+278h+dwFlags], r12d; int
0x1800404ce  cmovnz  edi, ebp
0x1800404d1  mov     edx, ebp; lInitialCount
0x1800404d3  mov     r8d, edi; lMaximumCount
0x1800404d6  xor     ecx, ecx; lpSemaphoreAttributes
0x1800404d8  call    cs:__imp_CreateSemaphoreExW
0x1800404de  mov     rbx, rax
0x1800404e1  test    rax, rax
0x1800404e4  jnz     short loc_180040514
0x1800404e6  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800404eb  mov     ebx, eax
0x1800404ed  test    eax, eax
0x1800404ef  jns     short loc_180040526
0x1800404f1  mov     rcx, [rsp+278h]; this
0x1800404f9  lea     r8, aWil; "wil"
0x180040500  mov     r9d, eax; char *
0x180040503  mov     edx, 90h; void *
0x180040508  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004050d  mov     eax, ebx
0x18004050f  jmp     loc_180040407
0x180040514  call    cs:__imp_GetLastError
0x18004051a  lea     rcx, [r15+8]
0x18004051e  mov     rdx, rbx
0x180040521  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180040526  xor     eax, eax
0x180040528  jmp     loc_180040407
0x18004052d  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
