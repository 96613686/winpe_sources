# updatewindow

- ea: `0x180004030`
- end: `0x180004140`
- name: `updatewindow`
- size: `272`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180002450`

## callees

- `0x180004030`
- `0x180009e76`
- `0x18003d010`

## pseudocode

```c
__int64 __fastcall updatewindow(__int64 a1, __int64 a2, unsigned int a3)
{
  __int64 v3; // rbx
  __int64 v5; // rbp
  char *v6; // r9
  __int64 v7; // rax
  unsigned int v9; // edi
  unsigned int v10; // eax
  __int64 v11; // rcx
  unsigned int v12; // edi
  unsigned int v13; // ebp
  unsigned int v14; // ecx
  unsigned int v15; // eax

  v3 = *(_QWORD *)(a1 + 40);
  v5 = a3;
  v6 = *(char **)(v3 + 64);
  if ( !v6 )
  {
    v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(a1 + 48))(
           *(_QWORD *)(a1 + 64),
           (unsigned int)(1 << *(_DWORD *)(v3 + 48)),
           1);
    *(_QWORD *)(v3 + 64) = v7;
    v6 = (char *)v7;
    if ( !v7 )
      return 1;
  }
  v9 = *(_DWORD *)(v3 + 52);
  if ( !v9 )
  {
    v9 = 1 << *(_DWORD *)(v3 + 48);
    *(_DWORD *)(v3 + 52) = v9;
    *(_QWORD *)(v3 + 56) = 0;
  }
  if ( (unsigned int)v5 < v9 )
  {
    v11 = *(unsigned int *)(v3 + 60);
    v12 = v9 - v11;
    if ( v12 > (unsigned int)v5 )
      v12 = v5;
    memcpy_0(&v6[v11], (const void *)(a2 - v5), v12);
    v13 = v5 - v12;
    if ( v13 )
    {
      memcpy_0(*(void **)(v3 + 64), (const void *)(a2 - v13), v13);
      v10 = *(_DWORD *)(v3 + 52);
      *(_DWORD *)(v3 + 60) = v13;
    }
    else
    {
      *(_DWORD *)(v3 + 60) += v12;
      v14 = *(_DWORD *)(v3 + 52);
      if ( *(_DWORD *)(v3 + 60) == v14 )
        *(_DWORD *)(v3 + 60) = 0;
      v15 = *(_DWORD *)(v3 + 56);
      if ( v15 >= v14 )
        return 0;
      v10 = v12 + v15;
    }
  }
  else
  {
    memcpy_0(v6, (const void *)(a2 - v9), v9);
    v10 = *(_DWORD *)(v3 + 52);
    *(_DWORD *)(v3 + 60) = 0;
  }
  *(_DWORD *)(v3 + 56) = v10;
  return 0;
}

```

## disassembly

```asm
0x180004030  mov     [rsp+arg_10], rbx
0x180004035  push    rbp
0x180004036  push    rsi
0x180004037  push    r14
0x180004039  sub     rsp, 20h
0x18000403d  mov     rbx, [rcx+28h]
0x180004041  mov     rsi, rdx
0x180004044  mov     ebp, r8d
0x180004047  mov     rax, rcx
0x18000404a  mov     r9, [rbx+40h]
0x18000404e  test    r9, r9
0x180004051  jnz     short loc_18000408F
0x180004053  mov     ecx, [rbx+30h]
0x180004056  mov     edx, 1
0x18000405b  shl     edx, cl
0x18000405d  mov     r8d, 1
0x180004063  mov     rcx, [rax+40h]
0x180004067  mov     rax, [rax+30h]
0x18000406b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004070  mov     [rbx+40h], rax
0x180004074  mov     r9, rax
0x180004077  test    rax, rax
0x18000407a  jnz     short loc_18000408F
0x18000407c  mov     eax, 1
0x180004081  mov     rbx, [rsp+38h+arg_10]
0x180004086  add     rsp, 20h
0x18000408a  pop     r14
0x18000408c  pop     rsi
0x18000408d  pop     rbp
0x18000408e  retn
0x18000408f  mov     [rsp+38h+arg_0], rdi
0x180004094  mov     edi, [rbx+34h]
0x180004097  mov     [rsp+38h+arg_8], r15
0x18000409c  xor     r15d, r15d
0x18000409f  test    edi, edi
0x1800040a1  jnz     short loc_1800040B4
0x1800040a3  mov     ecx, [rbx+30h]
0x1800040a6  mov     edi, 1
0x1800040ab  shl     edi, cl
0x1800040ad  mov     [rbx+34h], edi
0x1800040b0  mov     [rbx+38h], r15
0x1800040b4  cmp     ebp, edi
0x1800040b6  jb      short loc_1800040D2
0x1800040b8  mov     r8d, edi; Size
0x1800040bb  mov     rcx, r9; void *
0x1800040be  sub     rsi, r8
0x1800040c1  mov     rdx, rsi; Src
0x1800040c4  call    memcpy_0
0x1800040c9  mov     eax, [rbx+34h]
0x1800040cc  mov     [rbx+3Ch], r15d
0x1800040d0  jmp     short loc_180004123
0x1800040d2  mov     ecx, [rbx+3Ch]
0x1800040d5  mov     rdx, rsi
0x1800040d8  sub     edi, ecx
0x1800040da  cmp     edi, ebp
0x1800040dc  cmova   edi, ebp
0x1800040df  sub     rdx, rbp; Src
0x1800040e2  mov     r8d, edi; Size
0x1800040e5  add     rcx, r9; void *
0x1800040e8  call    memcpy_0
0x1800040ed  sub     ebp, edi
0x1800040ef  jz      short loc_18000410B
0x1800040f1  mov     rcx, [rbx+40h]; void *
0x1800040f5  mov     r8d, ebp; Size
0x1800040f8  sub     rsi, r8
0x1800040fb  mov     rdx, rsi; Src
0x1800040fe  call    memcpy_0
0x180004103  mov     eax, [rbx+34h]
0x180004106  mov     [rbx+3Ch], ebp
0x180004109  jmp     short loc_180004123
0x18000410b  add     [rbx+3Ch], edi
0x18000410e  mov     ecx, [rbx+34h]
0x180004111  cmp     [rbx+3Ch], ecx
0x180004114  jnz     short loc_18000411A
0x180004116  mov     [rbx+3Ch], r15d
0x18000411a  mov     eax, [rbx+38h]
0x18000411d  cmp     eax, ecx
0x18000411f  jnb     short loc_180004126
0x180004121  add     eax, edi
0x180004123  mov     [rbx+38h], eax
0x180004126  mov     r15, [rsp+38h+arg_8]
0x18000412b  xor     eax, eax
0x18000412d  mov     rdi, [rsp+38h+arg_0]
0x180004132  mov     rbx, [rsp+38h+arg_10]
0x180004137  add     rsp, 20h
0x18000413b  pop     r14
0x18000413d  pop     rsi
0x18000413e  pop     rbp
0x18000413f  retn
```
