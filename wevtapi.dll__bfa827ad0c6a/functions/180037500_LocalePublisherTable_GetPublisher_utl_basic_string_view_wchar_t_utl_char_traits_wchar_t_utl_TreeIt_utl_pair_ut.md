# LocalePublisherTable::GetPublisher(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::_TreeIt<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,LocalePublisherTable::_PublisherRecord>> &)

- ea: `0x180037500`
- end: `0x1800377a0`
- name: `?GetPublisher@LocalePublisherTable@@IEAA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@AEAV?$_TreeIt@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@U_PublisherRecord@LocalePublisherTable@@@utl@@@3@@Z`
- size: `672`
- prototype: `__int64 __fastcall(LocalePublisherTable::_PublisherRecord *this)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180017ef4`
- `0x180028478`

## callees

- `0x180003ed0`
- `0x180009d80`
- `0x18000a2d0`
- `0x18000a558`
- `0x18000a724`
- `0x18000c374`
- `0x1800137f0`
- `0x180023548`
- `0x18003608c`
- `0x1800363d0`
- `0x180036db0`
- `0x180037500`
- `0x1800377a8`
- `0x180038fa4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003759a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003759a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall LocalePublisherTable::GetPublisher(
        LocalePublisherTable::_PublisherRecord **this,
        __int64 *a2,
        __int64 *a3)
{
  char *v6; // rbx
  __int64 v7; // rax
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r9
  __int64 v11; // r8
  __int64 v12; // rcx
  unsigned int v13; // r14d
  LocalePublisherTable::_PublisherRecord *v14; // r10
  __int64 v15; // r9
  __int64 v16; // r9
  LocalePublisherTable::_PublisherRecord *v17; // r10
  int v18; // eax
  LocalePublisherTable::_PublisherRecord *v20; // [rsp+30h] [rbp-49h] BYREF
  __int64 v21; // [rsp+38h] [rbp-41h]
  __int128 v22; // [rsp+40h] [rbp-39h] BYREF
  _BYTE v23[32]; // [rsp+50h] [rbp-29h] BYREF
  __int128 pExceptionObject; // [rsp+70h] [rbp-9h] BYREF
  __int64 v25; // [rsp+80h] [rbp+7h]
  int v26; // [rsp+88h] [rbp+Fh]
  int v27; // [rsp+8Ch] [rbp+13h]
  int v28; // [rsp+90h] [rbp+17h]
  unsigned int v29; // [rsp+E0h] [rbp+67h] BYREF

  Buffer::Buffer((Buffer *)v23, 0, 0, 1);
  v6 = (char *)(this + 40);
  if ( this[42] == (LocalePublisherTable::_PublisherRecord *)(this + 40) )
  {
    *a3 = (__int64)v6;
  }
  else
  {
    v7 = utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,LocalePublisherTable::_PublisherRecord>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,LocalePublisherTable::_PublisherRecord>>,0>::_LowerBoundNonEmpty<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>>(
           this + 40,
           a2);
    *a3 = v7;
    if ( (char *)v7 != v6 )
    {
      v8 = a2[1];
      v9 = *(_QWORD *)(v7 + 24);
      v10 = (*(_QWORD *)(v7 + 32) - v9) >> 1;
      if ( (v8 | (unsigned __int64)v10) > 0x7FFFFFFF )
        __int2c();
      v11 = 2;
      if ( v9 )
        v11 = *(_QWORD *)(v7 + 24);
      v12 = 2;
      if ( *a2 )
        v12 = *a2;
      if ( CompareStringOrdinal((LPCWCH)v12, v8, (LPCWCH)v11, v10, 1) != 1 )
        goto LABEL_28;
    }
  }
  v13 = 0;
  do
  {
    ++v13;
    Buffer::SetCurrentIndex((Buffer *)v23, 0);
    v29 = 0;
    if ( !RecordCache::GetRecord(this[44], v13, (struct Buffer *)v23, &v29) )
    {
      if ( !v29 )
      {
        Buffer::~Buffer((Buffer *)v23);
        return 0;
      }
      Buffer::SetSize((Buffer *)v23, v29);
      if ( !RecordCache::GetRecord(this[44], v13, (struct Buffer *)v23, &v29) )
      {
        if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids, 1168);
        }
        pExceptionObject = 0;
        v25 = 0;
        v26 = 1168;
        v27 = -1;
        v28 = 1104;
        throw (EvtException *)&pExceptionObject;
      }
    }
    Buffer::SetCurrentIndex((Buffer *)v23, 0);
    LocalePublisherTable::_PublisherRecord::Deserialize(
      (LocalePublisherTable::_PublisherRecord *)this,
      (struct Buffer *)v23);
    v14 = *this;
    v15 = (this[1] - *this) >> 1;
    v22 = *(_OWORD *)a2;
    v20 = v14;
    v21 = v15;
  }
  while ( !(unsigned __int8)tlx::operator==<wchar_t,utl::char_traits<wchar_t>>(&v20, &v22) );
  v20 = v17;
  v21 = v16;
  v18 = MakeOrThrowOOM(&pExceptionObject, &v20);
  *a3 = *(_QWORD *)utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,LocalePublisherTable::_PublisherRecord>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,LocalePublisherTable::_PublisherRecord>>,0>::_TryEmplace<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,LocalePublisherTable::_PublisherRecord>(
                     (int)this + 320,
                     (unsigned int)&v22,
                     *a3,
                     v18,
                     (__int64)this);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(&pExceptionObject);
  if ( !*a3 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids, 14);
    }
    pExceptionObject = 0;
    v25 = 0;
    v26 = 14;
    v27 = -1;
    v28 = 1119;
    throw (EvtException *)&pExceptionObject;
  }
LABEL_28:
  Buffer::~Buffer((Buffer *)v23);
  return 1;
}

```

