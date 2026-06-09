# FixPreLowBoxMediaStreamingModeSecurableObject(void)

- ea: `0x1801584b4`
- end: `0x1801587d1`
- name: `?FixPreLowBoxMediaStreamingModeSecurableObject@@YAXXZ`
- size: `797`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1801587d8`

## callees

- `0x18000aa0c`
- `0x180011530`
- `0x18006be48`
- `0x1800c6774`
- `0x180106340`
- `0x18010730c`
- `0x180107330`
- `0x1801584b4`
- `0x18021e380`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1801586e3`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1801586e3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180158673`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180158673`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180158765`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180158765`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180158777`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180158777`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801586c5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801586c5`

## string_xrefs

- `0x18015863f`: `System\CurrentControlSet\Services\WlanSvc`

## pseudocode

```c
void FixPreLowBoxMediaStreamingModeSecurableObject(void)
{
  __int64 v0; // rdx
  BYTE *v1; // rcx
  const wchar_t *v2; // rax
  __int128 v3; // xmm1
  __int128 v4; // xmm0
  __int128 v5; // xmm1
  __int128 v6; // xmm0
  __int128 v7; // xmm1
  __int128 v8; // xmm0
  __int128 v9; // xmm1
  __int64 v10; // rdx
  BYTE *v11; // rax
  const wchar_t *v12; // rcx
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  __int64 v25; // rdx
  unsigned int ValueW; // ebx
  __int64 v27; // r8
  HKEY v28; // rcx
  DWORD v29; // eax
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  BYTE Buf1[272]; // [rsp+50h] [rbp-B0h] BYREF
  BYTE Data[336]; // [rsp+160h] [rbp+60h] BYREF
  WCHAR SubKey[264]; // [rsp+2B0h] [rbp+1B0h] BYREF
  wchar_t Source[2000]; // [rsp+4C0h] [rbp+3C0h] BYREF

  v0 = 2;
  v1 = Buf1;
  v2 = L"O:SYG:SYD:(A;;CCRC;;;BU)(A;;CCDCWPSDRCWD;;;BU)(A;;CCRC;;;NO)(A;;CCDCWPSDRCWD;;;NO)(A;;CCRC;;;BA)(A;;CCDCWPSDRCWD;"
        ";;BA)(D;;FA;;;WD)";
  do
  {
    v3 = *((_OWORD *)v2 + 1);
    *(_OWORD *)v1 = *(_OWORD *)v2;
    v4 = *((_OWORD *)v2 + 2);
    *((_OWORD *)v1 + 1) = v3;
    v5 = *((_OWORD *)v2 + 3);
    *((_OWORD *)v1 + 2) = v4;
    v6 = *((_OWORD *)v2 + 4);
    *((_OWORD *)v1 + 3) = v5;
    v7 = *((_OWORD *)v2 + 5);
    *((_OWORD *)v1 + 4) = v6;
    v8 = *((_OWORD *)v2 + 6);
    *((_OWORD *)v1 + 5) = v7;
    v9 = *((_OWORD *)v2 + 7);
    v2 += 64;
    *((_OWORD *)v1 + 6) = v8;
    *((_OWORD *)v1 + 7) = v9;
    v1 += 128;
    --v0;
  }
  while ( v0 );
  v10 = 2;
  *(_QWORD *)(v1 - 2) = *(_QWORD *)(v2 - 1);
  v11 = Data;
  v12 = L"O:SYG:SYD:(A;;CCRC;;;BU)(A;;CCDCWPSDRCWD;;;BU)(A;;CCRC;;;AC)(A;;CCDCWPSDRCWD;;;AC)(A;;CCRC;;;NO)(A;;CCDCWPSDRCWD"
         ";;;NO)(A;;CCRC;;;BA)(A;;CCDCWPSDRCWD;;;BA)(D;;FA;;;WD)";
  do
  {
    v13 = *((_OWORD *)v12 + 1);
    *(_OWORD *)v11 = *(_OWORD *)v12;
    v14 = *((_OWORD *)v12 + 2);
    *((_OWORD *)v11 + 1) = v13;
    v15 = *((_OWORD *)v12 + 3);
    *((_OWORD *)v11 + 2) = v14;
    v16 = *((_OWORD *)v12 + 4);
    *((_OWORD *)v11 + 3) = v15;
    v17 = *((_OWORD *)v12 + 5);
    *((_OWORD *)v11 + 4) = v16;
    v18 = *((_OWORD *)v12 + 6);
    *((_OWORD *)v11 + 5) = v17;
    v19 = *((_OWORD *)v12 + 7);
    v12 += 64;
    *((_OWORD *)v11 + 6) = v18;
    *((_OWORD *)v11 + 7) = v19;
    v11 += 128;
    --v10;
  }
  while ( v10 );
  v20 = *(_OWORD *)v12;
  hkey = 0;
  v21 = *((_OWORD *)v12 + 1);
  *(_OWORD *)v11 = v20;
  v22 = *((_OWORD *)v12 + 2);
  *((_OWORD *)v11 + 1) = v21;
  v23 = *((_OWORD *)v12 + 3);
  *((_OWORD *)v11 + 2) = v22;
  v24 = *(_OWORD *)(v12 + 31);
  *((_OWORD *)v11 + 3) = v23;
  *(_OWORD *)(v11 + 62) = v24;
  memset_0(Source, 0, sizeof(Source));
  pcbData = 2000;
  memset_0(SubKey, 0, 0x208u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 10, WPP_3a6abbfbb6653e334b912cc02283798e_Traceguids);
  }
  WlanStateSeparation_GetMutableRegistryKey(
    SubKey,
    260,
    L"System\\CurrentControlSet\\Services\\WlanSvc",
    L"Parameters\\WlanAPIPermissions");
  ValueW = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x2001Fu, &hkey);
  if ( !ValueW )
  {
    v28 = hkey;
    if ( !hkey )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(0, v25, v27);
      v28 = hkey;
    }
    ValueW = RegGetValueW(v28, 0, L"Media Streaming Mode Enabled", 2u, 0, Source, &pcbData);
    if ( !ValueW
      && 2 * (unsigned int)wcsnlen(Source, (unsigned __int64)pcbData >> 1) == 260
      && !memcmp_0(Buf1, Source, 0x106u) )
    {
      v29 = 334;
      pcbData = 334;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 11, WPP_3a6abbfbb6653e334b912cc02283798e_Traceguids);
        v29 = pcbData;
      }
      ValueW = RegSetValueExW(hkey, L"Media Streaming Mode Enabled", 0, 1u, Data, v29);
    }
  }
  if ( hkey )
    RegCloseKey(hkey);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 12, WPP_3a6abbfbb6653e334b912cc02283798e_Traceguids, ValueW);
  }
}

