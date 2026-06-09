# VPNIKEProtocolEngine::RoamClientConnectionsToBestCostInterface(void)

- ea: `0x180006738`
- end: `0x180006d7c`
- name: `?RoamClientConnectionsToBestCostInterface@VPNIKEProtocolEngine@@QEAAXXZ`
- size: `1604`
- prototype: `void __fastcall(VPNIKEProtocolEngine *__hidden this)`
- caller_count: `2`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x180008050`
- `0x180057c30`

## callees

- `0x180006738`
- `0x180007590`
- `0x180007794`
- `0x1800077bc`
- `0x180007894`
- `0x180007988`
- `0x180007a4c`
- `0x180007aa4`
- `0x180008fec`
- `0x18001e0b0`
- `0x18005d9ac`
- `0x180066b00`
- `0x180066c0c`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006d1b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006d1b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006d0d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006d0d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800068f9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006bb4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800068f9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006bb4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000690e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006bda`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000690e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006bda`

## string_xrefs

- `0x1800069c5`: `Connection %p already using best cost interface %d. Skipping.`

## pseudocode

```c
void __fastcall VPNIKEProtocolEngine::RoamClientConnectionsToBestCostInterface(VPNIKEProtocolEngine *this)
{
  VPNIKEProtocolEngine *v1; // r13
  PVOID *v2; // r10
  __int64 i; // r14
  __int64 v4; // rdi
  NET_LUID *v5; // rbx
  NET_IFINDEX v6; // r15d
  char v7; // si
  __int64 v8; // rdx
  __int64 v9; // r8
  unsigned int BestCostInterfaceIndex; // eax
  __int64 v11; // rdx
  __int64 v12; // r8
  unsigned int v13; // ebx
  unsigned int IPv4AddressFromIndex; // eax
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r9
  PVOID *v18; // rcx
  __int64 v19; // rdx
  unsigned int IPv6AddressFromIndex; // eax
  __int64 v21; // rdx
  const wchar_t *v22; // rdx
  __int64 v23; // rdi
  void *v24; // rbx
  HANDLE ProcessHeap; // rax
  int v26; // [rsp+38h] [rbp-C8h]
  ULONG v27; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v28; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v29; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID lpMem; // [rsp+50h] [rbp-B0h] BYREF
  tagRASTUNNELENDPOINT v31; // [rsp+58h] [rbp-A8h] BYREF
  int v32; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v33[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  v1 = VpnIkeProtocolEngine;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 89, &WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids);
  }
  lpMem = 0;
  v32 = 0;
  v29 = 0;
  memset_0(v33, 0, sizeof(v33));
  LOBYTE(v28) = byte_1800AA941 & 8;
  if ( (byte_1800AA941 & 8) != 0 )
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasVpnIkeTraceInfo,
      L"Entering RoamClientConnectionsToBestCostInterface.");
  (*(void (__fastcall **)(_QWORD, LPVOID *, unsigned int *))(**((_QWORD **)v1 + 1) + 64LL))(
    *((_QWORD *)v1 + 1),
    &lpMem,
    &v29);
  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, &WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids, v29);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= v29 )
      goto LABEL_84;
    if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 1) != 0 && *((_BYTE *)v2 + 25) >= 5u )
    {
      WPP_SF_d(v2[2], 91, &WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids, (unsigned int)i);
      v2 = (PVOID *)WPP_GLOBAL_Control;
    }
    v27 = 0;
    v28 = 0;
    memset(&v31, 0, sizeof(v31));
    v4 = *((_QWORD *)lpMem + i);
    if ( *(_DWORD *)(*(_QWORD *)(v4 + 112) + 40LL) != 1 )
    {
      if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 1) != 0 && *((_BYTE *)v2 + 25) >= 5u )
      {
        WPP_SF_d(v2[2], 92, &WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids, (unsigned int)i);
LABEL_66:
        v2 = (PVOID *)WPP_GLOBAL_Control;
        continue;
      }
      continue;
    }
    EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 160));
    v5 = *(NET_LUID **)(v4 + 32);
    v6 = *(_DWORD *)(v4 + 108);
    v7 = *(_BYTE *)(v4 + 16);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v4 + 160));
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      LOBYTE(v26) = v7;
      WPP_SF_dqddc(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, v9, (unsigned int)i, v4, v5[6].Value, v6, v26);
    }
    BestCostInterfaceIndex = GetBestCostInterfaceIndex(v6, v5 + 6, &v27);
    v13 = BestCostInterfaceIndex;
    if ( BestCostInterfaceIndex )
      break;
    if ( v6 != v27 )
    {
      if ( v7 )
      {
        IPv4AddressFromIndex = GetIPv4AddressFromIndex(v27, &v31.ipv4, &v28);
        if ( IPv4AddressFromIndex )
        {
          v18 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v19 = 96;
            goto LABEL_46;
          }
          goto LABEL_47;
        }
LABEL_58:
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_qddd(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, v16, v4, i, v6, v27);
        }
        if ( (byte_1800AA941 & 4) != 0 )
        {
          LOWORD(v32) = 0;
          FormatRRASErrorString(&v32, L"Roaming connection %p using interface %d.", v4, v6);
          if ( (byte_1800AA941 & 4) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v32);
        }
        EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 160));
        VPNIKEClientConnection::RoamToBestCostInterface(
          (VPNIKEClientConnection *)v4,
          v27,
          *((struct ThreadPoolHelper **)v1 + 3),
          &v31,
          v28);
        LeaveCriticalSection((LPCRITICAL_SECTION)(v4 + 160));
        goto LABEL_66;
      }
      IPv4AddressFromIndex = GetIPv6AddressFromIndex(v27, &v31.ipv4, &v28);
      if ( !IPv4AddressFromIndex )
        goto LABEL_58;
      v18 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v19 = 97;
