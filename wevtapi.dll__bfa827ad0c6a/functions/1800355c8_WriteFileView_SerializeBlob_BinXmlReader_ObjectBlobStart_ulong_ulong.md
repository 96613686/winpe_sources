# WriteFileView::SerializeBlob(BinXmlReader &,ObjectBlobStart *,ulong,ulong &)

- ea: `0x1800355c8`
- end: `0x18003577e`
- name: `?SerializeBlob@WriteFileView@@QEAAKAEAVBinXmlReader@@PEAUObjectBlobStart@@KAEAK@Z`
- size: `438`
- prototype: `__int64 __fastcall(WriteFileView *this, struct BinXmlReader *, struct ObjectBlobStart *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x18003316c`

## callees

- `0x180003a68`
- `0x180008b20`
- `0x18000a4b4`
- `0x1800196a0`
- `0x1800240ac`
- `0x18002e298`
- `0x180035480`
- `0x1800355c8`
- `0x180035790`
- `0x1800358f0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WriteFileView::SerializeBlob(
        WriteFileView *this,
        struct BinXmlReader *a2,
        struct ObjectBlobStart *a3,
        unsigned int a4,
        unsigned int *a5)
{
  unsigned int v9; // eax
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rax
  unsigned int v12; // r15d
  __int64 result; // rax
  unsigned int v14; // ecx
  _BYTE v15[16]; // [rsp+40h] [rbp-A8h] BYREF
  unsigned int v16; // [rsp+50h] [rbp-98h]
  EvtException *v17; // [rsp+58h] [rbp-90h] BYREF
  _BYTE v18[48]; // [rsp+60h] [rbp-88h] BYREF
  _BYTE v19[64]; // [rsp+90h] [rbp-58h] BYREF
  int v20; // [rsp+108h] [rbp+20h] BYREF

  v9 = *((_DWORD *)this + 8) - *((_DWORD *)this + 6) - 128;
  if ( a4 >= v9 )
    return 111;
  v10 = v9 - a4;
  v11 = *((unsigned int *)a2 + 46) + 4LL;
  if ( v11 > v10 )
    return 111;
  try
  {
    WriteFileView::SetCurrentIndex(this, a4);
    v12 = *((_DWORD *)this + 14) - *((_DWORD *)this + 6);
    WriteFileView::Advance(this, 0x18u);
    WriteBuffer::WriteBuffer((WriteBuffer *)v15, this);
    WriteBuffer::SetCurrentIndex((WriteBuffer *)v15, v16 + *((_DWORD *)this + 14) - *((_DWORD *)this + 6));
    BinXmlWriter::BinXmlWriter(
      (BinXmlWriter *)v18,
      0,
      (struct WriteBuffer *)v15,
      (WriteFileView *)((char *)this + 64),
      (WriteFileView *)((char *)this + 344),
      0,
      0);
    BinXmlReader::Reset(a2);
    BinXmlReader::CopyInto(a2, (struct BinXmlWriter *)v18);
    WriteFileView::SetCurrentIndex(this, v16);
    if ( ((*((_BYTE *)this + 56) - *((_BYTE *)this + 24) - 4) & 7) != 0 )
      WriteFileView::Advance(this, 8 - ((*((_BYTE *)this + 56) - *((_BYTE *)this + 24) - 4) & 7));
    v20 = *((_DWORD *)this + 14) - *((_DWORD *)this + 6) - a4 + 4;
    WriteFileView::Write(this, &v20, 4u);
    if ( *((_QWORD *)this + 7) < *((_QWORD *)this + 4) )
    {
      WriteFileView::SetCurrentIndex(this, v12);
      v14 = v20;
      *((_DWORD *)a3 + 1) = v20;
      *a5 = v14;
      WriteFileView::Write(this, a3, 0x18u);
      utl::vector<tag_EvtRpcVariant,utl::allocator<tag_EvtRpcVariant>>::_Uninit(v19);
      result = 0;
    }
    else
    {
      utl::vector<tag_EvtRpcVariant,utl::allocator<tag_EvtRpcVariant>>::_Uninit(v19);
      result = 111;
    }
  }
  catch ( EvtException *v17 )
  {
    if ( *((_DWORD *)v17 + 6) == 1359 )
      return 111;
    return (unsigned int)*((_DWORD *)v17 + 6);
  }
  WriteFileView::SetCurrentIndex(this, a4);
}

```

