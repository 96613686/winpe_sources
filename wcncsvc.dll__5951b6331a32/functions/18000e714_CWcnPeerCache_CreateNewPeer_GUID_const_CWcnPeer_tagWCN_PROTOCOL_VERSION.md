# CWcnPeerCache::CreateNewPeer(_GUID const *,CWcnPeer * *,tagWCN_PROTOCOL_VERSION)

- ea: `0x18000e714`
- end: `0x18000eab7`
- name: `?CreateNewPeer@CWcnPeerCache@@AEAAJPEBU_GUID@@PEAPEAVCWcnPeer@@W4tagWCN_PROTOCOL_VERSION@@@Z`
- size: `931`
- prototype: `__int64 __fastcall(__int64 ***, __int128 *, CWcnPeer **)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18000ebe0`

## callees

- `0x180001404`
- `0x180003044`
- `0x180004f78`
- `0x180004fb8`
- `0x180005014`
- `0x180005088`
- `0x18000c864`
- `0x18000db10`
- `0x18000e714`
- `0x18000eac0`
- `0x18000f4e0`
- `0x18000f5e4`
- `0x18001028c`
- `0x18001d920`
- `0x18001d9dc`
- `0x180053004`
- `0x18005a010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000ea65`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000ea65`

## string_xrefs

- `0x18000e95d`: `pProtocol`

## pseudocode

```c
__int64 __fastcall CWcnPeerCache::CreateNewPeer(__int64 ***a1, __int128 *a2, CWcnPeer **a3)
{
  __int128 *v4; // r12
  __int64 ***v5; // r15
  _QWORD *v6; // r10
  const char *Indent; // rax
  __int64 v8; // r10
  int Protocol; // eax
  int v11; // ebx
  _QWORD *v12; // r10
  CWcnPeer *v13; // r13
  unsigned int v14; // eax
  char v15; // r10
  CWcnPeer *v16; // rax
  CWcnPeer *v17; // r14
  bool *v18; // r9
  const struct _GUID *v19; // rdx
  CWcnPeerCache *v20; // rcx
  int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // r9
  const char *v24; // rax
  __int64 v25; // r10
  unsigned int v26; // eax
  __int64 v27; // r10
  unsigned int v28; // eax
  __int64 v29; // r10
  __int64 v30; // rax
  CWcnPeer *v31; // [rsp+30h] [rbp-58h] BYREF
  CWcnPeer *v32; // [rsp+38h] [rbp-50h]
  std::bad_alloc *v33; // [rsp+40h] [rbp-48h] BYREF

  v4 = a2;
  v5 = a1;
  v31 = 0;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v8 + 16), 52, WPP_f34e634574083547aa3a426270948a29_Traceguids, Indent);
    v6 = WPP_GLOBAL_Control;
  }
  if ( a3 )
  {
    *a3 = 0;
    Protocol = CWcnService::GetProtocol((__int64)g_pWcnService, 0, &v31);
    v11 = Protocol;
    if ( Protocol < 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return (unsigned int)v11;
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          54,
          WPP_f34e634574083547aa3a426270948a29_Traceguids,
          (unsigned int)Protocol);
LABEL_44:
        v12 = WPP_GLOBAL_Control;
        goto LABEL_45;
      }
      goto LABEL_45;
    }
    v32 = 0;
    if ( Protocol != 1
      || WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
    {
      v13 = v31;
    }
    else
    {
      v13 = v31;
      (*(void (__fastcall **)(CWcnPeer *))(*(_QWORD *)v31 + 32LL))(v31);
      v14 = (unsigned int)GetIndent(0);
      WPP_SF_sld(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        55,
        (unsigned int)WPP_f34e634574083547aa3a426270948a29_Traceguids,
        v14,
        0,
        v15);
    }
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      v16 = (CWcnPeer *)operator new(0x130u);
      v31 = v16;
      if ( v16 )
        v17 = CWcnPeer::CWcnPeer(v16);
      else
        v17 = 0;
      v32 = v17;
      *std::map<_GUID,CWcnPeer *,GuidCompare,std::allocator<std::pair<_GUID const,CWcnPeer *>>>::operator[](v5 + 10, v4) = (__int64)v17;
      v19 = (const struct _GUID *)v4;
      v20 = (CWcnPeerCache *)v5;
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', &v33) )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v30 = (*(__int64 (__fastcall **)(std::bad_alloc *))(*(_QWORD *)v33 + 8LL))(v33);
          WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_f34e634574083547aa3a426270948a29_Traceguids, v30);
        }
        v5 = a1;
        v4 = a2;
        v11 = -2147024882;
        v17 = v32;
        __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_18000EA0D);
        goto LABEL_41;
      }
    }
    v21 = CWcnPeerCache::SetPeerNotificationFilter(v20, v19, 0, v18);
    v11 = v21;
    if ( v21 >= 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v24 = GetIndent(1);
        WPP_SF_s(*(_QWORD *)(v25 + 16), 10, WPP_805ccd1b393d3e4b99a4efc8134fe3a0_Traceguids, v24);
        v12 = WPP_GLOBAL_Control;
      }
      if ( v13 )
      {
        *((_QWORD *)v17 + 15) = v13;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
        {
          v26 = (unsigned int)GetIndent(-1);
          WPP_SF_sd(*(_QWORD *)(v27 + 16), 12, (unsigned int)WPP_805ccd1b393d3e4b99a4efc8134fe3a0_Traceguids, v26, 0);
        }
        v11 = 0;
        CWcnIdentity::SetUuid((CWcnPeer *)((char *)v17 + 136), (const struct _GUID *)v4);
        CWcnPeerCache::SchedulePeerCacheReaper((CWcnPeerCache *)v5);
        ++*((_DWORD *)v17 + 67);
        *a3 = v17;
        goto LABEL_44;
      }
      if ( v12 != &WPP_GLOBAL_Control && *((_BYTE *)v12 + 25) >= 2u )
      {
        WPP_SF_s(v12[2], 11, WPP_805ccd1b393d3e4b99a4efc8134fe3a0_Traceguids, "pProtocol");
        v12 = WPP_GLOBAL_Control;
      }
      v11 = -2147467261;
      if ( v12 != &WPP_GLOBAL_Control && *((_BYTE *)v12 + 25) >= 2u )
      {
        v22 = 58;
        v23 = 2147500035LL;
        goto LABEL_26;
      }
    }
    else
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v22 = 57;
        v23 = (unsigned int)v21;
