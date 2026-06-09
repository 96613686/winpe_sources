# CWNPInterfaceSelector::GetWiFiConnectionCharacteristics(_GUID const &,bool *,bool *,bool *)

- ea: `0x180048b24`
- end: `0x180049293`
- name: `?GetWiFiConnectionCharacteristics@CWNPInterfaceSelector@@AEAAJAEBU_GUID@@PEA_N11@Z`
- size: `1903`
- prototype: `int(CWNPInterfaceSelector *__hidden this, const struct _GUID *, bool *, bool *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800474fc`

## callees

- `0x18000fddc`
- `0x18000fe2c`
- `0x18000fe54`
- `0x1800455ec`
- `0x180048b24`
- `0x180049448`
- `0x18004a0dc`

## import_xrefs

- `wlanapi!WlanCloseHandle` at `0x1800491f9`
- `wlanapi!WlanCloseHandle` at `0x1800491f9`
- `wlanapi!WlanOpenHandle` at `0x180048bc3`
- `wlanapi!WlanOpenHandle` at `0x180048bc3`
- `wlanapi!WlanFreeMemory` at `0x1800491dc`
- `wlanapi!WlanFreeMemory` at `0x18004920f`
- `wlanapi!WlanFreeMemory` at `0x180049229`
- `wlanapi!WlanFreeMemory` at `0x1800491dc`
- `wlanapi!WlanFreeMemory` at `0x18004920f`
- `wlanapi!WlanFreeMemory` at `0x180049229`
- `wlanapi!WlanGetProfileMetadata` at `0x180048e69`
- `wlanapi!WlanGetProfileMetadata` at `0x180048faa`
- `wlanapi!WlanGetProfileMetadata` at `0x180048e69`
- `wlanapi!WlanGetProfileMetadata` at `0x180048faa`
- `wlanapi!WlanQueryInterface` at `0x180048c95`
- `wlanapi!WlanQueryInterface` at `0x180048c95`

## pseudocode

