# HTTP2ServerVirtualConnection::InitializeServerConnection(uchar *,ulong,BASE_CONNECTION *,HTTP2ServerVirtualConnection * *,int *)

- ea: `0x18000dfe8`
- end: `0x18000ed89`
- name: `?InitializeServerConnection@HTTP2ServerVirtualConnection@@SAJPEAEKPEAVBASE_CONNECTION@@PEAPEAV1@PEAH@Z`
- size: `3489`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned int, struct BASE_CONNECTION *, struct HTTP2ServerVirtualConnection **, int *)`
- caller_count: `1`
- callee_count: `34`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b4c0`

## callees

- `0x180002b00`
- `0x180003218`
- `0x180004058`
- `0x1800043d8`
- `0x1800048d8`
- `0x180004fc8`
- `0x180005ba8`
- `0x180009d0c`
- `0x18000ab40`
- `0x18000dfe8`
- `0x18000f290`
- `0x18000f334`
- `0x18000f3fc`
- `0x180016df8`
- `0x1800191ec`
- `0x1800193d0`
- `0x18001941c`
- `0x18001977c`
- `0x1800197dc`
- `0x1800198e0`
- `0x1800199cc`
- `0x180019d0c`
- `0x18001ac1c`
- `0x18001ac60`
- `0x18001ac8c`
- `0x18001adac`
- `0x18001bfe4`
- `0x18001c5b0`
- `0x18001c714`
- `0x18001c86c`
- `0x18001ca64`
- `0x180024611`
- `0x180024640`
- `0x180025010`

## import_xrefs

- `ntdll!RtlInsertElementGenericTableAvl` at `0x18000e602`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x18000ea0e`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x18000e602`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x18000ea0e`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18000e64d`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18000e64d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000e36f`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000e665`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000eac0`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000e36f`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000e665`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000eac0`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000e326`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000e326`
- `RPCRT4!I_RpcLogEvent` at `0x18000e5bf`
- `RPCRT4!I_RpcLogEvent` at `0x18000e7c7`
- `RPCRT4!I_RpcLogEvent` at `0x18000e897`
- `RPCRT4!I_RpcLogEvent` at `0x18000e90b`
- `RPCRT4!I_RpcLogEvent` at `0x18000e9cd`
- `RPCRT4!I_RpcLogEvent` at `0x18000ea72`
- `RPCRT4!I_RpcLogEvent` at `0x18000e5bf`
- `RPCRT4!I_RpcLogEvent` at `0x18000e7c7`
- `RPCRT4!I_RpcLogEvent` at `0x18000e897`
- `RPCRT4!I_RpcLogEvent` at `0x18000e90b`
- `RPCRT4!I_RpcLogEvent` at `0x18000e9cd`
- `RPCRT4!I_RpcLogEvent` at `0x18000ea72`

## pseudocode

