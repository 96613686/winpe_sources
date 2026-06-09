# CConnectionEx::GetProtocolStatus(__MIDL_RCMPublic_0006,_PROTOCOLSTATUSEX *)

- ea: `0x18001c010`
- end: `0x18001c88a`
- name: `?GetProtocolStatus@CConnectionEx@@UEAAJW4__MIDL_RCMPublic_0006@@PEAU_PROTOCOLSTATUSEX@@@Z`
- size: `2170`
- prototype: `int __high(enum __MIDL_RCMPublic_0006, struct _PROTOCOLSTATUSEX *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000bdb0`
- `0x18001c010`
- `0x180033f60`
- `0x180034e64`
- `0x1800ce010`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x18001c133`
- `ntdll!EtwEventWriteTransfer` at `0x18001c133`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c057`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c057`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c146`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c163`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c146`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c163`

## string_xrefs

- `0x18001c091`: `CConnectionEx::GetProtocolStatus called after BrokenConnection was signaled. Returning ERROR_NOT_CONNECTED`

## pseudocode

```c
__int64 __fastcall CConnectionEx::GetProtocolStatus(__int64 a1, __int64 a2, __int64 a3)
{
  int v6; // r9d
  _DWORD v7[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v8; // [rsp+40h] [rbp-C0h]
  _WTS_PROTOCOL_COUNTERS v9; // [rsp+50h] [rbp-B0h] BYREF
  struct _WTS_PROTOCOL_COUNTERS v10; // [rsp+220h] [rbp+120h] BYREF
  int v11; // [rsp+3F0h] [rbp+2F0h]
  int v12; // [rsp+3F4h] [rbp+2F4h]
  int v13; // [rsp+3F8h] [rbp+2F8h]
  int v14; // [rsp+3FCh] [rbp+2FCh]
  int v15; // [rsp+400h] [rbp+300h]
  int v16; // [rsp+404h] [rbp+304h]
  int v17; // [rsp+408h] [rbp+308h]
  int v18; // [rsp+40Ch] [rbp+30Ch]
  int v19; // [rsp+410h] [rbp+310h]
  int v20; // [rsp+414h] [rbp+314h]
  int v21; // [rsp+418h] [rbp+318h]
  int v22; // [rsp+41Ch] [rbp+31Ch]
  int v23; // [rsp+420h] [rbp+320h]
  int v24; // [rsp+424h] [rbp+324h]
  int v25; // [rsp+428h] [rbp+328h]
  int v26; // [rsp+42Ch] [rbp+32Ch]
  int v27; // [rsp+430h] [rbp+330h]
  int v28; // [rsp+434h] [rbp+334h]
  int v29; // [rsp+438h] [rbp+338h]
  int v30; // [rsp+43Ch] [rbp+33Ch]
  int v31; // [rsp+440h] [rbp+340h]
  int v32; // [rsp+448h] [rbp+348h]
  int v33; // [rsp+44Ch] [rbp+34Ch]
  __int64 v34; // [rsp+450h] [rbp+350h]
  __int64 v35; // [rsp+458h] [rbp+358h]
  __int64 v36; // [rsp+460h] [rbp+360h]
  __int64 v37; // [rsp+468h] [rbp+368h]
  __int64 v38; // [rsp+470h] [rbp+370h]
  __int64 v39; // [rsp+478h] [rbp+378h]
  __int64 v40; // [rsp+480h] [rbp+380h]
  __int64 v41; // [rsp+488h] [rbp+388h]
  __int64 v42; // [rsp+490h] [rbp+390h]
  __int64 v43; // [rsp+498h] [rbp+398h]
  __int64 v44; // [rsp+4A0h] [rbp+3A0h]
  __int64 v45; // [rsp+4A8h] [rbp+3A8h]
  __int64 v46; // [rsp+4B0h] [rbp+3B0h]
  __int64 v47; // [rsp+4B8h] [rbp+3B8h]
  __int64 v48; // [rsp+4C0h] [rbp+3C0h]
  __int64 v49; // [rsp+4C8h] [rbp+3C8h]
  __int64 v50; // [rsp+4D0h] [rbp+3D0h]
  __int64 v51; // [rsp+4D8h] [rbp+3D8h]
  __int64 v52; // [rsp+4E0h] [rbp+3E0h]
  __int64 v53; // [rsp+4E8h] [rbp+3E8h]
  __int64 v54; // [rsp+4F0h] [rbp+3F0h]
  __int64 v55; // [rsp+4F8h] [rbp+3F8h]
  __int64 v56; // [rsp+500h] [rbp+400h]
  __int64 v57; // [rsp+508h] [rbp+408h]
  __int64 v58; // [rsp+510h] [rbp+410h]
  __int64 v59; // [rsp+518h] [rbp+418h]
  __int64 v60; // [rsp+520h] [rbp+420h]
  __int64 v61; // [rsp+528h] [rbp+428h]
  __int64 v62; // [rsp+530h] [rbp+430h]
  __int64 v63; // [rsp+538h] [rbp+438h]
  __int64 v64; // [rsp+540h] [rbp+440h]
  __int64 v65; // [rsp+548h] [rbp+448h]
  __int64 v66; // [rsp+550h] [rbp+450h]
  __int64 v67; // [rsp+558h] [rbp+458h]
  __int64 v68; // [rsp+560h] [rbp+460h]
  __int64 v69; // [rsp+568h] [rbp+468h]
  __int64 v70; // [rsp+570h] [rbp+470h]
  __int64 v71; // [rsp+578h] [rbp+478h]
  __int64 v72; // [rsp+580h] [rbp+480h]
  __int64 v73; // [rsp+588h] [rbp+488h]
  __int64 v74; // [rsp+590h] [rbp+490h]
  __int64 v75; // [rsp+598h] [rbp+498h]
  __int64 v76; // [rsp+5A0h] [rbp+4A0h]
  __int64 v77; // [rsp+5A8h] [rbp+4A8h]
  __int64 v78; // [rsp+5B0h] [rbp+4B0h]
  __int64 v79; // [rsp+5B8h] [rbp+4B8h]
  __int64 v80; // [rsp+5C0h] [rbp+4C0h]
  __int64 v81; // [rsp+5C8h] [rbp+4C8h]
  __int64 v82; // [rsp+5D0h] [rbp+4D0h]
  __int64 v83; // [rsp+5D8h] [rbp+4D8h]
  __int64 v84; // [rsp+5E0h] [rbp+4E0h]
  __int64 v85; // [rsp+5E8h] [rbp+4E8h]
  __int64 v86; // [rsp+5F0h] [rbp+4F0h]
  __int64 v87; // [rsp+5F8h] [rbp+4F8h]
  __int64 v88; // [rsp+600h] [rbp+500h]
  __int64 v89; // [rsp+608h] [rbp+508h]
  __int64 v90; // [rsp+610h] [rbp+510h]
  __int64 v91; // [rsp+618h] [rbp+518h]
  __int64 v92; // [rsp+620h] [rbp+520h]
  __int64 v93; // [rsp+628h] [rbp+528h]
  __int64 v94; // [rsp+630h] [rbp+530h]
  __int64 v95; // [rsp+638h] [rbp+538h]
  __int64 v96; // [rsp+640h] [rbp+540h]
  __int64 v97; // [rsp+648h] [rbp+548h]
  __int64 v98; // [rsp+650h] [rbp+550h]
  __int64 v99; // [rsp+658h] [rbp+558h]
  __int64 v100; // [rsp+660h] [rbp+560h]
  __int64 v101; // [rsp+668h] [rbp+568h]
  __int64 v102; // [rsp+670h] [rbp+570h]
  __int64 v103; // [rsp+678h] [rbp+578h]
  __int64 v104; // [rsp+680h] [rbp+580h]
  __int64 v105; // [rsp+688h] [rbp+588h]
  __int64 v106; // [rsp+690h] [rbp+590h]
  __int64 v107; // [rsp+698h] [rbp+598h]
  __int64 v108; // [rsp+6A0h] [rbp+5A0h]
  __int64 v109; // [rsp+6A8h] [rbp+5A8h]
  __int64 v110; // [rsp+6B0h] [rbp+5B0h]
  __int64 v111; // [rsp+6B8h] [rbp+5B8h]
  __int64 v112; // [rsp+6C0h] [rbp+5C0h]
  __int64 v113; // [rsp+6C8h] [rbp+5C8h]
  __int64 v114; // [rsp+6D0h] [rbp+5D0h]
  __int64 v115; // [rsp+6D8h] [rbp+5D8h]
  __int64 v116; // [rsp+6E0h] [rbp+5E0h]
  __int64 v117; // [rsp+6E8h] [rbp+5E8h]
  __int64 v118; // [rsp+6F0h] [rbp+5F0h]
  __int64 v119; // [rsp+6F8h] [rbp+5F8h]
  __int64 v120; // [rsp+700h] [rbp+600h]
  __int64 v121; // [rsp+708h] [rbp+608h]
  __int64 v122; // [rsp+710h] [rbp+610h]
  __int64 v123; // [rsp+718h] [rbp+618h]
  __int64 v124; // [rsp+720h] [rbp+620h]
  __int64 v125; // [rsp+728h] [rbp+628h]
  __int64 v126; // [rsp+730h] [rbp+630h]
  __int64 v127; // [rsp+738h] [rbp+638h]
  __int64 v128; // [rsp+740h] [rbp+640h]
  __int64 v129; // [rsp+748h] [rbp+648h]
  __int64 v130; // [rsp+750h] [rbp+650h]
  __int64 v131; // [rsp+758h] [rbp+658h]
  __int64 v132; // [rsp+760h] [rbp+660h]
  __int64 v133; // [rsp+768h] [rbp+668h]
  char *v134; // [rsp+770h] [rbp+670h] BYREF
  int v135; // [rsp+778h] [rbp+678h]
  int v136; // [rsp+77Ch] [rbp+67Ch]
  char *v137; // [rsp+780h] [rbp+680h]
  int v138; // [rsp+788h] [rbp+688h]
  int v139; // [rsp+78Ch] [rbp+68Ch]
  const char *v140; // [rsp+790h] [rbp+690h]
  __int64 v141; // [rsp+798h] [rbp+698h]

  memset_0(&v9, 0, 0x720u);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 1648));
  if ( *(_DWORD *)(a1 + 17868) == 1 )
  {
    if ( (unsigned int)dword_18012E170 > 2 )
    {
      v141 = 107;
      v8 = 0;
      v140 = "CConnectionEx::GetProtocolStatus called after BrokenConnection was signaled. Returning ERROR_NOT_CONNECTED";
      v7[1] = 2;
      v134 = (char *)off_18012E178;
      v7[0] = 184549376;
      v135 = *(unsigned __int16 *)off_18012E178;
      v137 = &byte_180115ACF;
      v136 = 2;
      v138 = 21;
      v139 = 1;
      EtwEventWriteTransfer(RegHandle, v7, 0, 0, 3, &v134);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 1648));
    return 2147944650LL;
  }
  else
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 1648));
    v6 = (*(__int64 (__fastcall **)(_QWORD, _WTS_PROTOCOL_COUNTERS *))(**(_QWORD **)(a1 + 1592) + 160LL))(
           *(_QWORD *)(a1 + 1592),
           &v9);
    if ( v6 >= 0 )
    {
      CHelper::WTSConvertProtocolCounters(&v9, (struct _PROTOCOLCOUNTERS *)a3);
      CHelper::WTSConvertProtocolCounters(&v10, (struct _PROTOCOLCOUNTERS *)(a3 + 460));
      if ( v11 != 1 )
      {
        if ( v11 == 2 )
        {
          *(_DWORD *)(a3 + 924) = v12;
        }
        else if ( v11 == 3 )
        {
          *(_DWORD *)(a3 + 924) = v12;
          *(_DWORD *)(a3 + 928) = v13;
          *(_DWORD *)(a3 + 932) = v14;
          *(_DWORD *)(a3 + 936) = v15;
          *(_DWORD *)(a3 + 940) = v16;
          *(_DWORD *)(a3 + 944) = v17;
          *(_DWORD *)(a3 + 948) = v18;
          *(_DWORD *)(a3 + 952) = v19;
          *(_DWORD *)(a3 + 956) = v20;
          *(_DWORD *)(a3 + 960) = v21;
          *(_DWORD *)(a3 + 964) = v22;
          *(_DWORD *)(a3 + 968) = v23;
          *(_DWORD *)(a3 + 972) = v24;
          *(_DWORD *)(a3 + 976) = v25;
          *(_DWORD *)(a3 + 980) = v26;
          *(_DWORD *)(a3 + 984) = v27;
          *(_DWORD *)(a3 + 988) = v28;
          *(_DWORD *)(a3 + 992) = v29;
          *(_DWORD *)(a3 + 996) = v30;
          *(_DWORD *)(a3 + 1000) = v31;
        }
      }
      *(_DWORD *)(a3 + 1004) = v32;
      *(_DWORD *)(a3 + 1008) = v33;
      *(_QWORD *)(a3 + 1016) = v34;
      *(_QWORD *)(a3 + 1024) = v35;
      *(_QWORD *)(a3 + 1032) = v36;
      *(_QWORD *)(a3 + 1040) = v37;
      *(_QWORD *)(a3 + 1048) = v38;
      *(_QWORD *)(a3 + 1056) = v39;
      *(_QWORD *)(a3 + 1064) = v40;
      *(_QWORD *)(a3 + 1072) = v41;
      *(_QWORD *)(a3 + 1080) = v42;
      *(_QWORD *)(a3 + 1088) = v43;
      *(_QWORD *)(a3 + 1096) = v44;
      *(_QWORD *)(a3 + 1104) = v45;
      *(_QWORD *)(a3 + 1112) = v46;
      *(_QWORD *)(a3 + 1120) = v47;
      *(_QWORD *)(a3 + 1128) = v48;
      *(_QWORD *)(a3 + 1136) = v49;
      *(_QWORD *)(a3 + 1144) = v50;
      *(_QWORD *)(a3 + 1152) = v51;
      *(_QWORD *)(a3 + 1160) = v52;
      *(_QWORD *)(a3 + 1168) = v53;
      *(_QWORD *)(a3 + 1176) = v54;
      *(_QWORD *)(a3 + 1184) = v55;
      *(_QWORD *)(a3 + 1192) = v56;
      *(_QWORD *)(a3 + 1200) = v57;
      *(_QWORD *)(a3 + 1208) = v58;
      *(_QWORD *)(a3 + 1216) = v59;
      *(_QWORD *)(a3 + 1224) = v60;
      *(_QWORD *)(a3 + 1232) = v61;
      *(_QWORD *)(a3 + 1240) = v62;
      *(_QWORD *)(a3 + 1248) = v63;
      *(_QWORD *)(a3 + 1256) = v64;
      *(_QWORD *)(a3 + 1264) = v65;
      *(_QWORD *)(a3 + 1272) = v66;
      *(_QWORD *)(a3 + 1280) = v67;
      *(_QWORD *)(a3 + 1288) = v68;
      *(_QWORD *)(a3 + 1296) = v69;
      *(_QWORD *)(a3 + 1304) = v70;
      *(_QWORD *)(a3 + 1312) = v71;
      *(_QWORD *)(a3 + 1320) = v72;
      *(_QWORD *)(a3 + 1328) = v73;
      *(_QWORD *)(a3 + 1336) = v74;
      *(_QWORD *)(a3 + 1344) = v75;
      *(_QWORD *)(a3 + 1352) = v76;
      *(_QWORD *)(a3 + 1360) = v77;
      *(_QWORD *)(a3 + 1368) = v78;
      *(_QWORD *)(a3 + 1376) = v79;
      *(_QWORD *)(a3 + 1384) = v80;
      *(_QWORD *)(a3 + 1392) = v81;
      *(_QWORD *)(a3 + 1400) = v82;
      *(_QWORD *)(a3 + 1408) = v83;
      *(_QWORD *)(a3 + 1416) = v84;
      *(_QWORD *)(a3 + 1424) = v85;
      *(_QWORD *)(a3 + 1432) = v86;
      *(_QWORD *)(a3 + 1440) = v87;
      *(_QWORD *)(a3 + 1448) = v88;
      *(_QWORD *)(a3 + 1456) = v89;
      *(_QWORD *)(a3 + 1464) = v90;
      *(_QWORD *)(a3 + 1472) = v91;
      *(_QWORD *)(a3 + 1480) = v92;
      *(_QWORD *)(a3 + 1488) = v93;
      *(_QWORD *)(a3 + 1496) = v94;
      *(_QWORD *)(a3 + 1504) = v95;
      *(_QWORD *)(a3 + 1512) = v96;
      *(_QWORD *)(a3 + 1520) = v97;
      *(_QWORD *)(a3 + 1528) = v98;
      *(_QWORD *)(a3 + 1536) = v99;
      *(_QWORD *)(a3 + 1544) = v100;
      *(_QWORD *)(a3 + 1552) = v101;
      *(_QWORD *)(a3 + 1560) = v102;
      *(_QWORD *)(a3 + 1568) = v103;
      *(_QWORD *)(a3 + 1576) = v104;
      *(_QWORD *)(a3 + 1584) = v105;
      *(_QWORD *)(a3 + 1592) = v106;
      *(_QWORD *)(a3 + 1600) = v107;
      *(_QWORD *)(a3 + 1608) = v108;
      *(_QWORD *)(a3 + 1616) = v109;
      *(_QWORD *)(a3 + 1624) = v110;
      *(_QWORD *)(a3 + 1632) = v111;
      *(_QWORD *)(a3 + 1640) = v112;
      *(_QWORD *)(a3 + 1648) = v113;
      *(_QWORD *)(a3 + 1656) = v114;
      *(_QWORD *)(a3 + 1664) = v115;
      *(_QWORD *)(a3 + 1672) = v116;
      *(_QWORD *)(a3 + 1680) = v117;
      *(_QWORD *)(a3 + 1688) = v118;
      *(_QWORD *)(a3 + 1696) = v119;
      *(_QWORD *)(a3 + 1704) = v120;
      *(_QWORD *)(a3 + 1712) = v121;
      *(_QWORD *)(a3 + 1720) = v122;
      *(_QWORD *)(a3 + 1728) = v123;
      *(_QWORD *)(a3 + 1736) = v124;
      *(_QWORD *)(a3 + 1744) = v125;
      *(_QWORD *)(a3 + 1752) = v126;
      *(_QWORD *)(a3 + 1760) = v127;
      *(_QWORD *)(a3 + 1768) = v128;
      *(_QWORD *)(a3 + 1776) = v129;
      *(_QWORD *)(a3 + 1784) = v130;
      *(_QWORD *)(a3 + 1792) = v131;
      *(_QWORD *)(a3 + 1800) = v132;
      *(_QWORD *)(a3 + 1808) = v133;
    }
    return (unsigned int)v6;
  }
}

