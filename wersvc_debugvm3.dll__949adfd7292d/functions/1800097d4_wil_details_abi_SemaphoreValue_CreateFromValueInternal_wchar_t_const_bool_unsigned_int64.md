# wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)

- ea: `0x1800097d4`
- end: `0x1800099fe`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const wchar_t *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000900c`
- `0x1800093dc`

## callees

- `0x1800029d0`
- `0x1800097d4`
- `0x18000a768`
- `0x18000cb10`
- `0x18000ce58`
- `0x18001140c`
- `0x18001141c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800098d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800098e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009974`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009983`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800098d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800098e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009974`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009983`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800098ff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000999a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800098ff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000999a`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180009898`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000993b`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180009898`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000993b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800098ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000998e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800098ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000998e`

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
0x1800097d4  mov     [rsp+arg_8], rbx
0x1800097d9  mov     [rsp+arg_10], rbp
0x1800097de  push    rsi
0x1800097df  push    rdi
0x1800097e0  push    r12
0x1800097e2  push    r14
0x1800097e4  push    r15
0x1800097e6  sub     rsp, 250h
0x1800097ed  mov     rax, cs:__security_cookie
0x1800097f4  xor     rax, rsp
0x1800097f7  mov     [rsp+278h+var_38], rax
0x1800097ff  mov     rax, 0C000000000000000h
0x180009809  mov     rbp, r9
0x18000980c  mov     r8, rdx
0x18000980f  mov     rbx, rcx
0x180009812  test    rax, r9
0x180009815  jnz     loc_1800099E5
0x18000981b  xor     r12d, r12d
0x18000981e  lea     rax, [rsp+278h+Name]
0x180009823  mov     ecx, 7FFFFFFEh
0x180009828  mov     edx, 104h
0x18000982d  lea     esi, [r12+1]
0x180009832  test    rcx, rcx
0x180009835  jz      short loc_180009855
0x180009837  movzx   r9d, word ptr [r8]
0x18000983b  test    r9w, r9w
0x18000983f  jz      short loc_180009855
0x180009841  mov     [rax], r9w
0x180009845  add     r8, 2
0x180009849  add     rax, 2
0x18000984d  sub     rcx, rsi
0x180009850  sub     rdx, rsi; unsigned __int64
0x180009853  jnz     short loc_180009832
0x180009855  test    rdx, rdx
0x180009858  lea     rcx, [rax-2]
0x18000985c  lea     r8, aP0; "_p0"
0x180009863  cmovnz  rcx, rax
0x180009867  mov     [rcx], r12w
0x18000986b  lea     rcx, [rsp+278h+Name]; wchar_t *
0x180009870  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180009875  mov     edx, ebp
0x180009877  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000987f  and     edx, 7FFFFFFFh; lInitialCount
0x180009885  mov     [rsp+278h+dwFlags], r12d; int
0x18000988a  mov     r8d, esi
0x18000988d  lea     r9, [rsp+278h+Name]; lpName
0x180009892  cmova   r8d, edx; lMaximumCount
0x180009896  xor     ecx, ecx; lpSemaphoreAttributes
0x180009898  call    cs:__imp_CreateSemaphoreExW
0x18000989e  mov     r15, rax
0x1800098a1  test    rax, rax
0x1800098a4  jnz     short loc_1800098D4
0x1800098a6  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800098ab  mov     edi, eax
0x1800098ad  test    eax, eax
0x1800098af  jns     short loc_180009908
0x1800098b1  mov     rcx, [rsp+278h]; this
0x1800098b9  lea     r8, aWil; "wil"
0x1800098c0  mov     r9d, eax; char *
0x1800098c3  mov     edx, 8Bh; void *
0x1800098c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800098cd  mov     eax, edi
0x1800098cf  jmp     loc_1800099A6
0x1800098d4  call    cs:__imp_GetLastError
0x1800098da  mov     rdi, [rbx]
0x1800098dd  test    rdi, rdi
0x1800098e0  jz      short loc_180009905
0x1800098e2  call    cs:__imp_GetLastError
0x1800098e8  mov     rcx, rdi; hObject
0x1800098eb  mov     r14d, eax
0x1800098ee  call    cs:__imp_CloseHandle
0x1800098f4  test    eax, eax
0x1800098f6  jz      loc_1800099EB
0x1800098fc  mov     ecx, r14d; dwErrCode
0x1800098ff  call    cs:__imp_SetLastError
0x180009905  mov     [rbx], r15
0x180009908  lea     r8, asc_180039938; "h"
0x18000990f  shr     rbp, 1Fh
0x180009913  lea     rcx, [rsp+278h+Name]; wchar_t *
0x180009918  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000991d  test    ebp, ebp
0x18000991f  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180009927  lea     r9, [rsp+278h+Name]; lpName
0x18000992c  mov     [rsp+278h+dwFlags], r12d; int
0x180009931  cmovnz  esi, ebp
0x180009934  mov     edx, ebp; lInitialCount
0x180009936  mov     r8d, esi; lMaximumCount
0x180009939  xor     ecx, ecx; lpSemaphoreAttributes
0x18000993b  call    cs:__imp_CreateSemaphoreExW
0x180009941  mov     rsi, rax
0x180009944  test    rax, rax
0x180009947  jnz     short loc_180009974
0x180009949  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000994e  mov     ebx, eax
0x180009950  test    eax, eax
0x180009952  jns     short loc_1800099A4
0x180009954  mov     rcx, [rsp+278h]; this
0x18000995c  lea     r8, aWil; "wil"
0x180009963  mov     r9d, eax; char *
0x180009966  mov     edx, 90h; void *
0x18000996b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009970  mov     eax, ebx
0x180009972  jmp     short loc_1800099A6
0x180009974  call    cs:__imp_GetLastError
0x18000997a  mov     rdi, [rbx+8]
0x18000997e  test    rdi, rdi
0x180009981  jz      short loc_1800099A0
0x180009983  call    cs:__imp_GetLastError
0x180009989  mov     rcx, rdi; hObject
0x18000998c  mov     ebp, eax
0x18000998e  call    cs:__imp_CloseHandle
0x180009994  test    eax, eax
0x180009996  jz      short loc_1800099D2
0x180009998  mov     ecx, ebp; dwErrCode
0x18000999a  call    cs:__imp_SetLastError
0x1800099a0  mov     [rbx+8], rsi
0x1800099a4  xor     eax, eax
0x1800099a6  mov     rcx, [rsp+278h+var_38]
0x1800099ae  xor     rcx, rsp; StackCookie
0x1800099b1  call    __security_check_cookie
0x1800099b6  lea     r11, [rsp+278h+var_28]
0x1800099be  mov     rbx, [r11+38h]
0x1800099c2  mov     rbp, [r11+40h]
0x1800099c6  mov     rsp, r11
0x1800099c9  pop     r15
0x1800099cb  pop     r14
0x1800099cd  pop     r12
0x1800099cf  pop     rdi
0x1800099d0  pop     rsi
0x1800099d1  retn
0x1800099d2  mov     rcx, [rsp+278h]; this
0x1800099da  mov     edx, 0A0Bh; void *
0x1800099df  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800099e5  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800099eb  mov     rcx, [rsp+278h]; this
0x1800099f3  mov     edx, 0A0Bh; void *
0x1800099f8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
