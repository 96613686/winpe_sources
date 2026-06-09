# ReadAllocCmapFormat4Segs

- ea: `0x1800132ac`
- end: `0x18001348e`
- name: `ReadAllocCmapFormat4Segs`
- size: `482`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180016f54`
- `0x180017330`

## callees

- `0x18000ee40`
- `0x1800132ac`
- `0x1800134a0`
- `0x1800164a0`

## pseudocode

```c
__int64 __fastcall ReadAllocCmapFormat4Segs(__int64 a1, unsigned __int16 a2, __int64 *a3, unsigned int a4, _DWORD *a5)
{
  int v5; // ebp
  size_t v9; // rcx
  __int64 v10; // rax
  unsigned __int16 i; // r10
  unsigned __int16 Word; // si
  __int16 v13; // r10
  __int64 result; // rax
  int v15; // r10d
  unsigned int v16; // eax
  unsigned int v17; // esi
  unsigned __int16 j; // r11
  unsigned int v19; // esi
  unsigned __int16 k; // r11
  unsigned int v21; // esi
  unsigned __int16 m; // dx
  __int64 v23; // rcx
  __int16 v24; // r11
  unsigned __int16 v25; // r15
  __int16 v26; // r11
  __int64 v27; // rax

  v5 = a2;
  v9 = 8 * (unsigned int)a2;
  if ( (unsigned int)v9 + a4 + 2 < a4 )
    return 1001;
  v10 = Mem_Alloc(v9);
  *a3 = v10;
  if ( !v10 )
    return 1005;
  for ( i = 0; i < (unsigned __int16)v5; i = v13 + 1 )
  {
    Word = ReadWord(a1, (_WORD *)(*a3 + 8LL * i), a4 + 2 * i);
    if ( Word )
    {
      Mem_Free(*a3);
      result = Word;
      goto LABEL_11;
    }
  }
  if ( !*(_QWORD *)a1 || (v15 = 2 * v5, v16 = 2 * v5 + a4, v17 = v16 + 2, v16 + 2 < v16) || v17 > *(_DWORD *)(a1 + 8) )
  {
LABEL_10:
    Mem_Free(*a3);
    result = 1001;
LABEL_11:
    *a3 = 0;
    return result;
  }
  for ( j = 0; j < (unsigned __int16)v5; j = v24 + 1 )
  {
    v25 = ReadWord(a1, (_WORD *)(*a3 + 2 + 8LL * j), v17 + 2 * j);
    if ( v25 )
    {
LABEL_29:
      Mem_Free(*a3);
      result = v25;
      goto LABEL_11;
    }
  }
  v19 = v15 + v17;
  for ( k = 0; k < (unsigned __int16)v5; k = v26 + 1 )
  {
    v25 = ReadWord(a1, (_WORD *)(*a3 + 4 + 8LL * k), v19 + 2 * k);
    if ( v25 )
      goto LABEL_29;
  }
  v21 = v15 + v19;
  for ( m = 0; m < (unsigned __int16)v5; ++m )
  {
    if ( !*(_QWORD *)a1 )
      goto LABEL_10;
    v23 = v21 + 2 * m;
    if ( (int)v23 + 2 < (unsigned int)v23 || (unsigned int)(v23 + 2) > *(_DWORD *)(a1 + 8) )
      goto LABEL_10;
    v27 = m;
    *(_WORD *)(*a3 + 8 * v27 + 6) = (*(unsigned __int8 *)((unsigned int)v23 + *(_QWORD *)a1) << 8)
                                  | *(unsigned __int8 *)(v23 + *(_QWORD *)a1 + 1);
  }
  *a5 = v21 + v15 - a4;
  return 0;
}

