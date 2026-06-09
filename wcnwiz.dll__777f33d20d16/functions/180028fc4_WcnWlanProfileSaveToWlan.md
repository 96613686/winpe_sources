# WcnWlanProfileSaveToWlan

- ea: `0x180028fc4`
- end: `0x1800292ce`
- name: `WcnWlanProfileSaveToWlan`
- size: `778`
- prototype: `__int64 __fastcall(LPCWSTR strProfileXml, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180028b30`

## callees

- `0x18000d630`
- `0x18000e0a0`
- `0x18000e1dc`
- `0x180028fc4`
- `0x1800292d4`
- `0x18002de1c`

## import_xrefs

- `wlanapi!WlanCloseHandle` at `0x18002927c`
- `wlanapi!WlanCloseHandle` at `0x18002927c`
- `wlanapi!WlanOpenHandle` at `0x180029079`
- `wlanapi!WlanOpenHandle` at `0x180029079`
- `wlanapi!WlanSetProfile` at `0x180029198`
- `wlanapi!WlanSetProfile` at `0x180029198`
- `wlanapi!WlanEnumInterfaces` at `0x1800290da`
- `wlanapi!WlanEnumInterfaces` at `0x1800290da`
- `wlanapi!WlanFreeMemory` at `0x180029264`
- `wlanapi!WlanFreeMemory` at `0x180029264`

## string_xrefs

- `0x180029053`: `wszWlanXmlProfile`

## pseudocode

