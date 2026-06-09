# CWcnPeerCache::AliasPeer(_GUID const *,CWcnPeer *)

- ea: `0x18000dcc8`
- end: `0x18000e5d8`
- name: `?AliasPeer@CWcnPeerCache@@QEAAJPEBU_GUID@@PEAVCWcnPeer@@@Z`
- size: `2320`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, const struct _GUID *, struct CWcnPeer *)`
- caller_count: `1`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x18000c58c`

## callees

- `0x180004f78`
- `0x180004fb8`
- `0x180005014`
- `0x18000ce18`
- `0x18000ce94`
- `0x18000d6b8`
- `0x18000db10`
- `0x18000dcc8`
- `0x18000eac0`
- `0x18000ed90`
- `0x18000f03c`
- `0x18000f5e4`
- `0x18000fe00`
- `0x18001028c`
- `0x1800104b8`
- `0x18001daa4`
- `0x18001db40`
- `0x18001de10`
- `0x180053004`
- `0x180056e30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ddb3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ddb3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000de08`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000de08`
- `RPCRT4!UuidCreate` at `0x18000e2b8`
- `RPCRT4!UuidCreate` at `0x18000e2b8`

## pseudocode

```c
__int64 __fastcall CWcnPeerCache::AliasPeer(
        LPCRITICAL_SECTION lpCriticalSection,
        struct _GUID *a2,
        struct CWcnPeer *a3)
{
  _BYTE *v6; // r10
  const char *Indent; // rax
  __int64 v8; // r10
  __int64 v9; // rdx
  const char *v10; // r9
  signed int v12; // r12d
  unsigned int v13; // eax
  __int64 v14; // r10
  LPCRITICAL_SECTION v15; // r13
  unsigned int v16; // eax
  __int64 v17; // r10
  __int64 v18; // rax
  __int64 v19; // r8
  bool *v20; // r9
  unsigned __int8 v21; // al
  __int64 *v22; // rbx
  CWcnPeer *v23; // r13
  unsigned int v24; // eax
  __int64 v25; // r11
  _BYTE *v26; // r11
  const char *v27; // rax
  __int64 v28; // r11
  const char *v29; // rax
  __int64 v30; // r11
  const char *v31; // rax
  __int64 v32; // r11
  const char *v33; // rax
  __int64 v34; // r11
  __int64 v35; // rdx
  const char *v36; // rax
  __int64 v37; // r11
  __int64 v38; // rdx
  const char *v39; // rax
  __int64 v40; // rdx
  __int64 v41; // r11
  __int64 v42; // rcx
  CWcnPeer *v43; // rcx
  unsigned int v44; // r14d
  _QWORD *p_DebugInfo; // rax
  __int64 *v46; // rbx
  struct _GUID *v47; // r12
  const char *v48; // rax
  __int64 v49; // r10
  const char *v50; // rax
  __int64 v51; // r11
  __int64 *v52; // rax
  __int64 *i; // rcx
  __int64 *v54; // rdx
  __int64 ***v55; // r14
  const char *v56; // rax
  __int64 v57; // r10
  RPC_STATUS v58; // eax
  __int64 v59; // r10
  bool *v60; // r9
  const char *v61; // rax
  __int64 v62; // r10
  unsigned int v63; // eax
  __int64 v64; // r10
  __int64 ***v65; // r14
  __int64 v66; // rax
  __int64 v67; // r8
  const char *v68; // rax
  __int64 v69; // r10
  _BYTE *v70; // rax
  __int64 *v71; // rcx
  __int64 *j; // rax
  unsigned int v73; // eax
  __int64 v74; // r10
  int v75; // edx
  int v76; // r8d
  const char *v77; // rax
  __int64 v78; // r10
  int v79; // eax
  __int64 v80; // rax
  bool v81; // [rsp+40h] [rbp-B8h] BYREF
  __int64 *v82; // [rsp+48h] [rbp-B0h] BYREF
  CWcnPeer *v83; // [rsp+50h] [rbp-A8h]
  LPCRITICAL_SECTION lpCriticalSectiona; // [rsp+58h] [rbp-A0h]
  struct _GUID *v85; // [rsp+60h] [rbp-98h]
  LPCRITICAL_SECTION v86; // [rsp+68h] [rbp-90h]
  __int64 *v87; // [rsp+70h] [rbp-88h] BYREF
  unsigned __int8 v88; // [rsp+78h] [rbp-80h]
  LPCRITICAL_SECTION v89; // [rsp+80h] [rbp-78h]
  std::bad_alloc *v90; // [rsp+88h] [rbp-70h] BYREF
  UUID Uuid; // [rsp+90h] [rbp-68h] BYREF
  struct _GUID v92; // [rsp+A0h] [rbp-58h] BYREF
  struct CWcnPeer *v93; // [rsp+B0h] [rbp-48h]

