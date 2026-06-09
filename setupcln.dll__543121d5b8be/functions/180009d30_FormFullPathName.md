# FormFullPathName

- ea: `0x180009d30`
- end: `0x180009dcd`
- name: `FormFullPathName`
- size: `157`
- prototype: `WCHAR *__fastcall(LPCWSTR lpFileName)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180005080`
- `0x18000a0f0`
- `0x18000b720`
- `0x18000bb18`
- `0x18000c580`

## callees

- `0x180009d30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009dac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009dbc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009dac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009dbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009da2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009da2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009d72`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009d72`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009d61`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009d61`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180009d50`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180009d8d`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180009d50`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180009d8d`

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
0x180009d30  push    rbx
0x180009d32  push    rbp
0x180009d33  push    rsi
0x180009d34  push    rdi
0x180009d35  sub     rsp, 28h
0x180009d39  mov     rdi, rcx
0x180009d3c  test    rcx, rcx
0x180009d3f  jz      short loc_180009DB7
0x180009d41  xor     eax, eax
0x180009d43  cmp     ax, [rcx]
0x180009d46  jz      short loc_180009DB7
0x180009d48  xor     r9d, r9d; lpFilePart
0x180009d4b  xor     r8d, r8d; lpBuffer
0x180009d4e  xor     edx, edx; nBufferLength
0x180009d50  call    cs:__imp_GetFullPathNameW
0x180009d56  mov     ebp, eax
0x180009d58  test    eax, eax
0x180009d5a  jz      short loc_180009DA0
0x180009d5c  mov     ebx, ebp
0x180009d5e  add     rbx, rbx
0x180009d61  call    cs:__imp_GetProcessHeap
0x180009d67  mov     r8, rbx; dwBytes
0x180009d6a  mov     edx, 8; dwFlags
0x180009d6f  mov     rcx, rax; hHeap
0x180009d72  call    cs:__imp_HeapAlloc
0x180009d78  mov     rsi, rax
0x180009d7b  test    rax, rax
0x180009d7e  jz      short loc_180009D99
0x180009d80  xor     r9d, r9d; lpFilePart
0x180009d83  mov     r8, rax; lpBuffer
0x180009d86  mov     edx, ebp; nBufferLength
0x180009d88  mov     rcx, rdi; lpFileName
0x180009d8b  xor     ebx, ebx
0x180009d8d  call    cs:__imp_GetFullPathNameW
0x180009d93  test    eax, eax
0x180009d95  jnz     short loc_180009DAA
0x180009d97  jmp     short loc_180009DA2
0x180009d99  mov     ebx, 0Eh
0x180009d9e  jmp     short loc_180009DAA
0x180009da0  xor     esi, esi
0x180009da2  call    cs:__imp_GetLastError
0x180009da8  mov     ebx, eax
0x180009daa  mov     ecx, ebx; dwErrCode
0x180009dac  call    cs:__imp_SetLastError
0x180009db2  mov     rax, rsi
0x180009db5  jmp     short loc_180009DC4
0x180009db7  mov     ecx, 57h ; 'W'; dwErrCode
0x180009dbc  call    cs:__imp_SetLastError
0x180009dc2  xor     eax, eax
0x180009dc4  add     rsp, 28h
0x180009dc8  pop     rdi
0x180009dc9  pop     rsi
0x180009dca  pop     rbp
0x180009dcb  pop     rbx
0x180009dcc  retn
```
