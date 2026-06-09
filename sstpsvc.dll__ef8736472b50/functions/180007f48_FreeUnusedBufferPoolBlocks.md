# FreeUnusedBufferPoolBlocks

- ea: `0x180007f48`
- end: `0x180007ff0`
- name: `FreeUnusedBufferPoolBlocks`
- size: `168`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x1800011b0`
- `0x180001b40`
- `0x180001fe0`
- `0x180002320`
- `0x180002f80`
- `0x180003010`
- `0x180008cd8`

## callees

- `0x180007f48`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007fcb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007fcb`

## pseudocode

```c
void __fastcall FreeUnusedBufferPoolBlocks(unsigned int *a1)
{
  unsigned int *v1; // rbx
  unsigned int *v3; // r8
  unsigned int v4; // eax
  unsigned int *v5; // rsi
  unsigned int v6; // r9d
  __int64 *v7; // rdx
  __int64 *v8; // rax
  __int64 v9; // rcx
  _QWORD *v10; // rax
  unsigned int *v11; // rcx

  v1 = a1 + 6;
  v3 = (unsigned int *)*((_QWORD *)a1 + 3);
  if ( v3 != a1 + 6 )
  {
    do
    {
      v4 = v3[6];
      v5 = *(unsigned int **)v3;
      if ( v3[7] >= v4 )
      {
        v6 = 0;
        v7 = (__int64 *)(v3 + 8);
        if ( v4 )
        {
          do
          {
            v8 = (__int64 *)v7[1];
            ++v6;
            v9 = *v7;
            *v8 = *v7;
            *(_QWORD *)(v9 + 8) = v8;
            v7[1] = (__int64)v7;
            *v7 = (__int64)v7;
            v7 = (__int64 *)((char *)v7 + *a1 + 24);
          }
          while ( v6 < v3[6] );
        }
        v10 = (_QWORD *)*((_QWORD *)v3 + 1);
        v11 = *(unsigned int **)v3;
        *v10 = *(_QWORD *)v3;
        *((_QWORD *)v11 + 1) = v10;
        LODWORD(v10) = v3[6];
        *((_QWORD *)v3 + 1) = v3;
        *(_QWORD *)v3 = v3;
        a1[3] -= (unsigned int)v10;
        HeapFree(*((HANDLE *)a1 + 7), 0, v3 - 4);
      }
      v3 = v5;
    }
    while ( v5 != v1 );
  }
}

```

## disassembly

```asm
0x180007f48  mov     [rsp+arg_0], rbx
0x180007f4d  mov     [rsp+arg_8], rsi
0x180007f52  push    rdi
0x180007f53  sub     rsp, 20h
0x180007f57  lea     rbx, [rcx+18h]
0x180007f5b  mov     rdi, rcx
0x180007f5e  mov     r8, [rbx]
0x180007f61  cmp     r8, rbx
0x180007f64  jz      short loc_180007FDF
0x180007f66  mov     eax, [r8+18h]
0x180007f6a  mov     rsi, [r8]
0x180007f6d  cmp     [r8+1Ch], eax
0x180007f71  jb      short loc_180007FD7
0x180007f73  xor     r9d, r9d
0x180007f76  lea     rdx, [r8+20h]
0x180007f7a  test    eax, eax
0x180007f7c  jz      short loc_180007FA5
0x180007f7e  mov     rax, [rdx+8]
0x180007f82  inc     r9d
0x180007f85  mov     rcx, [rdx]
0x180007f88  mov     [rax], rcx
0x180007f8b  mov     [rcx+8], rax
0x180007f8f  mov     [rdx+8], rdx
0x180007f93  mov     [rdx], rdx
0x180007f96  mov     eax, [rdi]
0x180007f98  add     rax, 18h
0x180007f9c  add     rdx, rax
0x180007f9f  cmp     r9d, [r8+18h]
0x180007fa3  jb      short loc_180007F7E
0x180007fa5  mov     rax, [r8+8]
0x180007fa9  xor     edx, edx; dwFlags
0x180007fab  mov     rcx, [r8]
0x180007fae  mov     [rax], rcx
0x180007fb1  mov     [rcx+8], rax
0x180007fb5  mov     eax, [r8+18h]
0x180007fb9  mov     [r8+8], r8
0x180007fbd  mov     [r8], r8
0x180007fc0  add     r8, 0FFFFFFFFFFFFFFF0h; lpMem
0x180007fc4  sub     [rdi+0Ch], eax
0x180007fc7  mov     rcx, [rdi+38h]; hHeap
0x180007fcb  call    cs:__imp_HeapFree
0x180007fd2  nop     dword ptr [rax+rax+00h]
0x180007fd7  mov     r8, rsi
0x180007fda  cmp     rsi, rbx
0x180007fdd  jnz     short loc_180007F66
0x180007fdf  mov     rbx, [rsp+28h+arg_0]
0x180007fe4  mov     rsi, [rsp+28h+arg_8]
0x180007fe9  add     rsp, 20h
0x180007fed  pop     rdi
0x180007fee  retn
```
