# CClassData::Purge(void)

- ea: `0x180028f90`
- end: `0x180029101`
- name: `?Purge@CClassData@@QEAAXXZ`
- size: `369`
- prototype: `void __fastcall(CClassData *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18002eaec`
- `0x180060644`

## callees

- `0x180028e94`
- `0x180028f90`
- `0x1800297e0`
- `0x18002af3c`
- `0x1800b2bb0`
- `0x1800b3bac`
- `0x18010b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180028ff5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180029021`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180028ff5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180029021`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028fe2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002900e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028fe2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002900e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028fed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029019`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002907a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029089`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029098`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800290a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028fed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029019`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002907a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029089`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029098`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800290a7`
- `ext-ms-win-advapi32-safer-l1-1-0!SaferCloseLevel` at `0x1800290f2`
- `ext-ms-win-advapi32-safer-l1-1-0!SaferCloseLevel` at `0x1800290f2`

## pseudocode

```c
void __fastcall CClassData::Purge(CClassData *this, __int64 a2, __int64 a3)
{
  void *v3; // rbx
  __int64 v5; // rbx
  HSTRING v6; // rsi
  DWORD LastError; // ebx
  HSTRING v8; // rsi
  DWORD v9; // ebx
  __int64 v10; // rcx
  HSTRING v11; // rcx
  HSTRING v12; // rcx
  HSTRING v13; // rcx
  HSTRING v14; // rcx

  v3 = (void *)*((_QWORD *)this + 11);
  if ( v3 )
  {
    CAppidData::~CAppidData(*((CAppidData **)this + 11));
    operator delete(v3, 0x138u);
    *((_QWORD *)this + 11) = 0;
  }
  v5 = *((_QWORD *)this + 12);
  if ( v5 )
  {
    CWinRTServerData::Purge(*((CWinRTServerData **)this + 12));
    if ( *(_QWORD *)v5 )
    {
      CToken::Release(*(CToken **)v5);
      *(_QWORD *)v5 = 0;
    }
    v10 = *(_QWORD *)(v5 + 16);
    *(_QWORD *)(v5 + 8) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    v11 = *(HSTRING *)(v5 + 96);
    if ( v11 )
      WindowsDeleteString(v11);
    v12 = *(HSTRING *)(v5 + 88);
    if ( v12 )
      WindowsDeleteString(v12);
    v13 = *(HSTRING *)(v5 + 80);
    if ( v13 )
      WindowsDeleteString(v13);
    v14 = *(HSTRING *)(v5 + 64);
    if ( v14 )
      WindowsDeleteString(v14);
    operator delete((void *)v5, 0x108u);
    *((_QWORD *)this + 12) = 0;
  }
  *((_BYTE *)this + 80) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  if ( *((_QWORD *)this + 7) && (unsigned __int8)IsSaferCloseLevelPresent(this, a2, a3) )
  {
    SaferCloseLevel(*((SAFER_LEVEL_HANDLE *)this + 7));
    *((_QWORD *)this + 7) = 0;
  }
  v6 = (HSTRING)*((_QWORD *)this + 17);
  if ( v6 )
  {
    LastError = GetLastError();
    WindowsDeleteString(v6);
    SetLastError(LastError);
  }
  *((_QWORD *)this + 17) = 0;
  v8 = (HSTRING)*((_QWORD *)this + 20);
  if ( v8 )
  {
    v9 = GetLastError();
    WindowsDeleteString(v8);
    SetLastError(v9);
  }
  *((_QWORD *)this + 20) = 0;
  *((_WORD *)this + 86) = 0;
  *((_QWORD *)this + 22) = 0;
}

```

## disassembly

