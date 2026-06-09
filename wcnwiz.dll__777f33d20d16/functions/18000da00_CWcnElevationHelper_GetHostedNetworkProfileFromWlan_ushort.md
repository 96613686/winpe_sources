# CWcnElevationHelper::GetHostedNetworkProfileFromWlan(ushort * *)

- ea: `0x18000da00`
- end: `0x18000dcfd`
- name: `?GetHostedNetworkProfileFromWlan@CWcnElevationHelper@@UEAAJPEAPEAG@Z`
- size: `765`
- prototype: `__int64 __fastcall(CWcnElevationHelper *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x18000d630`
- `0x18000da00`
- `0x18000e0a0`
- `0x18000e1dc`
- `0x18002de1c`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000dc3d`
- `OLEAUT32!__imp_SysAllocString` at `0x18000dc3d`
- `wlanapi!WlanCloseHandle` at `0x18000dcb2`
- `wlanapi!WlanCloseHandle` at `0x18000dcb2`
- `wlanapi!WlanHostedNetworkQueryStatus` at `0x18000db2c`
- `wlanapi!WlanHostedNetworkQueryStatus` at `0x18000db2c`
- `wlanapi!WlanOpenHandle` at `0x18000daca`
- `wlanapi!WlanOpenHandle` at `0x18000daca`
- `wlanapi!WlanHostedNetworkQueryProperty` at `0x18000dbd4`
- `wlanapi!WlanHostedNetworkQueryProperty` at `0x18000dbd4`
- `wlanapi!WlanFreeMemory` at `0x18000dc84`
- `wlanapi!WlanFreeMemory` at `0x18000dc9a`
- `wlanapi!WlanFreeMemory` at `0x18000dc84`
- `wlanapi!WlanFreeMemory` at `0x18000dc9a`

## string_xrefs

- `0x18000da70`: `pbstrXmlProfile`
- `0x18000dc66`: `*pbstrXmlProfile`

## pseudocode

```c
__int64 __fastcall CWcnElevationHelper::GetHostedNetworkProfileFromWlan(
        CWcnElevationHelper *this,
        unsigned __int16 **a2)
{
  _QWORD *v3; // r10
  signed int v4; // ebx
  const char *Indent; // rax
  __int64 v6; // r10
  signed int v8; // eax
  unsigned int v9; // ebx
  _QWORD *v10; // r10
  __int64 v11; // rdx
  unsigned int v12; // ebx
  const char *v13; // rax
  __int64 v14; // rdx
  const char *v15; // r9
  unsigned int v16; // ebx
  unsigned __int16 *v17; // rax
  unsigned int v18; // eax
  __int64 v19; // r10
  PVOID ppvData; // [rsp+30h] [rbp-20h] BYREF
  void *phClientHandle; // [rsp+38h] [rbp-18h] BYREF
  PWLAN_HOSTED_NETWORK_STATUS ppWlanHostedNetworkStatus; // [rsp+40h] [rbp-10h] BYREF
  DWORD pdwDataSize; // [rsp+88h] [rbp+38h] BYREF
  DWORD pdwNegotiatedVersion; // [rsp+90h] [rbp+40h] BYREF
  enum _WLAN_OPCODE_VALUE_TYPE pWlanOpcodeValueType; // [rsp+98h] [rbp+48h] BYREF

  v3 = WPP_GLOBAL_Control;
  v4 = 1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v6 + 16), 19, WPP_a09cfb1ef79339475d0105a4a8d169a8_Traceguids, Indent);
    v3 = WPP_GLOBAL_Control;
  }
  if ( !a2 )
  {
    if ( v3 != &WPP_GLOBAL_Control && *((_BYTE *)v3 + 25) >= 2u )
      WPP_SF_s(v3[2], 20, WPP_a09cfb1ef79339475d0105a4a8d169a8_Traceguids, "pbstrXmlProfile");
    return 2147500035LL;
  }
  phClientHandle = 0;
  pdwNegotiatedVersion = 0;
  ppWlanHostedNetworkStatus = 0;
  pdwDataSize = 0;
  ppvData = 0;
  pWlanOpcodeValueType = wlan_opcode_value_type_query_only;
  *a2 = 0;
  v8 = WlanOpenHandle(2u, 0, &pdwNegotiatedVersion, &phClientHandle);
  if ( v8 )
  {
    if ( v8 > 0 )
      v9 = (unsigned __int16)v8 | 0x80070000;
    else
      v9 = v8;
    v4 = v9 | 0x80000000;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_44;
    v11 = 21;
    goto LABEL_16;
  }
  v8 = WlanHostedNetworkQueryStatus(phClientHandle, &ppWlanHostedNetworkStatus, 0);
  if ( v8 )
  {
    if ( v8 > 0 )
      v12 = (unsigned __int16)v8 | 0x80070000;
    else
      v12 = v8;
    v4 = v12 | 0x80000000;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_44;
    v11 = 22;
    goto LABEL_16;
  }
  if ( ppWlanHostedNetworkStatus->HostedNetworkState == wlan_hosted_network_unavailable )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      goto LABEL_44;
    v13 = GetIndent(0);
    v14 = 23;
    v15 = v13;
