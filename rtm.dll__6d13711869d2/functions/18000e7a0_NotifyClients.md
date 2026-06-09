# NotifyClients

- ea: `0x18000e7a0`
- end: `0x18000ea18`
- name: `NotifyClients`
- size: `632`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x18000ea20`
- `0x18000eea0`
- `0x18000fa20`
- `0x18000fcb0`
- `0x1800102d0`

## callees

- `0x18000e7a0`
- `0x18001163c`
- `0x180011800`
- `0x18001f946`
- `0x180020010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18000e7f5`
- `KERNEL32!HeapAlloc` at `0x18000e814`
- `KERNEL32!HeapAlloc` at `0x18000e7f5`
- `KERNEL32!HeapAlloc` at `0x18000e814`
- `KERNEL32!HeapFree` at `0x18000e82b`
- `KERNEL32!HeapFree` at `0x18000e8b8`
- `KERNEL32!HeapFree` at `0x18000e9a2`
- `KERNEL32!HeapFree` at `0x18000e9b0`
- `KERNEL32!HeapFree` at `0x18000e9d6`
- `KERNEL32!HeapFree` at `0x18000e9e4`
- `KERNEL32!HeapFree` at `0x18000e82b`
- `KERNEL32!HeapFree` at `0x18000e8b8`
- `KERNEL32!HeapFree` at `0x18000e9a2`
- `KERNEL32!HeapFree` at `0x18000e9b0`
- `KERNEL32!HeapFree` at `0x18000e9d6`
- `KERNEL32!HeapFree` at `0x18000e9e4`
- `KERNEL32!SetEvent` at `0x18000e949`
- `KERNEL32!SetEvent` at `0x18000e949`

## pseudocode

```c
void __fastcall NotifyClients(__int64 a1, __int64 *a2, unsigned int a3, const void *a4, const void *a5)
{
  unsigned int v9; // eax
  unsigned int v10; // r15d
  _QWORD *v11; // rax
  _QWORD *v12; // rdi
  char *v13; // rax
  unsigned int v14; // esi
  unsigned int v15; // esi
  void *v16; // rcx
  const void *v17; // rdx
  void *v18; // r8
  __int64 *v19; // r14
  _QWORD *v20; // rax
  _QWORD *v21; // rcx
  _QWORD *v22; // rsi
  __int64 v24; // rcx
  _QWORD *v25; // rax
  void *v26; // r8
  void *v27; // r8

  (*(void (__fastcall **)(_QWORD, const void *, const void *))(a1 + 336))(a3, a4, a5);
  v9 = *(_DWORD *)(a1 + 280);
  if ( v9 + 84 < v9 )
    return;
  v10 = v9 + 84;
  v11 = HeapAlloc(*(HANDLE *)a1, 0, v9 + 84);
  v12 = v11;
  if ( !v11 )
    return;
  if ( a3 == 3 )
  {
    v13 = (char *)HeapAlloc(*(HANDLE *)a1, 0, v10);
    v12[4] = v13;
    if ( !v13 )
    {
LABEL_5:
      HeapFree(*(HANDLE *)a1, 0, v12);
      return;
    }
  }
  else
  {
    v11[4] = 0;
    v13 = 0;
  }
  *((_DWORD *)v12 + 7) = a3;
  *((_DWORD *)v12 + 6) = 0;
  v12[2] = a2;
  v14 = a3 - 1;
  if ( v14 )
  {
    v15 = v14 - 1;
    if ( v15 )
    {
      if ( v15 != 1 || !a5 )
        goto LABEL_18;
      v16 = v13 + 84;
      v17 = a5;
      goto LABEL_17;
    }
    if ( a5 )
    {
      v17 = a5;
LABEL_16:
      v16 = v12 + 5;
LABEL_17:
      memcpy_0(v16, v17, *(int *)(a1 + 280));
    }
  }
  else if ( a4 )
  {
    v17 = a4;
    goto LABEL_16;
  }
LABEL_18:
  if ( !DoEnterSyncList(a1, a1 + 224, 1) )
    goto LABEL_19;
  v19 = *(__int64 **)(a1 + 240);
  if ( !DoEnterSyncList(a1, a1 + 192, 1) )
  {
    LeaveSyncList(a1, a1 + 224);
LABEL_19:
    v18 = (void *)v12[4];
    if ( v18 )
      HeapFree(*(HANDLE *)a1, 0, v18);
    goto LABEL_5;
  }
  while ( v19 != (__int64 *)(a1 + 240) )
  {
    if ( v19 != a2 && v19[4] )
    {
      ++*((_DWORD *)v12 + 6);
      v20 = (_QWORD *)(a1 + 208);
      if ( *((_DWORD *)v12 + 6) == 1 )
      {
        v21 = *(_QWORD **)(a1 + 216);
        if ( (_QWORD *)*v21 != v20 )
          goto LABEL_46;
        *v12 = v20;
        v12[1] = v21;
        *v21 = v12;
        *(_QWORD *)(a1 + 216) = v12;
        ++*(_DWORD *)(a1 + 32);
      }
      v22 = (_QWORD *)v19[5];
      if ( v22 == v20 )
      {
        SetEvent((HANDLE)v19[4]);
        v19[5] = (__int64)v12;
      }
      else if ( *(_DWORD *)(a1 + 32) > 0x2710u && v22 == (_QWORD *)*v20 )
      {
        v19[5] = *v22;
        if ( (*((_DWORD *)v22 + 6))-- == 1 )
        {
          --*(_DWORD *)(a1 + 32);
          v24 = *v22;
          if ( *(_QWORD **)(*v22 + 8LL) != v22 || (v25 = (_QWORD *)v22[1], (_QWORD *)*v25 != v22) )
LABEL_46:
            __fastfail(3u);
          *v25 = v24;
          *(_QWORD *)(v24 + 8) = v25;
          v26 = (void *)v22[4];
          if ( v26 )
            HeapFree(*(HANDLE *)a1, 0, v26);
          HeapFree(*(HANDLE *)a1, 0, v22);
        }
      }
    }
    v19 = (__int64 *)*v19;
  }
  if ( !*((_DWORD *)v12 + 6) )
  {
    v27 = (void *)v12[4];
    if ( v27 )
      HeapFree(*(HANDLE *)a1, 0, v27);
    HeapFree(*(HANDLE *)a1, 0, v12);
  }
  LeaveSyncList(a1, a1 + 192);
  LeaveSyncList(a1, a1 + 224);
}

