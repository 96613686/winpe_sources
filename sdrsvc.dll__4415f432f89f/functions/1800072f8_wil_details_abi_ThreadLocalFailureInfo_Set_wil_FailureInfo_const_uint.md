# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x1800072f8`
- end: `0x180007514`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `540`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180004a90`

## callees

- `0x180005ce8`
- `0x1800072f8`
- `0x18002170a`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180007444`
- `msvcrt!memcpy_s` at `0x180007495`
- `msvcrt!memcpy_s` at `0x1800074e0`
- `msvcrt!memcpy_s` at `0x180007444`
- `msvcrt!memcpy_s` at `0x180007495`
- `msvcrt!memcpy_s` at `0x1800074e0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800073e0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800073e0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800073ee`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800073ee`

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
0x1800072f8  push    rbx
0x1800072fa  push    rbp
0x1800072fb  push    rsi
0x1800072fc  push    rdi
0x1800072fd  push    r12
0x1800072ff  push    r13
0x180007301  push    r14
0x180007303  push    r15
0x180007305  sub     rsp, 28h
0x180007309  mov     [rcx+4], r8d
0x18000730d  xor     r13d, r13d
0x180007310  mov     eax, [rdx+8]
0x180007313  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180007317  mov     [rcx+8], eax
0x18000731a  mov     rdi, rcx
0x18000731d  mov     [rcx+10h], r13
0x180007321  mov     r12, rdx
0x180007324  movzx   eax, word ptr [rdx+40h]
0x180007328  mov     [rcx+18h], ax
0x18000732c  mov     al, [rdx]
0x18000732e  mov     [rcx+1Ah], al
0x180007331  mov     [rcx+20h], r13
0x180007335  mov     rax, [rdx+88h]
0x18000733c  mov     [rcx+28h], rax
0x180007340  mov     rax, [rdx+90h]
0x180007347  mov     [rcx+30h], rax
0x18000734b  mov     [rcx+38h], r13
0x18000734f  mov     rcx, [rdx+38h]
0x180007353  lea     edx, [rbp+2]
0x180007356  test    rcx, rcx
0x180007359  jnz     short loc_180007360
0x18000735b  mov     r8d, edx
0x18000735e  jmp     short loc_180007370
0x180007360  mov     rax, rbp
0x180007363  inc     rax
0x180007366  cmp     [rcx+rax], r13b
0x18000736a  jnz     short loc_180007363
0x18000736c  lea     r8, [rax+1]; unsigned __int64
0x180007370  mov     rcx, [r12+80h]
0x180007378  test    rcx, rcx
0x18000737b  jz      short loc_18000738D
0x18000737d  mov     rax, rbp
0x180007380  inc     rax
0x180007383  cmp     [rcx+rax], r13b
0x180007387  jnz     short loc_180007380
0x180007389  lea     rdx, [rax+1]
0x18000738d  mov     rcx, [r12+18h]
0x180007392  test    rcx, rcx
0x180007395  jnz     short loc_18000739C
0x180007397  lea     eax, [rcx+2]
0x18000739a  jmp     short loc_1800073B1
0x18000739c  mov     rax, rbp
0x18000739f  inc     rax
0x1800073a2  cmp     [rcx+rax*2], r13w
0x1800073a7  jnz     short loc_18000739F
0x1800073a9  lea     rax, ds:2[rax*2]
0x1800073b1  lea     r14, [rdx+rax]
0x1800073b5  add     r14, r8
0x1800073b8  lea     rsi, [rdi+48h]
0x1800073bc  cmp     [rdi+40h], r13
0x1800073c0  jz      short loc_1800073C7
0x1800073c2  cmp     [rsi], r14
0x1800073c5  jnb     short loc_1800073FB
0x1800073c7  mov     rdx, r14; dwBytes
0x1800073ca  mov     ecx, 8; dwFlags
0x1800073cf  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800073d4  mov     r15, rax
0x1800073d7  test    rax, rax
0x1800073da  jz      short loc_1800073FB
0x1800073dc  mov     rbx, [rdi+40h]
0x1800073e0  call    cs:__imp_GetProcessHeap
0x1800073e6  mov     r8, rbx; lpMem
0x1800073e9  xor     edx, edx; dwFlags
0x1800073eb  mov     rcx, rax; hHeap
0x1800073ee  call    cs:__imp_HeapFree
0x1800073f4  mov     [rdi+40h], r15
0x1800073f8  mov     [rsi], r14
0x1800073fb  mov     rbx, [rdi+40h]
0x1800073ff  test    rbx, rbx
0x180007402  jz      loc_180007503
0x180007408  mov     rdx, [rsi]; DestinationSize
0x18000740b  lea     rsi, [rdx+rbx]
0x18000740f  cmp     rbx, rsi
0x180007412  jz      short loc_180007453
0x180007414  mov     r8, [r12+38h]; Source
0x180007419  test    r8, r8
0x18000741c  jz      short loc_180007453
0x18000741e  cmp     [r8], r13b
0x180007421  jz      short loc_180007453
0x180007423  mov     rax, rbp
0x180007426  inc     rax
0x180007429  cmp     [r8+rax], r13b
0x18000742d  jnz     short loc_180007426
0x18000742f  lea     r14, [rax+1]
0x180007433  cmp     rdx, r14
0x180007436  jnb     short loc_18000743E
0x180007438  mov     [rdi+10h], r13
0x18000743c  jmp     short loc_18000745C
0x18000743e  mov     r9, r14; SourceSize
0x180007441  mov     rcx, rbx; Destination
0x180007444  call    cs:__imp_memcpy_s
0x18000744a  mov     [rdi+10h], rbx
0x18000744e  add     rbx, r14
0x180007451  jmp     short loc_180007457
0x180007453  mov     [rdi+10h], r13
0x180007457  cmp     rbx, rsi
0x18000745a  jz      short loc_1800074A4
0x18000745c  mov     r8, [r12+80h]; Source
0x180007464  test    r8, r8
0x180007467  jz      short loc_1800074A4
0x180007469  cmp     [r8], r13b
0x18000746c  jz      short loc_1800074A4
0x18000746e  mov     rax, rbp
0x180007471  inc     rax
0x180007474  cmp     [r8+rax], r13b
0x180007478  jnz     short loc_180007471
0x18000747a  mov     rdx, rsi
0x18000747d  lea     r14, [rax+1]
0x180007481  sub     rdx, rbx; DestinationSize
0x180007484  cmp     rdx, r14
0x180007487  jnb     short loc_18000748F
0x180007489  mov     [rdi+20h], r13
0x18000748d  jmp     short loc_1800074AD
0x18000748f  mov     r9, r14; SourceSize
0x180007492  mov     rcx, rbx; Destination
0x180007495  call    cs:__imp_memcpy_s
0x18000749b  mov     [rdi+20h], rbx
0x18000749f  add     rbx, r14
0x1800074a2  jmp     short loc_1800074A8
0x1800074a4  mov     [rdi+20h], r13
0x1800074a8  cmp     rbx, rsi
0x1800074ab  jz      short loc_1800074EF
0x1800074ad  mov     r8, [r12+18h]; Source
0x1800074b2  test    r8, r8
0x1800074b5  jz      short loc_1800074EF
0x1800074b7  cmp     [r8], r13w
0x1800074bb  jz      short loc_1800074EF
0x1800074bd  inc     rbp
0x1800074c0  cmp     [r8+rbp*2], r13w
0x1800074c5  jnz     short loc_1800074BD
0x1800074c7  mov     rdx, rsi
0x1800074ca  lea     r14, ds:2[rbp*2]
0x1800074d2  sub     rdx, rbx; DestinationSize
0x1800074d5  cmp     rdx, r14
0x1800074d8  jb      short loc_1800074EF
0x1800074da  mov     r9, r14; SourceSize
0x1800074dd  mov     rcx, rbx; Destination
0x1800074e0  call    cs:__imp_memcpy_s
0x1800074e6  mov     [rdi+38h], rbx
0x1800074ea  add     rbx, r14
0x1800074ed  jmp     short loc_1800074F3
0x1800074ef  mov     [rdi+38h], r13
0x1800074f3  sub     rsi, rbx
0x1800074f6  xor     edx, edx; Val
0x1800074f8  mov     r8, rsi; Size
0x1800074fb  mov     rcx, rbx; void *
0x1800074fe  call    memset_0
0x180007503  add     rsp, 28h
0x180007507  pop     r15
0x180007509  pop     r14
0x18000750b  pop     r13
0x18000750d  pop     r12
0x18000750f  pop     rdi
0x180007510  pop     rsi
0x180007511  pop     rbp
0x180007512  pop     rbx
0x180007513  retn
```