LABEL_28:
    WPP_SF_s(v10[2], v14, WPP_a09cfb1ef79339475d0105a4a8d169a8_Traceguids, v15);
    goto LABEL_43;
  }
  v8 = WlanHostedNetworkQueryProperty(
         phClientHandle,
         wlan_hosted_network_opcode_station_profile,
         &pdwDataSize,
         &ppvData,
         &pWlanOpcodeValueType,
         0);
  if ( !v8 )
  {
    if ( pdwDataSize < 4 )
    {
      v4 = -2147418113;
      goto LABEL_43;
    }
    *((_BYTE *)ppvData + pdwDataSize - 2) = 0;
    *((_BYTE *)ppvData + pdwDataSize - 1) = 0;
    v17 = SysAllocString((const OLECHAR *)ppvData);
    *a2 = v17;
    if ( v17 )
    {
      v4 = 0;
      goto LABEL_43;
    }
    v4 = -2147024882;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_44;
    v14 = 25;
    v15 = "*pbstrXmlProfile";
    goto LABEL_28;
  }
  if ( v8 > 0 )
    v16 = (unsigned __int16)v8 | 0x80070000;
  else
    v16 = v8;
  v4 = v16 | 0x80000000;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    goto LABEL_44;
  v11 = 24;
LABEL_16:
  WPP_SF_Dd(v10[2], v11, WPP_a09cfb1ef79339475d0105a4a8d169a8_Traceguids, (unsigned int)v8, v4);
LABEL_43:
  v10 = WPP_GLOBAL_Control;
LABEL_44:
  if ( ppWlanHostedNetworkStatus )
  {
    WlanFreeMemory(ppWlanHostedNetworkStatus);
    v10 = WPP_GLOBAL_Control;
  }
  if ( ppvData )
  {
    WlanFreeMemory(ppvData);
    v10 = WPP_GLOBAL_Control;
  }
  if ( phClientHandle )
  {
    WlanCloseHandle(phClientHandle, 0);
    v10 = WPP_GLOBAL_Control;
  }
  if ( v10 != &WPP_GLOBAL_Control && (v4 < 0 || *((_BYTE *)v10 + 25) >= 6u) )
  {
    v18 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v19 + 16), 26, (unsigned int)WPP_a09cfb1ef79339475d0105a4a8d169a8_Traceguids, v18, v4);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000da00  push    rbp