```

## disassembly

```asm
0x18000e7a0  push    rbx
0x18000e7a2  push    rbp
0x18000e7a3  push    rsi
0x18000e7a4  push    rdi
0x18000e7a5  push    r12
0x18000e7a7  push    r13
0x18000e7a9  push    r14
0x18000e7ab  push    r15
0x18000e7ad  sub     rsp, 28h
0x18000e7b1  mov     rbp, [rsp+68h+arg_20]
0x18000e7b9  mov     rbx, rcx
0x18000e7bc  mov     esi, r8d
0x18000e7bf  mov     r13, rdx
0x18000e7c2  mov     r8, rbp
0x18000e7c5  mov     rdx, r9
0x18000e7c8  mov     ecx, esi
0x18000e7ca  mov     r14, r9
0x18000e7cd  mov     rax, [rbx+150h]
0x18000e7d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e7d9  mov     eax, [rbx+118h]
0x18000e7df  lea     ecx, [rax+54h]
0x18000e7e2  cmp     ecx, eax
0x18000e7e4  jb      loc_18000EA00
0x18000e7ea  mov     r15d, ecx
0x18000e7ed  xor     edx, edx; dwFlags
0x18000e7ef  mov     r8d, ecx; dwBytes
0x18000e7f2  mov     rcx, [rbx]; hHeap
0x18000e7f5  call    cs:__imp_HeapAlloc
0x18000e7fb  mov     rdi, rax
0x18000e7fe  test    rax, rax
0x18000e801  jz      loc_18000EA00
0x18000e807  cmp     esi, 3
0x18000e80a  jnz     short loc_18000E836
0x18000e80c  mov     rcx, [rbx]; hHeap
0x18000e80f  mov     r8d, r15d; dwBytes
0x18000e812  xor     edx, edx; dwFlags
0x18000e814  call    cs:__imp_HeapAlloc
0x18000e81a  mov     [rdi+20h], rax
0x18000e81e  test    rax, rax
0x18000e821  jnz     short loc_18000E840
0x18000e823  mov     rcx, [rbx]; hHeap
0x18000e826  mov     r8, rdi; lpMem
0x18000e829  xor     edx, edx; dwFlags
0x18000e82b  call    cs:__imp_HeapFree
0x18000e831  jmp     loc_18000EA00
0x18000e836  mov     qword ptr [rax+20h], 0
0x18000e83e  xor     eax, eax
0x18000e840  mov     [rdi+1Ch], esi
0x18000e843  mov     dword ptr [rdi+18h], 0
0x18000e84a  mov     [rdi+10h], r13
0x18000e84e  sub     esi, 1
0x18000e851  jz      short loc_18000E875
0x18000e853  sub     esi, 1
0x18000e856  jz      short loc_18000E86B
0x18000e858  cmp     esi, 1
0x18000e85b  jnz     short loc_18000E88D
0x18000e85d  test    rbp, rbp
0x18000e860  jz      short loc_18000E88D
0x18000e862  lea     rcx, [rax+54h]
0x18000e866  mov     rdx, rbp
0x18000e869  jmp     short loc_18000E881
0x18000e86b  test    rbp, rbp
0x18000e86e  jz      short loc_18000E88D
0x18000e870  mov     rdx, rbp
0x18000e873  jmp     short loc_18000E87D
0x18000e875  test    r14, r14
0x18000e878  jz      short loc_18000E88D
0x18000e87a  mov     rdx, r14; Src
0x18000e87d  lea     rcx, [rdi+28h]; void *
0x18000e881  movsxd  r8, dword ptr [rbx+118h]; Size
0x18000e888  call    memcpy_0
0x18000e88d  lea     rbp, [rbx+0E0h]
0x18000e894  mov     r8b, 1
0x18000e897  mov     rdx, rbp
0x18000e89a  mov     rcx, rbx
0x18000e89d  call    DoEnterSyncList
0x18000e8a2  test    al, al
0x18000e8a4  jnz     short loc_18000E8C3
0x18000e8a6  mov     r8, [rdi+20h]; lpMem
0x18000e8aa  test    r8, r8
0x18000e8ad  jz      loc_18000E823
0x18000e8b3  mov     rcx, [rbx]; hHeap
0x18000e8b6  xor     edx, edx; dwFlags
0x18000e8b8  call    cs:__imp_HeapFree
0x18000e8be  jmp     loc_18000E823
0x18000e8c3  lea     r12, [rbx+0C0h]
0x18000e8ca  mov     r8b, 1
0x18000e8cd  lea     r15, [rbx+0F0h]
0x18000e8d4  mov     rdx, r12
0x18000e8d7  mov     r14, [r15]
0x18000e8da  mov     rcx, rbx
0x18000e8dd  call    DoEnterSyncList
0x18000e8e2  test    al, al
0x18000e8e4  jnz     loc_18000E9B9
0x18000e8ea  mov     rdx, rbp
0x18000e8ed  mov     rcx, rbx
0x18000e8f0  call    LeaveSyncList
0x18000e8f5  jmp     short loc_18000E8A6
0x18000e8f7  cmp     r14, r13
0x18000e8fa  jz      loc_18000E9B6
0x18000e900  cmp     qword ptr [r14+20h], 0
0x18000e905  jz      loc_18000E9B6
0x18000e90b  inc     dword ptr [rdi+18h]
0x18000e90e  lea     rax, [rbx+0D0h]
0x18000e915  cmp     dword ptr [rdi+18h], 1
0x18000e919  jnz     short loc_18000E93C
0x18000e91b  mov     rcx, [rbx+0D8h]
0x18000e922  cmp     [rcx], rax
0x18000e925  jnz     loc_18000EA11
0x18000e92b  mov     [rdi], rax
0x18000e92e  mov     [rdi+8], rcx
0x18000e932  mov     [rcx], rdi
0x18000e935  mov     [rax+8], rdi
0x18000e939  inc     dword ptr [rbx+20h]
0x18000e93c  mov     rsi, [r14+28h]
0x18000e940  cmp     rsi, rax
0x18000e943  jnz     short loc_18000E955
0x18000e945  mov     rcx, [r14+20h]; hEvent
0x18000e949  call    cs:__imp_SetEvent
0x18000e94f  mov     [r14+28h], rdi
0x18000e953  jmp     short loc_18000E9B6
0x18000e955  cmp     dword ptr [rbx+20h], 2710h
0x18000e95c  jbe     short loc_18000E9B6
0x18000e95e  cmp     rsi, [rax]
0x18000e961  jnz     short loc_18000E9B6
0x18000e963  mov     rax, [rsi]
0x18000e966  mov     [r14+28h], rax
0x18000e96a  add     dword ptr [rsi+18h], 0FFFFFFFFh
0x18000e96e  jnz     short loc_18000E9B6
0x18000e970  dec     dword ptr [rbx+20h]
0x18000e973  mov     rcx, [rsi]
0x18000e976  cmp     [rcx+8], rsi
0x18000e97a  jnz     loc_18000EA11
0x18000e980  mov     rax, [rsi+8]
0x18000e984  cmp     [rax], rsi
0x18000e987  jnz     loc_18000EA11
0x18000e98d  mov     [rax], rcx
0x18000e990  mov     [rcx+8], rax
0x18000e994  mov     r8, [rsi+20h]; lpMem
0x18000e998  test    r8, r8
0x18000e99b  jz      short loc_18000E9A8
0x18000e99d  mov     rcx, [rbx]; hHeap
0x18000e9a0  xor     edx, edx; dwFlags
0x18000e9a2  call    cs:__imp_HeapFree
0x18000e9a8  mov     rcx, [rbx]; hHeap
0x18000e9ab  mov     r8, rsi; lpMem
0x18000e9ae  xor     edx, edx; dwFlags
0x18000e9b0  call    cs:__imp_HeapFree
0x18000e9b6  mov     r14, [r14]
0x18000e9b9  cmp     r14, r15
0x18000e9bc  jnz     loc_18000E8F7
0x18000e9c2  cmp     dword ptr [rdi+18h], 0
0x18000e9c6  jnz     short loc_18000E9EA
0x18000e9c8  mov     r8, [rdi+20h]; lpMem
0x18000e9cc  test    r8, r8
0x18000e9cf  jz      short loc_18000E9DC
0x18000e9d1  mov     rcx, [rbx]; hHeap
0x18000e9d4  xor     edx, edx; dwFlags
0x18000e9d6  call    cs:__imp_HeapFree
0x18000e9dc  mov     rcx, [rbx]; hHeap
0x18000e9df  mov     r8, rdi; lpMem
0x18000e9e2  xor     edx, edx; dwFlags
0x18000e9e4  call    cs:__imp_HeapFree
0x18000e9ea  mov     rdx, r12
0x18000e9ed  mov     rcx, rbx
0x18000e9f0  call    LeaveSyncList
0x18000e9f5  mov     rdx, rbp
0x18000e9f8  mov     rcx, rbx
0x18000e9fb  call    LeaveSyncList
0x18000ea00  add     rsp, 28h
0x18000ea04  pop     r15
0x18000ea06  pop     r14
0x18000ea08  pop     r13
0x18000ea0a  pop     r12
0x18000ea0c  pop     rdi
0x18000ea0d  pop     rsi
0x18000ea0e  pop     rbp
0x18000ea0f  pop     rbx
0x18000ea10  retn
0x18000ea11  mov     ecx, 3
0x18000ea16  int     29h; Win8: RtlFailFast(ecx)
```
