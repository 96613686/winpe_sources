# CWNPNet::MapDisconnectReasonToString(_WNP_CP_DISCONNECT_REASON)

- ea: `0x18003ae50`
- end: `0x18003b2c0`
- name: `?MapDisconnectReasonToString@CWNPNet@@AEAA?BV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4_WNP_CP_DISCONNECT_REASON@@@Z`
- size: `1136`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18003a4d4`

## callees

- `0x180007440`
- `0x1800074a8`
- `0x18000a5b4`
- `0x18000fe2c`
- `0x180010390`
- `0x180010650`
- `0x180010698`
- `0x180010824`
- `0x18003203c`
- `0x180032828`
- `0x180032b14`
- `0x18003ae50`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18003b2b9`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18003b2b9`

## string_xrefs

- `0x18003af14`: `ServerCommandErrorCNT`
- `0x18003af32`: `ServerCommandErrorATH`
- `0x18003af50`: `ServerCommandErrorBND`
- `0x18003af6d`: `ServerCommandErrorUBND`
- `0x18003af85`: `ServerCommandErrorUnknown`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
__int64 __fastcall CWNPNet::MapDisconnectReasonToString(__int64 a1, __int64 a2, int a3)
{
  PVOID *v6; // rcx
  __int64 *v7; // rdi
  __int64 v8; // r15
  int *v9; // rbx
  _QWORD *v10; // rbx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v14; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v15; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v16; // [rsp+30h] [rbp-D0h]
  _BYTE v17[16]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v18; // [rsp+50h] [rbp-B0h]
  int v19; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v20[32]; // [rsp+68h] [rbp-98h] BYREF
  int v21; // [rsp+88h] [rbp-78h]
  _BYTE v22[32]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v23[40]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v24[40]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v25[40]; // [rsp+100h] [rbp+0h] BYREF
  int v26; // [rsp+128h] [rbp+28h]
  _BYTE v27[32]; // [rsp+130h] [rbp+30h] BYREF
  int v28; // [rsp+150h] [rbp+50h]
  _BYTE v29[32]; // [rsp+158h] [rbp+58h] BYREF
  int v30; // [rsp+178h] [rbp+78h]
  _BYTE v31[32]; // [rsp+180h] [rbp+80h] BYREF
  int v32; // [rsp+1A0h] [rbp+A0h]
  _BYTE v33[32]; // [rsp+1A8h] [rbp+A8h] BYREF
  int v34; // [rsp+1C8h] [rbp+C8h]
  _BYTE v35[32]; // [rsp+1D0h] [rbp+D0h] BYREF
  _BYTE v36[40]; // [rsp+1F0h] [rbp+F0h] BYREF
  _BYTE v37[40]; // [rsp+218h] [rbp+118h] BYREF
  int v38; // [rsp+240h] [rbp+140h]
  _BYTE v39[32]; // [rsp+248h] [rbp+148h] BYREF
  int v40; // [rsp+268h] [rbp+168h]
  _BYTE v41[32]; // [rsp+270h] [rbp+170h] BYREF
  int v42; // [rsp+290h] [rbp+190h]
  _BYTE v43[32]; // [rsp+298h] [rbp+198h] BYREF
  _BYTE v44[40]; // [rsp+2B8h] [rbp+1B8h] BYREF
  _BYTE v45[40]; // [rsp+2E0h] [rbp+1E0h] BYREF
  int v46; // [rsp+308h] [rbp+208h]
  _BYTE v47[32]; // [rsp+310h] [rbp+210h] BYREF
  int v48; // [rsp+330h] [rbp+230h]
  _BYTE v49[32]; // [rsp+338h] [rbp+238h] BYREF
  _BYTE v50[40]; // [rsp+358h] [rbp+258h] BYREF
  int v51; // [rsp+380h] [rbp+280h]
  _BYTE v52[32]; // [rsp+388h] [rbp+288h] BYREF
  _BYTE v53[40]; // [rsp+3A8h] [rbp+2A8h] BYREF
  int v54; // [rsp+3D0h] [rbp+2D0h]
  _BYTE v55[32]; // [rsp+3D8h] [rbp+2D8h] BYREF
  char v56; // [rsp+3F8h] [rbp+2F8h] BYREF
  int v57; // [rsp+460h] [rbp+360h] BYREF

  v57 = a3;
  v14 = a2;
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 573, &WPP_4e47059d20e03c0ffeb37878b8bdc70f_Traceguids);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  v7 = (__int64 *)(a1 + 280);
  if ( !v7[1] )
  {
    v19 = 0;
    std::string::string((__int64)v20, (__int64)"None");
    v21 = 1;
    std::string::string((__int64)v22, (__int64)"SystemSuspend");
    LODWORD(v14) = 2;
    std::pair<enum _WNP_CP_DISCONNECT_REASON const,std::string>::pair<enum _WNP_CP_DISCONNECT_REASON const,std::string>(
      v23,
      &v14,
      "ServerCommandErrorCNT");
    LODWORD(v14) = 3;
    std::pair<enum _WNP_CP_DISCONNECT_REASON const,std::string>::pair<enum _WNP_CP_DISCONNECT_REASON const,std::string>(
      v24,
      &v14,
      "ServerCommandErrorATH");
    LODWORD(v14) = 4;
    std::pair<enum _WNP_CP_DISCONNECT_REASON const,std::string>::pair<enum _WNP_CP_DISCONNECT_REASON const,std::string>(
      v25,
      &v14,
      "ServerCommandErrorBND");
    v26 = 5;
    std::string::string((__int64)v27, (__int64)"ServerCommandErrorUBND");
    v28 = 6;
    std::string::string((__int64)v29, (__int64)"ServerCommandErrorUnknown");
    v30 = 7;
    std::string::string((__int64)v31, (__int64)"ServerOUT");
    v32 = 8;
    std::string::string((__int64)v33, (__int64)"ServerOUTOTH");
    v34 = 9;
    std::string::string((__int64)v35, (__int64)"ServerOUTOOS");
    LODWORD(v14) = 10;
    std::pair<enum _WNP_CP_DISCONNECT_REASON const,std::string>::pair<enum _WNP_CP_DISCONNECT_REASON const,std::string>(
      v36,
      &v14,
      "ServerOUTErrorCode");
    LODWORD(v14) = 11;
    std::pair<enum _WNP_CP_DISCONNECT_REASON const,std::string>::pair<enum _WNP_CP_DISCONNECT_REASON const,std::string>(
      v37,
      &v14,
      "ServerOUTUnexpected");
    v38 = 12;
    std::string::string((__int64)v39, (__int64)"XFR");
    v40 = 13;
    std::string::string((__int64)v41, (__int64)"XFRFallbackFailed");
    v42 = 14;
    std::string::string((__int64)v43, (__int64)"KeepAliveTimeOut");
    LODWORD(v14) = 15;
    std::pair<enum _WNP_CP_DISCONNECT_REASON const,std::string>::pair<enum _WNP_CP_DISCONNECT_REASON const,std::string>(
      v44,
      &v14,
      "ConnectionTimedOut");
    LODWORD(v14) = 16;
    std::pair<enum _WNP_CP_DISCONNECT_REASON const,std::string>::pair<enum _WNP_CP_DISCONNECT_REASON const,std::string>(
      v45,
      &v14,
      "NetworkDisconnected");
    v46 = 17;
    std::string::string((__int64)v47, (__int64)"PreferredInterfaceChange");
    v48 = 18;
    std::string::string((__int64)v49, (__int64)"StopKeepAliveMeasurement");
    LODWORD(v14) = 19;
    std::pair<enum _WNP_CP_DISCONNECT_REASON const,std::string>::pair<enum _WNP_CP_DISCONNECT_REASON const,std::string>(
      v50,
      &v14,
      "KeepAliveConverged");
    v51 = 20;
    std::string::string((__int64)v52, (__int64)"ReduceMaxKATime");
    LODWORD(v14) = 21;
    std::pair<enum _WNP_CP_DISCONNECT_REASON const,std::string>::pair<enum _WNP_CP_DISCONNECT_REASON const,std::string>(
      v53,
      &v14,
      "UpperLayerInitiated");
    v54 = 22;
    std::string::string((__int64)v55, (__int64)"DisconnectedStatusFromPNG");
    std::_Tree<std::_Tmap_traits<enum LogCommandFailureContext,std::wstring,std::less<enum LogCommandFailureContext>,std::allocator<std::pair<enum LogCommandFailureContext const,std::wstring>>,0>>::_Tree<std::_Tmap_traits<enum LogCommandFailureContext,std::wstring,std::less<enum LogCommandFailureContext>,std::allocator<std::pair<enum LogCommandFailureContext const,std::wstring>>,0>>(&v15);
    v8 = v15;
    v9 = &v19;
    do
    {
      std::_Tree<std::_Tmap_traits<enum _WNP_CP_DISCONNECT_REASON,std::string,std::less<enum _WNP_CP_DISCONNECT_REASON>,std::allocator<std::pair<enum _WNP_CP_DISCONNECT_REASON const,std::string>>,0>>::_Emplace_hint<std::pair<enum _WNP_CP_DISCONNECT_REASON const,std::string> const &>(
        &v15,
        v8,
        v9);
      v9 += 10;
    }
    while ( v9 != (int *)&v56 );
    if ( v7 != &v15 )
    {
      v10 = (_QWORD *)*v7;
      std::_Tree_val<std::_Tree_simple_types<std::pair<enum _WNP_CP_DISCONNECT_REASON const,std::string>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<enum _WNP_CP_DISCONNECT_REASON const,std::string>,void *>>>(
        v7,
        v7,
        *(_QWORD *)(*v7 + 8));
      v10[1] = v10;
      *v10 = v10;
      v10[2] = v10;
      v7[1] = 0;
      v11 = *v7;
      *v7 = v15;
      v15 = v11;
      v12 = v7[1];
      v7[1] = v16;
      v16 = v12;
    }
    std::_Tree<std::_Tmap_traits<enum _WNP_CP_DISCONNECT_REASON,std::string,std::less<enum _WNP_CP_DISCONNECT_REASON>,std::allocator<std::pair<enum _WNP_CP_DISCONNECT_REASON const,std::string>>,0>>::~_Tree<std::_Tmap_traits<enum _WNP_CP_DISCONNECT_REASON,std::string,std::less<enum _WNP_CP_DISCONNECT_REASON>,std::allocator<std::pair<enum _WNP_CP_DISCONNECT_REASON const,std::string>>,0>>(&v15);
    `eh vector destructor iterator'(
      &v19,
      0x28u,
      0x17u,
      (void (*)(void *))std::pair<unsigned long const,std::string>::~pair<unsigned long const,std::string>);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 4) != 0 && *((_BYTE *)v6 + 25) >= 6u )
    WPP_SF_(v6[2], 574, &WPP_4e47059d20e03c0ffeb37878b8bdc70f_Traceguids);
  std::_Tree<std::_Tmap_traits<enum _WNP_CP_DISCONNECT_REASON,std::string,std::less<enum _WNP_CP_DISCONNECT_REASON>,std::allocator<std::pair<enum _WNP_CP_DISCONNECT_REASON const,std::string>>,0>>::_Find_lower_bound<enum _WNP_CP_DISCONNECT_REASON>(
    v7,
    v17,
    &v57);
  if ( *(_BYTE *)(v18 + 25) || a3 < *(_DWORD *)(v18 + 32) )
  {
    std::_Xout_of_range("invalid map<K, T> key");
    JUMPOUT(0x18003B2BFLL);
  }
  std::string::string(a2, v18 + 40);
  return a2;
}