LABEL_46:
        WPP_SF_d(v18[2], v19, &WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids, IPv4AddressFromIndex);
        v18 = (PVOID *)WPP_GLOBAL_Control;
      }
LABEL_47:
      if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 1) != 0 && *((_BYTE *)v18 + 25) >= 5u )
      {
        LOBYTE(v17) = v7;
        WPP_SF_c(v18[2], 98, &WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids, v17);
      }
      if ( v7 )
      {
        IPv6AddressFromIndex = GetIPv6AddressFromIndex(v27, &v31.ipv4, &v28);
        v13 = IPv6AddressFromIndex;
        if ( !IPv6AddressFromIndex )
          goto LABEL_58;
        v2 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v21 = 100;
LABEL_72:
          WPP_SF_d(v2[2], v21, &WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids, IPv6AddressFromIndex);
          v2 = (PVOID *)WPP_GLOBAL_Control;
        }
      }
      else
      {
        IPv6AddressFromIndex = GetIPv4AddressFromIndex(v27, &v31.ipv4, &v28);
        v13 = IPv6AddressFromIndex;
        if ( !IPv6AddressFromIndex )
          goto LABEL_58;
        v2 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v21 = 99;
          goto LABEL_72;
        }
      }
      if ( (byte_1800AA941 & 4) == 0 )
        goto LABEL_84;
      v22 = L"GetIPvXAddressFromIndex failed. Error: %!WINERROR!";
      goto LABEL_81;
    }
    v2 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, v12, v4, v6);
      v2 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( (byte_1800AA941 & 4) != 0 )
    {
      LOWORD(v32) = 0;
      FormatRRASErrorString(&v32, L"Connection %p already using best cost interface %d. Skipping.", v4, v6);
      if ( (byte_1800AA941 & 4) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v32);
      goto LABEL_66;
    }
  }
  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      94,
      &WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids,
      BestCostInterfaceIndex);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( (byte_1800AA941 & 4) != 0 )
  {
    v22 = L"GetBestCostInterfaceIndex failed: %d";
LABEL_81:
    LOWORD(v32) = 0;
    FormatRRASErrorString(&v32, v22, v13);
    if ( (byte_1800AA941 & 4) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v32);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_84:
  v23 = 0;
  if ( v29 )
  {
    do
    {
      BaseConnection::DeleteRef(*((BaseConnection **)lpMem + v23));
      *((_QWORD *)lpMem + v23) = 0;
      v23 = (unsigned int)(v23 + 1);
    }
    while ( (unsigned int)v23 < v29 );
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  v24 = lpMem;
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v24);
    v2 = (PVOID *)WPP_GLOBAL_Control;
    lpMem = 0;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 1) != 0 && *((_BYTE *)v2 + 25) >= 6u )
    WPP_SF_(v2[2], 102, &WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids);
}

