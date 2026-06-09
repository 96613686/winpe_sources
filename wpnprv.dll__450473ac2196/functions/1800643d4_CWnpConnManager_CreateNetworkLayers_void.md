# CWnpConnManager::CreateNetworkLayers(void)

- ea: `0x1800643d4`
- end: `0x180064852`
- name: `?CreateNetworkLayers@CWnpConnManager@@AEAAJXZ`
- size: `1150`
- prototype: `__int64 __fastcall(CWnpConnManager *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800651b0`

## callees

- `0x18000795c`
- `0x18000fddc`
- `0x18000fe2c`
- `0x18000fe54`
- `0x18004ffb8`
- `0x1800643d4`
- `0x1800852d4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800644f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800644f2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180064453`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180064453`

## pseudocode

```c
__int64 __fastcall CWnpConnManager::CreateNetworkLayers(CWnpConnManager *this)
{
  int v2; // esi
  int v3; // eax
  int v4; // edi
  CWnpConnector *v5; // rax
  struct LogCommandManager **v6; // rsi
  unsigned __int64 v7; // rbp
  unsigned int v8; // edi
  PVOID *v9; // rcx
  __int64 v10; // rdx
  CWnpConnector *v11; // rax
  CWnpConnector *v12; // rax
  CWnpConnector *v13; // rax
  int phkResult; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  unsigned int v17; // [rsp+60h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF
  CWnpConnector *v19; // [rsp+70h] [rbp+18h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, &WPP_c2695b214f4937d505e61a78da1ced9b_Traceguids);
  }
  hKey = 0;
  v17 = 0;
  v2 = 4;
  v3 = RegOpenKeyExA(
         HKEY_LOCAL_MACHINE,
         "Software\\Microsoft\\Windows\\CurrentVersion\\PushNotifications",
         0,
         1u,
         &hKey);
  if ( v3 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      if ( v3 > 0 )
        v3 = (unsigned __int16)v3 | 0x80070000;
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        105,
        &WPP_c2695b214f4937d505e61a78da1ced9b_Traceguids,
        (unsigned int)v3);
    }
  }
  else
  {
    if ( (int)WpnRegLoadDWord(hKey, L"DisableTLS", &v17) >= 0 && v17 )
    {
      v2 = 0;
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 106, &WPP_c2695b214f4937d505e61a78da1ced9b_Traceguids);
    }
    RegCloseKey(hKey);
  }
  v4 = v2 | 8;
  if ( !*((_BYTE *)this + 212) )
    v4 = v2;
  v5 = (CWnpConnector *)operator new(0x268u, (const struct std::nothrow_t *)&std::nothrow);
  v19 = v5;
  v6 = (struct LogCommandManager **)((char *)this + 296);
  v7 = (unsigned __int64)this + 8;
  if ( v5 )
    v5 = CWnpConnector::CWnpConnector(
           v5,
           0,
           v4 | 0x11u,
           (struct IWnpConnectorEvents *)(v7 & -(__int64)(this != 0)),
           *v6);
  if ( v5 )
  {
    *((_QWORD *)this + 10) = v5;
    v11 = (CWnpConnector *)operator new(0x268u, (const struct std::nothrow_t *)&std::nothrow);
    v19 = v11;
    if ( v11 )
      v11 = CWnpConnector::CWnpConnector(
              v11,
              1,
              v4 | 1u,
              (struct IWnpConnectorEvents *)(v7 & -(__int64)(this != 0)),
              *v6);
    if ( v11 )
    {
      *((_QWORD *)this + 14) = v11;
      v12 = (CWnpConnector *)operator new(0x268u, (const struct std::nothrow_t *)&std::nothrow);
      v19 = v12;
      if ( v12 )
        v12 = CWnpConnector::CWnpConnector(
                v12,
                2,
                v4 | 2u,
                (struct IWnpConnectorEvents *)(v7 & -(__int64)(this != 0)),
                *v6);
      if ( v12 )
      {
        *((_QWORD *)this + 18) = v12;
        v13 = (CWnpConnector *)operator new(0x268u, (const struct std::nothrow_t *)&std::nothrow);
        v19 = v13;
        if ( v13 )
          v13 = CWnpConnector::CWnpConnector(
                  v13,
                  3,
                  v4 | 1u,
                  (struct IWnpConnectorEvents *)(v7 & -(__int64)(this != 0)),
                  *v6);
        if ( v13 )
        {
          v8 = 0;
          *((_QWORD *)this + 22) = v13;
          goto LABEL_64;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            113,
            &WPP_c2695b214f4937d505e61a78da1ced9b_Traceguids,
            2147942414LL);
        }
        v8 = -2147024882;
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x354,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpconnmanager.cpp",
          (const char *)0x8007000ELL,
          phkResult);
        v9 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
          {
            v10 = 114;
            goto LABEL_32;
          }
          goto LABEL_65;
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            111,
            &WPP_c2695b214f4937d505e61a78da1ced9b_Traceguids,
            2147942414LL);
        }
        v8 = -2147024882;
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x34A,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpconnmanager.cpp",
          (const char *)0x8007000ELL,
          phkResult);
        v9 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
          {
            v10 = 112;
            goto LABEL_32;
          }
          goto LABEL_65;
        }
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          109,
          &WPP_c2695b214f4937d505e61a78da1ced9b_Traceguids,
          2147942414LL);
      }
      v8 = -2147024882;
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x340,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpconnmanager.cpp",
        (const char *)0x8007000ELL,
        phkResult);
      v9 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
        {
          v10 = 110;
          goto LABEL_32;
        }
