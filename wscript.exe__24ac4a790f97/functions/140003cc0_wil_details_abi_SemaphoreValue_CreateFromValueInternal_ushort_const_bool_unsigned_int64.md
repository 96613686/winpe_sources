# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x140003cc0`
- end: `0x140003ecd`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1400038f0`

## callees

- `0x140003cc0`
- `0x140004300`
- `0x140004bd4`
- `0x140004bf8`
- `0x140005464`
- `0x140005474`
- `0x1400175a0`

## import_xrefs

- `KERNEL32!CreateSemaphoreExW` at `0x140003d84`
- `KERNEL32!CreateSemaphoreExW` at `0x140003e20`
- `KERNEL32!CreateSemaphoreExW` at `0x140003d84`
- `KERNEL32!CreateSemaphoreExW` at `0x140003e20`
- `KERNEL32!SetLastError` at `0x140003de4`
- `KERNEL32!SetLastError` at `0x140003e69`
- `KERNEL32!SetLastError` at `0x140003de4`
- `KERNEL32!SetLastError` at `0x140003e69`
- `KERNEL32!GetLastError` at `0x140003db9`
- `KERNEL32!GetLastError` at `0x140003dc7`
- `KERNEL32!GetLastError` at `0x140003e43`
- `KERNEL32!GetLastError` at `0x140003e52`
- `KERNEL32!GetLastError` at `0x140003db9`
- `KERNEL32!GetLastError` at `0x140003dc7`
- `KERNEL32!GetLastError` at `0x140003e43`
- `KERNEL32!GetLastError` at `0x140003e52`
- `KERNEL32!CloseHandle` at `0x140003dd3`
- `KERNEL32!CloseHandle` at `0x140003e5d`
- `KERNEL32!CloseHandle` at `0x140003dd3`
- `KERNEL32!CloseHandle` at `0x140003e5d`

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
  unsigned int v22; // r8d
  const char *v23; // r9
  unsigned __int64 v24; // rbp
  wil::details *v25; // rcx
  HANDLE v26; // rsi
  void *v27; // rbx
  DWORD v28; // ebp
  unsigned int v29; // r8d
  const char *v30; // r9
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
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v22, v23);
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
  v24 = a4 >> 31;
  StringCchCatW(Name, v15, L"h");
  if ( (_DWORD)v24 )
    v10 = v24;
  v26 = CreateSemaphoreExW(0, v24, v10, Name, 0, 0x1F0003u);
  if ( v26 )
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
    *((_QWORD *)this + 1) = v26;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v25);
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
0x140003cc0  mov     [rsp+arg_8], rbx
0x140003cc5  mov     [rsp+arg_10], rbp
0x140003cca  push    rsi
0x140003ccb  push    rdi
0x140003ccc  push    r12
0x140003cce  push    r14
0x140003cd0  push    r15
0x140003cd2  sub     rsp, 250h
0x140003cd9  mov     rax, cs:__security_cookie
0x140003ce0  xor     rax, rsp
0x140003ce3  mov     [rsp+278h+var_38], rax
0x140003ceb  mov     rax, 0C000000000000000h
0x140003cf5  mov     rbp, r9
0x140003cf8  mov     r8, rdx
0x140003cfb  mov     rdi, rcx
0x140003cfe  test    rax, r9
0x140003d01  jnz     loc_140003EB4
0x140003d07  xor     r12d, r12d
0x140003d0a  lea     rax, [rsp+278h+Name]
0x140003d0f  mov     ecx, 7FFFFFFEh
0x140003d14  mov     edx, 104h
0x140003d19  lea     esi, [r12+1]
0x140003d1e  test    rcx, rcx
0x140003d21  jz      short loc_140003D41
0x140003d23  movzx   r9d, word ptr [r8]
0x140003d27  test    r9w, r9w
0x140003d2b  jz      short loc_140003D41
0x140003d2d  mov     [rax], r9w
0x140003d31  add     r8, 2
0x140003d35  add     rax, 2
0x140003d39  sub     rcx, rsi
0x140003d3c  sub     rdx, rsi; unsigned __int64
0x140003d3f  jnz     short loc_140003D1E
0x140003d41  test    rdx, rdx
0x140003d44  lea     rcx, [rax-2]
0x140003d48  lea     r8, aP0; "_p0"
0x140003d4f  cmovnz  rcx, rax
0x140003d53  mov     [rcx], r12w
0x140003d57  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x140003d5c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140003d61  mov     edx, ebp
0x140003d63  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140003d6b  and     edx, 7FFFFFFFh; lInitialCount
0x140003d71  mov     [rsp+278h+dwFlags], r12d; int
0x140003d76  mov     r8d, esi
0x140003d79  lea     r9, [rsp+278h+Name]; lpName
0x140003d7e  cmova   r8d, edx; lMaximumCount
0x140003d82  xor     ecx, ecx; lpSemaphoreAttributes
0x140003d84  call    cs:__imp_CreateSemaphoreExW
0x140003d8a  mov     r15, rax
0x140003d8d  test    rax, rax
0x140003d90  jnz     short loc_140003DB9
0x140003d92  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140003d97  mov     ebx, eax
0x140003d99  test    eax, eax
0x140003d9b  jns     short loc_140003DED
0x140003d9d  mov     edx, 8Bh; void *
0x140003da2  mov     rcx, [rsp+278h]; this
0x140003daa  mov     r9d, ebx; char *
0x140003dad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003db2  mov     eax, ebx
0x140003db4  jmp     loc_140003E75
0x140003db9  call    cs:__imp_GetLastError
0x140003dbf  mov     rbx, [rdi]
0x140003dc2  test    rbx, rbx
0x140003dc5  jz      short loc_140003DEA
0x140003dc7  call    cs:__imp_GetLastError
0x140003dcd  mov     rcx, rbx; hObject
0x140003dd0  mov     r14d, eax
0x140003dd3  call    cs:__imp_CloseHandle
0x140003dd9  test    eax, eax
0x140003ddb  jz      loc_140003EBA
0x140003de1  mov     ecx, r14d; dwErrCode
0x140003de4  call    cs:__imp_SetLastError
0x140003dea  mov     [rdi], r15
0x140003ded  lea     r8, asc_14001B0C8; "h"
0x140003df4  shr     rbp, 1Fh
0x140003df8  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x140003dfd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140003e02  test    ebp, ebp
0x140003e04  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140003e0c  lea     r9, [rsp+278h+Name]; lpName
0x140003e11  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x140003e16  cmovnz  esi, ebp
0x140003e19  mov     edx, ebp; lInitialCount
0x140003e1b  mov     r8d, esi; lMaximumCount
0x140003e1e  xor     ecx, ecx; lpSemaphoreAttributes
0x140003e20  call    cs:__imp_CreateSemaphoreExW
0x140003e26  mov     rsi, rax
0x140003e29  test    rax, rax
0x140003e2c  jnz     short loc_140003E43
0x140003e2e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140003e33  mov     ebx, eax
0x140003e35  test    eax, eax
0x140003e37  jns     short loc_140003E73
0x140003e39  mov     edx, 90h
0x140003e3e  jmp     loc_140003DA2
0x140003e43  call    cs:__imp_GetLastError
0x140003e49  mov     rbx, [rdi+8]
0x140003e4d  test    rbx, rbx
0x140003e50  jz      short loc_140003E6F
0x140003e52  call    cs:__imp_GetLastError
0x140003e58  mov     rcx, rbx; hObject
0x140003e5b  mov     ebp, eax
0x140003e5d  call    cs:__imp_CloseHandle
0x140003e63  test    eax, eax
0x140003e65  jz      short loc_140003EA1
0x140003e67  mov     ecx, ebp; dwErrCode
0x140003e69  call    cs:__imp_SetLastError
0x140003e6f  mov     [rdi+8], rsi
0x140003e73  xor     eax, eax
0x140003e75  mov     rcx, [rsp+278h+var_38]
0x140003e7d  xor     rcx, rsp; StackCookie
0x140003e80  call    __security_check_cookie
0x140003e85  lea     r11, [rsp+278h+var_28]
0x140003e8d  mov     rbx, [r11+38h]
0x140003e91  mov     rbp, [r11+40h]
0x140003e95  mov     rsp, r11
0x140003e98  pop     r15
0x140003e9a  pop     r14
0x140003e9c  pop     r12
0x140003e9e  pop     rdi
0x140003e9f  pop     rsi
0x140003ea0  retn
0x140003ea1  mov     rcx, [rsp+278h]; this
0x140003ea9  mov     edx, 0A0Bh; void *
0x140003eae  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003eb4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140003eba  mov     rcx, [rsp+278h]; this
0x140003ec2  mov     edx, 0A0Bh; void *
0x140003ec7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
