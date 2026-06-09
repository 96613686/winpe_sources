# CMadcapHandler::GetLease(IMulticastCallback *,tagWDS_INTERFACE_INFO *,tagWDS_IP_ADDRESS6 *)

- ea: `0x1800162d4`
- end: `0x180016876`
- name: `?GetLease@CMadcapHandler@@QEAAKPEAVIMulticastCallback@@PEAUtagWDS_INTERFACE_INFO@@PEAUtagWDS_IP_ADDRESS6@@@Z`
- size: `1442`
- prototype: `unsigned int __fastcall(LPCRITICAL_SECTION lpCriticalSection, struct IMulticastCallback *, struct tagWDS_INTERFACE_INFO *, struct tagWDS_IP_ADDRESS6 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180018cdc`

## callees

- `0x18000195c`
- `0x180015f1c`
- `0x1800160e8`
- `0x1800161e0`
- `0x1800162d4`
- `0x1800173ac`
- `0x18001c112`
- `0x18001c11e`
- `0x18001c12a`
- `0x18001c150`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800163b6`
- `KERNEL32!LeaveCriticalSection` at `0x18001683f`
- `KERNEL32!LeaveCriticalSection` at `0x1800163b6`
- `KERNEL32!LeaveCriticalSection` at `0x18001683f`
- `KERNEL32!EnterCriticalSection` at `0x180016324`
- `KERNEL32!EnterCriticalSection` at `0x180016336`
- `KERNEL32!EnterCriticalSection` at `0x180016324`
- `KERNEL32!EnterCriticalSection` at `0x180016336`
- `dhcpcsvc!McastGenUID` at `0x1800164ca`
- `dhcpcsvc!McastGenUID` at `0x1800164ca`
- `dhcpcsvc!McastRequestAddress` at `0x1800165a3`
- `dhcpcsvc!McastRequestAddress` at `0x1800165a3`
- `WdsServerCommonLib!?IpAddressToString@CNetworkAddress@@SAKUtagWDS_IP_ADDRESS6@@PEAPEAG@Z` at `0x18001667c`
- `WdsServerCommonLib!?IpAddressToString@CNetworkAddress@@SAKUtagWDS_IP_ADDRESS6@@PEAPEAG@Z` at `0x18001667c`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800163e8`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18001657d`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800165f0`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180016705`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800163e8`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18001657d`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800165f0`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180016705`
- `WdsServerCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x1800167b4`
- `WdsServerCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x180016820`
- `WdsServerCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x1800167b4`
- `WdsServerCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x180016820`
- `WdsServerCommonLib!?IpAddressToString@CNetworkAddress@@SAKUtagWDS_IP_ADDRESS6@@PEAGK@Z` at `0x18001677d`
- `WdsServerCommonLib!?IpAddressToString@CNetworkAddress@@SAKUtagWDS_IP_ADDRESS6@@PEAGK@Z` at `0x18001677d`

## string_xrefs

- `0x1800163ce`: `[MADCAP] New lease request fulfilled from cache: %s`

## pseudocode

```c
__int64 __fastcall CMadcapHandler::GetLease(
        LPCRITICAL_SECTION lpCriticalSection,
        struct IMulticastCallback *a2,
        struct tagWDS_INTERFACE_INFO *a3,
        struct tagWDS_IP_ADDRESS6 *a4)
{
  __int64 NextScope; // r14
  struct _MCAST_CLIENT_UID *v5; // rdi
  _QWORD *v9; // rsi
  _QWORD *OwningThread; // rcx
  __int16 DebugInfo; // ax
  bool v12; // zf
  struct tagWDS_INTERFACE_INFO *v13; // rdx
  __int64 v14; // r9
  __int64 v15; // rdx
  __int64 v16; // r8
  int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // r8
  void *v20; // rcx
  int *v21; // r12
  struct _MCAST_CLIENT_UID *v22; // rax
  PMCAST_SCOPE_CTX v23; // r15
  struct _MCAST_CLIENT_UID *v24; // rsi
  __int64 v25; // rdx
  __int64 v26; // r8
  CIPString *v27; // rax
  const wchar_t *v28; // r9
  DWORD v29; // eax
  __int64 v30; // rdx
  __int64 v31; // r8
  CIPString *v32; // rax
  const wchar_t *v33; // r9
  struct tagWDS_INTERFACE_INFO *v34; // rdx
  int v35; // eax
  struct _MCAST_CLIENT_UID v36; // xmm0
  __int64 v37; // rdx
  __int64 v38; // r8
  size_t v39; // r8
  const wchar_t *v40; // rax
  CIPString *v41; // rax
  int v43; // [rsp+40h] [rbp-C0h]
  PMCAST_SCOPE_CTX pScopeCtx; // [rsp+48h] [rbp-B8h] BYREF
  void *v45; // [rsp+50h] [rbp-B0h] BYREF
  struct IMulticastCallback *v46; // [rsp+58h] [rbp-A8h]
  void *v47; // [rsp+60h] [rbp-A0h]
  struct _MCAST_CLIENT_UID v48; // [rsp+70h] [rbp-90h] BYREF
  int v49; // [rsp+80h] [rbp-80h]
  struct _MCAST_CLIENT_UID v50; // [rsp+90h] [rbp-70h] BYREF
  int v51; // [rsp+A0h] [rbp-60h]
  BOOL v52; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v53[140]; // [rsp+B4h] [rbp-4Ch] BYREF

