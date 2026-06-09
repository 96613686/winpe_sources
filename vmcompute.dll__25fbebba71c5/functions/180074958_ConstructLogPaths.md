# ConstructLogPaths

- ea: `0x180074958`
- end: `0x180074ba6`
- name: `ConstructLogPaths`
- size: `590`
- prototype: `__int64 __fastcall(HANDLE hFile, wchar_t *Source)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path`

## callers

- `0x1800750a8`

## callees

- `0x180003b26`
- `0x180003b32`
- `0x180003c30`
- `0x180003c48`
- `0x180003c78`
- `0x180074958`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180074b07`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180074b07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007499b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074aef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007499b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074aef`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180074989`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800749f1`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180074989`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800749f1`

## pseudocode

```c
__int64 __fastcall ConstructLogPaths(HANDLE hFile, wchar_t *Source, _QWORD *a3)
{
  void *v3; // rsi
  void *v4; // rdi
  _QWORD *v5; // r13
  DWORD FinalPathNameByHandleW; // eax
  __int64 v9; // rbx
  DWORD LastError; // ebx
  WCHAR *v11; // rax
  WCHAR *v12; // rbp
  DWORD v13; // eax
  size_t v14; // r14
  void *v15; // rax
  rsize_t v16; // rbx
  size_t v17; // r12
  WCHAR *v18; // rax

  v3 = 0;
  v4 = 0;
  v5 = a3;
  if ( Source )
  {
    v14 = wcsnlen(Source, 0x100u);
    v17 = 2 * v14 + 2;
    v18 = (WCHAR *)o__aligned_malloc_0(v17, 0x10u);
    v12 = v18;
    if ( !v18 )
      return 8;
    memset_0(v18, 0, v17);
    if ( (unsigned int)o_wcsncpy_s_0(v12, v17 >> 1, Source, v14) )
    {
LABEL_20:
      LastError = 1359;
      goto LABEL_22;
    }
  }
  else
  {
    FinalPathNameByHandleW = GetFinalPathNameByHandleW(hFile, 0, 0, 0);
    v9 = FinalPathNameByHandleW;
    if ( !FinalPathNameByHandleW )
      return GetLastError();
    v11 = (WCHAR *)o__aligned_malloc_0(2LL * FinalPathNameByHandleW, 0x10u);
    v12 = v11;
    if ( !v11 )
      return 8;
    memset_0(v11, 0, 2 * v9);
    v13 = GetFinalPathNameByHandleW(hFile, v12, v9, 0);
    if ( !v13 || v13 + 1 != (_DWORD)v9 )
      goto LABEL_17;
    v5 = a3;
    v14 = v9 - 1;
  }
  if ( !v14 )
  {
LABEL_17:
    LastError = GetLastError();
    goto LABEL_22;
  }
  v3 = o__aligned_malloc_0(2 * v14 + 12, 0x10u);
  v15 = o__aligned_malloc_0(2 * v14 + 12, 0x10u);
  v4 = v15;
  if ( !v3 || !v15 )
  {
    LastError = 8;
    goto LABEL_22;
  }
  memset_0(v3, 0, 2 * v14 + 12);
  memset_0(v4, 0, 2 * v14 + 12);
  v16 = (2 * v14 + 12) >> 1;
  if ( (unsigned int)o_wcsncpy_s_0(v3, v16, v12, v14)
    || wcscat_s((wchar_t *)v3, v16, L".LOG1")
    || (unsigned int)o_wcsncpy_s_0(v4, v16, v12, v14)
    || wcscat_s((wchar_t *)v4, v16, L".LOG2") )
  {
    goto LABEL_20;
  }
  *v5 = v3;
  v3 = 0;
  v5[1] = v4;
  v4 = 0;
  LastError = 0;
LABEL_22:
  aligned_free(v12);
  if ( v3 )
    aligned_free(v3);
  if ( v4 )
    aligned_free(v4);
  return LastError;
}

```

## disassembly

