# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x14000c028`
- end: `0x14000c244`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `540`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140009be0`

## callees

- `0x140005cd0`
- `0x14000c028`
- `0x14001094e`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14000c11e`
- `KERNEL32!HeapFree` at `0x14000c11e`
- `KERNEL32!GetProcessHeap` at `0x14000c110`
- `KERNEL32!GetProcessHeap` at `0x14000c110`
- `msvcrt!memcpy_s` at `0x14000c174`
- `msvcrt!memcpy_s` at `0x14000c1c5`
- `msvcrt!memcpy_s` at `0x14000c210`
- `msvcrt!memcpy_s` at `0x14000c174`
- `msvcrt!memcpy_s` at `0x14000c1c5`
- `msvcrt!memcpy_s` at `0x14000c210`

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
0x14000c028  push    rbx
0x14000c02a  push    rbp
0x14000c02b  push    rsi
0x14000c02c  push    rdi
0x14000c02d  push    r12
0x14000c02f  push    r13
0x14000c031  push    r14
0x14000c033  push    r15
0x14000c035  sub     rsp, 28h
0x14000c039  mov     [rcx+4], r8d
0x14000c03d  xor     r13d, r13d
0x14000c040  mov     eax, [rdx+8]
0x14000c043  or      rbp, 0FFFFFFFFFFFFFFFFh
0x14000c047  mov     [rcx+8], eax
0x14000c04a  mov     rdi, rcx
0x14000c04d  mov     [rcx+10h], r13
0x14000c051  mov     r12, rdx
0x14000c054  movzx   eax, word ptr [rdx+40h]
0x14000c058  mov     [rcx+18h], ax
0x14000c05c  mov     al, [rdx]
0x14000c05e  mov     [rcx+1Ah], al
0x14000c061  mov     [rcx+20h], r13
0x14000c065  mov     rax, [rdx+88h]
0x14000c06c  mov     [rcx+28h], rax
0x14000c070  mov     rax, [rdx+90h]
0x14000c077  mov     [rcx+30h], rax
0x14000c07b  mov     [rcx+38h], r13
0x14000c07f  mov     rcx, [rdx+38h]
0x14000c083  lea     edx, [rbp+2]
0x14000c086  test    rcx, rcx
0x14000c089  jnz     short loc_14000C090
0x14000c08b  mov     r8d, edx
0x14000c08e  jmp     short loc_14000C0A0
0x14000c090  mov     rax, rbp
0x14000c093  inc     rax
0x14000c096  cmp     [rcx+rax], r13b
0x14000c09a  jnz     short loc_14000C093
0x14000c09c  lea     r8, [rax+1]; unsigned __int64
0x14000c0a0  mov     rcx, [r12+80h]
0x14000c0a8  test    rcx, rcx
0x14000c0ab  jz      short loc_14000C0BD
0x14000c0ad  mov     rax, rbp
0x14000c0b0  inc     rax
0x14000c0b3  cmp     [rcx+rax], r13b
0x14000c0b7  jnz     short loc_14000C0B0
0x14000c0b9  lea     rdx, [rax+1]
0x14000c0bd  mov     rcx, [r12+18h]
0x14000c0c2  test    rcx, rcx
0x14000c0c5  jnz     short loc_14000C0CC
0x14000c0c7  lea     eax, [rcx+2]
0x14000c0ca  jmp     short loc_14000C0E1
0x14000c0cc  mov     rax, rbp
0x14000c0cf  inc     rax
0x14000c0d2  cmp     [rcx+rax*2], r13w
0x14000c0d7  jnz     short loc_14000C0CF
0x14000c0d9  lea     rax, ds:2[rax*2]
0x14000c0e1  lea     r14, [rdx+rax]
0x14000c0e5  add     r14, r8
0x14000c0e8  lea     rsi, [rdi+48h]
0x14000c0ec  cmp     [rdi+40h], r13
0x14000c0f0  jz      short loc_14000C0F7
0x14000c0f2  cmp     [rsi], r14
0x14000c0f5  jnb     short loc_14000C12B
0x14000c0f7  mov     rdx, r14; dwBytes
0x14000c0fa  mov     ecx, 8; dwFlags
0x14000c0ff  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000c104  mov     r15, rax
0x14000c107  test    rax, rax
0x14000c10a  jz      short loc_14000C12B
0x14000c10c  mov     rbx, [rdi+40h]
0x14000c110  call    cs:__imp_GetProcessHeap
0x14000c116  mov     r8, rbx; lpMem
0x14000c119  xor     edx, edx; dwFlags
0x14000c11b  mov     rcx, rax; hHeap
0x14000c11e  call    cs:__imp_HeapFree
0x14000c124  mov     [rdi+40h], r15
0x14000c128  mov     [rsi], r14
0x14000c12b  mov     rbx, [rdi+40h]
0x14000c12f  test    rbx, rbx
0x14000c132  jz      loc_14000C233
0x14000c138  mov     rdx, [rsi]; DestinationSize
0x14000c13b  lea     rsi, [rdx+rbx]
0x14000c13f  cmp     rbx, rsi
0x14000c142  jz      short loc_14000C183
0x14000c144  mov     r8, [r12+38h]; Source
0x14000c149  test    r8, r8
0x14000c14c  jz      short loc_14000C183
0x14000c14e  cmp     [r8], r13b
0x14000c151  jz      short loc_14000C183
0x14000c153  mov     rax, rbp
0x14000c156  inc     rax
0x14000c159  cmp     [r8+rax], r13b
0x14000c15d  jnz     short loc_14000C156
0x14000c15f  lea     r14, [rax+1]
0x14000c163  cmp     rdx, r14
0x14000c166  jnb     short loc_14000C16E
0x14000c168  mov     [rdi+10h], r13
0x14000c16c  jmp     short loc_14000C18C
0x14000c16e  mov     r9, r14; SourceSize
0x14000c171  mov     rcx, rbx; Destination
0x14000c174  call    cs:__imp_memcpy_s
0x14000c17a  mov     [rdi+10h], rbx
0x14000c17e  add     rbx, r14
0x14000c181  jmp     short loc_14000C187
0x14000c183  mov     [rdi+10h], r13
0x14000c187  cmp     rbx, rsi
0x14000c18a  jz      short loc_14000C1D4
0x14000c18c  mov     r8, [r12+80h]; Source
0x14000c194  test    r8, r8
0x14000c197  jz      short loc_14000C1D4
0x14000c199  cmp     [r8], r13b
0x14000c19c  jz      short loc_14000C1D4
0x14000c19e  mov     rax, rbp
0x14000c1a1  inc     rax
0x14000c1a4  cmp     [r8+rax], r13b
0x14000c1a8  jnz     short loc_14000C1A1
0x14000c1aa  mov     rdx, rsi
0x14000c1ad  lea     r14, [rax+1]
0x14000c1b1  sub     rdx, rbx; DestinationSize
0x14000c1b4  cmp     rdx, r14
0x14000c1b7  jnb     short loc_14000C1BF
0x14000c1b9  mov     [rdi+20h], r13
0x14000c1bd  jmp     short loc_14000C1DD
0x14000c1bf  mov     r9, r14; SourceSize
0x14000c1c2  mov     rcx, rbx; Destination
0x14000c1c5  call    cs:__imp_memcpy_s
0x14000c1cb  mov     [rdi+20h], rbx
0x14000c1cf  add     rbx, r14
0x14000c1d2  jmp     short loc_14000C1D8
0x14000c1d4  mov     [rdi+20h], r13
0x14000c1d8  cmp     rbx, rsi
0x14000c1db  jz      short loc_14000C21F
0x14000c1dd  mov     r8, [r12+18h]; Source
0x14000c1e2  test    r8, r8
0x14000c1e5  jz      short loc_14000C21F
0x14000c1e7  cmp     [r8], r13w
0x14000c1eb  jz      short loc_14000C21F
0x14000c1ed  inc     rbp
0x14000c1f0  cmp     [r8+rbp*2], r13w
0x14000c1f5  jnz     short loc_14000C1ED
0x14000c1f7  mov     rdx, rsi
0x14000c1fa  lea     r14, ds:2[rbp*2]
0x14000c202  sub     rdx, rbx; DestinationSize
0x14000c205  cmp     rdx, r14
0x14000c208  jb      short loc_14000C21F
0x14000c20a  mov     r9, r14; SourceSize
0x14000c20d  mov     rcx, rbx; Destination
0x14000c210  call    cs:__imp_memcpy_s
0x14000c216  mov     [rdi+38h], rbx
0x14000c21a  add     rbx, r14
0x14000c21d  jmp     short loc_14000C223
0x14000c21f  mov     [rdi+38h], r13
0x14000c223  sub     rsi, rbx
0x14000c226  xor     edx, edx; Val
0x14000c228  mov     r8, rsi; Size
0x14000c22b  mov     rcx, rbx; void *
0x14000c22e  call    memset_0
0x14000c233  add     rsp, 28h
0x14000c237  pop     r15
0x14000c239  pop     r14
0x14000c23b  pop     r13
0x14000c23d  pop     r12
0x14000c23f  pop     rdi
0x14000c240  pop     rsi
0x14000c241  pop     rbp
0x14000c242  pop     rbx
0x14000c243  retn
```
