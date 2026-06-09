# PipeReadWriteChainedMdl

- ea: `0x140002560`
- end: `0x14000261a`
- name: `PipeReadWriteChainedMdl`
- size: `186`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140001560`
- `0x140016ab0`

## callees

- `0x140002560`
- `0x140017240`

## pseudocode

```c
__int64 __fastcall PipeReadWriteChainedMdl(__int64 *a1, unsigned int a2, __int64 a3, int a4, char a5)
{
  unsigned int v5; // ebx
  unsigned int v6; // r15d
  unsigned int v7; // edi
  int v12; // edx
  __int64 v13; // r9
  unsigned int v14; // ecx
  unsigned int v15; // edx
  __int64 v16; // r8
  unsigned int v17; // eax
  void *v18; // rcx
  unsigned int v19; // r13d
  const void *v20; // rdx

  v5 = 0;
  v6 = 0;
  v7 = a2 + a4;
  while ( v5 < v7 )
  {
    v12 = *((_DWORD *)a1 + 10);
    if ( v12 + v5 >= a2 )
    {
      v13 = a1[3];
      if ( !v13 )
        return 3221225626LL;
      v14 = a2 - v5;
      if ( a2 <= v5 )
        v14 = 0;
      v15 = v12 - v14;
      v16 = v14;
      v17 = a4 - v6;
      if ( a4 - v6 >= v15 )
        v17 = v15;
      v18 = (void *)(a3 + v6);
      v19 = v17;
      if ( a5 )
      {
        v20 = (const void *)(a3 + v6);
        v18 = (void *)(v16 + v13);
      }
      else
      {
        v20 = (const void *)(v16 + v13);
      }
      memmove(v18, v20, v17);
      v6 += v19;
    }
    v5 += *((_DWORD *)a1 + 10);
    a1 = (__int64 *)*a1;
  }
  return 0;
}

```

## disassembly

```asm
0x140002560  mov     [rsp+arg_8], rbx
0x140002565  mov     [rsp+arg_10], rbp
0x14000256a  push    rsi
0x14000256b  push    rdi
0x14000256c  push    r12
0x14000256e  push    r14
0x140002570  push    r15
0x140002572  sub     rsp, 20h
0x140002576  xor     ebx, ebx
0x140002578  mov     [rsp+48h+arg_0], r13
0x14000257d  xor     r15d, r15d
0x140002580  lea     edi, [rdx+r9]
0x140002584  mov     ebp, r9d
0x140002587  mov     r12, r8
0x14000258a  mov     esi, edx
0x14000258c  mov     r14, rcx
0x14000258f  cmp     ebx, edi
0x140002591  jnb     short loc_1400025FB
0x140002593  mov     edx, [r14+28h]
0x140002597  lea     eax, [rdx+rbx]
0x14000259a  cmp     eax, esi
0x14000259c  jb      short loc_1400025EB
0x14000259e  mov     r9, [r14+18h]
0x1400025a2  test    r9, r9
0x1400025a5  jz      short loc_1400025F4
0x1400025a7  xor     eax, eax
0x1400025a9  mov     ecx, esi
0x1400025ab  sub     ecx, ebx
0x1400025ad  cmp     esi, ebx
0x1400025af  cmovbe  ecx, eax
0x1400025b2  mov     eax, ebp
0x1400025b4  sub     edx, ecx
0x1400025b6  mov     r8d, ecx
0x1400025b9  sub     eax, r15d
0x1400025bc  mov     ecx, r15d
0x1400025bf  cmp     eax, edx
0x1400025c1  cmovnb  eax, edx
0x1400025c4  add     rcx, r12; void *
0x1400025c7  cmp     [rsp+48h+arg_20], 0
0x1400025cc  mov     r13d, eax
0x1400025cf  lea     rax, [r8+r9]
0x1400025d3  mov     r8d, r13d; Size
0x1400025d6  jz      short loc_1400025E0
0x1400025d8  mov     rdx, rcx
0x1400025db  mov     rcx, rax
0x1400025de  jmp     short loc_1400025E3
0x1400025e0  mov     rdx, rax; Src
0x1400025e3  call    memmove
0x1400025e8  add     r15d, r13d
0x1400025eb  add     ebx, [r14+28h]
0x1400025ef  mov     r14, [r14]
0x1400025f2  jmp     short loc_14000258F
0x1400025f4  mov     eax, 0C000009Ah
0x1400025f9  jmp     short loc_1400025FD
0x1400025fb  xor     eax, eax
0x1400025fd  mov     r13, [rsp+48h+arg_0]
0x140002602  mov     rbx, [rsp+48h+arg_8]
0x140002607  mov     rbp, [rsp+48h+arg_10]
0x14000260c  add     rsp, 20h
0x140002610  pop     r15
0x140002612  pop     r14
0x140002614  pop     r12
0x140002616  pop     rdi
0x140002617  pop     rsi
0x140002618  retn
```
