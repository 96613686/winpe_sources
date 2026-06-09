# ChannelManager::GetChannel(tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>,bool,ulong)

- ea: `0x18002f1b0`
- end: `0x18002f967`
- name: `?GetChannel@ChannelManager@@AEAA?AV?$AutoRef@VChannel@@@wmi@@V?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@_NK@Z`
- size: `1975`
- prototype: `__int64 __usercall@<rax>(PSRWLOCK SRWLock@<rcx>, unsigned int)`
- caller_count: `16`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004f2c`
- `0x180017bb8`
- `0x18002f0e0`
- `0x180047c6c`
- `0x180048930`
- `0x180057f1c`
- `0x18005afd8`
- `0x18005c6fc`
- `0x180061500`
- `0x1800620ac`
- `0x180063060`
- `0x180063238`
- `0x1800660cc`
- `0x180091a68`
- `0x1800982f4`
- `0x18009f6d8`

## callees

- `0x180002ae4`
- `0x180016250`
- `0x180017b60`
- `0x180026e90`
- `0x18002b310`
- `0x18002f1b0`
- `0x180043a88`
- `0x180043c94`
- `0x18004d1d8`
- `0x180057e30`
- `0x180058b48`
- `0x180059410`
- `0x180059440`
- `0x1800741e4`
- `0x180084018`
- `0x180084f08`
- `0x18008d8a8`
- `0x180092008`
- `0x18009aee0`
- `0x18009f870`
- `0x1800d334c`
- `0x1800dd010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f64b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f65e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f675`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f64b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f65e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f675`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002f221`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002f221`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002f418`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002f4c0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002f418`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002f4c0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002f28f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002f3ad`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002f28f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002f3ad`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
Channel **__fastcall ChannelManager::GetChannel(PSRWLOCK SRWLock, Channel **a2, __int64 *a3, char a4, unsigned int a5)
{
  __int64 *v5; // rdi
  Channel **v6; // r12
  PSRWLOCK v7; // r14
  RTL_SRWLOCK *v8; // r13
  RTL_SRWLOCK *v9; // r15
  RTL_SRWLOCK *Ptr; // rbx
  __int64 v11; // r14
  __int64 v12; // rdi
  __int64 v13; // rsi
  PVOID v14; // r9
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rcx
  __int64 v18; // rax
  PVOID v19; // rcx
  __int64 v20; // r9
  __int64 v21; // r8
  char v22; // di
  volatile signed __int32 *v23; // rbx
  Channel *v24; // rcx
  unsigned int v25; // ebx
  unsigned int v26; // ebx
  RTL_SRWLOCK *v28; // rax
  __int64 *v29; // rsi
  __int64 v30; // rdi
  __int64 v31; // rsi
  Channel *v32; // rax
  __int64 CurrentChannelPolicy; // rax
  Channel *v34; // rdi
  struct ChannelConfigSnapshot *v35; // rax
  __int128 v37; // [rsp+40h] [rbp-338h] BYREF
  _QWORD v38[2]; // [rsp+50h] [rbp-328h] BYREF
  int v39; // [rsp+60h] [rbp-318h]
  PSRWLOCK SRWLocka; // [rsp+68h] [rbp-310h] BYREF
  unsigned int v41; // [rsp+70h] [rbp-308h]
  char v42; // [rsp+78h] [rbp-300h]
  Channel **v43; // [rsp+80h] [rbp-2F8h]
  _QWORD v44[4]; // [rsp+90h] [rbp-2E8h] BYREF
  _QWORD pExceptionObject[3]; // [rsp+B0h] [rbp-2C8h] BYREF
  int v46; // [rsp+C8h] [rbp-2B0h]
  __int64 v47; // [rsp+CCh] [rbp-2ACh]
  char v48; // [rsp+D4h] [rbp-2A4h]
  __int128 v49; // [rsp+D8h] [rbp-2A0h] BYREF
  __int64 v50; // [rsp+E8h] [rbp-290h]
  int v51; // [rsp+F0h] [rbp-288h]
  int v52; // [rsp+F4h] [rbp-284h]
  int v53; // [rsp+F8h] [rbp-280h]
  __int128 v54; // [rsp+100h] [rbp-278h] BYREF
  __int64 v55; // [rsp+110h] [rbp-268h]
  unsigned int v56; // [rsp+118h] [rbp-260h]
  int v57; // [rsp+11Ch] [rbp-25Ch]
  int v58; // [rsp+120h] [rbp-258h]
  __int128 v59; // [rsp+128h] [rbp-250h] BYREF
  __int64 v60; // [rsp+138h] [rbp-240h]
  int v61; // [rsp+140h] [rbp-238h]
  int v62; // [rsp+144h] [rbp-234h]
  int v63; // [rsp+148h] [rbp-230h]
  HKEY v64; // [rsp+150h] [rbp-228h] BYREF
  HKEY v65; // [rsp+158h] [rbp-220h]
  HKEY hKey; // [rsp+160h] [rbp-218h]
  char v67[32]; // [rsp+170h] [rbp-208h] BYREF
  _BYTE v68[32]; // [rsp+190h] [rbp-1E8h] BYREF
  _BYTE v69[32]; // [rsp+1B0h] [rbp-1C8h] BYREF
  char v70; // [rsp+1D0h] [rbp-1A8h]
  _BYTE v71[32]; // [rsp+1E0h] [rbp-198h] BYREF
  _BYTE v72[48]; // [rsp+200h] [rbp-178h] BYREF
  char v73[56]; // [rsp+230h] [rbp-148h] BYREF
  char v74[112]; // [rsp+268h] [rbp-110h] BYREF
  char v75[32]; // [rsp+2D8h] [rbp-A0h] BYREF
  char v76[56]; // [rsp+2F8h] [rbp-80h] BYREF

  v5 = a3;
  v38[0] = a3;
  v6 = a2;
  v43 = a2;
  v7 = SRWLock;
  SRWLocka = SRWLock;
  v44[2] = a2;
  v44[0] = a3;
  *a2 = 0;
  v39 = 1;
  *(_QWORD *)&v37 = SRWLock;
  AcquireSRWLockExclusive(SRWLock);
  v8 = v7 + 6;
  if ( v7[8].Ptr == &v7[6] )
    goto LABEL_14;
  v9 = v7 + 6;
  Ptr = (RTL_SRWLOCK *)v8->Ptr;
  v11 = *v5;
  v12 = v5[1];
  v13 = 2;
  do
  {
    v14 = Ptr[3].Ptr;
    v15 = ((char *)Ptr[4].Ptr - (char *)v14) >> 1;
    if ( (v12 | (unsigned __int64)v15) > 0x7FFFFFFF )
      __int2c();
    v16 = 2;
    if ( v11 )
      v16 = v11;
    v17 = 2;
    if ( v14 )
      v17 = (__int64)Ptr[3].Ptr;
    if ( CompareStringOrdinal((LPCWCH)v17, v15, (LPCWCH)v16, v12, 1) == 1 )
    {
      v18 = 2;
    }
    else
    {
      v9 = Ptr;
      v18 = 1;
    }
    Ptr = (RTL_SRWLOCK *)Ptr[v18].Ptr;
  }
  while ( Ptr != (RTL_SRWLOCK *)&utl::_TreeSentinel );
  v6 = v43;
  if ( v9 == v8 )
    goto LABEL_13;
  v19 = v9[3].Ptr;
  v20 = ((char *)v9[4].Ptr - (char *)v19) >> 1;
  if ( (v12 | (unsigned __int64)v20) > 0x7FFFFFFF )
    __int2c();
  v21 = 2;
  if ( v19 )
    v21 = (__int64)v9[3].Ptr;
  if ( v11 )
    v13 = v11;
  if ( CompareStringOrdinal((LPCWCH)v13, v12, (LPCWCH)v21, v20, 1) == 1 )
  {
LABEL_13:
    v5 = (__int64 *)v38[0];
    v7 = SRWLocka;
LABEL_14:
    if ( !a4 )
    {
      if ( (a5 & 0x20) == 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v44[0] = *v5;
          v44[1] = v5[1];
          WPP_SF__utlwsv_D(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            19,
            (unsigned int)&WPP_a49f58dc00e136e65a5fe002c08ed3b5_Traceguids,
            (unsigned int)v44,
            159);
        }
        pExceptionObject[0] = &word_1800EC961;
        pExceptionObject[1] = 0;
        pExceptionObject[2] = 0;
        v46 = 15007;
        v47 = -1;
        v48 = 0;
        throw (EvtException *)pExceptionObject;
      }
LABEL_36:
      ReleaseSRWLockExclusive(v7);
      return v6;
    }
    v26 = a5;
    goto LABEL_81;
  }
  v22 = 0;
  v23 = (volatile signed __int32 *)v9[7].Ptr;
  if ( v23 )
    _InterlockedIncrement(v23 + 2);
  v24 = *v43;
  if ( *v43 && _InterlockedExchangeAdd((volatile signed __int32 *)v24 + 2, 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(Channel *, __int64))v24)(v24, 1);
  *v43 = (Channel *)v23;
  v25 = *((_DWORD *)v23 + 20);
  if ( v25 )
  {
    if ( v25 != -1 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_a49f58dc00e136e65a5fe002c08ed3b5_Traceguids, v25);
      }
      v54 = 0;
      v55 = 0;
      v56 = v25;
      v57 = -1;
      v58 = 339;
      throw (EvtException *)&v54;
    }
    if ( !a4 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_a49f58dc00e136e65a5fe002c08ed3b5_Traceguids, 15007);
      }
      v49 = 0;
      v50 = 0;
      v51 = 15007;
      v52 = -1;
      v53 = 335;
      throw (EvtException *)&v49;
    }
    v26 = a5 | 4;
    v7 = SRWLocka;
