# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180005420`
- end: `0x180005651`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `561`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000504c`
- `0x18001392c`

## callees

- `0x180005420`
- `0x180005ca8`
- `0x180006a74`
- `0x180006df4`
- `0x180007448`
- `0x180007458`
- `0x1800772c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800054e9`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000558f`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800054e9`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000558f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005525`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005533`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800055c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800055d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005525`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005533`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800055c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800055d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005550`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800055ee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005550`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800055ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000553f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800055e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000553f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800055e2`

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
0x180005420  mov     [rsp+arg_8], rbx
0x180005425  push    rbp
0x180005426  push    rsi
0x180005427  push    rdi
0x180005428  push    r12
0x18000542a  push    r13
0x18000542c  push    r14
0x18000542e  push    r15
0x180005430  sub     rsp, 250h
0x180005437  mov     rax, cs:__security_cookie
0x18000543e  xor     rax, rsp
0x180005441  mov     [rsp+288h+var_48], rax
0x180005449  mov     rax, 0C000000000000000h
0x180005453  mov     rsi, r9
0x180005456  mov     r8, rdx
0x180005459  mov     rbx, rcx
0x18000545c  test    rax, r9
0x18000545f  jnz     loc_180005638
0x180005465  xor     r12d, r12d
0x180005468  lea     rax, [rsp+288h+Name]
0x18000546d  mov     r13d, 104h
0x180005473  mov     ecx, 7FFFFFFEh
0x180005478  mov     edx, r13d
0x18000547b  lea     ebp, [r12+1]
0x180005480  test    rcx, rcx
0x180005483  jz      short loc_1800054A3
0x180005485  movzx   r9d, word ptr [r8]
0x180005489  test    r9w, r9w
0x18000548d  jz      short loc_1800054A3
0x18000548f  mov     [rax], r9w
0x180005493  add     r8, 2
0x180005497  add     rax, 2
0x18000549b  sub     rcx, rbp
0x18000549e  sub     rdx, rbp
0x1800054a1  jnz     short loc_180005480
0x1800054a3  test    rdx, rdx
0x1800054a6  lea     rcx, [rax-2]
0x1800054aa  lea     r8, aP0; "_p0"
0x1800054b1  mov     rdx, r13; unsigned __int64
0x1800054b4  cmovnz  rcx, rax
0x1800054b8  mov     [rcx], r12w
0x1800054bc  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x1800054c1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800054c6  mov     edx, esi
0x1800054c8  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800054d0  and     edx, 7FFFFFFFh; lInitialCount
0x1800054d6  mov     [rsp+288h+dwFlags], r12d; int
0x1800054db  mov     r8d, ebp
0x1800054de  lea     r9, [rsp+288h+Name]; lpName
0x1800054e3  cmova   r8d, edx; lMaximumCount
0x1800054e7  xor     ecx, ecx; lpSemaphoreAttributes
0x1800054e9  call    cs:__imp_CreateSemaphoreExW
0x1800054ef  mov     r15, rax
0x1800054f2  test    rax, rax
0x1800054f5  jnz     short loc_180005525
0x1800054f7  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800054fc  mov     edi, eax
0x1800054fe  test    eax, eax
0x180005500  jns     short loc_180005559
0x180005502  mov     rcx, [rsp+288h]; this
0x18000550a  lea     r8, aWil; "wil"
0x180005511  mov     r9d, eax; char *
0x180005514  mov     edx, 8Bh; void *
0x180005519  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000551e  mov     eax, edi
0x180005520  jmp     loc_1800055FA
0x180005525  call    cs:__imp_GetLastError
0x18000552b  mov     rdi, [rbx]
0x18000552e  test    rdi, rdi
0x180005531  jz      short loc_180005556
0x180005533  call    cs:__imp_GetLastError
0x180005539  mov     rcx, rdi; hObject
0x18000553c  mov     r14d, eax
0x18000553f  call    cs:__imp_CloseHandle
0x180005545  test    eax, eax
0x180005547  jz      loc_18000563E
0x18000554d  mov     ecx, r14d; dwErrCode
0x180005550  call    cs:__imp_SetLastError
0x180005556  mov     [rbx], r15
0x180005559  lea     r8, asc_180083ED8; "h"
0x180005560  shr     rsi, 1Fh
0x180005564  mov     rdx, r13; unsigned __int64
0x180005567  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x18000556c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005571  test    esi, esi
0x180005573  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000557b  lea     r9, [rsp+288h+Name]; lpName
0x180005580  mov     [rsp+288h+dwFlags], r12d; int
0x180005585  cmovnz  ebp, esi
0x180005588  mov     edx, esi; lInitialCount
0x18000558a  mov     r8d, ebp; lMaximumCount
0x18000558d  xor     ecx, ecx; lpSemaphoreAttributes
0x18000558f  call    cs:__imp_CreateSemaphoreExW
0x180005595  mov     rbp, rax
0x180005598  test    rax, rax
0x18000559b  jnz     short loc_1800055C8
0x18000559d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800055a2  mov     ebx, eax
0x1800055a4  test    eax, eax
0x1800055a6  jns     short loc_1800055F8
0x1800055a8  mov     rcx, [rsp+288h]; this
0x1800055b0  lea     r8, aWil; "wil"
0x1800055b7  mov     r9d, eax; char *
0x1800055ba  mov     edx, 90h; void *
0x1800055bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800055c4  mov     eax, ebx
0x1800055c6  jmp     short loc_1800055FA
0x1800055c8  call    cs:__imp_GetLastError
0x1800055ce  mov     rdi, [rbx+8]
0x1800055d2  test    rdi, rdi
0x1800055d5  jz      short loc_1800055F4
0x1800055d7  call    cs:__imp_GetLastError
0x1800055dd  mov     rcx, rdi; hObject
0x1800055e0  mov     esi, eax
0x1800055e2  call    cs:__imp_CloseHandle
0x1800055e8  test    eax, eax
0x1800055ea  jz      short loc_180005625
0x1800055ec  mov     ecx, esi; dwErrCode
0x1800055ee  call    cs:__imp_SetLastError
0x1800055f4  mov     [rbx+8], rbp
0x1800055f8  xor     eax, eax
0x1800055fa  mov     rcx, [rsp+288h+var_48]
0x180005602  xor     rcx, rsp; StackCookie
0x180005605  call    __security_check_cookie
0x18000560a  mov     rbx, [rsp+288h+arg_8]
0x180005612  add     rsp, 250h
0x180005619  pop     r15
0x18000561b  pop     r14
0x18000561d  pop     r13
0x18000561f  pop     r12
0x180005621  pop     rdi
0x180005622  pop     rsi
0x180005623  pop     rbp
0x180005624  retn
0x180005625  mov     rcx, [rsp+288h]; this
0x18000562d  mov     edx, 0A0Bh; void *
0x180005632  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005638  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000563e  mov     rcx, [rsp+288h]; this
0x180005646  mov     edx, 0A0Bh; void *
0x18000564b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
