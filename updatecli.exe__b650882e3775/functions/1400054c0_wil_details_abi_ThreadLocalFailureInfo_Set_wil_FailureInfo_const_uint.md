# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x1400054c0`
- end: `0x1400056d9`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140004100`

## callees

- `0x140002c38`
- `0x140005158`
- `0x1400054c0`
- `0x1400064a8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400055a8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400055a8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400055b6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400055b6`

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
0x1400054c0  push    rbx
0x1400054c2  push    rbp
0x1400054c3  push    rsi
0x1400054c4  push    rdi
0x1400054c5  push    r12
0x1400054c7  push    r13
0x1400054c9  push    r14
0x1400054cb  push    r15
0x1400054cd  sub     rsp, 28h
0x1400054d1  mov     [rcx+4], r8d
0x1400054d5  xor     r13d, r13d
0x1400054d8  mov     eax, [rdx+8]
0x1400054db  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1400054df  mov     [rcx+8], eax
0x1400054e2  mov     rdi, rcx
0x1400054e5  mov     [rcx+10h], r13
0x1400054e9  mov     r12, rdx
0x1400054ec  movzx   eax, word ptr [rdx+40h]
0x1400054f0  mov     [rcx+18h], ax
0x1400054f4  mov     al, [rdx]
0x1400054f6  mov     [rcx+1Ah], al
0x1400054f9  mov     [rcx+20h], r13
0x1400054fd  mov     rax, [rdx+88h]
0x140005504  mov     [rcx+28h], rax
0x140005508  mov     rax, [rdx+90h]
0x14000550f  mov     [rcx+30h], rax
0x140005513  mov     [rcx+38h], r13
0x140005517  mov     rcx, [rdx+38h]
0x14000551b  lea     edx, [rbp+2]
0x14000551e  test    rcx, rcx
0x140005521  jnz     short loc_140005528
0x140005523  mov     r8d, edx
0x140005526  jmp     short loc_140005538
0x140005528  mov     rax, rbp
0x14000552b  inc     rax
0x14000552e  cmp     [rcx+rax], r13b
0x140005532  jnz     short loc_14000552B
0x140005534  lea     r8, [rax+1]; unsigned __int64
0x140005538  mov     rcx, [r12+80h]
0x140005540  test    rcx, rcx
0x140005543  jz      short loc_140005555
0x140005545  mov     rax, rbp
0x140005548  inc     rax
0x14000554b  cmp     [rcx+rax], r13b
0x14000554f  jnz     short loc_140005548
0x140005551  lea     rdx, [rax+1]
0x140005555  mov     rcx, [r12+18h]
0x14000555a  test    rcx, rcx
0x14000555d  jnz     short loc_140005564
0x14000555f  lea     eax, [rcx+2]
0x140005562  jmp     short loc_140005579
0x140005564  mov     rax, rbp
0x140005567  inc     rax
0x14000556a  cmp     [rcx+rax*2], r13w
0x14000556f  jnz     short loc_140005567
0x140005571  lea     rax, ds:2[rax*2]
0x140005579  lea     r14, [rdx+rax]
0x14000557d  add     r14, r8
0x140005580  lea     rsi, [rdi+48h]
0x140005584  cmp     [rdi+40h], r13
0x140005588  jz      short loc_14000558F
0x14000558a  cmp     [rsi], r14
0x14000558d  jnb     short loc_1400055C3
0x14000558f  mov     rdx, r14; dwBytes
0x140005592  mov     ecx, 8; dwFlags
0x140005597  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000559c  mov     r15, rax
0x14000559f  test    rax, rax
0x1400055a2  jz      short loc_1400055C3
0x1400055a4  mov     rbx, [rdi+40h]
0x1400055a8  call    cs:__imp_GetProcessHeap
0x1400055ae  mov     r8, rbx; lpMem
0x1400055b1  xor     edx, edx; dwFlags
0x1400055b3  mov     rcx, rax; hHeap
0x1400055b6  call    cs:__imp_HeapFree
0x1400055bc  mov     [rdi+40h], r15
0x1400055c0  mov     [rsi], r14
0x1400055c3  mov     rbx, [rdi+40h]
0x1400055c7  test    rbx, rbx
0x1400055ca  jz      loc_1400056C8
0x1400055d0  mov     rdx, [rsi]; DestinationSize
0x1400055d3  lea     rsi, [rdx+rbx]
0x1400055d7  cmp     rbx, rsi
0x1400055da  jz      short loc_14000561A
0x1400055dc  mov     r8, [r12+38h]; Source
0x1400055e1  test    r8, r8
0x1400055e4  jz      short loc_14000561A
0x1400055e6  cmp     [r8], r13b
0x1400055e9  jz      short loc_14000561A
0x1400055eb  mov     rax, rbp
0x1400055ee  inc     rax
0x1400055f1  cmp     [r8+rax], r13b
0x1400055f5  jnz     short loc_1400055EE
0x1400055f7  lea     r14, [rax+1]
0x1400055fb  cmp     rdx, r14
0x1400055fe  jnb     short loc_140005606
0x140005600  mov     [rdi+10h], r13
0x140005604  jmp     short loc_140005623
0x140005606  mov     r9, r14; SourceSize
0x140005609  mov     rcx, rbx; Destination
0x14000560c  call    memcpy_s
0x140005611  mov     [rdi+10h], rbx
0x140005615  add     rbx, r14
0x140005618  jmp     short loc_14000561E
0x14000561a  mov     [rdi+10h], r13
0x14000561e  cmp     rbx, rsi
0x140005621  jz      short loc_14000566A
0x140005623  mov     r8, [r12+80h]; Source
0x14000562b  test    r8, r8
0x14000562e  jz      short loc_14000566A
0x140005630  cmp     [r8], r13b
0x140005633  jz      short loc_14000566A
0x140005635  mov     rax, rbp
0x140005638  inc     rax
0x14000563b  cmp     [r8+rax], r13b
0x14000563f  jnz     short loc_140005638
0x140005641  mov     rdx, rsi
0x140005644  lea     r14, [rax+1]
0x140005648  sub     rdx, rbx; DestinationSize
0x14000564b  cmp     rdx, r14
0x14000564e  jnb     short loc_140005656
0x140005650  mov     [rdi+20h], r13
0x140005654  jmp     short loc_140005673
0x140005656  mov     r9, r14; SourceSize
0x140005659  mov     rcx, rbx; Destination
0x14000565c  call    memcpy_s
0x140005661  mov     [rdi+20h], rbx
0x140005665  add     rbx, r14
0x140005668  jmp     short loc_14000566E
0x14000566a  mov     [rdi+20h], r13
0x14000566e  cmp     rbx, rsi
0x140005671  jz      short loc_1400056B4
0x140005673  mov     r8, [r12+18h]; Source
0x140005678  test    r8, r8
0x14000567b  jz      short loc_1400056B4
0x14000567d  cmp     [r8], r13w
0x140005681  jz      short loc_1400056B4
0x140005683  inc     rbp
0x140005686  cmp     [r8+rbp*2], r13w
0x14000568b  jnz     short loc_140005683
0x14000568d  mov     rdx, rsi
0x140005690  lea     r14, ds:2[rbp*2]
0x140005698  sub     rdx, rbx; DestinationSize
0x14000569b  cmp     rdx, r14
0x14000569e  jb      short loc_1400056B4
0x1400056a0  mov     r9, r14; SourceSize
0x1400056a3  mov     rcx, rbx; Destination
0x1400056a6  call    memcpy_s
0x1400056ab  mov     [rdi+38h], rbx
0x1400056af  add     rbx, r14
0x1400056b2  jmp     short loc_1400056B8
0x1400056b4  mov     [rdi+38h], r13
0x1400056b8  sub     rsi, rbx
0x1400056bb  xor     edx, edx; Val
0x1400056bd  mov     r8, rsi; Size
0x1400056c0  mov     rcx, rbx; void *
0x1400056c3  call    memset_0
0x1400056c8  add     rsp, 28h
0x1400056cc  pop     r15
0x1400056ce  pop     r14
0x1400056d0  pop     r13
0x1400056d2  pop     r12
0x1400056d4  pop     rdi
0x1400056d5  pop     rsi
0x1400056d6  pop     rbp
0x1400056d7  pop     rbx
0x1400056d8  retn
```
