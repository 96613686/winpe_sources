# LogCommandManager::GetFailureContextAsString(LogCommandFailureContext)

- ea: `0x180080f04`
- end: `0x1800812bb`
- name: `?GetFailureContextAsString@LogCommandManager@@CA?BV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4LogCommandFailureContext@@@Z`
- size: `951`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800807c4`

## callees

- `0x180007440`
- `0x1800074a8`
- `0x18000a54c`
- `0x18000a5b4`
- `0x18000a9c8`
- `0x180032b14`
- `0x18003320c`
- `0x180033254`
- `0x1800804e4`
- `0x180080638`
- `0x180080f04`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x1800812b4`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x1800812b4`

## string_xrefs

- `0x180081038`: `OnSocketRead`
- `0x180081131`: `CreateConnectorWindow`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
__int64 __fastcall LogCommandManager::GetFailureContextAsString(__int64 a1, int a2)
{
  _QWORD *v4; // r14
  int *v5; // rbx
  _QWORD *v6; // rbx
  _QWORD *v7; // rcx
  __int64 v9; // [rsp+28h] [rbp-E0h] BYREF
  _QWORD *v10; // [rsp+30h] [rbp-D8h] BYREF
  __int64 v11; // [rsp+38h] [rbp-D0h]
  __int64 v12; // [rsp+40h] [rbp-C8h]
  int v13; // [rsp+58h] [rbp-B0h] BYREF
  _BYTE v14[32]; // [rsp+60h] [rbp-A8h] BYREF
  int v15; // [rsp+80h] [rbp-88h]
  _BYTE v16[32]; // [rsp+88h] [rbp-80h] BYREF
  int v17; // [rsp+A8h] [rbp-60h]
  _BYTE v18[32]; // [rsp+B0h] [rbp-58h] BYREF
  int v19; // [rsp+D0h] [rbp-38h]
  _BYTE v20[32]; // [rsp+D8h] [rbp-30h] BYREF
  int v21; // [rsp+F8h] [rbp-10h]
  _BYTE v22[32]; // [rsp+100h] [rbp-8h] BYREF
  int v23; // [rsp+120h] [rbp+18h]
  _BYTE v24[32]; // [rsp+128h] [rbp+20h] BYREF
  int v25; // [rsp+148h] [rbp+40h]
  _BYTE v26[32]; // [rsp+150h] [rbp+48h] BYREF
  int v27; // [rsp+170h] [rbp+68h]
  _BYTE v28[32]; // [rsp+178h] [rbp+70h] BYREF
  int v29; // [rsp+198h] [rbp+90h]
  _BYTE v30[32]; // [rsp+1A0h] [rbp+98h] BYREF
  int v31; // [rsp+1C0h] [rbp+B8h]
  _BYTE v32[32]; // [rsp+1C8h] [rbp+C0h] BYREF
  int v33; // [rsp+1E8h] [rbp+E0h]
  _BYTE v34[32]; // [rsp+1F0h] [rbp+E8h] BYREF
  _DWORD v35[12]; // [rsp+210h] [rbp+108h] BYREF
  _BYTE v36[32]; // [rsp+240h] [rbp+138h] BYREF
  int v37; // [rsp+260h] [rbp+158h]
  _BYTE v38[32]; // [rsp+268h] [rbp+160h] BYREF
  _DWORD v39[10]; // [rsp+288h] [rbp+180h] BYREF
  _DWORD v40[12]; // [rsp+2B0h] [rbp+1A8h] BYREF
  _BYTE v41[32]; // [rsp+2E0h] [rbp+1D8h] BYREF
  int v42; // [rsp+300h] [rbp+1F8h]
  _BYTE v43[32]; // [rsp+308h] [rbp+200h] BYREF
  int v44; // [rsp+328h] [rbp+220h]
  _BYTE v45[32]; // [rsp+330h] [rbp+228h] BYREF
  int v46; // [rsp+350h] [rbp+248h]
  _BYTE v47[32]; // [rsp+358h] [rbp+250h] BYREF
  int v48; // [rsp+378h] [rbp+270h]
  _BYTE v49[32]; // [rsp+380h] [rbp+278h] BYREF
  char v50; // [rsp+3A0h] [rbp+298h] BYREF
  int v51; // [rsp+3E0h] [rbp+2D8h] BYREF

  v51 = a2;
  v9 = a1;
  if ( !qword_1800AFF60 )
  {
    v13 = 0;
    std::wstring::wstring(v14, L"SocketError");
    v15 = 1;
    std::wstring::wstring(v16, L"ConnectEx");
    v17 = 2;
    std::wstring::wstring(v18, L"ConnectDirect");
    v19 = 3;
    std::wstring::wstring(v20, L"ConnectProxy");
    v21 = 4;
    std::wstring::wstring(v22, L"DnsLookUp");
    v23 = 5;
    std::wstring::wstring(v24, L"TryConnectWithAddrInfo");
    v25 = 6;
    std::wstring::wstring(v26, L"SetupSocket");
    v27 = 7;
    std::wstring::wstring(v28, L"GracefulSocketClose");
    v29 = 8;
    std::wstring::wstring(v30, L"OnSocketConnect");
    v31 = 9;
    std::wstring::wstring(v32, L"OnSocketRead");
    v33 = 10;
    std::wstring::wstring(v34, L"HandleAsyncConnectFailure");
    LODWORD(v9) = 11;
    std::pair<enum LogCommandFailureContext const,std::wstring>::pair<enum LogCommandFailureContext const,std::wstring>(
      v35,
      &v9,
      (__int64)L"UpperLayerDisconnect");
    v35[10] = 12;
    std::wstring::wstring(v36, L"StartTlsHandshake");
    v37 = 13;
    std::wstring::wstring(v38, L"InitializeSSPI");
    LODWORD(v9) = 14;
    std::pair<enum LogCommandFailureContext const,std::wstring>::pair<enum LogCommandFailureContext const,std::wstring>(
      v39,
      &v9,
      (__int64)L"ContinueTlsHandshake");
    LODWORD(v9) = 15;
    std::pair<enum LogCommandFailureContext const,std::wstring>::pair<enum LogCommandFailureContext const,std::wstring>(
      v40,
      &v9,
      (__int64)L"InitEncryptionBuffer");
    v40[10] = 16;
    std::wstring::wstring(v41, L"DecryptTlsData");
    v42 = 17;
    std::wstring::wstring(v43, L"CreateConnectorWindow");
    v44 = 18;
    std::wstring::wstring(v45, L"ConnectorFailure");
    v46 = 19;
    std::wstring::wstring(v47, L"ControlChannelTrigger");
    v48 = 20;
    std::wstring::wstring(v49, L"OnConnectorConnect");
    std::_Tree<std::_Tmap_traits<enum LogCommandFailureContext,std::wstring,std::less<enum LogCommandFailureContext>,std::allocator<std::pair<enum LogCommandFailureContext const,std::wstring>>,0>>::_Tree<std::_Tmap_traits<enum LogCommandFailureContext,std::wstring,std::less<enum LogCommandFailureContext>,std::allocator<std::pair<enum LogCommandFailureContext const,std::wstring>>,0>>(&v10);
    v4 = v10;
    v5 = &v13;
    do
    {
      std::_Tree<std::_Tmap_traits<enum LogCommandFailureContext,std::wstring,std::less<enum LogCommandFailureContext>,std::allocator<std::pair<enum LogCommandFailureContext const,std::wstring>>,0>>::_Emplace_hint<std::pair<enum LogCommandFailureContext const,std::wstring> const &>(
        &v10,
        (__int64)v4,
        (__int64)v5);
      v5 += 10;
    }
    while ( v5 != (int *)&v50 );
    v6 = (_QWORD *)qword_1800AFF58;
    std::_Tree_val<std::_Tree_simple_types<std::pair<enum LogCommandFailureContext const,std::wstring>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<enum LogCommandFailureContext const,std::wstring>,void *>>>(
      (__int64)&qword_1800AFF58,
      (__int64)&qword_1800AFF58,
      *(__int64 **)(qword_1800AFF58 + 8));
    v6[1] = v6;
    *v6 = v6;
    v6[2] = v6;
    v7 = (_QWORD *)qword_1800AFF58;
    qword_1800AFF58 = (__int64)v10;
    v10 = v7;
    qword_1800AFF60 = v11;
    v11 = 0;
    std::_Tree<std::_Tmap_traits<enum LogCommandFailureContext,std::wstring,std::less<enum LogCommandFailureContext>,std::allocator<std::pair<enum LogCommandFailureContext const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<enum LogCommandFailureContext,std::wstring,std::less<enum LogCommandFailureContext>,std::allocator<std::pair<enum LogCommandFailureContext const,std::wstring>>,0>>(&v10);
    `eh vector destructor iterator'(
      &v13,
      0x28u,
      0x15u,
      (void (*)(void *))std::pair<enum LogCommandFailureContext const,std::wstring>::~pair<enum LogCommandFailureContext const,std::wstring>);
  }
  std::_Tree<std::_Tmap_traits<enum _WNP_CP_DISCONNECT_REASON,std::string,std::less<enum _WNP_CP_DISCONNECT_REASON>,std::allocator<std::pair<enum _WNP_CP_DISCONNECT_REASON const,std::string>>,0>>::_Find_lower_bound<enum _WNP_CP_DISCONNECT_REASON>(
    &qword_1800AFF58,
    &v10,
    &v51);
  if ( *(_BYTE *)(v12 + 25) || a2 < *(_DWORD *)(v12 + 32) )
  {
    std::_Xout_of_range("invalid map<K, T> key");
    JUMPOUT(0x1800812BALL);
  }
  std::wstring::wstring(a1, v12 + 40);
  return a1;
}

