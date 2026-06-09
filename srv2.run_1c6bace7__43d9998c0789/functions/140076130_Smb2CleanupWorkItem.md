# Smb2CleanupWorkItem

- ea: `0x140076130`
- end: `0x1400766c6`
- name: `Smb2CleanupWorkItem`
- size: `1430`
- prototype: ``
- caller_count: `0`
- callee_count: `23`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140004dcc`
- `0x140005070`
- `0x14000bb80`
- `0x14000ca00`
- `0x14000e340`
- `0x140012790`
- `0x1400128b0`
- `0x140013810`
- `0x140013920`
- `0x140013990`
- `0x140018320`
- `0x1400240e4`
- `0x140025150`
- `0x140027390`
- `0x1400384d0`
- `0x140038980`
- `0x14006ead0`
- `0x140076130`
- `0x140077390`
- `0x140077900`
- `0x14007ca90`
- `0x1400803b4`
- `0x1400917ac`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14007639b`
- `ntoskrnl!ObfDereferenceObject` at `0x14007639b`
- `ntoskrnl!IofCallDriver` at `0x1400970b5`
- `ntoskrnl!IofCallDriver` at `0x1400970b5`
- `ntoskrnl!MmUnmapLockedPages` at `0x14007646f`
- `ntoskrnl!MmUnmapLockedPages` at `0x14007646f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007658a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140096e8f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400970da`
- `ntoskrnl!ExFreePoolWithTag` at `0x140097103`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009712c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140097155`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009717e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400971ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007658a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140096e8f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400970da`
- `ntoskrnl!ExFreePoolWithTag` at `0x140097103`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009712c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140097155`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009717e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400971ae`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x1400765e9`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x1400765e9`
- `ntoskrnl!IoCleanupIrp` at `0x140096e67`
- `ntoskrnl!IoCleanupIrp` at `0x140096e67`
- `ntoskrnl!CcMdlWriteAbort` at `0x140096f5e`
- `ntoskrnl!CcMdlWriteAbort` at `0x140096f5e`
- `srvnet!SrvNetFreeBuffer` at `0x14007665e`
- `srvnet!SrvNetFreeBuffer` at `0x140096df6`
- `srvnet!SrvNetFreeBuffer` at `0x14007665e`
- `srvnet!SrvNetFreeBuffer` at `0x140096df6`
- `srvnet!SrvNetIsRdmaConnection` at `0x140076289`
- `srvnet!SrvNetIsRdmaConnection` at `0x140076289`
- `srvnet!SmbCryptoHashDestroy` at `0x140076611`
- `srvnet!SmbCryptoHashDestroy` at `0x140076639`
- `srvnet!SmbCryptoHashDestroy` at `0x140076611`
- `srvnet!SmbCryptoHashDestroy` at `0x140076639`
- `srvnet!SrvLibFreePipeEa` at `0x1400765a9`
- `srvnet!SrvLibFreePipeEa` at `0x1400765a9`
- `ksecdd!FreeContextBuffer` at `0x14009754d`
- `ksecdd!FreeContextBuffer` at `0x14009754d`

## string_xrefs

- `0x140096ef4`: `Smb2CleanupWrite`
- `0x140096f92`: `Smb2CleanupWrite`

## pseudocode

