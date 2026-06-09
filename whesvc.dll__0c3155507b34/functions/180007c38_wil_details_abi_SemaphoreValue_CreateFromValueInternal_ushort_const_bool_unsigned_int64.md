# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180007c38`
- end: `0x180007e69`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `561`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180007864`
- `0x18000c5c4`

## callees

- `0x1800032e0`
- `0x180006348`
- `0x180007c38`
- `0x180008478`
- `0x180009044`
- `0x180009478`
- `0x180009d5c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007d3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007d4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007de0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007def`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007d3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007d4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007de0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007def`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007d68`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007e06`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007d68`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007e06`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180007d01`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180007da7`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180007d01`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180007da7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007d57`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007dfa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007d57`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007dfa`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
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
0x180007c38  mov     [rsp+arg_8], rbx
0x180007c3d  push    rbp
0x180007c3e  push    rsi
0x180007c3f  push    rdi
0x180007c40  push    r12
0x180007c42  push    r13
0x180007c44  push    r14
0x180007c46  push    r15
0x180007c48  sub     rsp, 250h
0x180007c4f  mov     rax, cs:__security_cookie
0x180007c56  xor     rax, rsp
0x180007c59  mov     [rsp+288h+var_48], rax
0x180007c61  mov     rax, 0C000000000000000h
0x180007c6b  mov     rsi, r9
0x180007c6e  mov     r8, rdx
0x180007c71  mov     rbx, rcx
0x180007c74  test    rax, r9
0x180007c77  jnz     loc_180007E50
0x180007c7d  xor     r12d, r12d
0x180007c80  lea     rax, [rsp+288h+Name]
0x180007c85  mov     r13d, 104h
0x180007c8b  mov     ecx, 7FFFFFFEh
0x180007c90  mov     edx, r13d
0x180007c93  lea     ebp, [r12+1]
0x180007c98  test    rcx, rcx
0x180007c9b  jz      short loc_180007CBB
0x180007c9d  movzx   r9d, word ptr [r8]
0x180007ca1  test    r9w, r9w
0x180007ca5  jz      short loc_180007CBB
0x180007ca7  mov     [rax], r9w
0x180007cab  add     r8, 2
0x180007caf  add     rax, 2
0x180007cb3  sub     rcx, rbp
0x180007cb6  sub     rdx, rbp
0x180007cb9  jnz     short loc_180007C98
0x180007cbb  test    rdx, rdx
0x180007cbe  lea     rcx, [rax-2]
0x180007cc2  lea     r8, aP0; "_p0"
0x180007cc9  mov     rdx, r13; unsigned __int64
0x180007ccc  cmovnz  rcx, rax
0x180007cd0  mov     [rcx], r12w
0x180007cd4  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x180007cd9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007cde  mov     edx, esi
0x180007ce0  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180007ce8  and     edx, 7FFFFFFFh; lInitialCount
0x180007cee  mov     [rsp+288h+dwFlags], r12d; int
0x180007cf3  mov     r8d, ebp
0x180007cf6  lea     r9, [rsp+288h+Name]; lpName
0x180007cfb  cmova   r8d, edx; lMaximumCount
0x180007cff  xor     ecx, ecx; lpSemaphoreAttributes
0x180007d01  call    cs:__imp_CreateSemaphoreExW
0x180007d07  mov     r15, rax
0x180007d0a  test    rax, rax
0x180007d0d  jnz     short loc_180007D3D
0x180007d0f  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180007d14  mov     edi, eax
0x180007d16  test    eax, eax
0x180007d18  jns     short loc_180007D71
0x180007d1a  mov     rcx, [rsp+288h]; this
0x180007d22  lea     r8, aWil; "wil"
0x180007d29  mov     r9d, eax; char *
0x180007d2c  mov     edx, 8Bh; void *
0x180007d31  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007d36  mov     eax, edi
0x180007d38  jmp     loc_180007E12
0x180007d3d  call    cs:__imp_GetLastError
0x180007d43  mov     rdi, [rbx]
0x180007d46  test    rdi, rdi
0x180007d49  jz      short loc_180007D6E
0x180007d4b  call    cs:__imp_GetLastError
0x180007d51  mov     rcx, rdi; hObject
0x180007d54  mov     r14d, eax
0x180007d57  call    cs:__imp_CloseHandle
0x180007d5d  test    eax, eax
0x180007d5f  jz      loc_180007E56
0x180007d65  mov     ecx, r14d; dwErrCode
0x180007d68  call    cs:__imp_SetLastError
0x180007d6e  mov     [rbx], r15
0x180007d71  lea     r8, asc_18002B510; "h"
0x180007d78  shr     rsi, 1Fh
0x180007d7c  mov     rdx, r13; unsigned __int64
0x180007d7f  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x180007d84  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007d89  test    esi, esi
0x180007d8b  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180007d93  lea     r9, [rsp+288h+Name]; lpName
0x180007d98  mov     [rsp+288h+dwFlags], r12d; int
0x180007d9d  cmovnz  ebp, esi
0x180007da0  mov     edx, esi; lInitialCount
0x180007da2  mov     r8d, ebp; lMaximumCount
0x180007da5  xor     ecx, ecx; lpSemaphoreAttributes
0x180007da7  call    cs:__imp_CreateSemaphoreExW
0x180007dad  mov     rbp, rax
0x180007db0  test    rax, rax
0x180007db3  jnz     short loc_180007DE0
0x180007db5  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180007dba  mov     ebx, eax
0x180007dbc  test    eax, eax
0x180007dbe  jns     short loc_180007E10
0x180007dc0  mov     rcx, [rsp+288h]; this
0x180007dc8  lea     r8, aWil; "wil"
0x180007dcf  mov     r9d, eax; char *
0x180007dd2  mov     edx, 90h; void *
0x180007dd7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007ddc  mov     eax, ebx
0x180007dde  jmp     short loc_180007E12
0x180007de0  call    cs:__imp_GetLastError
0x180007de6  mov     rdi, [rbx+8]
0x180007dea  test    rdi, rdi
0x180007ded  jz      short loc_180007E0C
0x180007def  call    cs:__imp_GetLastError
0x180007df5  mov     rcx, rdi; hObject
0x180007df8  mov     esi, eax
0x180007dfa  call    cs:__imp_CloseHandle
0x180007e00  test    eax, eax
0x180007e02  jz      short loc_180007E3D
0x180007e04  mov     ecx, esi; dwErrCode
0x180007e06  call    cs:__imp_SetLastError
0x180007e0c  mov     [rbx+8], rbp
0x180007e10  xor     eax, eax
0x180007e12  mov     rcx, [rsp+288h+var_48]
0x180007e1a  xor     rcx, rsp; StackCookie
0x180007e1d  call    __security_check_cookie
0x180007e22  mov     rbx, [rsp+288h+arg_8]
0x180007e2a  add     rsp, 250h
0x180007e31  pop     r15
0x180007e33  pop     r14
0x180007e35  pop     r13
0x180007e37  pop     r12
0x180007e39  pop     rdi
0x180007e3a  pop     rsi
0x180007e3b  pop     rbp
0x180007e3c  retn
0x180007e3d  mov     rcx, [rsp+288h]; this
0x180007e45  mov     edx, 0A0Bh; void *
0x180007e4a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007e50  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180007e56  mov     rcx, [rsp+288h]; this
0x180007e5e  mov     edx, 0A0Bh; void *
0x180007e63  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
