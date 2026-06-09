# SubscriptionConfigWriter::SaveEventSources(_EC_SUBSCRIPTION_TYPE,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x18001718c`
- end: `0x180017509`
- name: `?SaveEventSources@SubscriptionConfigWriter@@AEAAXW4_EC_SUBSCRIPTION_TYPE@@AEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@1@Z`
- size: `893`
- prototype: `void __fastcall(HKEY *this, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800165c0`

## callees

- `0x18000195c`
- `0x180002510`
- `0x1800032dc`
- `0x180003a50`
- `0x180003cc8`
- `0x180003d48`
- `0x180003e6c`
- `0x180006898`
- `0x180010ba0`
- `0x180015844`
- `0x180015f78`
- `0x18001718c`
- `0x18001780c`
- `0x1800178f0`
- `0x1800189e8`
- `0x18001df44`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180017200`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180017200`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall SubscriptionConfigWriter::SaveEventSources(HKEY *this, int a2, __int64 a3, __int64 a4)
{
  unsigned int v7; // ebx
  SubscriptionConfigWriter *v8; // rcx
  __int64 v9; // rdx
  unsigned int v10; // ebx
  unsigned __int16 *v11; // rcx
  unsigned int i; // edi
  unsigned int v13; // r11d
  __int64 v14; // rdx
  __int64 v15; // rbx
  const unsigned __int16 *v16; // r8
  unsigned int j; // r14d
  unsigned int v18; // r13d
  __int64 v19; // rbx
  __int64 v20; // rsi
  __int64 v21; // r12
  __int64 v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rax
  SubscriptionConfigWriter *v25; // rcx
  const unsigned __int16 *v26; // r8
  DWORD dwOptions; // [rsp+20h] [rbp-E0h]
  HKEY phkResult[2]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v29[3]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v30[24]; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int64 v31; // [rsp+90h] [rbp-70h]
  __int64 v32; // [rsp+98h] [rbp-68h]
  __int64 v33; // [rsp+A0h] [rbp-60h]
  __int64 v34; // [rsp+B0h] [rbp-50h]
  __int64 v35; // [rsp+C8h] [rbp-38h] BYREF
  void **pExceptionObject; // [rsp+E0h] [rbp-20h] BYREF
  char v37; // [rsp+E8h] [rbp-18h]
  const char *v38; // [rsp+F0h] [rbp-10h]
  __int64 v39; // [rsp+F8h] [rbp-8h]
  __int64 v40; // [rsp+100h] [rbp+0h]
  unsigned int v41; // [rsp+108h] [rbp+8h]
  int v42; // [rsp+10Ch] [rbp+Ch]
  int v43; // [rsp+110h] [rbp+10h]
  _BYTE v44[8]; // [rsp+118h] [rbp+18h] BYREF
  __int64 (__fastcall *v45)(); // [rsp+120h] [rbp+20h]
  __int64 *v46; // [rsp+128h] [rbp+28h]
  _BYTE v47[48]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int64 v48; // [rsp+160h] [rbp+60h]
  __int64 v49; // [rsp+168h] [rbp+68h]
  _BYTE v50[16]; // [rsp+1B0h] [rbp+B0h] BYREF
  _BYTE v51[64]; // [rsp+1C0h] [rbp+C0h] BYREF
  DWORD dwDisposition; // [rsp+210h] [rbp+110h] BYREF
  __int64 v53; // [rsp+228h] [rbp+128h]

  v53 = a4;
  phkResult[0] = 0;
  dwDisposition = 0;
  v7 = RegCreateKeyExW(this[2], L"EventSources", 0, 0, 0, 0x2001Fu, 0, phkResult, &dwDisposition);
  if ( v7 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_995d7fc7f38b34c45f7188ba39a91f1d_Traceguids, v7);
    }
    v37 = 0;
    v38 = "admin\\wmi\\events\\forwarding\\collector\\store\\store.cpp";
    v39 = 0;
    v40 = 0;
    v41 = v7;
    v42 = -1;
    v43 = 878;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::GenericException *)&pExceptionObject;
  }
  _EventSources::_EventSources((_EventSources *)v47);
  _EventSources::_EventSources((_EventSources *)v29);
  if ( dwDisposition == 2 )
    SubscriptionConfigReader::GetEventSources((SubscriptionConfigReader *)this, (struct _EventSources *)v47, 0);
  SubscriptionReadData::GetEventSources((SubscriptionReadData *)(this + 3), (struct _EventSources *)v29);
  v44[0] = 0;
  v45 = ZeroStringVector;
  v46 = &v35;
  v9 = v33;
  if ( (v33 - v32) >> 5 )
  {
    v10 = 0;
    v8 = 0;
    do
    {
      if ( (*(_BYTE *)(v29[0] + 4LL * (_QWORD)v8) & 0xF) != 0 )
      {
        v11 = (unsigned __int16 *)(v32 + 32LL * (_QWORD)v8);
        if ( *((_QWORD *)v11 + 3) >= 8u )
          v11 = *(unsigned __int16 **)v11;
        ValidateRegKeyName(v11);
        v9 = v33;
      }
      v8 = (SubscriptionConfigWriter *)++v10;
    }
    while ( v10 < (unsigned __int64)((v9 - v32) >> 5) );
  }
  for ( i = 0; i < v48; ++i )
  {
    v13 = 0;
    if ( v31 )
    {
      v14 = 0;
      do
      {
        if ( !(unsigned int)std::wstring::compare(32LL * i + v49, v32 + 32 * v14) )
          break;
        v14 = ++v13;
      }
      while ( v13 < v31 );
    }
    if ( v13 >= v31 )
    {
      v15 = 32LL * i;
      v16 = (const unsigned __int16 *)(v15 + v49);
      if ( a2 == 1 )
      {
        if ( *((_QWORD *)v16 + 3) >= 8u )
          v16 = *(const unsigned __int16 **)v16;
        SubscriptionConfigWriter::DeleteEventSource(v8, phkResult[0], v16);
      }
      else
      {
        if ( *((_QWORD *)v16 + 3) >= 8u )
          v16 = *(const unsigned __int16 **)v16;
        SubscriptionConfigWriter::SetBookmarkToFutureIfExists(v8, phkResult[0], v16);
      }
      std::vector<std::wstring>::push_back(a3, v15 + v49);
    }
  }
  for ( j = 0; j < v31; ++j )
  {
    v18 = *(_DWORD *)(v29[0] + 4LL * j);
    if ( (v18 & 0xF) != 0 )
    {
      v19 = v35;
      v20 = *(_QWORD *)(v35 + 24LL * j);
      v21 = 32LL * j;
      v22 = std::vector<bool>::operator[](v30, v50, j);
      if ( *(_QWORD *)(v19 + 24LL * j + 8) == v20 )
        v20 = 0;
      v23 = *(_QWORD *)(v22 + 8);
      LOBYTE(v23) = ((1 << v23) & **(_DWORD **)v22) != 0;
      LOBYTE(dwOptions) = v23;
      SubscriptionConfigWriter::SetEventSource(v23, phkResult[0], v18, v21 + v32, dwOptions, v21 + v34, v20);
      v24 = std::vector<bool>::operator[](v30, v51, j);
      v25 = *(SubscriptionConfigWriter **)(v24 + 8);
      if ( ((1 << (char)v25) & **(_DWORD **)v24) == 0 )
      {
        v26 = (const unsigned __int16 *)(v21 + v32);
        if ( *(_QWORD *)(v21 + v32 + 24) >= 8u )
          v26 = *(const unsigned __int16 **)v26;
        SubscriptionConfigWriter::SetBookmarkToFutureIfExists(v25, phkResult[0], v26);
      }
      std::vector<std::wstring>::push_back(v53, v21 + v32);
    }
  }
  wmi::ScopeGuardImpl1<void (*)(std::vector<std::vector<unsigned short>> *),std::vector<std::vector<unsigned short>> *>::~ScopeGuardImpl1<void (*)(std::vector<std::vector<unsigned short>> *),std::vector<std::vector<unsigned short>> *>(v44);
  _EventSources::~_EventSources((_EventSources *)v29);
  _EventSources::~_EventSources((_EventSources *)v47);
  wmi::AutoRegKey::Close((wmi::AutoRegKey *)phkResult);
}

