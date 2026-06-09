# CWcnEventSink::QueueNotification(tagWCNPRPC_NOTIFICATION const *)

- ea: `0x18003cad0`
- end: `0x18003cf9e`
- name: `?QueueNotification@CWcnEventSink@@QEAAJPEBUtagWCNPRPC_NOTIFICATION@@@Z`
- size: `1230`
- prototype: `__int64 __fastcall(CWcnEventSink *__hidden this, const struct tagWCNPRPC_NOTIFICATION *)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, service_task`

## callers

- `0x180002ec0`
- `0x180032960`

## callees

- `0x180001404`
- `0x1800015d0`
- `0x180001b68`
- `0x180004f78`
- `0x180004fb8`
- `0x180005014`
- `0x18000cd68`
- `0x18000ce18`
- `0x18000ed90`
- `0x18003986c`
- `0x18003c854`
- `0x18003cad0`
- `0x18003cfa4`
- `0x180053004`
- `0x180056490`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18003cf3e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003cf3e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003cb74`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003cb74`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003cf30`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003cf30`

## string_xrefs

- `0x18003cbbd`: `pNotificationCopy`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWcnEventSink::QueueNotification(CWcnEventSink *this, const struct tagWCNPRPC_NOTIFICATION *a2)
{
  _QWORD *v4; // r10
  const char *Indent; // rax
  __int64 v6; // r10
  struct tagWCNPRPC_NOTIFICATION *v8; // rax
  struct tagWCNPRPC_NOTIFICATION *v9; // rsi
  int v10; // edi
  __int64 v11; // rdx
  const char *v12; // r9
  __int64 v13; // rcx
  int v14; // eax
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r9
  __int64 v18; // rcx
  _BYTE *v19; // r10
  const char *v20; // rax
  __int64 v21; // r10
  const char *v22; // rax
  __int64 v23; // r10
  int PeerNotificationFilter; // eax
  int v25; // eax
  __int64 v26; // r10
  unsigned int v27; // eax
  __int64 v28; // r10
  __int64 v29; // rcx
  unsigned int v30; // eax
  const char *v31; // rax
  __int64 v32; // r10
  __int64 v33; // rax
  unsigned int v34; // eax
  __int64 v35; // r10
  char v36; // r11
  _QWORD *v37; // rsi
  _QWORD *v38; // rax
  __int64 v39; // r13
  __int64 v40; // rdx
  __int64 v41; // rax
  unsigned int v42; // eax
  __int64 v43; // r10
  __int64 v44; // rax
  struct _RTL_CRITICAL_SECTION *lpCriticalSection; // [rsp+30h] [rbp-38h]
  std::bad_alloc *v46; // [rsp+38h] [rbp-30h] BYREF
  _QWORD *v47; // [rsp+78h] [rbp+10h] BYREF
  unsigned int v48; // [rsp+80h] [rbp+18h] BYREF
  struct tagWCNPRPC_NOTIFICATION *v49; // [rsp+88h] [rbp+20h] BYREF

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v6 + 16), 15, WPP_5d51192a8202375b23254a09b83c8f5c_Traceguids, Indent);
    v4 = WPP_GLOBAL_Control;
  }
  if ( !a2 )
  {
    if ( v4 != &WPP_GLOBAL_Control && *((_BYTE *)v4 + 25) >= 2u )
      WPP_SF_s(v4[2], 16, WPP_5d51192a8202375b23254a09b83c8f5c_Traceguids, "pNotification");
    return 2147500035LL;
  }
  lpCriticalSection = (struct _RTL_CRITICAL_SECTION *)((char *)this + 24);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v8 = (struct tagWCNPRPC_NOTIFICATION *)operator new(0x48u, (const struct std::nothrow_t *)&std::nothrow);
  v9 = v8;
  v49 = v8;
  if ( !v8 )
  {
    v10 = -2147024882;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_69;
    v11 = 17;
    v12 = "pNotificationCopy";
    v13 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    goto LABEL_13;
  }
  *(_DWORD *)v8 = 0;
  v14 = WcnCopyNotification(v8, a2);
  v10 = v14;
  if ( v14 < 0 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_69;
    v16 = 18;
    goto LABEL_18;
  }
  v10 = 0;
  v19 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    v20 = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v21 + 16), 39, WPP_5d51192a8202375b23254a09b83c8f5c_Traceguids, v20);
    v19 = WPP_GLOBAL_Control;
  }
  if ( *(_DWORD *)v9 )
    goto LABEL_39;
  v48 = 0;
  LOBYTE(v47) = 0;
  if ( *((_QWORD *)g_pWcnService + 7) == -192 )
  {
    if ( v19 != (_BYTE *)&WPP_GLOBAL_Control && v19[25] >= 2u )
    {
      v22 = GetIndent(0);
      WPP_SF_s(*(_QWORD *)(v23 + 16), 40, WPP_5d51192a8202375b23254a09b83c8f5c_Traceguids, v22);
      v19 = WPP_GLOBAL_Control;
    }
    v10 = -2147467259;
    goto LABEL_39;
  }
  PeerNotificationFilter = CWcnPeerCache::GetPeerNotificationFilter(
                             (CWcnPeerCache *)(*((_QWORD *)g_pWcnService + 7) + 192LL),
                             (const struct _GUID *)((char *)v9 + 12),
                             &v48,
                             (bool *)&v47);
  v10 = PeerNotificationFilter;
  if ( PeerNotificationFilter >= 0 )
  {
    if ( (_BYTE)v47
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      v25 = (unsigned int)GetIndent(0);
      WPP_SF_s_guid_(
        *(_QWORD *)(v26 + 16),
        42,
        (int)WPP_5d51192a8202375b23254a09b83c8f5c_Traceguids,
        v25,
        (__int64)v9 + 12);
    }
    *((_DWORD *)v9 + 7) |= v48;
    goto LABEL_38;
  }
  v19 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    goto LABEL_43;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF__guid_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      41,
      WPP_5d51192a8202375b23254a09b83c8f5c_Traceguids,
      (char *)v9 + 12,
      PeerNotificationFilter);
