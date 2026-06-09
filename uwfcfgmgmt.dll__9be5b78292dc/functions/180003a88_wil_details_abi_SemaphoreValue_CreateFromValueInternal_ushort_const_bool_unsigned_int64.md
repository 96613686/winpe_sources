# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180003a88`
- end: `0x180003c95`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800036bc`

## callees

- `0x180003a88`
- `0x1800042f8`
- `0x180005094`
- `0x1800053ac`
- `0x180005924`
- `0x180005934`
- `0x18001b020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003b4c`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003be8`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003b4c`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003be8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003bac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003c31`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003bac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003c31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c1a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003b9b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c25`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003b9b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c25`

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
  unsigned __int64 v15; // rdx
  int LastErrorFailHr; // ebx
  unsigned int v17; // r8d
  __int64 v18; // rdx
  void *v20; // rbx
  DWORD LastError; // r14d
  __int64 v22; // r8
  const char *v23; // r9
  unsigned __int64 v24; // rbp
  wil::details *v25; // rcx
  HANDLE v26; // rsi
  void *v27; // rbx
  DWORD v28; // ebp
  __int64 v29; // r8
  const char *v30; // r9
  DWORD dwFlags; // [rsp+20h] [rbp-258h]
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
    v20 = *(void **)this;
    if ( *(_QWORD *)this )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v20) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v22, v23);
      SetLastError(LastError);
    }
    *(_QWORD *)this = Semaphore;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v13);
    if ( LastErrorFailHr < 0 )
    {
      v18 = 139;
LABEL_13:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v18, v17, (const char *)(unsigned int)LastErrorFailHr, dwFlags);
      return (unsigned int)LastErrorFailHr;
    }
  }
  v24 = a4 >> 31;
  StringCchCatW(Name, v15, L"h");
  if ( (_DWORD)v24 )
    v10 = v24;
  v26 = CreateSemaphoreExW(0, v24, v10, Name, 0, 0x1F0003u);
  if ( v26 )
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
    *((_QWORD *)this + 1) = v26;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v25);
    if ( LastErrorFailHr < 0 )
    {
      v18 = 144;
      goto LABEL_13;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180003a88  mov     [rsp+arg_8], rbx
0x180003a8d  mov     [rsp+arg_10], rbp
0x180003a92  push    rsi
0x180003a93  push    rdi
0x180003a94  push    r12
0x180003a96  push    r14
0x180003a98  push    r15
0x180003a9a  sub     rsp, 250h
0x180003aa1  mov     rax, cs:__security_cookie
0x180003aa8  xor     rax, rsp
0x180003aab  mov     [rsp+278h+var_38], rax
0x180003ab3  mov     rax, 0C000000000000000h
0x180003abd  mov     rbp, r9
0x180003ac0  mov     r8, rdx
0x180003ac3  mov     rdi, rcx
0x180003ac6  test    rax, r9
0x180003ac9  jnz     loc_180003C7C
0x180003acf  xor     r12d, r12d
0x180003ad2  lea     rax, [rsp+278h+Name]
0x180003ad7  mov     ecx, 7FFFFFFEh
0x180003adc  mov     edx, 104h
0x180003ae1  lea     esi, [r12+1]
0x180003ae6  test    rcx, rcx
0x180003ae9  jz      short loc_180003B09
0x180003aeb  movzx   r9d, word ptr [r8]
0x180003aef  test    r9w, r9w
0x180003af3  jz      short loc_180003B09
0x180003af5  mov     [rax], r9w
0x180003af9  add     r8, 2
0x180003afd  add     rax, 2
0x180003b01  sub     rcx, rsi
0x180003b04  sub     rdx, rsi; unsigned __int64
0x180003b07  jnz     short loc_180003AE6
0x180003b09  test    rdx, rdx
0x180003b0c  lea     rcx, [rax-2]
0x180003b10  lea     r8, aP0; "_p0"
0x180003b17  cmovnz  rcx, rax
0x180003b1b  mov     [rcx], r12w
0x180003b1f  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180003b24  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003b29  mov     edx, ebp
0x180003b2b  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180003b33  and     edx, 7FFFFFFFh; lInitialCount
0x180003b39  mov     [rsp+278h+dwFlags], r12d; int
0x180003b3e  mov     r8d, esi
0x180003b41  lea     r9, [rsp+278h+Name]; lpName
0x180003b46  cmova   r8d, edx; lMaximumCount
0x180003b4a  xor     ecx, ecx; lpSemaphoreAttributes
0x180003b4c  call    cs:__imp_CreateSemaphoreExW
0x180003b52  mov     r15, rax
0x180003b55  test    rax, rax
0x180003b58  jnz     short loc_180003B81
0x180003b5a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003b5f  mov     ebx, eax
0x180003b61  test    eax, eax
0x180003b63  jns     short loc_180003BB5
0x180003b65  mov     edx, 8Bh; void *
0x180003b6a  mov     rcx, [rsp+278h]; this
0x180003b72  mov     r9d, ebx; char *
0x180003b75  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003b7a  mov     eax, ebx
0x180003b7c  jmp     loc_180003C3D
0x180003b81  call    cs:__imp_GetLastError
0x180003b87  mov     rbx, [rdi]
0x180003b8a  test    rbx, rbx
0x180003b8d  jz      short loc_180003BB2
0x180003b8f  call    cs:__imp_GetLastError
0x180003b95  mov     rcx, rbx; hObject
0x180003b98  mov     r14d, eax
0x180003b9b  call    cs:__imp_CloseHandle
0x180003ba1  test    eax, eax
0x180003ba3  jz      loc_180003C82
0x180003ba9  mov     ecx, r14d; dwErrCode
0x180003bac  call    cs:__imp_SetLastError
0x180003bb2  mov     [rdi], r15
0x180003bb5  lea     r8, asc_18001F838; "h"
0x180003bbc  shr     rbp, 1Fh
0x180003bc0  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180003bc5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003bca  test    ebp, ebp
0x180003bcc  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180003bd4  lea     r9, [rsp+278h+Name]; lpName
0x180003bd9  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x180003bde  cmovnz  esi, ebp
0x180003be1  mov     edx, ebp; lInitialCount
0x180003be3  mov     r8d, esi; lMaximumCount
0x180003be6  xor     ecx, ecx; lpSemaphoreAttributes
0x180003be8  call    cs:__imp_CreateSemaphoreExW
0x180003bee  mov     rsi, rax
0x180003bf1  test    rax, rax
0x180003bf4  jnz     short loc_180003C0B
0x180003bf6  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003bfb  mov     ebx, eax
0x180003bfd  test    eax, eax
0x180003bff  jns     short loc_180003C3B
0x180003c01  mov     edx, 90h
0x180003c06  jmp     loc_180003B6A
0x180003c0b  call    cs:__imp_GetLastError
0x180003c11  mov     rbx, [rdi+8]
0x180003c15  test    rbx, rbx
0x180003c18  jz      short loc_180003C37
0x180003c1a  call    cs:__imp_GetLastError
0x180003c20  mov     rcx, rbx; hObject
0x180003c23  mov     ebp, eax
0x180003c25  call    cs:__imp_CloseHandle
0x180003c2b  test    eax, eax
0x180003c2d  jz      short loc_180003C69
0x180003c2f  mov     ecx, ebp; dwErrCode
0x180003c31  call    cs:__imp_SetLastError
0x180003c37  mov     [rdi+8], rsi
0x180003c3b  xor     eax, eax
0x180003c3d  mov     rcx, [rsp+278h+var_38]
0x180003c45  xor     rcx, rsp; StackCookie
0x180003c48  call    __security_check_cookie
0x180003c4d  lea     r11, [rsp+278h+var_28]
0x180003c55  mov     rbx, [r11+38h]
0x180003c59  mov     rbp, [r11+40h]
0x180003c5d  mov     rsp, r11
0x180003c60  pop     r15
0x180003c62  pop     r14
0x180003c64  pop     r12
0x180003c66  pop     rdi
0x180003c67  pop     rsi
0x180003c68  retn
0x180003c69  mov     rcx, [rsp+278h]; this
0x180003c71  mov     edx, 0A0Bh; void *
0x180003c76  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003c7c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003c82  mov     rcx, [rsp+278h]; this
0x180003c8a  mov     edx, 0A0Bh; void *
0x180003c8f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
