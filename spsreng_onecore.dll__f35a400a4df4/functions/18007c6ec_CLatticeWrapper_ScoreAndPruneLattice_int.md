# CLatticeWrapper::ScoreAndPruneLattice(int)

- ea: `0x18007c6ec`
- end: `0x18007c981`
- name: `?ScoreAndPruneLattice@CLatticeWrapper@@IEAAJH@Z`
- size: `661`
- prototype: `int(CLatticeWrapper *__hidden this, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18007d724`

## callees

- `0x180002470`
- `0x180002aac`
- `0x18004e610`
- `0x180078cd4`
- `0x18007bb8c`
- `0x18007c6ec`
- `0x18007c988`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007c953`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007c953`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18007c82c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18007c82c`

## pseudocode

```c
__int64 __fastcall CLatticeWrapper::ScoreAndPruneLattice(struct LATTICE_NODE **this, int a2)
{
  int v4; // r15d
  unsigned __int16 *v5; // rax
  CLatticeWrapper *v6; // rcx
  unsigned __int16 *v7; // r12
  int v8; // edi
  unsigned int v9; // ecx
  unsigned int v10; // edx
  struct LATTICE_NODE *v11; // rax
  __int64 v12; // r9
  LPVOID *v13; // r14
  _WORD *v14; // r15
  int v15; // edx
  __int64 v16; // rax
  struct LATTICE_NODE *v17; // r12
  __int64 v18; // r13
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // r12
  __int64 v22; // rax
  int v23; // ecx
  struct LATTICE_NODE *v25; // [rsp+40h] [rbp-18h]
  unsigned __int16 *v26; // [rsp+48h] [rbp-10h]
  int v27; // [rsp+A0h] [rbp+48h] BYREF
  unsigned int v28; // [rsp+A8h] [rbp+50h] BYREF
  int v29; // [rsp+B0h] [rbp+58h]
  int v30; // [rsp+B8h] [rbp+60h]

  v4 = CLatticeWrapper::ScoreLattice((CLatticeWrapper *)this, (struct LATTICE_HEADER *)(this + 3), this[96], this[99]);
  if ( a2 <= -536870912 )
  {
    return 0;
  }
  else
  {
    v5 = (unsigned __int16 *)CWinHeap::Alloc((CWinHeap *)&g_heap, 2LL * *((unsigned int *)this + 16), 0);
    v26 = v5;
    v7 = v5;
    if ( v5 )
    {
      CLatticeWrapper::PruneLattice(v6, (struct LATTICE_HEADER *)(this + 3), this[96], this[99], v5, v4, a2);
      v9 = *((_DWORD *)this + 17);
      if ( v9 <= 0x7FFF )
      {
        v10 = 0;
        *((_DWORD *)this + 248) = *((_DWORD *)this + 16);
        *((_DWORD *)this + 249) = v9;
        while ( 1 )
        {
          v11 = this[116];
          if ( v10 >= *((_DWORD *)v11 + 212) )
            break;
          v12 = *((_QWORD *)v11 + 104);
          if ( (*(_BYTE *)(v12 + 8LL * v10) & 1) == 0 )
          {
            *(_WORD *)(v12 + 8LL * v10 + 2) = v7[*(unsigned __int16 *)(v12 + 8LL * v10 + 2)];
            if ( *(_WORD *)(*((_QWORD *)this[116] + 104) + 8LL * v10 + 2) == 0xFFFF )
              goto LABEL_5;
          }
          ++v10;
        }
        v13 = (LPVOID *)(this + 101);
        v28 = 0;
        v14 = 0;
        if ( this[101] )
        {
          if ( *((_DWORD *)this + 208) )
            v15 = *((_DWORD *)this[103] + *((unsigned int *)this + 208));
          else
            v15 = 0;
          v14 = CoTaskMemRealloc(*v13, (2 * v15 + 3) & 0xFFFFFFFC);
          if ( !v14 )
            v14 = *v13;
          *v13 = 0;
          CStringBlobT<unsigned long>::Clear(this + 101);
        }
        v8 = CStringBlobT<unsigned short>::Add(this + 101, &word_18010FB50, &v28);
        if ( v8 >= 0 )
        {
          v16 = 0;
          v29 = 0;
          if ( *((_DWORD *)this + 248) )
          {
            while ( 1 )
            {
              v17 = this[96];
              v18 = 116 * v16;
              v25 = v17;
              v19 = *((unsigned int *)v17 + 29 * v16 + 3);
              v27 = v19;
              if ( (unsigned int)v19 > v28 )
              {
                v8 = CStringBlobT<unsigned short>::Add(this + 101, &v14[v19], &v27);
                if ( v8 < 0 )
                  goto LABEL_35;
                *(_DWORD *)((char *)v17 + v18 + 12) = v27;
              }
              v20 = *(unsigned int *)((char *)v17 + v18 + 16);
              v27 = v20;
              if ( (unsigned int)v20 > v28 )
              {
                v8 = CStringBlobT<unsigned short>::Add(this + 101, &v14[v20], &v27);
                if ( v8 < 0 )
                  goto LABEL_35;
                *(_DWORD *)((char *)v17 + v18 + 16) = v27;
              }
              v21 = *(unsigned int *)((char *)v17 + v18 + 20);
              if ( (_DWORD)v21 )
              {
                if ( v14[v21] )
                {
                  LODWORD(v22) = v21;
                  do
                  {
                    v22 = (unsigned int)(v22 - 1);
                    v23 = v22;
                  }
                  while ( v14[v22] );
                }
                else
                {
                  v23 = v21;
                }
                v30 = v23 + 1;
                v27 = v23 + 1;
                v8 = CStringBlobT<unsigned short>::Add(this + 101, &v14[v23 + 1], &v27);
                if ( v8 < 0 )
                {
LABEL_35:
                  v7 = v26;
                  break;
                }
                *(_DWORD *)((char *)v25 + v18 + 20) = v27 + v21 - v30;
              }
              v16 = (unsigned int)(v29 + 1);
              v29 = v16;
              if ( (unsigned int)v16 >= *((_DWORD *)this + 248) )
                goto LABEL_35;
            }
          }
        }
        if ( v14 )
          CoTaskMemFree(v14);
      }
      else
      {
LABEL_5:
        v8 = -2147024809;
      }
      CWinHeap::Free((CWinHeap *)&g_heap, v7);
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18007c6ec  push    rbp
0x18007c6ee  push    rbx
0x18007c6ef  push    rsi
0x18007c6f0  push    rdi
0x18007c6f1  push    r12
0x18007c6f3  push    r13
0x18007c6f5  push    r14
0x18007c6f7  push    r15
0x18007c6f9  mov     rbp, rsp
0x18007c6fc  sub     rsp, 58h
0x18007c700  mov     r9, [rcx+318h]; struct LATTICE_ARC *
0x18007c707  mov     edi, edx
0x18007c709  mov     r8, [rcx+300h]; struct LATTICE_NODE *
0x18007c710  lea     rdx, [rcx+18h]; struct LATTICE_HEADER *
0x18007c714  mov     rsi, rcx
0x18007c717  call    ?ScoreLattice@CLatticeWrapper@@IEAAHPEAULATTICE_HEADER@@PEAULATTICE_NODE@@PEAULATTICE_ARC@@@Z; CLatticeWrapper::ScoreLattice(LATTICE_HEADER *,LATTICE_NODE *,LATTICE_ARC *)
0x18007c71c  mov     r15d, eax
0x18007c71f  cmp     edi, 0E0000000h
0x18007c725  jle     loc_18007C96A
0x18007c72b  mov     edx, [rsi+40h]
0x18007c72e  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x18007c735  add     rdx, rdx; unsigned __int64
0x18007c738  xor     r8d, r8d; bool
0x18007c73b  call    ?Alloc@CWinHeap@@QEAAPEAX_K_N@Z; CWinHeap::Alloc(unsigned __int64,bool)
0x18007c740  xor     ebx, ebx
0x18007c742  mov     [rbp+var_10], rax
0x18007c746  mov     r12, rax
0x18007c749  test    rax, rax
0x18007c74c  jnz     short loc_18007C758
0x18007c74e  mov     edi, 8007000Eh
0x18007c753  jmp     loc_18007C96E
0x18007c758  mov     r9, [rsi+318h]; struct LATTICE_ARC *
0x18007c75f  lea     rdx, [rsi+18h]; struct LATTICE_HEADER *
0x18007c763  mov     r8, [rsi+300h]; struct LATTICE_NODE *
0x18007c76a  mov     [rsp+58h+var_28], edi; int
0x18007c76e  mov     [rsp+58h+var_30], r15d; int
0x18007c773  mov     [rsp+58h+var_38], r12; unsigned __int16 *
0x18007c778  call    ?PruneLattice@CLatticeWrapper@@IEAAXPEAULATTICE_HEADER@@PEAULATTICE_NODE@@PEAULATTICE_ARC@@PEAGHH@Z; CLatticeWrapper::PruneLattice(LATTICE_HEADER *,LATTICE_NODE *,LATTICE_ARC *,ushort *,int,int)
0x18007c77d  mov     ecx, [rsi+44h]
0x18007c780  cmp     ecx, 7FFFh
0x18007c786  jbe     short loc_18007C792
0x18007c788  mov     edi, 80070057h
0x18007c78d  jmp     loc_18007C959
0x18007c792  mov     eax, [rsi+40h]
0x18007c795  mov     edx, ebx
0x18007c797  mov     [rsi+3E0h], eax
0x18007c79d  mov     [rsi+3E4h], ecx
0x18007c7a3  mov     rax, [rsi+3A0h]
0x18007c7aa  cmp     edx, [rax+350h]
0x18007c7b0  jnb     short loc_18007C7F3
0x18007c7b2  mov     r9, [rax+340h]
0x18007c7b9  mov     r8d, edx
0x18007c7bc  test    byte ptr [r9+r8*8], 1
0x18007c7c1  jnz     short loc_18007C7EF
0x18007c7c3  movzx   eax, word ptr [r9+r8*8+2]
0x18007c7c9  movzx   ecx, word ptr [r12+rax*2]
0x18007c7ce  mov     [r9+r8*8+2], cx
0x18007c7d4  mov     rax, [rsi+3A0h]
0x18007c7db  mov     rcx, [rax+340h]
0x18007c7e2  mov     eax, 0FFFFh
0x18007c7e7  cmp     [rcx+r8*8+2], ax
0x18007c7ed  jz      short loc_18007C788
0x18007c7ef  inc     edx
0x18007c7f1  jmp     short loc_18007C7A3
0x18007c7f3  lea     r14, [rsi+328h]
0x18007c7fa  mov     [rbp+arg_8], ebx
0x18007c7fd  mov     r15, rbx
0x18007c800  cmp     [r14], rbx
0x18007c803  jz      short loc_18007C848
0x18007c805  cmp     [r14+18h], ebx
0x18007c809  jz      short loc_18007C818
0x18007c80b  mov     ecx, [r14+18h]
0x18007c80f  mov     rax, [r14+10h]
0x18007c813  mov     edx, [rax+rcx*4]
0x18007c816  jmp     short loc_18007C81A
0x18007c818  mov     edx, ebx
0x18007c81a  mov     rcx, [r14]; pv
0x18007c81d  lea     edx, ds:3[rdx*2]
0x18007c824  mov     eax, 0FFFFFFFCh
0x18007c829  and     rdx, rax; cb
0x18007c82c  call    cs:__imp_CoTaskMemRealloc
0x18007c832  mov     r15, rax
0x18007c835  test    rax, rax
0x18007c838  jnz     short loc_18007C83D
0x18007c83a  mov     r15, [r14]
0x18007c83d  mov     rcx, r14
0x18007c840  mov     [r14], rbx
0x18007c843  call    ?Clear@?$CStringBlobT@K@@QEAAXXZ; CStringBlobT<ulong>::Clear(void)
0x18007c848  lea     r8, [rbp+arg_8]
0x18007c84c  mov     rcx, r14
0x18007c84f  lea     rdx, word_18010FB50
0x18007c856  call    ?Add@?$CStringBlobT@G@@QEAAJPEBGPEAK1@Z; CStringBlobT<ushort>::Add(ushort const *,ulong *,ulong *)
0x18007c85b  mov     edi, eax
0x18007c85d  test    eax, eax
0x18007c85f  js      loc_18007C94B
0x18007c865  mov     eax, ebx
0x18007c867  mov     [rbp+arg_10], eax
0x18007c86a  cmp     [rsi+3E0h], ebx
0x18007c870  jbe     loc_18007C94B
0x18007c876  mov     r12, [rsi+300h]
0x18007c87d  imul    r13, rax, 74h ; 't'
0x18007c881  mov     [rbp+var_18], r12
0x18007c885  mov     eax, [r12+r13+0Ch]
0x18007c88a  mov     [rbp+arg_0], eax
0x18007c88d  cmp     eax, [rbp+arg_8]
0x18007c890  jbe     short loc_18007C8B4
0x18007c892  lea     rdx, [r15+rax*2]
0x18007c896  mov     rcx, r14
0x18007c899  lea     r8, [rbp+arg_0]
0x18007c89d  call    ?Add@?$CStringBlobT@G@@QEAAJPEBGPEAK1@Z; CStringBlobT<ushort>::Add(ushort const *,ulong *,ulong *)
0x18007c8a2  mov     edi, eax
0x18007c8a4  test    eax, eax
0x18007c8a6  js      loc_18007C947
0x18007c8ac  mov     eax, [rbp+arg_0]
0x18007c8af  mov     [r12+r13+0Ch], eax
0x18007c8b4  mov     eax, [r12+r13+10h]
0x18007c8b9  mov     [rbp+arg_0], eax
0x18007c8bc  cmp     eax, [rbp+arg_8]
0x18007c8bf  jbe     short loc_18007C8DF
0x18007c8c1  lea     rdx, [r15+rax*2]
0x18007c8c5  mov     rcx, r14
0x18007c8c8  lea     r8, [rbp+arg_0]
0x18007c8cc  call    ?Add@?$CStringBlobT@G@@QEAAJPEBGPEAK1@Z; CStringBlobT<ushort>::Add(ushort const *,ulong *,ulong *)
0x18007c8d1  mov     edi, eax
0x18007c8d3  test    eax, eax
0x18007c8d5  js      short loc_18007C947
0x18007c8d7  mov     eax, [rbp+arg_0]
0x18007c8da  mov     [r12+r13+10h], eax
0x18007c8df  mov     r12d, [r12+r13+14h]
0x18007c8e4  test    r12d, r12d
0x18007c8e7  jz      short loc_18007C933
0x18007c8e9  cmp     [r15+r12*2], bx
0x18007c8ee  jz      short loc_18007C900
0x18007c8f0  mov     eax, r12d
0x18007c8f3  dec     eax
0x18007c8f5  mov     ecx, eax
0x18007c8f7  cmp     [r15+rax*2], bx
0x18007c8fc  jnz     short loc_18007C8F3
0x18007c8fe  jmp     short loc_18007C903
0x18007c900  mov     ecx, r12d
0x18007c903  lea     eax, [rcx+1]
0x18007c906  mov     rcx, r14
0x18007c909  lea     rdx, [r15+rax*2]
0x18007c90d  mov     [rbp+arg_18], eax
0x18007c910  lea     r8, [rbp+arg_0]
0x18007c914  mov     [rbp+arg_0], eax
0x18007c917  call    ?Add@?$CStringBlobT@G@@QEAAJPEBGPEAK1@Z; CStringBlobT<ushort>::Add(ushort const *,ulong *,ulong *)
0x18007c91c  mov     edi, eax
0x18007c91e  test    eax, eax
0x18007c920  js      short loc_18007C947
0x18007c922  mov     rax, [rbp+var_18]
0x18007c926  sub     r12d, [rbp+arg_18]
0x18007c92a  add     r12d, [rbp+arg_0]
0x18007c92e  mov     [rax+r13+14h], r12d
0x18007c933  mov     eax, [rbp+arg_10]
0x18007c936  inc     eax
0x18007c938  mov     [rbp+arg_10], eax
0x18007c93b  cmp     eax, [rsi+3E0h]
0x18007c941  jb      loc_18007C876
0x18007c947  mov     r12, [rbp+var_10]
0x18007c94b  test    r15, r15
0x18007c94e  jz      short loc_18007C959
0x18007c950  mov     rcx, r15; pv
0x18007c953  call    cs:__imp_CoTaskMemFree
0x18007c959  mov     rdx, r12; void *
0x18007c95c  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x18007c963  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x18007c968  jmp     short loc_18007C96E
0x18007c96a  xor     ebx, ebx
0x18007c96c  mov     edi, ebx
0x18007c96e  mov     eax, edi
0x18007c970  add     rsp, 58h
0x18007c974  pop     r15
0x18007c976  pop     r14
0x18007c978  pop     r13
0x18007c97a  pop     r12
0x18007c97c  pop     rdi
0x18007c97d  pop     rsi
0x18007c97e  pop     rbx
0x18007c97f  pop     rbp
0x18007c980  retn
```