```

## disassembly

```asm
0x18001718c  mov     [rsp-8+arg_8], rbx
0x180017191  mov     [rsp-8+arg_18], r9
0x180017196  push    rbp
0x180017197  push    rsi
0x180017198  push    rdi
0x180017199  push    r12
0x18001719b  push    r13
0x18001719d  push    r14
0x18001719f  push    r15
0x1800171a1  lea     rbp, [rsp-0D0h]
0x1800171a9  sub     rsp, 1D0h
0x1800171b0  mov     r14, r8
0x1800171b3  mov     esi, edx
0x1800171b5  mov     rdi, rcx
0x1800171b8  xor     r15d, r15d
0x1800171bb  mov     [rsp+200h+var_1B0], r15
0x1800171c0  mov     [rbp+100h+dwDisposition], r15d
0x1800171c7  lea     rax, [rbp+100h+dwDisposition]
0x1800171ce  mov     [rsp+200h+lpdwDisposition], rax; lpdwDisposition
0x1800171d3  lea     rax, [rsp+200h+var_1B0]
0x1800171d8  mov     [rsp+200h+phkResult], rax; phkResult
0x1800171dd  mov     [rsp+200h+lpSecurityAttributes], r15; lpSecurityAttributes
0x1800171e2  mov     [rsp+200h+samDesired], 2001Fh; samDesired
0x1800171ea  mov     [rsp+200h+dwOptions], r15d; dwOptions
0x1800171ef  xor     r9d, r9d; lpClass
0x1800171f2  xor     r8d, r8d; Reserved
0x1800171f5  lea     rdx, aEventsources; "EventSources"
0x1800171fc  mov     rcx, [rcx+10h]; hKey
0x180017200  call    cs:__imp_RegCreateKeyExW
0x180017206  mov     ebx, eax
0x180017208  test    eax, eax
0x18001720a  jz      short loc_180017286
0x18001720c  lea     rax, WPP_GLOBAL_Control
0x180017213  mov     rcx, cs:WPP_GLOBAL_Control
0x18001721a  cmp     rcx, rax
0x18001721d  jz      short loc_180017242
0x18001721f  test    byte ptr [rcx+1Ch], 40h
0x180017223  jz      short loc_180017242
0x180017225  cmp     byte ptr [rcx+19h], 2
0x180017229  jb      short loc_180017242
0x18001722b  lea     edx, [r15+1Eh]
0x18001722f  mov     r9d, ebx
0x180017232  lea     r8, WPP_995d7fc7f38b34c45f7188ba39a91f1d_Traceguids
0x180017239  mov     rcx, [rcx+10h]
0x18001723d  call    WPP_SF_D
0x180017242  mov     [rbp+100h+var_118], r15b
0x180017246  lea     rax, aAdminWmiEvents_6; "admin\\wmi\\events\\forwarding\\collect"...
0x18001724d  mov     [rbp+100h+var_110], rax
0x180017251  mov     [rbp+100h+var_108], r15
0x180017255  mov     [rbp+100h+var_100], r15
0x180017259  mov     [rbp+100h+var_F8], ebx
0x18001725c  mov     [rbp+100h+var_F4], 0FFFFFFFFh
0x180017263  mov     [rbp+100h+var_F0], 36Eh
0x18001726a  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180017271  mov     [rbp+100h+pExceptionObject], rax
0x180017275  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001727c  lea     rcx, [rbp+100h+pExceptionObject]; pExceptionObject
0x180017280  call    _CxxThrowException_0
0x180017286  lea     rcx, [rbp+100h+var_D0]; this
0x18001728a  call    ??0_EventSources@@QEAA@XZ; _EventSources::_EventSources(void)
0x18001728f  nop
0x180017290  lea     rcx, [rsp+200h+var_1A0]; this
0x180017295  call    ??0_EventSources@@QEAA@XZ; _EventSources::_EventSources(void)
0x18001729a  nop
0x18001729b  cmp     [rbp+100h+dwDisposition], 2
0x1800172a2  jnz     short loc_1800172B3
0x1800172a4  xor     r8d, r8d; bool
0x1800172a7  lea     rdx, [rbp+100h+var_D0]; struct _EventSources *
0x1800172ab  mov     rcx, rdi; this
0x1800172ae  call    ?GetEventSources@SubscriptionConfigReader@@QEBA_NAEAU_EventSources@@_N@Z; SubscriptionConfigReader::GetEventSources(_EventSources &,bool)
0x1800172b3  lea     rcx, [rdi+18h]; this
0x1800172b7  lea     rdx, [rsp+200h+var_1A0]; struct _EventSources *
0x1800172bc  call    ?GetEventSources@SubscriptionReadData@@QEBAXAEAU_EventSources@@@Z; SubscriptionReadData::GetEventSources(_EventSources &)
0x1800172c1  mov     [rbp+100h+var_E8], r15b
0x1800172c5  lea     rax, ?ZeroStringVector@@YAXPEAV?$vector@V?$vector@GV?$allocator@G@std@@@std@@V?$allocator@V?$vector@GV?$allocator@G@std@@@std@@@2@@std@@@Z; ZeroStringVector(std::vector<std::vector<ushort>> *)
0x1800172cc  mov     [rbp+100h+var_E0], rax
0x1800172d0  lea     rax, [rbp+100h+var_138]
0x1800172d4  mov     [rbp+100h+var_D8], rax
0x1800172d8  mov     rdx, [rbp+100h+var_160]
0x1800172dc  mov     rax, rdx
0x1800172df  sub     rax, [rbp+100h+var_168]
0x1800172e3  sar     rax, 5
0x1800172e7  test    rax, rax
0x1800172ea  jz      short loc_18001732C
0x1800172ec  mov     ebx, r15d
0x1800172ef  mov     rcx, r15
0x1800172f2  mov     rax, [rsp+200h+var_1A0]
0x1800172f7  test    byte ptr [rax+rcx*4], 0Fh
0x1800172fb  jz      short loc_180017318
0x1800172fd  shl     rcx, 5
0x180017301  add     rcx, [rbp+100h+var_168]
0x180017305  cmp     qword ptr [rcx+18h], 8
0x18001730a  jb      short loc_18001730F
0x18001730c  mov     rcx, [rcx]; unsigned __int16 *
0x18001730f  call    ?ValidateRegKeyName@@YAXPEBG@Z; ValidateRegKeyName(ushort const *)
0x180017314  mov     rdx, [rbp+100h+var_160]
0x180017318  inc     ebx
0x18001731a  mov     ecx, ebx
0x18001731c  mov     rax, rdx
0x18001731f  sub     rax, [rbp+100h+var_168]
0x180017323  sar     rax, 5
0x180017327  cmp     rcx, rax
0x18001732a  jb      short loc_1800172F2
0x18001732c  mov     edi, r15d
0x18001732f  cmp     [rbp+100h+var_A0], r15
0x180017333  jbe     loc_1800173D1
0x180017339  mov     r11d, r15d
0x18001733c  cmp     [rbp+100h+var_170], r15
0x180017340  jbe     short loc_18001736F
0x180017342  mov     rdx, r15
0x180017345  mov     ebx, edi
0x180017347  shl     rbx, 5
0x18001734b  shl     rdx, 5
0x18001734f  add     rdx, [rbp+100h+var_168]
0x180017353  mov     rcx, [rbp+100h+var_98]
0x180017357  add     rcx, rbx
0x18001735a  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHAEBV12@@Z; std::wstring::compare(std::wstring const &)
0x18001735f  test    eax, eax
0x180017361  jz      short loc_18001736F
0x180017363  inc     r11d
0x180017366  mov     edx, r11d
0x180017369  cmp     rdx, [rbp+100h+var_170]
0x18001736d  jb      short loc_18001734B
0x18001736f  mov     eax, r11d
0x180017372  cmp     rax, [rbp+100h+var_170]
0x180017376  jb      short loc_1800173C3
0x180017378  mov     ebx, edi
0x18001737a  shl     rbx, 5
0x18001737e  mov     r8, [rbp+100h+var_98]
0x180017382  add     r8, rbx
0x180017385  cmp     esi, 1
0x180017388  jnz     short loc_1800173A0
0x18001738a  cmp     qword ptr [r8+18h], 8
0x18001738f  jb      short loc_180017394
0x180017391  mov     r8, [r8]; unsigned __int16 *
0x180017394  mov     rdx, [rsp+200h+var_1B0]; HKEY
0x180017399  call    ?DeleteEventSource@SubscriptionConfigWriter@@AEAAXPEAUHKEY__@@PEBG@Z; SubscriptionConfigWriter::DeleteEventSource(HKEY__ *,ushort const *)
0x18001739e  jmp     short loc_1800173B4
0x1800173a0  cmp     qword ptr [r8+18h], 8
0x1800173a5  jb      short loc_1800173AA
0x1800173a7  mov     r8, [r8]; unsigned __int16 *
0x1800173aa  mov     rdx, [rsp+200h+var_1B0]; HKEY
0x1800173af  call    ?SetBookmarkToFutureIfExists@SubscriptionConfigWriter@@AEAAXPEAUHKEY__@@PEBG@Z; SubscriptionConfigWriter::SetBookmarkToFutureIfExists(HKEY__ *,ushort const *)
0x1800173b4  mov     rdx, [rbp+100h+var_98]
0x1800173b8  add     rdx, rbx
0x1800173bb  mov     rcx, r14
0x1800173be  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring const &)
0x1800173c3  inc     edi
0x1800173c5  mov     eax, edi
0x1800173c7  cmp     rax, [rbp+100h+var_A0]
0x1800173cb  jb      loc_180017339
0x1800173d1  mov     r14d, r15d
0x1800173d4  cmp     [rbp+100h+var_170], r15
0x1800173d8  jbe     loc_1800174C5
0x1800173de  mov     r15d, r14d
0x1800173e1  mov     rax, [rsp+200h+var_1A0]
0x1800173e6  mov     r13d, [rax+r15*4]
0x1800173ea  test    r13b, 0Fh
0x1800173ee  jz      loc_1800174B5
0x1800173f4  lea     rdi, [r15+r15*2]
0x1800173f8  mov     rbx, [rbp+100h+var_138]
0x1800173fc  mov     rsi, [rbx+rdi*8]
0x180017400  mov     r12d, r15d
0x180017403  shl     r12, 5
0x180017407  mov     r8d, r15d
0x18001740a  lea     rdx, [rbp+100h+var_50]
0x180017411  lea     rcx, [rsp+200h+var_188]
0x180017416  call    ??A?$vector@_NV?$allocator@_N@std@@@std@@QEAA?AV?$_Vb_reference@U?$_Wrap_alloc@V?$allocator@I@std@@@std@@@1@_K@Z; std::vector<bool>::operator[](unsigned __int64)
0x18001741b  xor     ecx, ecx
0x18001741d  cmp     [rbx+rdi*8+8], rsi
0x180017422  cmovz   rsi, rcx
0x180017426  mov     r10, [rbp+100h+var_150]
0x18001742a  add     r10, r12
0x18001742d  mov     rcx, [rax+8]
0x180017431  mov     ebx, 1
0x180017436  mov     edx, ebx
0x180017438  shl     edx, cl
0x18001743a  mov     rax, [rax]
0x18001743d  test    [rax], edx
0x18001743f  setnz   cl
0x180017442  mov     r9, [rbp+100h+var_168]
0x180017446  add     r9, r12
0x180017449  mov     [rsp+200h+lpSecurityAttributes], rsi
0x18001744e  mov     qword ptr [rsp+200h+samDesired], r10
0x180017453  mov     byte ptr [rsp+200h+dwOptions], cl
0x180017457  mov     r8d, r13d
0x18001745a  mov     rdx, [rsp+200h+var_1B0]
0x18001745f  call    ?SetEventSource@SubscriptionConfigWriter@@AEAAXPEAUHKEY__@@KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N1PEBG@Z; SubscriptionConfigWriter::SetEventSource(HKEY__ *,ulong,std::wstring const &,bool,std::wstring const &,ushort const *)
0x180017464  mov     r8d, r15d
0x180017467  lea     rdx, [rbp+100h+var_40]
0x18001746e  lea     rcx, [rsp+200h+var_188]
0x180017473  call    ??A?$vector@_NV?$allocator@_N@std@@@std@@QEAA?AV?$_Vb_reference@U?$_Wrap_alloc@V?$allocator@I@std@@@std@@@1@_K@Z; std::vector<bool>::operator[](unsigned __int64)
0x180017478  mov     rcx, [rax+8]; this
0x18001747c  mov     edx, ebx
0x18001747e  shl     edx, cl
0x180017480  mov     rax, [rax]
0x180017483  test    [rax], edx
0x180017485  jnz     short loc_1800174A2
0x180017487  mov     r8, [rbp+100h+var_168]
0x18001748b  add     r8, r12
0x18001748e  cmp     qword ptr [r8+18h], 8
0x180017493  jb      short loc_180017498
0x180017495  mov     r8, [r8]; unsigned __int16 *
0x180017498  mov     rdx, [rsp+200h+var_1B0]; HKEY
0x18001749d  call    ?SetBookmarkToFutureIfExists@SubscriptionConfigWriter@@AEAAXPEAUHKEY__@@PEBG@Z; SubscriptionConfigWriter::SetBookmarkToFutureIfExists(HKEY__ *,ushort const *)
0x1800174a2  mov     rdx, [rbp+100h+var_168]
0x1800174a6  add     rdx, r12
0x1800174a9  mov     rcx, [rbp+100h+arg_18]
0x1800174b0  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring const &)
0x1800174b5  inc     r14d
0x1800174b8  mov     eax, r14d
0x1800174bb  cmp     rax, [rbp+100h+var_170]
0x1800174bf  jb      loc_1800173DE
0x1800174c5  lea     rcx, [rbp+100h+var_E8]
0x1800174c9  call    ??1?$ScopeGuardImpl1@P6AXPEAV?$vector@V?$vector@GV?$allocator@G@std@@@std@@V?$allocator@V?$vector@GV?$allocator@G@std@@@std@@@2@@std@@@ZPEAV12@@wmi@@QEAA@XZ; wmi::ScopeGuardImpl1<void (*)(std::vector<std::vector<ushort>> *),std::vector<std::vector<ushort>> *>::~ScopeGuardImpl1<void (*)(std::vector<std::vector<ushort>> *),std::vector<std::vector<ushort>> *>(void)
0x1800174ce  nop
0x1800174cf  lea     rcx, [rsp+200h+var_1A0]; this
0x1800174d4  call    ??1_EventSources@@QEAA@XZ; _EventSources::~_EventSources(void)
0x1800174d9  nop
0x1800174da  lea     rcx, [rbp+100h+var_D0]; this
0x1800174de  call    ??1_EventSources@@QEAA@XZ; _EventSources::~_EventSources(void)
0x1800174e3  nop
0x1800174e4  lea     rcx, [rsp+200h+var_1B0]; this
0x1800174e9  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x1800174ee  mov     rbx, [rsp+200h+arg_8]
0x1800174f6  add     rsp, 1D0h
0x1800174fd  pop     r15
0x1800174ff  pop     r14
0x180017501  pop     r13
0x180017503  pop     r12
0x180017505  pop     rdi
0x180017506  pop     rsi
0x180017507  pop     rbp
0x180017508  retn
```
