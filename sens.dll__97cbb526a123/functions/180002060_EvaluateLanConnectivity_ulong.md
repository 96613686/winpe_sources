# EvaluateLanConnectivity(ulong *)

- ea: `0x180002060`
- end: `0x18000264a`
- name: `?EvaluateLanConnectivity@@YAHPEAK@Z`
- size: `1514`
- prototype: `__int64 __fastcall(NTSTATUS *Parameter)`
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x180001510`
- `0x180001590`

## callees

- `0x180002060`
- `0x180002650`
- `0x180002ba4`
- `0x1800030a0`
- `0x1800082b4`
- `0x180008300`
- `0x1800093b0`
- `0x18000a7a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800020ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000217e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800024ca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800020ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000217e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800024ca`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800020bc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000213c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000249a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800020bc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000213c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000249a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002083`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002595`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002083`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002595`
- `IPHLPAPI!FreeMibTable` at `0x1800022de`
- `IPHLPAPI!FreeMibTable` at `0x1800022de`
- `IPHLPAPI!GetIfTable2` at `0x1800020a3`
- `IPHLPAPI!GetIfTable2` at `0x1800020a3`

## pseudocode

```c
__int64 __fastcall EvaluateLanConnectivity(NTSTATUS *Parameter)
{
  __int64 v2; // rsi
  NTSTATUS IfTable2; // eax
  _DWORD *v4; // rdx
  PMIB_IF_TABLE2 v6; // rbx
  unsigned __int32 v7; // r12d
  int v8; // r14d
  unsigned int v9; // r15d
  _QWORD *v10; // r11
  unsigned __int64 v11; // rdi
  _QWORD *v12; // r10
  unsigned __int32 v13; // r13d
  PMIB_IF_TABLE2 v14; // r8
  ULONG v15; // ebx
  unsigned __int64 v16; // rsi
  IFTYPE Type; // ecx
  BOOL v18; // edi
  IF_OPER_STATUS OperStatus; // eax
  int v20; // eax
  ULONG64 TransmitLinkSpeed; // rcx
  int v22; // edx
  ULONG v23; // r8d
  _DWORD *v24; // rax
  DWORD v25; // eax
  PMIB_IF_TABLE2 Table; // [rsp+30h] [rbp-39h] BYREF
  DWORD TickCount; // [rsp+38h] [rbp-31h]
  char v28; // [rsp+3Ch] [rbp-2Dh] BYREF
  _OWORD v29[2]; // [rsp+40h] [rbp-29h] BYREF
  __int64 v30; // [rsp+60h] [rbp-9h]
  __int128 v31; // [rsp+70h] [rbp+7h] BYREF
  __int128 v32; // [rsp+80h] [rbp+17h]
  __int64 v33; // [rsp+90h] [rbp+27h]

  TickCount = GetTickCount();
  if ( Parameter )
    *Parameter = 1222;
  else
    Parameter = (NTSTATUS *)&v28;
  v2 = 0;
  Table = 0;
  IfTable2 = GetIfTable2(&Table);
  if ( IfTable2 )
  {
    *Parameter = IfTable2;
    gdwLANState = 0;
    EnterCriticalSection(&gSensLock);
    v4 = gpSensCache;
    if ( gpSensCache )
    {
      *((_DWORD *)gpSensCache + 5) = gdwLANState;
      v4[6] = gdwLastLANTime;
      UpdateSensNetworkCache();
    }
    LeaveCriticalSection(&gSensLock);
    return 0;
  }
  v6 = Table;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  *Parameter = 0;
  EnterCriticalSection(&gSensLock);
  v10 = WPP_GLOBAL_Control;
  v11 = 0;
  do
  {
    if ( *(_DWORD *)((char *)&gIfState + v11) )
    {
      if ( !v6->NumEntries )
        goto LABEL_56;
      v22 = 0;
      v23 = 0;
      do
      {
        if ( v6->Table[v23].InterfaceIndex == *(_DWORD *)((char *)&gIfState + v11 + 4) )
          v22 = 1;
        ++v23;
      }
      while ( v23 < v6->NumEntries );
      v10 = WPP_GLOBAL_Control;
      if ( !v22 )
      {
LABEL_56:
        if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 1) != 0 && *((_BYTE *)v10 + 25) >= 2u )
        {
          WPP_SF_d(v10[2], 36, WPP_c7cc13fe6dc03834cd55671891cfefc7_Traceguids, (unsigned int)dword_1800117F4[v11 / 4]);
          v10 = WPP_GLOBAL_Control;
        }
        *(_OWORD *)((char *)&gIfState + v11) = 0;
        *(_OWORD *)((char *)&gIfState + v11 + 16) = 0;
        *(struct _IF_STATE near **)((char *)&gIfState + v11 + 32) = 0;
      }
    }
    ++v2;
    v11 += 40LL;
  }
  while ( v2 != 5 );
  LeaveCriticalSection(&gSensLock);
  v31 = 0;
  v33 = 0;
  v32 = 0;
  v12 = WPP_GLOBAL_Control;
  v13 = TickCount;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      WPP_c7cc13fe6dc03834cd55671891cfefc7_Traceguids,
      Table->NumEntries);
    v12 = WPP_GLOBAL_Control;
  }
  v14 = Table;
  v15 = 0;
  if ( Table->NumEntries )
  {
    do
    {
      v16 = v15;
      Type = v14->Table[v16].Type;
      if ( ((Type - 23) & 0xFFFFFFFA) != 0 || Type == 27 )
      {
        v18 = 0;
        if ( !v14->Table[v16].InUcastPkts )
          v18 = v14->Table[v16].OutUcastPkts == 0;
        OperStatus = v14->Table[v16].OperStatus;
        if ( OperStatus != IfOperStatusUp )
        {
          if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 1) != 0 && *((_BYTE *)v12 + 25) >= 5u )
          {
            WPP_SF_dd(
              v12[2],
              14,
              WPP_c7cc13fe6dc03834cd55671891cfefc7_Traceguids,
              v14->Table[v16].InterfaceIndex,
              OperStatus);
            v14 = Table;
          }
          v18 = 1;
        }
        DWORD1(v31) = v14->Table[v16].InterfaceIndex;
        DWORD2(v31) = v14->Table[v16].InUcastPkts;
        HIDWORD(v31) = v14->Table[v16].OutUcastPkts;
        LODWORD(v32) = v14->Table[v16].InNUcastPkts;
        DWORD1(v32) = v14->Table[v16].OutNUcastPkts;
        DWORD2(v32) = v14->Table[v16].InErrors;
        HIDWORD(v32) = v14->Table[v16].OutErrors;
        LODWORD(v33) = v14->Table[v16].InDiscards;
        HIDWORD(v33) = v14->Table[v16].OutDiscards;
        v29[0] = v31;
        v30 = v33;
        v29[1] = v32;
        v20 = HasIfStateChanged(v29, v18);
        v14 = Table;
        v12 = WPP_GLOBAL_Control;
        if ( v20 == 1 )
        {
          TransmitLinkSpeed = Table->Table[v16].TransmitLinkSpeed;
          v7 = 1;
          if ( TransmitLinkSpeed <= v9 )
            LODWORD(TransmitLinkSpeed) = v9;
          v9 = TransmitLinkSpeed;
        }
        else if ( !v18 )
        {
          v8 = 1;
        }
      }
      ++v15;
    }
    while ( v15 < v14->NumEntries );
    v13 = TickCount;
  }
  FreeMibTable(v14);
  if ( v8 != 1 )
  {
    if ( !v7 )
    {
LABEL_27:
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_c7cc13fe6dc03834cd55671891cfefc7_Traceguids);
      }
      v13 = 0;