```c
__int64 __fastcall HTTP2ServerVirtualConnection::InitializeServerConnection(
        unsigned __int8 *a1,
        unsigned int a2,
        struct BASE_CONNECTION *a3,
        struct HTTP2ServerVirtualConnection **a4,
        int *a5)
{
  struct HTTP2ServerInChannel *v6; // r12
  HTTP2Channel *v7; // r14
  unsigned int v8; // r13d
  __int16 v9; // r8
  unsigned int v10; // r15d
  unsigned __int8 *v11; // rcx
  __int16 v12; // r8
  int v13; // r9d
  __int64 v14; // r10
  unsigned int v15; // esi
  __int128 v16; // xmm6
  unsigned int v17; // ebx
  __int64 result; // rax
  unsigned int v19; // eax
  struct BASE_CONNECTION *v20; // rbx
  struct HTTP2ServerInChannel *v21; // rax
  int v22; // edx
  HTTP2TimeoutTargetConnection *v23; // rcx
  struct HTTP2VirtualConnection *Element; // rsi
  unsigned int v25; // ebx
  HTTP2Channel *v26; // rcx
  unsigned int v27; // edx
  HTTP2TimeoutTargetConnection *v28; // rcx
  int v29; // eax
  unsigned int v30; // edi
  unsigned int v31; // edx
  HTTP2TimeoutTargetConnection *v32; // rcx
  struct TimerContext *v33; // r8
  unsigned int v34; // eax
  __int64 v35; // rdx
  HTTP2TimeoutTargetConnection *v36; // rcx
  struct _RTL_BALANCED_LINKS *v37; // rdx
  PRTL_AVL_TABLE v38; // rcx
  int RightChild; // r8d
  unsigned int started; // edi
  unsigned int v41; // ebx
  void *v42; // rdx
  int v43; // r8d
  struct HTTP2VirtualConnection *v44; // rax
  HTTP2VirtualConnection *v45; // rdi
  int v46; // esi
  int v47; // r13d
  int v48; // r15d
  struct HTTP2SendContext *v49; // rax
  struct HTTP2SendContext *v50; // rbx
  int v51; // eax
  int v52; // esi
  struct _RTL_BALANCED_LINKS *Parent; // rax
  bool v54; // zf
  __int64 v55; // rdx
  __int64 v56; // rcx
  HTTP2VirtualConnection *v57; // rcx
  HTTP2Channel *v58; // rax
  signed int v59; // ebx
  __int128 v60; // xmm0
  __int64 v61; // rdx
  __int64 v62; // rcx
  __int128 v63; // xmm0
  __int64 v64; // rax
  __int64 v65; // rdx
  __int64 v66; // rcx
  __int64 v67; // rdx
  HTTP2VirtualConnection *v68; // rcx
  _DWORD *v69; // rbx
  int v70; // eax
  __int128 v71; // xmm0
  struct _RTL_BALANCED_LINKS *v72; // rdx
  PRTL_AVL_TABLE v73; // rcx
  int v74; // r8d
  struct _RTL_BALANCED_LINKS *v75; // rax
  HTTP2Channel *v76; // rax
  unsigned int v77; // eax
  _QWORD *v78; // rax
  __int64 *v79; // rcx
  __int64 v80; // r8
  _QWORD *v81; // rdx
  __int64 v82; // rax
  HTTP2Channel *v83; // rcx
  int v84; // esi
  struct HTTP2SendContext *v85; // rax
  struct HTTP2SendContext *v86; // rbx
  struct HTTP2VirtualConnection *v87; // rax
  struct HTTP2VirtualConnection *v88; // rsi
  int v89; // edi
  int v90; // r15d
  int v91; // r13d
  struct HTTP2SendContext *v92; // rax
  struct HTTP2SendContext *v93; // rbx
  int v94; // edi
  unsigned int v95; // esi
  struct HTTP2SendContext *v96; // rax
  HTTP2Channel *v97; // rbx
  HTTP2VirtualConnection *v98; // rax
  signed __int32 v99[8]; // [rsp+0h] [rbp-100h] BYREF
  struct HTTP2Cookie *v100; // [rsp+20h] [rbp-E0h]
  struct HTTP2Cookie *v101; // [rsp+28h] [rbp-D8h]
  unsigned int *v102; // [rsp+30h] [rbp-D0h]
  unsigned __int8 NewElement[4]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v104; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v105; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v106; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned int v107; // [rsp+60h] [rbp-A0h]
  unsigned int v108; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v109; // [rsp+68h] [rbp-98h] BYREF
  struct HTTP2ServerInChannel *v110; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v111; // [rsp+78h] [rbp-88h]
  HTTP2ChannelPointer *v112; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v113; // [rsp+88h] [rbp-78h] BYREF
  struct BASE_CONNECTION *v114; // [rsp+90h] [rbp-70h] BYREF
  HTTP2Channel *v115; // [rsp+98h] [rbp-68h] BYREF
  __int128 Buf2; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v117; // [rsp+B0h] [rbp-50h] BYREF
  int *v118; // [rsp+C0h] [rbp-40h]
  _OWORD v119[2]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v120[32]; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD v121[3]; // [rsp+110h] [rbp+10h] BYREF
  int v122; // [rsp+128h] [rbp+28h]

  v114 = a3;
  v110 = 0;
  v115 = 0;
  v118 = a5;
  v122 = 1;
  v6 = 0;
  v121[2] = 0;
  v7 = 0;
  v107 = 0;
  v8 = 0;
  v106 = 0;
  v104 = 0;
  v105 = 0;
  v108 = 0;
  v109 = 0;
  v113 = 0;
  v112 = 0;
  *a5 = 0;
  memset(v119, 0, sizeof(v119));
  if ( a2 < 0x14 )
    return 1728;
  v9 = *((_WORD *)a1 + 8);
  if ( (v9 & 0x10) != 0 )
  {
    v10 = (v9 & 4) != 0 ? 3 : 0;
  }
  else
  {
    if ( (v9 & 8) == 0 )
      return 1728;
    v10 = ((v9 & 4) != 0) + 1;
  }
  v111 = *(_DWORD *)(*((_QWORD *)a3 + 17) + 12LL);
  if ( !v10 )
  {
    if ( a2 >= 0x54 )
    {
      v11 = ValidateRTSPacketCommon(a1, a2);
      if ( v11 )
      {
        if ( *(_WORD *)(v14 + 18) == 5 && v12 == 16 && *(_DWORD *)v11 == 6 )
        {
          v15 = *((_DWORD *)v11 + 1);
          if ( *((_DWORD *)v11 + 2) == 3 )
          {
            v121[0] = *(_QWORD *)(v11 + 12);
            v121[1] = *(_QWORD *)(v11 + 20);
            if ( *((_DWORD *)v11 + 7) == 3 )
            {
              v16 = *((_OWORD *)v11 + 2);
              Buf2 = v16;
              if ( *((_DWORD *)v11 + 12) == v13 )
              {
                v8 = *((_DWORD *)v11 + 13);
                if ( !*((_DWORD *)v11 + 14) )
                {
                  v17 = *((_DWORD *)v11 + 15);
                  v107 = v17;
                  if ( v8 >= 0x20000 )
                  {
                    result = HTTP2ServerVirtualConnection::AllocateAndInitializeOutChannel(&v114, v8, &v115);
                    if ( (_DWORD)result )
                      return result;
                    v7 = v115;
                    HTTP2PlugChannel::Unplug((HTTP2Channel *)((char *)v115 + 88));
                    *((_DWORD *)v7 + 72) = v17;
                    *((_DWORD *)v7 + 71) = v17;
LABEL_31:
                    v20 = v114;
                    v21 = BASE_HTTP2_CONNECTION::From_BASE_CONNECTION(v114);
                    v22 = *((_DWORD *)v20 + 3);
                    v110 = v21;
                    v106 = v15 != 0;
                    if ( (unsigned int)(v22 - 13) > 1 )
                      (*((void (__fastcall **)(struct BASE_CONNECTION *))pRuntimeImportTable + 39))(v20);
                    RtlAcquireSRWLockExclusive(&g_pServerCookieCollection[1].BalancedRoot.LeftChild);
                    Element = CookieCollection::FindElement(
                                (CookieCollection *)g_pServerCookieCollection,
                                (struct HTTP2ServerCookie *)v120);
                    if ( v10 - 2 > 1 )
                    {
                      if ( !Element )
                      {
                        Element = HTTP2ServerVirtualConnection::HTTP2ServerVirtualConnection(
                                    a3,
                                    (struct HTTP2ServerCookie *)v120,
                                    v106);
                        v25 = HTTP2TimeoutTargetConnection::SetTimeout(
                                v28,
                                v27,
                                (struct HTTP2VirtualConnection *)((char *)Element + 280));
                        if ( !v25 )
                        {
                          v23 = (HTTP2TimeoutTargetConnection *)v111;
                          *v118 = 1;
                          if ( (_DWORD)v23 == 12 )
                          {
                            *((_DWORD *)Element + 3) = 11;
                          }
                          else
                          {
                            v29 = 10;
                            if ( (_DWORD)v23 == 13 )
                              v29 = 13;
                            *((_DWORD *)Element + 3) = v29;
                          }
                          *((_DWORD *)Element + 2) = 20;
                          v30 = 1;
LABEL_56:
                          v105 = v30;
                          v104 = 0;
                          *((_QWORD *)v110 + 4) = Element;
                          v34 = *((_DWORD *)Element + 102);
                          if ( v106 < v34 )
                            v34 = v106;
                          *((_DWORD *)Element + 102) = v34;
                          switch ( v10 )
                          {
                            case 0u:
                              _InterlockedOr(v99, 0);
                              if ( *((int *)Element + 50) >= 0 )
                              {
LABEL_60:
                                v25 = 1728;
LABEL_120:
                                (*(void (__fastcall **)(struct HTTP2VirtualConnection *, _QWORD))(*(_QWORD *)Element
                                                                                                + 64LL))(
                                  Element,
                                  0);
                                RtlReleaseSRWLockExclusive(&g_pServerCookieCollection[1].BalancedRoot.LeftChild);
                                return v25;
                              }
                              *((_DWORD *)Element + 103) = v107;
                              *((_DWORD *)Element + 104) = v8;
                              *((_OWORD *)Element + 15) = v16;
                              HTTP2VirtualConnection::SetFirstOutChannel(Element, v7);
                              *((_QWORD *)v7 + 6) = Element;
                              if ( v30 )
                              {
                                LOBYTE(v35) = 61;
                                LOBYTE(v36) = 50;
                                I_RpcLogEvent(v36, v35, Element, 0, 8, 1, 0);
                                *((_DWORD *)Element + 88) = 8;
                                v37 = (struct _RTL_BALANCED_LINKS *)((char *)Element + 56);
                                v38 = g_pServerCookieCollection;
                                RightChild = (int)g_pServerCookieCollection[1].BalancedRoot.RightChild;
                                if ( RightChild )
                                {
                                  if ( RightChild == 1 )
                                  {
                                    g_pServerCookieCollection[1].BalancedRoot.Parent = v37;
                                    NewElement[0] = 0;
                                    RtlInsertElementGenericTableAvl(v38, (char *)Element + 88, 0x10u, NewElement);
                                  }
                                }
                                else
                                {
                                  Parent = g_pServerCookieCollection->BalancedRoot.Parent;
                                  if ( (PRTL_AVL_TABLE)g_pServerCookieCollection->BalancedRoot.Parent->LeftChild != g_pServerCookieCollection )
                                    goto LABEL_131;
                                  v37->Parent = Parent;
                                  *((_QWORD *)Element + 8) = v38;
                                  Parent->LeftChild = v37;
                                  v38->BalancedRoot.Parent = v37;
                                  v54 = LODWORD(v38->BalancedRoot.RightChild)++ == -1;
                                  if ( !v54 )
                                    GenericTable<HTTP2ServerCookie,0,&int DefaultCompareKeys<HTTP2Cookie>(HTTP2Cookie const &,HTTP2Cookie const &)>::SwitchToTree(v38);
                                }
                                goto LABEL_72;
                              }
                              HTTP2TimeoutTargetConnection::CancelTimeout(
                                v36,
                                (struct HTTP2VirtualConnection *)((char *)Element + 280));
                              if ( *((_DWORD *)Element + 88) != 15 )
                                goto LABEL_60;
                              LOBYTE(v55) = 61;
                              LOBYTE(v56) = 50;
                              I_RpcLogEvent(v56, v55, Element, 0, 2, 1, 0);
                              *((_DWORD *)Element + 88) = 2;
                              *((_DWORD *)Element + 100) = 2;
                              goto LABEL_94;
                            case 1u:
                              _InterlockedOr(v99, 0);
                              if ( *((int *)Element + 30) >= 0 )
                                goto LABEL_60;
                              if ( !v30 )
                                HTTP2TimeoutTargetConnection::CancelTimeout(
                                  v23,
                                  (struct HTTP2VirtualConnection *)((char *)Element + 280));
                              v70 = v119[0];
                              *((_DWORD *)Element + 107) = v119[0];
                              if ( v70 )
                                *(_OWORD *)((char *)Element + 440) = *(_OWORD *)((char *)v119 + 12);
                              else
                                *((_DWORD *)Element + 109) = DWORD2(v119[0]);
                              v71 = v117;
                              *((_DWORD *)Element + 116) = v108;
                              *((_DWORD *)Element + 115) = v109;
                              *(_OWORD *)((char *)Element + 472) = v71;
                              *((_OWORD *)Element + 10) = v16;
                              HTTP2VirtualConnection::SetFirstInChannel(Element, v6);
                              *((_QWORD *)v6 + 6) = Element;
                              v69 = (_DWORD *)((char *)Element + 352);
                              break;
                            case 2u:
                              v63 = v117;
                              v104 = *((_DWORD *)Element + 48) ^ 1;
                              v64 = (int)v104;
                              *((_DWORD *)Element + (int)v104 + 116) = v108;
                              *((_DWORD *)Element + 115) = v109;
                              *((_OWORD *)Element + v64 + 10) = v63;
                              HTTP2VirtualConnection::SetNonDefaultInChannel(Element, v6);
                              LODWORD(v102) = 0;
                              LODWORD(v101) = 1;
                              LOBYTE(v65) = 61;
                              LODWORD(v100) = 5;
                              LOBYTE(v66) = 50;
                              *((_QWORD *)v6 + 6) = Element;
                              I_RpcLogEvent(v66, v65, Element, 0, (_DWORD)v100, (_DWORD)v101, (_DWORD)v102);
                              v69 = (_DWORD *)((char *)Element + 352);
                              *((_DWORD *)Element + 88) = 5;
                              break;
                            case 3u:
                              v60 = v117;
                              v104 = *((_DWORD *)Element + 68) ^ 1;
                              v59 = v104;
                              *((_DWORD *)Element + 2 * (int)v104 + 103) = v107;
                              *((_OWORD *)Element + v59 + 15) = v60;
                              HTTP2VirtualConnection::SetNonDefaultOutChannel(Element, v7);
                              LODWORD(v102) = 0;
                              LODWORD(v101) = 1;
                              LODWORD(v100) = 17;
                              LOBYTE(v61) = 61;
                              *((_QWORD *)v7 + 6) = Element;
                              LOBYTE(v62) = 50;
                              I_RpcLogEvent(v62, v61, Element, 1, (_DWORD)v100, (_DWORD)v101, (_DWORD)v102);
                              *((_DWORD *)Element + 100) = 17;
LABEL_94:
                              v58 = HTTP2VirtualConnection::LockDefaultChannel(
                                      v57,
                                      (volatile int *)Element + 48,
                                      (struct HTTP2VirtualConnection *)((char *)Element + 120),
                                      &v112);
                              v6 = v58;
                              if ( v58 )
                              {
                                HTTP2Channel::AddReference(v58);
                                HTTP2ChannelPointer::UnlockChannelPointer(v112);
                                HTTP2Channel::AddReference(v7);
LABEL_72:
                                started = (*(__int64 (__fastcall **)(HTTP2Channel *, __int64))(*(_QWORD *)v7 + 16LL))(
                                            v7,
                                            4);
                                v110 = v7;
LABEL_73:
                                v41 = v105;
                                if ( !v105 || !started )
                                {
LABEL_79:
                                  RtlReleaseSRWLockExclusive(&g_pServerCookieCollection[1].BalancedRoot.LeftChild);
                                  if ( v41 )
                                    return started;
                                  if ( v10 >= 2 )
                                  {
                                    if ( started )
                                      goto LABEL_152;
                                    v44 = HTTP2Channel::LockParentPointer(v7);
                                    v45 = v44;
                                    if ( v10 == 2 )
                                    {
                                      if ( !v44 )
                                      {
                                        started = -1073606638;
                                        goto LABEL_149;
                                      }
                                      v46 = *((_DWORD *)v44 + 115);
                                      v47 = *((_DWORD *)v44 + 102);
                                      v48 = *((_DWORD *)v44 + (int)v104 + 116);
                                      v49 = AllocateAndInitializeRTSPacket(0x20u);
                                      v50 = v49;
                                      if ( v49 )
                                      {
                                        *((_DWORD *)v49 + 30) = 0x40000;
                                        *(_QWORD *)((char *)v49 + 124) = 13;
                                        *((_DWORD *)v49 + 33) = 6;
                                        *((_DWORD *)v49 + 34) = v47;
                                        *((_DWORD *)v49 + 35) = 0;
                                        *((_DWORD *)v49 + 36) = v48;
                                        *((_DWORD *)v49 + 37) = 2;
                                        *((_DWORD *)v49 + 38) = v46;
                                        v51 = (*(__int64 (__fastcall **)(HTTP2Channel *, struct HTTP2SendContext *))(*(_QWORD *)v7 + 8LL))(
                                                v7,
                                                v49);
                                        v52 = v51;
                                        if ( v51 && v51 != -1073606614 )
                                          (*((void (__fastcall **)(struct HTTP2SendContext *))pRuntimeImportTable + 1))(v50);
                                        started = HTTP2VirtualConnection::StartChannelRecyclingIfNecessary(v45, v52, 0);
                                        goto LABEL_133;
                                      }
LABEL_132:
                                      started = 14;
LABEL_133:
                                      v83 = v7;
LABEL_148:
                                      HTTP2Channel::UnlockParentPointer(v83);
LABEL_149:
                                      if ( !started )
                                      {
LABEL_154:
                                        HTTP2Channel::RemoveReference(v6);
                                        HTTP2Channel::RemoveReference(v7);
                                        if ( !started )
                                          return (unsigned int)-1073606647;
                                        return started;
                                      }
LABEL_152:
                                      v97 = v110;
                                      v98 = HTTP2Channel::LockParentPointer(v110);
                                      if ( v98 )
                                      {
                                        HTTP2VirtualConnection::AbortChannels(v98, started);
                                        HTTP2Channel::UnlockParentPointer(v97);
                                      }
                                      goto LABEL_154;
                                    }
                                    if ( v44 )
                                    {
                                      v84 = *((_DWORD *)v44 + 102);
                                      v85 = AllocateAndInitializeRTSPacket(0x18u);
                                      v86 = v85;
                                      if ( v85 )
                                      {
                                        *((_DWORD *)v85 + 30) = 196624;
                                        *(_QWORD *)((char *)v85 + 124) = 13;
                                        *((_DWORD *)v85 + 33) = 6;
                                        *((_DWORD *)v85 + 34) = v84;
                                        *((_DWORD *)v85 + 35) = 2;
                                        *((_DWORD *)v85 + 36) = v113;
                                        started = HTTP2VirtualConnection::SendTrafficOnDefaultChannel(v45, 0, v85);
                                        if ( started )
                                          (*((void (__fastcall **)(struct HTTP2SendContext *))pRuntimeImportTable + 1))(v86);
                                        goto LABEL_133;
                                      }
                                      goto LABEL_132;
                                    }
LABEL_151:
                                    started = -1073606638;
                                    goto LABEL_152;
                                  }
                                  if ( started )
                                    goto LABEL_152;
                                  v87 = HTTP2Channel::LockParentPointer(v6);
                                  v88 = v87;
                                  if ( !v87 )
                                    goto LABEL_151;
                                  v89 = *((_DWORD *)v87 + 115);
                                  v90 = *((_DWORD *)v87 + 116);
                                  v91 = *((_DWORD *)v87 + 102);
                                  v92 = AllocateAndInitializeRTSPacket(0x18u);
                                  v93 = v92;
                                  if ( v92 )
                                  {
                                    *((_WORD *)v92 + 61) = 3;
                                    *((_DWORD *)v92 + 31) = 6;
                                    *((_DWORD *)v92 + 32) = v91;
                                    *((_DWORD *)v92 + 34) = v90;
                                    *((_DWORD *)v92 + 33) = 0;
                                    *((_DWORD *)v92 + 35) = 2;
                                    *((_DWORD *)v92 + 36) = v89;
                                    started = (*(__int64 (__fastcall **)(HTTP2Channel *, struct HTTP2SendContext *))(*(_QWORD *)v7 + 8LL))(
                                                v7,
                                                v92);
                                    if ( started )
                                      goto LABEL_145;
                                    v94 = *((_DWORD *)v88 + 102);
                                    v95 = HTTP2ServerReceiveWindow;
                                    v96 = AllocateAndInitializeRTSPacket(0x10u);
                                    v93 = v96;
                                    if ( v96 )
                                    {
                                      *((_WORD *)v96 + 61) = 2;
                                      *((_DWORD *)v96 + 31) = 0;
                                      *((_DWORD *)v96 + 32) = v95;
                                      *((_DWORD *)v96 + 33) = 6;
                                      *((_DWORD *)v96 + 34) = v94;
                                      started = (*(__int64 (__fastcall **)(struct HTTP2ServerInChannel *, struct HTTP2SendContext *))(*(_QWORD *)v6 + 8LL))(
                                                  v6,
                                                  v96);
                                      if ( !started )
                                      {
LABEL_147:
                                        v83 = v6;
                                        goto LABEL_148;
                                      }
LABEL_145:
                                      (*((void (__fastcall **)(struct HTTP2SendContext *))pRuntimeImportTable + 1))(v93);
                                      goto LABEL_147;
                                    }
                                  }
                                  started = 14;
                                  goto LABEL_147;
                                }
                                v42 = (char *)Element + 88;
                                v43 = (int)g_pServerCookieCollection[1].BalancedRoot.RightChild;
                                if ( v43 )
                                {
                                  if ( v43 == 1 )
                                    RtlDeleteElementGenericTableAvl(g_pServerCookieCollection, v42);
                                  goto LABEL_78;
                                }
                                v78 = (_QWORD *)GenericTable<HTTP2ServerCookie,0,&int DefaultCompareKeys<HTTP2Cookie>(HTTP2Cookie const &,HTTP2Cookie const &)>::ListFind(
                                                  g_pServerCookieCollection,
                                                  v42);
                                if ( !v78 )
                                {
LABEL_78:
                                  *((_BYTE *)Element + 508) = 1;
                                  goto LABEL_79;
                                }
                                v80 = *v78;
                                if ( *(_QWORD **)(*v78 + 8LL) == v78 )
                                {
                                  v81 = (_QWORD *)v78[1];
                                  if ( (_QWORD *)*v81 == v78 )
                                  {
                                    *v81 = v80;
                                    *(_QWORD *)(v80 + 8) = v81;
                                    v82 = *v79;
                                    --*((_DWORD *)v79 + 4);
                                    v79[3] = v82;
                                    goto LABEL_78;
                                  }
                                }
LABEL_131:
                                __fastfail(3u);
                              }
LABEL_119:
                              v25 = -1073606647;
                              goto LABEL_120;
                            default:
LABEL_123:
                              v77 = (*(__int64 (__fastcall **)(struct HTTP2ServerInChannel *, __int64))(*(_QWORD *)v6 + 16LL))(
                                      v6,
                                      1);
                              started = v77;
                              if ( v10 == 1 && !v77 )
                                started = (*(__int64 (__fastcall **)(struct HTTP2ServerInChannel *, __int64))(*(_QWORD *)v6 + 16LL))(
                                            v6,
                                            2);
                              v110 = v6;
                              goto LABEL_73;
                          }
                          if ( v30 )
                          {
                            LOBYTE(v67) = 61;
                            LOBYTE(v68) = 50;
                            I_RpcLogEvent(v68, v67, Element, 0, 15, 1, 0);
                            *v69 = 15;
                            v72 = (struct _RTL_BALANCED_LINKS *)((char *)Element + 56);
                            v73 = g_pServerCookieCollection;
                            v74 = (int)g_pServerCookieCollection[1].BalancedRoot.RightChild;
                            if ( v74 )
                            {
                              if ( v74 == 1 )
                              {
                                g_pServerCookieCollection[1].BalancedRoot.Parent = v72;
                                NewElement[0] = 0;
                                RtlInsertElementGenericTableAvl(v73, (char *)Element + 88, 0x10u, NewElement);
                              }
                            }
                            else
                            {
                              v75 = g_pServerCookieCollection->BalancedRoot.Parent;
                              if ( (PRTL_AVL_TABLE)g_pServerCookieCollection->BalancedRoot.Parent->LeftChild != g_pServerCookieCollection )
                                goto LABEL_131;
                              v72->Parent = v75;
                              *((_QWORD *)Element + 8) = v73;
                              v75->LeftChild = v72;
                              v73->BalancedRoot.Parent = v72;
                              v54 = LODWORD(v73->BalancedRoot.RightChild)++ == -1;
                              if ( !v54 )
                                GenericTable<HTTP2ServerCookie,0,&int DefaultCompareKeys<HTTP2Cookie>(HTTP2Cookie const &,HTTP2Cookie const &)>::SwitchToTree(v73);
                            }
                          }
                          else
                          {
                            if ( v10 == 1 )
                            {
                              if ( *v69 != 8 )
                                goto LABEL_119;
                              LOBYTE(v67) = 61;
                              LOBYTE(v68) = 50;
                              I_RpcLogEvent(v68, v67, Element, 0, 2, 1, 0);
                              *v69 = 2;
                              *((_DWORD *)Element + 100) = 2;
                            }
                            v76 = HTTP2VirtualConnection::LockDefaultChannel(
                                    v68,
                                    (volatile int *)Element + 68,
                                    (struct HTTP2VirtualConnection *)((char *)Element + 200),
                                    &v112);
                            v7 = v76;
                            if ( !v76 )
                              goto LABEL_119;
                            HTTP2Channel::AddReference(v76);
                            HTTP2ChannelPointer::UnlockChannelPointer(v112);
                            HTTP2Channel::AddReference(v6);
                          }
                          goto LABEL_123;
                        }
                        HTTP2ServerVirtualConnection::~HTTP2ServerVirtualConnection(Element);
                        *((_DWORD *)a3 + 4) = 1;
                        *((_QWORD *)a3 + 16) = 0;
                        goto LABEL_36;
                      }
                    }
                    else if ( !Element )
                    {
                      *((_DWORD *)a3 + 4) = 1;
                      v25 = -1073606647;
                      *((_QWORD *)a3 + 16) = 0;
                      goto LABEL_36;
                    }
                    *((_DWORD *)a3 + 4) = 1;
                    *((_QWORD *)a3 + 16) = 0;
                    if ( v10 == 2 )
                    {
                      if ( !memcmp_0((char *)Element + 16 * *((int *)Element + 48) + 160, &Buf2, 0x10u)
                        && *((_DWORD *)Element + 88) == 2
                        && !(unsigned int)HTTP2ServerVirtualConnection::ValidateChannelRecycleRequest(Element, 1) )
                      {
                        v33 = (struct HTTP2VirtualConnection *)((char *)Element + 280);
                        goto LABEL_54;
                      }
                    }
                    else
                    {
                      if ( v10 != 3 )
                        goto LABEL_55;
                      if ( !memcmp_0((char *)Element + 16 * *((int *)Element + 68) + 240, &Buf2, 0x10u)
                        && *((_DWORD *)Element + 100) == 16
                        && !(unsigned int)HTTP2ServerVirtualConnection::ValidateChannelRecycleRequest(Element, 0) )
                      {
                        v33 = (struct HTTP2VirtualConnection *)((char *)Element + 296);
LABEL_54:
                        v25 = HTTP2TimeoutTargetConnection::SetTimeout(v32, v31, v33);
                        if ( !v25 )
                        {
LABEL_55:
                          v30 = 0;
                          goto LABEL_56;
                        }
LABEL_36:
                        RtlReleaseSRWLockExclusive(&g_pServerCookieCollection[1].BalancedRoot.LeftChild);
                        if ( !v10 || v10 == 3 )
                        {
                          (*(void (__fastcall **)(HTTP2Channel *, _QWORD))(*(_QWORD *)v7 + 40LL))(v7, v25);
                          v26 = v7;
                        }
                        else
                        {
                          (*(void (__fastcall **)(struct HTTP2ServerInChannel *, _QWORD))(*(_QWORD *)v6 + 40LL))(
                            v6,
                            v25);
                          v26 = v6;
                        }
                        HTTP2Channel::RemoveReference(v26);
                        return v25;
                      }
                    }
                    v25 = 1728;
                    goto LABEL_36;
                  }
                }
              }
            }
          }
        }
      }
    }
    return 1728;
  }
  if ( v10 != 1 )
  {
    if ( v10 == 2 )
    {
      result = ParseD2_A2(
                 a1,
                 a2,
                 &v104,
                 (struct HTTP2Cookie *)v121,
                 (struct HTTP2Cookie *)&Buf2,
                 (struct HTTP2Cookie *)&v117,
                 &v108,
                 &v109);
      goto LABEL_23;
    }
    result = ParseD4_A4(
               a1,
               a2,
               &v104,
               (struct HTTP2Cookie *)v121,
               (struct HTTP2Cookie *)&Buf2,
               (struct HTTP2Cookie *)&v117,
               &v105,
               &v106,
               &v113);
    if ( (_DWORD)result )
      return result;
    v8 = v105;
    if ( v105 >= 0x20000 )
    {
      result = HTTP2ServerVirtualConnection::AllocateAndInitializeOutChannel(&v114, v105, &v115);
      if ( (_DWORD)result )
        return result;
      v19 = v106;
      v7 = v115;
      v107 = v106;
      *((_DWORD *)v115 + 72) = v106;
      *((_DWORD *)v7 + 71) = v19;
      goto LABEL_30;
    }
    return 1728;
  }
  result = ParseD1_B2(
             a1,
             a2,
             &v104,
             (struct HTTP2Cookie *)v121,
             (struct HTTP2Cookie *)&Buf2,
             &v108,
             &v109,
             (struct HTTP2Cookie *)&v117,
             (struct tagChannelSettingClientAddress *)v119);
LABEL_23:
  if ( !(_DWORD)result )
  {
    result = HTTP2ServerVirtualConnection::AllocateAndInitializeInChannel(&v114, &v110);
    if ( !(_DWORD)result )
    {
      v6 = v110;
LABEL_30:
      v16 = Buf2;
      v15 = v104;
      goto LABEL_31;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000dfe8  mov     rax, rsp
0x18000dfeb  mov     [rax+20h], rbx
0x18000dfef  push    rbp
0x18000dff0  push    rsi
0x18000dff1  push    rdi
0x18000dff2  push    r12
0x18000dff4  push    r13
0x18000dff6  push    r14
0x18000dff8  push    r15
0x18000dffa  lea     rbp, [rsp-50h]
0x18000dfff  sub     rsp, 150h
0x18000e006  movaps  xmmword ptr [rax-48h], xmm6
0x18000e00a  mov     rax, cs:__security_cookie
0x18000e011  xor     rax, rsp
0x18000e014  mov     [rbp+80h+var_50], rax
0x18000e018  xor     ebx, ebx
0x18000e01a  mov     [rbp+80h+var_F0], r8
0x18000e01e  mov     [rsp+180h+var_110], rbx
0x18000e023  xorps   xmm0, xmm0
0x18000e026  mov     [rbp+80h+var_E8], rbx
0x18000e02a  mov     r10, rcx
0x18000e02d  mov     rcx, [rbp+80h+arg_20]
0x18000e034  mov     rdi, r8
0x18000e037  mov     [rbp+80h+var_C0], rcx
0x18000e03b  lea     r11d, [rbx+1]
0x18000e03f  mov     [rbp+80h+var_58], r11d
0x18000e043  mov     r12d, ebx
0x18000e046  mov     [rbp+80h+var_60], rbx
0x18000e04a  mov     r14d, ebx
0x18000e04d  mov     [rsp+180h+var_120], ebx
0x18000e051  mov     r13d, ebx
0x18000e054  mov     [rsp+180h+var_124], ebx
0x18000e058  mov     [rsp+180h+var_12C], ebx
0x18000e05c  mov     [rsp+180h+var_128], ebx
0x18000e060  mov     [rsp+180h+var_11C], ebx
0x18000e064  mov     [rsp+180h+var_118], ebx
0x18000e068  mov     [rbp+80h+var_F8], ebx
0x18000e06b  mov     [rbp+80h+var_100], rbx
0x18000e06f  mov     [rcx], ebx
0x18000e071  movups  [rbp+80h+var_B8], xmm0
0x18000e075  movups  [rbp+80h+var_A8], xmm0
0x18000e079  cmp     edx, 14h
0x18000e07c  jb      loc_18000ED58
0x18000e082  movzx   r8d, word ptr [r10+10h]
0x18000e087  test    r8b, 10h
0x18000e08b  jz      short loc_18000E0A2
0x18000e08d  mov     al, r8b
0x18000e090  lea     r9d, [rbx+4]
0x18000e094  and     al, r9b
0x18000e097  neg     al
0x18000e099  sbb     r15d, r15d
0x18000e09c  and     r15d, 3
0x18000e0a0  jmp     short loc_18000E0C3
0x18000e0a2  test    r8b, 8
0x18000e0a6  jz      loc_18000ED58
0x18000e0ac  mov     al, r8b
0x18000e0af  mov     r9d, 4
0x18000e0b5  and     al, r9b
0x18000e0b8  neg     al
0x18000e0ba  sbb     r15d, r15d
0x18000e0bd  neg     r15d
0x18000e0c0  add     r15d, r11d
0x18000e0c3  mov     rax, [rdi+88h]
0x18000e0ca  mov     esi, 5
0x18000e0cf  mov     eax, [rax+0Ch]
0x18000e0d2  mov     [rsp+180h+var_108], eax
0x18000e0d6  test    r15d, r15d
0x18000e0d9  jnz     loc_18000E1B0
0x18000e0df  cmp     edx, 54h ; 'T'
0x18000e0e2  jb      loc_18000ED58
0x18000e0e8  mov     rcx, r10; unsigned __int8 *
0x18000e0eb  call    ?ValidateRTSPacketCommon@@YAPEAEPEAEK@Z; ValidateRTSPacketCommon(uchar *,ulong)
0x18000e0f0  mov     rcx, rax
0x18000e0f3  test    rax, rax
0x18000e0f6  jz      loc_18000ED58
0x18000e0fc  cmp     [r10+12h], si
0x18000e101  jnz     loc_18000ED58
0x18000e107  lea     eax, [rsi+0Bh]
0x18000e10a  cmp     r8w, ax
0x18000e10e  jnz     loc_18000ED58
0x18000e114  cmp     dword ptr [rcx], 6
0x18000e117  jnz     loc_18000ED58
0x18000e11d  mov     esi, [rcx+4]
0x18000e120  lea     edx, [rax-0Dh]
0x18000e123  cmp     [rcx+8], edx
0x18000e126  jnz     loc_18000ED58
0x18000e12c  mov     rax, [rcx+0Ch]
0x18000e130  mov     [rbp+80h+var_70], rax
0x18000e134  mov     rax, [rcx+14h]
0x18000e138  mov     [rbp+80h+var_68], rax
0x18000e13c  cmp     [rcx+1Ch], edx
0x18000e13f  jnz     loc_18000ED58
0x18000e145  movups  xmm6, xmmword ptr [rcx+20h]
0x18000e149  movups  [rbp+80h+Buf2], xmm6
0x18000e14d  cmp     [rcx+30h], r9d
0x18000e151  jnz     loc_18000ED58
0x18000e157  mov     r13d, [rcx+34h]
0x18000e15b  cmp     [rcx+38h], ebx
0x18000e15e  jnz     loc_18000ED58
0x18000e164  mov     ebx, [rcx+3Ch]
0x18000e167  mov     [rsp+180h+var_120], ebx
0x18000e16b  cmp     r13d, 20000h
0x18000e172  jb      loc_18000ED58
0x18000e178  lea     r8, [rbp+80h+var_E8]; struct HTTP2ServerOutChannel **
0x18000e17c  mov     edx, r13d; unsigned int
0x18000e17f  lea     rcx, [rbp+80h+var_F0]; struct BASE_CONNECTION **
0x18000e183  call    ?AllocateAndInitializeOutChannel@HTTP2ServerVirtualConnection@@SAJPEAPEAVBASE_CONNECTION@@KPEAPEAVHTTP2ServerOutChannel@@@Z; HTTP2ServerVirtualConnection::AllocateAndInitializeOutChannel(BASE_CONNECTION * *,ulong,HTTP2ServerOutChannel * *)
0x18000e188  test    eax, eax
0x18000e18a  jnz     loc_18000ED5D
0x18000e190  mov     r14, [rbp+80h+var_E8]
0x18000e194  lea     rcx, [r14+58h]; this
0x18000e198  call    ?Unplug@HTTP2PlugChannel@@QEAAJXZ; HTTP2PlugChannel::Unplug(void)
0x18000e19d  mov     [r14+120h], ebx
0x18000e1a4  mov     [r14+11Ch], ebx
0x18000e1ab  jmp     loc_18000E2D8
0x18000e1b0  lea     r9, [rbp+80h+var_70]; struct HTTP2Cookie *
0x18000e1b4  mov     rcx, r10; unsigned __int8 *
0x18000e1b7  lea     r8, [rsp+180h+var_12C]; unsigned int *
0x18000e1bc  cmp     r15d, r11d
0x18000e1bf  jnz     short loc_18000E1F7
0x18000e1c1  lea     rax, [rbp+80h+var_B8]
0x18000e1c5  mov     [rsp+180h+var_140], rax; struct tagChannelSettingClientAddress *
0x18000e1ca  lea     rax, [rbp+80h+var_D0]
0x18000e1ce  mov     [rsp+180h+var_148], rax; struct HTTP2Cookie *
0x18000e1d3  lea     rax, [rsp+180h+var_118]
0x18000e1d8  mov     [rsp+180h+var_150], rax; unsigned int *
0x18000e1dd  lea     rax, [rsp+180h+var_11C]
0x18000e1e2  mov     [rsp+180h+var_158], rax; unsigned int *
0x18000e1e7  lea     rax, [rbp+80h+Buf2]
0x18000e1eb  mov     [rsp+180h+var_160], rax; struct HTTP2Cookie *
0x18000e1f0  call    ?ParseD1_B2@@YAJPEAEKPEAKPEAVHTTP2Cookie@@2112PEAUtagChannelSettingClientAddress@@@Z; ParseD1_B2(uchar *,ulong,ulong *,HTTP2Cookie *,HTTP2Cookie *,ulong *,ulong *,HTTP2Cookie *,tagChannelSettingClientAddress *)
0x18000e1f5  jmp     short loc_18000E228
0x18000e1f7  cmp     r15d, 2
0x18000e1fb  jnz     short loc_18000E250
0x18000e1fd  lea     rax, [rsp+180h+var_118]
0x18000e202  mov     [rsp+180h+var_148], rax; unsigned int *
0x18000e207  lea     rax, [rsp+180h+var_11C]
0x18000e20c  mov     [rsp+180h+var_150], rax; unsigned int *
0x18000e211  lea     rax, [rbp+80h+var_D0]
0x18000e215  mov     [rsp+180h+var_158], rax; struct HTTP2Cookie *
0x18000e21a  lea     rax, [rbp+80h+Buf2]
0x18000e21e  mov     [rsp+180h+var_160], rax; struct HTTP2Cookie *
0x18000e223  call    ?ParseD2_A2@@YAJPEAEKPEAKPEAVHTTP2Cookie@@2211@Z; ParseD2_A2(uchar *,ulong,ulong *,HTTP2Cookie *,HTTP2Cookie *,HTTP2Cookie *,ulong *,ulong *)
0x18000e228  test    eax, eax
0x18000e22a  jnz     loc_18000ED5D
0x18000e230  lea     rdx, [rsp+180h+var_110]; struct HTTP2ServerInChannel **
0x18000e235  lea     rcx, [rbp+80h+var_F0]; struct BASE_CONNECTION **
0x18000e239  call    ?AllocateAndInitializeInChannel@HTTP2ServerVirtualConnection@@SAJPEAPEAVBASE_CONNECTION@@PEAPEAVHTTP2ServerInChannel@@@Z; HTTP2ServerVirtualConnection::AllocateAndInitializeInChannel(BASE_CONNECTION * *,HTTP2ServerInChannel * *)
0x18000e23e  test    eax, eax
0x18000e240  jnz     loc_18000ED5D
0x18000e246  mov     r12, [rsp+180h+var_110]
0x18000e24b  jmp     loc_18000E2D0
0x18000e250  lea     rax, [rbp+80h+var_F8]
0x18000e254  mov     [rsp+180h+var_140], rax; unsigned int *
0x18000e259  lea     rax, [rsp+180h+var_124]
0x18000e25e  mov     [rsp+180h+var_148], rax; unsigned int *
0x18000e263  lea     rax, [rsp+180h+var_128]
0x18000e268  mov     [rsp+180h+var_150], rax; unsigned int *
0x18000e26d  lea     rax, [rbp+80h+var_D0]
0x18000e271  mov     [rsp+180h+var_158], rax; struct HTTP2Cookie *
0x18000e276  lea     rax, [rbp+80h+Buf2]
0x18000e27a  mov     [rsp+180h+var_160], rax; struct HTTP2Cookie *
0x18000e27f  call    ?ParseD4_A4@@YAJPEAEKPEAKPEAVHTTP2Cookie@@22111@Z; ParseD4_A4(uchar *,ulong,ulong *,HTTP2Cookie *,HTTP2Cookie *,HTTP2Cookie *,ulong *,ulong *,ulong *)
0x18000e284  test    eax, eax
0x18000e286  jnz     loc_18000ED5D
0x18000e28c  mov     r13d, [rsp+180h+var_128]
0x18000e291  cmp     r13d, 20000h
0x18000e298  jb      loc_18000ED58
0x18000e29e  lea     r8, [rbp+80h+var_E8]; struct HTTP2ServerOutChannel **
0x18000e2a2  mov     edx, r13d; unsigned int
0x18000e2a5  lea     rcx, [rbp+80h+var_F0]; struct BASE_CONNECTION **
0x18000e2a9  call    ?AllocateAndInitializeOutChannel@HTTP2ServerVirtualConnection@@SAJPEAPEAVBASE_CONNECTION@@KPEAPEAVHTTP2ServerOutChannel@@@Z; HTTP2ServerVirtualConnection::AllocateAndInitializeOutChannel(BASE_CONNECTION * *,ulong,HTTP2ServerOutChannel * *)
0x18000e2ae  test    eax, eax
0x18000e2b0  jnz     loc_18000ED5D
0x18000e2b6  mov     eax, [rsp+180h+var_124]
0x18000e2ba  mov     r14, [rbp+80h+var_E8]
0x18000e2be  mov     [rsp+180h+var_120], eax
0x18000e2c2  mov     [r14+120h], eax
0x18000e2c9  mov     [r14+11Ch], eax
0x18000e2d0  movups  xmm6, [rbp+80h+Buf2]
0x18000e2d4  mov     esi, [rsp+180h+var_12C]
0x18000e2d8  mov     rbx, [rbp+80h+var_F0]
0x18000e2dc  mov     rcx, rbx; struct BASE_CONNECTION *
0x18000e2df  call    ?From_BASE_CONNECTION@BASE_HTTP2_CONNECTION@@SAPEAV1@PEAVBASE_CONNECTION@@@Z; BASE_HTTP2_CONNECTION::From_BASE_CONNECTION(BASE_CONNECTION *)
0x18000e2e4  mov     edx, [rbx+0Ch]
0x18000e2e7  mov     r8d, 1
0x18000e2ed  cmp     esi, r8d
0x18000e2f0  mov     [rsp+180h+var_110], rax
0x18000e2f5  cmovnb  esi, r8d
0x18000e2f9  sub     edx, 0Dh
0x18000e2fc  mov     [rsp+180h+var_124], esi
0x18000e300  cmp     edx, r8d
0x18000e303  jbe     short loc_18000E31B
0x18000e305  mov     rdx, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x18000e30c  mov     rcx, rbx
0x18000e30f  mov     rax, [rdx+138h]
0x18000e316  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e31b  mov     rcx, cs:?g_pServerCookieCollection@@3PEAVCookieCollection@@EA; CookieCollection * g_pServerCookieCollection
0x18000e322  add     rcx, 70h ; 'p'
0x18000e326  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000e32c  mov     rcx, cs:?g_pServerCookieCollection@@3PEAVCookieCollection@@EA; this
0x18000e333  lea     rdx, [rbp+80h+var_90]; struct HTTP2ServerCookie *
0x18000e337  call    ?FindElement@CookieCollection@@QEAAPEAVHTTP2VirtualConnection@@PEAVHTTP2ServerCookie@@@Z; CookieCollection::FindElement(HTTP2ServerCookie *)
0x18000e33c  mov     rsi, rax
0x18000e33f  mov     ebx, 1
0x18000e344  lea     eax, [r15-2]
0x18000e348  cmp     eax, ebx
0x18000e34a  ja      short loc_18000E3A2
0x18000e34c  test    rsi, rsi
0x18000e34f  jnz     loc_18000E42B
0x18000e355  mov     [rdi+10h], ebx
0x18000e358  mov     ebx, 0C0021009h
0x18000e35d  mov     [rdi+80h], rsi
0x18000e364  mov     rcx, cs:?g_pServerCookieCollection@@3PEAVCookieCollection@@EA; CookieCollection * g_pServerCookieCollection
0x18000e36b  add     rcx, 70h ; 'p'
0x18000e36f  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000e375  test    r15d, r15d
0x18000e378  jz      loc_18000E54C
0x18000e37e  cmp     r15d, 3
0x18000e382  jz      loc_18000E54C
0x18000e388  mov     rax, [r12]
0x18000e38c  mov     edx, ebx
0x18000e38e  mov     rcx, r12
0x18000e391  mov     rax, [rax+28h]
0x18000e395  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e39a  mov     rcx, r12
0x18000e39d  jmp     loc_18000E560
0x18000e3a2  test    rsi, rsi
0x18000e3a5  jnz     loc_18000E42B
0x18000e3ab  mov     r8d, [rsp+180h+var_124]; unsigned int
0x18000e3b0  lea     rdx, [rbp+80h+var_90]; struct HTTP2ServerCookie *
0x18000e3b4  mov     rcx, rdi; this
0x18000e3b7  call    ??0HTTP2ServerVirtualConnection@@QEAA@PEAVHTTP2ServerCookie@@K@Z; HTTP2ServerVirtualConnection::HTTP2ServerVirtualConnection(HTTP2ServerCookie *,ulong)
0x18000e3bc  mov     rsi, rax
0x18000e3bf  lea     r8, [rax+118h]; struct TimerContext *
0x18000e3c6  call    ?SetTimeout@HTTP2TimeoutTargetConnection@@QEAAJKPEAUTimerContext@@@Z; HTTP2TimeoutTargetConnection::SetTimeout(ulong,TimerContext *)
0x18000e3cb  mov     ebx, eax
0x18000e3cd  test    eax, eax
0x18000e3cf  jz      short loc_18000E3F0
0x18000e3d1  mov     rcx, rsi; this
0x18000e3d4  call    ??1HTTP2ServerVirtualConnection@@UEAA@XZ; HTTP2ServerVirtualConnection::~HTTP2ServerVirtualConnection(void)
0x18000e3d9  mov     dword ptr [rdi+10h], 1
0x18000e3e0  mov     qword ptr [rdi+80h], 0
0x18000e3eb  jmp     loc_18000E364
0x18000e3f0  mov     rax, [rbp+80h+var_C0]
0x18000e3f4  mov     r8d, 1
0x18000e3fa  mov     ecx, [rsp+180h+var_108]
0x18000e3fe  mov     [rax], r8d
0x18000e401  cmp     ecx, 0Ch
0x18000e404  jnz     short loc_18000E40F
0x18000e406  mov     dword ptr [rsi+0Ch], 0Bh
0x18000e40d  jmp     short loc_18000E41F
0x18000e40f  mov     eax, 0Ah
0x18000e414  lea     edx, [rax+3]
0x18000e417  cmp     ecx, edx
0x18000e419  cmovz   eax, edx
0x18000e41c  mov     [rsi+0Ch], eax
0x18000e41f  mov     dword ptr [rsi+8], 14h
0x18000e426  mov     edi, r8d
0x18000e429  jmp     short loc_18000E4A2
0x18000e42b  mov     [rdi+10h], ebx
0x18000e42e  mov     qword ptr [rdi+80h], 0
0x18000e439  mov     edi, 2
0x18000e43e  cmp     r15d, edi
0x18000e441  jnz     loc_18000E4F2
0x18000e447  movsxd  rcx, dword ptr [rsi+0C0h]
0x18000e44e  lea     r8d, [rdi+0Eh]; Size
0x18000e452  add     rcx, 0Ah
0x18000e456  lea     rdx, [rbp+80h+Buf2]; Buf2
0x18000e45a  shl     rcx, 4
0x18000e45e  add     rcx, rsi; Buf1
0x18000e461  call    memcmp_0
0x18000e466  test    eax, eax
0x18000e468  jz      short loc_18000E474
0x18000e46a  mov     ebx, 6C0h
0x18000e46f  jmp     loc_18000E364
0x18000e474  cmp     [rsi+160h], edi
0x18000e47a  jnz     short loc_18000E46A
0x18000e47c  mov     edx, ebx; int
0x18000e47e  mov     rcx, rsi; this
0x18000e481  call    ?ValidateChannelRecycleRequest@HTTP2ServerVirtualConnection@@AEAAJH@Z; HTTP2ServerVirtualConnection::ValidateChannelRecycleRequest(int)
0x18000e486  test    eax, eax
0x18000e488  jnz     short loc_18000E46A
0x18000e48a  lea     r8, [rsi+118h]; struct TimerContext *
0x18000e491  call    ?SetTimeout@HTTP2TimeoutTargetConnection@@QEAAJKPEAUTimerContext@@@Z; HTTP2TimeoutTargetConnection::SetTimeout(ulong,TimerContext *)
0x18000e496  mov     ebx, eax
0x18000e498  test    eax, eax
0x18000e49a  jnz     loc_18000E364
0x18000e4a0  xor     edi, edi
0x18000e4a2  mov     rax, [rsp+180h+var_110]
0x18000e4a7  mov     [rsp+180h+var_128], edi
0x18000e4ab  mov     [rsp+180h+var_12C], 0
0x18000e4b3  mov     [rax+20h], rsi
0x18000e4b7  mov     eax, [rsi+198h]
0x18000e4bd  cmp     [rsp+180h+var_124], eax
0x18000e4c1  cmovb   eax, [rsp+180h+var_124]
0x18000e4c6  mov     [rsi+198h], eax
0x18000e4cc  test    r15d, r15d
0x18000e4cf  jnz     loc_18000E81F
0x18000e4d5  lock or [rsp+180h+var_180], r15d
  ... truncated ...
```