```c
__int64 __fastcall WcnWlanProfileSaveToWlan(LPCWSTR strProfileXml, _QWORD *a2)
{
  _QWORD *v4; // r10
  signed int v5; // ebx
  const char *Indent; // rax
  __int64 v7; // r10
  signed int v9; // eax
  unsigned int v10; // ebx
  _QWORD *v11; // r10
  __int64 v12; // rdx
  unsigned int v13; // ebx
  char v14; // r14
  DWORD v15; // edi
  WLAN_INTERFACE_INFO *v16; // rsi
  __int64 v17; // rax
  unsigned int v18; // eax
  __int64 v19; // r10
  int v20; // edx
  int v21; // r8d
  char v22; // r11
  const char *v23; // rax
  __int64 v24; // r10
  unsigned int v25; // eax
  __int64 v26; // r10
  void *phClientHandle; // [rsp+40h] [rbp-10h] BYREF
  DWORD pdwNegotiatedVersion; // [rsp+90h] [rbp+40h] BYREF
  DWORD pdwReasonCode; // [rsp+A0h] [rbp+50h] BYREF
  PWLAN_INTERFACE_INFO_LIST ppInterfaceList; // [rsp+A8h] [rbp+58h] BYREF

  phClientHandle = 0;
  pdwNegotiatedVersion = 0;
  ppInterfaceList = 0;
  v4 = WPP_GLOBAL_Control;
  v5 = 1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v7 + 16), 10, WPP_d86a235b51753f579bf51b43ee4d8f7d_Traceguids, Indent);
    v4 = WPP_GLOBAL_Control;
  }
  if ( !strProfileXml )
  {
    if ( v4 != &WPP_GLOBAL_Control && *((_BYTE *)v4 + 25) >= 2u )
      WPP_SF_s(v4[2], 11, WPP_d86a235b51753f579bf51b43ee4d8f7d_Traceguids, "wszWlanXmlProfile");
    return 2147500035LL;
  }
  v9 = WlanOpenHandle(2u, 0, &pdwNegotiatedVersion, &phClientHandle);
  if ( v9 )
  {
    if ( v9 > 0 )
      v10 = (unsigned __int16)v9 | 0x80070000;
    else
      v10 = v9;
    v5 = v10 | 0x80000000;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_42;
    v12 = 12;
    goto LABEL_16;
  }
  v9 = WlanEnumInterfaces(phClientHandle, 0, &ppInterfaceList);
  if ( v9 )
  {
    if ( v9 > 0 )
      v13 = (unsigned __int16)v9 | 0x80070000;
    else
      v13 = v9;
    v5 = v13 | 0x80000000;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_42;
    v12 = 13;
LABEL_16:
    WPP_SF_Dd(v11[2], v12, WPP_d86a235b51753f579bf51b43ee4d8f7d_Traceguids, (unsigned int)v9, v5);
    goto LABEL_41;
  }
  v14 = 0;
  v11 = WPP_GLOBAL_Control;
  v15 = 0;
  if ( !ppInterfaceList->dwNumberOfItems )
    goto LABEL_38;
  do
  {
    v16 = &ppInterfaceList->InterfaceInfo[v15];
    if ( !a2 )
      goto LABEL_29;
    v17 = *a2 - *(_QWORD *)&v16->InterfaceGuid.Data1;
    if ( *a2 == *(_QWORD *)&v16->InterfaceGuid.Data1 )
      v17 = a2[1] - *(_QWORD *)v16->InterfaceGuid.Data4;
    if ( !v17 )
    {
LABEL_29:
      pdwReasonCode = 0;
      if ( !WlanSetProfile(phClientHandle, &v16->InterfaceGuid, 0, strProfileXml, 0, 1, 0, &pdwReasonCode) )
      {
        v14 = 1;
        goto LABEL_34;
      }
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        v18 = (unsigned int)GetIndent(0);
        WPP_SF_sS_guid_d(*(_QWORD *)(v19 + 16), v20, v21, v18, (__int64)v16->strInterfaceDescription, (__int64)v16, v22);
LABEL_34:
        v11 = WPP_GLOBAL_Control;
      }
    }
    ++v15;
  }
  while ( v15 < ppInterfaceList->dwNumberOfItems );
  if ( v14 )
  {
    v5 = 0;
    goto LABEL_42;
  }
LABEL_38:
  if ( v11 != &WPP_GLOBAL_Control && *((_BYTE *)v11 + 25) >= 4u )
  {
    v23 = GetIndent(0);
    WPP_SF_s(*(_QWORD *)(v24 + 16), 15, WPP_d86a235b51753f579bf51b43ee4d8f7d_Traceguids, v23);
LABEL_41:
    v11 = WPP_GLOBAL_Control;
  }
LABEL_42:
  if ( ppInterfaceList )
  {
    WlanFreeMemory(ppInterfaceList);
    v11 = WPP_GLOBAL_Control;
  }
  if ( phClientHandle )
  {
    WlanCloseHandle(phClientHandle, 0);
    v11 = WPP_GLOBAL_Control;
  }
  if ( v11 != &WPP_GLOBAL_Control && (v5 < 0 || *((_BYTE *)v11 + 25) >= 6u) )
  {
    v25 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v26 + 16), 16, (unsigned int)WPP_d86a235b51753f579bf51b43ee4d8f7d_Traceguids, v25, v5);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180028fc4  push    rbp
0x180028fc6  push    rbx
0x180028fc7  push    rsi
0x180028fc8  push    rdi
0x180028fc9  push    r12
0x180028fcb  push    r14
0x180028fcd  push    r15
0x180028fcf  mov     rbp, rsp
0x180028fd2  sub     rsp, 50h
0x180028fd6  mov     r15, rdx
0x180028fd9  mov     [rbp+phClientHandle], 0
0x180028fe1  mov     r12, rcx
0x180028fe4  mov     [rbp+pdwNegotiatedVersion], 0
0x180028feb  mov     [rbp+ppInterfaceList], 0
0x180028ff3  mov     r10, cs:WPP_GLOBAL_Control
0x180028ffa  lea     rdi, WPP_GLOBAL_Control
0x180029001  lea     rsi, WPP_d86a235b51753f579bf51b43ee4d8f7d_Traceguids
0x180029008  mov     ebx, 1
0x18002900d  cmp     r10, rdi
0x180029010  jz      short loc_180029039
0x180029012  cmp     byte ptr [r10+19h], 6
0x180029017  jb      short loc_180029039
0x180029019  mov     ecx, ebx; int
0x18002901b  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180029020  mov     rcx, [r10+10h]
0x180029024  lea     edx, [rbx+9]
0x180029027  mov     r9, rax
0x18002902a  mov     r8, rsi
0x18002902d  call    WPP_SF_s
0x180029032  mov     r10, cs:WPP_GLOBAL_Control
0x180029039  test    r12, r12
0x18002903c  jnz     short loc_18002906C
0x18002903e  cmp     r10, rdi
0x180029041  jz      short loc_180029062
0x180029043  cmp     byte ptr [r10+19h], 2
0x180029048  jb      short loc_180029062
0x18002904a  mov     rcx, [r10+10h]
0x18002904e  lea     edx, [r12+0Bh]
0x180029053  lea     r9, aWszwlanxmlprof; "wszWlanXmlProfile"
0x18002905a  mov     r8, rsi
0x18002905d  call    WPP_SF_s
0x180029062  mov     eax, 80004003h
0x180029067  jmp     loc_1800292BF
0x18002906c  xor     edx, edx; pReserved
0x18002906e  lea     r9, [rbp+phClientHandle]; phClientHandle
0x180029072  lea     r8, [rbp+pdwNegotiatedVersion]; pdwNegotiatedVersion
0x180029076  lea     ecx, [rdx+2]; dwClientVersion
0x180029079  call    cs:__imp_WlanOpenHandle
0x18002907f  test    eax, eax
0x180029081  jz      short loc_1800290D0
0x180029083  jg      short loc_180029089
0x180029085  mov     ebx, eax
0x180029087  jmp     short loc_180029092
0x180029089  movzx   ebx, ax
0x18002908c  or      ebx, 80070000h
0x180029092  or      ebx, 80000000h
0x180029098  mov     r10, cs:WPP_GLOBAL_Control
0x18002909f  cmp     r10, rdi
0x1800290a2  jz      loc_18002925B
0x1800290a8  cmp     byte ptr [r10+19h], 2
0x1800290ad  jb      loc_18002925B
0x1800290b3  mov     edx, 0Ch
0x1800290b8  mov     rcx, [r10+10h]
0x1800290bc  mov     r9d, eax
0x1800290bf  mov     r8, rsi
0x1800290c2  mov     dword ptr [rsp+50h+strAllUserProfileSecurity], ebx
0x1800290c6  call    WPP_SF_Dd
0x1800290cb  jmp     loc_180029254
0x1800290d0  mov     rcx, [rbp+phClientHandle]; hClientHandle
0x1800290d4  lea     r8, [rbp+ppInterfaceList]; ppInterfaceList
0x1800290d8  xor     edx, edx; pReserved
0x1800290da  call    cs:__imp_WlanEnumInterfaces
0x1800290e0  test    eax, eax
0x1800290e2  jz      short loc_18002911B
0x1800290e4  jg      short loc_1800290EA
0x1800290e6  mov     ebx, eax
0x1800290e8  jmp     short loc_1800290F3
0x1800290ea  movzx   ebx, ax
0x1800290ed  or      ebx, 80070000h
0x1800290f3  or      ebx, 80000000h
0x1800290f9  mov     r10, cs:WPP_GLOBAL_Control
0x180029100  cmp     r10, rdi
0x180029103  jz      loc_18002925B
0x180029109  cmp     byte ptr [r10+19h], 2
0x18002910e  jb      loc_18002925B
0x180029114  mov     edx, 0Dh
0x180029119  jmp     short loc_1800290B8
0x18002911b  mov     rax, [rbp+ppInterfaceList]
0x18002911f  xor     r14b, r14b
0x180029122  mov     r10, cs:WPP_GLOBAL_Control
0x180029129  xor     edi, edi
0x18002912b  cmp     [rax], edi
0x18002912d  jbe     loc_180029226
0x180029133  mov     rsi, [rbp+ppInterfaceList]
0x180029137  add     rsi, 8
0x18002913b  mov     eax, edi
0x18002913d  imul    rcx, rax, 214h
0x180029144  add     rsi, rcx
0x180029147  test    r15, r15
0x18002914a  jz      short loc_180029165
0x18002914c  mov     rax, [r15]
0x18002914f  sub     rax, [rsi]
0x180029152  jnz     short loc_18002915C
0x180029154  mov     rax, [r15+8]
0x180029158  sub     rax, [rsi+8]
0x18002915c  test    rax, rax
0x18002915f  jnz     loc_180029201
0x180029165  mov     rcx, [rbp+phClientHandle]; hClientHandle
0x180029169  lea     rax, [rbp+arg_10]
0x18002916d  mov     [rsp+50h+pdwReasonCode], rax; pdwReasonCode
0x180029172  mov     r9, r12; strProfileXml
0x180029175  mov     [rsp+50h+pReserved], 0; pReserved
0x18002917e  xor     r8d, r8d; dwFlags
0x180029181  mov     [rsp+50h+bOverwrite], ebx; bOverwrite
0x180029185  mov     rdx, rsi; pInterfaceGuid
0x180029188  mov     [rsp+50h+strAllUserProfileSecurity], 0; strAllUserProfileSecurity
0x180029191  mov     [rbp+arg_10], 0
0x180029198  call    cs:__imp_WlanSetProfile
0x18002919e  mov     r11d, eax
0x1800291a1  test    eax, eax
0x1800291a3  jz      short loc_1800291F7
0x1800291a5  mov     r10, cs:WPP_GLOBAL_Control
0x1800291ac  lea     rax, WPP_GLOBAL_Control
0x1800291b3  cmp     r10, rax
0x1800291b6  jz      short loc_180029201
0x1800291b8  cmp     byte ptr [r10+19h], 3
0x1800291bd  jb      short loc_180029201
0x1800291bf  test    r11d, r11d
0x1800291c2  jle     short loc_1800291CF
0x1800291c4  movzx   r11d, r11w
0x1800291c8  or      r11d, 80070000h
0x1800291cf  xor     ecx, ecx; int
0x1800291d1  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800291d6  mov     dword ptr [rsp+50h+pReserved], r11d
0x1800291db  lea     rcx, [rsi+10h]
0x1800291df  mov     qword ptr [rsp+50h+bOverwrite], rsi
0x1800291e4  mov     r9, rax
0x1800291e7  mov     [rsp+50h+strAllUserProfileSecurity], rcx
0x1800291ec  mov     rcx, [r10+10h]
0x1800291f0  call    WPP_SF_sS_guid_d
0x1800291f5  jmp     short loc_1800291FA
0x1800291f7  mov     r14b, bl
0x1800291fa  mov     r10, cs:WPP_GLOBAL_Control
0x180029201  mov     rax, [rbp+ppInterfaceList]
0x180029205  add     edi, ebx
0x180029207  cmp     edi, [rax]
0x180029209  jb      loc_180029133
0x18002920f  test    r14b, r14b
0x180029212  jz      short loc_18002921F
0x180029214  xor     ebx, ebx
0x180029216  lea     rdi, WPP_GLOBAL_Control
0x18002921d  jmp     short loc_18002925B
0x18002921f  lea     rsi, WPP_d86a235b51753f579bf51b43ee4d8f7d_Traceguids
0x180029226  lea     rdi, WPP_GLOBAL_Control
0x18002922d  cmp     r10, rdi
0x180029230  jz      short loc_18002925B
0x180029232  cmp     byte ptr [r10+19h], 4
0x180029237  jb      short loc_18002925B
0x180029239  xor     ecx, ecx; int
0x18002923b  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180029240  mov     rcx, [r10+10h]
0x180029244  mov     edx, 0Fh
0x180029249  mov     r9, rax
0x18002924c  mov     r8, rsi
0x18002924f  call    WPP_SF_s
0x180029254  mov     r10, cs:WPP_GLOBAL_Control
0x18002925b  mov     rcx, [rbp+ppInterfaceList]; pMemory
0x18002925f  test    rcx, rcx
0x180029262  jz      short loc_180029271
0x180029264  call    cs:__imp_WlanFreeMemory
0x18002926a  mov     r10, cs:WPP_GLOBAL_Control
0x180029271  mov     rcx, [rbp+phClientHandle]; hClientHandle
0x180029275  test    rcx, rcx
0x180029278  jz      short loc_180029289
0x18002927a  xor     edx, edx; pReserved
0x18002927c  call    cs:__imp_WlanCloseHandle
0x180029282  mov     r10, cs:WPP_GLOBAL_Control
0x180029289  cmp     r10, rdi
0x18002928c  jz      short loc_1800292BD
0x18002928e  test    ebx, ebx
0x180029290  js      short loc_180029299
0x180029292  cmp     byte ptr [r10+19h], 6
0x180029297  jb      short loc_1800292BD
0x180029299  or      ecx, 0FFFFFFFFh; int
0x18002929c  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800292a1  mov     rcx, [r10+10h]
0x1800292a5  lea     r8, WPP_d86a235b51753f579bf51b43ee4d8f7d_Traceguids
0x1800292ac  mov     edx, 10h
0x1800292b1  mov     dword ptr [rsp+50h+strAllUserProfileSecurity], ebx
0x1800292b5  mov     r9, rax
0x1800292b8  call    WPP_SF_sd
0x1800292bd  mov     eax, ebx
0x1800292bf  add     rsp, 50h
0x1800292c3  pop     r15
0x1800292c5  pop     r14
0x1800292c7  pop     r12
0x1800292c9  pop     rdi
0x1800292ca  pop     rsi
0x1800292cb  pop     rbx
0x1800292cc  pop     rbp
0x1800292cd  retn
```