## disassembly

```asm
0x180037500  push    rbp
0x180037502  push    rbx
0x180037503  push    rsi
0x180037504  push    rdi
0x180037505  push    r14
0x180037507  push    r15
0x180037509  lea     rbp, [rsp-2Fh]
0x18003750e  sub     rsp, 0A8h
0x180037515  mov     rdi, r8
0x180037518  mov     r15, rdx
0x18003751b  mov     rsi, rcx
0x18003751e  mov     r9b, 1; bool
0x180037521  xor     r8d, r8d; unsigned int
0x180037524  xor     edx, edx; unsigned __int8 *
0x180037526  lea     rcx, [rbp+57h+var_80]; this
0x18003752a  call    ??0Buffer@@QEAA@PEBEK_N@Z; Buffer::Buffer(uchar const *,ulong,bool)
0x18003752f  nop
0x180037530  lea     rbx, [rsi+140h]
0x180037537  mov     r14d, 2
0x18003753d  cmp     [rbx+10h], rbx
0x180037541  jnz     short loc_180037548
0x180037543  mov     [rdi], rbx
0x180037546  jmp     short loc_1800375A9
0x180037548  mov     rdx, r15
0x18003754b  mov     rcx, rbx
0x18003754e  call    ??$_LowerBoundNonEmpty@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@?$_Tree@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@U_PublisherRecord@LocalePublisherTable@@@2@Uistring_less_ordinal@tlx@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@U_PublisherRecord@LocalePublisherTable@@@utl@@@2@$0A@@utl@@AEBAPEAU?$_TreeNode@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@U_PublisherRecord@LocalePublisherTable@@@utl@@@1@AEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@1@@Z; utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,LocalePublisherTable::_PublisherRecord>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,LocalePublisherTable::_PublisherRecord>>,0>::_LowerBoundNonEmpty<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>>(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x180037553  mov     [rdi], rax
0x180037556  cmp     rax, rbx
0x180037559  jz      short loc_1800375A9
0x18003755b  mov     rdx, [r15+8]; cchCount1
0x18003755f  mov     rcx, [rax+18h]
0x180037563  mov     r9, [rax+20h]
0x180037567  sub     r9, rcx
0x18003756a  sar     r9, 1; cchCount2
0x18003756d  mov     rax, r9
0x180037570  or      rax, rdx
0x180037573  cmp     rax, 7FFFFFFFh
0x180037579  jbe     short loc_18003757D
0x18003757b  int     2Ch; Windows NT - assertion failure
0x18003757d  mov     r8, r14
0x180037580  test    rcx, rcx
0x180037583  cmovnz  r8, rcx; lpString2
0x180037587  mov     rcx, r14
0x18003758a  cmp     qword ptr [r15], 0
0x18003758e  cmovnz  rcx, [r15]; lpString1
0x180037592  mov     [rsp+0D0h+bIgnoreCase], 1; bIgnoreCase
0x18003759a  call    cs:__imp_CompareStringOrdinal
0x1800375a0  cmp     eax, 1
0x1800375a3  jnz     loc_180037785
0x1800375a9  xor     r14d, r14d
0x1800375ac  inc     r14d
0x1800375af  xor     edx, edx; unsigned int
0x1800375b1  lea     rcx, [rbp+57h+var_80]; this
0x1800375b5  call    ?SetCurrentIndex@Buffer@@UEAAXK@Z; Buffer::SetCurrentIndex(ulong)
0x1800375ba  mov     [rbp+57h+arg_0], 0
0x1800375c1  lea     r9, [rbp+57h+arg_0]; unsigned int *
0x1800375c5  lea     r8, [rbp+57h+var_80]; struct Buffer *
0x1800375c9  mov     edx, r14d; unsigned int
0x1800375cc  mov     rcx, [rsi+160h]; this
0x1800375d3  call    ?GetRecord@RecordCache@@QEAA_NKAEAVBuffer@@AEAK@Z; RecordCache::GetRecord(ulong,Buffer &,ulong &)
0x1800375d8  test    al, al
0x1800375da  jnz     short loc_18003760F
0x1800375dc  mov     edx, [rbp+57h+arg_0]; unsigned int
0x1800375df  test    edx, edx
0x1800375e1  jz      loc_180037778
0x1800375e7  lea     rcx, [rbp+57h+var_80]; this
0x1800375eb  call    ?SetSize@Buffer@@QEAAXK@Z; Buffer::SetSize(ulong)
0x1800375f0  lea     r9, [rbp+57h+arg_0]; unsigned int *
0x1800375f4  lea     r8, [rbp+57h+var_80]; struct Buffer *
0x1800375f8  mov     edx, r14d; unsigned int
0x1800375fb  mov     rcx, [rsi+160h]; this
0x180037602  call    ?GetRecord@RecordCache@@QEAA_NKAEAVBuffer@@AEAK@Z; RecordCache::GetRecord(ulong,Buffer &,ulong &)
0x180037607  test    al, al
0x180037609  jz      loc_18003770A
0x18003760f  xor     edx, edx; unsigned int
0x180037611  lea     rcx, [rbp+57h+var_80]; this
0x180037615  call    ?SetCurrentIndex@Buffer@@UEAAXK@Z; Buffer::SetCurrentIndex(ulong)
0x18003761a  lea     rdx, [rbp+57h+var_80]; struct Buffer *
0x18003761e  mov     rcx, rsi; this
0x180037621  call    ?Deserialize@_PublisherRecord@LocalePublisherTable@@QEAAXAEAVBuffer@@@Z; LocalePublisherTable::_PublisherRecord::Deserialize(Buffer &)
0x180037626  mov     r10, [rsi]
0x180037629  mov     r9, [rsi+8]
0x18003762d  sub     r9, r10
0x180037630  sar     r9, 1
0x180037633  movaps  xmm0, xmmword ptr [r15]
0x180037637  movdqa  [rbp+57h+var_90], xmm0
0x18003763c  mov     [rbp+57h+var_A0], r10
0x180037640  mov     [rbp+57h+var_98], r9
0x180037644  lea     rdx, [rbp+57h+var_90]
0x180037648  lea     rcx, [rbp+57h+var_A0]
0x18003764c  call    ??$?8_WU?$char_traits@_W@utl@@@tlx@@YA_NV?$basic_cstring_view@_WU?$char_traits@_W@utl@@@0@0@Z; tlx::operator==<wchar_t,utl::char_traits<wchar_t>>(tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>,tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>)
0x180037651  test    al, al
0x180037653  jz      loc_1800375AC
0x180037659  mov     [rbp+57h+var_A0], r10
0x18003765d  mov     [rbp+57h+var_98], r9
0x180037661  lea     rdx, [rbp+57h+var_A0]
0x180037665  lea     rcx, [rbp+57h+pExceptionObject]
0x180037669  call    ?MakeOrThrowOOM@@YA?AV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$basic_string_view@_WU?$char_traits@_W@utl@@@2@@Z; MakeOrThrowOOM(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x18003766e  mov     qword ptr [rsp+0D0h+bIgnoreCase], rsi
0x180037673  mov     r9, rax
0x180037676  mov     r8, [rdi]
0x180037679  lea     rdx, [rbp+57h+var_90]
0x18003767d  mov     rcx, rbx
0x180037680  call    ??$_TryEmplace@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@U_PublisherRecord@LocalePublisherTable@@@?$_Tree@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@U_PublisherRecord@LocalePublisherTable@@@2@Uistring_less_ordinal@tlx@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@U_PublisherRecord@LocalePublisherTable@@@utl@@@2@$0A@@utl@@IEAA?AU?$pair@V?$_TreeIt@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@U_PublisherRecord@LocalePublisherTable@@@utl@@@utl@@_N@1@PEAU?$_TreeNode@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@U_PublisherRecord@LocalePublisherTable@@@utl@@@1@$$QEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@1@$$QEAU_PublisherRecord@LocalePublisherTable@@@Z; utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,LocalePublisherTable::_PublisherRecord>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,LocalePublisherTable::_PublisherRecord>>,0>::_TryEmplace<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,LocalePublisherTable::_PublisherRecord>(utl::_TreeNode<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,LocalePublisherTable::_PublisherRecord>> *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&,LocalePublisherTable::_PublisherRecord &&)
0x180037685  mov     rcx, [rax]
0x180037688  mov     [rdi], rcx
0x18003768b  lea     rcx, [rbp+57h+pExceptionObject]
0x18003768f  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x180037694  cmp     qword ptr [rdi], 0
0x180037698  jnz     loc_180037785
0x18003769e  lea     rax, WPP_GLOBAL_Control
0x1800376a5  mov     ebx, 0Eh
0x1800376aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800376b1  cmp     rcx, rax
0x1800376b4  jz      short loc_1800376D8
0x1800376b6  test    byte ptr [rcx+1Ch], 1
0x1800376ba  jz      short loc_1800376D8
0x1800376bc  cmp     byte ptr [rcx+19h], 2
0x1800376c0  jb      short loc_1800376D8
0x1800376c2  lea     edx, [rbx+24h]
0x1800376c5  mov     r9d, ebx
0x1800376c8  lea     r8, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids
0x1800376cf  mov     rcx, [rcx+10h]
0x1800376d3  call    WPP_SF_D
0x1800376d8  xorps   xmm0, xmm0
0x1800376db  movdqu  [rbp+57h+pExceptionObject], xmm0
0x1800376e0  mov     [rbp+57h+var_50], 0
0x1800376e8  mov     [rbp+57h+var_48], ebx
0x1800376eb  mov     [rbp+57h+var_44], 0FFFFFFFFh
0x1800376f2  mov     [rbp+57h+var_40], 45Fh
0x1800376f9  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180037700  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180037704  call    _CxxThrowException_0
0x18003770a  lea     rax, WPP_GLOBAL_Control
0x180037711  mov     ebx, 490h
0x180037716  mov     rcx, cs:WPP_GLOBAL_Control
0x18003771d  cmp     rcx, rax
0x180037720  jz      short loc_180037746
0x180037722  test    byte ptr [rcx+1Ch], 1
0x180037726  jz      short loc_180037746
0x180037728  cmp     byte ptr [rcx+19h], 2
0x18003772c  jb      short loc_180037746
0x18003772e  mov     edx, 31h ; '1'
0x180037733  mov     r9d, ebx
0x180037736  lea     r8, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids
0x18003773d  mov     rcx, [rcx+10h]
0x180037741  call    WPP_SF_D
0x180037746  xorps   xmm0, xmm0
0x180037749  movdqu  [rbp+57h+pExceptionObject], xmm0
0x18003774e  mov     [rbp+57h+var_50], 0
0x180037756  mov     [rbp+57h+var_48], ebx
0x180037759  mov     [rbp+57h+var_44], 0FFFFFFFFh
0x180037760  mov     [rbp+57h+var_40], 450h
0x180037767  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18003776e  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180037772  call    _CxxThrowException_0
0x180037778  lea     rcx, [rbp+57h+var_80]; this
0x18003777c  call    ??1Buffer@@UEAA@XZ; Buffer::~Buffer(void)
0x180037781  xor     al, al
0x180037783  jmp     short loc_180037790
0x180037785  lea     rcx, [rbp+57h+var_80]; this
0x180037789  call    ??1Buffer@@UEAA@XZ; Buffer::~Buffer(void)
0x18003778e  mov     al, 1
0x180037790  add     rsp, 0A8h
0x180037797  pop     r15
0x180037799  pop     r14
0x18003779b  pop     rdi
0x18003779c  pop     rsi
0x18003779d  pop     rbx
0x18003779e  pop     rbp
0x18003779f  retn
```
