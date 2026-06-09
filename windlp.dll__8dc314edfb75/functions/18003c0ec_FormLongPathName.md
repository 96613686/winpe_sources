# FormLongPathName

- ea: `0x18003c0ec`
- end: `0x18003c1f6`
- name: `FormLongPathName`
- size: `266`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180038c34`
- `0x18003abd0`
- `0x18003db20`

## callees

- `0x18003c0ec`
- `0x18003c464`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x18003c126`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x18003c162`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x18003c126`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x18003c162`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003c137`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003c1b1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003c137`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003c1b1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003c148`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003c148`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003c1bf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003c1bf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c1d3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c1e3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c1d3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c1e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c16c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c18a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c1c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c16c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c18a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c1c9`

## pseudocode

```c
const WCHAR *__fastcall FormLongPathName(const wchar_t *a1)
{
  const WCHAR *v1; // rax
  const WCHAR *v2; // rbp
  DWORD LongPathNameW; // edi
  HANDLE ProcessHeap; // rax
  WCHAR *v5; // rax
  WCHAR *v6; // rsi
  DWORD v7; // r14d
  WCHAR *v8; // rax
  const WCHAR *v9; // rbx
  DWORD LastError; // edi
  WCHAR *v11; // rsi
  HANDLE v12; // rax

  if ( a1 && *a1 )
  {
    v1 = (const WCHAR *)PrepareUnicodePathEx(a1);
    v2 = v1;
    if ( !v1 )
    {
      v9 = 0;
      LastError = GetLastError();
LABEL_20:
      SetLastError(LastError);
      return v9;
    }
    LongPathNameW = GetLongPathNameW(v1, 0, 0);
    if ( LongPathNameW )
    {
      ProcessHeap = GetProcessHeap();
      v5 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, 2LL * LongPathNameW);
      v6 = v5;
      if ( v5 )
      {
        v7 = 0;
        if ( !GetLongPathNameW(v2, v5, LongPathNameW) )
          v7 = GetLastError();
      }
      else
      {
        v7 = 14;
      }
      v8 = v6;
      if ( v6 )
      {
        v9 = v6;
LABEL_13:
        LastError = 0;
        if ( v6 )
          LastError = v7;
        v11 = 0;
        if ( v8 )
          v11 = (WCHAR *)v2;
        if ( v11 )
        {
          v12 = GetProcessHeap();
          HeapFree(v12, 0, v11);
        }
        goto LABEL_20;
      }
    }
    else
    {
      v6 = 0;
      v7 = GetLastError();
      v8 = 0;
    }
    v9 = v2;
    goto LABEL_13;
  }
  SetLastError(0x57u);
  return 0;
}

```

## disassembly

```asm
0x18003c0ec  push    rbx
0x18003c0ee  push    rbp
0x18003c0ef  push    rsi
0x18003c0f0  push    rdi
0x18003c0f1  push    r14
0x18003c0f3  sub     rsp, 20h
0x18003c0f7  test    rcx, rcx
0x18003c0fa  jz      loc_18003C1DE
0x18003c100  xor     eax, eax
0x18003c102  cmp     ax, [rcx]
0x18003c105  jz      loc_18003C1DE
0x18003c10b  xor     edx, edx
0x18003c10d  call    PrepareUnicodePathEx
0x18003c112  mov     rbp, rax
0x18003c115  test    rax, rax
0x18003c118  jz      loc_18003C1C7
0x18003c11e  xor     r8d, r8d; cchBuffer
0x18003c121  xor     edx, edx; lpszLongPath
0x18003c123  mov     rcx, rax; lpszShortPath
0x18003c126  call    cs:__imp_GetLongPathNameW
0x18003c12c  mov     edi, eax
0x18003c12e  test    eax, eax
0x18003c130  jz      short loc_18003C18A
0x18003c132  mov     ebx, edi
0x18003c134  add     rbx, rbx
0x18003c137  call    cs:__imp_GetProcessHeap
0x18003c13d  mov     r8, rbx; dwBytes
0x18003c140  mov     edx, 8; dwFlags
0x18003c145  mov     rcx, rax; hHeap
0x18003c148  call    cs:__imp_HeapAlloc
0x18003c14e  mov     rsi, rax
0x18003c151  test    rax, rax
0x18003c154  jz      short loc_18003C177
0x18003c156  mov     r8d, edi; cchBuffer
0x18003c159  mov     rdx, rax; lpszLongPath
0x18003c15c  mov     rcx, rbp; lpszShortPath
0x18003c15f  xor     r14d, r14d
0x18003c162  call    cs:__imp_GetLongPathNameW
0x18003c168  test    eax, eax
0x18003c16a  jnz     short loc_18003C17D
0x18003c16c  call    cs:__imp_GetLastError
0x18003c172  mov     r14d, eax
0x18003c175  jmp     short loc_18003C17D
0x18003c177  mov     r14d, 0Eh
0x18003c17d  mov     rax, rsi
0x18003c180  test    rsi, rsi
0x18003c183  jz      short loc_18003C197
0x18003c185  mov     rbx, rsi
0x18003c188  jmp     short loc_18003C19A
0x18003c18a  call    cs:__imp_GetLastError
0x18003c190  xor     esi, esi
0x18003c192  mov     r14d, eax
0x18003c195  xor     eax, eax
0x18003c197  mov     rbx, rbp
0x18003c19a  xor     edi, edi
0x18003c19c  test    rsi, rsi
0x18003c19f  cmovnz  edi, r14d
0x18003c1a3  xor     esi, esi
0x18003c1a5  test    rax, rax
0x18003c1a8  cmovnz  rsi, rbp
0x18003c1ac  test    rsi, rsi
0x18003c1af  jz      short loc_18003C1D1
0x18003c1b1  call    cs:__imp_GetProcessHeap
0x18003c1b7  mov     r8, rsi; lpMem
0x18003c1ba  xor     edx, edx; dwFlags
0x18003c1bc  mov     rcx, rax; hHeap
0x18003c1bf  call    cs:__imp_HeapFree
0x18003c1c5  jmp     short loc_18003C1D1
0x18003c1c7  xor     ebx, ebx
0x18003c1c9  call    cs:__imp_GetLastError
0x18003c1cf  mov     edi, eax
0x18003c1d1  mov     ecx, edi; dwErrCode
0x18003c1d3  call    cs:__imp_SetLastError
0x18003c1d9  mov     rax, rbx
0x18003c1dc  jmp     short loc_18003C1EB
0x18003c1de  mov     ecx, 57h ; 'W'; dwErrCode
0x18003c1e3  call    cs:__imp_SetLastError
0x18003c1e9  xor     eax, eax
0x18003c1eb  add     rsp, 20h
0x18003c1ef  pop     r14
0x18003c1f1  pop     rdi
0x18003c1f2  pop     rsi
0x18003c1f3  pop     rbp
0x18003c1f4  pop     rbx
0x18003c1f5  retn
```
