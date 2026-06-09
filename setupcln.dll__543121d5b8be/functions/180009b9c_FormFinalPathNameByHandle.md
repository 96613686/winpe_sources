# FormFinalPathNameByHandle

- ea: `0x180009b9c`
- end: `0x180009c7c`
- name: `FormFinalPathNameByHandle`
- size: `224`
- prototype: `WCHAR *__fastcall(char *hFile, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path`

## callers

- `0x180009c84`
- `0x18000c580`

## callees

- `0x180009b9c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009c59`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009c69`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009c59`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009c69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009c4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009c4f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009c1e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009c1e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009c0d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009c0d`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180009bf9`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180009c3a`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180009bf9`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180009c3a`

## pseudocode

```c
WCHAR *__fastcall FormFinalPathNameByHandle(char *hFile, int a2)
{
  DWORD v3; // edi
  int v4; // edx
  int v5; // edx
  DWORD v6; // ecx
  DWORD FinalPathNameByHandleW; // eax
  DWORD v8; // r14d
  SIZE_T v9; // rbx
  HANDLE ProcessHeap; // rax
  WCHAR *v11; // rax
  WCHAR *v12; // rsi
  DWORD LastError; // ebx

  if ( (unsigned __int64)(hFile - 1) > 0xFFFFFFFFFFFFFFFDuLL || (a2 & 0xFFFFFFF8) != 0 )
  {
    v6 = 87;
    goto LABEL_19;
  }
  v3 = 0;
  if ( !a2 )
  {
LABEL_10:
    FinalPathNameByHandleW = GetFinalPathNameByHandleW(hFile, 0, 0, v3);
    if ( FinalPathNameByHandleW )
    {
      v8 = FinalPathNameByHandleW + 1;
      v9 = 2LL * (FinalPathNameByHandleW + 1);
      ProcessHeap = GetProcessHeap();
      v11 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, v9);
      v12 = v11;
      if ( v11 )
      {
        LastError = 0;
        if ( !GetFinalPathNameByHandleW(hFile, v11, v8, v3) )
          goto LABEL_16;
      }
      else
      {
        LastError = 14;
      }
LABEL_17:
      SetLastError(LastError);
      return v12;
    }
    v12 = 0;
LABEL_16:
    LastError = GetLastError();
    goto LABEL_17;
  }
  v4 = a2 - 1;
  if ( !v4 )
  {
    v3 = 1;
    goto LABEL_10;
  }
  v3 = 2;
  v5 = v4 - 1;
  if ( !v5 )
    goto LABEL_10;
  if ( v5 == 2 )
  {
    v3 = 4;
    goto LABEL_10;
  }
  v6 = 50;
LABEL_19:
  SetLastError(v6);
  return 0;
}

```

## disassembly

```asm
0x180009b9c  push    rbx
0x180009b9e  push    rbp
0x180009b9f  push    rsi
0x180009ba0  push    rdi
0x180009ba1  push    r14
0x180009ba3  sub     rsp, 20h
0x180009ba7  lea     rax, [rcx-1]
0x180009bab  mov     rbp, rcx
0x180009bae  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180009bb2  ja      loc_180009C64
0x180009bb8  test    edx, 0FFFFFFF8h
0x180009bbe  jnz     loc_180009C64
0x180009bc4  xor     edi, edi
0x180009bc6  test    edx, edx
0x180009bc8  jz      short loc_180009BF1
0x180009bca  sub     edx, 1
0x180009bcd  jz      short loc_180009BEC
0x180009bcf  mov     edi, 2
0x180009bd4  sub     edx, 1
0x180009bd7  jz      short loc_180009BF1
0x180009bd9  cmp     edx, edi
0x180009bdb  jz      short loc_180009BE5
0x180009bdd  lea     ecx, [rdi+30h]; hFile
0x180009be0  jmp     loc_180009C69
0x180009be5  mov     edi, 4
0x180009bea  jmp     short loc_180009BF1
0x180009bec  mov     edi, 1
0x180009bf1  mov     r9d, edi; dwFlags
0x180009bf4  xor     r8d, r8d; cchFilePath
0x180009bf7  xor     edx, edx; lpszFilePath
0x180009bf9  call    cs:__imp_GetFinalPathNameByHandleW
0x180009bff  test    eax, eax
0x180009c01  jz      short loc_180009C4D
0x180009c03  lea     r14d, [rax+1]
0x180009c07  mov     ebx, r14d
0x180009c0a  add     rbx, rbx
0x180009c0d  call    cs:__imp_GetProcessHeap
0x180009c13  mov     r8, rbx; dwBytes
0x180009c16  mov     edx, 8; dwFlags
0x180009c1b  mov     rcx, rax; hHeap
0x180009c1e  call    cs:__imp_HeapAlloc
0x180009c24  mov     rsi, rax
0x180009c27  test    rax, rax
0x180009c2a  jz      short loc_180009C46
0x180009c2c  mov     r9d, edi; dwFlags
0x180009c2f  mov     r8d, r14d; cchFilePath
0x180009c32  mov     rdx, rax; lpszFilePath
0x180009c35  mov     rcx, rbp; hFile
0x180009c38  xor     ebx, ebx
0x180009c3a  call    cs:__imp_GetFinalPathNameByHandleW
0x180009c40  test    eax, eax
0x180009c42  jnz     short loc_180009C57
0x180009c44  jmp     short loc_180009C4F
0x180009c46  mov     ebx, 0Eh
0x180009c4b  jmp     short loc_180009C57
0x180009c4d  xor     esi, esi
0x180009c4f  call    cs:__imp_GetLastError
0x180009c55  mov     ebx, eax
0x180009c57  mov     ecx, ebx; dwErrCode
0x180009c59  call    cs:__imp_SetLastError
0x180009c5f  mov     rax, rsi
0x180009c62  jmp     short loc_180009C71
0x180009c64  mov     ecx, 57h ; 'W'; dwErrCode
0x180009c69  call    cs:__imp_SetLastError
0x180009c6f  xor     eax, eax
0x180009c71  add     rsp, 20h
0x180009c75  pop     r14
0x180009c77  pop     rdi
0x180009c78  pop     rsi
0x180009c79  pop     rbp
0x180009c7a  pop     rbx
0x180009c7b  retn
```
