# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18001a05c`
- end: `0x18001a27f`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `547`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180019cb8`

## callees

- `0x180001d60`
- `0x1800187c0`
- `0x18001a05c`
- `0x18001abe8`
- `0x18001c2e0`
- `0x18001cb88`
- `0x18001cb98`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18001a174`
- `KERNEL32!CloseHandle` at `0x18001a210`
- `KERNEL32!CloseHandle` at `0x18001a174`
- `KERNEL32!CloseHandle` at `0x18001a210`
- `KERNEL32!CreateSemaphoreExW` at `0x18001a125`
- `KERNEL32!CreateSemaphoreExW` at `0x18001a1c4`
- `KERNEL32!CreateSemaphoreExW` at `0x18001a125`
- `KERNEL32!CreateSemaphoreExW` at `0x18001a1c4`
- `KERNEL32!SetLastError` at `0x18001a185`
- `KERNEL32!SetLastError` at `0x18001a21c`
- `KERNEL32!SetLastError` at `0x18001a185`
- `KERNEL32!SetLastError` at `0x18001a21c`
- `KERNEL32!GetLastError` at `0x18001a15a`
- `KERNEL32!GetLastError` at `0x18001a168`
- `KERNEL32!GetLastError` at `0x18001a1f6`
- `KERNEL32!GetLastError` at `0x18001a205`
- `KERNEL32!GetLastError` at `0x18001a15a`
- `KERNEL32!GetLastError` at `0x18001a168`
- `KERNEL32!GetLastError` at `0x18001a1f6`
- `KERNEL32!GetLastError` at `0x18001a205`

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
  unsigned int v21; // r8d
  const char *v22; // r9
  unsigned __int64 v23; // rsi
  wil::details *v24; // rcx
  HANDLE v25; // rbp
  int v26; // eax
  unsigned int v27; // r8d
  unsigned int v28; // ebx
  void *v29; // rdi
  DWORD v30; // esi
  unsigned int v31; // r8d
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
0x18001a05c  mov     [rsp+arg_8], rbx
0x18001a061  push    rbp
0x18001a062  push    rsi
0x18001a063  push    rdi
0x18001a064  push    r12
0x18001a066  push    r13
0x18001a068  push    r14
0x18001a06a  push    r15
0x18001a06c  sub     rsp, 250h
0x18001a073  mov     rax, cs:__security_cookie
0x18001a07a  xor     rax, rsp
0x18001a07d  mov     [rsp+288h+var_48], rax
0x18001a085  mov     rax, 0C000000000000000h
0x18001a08f  mov     rsi, r9
0x18001a092  mov     r8, rdx
0x18001a095  mov     rbx, rcx
0x18001a098  test    rax, r9
0x18001a09b  jnz     loc_18001A266
0x18001a0a1  xor     r12d, r12d
0x18001a0a4  lea     rax, [rsp+288h+Name]
0x18001a0a9  mov     r13d, 104h
0x18001a0af  mov     ecx, 7FFFFFFEh
0x18001a0b4  mov     edx, r13d
0x18001a0b7  lea     ebp, [r12+1]
0x18001a0bc  test    rcx, rcx
0x18001a0bf  jz      short loc_18001A0DF
0x18001a0c1  movzx   r9d, word ptr [r8]
0x18001a0c5  test    r9w, r9w
0x18001a0c9  jz      short loc_18001A0DF
0x18001a0cb  mov     [rax], r9w
0x18001a0cf  add     r8, 2
0x18001a0d3  add     rax, 2
0x18001a0d7  sub     rcx, rbp
0x18001a0da  sub     rdx, rbp
0x18001a0dd  jnz     short loc_18001A0BC
0x18001a0df  test    rdx, rdx
0x18001a0e2  lea     rcx, [rax-2]
0x18001a0e6  lea     r8, aP0; "_p0"
0x18001a0ed  mov     rdx, r13; unsigned __int64
0x18001a0f0  cmovnz  rcx, rax
0x18001a0f4  mov     [rcx], r12w
0x18001a0f8  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x18001a0fd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001a102  mov     edx, esi
0x18001a104  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18001a10c  and     edx, 7FFFFFFFh; lInitialCount
0x18001a112  mov     [rsp+288h+dwFlags], r12d; int
0x18001a117  mov     r8d, ebp
0x18001a11a  lea     r9, [rsp+288h+Name]; lpName
0x18001a11f  cmova   r8d, edx; lMaximumCount
0x18001a123  xor     ecx, ecx; lpSemaphoreAttributes
0x18001a125  call    cs:__imp_CreateSemaphoreExW
0x18001a12b  mov     r15, rax
0x18001a12e  test    rax, rax
0x18001a131  jnz     short loc_18001A15A
0x18001a133  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001a138  mov     edi, eax
0x18001a13a  test    eax, eax
0x18001a13c  jns     short loc_18001A18E
0x18001a13e  mov     rcx, [rsp+288h]; this
0x18001a146  mov     r9d, eax; char *
0x18001a149  mov     edx, 8Bh; void *
0x18001a14e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a153  mov     eax, edi
0x18001a155  jmp     loc_18001A228
0x18001a15a  call    cs:__imp_GetLastError
0x18001a160  mov     rdi, [rbx]
0x18001a163  test    rdi, rdi
0x18001a166  jz      short loc_18001A18B
0x18001a168  call    cs:__imp_GetLastError
0x18001a16e  mov     rcx, rdi; hObject
0x18001a171  mov     r14d, eax
0x18001a174  call    cs:__imp_CloseHandle
0x18001a17a  test    eax, eax
0x18001a17c  jz      loc_18001A26C
0x18001a182  mov     ecx, r14d; dwErrCode
0x18001a185  call    cs:__imp_SetLastError
0x18001a18b  mov     [rbx], r15
0x18001a18e  lea     r8, asc_180023B30; "h"
0x18001a195  shr     rsi, 1Fh
0x18001a199  mov     rdx, r13; unsigned __int64
0x18001a19c  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x18001a1a1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001a1a6  test    esi, esi
0x18001a1a8  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18001a1b0  lea     r9, [rsp+288h+Name]; lpName
0x18001a1b5  mov     [rsp+288h+dwFlags], r12d; int
0x18001a1ba  cmovnz  ebp, esi
0x18001a1bd  mov     edx, esi; lInitialCount
0x18001a1bf  mov     r8d, ebp; lMaximumCount
0x18001a1c2  xor     ecx, ecx; lpSemaphoreAttributes
0x18001a1c4  call    cs:__imp_CreateSemaphoreExW
0x18001a1ca  mov     rbp, rax
0x18001a1cd  test    rax, rax
0x18001a1d0  jnz     short loc_18001A1F6
0x18001a1d2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001a1d7  mov     ebx, eax
0x18001a1d9  test    eax, eax
0x18001a1db  jns     short loc_18001A226
0x18001a1dd  mov     rcx, [rsp+288h]; this
0x18001a1e5  mov     r9d, eax; char *
0x18001a1e8  mov     edx, 90h; void *
0x18001a1ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a1f2  mov     eax, ebx
0x18001a1f4  jmp     short loc_18001A228
0x18001a1f6  call    cs:__imp_GetLastError
0x18001a1fc  mov     rdi, [rbx+8]
0x18001a200  test    rdi, rdi
0x18001a203  jz      short loc_18001A222
0x18001a205  call    cs:__imp_GetLastError
0x18001a20b  mov     rcx, rdi; hObject
0x18001a20e  mov     esi, eax
0x18001a210  call    cs:__imp_CloseHandle
0x18001a216  test    eax, eax
0x18001a218  jz      short loc_18001A253
0x18001a21a  mov     ecx, esi; dwErrCode
0x18001a21c  call    cs:__imp_SetLastError
0x18001a222  mov     [rbx+8], rbp
0x18001a226  xor     eax, eax
0x18001a228  mov     rcx, [rsp+288h+var_48]
0x18001a230  xor     rcx, rsp; StackCookie
0x18001a233  call    __security_check_cookie
0x18001a238  mov     rbx, [rsp+288h+arg_8]
0x18001a240  add     rsp, 250h
0x18001a247  pop     r15
0x18001a249  pop     r14
0x18001a24b  pop     r13
0x18001a24d  pop     r12
0x18001a24f  pop     rdi
0x18001a250  pop     rsi
0x18001a251  pop     rbp
0x18001a252  retn
0x18001a253  mov     rcx, [rsp+288h]; this
0x18001a25b  mov     edx, 0A0Bh; void *
0x18001a260  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001a266  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18001a26c  mov     rcx, [rsp+288h]; this
0x18001a274  mov     edx, 0A0Bh; void *
0x18001a279  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
