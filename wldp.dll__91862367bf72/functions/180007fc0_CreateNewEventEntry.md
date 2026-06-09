# CreateNewEventEntry

- ea: `0x180007fc0`
- end: `0x18000826e`
- name: `CreateNewEventEntry`
- size: `686`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180006dc0`
- `0x180007b2c`

## callees

- `0x180007fc0`
- `0x1800229f8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008053`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008053`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008064`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008064`

## pseudocode

```c
__int64 __fastcall CreateNewEventEntry(__int128 *a1, unsigned __int8 a2, __int64 a3, char a4, int a5, char **a6)
{
  __int64 v6; // rbx
  __int64 v7; // r11
  unsigned __int8 v9; // r10
  __int64 v11; // rbp
  __int64 v12; // rcx
  __int64 v13; // rax
  unsigned __int64 v14; // rbx
  SIZE_T v15; // rdi
  HANDLE ProcessHeap; // rax
  char *v17; // rax
  char *v18; // rcx
  char *v19; // rsi
  unsigned __int8 v20; // r14
  unsigned __int8 v21; // bl
  unsigned __int8 v22; // r12
  __int64 v23; // rax
  __int64 v24; // r15
  char *v25; // r15
  __int128 v26; // xmm0
  __int64 v27; // r14
  __int64 v28; // rbx
  size_t v29; // r8
  char *v30; // rbp
  size_t v32; // r8
  char *v33; // rax
  char *v34; // [rsp+20h] [rbp-58h]
  char *v35; // [rsp+28h] [rbp-50h]
  __int64 v36; // [rsp+30h] [rbp-48h]

  v6 = 0;
  v7 = 0;
  v9 = 0;
  v11 = a3;
  *a6 = 0;
  if ( a2 )
  {
    do
    {
      v12 = *(unsigned int *)(a3 + 16LL * v9 + 8);
      if ( v9 >= 2u )
        v7 += v12;
      v13 = v12 + v6;
      if ( v9 >= 2u )
        v13 = v6;
      ++v9;
      v6 = v13;
    }
    while ( v9 < a2 );
    if ( (unsigned __int64)(v7 + v13) > 0xFFFF )
      return 534;
  }
  v14 = 16LL * a2;
  v15 = v7 + v14 + 46;
  if ( !v15 )
    return 8;
  ProcessHeap = GetProcessHeap();
  v17 = (char *)HeapAlloc(ProcessHeap, 8u, v15);
  v34 = v17;
  v18 = v17;
  if ( !v17 )
    return 8;
  if ( v14 && v15 >= v14 )
  {
    v19 = &v17[v14];
    v15 -= v14;
  }
  else
  {
    v19 = v17;
    v18 = 0;
    v34 = 0;
  }
  v20 = 0;
  v21 = a4 + 2;
  v22 = a4 + 2;
  if ( a4 != -2 )
  {
    v23 = 0;
    v36 = 0;
    do
    {
      v24 = 2 * v23;
      if ( v20 >= 2u )
      {
        v32 = *(unsigned int *)(v11 + 16 * v23 + 8);
        if ( *(_DWORD *)(v11 + 16 * v23 + 8) && v15 >= v32 )
        {
          v33 = v19;
          v19 += v32;
          v15 -= v32;
        }
        else
        {
          v33 = 0;
        }
        v35 = v33;
        memcpy_0(v33, *(const void **)(v11 + 8 * v24), v32);
        v18 = v34;
        *(_QWORD *)&v34[8 * v24] = v35;
        *(_DWORD *)&v34[8 * v24 + 12] = *(_DWORD *)(v11 + 8 * v24 + 12);
        *(_DWORD *)&v34[8 * v24 + 8] = *(_DWORD *)(v11 + 8 * v24 + 8);
        v23 = v36;
      }
      else
      {
        *(_OWORD *)&v18[16 * v23] = *(_OWORD *)(v11 + 16 * v23);
      }
      ++v23;
      ++v20;
      v36 = v23;
    }
    while ( v20 < v21 );
  }
  if ( v15 < 0x2E )
  {
    v25 = 0;
  }
  else
  {
    v25 = v19;
    v19 += 46;
    v15 -= 46LL;
  }
  *((_QWORD *)v25 + 2) = v18;
  v26 = *a1;
  v25[45] = a4;
  *((_DWORD *)v25 + 10) = a5;
  v25[44] = a2;
  *(_OWORD *)v25 = v26;
  if ( v21 < a2 )
  {
    v27 = v21;
    do
    {
      v28 = 2 * v27;
      v29 = *(unsigned int *)(v11 + 16 * v27 + 8);
      if ( *(_DWORD *)(v11 + 16 * v27 + 8) && v15 >= v29 )
      {
        v30 = v19;
        v19 += v29;
        v15 -= v29;
      }
      else
      {
        v30 = 0;
      }
      memcpy_0(v30, *(const void **)(a3 + 16 * v27), v29);
      ++v22;
      ++v27;
      *(_QWORD *)(*((_QWORD *)v25 + 2) + 8 * v28) = v30;
      v11 = a3;
      *(_DWORD *)(*((_QWORD *)v25 + 2) + 8 * v28 + 12) = *(_DWORD *)(a3 + 8 * v28 + 12);
      *(_DWORD *)(*((_QWORD *)v25 + 2) + 8 * v28 + 8) = *(_DWORD *)(a3 + 8 * v28 + 8);
    }
    while ( v22 < a2 );
  }
  *a6 = v25;
  return 0;
}

```