  v83 = a3;
  v85 = a2;
  lpCriticalSectiona = lpCriticalSection;
  v89 = lpCriticalSection;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v8 + 16), 22, WPP_f34e634574083547aa3a426270948a29_Traceguids, Indent);
    v6 = WPP_GLOBAL_Control;
  }
  if ( !a2 )
  {
    if ( v6 == (_BYTE *)&WPP_GLOBAL_Control || v6[25] < 2u )
      return 2147500035LL;
    v9 = 23;
    v10 = "pNewPeerGuid";
LABEL_12:
    WPP_SF_s(*((_QWORD *)v6 + 2), v9, WPP_f34e634574083547aa3a426270948a29_Traceguids, v10);
    return 2147500035LL;
  }
  if ( !a3 )
  {
    if ( v6 == (_BYTE *)&WPP_GLOBAL_Control || v6[25] < 2u )
      return 2147500035LL;
    v9 = 24;
    v10 = "pPeer";
    goto LABEL_12;
  }
  v12 = 0;
  EnterCriticalSection(lpCriticalSection);
  if ( *((_DWORD *)a3 + 74) == 1 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      v15 = lpCriticalSection;
      goto LABEL_19;
    }
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v13 = (unsigned int)GetIndent(0);
      WPP_SF_s_guid_(*(_QWORD *)(v14 + 16), 25, (int)WPP_f34e634574083547aa3a426270948a29_Traceguids, v13, (__int64)a2);
    }
    goto LABEL_18;
  }
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    v92 = *a2;
    v93 = a3;
    v86 = lpCriticalSection + 2;
    v18 = std::_Tree_buy<std::pair<_GUID const,CWcnPeer *>>::_Buynode<std::pair<_GUID const,CWcnPeer *> &>(
            &lpCriticalSection[2],
            &v92);
    std::_Tree<std::_Tmap_traits<_GUID,CWcnPeer *,GuidCompare,std::allocator<std::pair<_GUID const,CWcnPeer *>>,0>>::_Insert_nohint<std::pair<_GUID const,CWcnPeer *> &,std::_Tree_node<std::pair<_GUID const,CWcnPeer *>,void *> *>(
      (__int64 ***)&lpCriticalSection[2],
      (__int64)&v87,
      v19,
      (const void *)(v18 + 32),
      (void *)v18);
    v21 = v88;
    if ( v88 )
      goto LABEL_151;
    v22 = v87;
    v23 = (CWcnPeer *)v87[6];
    if ( v83 == v23 )
      goto LABEL_151;
    LODWORD(v82) = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v24 = (unsigned int)GetIndent(0);
      WPP_SF_s_guid_(*(_QWORD *)(v25 + 16), 26, (int)WPP_f34e634574083547aa3a426270948a29_Traceguids, v24, (__int64)v85);
    }
    CWcnPeer::GetBestTransport(v83, 0, (enum tagWcnTransportId *)&v82);
    if ( (_DWORD)v82 == 5 || (_DWORD)v82 == 6 )
    {
      if ( v26 != (_BYTE *)&WPP_GLOBAL_Control )
      {
        if ( v26[25] >= 4u )
        {
          v36 = GetIndent(0);
          v38 = 27;
          goto LABEL_75;
        }
LABEL_77:
        if ( v26 != (_BYTE *)&WPP_GLOBAL_Control && v26[25] >= 4u )
        {
          v50 = GetIndent(0);
          WPP_SF_s(*(_QWORD *)(v51 + 16), 34, WPP_f34e634574083547aa3a426270948a29_Traceguids, v50);
        }
      }
    }
    else
    {
      LODWORD(v82) = 0;
      CWcnPeer::GetBestTransport(v23, 0, (enum tagWcnTransportId *)&v82);
      if ( (_DWORD)v82 == 5 || (_DWORD)v82 == 6 )
      {
        if ( v26 == (_BYTE *)&WPP_GLOBAL_Control )
          goto LABEL_60;
        if ( v26[25] < 4u )
          goto LABEL_56;
        v33 = GetIndent(0);
        v35 = 28;
        goto LABEL_55;
      }
      if ( v26 != (_BYTE *)&WPP_GLOBAL_Control && v26[25] >= 4u )
      {
        v27 = GetIndent(0);
        WPP_SF_s(*(_QWORD *)(v28 + 16), 29, WPP_f34e634574083547aa3a426270948a29_Traceguids, v27);
        v26 = WPP_GLOBAL_Control;
      }
      if ( *((_DWORD *)v83 + 73) )
      {
        if ( v26 != (_BYTE *)&WPP_GLOBAL_Control && v26[25] >= 4u )
        {
          v29 = GetIndent(0);
          WPP_SF_s(*(_QWORD *)(v30 + 16), 30, WPP_f34e634574083547aa3a426270948a29_Traceguids, v29);
          v26 = WPP_GLOBAL_Control;
        }
        if ( !*((_DWORD *)v23 + 73) )
          goto LABEL_77;
        if ( v26 != (_BYTE *)&WPP_GLOBAL_Control && v26[25] >= 4u )
        {
          v31 = GetIndent(0);
          WPP_SF_s(*(_QWORD *)(v32 + 16), 31, WPP_f34e634574083547aa3a426270948a29_Traceguids, v31);
        }
        CWcnPeer::SetTargetedDiscoveryPeerValue(v23, 0);
        goto LABEL_76;
      }
      if ( *((_DWORD *)v23 + 73) )
      {
        if ( v26 == (_BYTE *)&WPP_GLOBAL_Control )
          goto LABEL_60;
        if ( v26[25] < 4u )
          goto LABEL_56;
        v33 = GetIndent(0);
        v35 = 32;
LABEL_55:
        WPP_SF_s(*(_QWORD *)(v34 + 16), v35, WPP_f34e634574083547aa3a426270948a29_Traceguids, v33);
        v26 = WPP_GLOBAL_Control;
LABEL_56:
        if ( v26 != (_BYTE *)&WPP_GLOBAL_Control && v26[25] >= 4u )
        {
          v39 = GetIndent(0);
          v40 = 39;
          v42 = *(_QWORD *)(v41 + 16);
LABEL_59:
          WPP_SF_s(v42, v40, WPP_f34e634574083547aa3a426270948a29_Traceguids, v39);
        }
        goto LABEL_60;
      }
      if ( v26 != (_BYTE *)&WPP_GLOBAL_Control )
      {
        if ( v26[25] >= 4u )
        {
          v36 = GetIndent(0);
          v38 = 33;
LABEL_75:
          WPP_SF_s(*(_QWORD *)(v37 + 16), v38, WPP_f34e634574083547aa3a426270948a29_Traceguids, v36);
LABEL_76:
          v26 = WPP_GLOBAL_Control;
          goto LABEL_77;
        }
        goto LABEL_77;
      }
    }
    v52 = *(__int64 **)&v86->DebugInfo->Type;
    while ( 1 )
    {
      while ( 1 )
      {
        do
        {
          if ( v52 == (__int64 *)v86->DebugInfo )
          {
            LODWORD(v82) = 0;
            Uuid = 0;
            v55 = (__int64 ***)lpCriticalSectiona;
            if ( (int)CWcnPeerCache::GetPeerNotificationFilter(
                        (CWcnPeerCache *)lpCriticalSectiona,
                        v85,
                        (unsigned int *)&v82,
                        0) < 0
              && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
            {
              v56 = GetIndent(0);
              WPP_SF_s(*(_QWORD *)(v57 + 16), 35, WPP_f34e634574083547aa3a426270948a29_Traceguids, v56);
            }
            v58 = UuidCreate(&Uuid);
            if ( !v58 || v58 == 1824 )
            {
              *std::map<_GUID,CWcnPeer *,GuidCompare,std::allocator<std::pair<_GUID const,CWcnPeer *>>>::operator[](
                 v55 + 10,
                 (__int128 *)&Uuid) = (__int64)v23;
              v12 = CWcnPeerCache::SetPeerNotificationFilter((CWcnPeerCache *)v55, &Uuid, (unsigned int)v82, v60);
              if ( v12 >= 0 )
              {
                ++*((_DWORD *)v23 + 67);
                *((_DWORD *)v23 + 74) = 1;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                {
                  v63 = (unsigned int)GetIndent(0);
                  WPP_SF_sd(
                    *(_QWORD *)(v64 + 16),
                    31,
                    (unsigned int)WPP_805ccd1b393d3e4b99a4efc8134fe3a0_Traceguids,
                    v63,
                    1);
                }
                goto LABEL_113;
              }
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
              {
                v61 = GetIndent(0);
                WPP_SF_s(*(_QWORD *)(v62 + 16), 37, WPP_f34e634574083547aa3a426270948a29_Traceguids, v61);
              }
              std::_Tree<std::_Tmap_traits<_GUID,CWcnPeer *,GuidCompare,std::allocator<std::pair<_GUID const,CWcnPeer *>>,0>>::erase(
                (__int64 *)v86,
                &Uuid);
            }
            else
            {
              v12 = -2147467259;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
              {
                v39 = GetIndent(0);
                v40 = 36;
                v42 = *(_QWORD *)(v59 + 16);
                goto LABEL_59;
              }
            }
LABEL_60:
            v21 = v88;
            goto LABEL_151;
          }
          if ( v23 == (CWcnPeer *)v52[6] && (*(_QWORD *)&v85->Data1 != v52[4] || *(_QWORD *)v85->Data4 != v52[5]) )
          {
            v55 = (__int64 ***)lpCriticalSectiona;
LABEL_113:
            CWcnPeer::CacheUnref(v23);
            CWcnPeerCache::DeletePeerNotificationFilter((struct _RTL_CRITICAL_SECTION *)v55, v85);
            v65 = (__int64 ***)v86;
            std::_Tree<std::_Tmap_traits<_GUID,CWcnWfdGoPeer const *,GuidCompare,std::allocator<std::pair<_GUID const,CWcnWfdGoPeer const *>>,0>>::erase(
              v86,
              &v82,
              v22);
            v66 = std::_Tree_buy<std::pair<_GUID const,CWcnPeer *>>::_Buynode<std::pair<_GUID const,CWcnPeer *> &>(
                    v65,
                    &v92);
            std::_Tree<std::_Tmap_traits<_GUID,CWcnPeer *,GuidCompare,std::allocator<std::pair<_GUID const,CWcnPeer *>>,0>>::_Insert_nohint<std::pair<_GUID const,CWcnPeer *> &,std::_Tree_node<std::pair<_GUID const,CWcnPeer *>,void *> *>(
              v65,
              (__int64)&Uuid,
              v67,
              (const void *)(v66 + 32),
              (void *)v66);
            v21 = Uuid.Data4[0];
            v81 = Uuid.Data4[0];
            if ( !Uuid.Data4[0]
              && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v68 = GetIndent(0);
              WPP_SF_s(*(_QWORD *)(v69 + 16), 38, WPP_f34e634574083547aa3a426270948a29_Traceguids, v68);
              v21 = v81;
            }
            goto LABEL_151;
          }
        }
        while ( *((_BYTE *)v52 + 25) );
        i = (__int64 *)v52[2];
        if ( !*((_BYTE *)i + 25) )
          break;
        for ( i = (__int64 *)v52[1]; !*((_BYTE *)i + 25) && v52 == (__int64 *)i[2]; i = (__int64 *)i[1] )
          v52 = i;
LABEL_94:
        v52 = i;
      }
      v54 = (__int64 *)*i;
      if ( *(_BYTE *)(*i + 25) )
        goto LABEL_94;
      do
      {
        v52 = v54;
        v54 = (__int64 *)*v54;
      }
      while ( !*((_BYTE *)v54 + 25) );
    }
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', &v90) )
    {
      LODWORD(v82) = -2147024882;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v80 = (*(__int64 (__fastcall **)(std::bad_alloc *))(*(_QWORD *)v90 + 8LL))(v90);
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_f34e634574083547aa3a426270948a29_Traceguids, v80);
      }
      v12 = (int)v82;
      v15 = v89;
      __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_18000E5B0);
      goto LABEL_19;
    }
  }
