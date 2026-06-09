# FormFullPathName

- ea: `0x18003c048`
- end: `0x18003c0e5`
- name: `FormFullPathName`
- size: `157`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18003abd0`
- `0x18003b04c`
- `0x18003c464`
- `0x18003db20`

## callees

- `0x18003c048`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18003c068`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18003c0a5`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18003c068`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18003c0a5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003c079`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003c079`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003c08a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003c08a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c0c4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c0d4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c0c4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c0d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c0ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c0ba`

## pseudocode

```c
WCHAR *__fastcall FormFullPathName(LPCWSTR lpFileName)
{
  DWORD FullPathNameW; // ebp
  HANDLE ProcessHeap; // rax
  WCHAR *v4; // rax
  WCHAR *v5; // rsi
  DWORD LastError; // ebx

  if ( lpFileName && *lpFileName )
  {
    FullPathNameW = GetFullPathNameW(lpFileName, 0, 0, 0);
    if ( FullPathNameW )
    {
      ProcessHeap = GetProcessHeap();
      v4 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, 2LL * FullPathNameW);
      v5 = v4;
      if ( v4 )
      {
        LastError = 0;
        if ( !GetFullPathNameW(lpFileName, FullPathNameW, v4, 0) )
          goto LABEL_9;
      }
      else
      {
        LastError = 14;
      }
LABEL_10:
      SetLastError(LastError);
      return v5;
    }
    v5 = 0;
LABEL_9:
    LastError = GetLastError();
    goto LABEL_10;
  }
  SetLastError(0x57u);
  return 0;
}

```

## disassembly

```asm
0x18003c048  push    rbx
0x18003c04a  push    rbp
0x18003c04b  push    rsi
0x18003c04c  push    rdi
0x18003c04d  sub     rsp, 28h
0x18003c051  mov     rdi, rcx
0x18003c054  test    rcx, rcx
0x18003c057  jz      short loc_18003C0CF
0x18003c059  xor     eax, eax
0x18003c05b  cmp     ax, [rcx]
0x18003c05e  jz      short loc_18003C0CF
0x18003c060  xor     r9d, r9d; lpFilePart
0x18003c063  xor     r8d, r8d; lpBuffer
0x18003c066  xor     edx, edx; nBufferLength
0x18003c068  call    cs:__imp_GetFullPathNameW
0x18003c06e  mov     ebp, eax
0x18003c070  test    eax, eax
0x18003c072  jz      short loc_18003C0B8
0x18003c074  mov     ebx, ebp
0x18003c076  add     rbx, rbx
0x18003c079  call    cs:__imp_GetProcessHeap
0x18003c07f  mov     r8, rbx; dwBytes
0x18003c082  mov     edx, 8; dwFlags
0x18003c087  mov     rcx, rax; hHeap
0x18003c08a  call    cs:__imp_HeapAlloc
0x18003c090  mov     rsi, rax
0x18003c093  test    rax, rax
0x18003c096  jz      short loc_18003C0B1
0x18003c098  xor     r9d, r9d; lpFilePart
0x18003c09b  mov     r8, rax; lpBuffer
0x18003c09e  mov     edx, ebp; nBufferLength
0x18003c0a0  mov     rcx, rdi; lpFileName
0x18003c0a3  xor     ebx, ebx
0x18003c0a5  call    cs:__imp_GetFullPathNameW
0x18003c0ab  test    eax, eax
0x18003c0ad  jnz     short loc_18003C0C2
0x18003c0af  jmp     short loc_18003C0BA
0x18003c0b1  mov     ebx, 0Eh
0x18003c0b6  jmp     short loc_18003C0C2
0x18003c0b8  xor     esi, esi
0x18003c0ba  call    cs:__imp_GetLastError
0x18003c0c0  mov     ebx, eax
0x18003c0c2  mov     ecx, ebx; dwErrCode
0x18003c0c4  call    cs:__imp_SetLastError
0x18003c0ca  mov     rax, rsi
0x18003c0cd  jmp     short loc_18003C0DC
0x18003c0cf  mov     ecx, 57h ; 'W'; dwErrCode
0x18003c0d4  call    cs:__imp_SetLastError
0x18003c0da  xor     eax, eax
0x18003c0dc  add     rsp, 28h
0x18003c0e0  pop     rdi
0x18003c0e1  pop     rsi
0x18003c0e2  pop     rbp
0x18003c0e3  pop     rbx
0x18003c0e4  retn
```
