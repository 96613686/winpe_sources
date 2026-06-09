# DPA_InsertPtr

- ea: `0x180008300`
- end: `0x18000841d`
- name: `DPA_InsertPtr`
- size: `285`
- prototype: `int __stdcall(HDPA hdpa, int i, void *p)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x180006ba0`
- `0x180007cb0`
- `0x180008270`
- `0x180008640`
- `0x1800092e0`
- `0x18000ad20`
- `0x180011e80`

## callees

- `0x180008300`
- `0x180016cf5`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x1800083a5`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x1800083a5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800083b0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800083b0`

## pseudocode

```c
int __stdcall DPA_InsertPtr(HDPA hdpa, int i, void *p)
{
  int v4; // ebx
  unsigned int v6; // eax
  unsigned int v7; // ecx
  int v8; // eax
  int v9; // r8d
  unsigned int v10; // eax
  int v11; // ebp
  SIZE_T v12; // rax
  void *v13; // r8
  void *v14; // rcx
  LPVOID v15; // rax
  int v16; // eax
  int result; // eax

  v4 = i;
  if ( !hdpa || i < 0 )
    return -1;
  v6 = *(_DWORD *)hdpa;
  if ( i > *(_DWORD *)hdpa )
    v4 = *(_DWORD *)hdpa;
  v7 = v6 + 1;
  if ( v6 + 1 < v6 )
    return -1;
  v8 = *((_DWORD *)hdpa + 6);
  if ( v8 < 0 )
    return -1;
  if ( v7 > v8 && (int)v7 > v8 )
  {
    v9 = *((_DWORD *)hdpa + 7);
    v10 = v7 + v9 - 1;
    if ( v10 >= v7 && v10 <= 0x7FFFFFFF )
    {
      v11 = v9 * ((int)v10 / v9);
      v12 = 8LL * v11;
      if ( is_mul_ok(8u, v11) )
      {
        v13 = (void *)*((_QWORD *)hdpa + 1);
        v14 = (void *)*((_QWORD *)hdpa + 2);
        v15 = v13 ? HeapReAlloc(v14, 8u, v13, v12) : HeapAlloc(v14, 8u, v12);
        if ( v15 )
        {
          *((_QWORD *)hdpa + 1) = v15;
          v16 = *((_DWORD *)hdpa + 7);
          *((_DWORD *)hdpa + 6) = v11;
          if ( v16 < 256 )
            *((_DWORD *)hdpa + 7) = 2 * v16;
          goto LABEL_18;
        }
      }
    }
    return -1;
  }
LABEL_18:
  if ( v4 < *(_DWORD *)hdpa )
    memmove_0(
      (void *)(*((_QWORD *)hdpa + 1) + 8LL * (v4 + 1)),
      (const void *)(*((_QWORD *)hdpa + 1) + 8LL * v4),
      8LL * (*(_DWORD *)hdpa - v4));
  result = v4;
  *(_QWORD *)(*((_QWORD *)hdpa + 1) + 8LL * v4) = p;
  ++*(_DWORD *)hdpa;
  return result;
}

```

## disassembly

```asm
0x180008300  mov     [rsp+arg_10], rbx
0x180008305  push    rbp
0x180008306  push    rsi
0x180008307  push    rdi
0x180008308  sub     rsp, 30h
0x18000830c  mov     rsi, r8
0x18000830f  mov     ebx, edx
0x180008311  mov     rdi, rcx
0x180008314  test    rcx, rcx
0x180008317  jz      loc_18000840B
0x18000831d  test    edx, edx
0x18000831f  js      loc_18000840B
0x180008325  mov     eax, [rcx]
0x180008327  cmp     edx, eax
0x180008329  jle     short loc_18000832D
0x18000832b  mov     ebx, eax
0x18000832d  lea     ecx, [rax+1]
0x180008330  cmp     ecx, eax
0x180008332  jb      loc_18000840B
0x180008338  mov     eax, [rdi+18h]
0x18000833b  test    eax, eax
0x18000833d  js      loc_18000840B
0x180008343  cmp     ecx, eax
0x180008345  jbe     loc_1800083D1
0x18000834b  jle     loc_1800083D1
0x180008351  mov     r8d, [rdi+1Ch]
0x180008355  lea     eax, [r8-1]
0x180008359  add     eax, ecx
0x18000835b  cmp     eax, ecx
0x18000835d  jb      loc_18000840B
0x180008363  cmp     eax, 7FFFFFFFh
0x180008368  ja      loc_18000840B
0x18000836e  cdq
0x18000836f  mov     [rsp+48h+var_28], 0
0x180008378  idiv    r8d
0x18000837b  mov     r10d, 8
0x180008381  mov     ebp, eax
0x180008383  imul    ebp, r8d
0x180008387  movsxd  rax, ebp
0x18000838a  mul     r10
0x18000838d  test    rdx, rdx
0x180008390  jnz     short loc_18000840B
0x180008392  mov     r8, [rdi+8]; lpMem
0x180008396  mov     edx, r10d; dwFlags
0x180008399  mov     rcx, [rdi+10h]; hHeap
0x18000839d  test    r8, r8
0x1800083a0  jz      short loc_1800083AD
0x1800083a2  mov     r9, rax; dwBytes
0x1800083a5  call    cs:__imp_HeapReAlloc
0x1800083ab  jmp     short loc_1800083B6
0x1800083ad  mov     r8, rax; dwBytes
0x1800083b0  call    cs:__imp_HeapAlloc
0x1800083b6  test    rax, rax
0x1800083b9  jz      short loc_18000840B
0x1800083bb  mov     [rdi+8], rax
0x1800083bf  mov     eax, [rdi+1Ch]
0x1800083c2  mov     [rdi+18h], ebp
0x1800083c5  cmp     eax, 100h
0x1800083ca  jge     short loc_1800083D1
0x1800083cc  add     eax, eax
0x1800083ce  mov     [rdi+1Ch], eax
0x1800083d1  mov     eax, [rdi]
0x1800083d3  cmp     ebx, eax
0x1800083d5  jge     short loc_1800083FA
0x1800083d7  mov     r10, [rdi+8]
0x1800083db  sub     eax, ebx
0x1800083dd  movsxd  rcx, ebx
0x1800083e0  movsxd  r8, eax
0x1800083e3  shl     r8, 3; Size
0x1800083e7  lea     rdx, [r10+rcx*8]; Src
0x1800083eb  lea     ecx, [rbx+1]
0x1800083ee  movsxd  r9, ecx
0x1800083f1  lea     rcx, [r10+r9*8]; void *
0x1800083f5  call    memmove_0
0x1800083fa  mov     rcx, [rdi+8]
0x1800083fe  mov     eax, ebx
0x180008400  movsxd  rdx, ebx
0x180008403  mov     [rcx+rdx*8], rsi
0x180008407  inc     dword ptr [rdi]
0x180008409  jmp     short loc_180008410
0x18000840b  mov     eax, 0FFFFFFFFh
0x180008410  mov     rbx, [rsp+48h+arg_10]
0x180008415  add     rsp, 30h
0x180008419  pop     rdi
0x18000841a  pop     rsi
0x18000841b  pop     rbp
0x18000841c  retn
```
