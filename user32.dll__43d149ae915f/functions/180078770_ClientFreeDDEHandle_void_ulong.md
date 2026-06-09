# _ClientFreeDDEHandle(void *,ulong)

- ea: `0x180078770`
- end: `0x180078858`
- name: `?_ClientFreeDDEHandle@@YAHPEAXK@Z`
- size: `232`
- prototype: `__int64 __fastcall(HGLOBAL hMem, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180094970`

## callees

- `0x180068bf8`
- `0x18006ef34`
- `0x180078770`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800787ad`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180078843`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800787ad`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180078843`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x1800787fc`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x180078818`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x1800787fc`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x180078818`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x1800787d6`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x1800787d6`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalFlags` at `0x1800787c6`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalFlags` at `0x1800787c6`

## pseudocode

```c
__int64 __fastcall _ClientFreeDDEHandle(void **hMem, __int16 a2)
{
  unsigned __int64 v2; // rbp
  void **v4; // rbx
  int v5; // r14d
  void **v6; // rcx

  v2 = 0;
  v4 = hMem;
  v5 = a2 & 1;
  if ( (a2 & 1) != 0 )
  {
    if ( !(unsigned int)IsValidGlobalHandle(hMem) )
      return 0;
    v6 = v4;
    if ( (a2 & 0x80u) == 0 )
      v6 = v4 + 1;
    v2 = (unsigned __int64)*v6;
    GlobalFree(v4);
    v4 = (void **)v2;
  }
  if ( (unsigned __int64)v4 > 0xFFFF && GlobalFlags(v4) != 0x8000 && GlobalSize(v4) )
  {
    if ( a2 < 0 )
    {
      if ( v5 )
      {
        if ( (v2 & 0xFFFFFFFFFFFF0000uLL) == 0 )
        {
          GlobalDeleteAtom(v2);
          if ( (a2 & 2) == 0 )
            return 1;
LABEL_17:
          FreeDDEData(v4, (a2 & 0x8000) == 0, a2 < 0);
          return 1;
        }
      }
      else if ( (a2 & 0x800) == 0 )
      {
        GlobalDeleteAtom((ATOM)v4);
        return 1;
      }
    }
    if ( (a2 & 2) == 0 )
    {
      GlobalFree(v4);
      return 1;
    }
    goto LABEL_17;
  }
  return 0;
}

```

## disassembly

```asm
0x180078770  push    rbx
0x180078772  push    rbp
0x180078773  push    rsi
0x180078774  push    rdi
0x180078775  push    r14
0x180078777  sub     rsp, 20h
0x18007877b  xor     ebp, ebp
0x18007877d  mov     r14d, edx
0x180078780  mov     edi, edx
0x180078782  mov     rbx, rcx
0x180078785  and     r14d, 1
0x180078789  jz      short loc_1800787B6
0x18007878b  call    ?IsValidGlobalHandle@@YAHPEAX@Z; IsValidGlobalHandle(void *)
0x180078790  test    eax, eax
0x180078792  jz      loc_18007884B
0x180078798  test    dil, 80h
0x18007879c  lea     rax, [rbx+8]
0x1800787a0  mov     rcx, rbx
0x1800787a3  cmovz   rcx, rax
0x1800787a7  mov     rbp, [rcx]
0x1800787aa  mov     rcx, rbx; hMem
0x1800787ad  call    cs:__imp_GlobalFree
0x1800787b3  mov     rbx, rbp
0x1800787b6  cmp     rbx, 0FFFFh
0x1800787bd  jbe     loc_18007884B
0x1800787c3  mov     rcx, rbx; hMem
0x1800787c6  call    cs:__imp_GlobalFlags
0x1800787cc  cmp     eax, 8000h
0x1800787d1  jz      short loc_18007884B
0x1800787d3  mov     rcx, rbx; hMem
0x1800787d6  call    cs:__imp_GlobalSize
0x1800787dc  test    rax, rax
0x1800787df  jz      short loc_18007884B
0x1800787e1  mov     esi, edi
0x1800787e3  and     esi, 8000h
0x1800787e9  jz      short loc_180078820
0x1800787eb  test    r14d, r14d
0x1800787ee  jz      short loc_18007880F
0x1800787f0  test    rbp, 0FFFFFFFFFFFF0000h
0x1800787f7  jnz     short loc_180078820
0x1800787f9  movzx   ecx, bp; nAtom
0x1800787fc  call    cs:__imp_GlobalDeleteAtom
0x180078802  test    dil, 2
0x180078806  jnz     short loc_180078826
0x180078808  mov     eax, 1
0x18007880d  jmp     short loc_18007884D
0x18007880f  bt      edi, 0Bh
0x180078813  jb      short loc_180078820
0x180078815  movzx   ecx, bx; nAtom
0x180078818  call    cs:__imp_GlobalDeleteAtom
0x18007881e  jmp     short loc_180078808
0x180078820  test    dil, 2
0x180078824  jz      short loc_180078840
0x180078826  xor     r8d, r8d
0x180078829  mov     rcx, rbx; hMem
0x18007882c  test    esi, esi
0x18007882e  setnz   r8b; int
0x180078832  xor     edx, edx
0x180078834  test    esi, esi
0x180078836  setz    dl; int
0x180078839  call    ?FreeDDEData@@YAXPEAXHH@Z; FreeDDEData(void *,int,int)
0x18007883e  jmp     short loc_180078808
0x180078840  mov     rcx, rbx; hMem
0x180078843  call    cs:__imp_GlobalFree
0x180078849  jmp     short loc_180078808
0x18007884b  xor     eax, eax
0x18007884d  add     rsp, 20h
0x180078851  pop     r14
0x180078853  pop     rdi
0x180078854  pop     rsi
0x180078855  pop     rbp
0x180078856  pop     rbx
0x180078857  retn
```
