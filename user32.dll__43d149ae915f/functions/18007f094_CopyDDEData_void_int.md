# CopyDDEData(void *,int)

- ea: `0x18007f094`
- end: `0x18007f1fe`
- name: `?CopyDDEData@@YAPEAXPEAXH@Z`
- size: `362`
- prototype: `void *__fastcall(void *, int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1800470a0`
- `0x18007f094`
- `0x180090590`

## callees

- `0x18007ef60`
- `0x18007f094`
- `0x18007f204`
- `0x180096dad`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18007f0dc`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18007f196`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18007f1a8`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18007f0dc`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18007f196`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18007f1a8`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18007f0b3`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18007f0b3`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x18007f0a5`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x18007f0f0`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x18007f0a5`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x18007f0f0`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18007f0cb`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18007f0e4`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18007f185`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18007f0cb`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18007f0e4`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18007f185`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18007f19f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18007f1c5`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18007f1e1`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18007f1ea`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18007f19f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18007f1c5`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18007f1e1`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18007f1ea`
- `GDI32!CopyEnhMetaFileW` at `0x18007f14b`
- `GDI32!CopyEnhMetaFileW` at `0x18007f14b`
- `GDI32!CopyMetaFileW` at `0x18007f1b8`
- `GDI32!CopyMetaFileW` at `0x18007f1b8`

## pseudocode

```c
HGLOBAL __fastcall CopyDDEData(void *a1, int a2)
{
  SIZE_T v4; // rax
  HGLOBAL v5; // rbx
  char *v7; // rdi
  char *v8; // rsi
  size_t v9; // rax
  HENHMETAFILE v10; // rax
  void *v11; // rdi
  LPVOID v12; // rax

  v4 = GlobalSize(a1);
  v5 = GlobalAlloc(0x2002u, v4);
  if ( !v5 )
    return 0;
  v7 = (char *)GlobalLock(a1);
  if ( !v7 )
  {
    GlobalFree(v5);
    return 0;
  }
  v8 = (char *)GlobalLock(v5);
  v9 = GlobalSize(a1);
  memcpy_0(v8, v7, v9);
  if ( a2 )
    goto LABEL_22;
  switch ( *((_WORD *)v7 + 1) )
  {
    case 2:
      goto LABEL_20;
    case 3:
      goto LABEL_17;
    case 8:
      v10 = (HENHMETAFILE)CopyDDEData(*(void **)(v7 + 4), 1);
      goto LABEL_21;
    case 9:
      v10 = (HENHMETAFILE)CopyPalette(*(HPALETTE *)(v7 + 4));
      goto LABEL_21;
    case 0xE:
LABEL_14:
      v10 = CopyEnhMetaFileW(*(HENHMETAFILE *)(v7 + 4), 0);
LABEL_21:
      *(_QWORD *)(v8 + 4) = v10;
      goto LABEL_22;
    case 0x82:
LABEL_20:
      v10 = (HENHMETAFILE)CopyBitmap(*(HBITMAP *)(v7 + 4));
      goto LABEL_21;
  }
  if ( *((_WORD *)v7 + 1) != 131 )
  {
    if ( *((_WORD *)v7 + 1) == 142 )
      goto LABEL_14;
LABEL_22:
    GlobalUnlock(v5);
    goto LABEL_23;
  }
LABEL_17:
  v11 = CopyDDEData(*(void **)(v7 + 4), 1);
  v12 = GlobalLock(v11);
  if ( v12 )
  {
    *((_QWORD *)v12 + 2) = CopyMetaFileW(*((HMETAFILE *)v12 + 2), 0);
    GlobalUnlock(v11);
    *(_QWORD *)(v8 + 4) = v11;
    goto LABEL_22;
  }
  GlobalFree(v11);
  GlobalUnlock(v5);
  GlobalFree(v5);
  v5 = 0;
LABEL_23:
  GlobalUnlock(a1);
  return v5;
}

```

## disassembly

