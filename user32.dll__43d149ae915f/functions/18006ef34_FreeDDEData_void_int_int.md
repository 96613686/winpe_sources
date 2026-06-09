# FreeDDEData(void *,int,int)

- ea: `0x18006ef34`
- end: `0x18006f061`
- name: `?FreeDDEData@@YAXPEAXHH@Z`
- size: `301`
- prototype: `void __fastcall(HGLOBAL hMem, int, int)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x1800470a0`
- `0x180061230`
- `0x18006da20`
- `0x180078770`
- `0x18007f2e4`
- `0x18008f4f0`
- `0x18008f600`
- `0x18008f9b0`
- `0x1800903f4`

## callees

- `0x18006ef34`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18006efe0`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18006f052`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18006efe0`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18006f052`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x18006ef76`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x18006f008`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x18006ef76`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x18006f008`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18006ef45`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18006eff6`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18006ef45`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18006eff6`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18006ef68`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18006f022`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18006f049`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18006ef68`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18006f022`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18006f049`
- `GDI32!DeleteEnhMetaFile` at `0x18006efca`
- `GDI32!DeleteEnhMetaFile` at `0x18006efca`
- `GDI32!DeleteMetaFile` at `0x18006f018`
- `GDI32!DeleteMetaFile` at `0x18006f018`
- `GDI32!DeleteObject` at `0x18006f040`
- `GDI32!DeleteObject` at `0x18006f040`

## pseudocode

```c
void __fastcall FreeDDEData(HGLOBAL hMem, int a2, int a3)
{
  char *v6; // rbx
  unsigned int v7; // eax
  HENHMETAFILE v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  HMETAFILE *v11; // rsi
  void *v12; // rcx

  v6 = (char *)GlobalLock(hMem);
  if ( v6 )
  {
    if ( (*(_WORD *)v6 & 0x2000) == 0 && !a2 )
    {
      GlobalUnlock(hMem);
      return;
    }
    v7 = GlobalSize(hMem);
    if ( *((_WORD *)v6 + 1) != 2 )
    {
      if ( *((_WORD *)v6 + 1) == 3 )
      {
LABEL_19:
        if ( v7 < 8 )
          goto LABEL_29;
        v10 = *(void **)(v6 + 4);
        if ( !v10 )
          goto LABEL_29;
        v11 = (HMETAFILE *)GlobalLock(v10);
        if ( !v11 )
          goto LABEL_29;
        if ( GlobalSize(*(HGLOBAL *)(v6 + 4)) >= 0x18 )
          DeleteMetaFile(v11[2]);
        GlobalUnlock(*(HGLOBAL *)(v6 + 4));
        v9 = *(void **)(v6 + 4);
        goto LABEL_18;
      }
      if ( *((_WORD *)v6 + 1) == 8 )
      {
        if ( v7 < 8 )
          goto LABEL_29;
        v9 = *(void **)(v6 + 4);
        if ( !v9 )
          goto LABEL_29;
LABEL_18:
        GlobalFree(v9);
        goto LABEL_29;
      }
      if ( *((_WORD *)v6 + 1) != 9 )
      {
        if ( *((_WORD *)v6 + 1) == 14 )
          goto LABEL_13;
        if ( *((_WORD *)v6 + 1) != 130 )
        {
          if ( *((_WORD *)v6 + 1) != 131 )
          {
            if ( *((_WORD *)v6 + 1) == 142 )
            {
LABEL_13:
              if ( v7 >= 8 )
              {
                v8 = *(HENHMETAFILE *)(v6 + 4);
                if ( v8 )
                  DeleteEnhMetaFile(v8);
              }
            }
LABEL_29:
            GlobalUnlock(hMem);
            GlobalFree(hMem);
            return;
          }
          goto LABEL_19;
        }
      }
    }
    if ( v7 >= 8 )
    {
      if ( a3 )
      {
        v12 = *(void **)(v6 + 4);
        if ( v12 )
          DeleteObject(v12);
      }
    }
    goto LABEL_29;
  }
}

```

## disassembly

