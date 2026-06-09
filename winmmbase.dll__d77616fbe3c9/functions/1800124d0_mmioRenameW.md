# mmioRenameW

- ea: `0x1800124d0`
- end: `0x18001262b`
- name: `mmioRenameW`
- size: `347`
- prototype: `MMRESULT __stdcall(LPCWSTR pszFileName, LPCWSTR pszNewFileName, LPCMMIOINFO pmmioinfo, DWORD fdwRename)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800106c0`
- `0x18001102a`
- `0x180011a18`
- `0x1800124d0`
- `0x180012b68`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800125b0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800125dc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800125ee`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800125b0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800125dc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800125ee`

## pseudocode

```c
MMRESULT __stdcall mmioRenameW(LPCWSTR pszFileName, LPCWSTR pszNewFileName, LPCMMIOINFO pmmioinfo, DWORD fdwRename)
{
  __int128 v7; // xmm0
  __int128 v8; // xmm1
  __int128 v9; // xmm0
  __int128 v10; // xmm1
  __int128 v11; // xmm0
  __int128 v12; // xmm1
  void *v13; // rdi
  void *v15; // rsi
  MMRESULT v16; // ebx
  _OWORD v17[6]; // [rsp+30h] [rbp-39h] BYREF
  int hmmio_high; // [rsp+90h] [rbp+27h]

  memset_0(v17, 0, 0x64u);
  if ( pmmioinfo )
  {
    v7 = *(_OWORD *)&pmmioinfo->dwFlags;
    v8 = *(_OWORD *)&pmmioinfo->wErrorRet;
    hmmio_high = HIDWORD(pmmioinfo->hmmio);
    v17[0] = v7;
    v9 = *(_OWORD *)&pmmioinfo->pchBuffer;
    v17[1] = v8;
    v10 = *(_OWORD *)&pmmioinfo->pchEndRead;
    v17[2] = v9;
    v11 = *(_OWORD *)&pmmioinfo->lBufOffset;
    v17[3] = v10;
    v12 = *(_OWORD *)&pmmioinfo->adwInfo[2];
    v17[4] = v11;
    v17[5] = v12;
  }
  SetIOProc(pszFileName, (__int64)v17);
  if ( (v17[0] & 0x1000000) != 0
    || *((__int64 (__fastcall **)(char *, int, void *, const WCHAR *))&v17[0] + 1) == mmioDOSIOProc
    || *((__int64 (__fastcall **)(char *, unsigned int, __int64, __int64))&v17[0] + 1) == mmioMEMIOProc )
  {
    return (*((__int64 (__fastcall **)(_OWORD *, __int64, LPCWSTR, LPCWSTR))&v17[0] + 1))(
             v17,
             6,
             pszFileName,
             pszNewFileName);
  }
  v13 = (void *)AllocAsciiStr(pszFileName);
  if ( !v13 )
    return 258;
  v15 = (void *)AllocAsciiStr(pszNewFileName);
  if ( !v15 )
  {
    HeapFree(hHeap, 0, v13);
    return 258;
  }
  v16 = (*((__int64 (__fastcall **)(_OWORD *, __int64, void *, void *))&v17[0] + 1))(v17, 6, v13, v15);
  HeapFree(hHeap, 0, v13);
  HeapFree(hHeap, 0, v15);
  return v16;
}

```

## disassembly

