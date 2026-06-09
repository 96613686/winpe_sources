# wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)

- ea: `0x1800057f0`
- end: `0x180005a21`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z`
- size: `561`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const wchar_t *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180004b78`
- `0x180004f48`

## callees

- `0x180001e40`
- `0x1800057f0`
- `0x180006e28`
- `0x18000a844`
- `0x18000b288`
- `0x18000c558`
- `0x18000c568`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800058b9`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000595f`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800058b9`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000595f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005920`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800059be`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005920`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800059be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800058f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005903`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005998`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800059a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800058f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005903`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005998`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800059a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000590f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800059b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000590f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800059b2`

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
0x1800057f0  mov     [rsp+arg_8], rbx
0x1800057f5  push    rbp
0x1800057f6  push    rsi
0x1800057f7  push    rdi
0x1800057f8  push    r12
0x1800057fa  push    r13
0x1800057fc  push    r14
0x1800057fe  push    r15
0x180005800  sub     rsp, 250h
0x180005807  mov     rax, cs:__security_cookie
0x18000580e  xor     rax, rsp
0x180005811  mov     [rsp+288h+var_48], rax
0x180005819  mov     rax, 0C000000000000000h
0x180005823  mov     rsi, r9
0x180005826  mov     r8, rdx
0x180005829  mov     rbx, rcx
0x18000582c  test    rax, r9
0x18000582f  jnz     loc_180005A08
0x180005835  xor     r12d, r12d
0x180005838  lea     rax, [rsp+288h+Name]
0x18000583d  mov     r13d, 104h
0x180005843  mov     ecx, 7FFFFFFEh
0x180005848  mov     edx, r13d
0x18000584b  lea     ebp, [r12+1]
0x180005850  test    rcx, rcx
0x180005853  jz      short loc_180005873
0x180005855  movzx   r9d, word ptr [r8]
0x180005859  test    r9w, r9w
0x18000585d  jz      short loc_180005873
0x18000585f  mov     [rax], r9w
0x180005863  add     r8, 2
0x180005867  add     rax, 2
0x18000586b  sub     rcx, rbp
0x18000586e  sub     rdx, rbp
0x180005871  jnz     short loc_180005850
0x180005873  test    rdx, rdx
0x180005876  lea     rcx, [rax-2]
0x18000587a  lea     r8, aP0; "_p0"
0x180005881  mov     rdx, r13; unsigned __int64
0x180005884  cmovnz  rcx, rax
0x180005888  mov     [rcx], r12w
0x18000588c  lea     rcx, [rsp+288h+Name]; wchar_t *
0x180005891  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180005896  mov     edx, esi
0x180005898  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800058a0  and     edx, 7FFFFFFFh; lInitialCount
0x1800058a6  mov     [rsp+288h+dwFlags], r12d; int
0x1800058ab  mov     r8d, ebp
0x1800058ae  lea     r9, [rsp+288h+Name]; lpName
0x1800058b3  cmova   r8d, edx; lMaximumCount
0x1800058b7  xor     ecx, ecx; lpSemaphoreAttributes
0x1800058b9  call    cs:__imp_CreateSemaphoreExW
0x1800058bf  mov     r15, rax
0x1800058c2  test    rax, rax
0x1800058c5  jnz     short loc_1800058F5
0x1800058c7  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800058cc  mov     edi, eax
0x1800058ce  test    eax, eax
0x1800058d0  jns     short loc_180005929
0x1800058d2  mov     rcx, [rsp+288h]; this
0x1800058da  lea     r8, aWil; "wil"
0x1800058e1  mov     r9d, eax; char *
0x1800058e4  mov     edx, 8Bh; void *
0x1800058e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800058ee  mov     eax, edi
0x1800058f0  jmp     loc_1800059CA
0x1800058f5  call    cs:__imp_GetLastError
0x1800058fb  mov     rdi, [rbx]
0x1800058fe  test    rdi, rdi
0x180005901  jz      short loc_180005926
0x180005903  call    cs:__imp_GetLastError
0x180005909  mov     rcx, rdi; hObject
0x18000590c  mov     r14d, eax
0x18000590f  call    cs:__imp_CloseHandle
0x180005915  test    eax, eax
0x180005917  jz      loc_180005A0E
0x18000591d  mov     ecx, r14d; dwErrCode
0x180005920  call    cs:__imp_SetLastError
0x180005926  mov     [rbx], r15
0x180005929  lea     r8, asc_18001D3A8; "h"
0x180005930  shr     rsi, 1Fh
0x180005934  mov     rdx, r13; unsigned __int64
0x180005937  lea     rcx, [rsp+288h+Name]; wchar_t *
0x18000593c  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180005941  test    esi, esi
0x180005943  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000594b  lea     r9, [rsp+288h+Name]; lpName
0x180005950  mov     [rsp+288h+dwFlags], r12d; int
0x180005955  cmovnz  ebp, esi
0x180005958  mov     edx, esi; lInitialCount
0x18000595a  mov     r8d, ebp; lMaximumCount
0x18000595d  xor     ecx, ecx; lpSemaphoreAttributes
0x18000595f  call    cs:__imp_CreateSemaphoreExW
0x180005965  mov     rbp, rax
0x180005968  test    rax, rax
0x18000596b  jnz     short loc_180005998
0x18000596d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005972  mov     ebx, eax
0x180005974  test    eax, eax
0x180005976  jns     short loc_1800059C8
0x180005978  mov     rcx, [rsp+288h]; this
0x180005980  lea     r8, aWil; "wil"
0x180005987  mov     r9d, eax; char *
0x18000598a  mov     edx, 90h; void *
0x18000598f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005994  mov     eax, ebx
0x180005996  jmp     short loc_1800059CA
0x180005998  call    cs:__imp_GetLastError
0x18000599e  mov     rdi, [rbx+8]
0x1800059a2  test    rdi, rdi
0x1800059a5  jz      short loc_1800059C4
0x1800059a7  call    cs:__imp_GetLastError
0x1800059ad  mov     rcx, rdi; hObject
0x1800059b0  mov     esi, eax
0x1800059b2  call    cs:__imp_CloseHandle
0x1800059b8  test    eax, eax
0x1800059ba  jz      short loc_1800059F5
0x1800059bc  mov     ecx, esi; dwErrCode
0x1800059be  call    cs:__imp_SetLastError
0x1800059c4  mov     [rbx+8], rbp
0x1800059c8  xor     eax, eax
0x1800059ca  mov     rcx, [rsp+288h+var_48]
0x1800059d2  xor     rcx, rsp; StackCookie
0x1800059d5  call    __security_check_cookie
0x1800059da  mov     rbx, [rsp+288h+arg_8]
0x1800059e2  add     rsp, 250h
0x1800059e9  pop     r15
0x1800059eb  pop     r14
0x1800059ed  pop     r13
0x1800059ef  pop     r12
0x1800059f1  pop     rdi
0x1800059f2  pop     rsi
0x1800059f3  pop     rbp
0x1800059f4  retn
0x1800059f5  mov     rcx, [rsp+288h]; this
0x1800059fd  mov     edx, 0A0Bh; void *
0x180005a02  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005a08  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180005a0e  mov     rcx, [rsp+288h]; this
0x180005a16  mov     edx, 0A0Bh; void *
0x180005a1b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