  v47 = a4;
  LODWORD(NextScope) = 0;
  pScopeCtx = 0;
  v5 = 0;
  v43 = 0;
  v46 = a2;
  EnterCriticalSection(lpCriticalSection);
  v9 = 0;
  EnterCriticalSection(lpCriticalSection);
  OwningThread = lpCriticalSection[1].OwningThread;
  while ( OwningThread )
  {
    v9 = OwningThread;
    OwningThread = (_QWORD *)OwningThread[29];
    if ( !*((_DWORD *)v9 + 52) )
      goto LABEL_14;
    DebugInfo = (__int16)lpCriticalSection[2].DebugInfo;
    if ( DebugInfo == 2 )
    {
      if ( *((_DWORD *)a3 + 4) != 4 )
        goto LABEL_14;
LABEL_5:
      if ( DebugInfo != 2 )
        goto LABEL_14;
      v12 = *((_DWORD *)v9 + 13) == *(_DWORD *)a3;
      goto LABEL_13;
    }
    if ( DebugInfo != 23 )
      goto LABEL_5;
    if ( *((_DWORD *)a3 + 4) != 16 || *(_QWORD *)((char *)v9 + 52) != *(_QWORD *)a3 )
      goto LABEL_14;
    v12 = *(_QWORD *)((char *)v9 + 60) == *((_QWORD *)a3 + 1);
LABEL_13:
    if ( v12 )
      break;
LABEL_14:
    v9 = 0;
  }
  LeaveCriticalSection(lpCriticalSection);
  if ( v9 )
  {
    v14 = v9[25];
    *((_DWORD *)v9 + 52) = 0;
    CTrace::Trace((CTrace *)qword_180039310, 0x20000u, L"[MADCAP] New lease request fulfilled from cache: %s", v14);
    memmove_0(a4, v9 + 22, 0x14u);
    goto LABEL_57;
  }
  v45 = 0;
  NextScope = CMadcapHandler::FindNextScope(lpCriticalSection, v13, &v45, (struct _MCAST_SCOPE_ENTRY **)&pScopeCtx);
  v17 = ElValidateWin32_8(NextScope, v15, v16, 446);
  v20 = 0;
  if ( !v17 )
    v20 = v45;
  v45 = v20;
  v21 = (int *)L"<<Failed>>";
  if ( !(unsigned int)ElValidateWin32_8((unsigned int)NextScope, v18, v19, 947) )
  {
    v43 = 1;
    while ( 1 )
    {
      if ( v5 )
      {
        CMadcapHandler::DestroyLease(lpCriticalSection, (struct CMadcapHandler::DhcpLease *)v5);
        v5 = 0;
      }
      v22 = (struct _MCAST_CLIENT_UID *)operator new(0xF8u, (const struct std::nothrow_t *)&std::nothrow);
      v23 = pScopeCtx;
      v24 = v22;
      if ( v22 )
      {
        memset_0(v22, 0, 0xF8u);
        LODWORD(v24[13].ClientUID) = 1;
        v24->ClientUID = (LPBYTE)&v24[1];
        v24->ClientUIDLength = 17;
        LODWORD(NextScope) = McastGenUID(v24);
        if ( !(_DWORD)NextScope )
        {
          v24[8].ClientUID = 0;
          v24[7].ClientUIDLength = 65537;
          LODWORD(v24[6].ClientUID) = 21600;
          HIDWORD(v24[6].ClientUID) = 21600;
          memmove_0(&v24[6].ClientUIDLength, &v23->ServerID, (unsigned int)lpCriticalSection[1].LockCount);
          LOWORD(v24[10].ClientUID) = 1;
          *(_QWORD *)&v24[10].ClientUIDLength = v24 + 11;
          v5 = v24;
          goto LABEL_29;
        }
      }
      else
      {
        v24 = 0;
        LODWORD(NextScope) = 8;
      }
      CMadcapHandler::DestroyLease(lpCriticalSection, (struct CMadcapHandler::DhcpLease *)v24);
LABEL_29:
      if ( (unsigned int)ElValidateWin32_8((unsigned int)NextScope, v25, v26, 973) )
        goto LABEL_44;
      v27 = CIPString::CIPString((CIPString *)&v52, &v23->ServerID, lpCriticalSection[1].LockCount);
      v28 = L"<<Failed>>";
      if ( !*(_DWORD *)v27 )
        v28 = (const wchar_t *)((char *)v27 + 4);
      CTrace::Trace((CTrace *)qword_180039310, 0x20000u, L"[MADCAP] Contacting Server: %s for multicast lease.", v28);
      v29 = McastRequestAddress(
              (IP_ADDR_FAMILY)lpCriticalSection[2].DebugInfo,
              v5,
              v23,
              (PMCAST_LEASE_REQUEST)&v5[5].ClientUIDLength,
              (PMCAST_LEASE_RESPONSE)&v5[8].ClientUIDLength);
      if ( !(unsigned int)ElValidateWin32_8(v29, v30, v31, 988) )
      {
        v5[14].ClientUID = (LPBYTE)v46;
        memmove_0((char *)&v5[2].ClientUID + 4, v23, 0x30u);
        v35 = 4;
        if ( LOWORD(lpCriticalSection[2].DebugInfo) != 2 )
          v35 = 16;
        LODWORD(v5[12].ClientUID) = v35;
        v36 = v5[11];
        v51 = v35;
        v50 = v36;
        NextScope = (unsigned int)CNetworkAddress::IpAddressToString(&v50, &v5[12].ClientUIDLength);
        if ( !(unsigned int)ElValidateWin32_8(NextScope, v37, v38, 1010) )
        {
          LODWORD(v5[13].ClientUID) = 0;
          if ( lpCriticalSection[1].OwningThread )
          {
            *(_QWORD *)&v5[14].ClientUIDLength = 0;
            v5[15].ClientUID = (LPBYTE)lpCriticalSection[1].LockSemaphore;
            *((_QWORD *)lpCriticalSection[1].LockSemaphore + 29) = v5;
            lpCriticalSection[1].LockSemaphore = v5;
          }
          else
          {
            lpCriticalSection[1].LockSemaphore = v5;
            lpCriticalSection[1].OwningThread = v5;
            *(_QWORD *)&v5[14].ClientUIDLength = 0;
            v5[15].ClientUID = 0;
          }
          ++HIDWORD(lpCriticalSection[1].SpinCount);
          CTrace::Trace(
            (CTrace *)qword_180039310,
            0x20000u,
            L"[MADCAP] New lease acquired: %s",
            *(_QWORD *)&v5[12].ClientUIDLength);
          memmove_0(v47, &v5[11], 0x14u);
        }
        goto LABEL_44;
      }
      v32 = CIPString::CIPString((CIPString *)&v52, &v23->ServerID, lpCriticalSection[1].LockCount);
      v33 = L"<<Failed>>";
      if ( !*(_DWORD *)v32 )
        v33 = (const wchar_t *)((char *)v32 + 4);
      CTrace::Trace((CTrace *)qword_180039310, 0x80000u, L"[MADCAP] Failed to obtain lease from Server [%s].", v33);
      if ( CMadcapHandler::FindNextScope(lpCriticalSection, v34, &v45, (struct _MCAST_SCOPE_ENTRY **)&pScopeCtx) )
      {
        v23 = pScopeCtx;
        LODWORD(NextScope) = 2;
        goto LABEL_50;
      }
    }
  }
  v23 = pScopeCtx;
LABEL_44:
  if ( (_DWORD)NextScope )
  {
    if ( v43 )
    {
LABEL_50:
      if ( v23 )
      {
        v41 = CIPString::CIPString((CIPString *)&v52, &v23->ServerID, lpCriticalSection[1].LockCount);
        if ( !*(_DWORD *)v41 )
          v21 = (int *)((char *)v41 + 4);
      }
      else
      {
        v21 = &dword_180021EC4;
      }
      CEventLog::Log((CEventLog *)qword_180039300, 0xC1010601, 2, 1, v21, 5, NextScope);
    }
    else
    {
      v39 = *((unsigned int *)a3 + 4);
      v50 = (struct _MCAST_CLIENT_UID)0LL;
      v51 = v39;
      memcpy_0(&v50, a3, v39);
      v49 = v51;
      v48 = v50;
      v12 = (unsigned int)CNetworkAddress::IpAddressToString(&v48, v53, 64) == 0;
      v40 = (const wchar_t *)v53;
      v52 = !v12;
      if ( !v12 )
        v40 = L"<<Failed>>";
      CEventLog::Log((CEventLog *)qword_180039300, 0xC1010603, 1, 1, v40);
    }
    if ( v5 )
      CMadcapHandler::DestroyLease(lpCriticalSection, (struct CMadcapHandler::DhcpLease *)v5);
  }
LABEL_57:
  LeaveCriticalSection(lpCriticalSection);
  return (unsigned int)NextScope;
}

