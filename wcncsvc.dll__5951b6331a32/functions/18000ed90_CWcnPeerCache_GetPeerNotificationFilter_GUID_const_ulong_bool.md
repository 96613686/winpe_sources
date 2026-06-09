# CWcnPeerCache::GetPeerNotificationFilter(_GUID const *,ulong *,bool *)

- ea: `0x18000ed90`
- end: `0x18000ef1e`
- name: `?GetPeerNotificationFilter@CWcnPeerCache@@QEAAJPEBU_GUID@@PEAKPEA_N@Z`
- size: `398`
- prototype: `__int64 __fastcall(CWcnPeerCache *__hidden this, const struct _GUID *, unsigned int *, bool *)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000dcc8`
- `0x18003cad0`

## callees

- `0x180004fb8`
- `0x180005014`
- `0x18000ce18`
- `0x18000ed90`
- `0x180010438`
- `0x180053004`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ee4d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ee4d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000eec8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000eec8`

## pseudocode

```c
__int64 __fastcall CWcnPeerCache::GetPeerNotificationFilter(
        CWcnPeerCache *this,
        const struct _GUID *a2,
        unsigned int *a3,
        bool *a4)
{
  _BYTE *v8; // r10
  const char *Indent; // rax
  __int64 v10; // r10
  __int64 v11; // rdx
  const char *v12; // r9
  struct _RTL_CRITICAL_SECTION *v14; // r14
  __int64 v15; // rax
  int v16; // ebx
  __int64 v17; // rax
  unsigned int v18; // eax
  __int64 v19; // r10
  unsigned int v20; // eax
  __int64 v21; // r10
  __int64 v22; // [rsp+68h] [rbp+10h] BYREF

  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v10 + 16), 62, WPP_f34e634574083547aa3a426270948a29_Traceguids, Indent);
    v8 = WPP_GLOBAL_Control;
  }
  if ( !a2 )
  {
    if ( v8 == (_BYTE *)&WPP_GLOBAL_Control || v8[25] < 2u )
      return 2147500035LL;
    v11 = 63;
    v12 = "pPeerGuid";
LABEL_12:
    WPP_SF_s(*((_QWORD *)v8 + 2), v11, WPP_f34e634574083547aa3a426270948a29_Traceguids, v12);
    return 2147500035LL;
  }
  if ( !a3 )
  {
    if ( v8 == (_BYTE *)&WPP_GLOBAL_Control || v8[25] < 2u )
      return 2147500035LL;
    v11 = 64;
    v12 = "pdwNotificationFilter";
    goto LABEL_12;
  }
  v14 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 40);
  EnterCriticalSection((LPCRITICAL_SECTION)this + 1);
  v15 = *std::_Tree<std::_Tmap_traits<_GUID,CWcnPeerCache::tagWCN_PEER_NOTIFICATION_FILTER,GuidCompare,std::allocator<std::pair<_GUID const,CWcnPeerCache::tagWCN_PEER_NOTIFICATION_FILTER>>,0>>::find(
           (__int64 *)this + 12,
           &v22,
           a2);
  if ( v15 == *((_QWORD *)this + 12) )
  {
    v16 = -2147023728;
  }
  else
  {
    v17 = *(_QWORD *)(v15 + 44);
    v16 = 0;
    *a3 = v17;
    if ( a4 )
      *a4 = BYTE4(v17);
    if ( BYTE4(v17)
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      v18 = (unsigned int)GetIndent(0);
      WPP_SF_s_guid_(
        *(_QWORD *)(v19 + 16),
        65,
        (unsigned int)WPP_f34e634574083547aa3a426270948a29_Traceguids,
        v18,
        (__int64)a2);
    }
  }
  LeaveCriticalSection(v14);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (v16 < 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u) )
  {
    v20 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v21 + 16), 66, (unsigned int)WPP_f34e634574083547aa3a426270948a29_Traceguids, v20, v16);
  }
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x18000ed90  mov     [rsp+arg_0], rbx
0x18000ed95  mov     [rsp+arg_10], rbp
0x18000ed9a  push    rsi
0x18000ed9b  push    rdi
0x18000ed9c  push    r12
0x18000ed9e  push    r14
0x18000eda0  push    r15
0x18000eda2  sub     rsp, 30h
0x18000eda6  mov     rsi, r9
0x18000eda9  mov     rdi, r8
0x18000edac  mov     rbp, rdx
0x18000edaf  mov     rbx, rcx
0x18000edb2  mov     r10, cs:WPP_GLOBAL_Control
0x18000edb9  lea     r15, WPP_GLOBAL_Control
0x18000edc0  lea     r12, WPP_f34e634574083547aa3a426270948a29_Traceguids
0x18000edc7  cmp     r10, r15
0x18000edca  jz      short loc_18000EDF8
0x18000edcc  cmp     byte ptr [r10+19h], 6
0x18000edd1  jb      short loc_18000EDF8
0x18000edd3  mov     ecx, 1; int
0x18000edd8  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000eddd  mov     rcx, [r10+10h]
0x18000ede1  mov     edx, 3Eh ; '>'
0x18000ede6  mov     r9, rax
0x18000ede9  mov     r8, r12
0x18000edec  call    WPP_SF_s
0x18000edf1  mov     r10, cs:WPP_GLOBAL_Control
0x18000edf8  test    rbp, rbp
0x18000edfb  jnz     short loc_18000EE15
0x18000edfd  cmp     r10, r15
0x18000ee00  jz      short loc_18000EE3C
0x18000ee02  cmp     byte ptr [r10+19h], 2
0x18000ee07  jb      short loc_18000EE3C
0x18000ee09  lea     edx, [rbp+3Fh]
0x18000ee0c  lea     r9, aPpeerguid; "pPeerGuid"
0x18000ee13  jmp     short loc_18000EE30
0x18000ee15  test    rdi, rdi
0x18000ee18  jnz     short loc_18000EE46
0x18000ee1a  cmp     r10, r15
0x18000ee1d  jz      short loc_18000EE3C
0x18000ee1f  cmp     byte ptr [r10+19h], 2
0x18000ee24  jb      short loc_18000EE3C
0x18000ee26  lea     edx, [rdi+40h]
0x18000ee29  lea     r9, aPdwnotificatio; "pdwNotificationFilter"
0x18000ee30  mov     rcx, [r10+10h]
0x18000ee34  mov     r8, r12
0x18000ee37  call    WPP_SF_s
0x18000ee3c  mov     eax, 80004003h
0x18000ee41  jmp     loc_18000EF07
0x18000ee46  lea     r14, [rbx+28h]
0x18000ee4a  mov     rcx, r14; lpCriticalSection
0x18000ee4d  call    cs:__imp_EnterCriticalSection
0x18000ee53  mov     r8, rbp
0x18000ee56  lea     rdx, [rsp+58h+arg_8]
0x18000ee5b  lea     rcx, [rbx+60h]
0x18000ee5f  call    ?find@?$_Tree@V?$_Tmap_traits@U_GUID@@UtagWCN_PEER_NOTIFICATION_FILTER@CWcnPeerCache@@UGuidCompare@@V?$allocator@U?$pair@$$CBU_GUID@@UtagWCN_PEER_NOTIFICATION_FILTER@CWcnPeerCache@@@std@@@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@UtagWCN_PEER_NOTIFICATION_FILTER@CWcnPeerCache@@@std@@@std@@@std@@@2@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,CWcnPeerCache::tagWCN_PEER_NOTIFICATION_FILTER,GuidCompare,std::allocator<std::pair<_GUID const,CWcnPeerCache::tagWCN_PEER_NOTIFICATION_FILTER>>,0>>::find(_GUID const &)
0x18000ee64  mov     rax, [rax]
0x18000ee67  cmp     rax, [rbx+60h]
0x18000ee6b  jnz     short loc_18000EE74
0x18000ee6d  mov     ebx, 80070490h
0x18000ee72  jmp     short loc_18000EEC5
0x18000ee74  mov     rax, [rax+2Ch]
0x18000ee78  xor     ebx, ebx
0x18000ee7a  mov     [rdi], eax
0x18000ee7c  test    rsi, rsi
0x18000ee7f  jz      short loc_18000EE8A
0x18000ee81  mov     rcx, rax
0x18000ee84  shr     rcx, 20h
0x18000ee88  mov     [rsi], cl
0x18000ee8a  shr     rax, 20h
0x18000ee8e  test    al, al
0x18000ee90  jz      short loc_18000EEC5
0x18000ee92  mov     r10, cs:WPP_GLOBAL_Control
0x18000ee99  cmp     r10, r15
0x18000ee9c  jz      short loc_18000EEC5
0x18000ee9e  cmp     byte ptr [r10+19h], 5
0x18000eea3  jb      short loc_18000EEC5
0x18000eea5  xor     ecx, ecx; int
0x18000eea7  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000eeac  mov     rcx, [r10+10h]
0x18000eeb0  mov     edx, 41h ; 'A'
0x18000eeb5  mov     r9, rax
0x18000eeb8  mov     [rsp+58h+var_38], rbp
0x18000eebd  mov     r8, r12
0x18000eec0  call    WPP_SF_s_guid_
0x18000eec5  mov     rcx, r14; lpCriticalSection
0x18000eec8  call    cs:__imp_LeaveCriticalSection
0x18000eece  mov     r10, cs:WPP_GLOBAL_Control
0x18000eed5  cmp     r10, r15
0x18000eed8  jz      short loc_18000EF05
0x18000eeda  test    ebx, ebx
0x18000eedc  js      short loc_18000EEE5
0x18000eede  cmp     byte ptr [r10+19h], 6
0x18000eee3  jb      short loc_18000EF05
0x18000eee5  or      ecx, 0FFFFFFFFh; int
0x18000eee8  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000eeed  mov     rcx, [r10+10h]
0x18000eef1  mov     edx, 42h ; 'B'
0x18000eef6  mov     r9, rax
0x18000eef9  mov     dword ptr [rsp+58h+var_38], ebx
0x18000eefd  mov     r8, r12
0x18000ef00  call    WPP_SF_sd
0x18000ef05  mov     eax, ebx
0x18000ef07  mov     rbx, [rsp+58h+arg_0]
0x18000ef0c  mov     rbp, [rsp+58h+arg_10]
0x18000ef11  add     rsp, 30h
0x18000ef15  pop     r15
0x18000ef17  pop     r14
0x18000ef19  pop     r12
0x18000ef1b  pop     rdi
0x18000ef1c  pop     rsi
0x18000ef1d  retn
```