```c
__int64 __fastcall CWNPInterfaceSelector::GetWiFiConnectionCharacteristics(
        CWNPInterfaceSelector *this,
        const struct _GUID *a2,
        bool *a3,
        bool *a4,
        bool *a5)
{
  bool *v9; // rsi
  signed int ProfileMetadata; // ebx
  __int64 v11; // r9
  bool v12; // sf
  __int64 v13; // rdx
  PVOID *v14; // r10
  __int64 v15; // rdx
  __int64 v16; // r9
  bool v17; // sf
  _DWORD *v18; // r8
  bool v19; // al
  unsigned int v20; // ecx
  bool v21; // cf
  __int64 v22; // r9
  bool v23; // sf
  float v24; // xmm2_4
  float v25; // xmm1_4
  float v26; // xmm0_4
  int v27; // eax
  PVOID *v28; // r10
  __int64 v29; // r9
  bool v30; // sf
  unsigned int v31; // ecx
  __int64 v32; // rdx
  PVOID v33; // r8
  int ppData; // [rsp+28h] [rbp-48h]
  int pWlanOpcodeValueType; // [rsp+30h] [rbp-40h]
  __int64 pdwDataSize; // [rsp+40h] [rbp-30h] BYREF
  PVOID pMemory; // [rsp+48h] [rbp-28h] BYREF
  PVOID v39; // [rsp+50h] [rbp-20h] BYREF
  PVOID v40; // [rsp+58h] [rbp-18h] BYREF
  void *phClientHandle; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  int v43; // [rsp+C0h] [rbp+50h] BYREF
  DWORD pdwNegotiatedVersion; // [rsp+C8h] [rbp+58h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 100, &WPP_bf5f8caf0c6b308512151c87984ca346_Traceguids);
  }
  v9 = a5;
  phClientHandle = (void *)-1LL;
  pdwNegotiatedVersion = 0;
  pMemory = 0;
  pdwDataSize = 0x25C00000003LL;
  v43 = 0;
  v39 = 0;
  v40 = 0;
  *a3 = 0;
  *a4 = 0;
  *v9 = 0;
  ProfileMetadata = WlanOpenHandle(2u, 0, &pdwNegotiatedVersion, &phClientHandle);
  if ( !ProfileMetadata )
    goto LABEL_15;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    if ( ProfileMetadata > 0 )
      v11 = (unsigned __int16)ProfileMetadata | 0x80070000;
    else
      v11 = (unsigned int)ProfileMetadata;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 101, &WPP_bf5f8caf0c6b308512151c87984ca346_Traceguids, v11);
  }
  v12 = ProfileMetadata < 0;
  if ( ProfileMetadata > 0 )
  {
    ProfileMetadata = (unsigned __int16)ProfileMetadata | 0x80070000;
LABEL_15:
    v12 = ProfileMetadata < 0;
  }
  if ( v12 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x3A0,
      (int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpintsel.cpp",
      (const char *)(unsigned int)ProfileMetadata);
    v14 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v15 = 102;
LABEL_114:
      WPP_SF_d(v14[2], v15, &WPP_bf5f8caf0c6b308512151c87984ca346_Traceguids, (unsigned int)ProfileMetadata);
      goto LABEL_115;
    }
    goto LABEL_116;
  }
  ProfileMetadata = WlanQueryInterface(
                      phClientHandle,
                      a2,
                      wlan_intf_opcode_current_connection,
                      0,
                      (PDWORD)&pdwDataSize + 1,
                      &pMemory,
                      (PWLAN_OPCODE_VALUE_TYPE)&pdwDataSize);
  if ( !ProfileMetadata )
  {
    v14 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_31;
  }
  v14 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    if ( ProfileMetadata > 0 )
      v16 = (unsigned __int16)ProfileMetadata | 0x80070000;
    else
      v16 = (unsigned int)ProfileMetadata;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 103, &WPP_bf5f8caf0c6b308512151c87984ca346_Traceguids, v16);
    v14 = (PVOID *)WPP_GLOBAL_Control;
  }
  v17 = ProfileMetadata < 0;
  if ( ProfileMetadata > 0 )
  {
    ProfileMetadata = (unsigned __int16)ProfileMetadata | 0x80070000;
LABEL_31:
    v17 = ProfileMetadata < 0;
  }
  if ( v17 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x3AF,
      (int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpintsel.cpp",
      (const char *)(unsigned int)ProfileMetadata);
    v14 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v15 = 104;
      goto LABEL_114;
    }
    goto LABEL_116;
  }
  if ( !pMemory )
  {
    ProfileMetadata = -2147418113;
    if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 4) != 0 && *((_BYTE *)v14 + 25) >= 2u )
      WPP_SF_d(v14[2], 105, &WPP_bf5f8caf0c6b308512151c87984ca346_Traceguids, 2147549183LL);
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x3B7,
      (int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpintsel.cpp",
      (const char *)0x8000FFFFLL);
    v14 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v15 = 106;
      goto LABEL_114;
    }
    goto LABEL_116;
  }
  if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 4) != 0 && *((_BYTE *)v14 + 25) >= 5u )
  {
    WPP_SF_ddd(
      v14[2],
      107,
      &WPP_bf5f8caf0c6b308512151c87984ca346_Traceguids,
      *(unsigned int *)pMemory,
      *((_DWORD *)pMemory + 1),
      *((_DWORD *)pMemory + 144));
    v14 = (PVOID *)WPP_GLOBAL_Control;
  }
  v18 = pMemory;
  v19 = *(_DWORD *)pMemory == 1;
  *a3 = v19;
  if ( !v19 )
    goto LABEL_116;
  v20 = v18[144];
  v21 = v20 < *((_DWORD *)this + 3);
  *a4 = v20 >= *((_DWORD *)this + 3);
  if ( v21 )
    goto LABEL_116;
  ProfileMetadata = WlanGetProfileMetadata(a2, v18 + 2, 0, L"Dwell Stats", &v43, &v39);
  if ( !ProfileMetadata )
  {
    v14 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_61;
  }
  v14 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    if ( ProfileMetadata > 0 )
      v22 = (unsigned __int16)ProfileMetadata | 0x80070000;
    else
      v22 = (unsigned int)ProfileMetadata;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 108, &WPP_bf5f8caf0c6b308512151c87984ca346_Traceguids, v22);
    v14 = (PVOID *)WPP_GLOBAL_Control;
  }
  v23 = ProfileMetadata < 0;
  if ( ProfileMetadata > 0 )
  {
    ProfileMetadata = (unsigned __int16)ProfileMetadata | 0x80070000;
LABEL_61:
    v23 = ProfileMetadata < 0;
  }
  if ( v23 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x3D6,
      (int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpintsel.cpp",
      (const char *)(unsigned int)ProfileMetadata);
    v14 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v15 = 109;
      goto LABEL_114;
    }
    goto LABEL_116;
  }
  if ( v43 != 24 || !v39 )
  {
    ProfileMetadata = -2147418113;
    if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 4) != 0 && *((_BYTE *)v14 + 25) >= 3u )
      WPP_SF_d(v14[2], 110, &WPP_bf5f8caf0c6b308512151c87984ca346_Traceguids, 2147549183LL);
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x3DE,
      (int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpintsel.cpp",
      (const char *)0x8000FFFFLL);
    v14 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v15 = 111;
      goto LABEL_114;
    }
    goto LABEL_116;
  }
  v24 = *((float *)v39 + 4);
  if ( (float)*((int *)this + 5) >= v24 || v24 <= 0.0 )
  {
    *v9 = 0;
    goto LABEL_116;
  }
  v25 = *((float *)v39 + 5) / v24;
  v26 = (float)*((int *)this + 4);
  *v9 = v25 >= v26;
  if ( v25 < v26 )
    goto LABEL_116;
  v43 = 0;
  v27 = WlanGetProfileMetadata(a2, (char *)pMemory + 8, 0, L"Connection Type", &v43, &v40);
  ProfileMetadata = v27;
  if ( !v27 )
  {
    v28 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_83;
  }
  v28 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    if ( v27 > 0 )
      v29 = (unsigned __int16)v27 | 0x80070000;
    else
      v29 = (unsigned int)v27;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 112, &WPP_bf5f8caf0c6b308512151c87984ca346_Traceguids, v29);
    v28 = (PVOID *)WPP_GLOBAL_Control;
  }
  v30 = ProfileMetadata < 0;
  if ( ProfileMetadata > 0 )
  {
    ProfileMetadata = (unsigned __int16)ProfileMetadata | 0x80070000;
LABEL_83:
    v30 = ProfileMetadata < 0;
  }
  if ( v30 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x404,
      (int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpintsel.cpp",
      (const char *)(unsigned int)ProfileMetadata);
    v14 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v15 = 113;
      goto LABEL_114;
    }
  }
  else
  {
    if ( v43 == 4 && v40 )
    {
      if ( (unsigned int)IsUserProfileType(*(unsigned __int8 *)v40) )
      {
        if ( v14 == &WPP_GLOBAL_Control || (*((_BYTE *)v14 + 28) & 4) == 0 || *((_BYTE *)v14 + 25) < 5u )
          goto LABEL_116;
        v32 = 117;
      }
      else
      {
        *v9 = 0;
        if ( v14 == &WPP_GLOBAL_Control || (*((_BYTE *)v14 + 28) & 4) == 0 || *((_BYTE *)v14 + 25) < 5u )
          goto LABEL_116;
        v32 = 116;
      }
      WPP_SF_d(v14[2], v32, &WPP_bf5f8caf0c6b308512151c87984ca346_Traceguids, v31);
LABEL_115:
      v14 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_116;
    }
    ProfileMetadata = -2147418113;
    if ( v28 != &WPP_GLOBAL_Control && (*((_BYTE *)v28 + 28) & 4) != 0 && *((_BYTE *)v28 + 25) >= 3u )
      WPP_SF_d(v28[2], 114, &WPP_bf5f8caf0c6b308512151c87984ca346_Traceguids, 2147549183LL);
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x40C,
      (int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpintsel.cpp",
      (const char *)0x8000FFFFLL);
    v14 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v15 = 115;
      goto LABEL_114;
    }
  }
LABEL_116:
  v33 = pMemory;
  if ( pMemory )
  {
    WlanFreeMemory(pMemory);
    v14 = (PVOID *)WPP_GLOBAL_Control;
    pMemory = 0;
  }
  if ( phClientHandle != (void *)-1LL )
  {
    WlanCloseHandle(phClientHandle, 0);
    v14 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v39 )
  {
    WlanFreeMemory(v39);
    v14 = (PVOID *)WPP_GLOBAL_Control;
    v39 = 0;
  }
  if ( v40 )
  {
    WlanFreeMemory(v40);
    v14 = (PVOID *)WPP_GLOBAL_Control;
    v40 = 0;
  }
  if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 4) != 0 && *((_BYTE *)v14 + 25) >= 6u )
  {
    LOBYTE(pWlanOpcodeValueType) = *a4;
    LOBYTE(ppData) = *a3;
    WPP_SF__guid_dccc(v14[2], v13, v33, a2, ProfileMetadata, ppData, pWlanOpcodeValueType, *v9, pdwDataSize);
  }
  return (unsigned int)ProfileMetadata;
}

```

