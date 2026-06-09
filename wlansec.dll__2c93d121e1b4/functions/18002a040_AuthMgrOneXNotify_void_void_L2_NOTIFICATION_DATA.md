# AuthMgrOneXNotify(void *,void *,_L2_NOTIFICATION_DATA *)

- ea: `0x18002a040`
- end: `0x18002a37e`
- name: `?AuthMgrOneXNotify@@YAKPEAX0PEAU_L2_NOTIFICATION_DATA@@@Z`
- size: `830`
- prototype: `unsigned int __fastcall(void *, void *, struct _L2_NOTIFICATION_DATA *)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation`

## callees

- `0x18000892c`
- `0x180008998`
- `0x18000b348`
- `0x180013600`
- `0x180013bc0`
- `0x1800169c0`
- `0x180026afc`
- `0x180028eb4`
- `0x18002a040`
- `0x18002a638`
- `0x18002b170`
- `0x18002bb08`
- `0x18006b170`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x18002a230`
- `MobileNetworking!ReleaseWriteLock` at `0x18002a26d`
- `MobileNetworking!ReleaseWriteLock` at `0x18002a230`
- `MobileNetworking!ReleaseWriteLock` at `0x18002a26d`
- `MobileNetworking!AcquireWriteLock` at `0x18002a16a`
- `MobileNetworking!AcquireWriteLock` at `0x18002a16a`

## pseudocode

```c
__int64 __fastcall AuthMgrOneXNotify(void *a1, void *a2, struct _L2_NOTIFICATION_DATA *a3)
{
  unsigned int v6; // eax
  unsigned int v7; // ebx
  PVOID *v8; // rcx
  struct MSMSEC_PORT_CONTEXT *v9; // rsi
  GUID *v10; // r14
  bool v11; // zf
  void *v12; // r13
  __int64 v13; // r10
  enum _ONEX_AUTH_RESTART_REASON *pData; // rax
  enum _ONEX_AUTH_RESTART_REASON v15; // ebx
  void *v16; // rdi
  unsigned int (*v17)(void *, void *, struct _L2_NOTIFICATION_DATA *); // rbx
  unsigned int v18; // ecx
  unsigned int v19; // eax
  unsigned __int8 *v21; // [rsp+28h] [rbp-41h]
  _EAP_METHOD_TYPE v22; // [rsp+50h] [rbp-19h] BYREF
  __int128 v23; // [rsp+60h] [rbp-9h] BYREF
  __int64 v24; // [rsp+70h] [rbp+7h]
  struct MSMSEC_PORT_CONTEXT *v25; // [rsp+E8h] [rbp+7Fh] BYREF

  *(_QWORD *)&v22.eapType.type = 0;
  v25 = 0;
  v23 = 0;
  v24 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 69, WPP_20060763357235bdafa6f501eee46e60_Traceguids);
  v6 = PreCallbackActions(a1, a2, (struct MSMSEC_INTF_CONTEXT **)&v22, &v25, (struct _AUTHMGR_LOCK_STATE *)&v23);
  v7 = v6;
  if ( !v6 )
  {
    v9 = v25;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        71,
        WPP_20060763357235bdafa6f501eee46e60_Traceguids,
        *((unsigned int *)v25 + 78));
    v10 = *(GUID **)&v22.eapType.type;
    TraceAdapterId(*(_DWORD *)(*(_QWORD *)&v22.eapType.type + 2496LL), ">>> Locking >>>");
    AcquireWriteLock(v10, &v10[157], "AuthMgrOneXNotify", 754);
    SecMgrCorrelateToSession(*(void **)v10[164].Data4);
    v11 = a3->NotificationCode == 2;
    v12 = *(void **)v10[164].Data4;
    a3->InterfaceGuid = v10[2];
    v13 = *((_QWORD *)v9 + 3);
    v22 = *(_EAP_METHOD_TYPE *)(*(unsigned int *)(*(_QWORD *)(*(_QWORD *)(v13 + 2784) + 48LL) + 64LL)
                              + *(_QWORD *)(*(_QWORD *)(v13 + 2784) + 48LL)
                              + 4LL);
    if ( v11 )
    {
      pData = (enum _ONEX_AUTH_RESTART_REASON *)a3->pData;
      v15 = *pData;
      MSMSecLogOneXRestart(
        (unsigned __int16 *)(v13 + 48),
        (struct _GUID *)(v13 + 32),
        (unsigned __int8 (*)[6])((char *)v9 + 296),
        (struct _DOT11_SSID *)(v13 + 2728),
        *(enum _DOT11_BSS_TYPE *)(v13 + 2764),
        (unsigned __int8 (*)[6])v21,
        &v22,
        *pData,
        v12);
      if ( (unsigned int)(v15 - 4) <= 1 )
        PmkCacheFlush(
          (struct MSMSEC_PMKCACHE_CONTEXT *)(*((_QWORD *)v9 + 3) + 3000LL),
          *((struct MSMSEC_INTF_CONTEXT **)v9 + 3));
    }
    TraceAdapterId(v10[156].Data1, "<<< Unlocking <<<");
    ReleaseWriteLock(v10, &v10[157], "AuthMgrOneXNotify", 789);
    v16 = (void *)*((_QWORD *)v9 + 4);
    v17 = (unsigned int (*)(void *, void *, struct _L2_NOTIFICATION_DATA *))*((_QWORD *)v9 + 13);
    TracePortId(*((_DWORD *)v9 + 78), "<<< Unlocking <<<");
    ReleaseWriteLock(v9, (char *)v9 + 320, "AuthMgrOneXNotify", 796);
    v18 = *((_DWORD *)v9 + 78);
    *((_QWORD *)&v23 + 1) = 0;
    TracePortId(v18, "<<< Derefing <<<");
    SecMgrDerefPortEx(v9, "AuthMgrOneXNotify", 800);
    TraceAdapterId(v10[156].Data1, "<<< Derefing <<<");
    SecMgrDerefAdapterEx((struct MSMSEC_INTF_CONTEXT *)v10, "AuthMgrOneXNotify", 804);
    DWORD1(v23) = 0;
    v19 = MSMSendNotification(v16, v12, a3, v17);
    v7 = v19;
    if ( v19 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 72, WPP_20060763357235bdafa6f501eee46e60_Traceguids, v19);
    PostCallbackActions(a1, (struct MSMSEC_INTF_CONTEXT *)v10, v9, (struct _AUTHMGR_LOCK_STATE *)&v23);
    goto LABEL_19;
  }
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v7;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 70, WPP_20060763357235bdafa6f501eee46e60_Traceguids, v6);
LABEL_19:
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v8 != &WPP_GLOBAL_Control && (*((_DWORD *)v8 + 17) & 0x100) != 0 )
    WPP_SF_d(v8[7], 73, WPP_20060763357235bdafa6f501eee46e60_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x18002a040  push    rbp
0x18002a042  push    rbx
0x18002a043  push    rsi
0x18002a044  push    rdi
0x18002a045  push    r12
0x18002a047  push    r13
0x18002a049  push    r14
0x18002a04b  push    r15
0x18002a04d  lea     rbp, [rsp-1Fh]
0x18002a052  sub     rsp, 88h
0x18002a059  xorps   xmm0, xmm0
0x18002a05c  mov     qword ptr [rbp+57h+var_70.eapType.type], 0
0x18002a064  xor     eax, eax
0x18002a066  mov     [rbp+57h+arg_18], 0
0x18002a06e  movups  [rbp+57h+var_60], xmm0
0x18002a072  mov     [rbp+57h+var_50], rax
0x18002a076  mov     r15, r8
0x18002a079  mov     rbx, rdx
0x18002a07c  mov     r12, rcx
0x18002a07f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a086  lea     rdi, WPP_GLOBAL_Control
0x18002a08d  cmp     rcx, rdi
0x18002a090  jz      short loc_18002A0AE
0x18002a092  test    dword ptr [rcx+44h], 100h
0x18002a099  jz      short loc_18002A0AE
0x18002a09b  mov     rcx, [rcx+38h]
0x18002a09f  lea     edx, [rax+45h]
0x18002a0a2  lea     r8, WPP_20060763357235bdafa6f501eee46e60_Traceguids
0x18002a0a9  call    WPP_SF_
0x18002a0ae  lea     rax, [rbp+57h+var_60]
0x18002a0b2  mov     rdx, rbx; void *
0x18002a0b5  lea     r9, [rbp+57h+arg_18]; struct MSMSEC_PORT_CONTEXT **
0x18002a0b9  mov     qword ptr [rsp+0C0h+var_A0], rax; struct _AUTHMGR_LOCK_STATE *
0x18002a0be  lea     r8, [rbp+57h+var_70]; struct MSMSEC_INTF_CONTEXT **
0x18002a0c2  mov     rcx, r12; void *
0x18002a0c5  call    ?PreCallbackActions@@YAKPEAX0PEAPEAUMSMSEC_INTF_CONTEXT@@PEAPEAUMSMSEC_PORT_CONTEXT@@PEAU_AUTHMGR_LOCK_STATE@@@Z; PreCallbackActions(void *,void *,MSMSEC_INTF_CONTEXT * *,MSMSEC_PORT_CONTEXT * *,_AUTHMGR_LOCK_STATE *)
0x18002a0ca  mov     ebx, eax
0x18002a0cc  test    eax, eax
0x18002a0ce  jz      short loc_18002A107
0x18002a0d0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a0d7  cmp     rcx, rdi
0x18002a0da  jz      loc_18002A367
0x18002a0e0  test    byte ptr [rcx+44h], 1
0x18002a0e4  jz      loc_18002A341
0x18002a0ea  mov     rcx, [rcx+38h]
0x18002a0ee  lea     r8, WPP_20060763357235bdafa6f501eee46e60_Traceguids
0x18002a0f5  mov     edx, 46h ; 'F'
0x18002a0fa  mov     r9d, eax
0x18002a0fd  call    WPP_SF_d
0x18002a102  jmp     loc_18002A33A
0x18002a107  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a10e  mov     rsi, [rbp+57h+arg_18]
0x18002a112  cmp     rcx, rdi
0x18002a115  jz      short loc_18002A139
0x18002a117  test    byte ptr [rcx+44h], 20h
0x18002a11b  jz      short loc_18002A139
0x18002a11d  mov     r9d, [rsi+138h]
0x18002a124  lea     r8, WPP_20060763357235bdafa6f501eee46e60_Traceguids
0x18002a12b  mov     rcx, [rcx+38h]
0x18002a12f  mov     edx, 47h ; 'G'
0x18002a134  call    WPP_SF_d
0x18002a139  mov     r14, qword ptr [rbp+57h+var_70.eapType.type]
0x18002a13d  lea     rdx, aLocking; ">>> Locking >>>"
0x18002a144  mov     ecx, [r14+9C0h]; unsigned int
0x18002a14b  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x18002a150  lea     rdi, [r14+9D0h]
0x18002a157  mov     r9d, 2F2h
0x18002a15d  mov     rdx, rdi
0x18002a160  lea     r8, aAuthmgronexnot; "AuthMgrOneXNotify"
0x18002a167  mov     rcx, r14
0x18002a16a  call    cs:__imp_AcquireWriteLock
0x18002a171  nop     dword ptr [rax+rax+00h]
0x18002a176  mov     rcx, [r14+0A48h]; void *
0x18002a17d  call    ?SecMgrCorrelateToSession@@YAXPEAX@Z; SecMgrCorrelateToSession(void *)
0x18002a182  cmp     dword ptr [r15+4], 2
0x18002a187  movups  xmm0, xmmword ptr [r14+20h]
0x18002a18c  mov     r13, [r14+0A48h]
0x18002a193  movdqu  xmmword ptr [r15+8], xmm0
0x18002a199  mov     r10, [rsi+18h]
0x18002a19d  mov     rax, [r10+0AE0h]
0x18002a1a4  mov     rcx, [rax+30h]
0x18002a1a8  mov     eax, [rcx+40h]
0x18002a1ab  movups  xmm0, xmmword ptr [rax+rcx+4]
0x18002a1b0  movdqu  xmmword ptr [rbp+57h+var_70.eapType.type], xmm0
0x18002a1b5  jnz     short loc_18002A20A
0x18002a1b7  mov     rax, [r15+20h]
0x18002a1bb  lea     r9, [r10+0AA8h]; struct _DOT11_SSID *
0x18002a1c2  mov     [rsp+0C0h+var_80], r13; void *
0x18002a1c7  lea     r8, [rsi+128h]; unsigned __int8 (*)[6]
0x18002a1ce  lea     rdx, [r10+20h]; struct _GUID *
0x18002a1d2  lea     rcx, [r10+30h]; unsigned __int16 *
0x18002a1d6  mov     ebx, [rax]
0x18002a1d8  lea     rax, [rbp+57h+var_70]
0x18002a1dc  mov     [rsp+0C0h+var_88], ebx; enum _ONEX_AUTH_RESTART_REASON
0x18002a1e0  mov     [rsp+0C0h+var_90], rax; struct _EAP_METHOD_TYPE *
0x18002a1e5  mov     eax, [r9+24h]
0x18002a1e9  mov     [rsp+0C0h+var_A0], eax; enum _DOT11_BSS_TYPE
0x18002a1ed  call    ?MSMSecLogOneXRestart@@YAKPEAGPEAU_GUID@@PEAY05EPEAU_DOT11_SSID@@W4_DOT11_BSS_TYPE@@2PEAU_EAP_METHOD_TYPE@@W4_ONEX_AUTH_RESTART_REASON@@PEAX@Z; MSMSecLogOneXRestart(ushort *,_GUID *,uchar (*)[6],_DOT11_SSID *,_DOT11_BSS_TYPE,uchar (*)[6],_EAP_METHOD_TYPE *,_ONEX_AUTH_RESTART_REASON,void *)
0x18002a1f2  lea     eax, [rbx-4]
0x18002a1f5  cmp     eax, 1
0x18002a1f8  ja      short loc_18002A20A
0x18002a1fa  mov     rdx, [rsi+18h]; struct MSMSEC_INTF_CONTEXT *
0x18002a1fe  lea     rcx, [rdx+0BB8h]; struct MSMSEC_PMKCACHE_CONTEXT *
0x18002a205  call    ?PmkCacheFlush@@YAXPEAUMSMSEC_PMKCACHE_CONTEXT@@PEAUMSMSEC_INTF_CONTEXT@@@Z; PmkCacheFlush(MSMSEC_PMKCACHE_CONTEXT *,MSMSEC_INTF_CONTEXT *)
0x18002a20a  mov     ecx, [r14+9C0h]; unsigned int
0x18002a211  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x18002a218  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x18002a21d  mov     r9d, 315h
0x18002a223  lea     r8, aAuthmgronexnot; "AuthMgrOneXNotify"
0x18002a22a  mov     rdx, rdi
0x18002a22d  mov     rcx, r14
0x18002a230  call    cs:__imp_ReleaseWriteLock
0x18002a237  nop     dword ptr [rax+rax+00h]
0x18002a23c  mov     ecx, [rsi+138h]; unsigned int
0x18002a242  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x18002a249  mov     rdi, [rsi+20h]
0x18002a24d  mov     rbx, [rsi+68h]
0x18002a251  call    ?TracePortId@@YAXKPEBD@Z; TracePortId(ulong,char const *)
0x18002a256  lea     rdx, [rsi+140h]
0x18002a25d  mov     r9d, 31Ch
0x18002a263  lea     r8, aAuthmgronexnot; "AuthMgrOneXNotify"
0x18002a26a  mov     rcx, rsi
0x18002a26d  call    cs:__imp_ReleaseWriteLock
0x18002a274  nop     dword ptr [rax+rax+00h]
0x18002a279  mov     ecx, [rsi+138h]; unsigned int
0x18002a27f  lea     rdx, aDerefing; "<<< Derefing <<<"
0x18002a286  mov     qword ptr [rbp+57h+var_60+8], 0
0x18002a28e  call    ?TracePortId@@YAXKPEBD@Z; TracePortId(ulong,char const *)
0x18002a293  mov     r8d, 320h; int
0x18002a299  lea     rdx, aAuthmgronexnot; "AuthMgrOneXNotify"
0x18002a2a0  mov     rcx, rsi; struct MSMSEC_PORT_CONTEXT *
0x18002a2a3  call    ?SecMgrDerefPortEx@@YAXPEAUMSMSEC_PORT_CONTEXT@@PEBDH@Z; SecMgrDerefPortEx(MSMSEC_PORT_CONTEXT *,char const *,int)
0x18002a2a8  mov     ecx, [r14+9C0h]; unsigned int
0x18002a2af  lea     rdx, aDerefing; "<<< Derefing <<<"
0x18002a2b6  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x18002a2bb  mov     r8d, 324h; int
0x18002a2c1  lea     rdx, aAuthmgronexnot; "AuthMgrOneXNotify"
0x18002a2c8  mov     rcx, r14; struct MSMSEC_INTF_CONTEXT *
0x18002a2cb  call    ?SecMgrDerefAdapterEx@@YAXPEAUMSMSEC_INTF_CONTEXT@@PEBDH@Z; SecMgrDerefAdapterEx(MSMSEC_INTF_CONTEXT *,char const *,int)
0x18002a2d0  mov     r9, rbx; unsigned int (*)(void *, void *, struct _L2_NOTIFICATION_DATA *)
0x18002a2d3  mov     dword ptr [rbp+57h+var_60+4], 0
0x18002a2da  mov     r8, r15; struct _L2_NOTIFICATION_DATA *
0x18002a2dd  mov     rdx, r13; void *
0x18002a2e0  mov     rcx, rdi; void *
0x18002a2e3  call    ?MSMSendNotification@@YAKPEAX0PEAU_L2_NOTIFICATION_DATA@@P6AK001@Z@Z; MSMSendNotification(void *,void *,_L2_NOTIFICATION_DATA *,ulong (*)(void *,void *,_L2_NOTIFICATION_DATA *))
0x18002a2e8  mov     ebx, eax
0x18002a2ea  test    eax, eax
0x18002a2ec  jz      short loc_18002A321
0x18002a2ee  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a2f5  lea     rdi, WPP_GLOBAL_Control
0x18002a2fc  cmp     rcx, rdi
0x18002a2ff  jz      short loc_18002A328
0x18002a301  test    byte ptr [rcx+44h], 1
0x18002a305  jz      short loc_18002A328
0x18002a307  mov     rcx, [rcx+38h]
0x18002a30b  lea     r8, WPP_20060763357235bdafa6f501eee46e60_Traceguids
0x18002a312  mov     edx, 48h ; 'H'
0x18002a317  mov     r9d, eax
0x18002a31a  call    WPP_SF_d
0x18002a31f  jmp     short loc_18002A328
0x18002a321  lea     rdi, WPP_GLOBAL_Control
0x18002a328  lea     r9, [rbp+57h+var_60]; struct _AUTHMGR_LOCK_STATE *
0x18002a32c  mov     r8, rsi; struct MSMSEC_PORT_CONTEXT *
0x18002a32f  mov     rdx, r14; struct MSMSEC_INTF_CONTEXT *
0x18002a332  mov     rcx, r12; void *
0x18002a335  call    ?PostCallbackActions@@YAKPEAXPEAUMSMSEC_INTF_CONTEXT@@PEAUMSMSEC_PORT_CONTEXT@@PEAU_AUTHMGR_LOCK_STATE@@@Z; PostCallbackActions(void *,MSMSEC_INTF_CONTEXT *,MSMSEC_PORT_CONTEXT *,_AUTHMGR_LOCK_STATE *)
0x18002a33a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a341  cmp     rcx, rdi
0x18002a344  jz      short loc_18002A367
0x18002a346  test    dword ptr [rcx+44h], 100h
0x18002a34d  jz      short loc_18002A367
0x18002a34f  mov     rcx, [rcx+38h]
0x18002a353  lea     r8, WPP_20060763357235bdafa6f501eee46e60_Traceguids
0x18002a35a  mov     edx, 49h ; 'I'
0x18002a35f  mov     r9d, ebx
0x18002a362  call    WPP_SF_d
0x18002a367  mov     eax, ebx
0x18002a369  add     rsp, 88h
0x18002a370  pop     r15
0x18002a372  pop     r14
0x18002a374  pop     r13
0x18002a376  pop     r12
0x18002a378  pop     rdi
0x18002a379  pop     rsi
0x18002a37a  pop     rbx
0x18002a37b  pop     rbp
0x18002a37c  retn
```
