# LocalePublisherTable::Open(RecordCache *,LocaleMessageTable *,bool)

- ea: `0x180038354`
- end: `0x1800384e2`
- name: `?Open@LocalePublisherTable@@QEAAXPEAVRecordCache@@PEAVLocaleMessageTable@@_N@Z`
- size: `398`
- prototype: `void(LocalePublisherTable *__hidden this, struct RecordCache *, struct LocaleMessageTable *, bool)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180036688`

## callees

- `0x180003ed0`
- `0x180009d80`
- `0x18000a2d0`
- `0x18000a558`
- `0x180023548`
- `0x180036db0`
- `0x1800377a8`
- `0x180038354`
- `0x180038fa4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall LocalePublisherTable::Open(
        LocalePublisherTable *this,
        struct RecordCache *a2,
        struct LocaleMessageTable *a3,
        char a4)
{
  _BYTE v7[32]; // [rsp+20h] [rbp-58h] BYREF
  __int128 pExceptionObject; // [rsp+40h] [rbp-38h] BYREF
  __int64 v9; // [rsp+50h] [rbp-28h]
  int v10; // [rsp+58h] [rbp-20h]
  int v11; // [rsp+5Ch] [rbp-1Ch]
  int v12; // [rsp+60h] [rbp-18h]
  unsigned int v13; // [rsp+B8h] [rbp+40h] BYREF

  LOBYTE(v13) = a4;
  Buffer::Buffer((Buffer *)v7, 0, 0, 1);
  v13 = 0;
  *((_QWORD *)this + 44) = a2;
  *((_QWORD *)this + 45) = a3;
  if ( !RecordCache::GetRecord(a2, 0, (struct Buffer *)v7, &v13) )
  {
    if ( !v13 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids, 1168);
      }
      pExceptionObject = 0;
      v9 = 0;
      v10 = 1168;
      v11 = -1;
      v12 = 1038;
      throw (EvtException *)&pExceptionObject;
    }
    Buffer::SetSize((Buffer *)v7, v13);
    if ( !RecordCache::GetRecord(*((RecordCache **)this + 44), 0, (struct Buffer *)v7, &v13) )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids, 1168);
      }
      pExceptionObject = 0;
      v9 = 0;
      v10 = 1168;
      v11 = -1;
      v12 = 1047;
      throw (EvtException *)&pExceptionObject;
    }
  }
  Buffer::SetCurrentIndex((Buffer *)v7, 0);
  LocalePublisherTable::_PublisherRecord::Deserialize((LocalePublisherTable *)((char *)this + 160), (struct Buffer *)v7);
  Buffer::~Buffer((Buffer *)v7);
}

```

## disassembly

