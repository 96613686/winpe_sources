# mmioRenameA

- ea: `0x180012370`
- end: `0x1800124c9`
- name: `mmioRenameA`
- size: `345`
- prototype: `MMRESULT __stdcall(LPCSTR pszFileName, LPCSTR pszNewFileName, LPCMMIOINFO pmmioinfo, DWORD fdwRename)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800106c0`
- `0x18001102a`
- `0x180011a18`
- `0x180012370`
- `0x180012bc8`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012464`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012490`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800124a2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012464`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012490`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800124a2`

## pseudocode

```c
MMRESULT __stdcall mmioRenameA(LPCSTR pszFileName, LPCSTR pszNewFileName, LPCMMIOINFO pmmioinfo, DWORD fdwRename)
{
  __int128 v7; // xmm0
  __int128 v8; // xmm1
  __int128 v9; // xmm0
  __int128 v10; // xmm1
  __int128 v11; // xmm0
  __int128 v12; // xmm1
  const wchar_t *v13; // rax
  wchar_t *v14; // rbx
  MMRESULT v16; // esi
  void *v17; // rdi
  _OWORD v18[6]; // [rsp+30h] [rbp-39h] BYREF
  int hmmio_high; // [rsp+90h] [rbp+27h]

  memset_0(v18, 0, 0x64u);
  if ( pmmioinfo )
  {
    v7 = *(_OWORD *)&pmmioinfo->dwFlags;
    v8 = *(_OWORD *)&pmmioinfo->wErrorRet;
    hmmio_high = HIDWORD(pmmioinfo->hmmio);
    v18[0] = v7;
    v9 = *(_OWORD *)&pmmioinfo->pchBuffer;
    v18[1] = v8;
    v10 = *(_OWORD *)&pmmioinfo->pchEndRead;
    v18[2] = v9;
    v11 = *(_OWORD *)&pmmioinfo->lBufOffset;
    v18[3] = v10;
    v12 = *(_OWORD *)&pmmioinfo->adwInfo[2];
    v18[4] = v11;
    v18[5] = v12;
  }
  v13 = (const wchar_t *)AllocUnicodeStr(pszFileName);
  v14 = (wchar_t *)v13;
  if ( !v13 )
    return 258;
  SetIOProc(v13, (__int64)v18);
  if ( (v18[0] & 0x1000000) != 0
    || *((__int64 (__fastcall **)(char *, int, void *, const WCHAR *))&v18[0] + 1) == mmioDOSIOProc
    || *((__int64 (__fastcall **)(char *, unsigned int, __int64, __int64))&v18[0] + 1) == mmioMEMIOProc )
  {
    v17 = (void *)AllocUnicodeStr(pszNewFileName);
    if ( !v17 )
    {
      HeapFree(hHeap, 0, v14);
      return 258;
    }
    v16 = (*((__int64 (__fastcall **)(_OWORD *, __int64, wchar_t *, void *))&v18[0] + 1))(v18, 6, v14, v17);
    HeapFree(hHeap, 0, v17);
  }
  else
  {
    v16 = (*((__int64 (__fastcall **)(_OWORD *, __int64, LPCSTR, LPCSTR))&v18[0] + 1))(
            v18,
            6,
            pszFileName,
            pszNewFileName);
  }
  HeapFree(hHeap, 0, v14);
  return v16;
}