```

## disassembly

```asm
0x1800162d4  mov     [rsp-8+arg_8], rbx
0x1800162d9  push    rbp
0x1800162da  push    rsi
0x1800162db  push    rdi
0x1800162dc  push    r12
0x1800162de  push    r13
0x1800162e0  push    r14
0x1800162e2  push    r15
0x1800162e4  lea     rbp, [rsp-50h]
0x1800162e9  sub     rsp, 150h
0x1800162f0  mov     rax, cs:__security_cookie
0x1800162f7  xor     rax, rsp
0x1800162fa  mov     [rbp+80h+var_40], rax
0x1800162fe  xor     r12d, r12d
0x180016301  mov     [rsp+180h+var_120], r9
0x180016306  mov     r14d, r12d
0x180016309  mov     [rsp+180h+pScopeCtx], r12
0x18001630e  mov     edi, r12d
0x180016311  mov     [rsp+180h+var_140], r12d
0x180016316  mov     r15, r9
0x180016319  mov     [rsp+180h+var_128], rdx
0x18001631e  mov     r13, r8
0x180016321  mov     rbx, rcx
0x180016324  call    cs:__imp_EnterCriticalSection
0x18001632b  nop     dword ptr [rax+rax+00h]
0x180016330  mov     rcx, rbx; lpCriticalSection
0x180016333  mov     esi, r12d
0x180016336  call    cs:__imp_EnterCriticalSection
0x18001633d  nop     dword ptr [rax+rax+00h]
0x180016342  mov     rcx, [rbx+38h]
0x180016346  lea     edx, [r12+2]
0x18001634b  lea     r8d, [r12+10h]
0x180016350  jmp     short loc_1800163AE
0x180016352  mov     rsi, rcx
0x180016355  mov     rcx, [rcx+0E8h]
0x18001635c  cmp     [rsi+0D0h], r12d
0x180016363  jz      short loc_1800163AB
0x180016365  movzx   eax, word ptr [rbx+50h]
0x180016369  cmp     ax, dx
0x18001636c  jnz     short loc_180016383
0x18001636e  cmp     dword ptr [r13+10h], 4
0x180016373  jnz     short loc_1800163AB
0x180016375  cmp     ax, dx
0x180016378  jnz     short loc_180016391
0x18001637a  mov     eax, [r13+0]
0x18001637e  cmp     [rsi+34h], eax
0x180016381  jmp     short loc_1800163A9
0x180016383  cmp     ax, 17h
0x180016387  jnz     short loc_180016375
0x180016389  cmp     [r13+10h], r8d
0x18001638d  jz      short loc_180016397
0x18001638f  jmp     short loc_1800163AB
0x180016391  cmp     ax, 17h
0x180016395  jnz     short loc_1800163AB
0x180016397  mov     rax, [rsi+34h]
0x18001639b  cmp     rax, [r13+0]
0x18001639f  jnz     short loc_1800163AB
0x1800163a1  mov     rax, [rsi+3Ch]
0x1800163a5  cmp     rax, [r13+8]
0x1800163a9  jz      short loc_1800163B3
0x1800163ab  mov     rsi, r12
0x1800163ae  test    rcx, rcx
0x1800163b1  jnz     short loc_180016352
0x1800163b3  mov     rcx, rbx; lpCriticalSection
0x1800163b6  call    cs:__imp_LeaveCriticalSection
0x1800163bd  nop     dword ptr [rax+rax+00h]
0x1800163c2  test    rsi, rsi
0x1800163c5  jz      short loc_18001640E
0x1800163c7  mov     r9, [rsi+0C8h]
0x1800163ce  lea     r8, aMadcapNewLease_0; "[MADCAP] New lease request fulfilled fr"...
0x1800163d5  mov     edx, 20000h
0x1800163da  mov     [rsi+0D0h], r12d
0x1800163e1  lea     rcx, qword_180039310
0x1800163e8  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x1800163ef  nop     dword ptr [rax+rax+00h]
0x1800163f4  lea     rdx, [rsi+0B0h]; Src
0x1800163fb  mov     r8d, 14h; Size
0x180016401  mov     rcx, r15; void *
0x180016404  call    memmove_0
0x180016409  jmp     loc_18001683C
0x18001640e  lea     r9, [rsp+180h+pScopeCtx]; struct _MCAST_SCOPE_ENTRY **
0x180016413  mov     [rsp+180h+var_130], r12
0x180016418  lea     r8, [rsp+180h+var_130]; void **
0x18001641d  mov     rcx, rbx; lpCriticalSection
0x180016420  call    ?FindNextScope@CMadcapHandler@@AEAAKPEAUtagWDS_INTERFACE_INFO@@PEAPEAXPEAPEAU_MCAST_SCOPE_ENTRY@@@Z; CMadcapHandler::FindNextScope(tagWDS_INTERFACE_INFO *,void * *,_MCAST_SCOPE_ENTRY * *)
0x180016425  mov     r9d, 1BEh
0x18001642b  mov     ecx, eax
0x18001642d  mov     r14d, eax
0x180016430  call    ElValidateWin32_8
0x180016435  test    eax, eax
0x180016437  mov     rcx, r12
0x18001643a  cmovz   rcx, [rsp+180h+var_130]
0x180016440  mov     [rsp+180h+var_130], rcx
0x180016445  mov     r9d, 3B3h
0x18001644b  mov     ecx, r14d
0x18001644e  call    ElValidateWin32_8
0x180016453  lea     r12, aFailed_0; "<<Failed>>"
0x18001645a  mov     esi, 1
0x18001645f  test    eax, eax
0x180016461  jnz     loc_1800167C2
0x180016467  mov     [rsp+180h+var_140], esi
0x18001646b  test    rdi, rdi
0x18001646e  jz      short loc_18001647D
0x180016470  mov     rdx, rdi; this
0x180016473  mov     rcx, rbx; lpCriticalSection
0x180016476  call    ?DestroyLease@CMadcapHandler@@AEAAKPEAUDhcpLease@1@@Z; CMadcapHandler::DestroyLease(CMadcapHandler::DhcpLease *)
0x18001647b  xor     edi, edi
0x18001647d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180016484  mov     ecx, 0F8h; unsigned __int64
0x180016489  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001648e  mov     r15, [rsp+180h+pScopeCtx]
0x180016493  mov     rsi, rax
0x180016496  test    rax, rax
0x180016499  jz      loc_180016526
0x18001649f  xor     edx, edx; Val
0x1800164a1  mov     r8d, 0F8h; Size
0x1800164a7  mov     rcx, rax; void *
0x1800164aa  call    memset_0
0x1800164af  lea     rax, [rsi+10h]
0x1800164b3  mov     dword ptr [rsi+0D0h], 1
0x1800164bd  mov     rcx, rsi; pRequestID
0x1800164c0  mov     [rsi], rax
0x1800164c3  mov     dword ptr [rsi+8], 11h
0x1800164ca  call    cs:__imp_McastGenUID
0x1800164d1  nop     dword ptr [rax+rax+00h]
0x1800164d6  mov     r14d, eax
0x1800164d9  test    eax, eax
0x1800164db  jnz     short loc_18001652C
0x1800164dd  and     qword ptr [rsi+80h], 0
0x1800164e5  lea     rdx, [r15+20h]; Src
0x1800164e9  mov     eax, 5460h
0x1800164ee  mov     dword ptr [rsi+78h], 10001h
0x1800164f5  mov     [rsi+60h], eax
0x1800164f8  lea     rcx, [rsi+68h]; void *
0x1800164fc  mov     [rsi+64h], eax
0x1800164ff  lea     edi, [r14+1]
0x180016503  mov     r8d, [rbx+30h]; Size
0x180016507  call    memmove_0
0x18001650c  lea     rax, [rsi+0B0h]
0x180016513  mov     [rsi+0A0h], di
0x18001651a  mov     [rsi+0A8h], rax
0x180016521  mov     rdi, rsi
0x180016524  jmp     short loc_180016537
0x180016526  xor     esi, esi
0x180016528  lea     r14d, [rsi+8]
0x18001652c  mov     rdx, rsi; this
0x18001652f  mov     rcx, rbx; lpCriticalSection
0x180016532  call    ?DestroyLease@CMadcapHandler@@AEAAKPEAUDhcpLease@1@@Z; CMadcapHandler::DestroyLease(CMadcapHandler::DhcpLease *)
0x180016537  mov     r9d, 3CDh
0x18001653d  mov     ecx, r14d
0x180016540  call    ElValidateWin32_8
0x180016545  test    eax, eax
0x180016547  jnz     loc_180016728
0x18001654d  mov     r8d, [rbx+30h]; unsigned int
0x180016551  lea     rdx, [r15+20h]; void *
0x180016555  lea     rcx, [rbp+80h+var_D0]; this
0x180016559  call    ??0CIPString@@QEAA@PEAXK@Z; CIPString::CIPString(void *,ulong)
0x18001655e  mov     r9, r12
0x180016561  cmp     dword ptr [rax], 0
0x180016564  jnz     short loc_18001656A
0x180016566  lea     r9, [rax+4]
0x18001656a  lea     r8, aMadcapContacti; "[MADCAP] Contacting Server: %s for mult"...
0x180016571  mov     edx, 20000h
0x180016576  lea     rcx, qword_180039310
0x18001657d  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180016584  nop     dword ptr [rax+rax+00h]
0x180016589  movzx   ecx, word ptr [rbx+50h]; AddrFamily
0x18001658d  lea     rax, [rdi+88h]
0x180016594  lea     r9, [rdi+58h]; pAddrRequest
0x180016598  mov     [rsp+180h+pAddrResponse], rax; pAddrResponse
0x18001659d  mov     r8, r15; pScopeCtx
0x1800165a0  mov     rdx, rdi; pRequestID
0x1800165a3  call    cs:__imp_McastRequestAddress
0x1800165aa  nop     dword ptr [rax+rax+00h]
0x1800165af  mov     ecx, eax
0x1800165b1  mov     r9d, 3DCh
0x1800165b7  call    ElValidateWin32_8
0x1800165bc  test    eax, eax
0x1800165be  jz      short loc_180016628
0x1800165c0  mov     r8d, [rbx+30h]; unsigned int
0x1800165c4  lea     rdx, [r15+20h]; void *
0x1800165c8  lea     rcx, [rbp+80h+var_D0]; this
0x1800165cc  call    ??0CIPString@@QEAA@PEAXK@Z; CIPString::CIPString(void *,ulong)
0x1800165d1  mov     r9, r12
0x1800165d4  cmp     dword ptr [rax], 0
0x1800165d7  jnz     short loc_1800165DD
0x1800165d9  lea     r9, [rax+4]
0x1800165dd  lea     r8, aMadcapFailedTo; "[MADCAP] Failed to obtain lease from Se"...
0x1800165e4  mov     edx, 80000h
0x1800165e9  lea     rcx, qword_180039310
0x1800165f0  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x1800165f7  nop     dword ptr [rax+rax+00h]
0x1800165fc  lea     r9, [rsp+180h+pScopeCtx]; struct _MCAST_SCOPE_ENTRY **
0x180016601  mov     rcx, rbx; lpCriticalSection
0x180016604  lea     r8, [rsp+180h+var_130]; void **
0x180016609  call    ?FindNextScope@CMadcapHandler@@AEAAKPEAUtagWDS_INTERFACE_INFO@@PEAPEAXPEAPEAU_MCAST_SCOPE_ENTRY@@@Z; CMadcapHandler::FindNextScope(tagWDS_INTERFACE_INFO *,void * *,_MCAST_SCOPE_ENTRY * *)
0x18001660e  test    eax, eax
0x180016610  jz      loc_18001646B
0x180016616  mov     r15, [rsp+180h+pScopeCtx]
0x18001661b  mov     esi, 2
0x180016620  mov     r14d, esi
0x180016623  jmp     loc_1800167D1
0x180016628  mov     rax, [rsp+180h+var_128]
0x18001662d  lea     rcx, [rdi+24h]; void *
0x180016631  mov     r8d, 30h ; '0'; Size
0x180016637  mov     [rdi+0E0h], rax
0x18001663e  mov     rdx, r15; Src
0x180016641  call    memmove_0
0x180016646  mov     eax, 2
0x18001664b  lea     rsi, [rdi+0C8h]
0x180016652  cmp     [rbx+50h], ax
0x180016656  mov     rdx, rsi
0x180016659  mov     eax, 4
0x18001665e  lea     ecx, [rax+0Ch]
0x180016661  cmovnz  eax, ecx
0x180016664  lea     rcx, [rbp+80h+var_F0]
0x180016668  mov     [rdi+0C0h], eax
0x18001666e  movups  xmm0, xmmword ptr [rdi+0B0h]
0x180016675  mov     [rbp+80h+var_E0], eax
0x180016678  movaps  [rbp+80h+var_F0], xmm0
0x18001667c  call    cs:__imp_?IpAddressToString@CNetworkAddress@@SAKUtagWDS_IP_ADDRESS6@@PEAPEAG@Z; CNetworkAddress::IpAddressToString(tagWDS_IP_ADDRESS6,ushort * *)
0x180016683  nop     dword ptr [rax+rax+00h]
0x180016688  mov     ecx, eax
0x18001668a  mov     r9d, 3F2h
0x180016690  mov     r14d, eax
0x180016693  call    ElValidateWin32_8
0x180016698  xor     ecx, ecx
0x18001669a  test    eax, eax
0x18001669c  jnz     loc_180016728
0x1800166a2  mov     [rdi+0D0h], ecx
0x1800166a8  cmp     [rbx+38h], rcx
0x1800166ac  jnz     short loc_1800166C6
0x1800166ae  mov     [rbx+40h], rdi
0x1800166b2  mov     [rbx+38h], rdi
0x1800166b6  mov     [rdi+0E8h], rcx
0x1800166bd  mov     [rdi+0F0h], rcx
0x1800166c4  jmp     short loc_1800166E7
0x1800166c6  mov     [rdi+0E8h], rcx
0x1800166cd  mov     rax, [rbx+40h]
0x1800166d1  mov     [rdi+0F0h], rax
0x1800166d8  mov     rax, [rbx+40h]
0x1800166dc  mov     [rax+0E8h], rdi
0x1800166e3  mov     [rbx+40h], rdi
0x1800166e7  mov     eax, 1
0x1800166ec  lea     r8, aMadcapNewLease; "[MADCAP] New lease acquired: %s"
0x1800166f3  add     [rbx+4Ch], eax
0x1800166f6  lea     rcx, qword_180039310
0x1800166fd  mov     r9, [rsi]
0x180016700  mov     edx, 20000h
0x180016705  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18001670c  nop     dword ptr [rax+rax+00h]
0x180016711  mov     rcx, [rsp+180h+var_120]; void *
0x180016716  lea     rdx, [rdi+0B0h]; Src
0x18001671d  mov     r8d, 14h; Size
0x180016723  call    memmove_0
0x180016728  mov     esi, 1
0x18001672d  test    r14d, r14d
0x180016730  jz      loc_18001683C
0x180016736  cmp     [rsp+180h+var_140], 0
0x18001673b  jnz     loc_1800167CC
0x180016741  mov     r8d, [r13+10h]; Size
0x180016745  lea     rcx, [rbp+80h+var_F0]; void *
0x180016749  and     qword ptr [rbp+80h+var_F0], 0
0x18001674e  mov     rdx, r13; Src
0x180016751  and     qword ptr [rbp+80h+var_F0+8], 0
0x180016756  mov     [rbp+80h+var_E0], r8d
0x18001675a  call    memcpy_0
0x18001675f  movups  xmm0, [rbp+80h+var_F0]
0x180016763  mov     eax, [rbp+80h+var_E0]
0x180016766  lea     rdx, [rbp+80h+var_CC]
0x18001676a  mov     r8d, 40h ; '@'
0x180016770  mov     [rbp+80h+var_100], eax
0x180016773  lea     rcx, [rsp+180h+var_110]
0x180016778  movaps  [rsp+180h+var_110], xmm0
0x18001677d  call    cs:__imp_?IpAddressToString@CNetworkAddress@@SAKUtagWDS_IP_ADDRESS6@@PEAGK@Z; CNetworkAddress::IpAddressToString(tagWDS_IP_ADDRESS6,ushort *,ulong)
0x180016784  nop     dword ptr [rax+rax+00h]
0x180016789  xor     ecx, ecx
0x18001678b  mov     r9d, esi
0x18001678e  test    eax, eax
0x180016790  mov     r8d, esi
0x180016793  lea     rax, [rbp+80h+var_CC]
0x180016797  mov     edx, 0C1010603h
0x18001679c  setnz   cl
0x18001679f  test    ecx, ecx
0x1800167a1  mov     [rbp+80h+var_D0], ecx
0x1800167a4  lea     rcx, qword_180039300
0x1800167ab  cmovnz  rax, r12
0x1800167af  mov     [rsp+180h+pAddrResponse], rax
0x1800167b4  call    cs:__imp_?Log@CEventLog@@QEAAKKHZZ; CEventLog::Log(ulong,int,...)
0x1800167bb  nop     dword ptr [rax+rax+00h]
0x1800167c0  jmp     short loc_18001682C
0x1800167c2  mov     r15, [rsp+180h+pScopeCtx]
0x1800167c7  jmp     loc_18001672D
0x1800167cc  mov     esi, 2
0x1800167d1  test    r15, r15
0x1800167d4  jz      short loc_1800167F2
0x1800167d6  mov     r8d, [rbx+30h]; unsigned int
0x1800167da  lea     rdx, [r15+20h]; void *
0x1800167de  lea     rcx, [rbp+80h+var_D0]; this
0x1800167e2  call    ??0CIPString@@QEAA@PEAXK@Z; CIPString::CIPString(void *,ulong)
  ... truncated ...
```
