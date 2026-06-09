# MRTComponent_Cleanup

- ea: `0x180002368`
- end: `0x180002663`
- name: `MRTComponent_Cleanup`
- size: `763`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180002670`

## callees

- `0x180001b50`
- `0x180001b88`
- `0x180002368`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002642`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002642`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800023a2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800023a2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800024f0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800024f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800023c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002458`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002502`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800025a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800023c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002458`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002502`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800025a0`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18000258a`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18000258a`
- `WDSCORE!WdsSetupLogMessageW` at `0x180002447`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800024d6`
- `WDSCORE!WdsSetupLogMessageW` at `0x180002625`
- `WDSCORE!WdsSetupLogMessageW` at `0x180002447`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800024d6`
- `WDSCORE!WdsSetupLogMessageW` at `0x180002625`
- `WDSCORE!CurrentIP` at `0x1800023d2`
- `WDSCORE!CurrentIP` at `0x180002466`
- `WDSCORE!CurrentIP` at `0x180002510`
- `WDSCORE!CurrentIP` at `0x1800025ae`
- `WDSCORE!CurrentIP` at `0x1800023d2`
- `WDSCORE!CurrentIP` at `0x180002466`
- `WDSCORE!CurrentIP` at `0x180002510`
- `WDSCORE!CurrentIP` at `0x1800025ae`

## string_xrefs

- `0x180002403`: `MRTComponent_Cleanup`
- `0x180002496`: `MRTComponent_Cleanup`
- `0x180002549`: `MRTComponent_Cleanup`
- `0x1800025e5`: `MRTComponent_Cleanup`
- `0x1800023e1`: `MRTGeneralize:%d - ERROR: Could not open MRT key: 0x%X`
- `0x18000252d`: `MRTGeneralize:%d - ERROR: Failed to remove values/subkeys under HKLM\%ls: %d`
- `0x1800025c9`: `MRTGeneralize:%d - WARN: Failed to remove HKLM\%ls`

## pseudocode

```c
__int64 MRTComponent_Cleanup()
{
  LSTATUS v0; // eax
  unsigned int v1; // esi
  DWORD v2; // edi
  __int64 v3; // rbx
  struct tagLOG_PARTIAL_MSG *v4; // rax
  DWORD LastError; // edi
  __int64 v6; // rbx
  struct tagLOG_PARTIAL_MSG *v7; // rax
  DWORD v8; // edi
  __int64 v9; // rbx
  struct tagLOG_PARTIAL_MSG *v10; // rax
  DWORD v11; // edi
  __int64 v12; // rbx
  struct tagLOG_PARTIAL_MSG *v13; // rax
  HKEY hKey; // [rsp+70h] [rbp+8h] BYREF

  hKey = 0;
  v0 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\RemovalTools\\MRT", 0, 0xF003Fu, &hKey);
  v1 = v0;
  if ( v0 )
  {
    if ( (unsigned int)(v0 - 2) <= 1 )
    {
      LastError = GetLastError();
      v6 = CurrentIP();
      v7 = ConstructPartialMsgW(0x4000000u, "MRTGeneralize:%d - MRT key does not exist, skipping action.", 247);
      WdsSetupLogMessageW(
        v7,
        983040,
        L"D",
        0,
        247,
        L"onecore\\amcore\\antimalware\\source\\filehascode\\table\\mrtgeneralize.cpp",
        L"MRTComponent_Cleanup",
        v6,
        LastError,
        0,
        0);
      v1 = 0;
    }
    else
    {
      v2 = GetLastError();
      v3 = CurrentIP();
      v4 = ConstructPartialMsgW(0x2000000u, "MRTGeneralize:%d - ERROR: Could not open MRT key: 0x%X", 255, v1);
      WdsSetupLogMessageW(
        v4,
        983040,
        L"D",
        0,
        255,
        L"onecore\\amcore\\antimalware\\source\\filehascode\\table\\mrtgeneralize.cpp",
        L"MRTComponent_Cleanup",
        v3,
        v2,
        0,
        0);
    }
  }
  else
  {
    v1 = RegDeleteTreeW(hKey, 0);
    if ( v1 )
    {
      v8 = GetLastError();
      v9 = CurrentIP();
      v10 = ConstructPartialMsgW(
              0x2000000u,
              "MRTGeneralize:%d - ERROR: Failed to remove values/subkeys under HKLM\\%ls: %d",
              267,
              L"SOFTWARE\\Microsoft\\RemovalTools\\MRT",
              v1);
      WdsSetupLogMessageW(
        v10,
        983040,
        L"D",
        0,
        267,
        L"onecore\\amcore\\antimalware\\source\\filehascode\\table\\mrtgeneralize.cpp",
        L"MRTComponent_Cleanup",
        v9,
        v8,
        0,
        0);
    }
    else
    {
      v1 = RegDeleteKeyW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\RemovalTools\\MRT");
      if ( v1 )
      {
        v11 = GetLastError();
        v12 = CurrentIP();
        v13 = ConstructPartialMsgW(
                0x3000000u,
                "MRTGeneralize:%d - WARN: Failed to remove HKLM\\%ls",
                279,
                L"SOFTWARE\\Microsoft\\RemovalTools\\MRT");
        WdsSetupLogMessageW(
          v13,
          983040,
          L"D",
          0,
          279,
          L"onecore\\amcore\\antimalware\\source\\filehascode\\table\\mrtgeneralize.cpp",
          L"MRTComponent_Cleanup",
          v12,
          v11,
          0,
          0);
        v1 = 0;
      }
      DeleteDefenderWscInstance();
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v1;
}

```

