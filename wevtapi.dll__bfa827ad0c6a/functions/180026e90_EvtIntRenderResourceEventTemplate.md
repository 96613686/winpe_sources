# EvtIntRenderResourceEventTemplate

- ea: `0x180026e90`
- end: `0x1800273d5`
- name: `EvtIntRenderResourceEventTemplate`
- size: `1349`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, unsigned int, int, int, unsigned __int8 *, _DWORD *)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180003158`
- `0x180003dc0`
- `0x18000a2d0`
- `0x18000a4b4`
- `0x18000a558`
- `0x18000b95c`
- `0x180012cb0`
- `0x1800196a0`
- `0x180023548`
- `0x1800243e4`
- `0x180024a50`
- `0x180026e90`
- `0x18002e298`
- `0x18002f384`
- `0x18002f4b0`
- `0x180038fa4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800270aa`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002715b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800270aa`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002715b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall EvtIntRenderResourceEventTemplate(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        unsigned int a4,
        int a5,
        int a6,
        unsigned __int8 *a7,
        _DWORD *a8)
{
  unsigned int v8; // esi
  __int64 v9; // rbx
  BinXmlTmplInstWriter *started; // rdi
  unsigned int i; // r15d
  __m128i v12; // xmm1
  __int64 v13; // rax
  __int64 v14; // rax
  unsigned int v15; // edi
  unsigned __int32 j; // esi
  _BYTE *v17; // rdx
  __int64 v18; // r8
  DWORD LengthSid; // eax
  _WORD *v20; // rdx
  __int64 v21; // r8
  unsigned int v22; // r8d
  __int64 result; // rax
  __m128i v24; // [rsp+48h] [rbp-3D0h] BYREF
  unsigned int v25; // [rsp+58h] [rbp-3C0h]
  __int64 v26; // [rsp+60h] [rbp-3B8h]
  BinXmlTmplInstWriter *v27; // [rsp+68h] [rbp-3B0h]
  char v28[8]; // [rsp+70h] [rbp-3A8h] BYREF
  __int64 v29; // [rsp+78h] [rbp-3A0h]
  __int128 pExceptionObject; // [rsp+90h] [rbp-388h] BYREF
  __int64 v31; // [rsp+A0h] [rbp-378h]
  int v32; // [rsp+A8h] [rbp-370h]
  int v33; // [rsp+ACh] [rbp-36Ch]
  int v34; // [rsp+B0h] [rbp-368h]
  __int128 v35; // [rsp+B8h] [rbp-360h] BYREF
  __int64 v36; // [rsp+C8h] [rbp-350h]
  int v37; // [rsp+D0h] [rbp-348h]
  int v38; // [rsp+D4h] [rbp-344h]
  int v39; // [rsp+D8h] [rbp-340h]
  char v40[8]; // [rsp+E0h] [rbp-338h] BYREF
  __int64 v41; // [rsp+E8h] [rbp-330h]
  unsigned int v42; // [rsp+F0h] [rbp-328h]
  char v43[8]; // [rsp+F8h] [rbp-320h] BYREF
  unsigned __int8 *v44; // [rsp+100h] [rbp-318h]
  int v45; // [rsp+108h] [rbp-310h]
  EvtException *v46; // [rsp+110h] [rbp-308h] BYREF
  _BYTE v47[32]; // [rsp+118h] [rbp-300h] BYREF
  _BYTE v48[32]; // [rsp+138h] [rbp-2E0h] BYREF
  _QWORD v49[3]; // [rsp+158h] [rbp-2C0h] BYREF
  __int128 v50; // [rsp+170h] [rbp-2A8h]
  WriteBuffer *v51[6]; // [rsp+180h] [rbp-298h] BYREF
  _BYTE v52[64]; // [rsp+1B0h] [rbp-268h] BYREF
  _BYTE v53[192]; // [rsp+1F0h] [rbp-228h] BYREF
  _QWORD v54[2]; // [rsp+2B0h] [rbp-168h] BYREF
  __int128 v55; // [rsp+2C0h] [rbp-158h]
  __int128 v56; // [rsp+2D0h] [rbp-148h]
  unsigned __int8 v57[256]; // [rsp+2E0h] [rbp-138h] BYREF

  try
  {
    v8 = a4;
    v25 = a4;
    v9 = a3;
    v26 = a3;
    if ( !a8 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_50a4b5d3db573bd708b949f391e8ee2a_Traceguids, 87);
      }
      pExceptionObject = 0;
      v31 = 0;
      v32 = 87;
      v33 = -1;
      v34 = 125;
      throw (EvtException *)&pExceptionObject;
    }
    *a8 = 0;
    if ( !a1 || a5 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_50a4b5d3db573bd708b949f391e8ee2a_Traceguids, 87);
      }
      v35 = 0;
      v36 = 0;
      v37 = 87;
      v38 = -1;
      v39 = 132;
      throw (EvtException *)&v35;
    }
    v54[0] = a1;
    v54[1] = a2;
    v55 = 0;
    v56 = 0;
    Buffer::Buffer((Buffer *)v48, v57, 0x100u, 0);
    WriteBuffer::WriteBuffer((WriteBuffer *)v40, (struct BufferStream *)v48);
    BinXmlWriter::BinXmlWriter((BinXmlWriter *)v51, 0, (struct WriteBuffer *)v40, 0, 0, 0, 0);
    started = (BinXmlTmplInstWriter *)BinXmlWriter::StartTemplateInstance(v51, v8, (const struct BinXmlTemplate *)v54);
    v27 = started;
    for ( i = 0; ; ++i )
    {
      if ( i >= v8 )
      {
        BinXmlWriter::EndOfFile((BinXmlWriter *)v51);
        v49[0] = 0;
        v50 = 0;
        v49[1] = v41;
        v49[2] = v42;
        BinXmlReader::BinXmlReader((BinXmlReader *)v53, (struct BinXmlReaderData *)v49, v22, 0, 0, 0);
        Buffer::Buffer((Buffer *)v47, a7, 2 * a6, 0);
        WriteBuffer::WriteBuffer((WriteBuffer *)v43, (struct BufferStream *)v47);
        BinXmlReader::GetXmlText((BinXmlReader *)v53, (struct WriteBuffer *)v43);
        *a8 = v45;
        if ( v44 == a7 )
        {
          Buffer::~Buffer((Buffer *)v47);
          BinXmlReader::~BinXmlReader((BinXmlReader *)v53);
          utl::vector<tag_EvtRpcVariant,utl::allocator<tag_EvtRpcVariant>>::_Uninit(v52);
          Buffer::~Buffer((Buffer *)v48);
          return 0;
        }
        else
        {
          Buffer::~Buffer((Buffer *)v47);
          BinXmlReader::~BinXmlReader((BinXmlReader *)v53);
          utl::vector<tag_EvtRpcVariant,utl::allocator<tag_EvtRpcVariant>>::_Uninit(v52);
          Buffer::~Buffer((Buffer *)v48);
          return 122;
        }
      }
      v12 = *(__m128i *)(v9 + 16LL * i);
      v24 = v12;
      v13 = HIDWORD(*(_QWORD *)(v9 + 16LL * i + 8));
      if ( (v13 & 0x80u) == 0LL )
        break;
      v15 = v24.m128i_i32[3] & 0xFFFFFF7F;
      Buffer::Buffer((Buffer *)v28, 0, 0, 1);
      for ( j = 0; j < v24.m128i_i32[2]; ++j )
      {
        switch ( v15 )
        {
          case 1u:
          case 0x23u:
            v20 = *(_WORD **)(*(_QWORD *)(v9 + 16LL * i) + 8LL * j);
            v21 = -1;
            do
              ++v21;
            while ( v20[v21] );
            Buffer::Write((Buffer *)v28, v20, 2 * v21 + 2);
            break;
          case 2u:
            v17 = *(_BYTE **)(*(_QWORD *)(v9 + 16LL * i) + 8LL * j);
            v18 = -1;
            do
              ++v18;
            while ( v17[v18] );
            Buffer::Write((Buffer *)v28, v17, v18 + 1);
            break;
          case 0x13u:
            LengthSid = GetLengthSid(*(PSID *)(*(_QWORD *)(v26 + 16LL * i) + 8LL * j));
            Buffer::Write((Buffer *)v28, *(const void **)(*(_QWORD *)(v26 + 16LL * i) + 8LL * j), LengthSid);
            v9 = v26;
            break;
        }
      }
      v24.m128i_i64[0] = v29;
      started = v27;
      BinXmlTmplInstWriter::Value(v27, (struct BinXmlVariant *)&v24);
      Buffer::~Buffer((Buffer *)v28);
      v8 = v25;
LABEL_44:
      ;
    }
    if ( (_DWORD)v13 == 1 || (_DWORD)v13 == 35 )
    {
      if ( v12.m128i_i64[0] )
      {
        v14 = -1;
        do
          ++v14;
        while ( *(_WORD *)(v12.m128i_i64[0] + 2 * v14) );
        goto LABEL_26;
      }
    }
    else if ( (_DWORD)v13 == 2 )
    {
      if ( v12.m128i_i64[0] )
      {
        v14 = -1;
        do
          ++v14;
        while ( *(_BYTE *)(v12.m128i_i64[0] + v14) );
        goto LABEL_26;
      }
    }
    else
    {
      if ( _mm_cvtsi128_si32(_mm_srli_si128(v12, 12)) != 19 )
      {
LABEL_28:
        BinXmlTmplInstWriter::Value(started, (struct BinXmlVariant *)&v24);
        goto LABEL_44;
      }
      if ( v12.m128i_i64[0] )
      {
        LODWORD(v14) = GetLengthSid((PSID)v12.m128i_i64[0]);
LABEL_26:
        v24.m128i_i32[2] = v14;
        goto LABEL_28;
      }
    }
    v24.m128i_i32[2] = 0;
    goto LABEL_28;
  }
  catch ( EvtException *v46 )
  {
    return *((unsigned int *)v46 + 6);
  }
  v8 = a4;
}