```asm
0x18007f094  push    rbx
0x18007f096  push    rbp
0x18007f097  push    rsi
0x18007f098  push    rdi
0x18007f099  push    r14
0x18007f09b  sub     rsp, 20h
0x18007f09f  mov     r14d, edx
0x18007f0a2  mov     rbp, rcx
0x18007f0a5  call    cs:__imp_GlobalSize
0x18007f0ab  mov     rdx, rax; dwBytes
0x18007f0ae  mov     ecx, 2002h; uFlags
0x18007f0b3  call    cs:__imp_GlobalAlloc
0x18007f0b9  mov     rbx, rax
0x18007f0bc  test    rax, rax
0x18007f0bf  jnz     short loc_18007F0C8
0x18007f0c1  xor     eax, eax
0x18007f0c3  jmp     loc_18007F1F3
0x18007f0c8  mov     rcx, rbp; hMem
0x18007f0cb  call    cs:__imp_GlobalLock
0x18007f0d1  mov     rdi, rax
0x18007f0d4  mov     rcx, rbx; hMem
0x18007f0d7  test    rax, rax
0x18007f0da  jnz     short loc_18007F0E4
0x18007f0dc  call    cs:__imp_GlobalFree
0x18007f0e2  jmp     short loc_18007F0C1
0x18007f0e4  call    cs:__imp_GlobalLock
0x18007f0ea  mov     rcx, rbp; hMem
0x18007f0ed  mov     rsi, rax
0x18007f0f0  call    cs:__imp_GlobalSize
0x18007f0f6  mov     rdx, rdi; Src
0x18007f0f9  mov     rcx, rsi; void *
0x18007f0fc  mov     r8, rax; Size
0x18007f0ff  call    memcpy_0
0x18007f104  test    r14d, r14d
0x18007f107  jnz     loc_18007F1DE
0x18007f10d  movzx   edx, word ptr [rdi+2]
0x18007f111  sub     edx, 2
0x18007f114  jz      loc_18007F1D1
0x18007f11a  sub     edx, 1
0x18007f11d  jz      short loc_18007F171
0x18007f11f  sub     edx, 5
0x18007f122  jz      short loc_18007F161
0x18007f124  sub     edx, 1
0x18007f127  jz      short loc_18007F156
0x18007f129  sub     edx, 5
0x18007f12c  jz      short loc_18007F145
0x18007f12e  sub     edx, 74h ; 't'
0x18007f131  jz      loc_18007F1D1
0x18007f137  sub     edx, 1
0x18007f13a  jz      short loc_18007F171
0x18007f13c  cmp     edx, 0Bh
0x18007f13f  jnz     loc_18007F1DE
0x18007f145  mov     rcx, [rdi+4]; hEnh
0x18007f149  xor     edx, edx; lpFileName
0x18007f14b  call    cs:__imp_CopyEnhMetaFileW
0x18007f151  jmp     loc_18007F1DA
0x18007f156  mov     rcx, [rdi+4]; hpal
0x18007f15a  call    ?CopyPalette@@YAPEAUHPALETTE__@@PEAU1@@Z; CopyPalette(HPALETTE__ *)
0x18007f15f  jmp     short loc_18007F1DA
0x18007f161  mov     rcx, [rdi+4]; void *
0x18007f165  mov     edx, 1; int
0x18007f16a  call    ?CopyDDEData@@YAPEAXPEAXH@Z; CopyDDEData(void *,int)
0x18007f16f  jmp     short loc_18007F1DA
0x18007f171  mov     rcx, [rdi+4]; void *
0x18007f175  mov     edx, 1; int
0x18007f17a  call    ?CopyDDEData@@YAPEAXPEAXH@Z; CopyDDEData(void *,int)
0x18007f17f  mov     rcx, rax; hMem
0x18007f182  mov     rdi, rax
0x18007f185  call    cs:__imp_GlobalLock
0x18007f18b  mov     r14, rax
0x18007f18e  test    rax, rax
0x18007f191  jnz     short loc_18007F1B2
0x18007f193  mov     rcx, rdi; hMem
0x18007f196  call    cs:__imp_GlobalFree
0x18007f19c  mov     rcx, rbx; hMem
0x18007f19f  call    cs:__imp_GlobalUnlock
0x18007f1a5  mov     rcx, rbx; hMem
0x18007f1a8  call    cs:__imp_GlobalFree
0x18007f1ae  xor     ebx, ebx
0x18007f1b0  jmp     short loc_18007F1E7
0x18007f1b2  mov     rcx, [rax+10h]; HMETAFILE
0x18007f1b6  xor     edx, edx; LPCWSTR
0x18007f1b8  call    cs:__imp_CopyMetaFileW
0x18007f1be  mov     rcx, rdi; hMem
0x18007f1c1  mov     [r14+10h], rax
0x18007f1c5  call    cs:__imp_GlobalUnlock
0x18007f1cb  mov     [rsi+4], rdi
0x18007f1cf  jmp     short loc_18007F1DE
0x18007f1d1  mov     rcx, [rdi+4]; h
0x18007f1d5  call    ?CopyBitmap@@YAPEAUHBITMAP__@@PEAU1@@Z; CopyBitmap(HBITMAP__ *)
0x18007f1da  mov     [rsi+4], rax
0x18007f1de  mov     rcx, rbx; hMem
0x18007f1e1  call    cs:__imp_GlobalUnlock
0x18007f1e7  mov     rcx, rbp; hMem
0x18007f1ea  call    cs:__imp_GlobalUnlock
0x18007f1f0  mov     rax, rbx
0x18007f1f3  add     rsp, 20h
0x18007f1f7  pop     r14
0x18007f1f9  pop     rdi
0x18007f1fa  pop     rsi
0x18007f1fb  pop     rbp
0x18007f1fc  pop     rbx
0x18007f1fd  retn
```
