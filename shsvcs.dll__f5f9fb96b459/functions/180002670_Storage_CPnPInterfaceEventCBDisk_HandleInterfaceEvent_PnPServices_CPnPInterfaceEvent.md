# Storage::CPnPInterfaceEventCBDisk::HandleInterfaceEvent(PnPServices::CPnPInterfaceEvent *)

- ea: `0x180002670`
- end: `0x18000287e`
- name: `?HandleInterfaceEvent@CPnPInterfaceEventCBDisk@Storage@@UEAAJPEAVCPnPInterfaceEvent@PnPServices@@@Z`
- size: `526`
- prototype: `__int64 __fastcall(Storage::CPnPInterfaceEventCBDisk *__hidden this, struct PnPServices::CPnPInterfaceEvent *)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task`

## callees

- `0x180001480`
- `0x1800014f0`
- `0x180002670`
- `0x180003570`
- `0x180007b04`
- `0x180007b20`
- `0x1800140f0`
- `0x180018f58`
- `0x18001b404`
- `0x180026604`
- `0x1800269d8`
- `0x180032c6a`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002730`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002730`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800027e2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800027e2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180002764`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180002764`

## pseudocode

```c
__int64 __fastcall Storage::CPnPInterfaceEventCBDisk::HandleInterfaceEvent(
        Storage::CPnPInterfaceEventCBDisk *this,
        struct PnPServices::CPnPInterfaceEvent *a2)
{
  int v3; // esi
  char *v4; // rax
  char *v5; // rbx
  const WCHAR *v6; // r15
  __int64 v7; // rcx
  CRefCounted *v8; // r13
  __int64 ValidHead; // rbp
  CRefCounted *v10; // r12
  CRefCounted *v11; // r14
  __int64 v12; // rdi
  int v13; // ebx
  CRefCounted *v14; // rbx
  __int64 v15; // rcx
  CRefCounted *v17; // [rsp+68h] [rbp+10h] BYREF
  __int64 v18; // [rsp+70h] [rbp+18h] BYREF

  if ( *((_DWORD *)a2 + 4) == 0x8000 )
  {
    v14 = Storage::g_pnelDisk;
    v18 = 0;
    CCritSectWithResource<CNamedElemList<PnPServices::CHandleNotif>>::Enter(*((_QWORD *)Storage::g_pnelDisk + 3));
    v3 = CNamedElemList<Storage::CDisk>::_Add<int,unsigned short const *>(v14, (char *)a2 + 20, &v18);
    CCritSectWithResource<CDummyResource>::Leave(*((_QWORD *)v14 + 3));
    if ( v3 >= 0 )
    {
      v17 = 0;
      if ( (int)Storage::_CreateVolumeOrDiskEventHelper<Storage::CDiskEvent>(
                  (unsigned __int16 *)a2 + 10,
                  &Storage::GUID_IO_DISK_ARRIVAL,
                  (__int64 *)&v17) >= 0 )
      {
        Storage::_BroadcastToVolumeCallbacksHelper<Storage::IDiskEventCB,Storage::CDiskEvent>(v15, v17);
        CRefCounted::Release(v17);
      }
      CRefCounted::Release((CRefCounted *)(v18 + 16));
    }
  }
  else if ( *((_DWORD *)a2 + 4) == 32772 )
  {
    v4 = (char *)operator new(0x228u);
    v5 = v4;
    if ( v4 )
    {
      memset_0(v4 + 12, 0, 0x21Cu);
      *((_DWORD *)v5 + 2) = 1;
      v6 = (const WCHAR *)((char *)a2 + 20);
      *(_QWORD *)v5 = &PnPServices::CPnPInterfaceEvent::`vftable';
      if ( (int)StringCchCopyW((unsigned __int16 *)v5 + 8, 0x104u, (unsigned __int16 *)a2 + 10) >= 0 )
      {
        *(GUID *)(v5 + 536) = Storage::GUID_IO_DISK_REMOVAL;
        Storage::_BroadcastToVolumeCallbacksHelper<Storage::IDiskEventCB,Storage::CDiskEvent>(v7, v5);
      }
      CRefCounted::Release((CRefCounted *)v5);
    }
    else
    {
      v6 = (const WCHAR *)((char *)a2 + 20);
    }
    v8 = Storage::g_pnelDisk;
    EnterCriticalSection((LPCRITICAL_SECTION)((*((_QWORD *)Storage::g_pnelDisk + 3) + 8LL)
                                            & -(__int64)(*((_QWORD *)Storage::g_pnelDisk + 3) != 0)));
    ValidHead = CNamedElemList<PnPServices::CInterfaceNotif>::_GetValidHead((__int64)v8);
    v10 = (CRefCounted *)ValidHead;
    v11 = 0;
    while ( ValidHead )
    {
      if ( v11 )
        goto LABEL_18;
      _InterlockedAdd((volatile signed __int32 *)(*(_QWORD *)(ValidHead + 16) + 24LL), 1u);
      v12 = *(_QWORD *)(ValidHead + 16);
      v13 = lstrcmpiW(v6, *(LPCWSTR *)(v12 + 8));
      CRefCounted::Release((CRefCounted *)(v12 + 16));
      if ( v13 )
      {
        ValidHead = CElemSlot<Storage::CDisk>::GetNextValid(ValidHead);
      }
      else
      {
        _InterlockedAdd((volatile signed __int32 *)(ValidHead + 8), 1u);
        v11 = (CRefCounted *)ValidHead;
      }
      CRefCounted::Release(v10);
      v10 = (CRefCounted *)ValidHead;
    }
    if ( !v11 )
    {
      v3 = -2147467259;
      goto LABEL_19;
    }
