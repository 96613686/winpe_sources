# wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)

- ea: `0x18000845c`
- end: `0x180008686`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const wchar_t *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180008080`

## callees

- `0x180006ea0`
- `0x1800071d4`
- `0x1800071e4`
- `0x18000845c`
- `0x180008834`
- `0x180009700`
- `0x18000e990`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000855c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000856a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800085fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000860b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000855c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000856a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800085fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000860b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008587`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008622`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008587`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008622`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180008520`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800085c3`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180008520`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800085c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008576`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008616`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008576`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008616`

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
0x18000845c  mov     [rsp+arg_8], rbx
0x180008461  mov     [rsp+arg_10], rbp
0x180008466  push    rsi
0x180008467  push    rdi
0x180008468  push    r12
0x18000846a  push    r14
0x18000846c  push    r15
0x18000846e  sub     rsp, 250h
0x180008475  mov     rax, cs:__security_cookie
0x18000847c  xor     rax, rsp
0x18000847f  mov     [rsp+278h+var_38], rax
0x180008487  mov     rax, 0C000000000000000h
0x180008491  mov     rbp, r9
0x180008494  mov     r8, rdx
0x180008497  mov     rbx, rcx
0x18000849a  test    rax, r9
0x18000849d  jnz     loc_18000866D
0x1800084a3  xor     r12d, r12d
0x1800084a6  lea     rax, [rsp+278h+Name]
0x1800084ab  mov     ecx, 7FFFFFFEh
0x1800084b0  mov     edx, 104h
0x1800084b5  lea     esi, [r12+1]
0x1800084ba  test    rcx, rcx
0x1800084bd  jz      short loc_1800084DD
0x1800084bf  movzx   r9d, word ptr [r8]
0x1800084c3  test    r9w, r9w
0x1800084c7  jz      short loc_1800084DD
0x1800084c9  mov     [rax], r9w
0x1800084cd  add     r8, 2
0x1800084d1  add     rax, 2
0x1800084d5  sub     rcx, rsi
0x1800084d8  sub     rdx, rsi; unsigned __int64
0x1800084db  jnz     short loc_1800084BA
0x1800084dd  test    rdx, rdx
0x1800084e0  lea     rcx, [rax-2]
0x1800084e4  lea     r8, aP0; "_p0"
0x1800084eb  cmovnz  rcx, rax
0x1800084ef  mov     [rcx], r12w
0x1800084f3  lea     rcx, [rsp+278h+Name]; wchar_t *
0x1800084f8  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800084fd  mov     edx, ebp
0x1800084ff  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180008507  and     edx, 7FFFFFFFh; lInitialCount
0x18000850d  mov     [rsp+278h+dwFlags], r12d; int
0x180008512  mov     r8d, esi
0x180008515  lea     r9, [rsp+278h+Name]; lpName
0x18000851a  cmova   r8d, edx; lMaximumCount
0x18000851e  xor     ecx, ecx; lpSemaphoreAttributes
0x180008520  call    cs:__imp_CreateSemaphoreExW
0x180008526  mov     r15, rax
0x180008529  test    rax, rax
0x18000852c  jnz     short loc_18000855C
0x18000852e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180008533  mov     edi, eax
0x180008535  test    eax, eax
0x180008537  jns     short loc_180008590
0x180008539  mov     rcx, [rsp+278h]; this
0x180008541  lea     r8, aWil; "wil"
0x180008548  mov     r9d, eax; char *
0x18000854b  mov     edx, 8Bh; void *
0x180008550  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008555  mov     eax, edi
0x180008557  jmp     loc_18000862E
0x18000855c  call    cs:__imp_GetLastError
0x180008562  mov     rdi, [rbx]
0x180008565  test    rdi, rdi
0x180008568  jz      short loc_18000858D
0x18000856a  call    cs:__imp_GetLastError
0x180008570  mov     rcx, rdi; hObject
0x180008573  mov     r14d, eax
0x180008576  call    cs:__imp_CloseHandle
0x18000857c  test    eax, eax
0x18000857e  jz      loc_180008673
0x180008584  mov     ecx, r14d; dwErrCode
0x180008587  call    cs:__imp_SetLastError
0x18000858d  mov     [rbx], r15
0x180008590  lea     r8, asc_1800139C0; "h"
0x180008597  shr     rbp, 1Fh
0x18000859b  lea     rcx, [rsp+278h+Name]; wchar_t *
0x1800085a0  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800085a5  test    ebp, ebp
0x1800085a7  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800085af  lea     r9, [rsp+278h+Name]; lpName
0x1800085b4  mov     [rsp+278h+dwFlags], r12d; int
0x1800085b9  cmovnz  esi, ebp
0x1800085bc  mov     edx, ebp; lInitialCount
0x1800085be  mov     r8d, esi; lMaximumCount
0x1800085c1  xor     ecx, ecx; lpSemaphoreAttributes
0x1800085c3  call    cs:__imp_CreateSemaphoreExW
0x1800085c9  mov     rsi, rax
0x1800085cc  test    rax, rax
0x1800085cf  jnz     short loc_1800085FC
0x1800085d1  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800085d6  mov     ebx, eax
0x1800085d8  test    eax, eax
0x1800085da  jns     short loc_18000862C
0x1800085dc  mov     rcx, [rsp+278h]; this
0x1800085e4  lea     r8, aWil; "wil"
0x1800085eb  mov     r9d, eax; char *
0x1800085ee  mov     edx, 90h; void *
0x1800085f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800085f8  mov     eax, ebx
0x1800085fa  jmp     short loc_18000862E
0x1800085fc  call    cs:__imp_GetLastError
0x180008602  mov     rdi, [rbx+8]
0x180008606  test    rdi, rdi
0x180008609  jz      short loc_180008628
0x18000860b  call    cs:__imp_GetLastError
0x180008611  mov     rcx, rdi; hObject
0x180008614  mov     ebp, eax
0x180008616  call    cs:__imp_CloseHandle
0x18000861c  test    eax, eax
0x18000861e  jz      short loc_18000865A
0x180008620  mov     ecx, ebp; dwErrCode
0x180008622  call    cs:__imp_SetLastError
0x180008628  mov     [rbx+8], rsi
0x18000862c  xor     eax, eax
0x18000862e  mov     rcx, [rsp+278h+var_38]
0x180008636  xor     rcx, rsp; StackCookie
0x180008639  call    __security_check_cookie
0x18000863e  lea     r11, [rsp+278h+var_28]
0x180008646  mov     rbx, [r11+38h]
0x18000864a  mov     rbp, [r11+40h]
0x18000864e  mov     rsp, r11
0x180008651  pop     r15
0x180008653  pop     r14
0x180008655  pop     r12
0x180008657  pop     rdi
0x180008658  pop     rsi
0x180008659  retn
0x18000865a  mov     rcx, [rsp+278h]; this
0x180008662  mov     edx, 0A0Bh; void *
0x180008667  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000866d  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180008673  mov     rcx, [rsp+278h]; this
0x18000867b  mov     edx, 0A0Bh; void *
0x180008680  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
