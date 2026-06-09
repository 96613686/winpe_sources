# SectionCache::LoadSectionTable(void)

- ea: `0x180037d98`
- end: `0x1800381d9`
- name: `?LoadSectionTable@SectionCache@@AEAAXXZ`
- size: `1089`
- prototype: `void __fastcall(SectionCache *__hidden this)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config`

## callers

- `0x180036578`

## callees

- `0x180009d80`
- `0x18000a2d0`
- `0x18000a558`
- `0x18000a724`
- `0x18000c374`
- `0x180013cc4`
- `0x1800169e8`
- `0x180023548`
- `0x1800239c0`
- `0x180024a50`
- `0x1800287f4`
- `0x1800362c8`
- `0x180036a94`
- `0x180036d10`
- `0x180037d98`
- `0x1800384e8`
- `0x1800385dc`
- `0x180038fa4`
- `0x180038fb0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180037dec`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180037dec`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003813d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003813d`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall SectionCache::LoadSectionTable(RTL_SRWLOCK *this)
{
  unsigned int Ptr; // eax
  int v3; // r14d
  int v4; // eax
  int v5; // r8d
  __int64 v6; // rdi
  char v7; // di
  __int128 pExceptionObject; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v9; // [rsp+40h] [rbp-C0h]
  int v10; // [rsp+48h] [rbp-B8h]
  int v11; // [rsp+4Ch] [rbp-B4h]
  int v12; // [rsp+50h] [rbp-B0h]
  _QWORD v13[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v14; // [rsp+70h] [rbp-90h] BYREF
  char v15; // [rsp+78h] [rbp-88h]
  _BYTE v16[32]; // [rsp+80h] [rbp-80h] BYREF
  int v17; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v18; // [rsp+A8h] [rbp-58h]
  __int64 v19; // [rsp+B0h] [rbp-50h]
  _QWORD v20[4]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v21[8]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v22[32]; // [rsp+E0h] [rbp-20h] BYREF
  RTL_SRWLOCK *v23; // [rsp+100h] [rbp+0h]
  __int64 Buf1; // [rsp+108h] [rbp+8h] BYREF
  __int64 v25; // [rsp+110h] [rbp+10h]
  unsigned int v26[2]; // [rsp+118h] [rbp+18h]

  Buf1 = 0;
  v25 = 0;
  *(_QWORD *)v26 = 0;
  Buffer::Buffer((Buffer *)v22, 0, 0, 1);
  v23 = this + 8;
  AcquireSRWLockExclusive(this + 8);
  if ( this[7].Ptr == (PVOID)-1LL || this[7].Ptr == 0 || !LOBYTE(this[9].Ptr) )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids, 4317);
    }
    pExceptionObject = 0;
    v9 = 0;
    v10 = 4317;
    v11 = -1;
    v12 = 611;
    throw (EvtException *)&pExceptionObject;
  }
  RecordCache::Seek((RecordCache *)this, 0);
  Buffer::Set((Buffer *)v22, (const unsigned __int8 *)&Buf1, 0x18u);
  Buffer::SetCurrentIndex((Buffer *)v22, 0x18u);
  RecordCache::ReadBytes(&this->Ptr, (struct Buffer *)v22);
  if ( strcmp((const char *)&Buf1, "MTAFile") )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids, 1500);
    }
    pExceptionObject = 0;
    v9 = 0;
    v10 = 1500;
    v11 = -1;
    v12 = 626;
    throw (EvtException *)&pExceptionObject;
  }
  Ptr = (unsigned int)this[135].Ptr;
  if ( (unsigned int)v25 > Ptr )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids, 15035);
    }
    pExceptionObject = 0;
    v9 = 0;
    v10 = 15035;
    v11 = -1;
    v12 = 631;
    throw (EvtException *)&pExceptionObject;
  }
  if ( (unsigned int)v25 < Ptr )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids, 15034);
    }
    pExceptionObject = 0;
    v9 = 0;
    v10 = 15034;
    v11 = -1;
    v12 = 636;
    throw (EvtException *)&pExceptionObject;
  }
  SectionCache::SectionHeader::SectionHeader((SectionCache::SectionHeader *)&v17);
  Buffer::Buffer((Buffer *)v16, 0, 0, 1);
  Buffer::SetCurrentIndex((Buffer *)v16, v26[0]);
  RecordCache::ReadBytes(&this->Ptr, (struct Buffer *)v16);
  Buffer::SetCurrentIndex((Buffer *)v16, 0);
  v3 = -1;
  while ( ++v3 < v26[1] )
  {
    SectionCache::SectionHeader::Deserialize((SectionCache::SectionHeader *)&v17, (struct Buffer *)v16);
    v13[0] = v20[0];
    v13[1] = (__int64)(v20[1] - v20[0]) >> 1;
    v4 = MakeOrThrowOOM(&pExceptionObject, v13);
    utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>,0>::_TryEmplace<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,SectionCache::SectionHeader>(
      (_DWORD)this + 1088,
      (unsigned int)&v14,
      v5,
      v4,
      (__int64)&v17);
    v6 = v14;
    if ( !v15 )
    {
      if ( !v14 )
        goto LABEL_27;
      *(_DWORD *)(v14 + 56) = v17;
      *(_QWORD *)(v6 + 64) = v18;
      *(_QWORD *)(v6 + 72) = v19;
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(v6 + 80, v20);
      utl::unique_ptr<ValuesRenderContext,utl::default_delete<ValuesRenderContext>>::operator=(v6 + 112, v21);
    }
    if ( v6 )
    {
      v7 = 0;
      goto LABEL_29;
    }
LABEL_27:
    v7 = 1;
LABEL_29:
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(&pExceptionObject);
    if ( v7 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids, 14);
      }
      pExceptionObject = 0;
      v9 = 0;
      v10 = 14;
      v11 = -1;
      v12 = 657;
      throw (EvtException *)&pExceptionObject;
    }
  }
  Buffer::~Buffer((Buffer *)v16);
  SectionCache::SectionHeader::~SectionHeader((SectionCache::SectionHeader *)&v17);
  ReleaseSRWLockExclusive(this + 8);
  Buffer::~Buffer((Buffer *)v22);
}

