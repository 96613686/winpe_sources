# EFIDECreateNewDriverEntry

- ea: `0x18001490c`
- end: `0x1800149d1`
- name: `EFIDECreateNewDriverEntry`
- size: `197`
- prototype: `_QWORD *__fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, reparse_path`

## callers

- `0x1800144b0`

## callees

- `0x18001490c`
- `0x180014a40`
- `0x180014a94`
- `0x180014b1c`
- `0x180014b70`
- `0x1800179c5`
- `0x180018010`

## pseudocode

```c
_QWORD *__fastcall EFIDECreateNewDriverEntry(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  _QWORD *v4; // rbx
  _QWORD *v9; // rax

  v4 = 0;
  if ( a1 )
  {
    if ( a2 )
    {
      if ( a4 )
      {
        if ( a3 )
        {
          if ( AllocRoutine )
          {
            v9 = (_QWORD *)AllocRoutine(2120);
            v4 = v9;
            if ( v9 )
            {
              memset_0(v9, 0, 0x848u);
              v4[261] = a1;
              v4[264] = EFIDEFlushDriverEntry;
              OSDriverSetFileName(v4, a4);
              OSDriverSetNtPath(v4, a3);
              OSDriverSetDirPath(v4, a4);
              OSDriverSetFriendlyName(v4, a2);
              *((_DWORD *)v4 + 521) |= 1u;
              *((_DWORD *)v4 + 521) |= 0x10000000u;
            }
          }
        }
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18001490c  push    rbx
0x18001490e  push    rbp
0x18001490f  push    rsi
0x180014910  push    rdi
0x180014911  push    r14
0x180014913  sub     rsp, 20h
0x180014917  xor     ebx, ebx
0x180014919  mov     rdi, r9
0x18001491c  mov     rsi, r8
0x18001491f  mov     rbp, rdx
0x180014922  mov     r14, rcx
0x180014925  test    rcx, rcx
0x180014928  jz      loc_1800149C3
0x18001492e  test    rdx, rdx
0x180014931  jz      loc_1800149C3
0x180014937  test    r9, r9
0x18001493a  jz      loc_1800149C3
0x180014940  test    r8, r8
0x180014943  jz      short loc_1800149C3
0x180014945  mov     rax, cs:AllocRoutine
0x18001494c  test    rax, rax
0x18001494f  jz      short loc_1800149C3
0x180014951  mov     ecx, 848h
0x180014956  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001495b  mov     rbx, rax
0x18001495e  test    rax, rax
0x180014961  jz      short loc_1800149C3
0x180014963  xor     edx, edx; Val
0x180014965  mov     r8d, 848h; Size
0x18001496b  mov     rcx, rax; void *
0x18001496e  call    memset_0
0x180014973  lea     rax, EFIDEFlushDriverEntry
0x18001497a  mov     [rbx+828h], r14
0x180014981  mov     rdx, rdi
0x180014984  mov     [rbx+840h], rax
0x18001498b  mov     rcx, rbx
0x18001498e  call    OSDriverSetFileName
0x180014993  mov     rdx, rsi
0x180014996  mov     rcx, rbx
0x180014999  call    OSDriverSetNtPath
0x18001499e  mov     rdx, rdi
0x1800149a1  mov     rcx, rbx
0x1800149a4  call    OSDriverSetDirPath
0x1800149a9  mov     rdx, rbp
0x1800149ac  mov     rcx, rbx
0x1800149af  call    OSDriverSetFriendlyName
0x1800149b4  or      dword ptr [rbx+824h], 1
0x1800149bb  bts     dword ptr [rbx+824h], 1Ch
0x1800149c3  mov     rax, rbx
0x1800149c6  add     rsp, 20h
0x1800149ca  pop     r14
0x1800149cc  pop     rdi
0x1800149cd  pop     rsi
0x1800149ce  pop     rbp
0x1800149cf  pop     rbx
0x1800149d0  retn
```
