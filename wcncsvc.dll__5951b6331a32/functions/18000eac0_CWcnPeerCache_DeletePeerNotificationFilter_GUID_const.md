# CWcnPeerCache::DeletePeerNotificationFilter(_GUID const *)

- ea: `0x18000eac0`
- end: `0x18000ebd7`
- name: `?DeletePeerNotificationFilter@CWcnPeerCache@@AEAAJPEBU_GUID@@@Z`
- size: `279`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this, const struct _GUID *)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000dcc8`
- `0x18000e714`
- `0x18000f258`

## callees

- `0x180004fb8`
- `0x180005014`
- `0x18000eac0`
- `0x18000fe00`
- `0x180010438`
- `0x180053004`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000eb51`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000eb51`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000eb85`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000eb85`

## pseudocode

```c
__int64 __fastcall CWcnPeerCache::DeletePeerNotificationFilter(
        struct _RTL_CRITICAL_SECTION *this,
        const struct _GUID *a2)
{
  _QWORD *v4; // r10
  unsigned int v5; // ebx
  const char *Indent; // rax
  __int64 v7; // r10
  _QWORD *v9; // rax
  unsigned int v10; // eax
  __int64 v11; // r10
  char v12; // [rsp+58h] [rbp+10h] BYREF

  v4 = WPP_GLOBAL_Control;
  v5 = 1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v7 + 16), 82, WPP_f34e634574083547aa3a426270948a29_Traceguids, Indent);
    v4 = WPP_GLOBAL_Control;
  }
  if ( a2 )
  {
    EnterCriticalSection(this + 1);
    v9 = (_QWORD *)std::_Tree<std::_Tmap_traits<_GUID,CWcnPeerCache::tagWCN_PEER_NOTIFICATION_FILTER,GuidCompare,std::allocator<std::pair<_GUID const,CWcnPeerCache::tagWCN_PEER_NOTIFICATION_FILTER>>,0>>::find(
                     &this[2].OwningThread,
                     &v12,
                     a2);
    if ( (HANDLE)*v9 != this[2].OwningThread )
    {
      v5 = 0;
      std::_Tree<std::_Tmap_traits<_GUID,CWcnWfdGoPeer const *,GuidCompare,std::allocator<std::pair<_GUID const,CWcnWfdGoPeer const *>>,0>>::erase(
        &this[2].OwningThread,
        &v12,
        *v9);
    }
    LeaveCriticalSection(this + 1);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      v10 = (unsigned int)GetIndent(-1);
      WPP_SF_sd(*(_QWORD *)(v11 + 16), 84, (unsigned int)WPP_f34e634574083547aa3a426270948a29_Traceguids, v10, v5);
    }
    return v5;
  }
  else
  {
    if ( v4 != &WPP_GLOBAL_Control && *((_BYTE *)v4 + 25) >= 2u )
      WPP_SF_s(v4[2], 83, WPP_f34e634574083547aa3a426270948a29_Traceguids, "pPeerGuid");
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x18000eac0  mov     [rsp+arg_0], rbx
0x18000eac5  mov     [rsp+arg_10], rbp
0x18000eaca  push    rsi
0x18000eacb  push    rdi
0x18000eacc  push    r14
0x18000eace  sub     rsp, 30h
0x18000ead2  mov     rdi, rdx
0x18000ead5  mov     rsi, rcx
0x18000ead8  mov     r10, cs:WPP_GLOBAL_Control
0x18000eadf  lea     r14, WPP_GLOBAL_Control
0x18000eae6  mov     ebx, 1
0x18000eaeb  cmp     r10, r14
0x18000eaee  jz      short loc_18000EB1B
0x18000eaf0  cmp     byte ptr [r10+19h], 6
0x18000eaf5  jb      short loc_18000EB1B
0x18000eaf7  mov     ecx, ebx; int
0x18000eaf9  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000eafe  mov     rcx, [r10+10h]
0x18000eb02  lea     edx, [rbx+51h]
0x18000eb05  mov     r9, rax
0x18000eb08  lea     r8, WPP_f34e634574083547aa3a426270948a29_Traceguids
0x18000eb0f  call    WPP_SF_s
0x18000eb14  mov     r10, cs:WPP_GLOBAL_Control
0x18000eb1b  test    rdi, rdi
0x18000eb1e  jnz     short loc_18000EB4D
0x18000eb20  cmp     r10, r14
0x18000eb23  jz      short loc_18000EB46
0x18000eb25  cmp     byte ptr [r10+19h], 2
0x18000eb2a  jb      short loc_18000EB46
0x18000eb2c  mov     rcx, [r10+10h]
0x18000eb30  lea     edx, [rdi+53h]
0x18000eb33  lea     r9, aPpeerguid; "pPeerGuid"
0x18000eb3a  lea     r8, WPP_f34e634574083547aa3a426270948a29_Traceguids
0x18000eb41  call    WPP_SF_s
0x18000eb46  mov     eax, 80004003h
0x18000eb4b  jmp     short loc_18000EBC4
0x18000eb4d  lea     rcx, [rsi+28h]; lpCriticalSection
0x18000eb51  call    cs:__imp_EnterCriticalSection
0x18000eb57  mov     r8, rdi
0x18000eb5a  lea     rdx, [rsp+48h+arg_8]
0x18000eb5f  lea     rcx, [rsi+60h]
0x18000eb63  call    ?find@?$_Tree@V?$_Tmap_traits@U_GUID@@UtagWCN_PEER_NOTIFICATION_FILTER@CWcnPeerCache@@UGuidCompare@@V?$allocator@U?$pair@$$CBU_GUID@@UtagWCN_PEER_NOTIFICATION_FILTER@CWcnPeerCache@@@std@@@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@UtagWCN_PEER_NOTIFICATION_FILTER@CWcnPeerCache@@@std@@@std@@@std@@@2@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,CWcnPeerCache::tagWCN_PEER_NOTIFICATION_FILTER,GuidCompare,std::allocator<std::pair<_GUID const,CWcnPeerCache::tagWCN_PEER_NOTIFICATION_FILTER>>,0>>::find(_GUID const &)
0x18000eb68  mov     r8, [rax]
0x18000eb6b  cmp     r8, [rsi+60h]
0x18000eb6f  jz      short loc_18000EB81
0x18000eb71  xor     ebx, ebx
0x18000eb73  lea     rdx, [rsp+48h+arg_8]
0x18000eb78  lea     rcx, [rsi+60h]
0x18000eb7c  call    ?erase@?$_Tree@V?$_Tmap_traits@U_GUID@@PEBVCWcnWfdGoPeer@@UGuidCompare@@V?$allocator@U?$pair@$$CBU_GUID@@PEBVCWcnWfdGoPeer@@@std@@@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@PEBVCWcnWfdGoPeer@@@std@@@std@@@std@@@2@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@PEBVCWcnWfdGoPeer@@@std@@@std@@@std@@@2@@Z; std::_Tree<std::_Tmap_traits<_GUID,CWcnWfdGoPeer const *,GuidCompare,std::allocator<std::pair<_GUID const,CWcnWfdGoPeer const *>>,0>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,CWcnWfdGoPeer const *>>>>)
0x18000eb81  lea     rcx, [rsi+28h]; lpCriticalSection
0x18000eb85  call    cs:__imp_LeaveCriticalSection
0x18000eb8b  mov     r10, cs:WPP_GLOBAL_Control
0x18000eb92  cmp     r10, r14
0x18000eb95  jz      short loc_18000EBC2
0x18000eb97  cmp     byte ptr [r10+19h], 6
0x18000eb9c  jb      short loc_18000EBC2
0x18000eb9e  or      ecx, 0FFFFFFFFh; int
0x18000eba1  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000eba6  mov     rcx, [r10+10h]
0x18000ebaa  lea     r8, WPP_f34e634574083547aa3a426270948a29_Traceguids
0x18000ebb1  mov     edx, 54h ; 'T'
0x18000ebb6  mov     [rsp+48h+var_28], ebx
0x18000ebba  mov     r9, rax
0x18000ebbd  call    WPP_SF_sd
0x18000ebc2  mov     eax, ebx
0x18000ebc4  mov     rbx, [rsp+48h+arg_0]
0x18000ebc9  mov     rbp, [rsp+48h+arg_10]
0x18000ebce  add     rsp, 30h
0x18000ebd2  pop     r14
0x18000ebd4  pop     rdi
0x18000ebd5  pop     rsi
0x18000ebd6  retn
```
