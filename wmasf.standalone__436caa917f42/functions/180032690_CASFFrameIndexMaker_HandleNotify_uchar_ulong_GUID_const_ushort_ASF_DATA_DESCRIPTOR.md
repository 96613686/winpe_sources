# CASFFrameIndexMaker::HandleNotify(uchar *,ulong,_GUID const *,ushort,_ASF_DATA_DESCRIPTOR *)

- ea: `0x180032690`
- end: `0x180032886`
- name: `?HandleNotify@CASFFrameIndexMaker@@MEAAJPEAEKPEBU_GUID@@GPEAU_ASF_DATA_DESCRIPTOR@@@Z`
- size: `502`
- prototype: `__int64 __usercall@<rax>(CASFFrameIndexMaker *__hidden this@<rcx>, unsigned __int8 *@<rdx>, unsigned int@<r8d>, const struct _GUID *@<r9>, unsigned __int16, struct _ASF_DATA_DESCRIPTOR *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18002f1dc`
- `0x18002f704`
- `0x180032110`
- `0x180032690`
- `0x18003288c`

## pseudocode

```c
__int64 __fastcall CASFFrameIndexMaker::HandleNotify(
        CASFFrameIndexMaker *this,
        unsigned __int8 *a2,
        unsigned int a3,
        const struct _GUID *a4,
        unsigned __int16 a5,
        struct _ASF_DATA_DESCRIPTOR *a6)
{
  unsigned int v8; // r10d
  unsigned int v9; // r15d
  __int64 Ptr; // rax
  int v11; // r10d
  unsigned int v12; // r12d
  unsigned int v13; // r13d
  char *v14; // rbp
  __int64 v15; // rax
  struct CASFBaseIndexMaker::STREAM_INFO *v16; // rdi
  _QWORD *v17; // r14
  __int64 v18; // rax
  __int64 v19; // xmm0_8
  struct CASFBaseIndexMaker::STREAM_INFO *v20; // rbx
  __int128 v21; // [rsp+20h] [rbp-A8h]
  __int128 v22; // [rsp+40h] [rbp-88h] BYREF
  __int64 v23; // [rsp+50h] [rbp-78h]
  __int128 v24; // [rsp+60h] [rbp-68h] BYREF
  __int64 v25; // [rsp+70h] [rbp-58h]
  unsigned int i; // [rsp+D0h] [rbp+8h]

  v21 = 0;
  if ( !a6 )
    return 1;
  v8 = 0;
  v9 = *((_DWORD *)this + 3250) >> 1;
  if ( v9 )
  {
    do
    {
      Ptr = CTDynArray<CASFBaseIndexMaker::STREAM_INFO,20>::GetPtr((char *)this + 352, v8);
      if ( Ptr )
        *(_QWORD *)(Ptr + 16) = 0;
      v8 = v11 + 1;
    }
    while ( v8 < v9 );
  }
  v12 = 0;
  for ( i = 0; v12 < a5; i = ++v12 )
  {
    v13 = 0;
    v14 = (char *)a6 + 88 * v12;
    if ( v9 )
    {
      do
      {
        v15 = CTDynArray<CASFBaseIndexMaker::STREAM_INFO,20>::GetPtr((char *)this + 352, v13);
        v16 = (struct CASFBaseIndexMaker::STREAM_INFO *)v15;
        if ( v15 && *(_WORD *)(v15 + 2) == *((_WORD *)v14 + 4) && *(_BYTE *)v15 != v14[10] )
        {
          v17 = (_QWORD *)(v15 + 24);
          if ( !*(_QWORD *)(v15 + 16) )
            *(_QWORD *)(v15 + 16) = *v17;
          if ( *(_WORD *)(v15 + 4) != 3 || (v14[24] & 2) != 0 && ((v14[24] & 4) == 0 || !*((_DWORD *)v14 + 11)) )
          {
            v17 = (_QWORD *)(v15 + 24);
            *(_QWORD *)&v21 = *(_QWORD *)(v15 + 24);
            v23 = *((_QWORD *)this + 14);
            v22 = v21;
            CTDynArray<CASFBaseIndexMaker::SEEK_POINT,20>::Add(v15 + 40, &v22);
            CASFFrameIndexMaker::CompleteStreamIndex(this, v16, *((_QWORD *)v16 + 3));
            v18 = CTDynArray<CASFBaseIndexMaker::STREAM_INFO,20>::GetPtr((char *)this + 352, v9 + v13);
            v19 = *((_QWORD *)v16 + 2);
            v20 = (struct CASFBaseIndexMaker::STREAM_INFO *)v18;
            v24 = v21;
            v25 = v19;
            CTDynArray<CASFBaseIndexMaker::SEEK_POINT,20>::Add(v18 + 40, &v24);
            CASFFrameIndexMaker::CompleteStreamIndex(this, v20, *((_QWORD *)v16 + 3));
          }
          ++*v17;
          *(_BYTE *)v16 = v14[10];
        }
        ++v13;
      }
      while ( v13 < v9 );
      v12 = i;
    }
  }
  CASFFrameIndexMaker::SendAllIndexBlocks(this);
  *((_QWORD *)this + 14) += a3;
  return 0;
}

```

