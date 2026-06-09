# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1800041b0`
- end: `0x1800043d3`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `547`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180003a3c`
- `0x180003de0`

## callees

- `0x1800041b0`
- `0x180005008`
- `0x180007204`
- `0x180007620`
- `0x1800083ec`
- `0x1800083fc`
- `0x180021740`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004279`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004318`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004279`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004318`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800042ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800042bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000434a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004359`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800042ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800042bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000434a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004359`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800042d9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004370`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800042d9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004370`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800042c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004364`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800042c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004364`

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
0x1800041b0  mov     [rsp+arg_8], rbx
0x1800041b5  push    rbp
0x1800041b6  push    rsi
0x1800041b7  push    rdi
0x1800041b8  push    r12
0x1800041ba  push    r13
0x1800041bc  push    r14
0x1800041be  push    r15
0x1800041c0  sub     rsp, 250h
0x1800041c7  mov     rax, cs:__security_cookie
0x1800041ce  xor     rax, rsp
0x1800041d1  mov     [rsp+288h+var_48], rax
0x1800041d9  mov     rax, 0C000000000000000h
0x1800041e3  mov     rsi, r9
0x1800041e6  mov     r8, rdx
0x1800041e9  mov     rbx, rcx
0x1800041ec  test    rax, r9
0x1800041ef  jnz     loc_1800043BA
0x1800041f5  xor     r12d, r12d
0x1800041f8  lea     rax, [rsp+288h+Name]
0x1800041fd  mov     r13d, 104h
0x180004203  mov     ecx, 7FFFFFFEh
0x180004208  mov     edx, r13d
0x18000420b  lea     ebp, [r12+1]
0x180004210  test    rcx, rcx
0x180004213  jz      short loc_180004233
0x180004215  movzx   r9d, word ptr [r8]
0x180004219  test    r9w, r9w
0x18000421d  jz      short loc_180004233
0x18000421f  mov     [rax], r9w
0x180004223  add     r8, 2
0x180004227  add     rax, 2
0x18000422b  sub     rcx, rbp
0x18000422e  sub     rdx, rbp
0x180004231  jnz     short loc_180004210
0x180004233  test    rdx, rdx
0x180004236  lea     rcx, [rax-2]
0x18000423a  lea     r8, aP0; "_p0"
0x180004241  mov     rdx, r13; unsigned __int64
0x180004244  cmovnz  rcx, rax
0x180004248  mov     [rcx], r12w
0x18000424c  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x180004251  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004256  mov     edx, esi
0x180004258  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180004260  and     edx, 7FFFFFFFh; lInitialCount
0x180004266  mov     [rsp+288h+dwFlags], r12d; int
0x18000426b  mov     r8d, ebp
0x18000426e  lea     r9, [rsp+288h+Name]; lpName
0x180004273  cmova   r8d, edx; lMaximumCount
0x180004277  xor     ecx, ecx; lpSemaphoreAttributes
0x180004279  call    cs:__imp_CreateSemaphoreExW
0x18000427f  mov     r15, rax
0x180004282  test    rax, rax
0x180004285  jnz     short loc_1800042AE
0x180004287  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000428c  mov     edi, eax
0x18000428e  test    eax, eax
0x180004290  jns     short loc_1800042E2
0x180004292  mov     rcx, [rsp+288h]; this
0x18000429a  mov     r9d, eax; char *
0x18000429d  mov     edx, 8Bh; void *
0x1800042a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800042a7  mov     eax, edi
0x1800042a9  jmp     loc_18000437C
0x1800042ae  call    cs:__imp_GetLastError
0x1800042b4  mov     rdi, [rbx]
0x1800042b7  test    rdi, rdi
0x1800042ba  jz      short loc_1800042DF
0x1800042bc  call    cs:__imp_GetLastError
0x1800042c2  mov     rcx, rdi; hObject
0x1800042c5  mov     r14d, eax
0x1800042c8  call    cs:__imp_CloseHandle
0x1800042ce  test    eax, eax
0x1800042d0  jz      loc_1800043C0
0x1800042d6  mov     ecx, r14d; dwErrCode
0x1800042d9  call    cs:__imp_SetLastError
0x1800042df  mov     [rbx], r15
0x1800042e2  lea     r8, asc_180024A40; "h"
0x1800042e9  shr     rsi, 1Fh
0x1800042ed  mov     rdx, r13; unsigned __int64
0x1800042f0  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x1800042f5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800042fa  test    esi, esi
0x1800042fc  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180004304  lea     r9, [rsp+288h+Name]; lpName
0x180004309  mov     [rsp+288h+dwFlags], r12d; int
0x18000430e  cmovnz  ebp, esi
0x180004311  mov     edx, esi; lInitialCount
0x180004313  mov     r8d, ebp; lMaximumCount
0x180004316  xor     ecx, ecx; lpSemaphoreAttributes
0x180004318  call    cs:__imp_CreateSemaphoreExW
0x18000431e  mov     rbp, rax
0x180004321  test    rax, rax
0x180004324  jnz     short loc_18000434A
0x180004326  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000432b  mov     ebx, eax
0x18000432d  test    eax, eax
0x18000432f  jns     short loc_18000437A
0x180004331  mov     rcx, [rsp+288h]; this
0x180004339  mov     r9d, eax; char *
0x18000433c  mov     edx, 90h; void *
0x180004341  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004346  mov     eax, ebx
0x180004348  jmp     short loc_18000437C
0x18000434a  call    cs:__imp_GetLastError
0x180004350  mov     rdi, [rbx+8]
0x180004354  test    rdi, rdi
0x180004357  jz      short loc_180004376
0x180004359  call    cs:__imp_GetLastError
0x18000435f  mov     rcx, rdi; hObject
0x180004362  mov     esi, eax
0x180004364  call    cs:__imp_CloseHandle
0x18000436a  test    eax, eax
0x18000436c  jz      short loc_1800043A7
0x18000436e  mov     ecx, esi; dwErrCode
0x180004370  call    cs:__imp_SetLastError
0x180004376  mov     [rbx+8], rbp
0x18000437a  xor     eax, eax
0x18000437c  mov     rcx, [rsp+288h+var_48]
0x180004384  xor     rcx, rsp; StackCookie
0x180004387  call    __security_check_cookie
0x18000438c  mov     rbx, [rsp+288h+arg_8]
0x180004394  add     rsp, 250h
0x18000439b  pop     r15
0x18000439d  pop     r14
0x18000439f  pop     r13
0x1800043a1  pop     r12
0x1800043a3  pop     rdi
0x1800043a4  pop     rsi
0x1800043a5  pop     rbp
0x1800043a6  retn
0x1800043a7  mov     rcx, [rsp+288h]; this
0x1800043af  mov     edx, 0A0Bh; void *
0x1800043b4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800043ba  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800043c0  mov     rcx, [rsp+288h]; this
0x1800043c8  mov     edx, 0A0Bh; void *
0x1800043cd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