```asm
0x1800124d0  mov     [rsp-8+arg_18], rbx
0x1800124d5  push    rbp
0x1800124d6  push    rsi
0x1800124d7  push    rdi
0x1800124d8  lea     rbp, [rsp-47h]
0x1800124dd  sub     rsp, 0B0h
0x1800124e4  mov     rax, cs:__security_cookie
0x1800124eb  xor     rax, rsp
0x1800124ee  mov     [rbp+57h+var_20], rax
0x1800124f2  mov     rsi, rdx
0x1800124f5  mov     rbx, r8
0x1800124f8  xor     edx, edx; Val
0x1800124fa  mov     rdi, rcx
0x1800124fd  lea     rcx, [rbp+57h+var_90]; void *
0x180012501  lea     r8d, [rdx+64h]; Size
0x180012505  call    memset_0
0x18001250a  test    rbx, rbx
0x18001250d  jz      short loc_180012544
0x18001250f  movups  xmm0, xmmword ptr [rbx]
0x180012512  mov     eax, [rbx+60h]
0x180012515  movups  xmm1, xmmword ptr [rbx+10h]
0x180012519  mov     [rbp+57h+var_30], eax
0x18001251c  movaps  [rbp+57h+var_90], xmm0
0x180012520  movups  xmm0, xmmword ptr [rbx+20h]
0x180012524  movaps  [rbp+57h+var_80], xmm1
0x180012528  movups  xmm1, xmmword ptr [rbx+30h]
0x18001252c  movaps  [rbp+57h+var_70], xmm0
0x180012530  movups  xmm0, xmmword ptr [rbx+40h]
0x180012534  movaps  [rbp+57h+var_60], xmm1
0x180012538  movups  xmm1, xmmword ptr [rbx+50h]
0x18001253c  movaps  [rbp+57h+var_50], xmm0
0x180012540  movaps  [rbp+57h+var_40], xmm1
0x180012544  lea     rdx, [rbp+57h+var_90]
0x180012548  mov     rcx, rdi
0x18001254b  call    SetIOProc
0x180012550  test    dword ptr [rbp+57h+var_90], 1000000h
0x180012557  mov     rax, qword ptr [rbp+57h+var_90+8]
0x18001255b  jnz     loc_1800125F8
0x180012561  lea     rcx, ?mmioDOSIOProc@@YA_JPEADI_J1@Z; mmioDOSIOProc(char *,uint,__int64,__int64)
0x180012568  cmp     rax, rcx
0x18001256b  jz      loc_1800125F8
0x180012571  lea     rcx, ?mmioMEMIOProc@@YA_JPEADI_J1@Z; mmioMEMIOProc(char *,uint,__int64,__int64)
0x180012578  cmp     rax, rcx
0x18001257b  jz      short loc_1800125F8
0x18001257d  mov     rcx, rdi
0x180012580  call    AllocAsciiStr
0x180012585  mov     rdi, rax
0x180012588  test    rax, rax
0x18001258b  jnz     short loc_180012594
0x18001258d  mov     eax, 102h
0x180012592  jmp     short loc_18001260C
0x180012594  mov     rcx, rsi
0x180012597  call    AllocAsciiStr
0x18001259c  mov     rsi, rax
0x18001259f  mov     r8, rdi; lpMem
0x1800125a2  test    rax, rax
0x1800125a5  jnz     short loc_1800125B8
0x1800125a7  mov     rcx, cs:hHeap; hHeap
0x1800125ae  xor     edx, edx; dwFlags
0x1800125b0  call    cs:__imp_HeapFree
0x1800125b6  jmp     short loc_18001258D
0x1800125b8  mov     rax, qword ptr [rbp+57h+var_90+8]
0x1800125bc  lea     rcx, [rbp+57h+var_90]
0x1800125c0  mov     r9, rsi
0x1800125c3  mov     edx, 6
0x1800125c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800125cd  mov     rcx, cs:hHeap; hHeap
0x1800125d4  mov     r8, rdi; lpMem
0x1800125d7  xor     edx, edx; dwFlags
0x1800125d9  mov     rbx, rax
0x1800125dc  call    cs:__imp_HeapFree
0x1800125e2  mov     rcx, cs:hHeap; hHeap
0x1800125e9  mov     r8, rsi; lpMem
0x1800125ec  xor     edx, edx; dwFlags
0x1800125ee  call    cs:__imp_HeapFree
0x1800125f4  mov     eax, ebx
0x1800125f6  jmp     short loc_18001260C
0x1800125f8  mov     r9, rsi
0x1800125fb  lea     rcx, [rbp+57h+var_90]
0x1800125ff  mov     r8, rdi
0x180012602  mov     edx, 6
0x180012607  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001260c  mov     rcx, [rbp+57h+var_20]
0x180012610  xor     rcx, rsp; StackCookie
0x180012613  call    __security_check_cookie
0x180012618  mov     rbx, [rsp+0C0h+arg_18]
0x180012620  add     rsp, 0B0h
0x180012627  pop     rdi
0x180012628  pop     rsi
0x180012629  pop     rbp
0x18001262a  retn
```