```

## disassembly

```asm
0x180037d98  push    rbp
0x180037d9a  push    rbx
0x180037d9b  push    rsi
0x180037d9c  push    rdi
0x180037d9d  push    r14
0x180037d9f  push    r15
0x180037da1  lea     rbp, [rsp-38h]
0x180037da6  sub     rsp, 138h
0x180037dad  mov     rax, cs:__security_cookie
0x180037db4  xor     rax, rsp
0x180037db7  mov     [rbp+60h+var_40], rax
0x180037dbb  mov     rsi, rcx
0x180037dbe  xor     eax, eax
0x180037dc0  mov     [rbp+60h+Buf1], rax
0x180037dc4  xor     r15d, r15d
0x180037dc7  mov     [rbp+60h+var_50], r15
0x180037dcb  mov     qword ptr [rbp+60h+var_48], r15
0x180037dcf  mov     r9b, 1; bool
0x180037dd2  xor     r8d, r8d; unsigned int
0x180037dd5  xor     edx, edx; unsigned __int8 *
0x180037dd7  lea     rcx, [rbp+60h+var_80]; this
0x180037ddb  call    ??0Buffer@@QEAA@PEBEK_N@Z; Buffer::Buffer(uchar const *,ulong,bool)
0x180037de0  nop
0x180037de1  lea     rbx, [rsi+40h]
0x180037de5  mov     [rbp+60h+var_60], rbx
0x180037de9  mov     rcx, rbx; SRWLock
0x180037dec  call    cs:__imp_AcquireSRWLockExclusive
0x180037df2  nop
0x180037df3  mov     rax, [rsi+38h]
0x180037df7  inc     rax
0x180037dfa  cmp     rax, 1
0x180037dfe  jbe     loc_180038169
0x180037e04  cmp     [rsi+48h], r15b
0x180037e08  jz      loc_180038169
0x180037e0e  xor     edx, edx; unsigned __int64
0x180037e10  mov     rcx, rsi; this
0x180037e13  call    ?Seek@RecordCache@@IEAAX_K@Z; RecordCache::Seek(unsigned __int64)
0x180037e18  lea     edi, [r15+18h]
0x180037e1c  mov     r8d, edi; unsigned int
0x180037e1f  lea     rdx, [rbp+60h+Buf1]; unsigned __int8 *
0x180037e23  lea     rcx, [rbp+60h+var_80]; this
0x180037e27  call    ?Set@Buffer@@QEAAXPEBEK@Z; Buffer::Set(uchar const *,ulong)
0x180037e2c  mov     edx, edi; unsigned int
0x180037e2e  lea     rcx, [rbp+60h+var_80]; this
0x180037e32  call    ?SetCurrentIndex@Buffer@@UEAAXK@Z; Buffer::SetCurrentIndex(ulong)
0x180037e37  lea     rdx, [rbp+60h+var_80]; struct Buffer *
0x180037e3b  mov     rcx, rsi; this
0x180037e3e  call    ?ReadBytes@RecordCache@@IEAAKAEAVBuffer@@@Z; RecordCache::ReadBytes(Buffer &)
0x180037e43  lea     r8d, [r15+8]; Size
0x180037e47  lea     rdx, aMtafile; "MTAFile"
0x180037e4e  lea     rcx, [rbp+60h+Buf1]; Buf1
0x180037e52  call    memcmp_0
0x180037e57  test    eax, eax
0x180037e59  jz      short loc_180037EC9
0x180037e5b  lea     rax, WPP_GLOBAL_Control
0x180037e62  mov     ebx, 5DCh
0x180037e67  mov     rcx, cs:WPP_GLOBAL_Control
0x180037e6e  cmp     rcx, rax
0x180037e71  jz      short loc_180037E95
0x180037e73  test    byte ptr [rcx+1Ch], 1
0x180037e77  jz      short loc_180037E95
0x180037e79  cmp     byte ptr [rcx+19h], 2
0x180037e7d  jb      short loc_180037E95
0x180037e7f  lea     edx, [rdi+6]
0x180037e82  mov     r9d, ebx
0x180037e85  lea     r8, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids
0x180037e8c  mov     rcx, [rcx+10h]
0x180037e90  call    WPP_SF_D
0x180037e95  xorps   xmm0, xmm0
0x180037e98  movdqu  [rsp+160h+pExceptionObject], xmm0
0x180037e9e  mov     [rsp+160h+var_120], r15
0x180037ea3  mov     [rsp+160h+var_118], ebx
0x180037ea7  mov     [rsp+160h+var_114], 0FFFFFFFFh
0x180037eaf  mov     [rsp+160h+var_110], 272h
0x180037eb7  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180037ebe  lea     rcx, [rsp+160h+pExceptionObject]; pExceptionObject
0x180037ec3  call    _CxxThrowException_0
0x180037ec9  mov     eax, [rsi+438h]
0x180037ecf  cmp     dword ptr [rbp+60h+var_50], eax
0x180037ed2  jbe     short loc_180037F44
0x180037ed4  lea     rax, WPP_GLOBAL_Control
0x180037edb  mov     ebx, 3ABBh
0x180037ee0  mov     rcx, cs:WPP_GLOBAL_Control
0x180037ee7  cmp     rcx, rax
0x180037eea  jz      short loc_180037F10
0x180037eec  test    byte ptr [rcx+1Ch], 1
0x180037ef0  jz      short loc_180037F10
0x180037ef2  cmp     byte ptr [rcx+19h], 2
0x180037ef6  jb      short loc_180037F10
0x180037ef8  mov     edx, 1Fh
0x180037efd  mov     r9d, ebx
0x180037f00  lea     r8, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids
0x180037f07  mov     rcx, [rcx+10h]
0x180037f0b  call    WPP_SF_D
0x180037f10  xorps   xmm0, xmm0
0x180037f13  movdqu  [rsp+160h+pExceptionObject], xmm0
0x180037f19  mov     [rsp+160h+var_120], r15
0x180037f1e  mov     [rsp+160h+var_118], ebx
0x180037f22  mov     [rsp+160h+var_114], 0FFFFFFFFh
0x180037f2a  mov     [rsp+160h+var_110], 277h
0x180037f32  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180037f39  lea     rcx, [rsp+160h+pExceptionObject]; pExceptionObject
0x180037f3e  call    _CxxThrowException_0
0x180037f44  jnb     short loc_180037FB6
0x180037f46  lea     rax, WPP_GLOBAL_Control
0x180037f4d  mov     ebx, 3ABAh
0x180037f52  mov     rcx, cs:WPP_GLOBAL_Control
0x180037f59  cmp     rcx, rax
0x180037f5c  jz      short loc_180037F82
0x180037f5e  test    byte ptr [rcx+1Ch], 1
0x180037f62  jz      short loc_180037F82
0x180037f64  cmp     byte ptr [rcx+19h], 2
0x180037f68  jb      short loc_180037F82
0x180037f6a  mov     edx, 20h ; ' '
0x180037f6f  mov     r9d, ebx
0x180037f72  lea     r8, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids
0x180037f79  mov     rcx, [rcx+10h]
0x180037f7d  call    WPP_SF_D
0x180037f82  xorps   xmm0, xmm0
0x180037f85  movdqu  [rsp+160h+pExceptionObject], xmm0
0x180037f8b  mov     [rsp+160h+var_120], r15
0x180037f90  mov     [rsp+160h+var_118], ebx
0x180037f94  mov     [rsp+160h+var_114], 0FFFFFFFFh
0x180037f9c  mov     [rsp+160h+var_110], 27Ch
0x180037fa4  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180037fab  lea     rcx, [rsp+160h+pExceptionObject]; pExceptionObject
0x180037fb0  call    _CxxThrowException_0
0x180037fb6  lea     rcx, [rbp+60h+var_C0]; this
0x180037fba  call    ??0SectionHeader@SectionCache@@QEAA@XZ; SectionCache::SectionHeader::SectionHeader(void)
0x180037fbf  nop
0x180037fc0  mov     r9b, 1; bool
0x180037fc3  xor     r8d, r8d; unsigned int
0x180037fc6  xor     edx, edx; unsigned __int8 *
0x180037fc8  lea     rcx, [rbp+60h+var_E0]; this
0x180037fcc  call    ??0Buffer@@QEAA@PEBEK_N@Z; Buffer::Buffer(uchar const *,ulong,bool)
0x180037fd1  nop
0x180037fd2  mov     edx, [rbp+60h+var_48]; unsigned int
0x180037fd5  lea     rcx, [rbp+60h+var_E0]; this
0x180037fd9  call    ?SetCurrentIndex@Buffer@@UEAAXK@Z; Buffer::SetCurrentIndex(ulong)
0x180037fde  lea     rdx, [rbp+60h+var_E0]; struct Buffer *
0x180037fe2  mov     rcx, rsi; this
0x180037fe5  call    ?ReadBytes@RecordCache@@IEAAKAEAVBuffer@@@Z; RecordCache::ReadBytes(Buffer &)
0x180037fea  xor     edx, edx; unsigned int
0x180037fec  lea     rcx, [rbp+60h+var_E0]; this
0x180037ff0  call    ?SetCurrentIndex@Buffer@@UEAAXK@Z; Buffer::SetCurrentIndex(ulong)
0x180037ff5  or      r14d, 0FFFFFFFFh
0x180037ff9  inc     r14d
0x180037ffc  cmp     r14d, [rbp+60h+var_48+4]
0x180038000  jnb     loc_180038126
0x180038006  lea     rdx, [rbp+60h+var_E0]; struct Buffer *
0x18003800a  lea     rcx, [rbp+60h+var_C0]; this
0x18003800e  call    ?Deserialize@SectionHeader@SectionCache@@QEAAXAEAVBuffer@@@Z; SectionCache::SectionHeader::Deserialize(Buffer &)
0x180038013  mov     rax, [rbp+60h+var_A8]
0x180038017  mov     [rsp+160h+var_100], rax
0x18003801c  mov     rcx, [rbp+60h+var_A0]
0x180038020  sub     rcx, rax
0x180038023  sar     rcx, 1
0x180038026  mov     [rsp+160h+var_F8], rcx
0x18003802b  lea     rdx, [rsp+160h+var_100]
0x180038030  lea     rcx, [rsp+160h+pExceptionObject]
0x180038035  call    ?MakeOrThrowOOM@@YA?AV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$basic_string_view@_WU?$char_traits@_W@utl@@@2@@Z; MakeOrThrowOOM(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x18003803a  lea     rcx, [rsi+440h]
0x180038041  lea     rdx, [rbp+60h+var_C0]
0x180038045  mov     [rsp+160h+var_140], rdx
0x18003804a  mov     r9, rax
0x18003804d  lea     rdx, [rsp+160h+var_F0]
0x180038052  call    ??$_TryEmplace@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@USectionHeader@SectionCache@@@?$_Tree@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@USectionHeader@SectionCache@@@2@Uistring_less_ordinal@tlx@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@USectionHeader@SectionCache@@@utl@@@2@$0A@@utl@@IEAA?AU?$pair@V?$_TreeIt@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@USectionHeader@SectionCache@@@utl@@@utl@@_N@1@PEAU?$_TreeNode@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@USectionHeader@SectionCache@@@utl@@@1@$$QEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@1@$$QEAUSectionHeader@SectionCache@@@Z; utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>,0>::_TryEmplace<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,SectionCache::SectionHeader>(utl::_TreeNode<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>> *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&,SectionCache::SectionHeader &&)
0x180038057  mov     rdi, [rsp+160h+var_F0]
0x18003805c  cmp     [rsp+160h+var_E8], r15b
0x180038061  jnz     short loc_180038098
0x180038063  test    rdi, rdi
0x180038066  jz      short loc_18003809D
0x180038068  mov     eax, [rbp+60h+var_C0]
0x18003806b  mov     [rdi+38h], eax
0x18003806e  mov     rax, [rbp+60h+var_B8]
0x180038072  mov     [rdi+40h], rax
0x180038076  mov     rax, [rbp+60h+var_B0]
0x18003807a  mov     [rdi+48h], rax
0x18003807e  lea     rcx, [rdi+50h]
0x180038082  lea     rdx, [rbp+60h+var_A8]
0x180038086  call    ??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x18003808b  lea     rcx, [rdi+70h]
0x18003808f  lea     rdx, [rbp+60h+var_88]
0x180038093  call    ??4?$unique_ptr@VValuesRenderContext@@U?$default_delete@VValuesRenderContext@@@utl@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::unique_ptr<ValuesRenderContext,utl::default_delete<ValuesRenderContext>>::operator=(utl::unique_ptr<ValuesRenderContext,utl::default_delete<ValuesRenderContext>> &&)
0x180038098  test    rdi, rdi
0x18003809b  jnz     short loc_1800380A2
0x18003809d  mov     dil, 1
0x1800380a0  jmp     short loc_1800380A5
0x1800380a2  mov     dil, r15b
0x1800380a5  lea     rcx, [rsp+160h+pExceptionObject]
0x1800380aa  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x1800380af  test    dil, dil
0x1800380b2  jz      loc_180037FF9
0x1800380b8  lea     rax, WPP_GLOBAL_Control
0x1800380bf  mov     ebx, 0Eh
0x1800380c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800380cb  cmp     rcx, rax
0x1800380ce  jz      short loc_1800380F2
0x1800380d0  test    byte ptr [rcx+1Ch], 1
0x1800380d4  jz      short loc_1800380F2
0x1800380d6  cmp     byte ptr [rcx+19h], 2
0x1800380da  jb      short loc_1800380F2
0x1800380dc  lea     edx, [rbx+13h]
0x1800380df  mov     r9d, ebx
0x1800380e2  lea     r8, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids
0x1800380e9  mov     rcx, [rcx+10h]
0x1800380ed  call    WPP_SF_D
0x1800380f2  xorps   xmm0, xmm0
0x1800380f5  movdqu  [rsp+160h+pExceptionObject], xmm0
0x1800380fb  mov     [rsp+160h+var_120], r15
0x180038100  mov     [rsp+160h+var_118], ebx
0x180038104  mov     [rsp+160h+var_114], 0FFFFFFFFh
0x18003810c  mov     [rsp+160h+var_110], 291h
0x180038114  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18003811b  lea     rcx, [rsp+160h+pExceptionObject]; pExceptionObject
0x180038120  call    _CxxThrowException_0
0x180038126  lea     rcx, [rbp+60h+var_E0]; this
0x18003812a  call    ??1Buffer@@UEAA@XZ; Buffer::~Buffer(void)
0x18003812f  nop
0x180038130  lea     rcx, [rbp+60h+var_C0]; this
0x180038134  call    ??1SectionHeader@SectionCache@@QEAA@XZ; SectionCache::SectionHeader::~SectionHeader(void)
0x180038139  nop
0x18003813a  mov     rcx, rbx; SRWLock
0x18003813d  call    cs:__imp_ReleaseSRWLockExclusive
0x180038143  nop
0x180038144  lea     rcx, [rbp+60h+var_80]; this
0x180038148  call    ??1Buffer@@UEAA@XZ; Buffer::~Buffer(void)
0x18003814d  mov     rcx, [rbp+60h+var_40]
0x180038151  xor     rcx, rsp; StackCookie
0x180038154  call    __security_check_cookie
0x180038159  add     rsp, 138h
0x180038160  pop     r15
0x180038162  pop     r14
0x180038164  pop     rdi
0x180038165  pop     rsi
0x180038166  pop     rbx
0x180038167  pop     rbp
0x180038168  retn
0x180038169  lea     rax, WPP_GLOBAL_Control
0x180038170  mov     ebx, 10DDh
0x180038175  mov     rcx, cs:WPP_GLOBAL_Control
0x18003817c  cmp     rcx, rax
0x18003817f  jz      short loc_1800381A5
0x180038181  test    byte ptr [rcx+1Ch], 1
0x180038185  jz      short loc_1800381A5
0x180038187  cmp     byte ptr [rcx+19h], 2
0x18003818b  jb      short loc_1800381A5
0x18003818d  mov     edx, 1Dh
0x180038192  mov     r9d, ebx
0x180038195  lea     r8, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids
0x18003819c  mov     rcx, [rcx+10h]
0x1800381a0  call    WPP_SF_D
0x1800381a5  xorps   xmm0, xmm0
0x1800381a8  movdqu  [rsp+160h+pExceptionObject], xmm0
0x1800381ae  mov     [rsp+160h+var_120], r15
0x1800381b3  mov     [rsp+160h+var_118], ebx
0x1800381b7  mov     [rsp+160h+var_114], 0FFFFFFFFh
0x1800381bf  mov     [rsp+160h+var_110], 263h
0x1800381c7  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800381ce  lea     rcx, [rsp+160h+pExceptionObject]; pExceptionObject
0x1800381d3  call    _CxxThrowException_0
```
