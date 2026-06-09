# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x1800052f0`
- end: `0x180005509`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180004720`

## callees

- `0x18000209e`
- `0x180003688`
- `0x18000502c`
- `0x1800052f0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800053d8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800053d8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800053e6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800053e6`

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
0x1800052f0  push    rbx
0x1800052f2  push    rbp
0x1800052f3  push    rsi
0x1800052f4  push    rdi
0x1800052f5  push    r12
0x1800052f7  push    r13
0x1800052f9  push    r14
0x1800052fb  push    r15
0x1800052fd  sub     rsp, 28h
0x180005301  mov     [rcx+4], r8d
0x180005305  xor     r13d, r13d
0x180005308  mov     eax, [rdx+8]
0x18000530b  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18000530f  mov     [rcx+8], eax
0x180005312  mov     rdi, rcx
0x180005315  mov     [rcx+10h], r13
0x180005319  mov     r12, rdx
0x18000531c  movzx   eax, word ptr [rdx+40h]
0x180005320  mov     [rcx+18h], ax
0x180005324  mov     al, [rdx]
0x180005326  mov     [rcx+1Ah], al
0x180005329  mov     [rcx+20h], r13
0x18000532d  mov     rax, [rdx+88h]
0x180005334  mov     [rcx+28h], rax
0x180005338  mov     rax, [rdx+90h]
0x18000533f  mov     [rcx+30h], rax
0x180005343  mov     [rcx+38h], r13
0x180005347  mov     rcx, [rdx+38h]
0x18000534b  lea     edx, [rbp+2]
0x18000534e  test    rcx, rcx
0x180005351  jnz     short loc_180005358
0x180005353  mov     r8d, edx
0x180005356  jmp     short loc_180005368
0x180005358  mov     rax, rbp
0x18000535b  inc     rax
0x18000535e  cmp     [rcx+rax], r13b
0x180005362  jnz     short loc_18000535B
0x180005364  lea     r8, [rax+1]; unsigned __int64
0x180005368  mov     rcx, [r12+80h]
0x180005370  test    rcx, rcx
0x180005373  jz      short loc_180005385
0x180005375  mov     rax, rbp
0x180005378  inc     rax
0x18000537b  cmp     [rcx+rax], r13b
0x18000537f  jnz     short loc_180005378
0x180005381  lea     rdx, [rax+1]
0x180005385  mov     rcx, [r12+18h]
0x18000538a  test    rcx, rcx
0x18000538d  jnz     short loc_180005394
0x18000538f  lea     eax, [rcx+2]
0x180005392  jmp     short loc_1800053A9
0x180005394  mov     rax, rbp
0x180005397  inc     rax
0x18000539a  cmp     [rcx+rax*2], r13w
0x18000539f  jnz     short loc_180005397
0x1800053a1  lea     rax, ds:2[rax*2]
0x1800053a9  lea     r14, [rdx+rax]
0x1800053ad  add     r14, r8
0x1800053b0  lea     rsi, [rdi+48h]
0x1800053b4  cmp     [rdi+40h], r13
0x1800053b8  jz      short loc_1800053BF
0x1800053ba  cmp     [rsi], r14
0x1800053bd  jnb     short loc_1800053F3
0x1800053bf  mov     rdx, r14; dwBytes
0x1800053c2  mov     ecx, 8; dwFlags
0x1800053c7  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800053cc  mov     r15, rax
0x1800053cf  test    rax, rax
0x1800053d2  jz      short loc_1800053F3
0x1800053d4  mov     rbx, [rdi+40h]
0x1800053d8  call    cs:__imp_GetProcessHeap
0x1800053de  mov     r8, rbx; lpMem
0x1800053e1  xor     edx, edx; dwFlags
0x1800053e3  mov     rcx, rax; hHeap
0x1800053e6  call    cs:__imp_HeapFree
0x1800053ec  mov     [rdi+40h], r15
0x1800053f0  mov     [rsi], r14
0x1800053f3  mov     rbx, [rdi+40h]
0x1800053f7  test    rbx, rbx
0x1800053fa  jz      loc_1800054F8
0x180005400  mov     rdx, [rsi]; DestinationSize
0x180005403  lea     rsi, [rdx+rbx]
0x180005407  cmp     rbx, rsi
0x18000540a  jz      short loc_18000544A
0x18000540c  mov     r8, [r12+38h]; Source
0x180005411  test    r8, r8
0x180005414  jz      short loc_18000544A
0x180005416  cmp     [r8], r13b
0x180005419  jz      short loc_18000544A
0x18000541b  mov     rax, rbp
0x18000541e  inc     rax
0x180005421  cmp     [r8+rax], r13b
0x180005425  jnz     short loc_18000541E
0x180005427  lea     r14, [rax+1]
0x18000542b  cmp     rdx, r14
0x18000542e  jnb     short loc_180005436
0x180005430  mov     [rdi+10h], r13
0x180005434  jmp     short loc_180005453
0x180005436  mov     r9, r14; SourceSize
0x180005439  mov     rcx, rbx; Destination
0x18000543c  call    memcpy_s
0x180005441  mov     [rdi+10h], rbx
0x180005445  add     rbx, r14
0x180005448  jmp     short loc_18000544E
0x18000544a  mov     [rdi+10h], r13
0x18000544e  cmp     rbx, rsi
0x180005451  jz      short loc_18000549A
0x180005453  mov     r8, [r12+80h]; Source
0x18000545b  test    r8, r8
0x18000545e  jz      short loc_18000549A
0x180005460  cmp     [r8], r13b
0x180005463  jz      short loc_18000549A
0x180005465  mov     rax, rbp
0x180005468  inc     rax
0x18000546b  cmp     [r8+rax], r13b
0x18000546f  jnz     short loc_180005468
0x180005471  mov     rdx, rsi
0x180005474  lea     r14, [rax+1]
0x180005478  sub     rdx, rbx; DestinationSize
0x18000547b  cmp     rdx, r14
0x18000547e  jnb     short loc_180005486
0x180005480  mov     [rdi+20h], r13
0x180005484  jmp     short loc_1800054A3
0x180005486  mov     r9, r14; SourceSize
0x180005489  mov     rcx, rbx; Destination
0x18000548c  call    memcpy_s
0x180005491  mov     [rdi+20h], rbx
0x180005495  add     rbx, r14
0x180005498  jmp     short loc_18000549E
0x18000549a  mov     [rdi+20h], r13
0x18000549e  cmp     rbx, rsi
0x1800054a1  jz      short loc_1800054E4
0x1800054a3  mov     r8, [r12+18h]; Source
0x1800054a8  test    r8, r8
0x1800054ab  jz      short loc_1800054E4
0x1800054ad  cmp     [r8], r13w
0x1800054b1  jz      short loc_1800054E4
0x1800054b3  inc     rbp
0x1800054b6  cmp     [r8+rbp*2], r13w
0x1800054bb  jnz     short loc_1800054B3
0x1800054bd  mov     rdx, rsi
0x1800054c0  lea     r14, ds:2[rbp*2]
0x1800054c8  sub     rdx, rbx; DestinationSize
0x1800054cb  cmp     rdx, r14
0x1800054ce  jb      short loc_1800054E4
0x1800054d0  mov     r9, r14; SourceSize
0x1800054d3  mov     rcx, rbx; Destination
0x1800054d6  call    memcpy_s
0x1800054db  mov     [rdi+38h], rbx
0x1800054df  add     rbx, r14
0x1800054e2  jmp     short loc_1800054E8
0x1800054e4  mov     [rdi+38h], r13
0x1800054e8  sub     rsi, rbx
0x1800054eb  xor     edx, edx; Val
0x1800054ed  mov     r8, rsi; Size
0x1800054f0  mov     rcx, rbx; void *
0x1800054f3  call    memset_0
0x1800054f8  add     rsp, 28h
0x1800054fc  pop     r15
0x1800054fe  pop     r14
0x180005500  pop     r13
0x180005502  pop     r12
0x180005504  pop     rdi
0x180005505  pop     rsi
0x180005506  pop     rbp
0x180005507  pop     rbx
0x180005508  retn
```
