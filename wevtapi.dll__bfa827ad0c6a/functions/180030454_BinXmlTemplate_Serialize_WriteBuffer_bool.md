# BinXmlTemplate::Serialize(WriteBuffer &,bool)

- ea: `0x180030454`
- end: `0x180030574`
- name: `?Serialize@BinXmlTemplate@@QEBAXAEAVWriteBuffer@@_N@Z`
- size: `288`
- prototype: `void(BinXmlTemplate *__hidden this, struct WriteBuffer *, bool)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18002f8a4`
- `0x180035a00`

## callees

- `0x180003780`
- `0x180003dc0`
- `0x180008b20`
- `0x18000a4b4`
- `0x18000b95c`
- `0x1800240ac`
- `0x18002e298`
- `0x180030454`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall BinXmlTemplate::Serialize(BinXmlTemplate *this, struct WriteBuffer *a2, char a3)
{
  __int64 v5; // rbx
  __int64 v6; // r8
  BinXmlTemplate *v7; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v8; // [rsp+48h] [rbp-B8h]
  __int128 v9; // [rsp+58h] [rbp-A8h]
  WriteBuffer *v10[6]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v11[64]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v12[224]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned int v13; // [rsp+1E0h] [rbp+E0h] BYREF

  LOBYTE(v13) = a3;
  WriteBuffer::Write(a2, (char *)this + 16, 0x10u);
  if ( *((_QWORD *)this + 4) == *((_QWORD *)this + 5) )
  {
    v13 = *((_DWORD *)this + 2);
    WriteBuffer::Write(a2, &v13, 4u);
    WriteBuffer::Write(a2, *(const void **)this, v13);
  }
  else
  {
    v5 = *((unsigned int *)a2 + 4);
    WriteBuffer::SetCurrentIndex(a2, v5 + 4);
    v8 = 0;
    v9 = 0;
    v7 = this;
    BinXmlReader::BinXmlReader(
      (BinXmlReader *)v12,
      (struct BinXmlReaderData *)&v7,
      v6,
      0,
      *((struct BinXmlStringTable **)this + 4),
      0);
    BinXmlWriter::BinXmlWriter((BinXmlWriter *)v10, 1, a2, *((struct BinXmlStringTable **)this + 5), 0, 0, 0);
    BinXmlReader::CopyInto((BinXmlReader *)v12, v10);
    *(_DWORD *)(v5 + *((_QWORD *)a2 + 1)) = *((_DWORD *)a2 + 4) - v5 - 4;
    utl::vector<tag_EvtRpcVariant,utl::allocator<tag_EvtRpcVariant>>::_Uninit(v11);
    BinXmlReader::~BinXmlReader((BinXmlReader *)v12);
  }
}