LABEL_38:
    v19 = WPP_GLOBAL_Control;
  }
LABEL_39:
  if ( v19 != (_BYTE *)&WPP_GLOBAL_Control && (v10 < 0 || v19[25] >= 6u) )
  {
    v27 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v28 + 16), 43, (unsigned int)WPP_5d51192a8202375b23254a09b83c8f5c_Traceguids, v27, v10);
    v19 = WPP_GLOBAL_Control;
  }
LABEL_43:
  if ( v10 < 0 )
  {
    if ( v19 == (_BYTE *)&WPP_GLOBAL_Control || v19[25] < 2u )
      goto LABEL_69;
    v16 = 19;
    v17 = (unsigned int)v10;
    v18 = *((_QWORD *)v19 + 2);
    goto LABEL_19;
  }
  v29 = *(unsigned int *)v9;
  if ( !(_DWORD)v29 )
  {
    v30 = *((_DWORD *)v9 + 7);
    if ( v30 )
    {
      if ( (v30 & *((_DWORD *)this + 26)) == 0 )
      {
        if ( v19 == (_BYTE *)&WPP_GLOBAL_Control || v19[25] < 5u )
          goto LABEL_69;
        v31 = GetIndent(0);
        v11 = 20;
        v12 = v31;
        v13 = *(_QWORD *)(v32 + 16);
LABEL_13:
        WPP_SF_s(v13, v11, WPP_5d51192a8202375b23254a09b83c8f5c_Traceguids, v12);
        goto LABEL_69;
      }
    }
  }
  if ( !*((_QWORD *)this + 8) )
  {
    v33 = *((_QWORD *)this + 10);
    if ( v33 && *(_QWORD *)(v33 + 8) > 0x3E8u )
    {
      v10 = -2147023604;
      if ( v19 != (_BYTE *)&WPP_GLOBAL_Control && v19[25] >= 3u )
      {
        v34 = (unsigned int)GetIndent(0);
        WPP_SF_sd(*(_QWORD *)(v35 + 16), 22, (unsigned int)WPP_5d51192a8202375b23254a09b83c8f5c_Traceguids, v34, v36);
      }
    }
    else
    {
      try
      {
        v37 = (_QWORD *)*((_QWORD *)this + 10);
        if ( !v37 )
        {
          v38 = operator new(0x10u);
          v37 = v38;
          v47 = v38;
          if ( v38 )
          {
            *v38 = 0;
            v38[1] = 0;
            *v38 = std::_List_alloc<0,std::_List_base_types<CWcnPeer *>>::_Buynode0(v29, 0, 0);
          }
          *((_QWORD *)this + 10) = v37;
        }
        v39 = *v37;
        v40 = std::_List_buy<CWcnPeer *>::_Buynode<CWcnPeer * const &>(v29, *v37, *(_QWORD *)(*v37 + 8LL), &v49);
        v41 = v37[1];
        if ( v41 == 0xAAAAAAAAAAAAAA9LL )
          std::_Xlength_error("list<T> too long");
        v37[1] = v41 + 1;
        *(_QWORD *)(v39 + 8) = v40;
        **(_QWORD **)(v40 + 8) = v40;
        v9 = 0;
        v49 = 0;
      }
      catch ( std::bad_alloc *v46 )
      {
        LODWORD(v47) = -2147024882;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v44 = (*(__int64 (__fastcall **)(std::bad_alloc *))(*(_QWORD *)v46 + 8LL))(v46);
          WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_5d51192a8202375b23254a09b83c8f5c_Traceguids, v44);
        }
        v10 = (int)v47;
        v9 = v49;
        goto LABEL_69;
      }
    }
    goto LABEL_69;
  }
  v14 = CWcnEventSink::DeliverNotification(this, v9);
  v10 = v14;
  if ( v14 < 0 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v16 = 21;
LABEL_18:
      v17 = (unsigned int)v14;
      v18 = v15[2];
LABEL_19:
      WPP_SF_d(v18, v16, WPP_5d51192a8202375b23254a09b83c8f5c_Traceguids, v17);
    }
  }
