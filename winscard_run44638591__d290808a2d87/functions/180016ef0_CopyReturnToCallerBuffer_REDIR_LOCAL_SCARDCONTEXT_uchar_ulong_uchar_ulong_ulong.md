# _CopyReturnToCallerBuffer(_REDIR_LOCAL_SCARDCONTEXT *,uchar *,ulong,uchar *,ulong *,ulong)

- ea: `0x180016ef0`
- end: `0x180016ff9`
- name: `?_CopyReturnToCallerBuffer@@YAJPEAU_REDIR_LOCAL_SCARDCONTEXT@@PEAEK1PEAKK@Z`
- size: `265`
- prototype: `int(struct _REDIR_LOCAL_SCARDCONTEXT *, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int *, unsigned int)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x18001326c`
- `0x180018b48`
- `0x1800190cc`
- `0x180019b80`
- `0x18002ba08`
- `0x18002bd60`
- `0x18002c434`
- `0x18002dd0c`

## callees

- `0x180016ef0`
- `0x18002ef38`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016fba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016fba`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016fcb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016fcb`

## pseudocode

```c
__int64 __fastcall _CopyReturnToCallerBuffer(
        struct _REDIR_LOCAL_SCARDCONTEXT *a1,
        unsigned __int8 *a2,
        unsigned int a3,
        unsigned __int8 *a4,
        unsigned int *a5,
        unsigned int a6)
{
  size_t v8; // rbx
  unsigned int v9; // eax
  unsigned int v10; // r8d
  unsigned int v11; // r9d
  bool v12; // zf
  unsigned __int8 *v13; // rcx
  HANDLE ProcessHeap; // rax
  unsigned __int8 *v16; // rax

  v8 = a3;
  v9 = a3;
  v10 = *a5;
  if ( a6 == 3 )
    v9 >>= 1;
  *a5 = v9;
  if ( !a2 || !a4 )
    return 0;
  if ( a6 != 3 )
  {
    if ( a6 == 2 )
    {
      if ( v10 == -1 || v10 >= (unsigned int)v8 )
      {
        if ( (unsigned int)v8 < 2 || a2[(unsigned int)(v8 - 1)] )
          return 2148532255LL;
        v12 = a2[(unsigned int)(v8 - 2)] == 0;
        goto LABEL_17;
      }
    }
    else
    {
      if ( v10 == -1 )
        goto LABEL_24;
      if ( v10 >= (unsigned int)v8 )
        goto LABEL_19;
    }
    return 2148532232LL;
  }
  v11 = (unsigned int)v8 >> 1;
  if ( v10 != -1 && v10 < (unsigned int)v8 >> 1 )
    return 2148532232LL;
  if ( v11 < 2 || *(_WORD *)&a2[2 * v11 - 2] )
    return 2148532255LL;
  v12 = *(_WORD *)&a2[2 * v11 - 4] == 0;
LABEL_17:
  if ( !v12 )
    return 2148532255LL;
  if ( v10 != -1 )
  {
LABEL_19:
    v13 = a4;
LABEL_29:
    memcpy_0(v13, a2, v8);
    return 0;
  }
LABEL_24:
  if ( a1 )
    ProcessHeap = (HANDLE)*((_QWORD *)a1 + 3);
  else
    ProcessHeap = GetProcessHeap();
  v16 = (unsigned __int8 *)HeapAlloc(ProcessHeap, 8u, v8);
  *(_QWORD *)a4 = v16;
  if ( v16 )
  {
    v13 = v16;
    goto LABEL_29;
  }
  return 2148532230LL;
}

```

## disassembly

