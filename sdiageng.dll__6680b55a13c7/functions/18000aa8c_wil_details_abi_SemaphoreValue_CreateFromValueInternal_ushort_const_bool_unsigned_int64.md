# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18000aa8c`
- end: `0x18000acaf`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `547`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000988c`
- `0x180009c30`

## callees

- `0x18000aa8c`
- `0x18000bd6c`
- `0x18000ffb4`
- `0x180010e70`
- `0x1800125a4`
- `0x1800125b4`
- `0x1800298c0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000ab8a`
- `KERNEL32!GetLastError` at `0x18000ab98`
- `KERNEL32!GetLastError` at `0x18000ac26`
- `KERNEL32!GetLastError` at `0x18000ac35`
- `KERNEL32!GetLastError` at `0x18000ab8a`
- `KERNEL32!GetLastError` at `0x18000ab98`
- `KERNEL32!GetLastError` at `0x18000ac26`
- `KERNEL32!GetLastError` at `0x18000ac35`
- `KERNEL32!CloseHandle` at `0x18000aba4`
- `KERNEL32!CloseHandle` at `0x18000ac40`
- `KERNEL32!CloseHandle` at `0x18000aba4`
- `KERNEL32!CloseHandle` at `0x18000ac40`
- `KERNEL32!SetLastError` at `0x18000abb5`
- `KERNEL32!SetLastError` at `0x18000ac4c`
- `KERNEL32!SetLastError` at `0x18000abb5`
- `KERNEL32!SetLastError` at `0x18000ac4c`
- `KERNEL32!CreateSemaphoreExW` at `0x18000ab55`
- `KERNEL32!CreateSemaphoreExW` at `0x18000abf4`
- `KERNEL32!CreateSemaphoreExW` at `0x18000ab55`
- `KERNEL32!CreateSemaphoreExW` at `0x18000abf4`

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
0x18000aa8c  mov     [rsp+arg_8], rbx
0x18000aa91  push    rbp
0x18000aa92  push    rsi
0x18000aa93  push    rdi
0x18000aa94  push    r12
0x18000aa96  push    r13
0x18000aa98  push    r14
0x18000aa9a  push    r15
0x18000aa9c  sub     rsp, 250h
0x18000aaa3  mov     rax, cs:__security_cookie
0x18000aaaa  xor     rax, rsp
0x18000aaad  mov     [rsp+288h+var_48], rax
0x18000aab5  mov     rax, 0C000000000000000h
0x18000aabf  mov     rsi, r9
0x18000aac2  mov     r8, rdx
0x18000aac5  mov     rbx, rcx
0x18000aac8  test    rax, r9
0x18000aacb  jnz     loc_18000AC96
0x18000aad1  xor     r12d, r12d
0x18000aad4  lea     rax, [rsp+288h+Name]
0x18000aad9  mov     r13d, 104h
0x18000aadf  mov     ecx, 7FFFFFFEh
0x18000aae4  mov     edx, r13d
0x18000aae7  lea     ebp, [r12+1]
0x18000aaec  test    rcx, rcx
0x18000aaef  jz      short loc_18000AB0F
0x18000aaf1  movzx   r9d, word ptr [r8]
0x18000aaf5  test    r9w, r9w
0x18000aaf9  jz      short loc_18000AB0F
0x18000aafb  mov     [rax], r9w
0x18000aaff  add     r8, 2
0x18000ab03  add     rax, 2
0x18000ab07  sub     rcx, rbp
0x18000ab0a  sub     rdx, rbp
0x18000ab0d  jnz     short loc_18000AAEC
0x18000ab0f  test    rdx, rdx
0x18000ab12  lea     rcx, [rax-2]
0x18000ab16  lea     r8, aP0; "_p0"
0x18000ab1d  mov     rdx, r13; unsigned __int64
0x18000ab20  cmovnz  rcx, rax
0x18000ab24  mov     [rcx], r12w
0x18000ab28  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x18000ab2d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000ab32  mov     edx, esi
0x18000ab34  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000ab3c  and     edx, 7FFFFFFFh; lInitialCount
0x18000ab42  mov     [rsp+288h+dwFlags], r12d; int
0x18000ab47  mov     r8d, ebp
0x18000ab4a  lea     r9, [rsp+288h+Name]; lpName
0x18000ab4f  cmova   r8d, edx; lMaximumCount
0x18000ab53  xor     ecx, ecx; lpSemaphoreAttributes
0x18000ab55  call    cs:__imp_CreateSemaphoreExW
0x18000ab5b  mov     r15, rax
0x18000ab5e  test    rax, rax
0x18000ab61  jnz     short loc_18000AB8A
0x18000ab63  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000ab68  mov     edi, eax
0x18000ab6a  test    eax, eax
0x18000ab6c  jns     short loc_18000ABBE
0x18000ab6e  mov     rcx, [rsp+288h]; this
0x18000ab76  mov     r9d, eax; char *
0x18000ab79  mov     edx, 8Bh; void *
0x18000ab7e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ab83  mov     eax, edi
0x18000ab85  jmp     loc_18000AC58
0x18000ab8a  call    cs:__imp_GetLastError
0x18000ab90  mov     rdi, [rbx]
0x18000ab93  test    rdi, rdi
0x18000ab96  jz      short loc_18000ABBB
0x18000ab98  call    cs:__imp_GetLastError
0x18000ab9e  mov     rcx, rdi; hObject
0x18000aba1  mov     r14d, eax
0x18000aba4  call    cs:__imp_CloseHandle
0x18000abaa  test    eax, eax
0x18000abac  jz      loc_18000AC9C
0x18000abb2  mov     ecx, r14d; dwErrCode
0x18000abb5  call    cs:__imp_SetLastError
0x18000abbb  mov     [rbx], r15
0x18000abbe  lea     r8, asc_18002E8A0; "h"
0x18000abc5  shr     rsi, 1Fh
0x18000abc9  mov     rdx, r13; unsigned __int64
0x18000abcc  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x18000abd1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000abd6  test    esi, esi
0x18000abd8  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000abe0  lea     r9, [rsp+288h+Name]; lpName
0x18000abe5  mov     [rsp+288h+dwFlags], r12d; int
0x18000abea  cmovnz  ebp, esi
0x18000abed  mov     edx, esi; lInitialCount
0x18000abef  mov     r8d, ebp; lMaximumCount
0x18000abf2  xor     ecx, ecx; lpSemaphoreAttributes
0x18000abf4  call    cs:__imp_CreateSemaphoreExW
0x18000abfa  mov     rbp, rax
0x18000abfd  test    rax, rax
0x18000ac00  jnz     short loc_18000AC26
0x18000ac02  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000ac07  mov     ebx, eax
0x18000ac09  test    eax, eax
0x18000ac0b  jns     short loc_18000AC56
0x18000ac0d  mov     rcx, [rsp+288h]; this
0x18000ac15  mov     r9d, eax; char *
0x18000ac18  mov     edx, 90h; void *
0x18000ac1d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ac22  mov     eax, ebx
0x18000ac24  jmp     short loc_18000AC58
0x18000ac26  call    cs:__imp_GetLastError
0x18000ac2c  mov     rdi, [rbx+8]
0x18000ac30  test    rdi, rdi
0x18000ac33  jz      short loc_18000AC52
0x18000ac35  call    cs:__imp_GetLastError
0x18000ac3b  mov     rcx, rdi; hObject
0x18000ac3e  mov     esi, eax
0x18000ac40  call    cs:__imp_CloseHandle
0x18000ac46  test    eax, eax
0x18000ac48  jz      short loc_18000AC83
0x18000ac4a  mov     ecx, esi; dwErrCode
0x18000ac4c  call    cs:__imp_SetLastError
0x18000ac52  mov     [rbx+8], rbp
0x18000ac56  xor     eax, eax
0x18000ac58  mov     rcx, [rsp+288h+var_48]
0x18000ac60  xor     rcx, rsp; StackCookie
0x18000ac63  call    __security_check_cookie
0x18000ac68  mov     rbx, [rsp+288h+arg_8]
0x18000ac70  add     rsp, 250h
0x18000ac77  pop     r15
0x18000ac79  pop     r14
0x18000ac7b  pop     r13
0x18000ac7d  pop     r12
0x18000ac7f  pop     rdi
0x18000ac80  pop     rsi
0x18000ac81  pop     rbp
0x18000ac82  retn
0x18000ac83  mov     rcx, [rsp+288h]; this
0x18000ac8b  mov     edx, 0A0Bh; void *
0x18000ac90  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000ac96  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000ac9c  mov     rcx, [rsp+288h]; this
0x18000aca4  mov     edx, 0A0Bh; void *
0x18000aca9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