```

## disassembly

```asm
0x1800132ac  push    rbx
0x1800132ae  push    rbp
0x1800132af  push    rsi
0x1800132b0  push    rdi
0x1800132b1  push    r12
0x1800132b3  push    r14
0x1800132b5  push    r15
0x1800132b7  sub     rsp, 20h
0x1800132bb  movzx   ebp, dx
0x1800132be  lea     eax, [r9+2]
0x1800132c2  mov     rdi, rcx
0x1800132c5  mov     r14d, r9d
0x1800132c8  mov     rbx, r8
0x1800132cb  lea     ecx, ds:0[rbp*8]; Size
0x1800132d2  add     eax, ecx
0x1800132d4  cmp     eax, r9d
0x1800132d7  jb      loc_1800133E2
0x1800132dd  call    Mem_Alloc
0x1800132e2  xor     r12d, r12d
0x1800132e5  mov     [rbx], rax
0x1800132e8  test    rax, rax
0x1800132eb  jz      loc_1800133EC
0x1800132f1  mov     r10d, r12d
0x1800132f4  cmp     r10w, bp
0x1800132f8  jnb     short loc_180013327
0x1800132fa  movzx   eax, r10w
0x1800132fe  movzx   ecx, r10w
0x180013302  lea     r8d, [r14+rax*2]
0x180013306  mov     rax, [rbx]
0x180013309  lea     rdx, [rax+rcx*8]
0x18001330d  mov     rcx, rdi
0x180013310  call    ReadWord
0x180013315  movzx   esi, ax
0x180013318  test    ax, ax
0x18001331b  jnz     loc_1800133BC
0x180013321  inc     r10w
0x180013325  jmp     short loc_1800132F4
0x180013327  cmp     [rdi], r12
0x18001332a  jnz     short loc_180013366
0x18001332c  mov     rcx, [rbx]
0x18001332f  mov     edi, 3E9h
0x180013334  call    Mem_Free
0x180013339  movzx   eax, di
0x18001333c  jmp     short loc_180013354
0x18001333e  cmp     eax, [rdi+8]
0x180013341  jbe     loc_180013469
0x180013347  mov     rcx, r8
0x18001334a  call    Mem_Free
0x18001334f  mov     eax, 3E9h
0x180013354  mov     [rbx], r12
0x180013357  add     rsp, 20h
0x18001335b  pop     r15
0x18001335d  pop     r14
0x18001335f  pop     r12
0x180013361  pop     rdi
0x180013362  pop     rsi
0x180013363  pop     rbp
0x180013364  pop     rbx
0x180013365  retn
0x180013366  lea     r10d, ds:0[rbp*2]
0x18001336e  lea     eax, [r10+r14]
0x180013372  lea     esi, [rax+2]
0x180013375  cmp     esi, eax
0x180013377  jb      short loc_18001332C
0x180013379  cmp     esi, [rdi+8]
0x18001337c  ja      short loc_18001332C
0x18001337e  mov     r11d, r12d
0x180013381  cmp     r11w, bp
0x180013385  jb      short loc_1800133F6
0x180013387  add     esi, r10d
0x18001338a  mov     r11d, r12d
0x18001338d  cmp     r11w, bp
0x180013391  jb      loc_180013438
0x180013397  add     esi, r10d
0x18001339a  mov     edx, r12d
0x18001339d  cmp     dx, bp
0x1800133a0  jnb     short loc_1800133C9
0x1800133a2  mov     r9, [rdi]
0x1800133a5  mov     r8, [rbx]
0x1800133a8  test    r9, r9
0x1800133ab  jz      short loc_180013347
0x1800133ad  movzx   eax, dx
0x1800133b0  lea     ecx, [rsi+rax*2]
0x1800133b3  lea     eax, [rcx+2]
0x1800133b6  cmp     eax, ecx
0x1800133b8  jb      short loc_180013347
0x1800133ba  jmp     short loc_18001333E
0x1800133bc  mov     rcx, [rbx]
0x1800133bf  call    Mem_Free
0x1800133c4  movzx   eax, si
0x1800133c7  jmp     short loc_180013354
0x1800133c9  mov     rax, [rsp+58h+arg_20]
0x1800133d1  sub     r10d, r14d
0x1800133d4  add     r10d, esi
0x1800133d7  mov     [rax], r10d
0x1800133da  mov     eax, r12d
0x1800133dd  jmp     loc_180013357
0x1800133e2  mov     eax, 3E9h
0x1800133e7  jmp     loc_180013357
0x1800133ec  mov     eax, 3EDh
0x1800133f1  jmp     loc_180013357
0x1800133f6  mov     rdx, [rbx]
0x1800133f9  movzx   ecx, r11w
0x1800133fd  add     rdx, 2
0x180013401  movzx   eax, r11w
0x180013405  lea     rdx, [rdx+rcx*8]
0x180013409  mov     rcx, rdi
0x18001340c  lea     r8d, [rsi+rax*2]
0x180013410  call    ReadWord
0x180013415  movzx   r15d, ax
0x180013419  test    ax, ax
0x18001341c  jnz     short loc_180013427
0x18001341e  inc     r11w
0x180013422  jmp     loc_180013381
0x180013427  mov     rcx, [rbx]
0x18001342a  call    Mem_Free
0x18001342f  movzx   eax, r15w
0x180013433  jmp     loc_180013354
0x180013438  mov     rdx, [rbx]
0x18001343b  movzx   ecx, r11w
0x18001343f  add     rdx, 4
0x180013443  movzx   eax, r11w
0x180013447  lea     rdx, [rdx+rcx*8]
0x18001344b  mov     rcx, rdi
0x18001344e  lea     r8d, [rsi+rax*2]
0x180013452  call    ReadWord
0x180013457  movzx   r15d, ax
0x18001345b  test    ax, ax
0x18001345e  jnz     short loc_180013427
0x180013460  inc     r11w
0x180013464  jmp     loc_18001338D
0x180013469  mov     eax, ecx
0x18001346b  movzx   ecx, byte ptr [rcx+r9+1]
0x180013471  movzx   eax, byte ptr [rax+r9]
0x180013476  shl     ax, 8
0x18001347a  or      cx, ax
0x18001347d  movzx   eax, dx
0x180013480  inc     dx
0x180013483  mov     [r8+rax*8+6], cx
0x180013489  jmp     loc_18001339D
```