LABEL_26:
        WPP_SF_d(v12[2], v22, WPP_f34e634574083547aa3a426270948a29_Traceguids, v23);
LABEL_41:
        v12 = WPP_GLOBAL_Control;
      }
    }
    if ( v17 )
    {
      std::_Tree<std::_Tmap_traits<_GUID,CWcnPeer *,GuidCompare,std::allocator<std::pair<_GUID const,CWcnPeer *>>,0>>::erase(
        (__int64 *)v5 + 10,
        v4);
      CWcnPeerCache::DeletePeerNotificationFilter((struct _RTL_CRITICAL_SECTION *)v5, (const struct _GUID *)v4);
      CWcnPeer::~CWcnPeer(v17);
      operator delete(v17);
      goto LABEL_44;
    }
LABEL_45:
    if ( v12 != &WPP_GLOBAL_Control && (v11 < 0 || *((_BYTE *)v12 + 25) >= 6u) )
    {
      v28 = (unsigned int)GetIndent(-1);
      WPP_SF_sd(*(_QWORD *)(v29 + 16), 59, (unsigned int)WPP_f34e634574083547aa3a426270948a29_Traceguids, v28, v11);
    }
    return (unsigned int)v11;
  }
  if ( v6 != &WPP_GLOBAL_Control && *((_BYTE *)v6 + 25) >= 2u )
    WPP_SF_s(v6[2], 53, WPP_f34e634574083547aa3a426270948a29_Traceguids, "ppPeer");
  return 2147500035LL;
}

