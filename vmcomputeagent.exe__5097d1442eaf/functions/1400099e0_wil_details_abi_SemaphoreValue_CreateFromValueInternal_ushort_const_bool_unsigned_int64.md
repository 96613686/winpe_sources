# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1400099e0`
- end: `0x140009c1f`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `575`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1400091b8`
- `0x140009598`

## callees

- `0x140005360`
- `0x1400099e0`
- `0x14000a900`
- `0x14000cef4`
- `0x14000d944`
- `0x14000ea34`
- `0x14000ea44`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140009aa9`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140009b4f`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140009aa9`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140009b4f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140009b10`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140009bae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140009b10`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140009bae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009ae5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009af3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009b88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009b97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009ae5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009af3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009b88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009b97`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140009aff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140009ba2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140009aff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140009ba2`

## string_xrefs

- `0x140009bed`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x140009c0d`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x1400099e0  mov     [rsp+arg_8], rbx
0x1400099e5  push    rbp
0x1400099e6  push    rsi
0x1400099e7  push    rdi
0x1400099e8  push    r12
0x1400099ea  push    r13
0x1400099ec  push    r14
0x1400099ee  push    r15
0x1400099f0  sub     rsp, 250h
0x1400099f7  mov     rax, cs:__security_cookie
0x1400099fe  xor     rax, rsp
0x140009a01  mov     [rsp+288h+var_48], rax
0x140009a09  mov     rax, 0C000000000000000h
0x140009a13  mov     rsi, r9
0x140009a16  mov     r8, rdx
0x140009a19  mov     rbx, rcx
0x140009a1c  test    rax, r9
0x140009a1f  jnz     loc_140009BFF
0x140009a25  xor     r12d, r12d
0x140009a28  lea     rax, [rsp+288h+Name]
0x140009a2d  mov     r13d, 104h
0x140009a33  mov     ecx, 7FFFFFFEh
0x140009a38  mov     edx, r13d
0x140009a3b  lea     ebp, [r12+1]
0x140009a40  test    rcx, rcx
0x140009a43  jz      short loc_140009A63
0x140009a45  movzx   r9d, word ptr [r8]
0x140009a49  test    r9w, r9w
0x140009a4d  jz      short loc_140009A63
0x140009a4f  mov     [rax], r9w
0x140009a53  add     r8, 2
0x140009a57  add     rax, 2
0x140009a5b  sub     rcx, rbp
0x140009a5e  sub     rdx, rbp
0x140009a61  jnz     short loc_140009A40
0x140009a63  test    rdx, rdx
0x140009a66  lea     rcx, [rax-2]
0x140009a6a  lea     r8, aP0; "_p0"
0x140009a71  mov     rdx, r13; unsigned __int64
0x140009a74  cmovnz  rcx, rax
0x140009a78  mov     [rcx], r12w
0x140009a7c  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x140009a81  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140009a86  mov     edx, esi
0x140009a88  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140009a90  and     edx, 7FFFFFFFh; lInitialCount
0x140009a96  mov     [rsp+288h+dwFlags], r12d; int
0x140009a9b  mov     r8d, ebp
0x140009a9e  lea     r9, [rsp+288h+Name]; lpName
0x140009aa3  cmova   r8d, edx; lMaximumCount
0x140009aa7  xor     ecx, ecx; lpSemaphoreAttributes
0x140009aa9  call    cs:__imp_CreateSemaphoreExW
0x140009aaf  mov     r15, rax
0x140009ab2  test    rax, rax
0x140009ab5  jnz     short loc_140009AE5
0x140009ab7  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140009abc  mov     edi, eax
0x140009abe  test    eax, eax
0x140009ac0  jns     short loc_140009B19
0x140009ac2  mov     rcx, [rsp+288h]; this
0x140009aca  lea     r8, aWil; "wil"
0x140009ad1  mov     r9d, eax; char *
0x140009ad4  mov     edx, 8Bh; void *
0x140009ad9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009ade  mov     eax, edi
0x140009ae0  jmp     loc_140009BBA
0x140009ae5  call    cs:__imp_GetLastError
0x140009aeb  mov     rdi, [rbx]
0x140009aee  test    rdi, rdi
0x140009af1  jz      short loc_140009B16
0x140009af3  call    cs:__imp_GetLastError
0x140009af9  mov     rcx, rdi; hObject
0x140009afc  mov     r14d, eax
0x140009aff  call    cs:__imp_CloseHandle
0x140009b05  test    eax, eax
0x140009b07  jz      loc_140009C05
0x140009b0d  mov     ecx, r14d; dwErrCode
0x140009b10  call    cs:__imp_SetLastError
0x140009b16  mov     [rbx], r15
0x140009b19  lea     r8, asc_140116B28; "h"
0x140009b20  shr     rsi, 1Fh
0x140009b24  mov     rdx, r13; unsigned __int64
0x140009b27  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x140009b2c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140009b31  test    esi, esi
0x140009b33  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140009b3b  lea     r9, [rsp+288h+Name]; lpName
0x140009b40  mov     [rsp+288h+dwFlags], r12d; int
0x140009b45  cmovnz  ebp, esi
0x140009b48  mov     edx, esi; lInitialCount
0x140009b4a  mov     r8d, ebp; lMaximumCount
0x140009b4d  xor     ecx, ecx; lpSemaphoreAttributes
0x140009b4f  call    cs:__imp_CreateSemaphoreExW
0x140009b55  mov     rbp, rax
0x140009b58  test    rax, rax
0x140009b5b  jnz     short loc_140009B88
0x140009b5d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140009b62  mov     ebx, eax
0x140009b64  test    eax, eax
0x140009b66  jns     short loc_140009BB8
0x140009b68  mov     rcx, [rsp+288h]; this
0x140009b70  lea     r8, aWil; "wil"
0x140009b77  mov     r9d, eax; char *
0x140009b7a  mov     edx, 90h; void *
0x140009b7f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009b84  mov     eax, ebx
0x140009b86  jmp     short loc_140009BBA
0x140009b88  call    cs:__imp_GetLastError
0x140009b8e  mov     rdi, [rbx+8]
0x140009b92  test    rdi, rdi
0x140009b95  jz      short loc_140009BB4
0x140009b97  call    cs:__imp_GetLastError
0x140009b9d  mov     rcx, rdi; hObject
0x140009ba0  mov     esi, eax
0x140009ba2  call    cs:__imp_CloseHandle
0x140009ba8  test    eax, eax
0x140009baa  jz      short loc_140009BE5
0x140009bac  mov     ecx, esi; dwErrCode
0x140009bae  call    cs:__imp_SetLastError
0x140009bb4  mov     [rbx+8], rbp
0x140009bb8  xor     eax, eax
0x140009bba  mov     rcx, [rsp+288h+var_48]
0x140009bc2  xor     rcx, rsp; StackCookie
0x140009bc5  call    __security_check_cookie
0x140009bca  mov     rbx, [rsp+288h+arg_8]
0x140009bd2  add     rsp, 250h
0x140009bd9  pop     r15
0x140009bdb  pop     r14
0x140009bdd  pop     r13
0x140009bdf  pop     r12
0x140009be1  pop     rdi
0x140009be2  pop     rsi
0x140009be3  pop     rbp
0x140009be4  retn
0x140009be5  mov     rcx, [rsp+288h]; this
0x140009bed  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140009bf4  mov     edx, 0A0Bh; void *
0x140009bf9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140009bff  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140009c05  mov     rcx, [rsp+288h]; this
0x140009c0d  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140009c14  mov     edx, 0A0Bh; void *
0x140009c19  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
