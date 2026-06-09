# SDiagPrviBuildPath(ushort const *,ushort const *,ushort * *)

- ea: `0x180002840`
- end: `0x180002a48`
- name: `?SDiagPrviBuildPath@@YAJPEBG0PEAPEAG@Z`
- size: `520`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180011d2c`

## callees

- `0x180002840`
- `0x180002ce0`
- `0x18000348c`
- `0x1800034e4`
- `0x1800180be`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800028b1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000290c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000295b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800028b1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000290c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000295b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800029fc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002a15`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002a32`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800029fc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002a15`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002a32`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000289e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800028fb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002948`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800029ee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002a07`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002a24`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000289e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800028fb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002948`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800029ee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002a07`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002a24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000298e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800029ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000298e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800029ce`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x1800029c4`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x1800029c4`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180002984`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180002984`

## pseudocode

```c
__int64 __fastcall SDiagPrviBuildPath(STRSAFE_PCNZWCH pszSrc, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  int v5; // ebx
  HANDLE ProcessHeap; // rax
  wchar_t *v7; // rax
  wchar_t *v8; // r15
  WCHAR *v9; // rdi
  size_t *v10; // r8
  HANDLE v11; // rax
  wchar_t *v12; // rax
  wchar_t *v13; // rsi
  unsigned __int64 v14; // rdx
  HANDLE v15; // rax
  WCHAR *v16; // rax
  DWORD FullPathNameW; // eax
  signed int v18; // eax
  signed int LastError; // eax
  HANDLE v20; // rax
  HANDLE v21; // rax
  HANDLE v22; // rax
  SIZE_T dwBytes; // [rsp+78h] [rbp+10h] BYREF

  dwBytes = 0;
  if ( !pszSrc || !a3 )
    return (unsigned int)-2147024809;
  *a3 = 0;
  v5 = ULongLongMult(0x104u, 2u, &dwBytes);
  if ( v5 < 0 )
    return (unsigned int)v5;
  ProcessHeap = GetProcessHeap();
  v7 = (wchar_t *)HeapAlloc(ProcessHeap, 8u, dwBytes);
  v8 = v7;
  if ( !v7 )
    return (unsigned int)-2147024882;
  v9 = 0;
  memset_0(v7, 0, dwBytes);
  v5 = StringCopyWorkerW(v8, 0x104u, v10, pszSrc, 0x7FFFFFFEu);
  if ( v5 < 0 )
  {
    v13 = 0;
    goto LABEL_26;
  }
  v11 = GetProcessHeap();
  v12 = (wchar_t *)HeapAlloc(v11, 8u, dwBytes);
  v13 = v12;
  if ( v12 )
  {
    memset_0(v12, 0, dwBytes);
    v5 = SDiagPrviExpandVariables(v13, v14, v8);
    if ( v5 < 0 )
      goto LABEL_26;
    v15 = GetProcessHeap();
    v16 = (WCHAR *)HeapAlloc(v15, 8u, dwBytes);
    v9 = v16;
    if ( v16 )
    {
      memset_0(v16, 0, dwBytes);
      FullPathNameW = GetFullPathNameW(v13, 0x104u, v9, 0);
      if ( FullPathNameW )
      {
        if ( FullPathNameW < 0x104 )
        {
          if ( GetLongPathNameW(v9, v9, 0x104u) )
            goto LABEL_24;
          LastError = GetLastError();
          v5 = LastError;
          if ( LastError > 0 )
            v5 = (unsigned __int16)LastError | 0x80070000;
          if ( v5 >= 0 )
LABEL_24:
            *a3 = v9;
        }
        else
        {
          v5 = -2147024774;
        }
      }
      else
      {
        v18 = GetLastError();
        v5 = v18;
        if ( v18 > 0 )
          v5 = (unsigned __int16)v18 | 0x80070000;
        if ( v5 >= 0 )
          v5 = -2147467259;
      }
      goto LABEL_26;
    }
  }
  v5 = -2147024882;
LABEL_26:
  v20 = GetProcessHeap();
  HeapFree(v20, 0, v8);
  if ( v13 )
  {
    v21 = GetProcessHeap();
    HeapFree(v21, 0, v13);
  }
  if ( v5 < 0 && v9 )
  {
    v22 = GetProcessHeap();
    HeapFree(v22, 0, v9);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180002840  mov     [rsp+dwBytes], rdx
0x180002845  push    rbx
0x180002846  push    rsi
0x180002847  push    rdi
0x180002848  push    r12
0x18000284a  push    r14
0x18000284c  push    r15
0x18000284e  sub     rsp, 38h
0x180002852  mov     [rsp+68h+dwBytes], 0
0x18000285b  mov     r14, r8
0x18000285e  mov     rsi, rcx
0x180002861  test    rcx, rcx
0x180002864  jnz     short loc_180002870
0x180002866  mov     ebx, 80070057h
0x18000286b  jmp     loc_180002A38
0x180002870  test    r14, r14
0x180002873  jz      short loc_180002866
0x180002875  mov     qword ptr [r8], 0
0x18000287c  mov     r12d, 104h
0x180002882  mov     ecx, r12d; unsigned __int64
0x180002885  lea     r8, [rsp+68h+dwBytes]; unsigned __int64 *
0x18000288a  mov     edx, 2; unsigned __int64
0x18000288f  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180002894  mov     ebx, eax
0x180002896  test    eax, eax
0x180002898  js      loc_180002A38
0x18000289e  call    cs:__imp_GetProcessHeap
0x1800028a4  mov     r8, [rsp+68h+dwBytes]; dwBytes
0x1800028a9  mov     edx, 8; dwFlags
0x1800028ae  mov     rcx, rax; hHeap
0x1800028b1  call    cs:__imp_HeapAlloc
0x1800028b7  mov     r15, rax
0x1800028ba  test    rax, rax
0x1800028bd  jnz     short loc_1800028C9
0x1800028bf  mov     ebx, 8007000Eh
0x1800028c4  jmp     loc_180002A38
0x1800028c9  mov     r8, [rsp+68h+dwBytes]; Size
0x1800028ce  xor     edx, edx; Val
0x1800028d0  mov     rcx, r15; void *
0x1800028d3  xor     edi, edi
0x1800028d5  call    memset_0
0x1800028da  mov     r9, rsi; pszSrc
0x1800028dd  mov     [rsp+68h+cchToCopy], 7FFFFFFEh; cchToCopy
0x1800028e6  mov     rdx, r12; cchDest
0x1800028e9  mov     rcx, r15; pszDest
0x1800028ec  call    StringCopyWorkerW
0x1800028f1  mov     ebx, eax
0x1800028f3  test    eax, eax
0x1800028f5  js      loc_1800029EC
0x1800028fb  call    cs:__imp_GetProcessHeap
0x180002901  mov     r8, [rsp+68h+dwBytes]; dwBytes
0x180002906  lea     edx, [rdi+8]; dwFlags
0x180002909  mov     rcx, rax; hHeap
0x18000290c  call    cs:__imp_HeapAlloc
0x180002912  mov     rsi, rax
0x180002915  test    rax, rax
0x180002918  jnz     short loc_180002924
0x18000291a  mov     ebx, 8007000Eh
0x18000291f  jmp     loc_1800029EE
0x180002924  mov     r8, [rsp+68h+dwBytes]; Size
0x180002929  xor     edx, edx; Val
0x18000292b  mov     rcx, rsi; void *
0x18000292e  call    memset_0
0x180002933  mov     r8, r15; unsigned __int16 *
0x180002936  mov     rcx, rsi; pszDest
0x180002939  call    ?SDiagPrviExpandVariables@@YAJPEAG_KPEBG@Z; SDiagPrviExpandVariables(ushort *,unsigned __int64,ushort const *)
0x18000293e  mov     ebx, eax
0x180002940  test    eax, eax
0x180002942  js      loc_1800029EE
0x180002948  call    cs:__imp_GetProcessHeap
0x18000294e  mov     r8, [rsp+68h+dwBytes]; dwBytes
0x180002953  mov     edx, 8; dwFlags
0x180002958  mov     rcx, rax; hHeap
0x18000295b  call    cs:__imp_HeapAlloc
0x180002961  mov     rdi, rax
0x180002964  test    rax, rax
0x180002967  jz      short loc_18000291A
0x180002969  mov     r8, [rsp+68h+dwBytes]; Size
0x18000296e  xor     edx, edx; Val
0x180002970  mov     rcx, rax; void *
0x180002973  call    memset_0
0x180002978  xor     r9d, r9d; lpFilePart
0x18000297b  mov     r8, rdi; lpBuffer
0x18000297e  mov     edx, r12d; nBufferLength
0x180002981  mov     rcx, rsi; lpFileName
0x180002984  call    cs:__imp_GetFullPathNameW
0x18000298a  test    eax, eax
0x18000298c  jnz     short loc_1800029AF
0x18000298e  call    cs:__imp_GetLastError
0x180002994  mov     ebx, eax
0x180002996  test    eax, eax
0x180002998  jle     short loc_1800029A3
0x18000299a  movzx   ebx, ax
0x18000299d  or      ebx, 80070000h
0x1800029a3  test    ebx, ebx
0x1800029a5  mov     eax, 80004005h
0x1800029aa  cmovns  ebx, eax
0x1800029ad  jmp     short loc_1800029EE
0x1800029af  cmp     eax, r12d
0x1800029b2  jb      short loc_1800029BB
0x1800029b4  mov     ebx, 8007007Ah
0x1800029b9  jmp     short loc_1800029EE
0x1800029bb  mov     r8d, r12d; cchBuffer
0x1800029be  mov     rdx, rdi; lpszLongPath
0x1800029c1  mov     rcx, rdi; lpszShortPath
0x1800029c4  call    cs:__imp_GetLongPathNameW
0x1800029ca  test    eax, eax
0x1800029cc  jnz     short loc_1800029E7
0x1800029ce  call    cs:__imp_GetLastError
0x1800029d4  mov     ebx, eax
0x1800029d6  test    eax, eax
0x1800029d8  jle     short loc_1800029E3
0x1800029da  movzx   ebx, ax
0x1800029dd  or      ebx, 80070000h
0x1800029e3  test    ebx, ebx
0x1800029e5  js      short loc_1800029EE
0x1800029e7  mov     [r14], rdi
0x1800029ea  jmp     short loc_1800029EE
0x1800029ec  xor     esi, esi
0x1800029ee  call    cs:__imp_GetProcessHeap
0x1800029f4  mov     r8, r15; lpMem
0x1800029f7  xor     edx, edx; dwFlags
0x1800029f9  mov     rcx, rax; hHeap
0x1800029fc  call    cs:__imp_HeapFree
0x180002a02  test    rsi, rsi
0x180002a05  jz      short loc_180002A1B
0x180002a07  call    cs:__imp_GetProcessHeap
0x180002a0d  mov     r8, rsi; lpMem
0x180002a10  xor     edx, edx; dwFlags
0x180002a12  mov     rcx, rax; hHeap
0x180002a15  call    cs:__imp_HeapFree
0x180002a1b  test    ebx, ebx
0x180002a1d  jns     short loc_180002A38
0x180002a1f  test    rdi, rdi
0x180002a22  jz      short loc_180002A38
0x180002a24  call    cs:__imp_GetProcessHeap
0x180002a2a  mov     r8, rdi; lpMem
0x180002a2d  xor     edx, edx; dwFlags
0x180002a2f  mov     rcx, rax; hHeap
0x180002a32  call    cs:__imp_HeapFree
0x180002a38  mov     eax, ebx
0x180002a3a  add     rsp, 38h
0x180002a3e  pop     r15
0x180002a40  pop     r14
0x180002a42  pop     r12
0x180002a44  pop     rdi
0x180002a45  pop     rsi
0x180002a46  pop     rbx
0x180002a47  retn
```