LABEL_18:
    CRefCounted::Release((CRefCounted *)(*((_QWORD *)v11 + 2) + 16LL));
    *((_QWORD *)v11 + 2) = 0;
    v3 = 0;
    CRefCounted::Release(v11);
    CRefCounted::Release(v11);
    --*((_DWORD *)v8 + 8);
LABEL_19:
    LeaveCriticalSection((LPCRITICAL_SECTION)((*((_QWORD *)v8 + 3) + 8LL) & -(__int64)(*((_QWORD *)v8 + 3) != 0)));
  }
  else
  {
    return 1;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180002670  mov     [rsp+arg_0], rbx
0x180002675  push    rbp
0x180002676  push    rsi
0x180002677  push    rdi
0x180002678  push    r12
0x18000267a  push    r13
0x18000267c  push    r14
0x18000267e  push    r15
0x180002680  sub     rsp, 20h
0x180002684  mov     ecx, [rdx+10h]
0x180002687  mov     rdi, rdx
0x18000268a  sub     ecx, 8000h
0x180002690  jz      loc_1800027EA
0x180002696  cmp     ecx, 4
0x180002699  jz      short loc_1800026A5
0x18000269b  mov     esi, 1
0x1800026a0  jmp     loc_180002867
0x1800026a5  mov     ecx, 228h; Size
0x1800026aa  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800026af  mov     rbx, rax
0x1800026b2  mov     esi, 1
0x1800026b7  test    rax, rax
0x1800026ba  jz      short loc_180002714
0x1800026bc  lea     rcx, [rax+0Ch]; void *
0x1800026c0  xor     edx, edx; Val
0x1800026c2  mov     r8d, 21Ch; Size
0x1800026c8  call    memset_0
0x1800026cd  lea     rax, ??_7CPnPInterfaceEvent@PnPServices@@6B@; const PnPServices::CPnPInterfaceEvent::`vftable'
0x1800026d4  mov     [rbx+8], esi
0x1800026d7  lea     r15, [rdi+14h]
0x1800026db  mov     [rbx], rax
0x1800026de  mov     r8, r15; unsigned __int16 *
0x1800026e1  lea     rcx, [rbx+10h]; unsigned __int16 *
0x1800026e5  mov     edx, 104h; unsigned __int64
0x1800026ea  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800026ef  test    eax, eax
0x1800026f1  js      short loc_18000270A
0x1800026f3  movups  xmm0, xmmword ptr cs:?GUID_IO_DISK_REMOVAL@Storage@@3U_GUID@@B.Data1; _GUID const Storage::GUID_IO_DISK_REMOVAL ...
0x1800026fa  mov     rdx, rbx
0x1800026fd  movdqu  xmmword ptr [rbx+218h], xmm0
0x180002705  call    ??$_BroadcastToVolumeCallbacksHelper@VIDiskEventCB@Storage@@VCDiskEvent@2@@Storage@@YAJPEAV?$CGrowableArray@VIDiskEventCB@Storage@@VCCritSect@@@@PEAVCDiskEvent@0@@Z; Storage::_BroadcastToVolumeCallbacksHelper<Storage::IDiskEventCB,Storage::CDiskEvent>(CGrowableArray<Storage::IDiskEventCB,CCritSect> *,Storage::CDiskEvent *)
0x18000270a  mov     rcx, rbx; this
0x18000270d  call    ?Release@CRefCounted@@QEBAKXZ; CRefCounted::Release(void)
0x180002712  jmp     short loc_180002718
0x180002714  lea     r15, [rdi+14h]
0x180002718  mov     r13, cs:?g_pnelDisk@Storage@@3PEAV?$CNamedElemList@VCDisk@Storage@@@@EA; CNamedElemList<Storage::CDisk> * Storage::g_pnelDisk
0x18000271f  mov     rax, [r13+18h]
0x180002723  lea     rdx, [rax+8]
0x180002727  neg     rax
0x18000272a  sbb     rcx, rcx
0x18000272d  and     rcx, rdx; lpCriticalSection
0x180002730  call    cs:__imp_EnterCriticalSection
0x180002736  mov     rcx, r13
0x180002739  call    ?_GetValidHead@?$CNamedElemList@VCInterfaceNotif@PnPServices@@@@AEBAPEAV?$CElemSlot@VCInterfaceNotif@PnPServices@@@@XZ; CNamedElemList<PnPServices::CInterfaceNotif>::_GetValidHead(void)
0x18000273e  mov     rbp, rax
0x180002741  mov     r12, rax
0x180002744  xor     r14d, r14d
0x180002747  test    rbp, rbp
0x18000274a  jz      short loc_18000279A
0x18000274c  test    r14, r14
0x18000274f  jnz     short loc_1800027A6
0x180002751  mov     rax, [rbp+10h]
0x180002755  lock add [rax+18h], esi
0x180002759  mov     rdi, [rbp+10h]
0x18000275d  mov     rcx, r15; lpString1
0x180002760  mov     rdx, [rdi+8]; lpString2
0x180002764  call    cs:__imp_lstrcmpiW
0x18000276a  lea     rcx, [rdi+10h]; this
0x18000276e  mov     ebx, eax
0x180002770  call    ?Release@CRefCounted@@QEBAKXZ; CRefCounted::Release(void)
0x180002775  test    ebx, ebx
0x180002777  jnz     short loc_180002782
0x180002779  lock add [rbp+8], esi
0x18000277d  mov     r14, rbp
0x180002780  jmp     short loc_18000278D
0x180002782  mov     rcx, rbp
0x180002785  call    ?GetNextValid@?$CElemSlot@VCDisk@Storage@@@@QEBAPEAV1@XZ; CElemSlot<Storage::CDisk>::GetNextValid(void)
0x18000278a  mov     rbp, rax
0x18000278d  mov     rcx, r12; this
0x180002790  call    ?Release@CRefCounted@@QEBAKXZ; CRefCounted::Release(void)
0x180002795  mov     r12, rbp
0x180002798  jmp     short loc_180002747
0x18000279a  test    r14, r14
0x18000279d  jnz     short loc_1800027A6
0x18000279f  mov     esi, 80004005h
0x1800027a4  jmp     short loc_1800027D1
0x1800027a6  mov     rcx, [r14+10h]
0x1800027aa  add     rcx, 10h; this
0x1800027ae  call    ?Release@CRefCounted@@QEBAKXZ; CRefCounted::Release(void)
0x1800027b3  mov     rcx, r14; this
0x1800027b6  mov     qword ptr [r14+10h], 0
0x1800027be  xor     esi, esi
0x1800027c0  call    ?Release@CRefCounted@@QEBAKXZ; CRefCounted::Release(void)
0x1800027c5  mov     rcx, r14; this
0x1800027c8  call    ?Release@CRefCounted@@QEBAKXZ; CRefCounted::Release(void)
0x1800027cd  dec     dword ptr [r13+20h]
0x1800027d1  mov     rax, [r13+18h]
0x1800027d5  lea     rdx, [rax+8]
0x1800027d9  neg     rax
0x1800027dc  sbb     rcx, rcx
0x1800027df  and     rcx, rdx; lpCriticalSection
0x1800027e2  call    cs:__imp_LeaveCriticalSection
0x1800027e8  jmp     short loc_180002867
0x1800027ea  mov     rbx, cs:?g_pnelDisk@Storage@@3PEAV?$CNamedElemList@VCDisk@Storage@@@@EA; CNamedElemList<Storage::CDisk> * Storage::g_pnelDisk
0x1800027f1  mov     [rsp+58h+arg_10], 0
0x1800027fa  mov     rcx, [rbx+18h]
0x1800027fe  call    ?Enter@?$CCritSectWithResource@V?$CNamedElemList@VCHandleNotif@PnPServices@@@@@@QEAAXXZ; CCritSectWithResource<CNamedElemList<PnPServices::CHandleNotif>>::Enter(void)
0x180002803  lea     r8, [rsp+58h+arg_10]
0x180002808  mov     rcx, rbx
0x18000280b  lea     rdx, [rdi+14h]
0x18000280f  call    ??$_Add@HPEBG@?$CNamedElemList@VCDisk@Storage@@@@AEAAJQEBGPEAPEAVCDisk@Storage@@H@Z; CNamedElemList<Storage::CDisk>::_Add<int,ushort const *>(ushort const * const,Storage::CDisk * *,int)
0x180002814  mov     rcx, [rbx+18h]
0x180002818  mov     esi, eax
0x18000281a  call    ?Leave@?$CCritSectWithResource@VCDummyResource@@@@QEAAXXZ; CCritSectWithResource<CDummyResource>::Leave(void)
0x18000281f  test    esi, esi
0x180002821  js      short loc_180002867
0x180002823  lea     r8, [rsp+58h+arg_8]
0x180002828  mov     [rsp+58h+arg_8], 0
0x180002831  lea     rdx, ?GUID_IO_DISK_ARRIVAL@Storage@@3U_GUID@@B; _GUID const Storage::GUID_IO_DISK_ARRIVAL
0x180002838  lea     rcx, [rdi+14h]; unsigned __int16 *
0x18000283c  call    ??$_CreateVolumeOrDiskEventHelper@VCDiskEvent@Storage@@@Storage@@YAJPEBGPEBU_GUID@@PEAPEAVCDiskEvent@0@@Z; Storage::_CreateVolumeOrDiskEventHelper<Storage::CDiskEvent>(ushort const *,_GUID const *,Storage::CDiskEvent * *)
0x180002841  test    eax, eax
0x180002843  js      short loc_180002859
0x180002845  mov     rdx, [rsp+58h+arg_8]
0x18000284a  call    ??$_BroadcastToVolumeCallbacksHelper@VIDiskEventCB@Storage@@VCDiskEvent@2@@Storage@@YAJPEAV?$CGrowableArray@VIDiskEventCB@Storage@@VCCritSect@@@@PEAVCDiskEvent@0@@Z; Storage::_BroadcastToVolumeCallbacksHelper<Storage::IDiskEventCB,Storage::CDiskEvent>(CGrowableArray<Storage::IDiskEventCB,CCritSect> *,Storage::CDiskEvent *)
0x18000284f  mov     rcx, [rsp+58h+arg_8]; this
0x180002854  call    ?Release@CRefCounted@@QEBAKXZ; CRefCounted::Release(void)
0x180002859  mov     rcx, [rsp+58h+arg_10]
0x18000285e  add     rcx, 10h; this
0x180002862  call    ?Release@CRefCounted@@QEBAKXZ; CRefCounted::Release(void)
0x180002867  mov     rbx, [rsp+58h+arg_0]
0x18000286c  mov     eax, esi
0x18000286e  add     rsp, 20h
0x180002872  pop     r15
0x180002874  pop     r14
0x180002876  pop     r13
0x180002878  pop     r12
0x18000287a  pop     rdi
0x18000287b  pop     rsi
0x18000287c  pop     rbp
0x18000287d  retn
```
