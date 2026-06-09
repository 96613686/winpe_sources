# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180009258`
- end: `0x180009471`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180008190`

## callees

- `0x180003da4`
- `0x180006868`
- `0x180008c88`
- `0x180009258`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000934e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000934e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009340`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009340`

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
0x180009258  push    rbx
0x18000925a  push    rbp
0x18000925b  push    rsi
0x18000925c  push    rdi
0x18000925d  push    r12
0x18000925f  push    r13
0x180009261  push    r14
0x180009263  push    r15
0x180009265  sub     rsp, 28h
0x180009269  mov     [rcx+4], r8d
0x18000926d  xor     r13d, r13d
0x180009270  mov     eax, [rdx+8]
0x180009273  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180009277  mov     [rcx+8], eax
0x18000927a  mov     rdi, rcx
0x18000927d  mov     [rcx+10h], r13
0x180009281  mov     r12, rdx
0x180009284  movzx   eax, word ptr [rdx+40h]
0x180009288  mov     [rcx+18h], ax
0x18000928c  mov     al, [rdx]
0x18000928e  mov     [rcx+1Ah], al
0x180009291  mov     [rcx+20h], r13
0x180009295  mov     rax, [rdx+88h]
0x18000929c  mov     [rcx+28h], rax
0x1800092a0  mov     rax, [rdx+90h]
0x1800092a7  mov     [rcx+30h], rax
0x1800092ab  mov     [rcx+38h], r13
0x1800092af  mov     rcx, [rdx+38h]
0x1800092b3  lea     edx, [rbp+2]
0x1800092b6  test    rcx, rcx
0x1800092b9  jnz     short loc_1800092C0
0x1800092bb  mov     r8d, edx
0x1800092be  jmp     short loc_1800092D0
0x1800092c0  mov     rax, rbp
0x1800092c3  inc     rax
0x1800092c6  cmp     [rcx+rax], r13b
0x1800092ca  jnz     short loc_1800092C3
0x1800092cc  lea     r8, [rax+1]; unsigned __int64
0x1800092d0  mov     rcx, [r12+80h]
0x1800092d8  test    rcx, rcx
0x1800092db  jz      short loc_1800092ED
0x1800092dd  mov     rax, rbp
0x1800092e0  inc     rax
0x1800092e3  cmp     [rcx+rax], r13b
0x1800092e7  jnz     short loc_1800092E0
0x1800092e9  lea     rdx, [rax+1]
0x1800092ed  mov     rcx, [r12+18h]
0x1800092f2  test    rcx, rcx
0x1800092f5  jnz     short loc_1800092FC
0x1800092f7  lea     eax, [rcx+2]
0x1800092fa  jmp     short loc_180009311
0x1800092fc  mov     rax, rbp
0x1800092ff  inc     rax
0x180009302  cmp     [rcx+rax*2], r13w
0x180009307  jnz     short loc_1800092FF
0x180009309  lea     rax, ds:2[rax*2]
0x180009311  lea     r14, [rdx+rax]
0x180009315  add     r14, r8
0x180009318  lea     rsi, [rdi+48h]
0x18000931c  cmp     [rdi+40h], r13
0x180009320  jz      short loc_180009327
0x180009322  cmp     [rsi], r14
0x180009325  jnb     short loc_18000935B
0x180009327  mov     rdx, r14; dwBytes
0x18000932a  mov     ecx, 8; dwFlags
0x18000932f  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180009334  mov     r15, rax
0x180009337  test    rax, rax
0x18000933a  jz      short loc_18000935B
0x18000933c  mov     rbx, [rdi+40h]
0x180009340  call    cs:__imp_GetProcessHeap
0x180009346  mov     r8, rbx; lpMem
0x180009349  xor     edx, edx; dwFlags
0x18000934b  mov     rcx, rax; hHeap
0x18000934e  call    cs:__imp_HeapFree
0x180009354  mov     [rdi+40h], r15
0x180009358  mov     [rsi], r14
0x18000935b  mov     rbx, [rdi+40h]
0x18000935f  test    rbx, rbx
0x180009362  jz      loc_180009460
0x180009368  mov     rdx, [rsi]; DestinationSize
0x18000936b  lea     rsi, [rdx+rbx]
0x18000936f  cmp     rbx, rsi
0x180009372  jz      short loc_1800093B2
0x180009374  mov     r8, [r12+38h]; Source
0x180009379  test    r8, r8
0x18000937c  jz      short loc_1800093B2
0x18000937e  cmp     [r8], r13b
0x180009381  jz      short loc_1800093B2
0x180009383  mov     rax, rbp
0x180009386  inc     rax
0x180009389  cmp     [r8+rax], r13b
0x18000938d  jnz     short loc_180009386
0x18000938f  lea     r14, [rax+1]
0x180009393  cmp     rdx, r14
0x180009396  jnb     short loc_18000939E
0x180009398  mov     [rdi+10h], r13
0x18000939c  jmp     short loc_1800093BB
0x18000939e  mov     r9, r14; SourceSize
0x1800093a1  mov     rcx, rbx; Destination
0x1800093a4  call    memcpy_s
0x1800093a9  mov     [rdi+10h], rbx
0x1800093ad  add     rbx, r14
0x1800093b0  jmp     short loc_1800093B6
0x1800093b2  mov     [rdi+10h], r13
0x1800093b6  cmp     rbx, rsi
0x1800093b9  jz      short loc_180009402
0x1800093bb  mov     r8, [r12+80h]; Source
0x1800093c3  test    r8, r8
0x1800093c6  jz      short loc_180009402
0x1800093c8  cmp     [r8], r13b
0x1800093cb  jz      short loc_180009402
0x1800093cd  mov     rax, rbp
0x1800093d0  inc     rax
0x1800093d3  cmp     [r8+rax], r13b
0x1800093d7  jnz     short loc_1800093D0
0x1800093d9  mov     rdx, rsi
0x1800093dc  lea     r14, [rax+1]
0x1800093e0  sub     rdx, rbx; DestinationSize
0x1800093e3  cmp     rdx, r14
0x1800093e6  jnb     short loc_1800093EE
0x1800093e8  mov     [rdi+20h], r13
0x1800093ec  jmp     short loc_18000940B
0x1800093ee  mov     r9, r14; SourceSize
0x1800093f1  mov     rcx, rbx; Destination
0x1800093f4  call    memcpy_s
0x1800093f9  mov     [rdi+20h], rbx
0x1800093fd  add     rbx, r14
0x180009400  jmp     short loc_180009406
0x180009402  mov     [rdi+20h], r13
0x180009406  cmp     rbx, rsi
0x180009409  jz      short loc_18000944C
0x18000940b  mov     r8, [r12+18h]; Source
0x180009410  test    r8, r8
0x180009413  jz      short loc_18000944C
0x180009415  cmp     [r8], r13w
0x180009419  jz      short loc_18000944C
0x18000941b  inc     rbp
0x18000941e  cmp     [r8+rbp*2], r13w
0x180009423  jnz     short loc_18000941B
0x180009425  mov     rdx, rsi
0x180009428  lea     r14, ds:2[rbp*2]
0x180009430  sub     rdx, rbx; DestinationSize
0x180009433  cmp     rdx, r14
0x180009436  jb      short loc_18000944C
0x180009438  mov     r9, r14; SourceSize
0x18000943b  mov     rcx, rbx; Destination
0x18000943e  call    memcpy_s
0x180009443  mov     [rdi+38h], rbx
0x180009447  add     rbx, r14
0x18000944a  jmp     short loc_180009450
0x18000944c  mov     [rdi+38h], r13
0x180009450  sub     rsi, rbx
0x180009453  xor     edx, edx; Val
0x180009455  mov     r8, rsi; Size
0x180009458  mov     rcx, rbx; void *
0x18000945b  call    memset_0
0x180009460  add     rsp, 28h
0x180009464  pop     r15
0x180009466  pop     r14
0x180009468  pop     r13
0x18000946a  pop     r12
0x18000946c  pop     rdi
0x18000946d  pop     rsi
0x18000946e  pop     rbp
0x18000946f  pop     rbx
0x180009470  retn
```