```asm
0x180038354  mov     byte ptr [rsp-20h+arg_18], r9b
0x180038359  push    rbp
0x18003835a  push    rbx
0x18003835b  push    rsi
0x18003835c  push    rdi
0x18003835d  mov     rbp, rsp
0x180038360  sub     rsp, 78h
0x180038364  mov     rbx, r8
0x180038367  mov     rdi, rdx
0x18003836a  mov     rsi, rcx
0x18003836d  mov     r9b, 1; bool
0x180038370  xor     r8d, r8d; unsigned int
0x180038373  xor     edx, edx; unsigned __int8 *
0x180038375  lea     rcx, [rbp+var_58]; this
0x180038379  call    ??0Buffer@@QEAA@PEBEK_N@Z; Buffer::Buffer(uchar const *,ulong,bool)
0x18003837e  nop
0x18003837f  mov     [rbp+arg_18], 0
0x180038386  mov     [rsi+160h], rdi
0x18003838d  mov     [rsi+168h], rbx
0x180038394  lea     r9, [rbp+arg_18]; unsigned int *
0x180038398  lea     r8, [rbp+var_58]; struct Buffer *
0x18003839c  xor     edx, edx; unsigned int
0x18003839e  mov     rcx, rdi; this
0x1800383a1  call    ?GetRecord@RecordCache@@QEAA_NKAEAVBuffer@@AEAK@Z; RecordCache::GetRecord(ulong,Buffer &,ulong &)
0x1800383a6  test    al, al
0x1800383a8  jnz     loc_1800384B4
0x1800383ae  mov     edx, [rbp+arg_18]; unsigned int
0x1800383b1  test    edx, edx
0x1800383b3  jnz     short loc_180038423
0x1800383b5  lea     rax, WPP_GLOBAL_Control
0x1800383bc  mov     ebx, 490h
0x1800383c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800383c8  cmp     rcx, rax
0x1800383cb  jz      short loc_1800383F1
0x1800383cd  test    byte ptr [rcx+1Ch], 1
0x1800383d1  jz      short loc_1800383F1
0x1800383d3  cmp     byte ptr [rcx+19h], 2
0x1800383d7  jb      short loc_1800383F1
0x1800383d9  mov     edx, 2Fh ; '/'
0x1800383de  mov     r9d, ebx
0x1800383e1  lea     r8, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids
0x1800383e8  mov     rcx, [rcx+10h]
0x1800383ec  call    WPP_SF_D
0x1800383f1  xorps   xmm0, xmm0
0x1800383f4  movdqu  [rbp+pExceptionObject], xmm0
0x1800383f9  mov     [rbp+var_28], 0
0x180038401  mov     [rbp+var_20], ebx
0x180038404  mov     [rbp+var_1C], 0FFFFFFFFh
0x18003840b  mov     [rbp+var_18], 40Eh
0x180038412  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180038419  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18003841d  call    _CxxThrowException_0
0x180038423  lea     rcx, [rbp+var_58]; this
0x180038427  call    ?SetSize@Buffer@@QEAAXK@Z; Buffer::SetSize(ulong)
0x18003842c  lea     r9, [rbp+arg_18]; unsigned int *
0x180038430  lea     r8, [rbp+var_58]; struct Buffer *
0x180038434  xor     edx, edx; unsigned int
0x180038436  mov     rcx, [rsi+160h]; this
0x18003843d  call    ?GetRecord@RecordCache@@QEAA_NKAEAVBuffer@@AEAK@Z; RecordCache::GetRecord(ulong,Buffer &,ulong &)
0x180038442  test    al, al
0x180038444  jnz     short loc_1800384B4
0x180038446  lea     rax, WPP_GLOBAL_Control
0x18003844d  mov     ebx, 490h
0x180038452  mov     rcx, cs:WPP_GLOBAL_Control
0x180038459  cmp     rcx, rax
0x18003845c  jz      short loc_180038482
0x18003845e  test    byte ptr [rcx+1Ch], 1
0x180038462  jz      short loc_180038482
0x180038464  cmp     byte ptr [rcx+19h], 2
0x180038468  jb      short loc_180038482
0x18003846a  mov     edx, 30h ; '0'
0x18003846f  mov     r9d, ebx
0x180038472  lea     r8, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids
0x180038479  mov     rcx, [rcx+10h]
0x18003847d  call    WPP_SF_D
0x180038482  xorps   xmm0, xmm0
0x180038485  movdqu  [rbp+pExceptionObject], xmm0
0x18003848a  mov     [rbp+var_28], 0
0x180038492  mov     [rbp+var_20], ebx
0x180038495  mov     [rbp+var_1C], 0FFFFFFFFh
0x18003849c  mov     [rbp+var_18], 417h
0x1800384a3  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800384aa  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800384ae  call    _CxxThrowException_0
0x1800384b4  xor     edx, edx; unsigned int
0x1800384b6  lea     rcx, [rbp+var_58]; this
0x1800384ba  call    ?SetCurrentIndex@Buffer@@UEAAXK@Z; Buffer::SetCurrentIndex(ulong)
0x1800384bf  lea     rcx, [rsi+0A0h]; this
0x1800384c6  lea     rdx, [rbp+var_58]; struct Buffer *
0x1800384ca  call    ?Deserialize@_PublisherRecord@LocalePublisherTable@@QEAAXAEAVBuffer@@@Z; LocalePublisherTable::_PublisherRecord::Deserialize(Buffer &)
0x1800384cf  nop
0x1800384d0  lea     rcx, [rbp+var_58]; this
0x1800384d4  call    ??1Buffer@@UEAA@XZ; Buffer::~Buffer(void)
0x1800384d9  add     rsp, 78h
0x1800384dd  pop     rdi
0x1800384de  pop     rsi
0x1800384df  pop     rbx
0x1800384e0  pop     rbp
0x1800384e1  retn
```