```

## disassembly

```asm
0x18000e714  mov     rax, rsp
0x18000e717  mov     [rax+20h], r9d
0x18000e71b  mov     [rax+18h], r8
0x18000e71f  mov     [rax+10h], rdx
0x18000e723  mov     [rax+8], rcx
0x18000e727  push    rbx
0x18000e728  push    rsi
0x18000e729  push    r12
0x18000e72b  push    r13
0x18000e72d  push    r14
0x18000e72f  push    r15
0x18000e731  sub     rsp, 58h
0x18000e735  mov     rbx, r8
0x18000e738  mov     r12, rdx
0x18000e73b  mov     r15, rcx
0x18000e73e  mov     qword ptr [rax-58h], 0
0x18000e746  lea     rsi, WPP_GLOBAL_Control
0x18000e74d  mov     r10, cs:WPP_GLOBAL_Control
0x18000e754  cmp     r10, rsi
0x18000e757  jz      short loc_18000E789
0x18000e759  cmp     byte ptr [r10+19h], 6
0x18000e75e  jb      short loc_18000E789
0x18000e760  mov     ecx, 1; int
0x18000e765  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000e76a  mov     edx, 34h ; '4'
0x18000e76f  mov     r9, rax
0x18000e772  lea     r8, WPP_f34e634574083547aa3a426270948a29_Traceguids
0x18000e779  mov     rcx, [r10+10h]
0x18000e77d  call    WPP_SF_s
0x18000e782  mov     r10, cs:WPP_GLOBAL_Control
0x18000e789  test    rbx, rbx
0x18000e78c  jnz     short loc_18000E7BE
0x18000e78e  cmp     r10, rsi
0x18000e791  jz      short loc_18000E7B4
0x18000e793  cmp     byte ptr [r10+19h], 2
0x18000e798  jb      short loc_18000E7B4
0x18000e79a  lea     edx, [rbx+35h]
0x18000e79d  lea     r9, aPppeer; "ppPeer"
0x18000e7a4  lea     r8, WPP_f34e634574083547aa3a426270948a29_Traceguids
0x18000e7ab  mov     rcx, [r10+10h]
0x18000e7af  call    WPP_SF_s
0x18000e7b4  mov     eax, 80004003h
0x18000e7b9  jmp     loc_18000EAA8
0x18000e7be  mov     qword ptr [rbx], 0
0x18000e7c5  lea     r8, [rsp+88h+var_58]
0x18000e7ca  xor     edx, edx
0x18000e7cc  mov     rcx, cs:?g_pWcnService@@3PEAVCWcnService@@EA; CWcnService * g_pWcnService
0x18000e7d3  call    ?GetProtocol@CWcnService@@QEAAJW4tagWCN_PROTOCOL_VERSION@@PEAPEAVIWcnProtocol@@@Z; CWcnService::GetProtocol(tagWCN_PROTOCOL_VERSION,IWcnProtocol * *)
0x18000e7d8  mov     ebx, eax
0x18000e7da  test    eax, eax
0x18000e7dc  jns     short loc_18000E816
0x18000e7de  mov     r10, cs:WPP_GLOBAL_Control
0x18000e7e5  cmp     r10, rsi
0x18000e7e8  jz      loc_18000EAA6
0x18000e7ee  cmp     byte ptr [r10+19h], 2
0x18000e7f3  jb      loc_18000EA72
0x18000e7f9  mov     edx, 36h ; '6'
0x18000e7fe  mov     r9d, eax
0x18000e801  lea     r8, WPP_f34e634574083547aa3a426270948a29_Traceguids
0x18000e808  mov     rcx, [r10+10h]
0x18000e80c  call    WPP_SF_d
0x18000e811  jmp     loc_18000EA6B
0x18000e816  mov     [rsp+88h+var_50], 0
0x18000e81f  cmp     eax, 1
0x18000e822  jnz     short loc_18000E883
0x18000e824  mov     rax, cs:WPP_GLOBAL_Control
0x18000e82b  cmp     rax, rsi
0x18000e82e  jz      short loc_18000E883
0x18000e830  cmp     byte ptr [rax+19h], 3
0x18000e834  jb      short loc_18000E883
0x18000e836  mov     r13, [rsp+88h+var_58]
0x18000e83b  mov     rax, [r13+0]
0x18000e83f  mov     rcx, r13
0x18000e842  mov     rax, [rax+20h]
0x18000e846  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e84b  mov     r10d, eax
0x18000e84e  xor     ecx, ecx; int
0x18000e850  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000e855  mov     edx, 37h ; '7'
0x18000e85a  mov     [rsp+88h+var_60], r10d
0x18000e85f  mov     [rsp+88h+var_68], 0
0x18000e867  mov     r9, rax
0x18000e86a  lea     r8, WPP_f34e634574083547aa3a426270948a29_Traceguids
0x18000e871  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e878  mov     rcx, [rcx+10h]
0x18000e87c  call    WPP_SF_sld
0x18000e881  jmp     short loc_18000E888
0x18000e883  mov     r13, [rsp+88h+var_58]
0x18000e888  mov     ecx, 130h; Size
0x18000e88d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e892  mov     [rsp+88h+var_58], rax
0x18000e897  test    rax, rax
0x18000e89a  jz      short loc_18000E8A9
0x18000e89c  mov     rcx, rax; this
0x18000e89f  call    ??0CWcnPeer@@QEAA@XZ; CWcnPeer::CWcnPeer(void)
0x18000e8a4  mov     r14, rax
0x18000e8a7  jmp     short loc_18000E8AC
0x18000e8a9  xor     r14d, r14d
0x18000e8ac  mov     [rsp+88h+var_50], r14
0x18000e8b1  lea     rcx, [r15+50h]
0x18000e8b5  mov     rdx, r12
0x18000e8b8  call    ??A?$map@U_GUID@@PEAVCWcnPeer@@UGuidCompare@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVCWcnPeer@@@std@@@std@@@std@@QEAAAEAPEAVCWcnPeer@@AEBU_GUID@@@Z; std::map<_GUID,CWcnPeer *,GuidCompare,std::allocator<std::pair<_GUID const,CWcnPeer *>>>::operator[](_GUID const &)
0x18000e8bd  mov     [rax], r14
0x18000e8c0  xor     r8d, r8d; unsigned int
0x18000e8c3  mov     rdx, r12; struct _GUID *
0x18000e8c6  mov     rcx, r15; this
0x18000e8c9  call    ?SetPeerNotificationFilter@CWcnPeerCache@@QEAAJPEBU_GUID@@KPEA_N@Z; CWcnPeerCache::SetPeerNotificationFilter(_GUID const *,ulong,bool *)
0x18000e8ce  mov     ebx, eax
0x18000e8d0  test    eax, eax
0x18000e8d2  jns     short loc_18000E90C
0x18000e8d4  mov     r10, cs:WPP_GLOBAL_Control
0x18000e8db  cmp     r10, rsi
0x18000e8de  jz      loc_18000EA37
0x18000e8e4  cmp     byte ptr [r10+19h], 2
0x18000e8e9  jb      loc_18000EA37
0x18000e8ef  mov     edx, 39h ; '9'
0x18000e8f4  mov     r9d, eax
0x18000e8f7  lea     r8, WPP_f34e634574083547aa3a426270948a29_Traceguids
0x18000e8fe  mov     rcx, [r10+10h]
0x18000e902  call    WPP_SF_d
0x18000e907  jmp     loc_18000EA30
0x18000e90c  mov     r10, cs:WPP_GLOBAL_Control
0x18000e913  cmp     r10, rsi
0x18000e916  jz      short loc_18000E948
0x18000e918  cmp     byte ptr [r10+19h], 6
0x18000e91d  jb      short loc_18000E948
0x18000e91f  mov     ecx, 1; int
0x18000e924  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000e929  mov     edx, 0Ah
0x18000e92e  mov     r9, rax
0x18000e931  lea     r8, WPP_805ccd1b393d3e4b99a4efc8134fe3a0_Traceguids
0x18000e938  mov     rcx, [r10+10h]
0x18000e93c  call    WPP_SF_s
0x18000e941  mov     r10, cs:WPP_GLOBAL_Control
0x18000e948  test    r13, r13
0x18000e94b  jnz     short loc_18000E9A1
0x18000e94d  cmp     r10, rsi
0x18000e950  jz      short loc_18000E97B
0x18000e952  cmp     byte ptr [r10+19h], 2
0x18000e957  jb      short loc_18000E97B
0x18000e959  lea     edx, [r13+0Bh]
0x18000e95d  lea     r9, aPprotocol; "pProtocol"
0x18000e964  lea     r8, WPP_805ccd1b393d3e4b99a4efc8134fe3a0_Traceguids
0x18000e96b  mov     rcx, [r10+10h]
0x18000e96f  call    WPP_SF_s
0x18000e974  mov     r10, cs:WPP_GLOBAL_Control
0x18000e97b  mov     ebx, 80004003h
0x18000e980  cmp     r10, rsi
0x18000e983  jz      loc_18000EA37
0x18000e989  cmp     byte ptr [r10+19h], 2
0x18000e98e  jb      loc_18000EA37
0x18000e994  mov     edx, 3Ah ; ':'
0x18000e999  mov     r9d, ebx
0x18000e99c  jmp     loc_18000E8F7
0x18000e9a1  mov     [r14+78h], r13
0x18000e9a5  mov     r10, cs:WPP_GLOBAL_Control
0x18000e9ac  cmp     r10, rsi
0x18000e9af  jz      short loc_18000E9E0
0x18000e9b1  cmp     byte ptr [r10+19h], 6
0x18000e9b6  jb      short loc_18000E9E0
0x18000e9b8  or      ecx, 0FFFFFFFFh; int
0x18000e9bb  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000e9c0  mov     edx, 0Ch
0x18000e9c5  mov     [rsp+88h+var_68], 0
0x18000e9cd  mov     r9, rax
0x18000e9d0  lea     r8, WPP_805ccd1b393d3e4b99a4efc8134fe3a0_Traceguids
0x18000e9d7  mov     rcx, [r10+10h]
0x18000e9db  call    WPP_SF_sd
0x18000e9e0  xor     ebx, ebx
0x18000e9e2  lea     rcx, [r14+88h]; this
0x18000e9e9  mov     rdx, r12; struct _GUID *
0x18000e9ec  call    ?SetUuid@CWcnIdentity@@QEAAJPEBU_GUID@@@Z; CWcnIdentity::SetUuid(_GUID const *)
0x18000e9f1  mov     rcx, r15; this
0x18000e9f4  call    ?SchedulePeerCacheReaper@CWcnPeerCache@@QEAAXXZ; CWcnPeerCache::SchedulePeerCacheReaper(void)
0x18000e9f9  inc     dword ptr [r14+10Ch]
0x18000ea00  mov     rax, [rsp+88h+arg_10]
0x18000ea08  mov     [rax], r14
0x18000ea0b  jmp     short loc_18000EA6B
0x18000ea0d  mov     r15, [rsp+88h+arg_0]
0x18000ea15  lea     rsi, WPP_GLOBAL_Control
0x18000ea1c  mov     r12, [rsp+88h+arg_8]
0x18000ea24  mov     ebx, [rsp+88h+arg_18]
0x18000ea2b  mov     r14, [rsp+88h+var_50]
0x18000ea30  mov     r10, cs:WPP_GLOBAL_Control
0x18000ea37  mov     rcx, r15
0x18000ea3a  mov     eax, 50h ; 'P'
0x18000ea3f  test    r14, r14
0x18000ea42  jz      short loc_18000EA72
0x18000ea44  add     rcx, rax
0x18000ea47  mov     rdx, r12
0x18000ea4a  call    ?erase@?$_Tree@V?$_Tmap_traits@U_GUID@@PEAVCWcnPeer@@UGuidCompare@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVCWcnPeer@@@std@@@std@@$0A@@std@@@std@@QEAA_KAEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,CWcnPeer *,GuidCompare,std::allocator<std::pair<_GUID const,CWcnPeer *>>,0>>::erase(_GUID const &)
0x18000ea4f  mov     rdx, r12; struct _GUID *
0x18000ea52  mov     rcx, r15; this
0x18000ea55  call    ?DeletePeerNotificationFilter@CWcnPeerCache@@AEAAJPEBU_GUID@@@Z; CWcnPeerCache::DeletePeerNotificationFilter(_GUID const *)
0x18000ea5a  mov     rcx, r14; this
0x18000ea5d  call    ??1CWcnPeer@@QEAA@XZ; CWcnPeer::~CWcnPeer(void)
0x18000ea62  mov     rcx, r14
0x18000ea65  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000ea6b  mov     r10, cs:WPP_GLOBAL_Control
0x18000ea72  cmp     r10, rsi
0x18000ea75  jz      short loc_18000EAA6
0x18000ea77  test    ebx, ebx
0x18000ea79  js      short loc_18000EA82
0x18000ea7b  cmp     byte ptr [r10+19h], 6
0x18000ea80  jb      short loc_18000EAA6
0x18000ea82  or      ecx, 0FFFFFFFFh; int
0x18000ea85  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000ea8a  mov     edx, 3Bh ; ';'
0x18000ea8f  mov     [rsp+88h+var_68], ebx
0x18000ea93  mov     r9, rax
0x18000ea96  lea     r8, WPP_f34e634574083547aa3a426270948a29_Traceguids
0x18000ea9d  mov     rcx, [r10+10h]
0x18000eaa1  call    WPP_SF_sd
0x18000eaa6  mov     eax, ebx
0x18000eaa8  add     rsp, 58h
0x18000eaac  pop     r15
0x18000eaae  pop     r14
0x18000eab0  pop     r13
0x18000eab2  pop     r12
0x18000eab4  pop     rsi
0x18000eab5  pop     rbx
0x18000eab6  retn
```
