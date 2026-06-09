# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180005328`
- end: `0x180005544`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `540`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180003fa0`

## callees

- `0x180004fe8`
- `0x180005328`
- `0x18001d33a`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180005474`
- `msvcrt!memcpy_s` at `0x1800054c5`
- `msvcrt!memcpy_s` at `0x180005510`
- `msvcrt!memcpy_s` at `0x180005474`
- `msvcrt!memcpy_s` at `0x1800054c5`
- `msvcrt!memcpy_s` at `0x180005510`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005410`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005410`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000541e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000541e`

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
0x180005328  push    rbx
0x18000532a  push    rbp
0x18000532b  push    rsi
0x18000532c  push    rdi
0x18000532d  push    r12
0x18000532f  push    r13
0x180005331  push    r14
0x180005333  push    r15
0x180005335  sub     rsp, 28h
0x180005339  mov     [rcx+4], r8d
0x18000533d  xor     r13d, r13d
0x180005340  mov     eax, [rdx+8]
0x180005343  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180005347  mov     [rcx+8], eax
0x18000534a  mov     rdi, rcx
0x18000534d  mov     [rcx+10h], r13
0x180005351  mov     r12, rdx
0x180005354  movzx   eax, word ptr [rdx+40h]
0x180005358  mov     [rcx+18h], ax
0x18000535c  mov     al, [rdx]
0x18000535e  mov     [rcx+1Ah], al
0x180005361  mov     [rcx+20h], r13
0x180005365  mov     rax, [rdx+88h]
0x18000536c  mov     [rcx+28h], rax
0x180005370  mov     rax, [rdx+90h]
0x180005377  mov     [rcx+30h], rax
0x18000537b  mov     [rcx+38h], r13
0x18000537f  mov     rcx, [rdx+38h]
0x180005383  lea     edx, [rbp+2]
0x180005386  test    rcx, rcx
0x180005389  jnz     short loc_180005390
0x18000538b  mov     r8d, edx
0x18000538e  jmp     short loc_1800053A0
0x180005390  mov     rax, rbp
0x180005393  inc     rax
0x180005396  cmp     [rcx+rax], r13b
0x18000539a  jnz     short loc_180005393
0x18000539c  lea     r8, [rax+1]; unsigned __int64
0x1800053a0  mov     rcx, [r12+80h]
0x1800053a8  test    rcx, rcx
0x1800053ab  jz      short loc_1800053BD
0x1800053ad  mov     rax, rbp
0x1800053b0  inc     rax
0x1800053b3  cmp     [rcx+rax], r13b
0x1800053b7  jnz     short loc_1800053B0
0x1800053b9  lea     rdx, [rax+1]
0x1800053bd  mov     rcx, [r12+18h]
0x1800053c2  test    rcx, rcx
0x1800053c5  jnz     short loc_1800053CC
0x1800053c7  lea     eax, [rcx+2]
0x1800053ca  jmp     short loc_1800053E1
0x1800053cc  mov     rax, rbp
0x1800053cf  inc     rax
0x1800053d2  cmp     [rcx+rax*2], r13w
0x1800053d7  jnz     short loc_1800053CF
0x1800053d9  lea     rax, ds:2[rax*2]
0x1800053e1  lea     r14, [rdx+rax]
0x1800053e5  add     r14, r8
0x1800053e8  lea     rsi, [rdi+48h]
0x1800053ec  cmp     [rdi+40h], r13
0x1800053f0  jz      short loc_1800053F7
0x1800053f2  cmp     [rsi], r14
0x1800053f5  jnb     short loc_18000542B
0x1800053f7  mov     rdx, r14; dwBytes
0x1800053fa  mov     ecx, 8; dwFlags
0x1800053ff  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180005404  mov     r15, rax
0x180005407  test    rax, rax
0x18000540a  jz      short loc_18000542B
0x18000540c  mov     rbx, [rdi+40h]
0x180005410  call    cs:__imp_GetProcessHeap
0x180005416  mov     r8, rbx; lpMem
0x180005419  xor     edx, edx; dwFlags
0x18000541b  mov     rcx, rax; hHeap
0x18000541e  call    cs:__imp_HeapFree
0x180005424  mov     [rdi+40h], r15
0x180005428  mov     [rsi], r14
0x18000542b  mov     rbx, [rdi+40h]
0x18000542f  test    rbx, rbx
0x180005432  jz      loc_180005533
0x180005438  mov     rdx, [rsi]; DestinationSize
0x18000543b  lea     rsi, [rdx+rbx]
0x18000543f  cmp     rbx, rsi
0x180005442  jz      short loc_180005483
0x180005444  mov     r8, [r12+38h]; Source
0x180005449  test    r8, r8
0x18000544c  jz      short loc_180005483
0x18000544e  cmp     [r8], r13b
0x180005451  jz      short loc_180005483
0x180005453  mov     rax, rbp
0x180005456  inc     rax
0x180005459  cmp     [r8+rax], r13b
0x18000545d  jnz     short loc_180005456
0x18000545f  lea     r14, [rax+1]
0x180005463  cmp     rdx, r14
0x180005466  jnb     short loc_18000546E
0x180005468  mov     [rdi+10h], r13
0x18000546c  jmp     short loc_18000548C
0x18000546e  mov     r9, r14; SourceSize
0x180005471  mov     rcx, rbx; Destination
0x180005474  call    cs:__imp_memcpy_s
0x18000547a  mov     [rdi+10h], rbx
0x18000547e  add     rbx, r14
0x180005481  jmp     short loc_180005487
0x180005483  mov     [rdi+10h], r13
0x180005487  cmp     rbx, rsi
0x18000548a  jz      short loc_1800054D4
0x18000548c  mov     r8, [r12+80h]; Source
0x180005494  test    r8, r8
0x180005497  jz      short loc_1800054D4
0x180005499  cmp     [r8], r13b
0x18000549c  jz      short loc_1800054D4
0x18000549e  mov     rax, rbp
0x1800054a1  inc     rax
0x1800054a4  cmp     [r8+rax], r13b
0x1800054a8  jnz     short loc_1800054A1
0x1800054aa  mov     rdx, rsi
0x1800054ad  lea     r14, [rax+1]
0x1800054b1  sub     rdx, rbx; DestinationSize
0x1800054b4  cmp     rdx, r14
0x1800054b7  jnb     short loc_1800054BF
0x1800054b9  mov     [rdi+20h], r13
0x1800054bd  jmp     short loc_1800054DD
0x1800054bf  mov     r9, r14; SourceSize
0x1800054c2  mov     rcx, rbx; Destination
0x1800054c5  call    cs:__imp_memcpy_s
0x1800054cb  mov     [rdi+20h], rbx
0x1800054cf  add     rbx, r14
0x1800054d2  jmp     short loc_1800054D8
0x1800054d4  mov     [rdi+20h], r13
0x1800054d8  cmp     rbx, rsi
0x1800054db  jz      short loc_18000551F
0x1800054dd  mov     r8, [r12+18h]; Source
0x1800054e2  test    r8, r8
0x1800054e5  jz      short loc_18000551F
0x1800054e7  cmp     [r8], r13w
0x1800054eb  jz      short loc_18000551F
0x1800054ed  inc     rbp
0x1800054f0  cmp     [r8+rbp*2], r13w
0x1800054f5  jnz     short loc_1800054ED
0x1800054f7  mov     rdx, rsi
0x1800054fa  lea     r14, ds:2[rbp*2]
0x180005502  sub     rdx, rbx; DestinationSize
0x180005505  cmp     rdx, r14
0x180005508  jb      short loc_18000551F
0x18000550a  mov     r9, r14; SourceSize
0x18000550d  mov     rcx, rbx; Destination
0x180005510  call    cs:__imp_memcpy_s
0x180005516  mov     [rdi+38h], rbx
0x18000551a  add     rbx, r14
0x18000551d  jmp     short loc_180005523
0x18000551f  mov     [rdi+38h], r13
0x180005523  sub     rsi, rbx
0x180005526  xor     edx, edx; Val
0x180005528  mov     r8, rsi; Size
0x18000552b  mov     rcx, rbx; void *
0x18000552e  call    memset_0
0x180005533  add     rsp, 28h
0x180005537  pop     r15
0x180005539  pop     r14
0x18000553b  pop     r13
0x18000553d  pop     r12
0x18000553f  pop     rdi
0x180005540  pop     rsi
0x180005541  pop     rbp
0x180005542  pop     rbx
0x180005543  retn
```
