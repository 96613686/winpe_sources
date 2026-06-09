# EvtIntWriteXmlEventToLocalLogfile

- ea: `0x180027570`
- end: `0x1800277e2`
- name: `EvtIntWriteXmlEventToLocalLogfile`
- size: `626`
- prototype: `__int64 __fastcall(__int64, __int64, int)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config`

## callees

- `0x180003a68`
- `0x180003dc0`
- `0x180006870`
- `0x180007aa0`
- `0x18000a2d0`
- `0x18000a4b4`
- `0x18000a558`
- `0x18000b95c`
- `0x1800108d0`
- `0x1800196a0`
- `0x180023548`
- `0x180027570`
- `0x18002e298`
- `0x18002ebac`
- `0x1800335f4`
- `0x180038fa4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800277c6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800277c6`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall EvtIntWriteXmlEventToLocalLogfile(__int64 a1, __int64 a2, int a3)
{
  void **v4; // rbx
  DWORD ReferencedObject; // edi
  __int64 v6; // rax
  unsigned int v7; // r8d
  __int128 v9; // [rsp+40h] [rbp-1E8h] BYREF
  __int128 pExceptionObject; // [rsp+50h] [rbp-1D8h] BYREF
  __int64 v11; // [rsp+60h] [rbp-1C8h]
  int v12; // [rsp+68h] [rbp-1C0h]
  int v13; // [rsp+6Ch] [rbp-1BCh]
  int v14; // [rsp+70h] [rbp-1B8h]
  _BYTE v15[8]; // [rsp+78h] [rbp-1B0h] BYREF
  __int64 v16; // [rsp+80h] [rbp-1A8h]
  unsigned int v17; // [rsp+88h] [rbp-1A0h]
  EvtException *v18; // [rsp+90h] [rbp-198h] BYREF
  _QWORD v19[3]; // [rsp+98h] [rbp-190h] BYREF
  __int128 v20; // [rsp+B0h] [rbp-178h]
  _BYTE v21[32]; // [rsp+C0h] [rbp-168h] BYREF
  _BYTE v22[48]; // [rsp+E0h] [rbp-148h] BYREF
  _BYTE v23[64]; // [rsp+110h] [rbp-118h] BYREF
  _BYTE v24[216]; // [rsp+150h] [rbp-D8h] BYREF
  void **v25; // [rsp+230h] [rbp+8h] BYREF
  void **v26; // [rsp+248h] [rbp+20h]

  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    if ( !a1 || !a2 || a3 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_50a4b5d3db573bd708b949f391e8ee2a_Traceguids, 87);
      }
      pExceptionObject = 0;
      v11 = 0;
      v12 = 87;
      v13 = -1;
      v14 = 329;
      throw (EvtException *)&pExceptionObject;
    }
    v4 = 0;
    v26 = 0;
    v25 = 0;
    ReferencedObject = ObjectTable::GetReferencedObject(a1, a1, &v25);
    if ( ReferencedObject )
      goto LABEL_11;
    v4 = v25;
    if ( *((_BYTE *)v25 + 28) == 17 )
    {
      v26 = v25;
      if ( v25 )
      {
        v25 = 0;
        ReferencedObject = 0;
LABEL_11:
        wmi::AutoRef<Object>::Release(&v25);
        if ( !ReferencedObject )
        {
          Buffer::Buffer((Buffer *)v21, 0, 0, 1);
          WriteBuffer::WriteBuffer((WriteBuffer *)v15, (struct BufferStream *)v21);
          BinXmlWriter::BinXmlWriter((BinXmlWriter *)v22, 0, (struct WriteBuffer *)v15, 0, 0, 0, 0);
          v6 = -1;
          do
            ++v6;
          while ( *(_WORD *)(a2 + 2 * v6) );
          *(_QWORD *)&v9 = a2;
          *((_QWORD *)&v9 + 1) = v6;
          BinXmlWriter::Parse((BinXmlWriter *)v22, &v9);
          v19[0] = 0;
          v20 = 0;
          v19[1] = v16;
          v19[2] = v17;
          v25 = &ZeroPublishedEventRecord::`vftable';
          BinXmlReader::BinXmlReader(
            (BinXmlReader *)v24,
            (struct BinXmlReaderData *)v19,
            v7,
            (struct AbstractPublishedEventRecord *)&v25,
            0,
            0);
          BinXmlReader::Reset((BinXmlReader *)v24);
          ReferencedObject = File::WriteRecord((File *)(v4 + 4), (struct BinXmlReader *)v24);
          BinXmlReader::~BinXmlReader((BinXmlReader *)v24);
          utl::vector<tag_EvtRpcVariant,utl::allocator<tag_EvtRpcVariant>>::_Uninit(v23);
          Buffer::~Buffer((Buffer *)v21);
        }
        if ( v4 )
          wmi::RefBase::Release((wmi::RefBase *)v4);
        goto LABEL_26;
      }
    }
    else
    {
      v4 = 0;
      v26 = 0;
    }
    ReferencedObject = 6;
    goto LABEL_11;
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &EvtException `RTTI Type Descriptor', &v18) )
    {
      LODWORD(v25) = *((_DWORD *)v18 + 6);
      ReferencedObject = (unsigned int)v25;
      __eh34_try_continuation(0, &EvtException `RTTI Type Descriptor', &loc_1800277BD);
    }
  }
LABEL_26:
  SetLastError(ReferencedObject);
  return ReferencedObject;
}

```

## disassembly

```asm
0x180027570  mov     rax, rsp
0x180027573  mov     [rax+10h], rbx
0x180027577  push    rsi
0x180027578  push    rdi
0x180027579  push    r14
0x18002757b  sub     rsp, 210h
0x180027582  mov     rsi, rdx
0x180027585  xor     r14d, r14d
0x180027588  test    rcx, rcx
0x18002758b  jz      loc_18002774D
0x180027591  test    rdx, rdx
0x180027594  jz      loc_18002774D
0x18002759a  test    r8d, r8d
0x18002759d  jnz     loc_18002774D
0x1800275a3  mov     ebx, r14d
0x1800275a6  mov     [rax+20h], rbx
0x1800275aa  mov     [rax+8], r14
0x1800275ae  lea     r8, [rax+8]
0x1800275b2  mov     rdx, rcx
0x1800275b5  call    ?GetReferencedObject@ObjectTable@@QEAAKPEAXAEAV?$AutoRef@VObject@@@wmi@@@Z; ObjectTable::GetReferencedObject(void *,wmi::AutoRef<Object> &)
0x1800275ba  mov     edi, eax
0x1800275bc  test    eax, eax
0x1800275be  jnz     short loc_1800275F8
0x1800275c0  mov     rbx, [rsp+228h+arg_0]
0x1800275c8  cmp     byte ptr [rbx+1Ch], 11h
0x1800275cc  jnz     short loc_1800275E8
0x1800275ce  mov     [rsp+228h+arg_18], rbx
0x1800275d6  test    rbx, rbx
0x1800275d9  jz      short loc_1800275F3
0x1800275db  mov     [rsp+228h+arg_0], r14
0x1800275e3  mov     edi, r14d
0x1800275e6  jmp     short loc_1800275F8
0x1800275e8  mov     rbx, r14
0x1800275eb  mov     [rsp+228h+arg_18], rbx
0x1800275f3  mov     edi, 6
0x1800275f8  lea     rcx, [rsp+228h+arg_0]; void *
0x180027600  call    ?Release@?$AutoRef@VObject@@@wmi@@QEAAXXZ; wmi::AutoRef<Object>::Release(void)
0x180027605  test    edi, edi
0x180027607  jnz     loc_18002773D
0x18002760d  mov     r9b, 1; bool
0x180027610  xor     r8d, r8d; unsigned int
0x180027613  xor     edx, edx; unsigned __int8 *
0x180027615  lea     rcx, [rsp+228h+var_168]; this
0x18002761d  call    ??0Buffer@@QEAA@PEBEK_N@Z; Buffer::Buffer(uchar const *,ulong,bool)
0x180027622  nop
0x180027623  lea     rdx, [rsp+228h+var_168]; struct BufferStream *
0x18002762b  lea     rcx, [rsp+228h+var_1B0]; this
0x180027630  call    ??0WriteBuffer@@QEAA@AEAVBufferStream@@@Z; WriteBuffer::WriteBuffer(BufferStream &)
0x180027635  mov     [rsp+228h+var_1F8], r14d; unsigned int
0x18002763a  mov     [rsp+228h+var_200], r14; unsigned int *
0x18002763f  mov     [rsp+228h+var_208], r14; struct BinXmlTemplateTable *
0x180027644  xor     r9d, r9d; struct BinXmlStringTable *
0x180027647  lea     r8, [rsp+228h+var_1B0]; struct WriteBuffer *
0x18002764c  xor     edx, edx; bool
0x18002764e  lea     rcx, [rsp+228h+var_148]; this
0x180027656  call    ??0BinXmlWriter@@QEAA@_NAEAVWriteBuffer@@PEAVBinXmlStringTable@@PEAVBinXmlTemplateTable@@PEBKK@Z; BinXmlWriter::BinXmlWriter(bool,WriteBuffer &,BinXmlStringTable *,BinXmlTemplateTable *,ulong const *,ulong)
0x18002765b  nop
0x18002765c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180027660  inc     rax
0x180027663  cmp     [rsi+rax*2], r14w
0x180027668  jnz     short loc_180027660
0x18002766a  mov     [rsp+228h+var_1E8], rsi
0x18002766f  mov     [rsp+228h+var_1E0], rax
0x180027674  xor     r8d, r8d
0x180027677  lea     rdx, [rsp+228h+var_1E8]
0x18002767c  lea     rcx, [rsp+228h+var_148]; this
0x180027684  call    ?Parse@BinXmlWriter@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@_N@Z; BinXmlWriter::Parse(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,bool)
0x180027689  mov     [rsp+228h+var_190], r14
0x180027691  xorps   xmm0, xmm0
0x180027694  movdqu  [rsp+228h+var_178], xmm0
0x18002769d  mov     rax, [rsp+228h+var_1A8]
0x1800276a5  mov     [rsp+228h+var_188], rax
0x1800276ad  mov     eax, [rsp+228h+var_1A0]
0x1800276b4  mov     [rsp+228h+var_180], rax
0x1800276bc  lea     rax, ??_7ZeroPublishedEventRecord@@6B@; const ZeroPublishedEventRecord::`vftable'
0x1800276c3  mov     [rsp+228h+arg_0], rax
0x1800276cb  mov     [rsp+228h+var_200], r14; struct BinXmlTemplateTable *
0x1800276d0  mov     [rsp+228h+var_208], r14; struct BinXmlStringTable *
0x1800276d5  lea     r9, [rsp+228h+arg_0]; struct AbstractPublishedEventRecord *
0x1800276dd  lea     rdx, [rsp+228h+var_190]; struct BinXmlReaderData *
0x1800276e5  lea     rcx, [rsp+228h+var_D8]; this
0x1800276ed  call    ??0BinXmlReader@@QEAA@PEAUBinXmlReaderData@@KPEAVAbstractPublishedEventRecord@@PEAVBinXmlStringTable@@PEAVBinXmlTemplateTable@@@Z; BinXmlReader::BinXmlReader(BinXmlReaderData *,ulong,AbstractPublishedEventRecord *,BinXmlStringTable *,BinXmlTemplateTable *)
0x1800276f2  nop
0x1800276f3  lea     rcx, [rsp+228h+var_D8]; this
0x1800276fb  call    ?Reset@BinXmlReader@@QEAAXXZ; BinXmlReader::Reset(void)
0x180027700  lea     rcx, [rbx+20h]; this
0x180027704  lea     rdx, [rsp+228h+var_D8]; struct BinXmlReader *
0x18002770c  call    ?WriteRecord@File@@QEAAKAEAVBinXmlReader@@@Z; File::WriteRecord(BinXmlReader &)
0x180027711  mov     edi, eax
0x180027713  lea     rcx, [rsp+228h+var_D8]; this
0x18002771b  call    ??1BinXmlReader@@QEAA@XZ; BinXmlReader::~BinXmlReader(void)
0x180027720  nop
0x180027721  lea     rcx, [rsp+228h+var_118]
0x180027729  call    ?_Uninit@?$vector@Utag_EvtRpcVariant@@V?$allocator@Utag_EvtRpcVariant@@@utl@@@utl@@AEAAXXZ; utl::vector<tag_EvtRpcVariant,utl::allocator<tag_EvtRpcVariant>>::_Uninit(void)
0x18002772e  nop
0x18002772f  lea     rcx, [rsp+228h+var_168]; this
0x180027737  call    ??1Buffer@@UEAA@XZ; Buffer::~Buffer(void)
0x18002773c  nop
0x18002773d  test    rbx, rbx
0x180027740  jz      short loc_18002774B
0x180027742  mov     rcx, rbx; this
0x180027745  call    ?Release@RefBase@wmi@@QEAAKXZ; wmi::RefBase::Release(void)
0x18002774a  nop
0x18002774b  jmp     short loc_1800277C4
0x18002774d  lea     rax, WPP_GLOBAL_Control
0x180027754  mov     rcx, cs:WPP_GLOBAL_Control
0x18002775b  cmp     rcx, rax
0x18002775e  jz      short loc_180027785
0x180027760  test    byte ptr [rcx+1Ch], 1
0x180027764  jz      short loc_180027785
0x180027766  cmp     byte ptr [rcx+19h], 2
0x18002776a  jb      short loc_180027785
0x18002776c  mov     edx, 0Eh
0x180027771  lea     r9d, [rdx+49h]
0x180027775  lea     r8, WPP_50a4b5d3db573bd708b949f391e8ee2a_Traceguids
0x18002777c  mov     rcx, [rcx+10h]
0x180027780  call    WPP_SF_D
0x180027785  xorps   xmm0, xmm0
0x180027788  movdqu  [rsp+228h+pExceptionObject], xmm0
0x18002778e  mov     [rsp+228h+var_1C8], r14
0x180027793  mov     [rsp+228h+var_1C0], 57h ; 'W'
0x18002779b  mov     [rsp+228h+var_1BC], 0FFFFFFFFh
0x1800277a3  mov     [rsp+228h+var_1B8], 149h
0x1800277ab  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800277b2  lea     rcx, [rsp+228h+pExceptionObject]; pExceptionObject
0x1800277b7  call    _CxxThrowException_0
0x1800277bd  mov     edi, dword ptr [rsp+228h+arg_0]
0x1800277c4  mov     ecx, edi; dwErrCode
0x1800277c6  call    cs:__imp_SetLastError
0x1800277cc  mov     eax, edi
0x1800277ce  mov     rbx, [rsp+228h+arg_8]
0x1800277d6  add     rsp, 210h
0x1800277dd  pop     r14
0x1800277df  pop     rdi
0x1800277e0  pop     rsi
0x1800277e1  retn
```