```

## disassembly

```asm
0x180080f04  mov     rax, rsp
0x180080f07  mov     [rax+18h], rbx
0x180080f0b  mov     [rax+20h], rsi
0x180080f0f  mov     [rax+10h], edx
0x180080f12  push    rbp
0x180080f13  push    rdi
0x180080f14  push    r14
0x180080f16  lea     rbp, [rax-2C8h]
0x180080f1d  sub     rsp, 3B0h
0x180080f24  mov     rax, cs:__security_cookie
0x180080f2b  xor     rax, rsp
0x180080f2e  mov     [rbp+2C0h+var_20], rax
0x180080f35  mov     esi, edx
0x180080f37  mov     rdi, rcx
0x180080f3a  mov     [rsp+3C0h+var_3A0], rcx
0x180080f3f  cmp     cs:qword_1800AFF60, 0
0x180080f47  jnz     loc_18008124F
0x180080f4d  mov     [rsp+3C0h+var_370], 0
0x180080f55  lea     rdx, aSocketerror; "SocketError"
0x180080f5c  lea     rcx, [rsp+3C0h+var_368]
0x180080f61  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180080f66  nop
0x180080f67  mov     [rsp+3C0h+var_348], 1
0x180080f6f  lea     rdx, aConnectex; "ConnectEx"
0x180080f76  lea     rcx, [rbp+2C0h+var_340]
0x180080f7a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180080f7f  nop
0x180080f80  mov     [rbp+2C0h+var_320], 2
0x180080f87  lea     rdx, aConnectdirect; "ConnectDirect"
0x180080f8e  lea     rcx, [rbp+2C0h+var_318]
0x180080f92  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180080f97  nop
0x180080f98  mov     [rbp+2C0h+var_2F8], 3
0x180080f9f  lea     rdx, aConnectproxy; "ConnectProxy"
0x180080fa6  lea     rcx, [rbp+2C0h+var_2F0]
0x180080faa  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180080faf  nop
0x180080fb0  mov     [rbp+2C0h+var_2D0], 4
0x180080fb7  lea     rdx, aDnslookup; "DnsLookUp"
0x180080fbe  lea     rcx, [rbp+2C0h+var_2C8]
0x180080fc2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180080fc7  nop
0x180080fc8  mov     [rbp+2C0h+var_2A8], 5
0x180080fcf  lea     rdx, aTryconnectwith; "TryConnectWithAddrInfo"
0x180080fd6  lea     rcx, [rbp+2C0h+var_2A0]
0x180080fda  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180080fdf  nop
0x180080fe0  mov     [rbp+2C0h+var_280], 6
0x180080fe7  lea     rdx, aSetupsocket; "SetupSocket"
0x180080fee  lea     rcx, [rbp+2C0h+var_278]
0x180080ff2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180080ff7  nop
0x180080ff8  mov     [rbp+2C0h+var_258], 7
0x180080fff  lea     rdx, aGracefulsocket; "GracefulSocketClose"
0x180081006  lea     rcx, [rbp+2C0h+var_250]
0x18008100a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18008100f  nop
0x180081010  mov     [rbp+2C0h+var_230], 8
0x18008101a  lea     rdx, aOnsocketconnec; "OnSocketConnect"
0x180081021  lea     rcx, [rbp+2C0h+var_228]
0x180081028  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18008102d  nop
0x18008102e  mov     [rbp+2C0h+var_208], 9
0x180081038  lea     rdx, aOnsocketread; "OnSocketRead"
0x18008103f  lea     rcx, [rbp+2C0h+var_200]
0x180081046  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18008104b  nop
0x18008104c  mov     [rbp+2C0h+var_1E0], 0Ah
0x180081056  lea     rdx, aHandleasynccon; "HandleAsyncConnectFailure"
0x18008105d  lea     rcx, [rbp+2C0h+var_1D8]
0x180081064  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180081069  nop
0x18008106a  mov     dword ptr [rsp+3C0h+var_3A0], 0Bh
0x180081072  lea     r8, aUpperlayerdisc; "UpperLayerDisconnect"
0x180081079  lea     rdx, [rsp+3C0h+var_3A0]
0x18008107e  lea     rcx, [rbp+2C0h+var_1B8]
0x180081085  call    ??$?0W4LogCommandFailureContext@@AEAY0BF@$$CBG$0A@@?$pair@$$CBW4LogCommandFailureContext@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAA@$$QEAW4LogCommandFailureContext@@AEAY0BF@$$CBG@Z; std::pair<LogCommandFailureContext const,std::wstring>::pair<LogCommandFailureContext const,std::wstring>(LogCommandFailureContext &&,ushort const (&)[21])
0x18008108a  nop
0x18008108b  mov     [rbp+2C0h+var_190], 0Ch
0x180081095  lea     rdx, aStarttlshandsh; "StartTlsHandshake"
0x18008109c  lea     rcx, [rbp+2C0h+var_188]
0x1800810a3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800810a8  nop
0x1800810a9  mov     [rbp+2C0h+var_168], 0Dh
0x1800810b3  lea     rdx, aInitializesspi; "InitializeSSPI"
0x1800810ba  lea     rcx, [rbp+2C0h+var_160]
0x1800810c1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800810c6  nop
0x1800810c7  mov     dword ptr [rsp+3C0h+var_3A0], 0Eh
0x1800810cf  lea     r8, aContinuetlshan; "ContinueTlsHandshake"
0x1800810d6  lea     rdx, [rsp+3C0h+var_3A0]
0x1800810db  lea     rcx, [rbp+2C0h+var_140]
0x1800810e2  call    ??$?0W4LogCommandFailureContext@@AEAY0BF@$$CBG$0A@@?$pair@$$CBW4LogCommandFailureContext@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAA@$$QEAW4LogCommandFailureContext@@AEAY0BF@$$CBG@Z; std::pair<LogCommandFailureContext const,std::wstring>::pair<LogCommandFailureContext const,std::wstring>(LogCommandFailureContext &&,ushort const (&)[21])
0x1800810e7  nop
0x1800810e8  mov     dword ptr [rsp+3C0h+var_3A0], 0Fh
0x1800810f0  lea     r8, aInitencryption; "InitEncryptionBuffer"
0x1800810f7  lea     rdx, [rsp+3C0h+var_3A0]
0x1800810fc  lea     rcx, [rbp+2C0h+var_118]
0x180081103  call    ??$?0W4LogCommandFailureContext@@AEAY0BF@$$CBG$0A@@?$pair@$$CBW4LogCommandFailureContext@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAA@$$QEAW4LogCommandFailureContext@@AEAY0BF@$$CBG@Z; std::pair<LogCommandFailureContext const,std::wstring>::pair<LogCommandFailureContext const,std::wstring>(LogCommandFailureContext &&,ushort const (&)[21])
0x180081108  nop
0x180081109  mov     [rbp+2C0h+var_F0], 10h
0x180081113  lea     rdx, aDecrypttlsdata; "DecryptTlsData"
0x18008111a  lea     rcx, [rbp+2C0h+var_E8]
0x180081121  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180081126  nop
0x180081127  mov     [rbp+2C0h+var_C8], 11h
0x180081131  lea     rdx, aCreateconnecto; "CreateConnectorWindow"
0x180081138  lea     rcx, [rbp+2C0h+var_C0]
0x18008113f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180081144  nop
0x180081145  mov     [rbp+2C0h+var_A0], 12h
0x18008114f  lea     rdx, aConnectorfailu; "ConnectorFailure"
0x180081156  lea     rcx, [rbp+2C0h+var_98]
0x18008115d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180081162  nop
0x180081163  mov     [rbp+2C0h+var_78], 13h
0x18008116d  lea     rdx, aControlchannel; "ControlChannelTrigger"
0x180081174  lea     rcx, [rbp+2C0h+var_70]
0x18008117b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180081180  nop
0x180081181  mov     [rbp+2C0h+var_50], 14h
0x18008118b  lea     rdx, aOnconnectorcon; "OnConnectorConnect"
0x180081192  lea     rcx, [rbp+2C0h+var_48]
0x180081199  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18008119e  nop
0x18008119f  lea     rcx, [rsp+3C0h+var_398]
0x1800811a4  call    ??0?$_Tree@V?$_Tmap_traits@W4LogCommandFailureContext@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4LogCommandFailureContext@@@3@V?$allocator@U?$pair@$$CBW4LogCommandFailureContext@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@3@$0A@@std@@@std@@QEAA@AEBU?$less@W4LogCommandFailureContext@@@1@@Z; std::_Tree<std::_Tmap_traits<LogCommandFailureContext,std::wstring,std::less<LogCommandFailureContext>,std::allocator<std::pair<LogCommandFailureContext const,std::wstring>>,0>>::_Tree<std::_Tmap_traits<LogCommandFailureContext,std::wstring,std::less<LogCommandFailureContext>,std::allocator<std::pair<LogCommandFailureContext const,std::wstring>>,0>>(std::less<LogCommandFailureContext> const &)
0x1800811a9  nop
0x1800811aa  mov     r14, [rsp+3C0h+var_398]
0x1800811af  lea     rbx, [rsp+3C0h+var_370]
0x1800811b4  mov     r8, rbx
0x1800811b7  mov     rdx, r14
0x1800811ba  lea     rcx, [rsp+3C0h+var_398]
0x1800811bf  call    ??$_Emplace_hint@AEBU?$pair@$$CBW4LogCommandFailureContext@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@?$_Tree@V?$_Tmap_traits@W4LogCommandFailureContext@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4LogCommandFailureContext@@@3@V?$allocator@U?$pair@$$CBW4LogCommandFailureContext@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@3@$0A@@std@@@std@@IEAAPEAU?$_Tree_node@U?$pair@$$CBW4LogCommandFailureContext@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@1@QEAU21@AEBU?$pair@$$CBW4LogCommandFailureContext@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<LogCommandFailureContext,std::wstring,std::less<LogCommandFailureContext>,std::allocator<std::pair<LogCommandFailureContext const,std::wstring>>,0>>::_Emplace_hint<std::pair<LogCommandFailureContext const,std::wstring> const &>(std::_Tree_node<std::pair<LogCommandFailureContext const,std::wstring>,void *> * const,std::pair<LogCommandFailureContext const,std::wstring> const &)
0x1800811c4  add     rbx, 28h ; '('
0x1800811c8  lea     rax, [rbp+2C0h+var_28]
0x1800811cf  cmp     rbx, rax
0x1800811d2  jnz     short loc_1800811B4
0x1800811d4  mov     rbx, cs:qword_1800AFF58
0x1800811db  mov     r8, [rbx+8]
0x1800811df  lea     rdx, qword_1800AFF58
0x1800811e6  lea     rcx, qword_1800AFF58
0x1800811ed  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBW4LogCommandFailureContext@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4LogCommandFailureContext@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBW4LogCommandFailureContext@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBW4LogCommandFailureContext@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<LogCommandFailureContext const,std::wstring>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<LogCommandFailureContext const,std::wstring>,void *>>>(std::allocator<std::_Tree_node<std::pair<LogCommandFailureContext const,std::wstring>,void *>> &,std::_Tree_node<std::pair<LogCommandFailureContext const,std::wstring>,void *> *)
0x1800811f2  mov     [rbx+8], rbx
0x1800811f6  mov     [rbx], rbx
0x1800811f9  mov     [rbx+10h], rbx
0x1800811fd  mov     rcx, cs:qword_1800AFF58
0x180081204  mov     rax, [rsp+3C0h+var_398]
0x180081209  mov     cs:qword_1800AFF58, rax
0x180081210  mov     [rsp+3C0h+var_398], rcx
0x180081215  mov     rax, [rsp+3C0h+var_390]
0x18008121a  mov     cs:qword_1800AFF60, rax
0x180081221  mov     [rsp+3C0h+var_390], 0
0x18008122a  lea     rcx, [rsp+3C0h+var_398]
0x18008122f  call    ??1?$_Tree@V?$_Tmap_traits@W4LogCommandFailureContext@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4LogCommandFailureContext@@@3@V?$allocator@U?$pair@$$CBW4LogCommandFailureContext@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<LogCommandFailureContext,std::wstring,std::less<LogCommandFailureContext>,std::allocator<std::pair<LogCommandFailureContext const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<LogCommandFailureContext,std::wstring,std::less<LogCommandFailureContext>,std::allocator<std::pair<LogCommandFailureContext const,std::wstring>>,0>>(void)
0x180081234  nop
0x180081235  lea     r9, ??1?$pair@$$CBW4LogCommandFailureContext@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAA@XZ; void (*)(void *)
0x18008123c  mov     edx, 28h ; '('; unsigned __int64
0x180081241  lea     r8d, [rdx-13h]; unsigned __int64
0x180081245  lea     rcx, [rsp+3C0h+var_370]; void *
0x18008124a  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18008124f  lea     r8, [rbp+2C0h+arg_8]
0x180081256  lea     rdx, [rsp+3C0h+var_398]
0x18008125b  lea     rcx, qword_1800AFF58
0x180081262  call    ??$_Find_lower_bound@W4_WNP_CP_DISCONNECT_REASON@@@?$_Tree@V?$_Tmap_traits@W4_WNP_CP_DISCONNECT_REASON@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$less@W4_WNP_CP_DISCONNECT_REASON@@@3@V?$allocator@U?$pair@$$CBW4_WNP_CP_DISCONNECT_REASON@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@@3@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBW4_WNP_CP_DISCONNECT_REASON@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@PEAX@std@@@1@AEBW4_WNP_CP_DISCONNECT_REASON@@@Z; std::_Tree<std::_Tmap_traits<_WNP_CP_DISCONNECT_REASON,std::string,std::less<_WNP_CP_DISCONNECT_REASON>,std::allocator<std::pair<_WNP_CP_DISCONNECT_REASON const,std::string>>,0>>::_Find_lower_bound<_WNP_CP_DISCONNECT_REASON>(_WNP_CP_DISCONNECT_REASON const &)
0x180081267  mov     rdx, [rsp+3C0h+var_388]
0x18008126c  cmp     byte ptr [rdx+19h], 0
0x180081270  jnz     short loc_1800812AD
0x180081272  cmp     esi, [rdx+20h]
0x180081275  jl      short loc_1800812AD
0x180081277  add     rdx, 28h ; '('
0x18008127b  mov     rcx, rdi
0x18008127e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180081283  mov     rax, rdi
0x180081286  mov     rcx, [rbp+2C0h+var_20]
0x18008128d  xor     rcx, rsp; StackCookie
0x180081290  call    __security_check_cookie
0x180081295  lea     r11, [rsp+3C0h+var_10]
0x18008129d  mov     rbx, [r11+30h]
0x1800812a1  mov     rsi, [r11+38h]
0x1800812a5  mov     rsp, r11
0x1800812a8  pop     r14
0x1800812aa  pop     rdi
0x1800812ab  pop     rbp
0x1800812ac  retn
0x1800812ad  lea     rcx, aInvalidMapKTKe; "invalid map<K, T> key"
0x1800812b4  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
```
