# CWinRTServerData::Purge(void)

- ea: `0x18002af3c`
- end: `0x18002b096`
- name: `?Purge@CWinRTServerData@@QEAAXXZ`
- size: `346`
- prototype: `void __fastcall(CWinRTServerData *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180028f90`
- `0x18002a310`

## callees

- `0x18002af3c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002afce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002aff4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b01a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b076`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002afce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002aff4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b01a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b076`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002afbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002afe1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b007`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b063`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002afbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002afe1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b007`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b063`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002af5b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002af8c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002af5b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002af8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002afc6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002afec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b012`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b06e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002afc6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002afec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b012`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b06e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18002b087`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18002b087`

## pseudocode

```c
void __fastcall CWinRTServerData::Purge(CWinRTServerData *this)
{
  void *v1; // r8
  wchar_t *v3; // r8
  HSTRING v4; // rsi
  DWORD LastError; // ebx
  HSTRING v6; // rsi
  DWORD v7; // ebx
  HSTRING v8; // rsi
  DWORD v9; // ebx
  HSTRING v10; // rsi
  void *v11; // rcx
  DWORD v12; // ebx

  v1 = (void *)*((_QWORD *)this + 4);
  *((_QWORD *)this + 3) = 0;
  HeapFree(g_hHeap, 0, v1);
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  if ( *((_QWORD *)this + 7) )
  {
    v3 = (wchar_t *)*((_QWORD *)this + 6);
    if ( v3 == L"." )
      v3 = (wchar_t *)*((_QWORD *)this + 7);
    HeapFree(g_hHeap, 0, v3);
  }
  *((_QWORD *)this + 14) = 0;
  *((_BYTE *)this + 241) = 0;
  *(_QWORD *)((char *)this + 244) = 0;
  *((_DWORD *)this + 63) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 6) = 0;
  v4 = (HSTRING)*((_QWORD *)this + 8);
  if ( v4 )
  {
    LastError = GetLastError();
    WindowsDeleteString(v4);
    SetLastError(LastError);
  }
  *((_QWORD *)this + 8) = 0;
  v6 = (HSTRING)*((_QWORD *)this + 10);
  if ( v6 )
  {
    v7 = GetLastError();
    WindowsDeleteString(v6);
    SetLastError(v7);
  }
  *((_QWORD *)this + 10) = 0;
  v8 = (HSTRING)*((_QWORD *)this + 11);
  if ( v8 )
  {
    v9 = GetLastError();
    WindowsDeleteString(v8);
    SetLastError(v9);
  }
  *((_QWORD *)this + 11) = 0;
  v10 = (HSTRING)*((_QWORD *)this + 12);
  if ( v10 )
  {
    v12 = GetLastError();
    WindowsDeleteString(v10);
    SetLastError(v12);
  }
  *((_QWORD *)this + 12) = 0;
  v11 = (void *)*((_QWORD *)this + 29);
  *((_QWORD *)this + 13) = 0;
  *(_QWORD *)((char *)this + 124) = 0;
  *(_QWORD *)((char *)this + 132) = 0;
  *((_QWORD *)this + 18) = 0;
  if ( v11 )
  {
    LocalFree(v11);
    *((_QWORD *)this + 29) = 0;
  }
  *((_BYTE *)this + 240) = 0;
}