```

## disassembly

```asm
0x18003ae50  mov     [rsp-8+arg_10], r8d
0x18003ae55  push    rbp
0x18003ae56  push    rbx
0x18003ae57  push    rsi
0x18003ae58  push    rdi
0x18003ae59  push    r13
0x18003ae5b  push    r14
0x18003ae5d  push    r15
0x18003ae5f  lea     rbp, [rsp-310h]
0x18003ae67  sub     rsp, 410h
0x18003ae6e  mov     rax, cs:__security_cookie
0x18003ae75  xor     rax, rsp
0x18003ae78  mov     [rbp+340h+var_40], rax
0x18003ae7f  mov     r14d, r8d
0x18003ae82  mov     rsi, rdx
0x18003ae85  mov     rdi, rcx
0x18003ae88  mov     [rsp+440h+var_420], rdx
0x18003ae8d  lea     r13, WPP_GLOBAL_Control
0x18003ae94  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ae9b  cmp     rcx, r13
0x18003ae9e  jz      short loc_18003AEC8
0x18003aea0  test    byte ptr [rcx+1Ch], 4
0x18003aea4  jz      short loc_18003AEC8
0x18003aea6  cmp     byte ptr [rcx+19h], 6
0x18003aeaa  jb      short loc_18003AEC8
0x18003aeac  mov     edx, 23Dh
0x18003aeb1  lea     r8, WPP_4e47059d20e03c0ffeb37878b8bdc70f_Traceguids
0x18003aeb8  mov     rcx, [rcx+10h]
0x18003aebc  call    WPP_SF_
0x18003aec1  mov     rcx, cs:WPP_GLOBAL_Control
0x18003aec8  add     rdi, 118h
0x18003aecf  cmp     qword ptr [rdi+8], 0
0x18003aed4  jnz     loc_18003B237
0x18003aeda  mov     [rsp+440h+var_3E0], 0
0x18003aee2  lea     rdx, aNone; "None"
0x18003aee9  lea     rcx, [rsp+440h+var_3D8]
0x18003aeee  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003aef3  nop
0x18003aef4  mov     [rbp+340h+var_3B8], 1
0x18003aefb  lea     rdx, aSystemsuspend; "SystemSuspend"
0x18003af02  lea     rcx, [rbp+340h+var_3B0]
0x18003af06  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003af0b  nop
0x18003af0c  mov     dword ptr [rsp+440h+var_420], 2
0x18003af14  lea     r8, aServercommande_2; "ServerCommandErrorCNT"
0x18003af1b  lea     rdx, [rsp+440h+var_420]
0x18003af20  lea     rcx, [rbp+340h+var_390]
0x18003af24  call    ??$?0W4_WNP_CP_DISCONNECT_REASON@@AEAY0BG@$$CBD$0A@@?$pair@$$CBW4_WNP_CP_DISCONNECT_REASON@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@QEAA@$$QEAW4_WNP_CP_DISCONNECT_REASON@@AEAY0BG@$$CBD@Z; std::pair<_WNP_CP_DISCONNECT_REASON const,std::string>::pair<_WNP_CP_DISCONNECT_REASON const,std::string>(_WNP_CP_DISCONNECT_REASON &&,char const (&)[22])
0x18003af29  nop
0x18003af2a  mov     dword ptr [rsp+440h+var_420], 3
0x18003af32  lea     r8, aServercommande; "ServerCommandErrorATH"
0x18003af39  lea     rdx, [rsp+440h+var_420]
0x18003af3e  lea     rcx, [rbp+340h+var_368]
0x18003af42  call    ??$?0W4_WNP_CP_DISCONNECT_REASON@@AEAY0BG@$$CBD$0A@@?$pair@$$CBW4_WNP_CP_DISCONNECT_REASON@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@QEAA@$$QEAW4_WNP_CP_DISCONNECT_REASON@@AEAY0BG@$$CBD@Z; std::pair<_WNP_CP_DISCONNECT_REASON const,std::string>::pair<_WNP_CP_DISCONNECT_REASON const,std::string>(_WNP_CP_DISCONNECT_REASON &&,char const (&)[22])
0x18003af47  nop
0x18003af48  mov     dword ptr [rsp+440h+var_420], 4
0x18003af50  lea     r8, aServercommande_0; "ServerCommandErrorBND"
0x18003af57  lea     rdx, [rsp+440h+var_420]
0x18003af5c  lea     rcx, [rbp+340h+var_340]
0x18003af60  call    ??$?0W4_WNP_CP_DISCONNECT_REASON@@AEAY0BG@$$CBD$0A@@?$pair@$$CBW4_WNP_CP_DISCONNECT_REASON@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@QEAA@$$QEAW4_WNP_CP_DISCONNECT_REASON@@AEAY0BG@$$CBD@Z; std::pair<_WNP_CP_DISCONNECT_REASON const,std::string>::pair<_WNP_CP_DISCONNECT_REASON const,std::string>(_WNP_CP_DISCONNECT_REASON &&,char const (&)[22])
0x18003af65  nop
0x18003af66  mov     [rbp+340h+var_318], 5
0x18003af6d  lea     rdx, aServercommande_3; "ServerCommandErrorUBND"
0x18003af74  lea     rcx, [rbp+340h+var_310]
0x18003af78  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003af7d  nop
0x18003af7e  mov     [rbp+340h+var_2F0], 6
0x18003af85  lea     rdx, aServercommande_1; "ServerCommandErrorUnknown"
0x18003af8c  lea     rcx, [rbp+340h+var_2E8]
0x18003af90  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003af95  nop
0x18003af96  mov     [rbp+340h+var_2C8], 7
0x18003af9d  lea     rdx, aServerout; "ServerOUT"
0x18003afa4  lea     rcx, [rbp+340h+var_2C0]
0x18003afab  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003afb0  nop
0x18003afb1  mov     [rbp+340h+var_2A0], 8
0x18003afbb  lea     rdx, aServeroutoth; "ServerOUTOTH"
0x18003afc2  lea     rcx, [rbp+340h+var_298]
0x18003afc9  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003afce  nop
0x18003afcf  mov     [rbp+340h+var_278], 9
0x18003afd9  lea     rdx, aServeroutoos; "ServerOUTOOS"
0x18003afe0  lea     rcx, [rbp+340h+var_270]
0x18003afe7  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003afec  nop
0x18003afed  mov     dword ptr [rsp+440h+var_420], 0Ah
0x18003aff5  lea     r8, aServerouterror; "ServerOUTErrorCode"
0x18003affc  lea     rdx, [rsp+440h+var_420]
0x18003b001  lea     rcx, [rbp+340h+var_250]
0x18003b008  call    ??$?0W4_WNP_CP_DISCONNECT_REASON@@AEAY0BG@$$CBD$0A@@?$pair@$$CBW4_WNP_CP_DISCONNECT_REASON@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@QEAA@$$QEAW4_WNP_CP_DISCONNECT_REASON@@AEAY0BG@$$CBD@Z; std::pair<_WNP_CP_DISCONNECT_REASON const,std::string>::pair<_WNP_CP_DISCONNECT_REASON const,std::string>(_WNP_CP_DISCONNECT_REASON &&,char const (&)[22])
0x18003b00d  nop
0x18003b00e  mov     dword ptr [rsp+440h+var_420], 0Bh
0x18003b016  lea     r8, aServeroutunexp; "ServerOUTUnexpected"
0x18003b01d  lea     rdx, [rsp+440h+var_420]
0x18003b022  lea     rcx, [rbp+340h+var_228]
0x18003b029  call    ??$?0W4_WNP_CP_DISCONNECT_REASON@@AEAY0BG@$$CBD$0A@@?$pair@$$CBW4_WNP_CP_DISCONNECT_REASON@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@QEAA@$$QEAW4_WNP_CP_DISCONNECT_REASON@@AEAY0BG@$$CBD@Z; std::pair<_WNP_CP_DISCONNECT_REASON const,std::string>::pair<_WNP_CP_DISCONNECT_REASON const,std::string>(_WNP_CP_DISCONNECT_REASON &&,char const (&)[22])
0x18003b02e  nop
0x18003b02f  mov     [rbp+340h+var_200], 0Ch
0x18003b039  lea     rdx, aXfr_0; "XFR"
0x18003b040  lea     rcx, [rbp+340h+var_1F8]
0x18003b047  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003b04c  nop
0x18003b04d  mov     [rbp+340h+var_1D8], 0Dh
0x18003b057  lea     rdx, aXfrfallbackfai; "XFRFallbackFailed"
0x18003b05e  lea     rcx, [rbp+340h+var_1D0]
0x18003b065  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003b06a  nop
0x18003b06b  mov     [rbp+340h+var_1B0], 0Eh
0x18003b075  lea     rdx, aKeepalivetimeo; "KeepAliveTimeOut"
0x18003b07c  lea     rcx, [rbp+340h+var_1A8]
0x18003b083  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003b088  nop
0x18003b089  mov     dword ptr [rsp+440h+var_420], 0Fh
0x18003b091  lea     r8, aConnectiontime; "ConnectionTimedOut"
0x18003b098  lea     rdx, [rsp+440h+var_420]
0x18003b09d  lea     rcx, [rbp+340h+var_188]
0x18003b0a4  call    ??$?0W4_WNP_CP_DISCONNECT_REASON@@AEAY0BG@$$CBD$0A@@?$pair@$$CBW4_WNP_CP_DISCONNECT_REASON@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@QEAA@$$QEAW4_WNP_CP_DISCONNECT_REASON@@AEAY0BG@$$CBD@Z; std::pair<_WNP_CP_DISCONNECT_REASON const,std::string>::pair<_WNP_CP_DISCONNECT_REASON const,std::string>(_WNP_CP_DISCONNECT_REASON &&,char const (&)[22])
0x18003b0a9  nop
0x18003b0aa  mov     dword ptr [rsp+440h+var_420], 10h
0x18003b0b2  lea     r8, aNetworkdisconn; "NetworkDisconnected"
0x18003b0b9  lea     rdx, [rsp+440h+var_420]
0x18003b0be  lea     rcx, [rbp+340h+var_160]
0x18003b0c5  call    ??$?0W4_WNP_CP_DISCONNECT_REASON@@AEAY0BG@$$CBD$0A@@?$pair@$$CBW4_WNP_CP_DISCONNECT_REASON@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@QEAA@$$QEAW4_WNP_CP_DISCONNECT_REASON@@AEAY0BG@$$CBD@Z; std::pair<_WNP_CP_DISCONNECT_REASON const,std::string>::pair<_WNP_CP_DISCONNECT_REASON const,std::string>(_WNP_CP_DISCONNECT_REASON &&,char const (&)[22])
0x18003b0ca  nop
0x18003b0cb  mov     [rbp+340h+var_138], 11h
0x18003b0d5  lea     rdx, aPreferredinter; "PreferredInterfaceChange"
0x18003b0dc  lea     rcx, [rbp+340h+var_130]
0x18003b0e3  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003b0e8  nop
0x18003b0e9  mov     [rbp+340h+var_110], 12h
0x18003b0f3  lea     rdx, aStopkeepalivem; "StopKeepAliveMeasurement"
0x18003b0fa  lea     rcx, [rbp+340h+var_108]
0x18003b101  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003b106  nop
0x18003b107  mov     dword ptr [rsp+440h+var_420], 13h
0x18003b10f  lea     r8, aKeepaliveconve; "KeepAliveConverged"
0x18003b116  lea     rdx, [rsp+440h+var_420]
0x18003b11b  lea     rcx, [rbp+340h+var_E8]
0x18003b122  call    ??$?0W4_WNP_CP_DISCONNECT_REASON@@AEAY0BG@$$CBD$0A@@?$pair@$$CBW4_WNP_CP_DISCONNECT_REASON@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@QEAA@$$QEAW4_WNP_CP_DISCONNECT_REASON@@AEAY0BG@$$CBD@Z; std::pair<_WNP_CP_DISCONNECT_REASON const,std::string>::pair<_WNP_CP_DISCONNECT_REASON const,std::string>(_WNP_CP_DISCONNECT_REASON &&,char const (&)[22])
0x18003b127  nop
0x18003b128  mov     [rbp+340h+var_C0], 14h
0x18003b132  lea     rdx, aReducemaxkatim; "ReduceMaxKATime"
0x18003b139  lea     rcx, [rbp+340h+var_B8]
0x18003b140  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003b145  nop
0x18003b146  mov     dword ptr [rsp+440h+var_420], 15h
0x18003b14e  lea     r8, aUpperlayerinit; "UpperLayerInitiated"
0x18003b155  lea     rdx, [rsp+440h+var_420]
0x18003b15a  lea     rcx, [rbp+340h+var_98]
0x18003b161  call    ??$?0W4_WNP_CP_DISCONNECT_REASON@@AEAY0BG@$$CBD$0A@@?$pair@$$CBW4_WNP_CP_DISCONNECT_REASON@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@QEAA@$$QEAW4_WNP_CP_DISCONNECT_REASON@@AEAY0BG@$$CBD@Z; std::pair<_WNP_CP_DISCONNECT_REASON const,std::string>::pair<_WNP_CP_DISCONNECT_REASON const,std::string>(_WNP_CP_DISCONNECT_REASON &&,char const (&)[22])
0x18003b166  nop
0x18003b167  mov     [rbp+340h+var_70], 16h
0x18003b171  lea     rdx, aDisconnectedst; "DisconnectedStatusFromPNG"
0x18003b178  lea     rcx, [rbp+340h+var_68]
0x18003b17f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003b184  nop
0x18003b185  lea     rcx, [rsp+440h+var_418]
0x18003b18a  call    ??0?$_Tree@V?$_Tmap_traits@W4LogCommandFailureContext@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4LogCommandFailureContext@@@3@V?$allocator@U?$pair@$$CBW4LogCommandFailureContext@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@3@$0A@@std@@@std@@QEAA@AEBU?$less@W4LogCommandFailureContext@@@1@@Z; std::_Tree<std::_Tmap_traits<LogCommandFailureContext,std::wstring,std::less<LogCommandFailureContext>,std::allocator<std::pair<LogCommandFailureContext const,std::wstring>>,0>>::_Tree<std::_Tmap_traits<LogCommandFailureContext,std::wstring,std::less<LogCommandFailureContext>,std::allocator<std::pair<LogCommandFailureContext const,std::wstring>>,0>>(std::less<LogCommandFailureContext> const &)
0x18003b18f  nop
0x18003b190  mov     r15, [rsp+440h+var_418]
0x18003b195  lea     rbx, [rsp+440h+var_3E0]
0x18003b19a  mov     r8, rbx
0x18003b19d  mov     rdx, r15
0x18003b1a0  lea     rcx, [rsp+440h+var_418]
0x18003b1a5  call    ??$_Emplace_hint@AEBU?$pair@$$CBW4_WNP_CP_DISCONNECT_REASON@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@@?$_Tree@V?$_Tmap_traits@W4_WNP_CP_DISCONNECT_REASON@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$less@W4_WNP_CP_DISCONNECT_REASON@@@3@V?$allocator@U?$pair@$$CBW4_WNP_CP_DISCONNECT_REASON@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@@3@$0A@@std@@@std@@IEAAPEAU?$_Tree_node@U?$pair@$$CBW4_WNP_CP_DISCONNECT_REASON@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@PEAX@1@QEAU21@AEBU?$pair@$$CBW4_WNP_CP_DISCONNECT_REASON@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<_WNP_CP_DISCONNECT_REASON,std::string,std::less<_WNP_CP_DISCONNECT_REASON>,std::allocator<std::pair<_WNP_CP_DISCONNECT_REASON const,std::string>>,0>>::_Emplace_hint<std::pair<_WNP_CP_DISCONNECT_REASON const,std::string> const &>(std::_Tree_node<std::pair<_WNP_CP_DISCONNECT_REASON const,std::string>,void *> * const,std::pair<_WNP_CP_DISCONNECT_REASON const,std::string> const &)
0x18003b1aa  add     rbx, 28h ; '('
0x18003b1ae  lea     rax, [rbp+340h+var_48]
0x18003b1b5  cmp     rbx, rax
0x18003b1b8  jnz     short loc_18003B19A
0x18003b1ba  lea     rax, [rsp+440h+var_418]
0x18003b1bf  cmp     rdi, rax
0x18003b1c2  jz      short loc_18003B20B
0x18003b1c4  mov     rbx, [rdi]
0x18003b1c7  mov     r8, [rbx+8]
0x18003b1cb  mov     rdx, rdi
0x18003b1ce  mov     rcx, rdi
0x18003b1d1  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBW4_WNP_CP_DISCONNECT_REASON@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4_WNP_CP_DISCONNECT_REASON@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBW4_WNP_CP_DISCONNECT_REASON@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBW4_WNP_CP_DISCONNECT_REASON@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_WNP_CP_DISCONNECT_REASON const,std::string>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<_WNP_CP_DISCONNECT_REASON const,std::string>,void *>>>(std::allocator<std::_Tree_node<std::pair<_WNP_CP_DISCONNECT_REASON const,std::string>,void *>> &,std::_Tree_node<std::pair<_WNP_CP_DISCONNECT_REASON const,std::string>,void *> *)
0x18003b1d6  mov     [rbx+8], rbx
0x18003b1da  mov     [rbx], rbx
0x18003b1dd  mov     [rbx+10h], rbx
0x18003b1e1  mov     qword ptr [rdi+8], 0
0x18003b1e9  mov     rcx, [rdi]
0x18003b1ec  mov     rax, [rsp+440h+var_418]
0x18003b1f1  mov     [rdi], rax
0x18003b1f4  mov     [rsp+440h+var_418], rcx
0x18003b1f9  mov     rcx, [rdi+8]
0x18003b1fd  mov     rax, [rsp+440h+var_410]
0x18003b202  mov     [rdi+8], rax
0x18003b206  mov     [rsp+440h+var_410], rcx
0x18003b20b  lea     rcx, [rsp+440h+var_418]
0x18003b210  call    ??1?$_Tree@V?$_Tmap_traits@W4_WNP_CP_DISCONNECT_REASON@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$less@W4_WNP_CP_DISCONNECT_REASON@@@3@V?$allocator@U?$pair@$$CBW4_WNP_CP_DISCONNECT_REASON@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<_WNP_CP_DISCONNECT_REASON,std::string,std::less<_WNP_CP_DISCONNECT_REASON>,std::allocator<std::pair<_WNP_CP_DISCONNECT_REASON const,std::string>>,0>>::~_Tree<std::_Tmap_traits<_WNP_CP_DISCONNECT_REASON,std::string,std::less<_WNP_CP_DISCONNECT_REASON>,std::allocator<std::pair<_WNP_CP_DISCONNECT_REASON const,std::string>>,0>>(void)
0x18003b215  nop
0x18003b216  lea     r9, ??1?$pair@$$CBKV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@QEAA@XZ; void (*)(void *)
0x18003b21d  mov     edx, 28h ; '('; unsigned __int64
0x18003b222  lea     r8d, [rdx-11h]; unsigned __int64
0x18003b226  lea     rcx, [rsp+440h+var_3E0]; void *
0x18003b22b  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18003b230  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b237  cmp     rcx, r13
0x18003b23a  jz      short loc_18003B25D
0x18003b23c  test    byte ptr [rcx+1Ch], 4
0x18003b240  jz      short loc_18003B25D
0x18003b242  cmp     byte ptr [rcx+19h], 6
0x18003b246  jb      short loc_18003B25D
0x18003b248  mov     edx, 23Eh
0x18003b24d  lea     r8, WPP_4e47059d20e03c0ffeb37878b8bdc70f_Traceguids
0x18003b254  mov     rcx, [rcx+10h]
0x18003b258  call    WPP_SF_
0x18003b25d  lea     r8, [rbp+340h+arg_10]
0x18003b264  lea     rdx, [rsp+440h+var_400]
0x18003b269  mov     rcx, rdi
0x18003b26c  call    ??$_Find_lower_bound@W4_WNP_CP_DISCONNECT_REASON@@@?$_Tree@V?$_Tmap_traits@W4_WNP_CP_DISCONNECT_REASON@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$less@W4_WNP_CP_DISCONNECT_REASON@@@3@V?$allocator@U?$pair@$$CBW4_WNP_CP_DISCONNECT_REASON@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@@3@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBW4_WNP_CP_DISCONNECT_REASON@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@PEAX@std@@@1@AEBW4_WNP_CP_DISCONNECT_REASON@@@Z; std::_Tree<std::_Tmap_traits<_WNP_CP_DISCONNECT_REASON,std::string,std::less<_WNP_CP_DISCONNECT_REASON>,std::allocator<std::pair<_WNP_CP_DISCONNECT_REASON const,std::string>>,0>>::_Find_lower_bound<_WNP_CP_DISCONNECT_REASON>(_WNP_CP_DISCONNECT_REASON const &)
0x18003b271  mov     rdx, [rsp+440h+var_3F0]
0x18003b276  cmp     byte ptr [rdx+19h], 0
0x18003b27a  jnz     short loc_18003B2B2
0x18003b27c  cmp     r14d, [rdx+20h]
0x18003b280  jl      short loc_18003B2B2
0x18003b282  add     rdx, 28h ; '('
0x18003b286  mov     rcx, rsi
0x18003b289  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x18003b28e  mov     rax, rsi
0x18003b291  mov     rcx, [rbp+340h+var_40]
0x18003b298  xor     rcx, rsp; StackCookie
0x18003b29b  call    __security_check_cookie
0x18003b2a0  add     rsp, 410h
0x18003b2a7  pop     r15
0x18003b2a9  pop     r14
0x18003b2ab  pop     r13
0x18003b2ad  pop     rdi
0x18003b2ae  pop     rsi
0x18003b2af  pop     rbx
0x18003b2b0  pop     rbp
0x18003b2b1  retn
0x18003b2b2  lea     rcx, aInvalidMapKTKe; "invalid map<K, T> key"
0x18003b2b9  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
```
