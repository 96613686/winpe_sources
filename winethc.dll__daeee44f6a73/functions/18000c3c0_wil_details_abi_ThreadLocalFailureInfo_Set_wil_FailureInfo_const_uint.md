# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18000c3c0`
- end: `0x18000c5fb`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `571`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800054e0`

## callees

- `0x18000ae8c`
- `0x18000c3c0`
- `0x180012d6e`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000c518`
- `msvcrt!memcpy_s` at `0x18000c56f`
- `msvcrt!memcpy_s` at `0x18000c5c0`
- `msvcrt!memcpy_s` at `0x18000c518`
- `msvcrt!memcpy_s` at `0x18000c56f`
- `msvcrt!memcpy_s` at `0x18000c5c0`
- `KERNEL32!GetProcessHeap` at `0x18000c4a8`
- `KERNEL32!GetProcessHeap` at `0x18000c4a8`
- `KERNEL32!HeapFree` at `0x18000c4bc`
- `KERNEL32!HeapFree` at `0x18000c4bc`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  __int64 v3; // rbp
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rax
  unsigned __int64 v15; // r14
  rsize_t *v16; // rsi
  LPVOID v17; // r15
  void *v18; // rbx
  HANDLE ProcessHeap; // rax
  char *v20; // rbx
  rsize_t v21; // rdx
  char *v22; // rsi
  _BYTE *v23; // r8
  __int64 v24; // rax
  __int64 v25; // r14
  _BYTE *v26; // r8
  __int64 v27; // rax
  __int64 v28; // r14
  _WORD *v29; // r8
  unsigned __int64 v30; // r14

  *((_DWORD *)this + 1) = a3;
  v3 = -1;
  *((_DWORD *)this + 2) = *((_DWORD *)a2 + 2);
  *((_QWORD *)this + 2) = 0;
  *((_WORD *)this + 12) = *((_WORD *)a2 + 32);
  *((_BYTE *)this + 26) = *(_BYTE *)a2;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = *((_QWORD *)a2 + 17);
  *((_QWORD *)this + 6) = *((_QWORD *)a2 + 18);
  *((_QWORD *)this + 7) = 0;
  v6 = *((_QWORD *)a2 + 7);
  v7 = 1;
  if ( v6 )
  {
    v9 = -1;
    do
      ++v9;
    while ( *(_BYTE *)(v6 + v9) );
    v8 = v9 + 1;
  }
  else
  {
    v8 = 1;
  }
  v10 = *((_QWORD *)a2 + 16);
  if ( v10 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *(_BYTE *)(v10 + v11) );
    v7 = v11 + 1;
  }
  v12 = *((_QWORD *)a2 + 3);
  if ( v12 )
  {
    v14 = -1;
    do
      ++v14;
    while ( *(_WORD *)(v12 + 2 * v14) );
    v13 = 2 * v14 + 2;
  }
  else
  {
    v13 = 2;
  }
  v15 = v8 + v7 + v13;
  v16 = (rsize_t *)((char *)this + 72);
  if ( !*((_QWORD *)this + 8) || *v16 < v15 )
  {
    v17 = wil::details::ProcessHeapAlloc(8u, v8 + v7 + v13);
    if ( v17 )
    {
      v18 = (void *)*((_QWORD *)this + 8);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v18);
      *((_QWORD *)this + 8) = v17;
      *v16 = v15;
    }
  }
  v20 = (char *)*((_QWORD *)this + 8);
  if ( v20 )
  {
    v21 = *v16;
    v22 = &v20[*v16];
    if ( v20 != v22 && (v23 = (_BYTE *)*((_QWORD *)a2 + 7)) != 0 && *v23 )
    {
      v24 = -1;
      do
        ++v24;
      while ( v23[v24] );
      v25 = v24 + 1;
      if ( v21 < v24 + 1 )
      {
        *((_QWORD *)this + 2) = 0;
LABEL_30:
        v26 = (_BYTE *)*((_QWORD *)a2 + 16);
        if ( v26 && *v26 )
        {
          v27 = -1;
          do
            ++v27;
          while ( v26[v27] );
          v28 = v27 + 1;
          if ( v22 - v20 < (unsigned __int64)(v27 + 1) )
          {
            *((_QWORD *)this + 4) = 0;
LABEL_39:
            v29 = (_WORD *)*((_QWORD *)a2 + 3);
            if ( v29 && *v29 )
            {
              do
                ++v3;
              while ( v29[v3] );
              v30 = 2 * v3 + 2;
              if ( v22 - v20 >= v30 )
              {
                memcpy_s(v20, v22 - v20, v29, 2 * v3 + 2);
                *((_QWORD *)this + 7) = v20;
                v20 += v30;
LABEL_45:
                memset_0(v20, 0, v22 - v20);
                return;
              }
            }
LABEL_44:
            *((_QWORD *)this + 7) = 0;
            goto LABEL_45;
          }
          memcpy_s(v20, v22 - v20, v26, v27 + 1);
          *((_QWORD *)this + 4) = v20;
          v20 += v28;
LABEL_38:
          if ( v20 == v22 )
            goto LABEL_44;
          goto LABEL_39;
        }
LABEL_37:
        *((_QWORD *)this + 4) = 0;
        goto LABEL_38;
      }
      memcpy_s(*((void *const *)this + 8), v21, v23, v24 + 1);
      *((_QWORD *)this + 2) = v20;
      v20 += v25;
    }
    else
    {
      *((_QWORD *)this + 2) = 0;
    }
    if ( v20 == v22 )
      goto LABEL_37;
    goto LABEL_30;
  }
}