LABEL_81:
    v22 = 1;
    goto LABEL_34;
  }
  v26 = a5;
  v7 = SRWLocka;
LABEL_34:
  if ( LOBYTE(v7[11].Ptr) || !v22 && (v26 & 0x10) == 0 )
  {
    if ( !*v6
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v37 = *(_OWORD *)v38[0];
      WPP_SF__utlwsv_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_a49f58dc00e136e65a5fe002c08ed3b5_Traceguids, &v37);
    }
    goto LABEL_36;
  }
  if ( *v6 )
  {
    v29 = (__int64 *)v38[0];
  }
  else
  {
    v28 = (RTL_SRWLOCK *)operator new(0x370u);
    SRWLocka = v28;
    v29 = (__int64 *)v38[0];
    if ( v28 )
    {
      v38[0] = *(_QWORD *)v38[0];
      v38[1] = v29[1];
      v28 = (RTL_SRWLOCK *)Channel::Channel(v28, v7, v38);
    }
    wmi::AutoRef<TermType>::operator=(v6, v28);
    if ( !*(_QWORD *)utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,wmi::AutoRef<Channel>>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,wmi::AutoRef<Channel>>>,0>::emplace<tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>> &,wmi::AutoRef<Channel> &,0>(
                       v8,
                       &SRWLocka,
                       v29,
                       v6) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_a49f58dc00e136e65a5fe002c08ed3b5_Traceguids, 14);
      }
      v59 = 0;
      v60 = 0;
      v61 = 14;
      v62 = -1;
      v63 = 389;
      throw (EvtException *)&v59;
    }
  }
  ReleaseSRWLockExclusive(v7);
  v30 = v29[1];
  v31 = *v29;
  *(_QWORD *)&v37 = v31;
  *((_QWORD *)&v37 + 1) = v30;
  ChannelConfigReader::ChannelConfigReader(&v64, &v37, -1);
  v32 = *v6;
  *(_QWORD *)&v37 = v32;
  SRWLocka = (PSRWLOCK)v32;
  DWORD2(v37) = v26;
  if ( v32 )
  {
    _InterlockedIncrement((volatile signed __int32 *)v32 + 2);
    _InterlockedIncrement((volatile signed __int32 *)v32 + 2);
  }
  v41 = v26;
  v42 = 1;
  wmi::AutoRef<TermType>::Release(&v37);
  *(_QWORD *)&v37 = v31;
  *((_QWORD *)&v37 + 1) = v30;
  CurrentChannelPolicy = PolicyManager::GetCurrentChannelPolicy((PSRWLOCK)v7[3].Ptr, v71);
  if ( *(_BYTE *)(CurrentChannelPolicy + 64) )
  {
    if ( v70 )
    {
      ChannelPolicy::operator=(v68, CurrentChannelPolicy);
    }
    else
    {
      ChannelPolicy::ChannelPolicy(v68, CurrentChannelPolicy);
      v70 = 1;
    }
  }
  else if ( v70 )
  {
    Buffer::~Buffer((Buffer *)v69);
    utl::set<void *,utl::less<void *>,utl::allocator<void *>>::~set<void *,utl::less<void *>,utl::allocator<void *>>(v68);
    v70 = 0;
  }
  if ( v72[32] )
  {
    Buffer::~Buffer((Buffer *)v72);
    utl::set<void *,utl::less<void *>,utl::allocator<void *>>::~set<void *,utl::less<void *>,utl::allocator<void *>>(v71);
  }
  v34 = *v6;
  v37 = 0;
  v35 = (struct ChannelConfigSnapshot *)ChannelConfigSnapshot::ChannelConfigSnapshot(v73, &v64, &v37);
  Channel::AssertConfig(v34, v35, v26);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v76);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v75);
  ChannelLogConfigData::~ChannelLogConfigData((ChannelLogConfigData *)v74);
  v42 = 0;
  wmi::AutoRef<TermType>::Release(&SRWLocka);
  if ( v70 )
  {
    Buffer::~Buffer((Buffer *)v69);
    utl::set<void *,utl::less<void *>,utl::allocator<void *>>::~set<void *,utl::less<void *>,utl::allocator<void *>>(v68);
  }
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v67);
  if ( hKey )
    RegCloseKey(hKey);
  if ( v65 )
    RegCloseKey(v65);
  if ( v64 )
    RegCloseKey(v64);
  return v6;
}

