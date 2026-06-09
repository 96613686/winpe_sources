# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1800052ec`
- end: `0x180005516`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180004f1c`

## callees

- `0x1800052ec`
- `0x180005ab8`
- `0x1800068f4`
- `0x180006c0c`
- `0x180007228`
- `0x180007238`
- `0x18001a210`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800053b0`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180005453`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800053b0`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180005453`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800053ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800053fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000548c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000549b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800053ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800053fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000548c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000549b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005417`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800054b2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005417`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800054b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005406`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800054a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005406`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800054a6`

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
0x1800052ec  mov     [rsp+arg_8], rbx
0x1800052f1  mov     [rsp+arg_10], rbp
0x1800052f6  push    rsi
0x1800052f7  push    rdi
0x1800052f8  push    r12
0x1800052fa  push    r14
0x1800052fc  push    r15
0x1800052fe  sub     rsp, 250h
0x180005305  mov     rax, cs:__security_cookie
0x18000530c  xor     rax, rsp
0x18000530f  mov     [rsp+278h+var_38], rax
0x180005317  mov     rax, 0C000000000000000h
0x180005321  mov     rbp, r9
0x180005324  mov     r8, rdx
0x180005327  mov     rbx, rcx
0x18000532a  test    rax, r9
0x18000532d  jnz     loc_1800054FD
0x180005333  xor     r12d, r12d
0x180005336  lea     rax, [rsp+278h+Name]
0x18000533b  mov     ecx, 7FFFFFFEh
0x180005340  mov     edx, 104h
0x180005345  lea     esi, [r12+1]
0x18000534a  test    rcx, rcx
0x18000534d  jz      short loc_18000536D
0x18000534f  movzx   r9d, word ptr [r8]
0x180005353  test    r9w, r9w
0x180005357  jz      short loc_18000536D
0x180005359  mov     [rax], r9w
0x18000535d  add     r8, 2
0x180005361  add     rax, 2
0x180005365  sub     rcx, rsi
0x180005368  sub     rdx, rsi; unsigned __int64
0x18000536b  jnz     short loc_18000534A
0x18000536d  test    rdx, rdx
0x180005370  lea     rcx, [rax-2]
0x180005374  lea     r8, aP0; "_p0"
0x18000537b  cmovnz  rcx, rax
0x18000537f  mov     [rcx], r12w
0x180005383  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180005388  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000538d  mov     edx, ebp
0x18000538f  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180005397  and     edx, 7FFFFFFFh; lInitialCount
0x18000539d  mov     [rsp+278h+dwFlags], r12d; int
0x1800053a2  mov     r8d, esi
0x1800053a5  lea     r9, [rsp+278h+Name]; lpName
0x1800053aa  cmova   r8d, edx; lMaximumCount
0x1800053ae  xor     ecx, ecx; lpSemaphoreAttributes
0x1800053b0  call    cs:__imp_CreateSemaphoreExW
0x1800053b6  mov     r15, rax
0x1800053b9  test    rax, rax
0x1800053bc  jnz     short loc_1800053EC
0x1800053be  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800053c3  mov     edi, eax
0x1800053c5  test    eax, eax
0x1800053c7  jns     short loc_180005420
0x1800053c9  mov     rcx, [rsp+278h]; this
0x1800053d1  lea     r8, aWil; "wil"
0x1800053d8  mov     r9d, eax; char *
0x1800053db  mov     edx, 8Bh; void *
0x1800053e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800053e5  mov     eax, edi
0x1800053e7  jmp     loc_1800054BE
0x1800053ec  call    cs:__imp_GetLastError
0x1800053f2  mov     rdi, [rbx]
0x1800053f5  test    rdi, rdi
0x1800053f8  jz      short loc_18000541D
0x1800053fa  call    cs:__imp_GetLastError
0x180005400  mov     rcx, rdi; hObject
0x180005403  mov     r14d, eax
0x180005406  call    cs:__imp_CloseHandle
0x18000540c  test    eax, eax
0x18000540e  jz      loc_180005503
0x180005414  mov     ecx, r14d; dwErrCode
0x180005417  call    cs:__imp_SetLastError
0x18000541d  mov     [rbx], r15
0x180005420  lea     r8, asc_18001F1F0; "h"
0x180005427  shr     rbp, 1Fh
0x18000542b  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180005430  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005435  test    ebp, ebp
0x180005437  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000543f  lea     r9, [rsp+278h+Name]; lpName
0x180005444  mov     [rsp+278h+dwFlags], r12d; int
0x180005449  cmovnz  esi, ebp
0x18000544c  mov     edx, ebp; lInitialCount
0x18000544e  mov     r8d, esi; lMaximumCount
0x180005451  xor     ecx, ecx; lpSemaphoreAttributes
0x180005453  call    cs:__imp_CreateSemaphoreExW
0x180005459  mov     rsi, rax
0x18000545c  test    rax, rax
0x18000545f  jnz     short loc_18000548C
0x180005461  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005466  mov     ebx, eax
0x180005468  test    eax, eax
0x18000546a  jns     short loc_1800054BC
0x18000546c  mov     rcx, [rsp+278h]; this
0x180005474  lea     r8, aWil; "wil"
0x18000547b  mov     r9d, eax; char *
0x18000547e  mov     edx, 90h; void *
0x180005483  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005488  mov     eax, ebx
0x18000548a  jmp     short loc_1800054BE
0x18000548c  call    cs:__imp_GetLastError
0x180005492  mov     rdi, [rbx+8]
0x180005496  test    rdi, rdi
0x180005499  jz      short loc_1800054B8
0x18000549b  call    cs:__imp_GetLastError
0x1800054a1  mov     rcx, rdi; hObject
0x1800054a4  mov     ebp, eax
0x1800054a6  call    cs:__imp_CloseHandle
0x1800054ac  test    eax, eax
0x1800054ae  jz      short loc_1800054EA
0x1800054b0  mov     ecx, ebp; dwErrCode
0x1800054b2  call    cs:__imp_SetLastError
0x1800054b8  mov     [rbx+8], rsi
0x1800054bc  xor     eax, eax
0x1800054be  mov     rcx, [rsp+278h+var_38]
0x1800054c6  xor     rcx, rsp; StackCookie
0x1800054c9  call    __security_check_cookie
0x1800054ce  lea     r11, [rsp+278h+var_28]
0x1800054d6  mov     rbx, [r11+38h]
0x1800054da  mov     rbp, [r11+40h]
0x1800054de  mov     rsp, r11
0x1800054e1  pop     r15
0x1800054e3  pop     r14
0x1800054e5  pop     r12
0x1800054e7  pop     rdi
0x1800054e8  pop     rsi
0x1800054e9  retn
0x1800054ea  mov     rcx, [rsp+278h]; this
0x1800054f2  mov     edx, 0A0Bh; void *
0x1800054f7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800054fd  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180005503  mov     rcx, [rsp+278h]; this
0x18000550b  mov     edx, 0A0Bh; void *
0x180005510  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