```

## disassembly

```asm
0x180026e90  mov     [rsp+arg_0], rbx
0x180026e95  mov     [rsp+arg_8], rsi
0x180026e9a  push    rdi
0x180026e9b  push    r12
0x180026e9d  push    r13
0x180026e9f  push    r14
0x180026ea1  push    r15
0x180026ea3  sub     rsp, 3F0h
0x180026eaa  mov     rax, cs:__security_cookie
0x180026eb1  xor     rax, rsp
0x180026eb4  mov     [rsp+418h+var_38], rax
0x180026ebc  mov     esi, r9d
0x180026ebf  mov     [rsp+418h+var_3C0], r9d
0x180026ec4  mov     rbx, r8
0x180026ec7  mov     [rsp+418h+var_3B8], rbx
0x180026ecc  mov     r14d, [rsp+418h+arg_28]
0x180026ed4  mov     [rsp+418h+var_3D8], r14d
0x180026ed9  mov     r13, [rsp+418h+arg_30]
0x180026ee1  mov     r12, [rsp+418h+arg_38]
0x180026ee9  xor     r14d, r14d
0x180026eec  test    r12, r12
0x180026eef  jnz     loc_180026F77
0x180026ef5  lea     rax, WPP_GLOBAL_Control
0x180026efc  mov     rcx, cs:WPP_GLOBAL_Control
0x180026f03  cmp     rcx, rax
0x180026f06  jz      short loc_180026F2E
0x180026f08  test    byte ptr [rcx+1Ch], 1
0x180026f0c  jz      short loc_180026F2E
0x180026f0e  cmp     byte ptr [rcx+19h], 2
0x180026f12  jb      short loc_180026F2E
0x180026f14  lea     edx, [r12+0Ah]
0x180026f19  lea     r9d, [r12+57h]
0x180026f1e  lea     r8, WPP_50a4b5d3db573bd708b949f391e8ee2a_Traceguids
0x180026f25  mov     rcx, [rcx+10h]
0x180026f29  call    WPP_SF_D
0x180026f2e  xorps   xmm0, xmm0
0x180026f31  movdqu  [rsp+418h+pExceptionObject], xmm0
0x180026f3a  mov     [rsp+418h+var_378], r14
0x180026f42  mov     [rsp+418h+var_370], 57h ; 'W'
0x180026f4d  mov     [rsp+418h+var_36C], 0FFFFFFFFh
0x180026f58  mov     [rsp+418h+var_368], 7Dh ; '}'
0x180026f63  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180026f6a  lea     rcx, [rsp+418h+pExceptionObject]; pExceptionObject
0x180026f72  call    _CxxThrowException_0
0x180026f77  mov     [r12], r14d
0x180026f7b  test    rcx, rcx
0x180026f7e  jz      loc_180027321
0x180026f84  cmp     [rsp+418h+arg_20], r14d
0x180026f8c  jnz     loc_180027321
0x180026f92  xorps   xmm0, xmm0
0x180026f95  mov     [rsp+418h+var_168], rcx
0x180026f9d  mov     eax, edx
0x180026f9f  mov     [rsp+418h+var_160], rax
0x180026fa7  movdqu  [rsp+418h+var_158], xmm0
0x180026fb0  movdqu  [rsp+418h+var_148], xmm0
0x180026fb9  xor     r9d, r9d; bool
0x180026fbc  mov     r8d, 100h; unsigned int
0x180026fc2  lea     rdx, [rsp+418h+var_138]; unsigned __int8 *
0x180026fca  lea     rcx, [rsp+418h+var_2E0]; this
0x180026fd2  call    ??0Buffer@@QEAA@PEBEK_N@Z; Buffer::Buffer(uchar const *,ulong,bool)
0x180026fd7  nop
0x180026fd8  lea     rdx, [rsp+418h+var_2E0]; struct BufferStream *
0x180026fe0  lea     rcx, [rsp+418h+var_338]; this
0x180026fe8  call    ??0WriteBuffer@@QEAA@AEAVBufferStream@@@Z; WriteBuffer::WriteBuffer(BufferStream &)
0x180026fed  mov     [rsp+418h+var_3E8], r14d; unsigned int
0x180026ff2  mov     [rsp+418h+var_3F0], r14; unsigned int *
0x180026ff7  mov     [rsp+418h+var_3F8], r14; struct BinXmlTemplateTable *
0x180026ffc  xor     r9d, r9d; struct BinXmlStringTable *
0x180026fff  lea     r8, [rsp+418h+var_338]; struct WriteBuffer *
0x180027007  xor     edx, edx; bool
0x180027009  lea     rcx, [rsp+418h+var_298]; this
0x180027011  call    ??0BinXmlWriter@@QEAA@_NAEAVWriteBuffer@@PEAVBinXmlStringTable@@PEAVBinXmlTemplateTable@@PEBKK@Z; BinXmlWriter::BinXmlWriter(bool,WriteBuffer &,BinXmlStringTable *,BinXmlTemplateTable *,ulong const *,ulong)
0x180027016  nop
0x180027017  lea     r8, [rsp+418h+var_168]; struct BinXmlTemplate *
0x18002701f  mov     edx, esi; unsigned int
0x180027021  lea     rcx, [rsp+418h+var_298]; this
0x180027029  call    ?StartTemplateInstance@BinXmlWriter@@QEAAPEAVBinXmlTmplInstWriter@@KAEBVBinXmlTemplate@@@Z; BinXmlWriter::StartTemplateInstance(ulong,BinXmlTemplate const &)
0x18002702e  mov     rdi, rax
0x180027031  mov     [rsp+418h+var_3B0], rax
0x180027036  mov     r15d, r14d
0x180027039  cmp     r15d, esi
0x18002703c  jnb     loc_1800271E9
0x180027042  mov     r14d, r15d
0x180027045  add     r14, r14
0x180027048  movups  xmm1, xmmword ptr [rbx+r14*8]
0x18002704d  movups  [rsp+418h+var_3D0], xmm1
0x180027052  mov     rax, [rbx+r14*8+8]
0x180027057  shr     rax, 20h
0x18002705b  test    al, al
0x18002705d  js      loc_1800270E7
0x180027063  cmp     eax, 1
0x180027066  jz      short loc_1800270B2
0x180027068  cmp     eax, 23h ; '#'
0x18002706b  jz      short loc_1800270B2
0x18002706d  cmp     eax, 2
0x180027070  jnz     short loc_18002708C
0x180027072  movq    rcx, xmm1
0x180027077  xor     edx, edx
0x180027079  test    rcx, rcx
0x18002707c  jz      short loc_1800270D1
0x18002707e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180027082  inc     rax
0x180027085  cmp     [rcx+rax], dl
0x180027088  jnz     short loc_180027082
0x18002708a  jmp     short loc_1800270CB
0x18002708c  movdqa  xmm0, xmm1
0x180027090  psrldq  xmm0, 0Ch
0x180027095  movd    eax, xmm0
0x180027099  cmp     eax, 13h
0x18002709c  jnz     short loc_1800270D5
0x18002709e  movq    rcx, xmm1; pSid
0x1800270a3  xor     edx, edx
0x1800270a5  test    rcx, rcx
0x1800270a8  jz      short loc_1800270D1
0x1800270aa  call    cs:__imp_GetLengthSid
0x1800270b0  jmp     short loc_1800270CB
0x1800270b2  movq    rcx, xmm1
0x1800270b7  xor     edx, edx
0x1800270b9  test    rcx, rcx
0x1800270bc  jz      short loc_1800270D1
0x1800270be  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800270c2  inc     rax
0x1800270c5  cmp     [rcx+rax*2], dx
0x1800270c9  jnz     short loc_1800270C2
0x1800270cb  mov     dword ptr [rsp+418h+var_3D0+8], eax
0x1800270cf  jmp     short loc_1800270D5
0x1800270d1  mov     dword ptr [rsp+418h+var_3D0+8], edx
0x1800270d5  lea     rdx, [rsp+418h+var_3D0]; struct BinXmlVariant *
0x1800270da  mov     rcx, rdi; this
0x1800270dd  call    ?Value@BinXmlTmplInstWriter@@QEAAXAEAUBinXmlVariant@@@Z; BinXmlTmplInstWriter::Value(BinXmlVariant &)
0x1800270e2  jmp     loc_1800271E1
0x1800270e7  mov     edi, dword ptr [rsp+418h+var_3D0+0Ch]
0x1800270eb  btr     edi, 7
0x1800270ef  mov     r9b, 1; bool
0x1800270f2  xor     r8d, r8d; unsigned int
0x1800270f5  xor     edx, edx; unsigned __int8 *
0x1800270f7  lea     rcx, [rsp+418h+var_3A8]; this
0x1800270fc  call    ??0Buffer@@QEAA@PEBEK_N@Z; Buffer::Buffer(uchar const *,ulong,bool)
0x180027101  nop
0x180027102  xor     r9d, r9d
0x180027105  mov     esi, r9d
0x180027108  cmp     esi, dword ptr [rsp+418h+var_3D0+8]
0x18002710c  jnb     loc_1800271B6
0x180027112  cmp     edi, 1
0x180027115  jz      short loc_180027182
0x180027117  cmp     edi, 23h ; '#'
0x18002711a  jz      short loc_180027182
0x18002711c  cmp     edi, 2
0x18002711f  jnz     short loc_180027147
0x180027121  mov     ecx, esi
0x180027123  mov     rax, [rbx+r14*8]
0x180027127  mov     rdx, [rax+rcx*8]; void *
0x18002712b  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002712f  inc     r8
0x180027132  cmp     [rdx+r8], r9b
0x180027136  jnz     short loc_18002712F
0x180027138  inc     r8d; unsigned int
0x18002713b  lea     rcx, [rsp+418h+var_3A8]; this
0x180027140  call    ?Write@Buffer@@UEAAXQEBXK@Z; Buffer::Write(void const * const,ulong)
0x180027145  jmp     short loc_1800271AC
0x180027147  cmp     edi, 13h
0x18002714a  jnz     short loc_1800271AF
0x18002714c  mov     ebx, esi
0x18002714e  mov     rax, [rsp+418h+var_3B8]
0x180027153  mov     rcx, [rax+r14*8]
0x180027157  mov     rcx, [rcx+rbx*8]; pSid
0x18002715b  call    cs:__imp_GetLengthSid
0x180027161  mov     rdx, [rsp+418h+var_3B8]
0x180027166  mov     rdx, [rdx+r14*8]
0x18002716a  mov     r8d, eax; unsigned int
0x18002716d  mov     rdx, [rdx+rbx*8]; void *
0x180027171  lea     rcx, [rsp+418h+var_3A8]; this
0x180027176  call    ?Write@Buffer@@UEAAXQEBXK@Z; Buffer::Write(void const * const,ulong)
0x18002717b  mov     rbx, [rsp+418h+var_3B8]
0x180027180  jmp     short loc_1800271AC
0x180027182  mov     ecx, esi
0x180027184  mov     rax, [rbx+r14*8]
0x180027188  mov     rdx, [rax+rcx*8]; void *
0x18002718c  or      r8, 0FFFFFFFFFFFFFFFFh
0x180027190  inc     r8
0x180027193  cmp     [rdx+r8*2], r9w
0x180027198  jnz     short loc_180027190
0x18002719a  lea     r8d, ds:2[r8*2]; unsigned int
0x1800271a2  lea     rcx, [rsp+418h+var_3A8]; this
0x1800271a7  call    ?Write@Buffer@@UEAAXQEBXK@Z; Buffer::Write(void const * const,ulong)
0x1800271ac  xor     r9d, r9d
0x1800271af  inc     esi
0x1800271b1  jmp     loc_180027108
0x1800271b6  mov     rax, [rsp+418h+var_3A0]
0x1800271bb  mov     qword ptr [rsp+418h+var_3D0], rax
0x1800271c0  lea     rdx, [rsp+418h+var_3D0]; struct BinXmlVariant *
0x1800271c5  mov     rdi, [rsp+418h+var_3B0]
0x1800271ca  mov     rcx, rdi; this
0x1800271cd  call    ?Value@BinXmlTmplInstWriter@@QEAAXAEAUBinXmlVariant@@@Z; BinXmlTmplInstWriter::Value(BinXmlVariant &)
0x1800271d2  nop
0x1800271d3  lea     rcx, [rsp+418h+var_3A8]; this
0x1800271d8  call    ??1Buffer@@UEAA@XZ; Buffer::~Buffer(void)
0x1800271dd  mov     esi, [rsp+418h+var_3C0]
0x1800271e1  inc     r15d
0x1800271e4  jmp     loc_180027039
0x1800271e9  lea     rcx, [rsp+418h+var_298]; this
0x1800271f1  call    ?EndOfFile@BinXmlWriter@@QEAAXXZ; BinXmlWriter::EndOfFile(void)
0x1800271f6  xor     ecx, ecx
0x1800271f8  mov     [rsp+418h+var_2C0], rcx
0x180027200  xorps   xmm0, xmm0
0x180027203  movdqu  [rsp+418h+var_2A8], xmm0
0x18002720c  mov     rax, [rsp+418h+var_330]
0x180027214  mov     [rsp+418h+var_2B8], rax
0x18002721c  mov     eax, [rsp+418h+var_328]
0x180027223  mov     [rsp+418h+var_2B0], rax
0x18002722b  mov     [rsp+418h+var_3F0], rcx; struct BinXmlTemplateTable *
0x180027230  mov     [rsp+418h+var_3F8], rcx; struct BinXmlStringTable *
0x180027235  xor     r9d, r9d; struct AbstractPublishedEventRecord *
0x180027238  lea     rdx, [rsp+418h+var_2C0]; struct BinXmlReaderData *
0x180027240  lea     rcx, [rsp+418h+var_228]; this
0x180027248  call    ??0BinXmlReader@@QEAA@PEAUBinXmlReaderData@@KPEAVAbstractPublishedEventRecord@@PEAVBinXmlStringTable@@PEAVBinXmlTemplateTable@@@Z; BinXmlReader::BinXmlReader(BinXmlReaderData *,ulong,AbstractPublishedEventRecord *,BinXmlStringTable *,BinXmlTemplateTable *)
0x18002724d  nop
0x18002724e  mov     r8d, [rsp+418h+var_3D8]
0x180027253  add     r8d, r8d; unsigned int
0x180027256  xor     r9d, r9d; bool
0x180027259  mov     rdx, r13; unsigned __int8 *
0x18002725c  lea     rcx, [rsp+418h+var_300]; this
0x180027264  call    ??0Buffer@@QEAA@PEBEK_N@Z; Buffer::Buffer(uchar const *,ulong,bool)
0x180027269  nop
0x18002726a  lea     rdx, [rsp+418h+var_300]; struct BufferStream *
0x180027272  lea     rcx, [rsp+418h+var_320]; this
0x18002727a  call    ??0WriteBuffer@@QEAA@AEAVBufferStream@@@Z; WriteBuffer::WriteBuffer(BufferStream &)
0x18002727f  lea     rdx, [rsp+418h+var_320]; struct WriteBuffer *
0x180027287  lea     rcx, [rsp+418h+var_228]; this
0x18002728f  call    ?GetXmlText@BinXmlReader@@QEAAXAEAVWriteBuffer@@@Z; BinXmlReader::GetXmlText(WriteBuffer &)
0x180027294  mov     eax, [rsp+418h+var_310]
0x18002729b  mov     [r12], eax
0x18002729f  lea     rcx, [rsp+418h+var_300]; this
0x1800272a7  cmp     [rsp+418h+var_318], r13
0x1800272af  jz      short loc_1800272EA
0x1800272b1  call    ??1Buffer@@UEAA@XZ; Buffer::~Buffer(void)
0x1800272b6  nop
0x1800272b7  lea     rcx, [rsp+418h+var_228]; this
0x1800272bf  call    ??1BinXmlReader@@QEAA@XZ; BinXmlReader::~BinXmlReader(void)
0x1800272c4  nop
0x1800272c5  lea     rcx, [rsp+418h+var_268]
0x1800272cd  call    ?_Uninit@?$vector@Utag_EvtRpcVariant@@V?$allocator@Utag_EvtRpcVariant@@@utl@@@utl@@AEAAXXZ; utl::vector<tag_EvtRpcVariant,utl::allocator<tag_EvtRpcVariant>>::_Uninit(void)
0x1800272d2  nop
0x1800272d3  lea     rcx, [rsp+418h+var_2E0]; this
0x1800272db  call    ??1Buffer@@UEAA@XZ; Buffer::~Buffer(void)
0x1800272e0  mov     eax, 7Ah ; 'z'
0x1800272e5  jmp     loc_1800273A7
0x1800272ea  call    ??1Buffer@@UEAA@XZ; Buffer::~Buffer(void)
0x1800272ef  nop
0x1800272f0  lea     rcx, [rsp+418h+var_228]; this
0x1800272f8  call    ??1BinXmlReader@@QEAA@XZ; BinXmlReader::~BinXmlReader(void)
0x1800272fd  nop
0x1800272fe  lea     rcx, [rsp+418h+var_268]
0x180027306  call    ?_Uninit@?$vector@Utag_EvtRpcVariant@@V?$allocator@Utag_EvtRpcVariant@@@utl@@@utl@@AEAAXXZ; utl::vector<tag_EvtRpcVariant,utl::allocator<tag_EvtRpcVariant>>::_Uninit(void)
0x18002730b  nop
0x18002730c  lea     rcx, [rsp+418h+var_2E0]; this
0x180027314  call    ??1Buffer@@UEAA@XZ; Buffer::~Buffer(void)
0x180027319  nop
0x18002731a  xor     eax, eax
0x18002731c  jmp     loc_1800273A7
0x180027321  lea     rax, WPP_GLOBAL_Control
0x180027328  mov     rcx, cs:WPP_GLOBAL_Control
0x18002732f  cmp     rcx, rax
0x180027332  jz      short loc_180027359
0x180027334  test    byte ptr [rcx+1Ch], 1
0x180027338  jz      short loc_180027359
0x18002733a  cmp     byte ptr [rcx+19h], 2
0x18002733e  jb      short loc_180027359
0x180027340  mov     edx, 0Bh
0x180027345  lea     r9d, [rdx+4Ch]
0x180027349  lea     r8, WPP_50a4b5d3db573bd708b949f391e8ee2a_Traceguids
0x180027350  mov     rcx, [rcx+10h]
0x180027354  call    WPP_SF_D
0x180027359  xorps   xmm0, xmm0
0x18002735c  movdqu  [rsp+418h+var_360], xmm0
0x180027365  mov     [rsp+418h+var_350], r14
0x18002736d  mov     [rsp+418h+var_348], 57h ; 'W'
0x180027378  mov     [rsp+418h+var_344], 0FFFFFFFFh
0x180027383  mov     [rsp+418h+var_340], 84h
0x18002738e  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180027395  lea     rcx, [rsp+418h+var_360]; pExceptionObject
0x18002739d  call    _CxxThrowException_0
0x1800273a3  mov     eax, [rsp+418h+var_3D8]
0x1800273a7  mov     rcx, [rsp+418h+var_38]
0x1800273af  xor     rcx, rsp; StackCookie
0x1800273b2  call    __security_check_cookie
0x1800273b7  lea     r11, [rsp+418h+var_28]
0x1800273bf  mov     rbx, [r11+30h]
0x1800273c3  mov     rsi, [r11+38h]
0x1800273c7  mov     rsp, r11
0x1800273ca  pop     r15
0x1800273cc  pop     r14
0x1800273ce  pop     r13
0x1800273d0  pop     r12
0x1800273d2  pop     rdi
0x1800273d3  retn
```
