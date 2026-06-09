# CheckDownloadSecurity

- ea: `0x18001a2b0`
- end: `0x18001a40b`
- name: `CheckDownloadSecurity`
- size: `347`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800190a4`
- `0x18002173c`

## callees

- `0x180017ee0`
- `0x180019dc0`
- `0x18001a2b0`
- `0x180021a70`
- `0x18002a542`
- `0x18002a54e`

## pseudocode

```c
__int64 __fastcall CheckDownloadSecurity(__int64 a1, __int64 a2, _DWORD *a3)
{
  int v6; // eax
  char *v7; // rdi
  void *v9; // r15
  char *i; // rbp
  __int64 v11; // rbx

  if ( a1 && (v6 = *(unsigned __int16 *)(a2 + 146), (_WORD)v6) && *(_WORD *)(a1 + 2) )
  {
    v7 = (char *)T2malloc((unsigned int)(v6 + 2));
    if ( !v7 )
      return 266;
    v9 = (void *)T2malloc(2 * (unsigned int)*(unsigned __int16 *)(a1 + 2) + 2);
    if ( !v9 )
    {
      T2free(v7);
      return 266;
    }
    memcpy_0(v7, *(const void **)(a2 + 152), *(unsigned __int16 *)(a2 + 146));
    memcpy_0(v9, *(const void **)(a1 + 8), 2LL * *(unsigned __int16 *)(a1 + 2));
    *(_WORD *)(*(_QWORD *)(a1 + 8) + 2 * ((unsigned __int64)*(unsigned __int16 *)(a1 + 2) >> 1)) = 0;
    WideAsciiLower(v9);
    for ( i = v7; i < &v7[*(unsigned __int16 *)(a2 + 146)]; i += 2 * (unsigned __int16)v11 + 2 )
    {
      v11 = -1;
      do
        ++v11;
      while ( *(_WORD *)&i[2 * v11] );
      if ( (_WORD)v11 )
      {
        WideAsciiLower(i);
        if ( *(_WORD *)(a1 + 2) >= (unsigned __int16)v11 && !memcmp_0(v9, i, 2LL * (unsigned __int16)v11) )
        {
          *a3 = 1;
          goto LABEL_17;
        }
      }
    }
    *a3 = 0;
LABEL_17:
    T2free(v7);
    T2free(v9);
  }
  else
  {
    *a3 = 1;
  }
  return 0;
}

```

## disassembly

```asm
0x18001a2b0  push    rbx
0x18001a2b2  push    rbp
0x18001a2b3  push    rdi
0x18001a2b4  push    r12
0x18001a2b6  push    r13
0x18001a2b8  push    r14
0x18001a2ba  push    r15
0x18001a2bc  sub     rsp, 20h
0x18001a2c0  xor     ebx, ebx
0x18001a2c2  mov     r12, r8
0x18001a2c5  mov     r13, rdx
0x18001a2c8  mov     r14, rcx
0x18001a2cb  test    rcx, rcx
0x18001a2ce  jz      loc_18001A3F2
0x18001a2d4  movzx   eax, word ptr [rdx+92h]
0x18001a2db  test    ax, ax
0x18001a2de  jz      loc_18001A3F2
0x18001a2e4  cmp     [rcx+2], bx
0x18001a2e8  jz      loc_18001A3F2
0x18001a2ee  lea     ecx, [rax+2]; dwBytes
0x18001a2f1  lea     edx, [rbx+1]
0x18001a2f4  call    T2malloc
0x18001a2f9  mov     rdi, rax
0x18001a2fc  test    rax, rax
0x18001a2ff  jnz     short loc_18001A30B
0x18001a301  mov     eax, 10Ah
0x18001a306  jmp     loc_18001A3FB
0x18001a30b  movzx   ecx, word ptr [r14+2]
0x18001a310  mov     edx, 1
0x18001a315  lea     ecx, ds:2[rcx*2]; dwBytes
0x18001a31c  call    T2malloc
0x18001a321  mov     r15, rax
0x18001a324  mov     rcx, rdi; lpMem
0x18001a327  test    rax, rax
0x18001a32a  jnz     short loc_18001A333
0x18001a32c  call    T2free
0x18001a331  jmp     short loc_18001A301
0x18001a333  movzx   r8d, word ptr [r13+92h]; Size
0x18001a33b  mov     rdx, [r13+98h]; Src
0x18001a342  call    memcpy_0
0x18001a347  movzx   r8d, word ptr [r14+2]
0x18001a34c  mov     rcx, r15; void *
0x18001a34f  mov     rdx, [r14+8]; Src
0x18001a353  add     r8, r8; Size
0x18001a356  call    memcpy_0
0x18001a35b  movzx   edx, word ptr [r14+2]
0x18001a360  mov     rcx, [r14+8]
0x18001a364  shr     rdx, 1
0x18001a367  mov     [rcx+rdx*2], bx
0x18001a36b  mov     rcx, r15
0x18001a36e  call    WideAsciiLower
0x18001a373  mov     rbp, rdi
0x18001a376  movzx   eax, word ptr [r13+92h]
0x18001a37e  add     rax, rdi
0x18001a381  cmp     rbp, rax
0x18001a384  jnb     short loc_18001A3E8
0x18001a386  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001a38a  xor     eax, eax
0x18001a38c  inc     rbx
0x18001a38f  cmp     [rbp+rbx*2+0], ax
0x18001a394  jnz     short loc_18001A38C
0x18001a396  test    bx, bx
0x18001a399  jz      short loc_18001A3C0
0x18001a39b  mov     rcx, rbp
0x18001a39e  call    WideAsciiLower
0x18001a3a3  cmp     [r14+2], bx
0x18001a3a8  jb      short loc_18001A3C0
0x18001a3aa  movzx   r8d, bx
0x18001a3ae  mov     rdx, rbp; Buf2
0x18001a3b1  add     r8, r8; Size
0x18001a3b4  mov     rcx, r15; Buf1
0x18001a3b7  call    memcmp_0
0x18001a3bc  test    eax, eax
0x18001a3be  jz      short loc_18001A3CE
0x18001a3c0  movzx   eax, bx
0x18001a3c3  lea     rbp, [rbp+rax*2+0]
0x18001a3c8  add     rbp, 2
0x18001a3cc  jmp     short loc_18001A376
0x18001a3ce  mov     dword ptr [r12], 1
0x18001a3d6  mov     rcx, rdi; lpMem
0x18001a3d9  call    T2free
0x18001a3de  mov     rcx, r15; lpMem
0x18001a3e1  call    T2free
0x18001a3e6  jmp     short loc_18001A3F9
0x18001a3e8  mov     dword ptr [r12], 0
0x18001a3f0  jmp     short loc_18001A3D6
0x18001a3f2  mov     dword ptr [r8], 1
0x18001a3f9  xor     eax, eax
0x18001a3fb  add     rsp, 20h
0x18001a3ff  pop     r15
0x18001a401  pop     r14
0x18001a403  pop     r13
0x18001a405  pop     r12
0x18001a407  pop     rdi
0x18001a408  pop     rbp
0x18001a409  pop     rbx
0x18001a40a  retn
```
