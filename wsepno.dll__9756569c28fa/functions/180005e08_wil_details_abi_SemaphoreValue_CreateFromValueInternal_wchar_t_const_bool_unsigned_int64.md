# wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)

- ea: `0x180005e08`
- end: `0x180006039`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z`
- size: `561`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const wchar_t *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000558c`
- `0x18000595c`

## callees

- `0x180001770`
- `0x180005e08`
- `0x180007418`
- `0x18000a374`
- `0x18000a6bc`
- `0x18000b494`
- `0x18000b4a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005f38`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005fd6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005f38`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005fd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005f0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005f1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005fb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005fbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005f0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005f1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005fb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005fbf`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180005ed1`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180005f77`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180005ed1`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180005f77`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005f27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005fca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005f27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005fca`

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
0x180005e08  mov     [rsp+arg_8], rbx
0x180005e0d  push    rbp
0x180005e0e  push    rsi
0x180005e0f  push    rdi
0x180005e10  push    r12
0x180005e12  push    r13
0x180005e14  push    r14
0x180005e16  push    r15
0x180005e18  sub     rsp, 250h
0x180005e1f  mov     rax, cs:__security_cookie
0x180005e26  xor     rax, rsp
0x180005e29  mov     [rsp+288h+var_48], rax
0x180005e31  mov     rax, 0C000000000000000h
0x180005e3b  mov     rsi, r9
0x180005e3e  mov     r8, rdx
0x180005e41  mov     rbx, rcx
0x180005e44  test    rax, r9
0x180005e47  jnz     loc_180006020
0x180005e4d  xor     r12d, r12d
0x180005e50  lea     rax, [rsp+288h+Name]
0x180005e55  mov     r13d, 104h
0x180005e5b  mov     ecx, 7FFFFFFEh
0x180005e60  mov     edx, r13d
0x180005e63  lea     ebp, [r12+1]
0x180005e68  test    rcx, rcx
0x180005e6b  jz      short loc_180005E8B
0x180005e6d  movzx   r9d, word ptr [r8]
0x180005e71  test    r9w, r9w
0x180005e75  jz      short loc_180005E8B
0x180005e77  mov     [rax], r9w
0x180005e7b  add     r8, 2
0x180005e7f  add     rax, 2
0x180005e83  sub     rcx, rbp
0x180005e86  sub     rdx, rbp
0x180005e89  jnz     short loc_180005E68
0x180005e8b  test    rdx, rdx
0x180005e8e  lea     rcx, [rax-2]
0x180005e92  lea     r8, aP0; "_p0"
0x180005e99  mov     rdx, r13; unsigned __int64
0x180005e9c  cmovnz  rcx, rax
0x180005ea0  mov     [rcx], r12w
0x180005ea4  lea     rcx, [rsp+288h+Name]; wchar_t *
0x180005ea9  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180005eae  mov     edx, esi
0x180005eb0  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180005eb8  and     edx, 7FFFFFFFh; lInitialCount
0x180005ebe  mov     [rsp+288h+dwFlags], r12d; int
0x180005ec3  mov     r8d, ebp
0x180005ec6  lea     r9, [rsp+288h+Name]; lpName
0x180005ecb  cmova   r8d, edx; lMaximumCount
0x180005ecf  xor     ecx, ecx; lpSemaphoreAttributes
0x180005ed1  call    cs:__imp_CreateSemaphoreExW
0x180005ed7  mov     r15, rax
0x180005eda  test    rax, rax
0x180005edd  jnz     short loc_180005F0D
0x180005edf  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005ee4  mov     edi, eax
0x180005ee6  test    eax, eax
0x180005ee8  jns     short loc_180005F41
0x180005eea  mov     rcx, [rsp+288h]; this
0x180005ef2  lea     r8, aWil; "wil"
0x180005ef9  mov     r9d, eax; char *
0x180005efc  mov     edx, 8Bh; void *
0x180005f01  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005f06  mov     eax, edi
0x180005f08  jmp     loc_180005FE2
0x180005f0d  call    cs:__imp_GetLastError
0x180005f13  mov     rdi, [rbx]
0x180005f16  test    rdi, rdi
0x180005f19  jz      short loc_180005F3E
0x180005f1b  call    cs:__imp_GetLastError
0x180005f21  mov     rcx, rdi; hObject
0x180005f24  mov     r14d, eax
0x180005f27  call    cs:__imp_CloseHandle
0x180005f2d  test    eax, eax
0x180005f2f  jz      loc_180006026
0x180005f35  mov     ecx, r14d; dwErrCode
0x180005f38  call    cs:__imp_SetLastError
0x180005f3e  mov     [rbx], r15
0x180005f41  lea     r8, asc_180010EC8; "h"
0x180005f48  shr     rsi, 1Fh
0x180005f4c  mov     rdx, r13; unsigned __int64
0x180005f4f  lea     rcx, [rsp+288h+Name]; wchar_t *
0x180005f54  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180005f59  test    esi, esi
0x180005f5b  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180005f63  lea     r9, [rsp+288h+Name]; lpName
0x180005f68  mov     [rsp+288h+dwFlags], r12d; int
0x180005f6d  cmovnz  ebp, esi
0x180005f70  mov     edx, esi; lInitialCount
0x180005f72  mov     r8d, ebp; lMaximumCount
0x180005f75  xor     ecx, ecx; lpSemaphoreAttributes
0x180005f77  call    cs:__imp_CreateSemaphoreExW
0x180005f7d  mov     rbp, rax
0x180005f80  test    rax, rax
0x180005f83  jnz     short loc_180005FB0
0x180005f85  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005f8a  mov     ebx, eax
0x180005f8c  test    eax, eax
0x180005f8e  jns     short loc_180005FE0
0x180005f90  mov     rcx, [rsp+288h]; this
0x180005f98  lea     r8, aWil; "wil"
0x180005f9f  mov     r9d, eax; char *
0x180005fa2  mov     edx, 90h; void *
0x180005fa7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005fac  mov     eax, ebx
0x180005fae  jmp     short loc_180005FE2
0x180005fb0  call    cs:__imp_GetLastError
0x180005fb6  mov     rdi, [rbx+8]
0x180005fba  test    rdi, rdi
0x180005fbd  jz      short loc_180005FDC
0x180005fbf  call    cs:__imp_GetLastError
0x180005fc5  mov     rcx, rdi; hObject
0x180005fc8  mov     esi, eax
0x180005fca  call    cs:__imp_CloseHandle
0x180005fd0  test    eax, eax
0x180005fd2  jz      short loc_18000600D
0x180005fd4  mov     ecx, esi; dwErrCode
0x180005fd6  call    cs:__imp_SetLastError
0x180005fdc  mov     [rbx+8], rbp
0x180005fe0  xor     eax, eax
0x180005fe2  mov     rcx, [rsp+288h+var_48]
0x180005fea  xor     rcx, rsp; StackCookie
0x180005fed  call    __security_check_cookie
0x180005ff2  mov     rbx, [rsp+288h+arg_8]
0x180005ffa  add     rsp, 250h
0x180006001  pop     r15
0x180006003  pop     r14
0x180006005  pop     r13
0x180006007  pop     r12
0x180006009  pop     rdi
0x18000600a  pop     rsi
0x18000600b  pop     rbp
0x18000600c  retn
0x18000600d  mov     rcx, [rsp+288h]; this
0x180006015  mov     edx, 0A0Bh; void *
0x18000601a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006020  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180006026  mov     rcx, [rsp+288h]; this
0x18000602e  mov     edx, 0A0Bh; void *
0x180006033  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
