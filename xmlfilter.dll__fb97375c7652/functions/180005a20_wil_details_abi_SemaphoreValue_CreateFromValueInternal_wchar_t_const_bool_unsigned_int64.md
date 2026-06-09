# wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)

- ea: `0x180005a20`
- end: `0x180005c4a`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180005198`
- `0x180005568`

## callees

- `0x1800020e0`
- `0x180005a20`
- `0x180008158`
- `0x18000b744`
- `0x18000c2b4`
- `0x18000d1fc`
- `0x18000d20c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005b4b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005be6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005b4b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005be6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005bc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005bcf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005bc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005bcf`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180005ae4`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180005b87`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180005ae4`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180005b87`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005b3a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005bda`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005b3a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005bda`

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
  __int64 v21; // r8
  const char *v22; // r9
  unsigned __int64 v23; // rbp
  wil::details *v24; // rcx
  HANDLE v25; // rsi
  int v26; // eax
  unsigned int v27; // ebx
  void *v28; // rdi
  DWORD v29; // ebp
  __int64 v30; // r8
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
0x180005a20  mov     [rsp+arg_8], rbx
0x180005a25  mov     [rsp+arg_10], rbp
0x180005a2a  push    rsi
0x180005a2b  push    rdi
0x180005a2c  push    r12
0x180005a2e  push    r14
0x180005a30  push    r15
0x180005a32  sub     rsp, 250h
0x180005a39  mov     rax, cs:__security_cookie
0x180005a40  xor     rax, rsp
0x180005a43  mov     [rsp+278h+var_38], rax
0x180005a4b  mov     rax, 0C000000000000000h
0x180005a55  mov     rbp, r9
0x180005a58  mov     r8, rdx
0x180005a5b  mov     rbx, rcx
0x180005a5e  test    rax, r9
0x180005a61  jnz     loc_180005C31
0x180005a67  xor     r12d, r12d
0x180005a6a  lea     rax, [rsp+278h+Name]
0x180005a6f  mov     ecx, 7FFFFFFEh
0x180005a74  mov     edx, 104h
0x180005a79  lea     esi, [r12+1]
0x180005a7e  test    rcx, rcx
0x180005a81  jz      short loc_180005AA1
0x180005a83  movzx   r9d, word ptr [r8]
0x180005a87  test    r9w, r9w
0x180005a8b  jz      short loc_180005AA1
0x180005a8d  mov     [rax], r9w
0x180005a91  add     r8, 2
0x180005a95  add     rax, 2
0x180005a99  sub     rcx, rsi
0x180005a9c  sub     rdx, rsi; unsigned __int64
0x180005a9f  jnz     short loc_180005A7E
0x180005aa1  test    rdx, rdx
0x180005aa4  lea     rcx, [rax-2]
0x180005aa8  lea     r8, aP0; "_p0"
0x180005aaf  cmovnz  rcx, rax
0x180005ab3  mov     [rcx], r12w
0x180005ab7  lea     rcx, [rsp+278h+Name]; wchar_t *
0x180005abc  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180005ac1  mov     edx, ebp
0x180005ac3  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180005acb  and     edx, 7FFFFFFFh; lInitialCount
0x180005ad1  mov     [rsp+278h+dwFlags], r12d; int
0x180005ad6  mov     r8d, esi
0x180005ad9  lea     r9, [rsp+278h+Name]; lpName
0x180005ade  cmova   r8d, edx; lMaximumCount
0x180005ae2  xor     ecx, ecx; lpSemaphoreAttributes
0x180005ae4  call    cs:__imp_CreateSemaphoreExW
0x180005aea  mov     r15, rax
0x180005aed  test    rax, rax
0x180005af0  jnz     short loc_180005B20
0x180005af2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005af7  mov     edi, eax
0x180005af9  test    eax, eax
0x180005afb  jns     short loc_180005B54
0x180005afd  mov     rcx, [rsp+278h]; this
0x180005b05  lea     r8, aWil; "wil"
0x180005b0c  mov     r9d, eax; char *
0x180005b0f  mov     edx, 8Bh; void *
0x180005b14  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005b19  mov     eax, edi
0x180005b1b  jmp     loc_180005BF2
0x180005b20  call    cs:__imp_GetLastError
0x180005b26  mov     rdi, [rbx]
0x180005b29  test    rdi, rdi
0x180005b2c  jz      short loc_180005B51
0x180005b2e  call    cs:__imp_GetLastError
0x180005b34  mov     rcx, rdi; hObject
0x180005b37  mov     r14d, eax
0x180005b3a  call    cs:__imp_CloseHandle
0x180005b40  test    eax, eax
0x180005b42  jz      loc_180005C37
0x180005b48  mov     ecx, r14d; dwErrCode
0x180005b4b  call    cs:__imp_SetLastError
0x180005b51  mov     [rbx], r15
0x180005b54  lea     r8, asc_180019780; "h"
0x180005b5b  shr     rbp, 1Fh
0x180005b5f  lea     rcx, [rsp+278h+Name]; wchar_t *
0x180005b64  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180005b69  test    ebp, ebp
0x180005b6b  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180005b73  lea     r9, [rsp+278h+Name]; lpName
0x180005b78  mov     [rsp+278h+dwFlags], r12d; int
0x180005b7d  cmovnz  esi, ebp
0x180005b80  mov     edx, ebp; lInitialCount
0x180005b82  mov     r8d, esi; lMaximumCount
0x180005b85  xor     ecx, ecx; lpSemaphoreAttributes
0x180005b87  call    cs:__imp_CreateSemaphoreExW
0x180005b8d  mov     rsi, rax
0x180005b90  test    rax, rax
0x180005b93  jnz     short loc_180005BC0
0x180005b95  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005b9a  mov     ebx, eax
0x180005b9c  test    eax, eax
0x180005b9e  jns     short loc_180005BF0
0x180005ba0  mov     rcx, [rsp+278h]; this
0x180005ba8  lea     r8, aWil; "wil"
0x180005baf  mov     r9d, eax; char *
0x180005bb2  mov     edx, 90h; void *
0x180005bb7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005bbc  mov     eax, ebx
0x180005bbe  jmp     short loc_180005BF2
0x180005bc0  call    cs:__imp_GetLastError
0x180005bc6  mov     rdi, [rbx+8]
0x180005bca  test    rdi, rdi
0x180005bcd  jz      short loc_180005BEC
0x180005bcf  call    cs:__imp_GetLastError
0x180005bd5  mov     rcx, rdi; hObject
0x180005bd8  mov     ebp, eax
0x180005bda  call    cs:__imp_CloseHandle
0x180005be0  test    eax, eax
0x180005be2  jz      short loc_180005C1E
0x180005be4  mov     ecx, ebp; dwErrCode
0x180005be6  call    cs:__imp_SetLastError
0x180005bec  mov     [rbx+8], rsi
0x180005bf0  xor     eax, eax
0x180005bf2  mov     rcx, [rsp+278h+var_38]
0x180005bfa  xor     rcx, rsp; StackCookie
0x180005bfd  call    __security_check_cookie
0x180005c02  lea     r11, [rsp+278h+var_28]
0x180005c0a  mov     rbx, [r11+38h]
0x180005c0e  mov     rbp, [r11+40h]
0x180005c12  mov     rsp, r11
0x180005c15  pop     r15
0x180005c17  pop     r14
0x180005c19  pop     r12
0x180005c1b  pop     rdi
0x180005c1c  pop     rsi
0x180005c1d  retn
0x180005c1e  mov     rcx, [rsp+278h]; this
0x180005c26  mov     edx, 0A0Bh; void *
0x180005c2b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005c31  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180005c37  mov     rcx, [rsp+278h]; this
0x180005c3f  mov     edx, 0A0Bh; void *
0x180005c44  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
