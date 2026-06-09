# CAppidData::Purge(void)

- ea: `0x18005c154`
- end: `0x18005c321`
- name: `?Purge@CAppidData@@QEAAXXZ`
- size: `461`
- prototype: `void __fastcall(CAppidData *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18001d3a0`
- `0x18009280c`

## callees

- `0x18005c154`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005c1f4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005c232`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005c270`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005c2ae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005c1f4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005c232`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005c270`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005c2ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c1d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c213`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c251`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c28f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c1d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c213`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c251`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c28f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005c16d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005c2f2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005c16d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005c2f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c1e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c224`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c262`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c2a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c1e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c224`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c262`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c2a0`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18005c309`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18005c309`

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
0x18005c154  push    rbx
0x18005c156  push    rbp
0x18005c157  push    rsi
0x18005c158  push    rdi
0x18005c159  sub     rsp, 28h
0x18005c15d  mov     r8, [rcx+10h]; lpMem
0x18005c161  mov     rdi, rcx
0x18005c164  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18005c16b  xor     edx, edx; dwFlags
0x18005c16d  call    cs:__imp_HeapFree
0x18005c174  nop     dword ptr [rax+rax+00h]
0x18005c179  xor     ebp, ebp
0x18005c17b  mov     [rdi+10h], rbp
0x18005c17f  mov     [rdi+18h], rbp
0x18005c183  mov     [rdi+30h], rbp
0x18005c187  cmp     [rdi+20h], rbp
0x18005c18b  jnz     loc_18005C2D9
0x18005c191  xorps   xmm0, xmm0
0x18005c194  mov     [rdi+20h], rbp
0x18005c198  mov     [rdi+28h], rbp
0x18005c19c  mov     [rdi+3Ch], rbp
0x18005c1a0  mov     [rdi+44h], rbp
0x18005c1a4  mov     dword ptr [rdi+4Ch], 0FFFFFFFFh
0x18005c1ab  movups  xmmword ptr [rdi+50h], xmm0
0x18005c1af  mov     rcx, [rdi+0E8h]; hMem
0x18005c1b6  mov     [rdi+38h], ebp
0x18005c1b9  mov     [rdi+68h], rbp
0x18005c1bd  mov     [rdi+60h], ebp
0x18005c1c0  test    rcx, rcx
0x18005c1c3  jnz     loc_18005C309
0x18005c1c9  mov     rsi, [rdi+0F0h]
0x18005c1d0  test    rsi, rsi
0x18005c1d3  jz      short loc_18005C200
0x18005c1d5  call    cs:__imp_GetLastError
0x18005c1dc  nop     dword ptr [rax+rax+00h]
0x18005c1e1  mov     rcx, rsi; string
0x18005c1e4  mov     ebx, eax
0x18005c1e6  call    cs:__imp_WindowsDeleteString
0x18005c1ed  nop     dword ptr [rax+rax+00h]
0x18005c1f2  mov     ecx, ebx; dwErrCode
0x18005c1f4  call    cs:__imp_SetLastError
0x18005c1fb  nop     dword ptr [rax+rax+00h]
0x18005c200  mov     [rdi+0F0h], rbp
0x18005c207  mov     rsi, [rdi+0F8h]
0x18005c20e  test    rsi, rsi
0x18005c211  jz      short loc_18005C23E
0x18005c213  call    cs:__imp_GetLastError
0x18005c21a  nop     dword ptr [rax+rax+00h]
0x18005c21f  mov     rcx, rsi; string
0x18005c222  mov     ebx, eax
0x18005c224  call    cs:__imp_WindowsDeleteString
0x18005c22b  nop     dword ptr [rax+rax+00h]
0x18005c230  mov     ecx, ebx; dwErrCode
0x18005c232  call    cs:__imp_SetLastError
0x18005c239  nop     dword ptr [rax+rax+00h]
0x18005c23e  mov     [rdi+0F8h], rbp
0x18005c245  mov     rsi, [rdi+110h]
0x18005c24c  test    rsi, rsi
0x18005c24f  jz      short loc_18005C27C
0x18005c251  call    cs:__imp_GetLastError
0x18005c258  nop     dword ptr [rax+rax+00h]
0x18005c25d  mov     rcx, rsi; string
0x18005c260  mov     ebx, eax
0x18005c262  call    cs:__imp_WindowsDeleteString
0x18005c269  nop     dword ptr [rax+rax+00h]
0x18005c26e  mov     ecx, ebx; dwErrCode
0x18005c270  call    cs:__imp_SetLastError
0x18005c277  nop     dword ptr [rax+rax+00h]
0x18005c27c  mov     [rdi+110h], rbp
0x18005c283  mov     rsi, [rdi+118h]
0x18005c28a  test    rsi, rsi
0x18005c28d  jz      short loc_18005C2BA
0x18005c28f  call    cs:__imp_GetLastError
0x18005c296  nop     dword ptr [rax+rax+00h]
0x18005c29b  mov     rcx, rsi; string
0x18005c29e  mov     ebx, eax
0x18005c2a0  call    cs:__imp_WindowsDeleteString
0x18005c2a7  nop     dword ptr [rax+rax+00h]
0x18005c2ac  mov     ecx, ebx; dwErrCode
0x18005c2ae  call    cs:__imp_SetLastError
0x18005c2b5  nop     dword ptr [rax+rax+00h]
0x18005c2ba  mov     [rdi+118h], rbp
0x18005c2c1  mov     [rdi+130h], bp
0x18005c2c8  mov     [rdi+132h], bpl
0x18005c2cf  add     rsp, 28h
0x18005c2d3  pop     rdi
0x18005c2d4  pop     rsi
0x18005c2d5  pop     rbp
0x18005c2d6  pop     rbx
0x18005c2d7  retn
0x18005c2d9  mov     r8, [rdi+28h]; lpMem
0x18005c2dd  lea     rax, asc_180120FB8; "."
0x18005c2e4  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18005c2eb  xor     edx, edx; dwFlags
0x18005c2ed  cmp     r8, rax
0x18005c2f0  jz      short loc_18005C303
0x18005c2f2  call    cs:__imp_HeapFree
0x18005c2f9  nop     dword ptr [rax+rax+00h]
0x18005c2fe  jmp     loc_18005C191
0x18005c303  mov     r8, [rdi+20h]
0x18005c307  jmp     short loc_18005C2F2
0x18005c309  call    cs:__imp_LocalFree
0x18005c310  nop     dword ptr [rax+rax+00h]
0x18005c315  mov     [rdi+0E8h], rbp
0x18005c31c  jmp     loc_18005C1C9
```
