# CreateBinXMLFromCustomXML(ulong,wchar_t const *,ulong,ulong const *,ulong,int,uchar *,ulong *,_GUID *)

- ea: `0x18002e094`
- end: `0x18002e290`
- name: `?CreateBinXMLFromCustomXML@@YAKKPEB_WKPEBKKHPEAEPEAKPEAU_GUID@@@Z`
- size: `508`
- prototype: `__int64 __fastcall(unsigned int, const wchar_t *, unsigned int, const unsigned int *, unsigned int, int, unsigned __int8 *, unsigned int *, struct _GUID *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x1800268c0`

## callees

- `0x180003ed0`
- `0x180007180`
- `0x180009d80`
- `0x18000a2d0`
- `0x18000a4b4`
- `0x18000a558`
- `0x18000bb4c`
- `0x1800196a0`
- `0x18002e094`
- `0x18002e298`
- `0x18002ebac`
- `0x180030c74`
- `0x180038fbc`
- `0x18003c010`

## pseudocode

```c
__int64 __fastcall CreateBinXMLFromCustomXML(
        unsigned int a1,
        const wchar_t *a2,
        unsigned int a3,
        const unsigned int *a4,
        unsigned int a5,
        int a6,
        unsigned __int8 *a7,
        unsigned int *a8,
        struct _GUID *a9)
{
  __int64 v10; // r15
  __int64 v12; // r14
  unsigned __int8 *v13; // rsi
  unsigned int *v14; // rdi
  size_t v15; // rax
  __int64 result; // rax
  size_t v17; // rdi
  unsigned __int8 *v18; // rax
  unsigned __int8 *v19; // rbx
  _BYTE v20[8]; // [rsp+40h] [rbp-F8h] BYREF
  void *Src; // [rsp+48h] [rbp-F0h]
  size_t Size; // [rsp+50h] [rbp-E8h]
  const wchar_t *v23; // [rsp+60h] [rbp-D8h]
  __int64 v24; // [rsp+68h] [rbp-D0h]
  _QWORD v25[2]; // [rsp+70h] [rbp-C8h] BYREF
  unsigned int v26; // [rsp+80h] [rbp-B8h]
  EvtException *v27; // [rsp+88h] [rbp-B0h] BYREF
  _BYTE v28[48]; // [rsp+90h] [rbp-A8h] BYREF
  _BYTE v29[120]; // [rsp+C0h] [rbp-78h] BYREF

  try
  {
    v10 = a3;
    v12 = a1;
    v13 = a7;
    if ( a7 )
    {
      if ( a5 )
      {
LABEL_4:
        v14 = a8;
        *a8 = 0;
        Buffer::Buffer((Buffer *)v20, 0, 0, 1);
        Buffer::SetSize((Buffer *)v20, 0x2800u);
        Buffer::SetCurrentIndex((Buffer *)v20, 0);
        WriteBuffer::WriteBuffer((WriteBuffer *)v25, (struct BufferStream *)v20);
        BinXmlWriter::BinXmlWriter((BinXmlWriter *)v28, 1, (struct WriteBuffer *)v25, 0, 0, a4, v10);
        v23 = a2;
        v24 = v12;
        BinXmlWriter::Parse((BinXmlWriter *)v28);
        (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v25[0] + 32LL))(v25[0], v26);
        v15 = (unsigned int)Size;
        *v14 = Size;
        if ( (unsigned int)v15 <= a5 )
        {
          memcpy_0(v13, Src, v15);
          v17 = 2 * v12;
          v18 = (unsigned __int8 *)MIDL_user_allocate(4 * v10 + 2 * v12);
          v19 = v18;
          a7 = v18;
          if ( v18 )
          {
            memcpy_0(v18, a2, v17);
            memcpy_0(&v19[v17], a4, 4 * v10);
            Sha256HashToGuid(v19, 4 * v10 + v17, a9);
            tlx::_FreeFixedLocal::~_FreeFixedLocal((tlx::_FreeFixedLocal *)&a7);
            utl::vector<tag_EvtRpcVariant,utl::allocator<tag_EvtRpcVariant>>::_Uninit(v29);
            Buffer::~Buffer((Buffer *)v20);
            return 0;
          }
          else
          {
            tlx::_FreeFixedLocal::~_FreeFixedLocal((tlx::_FreeFixedLocal *)&a7);
            utl::vector<tag_EvtRpcVariant,utl::allocator<tag_EvtRpcVariant>>::_Uninit(v29);
            Buffer::~Buffer((Buffer *)v20);
            return 14;
          }
        }
        else
        {
          utl::vector<tag_EvtRpcVariant,utl::allocator<tag_EvtRpcVariant>>::_Uninit(v29);
          Buffer::~Buffer((Buffer *)v20);
          return 122;
        }
      }
    }
    else if ( !a5 )
    {
      goto LABEL_4;
    }
    result = 87;
  }
  catch ( EvtException *v27 )
  {
    return *((unsigned int *)v27 + 6);
  }
  v10 = a3;
}

```