## disassembly

```asm
0x180007fc0  mov     [rsp+arg_18], r9b
0x180007fc5  mov     [rsp+arg_10], r8
0x180007fca  mov     [rsp+arg_0], rcx
0x180007fcf  push    rbx
0x180007fd0  push    rbp
0x180007fd1  push    r13
0x180007fd3  push    r15
0x180007fd5  sub     rsp, 58h
0x180007fd9  mov     rax, [rsp+78h+arg_28]
0x180007fe1  xor     ebx, ebx
0x180007fe3  xor     r11d, r11d
0x180007fe6  movzx   r13d, dl
0x180007fea  xor     r10b, r10b
0x180007fed  movzx   r15d, r9b
0x180007ff1  mov     rbp, r8
0x180007ff4  mov     [rax], rbx
0x180007ff7  test    dl, dl
0x180007ff9  jz      short loc_18000803A
0x180007ffb  nop     dword ptr [rax+rax+00h]
0x180008000  movzx   eax, r10b
0x180008004  add     rax, rax
0x180008007  cmp     r10b, 2
0x18000800b  mov     ecx, [r8+rax*8+8]
0x180008010  lea     rax, [rcx+r11]
0x180008014  cmovnb  r11, rax
0x180008018  lea     rax, [rcx+rbx]
0x18000801c  cmovnb  rax, rbx
0x180008020  inc     r10b
0x180008023  mov     rbx, rax
0x180008026  cmp     r10b, r13b
0x180008029  jb      short loc_180008000
0x18000802b  add     rax, r11
0x18000802e  cmp     rax, 0FFFFh
0x180008034  ja      loc_180008232
0x18000803a  mov     [rsp+78h+var_28], rdi
0x18000803f  mov     rbx, r13
0x180008042  shl     rbx, 4
0x180008046  lea     rdi, [rbx+2Eh]
0x18000804a  add     rdi, r11
0x18000804d  jz      loc_180008264
0x180008053  call    cs:__imp_GetProcessHeap
0x180008059  mov     r8, rdi; dwBytes
0x18000805c  mov     edx, 8; dwFlags
0x180008061  mov     rcx, rax; hHeap
0x180008064  call    cs:__imp_HeapAlloc
0x18000806a  mov     [rsp+78h+var_58], rax
0x18000806f  mov     rcx, rax
0x180008072  test    rax, rax
0x180008075  jz      loc_180008264
0x18000807b  mov     [rsp+78h+var_30], r12
0x180008080  mov     [rsp+78h+var_38], r14
0x180008085  mov     [rsp+78h+arg_8], rsi
0x18000808d  test    rbx, rbx
0x180008090  jz      loc_180008242
0x180008096  cmp     rdi, rbx
0x180008099  jb      loc_180008242
0x18000809f  lea     rsi, [rbx+rax]
0x1800080a3  sub     rdi, rbx
0x1800080a6  xor     r14b, r14b
0x1800080a9  movzx   ebx, r15b
0x1800080ad  add     bl, 2
0x1800080b0  movzx   r12d, bl
0x1800080b4  jz      short loc_1800080E8
0x1800080b6  xor     eax, eax
0x1800080b8  mov     [rsp+78h+var_48], rax
0x1800080bd  mov     r15, rax
0x1800080c0  add     r15, r15
0x1800080c3  cmp     r14b, 2
0x1800080c7  jnb     loc_1800081DC
0x1800080cd  movups  xmm0, xmmword ptr [rbp+r15*8+0]
0x1800080d3  movups  xmmword ptr [rcx+r15*8], xmm0
0x1800080d8  inc     rax
0x1800080db  inc     r14b
0x1800080de  mov     [rsp+78h+var_48], rax
0x1800080e3  cmp     r14b, bl
0x1800080e6  jb      short loc_1800080BD
0x1800080e8  cmp     rdi, 2Eh ; '.'
0x1800080ec  jb      loc_180008255
0x1800080f2  mov     r15, rsi
0x1800080f5  add     rsi, 2Eh ; '.'
0x1800080f9  sub     rdi, 2Eh ; '.'
0x1800080fd  mov     rax, [rsp+78h+arg_0]
0x180008105  mov     [r15+10h], rcx
0x180008109  movups  xmm0, xmmword ptr [rax]
0x18000810c  movzx   eax, [rsp+78h+arg_18]
0x180008114  mov     [r15+2Dh], al
0x180008118  mov     eax, [rsp+78h+arg_20]
0x18000811f  mov     [r15+28h], eax
0x180008123  mov     [r15+2Ch], r13b
0x180008127  movups  xmmword ptr [r15], xmm0
0x18000812b  cmp     bl, r13b
0x18000812e  jnb     short loc_1800081AD
0x180008130  movzx   r14d, bl
0x180008134  nop     dword ptr [rax+00h]
0x180008138  nop     dword ptr [rax+rax+00000000h]
0x180008140  mov     rbx, r14
0x180008143  add     rbx, rbx
0x180008146  mov     r8d, [rbp+rbx*8+8]; Size
0x18000814b  test    r8, r8
0x18000814e  jz      loc_18000825D
0x180008154  cmp     rdi, r8
0x180008157  jb      loc_18000825D
0x18000815d  mov     rbp, rsi
0x180008160  add     rsi, r8
0x180008163  sub     rdi, r8
0x180008166  mov     rdx, [rsp+78h+arg_10]
0x18000816e  mov     rcx, rbp; void *
0x180008171  mov     rdx, [rdx+rbx*8]; Src
0x180008175  call    memcpy_0
0x18000817a  mov     rax, [r15+10h]
0x18000817e  inc     r12b
0x180008181  inc     r14
0x180008184  mov     [rax+rbx*8], rbp
0x180008188  mov     rcx, [r15+10h]
0x18000818c  mov     rbp, [rsp+78h+arg_10]
0x180008194  mov     eax, [rbp+rbx*8+0Ch]
0x180008198  mov     [rcx+rbx*8+0Ch], eax
0x18000819c  mov     rcx, [r15+10h]
0x1800081a0  mov     eax, [rbp+rbx*8+8]
0x1800081a4  mov     [rcx+rbx*8+8], eax
0x1800081a8  cmp     r12b, r13b
0x1800081ab  jb      short loc_180008140
0x1800081ad  mov     rax, [rsp+78h+arg_28]
0x1800081b5  mov     r14, [rsp+78h+var_38]
0x1800081ba  mov     r12, [rsp+78h+var_30]
0x1800081bf  mov     rsi, [rsp+78h+arg_8]
0x1800081c7  mov     [rax], r15
0x1800081ca  xor     eax, eax
0x1800081cc  mov     rdi, [rsp+78h+var_28]
0x1800081d1  add     rsp, 58h
0x1800081d5  pop     r15
0x1800081d7  pop     r13
0x1800081d9  pop     rbp
0x1800081da  pop     rbx
0x1800081db  retn
0x1800081dc  mov     r8d, [rbp+r15*8+8]; Size
0x1800081e1  test    r8, r8
0x1800081e4  jz      short loc_180008251
0x1800081e6  cmp     rdi, r8
0x1800081e9  jb      short loc_180008251
0x1800081eb  mov     rax, rsi
0x1800081ee  add     rsi, r8
0x1800081f1  sub     rdi, r8
0x1800081f4  mov     rdx, [rbp+r15*8+0]; Src
0x1800081f9  mov     rcx, rax; void *
0x1800081fc  mov     [rsp+78h+var_50], rax
0x180008201  call    memcpy_0
0x180008206  mov     rcx, [rsp+78h+var_58]
0x18000820b  mov     rax, [rsp+78h+var_50]
0x180008210  mov     [rcx+r15*8], rax
0x180008214  mov     eax, [rbp+r15*8+0Ch]
0x180008219  mov     [rcx+r15*8+0Ch], eax
0x18000821e  mov     eax, [rbp+r15*8+8]
0x180008223  mov     [rcx+r15*8+8], eax
0x180008228  mov     rax, [rsp+78h+var_48]
0x18000822d  jmp     loc_1800080D8
0x180008232  mov     eax, 216h
0x180008237  add     rsp, 58h
0x18000823b  pop     r15
0x18000823d  pop     r13
0x18000823f  pop     rbp
0x180008240  pop     rbx
0x180008241  retn
0x180008242  mov     rsi, rcx
0x180008245  xor     ecx, ecx
0x180008247  mov     [rsp+78h+var_58], rcx
0x18000824c  jmp     loc_1800080A6
0x180008251  xor     eax, eax
0x180008253  jmp     short loc_1800081F4
0x180008255  xor     r15d, r15d
0x180008258  jmp     loc_1800080FD
0x18000825d  xor     ebp, ebp
0x18000825f  jmp     loc_180008166
0x180008264  mov     eax, 8
0x180008269  jmp     loc_1800081CC
```