LABEL_30:
      _InterlockedExchange(&gdwLastLANTime, v13);
      if ( _InterlockedExchange(&gdwLANState, v7) != v7 )
      {
        LODWORD(v31) = 0;
        *((_QWORD *)&v31 + 1) = 0x100000010LL;
        LODWORD(v32) = v9;
        DWORD1(v32) = v9;
        DWORD1(v31) = v7;
        *((_QWORD *)&v32 + 1) = L"LAN Connection";
        EnterCriticalSection(&gSensLock);
        v24 = gpSensCache;
        if ( gpSensCache )
        {
          *((_DWORD *)gpSensCache + 5) = gdwLANState;
          v24[6] = gdwLastLANTime;
          UpdateSensNetworkCache();
        }
        LeaveCriticalSection(&gSensLock);
        SensFireEvent(&v31);
      }
      return v7;
    }
LABEL_46:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_c7cc13fe6dc03834cd55671891cfefc7_Traceguids, v13 / 0x3E8);
    }
    goto LABEL_30;
  }
  if ( v7 )
    goto LABEL_46;
  v25 = GetTickCount();
  if ( v25 - gdwLastLANTime > 0x2BF20 || !gdwLastLANTime )
    goto LABEL_27;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      15,
      WPP_c7cc13fe6dc03834cd55671891cfefc7_Traceguids,
      v25 / 0x3E8,
      gdwLastLANTime / 1000);
  }
  return 1;
}