```

## disassembly

```asm
0x18002f1b0  push    rbx
0x18002f1b2  push    rsi
0x18002f1b3  push    rdi
0x18002f1b4  push    r12
0x18002f1b6  push    r13
0x18002f1b8  push    r14
0x18002f1ba  push    r15
0x18002f1bc  sub     rsp, 340h
0x18002f1c3  mov     rax, cs:__security_cookie
0x18002f1ca  xor     rax, rsp
0x18002f1cd  mov     [rsp+378h+var_48], rax
0x18002f1d5  mov     [rsp+378h+var_348], r9b
0x18002f1da  mov     rdi, r8
0x18002f1dd  mov     [rsp+378h+var_328], r8
0x18002f1e2  mov     r12, rdx
0x18002f1e5  mov     [rsp+378h+var_2F8], rdx
0x18002f1ed  mov     r14, rcx
0x18002f1f0  mov     [rsp+378h+SRWLock], rcx
0x18002f1f5  mov     [rsp+378h+var_2D8], rdx
0x18002f1fd  mov     [rsp+378h+var_2E8], r8
0x18002f205  mov     [rsp+378h+var_318], 1
0x18002f20d  mov     qword ptr [rdx], 0
0x18002f214  mov     [rsp+378h+var_318], 1
0x18002f21c  mov     qword ptr [rsp+378h+var_338], rcx
0x18002f221  call    cs:__imp_AcquireSRWLockExclusive
0x18002f227  nop
0x18002f228  lea     r13, [r14+30h]
0x18002f22c  cmp     [r13+10h], r13
0x18002f230  jz      loc_18002F2CA
0x18002f236  mov     r15, r13
0x18002f239  mov     rbx, [r13+0]
0x18002f23d  mov     r14, [rdi]
0x18002f240  mov     rdi, [rdi+8]
0x18002f244  mov     esi, 2
0x18002f249  lea     r12, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x18002f250  mov     r9, [rbx+18h]
0x18002f254  mov     rdx, [rbx+20h]
0x18002f258  sub     rdx, r9
0x18002f25b  sar     rdx, 1; cchCount1
0x18002f25e  mov     rax, rdx
0x18002f261  or      rax, rdi
0x18002f264  cmp     rax, 7FFFFFFFh
0x18002f26a  ja      loc_18002F368
0x18002f270  mov     r8, rsi
0x18002f273  test    r14, r14
0x18002f276  cmovnz  r8, r14; lpString2
0x18002f27a  mov     rcx, rsi
0x18002f27d  test    r9, r9
0x18002f280  cmovnz  rcx, r9; lpString1
0x18002f284  mov     [rsp+378h+bIgnoreCase], 1; bIgnoreCase
0x18002f28c  mov     r9d, edi; cchCount2
0x18002f28f  call    cs:__imp_CompareStringOrdinal
0x18002f295  cmp     eax, 1
0x18002f298  jz      loc_18002F35E
0x18002f29e  mov     r15, rbx
0x18002f2a1  mov     eax, 8
0x18002f2a6  mov     rbx, [rbx+rax]
0x18002f2aa  cmp     rbx, r12
0x18002f2ad  jnz     short loc_18002F250
0x18002f2af  cmp     r15, r13
0x18002f2b2  mov     r12, [rsp+378h+var_2F8]
0x18002f2ba  jnz     loc_18002F36F
0x18002f2c0  mov     rdi, [rsp+378h+var_328]
0x18002f2c5  mov     r14, [rsp+378h+SRWLock]
0x18002f2ca  cmp     [rsp+378h+var_348], 0
0x18002f2cf  jnz     loc_18002F874
0x18002f2d5  test    byte ptr [rsp+378h+arg_20], 20h
0x18002f2dd  jnz     loc_18002F415
0x18002f2e3  lea     rax, WPP_GLOBAL_Control
0x18002f2ea  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f2f1  cmp     rcx, rax
0x18002f2f4  jz      short loc_18002F303
0x18002f2f6  test    dword ptr [rcx+1Ch], 800h
0x18002f2fd  jnz     loc_18002F91B
0x18002f303  lea     rax, word_1800EC961
0x18002f30a  mov     [rsp+378h+pExceptionObject], rax
0x18002f312  mov     [rsp+378h+var_2C0], 0
0x18002f31e  mov     [rsp+378h+var_2B8], 0
0x18002f32a  mov     [rsp+378h+var_2B0], 3A9Fh
0x18002f335  mov     [rsp+378h+var_2AC], 0FFFFFFFFFFFFFFFFh
0x18002f341  mov     [rsp+378h+var_2A4], 0
0x18002f349  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18002f350  lea     rcx, [rsp+378h+pExceptionObject]; pExceptionObject
0x18002f358  call    _CxxThrowException_0
0x18002f35e  mov     eax, 10h
0x18002f363  jmp     loc_18002F2A6
0x18002f368  int     2Ch; Windows NT - assertion failure
0x18002f36a  jmp     loc_18002F270
0x18002f36f  mov     rcx, [r15+18h]
0x18002f373  mov     r9, [r15+20h]
0x18002f377  sub     r9, rcx
0x18002f37a  sar     r9, 1; cchCount2
0x18002f37d  mov     rax, r9
0x18002f380  or      rax, rdi
0x18002f383  cmp     rax, 7FFFFFFFh
0x18002f389  ja      loc_18002F733
0x18002f38f  mov     r8, rsi
0x18002f392  test    rcx, rcx
0x18002f395  cmovnz  r8, rcx; lpString2
0x18002f399  test    r14, r14
0x18002f39c  cmovnz  rsi, r14
0x18002f3a0  mov     [rsp+378h+bIgnoreCase], 1; bIgnoreCase
0x18002f3a8  mov     edx, edi; cchCount1
0x18002f3aa  mov     rcx, rsi; lpString1
0x18002f3ad  call    cs:__imp_CompareStringOrdinal
0x18002f3b3  cmp     eax, 1
0x18002f3b6  jz      loc_18002F2C0
0x18002f3bc  xor     dil, dil
0x18002f3bf  mov     rbx, [r15+38h]
0x18002f3c3  test    rbx, rbx
0x18002f3c6  jz      short loc_18002F3CC
0x18002f3c8  lock inc dword ptr [rbx+8]
0x18002f3cc  mov     rcx, [r12]
0x18002f3d0  test    rcx, rcx
0x18002f3d3  jz      short loc_18002F3E8
0x18002f3d5  mov     eax, 0FFFFFFFFh
0x18002f3da  lock xadd [rcx+8], eax
0x18002f3df  cmp     eax, 1
0x18002f3e2  jz      loc_18002F680
0x18002f3e8  mov     [r12], rbx
0x18002f3ec  mov     ebx, [rbx+50h]
0x18002f3ef  test    ebx, ebx
0x18002f3f1  jnz     loc_18002F73A
0x18002f3f7  mov     ebx, [rsp+378h+arg_20]
0x18002f3fe  mov     r14, [rsp+378h+SRWLock]
0x18002f403  cmp     byte ptr [r14+58h], 0
0x18002f408  jz      short loc_18002F445
0x18002f40a  cmp     qword ptr [r12], 0
0x18002f40f  jz      loc_18002F69F
0x18002f415  mov     rcx, r14; SRWLock
0x18002f418  call    cs:__imp_ReleaseSRWLockExclusive
0x18002f41e  nop
0x18002f41f  mov     rax, r12
0x18002f422  mov     rcx, [rsp+378h+var_48]
0x18002f42a  xor     rcx, rsp; StackCookie
0x18002f42d  call    __security_check_cookie
0x18002f432  add     rsp, 340h
0x18002f439  pop     r15
0x18002f43b  pop     r14
0x18002f43d  pop     r13
0x18002f43f  pop     r12
0x18002f441  pop     rdi
0x18002f442  pop     rsi
0x18002f443  pop     rbx
0x18002f444  retn
0x18002f445  test    dil, dil
0x18002f448  jnz     short loc_18002F44F
0x18002f44a  test    bl, 10h
0x18002f44d  jz      short loc_18002F40A
0x18002f44f  cmp     qword ptr [r12], 0
0x18002f454  jnz     loc_18002F695
0x18002f45a  mov     ecx, 370h; dwBytes
0x18002f45f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002f464  mov     [rsp+378h+SRWLock], rax
0x18002f469  mov     rsi, [rsp+378h+var_328]
0x18002f46e  test    rax, rax
0x18002f471  jz      short loc_18002F495
0x18002f473  mov     rcx, [rsi]
0x18002f476  mov     [rsp+378h+var_328], rcx
0x18002f47b  mov     rcx, [rsi+8]
0x18002f47f  mov     [rsp+378h+var_320], rcx
0x18002f484  lea     r8, [rsp+378h+var_328]
0x18002f489  mov     rdx, r14
0x18002f48c  mov     rcx, rax
0x18002f48f  call    ??0Channel@@AEAA@PEAVChannelManager@@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; Channel::Channel(ChannelManager *,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x18002f494  nop
0x18002f495  mov     rdx, rax
0x18002f498  mov     rcx, r12
0x18002f49b  call    ??4?$AutoRef@VTermType@@@wmi@@QEAAAEAV01@PEAVTermType@@@Z; wmi::AutoRef<TermType>::operator=(TermType *)
0x18002f4a0  mov     r9, r12
0x18002f4a3  mov     r8, rsi
0x18002f4a6  lea     rdx, [rsp+378h+SRWLock]
0x18002f4ab  mov     rcx, r13
0x18002f4ae  call    ??$emplace@AEAV?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@AEAV?$AutoRef@VChannel@@@wmi@@$0A@@?$_Tree@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$AutoRef@VChannel@@@wmi@@@2@Uistring_less_ordinal@tlx@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$AutoRef@VChannel@@@wmi@@@utl@@@2@$0A@@utl@@QEAA?AU?$pair@V?$_TreeIt@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$AutoRef@VChannel@@@wmi@@@utl@@@utl@@_N@1@AEAV?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@AEAV?$AutoRef@VChannel@@@wmi@@@Z; utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,wmi::AutoRef<Channel>>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,wmi::AutoRef<Channel>>>,0>::emplace<tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>> &,wmi::AutoRef<Channel> &,0>(tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>> &,wmi::AutoRef<Channel> &)
0x18002f4b3  cmp     qword ptr [rax], 0
0x18002f4b7  jz      loc_18002F883
0x18002f4bd  mov     rcx, r14; SRWLock
0x18002f4c0  call    cs:__imp_ReleaseSRWLockExclusive
0x18002f4c6  mov     rdi, [rsi+8]
0x18002f4ca  mov     rsi, [rsi]
0x18002f4cd  mov     qword ptr [rsp+378h+var_338], rsi
0x18002f4d2  mov     qword ptr [rsp+378h+var_338+8], rdi
0x18002f4d7  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18002f4de  lea     rdx, [rsp+378h+var_338]
0x18002f4e3  lea     rcx, [rsp+378h+var_228]
0x18002f4eb  call    ??0ChannelConfigReader@@QEAA@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@PEAX@Z; ChannelConfigReader::ChannelConfigReader(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,void *)
0x18002f4f0  nop
0x18002f4f1  mov     rax, [r12]
0x18002f4f5  mov     qword ptr [rsp+378h+var_338], rax
0x18002f4fa  mov     [rsp+378h+SRWLock], rax
0x18002f4ff  mov     dword ptr [rsp+378h+var_338+8], ebx
0x18002f503  test    rax, rax
0x18002f506  jz      short loc_18002F510
0x18002f508  lock inc dword ptr [rax+8]
0x18002f50c  lock inc dword ptr [rax+8]
0x18002f510  mov     [rsp+378h+var_308], ebx
0x18002f514  mov     [rsp+378h+var_300], 1
0x18002f519  lea     rcx, [rsp+378h+var_338]
0x18002f51e  call    ?Release@?$AutoRef@VTermType@@@wmi@@QEAAXXZ; wmi::AutoRef<TermType>::Release(void)
0x18002f523  nop
0x18002f524  mov     qword ptr [rsp+378h+var_338], rsi
0x18002f529  mov     qword ptr [rsp+378h+var_338+8], rdi
0x18002f52e  lea     r8, [rsp+378h+var_338]
0x18002f533  lea     rdx, [rsp+378h+var_198]; void *
0x18002f53b  mov     rcx, [r14+18h]; SRWLock
0x18002f53f  call    ?GetCurrentChannelPolicy@PolicyManager@@QEBA?AV?$optional@VChannelPolicy@@@utl@@V?$basic_string_view@_WU?$char_traits@_W@utl@@@3@@Z; PolicyManager::GetCurrentChannelPolicy(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x18002f544  cmp     byte ptr [rax+40h], 0
0x18002f548  jnz     loc_18002F702
0x18002f54e  cmp     [rsp+378h+var_1A8], 0
0x18002f556  jz      short loc_18002F57A
0x18002f558  lea     rcx, [rsp+378h+var_1C8]; this
0x18002f560  call    ??1Buffer@@UEAA@XZ; Buffer::~Buffer(void)
0x18002f565  lea     rcx, [rsp+378h+var_1E8]
0x18002f56d  call    ??1?$set@PEAXU?$less@PEAX@utl@@V?$allocator@PEAX@2@@utl@@QEAA@XZ; utl::set<void *,utl::less<void *>,utl::allocator<void *>>::~set<void *,utl::less<void *>,utl::allocator<void *>>(void)
0x18002f572  mov     [rsp+378h+var_1A8], 0
0x18002f57a  cmp     [rsp+378h+var_158], 0
0x18002f582  jz      short loc_18002F59E
0x18002f584  lea     rcx, [rsp+378h+var_178]; this
0x18002f58c  call    ??1Buffer@@UEAA@XZ; Buffer::~Buffer(void)
0x18002f591  lea     rcx, [rsp+378h+var_198]
0x18002f599  call    ??1?$set@PEAXU?$less@PEAX@utl@@V?$allocator@PEAX@2@@utl@@QEAA@XZ; utl::set<void *,utl::less<void *>,utl::allocator<void *>>::~set<void *,utl::less<void *>,utl::allocator<void *>>(void)
0x18002f59e  mov     rdi, [r12]
0x18002f5a2  xorps   xmm0, xmm0
0x18002f5a5  movdqa  [rsp+378h+var_338], xmm0
0x18002f5ab  lea     r8, [rsp+378h+var_338]
0x18002f5b0  lea     rdx, [rsp+378h+var_228]
0x18002f5b8  lea     rcx, [rsp+378h+var_148]
0x18002f5c0  call    ??0ChannelConfigSnapshot@@QEAA@AEBVChannelConfigReader@@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; ChannelConfigSnapshot::ChannelConfigSnapshot(ChannelConfigReader const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x18002f5c5  nop
0x18002f5c6  mov     r8d, ebx; unsigned int
0x18002f5c9  mov     rdx, rax; struct ChannelConfigSnapshot *
0x18002f5cc  mov     rcx, rdi; this
0x18002f5cf  call    ?AssertConfig@Channel@@AEAAX$$QEAVChannelConfigSnapshot@@K@Z; Channel::AssertConfig(ChannelConfigSnapshot &&,ulong)
0x18002f5d4  nop
0x18002f5d5  lea     rcx, [rsp+378h+var_80]; void *
0x18002f5dd  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18002f5e2  lea     rcx, [rsp+378h+var_A0]; void *
0x18002f5ea  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18002f5ef  lea     rcx, [rsp+378h+var_110]; this
0x18002f5f7  call    ??1ChannelLogConfigData@@QEAA@XZ; ChannelLogConfigData::~ChannelLogConfigData(void)
0x18002f5fc  nop
0x18002f5fd  mov     [rsp+378h+var_300], 0
0x18002f602  lea     rcx, [rsp+378h+SRWLock]
0x18002f607  call    ?Release@?$AutoRef@VTermType@@@wmi@@QEAAXXZ; wmi::AutoRef<TermType>::Release(void)
0x18002f60c  nop
0x18002f60d  cmp     [rsp+378h+var_1A8], 0
0x18002f615  jz      short loc_18002F631
0x18002f617  lea     rcx, [rsp+378h+var_1C8]; this
0x18002f61f  call    ??1Buffer@@UEAA@XZ; Buffer::~Buffer(void)
0x18002f624  lea     rcx, [rsp+378h+var_1E8]
0x18002f62c  call    ??1?$set@PEAXU?$less@PEAX@utl@@V?$allocator@PEAX@2@@utl@@QEAA@XZ; utl::set<void *,utl::less<void *>,utl::allocator<void *>>::~set<void *,utl::less<void *>,utl::allocator<void *>>(void)
0x18002f631  lea     rcx, [rsp+378h+var_208]; void *
0x18002f639  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18002f63e  mov     rcx, [rsp+378h+hKey]; hKey
0x18002f646  test    rcx, rcx
0x18002f649  jz      short loc_18002F651
0x18002f64b  call    cs:__imp_RegCloseKey
0x18002f651  mov     rcx, [rsp+378h+var_220]; hKey
0x18002f659  test    rcx, rcx
0x18002f65c  jz      short loc_18002F664
0x18002f65e  call    cs:__imp_RegCloseKey
0x18002f664  mov     rcx, [rsp+378h+var_228]; hKey
0x18002f66c  test    rcx, rcx
0x18002f66f  jz      loc_18002F41F
0x18002f675  call    cs:__imp_RegCloseKey
0x18002f67b  jmp     loc_18002F41F
0x18002f680  mov     rax, [rcx]
0x18002f683  mov     edx, 1
0x18002f688  mov     rax, [rax]
0x18002f68b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f690  jmp     loc_18002F3E8
0x18002f695  mov     rsi, [rsp+378h+var_328]
0x18002f69a  jmp     loc_18002F4BD
0x18002f69f  lea     rax, WPP_GLOBAL_Control
0x18002f6a6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f6ad  cmp     rcx, rax
0x18002f6b0  jz      loc_18002F415
0x18002f6b6  test    dword ptr [rcx+1Ch], 800h
0x18002f6bd  jz      loc_18002F415
0x18002f6c3  cmp     byte ptr [rcx+19h], 2
0x18002f6c7  jb      loc_18002F415
0x18002f6cd  mov     rsi, [rsp+378h+var_328]
0x18002f6d2  mov     rax, [rsi]
0x18002f6d5  mov     qword ptr [rsp+378h+var_338], rax
0x18002f6da  mov     rax, [rsi+8]
0x18002f6de  mov     qword ptr [rsp+378h+var_338+8], rax
0x18002f6e3  mov     edx, 14h
0x18002f6e8  lea     r9, [rsp+378h+var_338]
0x18002f6ed  lea     r8, WPP_a49f58dc00e136e65a5fe002c08ed3b5_Traceguids
0x18002f6f4  mov     rcx, [rcx+10h]
0x18002f6f8  call    WPP_SF__utlwsv_
0x18002f6fd  jmp     loc_18002F415
0x18002f702  mov     rdx, rax
0x18002f705  lea     rcx, [rsp+378h+var_1E8]
0x18002f70d  cmp     [rsp+378h+var_1A8], 0
0x18002f715  jz      short loc_18002F721
0x18002f717  call    ??4ChannelPolicy@@QEAAAEAV0@$$QEAV0@@Z; ChannelPolicy::operator=(ChannelPolicy &&)
0x18002f71c  jmp     loc_18002F57A
0x18002f721  call    ??0ChannelPolicy@@QEAA@$$QEAV0@@Z; ChannelPolicy::ChannelPolicy(ChannelPolicy &&)
0x18002f726  mov     [rsp+378h+var_1A8], 1
  ... truncated ...
```
