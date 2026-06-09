# UpdateNtpServer(void)

- ea: `0x18002522c`
- end: `0x18002576c`
- name: `?UpdateNtpServer@@YAJXZ`
- size: `1344`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180023510`

## callees

- `0x180015020`
- `0x180018138`
- `0x18001d9a0`
- `0x18002522c`
- `0x180025c14`
- `0x18002a980`
- `0x18002b7b0`
- `0x180046a88`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180025256`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18002570b`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180025256`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18002570b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002573b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002573b`

## string_xrefs

- `0x1800252f2`: `  AllowServerNonstandardModeCominations changed.\n`
- `0x180025462`: `  ChainTableMaxEntries using registry/default value.\n`
- `0x1800254d2`: `  ChainTableMaxHostEntries using registry/default value.\n`
- `0x180025542`: `  ChainTableEntryTimeout using registry/default value.\n`
- `0x1800255c0`: `  ChainLoggingRate using registry/default value.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 UpdateNtpServer(void)
{
  char v0; // r15
  int NtpServerConfig; // edi
  _DWORD *v2; // rsi
  _NtpProvState *v3; // rdx
  int v4; // eax
  int v5; // eax
  unsigned int v6; // eax
  unsigned int v7; // ecx
  unsigned int v8; // ecx
  _NtpProvState *v9; // rcx
  unsigned int v10; // eax
  void *v11; // rcx
  void *v12; // r9
  int v13; // eax
  void *v14; // rdx
  void *v15; // r9
  int v16; // eax
  unsigned int v18; // [rsp+30h] [rbp-68h]
  HLOCAL hMem; // [rsp+A0h] [rbp+8h] BYREF
  __int64 v20; // [rsp+A8h] [rbp+10h]

  hMem = 0;
  v0 = 0;
  v20 = _set_se_translator(SeTransFunc);
  NtpServerConfig = ReadNtpServerConfig((struct NtpServerConfig **)&hMem);
  if ( NtpServerConfig < 0 )
  {
    v2 = hMem;
    goto LABEL_77;
  }
  NtpServerConfig = TrapThreads(1);
  if ( NtpServerConfig < 0 )
  {
    v2 = hMem;
    goto LABEL_77;
  }
  v2 = hMem;
  v3 = g_pnpstate;
  if ( *((_BYTE *)g_pnpstate + 259) != (*(_DWORD *)hMem != 0) )
  {
    *((_BYTE *)g_pnpstate + 259) = *(_DWORD *)hMem != 0;
    if ( (unsigned __int8)FileLogAllowEntry(58) )
      FileLogAdd(L"  AllowServerNonstandardModeCominations changed.\n");
    v3 = g_pnpstate;
  }
  *((_DWORD *)v3 + 65) = v2[2];
  v4 = v2[1];
  if ( *((_DWORD *)v3 + 50) != v4 )
  {
    *((_DWORD *)v3 + 50) = v4;
    if ( (unsigned __int8)FileLogAllowEntry(58) )
      FileLogAdd(L"  EventLogFlags changed.\n");
    v3 = g_pnpstate;
  }
  *((_DWORD *)v3 + 62) = v2[3];
  if ( *((_BYTE *)v3 + 264) != (v2[14] != 0) )
  {
    *((_BYTE *)v3 + 264) = v2[14] != 0;
    if ( (unsigned __int8)FileLogAllowEntry(58) )
      FileLogAdd(L"  RequireSecureTimeSyncRequests changed.\n");
    v3 = g_pnpstate;
  }
  *((_DWORD *)v3 + 67) = v2[15];
  v5 = v2[16];
  if ( *((_DWORD *)v3 + 68) != v5 )
  {
    *((_DWORD *)v3 + 68) = v5;
    if ( (unsigned __int8)FileLogAllowEntry(58) )
      FileLogAdd(L"  UnsecureTimeSyncRequestsLogThrottlePeriod changed.\n");
    v3 = g_pnpstate;
  }
  *((_DWORD *)v3 + 69) = v2[17];
  if ( *((_BYTE *)v3 + 548) != (v2[10] != 0) )
  {
    *((_BYTE *)v3 + 548) = v2[10] != 0;
    if ( (unsigned __int8)FileLogAllowEntry(58) )
      FileLogAdd(L"  ChainTableDisabled changed.\n");
    v3 = g_pnpstate;
  }
  v6 = v2[6];
  if ( v6 <= 0x400 )
  {
    if ( v6 >= 0x80 )
    {
      *((_DWORD *)v3 + 138) = v6;
      if ( (unsigned __int8)FileLogAllowEntry(58) )
        FileLogAdd(L"  ChainTableMaxEntries using registry/default value.\n");
    }
    else
    {
      *((_DWORD *)v3 + 138) = 128;
      if ( (unsigned __int8)FileLogAllowEntry(58) )
        FileLogAdd(L"  ChainTableMaxEntries using minimum value.\n");
    }
  }
  else
  {
    *((_DWORD *)v3 + 138) = 1024;
    if ( (unsigned __int8)FileLogAllowEntry(58) )
      FileLogAdd(L"  ChainTableMaxEntries using maximum value.\n");
  }
  v7 = v2[8];
  if ( v7 <= 0x10 )
  {
    if ( v7 >= 4 )
    {
      *((_DWORD *)g_pnpstate + 139) = v7;
      if ( (unsigned __int8)FileLogAllowEntry(58) )
        FileLogAdd(L"  ChainTableMaxHostEntries using registry/default value.\n");
    }
    else
    {
      *((_DWORD *)g_pnpstate + 139) = 4;
      if ( (unsigned __int8)FileLogAllowEntry(58) )
        FileLogAdd(L"  ChainTableMaxHostEntries using minimum value.\n");
    }
  }
  else
  {
    *((_DWORD *)g_pnpstate + 139) = 16;
    if ( (unsigned __int8)FileLogAllowEntry(58) )
      FileLogAdd(L"  ChainTableMaxHostEntries using maximum value.\n");
  }
  v8 = v2[4];
  if ( v8 <= 0x10 )
  {
    if ( v8 >= 4 )
    {
      *((_DWORD *)g_pnpstate + 140) = v8;
      if ( (unsigned __int8)FileLogAllowEntry(58) )
        FileLogAdd(L"  ChainTableEntryTimeout using registry/default value.\n");
    }
    else
    {
      *((_DWORD *)g_pnpstate + 140) = 4;
      if ( (unsigned __int8)FileLogAllowEntry(58) )
        FileLogAdd(L"  ChainTableEntryTimeout using minimum value.\n");
    }
  }
  else
  {
    *((_DWORD *)g_pnpstate + 140) = 16;
    if ( (unsigned __int8)FileLogAllowEntry(58) )
      FileLogAdd(L"  ChainTableEntryTimeout using maximum value.\n");
  }
  v9 = g_pnpstate;
  if ( v2[12] != *((_DWORD *)g_pnpstate + 130) )
  {
    v0 = 1;
    if ( (unsigned __int8)FileLogAllowEntry(58) )
      FileLogAdd(L"  ChainLoggingRate changed.\n");
    v9 = g_pnpstate;
  }
  v10 = v2[12];
  if ( v10 <= 0x2760 )
  {
    *((_DWORD *)v9 + 130) = v10;
    if ( (unsigned __int8)FileLogAllowEntry(58) )
      FileLogAdd(L"  ChainLoggingRate using registry/default value.\n");
  }
  else
  {
    *((_DWORD *)v9 + 130) = 10080;
    if ( (unsigned __int8)FileLogAllowEntry(58) )
      FileLogAdd(L"  ChainLoggingRate using maximum value.\n");
  }
  if ( !*((_BYTE *)g_pnpstate + 524) )
  {
    v13 = *((_DWORD *)g_pnpstate + 130);
    if ( v13 )
    {
      NtpServerConfig = myStartTimerQueueTimer(
                          *((LPCRITICAL_SECTION *)g_pnpstate + 61),
                          g_pnpstate,
                          (void (*)(void *, unsigned __int8))HandleChainingCountTimeout,
                          v12,
                          0,
                          60000 * v13,
                          v18);
      if ( NtpServerConfig < 0 )
        goto LABEL_74;
      *((_BYTE *)g_pnpstate + 524) = 1;
      if ( (unsigned __int8)FileLogAllowEntry(58) )
        FileLogAdd(L"  ChainTableEventLogging is now enabled.\n");
    }
    goto LABEL_72;
  }
  if ( !*((_DWORD *)g_pnpstate + 130) && *((_QWORD *)g_pnpstate + 61) )
  {
    NtpServerConfig = myStopTimerQueueTimer(v11, *((void **)g_pnpstate + 61), (void *)0xFFFFFFFFFFFFFFFFLL);
    if ( NtpServerConfig < 0 )
      goto LABEL_74;
    *((_BYTE *)g_pnpstate + 524) = 0;
    if ( (unsigned __int8)FileLogAllowEntry(58) )
      FileLogAdd(L"  ChainTableEventLogging is now disabled.\n");
    goto LABEL_72;
  }
  if ( !v0
    || (NtpServerConfig = myStopTimerQueueTimer(v11, *((void **)g_pnpstate + 61), (void *)0xFFFFFFFFFFFFFFFFLL),
        NtpServerConfig >= 0)
    && (NtpServerConfig = myStartTimerQueueTimer(
                            *((LPCRITICAL_SECTION *)g_pnpstate + 61),
                            v14,
                            (void (*)(void *, unsigned __int8))HandleChainingCountTimeout,
                            v15,
                            0,
                            60000 * *((_DWORD *)g_pnpstate + 130),
                            v18),
        NtpServerConfig >= 0) )
  {
LABEL_72:
    _set_se_translator(v20);
    NtpServerConfig = 0;
  }
LABEL_74:
  v16 = TrapThreads(0);
  if ( v16 < 0 && NtpServerConfig >= 0 )
    NtpServerConfig = v16;
LABEL_77:
  if ( v2 )
    LocalFree(v2);
  if ( NtpServerConfig < 0 )
    StopNtpClient();
  return (unsigned int)NtpServerConfig;
}

