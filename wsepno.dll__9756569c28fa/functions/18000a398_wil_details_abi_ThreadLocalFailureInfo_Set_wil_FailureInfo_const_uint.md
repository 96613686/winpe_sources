# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18000a398`
- end: `0x18000a5b1`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800071a0`

## callees

- `0x1800021f4`
- `0x180003a28`
- `0x1800083d0`
- `0x18000a398`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a48e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a48e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a480`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a480`

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
0x18000a398  push    rbx
0x18000a39a  push    rbp
0x18000a39b  push    rsi
0x18000a39c  push    rdi
0x18000a39d  push    r12
0x18000a39f  push    r13
0x18000a3a1  push    r14
0x18000a3a3  push    r15
0x18000a3a5  sub     rsp, 28h
0x18000a3a9  mov     [rcx+4], r8d
0x18000a3ad  xor     r13d, r13d
0x18000a3b0  mov     eax, [rdx+8]
0x18000a3b3  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18000a3b7  mov     [rcx+8], eax
0x18000a3ba  mov     rdi, rcx
0x18000a3bd  mov     [rcx+10h], r13
0x18000a3c1  mov     r12, rdx
0x18000a3c4  movzx   eax, word ptr [rdx+40h]
0x18000a3c8  mov     [rcx+18h], ax
0x18000a3cc  mov     al, [rdx]
0x18000a3ce  mov     [rcx+1Ah], al
0x18000a3d1  mov     [rcx+20h], r13
0x18000a3d5  mov     rax, [rdx+88h]
0x18000a3dc  mov     [rcx+28h], rax
0x18000a3e0  mov     rax, [rdx+90h]
0x18000a3e7  mov     [rcx+30h], rax
0x18000a3eb  mov     [rcx+38h], r13
0x18000a3ef  mov     rcx, [rdx+38h]
0x18000a3f3  lea     edx, [rbp+2]
0x18000a3f6  test    rcx, rcx
0x18000a3f9  jnz     short loc_18000A400
0x18000a3fb  mov     r8d, edx
0x18000a3fe  jmp     short loc_18000A410
0x18000a400  mov     rax, rbp
0x18000a403  inc     rax
0x18000a406  cmp     [rcx+rax], r13b
0x18000a40a  jnz     short loc_18000A403
0x18000a40c  lea     r8, [rax+1]; unsigned __int64
0x18000a410  mov     rcx, [r12+80h]
0x18000a418  test    rcx, rcx
0x18000a41b  jz      short loc_18000A42D
0x18000a41d  mov     rax, rbp
0x18000a420  inc     rax
0x18000a423  cmp     [rcx+rax], r13b
0x18000a427  jnz     short loc_18000A420
0x18000a429  lea     rdx, [rax+1]
0x18000a42d  mov     rcx, [r12+18h]
0x18000a432  test    rcx, rcx
0x18000a435  jnz     short loc_18000A43C
0x18000a437  lea     eax, [rcx+2]
0x18000a43a  jmp     short loc_18000A451
0x18000a43c  mov     rax, rbp
0x18000a43f  inc     rax
0x18000a442  cmp     [rcx+rax*2], r13w
0x18000a447  jnz     short loc_18000A43F
0x18000a449  lea     rax, ds:2[rax*2]
0x18000a451  lea     r14, [rdx+rax]
0x18000a455  add     r14, r8
0x18000a458  lea     rsi, [rdi+48h]
0x18000a45c  cmp     [rdi+40h], r13
0x18000a460  jz      short loc_18000A467
0x18000a462  cmp     [rsi], r14
0x18000a465  jnb     short loc_18000A49B
0x18000a467  mov     rdx, r14; dwBytes
0x18000a46a  mov     ecx, 8; dwFlags
0x18000a46f  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000a474  mov     r15, rax
0x18000a477  test    rax, rax
0x18000a47a  jz      short loc_18000A49B
0x18000a47c  mov     rbx, [rdi+40h]
0x18000a480  call    cs:__imp_GetProcessHeap
0x18000a486  mov     r8, rbx; lpMem
0x18000a489  xor     edx, edx; dwFlags
0x18000a48b  mov     rcx, rax; hHeap
0x18000a48e  call    cs:__imp_HeapFree
0x18000a494  mov     [rdi+40h], r15
0x18000a498  mov     [rsi], r14
0x18000a49b  mov     rbx, [rdi+40h]
0x18000a49f  test    rbx, rbx
0x18000a4a2  jz      loc_18000A5A0
0x18000a4a8  mov     rdx, [rsi]; DestinationSize
0x18000a4ab  lea     rsi, [rdx+rbx]
0x18000a4af  cmp     rbx, rsi
0x18000a4b2  jz      short loc_18000A4F2
0x18000a4b4  mov     r8, [r12+38h]; Source
0x18000a4b9  test    r8, r8
0x18000a4bc  jz      short loc_18000A4F2
0x18000a4be  cmp     [r8], r13b
0x18000a4c1  jz      short loc_18000A4F2
0x18000a4c3  mov     rax, rbp
0x18000a4c6  inc     rax
0x18000a4c9  cmp     [r8+rax], r13b
0x18000a4cd  jnz     short loc_18000A4C6
0x18000a4cf  lea     r14, [rax+1]
0x18000a4d3  cmp     rdx, r14
0x18000a4d6  jnb     short loc_18000A4DE
0x18000a4d8  mov     [rdi+10h], r13
0x18000a4dc  jmp     short loc_18000A4FB
0x18000a4de  mov     r9, r14; SourceSize
0x18000a4e1  mov     rcx, rbx; Destination
0x18000a4e4  call    memcpy_s
0x18000a4e9  mov     [rdi+10h], rbx
0x18000a4ed  add     rbx, r14
0x18000a4f0  jmp     short loc_18000A4F6
0x18000a4f2  mov     [rdi+10h], r13
0x18000a4f6  cmp     rbx, rsi
0x18000a4f9  jz      short loc_18000A542
0x18000a4fb  mov     r8, [r12+80h]; Source
0x18000a503  test    r8, r8
0x18000a506  jz      short loc_18000A542
0x18000a508  cmp     [r8], r13b
0x18000a50b  jz      short loc_18000A542
0x18000a50d  mov     rax, rbp
0x18000a510  inc     rax
0x18000a513  cmp     [r8+rax], r13b
0x18000a517  jnz     short loc_18000A510
0x18000a519  mov     rdx, rsi
0x18000a51c  lea     r14, [rax+1]
0x18000a520  sub     rdx, rbx; DestinationSize
0x18000a523  cmp     rdx, r14
0x18000a526  jnb     short loc_18000A52E
0x18000a528  mov     [rdi+20h], r13
0x18000a52c  jmp     short loc_18000A54B
0x18000a52e  mov     r9, r14; SourceSize
0x18000a531  mov     rcx, rbx; Destination
0x18000a534  call    memcpy_s
0x18000a539  mov     [rdi+20h], rbx
0x18000a53d  add     rbx, r14
0x18000a540  jmp     short loc_18000A546
0x18000a542  mov     [rdi+20h], r13
0x18000a546  cmp     rbx, rsi
0x18000a549  jz      short loc_18000A58C
0x18000a54b  mov     r8, [r12+18h]; Source
0x18000a550  test    r8, r8
0x18000a553  jz      short loc_18000A58C
0x18000a555  cmp     [r8], r13w
0x18000a559  jz      short loc_18000A58C
0x18000a55b  inc     rbp
0x18000a55e  cmp     [r8+rbp*2], r13w
0x18000a563  jnz     short loc_18000A55B
0x18000a565  mov     rdx, rsi
0x18000a568  lea     r14, ds:2[rbp*2]
0x18000a570  sub     rdx, rbx; DestinationSize
0x18000a573  cmp     rdx, r14
0x18000a576  jb      short loc_18000A58C
0x18000a578  mov     r9, r14; SourceSize
0x18000a57b  mov     rcx, rbx; Destination
0x18000a57e  call    memcpy_s
0x18000a583  mov     [rdi+38h], rbx
0x18000a587  add     rbx, r14
0x18000a58a  jmp     short loc_18000A590
0x18000a58c  mov     [rdi+38h], r13
0x18000a590  sub     rsi, rbx
0x18000a593  xor     edx, edx; Val
0x18000a595  mov     r8, rsi; Size
0x18000a598  mov     rcx, rbx; void *
0x18000a59b  call    memset_0
0x18000a5a0  add     rsp, 28h
0x18000a5a4  pop     r15
0x18000a5a6  pop     r14
0x18000a5a8  pop     r13
0x18000a5aa  pop     r12
0x18000a5ac  pop     rdi
0x18000a5ad  pop     rsi
0x18000a5ae  pop     rbp
0x18000a5af  pop     rbx
0x18000a5b0  retn
```
