# CWcnPeerCache::UpdatePeerNotificationFilter(_GUID const *,ulong,bool *)

- ea: `0x18000f8dc`
- end: `0x18000faaf`
- name: `?UpdatePeerNotificationFilter@CWcnPeerCache@@QEAAJPEBU_GUID@@KPEA_N@Z`
- size: `467`
- prototype: `__int64 __fastcall(CWcnPeerCache *__hidden this, const struct _GUID *, unsigned int, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001de78`

## callees

- `0x180004fb8`
- `0x180005014`
- `0x18000ce18`
- `0x18000dbec`
- `0x18000f8dc`
- `0x180010438`
- `0x180053004`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f989`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f989`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fa60`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fa60`

## pseudocode

```c
__int64 __fastcall CWcnPeerCache::UpdatePeerNotificationFilter(
        CWcnPeerCache *this,
        struct _GUID *a2,
        __int64 a3,
        bool *a4)
{
  _QWORD *v6; // r10
  const char *Indent; // rax
  __int64 v8; // r10
  int v10; // edi
  struct _RTL_CRITICAL_SECTION *v11; // r14
  __int64 v12; // rax
  __int64 v13; // rax
  int v14; // eax
  __int64 v15; // r10
  int v16; // edx
  unsigned int v17; // eax
  __int64 v18; // r10
  __int64 v19; // rax
  __int64 v20; // [rsp+30h] [rbp-38h] BYREF
  std::bad_alloc *v21; // [rsp+38h] [rbp-30h] BYREF
  __int64 v22; // [rsp+88h] [rbp+20h]

  HIDWORD(v22) = 0;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v8 + 16), 67, WPP_f34e634574083547aa3a426270948a29_Traceguids, Indent);
    v6 = WPP_GLOBAL_Control;
  }
  if ( !a2 )
  {
    if ( v6 != &WPP_GLOBAL_Control && *((_BYTE *)v6 + 25) >= 2u )
      WPP_SF_s(v6[2], 68, WPP_f34e634574083547aa3a426270948a29_Traceguids, "pPeerGuid");
    return 2147500035LL;
  }
  v10 = 0;
  v11 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 40);
  EnterCriticalSection((LPCRITICAL_SECTION)this + 1);
  v12 = *std::_Tree<std::_Tmap_traits<_GUID,CWcnPeerCache::tagWCN_PEER_NOTIFICATION_FILTER,GuidCompare,std::allocator<std::pair<_GUID const,CWcnPeerCache::tagWCN_PEER_NOTIFICATION_FILTER>>,0>>::find(
           (__int64 *)this + 12,
           &v20,
           a2);
  if ( v12 == *((_QWORD *)this + 12) )
  {
    LODWORD(v22) = 1;
    BYTE4(v22) = 0;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
      goto LABEL_27;
    v14 = (unsigned int)GetIndent(0);
    v16 = 70;
  }
  else
  {
    v13 = *(_QWORD *)(v12 + 44);
    v22 = v13 | 1;
    if ( !BYTE4(v13)
      || WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
    {
      goto LABEL_27;
    }
    v14 = (unsigned int)GetIndent(0);
    v16 = 69;
  }
  WPP_SF_s_guid_(*(_QWORD *)(v15 + 16), v16, (int)WPP_f34e634574083547aa3a426270948a29_Traceguids, v14, (__int64)a2);
LABEL_27:
  try
  {
    *(_QWORD *)std::map<_GUID,CWcnPeerCache::tagWCN_PEER_NOTIFICATION_FILTER,GuidCompare,std::allocator<std::pair<_GUID const,CWcnPeerCache::tagWCN_PEER_NOTIFICATION_FILTER>>>::operator[](
                 (__int64 ***)this + 12,
                 (__int128 *)a2) = v22;
  }
  catch ( std::bad_alloc *v21 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v19 = (*(__int64 (__fastcall **)(std::bad_alloc *))(*(_QWORD *)v21 + 8LL))(v21);
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, WPP_f34e634574083547aa3a426270948a29_Traceguids, v19);
    }
    v10 = -2147024882;
    v11 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 40);
  }
  LeaveCriticalSection(v11);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (v10 < 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u) )
  {
    v17 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v18 + 16), 72, (unsigned int)WPP_f34e634574083547aa3a426270948a29_Traceguids, v17, v10);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000f8dc  mov     [rsp+arg_18], r9
0x18000f8e1  mov     [rsp+arg_10], r8d
0x18000f8e6  push    rbx
0x18000f8e7  push    rsi
0x18000f8e8  push    rdi
0x18000f8e9  push    r14
0x18000f8eb  push    r15
0x18000f8ed  sub     rsp, 40h
0x18000f8f1  mov     rsi, rdx
0x18000f8f4  mov     r15, rcx
0x18000f8f7  mov     [rsp+68h+arg_18], 0
0x18000f903  lea     rbx, WPP_GLOBAL_Control
0x18000f90a  mov     r10, cs:WPP_GLOBAL_Control
0x18000f911  cmp     r10, rbx
0x18000f914  jz      short loc_18000F946
0x18000f916  cmp     byte ptr [r10+19h], 6
0x18000f91b  jb      short loc_18000F946
0x18000f91d  mov     ecx, 1; int
0x18000f922  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000f927  mov     edx, 43h ; 'C'
0x18000f92c  mov     r9, rax
0x18000f92f  lea     r8, WPP_f34e634574083547aa3a426270948a29_Traceguids
0x18000f936  mov     rcx, [r10+10h]
0x18000f93a  call    WPP_SF_s
0x18000f93f  mov     r10, cs:WPP_GLOBAL_Control
0x18000f946  test    rsi, rsi
0x18000f949  jnz     short loc_18000F97B
0x18000f94b  cmp     r10, rbx
0x18000f94e  jz      short loc_18000F971
0x18000f950  cmp     byte ptr [r10+19h], 2
0x18000f955  jb      short loc_18000F971
0x18000f957  lea     edx, [rsi+44h]
0x18000f95a  lea     r9, aPpeerguid; "pPeerGuid"
0x18000f961  lea     r8, WPP_f34e634574083547aa3a426270948a29_Traceguids
0x18000f968  mov     rcx, [r10+10h]
0x18000f96c  call    WPP_SF_s
0x18000f971  mov     eax, 80004003h
0x18000f976  jmp     loc_18000FAA3
0x18000f97b  xor     edi, edi
0x18000f97d  lea     r14, [r15+28h]
0x18000f981  mov     [rsp+68h+arg_8], r14
0x18000f986  mov     rcx, r14; lpCriticalSection
0x18000f989  call    cs:__imp_EnterCriticalSection
0x18000f98f  mov     r8, rsi
0x18000f992  lea     rdx, [rsp+68h+var_38]
0x18000f997  lea     rcx, [r15+60h]
0x18000f99b  call    ?find@?$_Tree@V?$_Tmap_traits@U_GUID@@UtagWCN_PEER_NOTIFICATION_FILTER@CWcnPeerCache@@UGuidCompare@@V?$allocator@U?$pair@$$CBU_GUID@@UtagWCN_PEER_NOTIFICATION_FILTER@CWcnPeerCache@@@std@@@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@UtagWCN_PEER_NOTIFICATION_FILTER@CWcnPeerCache@@@std@@@std@@@std@@@2@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,CWcnPeerCache::tagWCN_PEER_NOTIFICATION_FILTER,GuidCompare,std::allocator<std::pair<_GUID const,CWcnPeerCache::tagWCN_PEER_NOTIFICATION_FILTER>>,0>>::find(_GUID const &)
0x18000f9a0  mov     rax, [rax]
0x18000f9a3  cmp     rax, [r15+60h]
0x18000f9a7  jz      short loc_18000F9E6
0x18000f9a9  mov     rax, [rax+2Ch]
0x18000f9ad  mov     [rsp+68h+arg_18], rax
0x18000f9b5  or      dword ptr [rsp+68h+arg_18], 1
0x18000f9bd  cmp     byte ptr [rsp+68h+arg_18+4], dil
0x18000f9c5  jz      short loc_18000FA31
0x18000f9c7  mov     r10, cs:WPP_GLOBAL_Control
0x18000f9ce  cmp     r10, rbx
0x18000f9d1  jz      short loc_18000FA31
0x18000f9d3  cmp     byte ptr [r10+19h], 3
0x18000f9d8  jb      short loc_18000FA31
0x18000f9da  xor     ecx, ecx; int
0x18000f9dc  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000f9e1  lea     edx, [rdi+45h]
0x18000f9e4  jmp     short loc_18000FA18
0x18000f9e6  mov     dword ptr [rsp+68h+arg_18], 1
0x18000f9f1  mov     byte ptr [rsp+68h+arg_18+4], dil
0x18000f9f9  mov     r10, cs:WPP_GLOBAL_Control
0x18000fa00  cmp     r10, rbx
0x18000fa03  jz      short loc_18000FA31
0x18000fa05  cmp     byte ptr [r10+19h], 3
0x18000fa0a  jb      short loc_18000FA31
0x18000fa0c  xor     ecx, ecx; int
0x18000fa0e  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000fa13  mov     edx, 46h ; 'F'
0x18000fa18  mov     [rsp+68h+var_48], rsi
0x18000fa1d  mov     r9, rax
0x18000fa20  lea     r8, WPP_f34e634574083547aa3a426270948a29_Traceguids
0x18000fa27  mov     rcx, [r10+10h]
0x18000fa2b  call    WPP_SF_s_guid_
0x18000fa30  nop
0x18000fa31  mov     rdx, rsi
0x18000fa34  lea     rcx, [r15+60h]
0x18000fa38  call    ??A?$map@U_GUID@@UtagWCN_PEER_NOTIFICATION_FILTER@CWcnPeerCache@@UGuidCompare@@V?$allocator@U?$pair@$$CBU_GUID@@UtagWCN_PEER_NOTIFICATION_FILTER@CWcnPeerCache@@@std@@@std@@@std@@QEAAAEAUtagWCN_PEER_NOTIFICATION_FILTER@CWcnPeerCache@@AEBU_GUID@@@Z; std::map<_GUID,CWcnPeerCache::tagWCN_PEER_NOTIFICATION_FILTER,GuidCompare,std::allocator<std::pair<_GUID const,CWcnPeerCache::tagWCN_PEER_NOTIFICATION_FILTER>>>::operator[](_GUID const &)
0x18000fa3d  mov     rcx, [rsp+68h+arg_18]
0x18000fa45  mov     [rax], rcx
0x18000fa48  jmp     short loc_18000FA5D
0x18000fa4a  lea     rbx, WPP_GLOBAL_Control
0x18000fa51  mov     edi, [rsp+68h+arg_10]
0x18000fa58  mov     r14, [rsp+68h+arg_8]
0x18000fa5d  mov     rcx, r14; lpCriticalSection
0x18000fa60  call    cs:__imp_LeaveCriticalSection
0x18000fa66  mov     r10, cs:WPP_GLOBAL_Control
0x18000fa6d  cmp     r10, rbx
0x18000fa70  jz      short loc_18000FAA1
0x18000fa72  test    edi, edi
0x18000fa74  js      short loc_18000FA7D
0x18000fa76  cmp     byte ptr [r10+19h], 6
0x18000fa7b  jb      short loc_18000FAA1
0x18000fa7d  or      ecx, 0FFFFFFFFh; int
0x18000fa80  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000fa85  mov     edx, 48h ; 'H'
0x18000fa8a  mov     dword ptr [rsp+68h+var_48], edi
0x18000fa8e  mov     r9, rax
0x18000fa91  lea     r8, WPP_f34e634574083547aa3a426270948a29_Traceguids
0x18000fa98  mov     rcx, [r10+10h]
0x18000fa9c  call    WPP_SF_sd
0x18000faa1  mov     eax, edi
0x18000faa3  add     rsp, 40h
0x18000faa7  pop     r15
0x18000faa9  pop     r14
0x18000faab  pop     rdi
0x18000faac  pop     rsi
0x18000faad  pop     rbx
0x18000faae  retn
```