```c
__int64 __fastcall Smb2CleanupWorkItem(_QWORD *a1, __int64 a2)
{
  __int64 v2; // r8
  __int64 v3; // r13
  _QWORD *v4; // rdi
  __int64 v5; // rbx
  __int64 v6; // rbx
  __int64 v7; // rdx
  unsigned __int64 v8; // rsi
  void *v9; // rcx
  struct _ECP_LIST *v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rdx
  void *v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rax
  void *v16; // rcx
  void *v17; // rcx
  void *v18; // rcx
  void *v19; // rcx
  unsigned int i; // esi
  int v22; // eax
  __int64 v23; // rcx
  __int64 v24; // rdx
  void *v25; // rcx
  void *v26; // rcx
  void *v27; // rcx
  __int64 v28; // r15
  __int64 v29; // r14
  __int64 v30; // rcx
  __int64 v31; // rax
  __int64 v32; // rcx
  __int64 v33; // r14
  char v34; // al
  _QWORD *v35; // rcx
  __int64 v36; // rdx
  void *v37; // rcx
  void *v38; // rcx
  void *v39; // rcx
  void *v40; // rcx
  void *v41; // rcx
  void *v42; // rcx
  __int64 v43; // rcx
  __int64 v44; // rbx
  __int16 v45; // ax
  __int64 v46; // rax
  __int64 v47; // rax
  __int64 v48; // rax
  __int64 v49; // rdx
  _QWORD *v50; // r12
  __int64 v51; // r15
  unsigned int v52; // edx
  unsigned int v53; // esi
  __int64 v54; // rbx
  UCHAR v55; // al
  int v56; // ecx
  _QWORD *v57; // r12
  __int64 v58; // r15
  unsigned int v59; // edx
  unsigned int v60; // esi
  __int64 v61; // rbx
  UCHAR v62; // al
  int v63; // ecx
  int v64; // [rsp+20h] [rbp-A9h]
  int v65; // [rsp+20h] [rbp-A9h]
  int v66; // [rsp+20h] [rbp-A9h]
  int v67; // [rsp+20h] [rbp-A9h]
  int v68; // [rsp+28h] [rbp-A1h]
  __int64 v69; // [rsp+B0h] [rbp-19h]
  __int64 v70; // [rsp+B8h] [rbp-11h]
  PVOID pvContextBuffer; // [rsp+C0h] [rbp-9h] BYREF
  __int64 v72; // [rsp+C8h] [rbp-1h] BYREF
  __int64 v73; // [rsp+D0h] [rbp+7h]
  __int16 v75; // [rsp+138h] [rbp+6Fh]
  __int16 v76; // [rsp+140h] [rbp+77h]
  __int64 v77; // [rsp+148h] [rbp+7Fh]

  v2 = a1[12];
  v3 = a1[70];
  v4 = a1;
  v5 = *(_QWORD *)(v2 + 496);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qqqqqqd(
      WPP_GLOBAL_Control->AttachedDevice,
      *(_QWORD *)(a1[39] + 24LL),
      v2,
      a1,
      v2,
      *(_QWORD *)(v2 + 480),
      *(_QWORD *)(v3 + 32),
      *(_QWORD *)(v3 + 56),
      *(_QWORD *)(v3 + 72),
      *(unsigned __int16 *)(*(_QWORD *)(a1[39] + 24LL) + 12LL));
  }
  if ( *(_BYTE *)(v3 + 7) )
  {
    *(_BYTE *)(v3 + 7) = 0;
    _InterlockedDecrement((volatile signed __int32 *)(v5 + 196));
  }
  if ( *(_BYTE *)(v3 + 2) && !*(_BYTE *)(v3 + 3) )
  {
    *(_BYTE *)(v3 + 3) = 1;
    _InterlockedDecrement((volatile signed __int32 *)(v5 + 192));
  }
  if ( *(_QWORD *)(v3 + 152) )
  {
    Smb2DereferenceClient();
    *(_QWORD *)(v3 + 152) = 0;
  }
  if ( *(_WORD *)(v3 + 14) )
  {
    switch ( *(_WORD *)(v3 + 14) )
    {
      case 1:
        if ( *(_QWORD *)(v3 + 200) )
        {
          SmbCryptoHashDestroy();
          *(_QWORD *)(v3 + 200) = 0;
        }
        break;
      case 5:
        if ( *(_BYTE *)(v3 + 303) )
        {
          SrvLibFreePipeEa(*(_QWORD *)(v3 + 208));
          *(_QWORD *)(v3 + 208) = 0;
          *(_DWORD *)(v3 + 216) = 0;
          *(_BYTE *)(v3 + 303) = 0;
        }
        if ( *(_BYTE *)(v3 + 306) )
        {
          v23 = *(_QWORD *)(v3 + 104);
          if ( v23 )
            Smb2LeaseDecrementOpensInProgressAndCloseIfUnused(v23, a2, 0);
        }
        v10 = *(struct _ECP_LIST **)(v3 + 320);
        if ( v10 )
        {
          FsRtlFreeExtraCreateParameterList(v10);
          *(_QWORD *)(v3 + 320) = 0;
        }
        break;
      case 8:
        if ( *(_BYTE *)(v3 + 4) || (unsigned int)Smb2CompleteRead(v4) != 259 )
          break;
        return 259;
      case 9:
        if ( *(_BYTE *)(v3 + 4) )
          break;
        v6 = v4[70];
        v7 = *(unsigned int *)(v6 + 260);
        *(_BYTE *)(v6 + 4) = 1;
        if ( (_DWORD)v7 && byte_140058150 )
        {
          _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(*(_QWORD *)(v6 + 56) + 104LL) + 368LL));
          _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(v6 + 40) + 216LL));
          v8 = (unsigned int)v7;
          _InterlockedAdd64(
            (volatile signed __int64 *)(*(_QWORD *)(*(_QWORD *)(v6 + 56) + 104LL) + 384LL),
            (unsigned int)v7);
          _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)(v6 + 40) + 232LL), (unsigned int)v7);
          _InterlockedAdd64(
            (volatile signed __int64 *)(*(_QWORD *)(*(_QWORD *)(v6 + 56) + 104LL) + 576LL),
            (unsigned int)v7);
          _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)(v6 + 40) + 376LL), (unsigned int)v7);
          _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(*(_QWORD *)(v6 + 56) + 104LL) + 568LL));
          _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(v6 + 40) + 368LL));
          if ( (unsigned __int8)SrvNetIsRdmaConnection(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v6 + 24) + 96LL) + 480LL)) )
          {
            _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(*(_QWORD *)(v6 + 56) + 104LL) + 372LL));
            _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)(*(_QWORD *)(v6 + 56) + 104LL) + 392LL), v8);
          }
          if ( *(_BYTE *)(*(_QWORD *)(v6 + 72) + 245LL) )
          {
            _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(*(_QWORD *)(v6 + 56) + 104LL) + 536LL));
            _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)(*(_QWORD *)(v6 + 56) + 104LL) + 544LL), v8);
          }
          if ( *(_QWORD *)(v6 + 216) )
          {
            _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)(*(_QWORD *)(v6 + 56) + 104LL) + 312LL), v8);
            _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)(v6 + 40) + 160LL), v8);
            _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)(*(_QWORD *)(v6 + 56) + 104LL) + 328LL), v8);
            _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)(v6 + 40) + 176LL), v8);
          }
        }
        if ( *(_QWORD *)(v6 + 240) )
        {
          for ( i = 0; i < *(_DWORD *)(v6 + 272); ++i )
          {
            v28 = *(_QWORD *)(v6 + 240);
            v29 = 32LL * i;
            if ( *(_QWORD *)(v29 + v28) )
              IoCleanupIrp();
            v30 = *(_QWORD *)(v29 + v28 + 8);
            if ( v30 && (*(_BYTE *)(v30 + 10) & 0x20) != 0 )
              MmUnmapLockedPages(*(PVOID *)(v30 + 24), *(PMDL *)(v29 + v28 + 8));
          }
          ExFreePoolWithTag(*(PVOID *)(v6 + 240), 0);
          *(_QWORD *)(v6 + 240) = 0;
        }
        if ( !*(_QWORD *)(v6 + 216) )
        {
          v9 = *(void **)(v6 + 208);
          if ( v9 )
          {
            ExFreePoolWithTag(v9, 0);
            *(_QWORD *)(v6 + 208) = 0;
          }
          break;
        }
        if ( (*(_BYTE *)(v6 + 280) & 3) != 1 )
          break;
        if ( !*(_QWORD *)(v6 + 200) )
          break;
        v31 = *(_QWORD *)(v6 + 88);
        if ( !v31 )
          break;
        v32 = *(_QWORD *)(v31 + 40);
        if ( v32 && *(_QWORD *)(v32 + 8) )
        {
          LOBYTE(v64) = 1;
          LOBYTE(v7) = 2;
          SRV2_PERF_ENTER_EX(v4 + 73, v7, 347, "Smb2CleanupWrite", v64);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_qqq(
              WPP_GLOBAL_Control->AttachedDevice,
              10,
              WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids,
              v4,
              *(_QWORD *)(v6 + 72),
              *(_QWORD *)(v6 + 88));
          }
          CcMdlWriteAbort(*(PFILE_OBJECT *)(v6 + 88), *(PMDL *)(v6 + 200));
          LOBYTE(v65) = 1;
          SRV2_PERF_ENTER_EX(v4 + 73, 0, 353, "Smb2CleanupWrite", v65);
          *(_QWORD *)(v6 + 200) = 0;
          break;
        }
        v33 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v6 + 96) + 8LL) + 80LL);
        if ( v33 && *(_DWORD *)v33 > 0x98u && *(_QWORD *)(v33 + 152) )
        {
          LOBYTE(v64) = 1;
          LOBYTE(v7) = 2;
          SRV2_PERF_ENTER_EX(v4 + 73, v7, 391, "Smb2CleanupWrite", v64);
          v34 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(v33 + 152))(
                  *(_QWORD *)(v6 + 88),
                  v6 + 192,
                  *(_QWORD *)(v6 + 200),
                  *(_QWORD *)(v6 + 96));
          LOBYTE(v66) = 1;
          v35 = v4 + 73;
          if ( v34 )
          {
            SRV2_PERF_ENTER_EX(v35, 0, 397, "Smb2CleanupWrite", v66);
            break;
          }
          SRV2_PERF_ENTER_EX(v35, 0, 401, "Smb2CleanupWrite", v66);
        }
        LOBYTE(v68) = 6;
        LOBYTE(v64) = 4;
        Smb2BuildReadOrWriteRequest(
          v4,
          0,
          *(_QWORD *)(v6 + 88),
          *(_QWORD *)(v6 + 96),
          v64,
          v68,
          0,
          *(_DWORD *)(v6 + 248),
          *(_QWORD *)(v6 + 200),
          *(_QWORD *)(v6 + 192),
          *(_DWORD *)(v6 + 256),
          0,
          0,
          0);
        LOBYTE(v67) = 1;
        v4[6] = Smb2CleanupWriteCompleteMdlWriteIrpCompleted;
        LOBYTE(v36) = 3;
        SRV2_PERF_ENTER_EX(v4 + 73, v36, 429, "Smb2CleanupWrite", v67);
        IofCallDriver(*(PDEVICE_OBJECT *)(v6 + 96), (PIRP)v4[15]);
        return 259;
      case 0xB:
        v22 = *(_DWORD *)(v3 + 192);
        switch ( v22 )
        {
          case 623428:
            v27 = *(void **)(v3 + 336);
            if ( v27 )
            {
              Smb2DereferenceHandle(v27);
              *(_QWORD *)(v3 + 336) = 0;
            }
            break;
          case 623592:
            v26 = *(void **)(v3 + 344);
            if ( v26 )
            {
              Smb2DereferenceHandle(v26);
              *(_QWORD *)(v3 + 344) = 0;
            }
            break;
          case 1327346:
          case 1343730:
            v25 = *(void **)(v3 + 352);
            if ( v25 )
            {
              Smb2DereferenceHandle(v25);
              *(_QWORD *)(v3 + 352) = 0;
            }
            if ( *(_QWORD *)(v3 + 368) )
            {
              SrvNetFreeBuffer();
              *(_QWORD *)(v3 + 368) = 0;
            }
            break;
        }
        break;
    }
  }
  else
  {
    if ( *(_QWORD *)(v3 + 200) )
    {
      SmbCryptoHashDestroy();
      *(_QWORD *)(v3 + 200) = 0;
    }
    v37 = *(void **)(v3 + 208);
    if ( v37 )
    {
      ExFreePoolWithTag(v37, 0x7732534Cu);
      *(_QWORD *)(v3 + 208) = 0;
      *(_WORD *)(v3 + 252) = 0;
    }
    v38 = *(void **)(v3 + 216);
    if ( v38 )
    {
      ExFreePoolWithTag(v38, 0x7732534Cu);
      *(_QWORD *)(v3 + 216) = 0;
      *(_WORD *)(v3 + 254) = 0;
    }
    v39 = *(void **)(v3 + 224);
    if ( v39 )
    {
      ExFreePoolWithTag(v39, 0x7732534Cu);
      *(_QWORD *)(v3 + 224) = 0;
      *(_WORD *)(v3 + 258) = 0;
    }
    v40 = *(void **)(v3 + 240);
    if ( v40 )
    {
      ExFreePoolWithTag(v40, 0x7732534Cu);
      *(_QWORD *)(v3 + 240) = 0;
      *(_WORD *)(v3 + 260) = 0;
    }
    v41 = *(void **)(v3 + 232);
    if ( v41 )
    {
      ExFreePoolWithTag(v41, 0x7732534Cu);
      *(_QWORD *)(v3 + 232) = 0;
      *(_WORD *)(v3 + 256) = 0;
    }
    v42 = *(void **)(v3 + 280);
    if ( v42 )
    {
      ExFreePoolWithTag(v42, 0x6E6E534Cu);
      *(_QWORD *)(v3 + 280) = 0;
    }
  }
  if ( (*(_BYTE *)(v3 + 16) & 4) != 0 )
    Smb2UpdatePerfCountersOnWorkItemCleanup(v3);
  v11 = v4[87];
  pvContextBuffer = 0;
  v72 = 0;
  v73 = 0;
  if ( !v11 )
    goto LABEL_35;
  v12 = v4[8];
  if ( v11 <= *(int *)(v12 + 184) )
    goto LABEL_35;
  v43 = v4[88];
  if ( !v43 )
    goto LABEL_35;
  if ( v43 <= *(int *)(v12 + 192) )
    goto LABEL_35;
  v44 = v4[70];
  v77 = v44;
  v45 = *(_WORD *)(v44 + 14);
  if ( v45 == 15 )
    goto LABEL_35;
  if ( v45 == 10 )
    goto LABEL_35;
  v46 = *(_QWORD *)(v44 + 56);
  if ( *(_DWORD *)(v46 + 76) == 1 )
    goto LABEL_35;
  v70 = 0;
  v76 = 0;
  v69 = 0;
  v75 = 0;
  if ( v46 )
  {
    v47 = *(_QWORD *)(v46 + 96);
    if ( v47 )
    {
      v76 = *(_WORD *)(v47 + 104) >> 1;
      v70 = *(_QWORD *)(v47 + 112);
    }
  }
  v48 = *(_QWORD *)(v44 + 72);
  if ( v48 )
  {
    v75 = *(_WORD *)(v48 + 208) >> 1;
    v69 = *(_QWORD *)(v48 + 216);
  }
  Smb2GetUserName(v44, &pvContextBuffer, &v72);
  v49 = v4[8];
  if ( v4[88] <= *(int *)(v49 + 192) )
  {
    if ( (byte_14004C339 & 0x40) == 0 )
      goto LABEL_142;
    v57 = *(_QWORD **)(v44 + 32);
    v58 = v4[12];
    v59 = (int)((unsigned __int64)(1759218605LL * *(int *)((*(_BYTE *)(v44 + 2) != 0 ? 4 : 0) + v49 + 184)) >> 32) >> 12;
    v60 = (v59 >> 31) + v59;
    v61 = v4[87] / 10000LL;
    v62 = SOCKADDR_SIZE(*(_WORD *)(v58 + 216));
    v63 = *(unsigned __int16 *)(v58 + 360);
    LOWORD(v63) = (unsigned __int16)v63 >> 1;
    McTemplateK0qjijhzr4hzr6hbr8hzr10hzr12xxqqq_EtwWriteTransfer(
      v63,
      (unsigned int)SMB2_EVENT_SLOW_FS_OPERATION_V1,
      (_DWORD)a1 + 584,
      *(unsigned __int16 *)(v77 + 14),
      (__int64)(v57 + 9),
      *v57,
      *(_QWORD *)(v58 + 496) + 72LL,
      (unsigned __int16)v72 >> 1,
      v73,
      v63,
      *(_QWORD *)(v58 + 368),
      v62,
      v58 + 216,
      v76,
      v70,
      v75,
      v69,
      v61,
      v60,
      *(_DWORD *)(v77 + 192),
      *(_DWORD *)(v77 + 208),
      *(_DWORD *)(v77 + 212));
  }
  else
  {
    if ( (byte_14004C339 & 0x40) == 0 )
      goto LABEL_142;
    v50 = *(_QWORD **)(v44 + 32);
    v51 = v4[12];
    v52 = (int)((unsigned __int64)(1759218605LL * *(int *)((*(_BYTE *)(v44 + 2) != 0 ? 4 : 0) + v49 + 184)) >> 32) >> 12;
    v53 = (v52 >> 31) + v52;
    v54 = v4[87] / 10000LL;
    v55 = SOCKADDR_SIZE(*(_WORD *)(v51 + 216));
    v56 = *(unsigned __int16 *)(v51 + 360);
    LOWORD(v56) = (unsigned __int16)v56 >> 1;
    McTemplateK0qjijhzr4hzr6hbr8hzr10hzr12xxqqq_EtwWriteTransfer(
      v56,
      (unsigned int)SMB2_EVENT_SLOW_NETWORK_OPERATION,
      (_DWORD)a1 + 584,
      *(unsigned __int16 *)(v77 + 14),
      (__int64)(v50 + 9),
      *v50,
      *(_QWORD *)(v51 + 496) + 72LL,
      (unsigned __int16)v72 >> 1,
      v73,
      v56,
      *(_QWORD *)(v51 + 368),
      v55,
      v51 + 216,
      v76,
      v70,
      v75,
      v69,
      v54,
      v53,
      *(_DWORD *)(v77 + 192),
      *(_DWORD *)(v77 + 208),
      *(_DWORD *)(v77 + 212));
  }
  v4 = a1;
LABEL_142:
  if ( pvContextBuffer )
    FreeContextBuffer(pvContextBuffer);
LABEL_35:
  if ( *(_QWORD *)(v3 + 160) )
    SrvNetFreeBuffer();
  v13 = *(void **)(v3 + 56);
  if ( v13 )
    Smb2DereferenceTreeConnect(v13);
  v14 = *(_QWORD *)(v3 + 32);
  if ( v14 )
    Smb2DereferenceSession(v14);
  if ( *(_QWORD *)(v3 + 48) )
    Smb2DereferenceSecurityContext();
  v15 = *(_QWORD *)(v3 + 80);
  if ( v15 )
  {
    v24 = *(_QWORD *)(v15 + 96);
    if ( v24 && *(_BYTE *)(v3 + 381) )
    {
      Smb2RkfNotifyComplete(v4[8], v24);
      *(_BYTE *)(v3 + 381) = 0;
    }
    Smb2DereferenceHandle(*(PVOID *)(v3 + 80));
  }
  v16 = *(void **)(v3 + 88);
  if ( v16 )
    ObfDereferenceObject(v16);
  v17 = *(void **)(v3 + 64);
  if ( v17 )
    Smb2DereferenceHandle(v17);
  Smb2PostCheckChannelSequence(v4);
  v18 = *(void **)(v3 + 72);
  if ( v18 )
    Smb2DereferenceFile(v18);
  v19 = *(void **)(v3 + 104);
  if ( v19 )
    Smb2DereferenceLease(v19);
  if ( *(_QWORD *)(v3 + 144) )
    Smb2DereferenceChannel();
  memset((void *)v3, 0, 0x1B0u);
  return 0;
}

```

