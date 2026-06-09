# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180006f54`
- end: `0x18000717e`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000671c`
- `0x180006af8`

## callees

- `0x180004120`
- `0x180006f54`
- `0x180007e18`
- `0x180009fe4`
- `0x18000aa34`
- `0x18000b75c`
- `0x18000b76c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180007018`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800070bb`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180007018`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800070bb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000707f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000711a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000707f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000711a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007054`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007062`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800070f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007103`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007054`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007062`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800070f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007103`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000706e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000710e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000706e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000710e`

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
0x180006f54  mov     [rsp+arg_8], rbx
0x180006f59  mov     [rsp+arg_10], rbp
0x180006f5e  push    rsi
0x180006f5f  push    rdi
0x180006f60  push    r12
0x180006f62  push    r14
0x180006f64  push    r15
0x180006f66  sub     rsp, 250h
0x180006f6d  mov     rax, cs:__security_cookie
0x180006f74  xor     rax, rsp
0x180006f77  mov     [rsp+278h+var_38], rax
0x180006f7f  mov     rax, 0C000000000000000h
0x180006f89  mov     rbp, r9
0x180006f8c  mov     r8, rdx
0x180006f8f  mov     rbx, rcx
0x180006f92  test    rax, r9
0x180006f95  jnz     loc_180007165
0x180006f9b  xor     r12d, r12d
0x180006f9e  lea     rax, [rsp+278h+Name]
0x180006fa3  mov     ecx, 7FFFFFFEh
0x180006fa8  mov     edx, 104h
0x180006fad  lea     esi, [r12+1]
0x180006fb2  test    rcx, rcx
0x180006fb5  jz      short loc_180006FD5
0x180006fb7  movzx   r9d, word ptr [r8]
0x180006fbb  test    r9w, r9w
0x180006fbf  jz      short loc_180006FD5
0x180006fc1  mov     [rax], r9w
0x180006fc5  add     r8, 2
0x180006fc9  add     rax, 2
0x180006fcd  sub     rcx, rsi
0x180006fd0  sub     rdx, rsi; unsigned __int64
0x180006fd3  jnz     short loc_180006FB2
0x180006fd5  test    rdx, rdx
0x180006fd8  lea     rcx, [rax-2]
0x180006fdc  lea     r8, aP0; "_p0"
0x180006fe3  cmovnz  rcx, rax
0x180006fe7  mov     [rcx], r12w
0x180006feb  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180006ff0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006ff5  mov     edx, ebp
0x180006ff7  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180006fff  and     edx, 7FFFFFFFh; lInitialCount
0x180007005  mov     [rsp+278h+dwFlags], r12d; int
0x18000700a  mov     r8d, esi
0x18000700d  lea     r9, [rsp+278h+Name]; lpName
0x180007012  cmova   r8d, edx; lMaximumCount
0x180007016  xor     ecx, ecx; lpSemaphoreAttributes
0x180007018  call    cs:__imp_CreateSemaphoreExW
0x18000701e  mov     r15, rax
0x180007021  test    rax, rax
0x180007024  jnz     short loc_180007054
0x180007026  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000702b  mov     edi, eax
0x18000702d  test    eax, eax
0x18000702f  jns     short loc_180007088
0x180007031  mov     rcx, [rsp+278h]; this
0x180007039  lea     r8, aWil; "wil"
0x180007040  mov     r9d, eax; char *
0x180007043  mov     edx, 8Bh; void *
0x180007048  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000704d  mov     eax, edi
0x18000704f  jmp     loc_180007126
0x180007054  call    cs:__imp_GetLastError
0x18000705a  mov     rdi, [rbx]
0x18000705d  test    rdi, rdi
0x180007060  jz      short loc_180007085
0x180007062  call    cs:__imp_GetLastError
0x180007068  mov     rcx, rdi; hObject
0x18000706b  mov     r14d, eax
0x18000706e  call    cs:__imp_CloseHandle
0x180007074  test    eax, eax
0x180007076  jz      loc_18000716B
0x18000707c  mov     ecx, r14d; dwErrCode
0x18000707f  call    cs:__imp_SetLastError
0x180007085  mov     [rbx], r15
0x180007088  lea     r8, asc_180036AB0; "h"
0x18000708f  shr     rbp, 1Fh
0x180007093  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180007098  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000709d  test    ebp, ebp
0x18000709f  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800070a7  lea     r9, [rsp+278h+Name]; lpName
0x1800070ac  mov     [rsp+278h+dwFlags], r12d; int
0x1800070b1  cmovnz  esi, ebp
0x1800070b4  mov     edx, ebp; lInitialCount
0x1800070b6  mov     r8d, esi; lMaximumCount
0x1800070b9  xor     ecx, ecx; lpSemaphoreAttributes
0x1800070bb  call    cs:__imp_CreateSemaphoreExW
0x1800070c1  mov     rsi, rax
0x1800070c4  test    rax, rax
0x1800070c7  jnz     short loc_1800070F4
0x1800070c9  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800070ce  mov     ebx, eax
0x1800070d0  test    eax, eax
0x1800070d2  jns     short loc_180007124
0x1800070d4  mov     rcx, [rsp+278h]; this
0x1800070dc  lea     r8, aWil; "wil"
0x1800070e3  mov     r9d, eax; char *
0x1800070e6  mov     edx, 90h; void *
0x1800070eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800070f0  mov     eax, ebx
0x1800070f2  jmp     short loc_180007126
0x1800070f4  call    cs:__imp_GetLastError
0x1800070fa  mov     rdi, [rbx+8]
0x1800070fe  test    rdi, rdi
0x180007101  jz      short loc_180007120
0x180007103  call    cs:__imp_GetLastError
0x180007109  mov     rcx, rdi; hObject
0x18000710c  mov     ebp, eax
0x18000710e  call    cs:__imp_CloseHandle
0x180007114  test    eax, eax
0x180007116  jz      short loc_180007152
0x180007118  mov     ecx, ebp; dwErrCode
0x18000711a  call    cs:__imp_SetLastError
0x180007120  mov     [rbx+8], rsi
0x180007124  xor     eax, eax
0x180007126  mov     rcx, [rsp+278h+var_38]
0x18000712e  xor     rcx, rsp; StackCookie
0x180007131  call    __security_check_cookie
0x180007136  lea     r11, [rsp+278h+var_28]
0x18000713e  mov     rbx, [r11+38h]
0x180007142  mov     rbp, [r11+40h]
0x180007146  mov     rsp, r11
0x180007149  pop     r15
0x18000714b  pop     r14
0x18000714d  pop     r12
0x18000714f  pop     rdi
0x180007150  pop     rsi
0x180007151  retn
0x180007152  mov     rcx, [rsp+278h]; this
0x18000715a  mov     edx, 0A0Bh; void *
0x18000715f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007165  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000716b  mov     rcx, [rsp+278h]; this
0x180007173  mov     edx, 0A0Bh; void *
0x180007178  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