```

## disassembly

```asm
0x180012370  mov     [rsp-8+arg_18], rbx
0x180012375  push    rbp
0x180012376  push    rsi
0x180012377  push    rdi
0x180012378  lea     rbp, [rsp-47h]
0x18001237d  sub     rsp, 0B0h
0x180012384  mov     rax, cs:__security_cookie
0x18001238b  xor     rax, rsp
0x18001238e  mov     [rbp+57h+var_20], rax
0x180012392  mov     rsi, rdx
0x180012395  mov     rbx, r8
0x180012398  xor     edx, edx; Val
0x18001239a  mov     rdi, rcx
0x18001239d  lea     rcx, [rbp+57h+var_90]; void *
0x1800123a1  lea     r8d, [rdx+64h]; Size
0x1800123a5  call    memset_0
0x1800123aa  test    rbx, rbx
0x1800123ad  jz      short loc_1800123E4
0x1800123af  movups  xmm0, xmmword ptr [rbx]
0x1800123b2  mov     eax, [rbx+60h]
0x1800123b5  movups  xmm1, xmmword ptr [rbx+10h]
0x1800123b9  mov     [rbp+57h+var_30], eax
0x1800123bc  movaps  [rbp+57h+var_90], xmm0
0x1800123c0  movups  xmm0, xmmword ptr [rbx+20h]
0x1800123c4  movaps  [rbp+57h+var_80], xmm1
0x1800123c8  movups  xmm1, xmmword ptr [rbx+30h]
0x1800123cc  movaps  [rbp+57h+var_70], xmm0
0x1800123d0  movups  xmm0, xmmword ptr [rbx+40h]
0x1800123d4  movaps  [rbp+57h+var_60], xmm1
0x1800123d8  movups  xmm1, xmmword ptr [rbx+50h]
0x1800123dc  movaps  [rbp+57h+var_50], xmm0
0x1800123e0  movaps  [rbp+57h+var_40], xmm1
0x1800123e4  mov     rcx, rdi
0x1800123e7  call    AllocUnicodeStr
0x1800123ec  mov     rbx, rax
0x1800123ef  test    rax, rax
0x1800123f2  jnz     short loc_1800123FE
0x1800123f4  mov     eax, 102h
0x1800123f9  jmp     loc_1800124AA
0x1800123fe  lea     rdx, [rbp+57h+var_90]
0x180012402  mov     rcx, rbx
0x180012405  call    SetIOProc
0x18001240a  test    dword ptr [rbp+57h+var_90], 1000000h
0x180012411  jnz     short loc_180012448
0x180012413  mov     rax, qword ptr [rbp+57h+var_90+8]
0x180012417  lea     rcx, ?mmioDOSIOProc@@YA_JPEADI_J1@Z; mmioDOSIOProc(char *,uint,__int64,__int64)
0x18001241e  cmp     rax, rcx
0x180012421  jz      short loc_180012448
0x180012423  lea     rcx, ?mmioMEMIOProc@@YA_JPEADI_J1@Z; mmioMEMIOProc(char *,uint,__int64,__int64)
0x18001242a  cmp     rax, rcx
0x18001242d  jz      short loc_180012448
0x18001242f  mov     r9, rsi
0x180012432  lea     rcx, [rbp+57h+var_90]
0x180012436  mov     r8, rdi
0x180012439  mov     edx, 6
0x18001243e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012443  mov     rsi, rax
0x180012446  jmp     short loc_180012496
0x180012448  mov     rcx, rsi
0x18001244b  call    AllocUnicodeStr
0x180012450  mov     rdi, rax
0x180012453  mov     r8, rbx; lpMem
0x180012456  test    rax, rax
0x180012459  jnz     short loc_18001246C
0x18001245b  mov     rcx, cs:hHeap; hHeap
0x180012462  xor     edx, edx; dwFlags
0x180012464  call    cs:__imp_HeapFree
0x18001246a  jmp     short loc_1800123F4
0x18001246c  mov     rax, qword ptr [rbp+57h+var_90+8]
0x180012470  lea     rcx, [rbp+57h+var_90]
0x180012474  mov     r9, rdi
0x180012477  mov     edx, 6
0x18001247c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012481  mov     rcx, cs:hHeap; hHeap
0x180012488  mov     r8, rdi; lpMem
0x18001248b  xor     edx, edx; dwFlags
0x18001248d  mov     rsi, rax
0x180012490  call    cs:__imp_HeapFree
0x180012496  mov     rcx, cs:hHeap; hHeap
0x18001249d  mov     r8, rbx; lpMem
0x1800124a0  xor     edx, edx; dwFlags
0x1800124a2  call    cs:__imp_HeapFree
0x1800124a8  mov     eax, esi
0x1800124aa  mov     rcx, [rbp+57h+var_20]
0x1800124ae  xor     rcx, rsp; StackCookie
0x1800124b1  call    __security_check_cookie
0x1800124b6  mov     rbx, [rsp+0C0h+arg_18]
0x1800124be  add     rsp, 0B0h
0x1800124c5  pop     rdi
0x1800124c6  pop     rsi
0x1800124c7  pop     rbp
0x1800124c8  retn
```
