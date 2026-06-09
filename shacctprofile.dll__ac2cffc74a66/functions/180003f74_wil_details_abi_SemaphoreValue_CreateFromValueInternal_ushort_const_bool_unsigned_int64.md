# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180003f74`
- end: `0x180004197`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `547`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180003bd0`

## callees

- `0x180002230`
- `0x180003f74`
- `0x1800047f8`
- `0x180005584`
- `0x180005830`
- `0x180005dac`
- `0x180005dbc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000403d`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800040dc`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000403d`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800040dc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000409d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004134`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000409d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004134`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004072`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004080`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000410e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000411d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004072`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004080`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000410e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000411d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000408c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004128`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000408c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004128`

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
0x180003f74  mov     [rsp+arg_8], rbx
0x180003f79  push    rbp
0x180003f7a  push    rsi
0x180003f7b  push    rdi
0x180003f7c  push    r12
0x180003f7e  push    r13
0x180003f80  push    r14
0x180003f82  push    r15
0x180003f84  sub     rsp, 250h
0x180003f8b  mov     rax, cs:__security_cookie
0x180003f92  xor     rax, rsp
0x180003f95  mov     [rsp+288h+var_48], rax
0x180003f9d  mov     rax, 0C000000000000000h
0x180003fa7  mov     rsi, r9
0x180003faa  mov     r8, rdx
0x180003fad  mov     rbx, rcx
0x180003fb0  test    rax, r9
0x180003fb3  jnz     loc_18000417E
0x180003fb9  xor     r12d, r12d
0x180003fbc  lea     rax, [rsp+288h+Name]
0x180003fc1  mov     r13d, 104h
0x180003fc7  mov     ecx, 7FFFFFFEh
0x180003fcc  mov     edx, r13d
0x180003fcf  lea     ebp, [r12+1]
0x180003fd4  test    rcx, rcx
0x180003fd7  jz      short loc_180003FF7
0x180003fd9  movzx   r9d, word ptr [r8]
0x180003fdd  test    r9w, r9w
0x180003fe1  jz      short loc_180003FF7
0x180003fe3  mov     [rax], r9w
0x180003fe7  add     r8, 2
0x180003feb  add     rax, 2
0x180003fef  sub     rcx, rbp
0x180003ff2  sub     rdx, rbp
0x180003ff5  jnz     short loc_180003FD4
0x180003ff7  test    rdx, rdx
0x180003ffa  lea     rcx, [rax-2]
0x180003ffe  lea     r8, aP0; "_p0"
0x180004005  mov     rdx, r13; unsigned __int64
0x180004008  cmovnz  rcx, rax
0x18000400c  mov     [rcx], r12w
0x180004010  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x180004015  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000401a  mov     edx, esi
0x18000401c  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180004024  and     edx, 7FFFFFFFh; lInitialCount
0x18000402a  mov     [rsp+288h+dwFlags], r12d; int
0x18000402f  mov     r8d, ebp
0x180004032  lea     r9, [rsp+288h+Name]; lpName
0x180004037  cmova   r8d, edx; lMaximumCount
0x18000403b  xor     ecx, ecx; lpSemaphoreAttributes
0x18000403d  call    cs:__imp_CreateSemaphoreExW
0x180004043  mov     r15, rax
0x180004046  test    rax, rax
0x180004049  jnz     short loc_180004072
0x18000404b  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004050  mov     edi, eax
0x180004052  test    eax, eax
0x180004054  jns     short loc_1800040A6
0x180004056  mov     rcx, [rsp+288h]; this
0x18000405e  mov     r9d, eax; char *
0x180004061  mov     edx, 8Bh; void *
0x180004066  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000406b  mov     eax, edi
0x18000406d  jmp     loc_180004140
0x180004072  call    cs:__imp_GetLastError
0x180004078  mov     rdi, [rbx]
0x18000407b  test    rdi, rdi
0x18000407e  jz      short loc_1800040A3
0x180004080  call    cs:__imp_GetLastError
0x180004086  mov     rcx, rdi; hObject
0x180004089  mov     r14d, eax
0x18000408c  call    cs:__imp_CloseHandle
0x180004092  test    eax, eax
0x180004094  jz      loc_180004184
0x18000409a  mov     ecx, r14d; dwErrCode
0x18000409d  call    cs:__imp_SetLastError
0x1800040a3  mov     [rbx], r15
0x1800040a6  lea     r8, asc_18000C028; "h"
0x1800040ad  shr     rsi, 1Fh
0x1800040b1  mov     rdx, r13; unsigned __int64
0x1800040b4  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x1800040b9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800040be  test    esi, esi
0x1800040c0  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800040c8  lea     r9, [rsp+288h+Name]; lpName
0x1800040cd  mov     [rsp+288h+dwFlags], r12d; int
0x1800040d2  cmovnz  ebp, esi
0x1800040d5  mov     edx, esi; lInitialCount
0x1800040d7  mov     r8d, ebp; lMaximumCount
0x1800040da  xor     ecx, ecx; lpSemaphoreAttributes
0x1800040dc  call    cs:__imp_CreateSemaphoreExW
0x1800040e2  mov     rbp, rax
0x1800040e5  test    rax, rax
0x1800040e8  jnz     short loc_18000410E
0x1800040ea  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800040ef  mov     ebx, eax
0x1800040f1  test    eax, eax
0x1800040f3  jns     short loc_18000413E
0x1800040f5  mov     rcx, [rsp+288h]; this
0x1800040fd  mov     r9d, eax; char *
0x180004100  mov     edx, 90h; void *
0x180004105  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000410a  mov     eax, ebx
0x18000410c  jmp     short loc_180004140
0x18000410e  call    cs:__imp_GetLastError
0x180004114  mov     rdi, [rbx+8]
0x180004118  test    rdi, rdi
0x18000411b  jz      short loc_18000413A
0x18000411d  call    cs:__imp_GetLastError
0x180004123  mov     rcx, rdi; hObject
0x180004126  mov     esi, eax
0x180004128  call    cs:__imp_CloseHandle
0x18000412e  test    eax, eax
0x180004130  jz      short loc_18000416B
0x180004132  mov     ecx, esi; dwErrCode
0x180004134  call    cs:__imp_SetLastError
0x18000413a  mov     [rbx+8], rbp
0x18000413e  xor     eax, eax
0x180004140  mov     rcx, [rsp+288h+var_48]
0x180004148  xor     rcx, rsp; StackCookie
0x18000414b  call    __security_check_cookie
0x180004150  mov     rbx, [rsp+288h+arg_8]
0x180004158  add     rsp, 250h
0x18000415f  pop     r15
0x180004161  pop     r14
0x180004163  pop     r13
0x180004165  pop     r12
0x180004167  pop     rdi
0x180004168  pop     rsi
0x180004169  pop     rbp
0x18000416a  retn
0x18000416b  mov     rcx, [rsp+288h]; this
0x180004173  mov     edx, 0A0Bh; void *
0x180004178  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000417e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004184  mov     rcx, [rsp+288h]; this
0x18000418c  mov     edx, 0A0Bh; void *
0x180004191  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