## disassembly

```asm
0x180002368  mov     r11, rsp
0x18000236b  mov     [r11+10h], rbx
0x18000236f  mov     [r11+18h], rsi
0x180002373  push    rdi
0x180002374  sub     rsp, 60h
0x180002378  lea     rax, [r11+8]
0x18000237c  mov     qword ptr [r11+8], 0
0x180002384  mov     rbx, 0FFFFFFFF80000002h
0x18000238b  mov     [r11-48h], rax
0x18000238f  mov     rcx, rbx; hKey
0x180002392  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\RemovalTools\\MRT"
0x180002399  mov     r9d, 0F003Fh; samDesired
0x18000239f  xor     r8d, r8d; ulOptions
0x1800023a2  call    cs:__imp_RegOpenKeyExW
0x1800023a9  nop     dword ptr [rax+rax+00h]
0x1800023ae  mov     esi, eax
0x1800023b0  test    eax, eax
0x1800023b2  jz      loc_1800024E9
0x1800023b8  lea     ecx, [rax-2]
0x1800023bb  cmp     ecx, 1
0x1800023be  jbe     loc_180002458
0x1800023c4  call    cs:__imp_GetLastError
0x1800023cb  nop     dword ptr [rax+rax+00h]
0x1800023d0  mov     edi, eax
0x1800023d2  call    cs:__imp_CurrentIP
0x1800023d9  nop     dword ptr [rax+rax+00h]
0x1800023de  mov     r9d, esi
0x1800023e1  lea     rdx, aMrtgeneralizeD_7; "MRTGeneralize:%d - ERROR: Could not ope"...
0x1800023e8  mov     r8d, 0FFh
0x1800023ee  mov     ecx, 2000000h; unsigned int
0x1800023f3  mov     rbx, rax
0x1800023f6  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800023fb  mov     [rsp+68h+var_18], 0
0x180002403  lea     rcx, aMrtcomponentCl; "MRTComponent_Cleanup"
0x18000240a  mov     [rsp+68h+var_20], 0
0x180002413  mov     [rsp+68h+var_28], edi
0x180002417  mov     [rsp+68h+var_30], rbx
0x18000241c  mov     [rsp+68h+var_38], rcx
0x180002421  lea     rcx, aOnecoreAmcoreA; "onecore\\amcore\\antimalware\\source\\f"...
0x180002428  mov     [rsp+68h+var_40], rcx
0x18000242d  mov     [rsp+68h+var_48], 0FFh
0x180002435  xor     r9d, r9d
0x180002438  lea     r8, aD; "D"
0x18000243f  mov     edx, 0F0000h
0x180002444  mov     rcx, rax
0x180002447  call    cs:__imp_WdsSetupLogMessageW
0x18000244e  nop     dword ptr [rax+rax+00h]
0x180002453  jmp     loc_180002638
0x180002458  call    cs:__imp_GetLastError
0x18000245f  nop     dword ptr [rax+rax+00h]
0x180002464  mov     edi, eax
0x180002466  call    cs:__imp_CurrentIP
0x18000246d  nop     dword ptr [rax+rax+00h]
0x180002472  mov     esi, 0F7h
0x180002477  lea     rdx, aMrtgeneralizeD_4; "MRTGeneralize:%d - MRT key does not exi"...
0x18000247e  mov     r8d, esi
0x180002481  mov     ecx, 4000000h; unsigned int
0x180002486  mov     rbx, rax
0x180002489  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000248e  mov     [rsp+68h+var_18], 0
0x180002496  lea     rcx, aMrtcomponentCl; "MRTComponent_Cleanup"
0x18000249d  mov     [rsp+68h+var_20], 0
0x1800024a6  lea     r8, aD; "D"
0x1800024ad  mov     [rsp+68h+var_28], edi
0x1800024b1  xor     r9d, r9d
0x1800024b4  mov     [rsp+68h+var_30], rbx
0x1800024b9  mov     edx, 0F0000h
0x1800024be  mov     [rsp+68h+var_38], rcx
0x1800024c3  lea     rcx, aOnecoreAmcoreA; "onecore\\amcore\\antimalware\\source\\f"...
0x1800024ca  mov     [rsp+68h+var_40], rcx
0x1800024cf  mov     rcx, rax
0x1800024d2  mov     [rsp+68h+var_48], esi
0x1800024d6  call    cs:__imp_WdsSetupLogMessageW
0x1800024dd  nop     dword ptr [rax+rax+00h]
0x1800024e2  xor     esi, esi
0x1800024e4  jmp     loc_180002638
0x1800024e9  mov     rcx, [rsp+68h+hKey]; hKey
0x1800024ee  xor     edx, edx; lpSubKey
0x1800024f0  call    cs:__imp_RegDeleteTreeW
0x1800024f7  nop     dword ptr [rax+rax+00h]
0x1800024fc  mov     esi, eax
0x1800024fe  test    eax, eax
0x180002500  jz      short loc_180002580
0x180002502  call    cs:__imp_GetLastError
0x180002509  nop     dword ptr [rax+rax+00h]
0x18000250e  mov     edi, eax
0x180002510  call    cs:__imp_CurrentIP
0x180002517  nop     dword ptr [rax+rax+00h]
0x18000251c  lea     r9, aSoftwareMicros; "SOFTWARE\\Microsoft\\RemovalTools\\MRT"
0x180002523  mov     [rsp+68h+var_48], esi
0x180002527  mov     r8d, 10Bh
0x18000252d  lea     rdx, aMrtgeneralizeD_12; "MRTGeneralize:%d - ERROR: Failed to rem"...
0x180002534  mov     ecx, 2000000h; unsigned int
0x180002539  mov     rbx, rax
0x18000253c  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180002541  mov     [rsp+68h+var_18], 0
0x180002549  lea     rcx, aMrtcomponentCl; "MRTComponent_Cleanup"
0x180002550  mov     [rsp+68h+var_20], 0
0x180002559  mov     [rsp+68h+var_28], edi
0x18000255d  mov     [rsp+68h+var_30], rbx
0x180002562  mov     [rsp+68h+var_38], rcx
0x180002567  lea     rcx, aOnecoreAmcoreA; "onecore\\amcore\\antimalware\\source\\f"...
0x18000256e  mov     [rsp+68h+var_40], rcx
0x180002573  mov     [rsp+68h+var_48], 10Bh
0x18000257b  jmp     loc_180002435
0x180002580  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\RemovalTools\\MRT"
0x180002587  mov     rcx, rbx; hKey
0x18000258a  call    cs:__imp_RegDeleteKeyW
0x180002591  nop     dword ptr [rax+rax+00h]
0x180002596  mov     esi, eax
0x180002598  test    eax, eax
0x18000259a  jz      loc_180002633
0x1800025a0  call    cs:__imp_GetLastError
0x1800025a7  nop     dword ptr [rax+rax+00h]
0x1800025ac  mov     edi, eax
0x1800025ae  call    cs:__imp_CurrentIP
0x1800025b5  nop     dword ptr [rax+rax+00h]
0x1800025ba  mov     esi, 117h
0x1800025bf  lea     r9, aSoftwareMicros; "SOFTWARE\\Microsoft\\RemovalTools\\MRT"
0x1800025c6  mov     r8d, esi
0x1800025c9  lea     rdx, aMrtgeneralizeD_8; "MRTGeneralize:%d - WARN: Failed to remo"...
0x1800025d0  mov     ecx, 3000000h; unsigned int
0x1800025d5  mov     rbx, rax
0x1800025d8  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800025dd  mov     [rsp+68h+var_18], 0
0x1800025e5  lea     rcx, aMrtcomponentCl; "MRTComponent_Cleanup"
0x1800025ec  mov     [rsp+68h+var_20], 0
0x1800025f5  lea     r8, aD; "D"
0x1800025fc  mov     [rsp+68h+var_28], edi
0x180002600  xor     r9d, r9d
0x180002603  mov     [rsp+68h+var_30], rbx
0x180002608  mov     edx, 0F0000h
0x18000260d  mov     [rsp+68h+var_38], rcx
0x180002612  lea     rcx, aOnecoreAmcoreA; "onecore\\amcore\\antimalware\\source\\f"...
0x180002619  mov     [rsp+68h+var_40], rcx
0x18000261e  mov     rcx, rax
0x180002621  mov     [rsp+68h+var_48], esi
0x180002625  call    cs:__imp_WdsSetupLogMessageW
0x18000262c  nop     dword ptr [rax+rax+00h]
0x180002631  xor     esi, esi
0x180002633  call    DeleteDefenderWscInstance
0x180002638  mov     rcx, [rsp+68h+hKey]; hKey
0x18000263d  test    rcx, rcx
0x180002640  jz      short loc_18000264E
0x180002642  call    cs:__imp_RegCloseKey
0x180002649  nop     dword ptr [rax+rax+00h]
0x18000264e  lea     r11, [rsp+68h+var_8]
0x180002653  mov     eax, esi
0x180002655  mov     rbx, [r11+18h]
0x180002659  mov     rsi, [r11+20h]
0x18000265d  mov     rsp, r11
0x180002660  pop     rdi
0x180002661  retn
```
