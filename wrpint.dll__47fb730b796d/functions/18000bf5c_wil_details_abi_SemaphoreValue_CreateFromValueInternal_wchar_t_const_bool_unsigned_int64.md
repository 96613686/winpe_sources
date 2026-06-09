# wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)

- ea: `0x18000bf5c`
- end: `0x18000c18d`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z`
- size: `561`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000b794`
- `0x18000bb64`

## callees

- `0x18000bf5c`
- `0x18000ce18`
- `0x18000ed74`
- `0x18000f1ac`
- `0x18000ff0c`
- `0x18000ff1c`
- `0x18001b7b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c08c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c12a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c08c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c12a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c061`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c06f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c104`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c113`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c061`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c06f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c104`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c113`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c07b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c11e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c07b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c11e`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000c025`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000c0cb`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000c025`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000c0cb`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        WCHAR *a2,
        __int64 a3,
        unsigned __int64 a4)
{
  WCHAR *v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rdx
  LONG v10; // ebp
  WCHAR *v11; // rcx
  LONG v12; // r8d
  wil::details *v13; // rcx
  HANDLE Semaphore; // r15
  int LastErrorFailHr; // eax
  unsigned int v16; // edi
  void *v18; // rdi
  DWORD LastError; // r14d
  __int64 v20; // r8
  const char *v21; // r9
  unsigned __int64 v22; // rsi
  wil::details *v23; // rcx
  HANDLE v24; // rbp
  int v25; // eax
  unsigned int v26; // ebx
  void *v27; // rdi
  DWORD v28; // esi
  __int64 v29; // r8
  const char *v30; // r9
  DWORD dwFlags; // [rsp+20h] [rbp-268h]
  DWORD dwFlagsa; // [rsp+20h] [rbp-268h]
  WCHAR Name[264]; // [rsp+30h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  v7 = Name;
  v8 = 2147483646;
  v9 = 260;
  v10 = 1;
  do
  {
    if ( !v8 )
      break;
    if ( !*a2 )
      break;
    *v7++ = *a2++;
    --v8;
    --v9;
  }
  while ( v9 );
  v11 = v7 - 1;
  if ( v9 )
    v11 = v7;
  *v11 = 0;
  StringCchCatW(Name, 0x104u, L"_p0");
  v12 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v12 = a4 & 0x7FFFFFFF;
  Semaphore = CreateSemaphoreExW(0, a4 & 0x7FFFFFFF, v12, Name, 0, 0x1F0003u);
  if ( Semaphore )
  {
    GetLastError();
    v18 = *(void **)this;
    if ( *(_QWORD *)this )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v18) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v20, v21);
      SetLastError(LastError);
    }
    *(_QWORD *)this = Semaphore;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v13);
    v16 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8B,
        (unsigned int)"wil",
        (const char *)(unsigned int)LastErrorFailHr,
        dwFlags);
      return v16;
    }
  }
  v22 = a4 >> 31;
  StringCchCatW(Name, 0x104u, L"h");
  if ( (_DWORD)v22 )
    v10 = v22;
  v24 = CreateSemaphoreExW(0, v22, v10, Name, 0, 0x1F0003u);
  if ( v24 )
  {
    GetLastError();
    v27 = (void *)*((_QWORD *)this + 1);
    if ( v27 )
    {
      v28 = GetLastError();
      if ( !CloseHandle(v27) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
      SetLastError(v28);
    }
    *((_QWORD *)this + 1) = v24;
  }
  else
  {
    v25 = wil::details::GetLastErrorFailHr(v23);
    v26 = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x90,
        (unsigned int)"wil",
        (const char *)(unsigned int)v25,
        dwFlagsa);
      return v26;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000bf5c  mov     [rsp+arg_8], rbx
0x18000bf61  push    rbp
0x18000bf62  push    rsi
0x18000bf63  push    rdi
0x18000bf64  push    r12
0x18000bf66  push    r13
0x18000bf68  push    r14
0x18000bf6a  push    r15
0x18000bf6c  sub     rsp, 250h
0x18000bf73  mov     rax, cs:__security_cookie
0x18000bf7a  xor     rax, rsp
0x18000bf7d  mov     [rsp+288h+var_48], rax
0x18000bf85  mov     rax, 0C000000000000000h
0x18000bf8f  mov     rsi, r9
0x18000bf92  mov     r8, rdx
0x18000bf95  mov     rbx, rcx
0x18000bf98  test    rax, r9
0x18000bf9b  jnz     loc_18000C174
0x18000bfa1  xor     r12d, r12d
0x18000bfa4  lea     rax, [rsp+288h+Name]
0x18000bfa9  mov     r13d, 104h
0x18000bfaf  mov     ecx, 7FFFFFFEh
0x18000bfb4  mov     edx, r13d
0x18000bfb7  lea     ebp, [r12+1]
0x18000bfbc  test    rcx, rcx
0x18000bfbf  jz      short loc_18000BFDF
0x18000bfc1  movzx   r9d, word ptr [r8]
0x18000bfc5  test    r9w, r9w
0x18000bfc9  jz      short loc_18000BFDF
0x18000bfcb  mov     [rax], r9w
0x18000bfcf  add     r8, 2
0x18000bfd3  add     rax, 2
0x18000bfd7  sub     rcx, rbp
0x18000bfda  sub     rdx, rbp
0x18000bfdd  jnz     short loc_18000BFBC
0x18000bfdf  test    rdx, rdx
0x18000bfe2  lea     rcx, [rax-2]
0x18000bfe6  lea     r8, aP0; "_p0"
0x18000bfed  mov     rdx, r13; unsigned __int64
0x18000bff0  cmovnz  rcx, rax
0x18000bff4  mov     [rcx], r12w
0x18000bff8  lea     rcx, [rsp+288h+Name]; wchar_t *
0x18000bffd  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000c002  mov     edx, esi
0x18000c004  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000c00c  and     edx, 7FFFFFFFh; lInitialCount
0x18000c012  mov     [rsp+288h+dwFlags], r12d; int
0x18000c017  mov     r8d, ebp
0x18000c01a  lea     r9, [rsp+288h+Name]; lpName
0x18000c01f  cmova   r8d, edx; lMaximumCount
0x18000c023  xor     ecx, ecx; lpSemaphoreAttributes
0x18000c025  call    cs:__imp_CreateSemaphoreExW
0x18000c02b  mov     r15, rax
0x18000c02e  test    rax, rax
0x18000c031  jnz     short loc_18000C061
0x18000c033  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000c038  mov     edi, eax
0x18000c03a  test    eax, eax
0x18000c03c  jns     short loc_18000C095
0x18000c03e  mov     rcx, [rsp+288h]; this
0x18000c046  lea     r8, aWil; "wil"
0x18000c04d  mov     r9d, eax; char *
0x18000c050  mov     edx, 8Bh; void *
0x18000c055  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c05a  mov     eax, edi
0x18000c05c  jmp     loc_18000C136
0x18000c061  call    cs:__imp_GetLastError
0x18000c067  mov     rdi, [rbx]
0x18000c06a  test    rdi, rdi
0x18000c06d  jz      short loc_18000C092
0x18000c06f  call    cs:__imp_GetLastError
0x18000c075  mov     rcx, rdi; hObject
0x18000c078  mov     r14d, eax
0x18000c07b  call    cs:__imp_CloseHandle
0x18000c081  test    eax, eax
0x18000c083  jz      loc_18000C17A
0x18000c089  mov     ecx, r14d; dwErrCode
0x18000c08c  call    cs:__imp_SetLastError
0x18000c092  mov     [rbx], r15
0x18000c095  lea     r8, asc_180023288; "h"
0x18000c09c  shr     rsi, 1Fh
0x18000c0a0  mov     rdx, r13; unsigned __int64
0x18000c0a3  lea     rcx, [rsp+288h+Name]; wchar_t *
0x18000c0a8  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000c0ad  test    esi, esi
0x18000c0af  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000c0b7  lea     r9, [rsp+288h+Name]; lpName
0x18000c0bc  mov     [rsp+288h+dwFlags], r12d; int
0x18000c0c1  cmovnz  ebp, esi
0x18000c0c4  mov     edx, esi; lInitialCount
0x18000c0c6  mov     r8d, ebp; lMaximumCount
0x18000c0c9  xor     ecx, ecx; lpSemaphoreAttributes
0x18000c0cb  call    cs:__imp_CreateSemaphoreExW
0x18000c0d1  mov     rbp, rax
0x18000c0d4  test    rax, rax
0x18000c0d7  jnz     short loc_18000C104
0x18000c0d9  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000c0de  mov     ebx, eax
0x18000c0e0  test    eax, eax
0x18000c0e2  jns     short loc_18000C134
0x18000c0e4  mov     rcx, [rsp+288h]; this
0x18000c0ec  lea     r8, aWil; "wil"
0x18000c0f3  mov     r9d, eax; char *
0x18000c0f6  mov     edx, 90h; void *
0x18000c0fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c100  mov     eax, ebx
0x18000c102  jmp     short loc_18000C136
0x18000c104  call    cs:__imp_GetLastError
0x18000c10a  mov     rdi, [rbx+8]
0x18000c10e  test    rdi, rdi
0x18000c111  jz      short loc_18000C130
0x18000c113  call    cs:__imp_GetLastError
0x18000c119  mov     rcx, rdi; hObject
0x18000c11c  mov     esi, eax
0x18000c11e  call    cs:__imp_CloseHandle
0x18000c124  test    eax, eax
0x18000c126  jz      short loc_18000C161
0x18000c128  mov     ecx, esi; dwErrCode
0x18000c12a  call    cs:__imp_SetLastError
0x18000c130  mov     [rbx+8], rbp
0x18000c134  xor     eax, eax
0x18000c136  mov     rcx, [rsp+288h+var_48]
0x18000c13e  xor     rcx, rsp; StackCookie
0x18000c141  call    __security_check_cookie
0x18000c146  mov     rbx, [rsp+288h+arg_8]
0x18000c14e  add     rsp, 250h
0x18000c155  pop     r15
0x18000c157  pop     r14
0x18000c159  pop     r13
0x18000c15b  pop     r12
0x18000c15d  pop     rdi
0x18000c15e  pop     rsi
0x18000c15f  pop     rbp
0x18000c160  retn
0x18000c161  mov     rcx, [rsp+288h]; this
0x18000c169  mov     edx, 0A0Bh; void *
0x18000c16e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c174  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000c17a  mov     rcx, [rsp+288h]; this
0x18000c182  mov     edx, 0A0Bh; void *
0x18000c187  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