```

## disassembly

```asm
0x180030454  mov     byte ptr [rsp-8+arg_10], r8b
0x180030459  push    rbp
0x18003045a  push    rbx
0x18003045b  push    rsi
0x18003045c  push    rdi
0x18003045d  lea     rbp, [rsp-0A8h]
0x180030465  sub     rsp, 1A8h
0x18003046c  mov     rsi, rdx
0x18003046f  mov     rdi, rcx
0x180030472  lea     rdx, [rcx+10h]; void *
0x180030476  mov     r8d, 10h; unsigned int
0x18003047c  mov     rcx, rsi; this
0x18003047f  call    ?Write@WriteBuffer@@QEAAXQEBXK@Z; WriteBuffer::Write(void const * const,ulong)
0x180030484  mov     rax, [rdi+28h]
0x180030488  mov     rcx, rsi; this
0x18003048b  cmp     [rdi+20h], rax
0x18003048f  jz      loc_18003053B
0x180030495  mov     ebx, [rsi+10h]
0x180030498  lea     edx, [rbx+4]; unsigned int
0x18003049b  call    ?SetCurrentIndex@WriteBuffer@@QEAAXK@Z; WriteBuffer::SetCurrentIndex(ulong)
0x1800304a0  xorps   xmm0, xmm0
0x1800304a3  movdqu  [rsp+1C0h+var_178], xmm0
0x1800304a9  xorps   xmm1, xmm1
0x1800304ac  movdqu  [rsp+1C0h+var_168], xmm1
0x1800304b2  mov     [rsp+1C0h+var_180], rdi
0x1800304b7  mov     [rsp+1C0h+var_198], 0; struct BinXmlTemplateTable *
0x1800304c0  mov     rax, [rdi+20h]
0x1800304c4  mov     [rsp+1C0h+var_1A0], rax; struct BinXmlStringTable *
0x1800304c9  xor     r9d, r9d; struct AbstractPublishedEventRecord *
0x1800304cc  lea     rdx, [rsp+1C0h+var_180]; struct BinXmlReaderData *
0x1800304d1  lea     rcx, [rbp+0C0h+var_E0]; this
0x1800304d5  call    ??0BinXmlReader@@QEAA@PEAUBinXmlReaderData@@KPEAVAbstractPublishedEventRecord@@PEAVBinXmlStringTable@@PEAVBinXmlTemplateTable@@@Z; BinXmlReader::BinXmlReader(BinXmlReaderData *,ulong,AbstractPublishedEventRecord *,BinXmlStringTable *,BinXmlTemplateTable *)
0x1800304da  nop
0x1800304db  mov     [rsp+1C0h+var_190], 0; unsigned int
0x1800304e3  mov     [rsp+1C0h+var_198], 0; unsigned int *
0x1800304ec  mov     [rsp+1C0h+var_1A0], 0; struct BinXmlTemplateTable *
0x1800304f5  mov     r9, [rdi+28h]; struct BinXmlStringTable *
0x1800304f9  mov     r8, rsi; struct WriteBuffer *
0x1800304fc  mov     dl, 1; bool
0x1800304fe  lea     rcx, [rsp+1C0h+var_150]; this
0x180030503  call    ??0BinXmlWriter@@QEAA@_NAEAVWriteBuffer@@PEAVBinXmlStringTable@@PEAVBinXmlTemplateTable@@PEBKK@Z; BinXmlWriter::BinXmlWriter(bool,WriteBuffer &,BinXmlStringTable *,BinXmlTemplateTable *,ulong const *,ulong)
0x180030508  nop
0x180030509  lea     rdx, [rsp+1C0h+var_150]; struct BinXmlWriter *
0x18003050e  lea     rcx, [rbp+0C0h+var_E0]; this
0x180030512  call    ?CopyInto@BinXmlReader@@QEAAXAEAVBinXmlWriter@@@Z; BinXmlReader::CopyInto(BinXmlWriter &)
0x180030517  mov     ecx, [rsi+10h]
0x18003051a  sub     ecx, ebx
0x18003051c  sub     ecx, 4
0x18003051f  mov     rax, [rsi+8]
0x180030523  mov     [rbx+rax], ecx
0x180030526  lea     rcx, [rbp+0C0h+var_120]
0x18003052a  call    ?_Uninit@?$vector@Utag_EvtRpcVariant@@V?$allocator@Utag_EvtRpcVariant@@@utl@@@utl@@AEAAXXZ; utl::vector<tag_EvtRpcVariant,utl::allocator<tag_EvtRpcVariant>>::_Uninit(void)
0x18003052f  nop
0x180030530  lea     rcx, [rbp+0C0h+var_E0]; this
0x180030534  call    ??1BinXmlReader@@QEAA@XZ; BinXmlReader::~BinXmlReader(void)
0x180030539  jmp     short loc_180030568
0x18003053b  mov     eax, [rdi+8]
0x18003053e  mov     [rbp+0C0h+arg_10], eax
0x180030544  mov     r8d, 4; unsigned int
0x18003054a  lea     rdx, [rbp+0C0h+arg_10]; void *
0x180030551  call    ?Write@WriteBuffer@@QEAAXQEBXK@Z; WriteBuffer::Write(void const * const,ulong)
0x180030556  mov     r8d, [rbp+0C0h+arg_10]; unsigned int
0x18003055d  mov     rdx, [rdi]; void *
0x180030560  mov     rcx, rsi; this
0x180030563  call    ?Write@WriteBuffer@@QEAAXQEBXK@Z; WriteBuffer::Write(void const * const,ulong)
0x180030568  add     rsp, 1A8h
0x18003056f  pop     rdi
0x180030570  pop     rsi
0x180030571  pop     rbx
0x180030572  pop     rbp
0x180030573  retn
```
