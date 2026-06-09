# ImageLogger::Log(unsigned __int64,LogLevel,wchar_t const *,...)

- ea: `0x18007351c`
- end: `0x18007365a`
- name: `?Log@ImageLogger@@QEBAX_KW4LogLevel@@PEB_WZZ`
- size: `318`
- prototype: `void __high(unsigned __int64, enum LogLevel, const wchar_t *, ...)`
- caller_count: `7`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1800722d8`
- `0x1800737d0`
- `0x180073940`
- `0x180073a10`
- `0x1800740d8`
- `0x180074288`
- `0x180074738`

## callees

- `0x18000d030`
- `0x18000d400`
- `0x18000d5a4`
- `0x18000de4c`
- `0x18000de9c`
- `0x18007351c`
- `0x18008a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800735c6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800735c6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180073612`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180073612`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteString` at `0x180073630`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteString` at `0x180073630`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x18007359e`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x18007359e`

## pseudocode

```c
void ImageLogger::Log(__int64 a1, ULONGLONG a2, int a3, const wchar_t *a4, ...)
{
  int v7; // eax
  unsigned __int64 v8; // r15
  unsigned __int64 v9; // rax
  wchar_t *v10; // rax
  WCHAR *v11; // rsi
  UCHAR v12; // bp
  int v13; // ebx
  int v14; // ebx
  void (__fastcall *v15)(WCHAR *); // rax
  const struct std::nothrow_t *v16; // rdx
  va_list va; // [rsp+90h] [rbp+28h] BYREF

  va_start(va, a4);
  v7 = vscwprintf(a4, va);
  if ( v7 <= 0 )
    return;
  v8 = v7 + 1;
  v9 = 2 * v8;
  if ( !is_mul_ok(v8, 2u) )
    v9 = -1;
  v10 = (wchar_t *)operator new[](v9, (const struct std::nothrow_t *)std::nothrow);
  v11 = v10;
  if ( !v10 )
  {
    RaiseFailFastException(0, 0, 0);
    return;
  }
  v12 = 0;
  vswprintf_s(v10, v8, a4, va);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 56));
  if ( !a3 )
  {
    v15 = *(void (__fastcall **)(WCHAR *))(a1 + 8);
    v12 = 2;
LABEL_14:
    if ( v15 )
      v15(v11);
    goto LABEL_16;
  }
  v13 = a3 - 1;
  if ( !v13 )
  {
    v15 = *(void (__fastcall **)(WCHAR *))(a1 + 16);
    v12 = 3;
    goto LABEL_14;
  }
  v14 = v13 - 1;
  if ( !v14 )
  {
    v15 = *(void (__fastcall **)(WCHAR *))(a1 + 24);
    v12 = 4;
    goto LABEL_14;
  }
  if ( v14 == 1 )
  {
    v15 = *(void (__fastcall **)(WCHAR *))(a1 + 32);
    v12 = 5;
    goto LABEL_14;
  }
LABEL_16:
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 56));
  if ( *(_BYTE *)(a1 + 48) )
  {
    if ( a2 )
      EventWriteString(*(_QWORD *)(a1 + 40), v12, a2, v11);
  }
  operator delete(v11, v16);
}

```

## disassembly

```asm
0x18007351c  mov     r11, rsp
0x18007351f  mov     [r11+20h], r9
0x180073523  push    rbx
0x180073524  push    rbp
0x180073525  push    rsi
0x180073526  push    rdi
0x180073527  push    r12
0x180073529  push    r14
0x18007352b  push    r15
0x18007352d  sub     rsp, 30h
0x180073531  mov     rax, cs:__security_cookie
0x180073538  xor     rax, rsp
0x18007353b  mov     [rsp+68h+var_40], rax
0x180073540  lea     r12, [r11+28h]
0x180073544  mov     qword ptr [r11-48h], 0
0x18007354c  mov     r14, rdx
0x18007354f  mov     rdi, rcx
0x180073552  mov     rdx, r12; ArgList
0x180073555  mov     rcx, r9; Format
0x180073558  mov     ebx, r8d
0x18007355b  call    _vscwprintf
0x180073560  test    eax, eax
0x180073562  jle     loc_18007363E
0x180073568  inc     eax
0x18007356a  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180073571  movsxd  r15, eax
0x180073574  mov     eax, 2
0x180073579  mul     r15
0x18007357c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180073583  cmovb   rax, rcx
0x180073587  mov     rcx, rax; unsigned __int64
0x18007358a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18007358f  mov     rsi, rax
0x180073592  test    rax, rax
0x180073595  jnz     short loc_1800735A9
0x180073597  xor     r8d, r8d; dwFlags
0x18007359a  xor     edx, edx; pContextRecord
0x18007359c  xor     ecx, ecx; pExceptionRecord
0x18007359e  call    cs:__imp_RaiseFailFastException
0x1800735a4  jmp     loc_18007363E
0x1800735a9  mov     r8, [rsp+68h+Format]; Format
0x1800735b1  mov     r9, r12; ArgList
0x1800735b4  mov     rdx, r15; BufferCount
0x1800735b7  mov     rcx, rsi; Buffer
0x1800735ba  xor     bpl, bpl
0x1800735bd  call    vswprintf_s
0x1800735c2  lea     rcx, [rdi+38h]; lpCriticalSection
0x1800735c6  call    cs:__imp_EnterCriticalSection
0x1800735cc  test    ebx, ebx
0x1800735ce  jz      short loc_1800735FA
0x1800735d0  sub     ebx, 1
0x1800735d3  jz      short loc_1800735F1
0x1800735d5  sub     ebx, 1
0x1800735d8  jz      short loc_1800735E8
0x1800735da  cmp     ebx, 1
0x1800735dd  jnz     short loc_18007360E
0x1800735df  mov     rax, [rdi+20h]
0x1800735e3  mov     bpl, 5
0x1800735e6  jmp     short loc_180073601
0x1800735e8  mov     rax, [rdi+18h]
0x1800735ec  mov     bpl, 4
0x1800735ef  jmp     short loc_180073601
0x1800735f1  mov     rax, [rdi+10h]
0x1800735f5  mov     bpl, 3
0x1800735f8  jmp     short loc_180073601
0x1800735fa  mov     rax, [rdi+8]
0x1800735fe  mov     bpl, 2
0x180073601  test    rax, rax
0x180073604  jz      short loc_18007360E
0x180073606  mov     rcx, rsi
0x180073609  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007360e  lea     rcx, [rdi+38h]; lpCriticalSection
0x180073612  call    cs:__imp_LeaveCriticalSection
0x180073618  cmp     byte ptr [rdi+30h], 0
0x18007361c  jz      short loc_180073636
0x18007361e  test    r14, r14
0x180073621  jz      short loc_180073636
0x180073623  mov     rcx, [rdi+28h]; RegHandle
0x180073627  mov     r9, rsi; String
0x18007362a  mov     r8, r14; Keyword
0x18007362d  mov     dl, bpl; Level
0x180073630  call    cs:__imp_EventWriteString
0x180073636  mov     rcx, rsi; void *
0x180073639  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18007363e  mov     rcx, [rsp+68h+var_40]
0x180073643  xor     rcx, rsp; StackCookie
0x180073646  call    __security_check_cookie
0x18007364b  add     rsp, 30h
0x18007364f  pop     r15
0x180073651  pop     r14
0x180073653  pop     r12
0x180073655  pop     rdi
0x180073656  pop     rsi
0x180073657  pop     rbp
0x180073658  pop     rbx
0x180073659  retn
```