```

## disassembly

```asm
0x180002060  push    rbp
0x180002062  push    rsi
0x180002063  push    rdi
0x180002064  push    r13
0x180002066  lea     rbp, [rsp-3Fh]
0x18000206b  sub     rsp, 0A8h
0x180002072  mov     rax, cs:__security_cookie
0x180002079  xor     rax, rsp
0x18000207c  mov     [rbp+57h+var_28], rax
0x180002080  mov     rdi, rcx
0x180002083  call    cs:__imp_GetTickCount
0x180002089  mov     [rbp+57h+var_88], eax
0x18000208c  test    rdi, rdi
0x18000208f  jnz     loc_180002383
0x180002095  lea     rdi, [rbp+57h+var_84]
0x180002099  xor     esi, esi
0x18000209b  lea     rcx, [rbp+57h+Table]; Table
0x18000209f  mov     [rbp+57h+Table], rsi
0x1800020a3  call    cs:__imp_GetIfTable2
0x1800020a9  lea     rcx, ?gSensLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800020b0  test    eax, eax
0x1800020b2  jz      short loc_18000210D
0x1800020b4  mov     [rdi], eax
0x1800020b6  mov     cs:?gdwLANState@@3JA, esi; long gdwLANState
0x1800020bc  call    cs:__imp_EnterCriticalSection
0x1800020c2  mov     rdx, cs:?gpSensCache@@3PEAU_SENS_CACHE@@EA; _SENS_CACHE * gpSensCache
0x1800020c9  test    rdx, rdx
0x1800020cc  jz      short loc_1800020E5
0x1800020ce  mov     eax, cs:?gdwLANState@@3JA; long gdwLANState
0x1800020d4  mov     [rdx+14h], eax
0x1800020d7  mov     eax, cs:?gdwLastLANTime@@3JA; long gdwLastLANTime
0x1800020dd  mov     [rdx+18h], eax
0x1800020e0  call    ?UpdateSensNetworkCache@@YAXXZ; UpdateSensNetworkCache(void)
0x1800020e5  lea     rcx, ?gSensLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800020ec  call    cs:__imp_LeaveCriticalSection
0x1800020f2  xor     eax, eax
0x1800020f4  mov     rcx, [rbp+57h+var_28]
0x1800020f8  xor     rcx, rsp; StackCookie
0x1800020fb  call    __security_check_cookie
0x180002100  add     rsp, 0A8h
0x180002107  pop     r13
0x180002109  pop     rdi
0x18000210a  pop     rsi
0x18000210b  pop     rbp
0x18000210c  retn
0x18000210d  mov     [rsp+0C0h+arg_8], rbx
0x180002115  mov     rbx, [rbp+57h+Table]
0x180002119  mov     [rsp+0C0h+arg_10], r12
0x180002121  mov     r12d, esi
0x180002124  mov     [rsp+0C0h+arg_18], r14
0x18000212c  mov     r14d, esi
0x18000212f  mov     [rsp+0C0h+var_20], r15
0x180002137  mov     r15d, esi
0x18000213a  mov     [rdi], esi
0x18000213c  call    cs:__imp_EnterCriticalSection
0x180002142  mov     r11, cs:WPP_GLOBAL_Control
0x180002149  lea     rcx, ?gIfState@@3PAU_IF_STATE@@A; _IF_STATE near * gIfState
0x180002150  xor     edi, edi
0x180002152  lea     r13, WPP_GLOBAL_Control
0x180002159  nop     dword ptr [rax+00000000h]
0x180002160  cmp     [rdi+rcx], r12d
0x180002164  jnz     loc_18000238E
0x18000216a  inc     rsi
0x18000216d  add     rdi, 28h ; '('
0x180002171  cmp     rsi, 5
0x180002175  jnz     short loc_180002160
0x180002177  lea     rcx, ?gSensLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000217e  call    cs:__imp_LeaveCriticalSection
0x180002184  xorps   xmm0, xmm0
0x180002187  xor     eax, eax
0x180002189  movups  [rbp+57h+var_50], xmm0
0x18000218d  mov     [rbp+57h+var_30], rax
0x180002191  movups  [rbp+57h+var_40], xmm0
0x180002195  mov     r10, cs:WPP_GLOBAL_Control
0x18000219c  lea     rdx, WPP_GLOBAL_Control
0x1800021a3  mov     r13d, [rbp+57h+var_88]
0x1800021a7  cmp     r10, rdx
0x1800021aa  jz      short loc_1800021B7
0x1800021ac  test    byte ptr [r10+1Ch], 1
0x1800021b1  jnz     loc_180002552
0x1800021b7  mov     r8, [rbp+57h+Table]
0x1800021bb  xor     ebx, ebx
0x1800021bd  cmp     [r8], ebx
0x1800021c0  jbe     loc_1800022DB
0x1800021c6  mov     r13d, 1
0x1800021cc  nop     dword ptr [rax+00h]
0x1800021d0  mov     eax, ebx
0x1800021d2  imul    rsi, rax, 548h
0x1800021d9  mov     ecx, [rsi+r8+470h]
0x1800021e1  lea     eax, [rcx-17h]
0x1800021e4  test    eax, 0FFFFFFFAh
0x1800021e9  jz      loc_180002358
0x1800021ef  xor     edi, edi
0x1800021f1  cmp     [rsi+r8+4C8h], rdi
0x1800021f9  jnz     short loc_180002207
0x1800021fb  cmp     [rsi+r8+510h], rdi
0x180002203  cmovz   edi, r13d
0x180002207  mov     eax, [rsi+r8+48Ch]
0x18000220f  cmp     eax, r13d
0x180002212  jz      short loc_180002226
0x180002214  cmp     r10, rdx
0x180002217  jz      short loc_180002223
0x180002219  test    [r10+1Ch], r13b
0x18000221d  jnz     loc_1800024DE
0x180002223  mov     edi, r13d
0x180002226  mov     eax, [rsi+r8+10h]
0x18000222b  lea     rcx, [rbp+57h+var_80]
0x18000222f  mov     dword ptr [rbp+57h+var_50+4], eax
0x180002232  mov     edx, edi
0x180002234  mov     eax, [rsi+r8+4C8h]
0x18000223c  mov     dword ptr [rbp+57h+var_50+8], eax
0x18000223f  mov     eax, [rsi+r8+510h]
0x180002247  mov     dword ptr [rbp+57h+var_50+0Ch], eax
0x18000224a  mov     eax, [rsi+r8+4D0h]
0x180002252  movups  xmm0, [rbp+57h+var_50]
0x180002256  mov     dword ptr [rbp+57h+var_40], eax
0x180002259  mov     eax, [rsi+r8+518h]
0x180002261  mov     dword ptr [rbp+57h+var_40+4], eax
0x180002264  mov     eax, [rsi+r8+4E0h]
0x18000226c  mov     dword ptr [rbp+57h+var_40+8], eax
0x18000226f  mov     eax, [rsi+r8+528h]
0x180002277  mov     dword ptr [rbp+57h+var_40+0Ch], eax
0x18000227a  mov     eax, [rsi+r8+4D8h]
0x180002282  movups  xmm1, [rbp+57h+var_40]
0x180002286  mov     dword ptr [rbp+57h+var_30], eax
0x180002289  mov     eax, [rsi+r8+520h]
0x180002291  mov     dword ptr [rbp+57h+var_30+4], eax
0x180002294  movaps  [rbp+57h+var_80], xmm0
0x180002298  movsd   xmm0, [rbp+57h+var_30]
0x18000229d  movsd   [rbp+57h+var_60], xmm0
0x1800022a2  movaps  [rbp+57h+var_70], xmm1
0x1800022a6  call    ?HasIfStateChanged@@YAHU_IF_STATE@@H@Z; HasIfStateChanged(_IF_STATE,int)
0x1800022ab  mov     r8, [rbp+57h+Table]
0x1800022af  lea     rdx, WPP_GLOBAL_Control
0x1800022b6  mov     r10, cs:WPP_GLOBAL_Control
0x1800022bd  cmp     eax, r13d
0x1800022c0  jz      loc_180002366
0x1800022c6  test    edi, edi
0x1800022c8  cmovz   r14d, r13d
0x1800022cc  inc     ebx
0x1800022ce  cmp     ebx, [r8]
0x1800022d1  jb      loc_1800021D0
0x1800022d7  mov     r13d, [rbp+57h+var_88]
0x1800022db  mov     rcx, r8; Memory
0x1800022de  call    cs:__imp_FreeMibTable
0x1800022e4  mov     rbx, [rsp+0C0h+arg_8]
0x1800022ec  cmp     r14d, 1
0x1800022f0  mov     r14, [rsp+0C0h+arg_18]
0x1800022f8  jz      loc_18000258C
0x1800022fe  test    r12d, r12d
0x180002301  jnz     loc_18000240C
0x180002307  mov     rcx, cs:WPP_GLOBAL_Control
0x18000230e  lea     rax, WPP_GLOBAL_Control
0x180002315  cmp     rcx, rax
0x180002318  jz      short loc_180002324
0x18000231a  test    byte ptr [rcx+1Ch], 1
0x18000231e  jnz     loc_180002626
0x180002324  xor     r13d, r13d
0x180002327  xchg    r13d, cs:?gdwLastLANTime@@3JA; long gdwLastLANTime
0x18000232e  mov     eax, r12d
0x180002331  xchg    eax, cs:?gdwLANState@@3JA; long gdwLANState
0x180002337  cmp     eax, r12d
0x18000233a  jnz     loc_180002460
0x180002340  mov     eax, r12d
0x180002343  mov     r12, [rsp+0C0h+arg_10]
0x18000234b  mov     r15, [rsp+0C0h+var_20]
0x180002353  jmp     loc_1800020F4
0x180002358  cmp     ecx, 1Bh
0x18000235b  jz      loc_1800021EF
0x180002361  jmp     loc_1800022CC
0x180002366  mov     rcx, [rsi+r8+4B0h]
0x18000236e  mov     r12d, r13d
0x180002371  mov     eax, r15d
0x180002374  cmp     rcx, rax
0x180002377  cmovbe  ecx, r15d
0x18000237b  mov     r15d, ecx
0x18000237e  jmp     loc_1800022CC
0x180002383  mov     dword ptr [rdi], 4C6h
0x180002389  jmp     loc_180002099
0x18000238e  mov     r9d, [rbx]
0x180002391  test    r9d, r9d
0x180002394  jz      short loc_1800023E1
0x180002396  mov     r10d, [rdi+rcx+4]
0x18000239b  xor     edx, edx
0x18000239d  xor     r8d, r8d
0x1800023a0  mov     r11d, 1
0x1800023a6  nop     word ptr [rax+rax+00000000h]
0x1800023b0  mov     eax, r8d
0x1800023b3  imul    rcx, rax, 548h
0x1800023ba  cmp     [rcx+rbx+10h], r10d
0x1800023bf  cmovz   edx, r11d
0x1800023c3  inc     r8d
0x1800023c6  cmp     r8d, r9d
0x1800023c9  jb      short loc_1800023B0
0x1800023cb  mov     r11, cs:WPP_GLOBAL_Control
0x1800023d2  lea     rcx, ?gIfState@@3PAU_IF_STATE@@A; _IF_STATE near * gIfState
0x1800023d9  test    edx, edx
0x1800023db  jnz     loc_18000216A
0x1800023e1  lea     rax, dword_1800117F4
0x1800023e8  mov     r9, rdi
0x1800023eb  cmp     r11, r13
0x1800023ee  jnz     loc_180002510
0x1800023f4  xorps   xmm0, xmm0
0x1800023f7  xor     eax, eax
0x1800023f9  movups  xmmword ptr [rdi+rcx], xmm0
0x1800023fd  movups  xmmword ptr [rdi+rcx+10h], xmm0
0x180002402  mov     [rdi+rcx+20h], rax
0x180002407  jmp     loc_18000216A
0x18000240c  mov     rcx, cs:WPP_GLOBAL_Control
0x180002413  lea     rax, WPP_GLOBAL_Control
0x18000241a  cmp     rcx, rax
0x18000241d  jz      loc_180002327
0x180002423  test    byte ptr [rcx+1Ch], 1
0x180002427  jz      loc_180002327
0x18000242d  cmp     byte ptr [rcx+19h], 5
0x180002431  jb      loc_180002327
0x180002437  mov     rcx, [rcx+10h]
0x18000243b  lea     r8, WPP_c7cc13fe6dc03834cd55671891cfefc7_Traceguids
0x180002442  mov     eax, 10624DD3h
0x180002447  mul     r13d
0x18000244a  mov     r9d, edx
0x18000244d  mov     edx, 10h
0x180002452  shr     r9d, 6
0x180002456  call    WPP_SF_d
0x18000245b  jmp     loc_180002327
0x180002460  xorps   xmm0, xmm0
0x180002463  mov     dword ptr [rbp+57h+var_50], 0
0x18000246a  movups  [rbp+57h+var_50+8], xmm0
0x18000246e  lea     rax, aLanConnection; "LAN Connection"
0x180002475  mov     dword ptr [rbp+57h+var_50+8], 10h
0x18000247c  lea     rcx, ?gSensLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180002483  mov     dword ptr [rbp+57h+var_50+0Ch], 1
0x18000248a  mov     dword ptr [rbp+57h+var_40], r15d
0x18000248e  mov     dword ptr [rbp+57h+var_40+4], r15d
0x180002492  mov     dword ptr [rbp+57h+var_50+4], r12d
0x180002496  mov     qword ptr [rbp+57h+var_40+8], rax
0x18000249a  call    cs:__imp_EnterCriticalSection
0x1800024a0  mov     rax, cs:?gpSensCache@@3PEAU_SENS_CACHE@@EA; _SENS_CACHE * gpSensCache
0x1800024a7  test    rax, rax
0x1800024aa  jz      short loc_1800024C3
0x1800024ac  mov     ecx, cs:?gdwLANState@@3JA; long gdwLANState
0x1800024b2  mov     [rax+14h], ecx
0x1800024b5  mov     ecx, cs:?gdwLastLANTime@@3JA; long gdwLastLANTime
0x1800024bb  mov     [rax+18h], ecx
0x1800024be  call    ?UpdateSensNetworkCache@@YAXXZ; UpdateSensNetworkCache(void)
0x1800024c3  lea     rcx, ?gSensLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800024ca  call    cs:__imp_LeaveCriticalSection
0x1800024d0  lea     rcx, [rbp+57h+var_50]; void *
0x1800024d4  call    ?SensFireEvent@@YAXPEAX@Z; SensFireEvent(void *)
0x1800024d9  jmp     loc_180002340
0x1800024de  cmp     byte ptr [r10+19h], 5
0x1800024e3  jb      loc_180002223
0x1800024e9  mov     r9d, [rsi+r8+10h]
0x1800024ee  mov     edx, 0Eh
0x1800024f3  mov     rcx, [r10+10h]
0x1800024f7  lea     r8, WPP_c7cc13fe6dc03834cd55671891cfefc7_Traceguids
0x1800024fe  mov     [rsp+0C0h+var_A0], eax
0x180002502  call    WPP_SF_dd
0x180002507  mov     r8, [rbp+57h+Table]
0x18000250b  jmp     loc_180002223
0x180002510  test    byte ptr [r11+1Ch], 1
0x180002515  jz      loc_1800023F4
0x18000251b  cmp     byte ptr [r11+19h], 2
0x180002520  jb      loc_1800023F4
0x180002526  mov     r9d, [r9+rax]
0x18000252a  lea     r8, WPP_c7cc13fe6dc03834cd55671891cfefc7_Traceguids
0x180002531  mov     rcx, [r11+10h]
0x180002535  mov     edx, 24h ; '$'
0x18000253a  call    WPP_SF_d
0x18000253f  mov     r11, cs:WPP_GLOBAL_Control
0x180002546  lea     rcx, ?gIfState@@3PAU_IF_STATE@@A; _IF_STATE near * gIfState
0x18000254d  jmp     loc_1800023F4
0x180002552  cmp     byte ptr [r10+19h], 5
0x180002557  jb      loc_1800021B7
0x18000255d  mov     r9, [rbp+57h+Table]
0x180002561  lea     r8, WPP_c7cc13fe6dc03834cd55671891cfefc7_Traceguids
0x180002568  mov     rcx, [r10+10h]
0x18000256c  mov     edx, 0Dh
0x180002571  mov     r9d, [r9]
0x180002574  call    WPP_SF_d
0x180002579  mov     r10, cs:WPP_GLOBAL_Control
0x180002580  lea     rdx, WPP_GLOBAL_Control
0x180002587  jmp     loc_1800021B7
0x18000258c  test    r12d, r12d
0x18000258f  jnz     loc_18000240C
0x180002595  call    cs:__imp_GetTickCount
0x18000259b  mov     edx, cs:?gdwLastLANTime@@3JA; long gdwLastLANTime
0x1800025a1  mov     ecx, eax
0x1800025a3  sub     ecx, edx
0x1800025a5  mov     r11d, eax
0x1800025a8  cmp     ecx, 2BF20h
0x1800025ae  ja      loc_180002307
0x1800025b4  test    edx, edx
0x1800025b6  jz      loc_180002307
0x1800025bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800025c3  lea     rax, WPP_GLOBAL_Control
0x1800025ca  cmp     rcx, rax
0x1800025cd  jz      short loc_18000261C
0x1800025cf  test    byte ptr [rcx+1Ch], 1
0x1800025d3  jz      short loc_18000261C
  ... truncated ...
```
