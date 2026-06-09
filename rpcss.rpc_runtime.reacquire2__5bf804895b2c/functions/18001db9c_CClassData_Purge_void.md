# CClassData::Purge(void)

- ea: `0x18001db9c`
- end: `0x18001dd50`
- name: `?Purge@CClassData@@QEAAXXZ`
- size: `436`
- prototype: `void __fastcall(CClassData *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180024358`
- `0x180065988`

## callees

- `0x18001d3a0`
- `0x18001db9c`
- `0x18001ecf0`
- `0x180020574`
- `0x1800b7e90`
- `0x1800b8eac`
- `0x180114010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001dc0d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001dc4b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001dc0d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001dc4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dbee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dc2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dbee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dc2c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001dbff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001dc3d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001dcab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001dcc0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001dcd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001dcea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001dbff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001dc3d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001dcab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001dcc0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001dcd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001dcea`
- `ext-ms-win-advapi32-safer-l1-1-0!SaferCloseLevel` at `0x18001dd3b`
- `ext-ms-win-advapi32-safer-l1-1-0!SaferCloseLevel` at `0x18001dd3b`

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
0x18001db9c  push    rbx
0x18001db9e  push    rbp
0x18001db9f  push    rsi
0x18001dba0  push    rdi
0x18001dba1  sub     rsp, 28h
0x18001dba5  mov     rbx, [rcx+58h]
0x18001dba9  xor     ebp, ebp
0x18001dbab  mov     rdi, rcx
0x18001dbae  test    rbx, rbx
0x18001dbb1  jnz     loc_18001DD0C
0x18001dbb7  mov     rbx, [rdi+60h]
0x18001dbbb  test    rbx, rbx
0x18001dbbe  jnz     loc_18001DC76
0x18001dbc4  mov     [rdi+50h], bpl
0x18001dbc8  mov     [rdi+10h], rbp
0x18001dbcc  mov     [rdi+28h], rbp
0x18001dbd0  mov     [rdi+18h], rbp
0x18001dbd4  mov     [rdi+20h], rbp
0x18001dbd8  cmp     [rdi+38h], rbp
0x18001dbdc  jnz     loc_18001DD2A
0x18001dbe2  mov     rsi, [rdi+88h]
0x18001dbe9  test    rsi, rsi
0x18001dbec  jz      short loc_18001DC19
0x18001dbee  call    cs:__imp_GetLastError
0x18001dbf5  nop     dword ptr [rax+rax+00h]
0x18001dbfa  mov     rcx, rsi; string
0x18001dbfd  mov     ebx, eax
0x18001dbff  call    cs:__imp_WindowsDeleteString
0x18001dc06  nop     dword ptr [rax+rax+00h]
0x18001dc0b  mov     ecx, ebx; dwErrCode
0x18001dc0d  call    cs:__imp_SetLastError
0x18001dc14  nop     dword ptr [rax+rax+00h]
0x18001dc19  mov     [rdi+88h], rbp
0x18001dc20  mov     rsi, [rdi+0A0h]
0x18001dc27  test    rsi, rsi
0x18001dc2a  jz      short loc_18001DC57
0x18001dc2c  call    cs:__imp_GetLastError
0x18001dc33  nop     dword ptr [rax+rax+00h]
0x18001dc38  mov     rcx, rsi; string
0x18001dc3b  mov     ebx, eax
0x18001dc3d  call    cs:__imp_WindowsDeleteString
0x18001dc44  nop     dword ptr [rax+rax+00h]
0x18001dc49  mov     ecx, ebx; dwErrCode
0x18001dc4b  call    cs:__imp_SetLastError
0x18001dc52  nop     dword ptr [rax+rax+00h]
0x18001dc57  mov     [rdi+0A0h], rbp
0x18001dc5e  mov     [rdi+0ACh], bp
0x18001dc65  mov     [rdi+0B0h], rbp
0x18001dc6c  add     rsp, 28h
0x18001dc70  pop     rdi
0x18001dc71  pop     rsi
0x18001dc72  pop     rbp
0x18001dc73  pop     rbx
0x18001dc74  retn
0x18001dc76  mov     rcx, rbx; this
0x18001dc79  call    ?Purge@CWinRTServerData@@QEAAXXZ; CWinRTServerData::Purge(void)
0x18001dc7e  mov     rcx, [rbx]; this
0x18001dc81  test    rcx, rcx
0x18001dc84  jz      short loc_18001DC8E
0x18001dc86  call    ?Release@CToken@@UEAAKXZ; CToken::Release(void)
0x18001dc8b  mov     [rbx], rbp
0x18001dc8e  mov     rcx, [rbx+10h]
0x18001dc92  mov     [rbx+8], rbp
0x18001dc96  mov     rax, [rcx]
0x18001dc99  mov     rax, [rax+10h]
0x18001dc9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dca2  mov     rcx, [rbx+60h]; string
0x18001dca6  test    rcx, rcx
0x18001dca9  jz      short loc_18001DCB7
0x18001dcab  call    cs:__imp_WindowsDeleteString
0x18001dcb2  nop     dword ptr [rax+rax+00h]
0x18001dcb7  mov     rcx, [rbx+58h]; string
0x18001dcbb  test    rcx, rcx
0x18001dcbe  jz      short loc_18001DCCC
0x18001dcc0  call    cs:__imp_WindowsDeleteString
0x18001dcc7  nop     dword ptr [rax+rax+00h]
0x18001dccc  mov     rcx, [rbx+50h]; string
0x18001dcd0  test    rcx, rcx
0x18001dcd3  jz      short loc_18001DCE1
0x18001dcd5  call    cs:__imp_WindowsDeleteString
0x18001dcdc  nop     dword ptr [rax+rax+00h]
0x18001dce1  mov     rcx, [rbx+40h]; string
0x18001dce5  test    rcx, rcx
0x18001dce8  jz      short loc_18001DCF6
0x18001dcea  call    cs:__imp_WindowsDeleteString
0x18001dcf1  nop     dword ptr [rax+rax+00h]
0x18001dcf6  mov     edx, 108h; unsigned __int64
0x18001dcfb  mov     rcx, rbx; void *
0x18001dcfe  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001dd03  mov     [rdi+60h], rbp
0x18001dd07  jmp     loc_18001DBC4
0x18001dd0c  mov     rcx, rbx; this
0x18001dd0f  call    ??1CAppidData@@QEAA@XZ; CAppidData::~CAppidData(void)
0x18001dd14  mov     edx, 138h; unsigned __int64
0x18001dd19  mov     rcx, rbx; void *
0x18001dd1c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001dd21  mov     [rdi+58h], rbp
0x18001dd25  jmp     loc_18001DBB7
0x18001dd2a  call    IsSaferCloseLevelPresent
0x18001dd2f  test    al, al
0x18001dd31  jz      loc_18001DBE2
0x18001dd37  mov     rcx, [rdi+38h]; hLevelHandle
0x18001dd3b  call    cs:__imp_SaferCloseLevel
0x18001dd42  nop     dword ptr [rax+rax+00h]
0x18001dd47  mov     [rdi+38h], rbp
0x18001dd4b  jmp     loc_18001DBE2
```
