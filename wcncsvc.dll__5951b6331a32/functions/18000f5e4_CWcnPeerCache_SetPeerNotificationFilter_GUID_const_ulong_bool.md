# CWcnPeerCache::SetPeerNotificationFilter(_GUID const *,ulong,bool *)

- ea: `0x18000f5e4`
- end: `0x18000f797`
- name: `?SetPeerNotificationFilter@CWcnPeerCache@@QEAAJPEBU_GUID@@KPEA_N@Z`
- size: `435`
- prototype: `__int64 __fastcall(CWcnPeerCache *__hidden this, const struct _GUID *, unsigned int, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000dcc8`
- `0x18000e714`

## callees

- `0x180004fb8`
- `0x180005014`
- `0x18000ce18`
- `0x18000dbec`
- `0x18000f5e4`
- `0x180010438`
- `0x180053004`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f696`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f696`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f742`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f742`

## pseudocode

```c
__int64 __fastcall CWcnPeerCache::SetPeerNotificationFilter(CWcnPeerCache *this, struct _GUID *a2, int a3, bool *a4)
{
  _QWORD *v7; // r10
  const char *Indent; // rax
  __int64 v9; // r10
  int v11; // ebx
  struct _RTL_CRITICAL_SECTION *v12; // r14
  __int64 v13; // rax
  int v14; // eax
  __int64 v15; // r10
  unsigned int v16; // eax
  __int64 v17; // r10
  __int64 v18; // rax
  __int64 v19; // [rsp+30h] [rbp-38h] BYREF
  std::bad_alloc *v20; // [rsp+38h] [rbp-30h] BYREF
  __int64 v21; // [rsp+88h] [rbp+20h]

  HIDWORD(v21) = 0;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v9 + 16), 73, WPP_f34e634574083547aa3a426270948a29_Traceguids, Indent);
    v7 = WPP_GLOBAL_Control;
  }
  if ( a2 )
  {
    v11 = 0;
    v12 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 40);
    EnterCriticalSection((LPCRITICAL_SECTION)this + 1);
    v13 = *std::_Tree<std::_Tmap_traits<_GUID,CWcnPeerCache::tagWCN_PEER_NOTIFICATION_FILTER,GuidCompare,std::allocator<std::pair<_GUID const,CWcnPeerCache::tagWCN_PEER_NOTIFICATION_FILTER>>,0>>::find(
             (__int64 *)this + 12,
             &v19,
             a2);
    if ( v13 == *((_QWORD *)this + 12) )
    {
      BYTE4(v21) = 0;
    }
    else
    {
      v21 = *(_QWORD *)(v13 + 44);
      if ( BYTE4(v21)
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        v14 = (unsigned int)GetIndent(0);
        WPP_SF_s_guid_(
          *(_QWORD *)(v15 + 16),
          75,
          (int)WPP_f34e634574083547aa3a426270948a29_Traceguids,
          v14,
          (__int64)a2);
      }
    }
    try
    {
      LODWORD(v21) = a3;
      *(_QWORD *)std::map<_GUID,CWcnPeerCache::tagWCN_PEER_NOTIFICATION_FILTER,GuidCompare,std::allocator<std::pair<_GUID const,CWcnPeerCache::tagWCN_PEER_NOTIFICATION_FILTER>>>::operator[](
                   (__int64 ***)this + 12,
                   (__int128 *)a2) = v21;
    }
    catch ( std::bad_alloc *v20 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v18 = (*(__int64 (__fastcall **)(std::bad_alloc *))(*(_QWORD *)v20 + 8LL))(v20);
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, WPP_f34e634574083547aa3a426270948a29_Traceguids, v18);
      }
      v11 = -2147024882;
      v12 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 40);
    }
    LeaveCriticalSection(v12);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (v11 < 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u) )
    {
      v16 = (unsigned int)GetIndent(-1);
      WPP_SF_sd(*(_QWORD *)(v17 + 16), 77, (unsigned int)WPP_f34e634574083547aa3a426270948a29_Traceguids, v16, v11);
    }
    return (unsigned int)v11;
  }
  else
  {
    if ( v7 != &WPP_GLOBAL_Control && *((_BYTE *)v7 + 25) >= 2u )
      WPP_SF_s(v7[2], 74, WPP_f34e634574083547aa3a426270948a29_Traceguids, "pPeerGuid");
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x18000f5e4  mov     [rsp+arg_0], rbx
0x18000f5e9  mov     [rsp+arg_18], r9
0x18000f5ee  push    rsi
0x18000f5ef  push    rdi
0x18000f5f0  push    r12
0x18000f5f2  push    r14
0x18000f5f4  push    r15
0x18000f5f6  sub     rsp, 40h
0x18000f5fa  mov     r15d, r8d
0x18000f5fd  mov     rsi, rdx
0x18000f600  mov     r12, rcx
0x18000f603  mov     [rsp+68h+arg_18], 0
0x18000f60f  lea     rdi, WPP_GLOBAL_Control
0x18000f616  mov     r10, cs:WPP_GLOBAL_Control
0x18000f61d  cmp     r10, rdi
0x18000f620  jz      short loc_18000F652
0x18000f622  cmp     byte ptr [r10+19h], 6
0x18000f627  jb      short loc_18000F652
0x18000f629  mov     ecx, 1; int
0x18000f62e  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000f633  mov     edx, 49h ; 'I'
0x18000f638  mov     r9, rax
0x18000f63b  lea     r8, WPP_f34e634574083547aa3a426270948a29_Traceguids
0x18000f642  mov     rcx, [r10+10h]
0x18000f646  call    WPP_SF_s
0x18000f64b  mov     r10, cs:WPP_GLOBAL_Control
0x18000f652  test    rsi, rsi
0x18000f655  jnz     short loc_18000F687
0x18000f657  cmp     r10, rdi
0x18000f65a  jz      short loc_18000F67D
0x18000f65c  cmp     byte ptr [r10+19h], 2
0x18000f661  jb      short loc_18000F67D
0x18000f663  lea     edx, [rsi+4Ah]
0x18000f666  lea     r9, aPpeerguid; "pPeerGuid"
0x18000f66d  lea     r8, WPP_f34e634574083547aa3a426270948a29_Traceguids
0x18000f674  mov     rcx, [r10+10h]
0x18000f678  call    WPP_SF_s
0x18000f67d  mov     eax, 80004003h
0x18000f682  jmp     loc_18000F785
0x18000f687  xor     ebx, ebx
0x18000f689  lea     r14, [r12+28h]
0x18000f68e  mov     [rsp+68h+arg_8], r14
0x18000f693  mov     rcx, r14; lpCriticalSection
0x18000f696  call    cs:__imp_EnterCriticalSection
0x18000f69c  mov     r8, rsi
0x18000f69f  lea     rdx, [rsp+68h+var_38]
0x18000f6a4  lea     rcx, [r12+60h]
0x18000f6a9  call    ?find@?$_Tree@V?$_Tmap_traits@U_GUID@@UtagWCN_PEER_NOTIFICATION_FILTER@CWcnPeerCache@@UGuidCompare@@V?$allocator@U?$pair@$$CBU_GUID@@UtagWCN_PEER_NOTIFICATION_FILTER@CWcnPeerCache@@@std@@@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@UtagWCN_PEER_NOTIFICATION_FILTER@CWcnPeerCache@@@std@@@std@@@std@@@2@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,CWcnPeerCache::tagWCN_PEER_NOTIFICATION_FILTER,GuidCompare,std::allocator<std::pair<_GUID const,CWcnPeerCache::tagWCN_PEER_NOTIFICATION_FILTER>>,0>>::find(_GUID const &)
0x18000f6ae  mov     rax, [rax]
0x18000f6b1  cmp     rax, [r12+60h]
0x18000f6b6  jz      short loc_18000F703
0x18000f6b8  mov     rax, [rax+2Ch]
0x18000f6bc  mov     [rsp+68h+arg_18], rax
0x18000f6c4  shr     rax, 20h
0x18000f6c8  test    al, al
0x18000f6ca  jz      short loc_18000F70A
0x18000f6cc  mov     r10, cs:WPP_GLOBAL_Control
0x18000f6d3  cmp     r10, rdi
0x18000f6d6  jz      short loc_18000F70A
0x18000f6d8  cmp     byte ptr [r10+19h], 3
0x18000f6dd  jb      short loc_18000F70A
0x18000f6df  xor     ecx, ecx; int
0x18000f6e1  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000f6e6  lea     edx, [rbx+4Bh]
0x18000f6e9  mov     [rsp+68h+var_48], rsi
0x18000f6ee  mov     r9, rax
0x18000f6f1  lea     r8, WPP_f34e634574083547aa3a426270948a29_Traceguids
0x18000f6f8  mov     rcx, [r10+10h]
0x18000f6fc  call    WPP_SF_s_guid_
0x18000f701  jmp     short loc_18000F70A
0x18000f703  mov     byte ptr [rsp+68h+arg_18+4], bl
0x18000f70a  mov     dword ptr [rsp+68h+arg_18], r15d
0x18000f712  mov     rdx, rsi
0x18000f715  lea     rcx, [r12+60h]
0x18000f71a  call    ??A?$map@U_GUID@@UtagWCN_PEER_NOTIFICATION_FILTER@CWcnPeerCache@@UGuidCompare@@V?$allocator@U?$pair@$$CBU_GUID@@UtagWCN_PEER_NOTIFICATION_FILTER@CWcnPeerCache@@@std@@@std@@@std@@QEAAAEAUtagWCN_PEER_NOTIFICATION_FILTER@CWcnPeerCache@@AEBU_GUID@@@Z; std::map<_GUID,CWcnPeerCache::tagWCN_PEER_NOTIFICATION_FILTER,GuidCompare,std::allocator<std::pair<_GUID const,CWcnPeerCache::tagWCN_PEER_NOTIFICATION_FILTER>>>::operator[](_GUID const &)
0x18000f71f  mov     rcx, [rsp+68h+arg_18]
0x18000f727  mov     [rax], rcx
0x18000f72a  jmp     short loc_18000F73F
0x18000f72c  lea     rdi, WPP_GLOBAL_Control
0x18000f733  mov     ebx, dword ptr [rsp+68h+arg_18]
0x18000f73a  mov     r14, [rsp+68h+arg_8]
0x18000f73f  mov     rcx, r14; lpCriticalSection
0x18000f742  call    cs:__imp_LeaveCriticalSection
0x18000f748  mov     r10, cs:WPP_GLOBAL_Control
0x18000f74f  cmp     r10, rdi
0x18000f752  jz      short loc_18000F783
0x18000f754  test    ebx, ebx
0x18000f756  js      short loc_18000F75F
0x18000f758  cmp     byte ptr [r10+19h], 6
0x18000f75d  jb      short loc_18000F783
0x18000f75f  or      ecx, 0FFFFFFFFh; int
0x18000f762  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000f767  mov     edx, 4Dh ; 'M'
0x18000f76c  mov     dword ptr [rsp+68h+var_48], ebx
0x18000f770  mov     r9, rax
0x18000f773  lea     r8, WPP_f34e634574083547aa3a426270948a29_Traceguids
0x18000f77a  mov     rcx, [r10+10h]
0x18000f77e  call    WPP_SF_sd
0x18000f783  mov     eax, ebx
0x18000f785  mov     rbx, [rsp+68h+arg_0]
0x18000f78a  add     rsp, 40h
0x18000f78e  pop     r15
0x18000f790  pop     r14
0x18000f792  pop     r12
0x18000f794  pop     rdi
0x18000f795  pop     rsi
0x18000f796  retn
```
