# CAppidData::Purge(void)

- ea: `0x180056bd0`
- end: `0x180056d42`
- name: `?Purge@CAppidData@@QEAAXXZ`
- size: `370`
- prototype: `void __fastcall(CAppidData *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180028e94`
- `0x180091620`

## callees

- `0x180056bd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180056c5e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180056c8a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180056cb6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180056ce2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180056c5e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180056c8a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180056cb6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180056ce2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056c4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056c77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056ca3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056ccf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056c4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056c77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056ca3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056ccf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180056be9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180056d1f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180056be9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180056d1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180056c56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180056c82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180056cae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180056cda`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180056c56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180056c82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180056cae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180056cda`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180056d30`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180056d30`

## pseudocode

```c
void __fastcall CAppidData::Purge(CAppidData *this)
{
  void *v2; // rcx
  HSTRING v3; // rsi
  DWORD LastError; // ebx
  HSTRING v5; // rsi
  DWORD v6; // ebx
  HSTRING v7; // rsi
  DWORD v8; // ebx
  HSTRING v9; // rsi
  DWORD v10; // ebx
  wchar_t *v11; // r8

  HeapFree(g_hHeap, 0, *((LPVOID *)this + 2));
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 6) = 0;
  if ( *((_QWORD *)this + 4) )
  {
    v11 = (wchar_t *)*((_QWORD *)this + 5);
    if ( v11 == L"." )
      v11 = (wchar_t *)*((_QWORD *)this + 4);
    HeapFree(g_hHeap, 0, v11);
  }
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *(_QWORD *)((char *)this + 60) = 0;
  *(_QWORD *)((char *)this + 68) = 0;
  *((_DWORD *)this + 19) = -1;
  *((_OWORD *)this + 5) = 0;
  v2 = (void *)*((_QWORD *)this + 29);
  *((_DWORD *)this + 14) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_DWORD *)this + 24) = 0;
  if ( v2 )
  {
    LocalFree(v2);
    *((_QWORD *)this + 29) = 0;
  }
  v3 = (HSTRING)*((_QWORD *)this + 30);
  if ( v3 )
  {
    LastError = GetLastError();
    WindowsDeleteString(v3);
    SetLastError(LastError);
  }
  *((_QWORD *)this + 30) = 0;
  v5 = (HSTRING)*((_QWORD *)this + 31);
  if ( v5 )
  {
    v6 = GetLastError();
    WindowsDeleteString(v5);
    SetLastError(v6);
  }
  *((_QWORD *)this + 31) = 0;
  v7 = (HSTRING)*((_QWORD *)this + 34);
  if ( v7 )
  {
    v8 = GetLastError();
    WindowsDeleteString(v7);
    SetLastError(v8);
  }
  *((_QWORD *)this + 34) = 0;
  v9 = (HSTRING)*((_QWORD *)this + 35);
  if ( v9 )
  {
    v10 = GetLastError();
    WindowsDeleteString(v9);
    SetLastError(v10);
  }
  *((_QWORD *)this + 35) = 0;
  *((_WORD *)this + 152) = 0;
  *((_BYTE *)this + 306) = 0;
}