```

## disassembly

```asm
0x18000c3c0  push    rbx
0x18000c3c2  push    rbp
0x18000c3c3  push    rsi
0x18000c3c4  push    rdi
0x18000c3c5  push    r12
0x18000c3c7  push    r13
0x18000c3c9  push    r14
0x18000c3cb  push    r15
0x18000c3cd  sub     rsp, 28h
0x18000c3d1  mov     [rcx+4], r8d
0x18000c3d5  xor     r13d, r13d
0x18000c3d8  mov     eax, [rdx+8]
0x18000c3db  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18000c3df  mov     [rcx+8], eax
0x18000c3e2  mov     rdi, rcx
0x18000c3e5  mov     [rcx+10h], r13
0x18000c3e9  mov     r12, rdx
0x18000c3ec  movzx   eax, word ptr [rdx+40h]
0x18000c3f0  mov     [rcx+18h], ax
0x18000c3f4  mov     al, [rdx]
0x18000c3f6  mov     [rcx+1Ah], al
0x18000c3f9  mov     [rcx+20h], r13
0x18000c3fd  mov     rax, [rdx+88h]
0x18000c404  mov     [rcx+28h], rax
0x18000c408  mov     rax, [rdx+90h]
0x18000c40f  mov     [rcx+30h], rax
0x18000c413  mov     [rcx+38h], r13
0x18000c417  mov     rcx, [rdx+38h]
0x18000c41b  lea     edx, [rbp+2]
0x18000c41e  test    rcx, rcx
0x18000c421  jnz     short loc_18000C428
0x18000c423  mov     r8d, edx
0x18000c426  jmp     short loc_18000C438
0x18000c428  mov     rax, rbp
0x18000c42b  inc     rax
0x18000c42e  cmp     [rcx+rax], r13b
0x18000c432  jnz     short loc_18000C42B
0x18000c434  lea     r8, [rax+1]; unsigned __int64
0x18000c438  mov     rcx, [r12+80h]
0x18000c440  test    rcx, rcx
0x18000c443  jz      short loc_18000C455
0x18000c445  mov     rax, rbp
0x18000c448  inc     rax
0x18000c44b  cmp     [rcx+rax], r13b
0x18000c44f  jnz     short loc_18000C448
0x18000c451  lea     rdx, [rax+1]
0x18000c455  mov     rcx, [r12+18h]
0x18000c45a  test    rcx, rcx
0x18000c45d  jnz     short loc_18000C464
0x18000c45f  lea     eax, [rcx+2]
0x18000c462  jmp     short loc_18000C479
0x18000c464  mov     rax, rbp
0x18000c467  inc     rax
0x18000c46a  cmp     [rcx+rax*2], r13w
0x18000c46f  jnz     short loc_18000C467
0x18000c471  lea     rax, ds:2[rax*2]
0x18000c479  lea     r14, [rdx+rax]
0x18000c47d  add     r14, r8
0x18000c480  lea     rsi, [rdi+48h]
0x18000c484  cmp     [rdi+40h], r13
0x18000c488  jz      short loc_18000C48F
0x18000c48a  cmp     [rsi], r14
0x18000c48d  jnb     short loc_18000C4CF
0x18000c48f  mov     rdx, r14; dwBytes
0x18000c492  mov     ecx, 8; dwFlags
0x18000c497  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000c49c  mov     r15, rax
0x18000c49f  test    rax, rax
0x18000c4a2  jz      short loc_18000C4CF
0x18000c4a4  mov     rbx, [rdi+40h]
0x18000c4a8  call    cs:__imp_GetProcessHeap
0x18000c4af  nop     dword ptr [rax+rax+00h]
0x18000c4b4  mov     r8, rbx; lpMem
0x18000c4b7  xor     edx, edx; dwFlags
0x18000c4b9  mov     rcx, rax; hHeap
0x18000c4bc  call    cs:__imp_HeapFree
0x18000c4c3  nop     dword ptr [rax+rax+00h]
0x18000c4c8  mov     [rdi+40h], r15
0x18000c4cc  mov     [rsi], r14
0x18000c4cf  mov     rbx, [rdi+40h]
0x18000c4d3  test    rbx, rbx
0x18000c4d6  jz      loc_18000C5E9
0x18000c4dc  mov     rdx, [rsi]; DestinationSize
0x18000c4df  lea     rsi, [rdx+rbx]
0x18000c4e3  cmp     rbx, rsi
0x18000c4e6  jz      short loc_18000C52D
0x18000c4e8  mov     r8, [r12+38h]; Source
0x18000c4ed  test    r8, r8
0x18000c4f0  jz      short loc_18000C52D
0x18000c4f2  cmp     [r8], r13b
0x18000c4f5  jz      short loc_18000C52D
0x18000c4f7  mov     rax, rbp
0x18000c4fa  inc     rax
0x18000c4fd  cmp     [r8+rax], r13b
0x18000c501  jnz     short loc_18000C4FA
0x18000c503  lea     r14, [rax+1]
0x18000c507  cmp     rdx, r14
0x18000c50a  jnb     short loc_18000C512
0x18000c50c  mov     [rdi+10h], r13
0x18000c510  jmp     short loc_18000C536
0x18000c512  mov     r9, r14; SourceSize
0x18000c515  mov     rcx, rbx; Destination
0x18000c518  call    cs:__imp_memcpy_s
0x18000c51f  nop     dword ptr [rax+rax+00h]
0x18000c524  mov     [rdi+10h], rbx
0x18000c528  add     rbx, r14
0x18000c52b  jmp     short loc_18000C531
0x18000c52d  mov     [rdi+10h], r13
0x18000c531  cmp     rbx, rsi
0x18000c534  jz      short loc_18000C584
0x18000c536  mov     r8, [r12+80h]; Source
0x18000c53e  test    r8, r8
0x18000c541  jz      short loc_18000C584
0x18000c543  cmp     [r8], r13b
0x18000c546  jz      short loc_18000C584
0x18000c548  mov     rax, rbp
0x18000c54b  inc     rax
0x18000c54e  cmp     [r8+rax], r13b
0x18000c552  jnz     short loc_18000C54B
0x18000c554  mov     rdx, rsi
0x18000c557  lea     r14, [rax+1]
0x18000c55b  sub     rdx, rbx; DestinationSize
0x18000c55e  cmp     rdx, r14
0x18000c561  jnb     short loc_18000C569
0x18000c563  mov     [rdi+20h], r13
0x18000c567  jmp     short loc_18000C58D
0x18000c569  mov     r9, r14; SourceSize
0x18000c56c  mov     rcx, rbx; Destination
0x18000c56f  call    cs:__imp_memcpy_s
0x18000c576  nop     dword ptr [rax+rax+00h]
0x18000c57b  mov     [rdi+20h], rbx
0x18000c57f  add     rbx, r14
0x18000c582  jmp     short loc_18000C588
0x18000c584  mov     [rdi+20h], r13
0x18000c588  cmp     rbx, rsi
0x18000c58b  jz      short loc_18000C5D5
0x18000c58d  mov     r8, [r12+18h]; Source
0x18000c592  test    r8, r8
0x18000c595  jz      short loc_18000C5D5
0x18000c597  cmp     [r8], r13w
0x18000c59b  jz      short loc_18000C5D5
0x18000c59d  inc     rbp
0x18000c5a0  cmp     [r8+rbp*2], r13w
0x18000c5a5  jnz     short loc_18000C59D
0x18000c5a7  mov     rdx, rsi
0x18000c5aa  lea     r14, ds:2[rbp*2]
0x18000c5b2  sub     rdx, rbx; DestinationSize
0x18000c5b5  cmp     rdx, r14
0x18000c5b8  jb      short loc_18000C5D5
0x18000c5ba  mov     r9, r14; SourceSize
0x18000c5bd  mov     rcx, rbx; Destination
0x18000c5c0  call    cs:__imp_memcpy_s
0x18000c5c7  nop     dword ptr [rax+rax+00h]
0x18000c5cc  mov     [rdi+38h], rbx
0x18000c5d0  add     rbx, r14
0x18000c5d3  jmp     short loc_18000C5D9
0x18000c5d5  mov     [rdi+38h], r13
0x18000c5d9  sub     rsi, rbx
0x18000c5dc  xor     edx, edx; Val
0x18000c5de  mov     r8, rsi; Size
0x18000c5e1  mov     rcx, rbx; void *
0x18000c5e4  call    memset_0
0x18000c5e9  add     rsp, 28h
0x18000c5ed  pop     r15
0x18000c5ef  pop     r14
0x18000c5f1  pop     r13
0x18000c5f3  pop     r12
0x18000c5f5  pop     rdi
0x18000c5f6  pop     rsi
0x18000c5f7  pop     rbp
0x18000c5f8  pop     rbx
0x18000c5f9  retn
```
