# CGenLexer::NextToken(void)

- ea: `0x180015374`
- end: `0x18001552c`
- name: `?NextToken@CGenLexer@@QEAAHXZ`
- size: `440`
- prototype: `__int64 __fastcall(CGenLexer *this, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800147b8`

## callees

- `0x180015374`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015441`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015441`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180015455`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180015455`

## pseudocode

```c
__int64 __fastcall CGenLexer::NextToken(CGenLexer *this, __int64 a2)
{
  _WORD *v3; // rcx
  int v4; // ebx
  int v5; // edi
  int v6; // r12d
  unsigned __int16 v7; // bp
  BOOL v8; // r13d
  __int64 v9; // r15
  __int16 v10; // r14
  __int64 v11; // rcx
  unsigned __int16 v12; // ax
  unsigned __int16 v13; // cx
  int v14; // ebx
  void *v15; // rdi
  int v16; // ebx
  HANDLE ProcessHeap; // rax
  LPVOID v18; // rax
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 result; // rax

  v3 = *(_WORD **)this;
  if ( !v3 )
    return 0;
  *v3 = 0;
  v4 = 1;
  v5 = 0;
  v6 = 0;
  v7 = 0;
  v8 = 0;
  while ( 1 )
  {
    while ( 1 )
    {
      v9 = 5LL * v5;
      v10 = *(_WORD *)(*((_QWORD *)this + 3) + 10LL * v5 + 8);
      if ( v4 )
      {
        if ( v8 )
          return 1;
        v7 = (***((__int64 (__fastcall ****)(_QWORD, __int64, _QWORD))this + 2))(*((_QWORD *)this + 2), a2, 0);
        v8 = v7 == 0;
      }
      v11 = *((_QWORD *)this + 3);
      a2 = 0xFFFF;
      v4 = 0;
      v12 = *(_WORD *)(v11 + 10LL * v5);
      if ( v12 == 0xFFFF )
        goto LABEL_10;
      v13 = *(_WORD *)(v11 + 10LL * v5 + 2);
      a2 = 65534;
      if ( v13 != 0xFFFE )
        break;
      if ( v7 == v12 || (v10 & 8) != 0 )
        goto LABEL_10;
LABEL_29:
      ++v5;
    }
    if ( ((v10 & 8) == 0 || v7 >= v12 && v7 <= v13) && (v7 < v12 || v7 > v13) )
      goto LABEL_29;
LABEL_10:
    if ( (v10 & 1) == 0 )
      goto LABEL_15;
    v14 = *((_DWORD *)this + 3);
    if ( v6 == v14 - 1 )
      break;
LABEL_14:
    v4 = 1;
    v19 = v6;
    a2 = v6++;
    *(_WORD *)(*(_QWORD *)this + 2 * v19) = v7;
    *(_WORD *)(*(_QWORD *)this + 2 * a2 + 2) = 0;
LABEL_15:
    if ( (v10 & 2) != 0 )
      v4 = 1;
    if ( (v10 & 4) != 0 )
    {
      v4 = 1;
      (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 2) + 8LL))(*((_QWORD *)this + 2), v7, 0);
    }
    if ( (v10 & 0x10) != 0 )
      ++*((_DWORD *)this + 2);
    v20 = *((_QWORD *)this + 3);
    result = *(unsigned __int16 *)(v20 + 2 * v9 + 6);
    if ( (_WORD)result || (v10 & 0x20) != 0 )
      return result;
    v5 = *(unsigned __int16 *)(v20 + 2 * v9 + 4);
  }
  v15 = *(void **)this;
  v16 = v14 + 256;
  *((_DWORD *)this + 3) = v16;
  ProcessHeap = GetProcessHeap();
  v18 = HeapReAlloc(ProcessHeap, 0, v15, 2 * v16);
  if ( v18 )
  {
    *(_QWORD *)this = v18;
    goto LABEL_14;
  }
  *((_DWORD *)this + 3) -= 256;
  return 0;
}

```

## disassembly