```

## disassembly

```asm
0x18001c010  mov     [rsp-8+arg_8], rbx
0x18001c015  push    rbp
0x18001c016  push    rsi
0x18001c017  push    rdi
0x18001c018  lea     rbp, [rsp-6B0h]
0x18001c020  sub     rsp, 7B0h
0x18001c027  mov     rax, cs:__security_cookie
0x18001c02e  xor     rax, rsp
0x18001c031  mov     [rbp+6C0h+var_20], rax
0x18001c038  mov     rbx, r8
0x18001c03b  mov     rsi, rcx
0x18001c03e  mov     r8d, 720h; Size
0x18001c044  lea     rcx, [rsp+7C0h+var_770]; void *
0x18001c049  xor     edx, edx; Val
0x18001c04b  call    memset_0
0x18001c050  lea     rcx, [rsi+670h]; lpCriticalSection
0x18001c057  call    cs:__imp_EnterCriticalSection
0x18001c05e  nop     dword ptr [rax+rax+00h]
0x18001c063  cmp     dword ptr [rsi+45CCh], 1
0x18001c06a  jnz     loc_18001C15C
0x18001c070  mov     eax, cs:dword_18012E170
0x18001c076  cmp     eax, 2
0x18001c079  jbe     loc_18001C13F
0x18001c07f  xor     ecx, ecx
0x18001c081  mov     [rbp+6C0h+var_28], 6Bh ; 'k'
0x18001c08c  mov     [rsp+7C0h+var_780], rcx
0x18001c091  lea     rax, aCconnectionexG_4; "CConnectionEx::GetProtocolStatus called"...
0x18001c098  mov     [rbp+6C0h+var_30], rax
0x18001c09f  lea     rcx, _TraceLoggingMetadata
0x18001c0a6  movzx   eax, cs:word_180115AC5
0x18001c0ad  lea     rdx, [rsp+7C0h+var_788]
0x18001c0b2  mov     [rsp+7C0h+var_784], eax
0x18001c0b6  xor     r9d, r9d
0x18001c0b9  mov     rax, cs:off_18012E178
0x18001c0c0  xor     r8d, r8d
0x18001c0c3  mov     [rbp+6C0h+var_50], rax
0x18001c0ca  mov     [rsp+7C0h+var_788], 0B000000h
0x18001c0d2  movzx   eax, word ptr [rax]
0x18001c0d5  mov     [rbp+6C0h+var_48], eax
0x18001c0db  lea     rax, byte_180115ACF
0x18001c0e2  mov     [rbp+6C0h+var_40], rax
0x18001c0e9  lea     rax, _TraceLoggingMetadataEnd
0x18001c0f0  sub     eax, ecx
0x18001c0f2  mov     [rbp+6C0h+var_44], 2
0x18001c0fc  mov     [rbp+6C0h+var_38], 15h
0x18001c106  mov     [rbp+6C0h+var_34], 1
0x18001c110  mov     [rsp+7C0h+var_790], eax
0x18001c114  mov     eax, [rsp+7C0h+var_790]
0x18001c118  mov     rcx, cs:RegHandle
0x18001c11f  lea     rax, [rbp+6C0h+var_50]
0x18001c126  mov     [rsp+7C0h+var_798], rax
0x18001c12b  mov     [rsp+7C0h+var_7A0], 3
0x18001c133  call    cs:__imp_EtwEventWriteTransfer
0x18001c13a  nop     dword ptr [rax+rax+00h]
0x18001c13f  lea     rcx, [rsi+670h]; lpCriticalSection
0x18001c146  call    cs:__imp_LeaveCriticalSection
0x18001c14d  nop     dword ptr [rax+rax+00h]
0x18001c152  mov     eax, 800708CAh
0x18001c157  jmp     loc_18001C867
0x18001c15c  lea     rcx, [rsi+670h]; lpCriticalSection
0x18001c163  call    cs:__imp_LeaveCriticalSection
0x18001c16a  nop     dword ptr [rax+rax+00h]
0x18001c16f  mov     rcx, [rsi+638h]
0x18001c176  lea     rdx, [rsp+7C0h+var_770]
0x18001c17b  mov     rax, [rcx]
0x18001c17e  mov     rax, [rax+0A0h]
0x18001c185  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c18a  mov     r9d, eax
0x18001c18d  test    eax, eax
0x18001c18f  js      loc_18001C864
0x18001c195  mov     rdx, rbx; struct _PROTOCOLCOUNTERS *
0x18001c198  lea     rcx, [rsp+7C0h+var_770]; struct _WTS_PROTOCOL_COUNTERS *
0x18001c19d  call    ?WTSConvertProtocolCounters@CHelper@@CAJPEAU_WTS_PROTOCOL_COUNTERS@@PEAU_PROTOCOLCOUNTERS@@@Z; CHelper::WTSConvertProtocolCounters(_WTS_PROTOCOL_COUNTERS *,_PROTOCOLCOUNTERS *)
0x18001c1a2  lea     rdx, [rbx+1CCh]; struct _PROTOCOLCOUNTERS *
0x18001c1a9  lea     rcx, [rbp+6C0h+var_5A0]; struct _WTS_PROTOCOL_COUNTERS *
0x18001c1b0  call    ?WTSConvertProtocolCounters@CHelper@@CAJPEAU_WTS_PROTOCOL_COUNTERS@@PEAU_PROTOCOLCOUNTERS@@@Z; CHelper::WTSConvertProtocolCounters(_WTS_PROTOCOL_COUNTERS *,_PROTOCOLCOUNTERS *)
0x18001c1b5  mov     ecx, [rbp+6C0h+var_3D0]
0x18001c1bb  sub     ecx, 1
0x18001c1be  jz      loc_18001C2D4
0x18001c1c4  sub     ecx, 1
0x18001c1c7  jz      loc_18001C2C8
0x18001c1cd  cmp     ecx, 1
0x18001c1d0  jnz     loc_18001C2D4
0x18001c1d6  mov     eax, [rbp+6C0h+var_3CC]
0x18001c1dc  mov     [rbx+39Ch], eax
0x18001c1e2  mov     eax, [rbp+6C0h+var_3C8]
0x18001c1e8  mov     [rbx+3A0h], eax
0x18001c1ee  mov     eax, [rbp+6C0h+var_3C4]
0x18001c1f4  mov     [rbx+3A4h], eax
0x18001c1fa  mov     eax, [rbp+6C0h+var_3C0]
0x18001c200  mov     [rbx+3A8h], eax
0x18001c206  mov     eax, [rbp+6C0h+var_3BC]
0x18001c20c  mov     [rbx+3ACh], eax
0x18001c212  mov     eax, [rbp+6C0h+var_3B8]
0x18001c218  mov     [rbx+3B0h], eax
0x18001c21e  mov     eax, [rbp+6C0h+var_3B4]
0x18001c224  mov     [rbx+3B4h], eax
0x18001c22a  mov     eax, [rbp+6C0h+var_3B0]
0x18001c230  mov     [rbx+3B8h], eax
0x18001c236  mov     eax, [rbp+6C0h+var_3AC]
0x18001c23c  mov     [rbx+3BCh], eax
0x18001c242  mov     eax, [rbp+6C0h+var_3A8]
0x18001c248  mov     [rbx+3C0h], eax
0x18001c24e  mov     eax, [rbp+6C0h+var_3A4]
0x18001c254  mov     [rbx+3C4h], eax
0x18001c25a  mov     eax, [rbp+6C0h+var_3A0]
0x18001c260  mov     [rbx+3C8h], eax
0x18001c266  mov     eax, [rbp+6C0h+var_39C]
0x18001c26c  mov     [rbx+3CCh], eax
0x18001c272  mov     eax, [rbp+6C0h+var_398]
0x18001c278  mov     [rbx+3D0h], eax
0x18001c27e  mov     eax, [rbp+6C0h+var_394]
0x18001c284  mov     [rbx+3D4h], eax
0x18001c28a  mov     eax, [rbp+6C0h+var_390]
0x18001c290  mov     [rbx+3D8h], eax
0x18001c296  mov     eax, [rbp+6C0h+var_38C]
0x18001c29c  mov     [rbx+3DCh], eax
0x18001c2a2  mov     eax, [rbp+6C0h+var_388]
0x18001c2a8  mov     [rbx+3E0h], eax
0x18001c2ae  mov     eax, [rbp+6C0h+var_384]
0x18001c2b4  mov     [rbx+3E4h], eax
0x18001c2ba  mov     eax, [rbp+6C0h+var_380]
0x18001c2c0  mov     [rbx+3E8h], eax
0x18001c2c6  jmp     short loc_18001C2D4
0x18001c2c8  mov     eax, [rbp+6C0h+var_3CC]
0x18001c2ce  mov     [rbx+39Ch], eax
0x18001c2d4  mov     eax, [rbp+6C0h+var_378]
0x18001c2da  mov     [rbx+3ECh], eax
0x18001c2e0  mov     eax, [rbp+6C0h+var_374]
0x18001c2e6  mov     [rbx+3F0h], eax
0x18001c2ec  mov     rax, [rbp+6C0h+var_370]
0x18001c2f3  mov     [rbx+3F8h], rax
0x18001c2fa  mov     rax, [rbp+6C0h+var_368]
0x18001c301  mov     [rbx+400h], rax
0x18001c308  mov     rax, [rbp+6C0h+var_360]
0x18001c30f  mov     [rbx+408h], rax
0x18001c316  mov     rax, [rbp+6C0h+var_358]
0x18001c31d  mov     [rbx+410h], rax
0x18001c324  mov     rax, [rbp+6C0h+var_350]
0x18001c32b  mov     [rbx+418h], rax
0x18001c332  mov     rax, [rbp+6C0h+var_348]
0x18001c339  mov     [rbx+420h], rax
0x18001c340  mov     rax, [rbp+6C0h+var_340]
0x18001c347  mov     [rbx+428h], rax
0x18001c34e  mov     rax, [rbp+6C0h+var_338]
0x18001c355  mov     [rbx+430h], rax
0x18001c35c  mov     rax, [rbp+6C0h+var_330]
0x18001c363  mov     [rbx+438h], rax
0x18001c36a  mov     rax, [rbp+6C0h+var_328]
0x18001c371  mov     [rbx+440h], rax
0x18001c378  mov     rax, [rbp+6C0h+var_320]
0x18001c37f  mov     [rbx+448h], rax
0x18001c386  mov     rax, [rbp+6C0h+var_318]
0x18001c38d  mov     [rbx+450h], rax
0x18001c394  mov     rax, [rbp+6C0h+var_310]
0x18001c39b  mov     [rbx+458h], rax
0x18001c3a2  mov     rax, [rbp+6C0h+var_308]
0x18001c3a9  mov     [rbx+460h], rax
0x18001c3b0  mov     rax, [rbp+6C0h+var_300]
0x18001c3b7  mov     [rbx+468h], rax
0x18001c3be  mov     rax, [rbp+6C0h+var_2F8]
0x18001c3c5  mov     [rbx+470h], rax
0x18001c3cc  mov     rax, [rbp+6C0h+var_2F0]
0x18001c3d3  mov     [rbx+478h], rax
0x18001c3da  mov     rax, [rbp+6C0h+var_2E8]
0x18001c3e1  mov     [rbx+480h], rax
0x18001c3e8  mov     rax, [rbp+6C0h+var_2E0]
0x18001c3ef  mov     [rbx+488h], rax
0x18001c3f6  mov     rax, [rbp+6C0h+var_2D8]
0x18001c3fd  mov     [rbx+490h], rax
0x18001c404  mov     rax, [rbp+6C0h+var_2D0]
0x18001c40b  mov     [rbx+498h], rax
0x18001c412  mov     rax, [rbp+6C0h+var_2C8]
0x18001c419  mov     [rbx+4A0h], rax
0x18001c420  mov     rax, [rbp+6C0h+var_2C0]
0x18001c427  mov     [rbx+4A8h], rax
0x18001c42e  mov     rax, [rbp+6C0h+var_2B8]
0x18001c435  mov     [rbx+4B0h], rax
0x18001c43c  mov     rax, [rbp+6C0h+var_2B0]
0x18001c443  mov     [rbx+4B8h], rax
0x18001c44a  mov     rax, [rbp+6C0h+var_2A8]
0x18001c451  mov     [rbx+4C0h], rax
0x18001c458  mov     rax, [rbp+6C0h+var_2A0]
0x18001c45f  mov     [rbx+4C8h], rax
0x18001c466  mov     rax, [rbp+6C0h+var_298]
0x18001c46d  mov     [rbx+4D0h], rax
0x18001c474  mov     rax, [rbp+6C0h+var_290]
0x18001c47b  mov     [rbx+4D8h], rax
0x18001c482  mov     rax, [rbp+6C0h+var_288]
0x18001c489  mov     [rbx+4E0h], rax
0x18001c490  mov     rax, [rbp+6C0h+var_280]
0x18001c497  mov     [rbx+4E8h], rax
0x18001c49e  mov     rax, [rbp+6C0h+var_278]
0x18001c4a5  mov     [rbx+4F0h], rax
0x18001c4ac  mov     rax, [rbp+6C0h+var_270]
0x18001c4b3  mov     [rbx+4F8h], rax
0x18001c4ba  mov     rax, [rbp+6C0h+var_268]
0x18001c4c1  mov     [rbx+500h], rax
0x18001c4c8  mov     rax, [rbp+6C0h+var_260]
0x18001c4cf  mov     [rbx+508h], rax
0x18001c4d6  mov     rax, [rbp+6C0h+var_258]
0x18001c4dd  mov     [rbx+510h], rax
0x18001c4e4  mov     rax, [rbp+6C0h+var_250]
0x18001c4eb  mov     [rbx+518h], rax
0x18001c4f2  mov     rax, [rbp+6C0h+var_248]
0x18001c4f9  mov     [rbx+520h], rax
0x18001c500  mov     rax, [rbp+6C0h+var_240]
0x18001c507  mov     [rbx+528h], rax
0x18001c50e  mov     rax, [rbp+6C0h+var_238]
0x18001c515  mov     [rbx+530h], rax
0x18001c51c  mov     rax, [rbp+6C0h+var_230]
0x18001c523  mov     [rbx+538h], rax
0x18001c52a  mov     rax, [rbp+6C0h+var_228]
0x18001c531  mov     [rbx+540h], rax
0x18001c538  mov     rax, [rbp+6C0h+var_220]
0x18001c53f  mov     [rbx+548h], rax
0x18001c546  mov     rax, [rbp+6C0h+var_218]
0x18001c54d  mov     [rbx+550h], rax
0x18001c554  mov     rax, [rbp+6C0h+var_210]
0x18001c55b  mov     [rbx+558h], rax
0x18001c562  mov     rax, [rbp+6C0h+var_208]
0x18001c569  mov     [rbx+560h], rax
0x18001c570  mov     rax, [rbp+6C0h+var_200]
0x18001c577  mov     [rbx+568h], rax
0x18001c57e  mov     rax, [rbp+6C0h+var_1F8]
0x18001c585  mov     [rbx+570h], rax
0x18001c58c  mov     rax, [rbp+6C0h+var_1F0]
0x18001c593  mov     [rbx+578h], rax
0x18001c59a  mov     rax, [rbp+6C0h+var_1E8]
0x18001c5a1  mov     [rbx+580h], rax
0x18001c5a8  mov     rax, [rbp+6C0h+var_1E0]
0x18001c5af  mov     [rbx+588h], rax
0x18001c5b6  mov     rax, [rbp+6C0h+var_1D8]
0x18001c5bd  mov     [rbx+590h], rax
0x18001c5c4  mov     rax, [rbp+6C0h+var_1D0]
0x18001c5cb  mov     [rbx+598h], rax
0x18001c5d2  mov     rax, [rbp+6C0h+var_1C8]
0x18001c5d9  mov     [rbx+5A0h], rax
0x18001c5e0  mov     rax, [rbp+6C0h+var_1C0]
0x18001c5e7  mov     [rbx+5A8h], rax
0x18001c5ee  mov     rax, [rbp+6C0h+var_1B8]
0x18001c5f5  mov     [rbx+5B0h], rax
0x18001c5fc  mov     rax, [rbp+6C0h+var_1B0]
0x18001c603  mov     [rbx+5B8h], rax
0x18001c60a  mov     rax, [rbp+6C0h+var_1A8]
0x18001c611  mov     [rbx+5C0h], rax
0x18001c618  mov     rax, [rbp+6C0h+var_1A0]
0x18001c61f  mov     [rbx+5C8h], rax
0x18001c626  mov     rax, [rbp+6C0h+var_198]
0x18001c62d  mov     [rbx+5D0h], rax
0x18001c634  mov     rax, [rbp+6C0h+var_190]
0x18001c63b  mov     [rbx+5D8h], rax
0x18001c642  mov     rax, [rbp+6C0h+var_188]
0x18001c649  mov     [rbx+5E0h], rax
0x18001c650  mov     rax, [rbp+6C0h+var_180]
0x18001c657  mov     [rbx+5E8h], rax
0x18001c65e  mov     rax, [rbp+6C0h+var_178]
0x18001c665  mov     [rbx+5F0h], rax
0x18001c66c  mov     rax, [rbp+6C0h+var_170]
0x18001c673  mov     [rbx+5F8h], rax
0x18001c67a  mov     rax, [rbp+6C0h+var_168]
0x18001c681  mov     [rbx+600h], rax
0x18001c688  mov     rax, [rbp+6C0h+var_160]
0x18001c68f  mov     [rbx+608h], rax
0x18001c696  mov     rax, [rbp+6C0h+var_158]
0x18001c69d  mov     [rbx+610h], rax
0x18001c6a4  mov     rax, [rbp+6C0h+var_150]
0x18001c6ab  mov     [rbx+618h], rax
0x18001c6b2  mov     rax, [rbp+6C0h+var_148]
0x18001c6b9  mov     [rbx+620h], rax
0x18001c6c0  mov     rax, [rbp+6C0h+var_140]
0x18001c6c7  mov     [rbx+628h], rax
0x18001c6ce  mov     rax, [rbp+6C0h+var_138]
0x18001c6d5  mov     [rbx+630h], rax
0x18001c6dc  mov     rax, [rbp+6C0h+var_130]
0x18001c6e3  mov     [rbx+638h], rax
0x18001c6ea  mov     rax, [rbp+6C0h+var_128]
0x18001c6f1  mov     [rbx+640h], rax
0x18001c6f8  mov     rax, [rbp+6C0h+var_120]
0x18001c6ff  mov     [rbx+648h], rax
0x18001c706  mov     rax, [rbp+6C0h+var_118]
0x18001c70d  mov     [rbx+650h], rax
0x18001c714  mov     rax, [rbp+6C0h+var_110]
0x18001c71b  mov     [rbx+658h], rax
0x18001c722  mov     rax, [rbp+6C0h+var_108]
0x18001c729  mov     [rbx+660h], rax
0x18001c730  mov     rax, [rbp+6C0h+var_100]
0x18001c737  mov     [rbx+668h], rax
0x18001c73e  mov     rax, [rbp+6C0h+var_F8]
0x18001c745  mov     [rbx+670h], rax
0x18001c74c  mov     rax, [rbp+6C0h+var_F0]
0x18001c753  mov     [rbx+678h], rax
0x18001c75a  mov     rax, [rbp+6C0h+var_E8]
0x18001c761  mov     [rbx+680h], rax
0x18001c768  mov     rax, [rbp+6C0h+var_E0]
0x18001c76f  mov     [rbx+688h], rax
0x18001c776  mov     rax, [rbp+6C0h+var_D8]
0x18001c77d  mov     [rbx+690h], rax
0x18001c784  mov     rax, [rbp+6C0h+var_D0]
0x18001c78b  mov     [rbx+698h], rax
  ... truncated ...
```