## disassembly

```asm
0x140076130  mov     [rsp-8+arg_0], rcx
0x140076135  push    rbp
0x140076136  push    rbx
0x140076137  push    rsi
0x140076138  push    rdi
0x140076139  push    r12
0x14007613b  push    r13
0x14007613d  push    r14
0x14007613f  push    r15
0x140076141  lea     rbp, [rsp-1Fh]
0x140076146  sub     rsp, 0E8h
0x14007614d  mov     r8, [rcx+60h]
0x140076151  lea     r15, WPP_GLOBAL_Control
0x140076158  mov     r13, [rcx+230h]
0x14007615f  mov     rdi, rcx
0x140076162  mov     rcx, cs:WPP_GLOBAL_Control
0x140076169  mov     rbx, [r8+1F0h]
0x140076170  test    dword ptr [rcx+2Ch], 2000h
0x140076177  jnz     loc_140096D6A
0x14007617d  xor     r12d, r12d
0x140076180  cmp     [r13+7], r12b
0x140076184  jnz     loc_140076495
0x14007618a  cmp     [r13+2], r12b
0x14007618e  jnz     loc_1400764A5
0x140076194  mov     rcx, [r13+98h]
0x14007619b  test    rcx, rcx
0x14007619e  jnz     loc_1400764C0
0x1400761a4  movzx   ecx, word ptr [r13+0Eh]
0x1400761a9  mov     esi, 0Ah
0x1400761ae  test    ecx, ecx
0x1400761b0  jz      loc_140076629
0x1400761b6  sub     ecx, 1
0x1400761b9  jz      loc_140076601
0x1400761bf  sub     ecx, 4
0x1400761c2  jz      loc_1400762EC
0x1400761c8  sub     ecx, 3
0x1400761cb  jz      loc_140076413
0x1400761d1  sub     ecx, 1
0x1400761d4  jnz     loc_1400764D1
0x1400761da  cmp     [r13+4], r12b
0x1400761de  jnz     loc_140076316
0x1400761e4  mov     rbx, [rdi+230h]
0x1400761eb  mov     edx, [rbx+104h]
0x1400761f1  mov     byte ptr [rbx+4], 1
0x1400761f5  test    edx, edx
0x1400761f7  jz      loc_1400762BB
0x1400761fd  cmp     cs:byte_140058150, r12b
0x140076204  jz      loc_1400762BB
0x14007620a  mov     rax, [rbx+38h]
0x14007620e  mov     r8d, 170h
0x140076214  mov     rcx, [rax+68h]
0x140076218  lock inc dword ptr [rcx+r8]
0x14007621d  mov     rax, [rbx+28h]
0x140076221  lock inc dword ptr [rax+0D8h]
0x140076228  mov     rax, [rbx+38h]
0x14007622c  mov     esi, edx
0x14007622e  mov     rcx, [rax+68h]
0x140076232  lock add [rcx+180h], rsi
0x14007623a  mov     rax, [rbx+28h]
0x14007623e  lock add [rax+0E8h], rsi
0x140076246  mov     rax, [rbx+38h]
0x14007624a  mov     rcx, [rax+68h]
0x14007624e  lock add [rcx+240h], rsi
0x140076256  mov     rax, [rbx+28h]
0x14007625a  lock add [rax+178h], rsi
0x140076262  mov     rax, [rbx+38h]
0x140076266  mov     rcx, [rax+68h]
0x14007626a  lock inc dword ptr [rcx+238h]
0x140076271  mov     rax, [rbx+28h]
0x140076275  lock inc dword ptr [rax+r8]
0x14007627a  mov     rax, [rbx+18h]
0x14007627e  mov     rcx, [rax+60h]
0x140076282  mov     rcx, [rcx+1E0h]
0x140076289  call    cs:__imp_SrvNetIsRdmaConnection
0x140076290  nop     dword ptr [rax+rax+00h]
0x140076295  test    al, al
0x140076297  jnz     loc_14007643E
0x14007629d  mov     rax, [rbx+48h]
0x1400762a1  cmp     [rax+0F5h], r12b
0x1400762a8  jnz     loc_140076512
0x1400762ae  cmp     [rbx+0D8h], r12
0x1400762b5  jnz     loc_140076536
0x1400762bb  cmp     [rbx+0F0h], r12
0x1400762c2  jnz     loc_140076573
0x1400762c8  cmp     [rbx+0D8h], r12
0x1400762cf  jnz     loc_140096EA7
0x1400762d5  mov     rcx, [rbx+0D0h]; P
0x1400762dc  test    rcx, rcx
0x1400762df  jnz     loc_140076588
0x1400762e5  mov     esi, 0Ah
0x1400762ea  jmp     short loc_140076316
0x1400762ec  cmp     [r13+12Fh], r12b
0x1400762f3  jnz     loc_1400765A2
0x1400762f9  cmp     [r13+132h], r12b
0x140076300  jnz     loc_1400765CF
0x140076306  mov     rcx, [r13+140h]; EcpList
0x14007630d  test    rcx, rcx
0x140076310  jnz     loc_1400765E9
0x140076316  test    byte ptr [r13+10h], 4
0x14007631b  jnz     loc_140076651
0x140076321  mov     rcx, [rdi+2B8h]
0x140076328  mov     [rbp+57h+pvContextBuffer], r12
0x14007632c  mov     [rbp+57h+var_58], r12
0x140076330  mov     [rbp+57h+var_50], r12
0x140076334  test    rcx, rcx
0x140076337  jz      short loc_14007634D
0x140076339  mov     rdx, [rdi+40h]
0x14007633d  movsxd  rax, dword ptr [rdx+0B8h]
0x140076344  cmp     rcx, rax
0x140076347  jg      loc_1400971C6
0x14007634d  mov     rcx, [r13+0A0h]
0x140076354  test    rcx, rcx
0x140076357  jnz     loc_14007665E
0x14007635d  mov     rcx, [r13+38h]; P
0x140076361  test    rcx, rcx
0x140076364  jnz     loc_14007666F
0x14007636a  mov     rcx, [r13+20h]
0x14007636e  test    rcx, rcx
0x140076371  jz      short loc_140076378
0x140076373  call    Smb2DereferenceSession
0x140076378  mov     rcx, [r13+30h]
0x14007637c  test    rcx, rcx
0x14007637f  jnz     loc_140076409
0x140076385  mov     rax, [r13+50h]
0x140076389  test    rax, rax
0x14007638c  jnz     loc_140076679
0x140076392  mov     rcx, [r13+58h]; Object
0x140076396  test    rcx, rcx
0x140076399  jz      short loc_1400763A7
0x14007639b  call    cs:__imp_ObfDereferenceObject
0x1400763a2  nop     dword ptr [rax+rax+00h]
0x1400763a7  mov     rcx, [r13+40h]; P
0x1400763ab  test    rcx, rcx
0x1400763ae  jnz     loc_1400766A8
0x1400763b4  mov     rcx, rdi
0x1400763b7  call    Smb2PostCheckChannelSequence
0x1400763bc  mov     rcx, [r13+48h]; P
0x1400763c0  test    rcx, rcx
0x1400763c3  jnz     short loc_140076437
0x1400763c5  mov     rcx, [r13+68h]
0x1400763c9  test    rcx, rcx
0x1400763cc  jnz     loc_1400766B2
0x1400763d2  mov     rcx, [r13+90h]
0x1400763d9  test    rcx, rcx
0x1400763dc  jnz     loc_1400766BC
0x1400763e2  xor     edx, edx; Val
0x1400763e4  mov     r8d, 1B0h; Size
0x1400763ea  mov     rcx, r13; void *
0x1400763ed  call    memset
0x1400763f2  xor     eax, eax
0x1400763f4  add     rsp, 0E8h
0x1400763fb  pop     r15
0x1400763fd  pop     r14
0x1400763ff  pop     r13
0x140076401  pop     r12
0x140076403  pop     rdi
0x140076404  pop     rsi
0x140076405  pop     rbx
0x140076406  pop     rbp
0x140076407  retn
0x140076409  call    Smb2DereferenceSecurityContext
0x14007640e  jmp     loc_140076385
0x140076413  cmp     [r13+4], r12b
0x140076417  jnz     loc_140076316
0x14007641d  mov     rcx, rdi
0x140076420  call    Smb2CompleteRead
0x140076425  cmp     eax, 103h
0x14007642a  jnz     loc_140076316
0x140076430  mov     eax, 103h
0x140076435  jmp     short loc_1400763F4
0x140076437  call    Smb2DereferenceFile
0x14007643c  jmp     short loc_1400763C5
0x14007643e  mov     rax, [rbx+38h]
0x140076442  mov     rcx, [rax+68h]
0x140076446  lock inc dword ptr [rcx+174h]
0x14007644d  mov     rax, [rbx+38h]
0x140076451  mov     rcx, [rax+68h]
0x140076455  lock add [rcx+188h], rsi
0x14007645d  jmp     loc_14007629D
0x140076462  test    byte ptr [rcx+0Ah], 20h
0x140076466  jz      short loc_14007647B
0x140076468  mov     rdx, rcx; MemoryDescriptorList
0x14007646b  mov     rcx, [rcx+18h]; BaseAddress
0x14007646f  call    cs:__imp_MmUnmapLockedPages
0x140076476  nop     dword ptr [rax+rax+00h]
0x14007647b  inc     esi
0x14007647d  cmp     esi, [rbx+110h]
0x140076483  jb      loc_140096E50
0x140076489  lea     r15, WPP_GLOBAL_Control
0x140076490  jmp     loc_140096E86
0x140076495  mov     [r13+7], r12b
0x140076499  lock dec dword ptr [rbx+0C4h]
0x1400764a0  jmp     loc_14007618A
0x1400764a5  cmp     [r13+3], r12b
0x1400764a9  jnz     loc_140076194
0x1400764af  mov     byte ptr [r13+3], 1
0x1400764b4  lock dec dword ptr [rbx+0C0h]
0x1400764bb  jmp     loc_140076194
0x1400764c0  call    Smb2DereferenceClient
0x1400764c5  mov     [r13+98h], r12
0x1400764cc  jmp     loc_1400761A4
0x1400764d1  cmp     ecx, 2
0x1400764d4  jnz     loc_140076316
0x1400764da  mov     eax, [r13+0C0h]
0x1400764e1  cmp     eax, 98344h
0x1400764e6  jz      loc_140096E2F
0x1400764ec  cmp     eax, 983E8h
0x1400764f1  jz      loc_140096E0E
0x1400764f7  cmp     eax, 1440F2h
0x1400764fc  jz      loc_140096DCE
0x140076502  cmp     eax, 1480F2h
0x140076507  jnz     loc_140076316
0x14007650d  jmp     loc_140096DCE
0x140076512  mov     rax, [rbx+38h]
0x140076516  mov     rcx, [rax+68h]
0x14007651a  lock inc dword ptr [rcx+218h]
0x140076521  mov     rax, [rbx+38h]
0x140076525  mov     rcx, [rax+68h]
0x140076529  lock add [rcx+220h], rsi
0x140076531  jmp     loc_1400762AE
0x140076536  mov     rax, [rbx+38h]
0x14007653a  mov     rcx, [rax+68h]
0x14007653e  lock add [rcx+138h], rsi
0x140076546  mov     rax, [rbx+28h]
0x14007654a  lock add [rax+0A0h], rsi
0x140076552  mov     rax, [rbx+38h]
0x140076556  mov     rcx, [rax+68h]
0x14007655a  lock add [rcx+148h], rsi
0x140076562  mov     rax, [rbx+28h]
0x140076566  lock add [rax+0B0h], rsi
0x14007656e  jmp     loc_1400762BB
0x140076573  mov     esi, r12d
0x140076576  cmp     [rbx+110h], r12d
0x14007657d  ja      loc_140096E50
0x140076583  jmp     loc_140096E86
0x140076588  xor     edx, edx; Tag
0x14007658a  call    cs:__imp_ExFreePoolWithTag
0x140076591  nop     dword ptr [rax+rax+00h]
0x140076596  mov     [rbx+0D0h], r12
0x14007659d  jmp     loc_1400762E5
0x1400765a2  mov     rcx, [r13+0D0h]
0x1400765a9  call    cs:__imp_SrvLibFreePipeEa
0x1400765b0  nop     dword ptr [rax+rax+00h]
0x1400765b5  mov     [r13+0D0h], r12
0x1400765bc  mov     [r13+0D8h], r12d
0x1400765c3  mov     [r13+12Fh], r12b
0x1400765ca  jmp     loc_1400762F9
0x1400765cf  mov     rcx, [r13+68h]
0x1400765d3  test    rcx, rcx
0x1400765d6  jz      loc_140076306
0x1400765dc  xor     r8d, r8d
0x1400765df  call    Smb2LeaseDecrementOpensInProgressAndCloseIfUnused
0x1400765e4  jmp     loc_140076306
0x1400765e9  call    cs:__imp_FsRtlFreeExtraCreateParameterList
0x1400765f0  nop     dword ptr [rax+rax+00h]
0x1400765f5  mov     [r13+140h], r12
0x1400765fc  jmp     loc_140076316
0x140076601  mov     rcx, [r13+0C8h]
0x140076608  test    rcx, rcx
0x14007660b  jz      loc_140076316
0x140076611  call    cs:__imp_SmbCryptoHashDestroy
0x140076618  nop     dword ptr [rax+rax+00h]
0x14007661d  mov     [r13+0C8h], r12
0x140076624  jmp     loc_140076316
0x140076629  mov     rcx, [r13+0C8h]
0x140076630  test    rcx, rcx
0x140076633  jz      loc_1400970C7
0x140076639  call    cs:__imp_SmbCryptoHashDestroy
0x140076640  nop     dword ptr [rax+rax+00h]
0x140076645  mov     [r13+0C8h], r12
0x14007664c  jmp     loc_1400970C7
0x140076651  mov     rcx, r13
0x140076654  call    Smb2UpdatePerfCountersOnWorkItemCleanup
0x140076659  jmp     loc_140076321
0x14007665e  call    cs:__imp_SrvNetFreeBuffer
0x140076665  nop     dword ptr [rax+rax+00h]
0x14007666a  jmp     loc_14007635D
0x14007666f  call    Smb2DereferenceTreeConnect
0x140076674  jmp     loc_14007636A
0x140076679  mov     rdx, [rax+60h]
0x14007667d  test    rdx, rdx
0x140076680  jz      loc_14009755F
0x140076686  cmp     [r13+17Dh], r12b
0x14007668d  jz      loc_14009755F
0x140076693  mov     rcx, [rdi+40h]
0x140076697  call    Smb2RkfNotifyComplete
0x14007669c  mov     [r13+17Dh], r12b
0x1400766a3  jmp     loc_14009755F
0x1400766a8  call    Smb2DereferenceHandle
0x1400766ad  jmp     loc_1400763B4
0x1400766b2  call    Smb2DereferenceLease
0x1400766b7  jmp     loc_1400763D2
0x1400766bc  call    Smb2DereferenceChannel
0x1400766c1  jmp     loc_1400763E2
0x140096d6a  cmp     rcx, r15
0x140096d6d  jz      loc_14007617D
0x140096d73  cmp     byte ptr [rcx+29h], 2
0x140096d77  jb      loc_14007617D
0x140096d7d  mov     rax, [rdi+138h]
0x140096d84  mov     r9, rdi
  ... truncated ...
```