```asm
0x180015374  push    rbx
0x180015376  push    rbp
0x180015377  push    rsi
0x180015378  push    rdi
0x180015379  push    r12
0x18001537b  push    r13
0x18001537d  push    r14
0x18001537f  push    r15
0x180015381  sub     rsp, 28h
0x180015385  mov     rsi, rcx
0x180015388  xor     r8d, r8d
0x18001538b  mov     rcx, [rcx]
0x18001538e  test    rcx, rcx
0x180015391  jz      loc_180015519
0x180015397  lea     r9d, [r8+1]
0x18001539b  mov     [rcx], r8w
0x18001539f  mov     ebx, r9d
0x1800153a2  mov     edi, r8d
0x1800153a5  mov     r12d, r8d
0x1800153a8  mov     ebp, r8d
0x1800153ab  mov     r13d, r8d
0x1800153ae  movsxd  rax, edi
0x1800153b1  lea     r15, [rax+rax*4]
0x1800153b5  mov     rax, [rsi+18h]
0x1800153b9  movzx   r14d, word ptr [rax+r15*2+8]
0x1800153bf  test    ebx, ebx
0x1800153c1  jz      short loc_1800153EC
0x1800153c3  test    r13d, r13d
0x1800153c6  jnz     loc_18001550D
0x1800153cc  mov     rcx, [rsi+10h]
0x1800153d0  mov     rax, [rcx]
0x1800153d3  mov     rax, [rax]
0x1800153d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800153db  xor     r8d, r8d
0x1800153de  lea     r9d, [r13+1]
0x1800153e2  test    ax, ax
0x1800153e5  movzx   ebp, ax
0x1800153e8  cmovz   r13d, r9d
0x1800153ec  mov     rcx, [rsi+18h]
0x1800153f0  mov     edx, 0FFFFh
0x1800153f5  mov     ebx, r8d
0x1800153f8  movzx   eax, word ptr [rcx+r15*2]
0x1800153fd  cmp     ax, dx
0x180015400  jz      short loc_180015425
0x180015402  movzx   ecx, word ptr [rcx+r15*2+2]
0x180015408  mov     edx, 0FFFEh
0x18001540d  cmp     cx, dx
0x180015410  jnz     loc_1800154DF
0x180015416  cmp     bp, ax
0x180015419  jz      short loc_180015425
0x18001541b  test    r14b, 8
0x18001541f  jz      loc_180015505
0x180015425  test    r9b, r14b
0x180015428  jz      short loc_18001548A
0x18001542a  mov     ebx, [rsi+0Ch]
0x18001542d  lea     eax, [rbx-1]
0x180015430  cmp     r12d, eax
0x180015433  jnz     short loc_18001546E
0x180015435  mov     rdi, [rsi]
0x180015438  add     ebx, 100h
0x18001543e  mov     [rsi+0Ch], ebx
0x180015441  call    cs:__imp_GetProcessHeap
0x180015447  lea     ecx, [rbx+rbx]
0x18001544a  mov     r8, rdi; lpMem
0x18001544d  movsxd  r9, ecx; dwBytes
0x180015450  xor     edx, edx; dwFlags
0x180015452  mov     rcx, rax; hHeap
0x180015455  call    cs:__imp_HeapReAlloc
0x18001545b  xor     r8d, r8d
0x18001545e  test    rax, rax
0x180015461  jz      loc_180015512
0x180015467  mov     [rsi], rax
0x18001546a  lea     r9d, [r8+1]
0x18001546e  mov     rax, [rsi]
0x180015471  mov     ebx, r9d
0x180015474  movsxd  rcx, r12d
0x180015477  movsxd  rdx, r12d
0x18001547a  add     r12d, r9d
0x18001547d  mov     [rax+rcx*2], bp
0x180015481  mov     rcx, [rsi]
0x180015484  mov     [rcx+rdx*2+2], r8w
0x18001548a  test    r14b, 2
0x18001548e  cmovnz  ebx, r9d
0x180015492  test    r14b, 4
0x180015496  jz      short loc_1800154B5
0x180015498  mov     rcx, [rsi+10h]
0x18001549c  movzx   edx, bp
0x18001549f  mov     ebx, r9d
0x1800154a2  mov     rax, [rcx]
0x1800154a5  mov     rax, [rax+8]
0x1800154a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154ae  xor     r8d, r8d
0x1800154b1  lea     r9d, [r8+1]
0x1800154b5  test    r14b, 10h
0x1800154b9  jz      short loc_1800154BF
0x1800154bb  add     [rsi+8], r9d
0x1800154bf  mov     rcx, [rsi+18h]
0x1800154c3  movzx   eax, word ptr [rcx+r15*2+6]
0x1800154c9  test    ax, ax
0x1800154cc  jnz     short loc_18001551B
0x1800154ce  test    r14b, 20h
0x1800154d2  jnz     short loc_18001551B
0x1800154d4  movzx   edi, word ptr [rcx+r15*2+4]
0x1800154da  jmp     loc_1800153AE
0x1800154df  test    r14b, 8
0x1800154e3  jz      short loc_1800154F7
0x1800154e5  cmp     bp, ax
0x1800154e8  jb      loc_180015425
0x1800154ee  cmp     bp, cx
0x1800154f1  ja      loc_180015425
0x1800154f7  cmp     bp, ax
0x1800154fa  jb      short loc_180015505
0x1800154fc  cmp     bp, cx
0x1800154ff  jbe     loc_180015425
0x180015505  add     edi, r9d
0x180015508  jmp     loc_1800153AE
0x18001550d  mov     eax, r9d
0x180015510  jmp     short loc_18001551B
0x180015512  add     dword ptr [rsi+0Ch], 0FFFFFF00h
0x180015519  xor     eax, eax
0x18001551b  add     rsp, 28h
0x18001551f  pop     r15
0x180015521  pop     r14
0x180015523  pop     r13
0x180015525  pop     r12
0x180015527  pop     rdi
0x180015528  pop     rsi
0x180015529  pop     rbp
0x18001552a  pop     rbx
0x18001552b  retn
```
