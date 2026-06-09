# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1400038f0`
- end: `0x140003b21`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `561`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140003410`

## callees

- `0x1400038f0`
- `0x1400047f0`
- `0x140006844`
- `0x140006f60`
- `0x140007d54`
- `0x140007d64`
- `0x14002e420`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400039f5`
- `KERNEL32!GetLastError` at `0x140003a03`
- `KERNEL32!GetLastError` at `0x140003a98`
- `KERNEL32!GetLastError` at `0x140003aa7`
- `KERNEL32!GetLastError` at `0x1400039f5`
- `KERNEL32!GetLastError` at `0x140003a03`
- `KERNEL32!GetLastError` at `0x140003a98`
- `KERNEL32!GetLastError` at `0x140003aa7`
- `KERNEL32!CloseHandle` at `0x140003a0f`
- `KERNEL32!CloseHandle` at `0x140003ab2`
- `KERNEL32!CloseHandle` at `0x140003a0f`
- `KERNEL32!CloseHandle` at `0x140003ab2`
- `KERNEL32!SetLastError` at `0x140003a20`
- `KERNEL32!SetLastError` at `0x140003abe`
- `KERNEL32!SetLastError` at `0x140003a20`
- `KERNEL32!SetLastError` at `0x140003abe`
- `KERNEL32!CreateSemaphoreExW` at `0x1400039b9`
- `KERNEL32!CreateSemaphoreExW` at `0x140003a5f`
- `KERNEL32!CreateSemaphoreExW` at `0x1400039b9`
- `KERNEL32!CreateSemaphoreExW` at `0x140003a5f`

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
0x1400038f0  mov     [rsp+arg_8], rbx
0x1400038f5  push    rbp
0x1400038f6  push    rsi
0x1400038f7  push    rdi
0x1400038f8  push    r12
0x1400038fa  push    r13
0x1400038fc  push    r14
0x1400038fe  push    r15
0x140003900  sub     rsp, 250h
0x140003907  mov     rax, cs:__security_cookie
0x14000390e  xor     rax, rsp
0x140003911  mov     [rsp+288h+var_48], rax
0x140003919  mov     rax, 0C000000000000000h
0x140003923  mov     rsi, r9
0x140003926  mov     r8, rdx
0x140003929  mov     rbx, rcx
0x14000392c  test    rax, r9
0x14000392f  jnz     loc_140003B08
0x140003935  xor     r12d, r12d
0x140003938  lea     rax, [rsp+288h+Name]
0x14000393d  mov     r13d, 104h
0x140003943  mov     ecx, 7FFFFFFEh
0x140003948  mov     edx, r13d
0x14000394b  lea     ebp, [r12+1]
0x140003950  test    rcx, rcx
0x140003953  jz      short loc_140003973
0x140003955  movzx   r9d, word ptr [r8]
0x140003959  test    r9w, r9w
0x14000395d  jz      short loc_140003973
0x14000395f  mov     [rax], r9w
0x140003963  add     r8, 2
0x140003967  add     rax, 2
0x14000396b  sub     rcx, rbp
0x14000396e  sub     rdx, rbp
0x140003971  jnz     short loc_140003950
0x140003973  test    rdx, rdx
0x140003976  lea     rcx, [rax-2]
0x14000397a  lea     r8, aP0; "_p0"
0x140003981  mov     rdx, r13; unsigned __int64
0x140003984  cmovnz  rcx, rax
0x140003988  mov     [rcx], r12w
0x14000398c  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x140003991  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140003996  mov     edx, esi
0x140003998  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1400039a0  and     edx, 7FFFFFFFh; lInitialCount
0x1400039a6  mov     [rsp+288h+dwFlags], r12d; int
0x1400039ab  mov     r8d, ebp
0x1400039ae  lea     r9, [rsp+288h+Name]; lpName
0x1400039b3  cmova   r8d, edx; lMaximumCount
0x1400039b7  xor     ecx, ecx; lpSemaphoreAttributes
0x1400039b9  call    cs:__imp_CreateSemaphoreExW
0x1400039bf  mov     r15, rax
0x1400039c2  test    rax, rax
0x1400039c5  jnz     short loc_1400039F5
0x1400039c7  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400039cc  mov     edi, eax
0x1400039ce  test    eax, eax
0x1400039d0  jns     short loc_140003A29
0x1400039d2  mov     rcx, [rsp+288h]; this
0x1400039da  lea     r8, aWil; "wil"
0x1400039e1  mov     r9d, eax; char *
0x1400039e4  mov     edx, 8Bh; void *
0x1400039e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400039ee  mov     eax, edi
0x1400039f0  jmp     loc_140003ACA
0x1400039f5  call    cs:__imp_GetLastError
0x1400039fb  mov     rdi, [rbx]
0x1400039fe  test    rdi, rdi
0x140003a01  jz      short loc_140003A26
0x140003a03  call    cs:__imp_GetLastError
0x140003a09  mov     rcx, rdi; hObject
0x140003a0c  mov     r14d, eax
0x140003a0f  call    cs:__imp_CloseHandle
0x140003a15  test    eax, eax
0x140003a17  jz      loc_140003B0E
0x140003a1d  mov     ecx, r14d; dwErrCode
0x140003a20  call    cs:__imp_SetLastError
0x140003a26  mov     [rbx], r15
0x140003a29  lea     r8, asc_1400329A0; "h"
0x140003a30  shr     rsi, 1Fh
0x140003a34  mov     rdx, r13; unsigned __int64
0x140003a37  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x140003a3c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140003a41  test    esi, esi
0x140003a43  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140003a4b  lea     r9, [rsp+288h+Name]; lpName
0x140003a50  mov     [rsp+288h+dwFlags], r12d; int
0x140003a55  cmovnz  ebp, esi
0x140003a58  mov     edx, esi; lInitialCount
0x140003a5a  mov     r8d, ebp; lMaximumCount
0x140003a5d  xor     ecx, ecx; lpSemaphoreAttributes
0x140003a5f  call    cs:__imp_CreateSemaphoreExW
0x140003a65  mov     rbp, rax
0x140003a68  test    rax, rax
0x140003a6b  jnz     short loc_140003A98
0x140003a6d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140003a72  mov     ebx, eax
0x140003a74  test    eax, eax
0x140003a76  jns     short loc_140003AC8
0x140003a78  mov     rcx, [rsp+288h]; this
0x140003a80  lea     r8, aWil; "wil"
0x140003a87  mov     r9d, eax; char *
0x140003a8a  mov     edx, 90h; void *
0x140003a8f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003a94  mov     eax, ebx
0x140003a96  jmp     short loc_140003ACA
0x140003a98  call    cs:__imp_GetLastError
0x140003a9e  mov     rdi, [rbx+8]
0x140003aa2  test    rdi, rdi
0x140003aa5  jz      short loc_140003AC4
0x140003aa7  call    cs:__imp_GetLastError
0x140003aad  mov     rcx, rdi; hObject
0x140003ab0  mov     esi, eax
0x140003ab2  call    cs:__imp_CloseHandle
0x140003ab8  test    eax, eax
0x140003aba  jz      short loc_140003AF5
0x140003abc  mov     ecx, esi; dwErrCode
0x140003abe  call    cs:__imp_SetLastError
0x140003ac4  mov     [rbx+8], rbp
0x140003ac8  xor     eax, eax
0x140003aca  mov     rcx, [rsp+288h+var_48]
0x140003ad2  xor     rcx, rsp; StackCookie
0x140003ad5  call    __security_check_cookie
0x140003ada  mov     rbx, [rsp+288h+arg_8]
0x140003ae2  add     rsp, 250h
0x140003ae9  pop     r15
0x140003aeb  pop     r14
0x140003aed  pop     r13
0x140003aef  pop     r12
0x140003af1  pop     rdi
0x140003af2  pop     rsi
0x140003af3  pop     rbp
0x140003af4  retn
0x140003af5  mov     rcx, [rsp+288h]; this
0x140003afd  mov     edx, 0A0Bh; void *
0x140003b02  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003b08  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140003b0e  mov     rcx, [rsp+288h]; this
0x140003b16  mov     edx, 0A0Bh; void *
0x140003b1b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
