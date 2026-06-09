# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180023474`
- end: `0x1800236b3`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `575`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18001d998`
- `0x18001dd6c`

## callees

- `0x180002ad0`
- `0x180023474`
- `0x180031454`
- `0x180048954`
- `0x18004e9f8`
- `0x180052f18`
- `0x180052f28`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18002353d`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800235e3`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18002353d`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800235e3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800235a4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023642`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800235a4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023642`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023579`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023587`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002361c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002362b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023579`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023587`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002361c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002362b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023593`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023636`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023593`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023636`

## string_xrefs

- `0x180023681`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800236a1`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  const char *v20; // r9
  unsigned __int64 v21; // rsi
  wil::details *v22; // rcx
  HANDLE v23; // rbp
  int v24; // eax
  unsigned int v25; // ebx
  void *v26; // rdi
  DWORD v27; // esi
  const char *v28; // r9
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
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA0B,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v20);
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
  v21 = a4 >> 31;
  StringCchCatW(Name, 0x104u, L"h");
  if ( (_DWORD)v21 )
    v10 = v21;
  v23 = CreateSemaphoreExW(0, v21, v10, Name, 0, 0x1F0003u);
  if ( v23 )
  {
    GetLastError();
    v26 = (void *)*((_QWORD *)this + 1);
    if ( v26 )
    {
      v27 = GetLastError();
      if ( !CloseHandle(v26) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA0B,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v28);
      SetLastError(v27);
    }
    *((_QWORD *)this + 1) = v23;
  }
  else
  {
    v24 = wil::details::GetLastErrorFailHr(v22);
    v25 = v24;
    if ( v24 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x90,
        (unsigned int)"wil",
        (const char *)(unsigned int)v24,
        dwFlagsa);
      return v25;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180023474  mov     [rsp+arg_8], rbx
0x180023479  push    rbp
0x18002347a  push    rsi
0x18002347b  push    rdi
0x18002347c  push    r12
0x18002347e  push    r13
0x180023480  push    r14
0x180023482  push    r15
0x180023484  sub     rsp, 250h
0x18002348b  mov     rax, cs:__security_cookie
0x180023492  xor     rax, rsp
0x180023495  mov     [rsp+288h+var_48], rax
0x18002349d  mov     rax, 0C000000000000000h
0x1800234a7  mov     rsi, r9
0x1800234aa  mov     r8, rdx
0x1800234ad  mov     rbx, rcx
0x1800234b0  test    rax, r9
0x1800234b3  jnz     loc_180023693
0x1800234b9  xor     r12d, r12d
0x1800234bc  lea     rax, [rsp+288h+Name]
0x1800234c1  mov     r13d, 104h
0x1800234c7  mov     ecx, 7FFFFFFEh
0x1800234cc  mov     edx, r13d
0x1800234cf  lea     ebp, [r12+1]
0x1800234d4  test    rcx, rcx
0x1800234d7  jz      short loc_1800234F7
0x1800234d9  movzx   r9d, word ptr [r8]
0x1800234dd  test    r9w, r9w
0x1800234e1  jz      short loc_1800234F7
0x1800234e3  mov     [rax], r9w
0x1800234e7  add     r8, 2
0x1800234eb  add     rax, 2
0x1800234ef  sub     rcx, rbp
0x1800234f2  sub     rdx, rbp
0x1800234f5  jnz     short loc_1800234D4
0x1800234f7  test    rdx, rdx
0x1800234fa  lea     rcx, [rax-2]
0x1800234fe  lea     r8, aP0; "_p0"
0x180023505  mov     rdx, r13; unsigned __int64
0x180023508  cmovnz  rcx, rax
0x18002350c  mov     [rcx], r12w
0x180023510  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x180023515  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002351a  mov     edx, esi
0x18002351c  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180023524  and     edx, 7FFFFFFFh; lInitialCount
0x18002352a  mov     [rsp+288h+dwFlags], r12d; int
0x18002352f  mov     r8d, ebp
0x180023532  lea     r9, [rsp+288h+Name]; lpName
0x180023537  cmova   r8d, edx; lMaximumCount
0x18002353b  xor     ecx, ecx; lpSemaphoreAttributes
0x18002353d  call    cs:__imp_CreateSemaphoreExW
0x180023543  mov     r15, rax
0x180023546  test    rax, rax
0x180023549  jnz     short loc_180023579
0x18002354b  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180023550  mov     edi, eax
0x180023552  test    eax, eax
0x180023554  jns     short loc_1800235AD
0x180023556  mov     rcx, [rsp+288h]; this
0x18002355e  lea     r8, aWil; "wil"
0x180023565  mov     r9d, eax; char *
0x180023568  mov     edx, 8Bh; void *
0x18002356d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023572  mov     eax, edi
0x180023574  jmp     loc_18002364E
0x180023579  call    cs:__imp_GetLastError
0x18002357f  mov     rdi, [rbx]
0x180023582  test    rdi, rdi
0x180023585  jz      short loc_1800235AA
0x180023587  call    cs:__imp_GetLastError
0x18002358d  mov     rcx, rdi; hObject
0x180023590  mov     r14d, eax
0x180023593  call    cs:__imp_CloseHandle
0x180023599  test    eax, eax
0x18002359b  jz      loc_180023699
0x1800235a1  mov     ecx, r14d; dwErrCode
0x1800235a4  call    cs:__imp_SetLastError
0x1800235aa  mov     [rbx], r15
0x1800235ad  lea     r8, asc_180094808; "h"
0x1800235b4  shr     rsi, 1Fh
0x1800235b8  mov     rdx, r13; unsigned __int64
0x1800235bb  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x1800235c0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800235c5  test    esi, esi
0x1800235c7  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800235cf  lea     r9, [rsp+288h+Name]; lpName
0x1800235d4  mov     [rsp+288h+dwFlags], r12d; int
0x1800235d9  cmovnz  ebp, esi
0x1800235dc  mov     edx, esi; lInitialCount
0x1800235de  mov     r8d, ebp; lMaximumCount
0x1800235e1  xor     ecx, ecx; lpSemaphoreAttributes
0x1800235e3  call    cs:__imp_CreateSemaphoreExW
0x1800235e9  mov     rbp, rax
0x1800235ec  test    rax, rax
0x1800235ef  jnz     short loc_18002361C
0x1800235f1  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800235f6  mov     ebx, eax
0x1800235f8  test    eax, eax
0x1800235fa  jns     short loc_18002364C
0x1800235fc  mov     rcx, [rsp+288h]; this
0x180023604  lea     r8, aWil; "wil"
0x18002360b  mov     r9d, eax; char *
0x18002360e  mov     edx, 90h; void *
0x180023613  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023618  mov     eax, ebx
0x18002361a  jmp     short loc_18002364E
0x18002361c  call    cs:__imp_GetLastError
0x180023622  mov     rdi, [rbx+8]
0x180023626  test    rdi, rdi
0x180023629  jz      short loc_180023648
0x18002362b  call    cs:__imp_GetLastError
0x180023631  mov     rcx, rdi; hObject
0x180023634  mov     esi, eax
0x180023636  call    cs:__imp_CloseHandle
0x18002363c  test    eax, eax
0x18002363e  jz      short loc_180023679
0x180023640  mov     ecx, esi; dwErrCode
0x180023642  call    cs:__imp_SetLastError
0x180023648  mov     [rbx+8], rbp
0x18002364c  xor     eax, eax
0x18002364e  mov     rcx, [rsp+288h+var_48]
0x180023656  xor     rcx, rsp; StackCookie
0x180023659  call    __security_check_cookie
0x18002365e  mov     rbx, [rsp+288h+arg_8]
0x180023666  add     rsp, 250h
0x18002366d  pop     r15
0x18002366f  pop     r14
0x180023671  pop     r13
0x180023673  pop     r12
0x180023675  pop     rdi
0x180023676  pop     rsi
0x180023677  pop     rbp
0x180023678  retn
0x180023679  mov     rcx, [rsp+288h]; this
0x180023681  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180023688  mov     edx, 0A0Bh; void *
0x18002368d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180023693  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180023699  mov     rcx, [rsp+288h]; this
0x1800236a1  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800236a8  mov     edx, 0A0Bh; void *
0x1800236ad  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