```

## disassembly

```asm
0x18002522c  mov     rax, rsp
0x18002522f  mov     [rax+18h], rbx
0x180025233  mov     [rax+20h], rsi
0x180025237  push    rdi
0x180025238  push    r14
0x18002523a  push    r15
0x18002523c  sub     rsp, 80h
0x180025243  xor     ebx, ebx
0x180025245  mov     [rax+8], rbx
0x180025249  mov     [rax-58h], bl
0x18002524c  mov     r15b, bl
0x18002524f  lea     rcx, ?SeTransFunc@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; SeTransFunc(uint,_EXCEPTION_POINTERS *)
0x180025256  call    cs:__imp__set_se_translator
0x18002525d  nop     dword ptr [rax+rax+00h]
0x180025262  mov     [rsp+98h+arg_8], rax
0x18002526a  lea     rcx, [rsp+98h+hMem]; struct NtpServerConfig **
0x180025272  call    ?ReadNtpServerConfig@@YAJPEAPEAUNtpServerConfig@@@Z; ReadNtpServerConfig(NtpServerConfig * *)
0x180025277  mov     edi, eax
0x180025279  mov     [rsp+98h+var_54], eax
0x18002527d  test    eax, eax
0x18002527f  jns     short loc_18002528E
0x180025281  mov     rsi, [rsp+98h+hMem]
0x180025289  jmp     loc_180025733
0x18002528e  mov     ecx, 1; int
0x180025293  call    ?TrapThreads@@YAJH@Z; TrapThreads(int)
0x180025298  mov     edi, eax
0x18002529a  mov     [rsp+98h+var_54], eax
0x18002529e  test    eax, eax
0x1800252a0  jns     short loc_1800252AF
0x1800252a2  mov     rsi, [rsp+98h+hMem]
0x1800252aa  jmp     loc_180025733
0x1800252af  mov     [rsp+98h+var_58], 1
0x1800252b4  mov     rsi, [rsp+98h+hMem]
0x1800252bc  mov     rdx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x1800252c3  mov     ecx, ebx
0x1800252c5  cmp     [rsi], ebx
0x1800252c7  setnz   cl
0x1800252ca  movzx   eax, byte ptr [rdx+103h]
0x1800252d1  mov     r14d, 3Ah ; ':'
0x1800252d7  cmp     eax, ecx
0x1800252d9  jz      short loc_180025305
0x1800252db  cmp     [rsi], ebx
0x1800252dd  setnz   al
0x1800252e0  mov     [rdx+103h], al
0x1800252e6  mov     ecx, r14d
0x1800252e9  call    FileLogAllowEntry
0x1800252ee  test    al, al
0x1800252f0  jz      short loc_1800252FE
0x1800252f2  lea     rcx, aAllowservernon; "  AllowServerNonstandardModeCominations"...
0x1800252f9  call    FileLogAdd
0x1800252fe  mov     rdx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180025305  mov     eax, [rsi+8]
0x180025308  mov     [rdx+104h], eax
0x18002530e  mov     eax, [rsi+4]
0x180025311  cmp     [rdx+0C8h], eax
0x180025317  jz      short loc_18002533E
0x180025319  mov     [rdx+0C8h], eax
0x18002531f  mov     ecx, r14d
0x180025322  call    FileLogAllowEntry
0x180025327  test    al, al
0x180025329  jz      short loc_180025337
0x18002532b  lea     rcx, aEventlogflagsC_0; "  EventLogFlags changed.\n"
0x180025332  call    FileLogAdd
0x180025337  mov     rdx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x18002533e  mov     eax, [rsi+0Ch]
0x180025341  mov     [rdx+0F8h], eax
0x180025347  mov     ecx, ebx
0x180025349  cmp     [rsi+38h], ebx
0x18002534c  setnz   cl
0x18002534f  movzx   eax, byte ptr [rdx+108h]
0x180025356  cmp     eax, ecx
0x180025358  jz      short loc_180025385
0x18002535a  cmp     [rsi+38h], ebx
0x18002535d  setnz   al
0x180025360  mov     [rdx+108h], al
0x180025366  mov     ecx, r14d
0x180025369  call    FileLogAllowEntry
0x18002536e  test    al, al
0x180025370  jz      short loc_18002537E
0x180025372  lea     rcx, aRequiresecuret_0; "  RequireSecureTimeSyncRequests changed"...
0x180025379  call    FileLogAdd
0x18002537e  mov     rdx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180025385  mov     eax, [rsi+3Ch]
0x180025388  mov     [rdx+10Ch], eax
0x18002538e  mov     eax, [rsi+40h]
0x180025391  cmp     [rdx+110h], eax
0x180025397  jz      short loc_1800253BE
0x180025399  mov     [rdx+110h], eax
0x18002539f  mov     ecx, r14d
0x1800253a2  call    FileLogAllowEntry
0x1800253a7  test    al, al
0x1800253a9  jz      short loc_1800253B7
0x1800253ab  lea     rcx, aUnsecuretimesy_0; "  UnsecureTimeSyncRequestsLogThrottlePe"...
0x1800253b2  call    FileLogAdd
0x1800253b7  mov     rdx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x1800253be  mov     eax, [rsi+44h]
0x1800253c1  mov     [rdx+114h], eax
0x1800253c7  mov     ecx, ebx
0x1800253c9  cmp     [rsi+28h], ebx
0x1800253cc  setnz   cl
0x1800253cf  movzx   eax, byte ptr [rdx+224h]
0x1800253d6  cmp     eax, ecx
0x1800253d8  jz      short loc_180025405
0x1800253da  cmp     [rsi+28h], ebx
0x1800253dd  setnz   al
0x1800253e0  mov     [rdx+224h], al
0x1800253e6  mov     ecx, r14d
0x1800253e9  call    FileLogAllowEntry
0x1800253ee  test    al, al
0x1800253f0  jz      short loc_1800253FE
0x1800253f2  lea     rcx, aChaintabledisa; "  ChainTableDisabled changed.\n"
0x1800253f9  call    FileLogAdd
0x1800253fe  mov     rdx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180025405  mov     eax, [rsi+18h]
0x180025408  mov     ecx, 400h
0x18002540d  cmp     eax, ecx
0x18002540f  jbe     short loc_18002542C
0x180025411  mov     [rdx+228h], ecx
0x180025417  mov     ecx, r14d
0x18002541a  call    FileLogAllowEntry
0x18002541f  test    al, al
0x180025421  jz      short loc_18002546E
0x180025423  lea     rcx, aChaintablemaxe_0; "  ChainTableMaxEntries using maximum va"...
0x18002542a  jmp     short loc_180025469
0x18002542c  mov     ecx, 80h
0x180025431  cmp     eax, ecx
0x180025433  jnb     short loc_180025450
0x180025435  mov     [rdx+228h], ecx
0x18002543b  mov     ecx, r14d
0x18002543e  call    FileLogAllowEntry
0x180025443  test    al, al
0x180025445  jz      short loc_18002546E
0x180025447  lea     rcx, aChaintablemaxe; "  ChainTableMaxEntries using minimum va"...
0x18002544e  jmp     short loc_180025469
0x180025450  mov     [rdx+228h], eax
0x180025456  mov     ecx, r14d
0x180025459  call    FileLogAllowEntry
0x18002545e  test    al, al
0x180025460  jz      short loc_18002546E
0x180025462  lea     rcx, aChaintablemaxe_1; "  ChainTableMaxEntries using registry/d"...
0x180025469  call    FileLogAdd
0x18002546e  mov     ecx, [rsi+20h]
0x180025471  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180025478  cmp     ecx, 10h
0x18002547b  jbe     short loc_18002549C
0x18002547d  mov     dword ptr [rax+22Ch], 10h
0x180025487  mov     ecx, r14d
0x18002548a  call    FileLogAllowEntry
0x18002548f  test    al, al
0x180025491  jz      short loc_1800254DE
0x180025493  lea     rcx, aChaintablemaxh_1; "  ChainTableMaxHostEntries using maximu"...
0x18002549a  jmp     short loc_1800254D9
0x18002549c  cmp     ecx, 4
0x18002549f  jnb     short loc_1800254C0
0x1800254a1  mov     dword ptr [rax+22Ch], 4
0x1800254ab  mov     ecx, r14d
0x1800254ae  call    FileLogAllowEntry
0x1800254b3  test    al, al
0x1800254b5  jz      short loc_1800254DE
0x1800254b7  lea     rcx, aChaintablemaxh; "  ChainTableMaxHostEntries using minimu"...
0x1800254be  jmp     short loc_1800254D9
0x1800254c0  mov     [rax+22Ch], ecx
0x1800254c6  mov     ecx, r14d
0x1800254c9  call    FileLogAllowEntry
0x1800254ce  test    al, al
0x1800254d0  jz      short loc_1800254DE
0x1800254d2  lea     rcx, aChaintablemaxh_0; "  ChainTableMaxHostEntries using regist"...
0x1800254d9  call    FileLogAdd
0x1800254de  mov     ecx, [rsi+10h]
0x1800254e1  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x1800254e8  cmp     ecx, 10h
0x1800254eb  jbe     short loc_18002550C
0x1800254ed  mov     dword ptr [rax+230h], 10h
0x1800254f7  mov     ecx, r14d
0x1800254fa  call    FileLogAllowEntry
0x1800254ff  test    al, al
0x180025501  jz      short loc_18002554E
0x180025503  lea     rcx, aChaintableentr_1; "  ChainTableEntryTimeout using maximum "...
0x18002550a  jmp     short loc_180025549
0x18002550c  cmp     ecx, 4
0x18002550f  jnb     short loc_180025530
0x180025511  mov     dword ptr [rax+230h], 4
0x18002551b  mov     ecx, r14d
0x18002551e  call    FileLogAllowEntry
0x180025523  test    al, al
0x180025525  jz      short loc_18002554E
0x180025527  lea     rcx, aChaintableentr_0; "  ChainTableEntryTimeout using minimum "...
0x18002552e  jmp     short loc_180025549
0x180025530  mov     [rax+230h], ecx
0x180025536  mov     ecx, r14d
0x180025539  call    FileLogAllowEntry
0x18002553e  test    al, al
0x180025540  jz      short loc_18002554E
0x180025542  lea     rcx, aChaintableentr; "  ChainTableEntryTimeout using registry"...
0x180025549  call    FileLogAdd
0x18002554e  mov     rcx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180025555  mov     eax, [rcx+208h]
0x18002555b  cmp     [rsi+30h], eax
0x18002555e  jz      short loc_180025587
0x180025560  mov     r15b, 1
0x180025563  mov     [rsp+98h+var_57], r15b
0x180025568  mov     ecx, r14d
0x18002556b  call    FileLogAllowEntry
0x180025570  test    al, al
0x180025572  jz      short loc_180025580
0x180025574  lea     rcx, aChainloggingra_2; "  ChainLoggingRate changed.\n"
0x18002557b  call    FileLogAdd
0x180025580  mov     rcx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180025587  mov     eax, [rsi+30h]
0x18002558a  mov     edx, 2760h
0x18002558f  cmp     eax, edx
0x180025591  jbe     short loc_1800255AE
0x180025593  mov     [rcx+208h], edx
0x180025599  mov     ecx, r14d
0x18002559c  call    FileLogAllowEntry
0x1800255a1  test    al, al
0x1800255a3  jz      short loc_1800255CC
0x1800255a5  lea     rcx, aChainloggingra_1; "  ChainLoggingRate using maximum value."...
0x1800255ac  jmp     short loc_1800255C7
0x1800255ae  mov     [rcx+208h], eax
0x1800255b4  mov     ecx, r14d
0x1800255b7  call    FileLogAllowEntry
0x1800255bc  test    al, al
0x1800255be  jz      short loc_1800255CC
0x1800255c0  lea     rcx, aChainloggingra_0; "  ChainLoggingRate using registry/defau"...
0x1800255c7  call    FileLogAdd
0x1800255cc  mov     rdx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; void *
0x1800255d3  cmp     [rdx+20Ch], bl
0x1800255d9  jnz     short loc_180025640
0x1800255db  mov     eax, [rdx+208h]
0x1800255e1  test    eax, eax
0x1800255e3  jz      loc_1800256EF
0x1800255e9  imul    eax, 0EA60h
0x1800255ef  mov     [rsp+98h+var_70], eax; unsigned int
0x1800255f3  mov     [rsp+98h+var_78], ebx; unsigned int
0x1800255f7  lea     r8, ?HandleChainingCountTimeout@@YAXPEAXE@Z; void (*)(void *, unsigned __int8)
0x1800255fe  mov     rcx, [rdx+1E8h]; lpCriticalSection
0x180025605  call    ?myStartTimerQueueTimer@@YAJPEAX0P6AX0E@Z0KKK@Z; myStartTimerQueueTimer(void *,void *,void (*)(void *,uchar),void *,ulong,ulong,ulong)
0x18002560a  mov     edi, eax
0x18002560c  mov     [rsp+98h+var_54], eax
0x180025610  test    eax, eax
0x180025612  jns     short loc_180025619
0x180025614  jmp     loc_180025723
0x180025619  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180025620  mov     byte ptr [rax+20Ch], 1
0x180025627  mov     ecx, r14d
0x18002562a  call    FileLogAllowEntry
0x18002562f  test    al, al
0x180025631  jz      loc_1800256EF
0x180025637  lea     rcx, aChaintableeven_0; "  ChainTableEventLogging is now enabled"...
0x18002563e  jmp     short loc_18002568F
0x180025640  cmp     [rdx+208h], ebx
0x180025646  jnz     short loc_180025696
0x180025648  mov     rax, [rdx+1E8h]
0x18002564f  test    rax, rax
0x180025652  jz      short loc_180025696
0x180025654  or      r8, 0FFFFFFFFFFFFFFFFh; void *
0x180025658  mov     rdx, rax; void *
0x18002565b  call    ?myStopTimerQueueTimer@@YAJPEAX00@Z; myStopTimerQueueTimer(void *,void *,void *)
0x180025660  mov     edi, eax
0x180025662  mov     [rsp+98h+var_54], eax
0x180025666  test    eax, eax
0x180025668  jns     short loc_18002566F
0x18002566a  jmp     loc_180025723
0x18002566f  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180025676  mov     [rax+20Ch], bl
0x18002567c  mov     ecx, r14d
0x18002567f  call    FileLogAllowEntry
0x180025684  test    al, al
0x180025686  jz      short loc_1800256EF
0x180025688  lea     rcx, aChaintableeven; "  ChainTableEventLogging is now disable"...
0x18002568f  call    FileLogAdd
0x180025694  jmp     short loc_1800256EF
0x180025696  test    r15b, r15b
0x180025699  jz      short loc_1800256EF
0x18002569b  or      r8, 0FFFFFFFFFFFFFFFFh; void *
0x18002569f  mov     rdx, [rdx+1E8h]; void *
0x1800256a6  call    ?myStopTimerQueueTimer@@YAJPEAX00@Z; myStopTimerQueueTimer(void *,void *,void *)
0x1800256ab  mov     edi, eax
0x1800256ad  mov     [rsp+98h+var_54], eax
0x1800256b1  test    eax, eax
0x1800256b3  jns     short loc_1800256B7
0x1800256b5  jmp     short loc_180025723
0x1800256b7  mov     rcx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x1800256be  imul    eax, [rcx+208h], 0EA60h
0x1800256c8  mov     [rsp+98h+var_70], eax; unsigned int
0x1800256cc  mov     [rsp+98h+var_78], ebx; unsigned int
0x1800256d0  lea     r8, ?HandleChainingCountTimeout@@YAXPEAXE@Z; void (*)(void *, unsigned __int8)
0x1800256d7  mov     rcx, [rcx+1E8h]; lpCriticalSection
0x1800256de  call    ?myStartTimerQueueTimer@@YAJPEAX0P6AX0E@Z0KKK@Z; myStartTimerQueueTimer(void *,void *,void (*)(void *,uchar),void *,ulong,ulong,ulong)
0x1800256e3  mov     edi, eax
0x1800256e5  mov     [rsp+98h+var_54], eax
0x1800256e9  test    eax, eax
0x1800256eb  jns     short loc_1800256EF
0x1800256ed  jmp     short loc_180025723
0x1800256ef  jmp     short loc_180025703
0x1800256f1  jmp     short loc_1800256F5
0x1800256f3  jmp     short $+2
0x1800256f5  xor     ebx, ebx
0x1800256f7  mov     edi, [rsp+98h+var_54]
  ... truncated ...
```