LABEL_69:
  LeaveCriticalSection(lpCriticalSection);
  if ( v9 )
    operator delete(v9);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (v10 < 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u) )
  {
    v42 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v43 + 16), 24, (unsigned int)WPP_5d51192a8202375b23254a09b83c8f5c_Traceguids, v42, v10);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18003cad0  mov     [rsp+arg_0], rsi
0x18003cad5  push    rdi
0x18003cad6  push    r12
0x18003cad8  push    r13
0x18003cada  push    r14
0x18003cadc  push    r15
0x18003cade  sub     rsp, 40h
0x18003cae2  mov     rdi, rdx
0x18003cae5  mov     r13, rcx
0x18003cae8  lea     r14, WPP_GLOBAL_Control
0x18003caef  mov     r10, cs:WPP_GLOBAL_Control
0x18003caf6  cmp     r10, r14
0x18003caf9  jz      short loc_18003CB30
0x18003cafb  cmp     byte ptr [r10+19h], 6
0x18003cb00  jb      short loc_18003CB30
0x18003cb02  mov     ecx, 1; int
0x18003cb07  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18003cb0c  mov     edx, 0Fh
0x18003cb11  mov     r9, rax
0x18003cb14  lea     r15, WPP_5d51192a8202375b23254a09b83c8f5c_Traceguids
0x18003cb1b  mov     r8, r15
0x18003cb1e  mov     rcx, [r10+10h]
0x18003cb22  call    WPP_SF_s
0x18003cb27  mov     r10, cs:WPP_GLOBAL_Control
0x18003cb2e  jmp     short loc_18003CB37
0x18003cb30  lea     r15, WPP_5d51192a8202375b23254a09b83c8f5c_Traceguids
0x18003cb37  test    rdi, rdi
0x18003cb3a  jnz     short loc_18003CB68
0x18003cb3c  cmp     r10, r14
0x18003cb3f  jz      short loc_18003CB5E
0x18003cb41  cmp     byte ptr [r10+19h], 2
0x18003cb46  jb      short loc_18003CB5E
0x18003cb48  lea     edx, [rdi+10h]
0x18003cb4b  lea     r9, aPnotification; "pNotification"
0x18003cb52  mov     r8, r15
0x18003cb55  mov     rcx, [r10+10h]
0x18003cb59  call    WPP_SF_s
0x18003cb5e  mov     eax, 80004003h
0x18003cb63  jmp     loc_18003CF7D
0x18003cb68  lea     rax, [r13+18h]
0x18003cb6c  mov     [rsp+68h+lpCriticalSection], rax
0x18003cb71  mov     rcx, rax; lpCriticalSection
0x18003cb74  call    cs:__imp_EnterCriticalSection
0x18003cb7a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003cb81  mov     ecx, 48h ; 'H'; unsigned __int64
0x18003cb86  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003cb8b  mov     rsi, rax
0x18003cb8e  mov     [rsp+68h+arg_18], rax
0x18003cb96  test    rax, rax
0x18003cb99  jnz     short loc_18003CBD5
0x18003cb9b  mov     edi, 8007000Eh
0x18003cba0  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cba7  cmp     rcx, r14
0x18003cbaa  jz      loc_18003CF2B
0x18003cbb0  cmp     byte ptr [rcx+19h], 2
0x18003cbb4  jb      loc_18003CF2B
0x18003cbba  lea     edx, [rax+11h]
0x18003cbbd  lea     r9, aPnotificationc; "pNotificationCopy"
0x18003cbc4  mov     rcx, [rcx+10h]
0x18003cbc8  mov     r8, r15
0x18003cbcb  call    WPP_SF_s
0x18003cbd0  jmp     loc_18003CF2B
0x18003cbd5  mov     dword ptr [rax], 0
0x18003cbdb  mov     rdx, rdi; struct tagWCNPRPC_NOTIFICATION *
0x18003cbde  mov     rcx, rsi; struct tagWCNPRPC_NOTIFICATION *
0x18003cbe1  call    ?WcnCopyNotification@@YAJPEAUtagWCNPRPC_NOTIFICATION@@PEBU1@@Z; WcnCopyNotification(tagWCNPRPC_NOTIFICATION *,tagWCNPRPC_NOTIFICATION const *)
0x18003cbe6  mov     edi, eax
0x18003cbe8  test    eax, eax
0x18003cbea  jns     short loc_18003CC1F
0x18003cbec  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cbf3  cmp     rcx, r14
0x18003cbf6  jz      loc_18003CF2B
0x18003cbfc  cmp     byte ptr [rcx+19h], 2
0x18003cc00  jb      loc_18003CF2B
0x18003cc06  mov     edx, 12h
0x18003cc0b  mov     r9d, eax
0x18003cc0e  mov     rcx, [rcx+10h]
0x18003cc12  mov     r8, r15
0x18003cc15  call    WPP_SF_d
0x18003cc1a  jmp     loc_18003CF2B
0x18003cc1f  xor     edi, edi
0x18003cc21  mov     r10, cs:WPP_GLOBAL_Control
0x18003cc28  cmp     r10, r14
0x18003cc2b  jz      short loc_18003CC55
0x18003cc2d  cmp     byte ptr [r10+19h], 6
0x18003cc32  jb      short loc_18003CC55
0x18003cc34  lea     ecx, [rdi+1]; int
0x18003cc37  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18003cc3c  lea     edx, [rdi+27h]
0x18003cc3f  mov     r9, rax
0x18003cc42  mov     r8, r15
0x18003cc45  mov     rcx, [r10+10h]
0x18003cc49  call    WPP_SF_s
0x18003cc4e  mov     r10, cs:WPP_GLOBAL_Control
0x18003cc55  mov     ecx, [rsi]
0x18003cc57  test    ecx, ecx
0x18003cc59  jnz     loc_18003CD50
0x18003cc5f  mov     [rsp+68h+arg_10], edi
0x18003cc66  mov     byte ptr [rsp+68h+arg_8], dil
0x18003cc6b  mov     rax, cs:?g_pWcnService@@3PEAVCWcnService@@EA; CWcnService * g_pWcnService
0x18003cc72  mov     rcx, [rax+38h]
0x18003cc76  add     rcx, 0C0h; this
0x18003cc7d  jnz     short loc_18003CCB5
0x18003cc7f  cmp     r10, r14
0x18003cc82  jz      short loc_18003CCAB
0x18003cc84  cmp     byte ptr [r10+19h], 2
0x18003cc89  jb      short loc_18003CCAB
0x18003cc8b  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18003cc90  mov     edx, 28h ; '('
0x18003cc95  mov     r9, rax
0x18003cc98  mov     r8, r15
0x18003cc9b  mov     rcx, [r10+10h]
0x18003cc9f  call    WPP_SF_s
0x18003cca4  mov     r10, cs:WPP_GLOBAL_Control
0x18003ccab  mov     edi, 80004005h
0x18003ccb0  jmp     loc_18003CD50
0x18003ccb5  lea     r12, [rsi+0Ch]
0x18003ccb9  lea     r9, [rsp+68h+arg_8]; bool *
0x18003ccbe  lea     r8, [rsp+68h+arg_10]; unsigned int *
0x18003ccc6  mov     rdx, r12; struct _GUID *
0x18003ccc9  call    ?GetPeerNotificationFilter@CWcnPeerCache@@QEAAJPEBU_GUID@@PEAKPEA_N@Z; CWcnPeerCache::GetPeerNotificationFilter(_GUID const *,ulong *,bool *)
0x18003ccce  mov     edi, eax
0x18003ccd0  test    eax, eax
0x18003ccd2  jns     short loc_18003CD05
0x18003ccd4  mov     r10, cs:WPP_GLOBAL_Control
0x18003ccdb  cmp     r10, r14
0x18003ccde  jz      loc_18003CD87
0x18003cce4  cmp     byte ptr [r10+19h], 2
0x18003cce9  jb      short loc_18003CD50
0x18003cceb  mov     edx, 29h ; ')'
0x18003ccf0  mov     dword ptr [rsp+68h+var_48], eax
0x18003ccf4  mov     r9, r12
0x18003ccf7  mov     r8, r15
0x18003ccfa  mov     rcx, [r10+10h]
0x18003ccfe  call    WPP_SF__guid_d
0x18003cd03  jmp     short loc_18003CD49
0x18003cd05  cmp     byte ptr [rsp+68h+arg_8], 0
0x18003cd0a  jz      short loc_18003CD3F
0x18003cd0c  mov     r10, cs:WPP_GLOBAL_Control
0x18003cd13  cmp     r10, r14
0x18003cd16  jz      short loc_18003CD3F
0x18003cd18  cmp     byte ptr [r10+19h], 3
0x18003cd1d  jb      short loc_18003CD3F
0x18003cd1f  xor     ecx, ecx; int
0x18003cd21  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18003cd26  mov     edx, 2Ah ; '*'
0x18003cd2b  mov     [rsp+68h+var_48], r12
0x18003cd30  mov     r9, rax
0x18003cd33  mov     r8, r15
0x18003cd36  mov     rcx, [r10+10h]
0x18003cd3a  call    WPP_SF_s_guid_
0x18003cd3f  mov     eax, [rsp+68h+arg_10]
0x18003cd46  or      [rsi+1Ch], eax
0x18003cd49  mov     r10, cs:WPP_GLOBAL_Control
0x18003cd50  cmp     r10, r14
0x18003cd53  jz      short loc_18003CD87
0x18003cd55  test    edi, edi
0x18003cd57  js      short loc_18003CD60
0x18003cd59  cmp     byte ptr [r10+19h], 6
0x18003cd5e  jb      short loc_18003CD87
0x18003cd60  or      ecx, 0FFFFFFFFh; int
0x18003cd63  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18003cd68  mov     edx, 2Bh ; '+'
0x18003cd6d  mov     dword ptr [rsp+68h+var_48], edi
0x18003cd71  mov     r9, rax
0x18003cd74  mov     r8, r15
0x18003cd77  mov     rcx, [r10+10h]
0x18003cd7b  call    WPP_SF_sd
0x18003cd80  mov     r10, cs:WPP_GLOBAL_Control
0x18003cd87  test    edi, edi
0x18003cd89  jns     short loc_18003CDB0
0x18003cd8b  cmp     r10, r14
0x18003cd8e  jz      loc_18003CF2B
0x18003cd94  cmp     byte ptr [r10+19h], 2
0x18003cd99  jb      loc_18003CF2B
0x18003cd9f  mov     edx, 13h
0x18003cda4  mov     r9d, edi
0x18003cda7  mov     rcx, [r10+10h]
0x18003cdab  jmp     loc_18003CC12
0x18003cdb0  mov     ecx, [rsi]; int
0x18003cdb2  test    ecx, ecx
0x18003cdb4  jnz     short loc_18003CDED
0x18003cdb6  mov     eax, [rsi+1Ch]
0x18003cdb9  test    eax, eax
0x18003cdbb  jz      short loc_18003CDED
0x18003cdbd  test    [r13+68h], eax
0x18003cdc1  jnz     short loc_18003CDED
0x18003cdc3  cmp     r10, r14
0x18003cdc6  jz      loc_18003CF2B
0x18003cdcc  cmp     byte ptr [r10+19h], 5
0x18003cdd1  jb      loc_18003CF2B
0x18003cdd7  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18003cddc  mov     edx, 14h
0x18003cde1  mov     r9, rax
0x18003cde4  mov     rcx, [r10+10h]
0x18003cde8  jmp     loc_18003CBC8
0x18003cded  cmp     qword ptr [r13+40h], 0
0x18003cdf2  jz      short loc_18003CE2D
0x18003cdf4  mov     rdx, rsi; struct tagWCNPRPC_NOTIFICATION *
0x18003cdf7  mov     rcx, r13; this
0x18003cdfa  call    ?DeliverNotification@CWcnEventSink@@AEAAJPEBUtagWCNPRPC_NOTIFICATION@@@Z; CWcnEventSink::DeliverNotification(tagWCNPRPC_NOTIFICATION const *)
0x18003cdff  mov     edi, eax
0x18003ce01  test    eax, eax
0x18003ce03  jns     loc_18003CF2B
0x18003ce09  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ce10  cmp     rcx, r14
0x18003ce13  jz      loc_18003CF2B
0x18003ce19  cmp     byte ptr [rcx+19h], 2
0x18003ce1d  jb      loc_18003CF2B
0x18003ce23  mov     edx, 15h
0x18003ce28  jmp     loc_18003CC0B
0x18003ce2d  mov     rax, [r13+50h]
0x18003ce31  test    rax, rax
0x18003ce34  jz      short loc_18003CE80
0x18003ce36  mov     r11d, 3E8h
0x18003ce3c  cmp     [rax+8], r11
0x18003ce40  jbe     short loc_18003CE80
0x18003ce42  mov     edi, 8007050Ch
0x18003ce47  cmp     r10, r14
0x18003ce4a  jz      loc_18003CF2B
0x18003ce50  cmp     byte ptr [r10+19h], 3
0x18003ce55  jb      loc_18003CF2B
0x18003ce5b  xor     ecx, ecx; int
0x18003ce5d  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18003ce62  mov     edx, 16h
0x18003ce67  mov     dword ptr [rsp+68h+var_48], r11d
0x18003ce6c  mov     r9, rax
0x18003ce6f  mov     r8, r15
0x18003ce72  mov     rcx, [r10+10h]
0x18003ce76  call    WPP_SF_sd
0x18003ce7b  jmp     loc_18003CF2B
0x18003ce80  mov     rsi, [r13+50h]
0x18003ce84  test    rsi, rsi
0x18003ce87  jnz     short loc_18003CEBE
0x18003ce89  lea     ecx, [rsi+10h]; Size
0x18003ce8c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003ce91  mov     rsi, rax
0x18003ce94  mov     [rsp+68h+arg_8], rax
0x18003ce99  test    rsi, rsi
0x18003ce9c  jz      short loc_18003CEBA
0x18003ce9e  mov     qword ptr [rax], 0
0x18003cea5  mov     qword ptr [rax+8], 0
0x18003cead  xor     r8d, r8d
0x18003ceb0  xor     edx, edx
0x18003ceb2  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@PEAVCWcnPeer@@V?$allocator@PEAVCWcnPeer@@@std@@@std@@@std@@QEAAPEAU?$_List_node@PEAVCWcnPeer@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<CWcnPeer *>>::_Buynode0(std::_List_node<CWcnPeer *,void *> *,std::_List_node<CWcnPeer *,void *> *)
0x18003ceb7  mov     [rsi], rax
0x18003ceba  mov     [r13+50h], rsi
0x18003cebe  mov     r13, [rsi]
0x18003cec1  lea     r9, [rsp+68h+arg_18]
0x18003cec9  mov     r8, [r13+8]
0x18003cecd  mov     rdx, r13
0x18003ced0  call    ??$_Buynode@AEBQEAVCWcnPeer@@@?$_List_buy@PEAVCWcnPeer@@V?$allocator@PEAVCWcnPeer@@@std@@@std@@QEAAPEAU?$_List_node@PEAVCWcnPeer@@PEAX@1@PEAU21@0AEBQEAVCWcnPeer@@@Z; std::_List_buy<CWcnPeer *>::_Buynode<CWcnPeer * const &>(std::_List_node<CWcnPeer *,void *> *,std::_List_node<CWcnPeer *,void *> *,CWcnPeer * const &)
0x18003ced5  mov     rdx, rax
0x18003ced8  mov     rax, [rsi+8]
0x18003cedc  mov     rcx, 0AAAAAAAAAAAAAA9h
0x18003cee6  sub     rcx, rax
0x18003cee9  cmp     rcx, 1
0x18003ceed  jb      loc_18003CF90
0x18003cef3  inc     rax
0x18003cef6  mov     [rsi+8], rax
0x18003cefa  mov     [r13+8], rdx
0x18003cefe  mov     rax, [rdx+8]
0x18003cf02  mov     [rax], rdx
0x18003cf05  xor     esi, esi
0x18003cf07  mov     [rsp+68h+arg_18], rsi
0x18003cf0f  jmp     short loc_18003CF2B
0x18003cf11  lea     r14, WPP_GLOBAL_Control
0x18003cf18  lea     r15, WPP_5d51192a8202375b23254a09b83c8f5c_Traceguids
0x18003cf1f  mov     edi, dword ptr [rsp+68h+arg_8]
0x18003cf23  mov     rsi, [rsp+68h+arg_18]
0x18003cf2b  mov     rcx, [rsp+68h+lpCriticalSection]; lpCriticalSection
0x18003cf30  call    cs:__imp_LeaveCriticalSection
0x18003cf36  test    rsi, rsi
0x18003cf39  jz      short loc_18003CF44
0x18003cf3b  mov     rcx, rsi
0x18003cf3e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003cf44  mov     r10, cs:WPP_GLOBAL_Control
0x18003cf4b  cmp     r10, r14
0x18003cf4e  jz      short loc_18003CF7B
0x18003cf50  test    edi, edi
0x18003cf52  js      short loc_18003CF5B
0x18003cf54  cmp     byte ptr [r10+19h], 6
0x18003cf59  jb      short loc_18003CF7B
0x18003cf5b  or      ecx, 0FFFFFFFFh; int
0x18003cf5e  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18003cf63  mov     edx, 18h
0x18003cf68  mov     dword ptr [rsp+68h+var_48], edi
0x18003cf6c  mov     r9, rax
0x18003cf6f  mov     r8, r15
0x18003cf72  mov     rcx, [r10+10h]
0x18003cf76  call    WPP_SF_sd
0x18003cf7b  mov     eax, edi
0x18003cf7d  mov     rsi, [rsp+68h+arg_0]
0x18003cf82  add     rsp, 40h
0x18003cf86  pop     r15
0x18003cf88  pop     r14
0x18003cf8a  pop     r13
0x18003cf8c  pop     r12
0x18003cf8e  pop     rdi
0x18003cf8f  retn
  ... truncated ...
```
