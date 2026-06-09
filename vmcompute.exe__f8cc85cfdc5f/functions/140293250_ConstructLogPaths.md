# ConstructLogPaths

- ea: `0x140293250`
- end: `0x14029349e`
- name: `ConstructLogPaths`
- size: `590`
- prototype: `__int64 __fastcall(HANDLE hFile, wchar_t *Source)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path`

## callers

- `0x140293998`

## callees

- `0x140133eba`
- `0x140134000`
- `0x140134018`
- `0x140134048`
- `0x140249edc`
- `0x140293250`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1402933ff`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1402933ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140293293`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1402933e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140293293`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1402933e7`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x140293281`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1402932e9`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x140293281`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1402932e9`

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
  ORFree(v12);
  if ( v3 )
    ORFree(v3);
  if ( v4 )
    ORFree(v4);
  return LastError;
}

```

## disassembly

```asm
0x140293250  mov     [rsp+arg_10], r8
0x140293255  push    rbx
0x140293256  push    rbp
0x140293257  push    rsi
0x140293258  push    rdi
0x140293259  push    r12
0x14029325b  push    r13
0x14029325d  push    r14
0x14029325f  push    r15
0x140293261  sub     rsp, 28h
0x140293265  xor     esi, esi
0x140293267  xor     edi, edi
0x140293269  mov     r13, r8
0x14029326c  mov     rbx, rdx
0x14029326f  mov     r12, rcx
0x140293272  test    rdx, rdx
0x140293275  jnz     loc_1402933F7
0x14029327b  xor     r9d, r9d; dwFlags
0x14029327e  xor     r8d, r8d; cchFilePath
0x140293281  call    cs:__imp_GetFinalPathNameByHandleW
0x140293288  nop     dword ptr [rax+rax+00h]
0x14029328d  mov     ebx, eax
0x14029328f  test    eax, eax
0x140293291  jnz     short loc_1402932A6
0x140293293  call    cs:__imp_GetLastError
0x14029329a  nop     dword ptr [rax+rax+00h]
0x14029329f  mov     ebx, eax
0x1402932a1  jmp     loc_14029348A
0x1402932a6  lea     r13, [rbx+rbx]
0x1402932aa  mov     r15d, 10h
0x1402932b0  mov     edx, r15d; Alignment
0x1402932b3  mov     rcx, r13; Size
0x1402932b6  mov     r14, rbx
0x1402932b9  call    _o__aligned_malloc_0
0x1402932be  mov     rbp, rax
0x1402932c1  test    rax, rax
0x1402932c4  jnz     short loc_1402932D0
0x1402932c6  mov     ebx, 8
0x1402932cb  jmp     loc_14029348A
0x1402932d0  mov     r8, r13; Size
0x1402932d3  xor     edx, edx; Val
0x1402932d5  mov     rcx, rbp; void *
0x1402932d8  call    memset_0
0x1402932dd  xor     r9d, r9d; dwFlags
0x1402932e0  mov     r8d, ebx; cchFilePath
0x1402932e3  mov     rdx, rbp; lpszFilePath
0x1402932e6  mov     rcx, r12; hFile
0x1402932e9  call    cs:__imp_GetFinalPathNameByHandleW
0x1402932f0  nop     dword ptr [rax+rax+00h]
0x1402932f5  test    eax, eax
0x1402932f7  jz      loc_1402933E7
0x1402932fd  inc     eax
0x1402932ff  cmp     eax, ebx
0x140293301  jnz     loc_1402933E7
0x140293307  mov     r13, [rsp+68h+arg_10]
0x14029330f  dec     r14
0x140293312  test    r14, r14
0x140293315  jz      loc_1402933E7
0x14029331b  lea     rbx, ds:0Ch[r14*2]
0x140293323  mov     rdx, r15; Alignment
0x140293326  mov     rcx, rbx; Size
0x140293329  call    _o__aligned_malloc_0
0x14029332e  mov     rdx, r15; Alignment
0x140293331  mov     rcx, rbx; Size
0x140293334  mov     rsi, rax
0x140293337  call    _o__aligned_malloc_0
0x14029333c  mov     rdi, rax
0x14029333f  test    rsi, rsi
0x140293342  jz      loc_140293463
0x140293348  test    rax, rax
0x14029334b  jz      loc_140293463
0x140293351  mov     r8, rbx; Size
0x140293354  xor     edx, edx; Val
0x140293356  mov     rcx, rsi; void *
0x140293359  call    memset_0
0x14029335e  mov     r8, rbx; Size
0x140293361  xor     edx, edx; Val
0x140293363  mov     rcx, rdi; void *
0x140293366  call    memset_0
0x14029336b  shr     rbx, 1
0x14029336e  mov     r9, r14
0x140293371  mov     rdx, rbx
0x140293374  mov     r8, rbp
0x140293377  mov     rcx, rsi
0x14029337a  call    _o_wcsncpy_s_0
0x14029337f  test    eax, eax
0x140293381  jnz     loc_14029345C
0x140293387  lea     r8, aLog1; ".LOG1"
0x14029338e  mov     rdx, rbx; SizeInWords
0x140293391  mov     rcx, rsi; Destination
0x140293394  call    wcscat_s
0x140293399  test    eax, eax
0x14029339b  jnz     loc_14029345C
0x1402933a1  mov     r9, r14
0x1402933a4  mov     r8, rbp
0x1402933a7  mov     rdx, rbx
0x1402933aa  mov     rcx, rdi
0x1402933ad  call    _o_wcsncpy_s_0
0x1402933b2  test    eax, eax
0x1402933b4  jnz     loc_14029345C
0x1402933ba  lea     r8, aLog2; ".LOG2"
0x1402933c1  mov     rdx, rbx; SizeInWords
0x1402933c4  mov     rcx, rdi; Destination
0x1402933c7  call    wcscat_s
0x1402933cc  test    eax, eax
0x1402933ce  jnz     loc_14029345C
0x1402933d4  mov     [r13+0], rsi
0x1402933d8  xor     esi, esi
0x1402933da  mov     [r13+8], rdi
0x1402933de  xor     edi, edi
0x1402933e0  xor     ebx, ebx
0x1402933e2  jmp     loc_140293468
0x1402933e7  call    cs:__imp_GetLastError
0x1402933ee  nop     dword ptr [rax+rax+00h]
0x1402933f3  mov     ebx, eax
0x1402933f5  jmp     short loc_140293468
0x1402933f7  mov     edx, 100h; MaxCount
0x1402933fc  mov     rcx, rbx; Source
0x1402933ff  call    cs:__imp_wcsnlen
0x140293406  nop     dword ptr [rax+rax+00h]
0x14029340b  mov     r15d, 10h
0x140293411  mov     r14, rax
0x140293414  mov     edx, r15d; Alignment
0x140293417  lea     r12, ds:2[rax*2]
0x14029341f  mov     rcx, r12; Size
0x140293422  call    _o__aligned_malloc_0
0x140293427  mov     rbp, rax
0x14029342a  test    rax, rax
0x14029342d  jz      loc_1402932C6
0x140293433  mov     r8, r12; Size
0x140293436  xor     edx, edx; Val
0x140293438  mov     rcx, rax; void *
0x14029343b  call    memset_0
0x140293440  shr     r12, 1
0x140293443  mov     r9, r14
0x140293446  mov     rdx, r12
0x140293449  mov     r8, rbx
0x14029344c  mov     rcx, rbp
0x14029344f  call    _o_wcsncpy_s_0
0x140293454  test    eax, eax
0x140293456  jz      loc_140293312
0x14029345c  mov     ebx, 54Fh
0x140293461  jmp     short loc_140293468
0x140293463  mov     ebx, 8
0x140293468  mov     rcx, rbp
0x14029346b  call    ORFree
0x140293470  test    rsi, rsi
0x140293473  jz      short loc_14029347D
0x140293475  mov     rcx, rsi
0x140293478  call    ORFree
0x14029347d  test    rdi, rdi
0x140293480  jz      short loc_14029348A
0x140293482  mov     rcx, rdi
0x140293485  call    ORFree
0x14029348a  mov     eax, ebx
0x14029348c  add     rsp, 28h
0x140293490  pop     r15
0x140293492  pop     r14
0x140293494  pop     r13
0x140293496  pop     r12
0x140293498  pop     rdi
0x140293499  pop     rsi
0x14029349a  pop     rbp
0x14029349b  pop     rbx
0x14029349c  retn
```
