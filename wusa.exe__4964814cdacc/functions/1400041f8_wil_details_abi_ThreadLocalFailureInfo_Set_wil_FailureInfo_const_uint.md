# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x1400041f8`
- end: `0x140004414`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `540`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140002e60`

## callees

- `0x140001a63`
- `0x140003eb8`
- `0x1400041f8`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1400042ee`
- `KERNEL32!HeapFree` at `0x1400042ee`
- `KERNEL32!GetProcessHeap` at `0x1400042e0`
- `KERNEL32!GetProcessHeap` at `0x1400042e0`
- `msvcrt!memcpy_s` at `0x140004344`
- `msvcrt!memcpy_s` at `0x140004395`
- `msvcrt!memcpy_s` at `0x1400043e0`
- `msvcrt!memcpy_s` at `0x140004344`
- `msvcrt!memcpy_s` at `0x140004395`
- `msvcrt!memcpy_s` at `0x1400043e0`

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
0x1400041f8  push    rbx
0x1400041fa  push    rbp
0x1400041fb  push    rsi
0x1400041fc  push    rdi
0x1400041fd  push    r12
0x1400041ff  push    r13
0x140004201  push    r14
0x140004203  push    r15
0x140004205  sub     rsp, 28h
0x140004209  mov     [rcx+4], r8d
0x14000420d  xor     r13d, r13d
0x140004210  mov     eax, [rdx+8]
0x140004213  or      rbp, 0FFFFFFFFFFFFFFFFh
0x140004217  mov     [rcx+8], eax
0x14000421a  mov     rdi, rcx
0x14000421d  mov     [rcx+10h], r13
0x140004221  mov     r12, rdx
0x140004224  movzx   eax, word ptr [rdx+40h]
0x140004228  mov     [rcx+18h], ax
0x14000422c  mov     al, [rdx]
0x14000422e  mov     [rcx+1Ah], al
0x140004231  mov     [rcx+20h], r13
0x140004235  mov     rax, [rdx+88h]
0x14000423c  mov     [rcx+28h], rax
0x140004240  mov     rax, [rdx+90h]
0x140004247  mov     [rcx+30h], rax
0x14000424b  mov     [rcx+38h], r13
0x14000424f  mov     rcx, [rdx+38h]
0x140004253  lea     edx, [rbp+2]
0x140004256  test    rcx, rcx
0x140004259  jnz     short loc_140004260
0x14000425b  mov     r8d, edx
0x14000425e  jmp     short loc_140004270
0x140004260  mov     rax, rbp
0x140004263  inc     rax
0x140004266  cmp     [rcx+rax], r13b
0x14000426a  jnz     short loc_140004263
0x14000426c  lea     r8, [rax+1]; unsigned __int64
0x140004270  mov     rcx, [r12+80h]
0x140004278  test    rcx, rcx
0x14000427b  jz      short loc_14000428D
0x14000427d  mov     rax, rbp
0x140004280  inc     rax
0x140004283  cmp     [rcx+rax], r13b
0x140004287  jnz     short loc_140004280
0x140004289  lea     rdx, [rax+1]
0x14000428d  mov     rcx, [r12+18h]
0x140004292  test    rcx, rcx
0x140004295  jnz     short loc_14000429C
0x140004297  lea     eax, [rcx+2]
0x14000429a  jmp     short loc_1400042B1
0x14000429c  mov     rax, rbp
0x14000429f  inc     rax
0x1400042a2  cmp     [rcx+rax*2], r13w
0x1400042a7  jnz     short loc_14000429F
0x1400042a9  lea     rax, ds:2[rax*2]
0x1400042b1  lea     r14, [rdx+rax]
0x1400042b5  add     r14, r8
0x1400042b8  lea     rsi, [rdi+48h]
0x1400042bc  cmp     [rdi+40h], r13
0x1400042c0  jz      short loc_1400042C7
0x1400042c2  cmp     [rsi], r14
0x1400042c5  jnb     short loc_1400042FB
0x1400042c7  mov     rdx, r14; dwBytes
0x1400042ca  mov     ecx, 8; dwFlags
0x1400042cf  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1400042d4  mov     r15, rax
0x1400042d7  test    rax, rax
0x1400042da  jz      short loc_1400042FB
0x1400042dc  mov     rbx, [rdi+40h]
0x1400042e0  call    cs:__imp_GetProcessHeap
0x1400042e6  mov     r8, rbx; lpMem
0x1400042e9  xor     edx, edx; dwFlags
0x1400042eb  mov     rcx, rax; hHeap
0x1400042ee  call    cs:__imp_HeapFree
0x1400042f4  mov     [rdi+40h], r15
0x1400042f8  mov     [rsi], r14
0x1400042fb  mov     rbx, [rdi+40h]
0x1400042ff  test    rbx, rbx
0x140004302  jz      loc_140004403
0x140004308  mov     rdx, [rsi]; DestinationSize
0x14000430b  lea     rsi, [rdx+rbx]
0x14000430f  cmp     rbx, rsi
0x140004312  jz      short loc_140004353
0x140004314  mov     r8, [r12+38h]; Source
0x140004319  test    r8, r8
0x14000431c  jz      short loc_140004353
0x14000431e  cmp     [r8], r13b
0x140004321  jz      short loc_140004353
0x140004323  mov     rax, rbp
0x140004326  inc     rax
0x140004329  cmp     [r8+rax], r13b
0x14000432d  jnz     short loc_140004326
0x14000432f  lea     r14, [rax+1]
0x140004333  cmp     rdx, r14
0x140004336  jnb     short loc_14000433E
0x140004338  mov     [rdi+10h], r13
0x14000433c  jmp     short loc_14000435C
0x14000433e  mov     r9, r14; SourceSize
0x140004341  mov     rcx, rbx; Destination
0x140004344  call    cs:__imp_memcpy_s
0x14000434a  mov     [rdi+10h], rbx
0x14000434e  add     rbx, r14
0x140004351  jmp     short loc_140004357
0x140004353  mov     [rdi+10h], r13
0x140004357  cmp     rbx, rsi
0x14000435a  jz      short loc_1400043A4
0x14000435c  mov     r8, [r12+80h]; Source
0x140004364  test    r8, r8
0x140004367  jz      short loc_1400043A4
0x140004369  cmp     [r8], r13b
0x14000436c  jz      short loc_1400043A4
0x14000436e  mov     rax, rbp
0x140004371  inc     rax
0x140004374  cmp     [r8+rax], r13b
0x140004378  jnz     short loc_140004371
0x14000437a  mov     rdx, rsi
0x14000437d  lea     r14, [rax+1]
0x140004381  sub     rdx, rbx; DestinationSize
0x140004384  cmp     rdx, r14
0x140004387  jnb     short loc_14000438F
0x140004389  mov     [rdi+20h], r13
0x14000438d  jmp     short loc_1400043AD
0x14000438f  mov     r9, r14; SourceSize
0x140004392  mov     rcx, rbx; Destination
0x140004395  call    cs:__imp_memcpy_s
0x14000439b  mov     [rdi+20h], rbx
0x14000439f  add     rbx, r14
0x1400043a2  jmp     short loc_1400043A8
0x1400043a4  mov     [rdi+20h], r13
0x1400043a8  cmp     rbx, rsi
0x1400043ab  jz      short loc_1400043EF
0x1400043ad  mov     r8, [r12+18h]; Source
0x1400043b2  test    r8, r8
0x1400043b5  jz      short loc_1400043EF
0x1400043b7  cmp     [r8], r13w
0x1400043bb  jz      short loc_1400043EF
0x1400043bd  inc     rbp
0x1400043c0  cmp     [r8+rbp*2], r13w
0x1400043c5  jnz     short loc_1400043BD
0x1400043c7  mov     rdx, rsi
0x1400043ca  lea     r14, ds:2[rbp*2]
0x1400043d2  sub     rdx, rbx; DestinationSize
0x1400043d5  cmp     rdx, r14
0x1400043d8  jb      short loc_1400043EF
0x1400043da  mov     r9, r14; SourceSize
0x1400043dd  mov     rcx, rbx; Destination
0x1400043e0  call    cs:__imp_memcpy_s
0x1400043e6  mov     [rdi+38h], rbx
0x1400043ea  add     rbx, r14
0x1400043ed  jmp     short loc_1400043F3
0x1400043ef  mov     [rdi+38h], r13
0x1400043f3  sub     rsi, rbx
0x1400043f6  xor     edx, edx; Val
0x1400043f8  mov     r8, rsi; Size
0x1400043fb  mov     rcx, rbx; void *
0x1400043fe  call    memset_0
0x140004403  add     rsp, 28h
0x140004407  pop     r15
0x140004409  pop     r14
0x14000440b  pop     r13
0x14000440d  pop     r12
0x14000440f  pop     rdi
0x140004410  pop     rsi
0x140004411  pop     rbp
0x140004412  pop     rbx
0x140004413  retn
```