## disassembly

```asm
0x1800355c8  mov     [rsp+arg_0], rbx
0x1800355cd  mov     [rsp+arg_8], rsi
0x1800355d2  push    rdi
0x1800355d3  push    r14
0x1800355d5  push    r15
0x1800355d7  sub     rsp, 0D0h
0x1800355de  mov     edi, r9d
0x1800355e1  mov     r14, r8
0x1800355e4  mov     rsi, rdx
0x1800355e7  mov     rbx, rcx
0x1800355ea  mov     eax, [rcx+20h]
0x1800355ed  sub     eax, [rcx+18h]
0x1800355f0  add     eax, 0FFFFFF80h
0x1800355f3  cmp     r9d, eax
0x1800355f6  jnb     loc_18003575F
0x1800355fc  sub     eax, r9d
0x1800355ff  mov     ecx, eax
0x180035601  mov     eax, [rdx+0B8h]
0x180035607  add     rax, 4
0x18003560b  cmp     rax, rcx
0x18003560e  ja      loc_18003575F
0x180035614  mov     edx, r9d; unsigned int
0x180035617  mov     rcx, rbx; this
0x18003561a  call    ?SetCurrentIndex@WriteFileView@@UEAAXK@Z; WriteFileView::SetCurrentIndex(ulong)
0x18003561f  mov     r15d, [rbx+38h]
0x180035623  sub     r15d, [rbx+18h]
0x180035627  mov     edx, 18h; unsigned int
0x18003562c  mov     rcx, rbx; this
0x18003562f  call    ?Advance@WriteFileView@@UEAAXK@Z; WriteFileView::Advance(ulong)
0x180035634  mov     rdx, rbx; struct BufferStream *
0x180035637  lea     rcx, [rsp+0E8h+var_A8]; this
0x18003563c  call    ??0WriteBuffer@@QEAA@AEAVBufferStream@@@Z; WriteBuffer::WriteBuffer(BufferStream &)
0x180035641  mov     edx, [rbx+38h]
0x180035644  sub     edx, [rbx+18h]
0x180035647  add     edx, [rsp+0E8h+var_98]; unsigned int
0x18003564b  lea     rcx, [rsp+0E8h+var_A8]; this
0x180035650  call    ?SetCurrentIndex@WriteBuffer@@QEAAXK@Z; WriteBuffer::SetCurrentIndex(ulong)
0x180035655  lea     rax, [rbx+158h]
0x18003565c  lea     r9, [rbx+40h]; struct BinXmlStringTable *
0x180035660  mov     [rsp+0E8h+var_B8], 0; unsigned int
0x180035668  mov     [rsp+0E8h+var_C0], 0; unsigned int *
0x180035671  mov     [rsp+0E8h+var_C8], rax; struct BinXmlTemplateTable *
0x180035676  lea     r8, [rsp+0E8h+var_A8]; struct WriteBuffer *
0x18003567b  xor     edx, edx; bool
0x18003567d  lea     rcx, [rsp+0E8h+var_88]; this
0x180035682  call    ??0BinXmlWriter@@QEAA@_NAEAVWriteBuffer@@PEAVBinXmlStringTable@@PEAVBinXmlTemplateTable@@PEBKK@Z; BinXmlWriter::BinXmlWriter(bool,WriteBuffer &,BinXmlStringTable *,BinXmlTemplateTable *,ulong const *,ulong)
0x180035687  nop
0x180035688  mov     rcx, rsi; this
0x18003568b  call    ?Reset@BinXmlReader@@QEAAXXZ; BinXmlReader::Reset(void)
0x180035690  lea     rdx, [rsp+0E8h+var_88]; struct BinXmlWriter *
0x180035695  mov     rcx, rsi; this
0x180035698  call    ?CopyInto@BinXmlReader@@QEAAXAEAVBinXmlWriter@@@Z; BinXmlReader::CopyInto(BinXmlWriter &)
0x18003569d  mov     edx, [rsp+0E8h+var_98]; unsigned int
0x1800356a1  mov     rcx, rbx; this
0x1800356a4  call    ?SetCurrentIndex@WriteFileView@@UEAAXK@Z; WriteFileView::SetCurrentIndex(ulong)
0x1800356a9  mov     eax, [rbx+38h]
0x1800356ac  sub     eax, [rbx+18h]
0x1800356af  sub     eax, 4
0x1800356b2  and     eax, 7
0x1800356b5  jz      short loc_1800356C6
0x1800356b7  mov     edx, 8
0x1800356bc  sub     edx, eax; unsigned int
0x1800356be  mov     rcx, rbx; this
0x1800356c1  call    ?Advance@WriteFileView@@UEAAXK@Z; WriteFileView::Advance(ulong)
0x1800356c6  mov     eax, [rbx+38h]
0x1800356c9  sub     eax, [rbx+18h]
0x1800356cc  sub     eax, edi
0x1800356ce  add     eax, 4
0x1800356d1  mov     [rsp+0E8h+arg_18], eax
0x1800356d8  mov     r8d, 4; unsigned int
0x1800356de  lea     rdx, [rsp+0E8h+arg_18]; void *
0x1800356e6  mov     rcx, rbx; this
0x1800356e9  call    ?Write@WriteFileView@@UEAAXQEBXK@Z; WriteFileView::Write(void const * const,ulong)
0x1800356ee  mov     rax, [rbx+20h]
0x1800356f2  cmp     [rbx+38h], rax
0x1800356f6  jb      short loc_18003570C
0x1800356f8  lea     rcx, [rsp+0E8h+var_58]
0x180035700  call    ?_Uninit@?$vector@Utag_EvtRpcVariant@@V?$allocator@Utag_EvtRpcVariant@@@utl@@@utl@@AEAAXXZ; utl::vector<tag_EvtRpcVariant,utl::allocator<tag_EvtRpcVariant>>::_Uninit(void)
0x180035705  mov     eax, 6Fh ; 'o'
0x18003570a  jmp     short loc_180035764
0x18003570c  mov     edx, r15d; unsigned int
0x18003570f  mov     rcx, rbx; this
0x180035712  call    ?SetCurrentIndex@WriteFileView@@UEAAXK@Z; WriteFileView::SetCurrentIndex(ulong)
0x180035717  mov     ecx, [rsp+0E8h+arg_18]
0x18003571e  mov     [r14+4], ecx
0x180035722  mov     rax, [rsp+0E8h+arg_20]
0x18003572a  mov     [rax], ecx
0x18003572c  mov     r8d, 18h; unsigned int
0x180035732  mov     rdx, r14; void *
0x180035735  mov     rcx, rbx; this
0x180035738  call    ?Write@WriteFileView@@UEAAXQEBXK@Z; WriteFileView::Write(void const * const,ulong)
0x18003573d  nop
0x18003573e  lea     rcx, [rsp+0E8h+var_58]
0x180035746  call    ?_Uninit@?$vector@Utag_EvtRpcVariant@@V?$allocator@Utag_EvtRpcVariant@@@utl@@@utl@@AEAAXXZ; utl::vector<tag_EvtRpcVariant,utl::allocator<tag_EvtRpcVariant>>::_Uninit(void)
0x18003574b  xor     eax, eax
0x18003574d  jmp     short loc_180035764
0x18003574f  mov     eax, 6Fh ; 'o'
0x180035754  jmp     short loc_18003575D
0x180035756  mov     eax, [rsp+0E8h+arg_18]
0x18003575d  jmp     short loc_180035764
0x18003575f  mov     eax, 6Fh ; 'o'
0x180035764  lea     r11, [rsp+0E8h+var_18]
0x18003576c  mov     rbx, [r11+20h]
0x180035770  mov     rsi, [r11+28h]
0x180035774  mov     rsp, r11
0x180035777  pop     r15
0x180035779  pop     r14
0x18003577b  pop     rdi
0x18003577c  retn
```
