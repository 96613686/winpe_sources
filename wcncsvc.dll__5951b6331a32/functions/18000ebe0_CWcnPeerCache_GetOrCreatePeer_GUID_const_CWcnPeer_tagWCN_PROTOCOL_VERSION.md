# CWcnPeerCache::GetOrCreatePeer(_GUID const *,CWcnPeer * *,tagWCN_PROTOCOL_VERSION)

- ea: `0x18000ebe0`
- end: `0x18000ed89`
- name: `?GetOrCreatePeer@CWcnPeerCache@@QEAAJPEBU_GUID@@PEAPEAVCWcnPeer@@W4tagWCN_PROTOCOL_VERSION@@@Z`
- size: `425`
- prototype: `__int64 __fastcall(__int64, void *, CWcnPeer **)`
- caller_count: `6`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18003e180`
- `0x18003ef38`
- `0x1800460f4`
- `0x1800496c0`
- `0x18004b644`
- `0x18004e048`

## callees

- `0x180004f78`
- `0x180004fb8`
- `0x180005014`
- `0x18000e714`
- `0x18000ebe0`
- `0x1800103b8`
- `0x180053004`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ec9e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ec9e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ed3d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ed3d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000ed0f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000ed0f`

## pseudocode

```c
__int64 __fastcall CWcnPeerCache::GetOrCreatePeer(__int64 a1, void *a2, CWcnPeer **a3)
{
  _BYTE *v6; // r10
  const char *Indent; // rax
  __int64 v8; // r10
  __int64 v9; // rdx
  const char *v10; // r9
  __int64 v12; // rcx
  int v13; // eax
  int v14; // ebx
  CWcnPeer *v15; // rdi
  ULONGLONG TickCount64; // rax
  unsigned int v17; // eax
  __int64 v18; // r10
  _QWORD v19[9]; // [rsp+30h] [rbp-48h] BYREF
  CWcnPeer *v20; // [rsp+88h] [rbp+10h] BYREF

  v20 = 0;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v8 + 16), 17, WPP_f34e634574083547aa3a426270948a29_Traceguids, Indent);
    v6 = WPP_GLOBAL_Control;
  }
  if ( !a2 )
  {
    if ( v6 == (_BYTE *)&WPP_GLOBAL_Control || v6[25] < 2u )
      return 2147500035LL;
    v9 = 18;
    v10 = "pPeerGuid";
LABEL_12:
    WPP_SF_s(*((_QWORD *)v6 + 2), v9, WPP_f34e634574083547aa3a426270948a29_Traceguids, v10);
    return 2147500035LL;
  }
  if ( !a3 )
  {
    if ( v6 == (_BYTE *)&WPP_GLOBAL_Control || v6[25] < 2u )
      return 2147500035LL;
    v9 = 19;
    v10 = "ppPeer_out";
    goto LABEL_12;
  }
  *a3 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)a1);
  v12 = *std::_Tree<std::_Tmap_traits<_GUID,CWcnPeer *,GuidCompare,std::allocator<std::pair<_GUID const,CWcnPeer *>>,0>>::find(
           (__int64 *)(a1 + 80),
           v19,
           a2);
  if ( v12 == *(_QWORD *)(a1 + 80) )
  {
    v13 = CWcnPeerCache::CreateNewPeer((__int64 ***)a1, (__int128 *)a2, &v20);
    v14 = v13;
    if ( v13 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          20,
          WPP_f34e634574083547aa3a426270948a29_Traceguids,
          (unsigned int)v13);
      goto LABEL_22;
    }
    v15 = v20;
  }
  else
  {
    v15 = *(CWcnPeer **)(v12 + 48);
    v14 = 0;
    TickCount64 = GetTickCount64();
    *((_QWORD *)v15 + 35) = TickCount64 + 120000;
    *((_QWORD *)v15 + 34) = TickCount64 + 90000;
    _InterlockedIncrement((volatile signed __int32 *)v15 + 66);
  }
  *a3 = v15;
LABEL_22:
  LeaveCriticalSection((LPCRITICAL_SECTION)a1);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (v14 < 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u) )
  {
    v17 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v18 + 16), 21, (unsigned int)WPP_f34e634574083547aa3a426270948a29_Traceguids, v17, v14);
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18000ebe0  mov     rax, rsp
0x18000ebe3  push    rbx
0x18000ebe4  push    rbp
0x18000ebe5  push    rsi
0x18000ebe6  push    rdi
0x18000ebe7  push    r14
0x18000ebe9  push    r15
0x18000ebeb  sub     rsp, 48h
0x18000ebef  mov     rsi, r8
0x18000ebf2  mov     qword ptr [rax+10h], 0
0x18000ebfa  mov     rdi, rdx
0x18000ebfd  mov     rbp, rcx
0x18000ec00  mov     r10, cs:WPP_GLOBAL_Control
0x18000ec07  lea     r14, WPP_GLOBAL_Control
0x18000ec0e  lea     r15, WPP_f34e634574083547aa3a426270948a29_Traceguids
0x18000ec15  cmp     r10, r14
0x18000ec18  jz      short loc_18000EC46
0x18000ec1a  cmp     byte ptr [r10+19h], 6
0x18000ec1f  jb      short loc_18000EC46
0x18000ec21  mov     ecx, 1; int
0x18000ec26  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000ec2b  mov     rcx, [r10+10h]
0x18000ec2f  mov     edx, 11h
0x18000ec34  mov     r9, rax
0x18000ec37  mov     r8, r15
0x18000ec3a  call    WPP_SF_s
0x18000ec3f  mov     r10, cs:WPP_GLOBAL_Control
0x18000ec46  test    rdi, rdi
0x18000ec49  jnz     short loc_18000EC63
0x18000ec4b  cmp     r10, r14
0x18000ec4e  jz      short loc_18000EC8A
0x18000ec50  cmp     byte ptr [r10+19h], 2
0x18000ec55  jb      short loc_18000EC8A
0x18000ec57  lea     edx, [rdi+12h]
0x18000ec5a  lea     r9, aPpeerguid; "pPeerGuid"
0x18000ec61  jmp     short loc_18000EC7E
0x18000ec63  test    rsi, rsi
0x18000ec66  jnz     short loc_18000EC94
0x18000ec68  cmp     r10, r14
0x18000ec6b  jz      short loc_18000EC8A
0x18000ec6d  cmp     byte ptr [r10+19h], 2
0x18000ec72  jb      short loc_18000EC8A
0x18000ec74  lea     edx, [rsi+13h]
0x18000ec77  lea     r9, aPppeerOut; "ppPeer_out"
0x18000ec7e  mov     rcx, [r10+10h]
0x18000ec82  mov     r8, r15
0x18000ec85  call    WPP_SF_s
0x18000ec8a  mov     eax, 80004003h
0x18000ec8f  jmp     loc_18000ED7C
0x18000ec94  mov     rcx, rbp; lpCriticalSection
0x18000ec97  mov     qword ptr [rsi], 0
0x18000ec9e  call    cs:__imp_EnterCriticalSection
0x18000eca4  mov     r8, rdi
0x18000eca7  lea     rdx, [rsp+78h+var_48]
0x18000ecac  lea     rcx, [rbp+50h]
0x18000ecb0  call    ?find@?$_Tree@V?$_Tmap_traits@U_GUID@@PEAVCWcnPeer@@UGuidCompare@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVCWcnPeer@@@std@@@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@PEAVCWcnPeer@@@std@@@std@@@std@@@2@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,CWcnPeer *,GuidCompare,std::allocator<std::pair<_GUID const,CWcnPeer *>>,0>>::find(_GUID const &)
0x18000ecb5  mov     rcx, [rax]
0x18000ecb8  cmp     rcx, [rbp+50h]
0x18000ecbc  jnz     short loc_18000ED09
0x18000ecbe  lea     r8, [rsp+78h+arg_8]
0x18000ecc6  mov     rdx, rdi
0x18000ecc9  mov     rcx, rbp
0x18000eccc  call    ?CreateNewPeer@CWcnPeerCache@@AEAAJPEBU_GUID@@PEAPEAVCWcnPeer@@W4tagWCN_PROTOCOL_VERSION@@@Z; CWcnPeerCache::CreateNewPeer(_GUID const *,CWcnPeer * *,tagWCN_PROTOCOL_VERSION)
0x18000ecd1  mov     ebx, eax
0x18000ecd3  test    eax, eax
0x18000ecd5  jns     short loc_18000ECFF
0x18000ecd7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ecde  cmp     rcx, r14
0x18000ece1  jz      short loc_18000ED3A
0x18000ece3  cmp     byte ptr [rcx+19h], 2
0x18000ece7  jb      short loc_18000ED3A
0x18000ece9  mov     rcx, [rcx+10h]
0x18000eced  mov     edx, 14h
0x18000ecf2  mov     r9d, eax
0x18000ecf5  mov     r8, r15
0x18000ecf8  call    WPP_SF_d
0x18000ecfd  jmp     short loc_18000ED3A
0x18000ecff  mov     rdi, [rsp+78h+arg_8]
0x18000ed07  jmp     short loc_18000ED37
0x18000ed09  mov     rdi, [rcx+30h]
0x18000ed0d  xor     ebx, ebx
0x18000ed0f  call    cs:__imp_GetTickCount64
0x18000ed15  lea     rcx, [rax+15F90h]
0x18000ed1c  add     rax, 1D4C0h
0x18000ed22  mov     [rdi+118h], rax
0x18000ed29  mov     [rdi+110h], rcx
0x18000ed30  lock inc dword ptr [rdi+108h]
0x18000ed37  mov     [rsi], rdi
0x18000ed3a  mov     rcx, rbp; lpCriticalSection
0x18000ed3d  call    cs:__imp_LeaveCriticalSection
0x18000ed43  mov     r10, cs:WPP_GLOBAL_Control
0x18000ed4a  cmp     r10, r14
0x18000ed4d  jz      short loc_18000ED7A
0x18000ed4f  test    ebx, ebx
0x18000ed51  js      short loc_18000ED5A
0x18000ed53  cmp     byte ptr [r10+19h], 6
0x18000ed58  jb      short loc_18000ED7A
0x18000ed5a  or      ecx, 0FFFFFFFFh; int
0x18000ed5d  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000ed62  mov     rcx, [r10+10h]
0x18000ed66  mov     edx, 15h
0x18000ed6b  mov     r9, rax
0x18000ed6e  mov     [rsp+78h+var_58], ebx
0x18000ed72  mov     r8, r15
0x18000ed75  call    WPP_SF_sd
0x18000ed7a  mov     eax, ebx
0x18000ed7c  add     rsp, 48h
0x18000ed80  pop     r15
0x18000ed82  pop     r14
0x18000ed84  pop     rdi
0x18000ed85  pop     rsi
0x18000ed86  pop     rbp
0x18000ed87  pop     rbx
0x18000ed88  retn
```
