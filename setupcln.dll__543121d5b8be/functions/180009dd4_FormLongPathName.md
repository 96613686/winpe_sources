# FormLongPathName

- ea: `0x180009dd4`
- end: `0x180009ede`
- name: `FormLongPathName`
- size: `266`
- prototype: `const WCHAR *__fastcall(const wchar_t *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000aa40`
- `0x18000b720`
- `0x18000c580`

## callees

- `0x180009dd4`
- `0x18000a0f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009ebb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009ecb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009ebb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009ecb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009e54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009e72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009eb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009e54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009e72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009eb1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009e30`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009e30`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009e1f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009e99`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009e1f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009e99`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009ea7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009ea7`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x180009e0e`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x180009e4a`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x180009e0e`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x180009e4a`

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
0x180009dd4  push    rbx
0x180009dd6  push    rbp
0x180009dd7  push    rsi
0x180009dd8  push    rdi
0x180009dd9  push    r14
0x180009ddb  sub     rsp, 20h
0x180009ddf  test    rcx, rcx
0x180009de2  jz      loc_180009EC6
0x180009de8  xor     eax, eax
0x180009dea  cmp     ax, [rcx]
0x180009ded  jz      loc_180009EC6
0x180009df3  xor     edx, edx
0x180009df5  call    PrepareUnicodePathEx
0x180009dfa  mov     rbp, rax
0x180009dfd  test    rax, rax
0x180009e00  jz      loc_180009EAF
0x180009e06  xor     r8d, r8d; cchBuffer
0x180009e09  xor     edx, edx; lpszLongPath
0x180009e0b  mov     rcx, rax; lpszShortPath
0x180009e0e  call    cs:__imp_GetLongPathNameW
0x180009e14  mov     edi, eax
0x180009e16  test    eax, eax
0x180009e18  jz      short loc_180009E72
0x180009e1a  mov     ebx, edi
0x180009e1c  add     rbx, rbx
0x180009e1f  call    cs:__imp_GetProcessHeap
0x180009e25  mov     r8, rbx; dwBytes
0x180009e28  mov     edx, 8; dwFlags
0x180009e2d  mov     rcx, rax; hHeap
0x180009e30  call    cs:__imp_HeapAlloc
0x180009e36  mov     rsi, rax
0x180009e39  test    rax, rax
0x180009e3c  jz      short loc_180009E5F
0x180009e3e  mov     r8d, edi; cchBuffer
0x180009e41  mov     rdx, rax; lpszLongPath
0x180009e44  mov     rcx, rbp; lpszShortPath
0x180009e47  xor     r14d, r14d
0x180009e4a  call    cs:__imp_GetLongPathNameW
0x180009e50  test    eax, eax
0x180009e52  jnz     short loc_180009E65
0x180009e54  call    cs:__imp_GetLastError
0x180009e5a  mov     r14d, eax
0x180009e5d  jmp     short loc_180009E65
0x180009e5f  mov     r14d, 0Eh
0x180009e65  mov     rax, rsi
0x180009e68  test    rsi, rsi
0x180009e6b  jz      short loc_180009E7F
0x180009e6d  mov     rbx, rsi
0x180009e70  jmp     short loc_180009E82
0x180009e72  call    cs:__imp_GetLastError
0x180009e78  xor     esi, esi
0x180009e7a  mov     r14d, eax
0x180009e7d  xor     eax, eax
0x180009e7f  mov     rbx, rbp
0x180009e82  xor     edi, edi
0x180009e84  test    rsi, rsi
0x180009e87  cmovnz  edi, r14d
0x180009e8b  xor     esi, esi
0x180009e8d  test    rax, rax
0x180009e90  cmovnz  rsi, rbp
0x180009e94  test    rsi, rsi
0x180009e97  jz      short loc_180009EB9
0x180009e99  call    cs:__imp_GetProcessHeap
0x180009e9f  mov     r8, rsi; lpMem
0x180009ea2  xor     edx, edx; dwFlags
0x180009ea4  mov     rcx, rax; hHeap
0x180009ea7  call    cs:__imp_HeapFree
0x180009ead  jmp     short loc_180009EB9
0x180009eaf  xor     ebx, ebx
0x180009eb1  call    cs:__imp_GetLastError
0x180009eb7  mov     edi, eax
0x180009eb9  mov     ecx, edi; dwErrCode
0x180009ebb  call    cs:__imp_SetLastError
0x180009ec1  mov     rax, rbx
0x180009ec4  jmp     short loc_180009ED3
0x180009ec6  mov     ecx, 57h ; 'W'; dwErrCode
0x180009ecb  call    cs:__imp_SetLastError
0x180009ed1  xor     eax, eax
0x180009ed3  add     rsp, 20h
0x180009ed7  pop     r14
0x180009ed9  pop     rdi
0x180009eda  pop     rsi
0x180009edb  pop     rbp
0x180009edc  pop     rbx
0x180009edd  retn
```