```

## disassembly

```asm
0x180056bd0  push    rbx
0x180056bd2  push    rbp
0x180056bd3  push    rsi
0x180056bd4  push    rdi
0x180056bd5  sub     rsp, 28h
0x180056bd9  mov     r8, [rcx+10h]; lpMem
0x180056bdd  mov     rdi, rcx
0x180056be0  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180056be7  xor     edx, edx; dwFlags
0x180056be9  call    cs:__imp_HeapFree
0x180056bef  xor     ebp, ebp
0x180056bf1  mov     [rdi+10h], rbp
0x180056bf5  mov     [rdi+18h], rbp
0x180056bf9  mov     [rdi+30h], rbp
0x180056bfd  cmp     [rdi+20h], rbp
0x180056c01  jnz     loc_180056D06
0x180056c07  xorps   xmm0, xmm0
0x180056c0a  mov     [rdi+20h], rbp
0x180056c0e  mov     [rdi+28h], rbp
0x180056c12  mov     [rdi+3Ch], rbp
0x180056c16  mov     [rdi+44h], rbp
0x180056c1a  mov     dword ptr [rdi+4Ch], 0FFFFFFFFh
0x180056c21  movups  xmmword ptr [rdi+50h], xmm0
0x180056c25  mov     rcx, [rdi+0E8h]; hMem
0x180056c2c  mov     [rdi+38h], ebp
0x180056c2f  mov     [rdi+68h], rbp
0x180056c33  mov     [rdi+60h], ebp
0x180056c36  test    rcx, rcx
0x180056c39  jnz     loc_180056D30
0x180056c3f  mov     rsi, [rdi+0F0h]
0x180056c46  test    rsi, rsi
0x180056c49  jz      short loc_180056C64
0x180056c4b  call    cs:__imp_GetLastError
0x180056c51  mov     rcx, rsi; string
0x180056c54  mov     ebx, eax
0x180056c56  call    cs:__imp_WindowsDeleteString
0x180056c5c  mov     ecx, ebx; dwErrCode
0x180056c5e  call    cs:__imp_SetLastError
0x180056c64  mov     [rdi+0F0h], rbp
0x180056c6b  mov     rsi, [rdi+0F8h]
0x180056c72  test    rsi, rsi
0x180056c75  jz      short loc_180056C90
0x180056c77  call    cs:__imp_GetLastError
0x180056c7d  mov     rcx, rsi; string
0x180056c80  mov     ebx, eax
0x180056c82  call    cs:__imp_WindowsDeleteString
0x180056c88  mov     ecx, ebx; dwErrCode
0x180056c8a  call    cs:__imp_SetLastError
0x180056c90  mov     [rdi+0F8h], rbp
0x180056c97  mov     rsi, [rdi+110h]
0x180056c9e  test    rsi, rsi
0x180056ca1  jz      short loc_180056CBC
0x180056ca3  call    cs:__imp_GetLastError
0x180056ca9  mov     rcx, rsi; string
0x180056cac  mov     ebx, eax
0x180056cae  call    cs:__imp_WindowsDeleteString
0x180056cb4  mov     ecx, ebx; dwErrCode
0x180056cb6  call    cs:__imp_SetLastError
0x180056cbc  mov     [rdi+110h], rbp
0x180056cc3  mov     rsi, [rdi+118h]
0x180056cca  test    rsi, rsi
0x180056ccd  jz      short loc_180056CE8
0x180056ccf  call    cs:__imp_GetLastError
0x180056cd5  mov     rcx, rsi; string
0x180056cd8  mov     ebx, eax
0x180056cda  call    cs:__imp_WindowsDeleteString
0x180056ce0  mov     ecx, ebx; dwErrCode
0x180056ce2  call    cs:__imp_SetLastError
0x180056ce8  mov     [rdi+118h], rbp
0x180056cef  mov     [rdi+130h], bp
0x180056cf6  mov     [rdi+132h], bpl
0x180056cfd  add     rsp, 28h
0x180056d01  pop     rdi
0x180056d02  pop     rsi
0x180056d03  pop     rbp
0x180056d04  pop     rbx
0x180056d05  retn
0x180056d06  mov     r8, [rdi+28h]; lpMem
0x180056d0a  lea     rax, asc_180118818; "."
0x180056d11  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180056d18  xor     edx, edx; dwFlags
0x180056d1a  cmp     r8, rax
0x180056d1d  jz      short loc_180056D2A
0x180056d1f  call    cs:__imp_HeapFree
0x180056d25  jmp     loc_180056C07
0x180056d2a  mov     r8, [rdi+20h]
0x180056d2e  jmp     short loc_180056D1F
0x180056d30  call    cs:__imp_LocalFree
0x180056d36  mov     [rdi+0E8h], rbp
0x180056d3d  jmp     loc_180056C3F
```