0x18000da02  push    rbx
0x18000da03  push    rsi
0x18000da04  push    r12
0x18000da06  push    r15
0x18000da08  mov     rbp, rsp
0x18000da0b  sub     rsp, 50h
0x18000da0f  mov     rsi, rdx
0x18000da12  mov     r10, cs:WPP_GLOBAL_Control
0x18000da19  lea     r15, WPP_GLOBAL_Control
0x18000da20  lea     r12, WPP_a09cfb1ef79339475d0105a4a8d169a8_Traceguids
0x18000da27  mov     ebx, 1
0x18000da2c  cmp     r10, r15
0x18000da2f  jz      short loc_18000DA58
0x18000da31  cmp     byte ptr [r10+19h], 6
0x18000da36  jb      short loc_18000DA58
0x18000da38  mov     ecx, ebx; int
0x18000da3a  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000da3f  mov     rcx, [r10+10h]
0x18000da43  lea     edx, [rbx+12h]
0x18000da46  mov     r9, rax
0x18000da49  mov     r8, r12
0x18000da4c  call    WPP_SF_s
0x18000da51  mov     r10, cs:WPP_GLOBAL_Control
0x18000da58  test    rsi, rsi
0x18000da5b  jnz     short loc_18000DA89
0x18000da5d  cmp     r10, r15
0x18000da60  jz      short loc_18000DA7F
0x18000da62  cmp     byte ptr [r10+19h], 2
0x18000da67  jb      short loc_18000DA7F
0x18000da69  mov     rcx, [r10+10h]
0x18000da6d  lea     edx, [rsi+14h]
0x18000da70  lea     r9, aPbstrxmlprofil_0; "pbstrXmlProfile"
0x18000da77  mov     r8, r12
0x18000da7a  call    WPP_SF_s
0x18000da7f  mov     eax, 80004003h
0x18000da84  jmp     loc_18000DCF1
0x18000da89  xor     edx, edx; pReserved
0x18000da8b  mov     [rbp+phClientHandle], 0
0x18000da93  lea     r9, [rbp+phClientHandle]; phClientHandle
0x18000da97  mov     [rbp+pdwNegotiatedVersion], 0
0x18000da9e  lea     r8, [rbp+pdwNegotiatedVersion]; pdwNegotiatedVersion
0x18000daa2  mov     [rbp+ppWlanHostedNetworkStatus], 0
0x18000daaa  mov     [rbp+pdwDataSize], 0
0x18000dab1  lea     ecx, [rdx+2]; dwClientVersion
0x18000dab4  mov     [rbp+ppvData], 0
0x18000dabc  mov     [rbp+arg_18], 0
0x18000dac3  mov     qword ptr [rsi], 0
0x18000daca  call    cs:__imp_WlanOpenHandle
0x18000dad0  test    eax, eax
0x18000dad2  jz      short loc_18000DB21
0x18000dad4  jg      short loc_18000DADA
0x18000dad6  mov     ebx, eax
0x18000dad8  jmp     short loc_18000DAE3
0x18000dada  movzx   ebx, ax
0x18000dadd  or      ebx, 80070000h
0x18000dae3  or      ebx, 80000000h
0x18000dae9  mov     r10, cs:WPP_GLOBAL_Control
0x18000daf0  cmp     r10, r15
0x18000daf3  jz      loc_18000DC7B
0x18000daf9  cmp     byte ptr [r10+19h], 2
0x18000dafe  jb      loc_18000DC7B
0x18000db04  mov     edx, 15h
0x18000db09  mov     rcx, [r10+10h]
0x18000db0d  mov     r9d, eax
0x18000db10  mov     r8, r12
0x18000db13  mov     dword ptr [rsp+50h+pWlanOpcodeValueType], ebx
0x18000db17  call    WPP_SF_Dd
0x18000db1c  jmp     loc_18000DC74
0x18000db21  mov     rcx, [rbp+phClientHandle]; hClientHandle
0x18000db25  lea     rdx, [rbp+ppWlanHostedNetworkStatus]; ppWlanHostedNetworkStatus
0x18000db29  xor     r8d, r8d; pvReserved
0x18000db2c  call    cs:__imp_WlanHostedNetworkQueryStatus
0x18000db32  test    eax, eax
0x18000db34  jz      short loc_18000DB6D
0x18000db36  jg      short loc_18000DB3C
0x18000db38  mov     ebx, eax
0x18000db3a  jmp     short loc_18000DB45
0x18000db3c  movzx   ebx, ax
0x18000db3f  or      ebx, 80070000h
0x18000db45  or      ebx, 80000000h
0x18000db4b  mov     r10, cs:WPP_GLOBAL_Control
0x18000db52  cmp     r10, r15
0x18000db55  jz      loc_18000DC7B
0x18000db5b  cmp     byte ptr [r10+19h], 2
0x18000db60  jb      loc_18000DC7B
0x18000db66  mov     edx, 16h
0x18000db6b  jmp     short loc_18000DB09
0x18000db6d  mov     rax, [rbp+ppWlanHostedNetworkStatus]
0x18000db71  cmp     dword ptr [rax], 0
0x18000db74  jnz     short loc_18000DBB1
0x18000db76  mov     r10, cs:WPP_GLOBAL_Control
0x18000db7d  cmp     r10, r15
0x18000db80  jz      loc_18000DC7B
0x18000db86  cmp     byte ptr [r10+19h], 4
0x18000db8b  jb      loc_18000DC7B
0x18000db91  xor     ecx, ecx; int
0x18000db93  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000db98  mov     edx, 17h
0x18000db9d  mov     r9, rax
0x18000dba0  mov     rcx, [r10+10h]
0x18000dba4  mov     r8, r12
0x18000dba7  call    WPP_SF_s
0x18000dbac  jmp     loc_18000DC74
0x18000dbb1  mov     rcx, [rbp+phClientHandle]; hClientHandle
0x18000dbb5  lea     rax, [rbp+arg_18]
0x18000dbb9  mov     [rsp+50h+pvReserved], 0; pvReserved
0x18000dbc2  lea     r9, [rbp+ppvData]; ppvData
0x18000dbc6  lea     r8, [rbp+pdwDataSize]; pdwDataSize
0x18000dbca  mov     [rsp+50h+pWlanOpcodeValueType], rax; pWlanOpcodeValueType
0x18000dbcf  mov     edx, 2; OpCode
0x18000dbd4  call    cs:__imp_WlanHostedNetworkQueryProperty
0x18000dbda  test    eax, eax
0x18000dbdc  jz      short loc_18000DC10
0x18000dbde  jg      short loc_18000DBE4
0x18000dbe0  mov     ebx, eax
0x18000dbe2  jmp     short loc_18000DBED
0x18000dbe4  movzx   ebx, ax
0x18000dbe7  or      ebx, 80070000h
0x18000dbed  or      ebx, 80000000h
0x18000dbf3  mov     r10, cs:WPP_GLOBAL_Control
0x18000dbfa  cmp     r10, r15
0x18000dbfd  jz      short loc_18000DC7B
0x18000dbff  cmp     byte ptr [r10+19h], 2
0x18000dc04  jb      short loc_18000DC7B
0x18000dc06  mov     edx, 18h
0x18000dc0b  jmp     loc_18000DB09
0x18000dc10  mov     eax, [rbp+pdwDataSize]
0x18000dc13  cmp     eax, 4
0x18000dc16  jnb     short loc_18000DC1F
0x18000dc18  mov     ebx, 8000FFFFh
0x18000dc1d  jmp     short loc_18000DC74
0x18000dc1f  add     eax, 0FFFFFFFEh
0x18000dc22  mov     ecx, eax
0x18000dc24  mov     rax, [rbp+ppvData]
0x18000dc28  mov     byte ptr [rcx+rax], 0
0x18000dc2c  mov     ecx, [rbp+pdwDataSize]
0x18000dc2f  mov     rax, [rbp+ppvData]
0x18000dc33  dec     ecx
0x18000dc35  mov     byte ptr [rcx+rax], 0
0x18000dc39  mov     rcx, [rbp+ppvData]; psz
0x18000dc3d  call    cs:__imp_SysAllocString
0x18000dc43  mov     [rsi], rax
0x18000dc46  test    rax, rax
0x18000dc49  jnz     short loc_18000DC72
0x18000dc4b  mov     ebx, 8007000Eh
0x18000dc50  mov     r10, cs:WPP_GLOBAL_Control
0x18000dc57  cmp     r10, r15
0x18000dc5a  jz      short loc_18000DC7B
0x18000dc5c  cmp     byte ptr [r10+19h], 2
0x18000dc61  jb      short loc_18000DC7B
0x18000dc63  lea     edx, [rax+19h]
0x18000dc66  lea     r9, aPbstrxmlprofil; "*pbstrXmlProfile"
0x18000dc6d  jmp     loc_18000DBA0
0x18000dc72  xor     ebx, ebx
0x18000dc74  mov     r10, cs:WPP_GLOBAL_Control
0x18000dc7b  mov     rcx, [rbp+ppWlanHostedNetworkStatus]; pMemory
0x18000dc7f  test    rcx, rcx
0x18000dc82  jz      short loc_18000DC91
0x18000dc84  call    cs:__imp_WlanFreeMemory
0x18000dc8a  mov     r10, cs:WPP_GLOBAL_Control
0x18000dc91  mov     rcx, [rbp+ppvData]; pMemory
0x18000dc95  test    rcx, rcx
0x18000dc98  jz      short loc_18000DCA7
0x18000dc9a  call    cs:__imp_WlanFreeMemory
0x18000dca0  mov     r10, cs:WPP_GLOBAL_Control
0x18000dca7  mov     rcx, [rbp+phClientHandle]; hClientHandle
0x18000dcab  test    rcx, rcx
0x18000dcae  jz      short loc_18000DCBF
0x18000dcb0  xor     edx, edx; pReserved
0x18000dcb2  call    cs:__imp_WlanCloseHandle
0x18000dcb8  mov     r10, cs:WPP_GLOBAL_Control
0x18000dcbf  cmp     r10, r15
0x18000dcc2  jz      short loc_18000DCEF
0x18000dcc4  test    ebx, ebx
0x18000dcc6  js      short loc_18000DCCF
0x18000dcc8  cmp     byte ptr [r10+19h], 6
0x18000dccd  jb      short loc_18000DCEF
0x18000dccf  or      ecx, 0FFFFFFFFh; int
0x18000dcd2  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000dcd7  mov     rcx, [r10+10h]
0x18000dcdb  mov     edx, 1Ah
0x18000dce0  mov     r9, rax
0x18000dce3  mov     dword ptr [rsp+50h+pWlanOpcodeValueType], ebx
0x18000dce7  mov     r8, r12
0x18000dcea  call    WPP_SF_sd
0x18000dcef  mov     eax, ebx
0x18000dcf1  add     rsp, 50h
0x18000dcf5  pop     r15
0x18000dcf7  pop     r12
0x18000dcf9  pop     rsi
0x18000dcfa  pop     rbx
0x18000dcfb  pop     rbp
0x18000dcfc  retn
```
