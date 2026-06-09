# VerifyPathRedirectionByHandle

- ea: `0x18000c580`
- end: `0x18000c7cb`
- name: `VerifyPathRedirectionByHandle`
- size: `587`
- prototype: `_BOOL8 __fastcall(char *hFile, WCHAR *lpFileName, BOOL *, wchar_t **)`
- caller_count: `2`
- callee_count: `8`
- tags: `reparse_path`

## callers

- `0x18000aa40`
- `0x18000b380`

## callees

- `0x180009b9c`
- `0x180009d30`
- `0x180009dd4`
- `0x18000a780`
- `0x18000c3b0`
- `0x18000c580`
- `0x1800131ae`
- `0x1800131e0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000c6e5`
- `msvcrt!_wcsicmp` at `0x18000c6e5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c791`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c7a5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c791`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c7a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c700`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c700`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c667`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c67b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c730`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c749`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c762`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c77b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c667`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c67b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c730`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c749`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c762`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c77b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c675`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c689`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c73e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c757`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c770`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c789`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c675`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c689`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c73e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c757`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c770`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c789`

## pseudocode

```c
_BOOL8 __fastcall VerifyPathRedirectionByHandle(char *hFile, WCHAR *lpFileName, BOOL *a3, wchar_t **a4)
{
  WCHAR *v6; // r14
  __int64 v8; // rax
  void *v9; // rbx
  const wchar_t *v10; // rax
  wchar_t *v11; // rdi
  __int64 v12; // rax
  void *v13; // rsi
  HANDLE v14; // rax
  HANDLE ProcessHeap; // rax
  wchar_t *v16; // r15
  DWORD LastError; // ebp
  BOOL v18; // r14d
  HANDLE v19; // rax
  HANDLE v20; // rax
  HANDLE v21; // rax
  HANDLE v22; // rax
  wchar_t String2[8]; // [rsp+30h] [rbp-68h] BYREF

  v6 = lpFileName;
  if ( (unsigned __int64)(hFile - 1) > 0xFFFFFFFFFFFFFFFDuLL || !lpFileName || !a3 )
  {
    SetLastError(0x57u);
    return 0;
  }
  wcscpy(String2, L"\\\\?\\");
  if ( !wcsncmp_0(lpFileName, String2, 4u) )
  {
    v11 = 0;
    v13 = 0;
    v9 = 0;
  }
  else
  {
    v8 = FormFullPathName(v6);
    v9 = (void *)v8;
    if ( !v8 )
      return 0;
    v10 = (const wchar_t *)FormLongPathName(v8);
    v11 = (wchar_t *)v10;
    if ( !v10 )
    {
LABEL_11:
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v9);
      return 0;
    }
    if ( wcsncmp_0(v10, String2, 4u) )
    {
      v12 = BuildPath(String2, (STRSAFE_PCNZWCH)v9);
      v13 = (void *)v12;
      if ( v12 )
      {
        v6 = (WCHAR *)v12;
        goto LABEL_14;
      }
      v14 = GetProcessHeap();
      HeapFree(v14, 0, v11);
      goto LABEL_11;
    }
    v6 = v11;
    v13 = 0;
  }
LABEL_14:
  GetFinalPathFlags(v6);
  v16 = (wchar_t *)FormFinalPathNameByHandle(hFile);
  if ( v16 )
  {
    LastError = 0;
    v18 = _wcsicmp(v16, v6) == 0;
LABEL_17:
    *a3 = v18;
    if ( a4 )
    {
      if ( v18 )
      {
        *a4 = 0;
      }
      else
      {
        *a4 = v16;
        v16 = 0;
      }
    }
    if ( v16 )
    {
      v19 = GetProcessHeap();
      HeapFree(v19, 0, v16);
    }
    goto LABEL_23;
  }
  v18 = 0;
  LastError = GetLastError();
  if ( !LastError )
    goto LABEL_17;
LABEL_23:
  if ( v13 )
  {
    v20 = GetProcessHeap();
    HeapFree(v20, 0, v13);
  }
  if ( v11 )
  {
    v21 = GetProcessHeap();
    HeapFree(v21, 0, v11);
  }
  if ( v9 )
  {
    v22 = GetProcessHeap();
    HeapFree(v22, 0, v9);
  }
  SetLastError(LastError);
  return LastError == 0;
}