```asm
0x180028f90  push    rbx
0x180028f92  push    rbp
0x180028f93  push    rsi
0x180028f94  push    rdi
0x180028f95  sub     rsp, 28h
0x180028f99  mov     rbx, [rcx+58h]
0x180028f9d  xor     ebp, ebp
0x180028f9f  mov     rdi, rcx
0x180028fa2  test    rbx, rbx
0x180028fa5  jnz     loc_1800290C3
0x180028fab  mov     rbx, [rdi+60h]
0x180028faf  test    rbx, rbx
0x180028fb2  jnz     loc_180029045
0x180028fb8  mov     [rdi+50h], bpl
0x180028fbc  mov     [rdi+10h], rbp
0x180028fc0  mov     [rdi+28h], rbp
0x180028fc4  mov     [rdi+18h], rbp
0x180028fc8  mov     [rdi+20h], rbp
0x180028fcc  cmp     [rdi+38h], rbp
0x180028fd0  jnz     loc_1800290E1
0x180028fd6  mov     rsi, [rdi+88h]
0x180028fdd  test    rsi, rsi
0x180028fe0  jz      short loc_180028FFB
0x180028fe2  call    cs:__imp_GetLastError
0x180028fe8  mov     rcx, rsi; string
0x180028feb  mov     ebx, eax
0x180028fed  call    cs:__imp_WindowsDeleteString
0x180028ff3  mov     ecx, ebx; dwErrCode
0x180028ff5  call    cs:__imp_SetLastError
0x180028ffb  mov     [rdi+88h], rbp
0x180029002  mov     rsi, [rdi+0A0h]
0x180029009  test    rsi, rsi
0x18002900c  jz      short loc_180029027
0x18002900e  call    cs:__imp_GetLastError
0x180029014  mov     rcx, rsi; string
0x180029017  mov     ebx, eax
0x180029019  call    cs:__imp_WindowsDeleteString
0x18002901f  mov     ecx, ebx; dwErrCode
0x180029021  call    cs:__imp_SetLastError
0x180029027  mov     [rdi+0A0h], rbp
0x18002902e  mov     [rdi+0ACh], bp
0x180029035  mov     [rdi+0B0h], rbp
0x18002903c  add     rsp, 28h
0x180029040  pop     rdi
0x180029041  pop     rsi
0x180029042  pop     rbp
0x180029043  pop     rbx
0x180029044  retn
0x180029045  mov     rcx, rbx; this
0x180029048  call    ?Purge@CWinRTServerData@@QEAAXXZ; CWinRTServerData::Purge(void)
0x18002904d  mov     rcx, [rbx]; this
0x180029050  test    rcx, rcx
0x180029053  jz      short loc_18002905D
0x180029055  call    ?Release@CToken@@UEAAKXZ; CToken::Release(void)
0x18002905a  mov     [rbx], rbp
0x18002905d  mov     rcx, [rbx+10h]
0x180029061  mov     [rbx+8], rbp
0x180029065  mov     rax, [rcx]
0x180029068  mov     rax, [rax+10h]
0x18002906c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029071  mov     rcx, [rbx+60h]; string
0x180029075  test    rcx, rcx
0x180029078  jz      short loc_180029080
0x18002907a  call    cs:__imp_WindowsDeleteString
0x180029080  mov     rcx, [rbx+58h]; string
0x180029084  test    rcx, rcx
0x180029087  jz      short loc_18002908F
0x180029089  call    cs:__imp_WindowsDeleteString
0x18002908f  mov     rcx, [rbx+50h]; string
0x180029093  test    rcx, rcx
0x180029096  jz      short loc_18002909E
0x180029098  call    cs:__imp_WindowsDeleteString
0x18002909e  mov     rcx, [rbx+40h]; string
0x1800290a2  test    rcx, rcx
0x1800290a5  jz      short loc_1800290AD
0x1800290a7  call    cs:__imp_WindowsDeleteString
0x1800290ad  mov     edx, 108h; unsigned __int64
0x1800290b2  mov     rcx, rbx; void *
0x1800290b5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800290ba  mov     [rdi+60h], rbp
0x1800290be  jmp     loc_180028FB8
0x1800290c3  mov     rcx, rbx; this
0x1800290c6  call    ??1CAppidData@@QEAA@XZ; CAppidData::~CAppidData(void)
0x1800290cb  mov     edx, 138h; unsigned __int64
0x1800290d0  mov     rcx, rbx; void *
0x1800290d3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800290d8  mov     [rdi+58h], rbp
0x1800290dc  jmp     loc_180028FAB
0x1800290e1  call    IsSaferCloseLevelPresent
0x1800290e6  test    al, al
0x1800290e8  jz      loc_180028FD6
0x1800290ee  mov     rcx, [rdi+38h]; hLevelHandle
0x1800290f2  call    cs:__imp_SaferCloseLevel
0x1800290f8  mov     [rdi+38h], rbp
0x1800290fc  jmp     loc_180028FD6
```
