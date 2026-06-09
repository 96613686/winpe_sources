# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180034d48`
- end: `0x180034f63`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `539`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800345d8`
- `0x18003497c`

## callees

- `0x180004510`
- `0x180034d48`
- `0x180035ba8`
- `0x180037ea4`
- `0x1800388e8`
- `0x1800396ec`
- `0x1800396fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180034e0c`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180034ea8`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180034e0c`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180034ea8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180034e6c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180034ef1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180034e6c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180034ef1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034e41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034e4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034ecb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034eda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034e41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034e4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034ecb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034eda`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034e5b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034ee5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034e5b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034ee5`

## string_xrefs

- `0x180034f31`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180034f51`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  unsigned __int64 v9; // rdx
  LONG v10; // esi
  WCHAR *v11; // rcx
  LONG v12; // r8d
  wil::details *v13; // rcx
  HANDLE Semaphore; // r15
  unsigned __int64 v15; // rdx
  int LastErrorFailHr; // ebx
  unsigned int v17; // r8d
  __int64 v18; // rdx
  void *v20; // rbx
  DWORD LastError; // r14d
  const char *v22; // r9
  unsigned __int64 v23; // rbp
  wil::details *v24; // rcx
  HANDLE v25; // rsi
  void *v26; // rbx
  DWORD v27; // ebp
  const char *v28; // r9
  DWORD dwFlags; // [rsp+20h] [rbp-258h]
  WCHAR Name[264]; // [rsp+30h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

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
  StringCchCatW(Name, v9, L"_p0");
  v12 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v12 = a4 & 0x7FFFFFFF;
  Semaphore = CreateSemaphoreExW(0, a4 & 0x7FFFFFFF, v12, Name, 0, 0x1F0003u);
  if ( Semaphore )
  {
    GetLastError();
    v20 = *(void **)this;
    if ( *(_QWORD *)this )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v20) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA0B,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v22);
      SetLastError(LastError);
    }
    *(_QWORD *)this = Semaphore;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v13);
    if ( LastErrorFailHr < 0 )
    {
      v18 = 139;
LABEL_13:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v18, v17, (const char *)(unsigned int)LastErrorFailHr, dwFlags);
      return (unsigned int)LastErrorFailHr;
    }
  }
  v23 = a4 >> 31;
  StringCchCatW(Name, v15, L"h");
  if ( (_DWORD)v23 )
    v10 = v23;
  v25 = CreateSemaphoreExW(0, v23, v10, Name, 0, 0x1F0003u);
  if ( v25 )
  {
    GetLastError();
    v26 = (void *)*((_QWORD *)this + 1);
    if ( v26 )
    {
      v27 = GetLastError();
      if ( !CloseHandle(v26) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA0B,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v28);
      SetLastError(v27);
    }
    *((_QWORD *)this + 1) = v25;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v24);
    if ( LastErrorFailHr < 0 )
    {
      v18 = 144;
      goto LABEL_13;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180034d48  mov     [rsp+arg_8], rbx
0x180034d4d  mov     [rsp+arg_10], rbp
0x180034d52  push    rsi
0x180034d53  push    rdi
0x180034d54  push    r12
0x180034d56  push    r14
0x180034d58  push    r15
0x180034d5a  sub     rsp, 250h
0x180034d61  mov     rax, cs:__security_cookie
0x180034d68  xor     rax, rsp
0x180034d6b  mov     [rsp+278h+var_38], rax
0x180034d73  mov     rax, 0C000000000000000h
0x180034d7d  mov     rbp, r9
0x180034d80  mov     r8, rdx
0x180034d83  mov     rdi, rcx
0x180034d86  test    rax, r9
0x180034d89  jnz     loc_180034F43
0x180034d8f  xor     r12d, r12d
0x180034d92  lea     rax, [rsp+278h+Name]
0x180034d97  mov     ecx, 7FFFFFFEh
0x180034d9c  mov     edx, 104h
0x180034da1  lea     esi, [r12+1]
0x180034da6  test    rcx, rcx
0x180034da9  jz      short loc_180034DC9
0x180034dab  movzx   r9d, word ptr [r8]
0x180034daf  test    r9w, r9w
0x180034db3  jz      short loc_180034DC9
0x180034db5  mov     [rax], r9w
0x180034db9  add     r8, 2
0x180034dbd  add     rax, 2
0x180034dc1  sub     rcx, rsi
0x180034dc4  sub     rdx, rsi; unsigned __int64
0x180034dc7  jnz     short loc_180034DA6
0x180034dc9  test    rdx, rdx
0x180034dcc  lea     rcx, [rax-2]
0x180034dd0  lea     r8, aP0; "_p0"
0x180034dd7  cmovnz  rcx, rax
0x180034ddb  mov     [rcx], r12w
0x180034ddf  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180034de4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180034de9  mov     edx, ebp
0x180034deb  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180034df3  and     edx, 7FFFFFFFh; lInitialCount
0x180034df9  mov     [rsp+278h+dwFlags], r12d; int
0x180034dfe  mov     r8d, esi
0x180034e01  lea     r9, [rsp+278h+Name]; lpName
0x180034e06  cmova   r8d, edx; lMaximumCount
0x180034e0a  xor     ecx, ecx; lpSemaphoreAttributes
0x180034e0c  call    cs:__imp_CreateSemaphoreExW
0x180034e12  mov     r15, rax
0x180034e15  test    rax, rax
0x180034e18  jnz     short loc_180034E41
0x180034e1a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180034e1f  mov     ebx, eax
0x180034e21  test    eax, eax
0x180034e23  jns     short loc_180034E75
0x180034e25  mov     edx, 8Bh; void *
0x180034e2a  mov     rcx, [rsp+278h]; this
0x180034e32  mov     r9d, ebx; char *
0x180034e35  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034e3a  mov     eax, ebx
0x180034e3c  jmp     loc_180034EFD
0x180034e41  call    cs:__imp_GetLastError
0x180034e47  mov     rbx, [rdi]
0x180034e4a  test    rbx, rbx
0x180034e4d  jz      short loc_180034E72
0x180034e4f  call    cs:__imp_GetLastError
0x180034e55  mov     rcx, rbx; hObject
0x180034e58  mov     r14d, eax
0x180034e5b  call    cs:__imp_CloseHandle
0x180034e61  test    eax, eax
0x180034e63  jz      loc_180034F49
0x180034e69  mov     ecx, r14d; dwErrCode
0x180034e6c  call    cs:__imp_SetLastError
0x180034e72  mov     [rdi], r15
0x180034e75  lea     r8, asc_1800A5370; "h"
0x180034e7c  shr     rbp, 1Fh
0x180034e80  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180034e85  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180034e8a  test    ebp, ebp
0x180034e8c  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180034e94  lea     r9, [rsp+278h+Name]; lpName
0x180034e99  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x180034e9e  cmovnz  esi, ebp
0x180034ea1  mov     edx, ebp; lInitialCount
0x180034ea3  mov     r8d, esi; lMaximumCount
0x180034ea6  xor     ecx, ecx; lpSemaphoreAttributes
0x180034ea8  call    cs:__imp_CreateSemaphoreExW
0x180034eae  mov     rsi, rax
0x180034eb1  test    rax, rax
0x180034eb4  jnz     short loc_180034ECB
0x180034eb6  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180034ebb  mov     ebx, eax
0x180034ebd  test    eax, eax
0x180034ebf  jns     short loc_180034EFB
0x180034ec1  mov     edx, 90h
0x180034ec6  jmp     loc_180034E2A
0x180034ecb  call    cs:__imp_GetLastError
0x180034ed1  mov     rbx, [rdi+8]
0x180034ed5  test    rbx, rbx
0x180034ed8  jz      short loc_180034EF7
0x180034eda  call    cs:__imp_GetLastError
0x180034ee0  mov     rcx, rbx; hObject
0x180034ee3  mov     ebp, eax
0x180034ee5  call    cs:__imp_CloseHandle
0x180034eeb  test    eax, eax
0x180034eed  jz      short loc_180034F29
0x180034eef  mov     ecx, ebp; dwErrCode
0x180034ef1  call    cs:__imp_SetLastError
0x180034ef7  mov     [rdi+8], rsi
0x180034efb  xor     eax, eax
0x180034efd  mov     rcx, [rsp+278h+var_38]
0x180034f05  xor     rcx, rsp; StackCookie
0x180034f08  call    __security_check_cookie
0x180034f0d  lea     r11, [rsp+278h+var_28]
0x180034f15  mov     rbx, [r11+38h]
0x180034f19  mov     rbp, [r11+40h]
0x180034f1d  mov     rsp, r11
0x180034f20  pop     r15
0x180034f22  pop     r14
0x180034f24  pop     r12
0x180034f26  pop     rdi
0x180034f27  pop     rsi
0x180034f28  retn
0x180034f29  mov     rcx, [rsp+278h]; this
0x180034f31  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180034f38  mov     edx, 0A0Bh; void *
0x180034f3d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180034f43  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180034f49  mov     rcx, [rsp+278h]; this
0x180034f51  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180034f58  mov     edx, 0A0Bh; void *
0x180034f5d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