## disassembly

```asm
0x180032690  mov     rax, rsp
0x180032693  mov     [rax+10h], rbx
0x180032697  mov     [rax+18h], r8d
0x18003269b  push    rbp
0x18003269c  push    rsi
0x18003269d  push    rdi
0x18003269e  push    r12
0x1800326a0  push    r13
0x1800326a2  push    r14
0x1800326a4  push    r15
0x1800326a6  sub     rsp, 90h
0x1800326ad  movaps  xmmword ptr [rax-48h], xmm6
0x1800326b1  xorps   xmm0, xmm0
0x1800326b4  xor     eax, eax
0x1800326b6  mov     rsi, rcx
0x1800326b9  movups  [rsp+0C8h+var_A8], xmm0
0x1800326be  cmp     [rsp+0C8h+arg_28], rax
0x1800326c6  jnz     short loc_1800326D2
0x1800326c8  mov     eax, 1
0x1800326cd  jmp     loc_180032866
0x1800326d2  mov     r15d, [rcx+32C8h]
0x1800326d9  xor     r10d, r10d
0x1800326dc  shr     r15d, 1
0x1800326df  jz      short loc_180032705
0x1800326e1  mov     edx, r10d
0x1800326e4  lea     rcx, [rsi+160h]
0x1800326eb  call    ?GetPtr@?$CTDynArray@USTREAM_INFO@CASFBaseIndexMaker@@$0BE@@@QEAAPEAUSTREAM_INFO@CASFBaseIndexMaker@@K@Z; CTDynArray<CASFBaseIndexMaker::STREAM_INFO,20>::GetPtr(ulong)
0x1800326f0  test    rax, rax
0x1800326f3  jz      short loc_1800326FD
0x1800326f5  mov     qword ptr [rax+10h], 0
0x1800326fd  inc     r10d
0x180032700  cmp     r10d, r15d
0x180032703  jb      short loc_1800326E1
0x180032705  movzx   eax, [rsp+0C8h+arg_20]
0x18003270d  xor     r12d, r12d
0x180032710  mov     [rsp+0C8h+arg_0], r12d
0x180032718  test    eax, eax
0x18003271a  jz      loc_180032851
0x180032720  mov     eax, r12d
0x180032723  xor     r13d, r13d
0x180032726  imul    rbp, rax, 58h ; 'X'
0x18003272a  add     rbp, [rsp+0C8h+arg_28]
0x180032732  test    r15d, r15d
0x180032735  jz      loc_180032835
0x18003273b  lea     r12, [rsi+160h]
0x180032742  mov     edx, r13d
0x180032745  mov     rcx, r12
0x180032748  call    ?GetPtr@?$CTDynArray@USTREAM_INFO@CASFBaseIndexMaker@@$0BE@@@QEAAPEAUSTREAM_INFO@CASFBaseIndexMaker@@K@Z; CTDynArray<CASFBaseIndexMaker::STREAM_INFO,20>::GetPtr(ulong)
0x18003274d  mov     rdi, rax
0x180032750  test    rax, rax
0x180032753  jz      loc_180032821
0x180032759  movzx   ecx, word ptr [rbp+8]
0x18003275d  cmp     [rax+2], cx
0x180032761  jnz     loc_180032821
0x180032767  mov     cl, [rbp+0Ah]
0x18003276a  cmp     [rax], cl
0x18003276c  jz      loc_180032821
0x180032772  cmp     qword ptr [rax+10h], 0
0x180032777  lea     r14, [rax+18h]
0x18003277b  jnz     short loc_180032784
0x18003277d  mov     rax, [r14]
0x180032780  mov     [rdi+10h], rax
0x180032784  cmp     word ptr [rdi+4], 3
0x180032789  jnz     short loc_1800327A1
0x18003278b  test    byte ptr [rbp+18h], 2
0x18003278f  jz      loc_180032819
0x180032795  test    byte ptr [rbp+18h], 4
0x180032799  jz      short loc_1800327A1
0x18003279b  cmp     dword ptr [rbp+2Ch], 0
0x18003279f  jnz     short loc_180032819
0x1800327a1  movsd   xmm0, qword ptr [rsi+70h]
0x1800327a6  lea     r14, [rdi+18h]
0x1800327aa  mov     rax, [r14]
0x1800327ad  lea     rcx, [rdi+28h]
0x1800327b1  mov     qword ptr [rsp+0C8h+var_A8], rax
0x1800327b6  lea     rdx, [rsp+0C8h+var_88]
0x1800327bb  movups  xmm6, [rsp+0C8h+var_A8]
0x1800327c0  movsd   [rsp+0C8h+var_78], xmm0
0x1800327c6  movaps  [rsp+0C8h+var_88], xmm6
0x1800327cb  call    ?Add@?$CTDynArray@USEEK_POINT@CASFBaseIndexMaker@@$0BE@@@QEAAHUSEEK_POINT@CASFBaseIndexMaker@@PEAK@Z; CTDynArray<CASFBaseIndexMaker::SEEK_POINT,20>::Add(CASFBaseIndexMaker::SEEK_POINT,ulong *)
0x1800327d0  mov     r8, [r14]; unsigned __int64
0x1800327d3  mov     rdx, rdi; struct CASFBaseIndexMaker::STREAM_INFO *
0x1800327d6  mov     rcx, rsi; this
0x1800327d9  call    ?CompleteStreamIndex@CASFFrameIndexMaker@@AEAAJPEAUSTREAM_INFO@CASFBaseIndexMaker@@_K@Z; CASFFrameIndexMaker::CompleteStreamIndex(CASFBaseIndexMaker::STREAM_INFO *,unsigned __int64)
0x1800327de  lea     edx, [r15+r13]
0x1800327e2  mov     rcx, r12
0x1800327e5  call    ?GetPtr@?$CTDynArray@USTREAM_INFO@CASFBaseIndexMaker@@$0BE@@@QEAAPEAUSTREAM_INFO@CASFBaseIndexMaker@@K@Z; CTDynArray<CASFBaseIndexMaker::STREAM_INFO,20>::GetPtr(ulong)
0x1800327ea  movsd   xmm0, qword ptr [rdi+10h]
0x1800327ef  lea     rdx, [rsp+0C8h+var_68]
0x1800327f4  mov     rbx, rax
0x1800327f7  movaps  [rsp+0C8h+var_68], xmm6
0x1800327fc  movsd   [rsp+0C8h+var_58], xmm0
0x180032802  lea     rcx, [rax+28h]
0x180032806  call    ?Add@?$CTDynArray@USEEK_POINT@CASFBaseIndexMaker@@$0BE@@@QEAAHUSEEK_POINT@CASFBaseIndexMaker@@PEAK@Z; CTDynArray<CASFBaseIndexMaker::SEEK_POINT,20>::Add(CASFBaseIndexMaker::SEEK_POINT,ulong *)
0x18003280b  mov     r8, [r14]; unsigned __int64
0x18003280e  mov     rdx, rbx; struct CASFBaseIndexMaker::STREAM_INFO *
0x180032811  mov     rcx, rsi; this
0x180032814  call    ?CompleteStreamIndex@CASFFrameIndexMaker@@AEAAJPEAUSTREAM_INFO@CASFBaseIndexMaker@@_K@Z; CASFFrameIndexMaker::CompleteStreamIndex(CASFBaseIndexMaker::STREAM_INFO *,unsigned __int64)
0x180032819  inc     qword ptr [r14]
0x18003281c  mov     al, [rbp+0Ah]
0x18003281f  mov     [rdi], al
0x180032821  inc     r13d
0x180032824  cmp     r13d, r15d
0x180032827  jb      loc_180032742
0x18003282d  mov     r12d, [rsp+0C8h+arg_0]
0x180032835  movzx   eax, [rsp+0C8h+arg_20]
0x18003283d  inc     r12d
0x180032840  mov     [rsp+0C8h+arg_0], r12d
0x180032848  cmp     r12d, eax
0x18003284b  jb      loc_180032720
0x180032851  mov     rcx, rsi; this
0x180032854  call    ?SendAllIndexBlocks@CASFFrameIndexMaker@@AEAAJXZ; CASFFrameIndexMaker::SendAllIndexBlocks(void)
0x180032859  mov     eax, [rsp+0C8h+arg_10]
0x180032860  add     [rsi+70h], rax
0x180032864  xor     eax, eax
0x180032866  lea     r11, [rsp+0C8h+var_38]
0x18003286e  mov     rbx, [r11+48h]
0x180032872  movaps  xmm6, xmmword ptr [r11-10h]
0x180032877  mov     rsp, r11
0x18003287a  pop     r15
0x18003287c  pop     r14
0x18003287e  pop     r13
0x180032880  pop     r12
0x180032882  pop     rdi
0x180032883  pop     rsi
0x180032884  pop     rbp
0x180032885  retn
```
