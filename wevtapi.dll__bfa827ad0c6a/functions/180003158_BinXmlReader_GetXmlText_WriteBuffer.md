# BinXmlReader::GetXmlText(WriteBuffer &)

- ea: `0x180003158`
- end: `0x1800031ea`
- name: `?GetXmlText@BinXmlReader@@QEAAXAEAVWriteBuffer@@@Z`
- size: `146`
- prototype: `void __fastcall(BinXmlReader *__hidden this, struct WriteBuffer *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x180001568`
- `0x180026e90`

## callees

- `0x1800017cc`
- `0x1800017e8`
- `0x180003158`
- `0x1800031f0`
- `0x180003a68`
- `0x180004070`
- `0x18000a100`

## pseudocode

```c
void __fastcall BinXmlReader::GetXmlText(BinXmlReader *this, struct WriteBuffer *a2)
{
  __int64 v3; // rdx
  __int64 v4; // [rsp+20h] [rbp-30h] BYREF
  int v5; // [rsp+28h] [rbp-28h]
  __int64 v6; // [rsp+2Ch] [rbp-24h]
  char v7; // [rsp+34h] [rbp-1Ch]
  void *v8[3]; // [rsp+38h] [rbp-18h] BYREF

  v4 = 0;
  v5 = -1;
  v6 = 0;
  v7 = 0;
  BinXmlReader::Reset(this);
  utl::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>(
    v8,
    v3);
  utl::vector<wchar_t const *,utl::allocator<wchar_t const *>>::reserve(v8);
  do
  {
    BinXmlReader::NextToken(this, (struct BinXmlToken *)&v4, 1);
    BinXmlReader::WriteTokenText(this, (struct BinXmlToken *)&v4);
  }
  while ( HIDWORD(v6) );
  if ( v8[0] != (void *)-1LL )
    operator delete(v8[0]);
}

```

## disassembly

```asm
0x180003158  mov     [rsp-8+arg_0], rbx
0x18000315d  mov     [rsp-8+arg_8], rdi
0x180003162  push    rbp
0x180003163  mov     rbp, rsp
0x180003166  sub     rsp, 50h
0x18000316a  mov     rdi, rdx
0x18000316d  mov     rbx, rcx
0x180003170  mov     [rbp+var_30], 0
0x180003178  mov     [rbp+var_28], 0FFFFFFFFh
0x18000317f  mov     [rbp+var_24], 0
0x180003187  mov     [rbp+var_1C], 0
0x18000318b  call    ?Reset@BinXmlReader@@QEAAXXZ; BinXmlReader::Reset(void)
0x180003190  lea     rcx, [rbp+var_18]
0x180003194  call    ??0?$vector@UTmplInstInfo@BinXmlReader@@V?$allocator@UTmplInstInfo@BinXmlReader@@@utl@@@utl@@QEAA@XZ; utl::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>(void)
0x180003199  nop
0x18000319a  lea     rcx, [rbp+var_18]
0x18000319e  call    ?reserve@?$vector@PEB_WV?$allocator@PEB_W@utl@@@utl@@QEAA_N_K@Z; utl::vector<wchar_t const *,utl::allocator<wchar_t const *>>::reserve(unsigned __int64)
0x1800031a3  mov     r8b, 1; bool
0x1800031a6  lea     rdx, [rbp+var_30]; struct BinXmlToken *
0x1800031aa  mov     rcx, rbx; this
0x1800031ad  call    ?NextToken@BinXmlReader@@QEAAXAEAUBinXmlToken@@_N@Z; BinXmlReader::NextToken(BinXmlToken &,bool)
0x1800031b2  mov     r9, rdi
0x1800031b5  lea     r8, [rbp+var_18]
0x1800031b9  lea     rdx, [rbp+var_30]
0x1800031bd  mov     rcx, rbx
0x1800031c0  call    ?WriteTokenText@BinXmlReader@@AEAAXAEAUBinXmlToken@@AEAV?$vector@PEB_WV?$allocator@PEB_W@utl@@@utl@@AEAVWriteBuffer@@@Z; BinXmlReader::WriteTokenText(BinXmlToken &,utl::vector<wchar_t const *,utl::allocator<wchar_t const *>> &,WriteBuffer &)
0x1800031c5  cmp     dword ptr [rbp+var_24+4], 0
0x1800031c9  jnz     short loc_1800031A3
0x1800031cb  mov     rcx, [rbp+var_18]; void *
0x1800031cf  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800031d3  jz      short loc_1800031DA
0x1800031d5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800031da  mov     rbx, [rsp+50h+arg_0]
0x1800031df  mov     rdi, [rsp+50h+arg_8]
0x1800031e4  add     rsp, 50h
0x1800031e8  pop     rbp
0x1800031e9  retn
```