LABEL_65:
        if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 4) != 0 && *((_BYTE *)v9 + 25) >= 6u )
          WPP_SF_d(v9[2], 115, &WPP_c2695b214f4937d505e61a78da1ced9b_Traceguids, v8);
      }
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, &WPP_c2695b214f4937d505e61a78da1ced9b_Traceguids, 2147942414LL);
    }
    v8 = -2147024882;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x336,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpconnmanager.cpp",
      (const char *)0x8007000ELL,
      phkResult);
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v10 = 108;
LABEL_32:
        WPP_SF_d(v9[2], v10, &WPP_c2695b214f4937d505e61a78da1ced9b_Traceguids, 2147942414LL);
LABEL_64:
        v9 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_65;
      }
      goto LABEL_65;
    }
  }
  return v8;
}

```

## disassembly

```asm
0x1800643d4  mov     [rsp+arg_18], rbx
0x1800643d9  push    rbp
0x1800643da  push    rsi
0x1800643db  push    rdi
0x1800643dc  push    r12
0x1800643de  push    r15
0x1800643e0  sub     rsp, 30h
0x1800643e4  mov     rbx, rcx
0x1800643e7  lea     r15, WPP_GLOBAL_Control
0x1800643ee  lea     r12, WPP_c2695b214f4937d505e61a78da1ced9b_Traceguids
0x1800643f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800643fc  cmp     rcx, r15
0x1800643ff  jz      short loc_18006441E
0x180064401  test    byte ptr [rcx+1Ch], 4
0x180064405  jz      short loc_18006441E
0x180064407  cmp     byte ptr [rcx+19h], 6
0x18006440b  jb      short loc_18006441E
0x18006440d  mov     edx, 68h ; 'h'
0x180064412  mov     r8, r12
0x180064415  mov     rcx, [rcx+10h]
0x180064419  call    WPP_SF_
0x18006441e  mov     [rsp+58h+hKey], 0
0x180064427  mov     [rsp+58h+arg_0], 0
0x18006442f  mov     esi, 4
0x180064434  lea     rax, [rsp+58h+hKey]
0x180064439  mov     qword ptr [rsp+58h+phkResult], rax; phkResult
0x18006443e  lea     r9d, [rsi-3]; samDesired
0x180064442  xor     r8d, r8d; ulOptions
0x180064445  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18006444c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180064453  call    cs:__imp_RegOpenKeyExA
0x180064459  test    eax, eax
0x18006445b  jz      short loc_18006449F
0x18006445d  mov     rcx, cs:WPP_GLOBAL_Control
0x180064464  cmp     rcx, r15
0x180064467  jz      loc_1800644F8
0x18006446d  test    [rcx+1Ch], sil
0x180064471  jz      loc_1800644F8
0x180064477  cmp     byte ptr [rcx+19h], 2
0x18006447b  jb      short loc_1800644F8
0x18006447d  test    eax, eax
0x18006447f  jle     short loc_180064489
0x180064481  movzx   eax, ax
0x180064484  or      eax, 80070000h
0x180064489  mov     edx, 69h ; 'i'
0x18006448e  mov     r9d, eax
0x180064491  mov     r8, r12
0x180064494  mov     rcx, [rcx+10h]
0x180064498  call    WPP_SF_d
0x18006449d  jmp     short loc_1800644F8
0x18006449f  lea     r8, [rsp+58h+arg_0]; unsigned int *
0x1800644a4  lea     rdx, aDisabletls; "DisableTLS"
0x1800644ab  mov     rcx, [rsp+58h+hKey]; hKey
0x1800644b0  call    ?WpnRegLoadDWord@@YAJPEAUHKEY__@@PEBGPEAK@Z; WpnRegLoadDWord(HKEY__ *,ushort const *,ulong *)
0x1800644b5  test    eax, eax
0x1800644b7  js      short loc_1800644C4
0x1800644b9  cmp     [rsp+58h+arg_0], 0
0x1800644be  jz      short loc_1800644C4
0x1800644c0  xor     esi, esi
0x1800644c2  jmp     short loc_1800644ED
0x1800644c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800644cb  cmp     rcx, r15
0x1800644ce  jz      short loc_1800644ED
0x1800644d0  test    [rcx+1Ch], sil
0x1800644d4  jz      short loc_1800644ED
0x1800644d6  cmp     byte ptr [rcx+19h], 3
0x1800644da  jb      short loc_1800644ED
0x1800644dc  mov     edx, 6Ah ; 'j'
0x1800644e1  mov     r8, r12
0x1800644e4  mov     rcx, [rcx+10h]
0x1800644e8  call    WPP_SF_
0x1800644ed  mov     rcx, [rsp+58h+hKey]; hKey
0x1800644f2  call    cs:__imp_RegCloseKey
0x1800644f8  mov     edi, esi
0x1800644fa  or      edi, 8
0x1800644fd  cmp     byte ptr [rbx+0D4h], 0
0x180064504  cmovz   edi, esi
0x180064507  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18006450e  mov     ecx, 268h; unsigned __int64
0x180064513  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180064518  mov     r10, rax
0x18006451b  mov     [rsp+58h+arg_10], rax
0x180064520  lea     rsi, [rbx+128h]
0x180064527  lea     rbp, [rbx+8]
0x18006452b  test    rax, rax
0x18006452e  jz      short loc_180064556
0x180064530  mov     rcx, rbx
0x180064533  neg     rcx
0x180064536  sbb     r9, r9
0x180064539  and     r9, rbp; struct IWnpConnectorEvents *
0x18006453c  mov     r8d, edi
0x18006453f  or      r8d, 11h; unsigned int
0x180064543  mov     rax, [rsi]
0x180064546  mov     qword ptr [rsp+58h+phkResult], rax; int
0x18006454b  xor     edx, edx; unsigned int
0x18006454d  mov     rcx, r10; this
0x180064550  call    ??0CWnpConnector@@QEAA@KKPEAUIWnpConnectorEvents@@PEAVLogCommandManager@@@Z; CWnpConnector::CWnpConnector(ulong,ulong,IWnpConnectorEvents *,LogCommandManager *)
0x180064555  nop
0x180064556  test    rax, rax
0x180064559  jnz     loc_1800645DF
0x18006455f  mov     ebx, 8007000Eh
0x180064564  mov     rcx, cs:WPP_GLOBAL_Control
0x18006456b  cmp     rcx, r15
0x18006456e  jz      short loc_18006458E
0x180064570  test    byte ptr [rcx+1Ch], 4
0x180064574  jz      short loc_18006458E
0x180064576  cmp     byte ptr [rcx+19h], 2
0x18006457a  jb      short loc_18006458E
0x18006457c  lea     edx, [rax+6Bh]
0x18006457f  mov     r9d, ebx
0x180064582  mov     r8, r12
0x180064585  mov     rcx, [rcx+10h]
0x180064589  call    WPP_SF_d
0x18006458e  mov     edi, ebx
0x180064590  mov     rcx, [rsp+58h]; this
0x180064595  mov     r9d, ebx; char *
0x180064598  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006459f  mov     edx, 336h; void *
0x1800645a4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800645a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800645b0  cmp     rcx, r15
0x1800645b3  jz      loc_18006483F
0x1800645b9  test    byte ptr [rcx+1Ch], 80h
0x1800645bd  jz      loc_18006481A
0x1800645c3  mov     edx, 6Ch ; 'l'
0x1800645c8  mov     r9d, 8007000Eh
0x1800645ce  mov     r8, r12
0x1800645d1  mov     rcx, [rcx+10h]
0x1800645d5  call    WPP_SF_d
0x1800645da  jmp     loc_180064813
0x1800645df  mov     [rbx+50h], rax
0x1800645e3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800645ea  mov     ecx, 268h; unsigned __int64
0x1800645ef  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800645f4  mov     [rsp+58h+arg_10], rax
0x1800645f9  test    rax, rax
0x1800645fc  jz      short loc_180064627
0x1800645fe  mov     rcx, rbx
0x180064601  neg     rcx
0x180064604  sbb     r9, r9
0x180064607  and     r9, rbp; struct IWnpConnectorEvents *
0x18006460a  mov     r8d, edi
0x18006460d  or      r8d, 1; unsigned int
0x180064611  mov     rcx, [rsi]
0x180064614  mov     qword ptr [rsp+58h+phkResult], rcx; int
0x180064619  mov     edx, 1; unsigned int
0x18006461e  mov     rcx, rax; this
0x180064621  call    ??0CWnpConnector@@QEAA@KKPEAUIWnpConnectorEvents@@PEAVLogCommandManager@@@Z; CWnpConnector::CWnpConnector(ulong,ulong,IWnpConnectorEvents *,LogCommandManager *)
0x180064626  nop
0x180064627  test    rax, rax
0x18006462a  jnz     short loc_18006469A
0x18006462c  mov     ebx, 8007000Eh
0x180064631  mov     rcx, cs:WPP_GLOBAL_Control
0x180064638  cmp     rcx, r15
0x18006463b  jz      short loc_18006465B
0x18006463d  test    byte ptr [rcx+1Ch], 4
0x180064641  jz      short loc_18006465B
0x180064643  cmp     byte ptr [rcx+19h], 2
0x180064647  jb      short loc_18006465B
0x180064649  lea     edx, [rax+6Dh]
0x18006464c  mov     r9d, ebx
0x18006464f  mov     r8, r12
0x180064652  mov     rcx, [rcx+10h]
0x180064656  call    WPP_SF_d
0x18006465b  mov     edi, ebx
0x18006465d  mov     rcx, [rsp+58h]; this
0x180064662  mov     r9d, ebx; char *
0x180064665  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006466c  mov     edx, 340h; void *
0x180064671  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180064676  mov     rcx, cs:WPP_GLOBAL_Control
0x18006467d  cmp     rcx, r15
0x180064680  jz      loc_18006483F
0x180064686  test    byte ptr [rcx+1Ch], 80h
0x18006468a  jz      loc_18006481A
0x180064690  mov     edx, 6Eh ; 'n'
0x180064695  jmp     loc_1800645C8
0x18006469a  mov     [rbx+70h], rax
0x18006469e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800646a5  mov     ecx, 268h; unsigned __int64
0x1800646aa  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800646af  mov     [rsp+58h+arg_10], rax
0x1800646b4  test    rax, rax
0x1800646b7  jz      short loc_1800646E2
0x1800646b9  mov     rcx, rbx
0x1800646bc  neg     rcx
0x1800646bf  sbb     r9, r9
0x1800646c2  and     r9, rbp; struct IWnpConnectorEvents *
0x1800646c5  mov     r8d, edi
0x1800646c8  or      r8d, 2; unsigned int
0x1800646cc  mov     rcx, [rsi]
0x1800646cf  mov     qword ptr [rsp+58h+phkResult], rcx; int
0x1800646d4  mov     edx, 2; unsigned int
0x1800646d9  mov     rcx, rax; this
0x1800646dc  call    ??0CWnpConnector@@QEAA@KKPEAUIWnpConnectorEvents@@PEAVLogCommandManager@@@Z; CWnpConnector::CWnpConnector(ulong,ulong,IWnpConnectorEvents *,LogCommandManager *)
0x1800646e1  nop
0x1800646e2  test    rax, rax
0x1800646e5  jnz     short loc_180064755
0x1800646e7  mov     ebx, 8007000Eh
0x1800646ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800646f3  cmp     rcx, r15
0x1800646f6  jz      short loc_180064716
0x1800646f8  test    byte ptr [rcx+1Ch], 4
0x1800646fc  jz      short loc_180064716
0x1800646fe  cmp     byte ptr [rcx+19h], 2
0x180064702  jb      short loc_180064716
0x180064704  lea     edx, [rax+6Fh]
0x180064707  mov     r9d, ebx
0x18006470a  mov     r8, r12
0x18006470d  mov     rcx, [rcx+10h]
0x180064711  call    WPP_SF_d
0x180064716  mov     edi, ebx
0x180064718  mov     rcx, [rsp+58h]; this
0x18006471d  mov     r9d, ebx; char *
0x180064720  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180064727  mov     edx, 34Ah; void *
0x18006472c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180064731  mov     rcx, cs:WPP_GLOBAL_Control
0x180064738  cmp     rcx, r15
0x18006473b  jz      loc_18006483F
0x180064741  test    byte ptr [rcx+1Ch], 80h
0x180064745  jz      loc_18006481A
0x18006474b  mov     edx, 70h ; 'p'
0x180064750  jmp     loc_1800645C8
0x180064755  mov     [rbx+90h], rax
0x18006475c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180064763  mov     ecx, 268h; unsigned __int64
0x180064768  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18006476d  mov     [rsp+58h+arg_10], rax
0x180064772  test    rax, rax
0x180064775  jz      short loc_18006479F
0x180064777  mov     rcx, rbx
0x18006477a  neg     rcx
0x18006477d  sbb     r9, r9
0x180064780  and     r9, rbp; struct IWnpConnectorEvents *
0x180064783  or      edi, 1
0x180064786  mov     rcx, [rsi]
0x180064789  mov     qword ptr [rsp+58h+phkResult], rcx; int
0x18006478e  mov     r8d, edi; unsigned int
0x180064791  mov     edx, 3; unsigned int
0x180064796  mov     rcx, rax; this
0x180064799  call    ??0CWnpConnector@@QEAA@KKPEAUIWnpConnectorEvents@@PEAVLogCommandManager@@@Z; CWnpConnector::CWnpConnector(ulong,ulong,IWnpConnectorEvents *,LogCommandManager *)
0x18006479e  nop
0x18006479f  test    rax, rax
0x1800647a2  jnz     short loc_18006480A
0x1800647a4  mov     ebx, 8007000Eh
0x1800647a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800647b0  cmp     rcx, r15
0x1800647b3  jz      short loc_1800647D3
0x1800647b5  test    byte ptr [rcx+1Ch], 4
0x1800647b9  jz      short loc_1800647D3
0x1800647bb  cmp     byte ptr [rcx+19h], 2
0x1800647bf  jb      short loc_1800647D3
0x1800647c1  lea     edx, [rax+71h]
0x1800647c4  mov     r9d, ebx
0x1800647c7  mov     r8, r12
0x1800647ca  mov     rcx, [rcx+10h]
0x1800647ce  call    WPP_SF_d
0x1800647d3  mov     edi, ebx
0x1800647d5  mov     rcx, [rsp+58h]; this
0x1800647da  mov     r9d, ebx; char *
0x1800647dd  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800647e4  mov     edx, 354h; void *
0x1800647e9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800647ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800647f5  cmp     rcx, r15
0x1800647f8  jz      short loc_18006483F
0x1800647fa  test    byte ptr [rcx+1Ch], 80h
0x1800647fe  jz      short loc_18006481A
0x180064800  mov     edx, 72h ; 'r'
0x180064805  jmp     loc_1800645C8
0x18006480a  xor     edi, edi
0x18006480c  mov     [rbx+0B0h], rax
0x180064813  mov     rcx, cs:WPP_GLOBAL_Control
0x18006481a  cmp     rcx, r15
0x18006481d  jz      short loc_18006483F
0x18006481f  test    byte ptr [rcx+1Ch], 4
0x180064823  jz      short loc_18006483F
0x180064825  cmp     byte ptr [rcx+19h], 6
0x180064829  jb      short loc_18006483F
0x18006482b  mov     edx, 73h ; 's'
0x180064830  mov     r9d, edi
0x180064833  mov     r8, r12
0x180064836  mov     rcx, [rcx+10h]
0x18006483a  call    WPP_SF_d
0x18006483f  mov     eax, edi
0x180064841  mov     rbx, [rsp+58h+arg_18]
0x180064846  add     rsp, 30h
0x18006484a  pop     r15
0x18006484c  pop     r12
0x18006484e  pop     rdi
0x18006484f  pop     rsi
0x180064850  pop     rbp
0x180064851  retn
```