LABEL_151:
  if ( v12 < 0 )
  {
LABEL_18:
    v15 = lpCriticalSectiona;
    goto LABEL_19;
  }
  v15 = lpCriticalSectiona;
  if ( !v21 )
    goto LABEL_19;
  v43 = v83;
  ++*((_DWORD *)v83 + 67);
  v44 = 0;
  p_DebugInfo = &v86->DebugInfo;
  v46 = *(__int64 **)&v86->DebugInfo->Type;
  while ( 1 )
  {
    if ( v46 == (__int64 *)*p_DebugInfo )
    {
      v47 = v85;
      goto LABEL_140;
    }
    if ( v43 == (CWcnPeer *)v46[6] )
      break;
LABEL_120:
    if ( !*((_BYTE *)v46 + 25) )
    {
      v70 = (_BYTE *)v46[2];
      if ( v70[25] )
      {
        for ( j = (__int64 *)v46[1]; !*((_BYTE *)j + 25) && v46 == (__int64 *)j[2]; j = (__int64 *)j[1] )
          v46 = j;
        v46 = j;
        p_DebugInfo = &v15[2].DebugInfo;
      }
      else
      {
        v71 = *(__int64 **)v70;
        if ( *(_BYTE *)(*(_QWORD *)v70 + 25LL) )
        {
          v46 = (__int64 *)v46[2];
        }
        else
        {
          do
          {
            v46 = v71;
            v71 = (__int64 *)*v71;
          }
          while ( !*((_BYTE *)v71 + 25) );
        }
        p_DebugInfo = &v15[2].DebugInfo;
        v43 = v83;
      }
    }
  }
  v47 = v85;
  if ( *(_QWORD *)&v85->Data1 == v46[4] && *(_QWORD *)v85->Data4 == v46[5] )
  {
LABEL_119:
    p_DebugInfo = &v15[2].DebugInfo;
    goto LABEL_120;
  }
  LODWORD(v82) = 0;
  v81 = 0;
  Uuid = (UUID)*((_OWORD *)v46 + 2);
  if ( (int)CWcnPeerCache::GetPeerNotificationFilter((CWcnPeerCache *)v15, &Uuid, (unsigned int *)&v82, &v81) < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      v48 = GetIndent(0);
      WPP_SF_s(*(_QWORD *)(v49 + 16), 41, WPP_f34e634574083547aa3a426270948a29_Traceguids, v48);
    }
    goto LABEL_118;
  }
  if ( v81 )
  {
LABEL_118:
    v43 = v83;
    goto LABEL_119;
  }
  v44 = (unsigned int)v82;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v73 = (unsigned int)GetIndent(0);
    WPP_SF_s_guid__guid_D(*(_QWORD *)(v74 + 16), v75, v76, v73, (__int64)&Uuid, (__int64)v47, v44);
  }
  if ( (int)CWcnPeerCache::MarkStalePeerGuidNotificationFilter((CWcnPeerCache *)v15, &Uuid) < 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    v77 = GetIndent(0);
    WPP_SF_s(*(_QWORD *)(v78 + 16), 43, WPP_f34e634574083547aa3a426270948a29_Traceguids, v77);
  }