## disassembly

```asm
0x18002e094  push    rbx
0x18002e096  push    rsi
0x18002e097  push    rdi
0x18002e098  push    r12
0x18002e09a  push    r13
0x18002e09c  push    r14
0x18002e09e  push    r15
0x18002e0a0  sub     rsp, 100h
0x18002e0a7  mov     r12, r9
0x18002e0aa  mov     r15d, r8d
0x18002e0ad  mov     r13, rdx
0x18002e0b0  mov     r14d, ecx
0x18002e0b3  mov     rsi, [rsp+138h+arg_30]
0x18002e0bb  mov     ebx, [rsp+138h+arg_20]
0x18002e0c2  test    rsi, rsi
0x18002e0c5  jnz     loc_18002E267
0x18002e0cb  test    ebx, ebx
0x18002e0cd  jnz     loc_18002E26F
0x18002e0d3  mov     rdi, [rsp+138h+arg_38]
0x18002e0db  mov     dword ptr [rdi], 0
0x18002e0e1  mov     r9b, 1; bool
0x18002e0e4  xor     r8d, r8d; unsigned int
0x18002e0e7  xor     edx, edx; unsigned __int8 *
0x18002e0e9  lea     rcx, [rsp+138h+var_F8]; this
0x18002e0ee  call    ??0Buffer@@QEAA@PEBEK_N@Z; Buffer::Buffer(uchar const *,ulong,bool)
0x18002e0f3  nop
0x18002e0f4  mov     edx, 2800h; unsigned int
0x18002e0f9  lea     rcx, [rsp+138h+var_F8]; this
0x18002e0fe  call    ?SetSize@Buffer@@QEAAXK@Z; Buffer::SetSize(ulong)
0x18002e103  xor     edx, edx; unsigned int
0x18002e105  lea     rcx, [rsp+138h+var_F8]; this
0x18002e10a  call    ?SetCurrentIndex@Buffer@@UEAAXK@Z; Buffer::SetCurrentIndex(ulong)
0x18002e10f  lea     rdx, [rsp+138h+var_F8]; struct BufferStream *
0x18002e114  lea     rcx, [rsp+138h+var_C8]; this
0x18002e119  call    ??0WriteBuffer@@QEAA@AEAVBufferStream@@@Z; WriteBuffer::WriteBuffer(BufferStream &)
0x18002e11e  mov     [rsp+138h+var_108], r15d; unsigned int
0x18002e123  mov     [rsp+138h+var_110], r12; unsigned int *
0x18002e128  mov     [rsp+138h+var_118], 0; struct BinXmlTemplateTable *
0x18002e131  xor     r9d, r9d; struct BinXmlStringTable *
0x18002e134  lea     r8, [rsp+138h+var_C8]; struct WriteBuffer *
0x18002e139  mov     dl, 1; bool
0x18002e13b  lea     rcx, [rsp+138h+var_A8]; this
0x18002e143  call    ??0BinXmlWriter@@QEAA@_NAEAVWriteBuffer@@PEAVBinXmlStringTable@@PEAVBinXmlTemplateTable@@PEBKK@Z; BinXmlWriter::BinXmlWriter(bool,WriteBuffer &,BinXmlStringTable *,BinXmlTemplateTable *,ulong const *,ulong)
0x18002e148  nop
0x18002e149  mov     [rsp+138h+var_D8], r13
0x18002e14e  mov     [rsp+138h+var_D0], r14
0x18002e153  xor     r8d, r8d
0x18002e156  lea     rdx, [rsp+138h+var_D8]
0x18002e15b  lea     rcx, [rsp+138h+var_A8]; this
0x18002e163  call    ?Parse@BinXmlWriter@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@_N@Z; BinXmlWriter::Parse(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,bool)
0x18002e168  mov     rcx, [rsp+138h+var_C8]
0x18002e16d  mov     rax, [rcx]
0x18002e170  mov     edx, [rsp+138h+var_B8]
0x18002e177  mov     rax, [rax+20h]
0x18002e17b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e180  mov     eax, dword ptr [rsp+138h+Size]
0x18002e184  mov     [rdi], eax
0x18002e186  cmp     eax, ebx
0x18002e188  jbe     short loc_18002E1AC
0x18002e18a  lea     rcx, [rsp+138h+var_78]
0x18002e192  call    ?_Uninit@?$vector@Utag_EvtRpcVariant@@V?$allocator@Utag_EvtRpcVariant@@@utl@@@utl@@AEAAXXZ; utl::vector<tag_EvtRpcVariant,utl::allocator<tag_EvtRpcVariant>>::_Uninit(void)
0x18002e197  nop
0x18002e198  lea     rcx, [rsp+138h+var_F8]; this
0x18002e19d  call    ??1Buffer@@UEAA@XZ; Buffer::~Buffer(void)
0x18002e1a2  mov     eax, 7Ah ; 'z'
0x18002e1a7  jmp     loc_18002E27D
0x18002e1ac  mov     r8, rax; Size
0x18002e1af  mov     rdx, [rsp+138h+Src]; Src
0x18002e1b4  mov     rcx, rsi; void *
0x18002e1b7  call    memcpy_0
0x18002e1bc  lea     rdi, [r14+r14]
0x18002e1c0  lea     rsi, ds:0[r15*4]
0x18002e1c8  lea     rcx, [rsi+rdi]; size
0x18002e1cc  call    MIDL_user_allocate
0x18002e1d1  mov     rbx, rax
0x18002e1d4  mov     [rsp+138h+arg_30], rax
0x18002e1dc  test    rax, rax
0x18002e1df  jnz     short loc_18002E20C
0x18002e1e1  lea     rcx, [rsp+138h+arg_30]; this
0x18002e1e9  call    ??1_FreeFixedLocal@tlx@@QEAA@XZ; tlx::_FreeFixedLocal::~_FreeFixedLocal(void)
0x18002e1ee  nop
0x18002e1ef  lea     rcx, [rsp+138h+var_78]
0x18002e1f7  call    ?_Uninit@?$vector@Utag_EvtRpcVariant@@V?$allocator@Utag_EvtRpcVariant@@@utl@@@utl@@AEAAXXZ; utl::vector<tag_EvtRpcVariant,utl::allocator<tag_EvtRpcVariant>>::_Uninit(void)
0x18002e1fc  nop
0x18002e1fd  lea     rcx, [rsp+138h+var_F8]; this
0x18002e202  call    ??1Buffer@@UEAA@XZ; Buffer::~Buffer(void)
0x18002e207  lea     eax, [rbx+0Eh]
0x18002e20a  jmp     short loc_18002E27D
0x18002e20c  mov     r8, rdi; Size
0x18002e20f  mov     rdx, r13; Src
0x18002e212  mov     rcx, rbx; void *
0x18002e215  call    memcpy_0
0x18002e21a  lea     rcx, [rdi+rbx]; void *
0x18002e21e  mov     r8, rsi; Size
0x18002e221  mov     rdx, r12; Src
0x18002e224  call    memcpy_0
0x18002e229  lea     edx, [rsi+rdi]; unsigned int
0x18002e22c  mov     r8, [rsp+138h+arg_40]; struct _GUID *
0x18002e234  mov     rcx, rbx; unsigned __int8 *
0x18002e237  call    ?Sha256HashToGuid@@YAJPEAEKPEAU_GUID@@@Z; Sha256HashToGuid(uchar *,ulong,_GUID *)
0x18002e23c  lea     rcx, [rsp+138h+arg_30]; this
0x18002e244  call    ??1_FreeFixedLocal@tlx@@QEAA@XZ; tlx::_FreeFixedLocal::~_FreeFixedLocal(void)
0x18002e249  nop
0x18002e24a  lea     rcx, [rsp+138h+var_78]
0x18002e252  call    ?_Uninit@?$vector@Utag_EvtRpcVariant@@V?$allocator@Utag_EvtRpcVariant@@@utl@@@utl@@AEAAXXZ; utl::vector<tag_EvtRpcVariant,utl::allocator<tag_EvtRpcVariant>>::_Uninit(void)
0x18002e257  nop
0x18002e258  lea     rcx, [rsp+138h+var_F8]; this
0x18002e25d  call    ??1Buffer@@UEAA@XZ; Buffer::~Buffer(void)
0x18002e262  nop
0x18002e263  xor     eax, eax
0x18002e265  jmp     short loc_18002E27D
0x18002e267  test    ebx, ebx
0x18002e269  jnz     loc_18002E0D3
0x18002e26f  mov     eax, 57h ; 'W'
0x18002e274  jmp     short loc_18002E27D
0x18002e276  mov     eax, [rsp+138h+arg_28]
0x18002e27d  add     rsp, 100h
0x18002e284  pop     r15
0x18002e286  pop     r14
0x18002e288  pop     r13
0x18002e28a  pop     r12
0x18002e28c  pop     rdi
0x18002e28d  pop     rsi
0x18002e28e  pop     rbx
0x18002e28f  retn
```
