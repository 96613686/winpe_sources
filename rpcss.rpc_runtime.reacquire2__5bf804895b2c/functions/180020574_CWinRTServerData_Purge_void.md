# CWinRTServerData::Purge(void)

- ea: `0x180020574`
- end: `0x180020729`
- name: `?Purge@CWinRTServerData@@QEAAXXZ`
- size: `437`
- prototype: `void __fastcall(CWinRTServerData *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18001db9c`
- `0x18001f8f0`

## callees

- `0x180020574`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002061e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020656`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002068e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800206fd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002061e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020656`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002068e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800206fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800205ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020637`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002066f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800206de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800205ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020637`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002066f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800206de`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020593`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800205ca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020593`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800205ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020610`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020648`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020680`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800206ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020610`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020648`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020680`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800206ef`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180020714`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180020714`

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
0x180020574  push    rbx
0x180020576  push    rbp
0x180020577  push    rsi
0x180020578  push    rdi
0x180020579  sub     rsp, 28h
0x18002057d  mov     r8, [rcx+20h]; lpMem
0x180020581  mov     rdi, rcx
0x180020584  xor     ebp, ebp
0x180020586  xor     edx, edx; dwFlags
0x180020588  mov     [rcx+18h], rbp
0x18002058c  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180020593  call    cs:__imp_HeapFree
0x18002059a  nop     dword ptr [rax+rax+00h]
0x18002059f  mov     [rdi+20h], rbp
0x1800205a3  mov     [rdi+28h], rbp
0x1800205a7  cmp     [rdi+38h], rbp
0x1800205ab  jz      short loc_1800205D6
0x1800205ad  mov     r8, [rdi+30h]; lpMem
0x1800205b1  lea     rax, asc_180120FB8; "."
0x1800205b8  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800205bf  xor     edx, edx; dwFlags
0x1800205c1  cmp     r8, rax
0x1800205c4  jz      loc_18002070B
0x1800205ca  call    cs:__imp_HeapFree
0x1800205d1  nop     dword ptr [rax+rax+00h]
0x1800205d6  mov     [rdi+70h], rbp
0x1800205da  mov     [rdi+0F1h], bpl
0x1800205e1  mov     [rdi+0F4h], rbp
0x1800205e8  mov     [rdi+0FCh], ebp
0x1800205ee  mov     [rdi+38h], rbp
0x1800205f2  mov     [rdi+30h], rbp
0x1800205f6  mov     rsi, [rdi+40h]
0x1800205fa  test    rsi, rsi
0x1800205fd  jz      short loc_18002062A
0x1800205ff  call    cs:__imp_GetLastError
0x180020606  nop     dword ptr [rax+rax+00h]
0x18002060b  mov     rcx, rsi; string
0x18002060e  mov     ebx, eax
0x180020610  call    cs:__imp_WindowsDeleteString
0x180020617  nop     dword ptr [rax+rax+00h]
0x18002061c  mov     ecx, ebx; dwErrCode
0x18002061e  call    cs:__imp_SetLastError
0x180020625  nop     dword ptr [rax+rax+00h]
0x18002062a  mov     [rdi+40h], rbp
0x18002062e  mov     rsi, [rdi+50h]
0x180020632  test    rsi, rsi
0x180020635  jz      short loc_180020662
0x180020637  call    cs:__imp_GetLastError
0x18002063e  nop     dword ptr [rax+rax+00h]
0x180020643  mov     rcx, rsi; string
0x180020646  mov     ebx, eax
0x180020648  call    cs:__imp_WindowsDeleteString
0x18002064f  nop     dword ptr [rax+rax+00h]
0x180020654  mov     ecx, ebx; dwErrCode
0x180020656  call    cs:__imp_SetLastError
0x18002065d  nop     dword ptr [rax+rax+00h]
0x180020662  mov     [rdi+50h], rbp
0x180020666  mov     rsi, [rdi+58h]
0x18002066a  test    rsi, rsi
0x18002066d  jz      short loc_18002069A
0x18002066f  call    cs:__imp_GetLastError
0x180020676  nop     dword ptr [rax+rax+00h]
0x18002067b  mov     rcx, rsi; string
0x18002067e  mov     ebx, eax
0x180020680  call    cs:__imp_WindowsDeleteString
0x180020687  nop     dword ptr [rax+rax+00h]
0x18002068c  mov     ecx, ebx; dwErrCode
0x18002068e  call    cs:__imp_SetLastError
0x180020695  nop     dword ptr [rax+rax+00h]
0x18002069a  mov     [rdi+58h], rbp
0x18002069e  mov     rsi, [rdi+60h]
0x1800206a2  test    rsi, rsi
0x1800206a5  jnz     short loc_1800206DE
0x1800206a7  mov     [rdi+60h], rbp
0x1800206ab  mov     rcx, [rdi+0E8h]; hMem
0x1800206b2  mov     [rdi+68h], rbp
0x1800206b6  mov     [rdi+7Ch], rbp
0x1800206ba  mov     [rdi+84h], rbp
0x1800206c1  mov     [rdi+90h], rbp
0x1800206c8  test    rcx, rcx
0x1800206cb  jnz     short loc_180020714
0x1800206cd  mov     [rdi+0F0h], bpl
0x1800206d4  add     rsp, 28h
0x1800206d8  pop     rdi
0x1800206d9  pop     rsi
0x1800206da  pop     rbp
0x1800206db  pop     rbx
0x1800206dc  retn
0x1800206de  call    cs:__imp_GetLastError
0x1800206e5  nop     dword ptr [rax+rax+00h]
0x1800206ea  mov     rcx, rsi; string
0x1800206ed  mov     ebx, eax
0x1800206ef  call    cs:__imp_WindowsDeleteString
0x1800206f6  nop     dword ptr [rax+rax+00h]
0x1800206fb  mov     ecx, ebx; dwErrCode
0x1800206fd  call    cs:__imp_SetLastError
0x180020704  nop     dword ptr [rax+rax+00h]
0x180020709  jmp     short loc_1800206A7
0x18002070b  mov     r8, [rdi+38h]
0x18002070f  jmp     loc_1800205CA
0x180020714  call    cs:__imp_LocalFree
0x18002071b  nop     dword ptr [rax+rax+00h]
0x180020720  mov     [rdi+0E8h], rbp
0x180020727  jmp     short loc_1800206CD
```
