# CASFFrameIndexMaker::CompleteIndexBlocks(unsigned __int64)

- ea: `0x180032070`
- end: `0x180032109`
- name: `?CompleteIndexBlocks@CASFFrameIndexMaker@@MEAAJ_K@Z`
- size: `153`
- prototype: `__int64 __fastcall(CASFFrameIndexMaker *__hidden this, unsigned __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18002f704`
- `0x180032070`
- `0x180032110`
- `0x18003288c`

## pseudocode

```c
__int64 __fastcall CASFFrameIndexMaker::CompleteIndexBlocks(CASFFrameIndexMaker *this)
{
  unsigned __int64 v1; // rsi
  char *v2; // rbp
  unsigned int v3; // r10d
  __int64 Ptr; // rax
  int v6; // r10d
  unsigned __int64 v7; // rcx
  unsigned int v8; // eax
  unsigned int v9; // edi
  struct CASFBaseIndexMaker::STREAM_INFO *v10; // rax

  v1 = 0;
  v2 = (char *)this + 352;
  v3 = 0;
  if ( *((_DWORD *)this + 3250) )
  {
    do
    {
      Ptr = CTDynArray<CASFBaseIndexMaker::STREAM_INFO,20>::GetPtr(v2, v3);
      if ( Ptr )
      {
        v7 = *(_QWORD *)(Ptr + 24);
        if ( v7 > v1 + 1 )
          v1 = v7 - 1;
      }
      v8 = *((_DWORD *)this + 3250);
      v3 = v6 + 1;
    }
    while ( v3 < v8 );
    v9 = 0;
    if ( v8 )
    {
      do
      {
        v10 = (struct CASFBaseIndexMaker::STREAM_INFO *)CTDynArray<CASFBaseIndexMaker::STREAM_INFO,20>::GetPtr(v2, v9);
        if ( v10 )
          CASFFrameIndexMaker::CompleteStreamIndex(
            this,
            v10,
            v1 + *((unsigned int *)this + 17) + *((unsigned int *)this + 16));
        ++v9;
      }
      while ( v9 < *((_DWORD *)this + 3250) );
    }
  }
  CASFFrameIndexMaker::SendAllIndexBlocks(this);
  return 0;
}

```

## disassembly

```asm
0x180032070  push    rbx
0x180032072  push    rbp
0x180032073  push    rsi
0x180032074  push    rdi
0x180032075  sub     rsp, 28h
0x180032079  xor     esi, esi
0x18003207b  lea     rbp, [rcx+160h]
0x180032082  xor     r10d, r10d
0x180032085  mov     rbx, rcx
0x180032088  cmp     [rcx+32C8h], esi
0x18003208e  jbe     short loc_1800320F6
0x180032090  mov     edx, r10d
0x180032093  mov     rcx, rbp
0x180032096  call    ?GetPtr@?$CTDynArray@USTREAM_INFO@CASFBaseIndexMaker@@$0BE@@@QEAAPEAUSTREAM_INFO@CASFBaseIndexMaker@@K@Z; CTDynArray<CASFBaseIndexMaker::STREAM_INFO,20>::GetPtr(ulong)
0x18003209b  test    rax, rax
0x18003209e  jz      short loc_1800320B1
0x1800320a0  mov     rcx, [rax+18h]
0x1800320a4  lea     rax, [rsi+1]
0x1800320a8  cmp     rcx, rax
0x1800320ab  jbe     short loc_1800320B1
0x1800320ad  lea     rsi, [rcx-1]
0x1800320b1  mov     eax, [rbx+32C8h]
0x1800320b7  inc     r10d
0x1800320ba  cmp     r10d, eax
0x1800320bd  jb      short loc_180032090
0x1800320bf  xor     edi, edi
0x1800320c1  test    eax, eax
0x1800320c3  jz      short loc_1800320F6
0x1800320c5  mov     edx, edi
0x1800320c7  mov     rcx, rbp
0x1800320ca  call    ?GetPtr@?$CTDynArray@USTREAM_INFO@CASFBaseIndexMaker@@$0BE@@@QEAAPEAUSTREAM_INFO@CASFBaseIndexMaker@@K@Z; CTDynArray<CASFBaseIndexMaker::STREAM_INFO,20>::GetPtr(ulong)
0x1800320cf  test    rax, rax
0x1800320d2  jz      short loc_1800320EC
0x1800320d4  mov     ecx, [rbx+44h]
0x1800320d7  mov     rdx, rax; struct CASFBaseIndexMaker::STREAM_INFO *
0x1800320da  mov     r8d, [rbx+40h]
0x1800320de  add     rcx, rsi
0x1800320e1  add     r8, rcx; unsigned __int64
0x1800320e4  mov     rcx, rbx; this
0x1800320e7  call    ?CompleteStreamIndex@CASFFrameIndexMaker@@AEAAJPEAUSTREAM_INFO@CASFBaseIndexMaker@@_K@Z; CASFFrameIndexMaker::CompleteStreamIndex(CASFBaseIndexMaker::STREAM_INFO *,unsigned __int64)
0x1800320ec  inc     edi
0x1800320ee  cmp     edi, [rbx+32C8h]
0x1800320f4  jb      short loc_1800320C5
0x1800320f6  mov     rcx, rbx; this
0x1800320f9  call    ?SendAllIndexBlocks@CASFFrameIndexMaker@@AEAAJXZ; CASFFrameIndexMaker::SendAllIndexBlocks(void)
0x1800320fe  xor     eax, eax
0x180032100  add     rsp, 28h
0x180032104  pop     rdi
0x180032105  pop     rsi
0x180032106  pop     rbp
0x180032107  pop     rbx
0x180032108  retn
```