```

## disassembly

```asm
0x180006738  push    rbp
0x18000673a  push    rbx
0x18000673b  push    rsi
0x18000673c  push    rdi
0x18000673d  push    r12
0x18000673f  push    r13
0x180006741  push    r14
0x180006743  push    r15
0x180006745  lea     rbp, [rsp-788h]
0x18000674d  sub     rsp, 888h
0x180006754  mov     rax, cs:__security_cookie
0x18000675b  xor     rax, rsp
0x18000675e  mov     [rbp+7C0h+var_50], rax
0x180006765  mov     r13, cs:?VpnIkeProtocolEngine@@3PEAVVPNIKEProtocolEngine@@EA; VPNIKEProtocolEngine * VpnIkeProtocolEngine
0x18000676c  mov     rcx, cs:WPP_GLOBAL_Control
0x180006773  lea     rsi, WPP_GLOBAL_Control
0x18000677a  cmp     rcx, rsi
0x18000677d  jz      short loc_1800067A0
0x18000677f  test    byte ptr [rcx+1Ch], 1
0x180006783  jz      short loc_1800067A0
0x180006785  cmp     byte ptr [rcx+19h], 6
0x180006789  jb      short loc_1800067A0
0x18000678b  mov     rcx, [rcx+10h]
0x18000678f  lea     r8, WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids
0x180006796  mov     edx, 59h ; 'Y'
0x18000679b  call    WPP_SF_
0x1800067a0  xor     eax, eax
0x1800067a2  mov     [rsp+8C0h+lpMem], 0
0x1800067ab  xor     edx, edx; Val
0x1800067ad  mov     [rsp+8C0h+var_850], eax
0x1800067b1  mov     r8d, 7FCh; Size
0x1800067b7  mov     [rsp+8C0h+var_878], 0
0x1800067bf  lea     rcx, [rsp+8C0h+var_84C]; void *
0x1800067c4  call    memset_0
0x1800067c9  mov     al, cs:byte_1800AA941
0x1800067cf  and     al, 8
0x1800067d1  mov     byte ptr [rsp+8C0h+var_87C], al
0x1800067d5  jz      short loc_1800067F1
0x1800067d7  lea     r8, aEnteringRoamcl; "Entering RoamClientConnectionsToBestCos"...
0x1800067de  lea     rdx, RasVpnIkeTraceInfo
0x1800067e5  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800067ec  call    McTemplateU0z_EventWriteTransfer
0x1800067f1  mov     rcx, [r13+8]
0x1800067f5  lea     r8, [rsp+8C0h+var_878]
0x1800067fa  lea     rdx, [rsp+8C0h+lpMem]
0x1800067ff  mov     rax, [rcx]
0x180006802  mov     rax, [rax+40h]
0x180006806  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000680b  mov     r10, cs:WPP_GLOBAL_Control
0x180006812  cmp     r10, rsi
0x180006815  jz      short loc_180006846
0x180006817  test    byte ptr [r10+1Ch], 1
0x18000681c  jz      short loc_180006846
0x18000681e  cmp     byte ptr [r10+19h], 5
0x180006823  jb      short loc_180006846
0x180006825  mov     r9d, [rsp+8C0h+var_878]
0x18000682a  lea     r8, WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids
0x180006831  mov     rcx, [r10+10h]
0x180006835  mov     edx, 5Ah ; 'Z'
0x18000683a  call    WPP_SF_d
0x18000683f  mov     r10, cs:WPP_GLOBAL_Control
0x180006846  xor     r14d, r14d
0x180006849  cmp     r14d, [rsp+8C0h+var_878]
0x18000684e  jnb     loc_180006CD1
0x180006854  cmp     r10, rsi
0x180006857  jz      short loc_180006886
0x180006859  test    byte ptr [r10+1Ch], 1
0x18000685e  jz      short loc_180006886
0x180006860  cmp     byte ptr [r10+19h], 5
0x180006865  jb      short loc_180006886
0x180006867  mov     rcx, [r10+10h]
0x18000686b  lea     r8, WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids
0x180006872  mov     edx, 5Bh ; '['
0x180006877  mov     r9d, r14d
0x18000687a  call    WPP_SF_d
0x18000687f  mov     r10, cs:WPP_GLOBAL_Control
0x180006886  xor     eax, eax
0x180006888  mov     [rsp+8C0h+var_880], 0
0x180006890  mov     dword ptr [rsp+8C0h+var_868.4+0Ch], eax
0x180006894  xorps   xmm0, xmm0
0x180006897  mov     [rsp+8C0h+var_87C], eax
0x18000689b  mov     rax, [rsp+8C0h+lpMem]
0x1800068a0  movups  xmmword ptr [rsp+8C0h+var_868.dwType], xmm0
0x1800068a5  mov     rdi, [rax+r14*8]
0x1800068a9  mov     rax, [rdi+70h]
0x1800068ad  cmp     dword ptr [rax+28h], 1
0x1800068b1  jz      short loc_1800068EF
0x1800068b3  cmp     r10, rsi
0x1800068b6  jz      loc_180006BE7
0x1800068bc  test    byte ptr [r10+1Ch], 1
0x1800068c1  jz      loc_180006BE7
0x1800068c7  cmp     byte ptr [r10+19h], 5
0x1800068cc  jb      loc_180006BE7
0x1800068d2  mov     rcx, [r10+10h]
0x1800068d6  lea     r8, WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids
0x1800068dd  mov     edx, 5Ch ; '\'
0x1800068e2  mov     r9d, r14d
0x1800068e5  call    WPP_SF_d
0x1800068ea  jmp     loc_180006BE0
0x1800068ef  lea     r12, [rdi+0A0h]
0x1800068f6  mov     rcx, r12; lpCriticalSection
0x1800068f9  call    cs:__imp_EnterCriticalSection
0x1800068ff  mov     rbx, [rdi+20h]
0x180006903  mov     rcx, r12; lpCriticalSection
0x180006906  mov     r15d, [rdi+6Ch]
0x18000690a  mov     sil, [rdi+10h]
0x18000690e  call    cs:__imp_LeaveCriticalSection
0x180006914  mov     rcx, cs:WPP_GLOBAL_Control
0x18000691b  lea     rax, WPP_GLOBAL_Control
0x180006922  cmp     rcx, rax
0x180006925  jz      short loc_180006955
0x180006927  test    byte ptr [rcx+1Ch], 1
0x18000692b  jz      short loc_180006955
0x18000692d  cmp     byte ptr [rcx+19h], 5
0x180006931  jb      short loc_180006955
0x180006933  mov     eax, [rbx+30h]
0x180006936  mov     r9d, r14d
0x180006939  mov     rcx, [rcx+10h]
0x18000693d  mov     [rsp+8C0h+var_888], sil
0x180006942  mov     [rsp+8C0h+var_890], r15d
0x180006947  mov     [rsp+8C0h+var_898], eax
0x18000694b  mov     qword ptr [rsp+8C0h+var_8A0], rdi
0x180006950  call    WPP_SF_dqddc
0x180006955  lea     r8, [rsp+8C0h+var_880]; PNET_IFINDEX
0x18000695a  mov     ecx, r15d; InterfaceIndex
0x18000695d  lea     rdx, [rbx+30h]; InterfaceLuid
0x180006961  call    GetBestCostInterfaceIndex
0x180006966  mov     ebx, eax
0x180006968  test    eax, eax
0x18000696a  jnz     loc_180006C45
0x180006970  mov     ecx, [rsp+8C0h+var_880]
0x180006974  cmp     r15d, ecx
0x180006977  jnz     loc_180006A0B
0x18000697d  mov     r10, cs:WPP_GLOBAL_Control
0x180006984  lea     rsi, WPP_GLOBAL_Control
0x18000698b  cmp     r10, rsi
0x18000698e  jz      short loc_1800069B6
0x180006990  test    byte ptr [r10+1Ch], 1
0x180006995  jz      short loc_1800069B6
0x180006997  cmp     byte ptr [r10+19h], 5
0x18000699c  jb      short loc_1800069B6
0x18000699e  mov     rcx, [r10+10h]
0x1800069a2  mov     r9, rdi
0x1800069a5  mov     [rsp+8C0h+var_8A0], r15d
0x1800069aa  call    WPP_SF_qd
0x1800069af  mov     r10, cs:WPP_GLOBAL_Control
0x1800069b6  test    cs:byte_1800AA941, 4
0x1800069bd  jz      loc_180006BE7
0x1800069c3  xor     eax, eax
0x1800069c5  lea     rdx, aConnectionPAlr; "Connection %p already using best cost i"...
0x1800069cc  mov     r9d, r15d
0x1800069cf  mov     word ptr [rsp+8C0h+var_850], ax
0x1800069d4  mov     r8, rdi
0x1800069d7  lea     rcx, [rsp+8C0h+var_850]
0x1800069dc  call    FormatRRASErrorString
0x1800069e1  test    cs:byte_1800AA941, 4
0x1800069e8  jz      loc_180006BE0
0x1800069ee  lea     r8, [rsp+8C0h+var_850]
0x1800069f3  lea     rdx, RasVpnIkeTraceError
0x1800069fa  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180006a01  call    McTemplateU0z_EventWriteTransfer
0x180006a06  jmp     loc_180006BE0
0x180006a0b  lea     r8, [rsp+8C0h+var_87C]
0x180006a10  lea     rdx, [rsp+8C0h+var_868.4]
0x180006a15  test    sil, sil
0x180006a18  jz      short loc_180006A4D
0x180006a1a  call    GetIPv4AddressFromIndex
0x180006a1f  test    eax, eax
0x180006a21  jz      loc_180006B2C
0x180006a27  mov     rcx, cs:WPP_GLOBAL_Control
0x180006a2e  lea     rdx, WPP_GLOBAL_Control
0x180006a35  cmp     rcx, rdx
0x180006a38  jz      short loc_180006A98
0x180006a3a  test    byte ptr [rcx+1Ch], 1
0x180006a3e  jz      short loc_180006A98
0x180006a40  cmp     byte ptr [rcx+19h], 2
0x180006a44  jb      short loc_180006A98
0x180006a46  mov     edx, 60h ; '`'
0x180006a4b  jmp     short loc_180006A7E
0x180006a4d  call    GetIPv6AddressFromIndex
0x180006a52  test    eax, eax
0x180006a54  jz      loc_180006B2C
0x180006a5a  mov     rcx, cs:WPP_GLOBAL_Control
0x180006a61  lea     rdx, WPP_GLOBAL_Control
0x180006a68  cmp     rcx, rdx
0x180006a6b  jz      short loc_180006A98
0x180006a6d  test    byte ptr [rcx+1Ch], 1
0x180006a71  jz      short loc_180006A98
0x180006a73  cmp     byte ptr [rcx+19h], 2
0x180006a77  jb      short loc_180006A98
0x180006a79  mov     edx, 61h ; 'a'
0x180006a7e  mov     rcx, [rcx+10h]
0x180006a82  lea     r8, WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids
0x180006a89  mov     r9d, eax
0x180006a8c  call    WPP_SF_d
0x180006a91  mov     rcx, cs:WPP_GLOBAL_Control
0x180006a98  lea     rax, WPP_GLOBAL_Control
0x180006a9f  cmp     rcx, rax
0x180006aa2  jz      short loc_180006AC8
0x180006aa4  test    byte ptr [rcx+1Ch], 1
0x180006aa8  jz      short loc_180006AC8
0x180006aaa  cmp     byte ptr [rcx+19h], 5
0x180006aae  jb      short loc_180006AC8
0x180006ab0  mov     rcx, [rcx+10h]
0x180006ab4  lea     r8, WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids
0x180006abb  mov     edx, 62h ; 'b'
0x180006ac0  mov     r9b, sil
0x180006ac3  call    WPP_SF_c
0x180006ac8  mov     ecx, [rsp+8C0h+var_880]
0x180006acc  lea     r8, [rsp+8C0h+var_87C]
0x180006ad1  lea     rdx, [rsp+8C0h+var_868.4]
0x180006ad6  test    sil, sil
0x180006ad9  jnz     short loc_180006B1D
0x180006adb  call    GetIPv4AddressFromIndex
0x180006ae0  mov     ebx, eax
0x180006ae2  test    eax, eax
0x180006ae4  jz      short loc_180006B2C
0x180006ae6  mov     r10, cs:WPP_GLOBAL_Control
0x180006aed  lea     rsi, WPP_GLOBAL_Control
0x180006af4  cmp     r10, rsi
0x180006af7  jz      loc_180006C2F
0x180006afd  test    byte ptr [r10+1Ch], 1
0x180006b02  jz      loc_180006C2F
0x180006b08  cmp     byte ptr [r10+19h], 2
0x180006b0d  jb      loc_180006C2F
0x180006b13  mov     edx, 63h ; 'c'
0x180006b18  jmp     loc_180006C15
0x180006b1d  call    GetIPv6AddressFromIndex
0x180006b22  mov     ebx, eax
0x180006b24  test    eax, eax
0x180006b26  jnz     loc_180006BEF
0x180006b2c  mov     rcx, cs:WPP_GLOBAL_Control
0x180006b33  lea     rsi, WPP_GLOBAL_Control
0x180006b3a  cmp     rcx, rsi
0x180006b3d  jz      short loc_180006B69
0x180006b3f  test    byte ptr [rcx+1Ch], 1
0x180006b43  jz      short loc_180006B69
0x180006b45  cmp     byte ptr [rcx+19h], 5
0x180006b49  jb      short loc_180006B69
0x180006b4b  mov     eax, [rsp+8C0h+var_880]
0x180006b4f  mov     r9, rdi
0x180006b52  mov     rcx, [rcx+10h]
0x180006b56  mov     [rsp+8C0h+var_890], eax
0x180006b5a  mov     [rsp+8C0h+var_898], r15d
0x180006b5f  mov     [rsp+8C0h+var_8A0], r14d
0x180006b64  call    WPP_SF_qddd
0x180006b69  test    cs:byte_1800AA941, 4
0x180006b70  jz      short loc_180006BB1
0x180006b72  xor     eax, eax
0x180006b74  lea     rdx, aRoamingConnect; "Roaming connection %p using interface %"...
0x180006b7b  mov     r9d, r15d
0x180006b7e  mov     word ptr [rsp+8C0h+var_850], ax
0x180006b83  mov     r8, rdi
0x180006b86  lea     rcx, [rsp+8C0h+var_850]
0x180006b8b  call    FormatRRASErrorString
0x180006b90  test    cs:byte_1800AA941, 4
0x180006b97  jz      short loc_180006BB1
0x180006b99  lea     r8, [rsp+8C0h+var_850]
0x180006b9e  lea     rdx, RasVpnIkeTraceError
0x180006ba5  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180006bac  call    McTemplateU0z_EventWriteTransfer
0x180006bb1  mov     rcx, r12; lpCriticalSection
0x180006bb4  call    cs:__imp_EnterCriticalSection
0x180006bba  mov     eax, [rsp+8C0h+var_87C]
0x180006bbe  lea     r9, [rsp+8C0h+var_868]; struct tagRASTUNNELENDPOINT *
0x180006bc3  mov     r8, [r13+18h]; struct ThreadPoolHelper *
0x180006bc7  mov     rcx, rdi; this
0x180006bca  mov     edx, [rsp+8C0h+var_880]; unsigned int
0x180006bce  mov     [rsp+8C0h+var_8A0], eax; unsigned int
0x180006bd2  call    ?RoamToBestCostInterface@VPNIKEClientConnection@@QEAAXKPEAVThreadPoolHelper@@PEAUtagRASTUNNELENDPOINT@@K@Z; VPNIKEClientConnection::RoamToBestCostInterface(ulong,ThreadPoolHelper *,tagRASTUNNELENDPOINT *,ulong)
0x180006bd7  mov     rcx, r12; lpCriticalSection
0x180006bda  call    cs:__imp_LeaveCriticalSection
0x180006be0  mov     r10, cs:WPP_GLOBAL_Control
0x180006be7  inc     r14d
0x180006bea  jmp     loc_180006849
0x180006bef  mov     r10, cs:WPP_GLOBAL_Control
0x180006bf6  lea     rsi, WPP_GLOBAL_Control
0x180006bfd  cmp     r10, rsi
0x180006c00  jz      short loc_180006C2F
0x180006c02  test    byte ptr [r10+1Ch], 1
0x180006c07  jz      short loc_180006C2F
0x180006c09  cmp     byte ptr [r10+19h], 2
0x180006c0e  jb      short loc_180006C2F
0x180006c10  mov     edx, 64h ; 'd'
0x180006c15  mov     rcx, [r10+10h]
0x180006c19  lea     r8, WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids
0x180006c20  mov     r9d, eax
0x180006c23  call    WPP_SF_d
0x180006c28  mov     r10, cs:WPP_GLOBAL_Control
0x180006c2f  test    cs:byte_1800AA941, 4
0x180006c36  jz      loc_180006CD1
0x180006c3c  lea     rdx, aGetipvxaddress_0; "GetIPvXAddressFromIndex failed. Error: "...
0x180006c43  jmp     short loc_180006C95
0x180006c45  mov     r10, cs:WPP_GLOBAL_Control
0x180006c4c  lea     rsi, WPP_GLOBAL_Control
0x180006c53  cmp     r10, rsi
0x180006c56  jz      short loc_180006C85
0x180006c58  test    byte ptr [r10+1Ch], 1
0x180006c5d  jz      short loc_180006C85
0x180006c5f  cmp     byte ptr [r10+19h], 2
  ... truncated ...
```
