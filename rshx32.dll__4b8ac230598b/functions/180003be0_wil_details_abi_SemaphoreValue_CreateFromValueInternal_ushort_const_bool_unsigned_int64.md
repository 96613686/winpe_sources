# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180003be0`
- end: `0x180003e03`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `547`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000383c`
- `0x18001a148`

## callees

- `0x180003be0`
- `0x180004518`
- `0x180005230`
- `0x18000554c`
- `0x180005acc`
- `0x180005adc`
- `0x18001d370`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003ca9`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003d48`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003ca9`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003d48`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003d09`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003da0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003d09`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003da0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003cde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003cec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003cde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003cec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d89`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003cf8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d94`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003cf8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d94`

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
  unsigned int v16; // r8d
  unsigned int v17; // edi
  void *v19; // rdi
  DWORD LastError; // r14d
  __int64 v21; // r8
  const char *v22; // r9
  unsigned __int64 v23; // rsi
  wil::details *v24; // rcx
  HANDLE v25; // rbp
  int v26; // eax
  unsigned int v27; // r8d
  unsigned int v28; // ebx
  void *v29; // rdi
  DWORD v30; // esi
  __int64 v31; // r8
  const char *v32; // r9
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
    v19 = *(void **)this;
    if ( *(_QWORD *)this )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v19) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v21, v22);
      SetLastError(LastError);
    }
    *(_QWORD *)this = Semaphore;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v13);
    v17 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8B,
        v16,
        (const char *)(unsigned int)LastErrorFailHr,
        dwFlags);
      return v17;
    }
  }
  v23 = a4 >> 31;
  StringCchCatW(Name, 0x104u, L"h");
  if ( (_DWORD)v23 )
    v10 = v23;
  v25 = CreateSemaphoreExW(0, v23, v10, Name, 0, 0x1F0003u);
  if ( v25 )
  {
    GetLastError();
    v29 = (void *)*((_QWORD *)this + 1);
    if ( v29 )
    {
      v30 = GetLastError();
      if ( !CloseHandle(v29) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
      SetLastError(v30);
    }
    *((_QWORD *)this + 1) = v25;
  }
  else
  {
    v26 = wil::details::GetLastErrorFailHr(v24);
    v28 = v26;
    if ( v26 < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x90, v27, (const char *)(unsigned int)v26, dwFlagsa);
      return v28;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180003be0  mov     [rsp+arg_8], rbx
0x180003be5  push    rbp
0x180003be6  push    rsi
0x180003be7  push    rdi
0x180003be8  push    r12
0x180003bea  push    r13
0x180003bec  push    r14
0x180003bee  push    r15
0x180003bf0  sub     rsp, 250h
0x180003bf7  mov     rax, cs:__security_cookie
0x180003bfe  xor     rax, rsp
0x180003c01  mov     [rsp+288h+var_48], rax
0x180003c09  mov     rax, 0C000000000000000h
0x180003c13  mov     rsi, r9
0x180003c16  mov     r8, rdx
0x180003c19  mov     rbx, rcx
0x180003c1c  test    rax, r9
0x180003c1f  jnz     loc_180003DEA
0x180003c25  xor     r12d, r12d
0x180003c28  lea     rax, [rsp+288h+Name]
0x180003c2d  mov     r13d, 104h
0x180003c33  mov     ecx, 7FFFFFFEh
0x180003c38  mov     edx, r13d
0x180003c3b  lea     ebp, [r12+1]
0x180003c40  test    rcx, rcx
0x180003c43  jz      short loc_180003C63
0x180003c45  movzx   r9d, word ptr [r8]
0x180003c49  test    r9w, r9w
0x180003c4d  jz      short loc_180003C63
0x180003c4f  mov     [rax], r9w
0x180003c53  add     r8, 2
0x180003c57  add     rax, 2
0x180003c5b  sub     rcx, rbp
0x180003c5e  sub     rdx, rbp
0x180003c61  jnz     short loc_180003C40
0x180003c63  test    rdx, rdx
0x180003c66  lea     rcx, [rax-2]
0x180003c6a  lea     r8, aP0; "_p0"
0x180003c71  mov     rdx, r13; unsigned __int64
0x180003c74  cmovnz  rcx, rax
0x180003c78  mov     [rcx], r12w
0x180003c7c  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x180003c81  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003c86  mov     edx, esi
0x180003c88  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180003c90  and     edx, 7FFFFFFFh; lInitialCount
0x180003c96  mov     [rsp+288h+dwFlags], r12d; int
0x180003c9b  mov     r8d, ebp
0x180003c9e  lea     r9, [rsp+288h+Name]; lpName
0x180003ca3  cmova   r8d, edx; lMaximumCount
0x180003ca7  xor     ecx, ecx; lpSemaphoreAttributes
0x180003ca9  call    cs:__imp_CreateSemaphoreExW
0x180003caf  mov     r15, rax
0x180003cb2  test    rax, rax
0x180003cb5  jnz     short loc_180003CDE
0x180003cb7  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003cbc  mov     edi, eax
0x180003cbe  test    eax, eax
0x180003cc0  jns     short loc_180003D12
0x180003cc2  mov     rcx, [rsp+288h]; this
0x180003cca  mov     r9d, eax; char *
0x180003ccd  mov     edx, 8Bh; void *
0x180003cd2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003cd7  mov     eax, edi
0x180003cd9  jmp     loc_180003DAC
0x180003cde  call    cs:__imp_GetLastError
0x180003ce4  mov     rdi, [rbx]
0x180003ce7  test    rdi, rdi
0x180003cea  jz      short loc_180003D0F
0x180003cec  call    cs:__imp_GetLastError
0x180003cf2  mov     rcx, rdi; hObject
0x180003cf5  mov     r14d, eax
0x180003cf8  call    cs:__imp_CloseHandle
0x180003cfe  test    eax, eax
0x180003d00  jz      loc_180003DF0
0x180003d06  mov     ecx, r14d; dwErrCode
0x180003d09  call    cs:__imp_SetLastError
0x180003d0f  mov     [rbx], r15
0x180003d12  lea     r8, asc_180020BC8; "h"
0x180003d19  shr     rsi, 1Fh
0x180003d1d  mov     rdx, r13; unsigned __int64
0x180003d20  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x180003d25  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003d2a  test    esi, esi
0x180003d2c  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180003d34  lea     r9, [rsp+288h+Name]; lpName
0x180003d39  mov     [rsp+288h+dwFlags], r12d; int
0x180003d3e  cmovnz  ebp, esi
0x180003d41  mov     edx, esi; lInitialCount
0x180003d43  mov     r8d, ebp; lMaximumCount
0x180003d46  xor     ecx, ecx; lpSemaphoreAttributes
0x180003d48  call    cs:__imp_CreateSemaphoreExW
0x180003d4e  mov     rbp, rax
0x180003d51  test    rax, rax
0x180003d54  jnz     short loc_180003D7A
0x180003d56  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003d5b  mov     ebx, eax
0x180003d5d  test    eax, eax
0x180003d5f  jns     short loc_180003DAA
0x180003d61  mov     rcx, [rsp+288h]; this
0x180003d69  mov     r9d, eax; char *
0x180003d6c  mov     edx, 90h; void *
0x180003d71  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003d76  mov     eax, ebx
0x180003d78  jmp     short loc_180003DAC
0x180003d7a  call    cs:__imp_GetLastError
0x180003d80  mov     rdi, [rbx+8]
0x180003d84  test    rdi, rdi
0x180003d87  jz      short loc_180003DA6
0x180003d89  call    cs:__imp_GetLastError
0x180003d8f  mov     rcx, rdi; hObject
0x180003d92  mov     esi, eax
0x180003d94  call    cs:__imp_CloseHandle
0x180003d9a  test    eax, eax
0x180003d9c  jz      short loc_180003DD7
0x180003d9e  mov     ecx, esi; dwErrCode
0x180003da0  call    cs:__imp_SetLastError
0x180003da6  mov     [rbx+8], rbp
0x180003daa  xor     eax, eax
0x180003dac  mov     rcx, [rsp+288h+var_48]
0x180003db4  xor     rcx, rsp; StackCookie
0x180003db7  call    __security_check_cookie
0x180003dbc  mov     rbx, [rsp+288h+arg_8]
0x180003dc4  add     rsp, 250h
0x180003dcb  pop     r15
0x180003dcd  pop     r14
0x180003dcf  pop     r13
0x180003dd1  pop     r12
0x180003dd3  pop     rdi
0x180003dd4  pop     rsi
0x180003dd5  pop     rbp
0x180003dd6  retn
0x180003dd7  mov     rcx, [rsp+288h]; this
0x180003ddf  mov     edx, 0A0Bh; void *
0x180003de4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003dea  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003df0  mov     rcx, [rsp+288h]; this
0x180003df8  mov     edx, 0A0Bh; void *
0x180003dfd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