```asm
0x180074958  mov     [rsp+arg_10], r8
0x18007495d  push    rbx
0x18007495e  push    rbp
0x18007495f  push    rsi
0x180074960  push    rdi
0x180074961  push    r12
0x180074963  push    r13
0x180074965  push    r14
0x180074967  push    r15
0x180074969  sub     rsp, 28h
0x18007496d  xor     esi, esi
0x18007496f  xor     edi, edi
0x180074971  mov     r13, r8
0x180074974  mov     rbx, rdx
0x180074977  mov     r12, rcx
0x18007497a  test    rdx, rdx
0x18007497d  jnz     loc_180074AFF
0x180074983  xor     r9d, r9d; dwFlags
0x180074986  xor     r8d, r8d; cchFilePath
0x180074989  call    cs:__imp_GetFinalPathNameByHandleW
0x180074990  nop     dword ptr [rax+rax+00h]
0x180074995  mov     ebx, eax
0x180074997  test    eax, eax
0x180074999  jnz     short loc_1800749AE
0x18007499b  call    cs:__imp_GetLastError
0x1800749a2  nop     dword ptr [rax+rax+00h]
0x1800749a7  mov     ebx, eax
0x1800749a9  jmp     loc_180074B92
0x1800749ae  lea     r13, [rbx+rbx]
0x1800749b2  mov     r15d, 10h
0x1800749b8  mov     edx, r15d; Alignment
0x1800749bb  mov     rcx, r13; Size
0x1800749be  mov     r14, rbx
0x1800749c1  call    _o__aligned_malloc_0
0x1800749c6  mov     rbp, rax
0x1800749c9  test    rax, rax
0x1800749cc  jnz     short loc_1800749D8
0x1800749ce  mov     ebx, 8
0x1800749d3  jmp     loc_180074B92
0x1800749d8  mov     r8, r13; Size
0x1800749db  xor     edx, edx; Val
0x1800749dd  mov     rcx, rbp; void *
0x1800749e0  call    memset_0
0x1800749e5  xor     r9d, r9d; dwFlags
0x1800749e8  mov     r8d, ebx; cchFilePath
0x1800749eb  mov     rdx, rbp; lpszFilePath
0x1800749ee  mov     rcx, r12; hFile
0x1800749f1  call    cs:__imp_GetFinalPathNameByHandleW
0x1800749f8  nop     dword ptr [rax+rax+00h]
0x1800749fd  test    eax, eax
0x1800749ff  jz      loc_180074AEF
0x180074a05  inc     eax
0x180074a07  cmp     eax, ebx
0x180074a09  jnz     loc_180074AEF
0x180074a0f  mov     r13, [rsp+68h+arg_10]
0x180074a17  dec     r14
0x180074a1a  test    r14, r14
0x180074a1d  jz      loc_180074AEF
0x180074a23  lea     rbx, ds:0Ch[r14*2]
0x180074a2b  mov     rdx, r15; Alignment
0x180074a2e  mov     rcx, rbx; Size
0x180074a31  call    _o__aligned_malloc_0
0x180074a36  mov     rdx, r15; Alignment
0x180074a39  mov     rcx, rbx; Size
0x180074a3c  mov     rsi, rax
0x180074a3f  call    _o__aligned_malloc_0
0x180074a44  mov     rdi, rax
0x180074a47  test    rsi, rsi
0x180074a4a  jz      loc_180074B6B
0x180074a50  test    rax, rax
0x180074a53  jz      loc_180074B6B
0x180074a59  mov     r8, rbx; Size
0x180074a5c  xor     edx, edx; Val
0x180074a5e  mov     rcx, rsi; void *
0x180074a61  call    memset_0
0x180074a66  mov     r8, rbx; Size
0x180074a69  xor     edx, edx; Val
0x180074a6b  mov     rcx, rdi; void *
0x180074a6e  call    memset_0
0x180074a73  shr     rbx, 1
0x180074a76  mov     r9, r14
0x180074a79  mov     rdx, rbx
0x180074a7c  mov     r8, rbp
0x180074a7f  mov     rcx, rsi
0x180074a82  call    _o_wcsncpy_s_0
0x180074a87  test    eax, eax
0x180074a89  jnz     loc_180074B64
0x180074a8f  lea     r8, aLog1; ".LOG1"
0x180074a96  mov     rdx, rbx; SizeInWords
0x180074a99  mov     rcx, rsi; Destination
0x180074a9c  call    wcscat_s
0x180074aa1  test    eax, eax
0x180074aa3  jnz     loc_180074B64
0x180074aa9  mov     r9, r14
0x180074aac  mov     r8, rbp
0x180074aaf  mov     rdx, rbx
0x180074ab2  mov     rcx, rdi
0x180074ab5  call    _o_wcsncpy_s_0
0x180074aba  test    eax, eax
0x180074abc  jnz     loc_180074B64
0x180074ac2  lea     r8, aLog2; ".LOG2"
0x180074ac9  mov     rdx, rbx; SizeInWords
0x180074acc  mov     rcx, rdi; Destination
0x180074acf  call    wcscat_s
0x180074ad4  test    eax, eax
0x180074ad6  jnz     loc_180074B64
0x180074adc  mov     [r13+0], rsi
0x180074ae0  xor     esi, esi
0x180074ae2  mov     [r13+8], rdi
0x180074ae6  xor     edi, edi
0x180074ae8  xor     ebx, ebx
0x180074aea  jmp     loc_180074B70
0x180074aef  call    cs:__imp_GetLastError
0x180074af6  nop     dword ptr [rax+rax+00h]
0x180074afb  mov     ebx, eax
0x180074afd  jmp     short loc_180074B70
0x180074aff  mov     edx, 100h; MaxCount
0x180074b04  mov     rcx, rbx; Source
0x180074b07  call    cs:__imp_wcsnlen
0x180074b0e  nop     dword ptr [rax+rax+00h]
0x180074b13  mov     r15d, 10h
0x180074b19  mov     r14, rax
0x180074b1c  mov     edx, r15d; Alignment
0x180074b1f  lea     r12, ds:2[rax*2]
0x180074b27  mov     rcx, r12; Size
0x180074b2a  call    _o__aligned_malloc_0
0x180074b2f  mov     rbp, rax
0x180074b32  test    rax, rax
0x180074b35  jz      loc_1800749CE
0x180074b3b  mov     r8, r12; Size
0x180074b3e  xor     edx, edx; Val
0x180074b40  mov     rcx, rax; void *
0x180074b43  call    memset_0
0x180074b48  shr     r12, 1
0x180074b4b  mov     r9, r14
0x180074b4e  mov     rdx, r12
0x180074b51  mov     r8, rbx
0x180074b54  mov     rcx, rbp
0x180074b57  call    _o_wcsncpy_s_0
0x180074b5c  test    eax, eax
0x180074b5e  jz      loc_180074A1A
0x180074b64  mov     ebx, 54Fh
0x180074b69  jmp     short loc_180074B70
0x180074b6b  mov     ebx, 8
0x180074b70  mov     rcx, rbp; Block
0x180074b73  call    _aligned_free
0x180074b78  test    rsi, rsi
0x180074b7b  jz      short loc_180074B85
0x180074b7d  mov     rcx, rsi; Block
0x180074b80  call    _aligned_free
0x180074b85  test    rdi, rdi
0x180074b88  jz      short loc_180074B92
0x180074b8a  mov     rcx, rdi; Block
0x180074b8d  call    _aligned_free
0x180074b92  mov     eax, ebx
0x180074b94  add     rsp, 28h
0x180074b98  pop     r15
0x180074b9a  pop     r14
0x180074b9c  pop     r13
0x180074b9e  pop     r12
0x180074ba0  pop     rdi
0x180074ba1  pop     rsi
0x180074ba2  pop     rbp
0x180074ba3  pop     rbx
0x180074ba4  retn
```
