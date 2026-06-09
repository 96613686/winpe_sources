# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x140002a8c`
- end: `0x140002cbd`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `561`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1400026bc`
- `0x14000539c`

## callees

- `0x140002a8c`
- `0x1400033d8`
- `0x140004100`
- `0x14000441c`
- `0x14000493c`
- `0x14000494c`
- `0x140014910`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140002bab`
- `KERNEL32!CloseHandle` at `0x140002c4e`
- `KERNEL32!CloseHandle` at `0x140002bab`
- `KERNEL32!CloseHandle` at `0x140002c4e`
- `KERNEL32!CreateSemaphoreExW` at `0x140002b55`
- `KERNEL32!CreateSemaphoreExW` at `0x140002bfb`
- `KERNEL32!CreateSemaphoreExW` at `0x140002b55`
- `KERNEL32!CreateSemaphoreExW` at `0x140002bfb`
- `KERNEL32!GetLastError` at `0x140002b91`
- `KERNEL32!GetLastError` at `0x140002b9f`
- `KERNEL32!GetLastError` at `0x140002c34`
- `KERNEL32!GetLastError` at `0x140002c43`
- `KERNEL32!GetLastError` at `0x140002b91`
- `KERNEL32!GetLastError` at `0x140002b9f`
- `KERNEL32!GetLastError` at `0x140002c34`
- `KERNEL32!GetLastError` at `0x140002c43`
- `KERNEL32!SetLastError` at `0x140002bbc`
- `KERNEL32!SetLastError` at `0x140002c5a`
- `KERNEL32!SetLastError` at `0x140002bbc`
- `KERNEL32!SetLastError` at `0x140002c5a`

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
  unsigned int v20; // r8d
  const char *v21; // r9
  unsigned __int64 v22; // rsi
  wil::details *v23; // rcx
  HANDLE v24; // rbp
  int v25; // eax
  unsigned int v26; // ebx
  void *v27; // rdi
  DWORD v28; // esi
  unsigned int v29; // r8d
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
0x140002a8c  mov     [rsp+arg_8], rbx
0x140002a91  push    rbp
0x140002a92  push    rsi
0x140002a93  push    rdi
0x140002a94  push    r12
0x140002a96  push    r13
0x140002a98  push    r14
0x140002a9a  push    r15
0x140002a9c  sub     rsp, 250h
0x140002aa3  mov     rax, cs:__security_cookie
0x140002aaa  xor     rax, rsp
0x140002aad  mov     [rsp+288h+var_48], rax
0x140002ab5  mov     rax, 0C000000000000000h
0x140002abf  mov     rsi, r9
0x140002ac2  mov     r8, rdx
0x140002ac5  mov     rbx, rcx
0x140002ac8  test    rax, r9
0x140002acb  jnz     loc_140002CA4
0x140002ad1  xor     r12d, r12d
0x140002ad4  lea     rax, [rsp+288h+Name]
0x140002ad9  mov     r13d, 104h
0x140002adf  mov     ecx, 7FFFFFFEh
0x140002ae4  mov     edx, r13d
0x140002ae7  lea     ebp, [r12+1]
0x140002aec  test    rcx, rcx
0x140002aef  jz      short loc_140002B0F
0x140002af1  movzx   r9d, word ptr [r8]
0x140002af5  test    r9w, r9w
0x140002af9  jz      short loc_140002B0F
0x140002afb  mov     [rax], r9w
0x140002aff  add     r8, 2
0x140002b03  add     rax, 2
0x140002b07  sub     rcx, rbp
0x140002b0a  sub     rdx, rbp
0x140002b0d  jnz     short loc_140002AEC
0x140002b0f  test    rdx, rdx
0x140002b12  lea     rcx, [rax-2]
0x140002b16  lea     r8, aP0; "_p0"
0x140002b1d  mov     rdx, r13; unsigned __int64
0x140002b20  cmovnz  rcx, rax
0x140002b24  mov     [rcx], r12w
0x140002b28  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x140002b2d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140002b32  mov     edx, esi
0x140002b34  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140002b3c  and     edx, 7FFFFFFFh; lInitialCount
0x140002b42  mov     [rsp+288h+dwFlags], r12d; int
0x140002b47  mov     r8d, ebp
0x140002b4a  lea     r9, [rsp+288h+Name]; lpName
0x140002b4f  cmova   r8d, edx; lMaximumCount
0x140002b53  xor     ecx, ecx; lpSemaphoreAttributes
0x140002b55  call    cs:__imp_CreateSemaphoreExW
0x140002b5b  mov     r15, rax
0x140002b5e  test    rax, rax
0x140002b61  jnz     short loc_140002B91
0x140002b63  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140002b68  mov     edi, eax
0x140002b6a  test    eax, eax
0x140002b6c  jns     short loc_140002BC5
0x140002b6e  mov     rcx, [rsp+288h]; this
0x140002b76  lea     r8, aWil; "wil"
0x140002b7d  mov     r9d, eax; char *
0x140002b80  mov     edx, 8Bh; void *
0x140002b85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002b8a  mov     eax, edi
0x140002b8c  jmp     loc_140002C66
0x140002b91  call    cs:__imp_GetLastError
0x140002b97  mov     rdi, [rbx]
0x140002b9a  test    rdi, rdi
0x140002b9d  jz      short loc_140002BC2
0x140002b9f  call    cs:__imp_GetLastError
0x140002ba5  mov     rcx, rdi; hObject
0x140002ba8  mov     r14d, eax
0x140002bab  call    cs:__imp_CloseHandle
0x140002bb1  test    eax, eax
0x140002bb3  jz      loc_140002CAA
0x140002bb9  mov     ecx, r14d; dwErrCode
0x140002bbc  call    cs:__imp_SetLastError
0x140002bc2  mov     [rbx], r15
0x140002bc5  lea     r8, asc_140016E78; "h"
0x140002bcc  shr     rsi, 1Fh
0x140002bd0  mov     rdx, r13; unsigned __int64
0x140002bd3  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x140002bd8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140002bdd  test    esi, esi
0x140002bdf  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140002be7  lea     r9, [rsp+288h+Name]; lpName
0x140002bec  mov     [rsp+288h+dwFlags], r12d; int
0x140002bf1  cmovnz  ebp, esi
0x140002bf4  mov     edx, esi; lInitialCount
0x140002bf6  mov     r8d, ebp; lMaximumCount
0x140002bf9  xor     ecx, ecx; lpSemaphoreAttributes
0x140002bfb  call    cs:__imp_CreateSemaphoreExW
0x140002c01  mov     rbp, rax
0x140002c04  test    rax, rax
0x140002c07  jnz     short loc_140002C34
0x140002c09  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140002c0e  mov     ebx, eax
0x140002c10  test    eax, eax
0x140002c12  jns     short loc_140002C64
0x140002c14  mov     rcx, [rsp+288h]; this
0x140002c1c  lea     r8, aWil; "wil"
0x140002c23  mov     r9d, eax; char *
0x140002c26  mov     edx, 90h; void *
0x140002c2b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002c30  mov     eax, ebx
0x140002c32  jmp     short loc_140002C66
0x140002c34  call    cs:__imp_GetLastError
0x140002c3a  mov     rdi, [rbx+8]
0x140002c3e  test    rdi, rdi
0x140002c41  jz      short loc_140002C60
0x140002c43  call    cs:__imp_GetLastError
0x140002c49  mov     rcx, rdi; hObject
0x140002c4c  mov     esi, eax
0x140002c4e  call    cs:__imp_CloseHandle
0x140002c54  test    eax, eax
0x140002c56  jz      short loc_140002C91
0x140002c58  mov     ecx, esi; dwErrCode
0x140002c5a  call    cs:__imp_SetLastError
0x140002c60  mov     [rbx+8], rbp
0x140002c64  xor     eax, eax
0x140002c66  mov     rcx, [rsp+288h+var_48]
0x140002c6e  xor     rcx, rsp; StackCookie
0x140002c71  call    __security_check_cookie
0x140002c76  mov     rbx, [rsp+288h+arg_8]
0x140002c7e  add     rsp, 250h
0x140002c85  pop     r15
0x140002c87  pop     r14
0x140002c89  pop     r13
0x140002c8b  pop     r12
0x140002c8d  pop     rdi
0x140002c8e  pop     rsi
0x140002c8f  pop     rbp
0x140002c90  retn
0x140002c91  mov     rcx, [rsp+288h]; this
0x140002c99  mov     edx, 0A0Bh; void *
0x140002c9e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140002ca4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140002caa  mov     rcx, [rsp+288h]; this
0x140002cb2  mov     edx, 0A0Bh; void *
0x140002cb7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