```

## disassembly

```asm
0x1801584b4  mov     [rsp-8+arg_0], rbx
0x1801584b9  mov     [rsp-8+arg_8], r15
0x1801584be  push    rbp
0x1801584bf  lea     rbp, [rsp-1370h]
0x1801584c7  mov     eax, 1470h
0x1801584cc  call    _alloca_probe
0x1801584d1  sub     rsp, rax
0x1801584d4  mov     rax, cs:__security_cookie
0x1801584db  xor     rax, rsp
0x1801584de  mov     [rbp+1370h+var_10], rax
0x1801584e5  mov     edx, 2
0x1801584ea  lea     rcx, [rsp+1470h+Buf1]
0x1801584ef  lea     rax, aOSygSydACcrcBu; "O:SYG:SYD:(A;;CCRC;;;BU)(A;;CCDCWPSDRCW"...
0x1801584f6  lea     r8d, [rdx+7Eh]
0x1801584fa  movups  xmm0, xmmword ptr [rax]
0x1801584fd  movups  xmm1, xmmword ptr [rax+10h]
0x180158501  movups  xmmword ptr [rcx], xmm0
0x180158504  movups  xmm0, xmmword ptr [rax+20h]
0x180158508  movups  xmmword ptr [rcx+10h], xmm1
0x18015850c  movups  xmm1, xmmword ptr [rax+30h]
0x180158510  movups  xmmword ptr [rcx+20h], xmm0
0x180158514  movups  xmm0, xmmword ptr [rax+40h]
0x180158518  movups  xmmword ptr [rcx+30h], xmm1
0x18015851c  movups  xmm1, xmmword ptr [rax+50h]
0x180158520  movups  xmmword ptr [rcx+40h], xmm0
0x180158524  movups  xmm0, xmmword ptr [rax+60h]
0x180158528  movups  xmmword ptr [rcx+50h], xmm1
0x18015852c  movups  xmm1, xmmword ptr [rax+70h]
0x180158530  add     rax, r8
0x180158533  movups  xmmword ptr [rcx+60h], xmm0
0x180158537  movups  xmmword ptr [rcx+70h], xmm1
0x18015853b  add     rcx, r8
0x18015853e  sub     rdx, 1
0x180158542  jnz     short loc_1801584FA
0x180158544  mov     rax, [rax-2]
0x180158548  mov     edx, 2
0x18015854d  mov     [rcx-2], rax
0x180158551  lea     rax, [rbp+1370h+Data]
0x180158555  lea     rcx, aOSygSydACcrcBu_0; "O:SYG:SYD:(A;;CCRC;;;BU)(A;;CCDCWPSDRCW"...
0x18015855c  movups  xmm0, xmmword ptr [rcx]
0x18015855f  movups  xmm1, xmmword ptr [rcx+10h]
0x180158563  movups  xmmword ptr [rax], xmm0
0x180158566  movups  xmm0, xmmword ptr [rcx+20h]
0x18015856a  movups  xmmword ptr [rax+10h], xmm1
0x18015856e  movups  xmm1, xmmword ptr [rcx+30h]
0x180158572  movups  xmmword ptr [rax+20h], xmm0
0x180158576  movups  xmm0, xmmword ptr [rcx+40h]
0x18015857a  movups  xmmword ptr [rax+30h], xmm1
0x18015857e  movups  xmm1, xmmword ptr [rcx+50h]
0x180158582  movups  xmmword ptr [rax+40h], xmm0
0x180158586  movups  xmm0, xmmword ptr [rcx+60h]
0x18015858a  movups  xmmword ptr [rax+50h], xmm1
0x18015858e  movups  xmm1, xmmword ptr [rcx+70h]
0x180158592  add     rcx, r8
0x180158595  movups  xmmword ptr [rax+60h], xmm0
0x180158599  movups  xmmword ptr [rax+70h], xmm1
0x18015859d  add     rax, r8
0x1801585a0  sub     rdx, 1; Val
0x1801585a4  jnz     short loc_18015855C
0x1801585a6  movups  xmm0, xmmword ptr [rcx]
0x1801585a9  mov     r8d, 0FA0h; Size
0x1801585af  mov     [rsp+1470h+hkey], rdx
0x1801585b4  movups  xmm1, xmmword ptr [rcx+10h]
0x1801585b8  movups  xmmword ptr [rax], xmm0
0x1801585bb  movups  xmm0, xmmword ptr [rcx+20h]
0x1801585bf  movups  xmmword ptr [rax+10h], xmm1
0x1801585c3  movups  xmm1, xmmword ptr [rcx+30h]
0x1801585c7  movups  xmmword ptr [rax+20h], xmm0
0x1801585cb  movups  xmm0, xmmword ptr [rcx+3Eh]
0x1801585cf  lea     rcx, [rbp+1370h+Source]; void *
0x1801585d6  movups  xmmword ptr [rax+30h], xmm1
0x1801585da  movups  xmmword ptr [rax+3Eh], xmm0
0x1801585de  call    memset_0
0x1801585e3  xor     edx, edx; Val
0x1801585e5  mov     [rsp+1470h+var_1430], 7D0h
0x1801585ed  mov     r8d, 208h; Size
0x1801585f3  lea     rcx, [rbp+1370h+SubKey]; void *
0x1801585fa  call    memset_0
0x1801585ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180158606  lea     r15, WPP_GLOBAL_Control
0x18015860d  cmp     rcx, r15
0x180158610  jz      short loc_180158633
0x180158612  cmp     byte ptr [rcx+69h], 4
0x180158616  jb      short loc_180158633
0x180158618  test    byte ptr [rcx+6Ch], 1
0x18015861c  jz      short loc_180158633
0x18015861e  mov     rcx, [rcx+60h]
0x180158622  lea     r8, WPP_3a6abbfbb6653e334b912cc02283798e_Traceguids
0x180158629  mov     edx, 0Ah
0x18015862e  call    WPP_SF_
0x180158633  lea     r9, aParametersWlan; "Parameters\\WlanAPIPermissions"
0x18015863a  mov     edx, 104h
0x18015863f  lea     r8, aSystemCurrentc_9; "System\\CurrentControlSet\\Services\\Wl"...
0x180158646  lea     rcx, [rbp+1370h+SubKey]
0x18015864d  call    WlanStateSeparation_GetMutableRegistryKey
0x180158652  lea     rax, [rsp+1470h+hkey]
0x180158657  mov     r9d, 2001Fh; samDesired
0x18015865d  xor     r8d, r8d; ulOptions
0x180158660  mov     [rsp+1470h+phkResult], rax; phkResult
0x180158665  lea     rdx, [rbp+1370h+SubKey]; lpSubKey
0x18015866c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180158673  call    cs:__imp_RegOpenKeyExW
0x180158679  mov     ebx, eax
0x18015867b  test    eax, eax
0x18015867d  jnz     loc_18015876D
0x180158683  mov     rcx, [rsp+1470h+hkey]
0x180158688  test    rcx, rcx
0x18015868b  jnz     short loc_180158697
0x18015868d  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "hKey")
0x180158692  mov     rcx, [rsp+1470h+hkey]; hkey
0x180158697  lea     rax, [rsp+1470h+var_1430]
0x18015869c  mov     r9d, 2; dwFlags
0x1801586a2  mov     [rsp+1470h+pcbData], rax; pcbData
0x1801586a7  lea     r8, aMediaStreaming; "Media Streaming Mode Enabled"
0x1801586ae  lea     rax, [rbp+1370h+Source]
0x1801586b5  xor     edx, edx; lpSubKey
0x1801586b7  mov     [rsp+1470h+pvData], rax; pvData
0x1801586bc  mov     [rsp+1470h+phkResult], 0; pdwType
0x1801586c5  call    cs:__imp_RegGetValueW
0x1801586cb  mov     ebx, eax
0x1801586cd  test    eax, eax
0x1801586cf  jnz     loc_18015876D
0x1801586d5  mov     edx, [rsp+1470h+var_1430]
0x1801586d9  lea     rcx, [rbp+1370h+Source]; Source
0x1801586e0  shr     rdx, 1; MaxCount
0x1801586e3  call    cs:__imp_wcsnlen
0x1801586e9  add     eax, eax
0x1801586eb  cmp     eax, 104h
0x1801586f0  jnz     short loc_18015876D
0x1801586f2  lea     r8d, [rax+2]; Size
0x1801586f6  lea     rdx, [rbp+1370h+Source]; Buf2
0x1801586fd  lea     rcx, [rsp+1470h+Buf1]; Buf1
0x180158702  call    memcmp_0
0x180158707  test    eax, eax
0x180158709  jnz     short loc_18015876D
0x18015870b  mov     eax, 14Eh
0x180158710  mov     [rsp+1470h+var_1430], eax
0x180158714  mov     rcx, cs:WPP_GLOBAL_Control
0x18015871b  cmp     rcx, r15
0x18015871e  jz      short loc_180158743
0x180158720  cmp     byte ptr [rcx+69h], 3
0x180158724  jb      short loc_180158743
0x180158726  test    byte ptr [rcx+6Ch], 1
0x18015872a  jz      short loc_180158743
0x18015872c  mov     rcx, [rcx+60h]
0x180158730  lea     edx, [rbx+0Bh]
0x180158733  lea     r8, WPP_3a6abbfbb6653e334b912cc02283798e_Traceguids
0x18015873a  call    WPP_SF_
0x18015873f  mov     eax, [rsp+1470h+var_1430]
0x180158743  mov     rcx, [rsp+1470h+hkey]; hKey
0x180158748  lea     rdx, aMediaStreaming; "Media Streaming Mode Enabled"
0x18015874f  mov     dword ptr [rsp+1470h+pvData], eax; cbData
0x180158753  mov     r9d, 1; dwType
0x180158759  lea     rax, [rbp+1370h+Data]
0x18015875d  xor     r8d, r8d; Reserved
0x180158760  mov     [rsp+1470h+phkResult], rax; lpData
0x180158765  call    cs:__imp_RegSetValueExW
0x18015876b  mov     ebx, eax
0x18015876d  mov     rcx, [rsp+1470h+hkey]; hKey
0x180158772  test    rcx, rcx
0x180158775  jz      short loc_18015877D
0x180158777  call    cs:__imp_RegCloseKey
0x18015877d  mov     rcx, cs:WPP_GLOBAL_Control
0x180158784  cmp     rcx, r15
0x180158787  jz      short loc_1801587AD
0x180158789  cmp     byte ptr [rcx+69h], 4
0x18015878d  jb      short loc_1801587AD
0x18015878f  test    byte ptr [rcx+6Ch], 1
0x180158793  jz      short loc_1801587AD
0x180158795  mov     rcx, [rcx+60h]
0x180158799  lea     r8, WPP_3a6abbfbb6653e334b912cc02283798e_Traceguids
0x1801587a0  mov     edx, 0Ch
0x1801587a5  mov     r9d, ebx
0x1801587a8  call    WPP_SF_d
0x1801587ad  mov     rcx, [rbp+1370h+var_10]
0x1801587b4  xor     rcx, rsp; StackCookie
0x1801587b7  call    __security_check_cookie
0x1801587bc  lea     r11, [rsp+1470h+var_s0]
0x1801587c4  mov     rbx, [r11+10h]
0x1801587c8  mov     r15, [r11+18h]
0x1801587cc  mov     rsp, r11
0x1801587cf  pop     rbp
0x1801587d0  retn
```