LABEL_140:
  v79 = CWcnPeerCache::SetPeerNotificationFilter((CWcnPeerCache *)v15, v47, v44, v20);
  v12 = v79;
  if ( v79 < 0 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      44,
      WPP_f34e634574083547aa3a426270948a29_Traceguids,
      (unsigned int)v79);
LABEL_19:
  LeaveCriticalSection(v15);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (v12 < 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u) )
  {
    v16 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v17 + 16), 45, (unsigned int)WPP_f34e634574083547aa3a426270948a29_Traceguids, v16, v12);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000dcc8  push    rbx
0x18000dcca  push    rsi
0x18000dccb  push    rdi
0x18000dccc  push    r12
0x18000dcce  push    r13
0x18000dcd0  push    r14
0x18000dcd2  push    r15
0x18000dcd4  sub     rsp, 0C0h
0x18000dcdb  mov     rax, cs:__security_cookie
0x18000dce2  xor     rax, rsp
0x18000dce5  mov     [rsp+0F8h+var_40], rax
0x18000dced  mov     r13, r8
0x18000dcf0  mov     [rsp+0F8h+var_A8], r8
0x18000dcf5  mov     rbx, rdx
0x18000dcf8  mov     [rsp+0F8h+var_98], rdx
0x18000dcfd  mov     r14, rcx
0x18000dd00  mov     [rsp+0F8h+lpCriticalSection], rcx
0x18000dd05  mov     [rsp+0F8h+var_78], rcx
0x18000dd0d  lea     rsi, WPP_GLOBAL_Control
0x18000dd14  mov     r10, cs:WPP_GLOBAL_Control
0x18000dd1b  cmp     r10, rsi
0x18000dd1e  jz      short loc_18000DD55
0x18000dd20  cmp     byte ptr [r10+19h], 6
0x18000dd25  jb      short loc_18000DD55
0x18000dd27  mov     ecx, 1; int
0x18000dd2c  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000dd31  mov     edx, 16h
0x18000dd36  mov     r9, rax
0x18000dd39  lea     r15, WPP_f34e634574083547aa3a426270948a29_Traceguids
0x18000dd40  mov     r8, r15
0x18000dd43  mov     rcx, [r10+10h]
0x18000dd47  call    WPP_SF_s
0x18000dd4c  mov     r10, cs:WPP_GLOBAL_Control
0x18000dd53  jmp     short loc_18000DD5C
0x18000dd55  lea     r15, WPP_f34e634574083547aa3a426270948a29_Traceguids
0x18000dd5c  xor     edi, edi
0x18000dd5e  test    rbx, rbx
0x18000dd61  jnz     short loc_18000DD7B
0x18000dd63  cmp     r10, rsi
0x18000dd66  jz      short loc_18000DDA3
0x18000dd68  cmp     byte ptr [r10+19h], 2
0x18000dd6d  jb      short loc_18000DDA3
0x18000dd6f  lea     edx, [rdi+17h]
0x18000dd72  lea     r9, aPnewpeerguid; "pNewPeerGuid"
0x18000dd79  jmp     short loc_18000DD97
0x18000dd7b  test    r13, r13
0x18000dd7e  jnz     short loc_18000DDAD
0x18000dd80  cmp     r10, rsi
0x18000dd83  jz      short loc_18000DDA3
0x18000dd85  cmp     byte ptr [r10+19h], 2
0x18000dd8a  jb      short loc_18000DDA3
0x18000dd8c  lea     edx, [r13+18h]
0x18000dd90  lea     r9, aPpeer; "pPeer"
0x18000dd97  mov     r8, r15
0x18000dd9a  mov     rcx, [r10+10h]
0x18000dd9e  call    WPP_SF_s
0x18000dda3  mov     eax, 80004003h
0x18000dda8  jmp     loc_18000DE4A
0x18000ddad  mov     r12d, edi
0x18000ddb0  mov     rcx, r14; lpCriticalSection
0x18000ddb3  call    cs:__imp_EnterCriticalSection
0x18000ddb9  cmp     dword ptr [r13+128h], 1
0x18000ddc1  jnz     loc_18000DE6D
0x18000ddc7  mov     r10, cs:WPP_GLOBAL_Control
0x18000ddce  cmp     r10, rsi
0x18000ddd1  jz      loc_18000E5D0
0x18000ddd7  mov     r14b, 4
0x18000ddda  cmp     [r10+19h], r14b
0x18000ddde  jb      short loc_18000DE00
0x18000dde0  xor     ecx, ecx; int
0x18000dde2  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000dde7  mov     edx, 19h
0x18000ddec  mov     [rsp+0F8h+var_D8], rbx
0x18000ddf1  mov     r9, rax
0x18000ddf4  mov     r8, r15
0x18000ddf7  mov     rcx, [r10+10h]
0x18000ddfb  call    WPP_SF_s_guid_
0x18000de00  mov     r13, [rsp+0F8h+lpCriticalSection]
0x18000de05  mov     rcx, r13; lpCriticalSection
0x18000de08  call    cs:__imp_LeaveCriticalSection
0x18000de0e  mov     r10, cs:WPP_GLOBAL_Control
0x18000de15  cmp     r10, rsi
0x18000de18  jz      short loc_18000DE47
0x18000de1a  test    r12d, r12d
0x18000de1d  js      short loc_18000DE26
0x18000de1f  cmp     byte ptr [r10+19h], 6
0x18000de24  jb      short loc_18000DE47
0x18000de26  or      ecx, 0FFFFFFFFh; int
0x18000de29  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000de2e  mov     edx, 2Dh ; '-'
0x18000de33  mov     dword ptr [rsp+0F8h+var_D8], r12d
0x18000de38  mov     r9, rax
0x18000de3b  mov     r8, r15
0x18000de3e  mov     rcx, [r10+10h]
0x18000de42  call    WPP_SF_sd
0x18000de47  mov     eax, r12d
0x18000de4a  mov     rcx, [rsp+0F8h+var_40]
0x18000de52  xor     rcx, rsp; StackCookie
0x18000de55  call    __security_check_cookie
0x18000de5a  add     rsp, 0C0h
0x18000de61  pop     r15
0x18000de63  pop     r14
0x18000de65  pop     r13
0x18000de67  pop     r12
0x18000de69  pop     rdi
0x18000de6a  pop     rsi
0x18000de6b  pop     rbx
0x18000de6c  retn
0x18000de6d  movups  xmm0, xmmword ptr [rbx]
0x18000de70  movdqu  [rsp+0F8h+var_58], xmm0
0x18000de79  mov     [rsp+0F8h+var_48], r13
0x18000de81  add     r14, 50h ; 'P'
0x18000de85  mov     [rsp+0F8h+var_90], r14
0x18000de8a  lea     rdx, [rsp+0F8h+var_58]
0x18000de92  mov     rcx, r14
0x18000de95  call    ??$_Buynode@AEAU?$pair@$$CBU_GUID@@PEAVCWcnPeer@@@std@@@?$_Tree_buy@U?$pair@$$CBU_GUID@@PEAVCWcnPeer@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVCWcnPeer@@@std@@@2@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@PEAVCWcnPeer@@@std@@PEAX@1@AEAU?$pair@$$CBU_GUID@@PEAVCWcnPeer@@@1@@Z; std::_Tree_buy<std::pair<_GUID const,CWcnPeer *>>::_Buynode<std::pair<_GUID const,CWcnPeer *> &>(std::pair<_GUID const,CWcnPeer *> &)
0x18000de9a  lea     r9, [rax+20h]
0x18000de9e  mov     [rsp+0F8h+var_D8], rax
0x18000dea3  lea     rdx, [rsp+0F8h+var_88]
0x18000dea8  mov     rcx, r14
0x18000deab  call    ??$_Insert_nohint@AEAU?$pair@$$CBU_GUID@@PEAVCWcnPeer@@@std@@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@PEAVCWcnPeer@@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@U_GUID@@PEAVCWcnPeer@@UGuidCompare@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVCWcnPeer@@@std@@@std@@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@PEAVCWcnPeer@@@std@@@std@@@std@@@std@@_N@1@_NAEAU?$pair@$$CBU_GUID@@PEAVCWcnPeer@@@1@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@PEAVCWcnPeer@@@std@@PEAX@1@@Z; std::_Tree<std::_Tmap_traits<_GUID,CWcnPeer *,GuidCompare,std::allocator<std::pair<_GUID const,CWcnPeer *>>,0>>::_Insert_nohint<std::pair<_GUID const,CWcnPeer *> &,std::_Tree_node<std::pair<_GUID const,CWcnPeer *>,void *> *>(bool,std::pair<_GUID const,CWcnPeer *> &,std::_Tree_node<std::pair<_GUID const,CWcnPeer *>,void *> *)
0x18000deb0  mov     al, [rsp+0F8h+var_80]
0x18000deb4  test    al, al
0x18000deb6  jnz     loc_18000E0AF
0x18000debc  mov     rbx, [rsp+0F8h+var_88]
0x18000dec1  mov     r13, [rbx+30h]
0x18000dec5  cmp     [rsp+0F8h+var_A8], r13
0x18000deca  jz      loc_18000E0AF
0x18000ded0  mov     dword ptr [rsp+0F8h+var_B0], edi
0x18000ded4  mov     r11, cs:WPP_GLOBAL_Control
0x18000dedb  mov     r14b, 4
0x18000dede  cmp     r11, rsi
0x18000dee1  jz      short loc_18000DF15
0x18000dee3  cmp     [r11+19h], r14b
0x18000dee7  jb      short loc_18000DF15
0x18000dee9  xor     ecx, ecx; int
0x18000deeb  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000def0  mov     edx, 1Ah
0x18000def5  mov     rcx, [rsp+0F8h+var_98]
0x18000defa  mov     [rsp+0F8h+var_D8], rcx
0x18000deff  mov     r9, rax
0x18000df02  mov     r8, r15
0x18000df05  mov     rcx, [r11+10h]
0x18000df09  call    WPP_SF_s_guid_
0x18000df0e  mov     r11, cs:WPP_GLOBAL_Control
0x18000df15  lea     r8, [rsp+0F8h+var_B0]; enum tagWcnTransportId *
0x18000df1a  xor     edx, edx; bool
0x18000df1c  mov     rcx, [rsp+0F8h+var_A8]; this
0x18000df21  call    ?GetBestTransport@CWcnPeer@@QEAAPEAVIWcnTransportPeer@@_NPEAW4tagWcnTransportId@@@Z; CWcnPeer::GetBestTransport(bool,tagWcnTransportId *)
0x18000df26  mov     edx, dword ptr [rsp+0F8h+var_B0]
0x18000df2a  sub     edx, 5
0x18000df2d  jz      loc_18000E182
0x18000df33  cmp     edx, 1
0x18000df36  jz      loc_18000E182
0x18000df3c  mov     dword ptr [rsp+0F8h+var_B0], edi
0x18000df40  lea     r8, [rsp+0F8h+var_B0]; enum tagWcnTransportId *
0x18000df45  xor     edx, edx; bool
0x18000df47  mov     rcx, r13; this
0x18000df4a  call    ?GetBestTransport@CWcnPeer@@QEAAPEAVIWcnTransportPeer@@_NPEAW4tagWcnTransportId@@@Z; CWcnPeer::GetBestTransport(bool,tagWcnTransportId *)
0x18000df4f  mov     edx, dword ptr [rsp+0F8h+var_B0]
0x18000df53  sub     edx, 5
0x18000df56  jz      loc_18000E058
0x18000df5c  cmp     edx, 1
0x18000df5f  jz      loc_18000E058
0x18000df65  cmp     r11, rsi
0x18000df68  jz      short loc_18000DF92
0x18000df6a  cmp     [r11+19h], r14b
0x18000df6e  jb      short loc_18000DF92
0x18000df70  xor     ecx, ecx; int
0x18000df72  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000df77  mov     edx, 1Dh
0x18000df7c  mov     r9, rax
0x18000df7f  mov     r8, r15
0x18000df82  mov     rcx, [r11+10h]
0x18000df86  call    WPP_SF_s
0x18000df8b  mov     r11, cs:WPP_GLOBAL_Control
0x18000df92  mov     rax, [rsp+0F8h+var_A8]
0x18000df97  cmp     [rax+124h], edi
0x18000df9d  jz      short loc_18000E00E
0x18000df9f  cmp     r11, rsi
0x18000dfa2  jz      short loc_18000DFCC
0x18000dfa4  cmp     [r11+19h], r14b
0x18000dfa8  jb      short loc_18000DFCC
0x18000dfaa  xor     ecx, ecx; int
0x18000dfac  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000dfb1  mov     edx, 1Eh
0x18000dfb6  mov     r9, rax
0x18000dfb9  mov     r8, r15
0x18000dfbc  mov     rcx, [r11+10h]
0x18000dfc0  call    WPP_SF_s
0x18000dfc5  mov     r11, cs:WPP_GLOBAL_Control
0x18000dfcc  cmp     [r13+124h], edi
0x18000dfd3  jz      loc_18000E1AF
0x18000dfd9  cmp     r11, rsi
0x18000dfdc  jz      short loc_18000DFFF
0x18000dfde  cmp     [r11+19h], r14b
0x18000dfe2  jb      short loc_18000DFFF
0x18000dfe4  xor     ecx, ecx; int
0x18000dfe6  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000dfeb  mov     edx, 1Fh
0x18000dff0  mov     r9, rax
0x18000dff3  mov     r8, r15
0x18000dff6  mov     rcx, [r11+10h]
0x18000dffa  call    WPP_SF_s
0x18000dfff  xor     edx, edx; int
0x18000e001  mov     rcx, r13; this
0x18000e004  call    ?SetTargetedDiscoveryPeerValue@CWcnPeer@@QEAAXH@Z; CWcnPeer::SetTargetedDiscoveryPeerValue(int)
0x18000e009  jmp     loc_18000E1A8
0x18000e00e  cmp     [r13+124h], edi
0x18000e015  jz      short loc_18000E034
0x18000e017  cmp     r11, rsi
0x18000e01a  jz      loc_18000E0AB
0x18000e020  cmp     [r11+19h], r14b
0x18000e024  jb      short loc_18000E085
0x18000e026  xor     ecx, ecx; int
0x18000e028  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000e02d  mov     edx, 20h ; ' '
0x18000e032  jmp     short loc_18000E06F
0x18000e034  cmp     r11, rsi
0x18000e037  jz      loc_18000E1D5
0x18000e03d  cmp     [r11+19h], r14b
0x18000e041  jb      loc_18000E1AF
0x18000e047  xor     ecx, ecx; int
0x18000e049  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000e04e  mov     edx, 21h ; '!'
0x18000e053  jmp     loc_18000E199
0x18000e058  cmp     r11, rsi
0x18000e05b  jz      short loc_18000E0AB
0x18000e05d  cmp     [r11+19h], r14b
0x18000e061  jb      short loc_18000E085
0x18000e063  xor     ecx, ecx; int
0x18000e065  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000e06a  mov     edx, 1Ch
0x18000e06f  mov     r9, rax
0x18000e072  mov     r8, r15
0x18000e075  mov     rcx, [r11+10h]
0x18000e079  call    WPP_SF_s
0x18000e07e  mov     r11, cs:WPP_GLOBAL_Control
0x18000e085  cmp     r11, rsi
0x18000e088  jz      short loc_18000E0AB
0x18000e08a  cmp     [r11+19h], r14b
0x18000e08e  jb      short loc_18000E0AB
0x18000e090  xor     ecx, ecx; int
0x18000e092  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000e097  mov     edx, 27h ; '''
0x18000e09c  mov     rcx, [r11+10h]
0x18000e0a0  mov     r8, r15
0x18000e0a3  mov     r9, rax
0x18000e0a6  call    WPP_SF_s
0x18000e0ab  mov     al, [rsp+0F8h+var_80]
0x18000e0af  test    r12d, r12d
0x18000e0b2  js      loc_18000DE00
0x18000e0b8  mov     r13, [rsp+0F8h+lpCriticalSection]
0x18000e0bd  test    al, al
0x18000e0bf  jz      loc_18000DE05
0x18000e0c5  mov     rcx, [rsp+0F8h+var_A8]
0x18000e0ca  inc     dword ptr [rcx+10Ch]
0x18000e0d0  mov     r14d, edi
0x18000e0d3  mov     rax, [rsp+0F8h+var_90]
0x18000e0d8  mov     rbx, [rax]
0x18000e0db  mov     rbx, [rbx]
0x18000e0de  cmp     rbx, [rax]
0x18000e0e1  jz      loc_18000E55F
0x18000e0e7  cmp     rcx, [rbx+30h]
0x18000e0eb  jnz     loc_18000E475
0x18000e0f1  mov     r12, [rsp+0F8h+var_98]
0x18000e0f6  mov     rax, [r12]
0x18000e0fa  cmp     rax, [rbx+20h]
0x18000e0fe  jnz     short loc_18000E10F
0x18000e100  mov     rax, [r12+8]
0x18000e105  cmp     rax, [rbx+28h]
0x18000e109  jz      loc_18000E471
0x18000e10f  mov     dword ptr [rsp+0F8h+var_B0], edi
0x18000e113  mov     [rsp+0F8h+var_B8], dil
0x18000e118  movups  xmm0, xmmword ptr [rbx+20h]
0x18000e11c  movdqu  xmmword ptr [rsp+0F8h+Uuid.Data1], xmm0
0x18000e125  lea     r9, [rsp+0F8h+var_B8]; bool *
0x18000e12a  lea     r8, [rsp+0F8h+var_B0]; unsigned int *
0x18000e12f  lea     rdx, [rsp+0F8h+Uuid]; struct _GUID *
0x18000e137  mov     rcx, r13; this
0x18000e13a  call    ?GetPeerNotificationFilter@CWcnPeerCache@@QEAAJPEBU_GUID@@PEAKPEA_N@Z; CWcnPeerCache::GetPeerNotificationFilter(_GUID const *,ulong *,bool *)
0x18000e13f  test    eax, eax
0x18000e141  jns     loc_18000E465
0x18000e147  mov     r10, cs:WPP_GLOBAL_Control
0x18000e14e  cmp     r10, rsi
0x18000e151  jz      loc_18000E46C
0x18000e157  cmp     byte ptr [r10+19h], 3
0x18000e15c  jb      loc_18000E46C
0x18000e162  xor     ecx, ecx; int
0x18000e164  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000e169  mov     edx, 29h ; ')'
0x18000e16e  mov     r9, rax
0x18000e171  mov     r8, r15
0x18000e174  mov     rcx, [r10+10h]
0x18000e178  call    WPP_SF_s
0x18000e17d  jmp     loc_18000E46C
0x18000e182  cmp     r11, rsi
0x18000e185  jz      short loc_18000E1D5
0x18000e187  cmp     [r11+19h], r14b
0x18000e18b  jb      short loc_18000E1AF
  ... truncated ...
```
