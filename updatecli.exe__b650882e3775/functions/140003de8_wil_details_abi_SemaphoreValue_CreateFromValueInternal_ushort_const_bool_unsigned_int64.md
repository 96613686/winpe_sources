# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x140003de8`
- end: `0x140004012`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140003a18`

## callees

- `0x140002130`
- `0x140003de8`
- `0x140004678`
- `0x140005434`
- `0x140005d10`
- `0x14000627c`
- `0x14000628c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140003eac`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140003f4f`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140003eac`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140003f4f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003f13`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003fae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003f13`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003fae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003ee8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003ef6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003f88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003f97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003ee8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003ef6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003f88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003f97`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003f02`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003fa2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003f02`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003fa2`

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
  int LastErrorFailHr; // eax
  unsigned __int64 v16; // rdx
  unsigned int v17; // edi
  void *v19; // rdi
  DWORD LastError; // r14d
  __int64 v21; // r8
  const char *v22; // r9
  unsigned __int64 v23; // rbp
  wil::details *v24; // rcx
  HANDLE v25; // rsi
  int v26; // eax
  unsigned int v27; // ebx
  void *v28; // rdi
  DWORD v29; // ebp
  __int64 v30; // r8
  const char *v31; // r9
  DWORD dwFlags; // [rsp+20h] [rbp-258h]
  DWORD dwFlagsa; // [rsp+20h] [rbp-258h]
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
        (unsigned int)"wil",
        (const char *)(unsigned int)LastErrorFailHr,
        dwFlags);
      return v17;
    }
  }
  v23 = a4 >> 31;
  StringCchCatW(Name, v16, L"h");
  if ( (_DWORD)v23 )
    v10 = v23;
  v25 = CreateSemaphoreExW(0, v23, v10, Name, 0, 0x1F0003u);
  if ( v25 )
  {
    GetLastError();
    v28 = (void *)*((_QWORD *)this + 1);
    if ( v28 )
    {
      v29 = GetLastError();
      if ( !CloseHandle(v28) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
      SetLastError(v29);
    }
    *((_QWORD *)this + 1) = v25;
  }
  else
  {
    v26 = wil::details::GetLastErrorFailHr(v24);
    v27 = v26;
    if ( v26 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x90,
        (unsigned int)"wil",
        (const char *)(unsigned int)v26,
        dwFlagsa);
      return v27;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140003de8  mov     [rsp+arg_8], rbx
0x140003ded  mov     [rsp+arg_10], rbp
0x140003df2  push    rsi
0x140003df3  push    rdi
0x140003df4  push    r12
0x140003df6  push    r14
0x140003df8  push    r15
0x140003dfa  sub     rsp, 250h
0x140003e01  mov     rax, cs:__security_cookie
0x140003e08  xor     rax, rsp
0x140003e0b  mov     [rsp+278h+var_38], rax
0x140003e13  mov     rax, 0C000000000000000h
0x140003e1d  mov     rbp, r9
0x140003e20  mov     r8, rdx
0x140003e23  mov     rbx, rcx
0x140003e26  test    rax, r9
0x140003e29  jnz     loc_140003FF9
0x140003e2f  xor     r12d, r12d
0x140003e32  lea     rax, [rsp+278h+Name]
0x140003e37  mov     ecx, 7FFFFFFEh
0x140003e3c  mov     edx, 104h
0x140003e41  lea     esi, [r12+1]
0x140003e46  test    rcx, rcx
0x140003e49  jz      short loc_140003E69
0x140003e4b  movzx   r9d, word ptr [r8]
0x140003e4f  test    r9w, r9w
0x140003e53  jz      short loc_140003E69
0x140003e55  mov     [rax], r9w
0x140003e59  add     r8, 2
0x140003e5d  add     rax, 2
0x140003e61  sub     rcx, rsi
0x140003e64  sub     rdx, rsi; unsigned __int64
0x140003e67  jnz     short loc_140003E46
0x140003e69  test    rdx, rdx
0x140003e6c  lea     rcx, [rax-2]
0x140003e70  lea     r8, aP0; "_p0"
0x140003e77  cmovnz  rcx, rax
0x140003e7b  mov     [rcx], r12w
0x140003e7f  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x140003e84  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140003e89  mov     edx, ebp
0x140003e8b  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140003e93  and     edx, 7FFFFFFFh; lInitialCount
0x140003e99  mov     [rsp+278h+dwFlags], r12d; int
0x140003e9e  mov     r8d, esi
0x140003ea1  lea     r9, [rsp+278h+Name]; lpName
0x140003ea6  cmova   r8d, edx; lMaximumCount
0x140003eaa  xor     ecx, ecx; lpSemaphoreAttributes
0x140003eac  call    cs:__imp_CreateSemaphoreExW
0x140003eb2  mov     r15, rax
0x140003eb5  test    rax, rax
0x140003eb8  jnz     short loc_140003EE8
0x140003eba  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140003ebf  mov     edi, eax
0x140003ec1  test    eax, eax
0x140003ec3  jns     short loc_140003F1C
0x140003ec5  mov     rcx, [rsp+278h]; this
0x140003ecd  lea     r8, aWil; "wil"
0x140003ed4  mov     r9d, eax; char *
0x140003ed7  mov     edx, 8Bh; void *
0x140003edc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003ee1  mov     eax, edi
0x140003ee3  jmp     loc_140003FBA
0x140003ee8  call    cs:__imp_GetLastError
0x140003eee  mov     rdi, [rbx]
0x140003ef1  test    rdi, rdi
0x140003ef4  jz      short loc_140003F19
0x140003ef6  call    cs:__imp_GetLastError
0x140003efc  mov     rcx, rdi; hObject
0x140003eff  mov     r14d, eax
0x140003f02  call    cs:__imp_CloseHandle
0x140003f08  test    eax, eax
0x140003f0a  jz      loc_140003FFF
0x140003f10  mov     ecx, r14d; dwErrCode
0x140003f13  call    cs:__imp_SetLastError
0x140003f19  mov     [rbx], r15
0x140003f1c  lea     r8, asc_14000DC38; "h"
0x140003f23  shr     rbp, 1Fh
0x140003f27  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x140003f2c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140003f31  test    ebp, ebp
0x140003f33  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140003f3b  lea     r9, [rsp+278h+Name]; lpName
0x140003f40  mov     [rsp+278h+dwFlags], r12d; int
0x140003f45  cmovnz  esi, ebp
0x140003f48  mov     edx, ebp; lInitialCount
0x140003f4a  mov     r8d, esi; lMaximumCount
0x140003f4d  xor     ecx, ecx; lpSemaphoreAttributes
0x140003f4f  call    cs:__imp_CreateSemaphoreExW
0x140003f55  mov     rsi, rax
0x140003f58  test    rax, rax
0x140003f5b  jnz     short loc_140003F88
0x140003f5d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140003f62  mov     ebx, eax
0x140003f64  test    eax, eax
0x140003f66  jns     short loc_140003FB8
0x140003f68  mov     rcx, [rsp+278h]; this
0x140003f70  lea     r8, aWil; "wil"
0x140003f77  mov     r9d, eax; char *
0x140003f7a  mov     edx, 90h; void *
0x140003f7f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003f84  mov     eax, ebx
0x140003f86  jmp     short loc_140003FBA
0x140003f88  call    cs:__imp_GetLastError
0x140003f8e  mov     rdi, [rbx+8]
0x140003f92  test    rdi, rdi
0x140003f95  jz      short loc_140003FB4
0x140003f97  call    cs:__imp_GetLastError
0x140003f9d  mov     rcx, rdi; hObject
0x140003fa0  mov     ebp, eax
0x140003fa2  call    cs:__imp_CloseHandle
0x140003fa8  test    eax, eax
0x140003faa  jz      short loc_140003FE6
0x140003fac  mov     ecx, ebp; dwErrCode
0x140003fae  call    cs:__imp_SetLastError
0x140003fb4  mov     [rbx+8], rsi
0x140003fb8  xor     eax, eax
0x140003fba  mov     rcx, [rsp+278h+var_38]
0x140003fc2  xor     rcx, rsp; StackCookie
0x140003fc5  call    __security_check_cookie
0x140003fca  lea     r11, [rsp+278h+var_28]
0x140003fd2  mov     rbx, [r11+38h]
0x140003fd6  mov     rbp, [r11+40h]
0x140003fda  mov     rsp, r11
0x140003fdd  pop     r15
0x140003fdf  pop     r14
0x140003fe1  pop     r12
0x140003fe3  pop     rdi
0x140003fe4  pop     rsi
0x140003fe5  retn
0x140003fe6  mov     rcx, [rsp+278h]; this
0x140003fee  mov     edx, 0A0Bh; void *
0x140003ff3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003ff9  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140003fff  mov     rcx, [rsp+278h]; this
0x140004007  mov     edx, 0A0Bh; void *
0x14000400c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