```asm
0x18006ef34  push    rbx
0x18006ef36  push    rbp
0x18006ef37  push    rsi
0x18006ef38  push    rdi
0x18006ef39  sub     rsp, 28h
0x18006ef3d  mov     ebp, r8d
0x18006ef40  mov     esi, edx
0x18006ef42  mov     rdi, rcx
0x18006ef45  call    cs:__imp_GlobalLock
0x18006ef4b  mov     rbx, rax
0x18006ef4e  test    rax, rax
0x18006ef51  jz      loc_18006F058
0x18006ef57  mov     eax, 2000h
0x18006ef5c  test    [rbx], ax
0x18006ef5f  jnz     short loc_18006EF73
0x18006ef61  test    esi, esi
0x18006ef63  jnz     short loc_18006EF73
0x18006ef65  mov     rcx, rdi; hMem
0x18006ef68  call    cs:__imp_GlobalUnlock
0x18006ef6e  jmp     loc_18006F058
0x18006ef73  mov     rcx, rdi; hMem
0x18006ef76  call    cs:__imp_GlobalSize
0x18006ef7c  movzx   edx, word ptr [rbx+2]
0x18006ef80  sub     edx, 2
0x18006ef83  jz      loc_18006F02E
0x18006ef89  sub     edx, 1
0x18006ef8c  jz      short loc_18006EFE8
0x18006ef8e  sub     edx, 5
0x18006ef91  jz      short loc_18006EFD2
0x18006ef93  sub     edx, 1
0x18006ef96  jz      loc_18006F02E
0x18006ef9c  sub     edx, 5
0x18006ef9f  jz      short loc_18006EFB8
0x18006efa1  sub     edx, 74h ; 't'
0x18006efa4  jz      loc_18006F02E
0x18006efaa  sub     edx, 1
0x18006efad  jz      short loc_18006EFE8
0x18006efaf  cmp     edx, 0Bh
0x18006efb2  jnz     loc_18006F046
0x18006efb8  cmp     eax, 8
0x18006efbb  jb      loc_18006F046
0x18006efc1  mov     rcx, [rbx+4]; hmf
0x18006efc5  test    rcx, rcx
0x18006efc8  jz      short loc_18006F046
0x18006efca  call    cs:__imp_DeleteEnhMetaFile
0x18006efd0  jmp     short loc_18006F046
0x18006efd2  cmp     eax, 8
0x18006efd5  jb      short loc_18006F046
0x18006efd7  mov     rcx, [rbx+4]; hMem
0x18006efdb  test    rcx, rcx
0x18006efde  jz      short loc_18006F046
0x18006efe0  call    cs:__imp_GlobalFree
0x18006efe6  jmp     short loc_18006F046
0x18006efe8  cmp     eax, 8
0x18006efeb  jb      short loc_18006F046
0x18006efed  mov     rcx, [rbx+4]; hMem
0x18006eff1  test    rcx, rcx
0x18006eff4  jz      short loc_18006F046
0x18006eff6  call    cs:__imp_GlobalLock
0x18006effc  mov     rsi, rax
0x18006efff  test    rax, rax
0x18006f002  jz      short loc_18006F046
0x18006f004  mov     rcx, [rbx+4]; hMem
0x18006f008  call    cs:__imp_GlobalSize
0x18006f00e  cmp     rax, 18h
0x18006f012  jb      short loc_18006F01E
0x18006f014  mov     rcx, [rsi+10h]; hmf
0x18006f018  call    cs:__imp_DeleteMetaFile
0x18006f01e  mov     rcx, [rbx+4]; hMem
0x18006f022  call    cs:__imp_GlobalUnlock
0x18006f028  mov     rcx, [rbx+4]
0x18006f02c  jmp     short loc_18006EFE0
0x18006f02e  cmp     eax, 8
0x18006f031  jb      short loc_18006F046
0x18006f033  test    ebp, ebp
0x18006f035  jz      short loc_18006F046
0x18006f037  mov     rcx, [rbx+4]; ho
0x18006f03b  test    rcx, rcx
0x18006f03e  jz      short loc_18006F046
0x18006f040  call    cs:__imp_DeleteObject
0x18006f046  mov     rcx, rdi; hMem
0x18006f049  call    cs:__imp_GlobalUnlock
0x18006f04f  mov     rcx, rdi; hMem
0x18006f052  call    cs:__imp_GlobalFree
0x18006f058  add     rsp, 28h
0x18006f05c  pop     rdi
0x18006f05d  pop     rsi
0x18006f05e  pop     rbp
0x18006f05f  pop     rbx
0x18006f060  retn
```
