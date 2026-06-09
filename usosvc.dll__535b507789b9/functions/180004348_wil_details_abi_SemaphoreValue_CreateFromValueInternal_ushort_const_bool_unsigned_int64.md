# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180004348`
- end: `0x180004572`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180003f78`
- `0x18000b35c`

## callees

- `0x1800026d0`
- `0x180004348`
- `0x180004c88`
- `0x1800059c4`
- `0x180006304`
- `0x18000686c`
- `0x18000687c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000440c`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800044af`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000440c`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800044af`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004473`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000450e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004473`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000450e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004448`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004456`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800044e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800044f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004448`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004456`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800044e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800044f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004462`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004502`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004462`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004502`

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
  unsigned int v21; // r8d
  const char *v22; // r9
  unsigned __int64 v23; // rbp
  wil::details *v24; // rcx
  HANDLE v25; // rsi
  int v26; // eax
  unsigned int v27; // ebx
  void *v28; // rdi
  DWORD v29; // ebp
  unsigned int v30; // r8d
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
0x180004348  mov     [rsp+arg_8], rbx
0x18000434d  mov     [rsp+arg_10], rbp
0x180004352  push    rsi
0x180004353  push    rdi
0x180004354  push    r12
0x180004356  push    r14
0x180004358  push    r15
0x18000435a  sub     rsp, 250h
0x180004361  mov     rax, cs:__security_cookie
0x180004368  xor     rax, rsp
0x18000436b  mov     [rsp+278h+var_38], rax
0x180004373  mov     rax, 0C000000000000000h
0x18000437d  mov     rbp, r9
0x180004380  mov     r8, rdx
0x180004383  mov     rbx, rcx
0x180004386  test    rax, r9
0x180004389  jnz     loc_180004559
0x18000438f  xor     r12d, r12d
0x180004392  lea     rax, [rsp+278h+Name]
0x180004397  mov     ecx, 7FFFFFFEh
0x18000439c  mov     edx, 104h
0x1800043a1  lea     esi, [r12+1]
0x1800043a6  test    rcx, rcx
0x1800043a9  jz      short loc_1800043C9
0x1800043ab  movzx   r9d, word ptr [r8]
0x1800043af  test    r9w, r9w
0x1800043b3  jz      short loc_1800043C9
0x1800043b5  mov     [rax], r9w
0x1800043b9  add     r8, 2
0x1800043bd  add     rax, 2
0x1800043c1  sub     rcx, rsi
0x1800043c4  sub     rdx, rsi; unsigned __int64
0x1800043c7  jnz     short loc_1800043A6
0x1800043c9  test    rdx, rdx
0x1800043cc  lea     rcx, [rax-2]
0x1800043d0  lea     r8, aP0; "_p0"
0x1800043d7  cmovnz  rcx, rax
0x1800043db  mov     [rcx], r12w
0x1800043df  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800043e4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800043e9  mov     edx, ebp
0x1800043eb  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800043f3  and     edx, 7FFFFFFFh; lInitialCount
0x1800043f9  mov     [rsp+278h+dwFlags], r12d; int
0x1800043fe  mov     r8d, esi
0x180004401  lea     r9, [rsp+278h+Name]; lpName
0x180004406  cmova   r8d, edx; lMaximumCount
0x18000440a  xor     ecx, ecx; lpSemaphoreAttributes
0x18000440c  call    cs:__imp_CreateSemaphoreExW
0x180004412  mov     r15, rax
0x180004415  test    rax, rax
0x180004418  jnz     short loc_180004448
0x18000441a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000441f  mov     edi, eax
0x180004421  test    eax, eax
0x180004423  jns     short loc_18000447C
0x180004425  mov     rcx, [rsp+278h]; this
0x18000442d  lea     r8, aWil; "wil"
0x180004434  mov     r9d, eax; char *
0x180004437  mov     edx, 8Bh; void *
0x18000443c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004441  mov     eax, edi
0x180004443  jmp     loc_18000451A
0x180004448  call    cs:__imp_GetLastError
0x18000444e  mov     rdi, [rbx]
0x180004451  test    rdi, rdi
0x180004454  jz      short loc_180004479
0x180004456  call    cs:__imp_GetLastError
0x18000445c  mov     rcx, rdi; hObject
0x18000445f  mov     r14d, eax
0x180004462  call    cs:__imp_CloseHandle
0x180004468  test    eax, eax
0x18000446a  jz      loc_18000455F
0x180004470  mov     ecx, r14d; dwErrCode
0x180004473  call    cs:__imp_SetLastError
0x180004479  mov     [rbx], r15
0x18000447c  lea     r8, asc_180010D68; "h"
0x180004483  shr     rbp, 1Fh
0x180004487  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x18000448c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004491  test    ebp, ebp
0x180004493  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000449b  lea     r9, [rsp+278h+Name]; lpName
0x1800044a0  mov     [rsp+278h+dwFlags], r12d; int
0x1800044a5  cmovnz  esi, ebp
0x1800044a8  mov     edx, ebp; lInitialCount
0x1800044aa  mov     r8d, esi; lMaximumCount
0x1800044ad  xor     ecx, ecx; lpSemaphoreAttributes
0x1800044af  call    cs:__imp_CreateSemaphoreExW
0x1800044b5  mov     rsi, rax
0x1800044b8  test    rax, rax
0x1800044bb  jnz     short loc_1800044E8
0x1800044bd  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800044c2  mov     ebx, eax
0x1800044c4  test    eax, eax
0x1800044c6  jns     short loc_180004518
0x1800044c8  mov     rcx, [rsp+278h]; this
0x1800044d0  lea     r8, aWil; "wil"
0x1800044d7  mov     r9d, eax; char *
0x1800044da  mov     edx, 90h; void *
0x1800044df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800044e4  mov     eax, ebx
0x1800044e6  jmp     short loc_18000451A
0x1800044e8  call    cs:__imp_GetLastError
0x1800044ee  mov     rdi, [rbx+8]
0x1800044f2  test    rdi, rdi
0x1800044f5  jz      short loc_180004514
0x1800044f7  call    cs:__imp_GetLastError
0x1800044fd  mov     rcx, rdi; hObject
0x180004500  mov     ebp, eax
0x180004502  call    cs:__imp_CloseHandle
0x180004508  test    eax, eax
0x18000450a  jz      short loc_180004546
0x18000450c  mov     ecx, ebp; dwErrCode
0x18000450e  call    cs:__imp_SetLastError
0x180004514  mov     [rbx+8], rsi
0x180004518  xor     eax, eax
0x18000451a  mov     rcx, [rsp+278h+var_38]
0x180004522  xor     rcx, rsp; StackCookie
0x180004525  call    __security_check_cookie
0x18000452a  lea     r11, [rsp+278h+var_28]
0x180004532  mov     rbx, [r11+38h]
0x180004536  mov     rbp, [r11+40h]
0x18000453a  mov     rsp, r11
0x18000453d  pop     r15
0x18000453f  pop     r14
0x180004541  pop     r12
0x180004543  pop     rdi
0x180004544  pop     rsi
0x180004545  retn
0x180004546  mov     rcx, [rsp+278h]; this
0x18000454e  mov     edx, 0A0Bh; void *
0x180004553  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004559  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000455f  mov     rcx, [rsp+278h]; this
0x180004567  mov     edx, 0A0Bh; void *
0x18000456c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
