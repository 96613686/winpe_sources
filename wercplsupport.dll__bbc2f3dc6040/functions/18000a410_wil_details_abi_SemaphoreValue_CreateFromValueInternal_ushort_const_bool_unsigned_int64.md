# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18000a410`
- end: `0x18000a64a`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `570`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180009b78`
- `0x180009f58`

## callees

- `0x18000a410`
- `0x18000b6d4`
- `0x18000d97c`
- `0x18000dccc`
- `0x18000f200`
- `0x18000f210`
- `0x1800121b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000a4d4`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000a578`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000a4d4`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000a578`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a511`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a51f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a5b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a5c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a511`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a51f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a5b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a5c1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a53c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a5d8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a53c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a5d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a52b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a5cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a52b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a5cc`

## string_xrefs

- `0x18000a4f5`: `wil::details_abi::SemaphoreValue::CreateFromValueInternal`
- `0x18000a599`: `wil::details_abi::SemaphoreValue::CreateFromValueInternal`

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
  unsigned int v17; // r8d
  unsigned int v18; // edi
  void *v20; // rdi
  DWORD LastError; // r14d
  unsigned int v22; // r8d
  unsigned __int64 v23; // rbp
  wil::details *v24; // rcx
  HANDLE v25; // rsi
  int v26; // eax
  unsigned int v27; // r8d
  unsigned int v28; // ebx
  void *v29; // rdi
  DWORD v30; // ebp
  unsigned int v31; // r8d
  char *dwFlags; // [rsp+20h] [rbp-258h]
  char *dwFlagsa; // [rsp+20h] [rbp-258h]
  DWORD dwDesiredAccess; // [rsp+28h] [rbp-250h]
  DWORD dwDesiredAccessa; // [rsp+28h] [rbp-250h]
  WCHAR Name[264]; // [rsp+30h] [rbp-248h] BYREF
  wil::details::in1diag4 *retaddr; // [rsp+278h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag4::_FailFastImmediate_Unexpected(this);
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
        wil::details::in1diag4::_FailFast_GetLastError(
          retaddr,
          (void *)0xA0B,
          v22,
          "wil::details::CloseHandle",
          dwFlags);
      SetLastError(LastError);
    }
    *(_QWORD *)this = Semaphore;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v13);
    v18 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 )
    {
      LODWORD(dwFlags) = LastErrorFailHr;
      wil::details::in1diag4::Return_Hr(
        retaddr,
        (void *)0x8B,
        v17,
        "wil::details_abi::SemaphoreValue::CreateFromValueInternal",
        (wil::details *)dwFlags,
        dwDesiredAccess);
      return v18;
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
    v29 = (void *)*((_QWORD *)this + 1);
    if ( v29 )
    {
      v30 = GetLastError();
      if ( !CloseHandle(v29) )
        wil::details::in1diag4::_FailFast_GetLastError(
          retaddr,
          (void *)0xA0B,
          v31,
          "wil::details::CloseHandle",
          dwFlagsa);
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
      LODWORD(dwFlagsa) = v26;
      wil::details::in1diag4::Return_Hr(
        retaddr,
        (void *)0x90,
        v27,
        "wil::details_abi::SemaphoreValue::CreateFromValueInternal",
        (wil::details *)dwFlagsa,
        dwDesiredAccessa);
      return v28;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000a410  mov     [rsp+arg_8], rbx
0x18000a415  mov     [rsp+arg_10], rbp
0x18000a41a  push    rsi
0x18000a41b  push    rdi
0x18000a41c  push    r12
0x18000a41e  push    r14
0x18000a420  push    r15
0x18000a422  sub     rsp, 250h
0x18000a429  mov     rax, cs:__security_cookie
0x18000a430  xor     rax, rsp
0x18000a433  mov     [rsp+278h+var_38], rax
0x18000a43b  mov     rax, 0C000000000000000h
0x18000a445  mov     rbp, r9
0x18000a448  mov     r8, rdx
0x18000a44b  mov     rbx, rcx
0x18000a44e  test    rax, r9
0x18000a451  jnz     loc_18000A62A
0x18000a457  xor     r12d, r12d
0x18000a45a  lea     rax, [rsp+278h+Name]
0x18000a45f  mov     ecx, 7FFFFFFEh
0x18000a464  mov     edx, 104h
0x18000a469  lea     esi, [r12+1]
0x18000a46e  test    rcx, rcx
0x18000a471  jz      short loc_18000A491
0x18000a473  movzx   r9d, word ptr [r8]
0x18000a477  test    r9w, r9w
0x18000a47b  jz      short loc_18000A491
0x18000a47d  mov     [rax], r9w
0x18000a481  add     r8, 2
0x18000a485  add     rax, 2
0x18000a489  sub     rcx, rsi
0x18000a48c  sub     rdx, rsi; unsigned __int64
0x18000a48f  jnz     short loc_18000A46E
0x18000a491  test    rdx, rdx
0x18000a494  lea     rcx, [rax-2]
0x18000a498  lea     r8, aP0; "_p0"
0x18000a49f  cmovnz  rcx, rax
0x18000a4a3  mov     [rcx], r12w
0x18000a4a7  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x18000a4ac  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a4b1  mov     edx, ebp
0x18000a4b3  mov     [rsp+278h+dwDesiredAccess], 1F0003h; int
0x18000a4bb  and     edx, 7FFFFFFFh; lInitialCount
0x18000a4c1  mov     dword ptr [rsp+278h+dwFlags], r12d; char *
0x18000a4c6  mov     r8d, esi
0x18000a4c9  lea     r9, [rsp+278h+Name]; lpName
0x18000a4ce  cmova   r8d, edx; lMaximumCount
0x18000a4d2  xor     ecx, ecx; lpSemaphoreAttributes
0x18000a4d4  call    cs:__imp_CreateSemaphoreExW
0x18000a4da  mov     r15, rax
0x18000a4dd  test    rax, rax
0x18000a4e0  jnz     short loc_18000A511
0x18000a4e2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000a4e7  mov     edi, eax
0x18000a4e9  test    eax, eax
0x18000a4eb  jns     short loc_18000A545
0x18000a4ed  mov     rcx, [rsp+278h]; this
0x18000a4f5  lea     r9, aWilDetailsAbiS_3; "wil::details_abi::SemaphoreValue::Creat"...
0x18000a4fc  mov     edx, 8Bh; void *
0x18000a501  mov     dword ptr [rsp+278h+dwFlags], eax; wil::details *
0x18000a505  call    ?Return_Hr@in1diag4@details@wil@@YAXPEAXIPEBD1J@Z; wil::details::in1diag4::Return_Hr(void *,uint,char const *,char const *,long)
0x18000a50a  mov     eax, edi
0x18000a50c  jmp     loc_18000A5E4
0x18000a511  call    cs:__imp_GetLastError
0x18000a517  mov     rdi, [rbx]
0x18000a51a  test    rdi, rdi
0x18000a51d  jz      short loc_18000A542
0x18000a51f  call    cs:__imp_GetLastError
0x18000a525  mov     rcx, rdi; hObject
0x18000a528  mov     r14d, eax
0x18000a52b  call    cs:__imp_CloseHandle
0x18000a531  test    eax, eax
0x18000a533  jz      loc_18000A630
0x18000a539  mov     ecx, r14d; dwErrCode
0x18000a53c  call    cs:__imp_SetLastError
0x18000a542  mov     [rbx], r15
0x18000a545  lea     r8, asc_180016E84; "h"
0x18000a54c  shr     rbp, 1Fh
0x18000a550  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x18000a555  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a55a  test    ebp, ebp
0x18000a55c  mov     [rsp+278h+dwDesiredAccess], 1F0003h; int
0x18000a564  lea     r9, [rsp+278h+Name]; lpName
0x18000a569  mov     dword ptr [rsp+278h+dwFlags], r12d; char *
0x18000a56e  cmovnz  esi, ebp
0x18000a571  mov     edx, ebp; lInitialCount
0x18000a573  mov     r8d, esi; lMaximumCount
0x18000a576  xor     ecx, ecx; lpSemaphoreAttributes
0x18000a578  call    cs:__imp_CreateSemaphoreExW
0x18000a57e  mov     rsi, rax
0x18000a581  test    rax, rax
0x18000a584  jnz     short loc_18000A5B2
0x18000a586  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000a58b  mov     ebx, eax
0x18000a58d  test    eax, eax
0x18000a58f  jns     short loc_18000A5E2
0x18000a591  mov     rcx, [rsp+278h]; this
0x18000a599  lea     r9, aWilDetailsAbiS_3; "wil::details_abi::SemaphoreValue::Creat"...
0x18000a5a0  mov     edx, 90h; void *
0x18000a5a5  mov     dword ptr [rsp+278h+dwFlags], eax; wil::details *
0x18000a5a9  call    ?Return_Hr@in1diag4@details@wil@@YAXPEAXIPEBD1J@Z; wil::details::in1diag4::Return_Hr(void *,uint,char const *,char const *,long)
0x18000a5ae  mov     eax, ebx
0x18000a5b0  jmp     short loc_18000A5E4
0x18000a5b2  call    cs:__imp_GetLastError
0x18000a5b8  mov     rdi, [rbx+8]
0x18000a5bc  test    rdi, rdi
0x18000a5bf  jz      short loc_18000A5DE
0x18000a5c1  call    cs:__imp_GetLastError
0x18000a5c7  mov     rcx, rdi; hObject
0x18000a5ca  mov     ebp, eax
0x18000a5cc  call    cs:__imp_CloseHandle
0x18000a5d2  test    eax, eax
0x18000a5d4  jz      short loc_18000A610
0x18000a5d6  mov     ecx, ebp; dwErrCode
0x18000a5d8  call    cs:__imp_SetLastError
0x18000a5de  mov     [rbx+8], rsi
0x18000a5e2  xor     eax, eax
0x18000a5e4  mov     rcx, [rsp+278h+var_38]
0x18000a5ec  xor     rcx, rsp; StackCookie
0x18000a5ef  call    __security_check_cookie
0x18000a5f4  lea     r11, [rsp+278h+var_28]
0x18000a5fc  mov     rbx, [r11+38h]
0x18000a600  mov     rbp, [r11+40h]
0x18000a604  mov     rsp, r11
0x18000a607  pop     r15
0x18000a609  pop     r14
0x18000a60b  pop     r12
0x18000a60d  pop     rdi
0x18000a60e  pop     rsi
0x18000a60f  retn
0x18000a610  mov     rcx, [rsp+278h]; this
0x18000a618  lea     r9, aWilDetailsClos; "wil::details::CloseHandle"
0x18000a61f  mov     edx, 0A0Bh; void *
0x18000a624  call    ?_FailFast_GetLastError@in1diag4@details@wil@@YAXPEAXIPEBD1@Z; wil::details::in1diag4::_FailFast_GetLastError(void *,uint,char const *,char const *)
0x18000a62a  call    ?_FailFastImmediate_Unexpected@in1diag4@details@wil@@YAXXZ; wil::details::in1diag4::_FailFastImmediate_Unexpected(void)
0x18000a630  mov     rcx, [rsp+278h]; this
0x18000a638  lea     r9, aWilDetailsClos; "wil::details::CloseHandle"
0x18000a63f  mov     edx, 0A0Bh; void *
0x18000a644  call    ?_FailFast_GetLastError@in1diag4@details@wil@@YAXPEAXIPEBD1@Z; wil::details::in1diag4::_FailFast_GetLastError(void *,uint,char const *,char const *)
```