```

## disassembly

```asm
0x18002af3c  push    rbx
0x18002af3e  push    rbp
0x18002af3f  push    rsi
0x18002af40  push    rdi
0x18002af41  sub     rsp, 28h
0x18002af45  mov     r8, [rcx+20h]; lpMem
0x18002af49  mov     rdi, rcx
0x18002af4c  xor     ebp, ebp
0x18002af4e  xor     edx, edx; dwFlags
0x18002af50  mov     [rcx+18h], rbp
0x18002af54  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18002af5b  call    cs:__imp_HeapFree
0x18002af61  mov     [rdi+20h], rbp
0x18002af65  mov     [rdi+28h], rbp
0x18002af69  cmp     [rdi+38h], rbp
0x18002af6d  jz      short loc_18002AF92
0x18002af6f  mov     r8, [rdi+30h]; lpMem
0x18002af73  lea     rax, asc_180118818; "."
0x18002af7a  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18002af81  xor     edx, edx; dwFlags
0x18002af83  cmp     r8, rax
0x18002af86  jz      loc_18002B07E
0x18002af8c  call    cs:__imp_HeapFree
0x18002af92  mov     [rdi+70h], rbp
0x18002af96  mov     [rdi+0F1h], bpl
0x18002af9d  mov     [rdi+0F4h], rbp
0x18002afa4  mov     [rdi+0FCh], ebp
0x18002afaa  mov     [rdi+38h], rbp
0x18002afae  mov     [rdi+30h], rbp
0x18002afb2  mov     rsi, [rdi+40h]
0x18002afb6  test    rsi, rsi
0x18002afb9  jz      short loc_18002AFD4
0x18002afbb  call    cs:__imp_GetLastError
0x18002afc1  mov     rcx, rsi; string
0x18002afc4  mov     ebx, eax
0x18002afc6  call    cs:__imp_WindowsDeleteString
0x18002afcc  mov     ecx, ebx; dwErrCode
0x18002afce  call    cs:__imp_SetLastError
0x18002afd4  mov     [rdi+40h], rbp
0x18002afd8  mov     rsi, [rdi+50h]
0x18002afdc  test    rsi, rsi
0x18002afdf  jz      short loc_18002AFFA
0x18002afe1  call    cs:__imp_GetLastError
0x18002afe7  mov     rcx, rsi; string
0x18002afea  mov     ebx, eax
0x18002afec  call    cs:__imp_WindowsDeleteString
0x18002aff2  mov     ecx, ebx; dwErrCode
0x18002aff4  call    cs:__imp_SetLastError
0x18002affa  mov     [rdi+50h], rbp
0x18002affe  mov     rsi, [rdi+58h]
0x18002b002  test    rsi, rsi
0x18002b005  jz      short loc_18002B020
0x18002b007  call    cs:__imp_GetLastError
0x18002b00d  mov     rcx, rsi; string
0x18002b010  mov     ebx, eax
0x18002b012  call    cs:__imp_WindowsDeleteString
0x18002b018  mov     ecx, ebx; dwErrCode
0x18002b01a  call    cs:__imp_SetLastError
0x18002b020  mov     [rdi+58h], rbp
0x18002b024  mov     rsi, [rdi+60h]
0x18002b028  test    rsi, rsi
0x18002b02b  jnz     short loc_18002B063
0x18002b02d  mov     [rdi+60h], rbp
0x18002b031  mov     rcx, [rdi+0E8h]; hMem
0x18002b038  mov     [rdi+68h], rbp
0x18002b03c  mov     [rdi+7Ch], rbp
0x18002b040  mov     [rdi+84h], rbp
0x18002b047  mov     [rdi+90h], rbp
0x18002b04e  test    rcx, rcx
0x18002b051  jnz     short loc_18002B087
0x18002b053  mov     [rdi+0F0h], bpl
0x18002b05a  add     rsp, 28h
0x18002b05e  pop     rdi
0x18002b05f  pop     rsi
0x18002b060  pop     rbp
0x18002b061  pop     rbx
0x18002b062  retn
0x18002b063  call    cs:__imp_GetLastError
0x18002b069  mov     rcx, rsi; string
0x18002b06c  mov     ebx, eax
0x18002b06e  call    cs:__imp_WindowsDeleteString
0x18002b074  mov     ecx, ebx; dwErrCode
0x18002b076  call    cs:__imp_SetLastError
0x18002b07c  jmp     short loc_18002B02D
0x18002b07e  mov     r8, [rdi+38h]
0x18002b082  jmp     loc_18002AF8C
0x18002b087  call    cs:__imp_LocalFree
0x18002b08d  mov     [rdi+0E8h], rbp
0x18002b094  jmp     short loc_18002B053
```