```

## disassembly

```asm
0x18000c580  push    rbx
0x18000c582  push    rbp
0x18000c583  push    rsi
0x18000c584  push    rdi
0x18000c585  push    r12
0x18000c587  push    r13
0x18000c589  push    r14
0x18000c58b  push    r15
0x18000c58d  sub     rsp, 58h
0x18000c591  mov     rax, cs:__security_cookie
0x18000c598  xor     rax, rsp
0x18000c59b  mov     [rsp+98h+var_58], rax
0x18000c5a0  lea     rax, [rcx-1]
0x18000c5a4  mov     [rsp+98h+var_78], 0
0x18000c5ad  mov     [rsp+98h+var_70], 0
0x18000c5b6  mov     r12, r9
0x18000c5b9  mov     r13, r8
0x18000c5bc  mov     r14, rdx
0x18000c5bf  mov     rbp, rcx
0x18000c5c2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000c5c6  ja      loc_18000C7A0
0x18000c5cc  test    rdx, rdx
0x18000c5cf  jz      loc_18000C7A0
0x18000c5d5  test    r8, r8
0x18000c5d8  jz      loc_18000C7A0
0x18000c5de  movsd   xmm0, qword ptr cs:pszSrc; "\\\\?\\"
0x18000c5e6  lea     rdx, [rsp+98h+String2]; String2
0x18000c5eb  movzx   eax, word ptr cs:pszSrc+8; ""
0x18000c5f2  mov     esi, 4
0x18000c5f7  mov     r8d, esi; MaxCount
0x18000c5fa  movsd   qword ptr [rsp+98h+String2], xmm0
0x18000c600  mov     rcx, r14; String1
0x18000c603  mov     [rsp+98h+var_60], ax
0x18000c608  call    wcsncmp_0
0x18000c60d  test    eax, eax
0x18000c60f  jz      loc_18000C69B
0x18000c615  mov     rcx, r14; lpFileName
0x18000c618  call    FormFullPathName
0x18000c61d  mov     rbx, rax
0x18000c620  test    rax, rax
0x18000c623  jz      loc_18000C7AB
0x18000c629  mov     rcx, rax
0x18000c62c  call    FormLongPathName
0x18000c631  mov     rdi, rax
0x18000c634  test    rax, rax
0x18000c637  jz      short loc_18000C67B
0x18000c639  mov     r8d, esi; MaxCount
0x18000c63c  lea     rdx, [rsp+98h+String2]; String2
0x18000c641  mov     rcx, rax; String1
0x18000c644  call    wcsncmp_0
0x18000c649  test    eax, eax
0x18000c64b  jz      short loc_18000C694
0x18000c64d  mov     rdx, rbx; STRSAFE_PCNZWCH
0x18000c650  lea     rcx, [rsp+98h+String2]; pszSrc
0x18000c655  call    BuildPath
0x18000c65a  mov     rsi, rax
0x18000c65d  test    rax, rax
0x18000c660  jz      short loc_18000C667
0x18000c662  mov     r14, rax
0x18000c665  jmp     short loc_18000C6A1
0x18000c667  call    cs:__imp_GetProcessHeap
0x18000c66d  mov     r8, rdi; lpMem
0x18000c670  xor     edx, edx; dwFlags
0x18000c672  mov     rcx, rax; hHeap
0x18000c675  call    cs:__imp_HeapFree
0x18000c67b  call    cs:__imp_GetProcessHeap
0x18000c681  mov     r8, rbx; lpMem
0x18000c684  xor     edx, edx; dwFlags
0x18000c686  mov     rcx, rax; hHeap
0x18000c689  call    cs:__imp_HeapFree
0x18000c68f  jmp     loc_18000C7AB
0x18000c694  mov     r14, rdi
0x18000c697  xor     esi, esi
0x18000c699  jmp     short loc_18000C6A1
0x18000c69b  xor     edi, edi
0x18000c69d  xor     esi, esi
0x18000c69f  xor     ebx, ebx
0x18000c6a1  lea     r8, [rsp+98h+var_70]
0x18000c6a6  mov     rcx, r14; String1
0x18000c6a9  lea     rdx, [rsp+98h+var_78]
0x18000c6ae  call    GetFinalPathFlags
0x18000c6b3  mov     edx, eax
0x18000c6b5  mov     rcx, rbp; hFile
0x18000c6b8  call    FormFinalPathNameByHandle
0x18000c6bd  mov     r15, rax
0x18000c6c0  test    rax, rax
0x18000c6c3  jz      short loc_18000C6FD
0x18000c6c5  mov     rax, [rsp+98h+var_78]
0x18000c6ca  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000c6ce  jz      short loc_18000C6F6
0x18000c6d0  mov     rcx, [rsp+98h+var_70]
0x18000c6d5  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000c6d9  jz      short loc_18000C6F6
0x18000c6db  lea     rdx, [r14+rax*2]; String2
0x18000c6df  xor     ebp, ebp
0x18000c6e1  lea     rcx, [r15+rcx*2]; String1
0x18000c6e5  call    cs:__imp__wcsicmp
0x18000c6eb  xor     r14d, r14d
0x18000c6ee  test    eax, eax
0x18000c6f0  setz    r14b
0x18000c6f4  jmp     short loc_18000C70C
0x18000c6f6  mov     ebp, 307h
0x18000c6fb  jmp     short loc_18000C730
0x18000c6fd  xor     r14d, r14d
0x18000c700  call    cs:__imp_GetLastError
0x18000c706  mov     ebp, eax
0x18000c708  test    eax, eax
0x18000c70a  jnz     short loc_18000C744
0x18000c70c  mov     [r13+0], r14d
0x18000c710  test    r12, r12
0x18000c713  jz      short loc_18000C72B
0x18000c715  test    r14d, r14d
0x18000c718  jnz     short loc_18000C723
0x18000c71a  mov     [r12], r15
0x18000c71e  xor     r15d, r15d
0x18000c721  jmp     short loc_18000C72B
0x18000c723  mov     qword ptr [r12], 0
0x18000c72b  test    r15, r15
0x18000c72e  jz      short loc_18000C744
0x18000c730  call    cs:__imp_GetProcessHeap
0x18000c736  mov     r8, r15; lpMem
0x18000c739  xor     edx, edx; dwFlags
0x18000c73b  mov     rcx, rax; hHeap
0x18000c73e  call    cs:__imp_HeapFree
0x18000c744  test    rsi, rsi
0x18000c747  jz      short loc_18000C75D
0x18000c749  call    cs:__imp_GetProcessHeap
0x18000c74f  mov     r8, rsi; lpMem
0x18000c752  xor     edx, edx; dwFlags
0x18000c754  mov     rcx, rax; hHeap
0x18000c757  call    cs:__imp_HeapFree
0x18000c75d  test    rdi, rdi
0x18000c760  jz      short loc_18000C776
0x18000c762  call    cs:__imp_GetProcessHeap
0x18000c768  mov     r8, rdi; lpMem
0x18000c76b  xor     edx, edx; dwFlags
0x18000c76d  mov     rcx, rax; hHeap
0x18000c770  call    cs:__imp_HeapFree
0x18000c776  test    rbx, rbx
0x18000c779  jz      short loc_18000C78F
0x18000c77b  call    cs:__imp_GetProcessHeap
0x18000c781  mov     r8, rbx; lpMem
0x18000c784  xor     edx, edx; dwFlags
0x18000c786  mov     rcx, rax; hHeap
0x18000c789  call    cs:__imp_HeapFree
0x18000c78f  mov     ecx, ebp; dwErrCode
0x18000c791  call    cs:__imp_SetLastError
0x18000c797  xor     eax, eax
0x18000c799  test    ebp, ebp
0x18000c79b  setz    al
0x18000c79e  jmp     short loc_18000C7AD
0x18000c7a0  mov     ecx, 57h ; 'W'; dwErrCode
0x18000c7a5  call    cs:__imp_SetLastError
0x18000c7ab  xor     eax, eax
0x18000c7ad  mov     rcx, [rsp+98h+var_58]
0x18000c7b2  xor     rcx, rsp; StackCookie
0x18000c7b5  call    __security_check_cookie
0x18000c7ba  add     rsp, 58h
0x18000c7be  pop     r15
0x18000c7c0  pop     r14
0x18000c7c2  pop     r13
0x18000c7c4  pop     r12
0x18000c7c6  pop     rdi
0x18000c7c7  pop     rsi
0x18000c7c8  pop     rbp
0x18000c7c9  pop     rbx
0x18000c7ca  retn
```