## disassembly

```asm
0x180048b24  mov     [rsp-38h+arg_0], rbx
0x180048b29  push    rbp
0x180048b2a  push    rsi
0x180048b2b  push    rdi
0x180048b2c  push    r12
0x180048b2e  push    r13
0x180048b30  push    r14
0x180048b32  push    r15
0x180048b34  mov     rbp, rsp
0x180048b37  sub     rsp, 70h
0x180048b3b  mov     r15, r9
0x180048b3e  mov     r12, r8
0x180048b41  mov     r14, rdx
0x180048b44  mov     rdi, rcx
0x180048b47  mov     rcx, cs:WPP_GLOBAL_Control
0x180048b4e  lea     rax, WPP_GLOBAL_Control
0x180048b55  cmp     rcx, rax
0x180048b58  jz      short loc_180048B7B
0x180048b5a  test    byte ptr [rcx+1Ch], 4
0x180048b5e  jz      short loc_180048B7B
0x180048b60  cmp     byte ptr [rcx+19h], 6
0x180048b64  jb      short loc_180048B7B
0x180048b66  mov     rcx, [rcx+10h]
0x180048b6a  lea     r8, WPP_bf5f8caf0c6b308512151c87984ca346_Traceguids
0x180048b71  mov     edx, 64h ; 'd'
0x180048b76  call    WPP_SF_
0x180048b7b  mov     rsi, [rbp+arg_20]
0x180048b7f  lea     r9, [rbp+phClientHandle]; phClientHandle
0x180048b83  xor     r13d, r13d
0x180048b86  mov     [rbp+phClientHandle], 0FFFFFFFFFFFFFFFFh
0x180048b8e  xor     edx, edx; pReserved
0x180048b90  mov     [rbp+pdwNegotiatedVersion], r13d
0x180048b94  lea     r8, [rbp+pdwNegotiatedVersion]; pdwNegotiatedVersion
0x180048b98  mov     [rbp+pMemory], r13
0x180048b9c  mov     [rbp+var_2C], 25Ch
0x180048ba3  mov     [rbp+var_30], 3
0x180048baa  lea     ecx, [rdx+2]; dwClientVersion
0x180048bad  mov     [rbp+arg_10], r13d
0x180048bb1  mov     [rbp+var_20], r13
0x180048bb5  mov     [rbp+var_18], r13
0x180048bb9  mov     [r12], r13b
0x180048bbd  mov     [r15], r13b
0x180048bc0  mov     [rsi], r13b
0x180048bc3  call    cs:__imp_WlanOpenHandle
0x180048bc9  mov     ebx, eax
0x180048bcb  test    eax, eax
0x180048bcd  jz      short loc_180048C24
0x180048bcf  mov     rcx, cs:WPP_GLOBAL_Control
0x180048bd6  lea     rax, WPP_GLOBAL_Control
0x180048bdd  cmp     rcx, rax
0x180048be0  jz      short loc_180048C17
0x180048be2  test    byte ptr [rcx+1Ch], 4
0x180048be6  jz      short loc_180048C17
0x180048be8  cmp     byte ptr [rcx+19h], 2
0x180048bec  jb      short loc_180048C17
0x180048bee  test    ebx, ebx
0x180048bf0  jg      short loc_180048BF7
0x180048bf2  mov     r9d, ebx
0x180048bf5  jmp     short loc_180048C02
0x180048bf7  movzx   r9d, bx
0x180048bfb  or      r9d, 80070000h
0x180048c02  mov     rcx, [rcx+10h]
0x180048c06  lea     r8, WPP_bf5f8caf0c6b308512151c87984ca346_Traceguids
0x180048c0d  mov     edx, 65h ; 'e'
0x180048c12  call    WPP_SF_d
0x180048c17  test    ebx, ebx
0x180048c19  jle     short loc_180048C26
0x180048c1b  movzx   ebx, bx
0x180048c1e  or      ebx, 80070000h
0x180048c24  test    ebx, ebx
0x180048c26  jns     short loc_180048C6C
0x180048c28  mov     rcx, [rbp+38h]; this
0x180048c2c  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180048c33  mov     r9d, ebx; char *
0x180048c36  mov     edx, 3A0h; void *
0x180048c3b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180048c40  mov     r10, cs:WPP_GLOBAL_Control
0x180048c47  lea     rdi, WPP_GLOBAL_Control
0x180048c4e  cmp     r10, rdi
0x180048c51  jz      loc_1800491D0
0x180048c57  test    byte ptr [r10+1Ch], 80h
0x180048c5c  jz      loc_1800491D0
0x180048c62  mov     edx, 66h ; 'f'
0x180048c67  jmp     loc_1800491B6
0x180048c6c  mov     rcx, [rbp+phClientHandle]; hClientHandle
0x180048c70  lea     rax, [rbp+var_30]
0x180048c74  mov     [rsp+70h+pWlanOpcodeValueType], rax; pWlanOpcodeValueType
0x180048c79  xor     r9d, r9d; pReserved
0x180048c7c  lea     rax, [rbp+pMemory]
0x180048c80  mov     rdx, r14; pInterfaceGuid
0x180048c83  mov     [rsp+70h+ppData], rax; ppData
0x180048c88  lea     rax, [rbp+var_2C]
0x180048c8c  mov     [rsp+70h+pdwDataSize], rax; int
0x180048c91  lea     r8d, [r9+7]; OpCode
0x180048c95  call    cs:__imp_WlanQueryInterface
0x180048c9b  mov     ebx, eax
0x180048c9d  test    eax, eax
0x180048c9f  jz      short loc_180048D01
0x180048ca1  mov     r10, cs:WPP_GLOBAL_Control
0x180048ca8  lea     rax, WPP_GLOBAL_Control
0x180048caf  cmp     r10, rax
0x180048cb2  jz      short loc_180048CF2
0x180048cb4  test    byte ptr [r10+1Ch], 4
0x180048cb9  jz      short loc_180048CF2
0x180048cbb  cmp     byte ptr [r10+19h], 2
0x180048cc0  jb      short loc_180048CF2
0x180048cc2  test    ebx, ebx
0x180048cc4  jg      short loc_180048CCB
0x180048cc6  mov     r9d, ebx
0x180048cc9  jmp     short loc_180048CD6
0x180048ccb  movzx   r9d, bx
0x180048ccf  or      r9d, 80070000h
0x180048cd6  mov     rcx, [r10+10h]
0x180048cda  lea     r8, WPP_bf5f8caf0c6b308512151c87984ca346_Traceguids
0x180048ce1  mov     edx, 67h ; 'g'
0x180048ce6  call    WPP_SF_d
0x180048ceb  mov     r10, cs:WPP_GLOBAL_Control
0x180048cf2  test    ebx, ebx
0x180048cf4  jle     short loc_180048D0A
0x180048cf6  movzx   ebx, bx
0x180048cf9  or      ebx, 80070000h
0x180048cff  jmp     short loc_180048D08
0x180048d01  mov     r10, cs:WPP_GLOBAL_Control
0x180048d08  test    ebx, ebx
0x180048d0a  jns     short loc_180048D50
0x180048d0c  mov     rcx, [rbp+38h]; this
0x180048d10  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180048d17  mov     r9d, ebx; char *
0x180048d1a  mov     edx, 3AFh; void *
0x180048d1f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180048d24  mov     r10, cs:WPP_GLOBAL_Control
0x180048d2b  lea     rax, WPP_GLOBAL_Control
0x180048d32  cmp     r10, rax
0x180048d35  jz      loc_1800491D0
0x180048d3b  test    byte ptr [r10+1Ch], 80h
0x180048d40  jz      loc_1800491D0
0x180048d46  mov     edx, 68h ; 'h'
0x180048d4b  jmp     loc_1800491B6
0x180048d50  cmp     [rbp+pMemory], r13
0x180048d54  jnz     short loc_180048DCB
0x180048d56  mov     r9d, 8000FFFFh
0x180048d5c  mov     ebx, r9d
0x180048d5f  lea     rdi, WPP_GLOBAL_Control
0x180048d66  cmp     r10, rdi
0x180048d69  jz      short loc_180048D8E
0x180048d6b  test    byte ptr [r10+1Ch], 4
0x180048d70  jz      short loc_180048D8E
0x180048d72  cmp     byte ptr [r10+19h], 2
0x180048d77  jb      short loc_180048D8E
0x180048d79  mov     rcx, [r10+10h]
0x180048d7d  lea     r8, WPP_bf5f8caf0c6b308512151c87984ca346_Traceguids
0x180048d84  mov     edx, 69h ; 'i'
0x180048d89  call    WPP_SF_d
0x180048d8e  mov     rcx, [rbp+38h]; this
0x180048d92  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180048d99  mov     r9d, ebx; char *
0x180048d9c  mov     edx, 3B7h; void *
0x180048da1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180048da6  mov     r10, cs:WPP_GLOBAL_Control
0x180048dad  cmp     r10, rdi
0x180048db0  jz      loc_1800491D0
0x180048db6  test    byte ptr [r10+1Ch], 80h
0x180048dbb  jz      loc_1800491D0
0x180048dc1  mov     edx, 6Ah ; 'j'
0x180048dc6  jmp     loc_1800491B6
0x180048dcb  lea     rax, WPP_GLOBAL_Control
0x180048dd2  cmp     r10, rax
0x180048dd5  jz      short loc_180048E1B
0x180048dd7  test    byte ptr [r10+1Ch], 4
0x180048ddc  jz      short loc_180048E1B
0x180048dde  cmp     byte ptr [r10+19h], 5
0x180048de3  jb      short loc_180048E1B
0x180048de5  mov     r8, [rbp+pMemory]
0x180048de9  mov     edx, 6Bh ; 'k'
0x180048dee  mov     rcx, [r10+10h]
0x180048df2  mov     eax, [r8+240h]
0x180048df9  mov     r9d, [r8]
0x180048dfc  mov     dword ptr [rsp+70h+ppData], eax
0x180048e00  mov     eax, [r8+4]
0x180048e04  lea     r8, WPP_bf5f8caf0c6b308512151c87984ca346_Traceguids
0x180048e0b  mov     dword ptr [rsp+70h+pdwDataSize], eax
0x180048e0f  call    WPP_SF_ddd
0x180048e14  mov     r10, cs:WPP_GLOBAL_Control
0x180048e1b  mov     r8, [rbp+pMemory]
0x180048e1f  cmp     dword ptr [r8], 1
0x180048e23  setz    al
0x180048e26  mov     [r12], al
0x180048e2a  jnz     loc_1800491D0
0x180048e30  mov     ecx, [r8+240h]
0x180048e37  cmp     ecx, [rdi+0Ch]
0x180048e3a  setnb   al
0x180048e3d  mov     [r15], al
0x180048e40  jb      loc_1800491D0
0x180048e46  lea     rax, [rbp+var_20]
0x180048e4a  mov     rcx, r14
0x180048e4d  mov     [rsp+70h+ppData], rax
0x180048e52  lea     rdx, [r8+8]
0x180048e56  lea     rax, [rbp+arg_10]
0x180048e5a  xor     r8d, r8d
0x180048e5d  lea     r9, aDwellStats; "Dwell Stats"
0x180048e64  mov     [rsp+70h+pdwDataSize], rax; int
0x180048e69  call    cs:__imp_WlanGetProfileMetadata
0x180048e6f  mov     ebx, eax
0x180048e71  test    eax, eax
0x180048e73  jz      short loc_180048ED5
0x180048e75  mov     r10, cs:WPP_GLOBAL_Control
0x180048e7c  lea     rax, WPP_GLOBAL_Control
0x180048e83  cmp     r10, rax
0x180048e86  jz      short loc_180048EC6
0x180048e88  test    byte ptr [r10+1Ch], 4
0x180048e8d  jz      short loc_180048EC6
0x180048e8f  cmp     byte ptr [r10+19h], 2
0x180048e94  jb      short loc_180048EC6
0x180048e96  test    ebx, ebx
0x180048e98  jg      short loc_180048E9F
0x180048e9a  mov     r9d, ebx
0x180048e9d  jmp     short loc_180048EAA
0x180048e9f  movzx   r9d, bx
0x180048ea3  or      r9d, 80070000h
0x180048eaa  mov     rcx, [r10+10h]
0x180048eae  lea     r8, WPP_bf5f8caf0c6b308512151c87984ca346_Traceguids
0x180048eb5  mov     edx, 6Ch ; 'l'
0x180048eba  call    WPP_SF_d
0x180048ebf  mov     r10, cs:WPP_GLOBAL_Control
0x180048ec6  test    ebx, ebx
0x180048ec8  jle     short loc_180048EDE
0x180048eca  movzx   ebx, bx
0x180048ecd  or      ebx, 80070000h
0x180048ed3  jmp     short loc_180048EDC
0x180048ed5  mov     r10, cs:WPP_GLOBAL_Control
0x180048edc  test    ebx, ebx
0x180048ede  jns     short loc_180048F24
0x180048ee0  mov     rcx, [rbp+38h]; this
0x180048ee4  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180048eeb  mov     r9d, ebx; char *
0x180048eee  mov     edx, 3D6h; void *
0x180048ef3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180048ef8  mov     r10, cs:WPP_GLOBAL_Control
0x180048eff  lea     rax, WPP_GLOBAL_Control
0x180048f06  cmp     r10, rax
0x180048f09  jz      loc_1800491D0
0x180048f0f  test    byte ptr [r10+1Ch], 80h
0x180048f14  jz      loc_1800491D0
0x180048f1a  mov     edx, 6Dh ; 'm'
0x180048f1f  jmp     loc_1800491B6
0x180048f24  cmp     [rbp+arg_10], 18h
0x180048f28  jnz     loc_18004914E
0x180048f2e  mov     rcx, [rbp+var_20]
0x180048f32  test    rcx, rcx
0x180048f35  jz      loc_18004914E
0x180048f3b  movd    xmm0, dword ptr [rdi+14h]
0x180048f40  movss   xmm2, dword ptr [rcx+10h]
0x180048f45  cvtdq2ps xmm0, xmm0
0x180048f48  comiss  xmm0, xmm2
0x180048f4b  jb      short loc_180048F55
0x180048f4d  mov     [rsi], r13b
0x180048f50  jmp     loc_1800491D0
0x180048f55  comiss  xmm2, cs:__real@00000000
0x180048f5c  jbe     short loc_180048F4D
0x180048f5e  movss   xmm1, dword ptr [rcx+14h]
0x180048f63  movd    xmm0, dword ptr [rdi+10h]
0x180048f68  divss   xmm1, xmm2
0x180048f6c  cvtdq2ps xmm0, xmm0
0x180048f6f  comiss  xmm1, xmm0
0x180048f72  setnb   al
0x180048f75  mov     [rsi], al
0x180048f77  test    al, al
0x180048f79  jz      loc_1800491D0
0x180048f7f  mov     rdx, [rbp+pMemory]
0x180048f83  lea     rax, [rbp+var_18]
0x180048f87  mov     [rsp+70h+ppData], rax
0x180048f8c  lea     r9, aConnectionType; "Connection Type"
0x180048f93  lea     rax, [rbp+arg_10]
0x180048f97  mov     [rbp+arg_10], r13d
0x180048f9b  add     rdx, 8
0x180048f9f  mov     [rsp+70h+pdwDataSize], rax; int
0x180048fa4  xor     r8d, r8d
0x180048fa7  mov     rcx, r14
0x180048faa  call    cs:__imp_WlanGetProfileMetadata
0x180048fb0  mov     ebx, eax
0x180048fb2  test    eax, eax
0x180048fb4  jz      short loc_180049016
0x180048fb6  mov     r10, cs:WPP_GLOBAL_Control
0x180048fbd  lea     rdi, WPP_GLOBAL_Control
0x180048fc4  cmp     r10, rdi
0x180048fc7  jz      short loc_180049007
0x180048fc9  test    byte ptr [r10+1Ch], 4
0x180048fce  jz      short loc_180049007
0x180048fd0  cmp     byte ptr [r10+19h], 2
0x180048fd5  jb      short loc_180049007
0x180048fd7  test    eax, eax
0x180048fd9  jg      short loc_180048FE0
0x180048fdb  mov     r9d, eax
0x180048fde  jmp     short loc_180048FEB
0x180048fe0  movzx   r9d, bx
0x180048fe4  or      r9d, 80070000h
0x180048feb  mov     rcx, [r10+10h]
0x180048fef  lea     r8, WPP_bf5f8caf0c6b308512151c87984ca346_Traceguids
0x180048ff6  mov     edx, 70h ; 'p'
0x180048ffb  call    WPP_SF_d
  ... truncated ...
```