```asm
0x180016ef0  push    rbx
0x180016ef2  push    rbp
0x180016ef3  push    rsi
0x180016ef4  push    rdi
0x180016ef5  sub     rsp, 28h
0x180016ef9  mov     r10, [rsp+48h+arg_20]
0x180016efe  mov     rdi, rdx
0x180016f01  mov     edx, [rsp+48h+arg_28]
0x180016f05  mov     rsi, r9
0x180016f08  mov     ebx, r8d
0x180016f0b  mov     eax, ebx
0x180016f0d  mov     r8d, [r10]
0x180016f10  cmp     edx, 3
0x180016f13  jnz     short loc_180016F17
0x180016f15  shr     eax, 1
0x180016f17  xor     ebp, ebp
0x180016f19  mov     [r10], eax
0x180016f1c  test    rdi, rdi
0x180016f1f  jz      loc_180016FE7
0x180016f25  test    rsi, rsi
0x180016f28  jz      loc_180016FE7
0x180016f2e  cmp     edx, 3
0x180016f31  jnz     short loc_180016F61
0x180016f33  mov     eax, ebx
0x180016f35  or      edx, 0FFFFFFFFh
0x180016f38  shr     eax, 1
0x180016f3a  mov     r9d, eax
0x180016f3d  cmp     r8d, edx
0x180016f40  jz      short loc_180016F47
0x180016f42  cmp     r8d, eax
0x180016f45  jb      short loc_180016FA8
0x180016f47  cmp     r9d, 2
0x180016f4b  jb      short loc_180016F94
0x180016f4d  lea     eax, [r9-1]
0x180016f51  cmp     [rdi+rax*2], bp
0x180016f55  jnz     short loc_180016F94
0x180016f57  lea     eax, [r9-2]
0x180016f5b  cmp     [rdi+rax*2], bp
0x180016f5f  jmp     short loc_180016F88
0x180016f61  cmp     edx, 2
0x180016f64  jnz     short loc_180016F9B
0x180016f66  or      edx, 0FFFFFFFFh
0x180016f69  cmp     r8d, edx
0x180016f6c  jz      short loc_180016F73
0x180016f6e  cmp     r8d, ebx
0x180016f71  jb      short loc_180016FA8
0x180016f73  cmp     ebx, 2
0x180016f76  jb      short loc_180016F94
0x180016f78  lea     eax, [rbx-1]
0x180016f7b  cmp     [rax+rdi], bpl
0x180016f7f  jnz     short loc_180016F94
0x180016f81  lea     eax, [rbx-2]
0x180016f84  cmp     [rax+rdi], bpl
0x180016f88  jnz     short loc_180016F94
0x180016f8a  cmp     r8d, edx
0x180016f8d  jz      short loc_180016FAF
0x180016f8f  mov     rcx, rsi
0x180016f92  jmp     short loc_180016FDC
0x180016f94  mov     eax, 8010001Fh
0x180016f99  jmp     short loc_180016FE9
0x180016f9b  or      edx, 0FFFFFFFFh
0x180016f9e  cmp     r8d, edx
0x180016fa1  jz      short loc_180016FAF
0x180016fa3  cmp     r8d, ebx
0x180016fa6  jnb     short loc_180016F8F
0x180016fa8  mov     eax, 80100008h
0x180016fad  jmp     short loc_180016FE9
0x180016faf  test    rcx, rcx
0x180016fb2  jz      short loc_180016FBA
0x180016fb4  mov     rax, [rcx+18h]
0x180016fb8  jmp     short loc_180016FC0
0x180016fba  call    cs:__imp_GetProcessHeap
0x180016fc0  mov     r8, rbx; dwBytes
0x180016fc3  mov     edx, 8; dwFlags
0x180016fc8  mov     rcx, rax; hHeap
0x180016fcb  call    cs:__imp_HeapAlloc
0x180016fd1  mov     [rsi], rax
0x180016fd4  test    rax, rax
0x180016fd7  jz      short loc_180016FF2
0x180016fd9  mov     rcx, rax; void *
0x180016fdc  mov     rdx, rdi; Src
0x180016fdf  mov     r8, rbx; Size
0x180016fe2  call    memcpy_0
0x180016fe7  xor     eax, eax
0x180016fe9  add     rsp, 28h
0x180016fed  pop     rdi
0x180016fee  pop     rsi
0x180016fef  pop     rbp
0x180016ff0  pop     rbx
0x180016ff1  retn
0x180016ff2  mov     eax, 80100006h
0x180016ff7  jmp     short loc_180016FE9
```
