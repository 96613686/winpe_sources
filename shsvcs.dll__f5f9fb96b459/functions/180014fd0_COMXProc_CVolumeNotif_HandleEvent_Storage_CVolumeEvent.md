# COMXProc::CVolumeNotif::HandleEvent(Storage::CVolumeEvent *)

- ea: `0x180014fd0`
- end: `0x1800153aa`
- name: `?HandleEvent@CVolumeNotif@COMXProc@@UEAAJPEAVCVolumeEvent@Storage@@@Z`
- size: `986`
- prototype: `int(COMXProc::CVolumeNotif *__hidden this, struct Storage::CVolumeEvent *)`
- caller_count: `0`
- callee_count: `14`
- tags: `reparse_path, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180003570`
- `0x180007b04`
- `0x180007b20`
- `0x1800137e0`
- `0x180014fd0`
- `0x1800153b0`
- `0x1800169e0`
- `0x180018480`
- `0x1800185c8`
- `0x18001b404`
- `0x1800298d8`
- `0x180029cdc`
- `0x180029dec`
- `0x180029eec`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800150f4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800150f4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015104`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015104`

## pseudocode

```c
__int64 __fastcall COMXProc::CVolumeNotif::HandleEvent(COMXProc::CVolumeNotif *this, struct Storage::CVolumeEvent *a2)
{
  __int64 v3; // rax
  CRefCounted *v4; // rsi
  __int64 v5; // rdi
  int Elem; // ebx
  CRefCounted *v7; // rcx
  int VOLUMEINFO2; // ebx
  _QWORD *v9; // rax
  void *v10; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v12; // rax
  COMXProc *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rax
  __int64 v25; // rax
  const unsigned __int16 *v26; // rdx
  __int64 v27; // r8
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  LPVOID lpMem; // [rsp+38h] [rbp+10h] BYREF
  CRefCounted *v33; // [rsp+40h] [rbp+18h] BYREF

  v3 = *(_QWORD *)&GUID_IO_MEDIA_ARRIVAL.Data1 - *((_QWORD *)a2 + 67);
  if ( *(_QWORD *)&GUID_IO_MEDIA_ARRIVAL.Data1 == *((_QWORD *)a2 + 67) )
    v3 = *(_QWORD *)GUID_IO_MEDIA_ARRIVAL.Data4 - *((_QWORD *)a2 + 68);
  if ( !v3 )
  {
    v4 = Storage::g_pnelVolumeInfo;
    v5 = 0;
    lpMem = 0;
    v33 = 0;
    CCritSectWithResource<CNamedElemList<PnPServices::CHandleNotif>>::Enter(*((_QWORD *)Storage::g_pnelVolumeInfo + 3));
    Elem = CNamedElemList<Storage::CVolumeInfo>::_GetElemSlot<unsigned short const *>(v4, (char *)a2 + 16, &v33);
    if ( Elem >= 0 )
    {
      v7 = v33;
      _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)v33 + 2) + 24LL));
      v5 = *((_QWORD *)v7 + 2);
      Elem = 0;
      CRefCounted::Release(v7);
    }
    CCritSectWithResource<CDummyResource>::Leave(*((_QWORD *)v4 + 3));
    if ( Elem >= 0 )
    {
      VOLUMEINFO2 = Storage::CVolume::GetVOLUMEINFO2((Storage::CVolume *)(v5 + 32), (struct tagVOLUMEINFO2 **)&lpMem);
      CRefCounted::Release((CRefCounted *)(v5 + 16));
      if ( VOLUMEINFO2 >= 0 )
      {
        v9 = operator new(0x38u);
        v10 = v9;
        if ( v9 )
        {
          *((_DWORD *)v9 + 2) = 1;
          *((_DWORD *)v9 + 4) = -2147418113;
          v9[3] = 0;
          *((_DWORD *)v9 + 8) = 0;
          v9[5] = 0;
          *v9 = &COMXProc::CThreadTaskVolumeEvent::`vftable';
          if ( (int)CThreadTaskRegister::RegisterWithService((CThreadTaskRegister *)v9) >= 0
            && COMXProc::CThreadTaskVolumeEvent::InitUpdated(
                 (COMXProc::CThreadTaskVolumeEvent *)v10,
                 (struct tagVOLUMEINFO2 *)lpMem) >= 0 )
          {
            CThreadTask::Run(v10);
          }
          CRefCounted::Release((CRefCounted *)v10);
        }
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, lpMem);
      }
    }
    return 0;
  }
  v12 = *(_QWORD *)&GUID_IO_DEVICE_BECOMING_READY.Data1 - *((_QWORD *)a2 + 67);
  if ( *(_QWORD *)&GUID_IO_DEVICE_BECOMING_READY.Data1 == *((_QWORD *)a2 + 67) )
    v12 = *(_QWORD *)GUID_IO_DEVICE_BECOMING_READY.Data4 - *((_QWORD *)a2 + 68);
  if ( !v12 )
  {
    v13 = (struct Storage::CVolumeEvent *)((char *)a2 + 16);
    v14 = 1024;
LABEL_44:
    COMXProc::_AdviseVolumeGenericEvent(v13, (const unsigned __int16 *)v14);
    return 0;
  }
  v15 = *(_QWORD *)&GUID_IO_MEDIA_REMOVAL.Data1 - *((_QWORD *)a2 + 67);
  if ( *(_QWORD *)&GUID_IO_MEDIA_REMOVAL.Data1 == *((_QWORD *)a2 + 67) )
    v15 = *(_QWORD *)GUID_IO_MEDIA_REMOVAL.Data4 - *((_QWORD *)a2 + 68);
  if ( !v15 )
    goto LABEL_68;
  v16 = *(_QWORD *)&GUID_IO_VOLUME_CHANGE.Data1 - *((_QWORD *)a2 + 67);
  if ( *(_QWORD *)&GUID_IO_VOLUME_CHANGE.Data1 == *((_QWORD *)a2 + 67) )
    v16 = *(_QWORD *)GUID_IO_VOLUME_CHANGE.Data4 - *((_QWORD *)a2 + 68);
  if ( !v16 )
    goto LABEL_68;
  v17 = *(_QWORD *)&GUID_IO_VOLUME_MOUNT.Data1 - *((_QWORD *)a2 + 67);
  if ( *(_QWORD *)&GUID_IO_VOLUME_MOUNT.Data1 == *((_QWORD *)a2 + 67) )
    v17 = *(_QWORD *)GUID_IO_VOLUME_MOUNT.Data4 - *((_QWORD *)a2 + 68);
  if ( !v17 )
  {
    COMXProc::_AdviseVolumeGenericEvent(
      (struct Storage::CVolumeEvent *)((char *)a2 + 16),
      (const unsigned __int16 *)0x100);
LABEL_68:
    v23 = 0;
    goto LABEL_69;
  }
  v18 = *(_QWORD *)&GUID_IO_VOLUME_DISMOUNT.Data1 - *((_QWORD *)a2 + 67);
  if ( *(_QWORD *)&GUID_IO_VOLUME_DISMOUNT.Data1 == *((_QWORD *)a2 + 67) )
    v18 = *(_QWORD *)GUID_IO_VOLUME_DISMOUNT.Data4 - *((_QWORD *)a2 + 68);
  if ( !v18 )
  {
    v13 = (struct Storage::CVolumeEvent *)((char *)a2 + 16);
    v14 = 512;
    goto LABEL_44;
  }
  v19 = *(_QWORD *)&GUID_IO_VOLUME_DISMOUNT_FAILED.Data1 - *((_QWORD *)a2 + 67);
  if ( *(_QWORD *)&GUID_IO_VOLUME_DISMOUNT_FAILED.Data1 == *((_QWORD *)a2 + 67) )
    v19 = *(_QWORD *)GUID_IO_VOLUME_DISMOUNT_FAILED.Data4 - *((_QWORD *)a2 + 68);
  if ( !v19 )
  {
    v13 = (struct Storage::CVolumeEvent *)((char *)a2 + 16);
    v14 = 256;
    goto LABEL_44;
  }
  v20 = *(_QWORD *)&GUID_IO_VOLUME_PREPARING_EJECT.Data1 - *((_QWORD *)a2 + 67);
  if ( *(_QWORD *)&GUID_IO_VOLUME_PREPARING_EJECT.Data1 == *((_QWORD *)a2 + 67) )
    v20 = *(_QWORD *)GUID_IO_VOLUME_PREPARING_EJECT.Data4 - *((_QWORD *)a2 + 68);
  if ( !v20 )
  {
    v13 = (struct Storage::CVolumeEvent *)((char *)a2 + 16);
    v14 = 2048;
    goto LABEL_44;
  }
  v21 = *(_QWORD *)&GUID_IO_VOLUME_BACKGROUND_FORMAT.Data1 - *((_QWORD *)a2 + 67);
  if ( *(_QWORD *)&GUID_IO_VOLUME_BACKGROUND_FORMAT.Data1 == *((_QWORD *)a2 + 67) )
    v21 = *(_QWORD *)GUID_IO_VOLUME_BACKGROUND_FORMAT.Data4 - *((_QWORD *)a2 + 68);
  if ( !v21 )
  {
    v13 = (struct Storage::CVolumeEvent *)((char *)a2 + 16);
    v14 = 4096;
    goto LABEL_44;
  }
  v22 = *(_QWORD *)&Storage::GUID_IO_VOLUME_ARRIVAL.Data1 - *((_QWORD *)a2 + 67);
  if ( *(_QWORD *)&Storage::GUID_IO_VOLUME_ARRIVAL.Data1 == *((_QWORD *)a2 + 67) )
    v22 = *(_QWORD *)Storage::GUID_IO_VOLUME_ARRIVAL.Data4 - *((_QWORD *)a2 + 68);
  if ( !v22 )
  {
    v23 = 1;
LABEL_69:
    COMXProc::_AdviseVolumeChangeHelper(a2, (struct Storage::CVolumeEvent *)v23);
    return 0;
  }
  v24 = *(_QWORD *)&Storage::GUID_IO_VOLUME_REMOVAL.Data1 - *((_QWORD *)a2 + 67);
  if ( *(_QWORD *)&Storage::GUID_IO_VOLUME_REMOVAL.Data1 == *((_QWORD *)a2 + 67) )
    v24 = *(_QWORD *)Storage::GUID_IO_VOLUME_REMOVAL.Data4 - *((_QWORD *)a2 + 68);
  if ( !v24 )
  {
    COMXProc::_AdviseVolumeRemoved((struct Storage::CVolumeEvent *)((char *)a2 + 16), (const unsigned __int16 *)a2);
    return 0;
  }
  v25 = *(_QWORD *)&Storage::GUID_IO_MOUNTPOINT_ARRIVAL.Data1 - *((_QWORD *)a2 + 67);
  if ( *(_QWORD *)&Storage::GUID_IO_MOUNTPOINT_ARRIVAL.Data1 == *((_QWORD *)a2 + 67) )
    v25 = *(_QWORD *)Storage::GUID_IO_MOUNTPOINT_ARRIVAL.Data4 - *((_QWORD *)a2 + 68);
  if ( !v25 )
  {
    v26 = (const unsigned __int16 *)((char *)a2 + 16);
    v27 = 1;
LABEL_61:
    COMXProc::_AdviseMountPointHelper(
      (struct Storage::CVolumeEvent *)((char *)a2 + 552),
      v26,
      (const unsigned __int16 *)v27);
    return 0;
  }
  v28 = *(_QWORD *)&Storage::GUID_IO_MOUNTPOINT_REMOVAL.Data1 - *((_QWORD *)a2 + 67);
  if ( *(_QWORD *)&Storage::GUID_IO_MOUNTPOINT_REMOVAL.Data1 == *((_QWORD *)a2 + 67) )
    v28 = *(_QWORD *)Storage::GUID_IO_MOUNTPOINT_REMOVAL.Data4 - *((_QWORD *)a2 + 68);
  if ( !v28 )
  {
    v26 = (const unsigned __int16 *)((char *)a2 + 16);
    v27 = 0;
    goto LABEL_61;
  }
  v29 = *(_QWORD *)&GUID_IO_VOLUME_FVE_STATUS_CHANGE.Data1 - *((_QWORD *)a2 + 67);
  if ( *(_QWORD *)&GUID_IO_VOLUME_FVE_STATUS_CHANGE.Data1 == *((_QWORD *)a2 + 67) )
    v29 = *(_QWORD *)GUID_IO_VOLUME_FVE_STATUS_CHANGE.Data4 - *((_QWORD *)a2 + 68);
  if ( !v29 )
    goto LABEL_68;
  v30 = *(_QWORD *)&GUID_IO_VOLUME_PHYSICAL_CONFIGURATION_CHANGE.Data1 - *((_QWORD *)a2 + 67);
  if ( *(_QWORD *)&GUID_IO_VOLUME_PHYSICAL_CONFIGURATION_CHANGE.Data1 == *((_QWORD *)a2 + 67) )
    v30 = *(_QWORD *)GUID_IO_VOLUME_PHYSICAL_CONFIGURATION_CHANGE.Data4 - *((_QWORD *)a2 + 68);
  if ( !v30 )
    goto LABEL_68;
  return 0;
}

```

## disassembly

```asm
0x180014fd0  mov     [rsp+arg_0], rbx
0x180014fd5  mov     [rsp+arg_18], rsi
0x180014fda  push    rdi
0x180014fdb  sub     rsp, 20h
0x180014fdf  mov     rax, qword ptr cs:GUID_IO_MEDIA_ARRIVAL.Data1
0x180014fe6  mov     rbx, rdx
0x180014fe9  sub     rax, [rdx+218h]
0x180014ff0  jnz     short loc_180015000
0x180014ff2  mov     rax, qword ptr cs:GUID_IO_MEDIA_ARRIVAL.Data4
0x180014ff9  sub     rax, [rdx+220h]
0x180015000  test    rax, rax
0x180015003  jnz     loc_18001510F
0x180015009  mov     rsi, cs:?g_pnelVolumeInfo@Storage@@3PEAV?$CNamedElemList@VCVolumeInfo@Storage@@@@EA; CNamedElemList<Storage::CVolumeInfo> * Storage::g_pnelVolumeInfo
0x180015010  xor     edi, edi
0x180015012  mov     [rsp+28h+lpMem], rax
0x180015017  mov     [rsp+28h+arg_10], rax
0x18001501c  mov     rcx, [rsi+18h]
0x180015020  call    ?Enter@?$CCritSectWithResource@V?$CNamedElemList@VCHandleNotif@PnPServices@@@@@@QEAAXXZ; CCritSectWithResource<CNamedElemList<PnPServices::CHandleNotif>>::Enter(void)
0x180015025  lea     rdx, [rbx+10h]
0x180015029  mov     rcx, rsi
0x18001502c  lea     r8, [rsp+28h+arg_10]
0x180015031  call    ??$_GetElemSlot@PEBG@?$CNamedElemList@VCVolumeInfo@Storage@@@@AEAAJQEBGPEAPEAV?$CElemSlot@VCVolumeInfo@Storage@@@@@Z; CNamedElemList<Storage::CVolumeInfo>::_GetElemSlot<ushort const *>(ushort const * const,CElemSlot<Storage::CVolumeInfo> * *)
0x180015036  mov     ebx, eax
0x180015038  test    eax, eax
0x18001503a  js      short loc_180015054
0x18001503c  mov     rcx, [rsp+28h+arg_10]; this
0x180015041  mov     rax, [rcx+10h]
0x180015045  lock inc dword ptr [rax+18h]
0x180015049  mov     rdi, [rcx+10h]
0x18001504d  xor     ebx, ebx
0x18001504f  call    ?Release@CRefCounted@@QEBAKXZ; CRefCounted::Release(void)
0x180015054  mov     rcx, [rsi+18h]
0x180015058  call    ?Leave@?$CCritSectWithResource@VCDummyResource@@@@QEAAXXZ; CCritSectWithResource<CDummyResource>::Leave(void)
0x18001505d  test    ebx, ebx
0x18001505f  js      loc_180015398
0x180015065  lea     rcx, [rdi+20h]; this
0x180015069  lea     rdx, [rsp+28h+lpMem]; struct tagVOLUMEINFO2 **
0x18001506e  call    ?GetVOLUMEINFO2@CVolume@Storage@@QEAAJPEAPEAUtagVOLUMEINFO2@@@Z; Storage::CVolume::GetVOLUMEINFO2(tagVOLUMEINFO2 * *)
0x180015073  lea     rcx, [rdi+10h]; this
0x180015077  mov     ebx, eax
0x180015079  call    ?Release@CRefCounted@@QEBAKXZ; CRefCounted::Release(void)
0x18001507e  test    ebx, ebx
0x180015080  js      loc_180015398
0x180015086  mov     ecx, 38h ; '8'; Size
0x18001508b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180015090  mov     rbx, rax
0x180015093  test    rax, rax
0x180015096  jz      short loc_1800150F4
0x180015098  mov     dword ptr [rax+8], 1
0x18001509f  mov     rcx, rbx; this
0x1800150a2  mov     dword ptr [rax+10h], 8000FFFFh
0x1800150a9  mov     qword ptr [rax+18h], 0
0x1800150b1  mov     dword ptr [rax+20h], 0
0x1800150b8  mov     qword ptr [rax+28h], 0
0x1800150c0  lea     rax, ??_7CThreadTaskVolumeEvent@COMXProc@@6B@; const COMXProc::CThreadTaskVolumeEvent::`vftable'
0x1800150c7  mov     [rbx], rax
0x1800150ca  call    ?RegisterWithService@CThreadTaskRegister@@QEAAJXZ; CThreadTaskRegister::RegisterWithService(void)
0x1800150cf  test    eax, eax
0x1800150d1  js      short loc_1800150EC
0x1800150d3  mov     rdx, [rsp+28h+lpMem]; struct tagVOLUMEINFO2 *
0x1800150d8  mov     rcx, rbx; this
0x1800150db  call    ?InitUpdated@CThreadTaskVolumeEvent@COMXProc@@QEAAJPEAUtagVOLUMEINFO2@@@Z; COMXProc::CThreadTaskVolumeEvent::InitUpdated(tagVOLUMEINFO2 *)
0x1800150e0  test    eax, eax
0x1800150e2  js      short loc_1800150EC
0x1800150e4  mov     rcx, rbx; Context
0x1800150e7  call    ?Run@CThreadTask@@QEAAJXZ; CThreadTask::Run(void)
0x1800150ec  mov     rcx, rbx; this
0x1800150ef  call    ?Release@CRefCounted@@QEBAKXZ; CRefCounted::Release(void)
0x1800150f4  call    cs:__imp_GetProcessHeap
0x1800150fa  mov     r8, [rsp+28h+lpMem]; lpMem
0x1800150ff  xor     edx, edx; dwFlags
0x180015101  mov     rcx, rax; hHeap
0x180015104  call    cs:__imp_HeapFree
0x18001510a  jmp     loc_180015398
0x18001510f  mov     rax, qword ptr cs:GUID_IO_DEVICE_BECOMING_READY.Data1
0x180015116  sub     rax, [rdx+218h]
0x18001511d  jnz     short loc_18001512D
0x18001511f  mov     rax, qword ptr cs:GUID_IO_DEVICE_BECOMING_READY.Data4
0x180015126  sub     rax, [rdx+220h]
0x18001512d  test    rax, rax
0x180015130  jnz     short loc_180015140
0x180015132  lea     rcx, [rdx+10h]
0x180015136  mov     edx, 400h
0x18001513b  jmp     loc_18001527D
0x180015140  mov     rax, qword ptr cs:GUID_IO_MEDIA_REMOVAL.Data1
0x180015147  sub     rax, [rdx+218h]
0x18001514e  jnz     short loc_18001515E
0x180015150  mov     rax, qword ptr cs:GUID_IO_MEDIA_REMOVAL.Data4
0x180015157  sub     rax, [rdx+220h]
0x18001515e  test    rax, rax
0x180015161  jz      loc_18001538E
0x180015167  mov     rax, qword ptr cs:GUID_IO_VOLUME_CHANGE.Data1
0x18001516e  sub     rax, [rdx+218h]
0x180015175  jnz     short loc_180015185
0x180015177  mov     rax, qword ptr cs:GUID_IO_VOLUME_CHANGE.Data4
0x18001517e  sub     rax, [rdx+220h]
0x180015185  test    rax, rax
0x180015188  jz      loc_18001538E
0x18001518e  mov     rax, qword ptr cs:GUID_IO_VOLUME_MOUNT.Data1
0x180015195  sub     rax, [rdx+218h]
0x18001519c  jnz     short loc_1800151AC
0x18001519e  mov     rax, qword ptr cs:GUID_IO_VOLUME_MOUNT.Data4
0x1800151a5  sub     rax, [rdx+220h]
0x1800151ac  test    rax, rax
0x1800151af  jnz     short loc_1800151C4
0x1800151b1  lea     rcx, [rdx+10h]; this
0x1800151b5  mov     edx, 100h; unsigned __int16 *
0x1800151ba  call    ?_AdviseVolumeGenericEvent@COMXProc@@YAJPEBGK@Z; COMXProc::_AdviseVolumeGenericEvent(ushort const *,ulong)
0x1800151bf  jmp     loc_18001538E
0x1800151c4  mov     rax, qword ptr cs:GUID_IO_VOLUME_DISMOUNT.Data1
0x1800151cb  sub     rax, [rdx+218h]
0x1800151d2  jnz     short loc_1800151E2
0x1800151d4  mov     rax, qword ptr cs:GUID_IO_VOLUME_DISMOUNT.Data4
0x1800151db  sub     rax, [rdx+220h]
0x1800151e2  test    rax, rax
0x1800151e5  jnz     short loc_1800151F5
0x1800151e7  lea     rcx, [rdx+10h]
0x1800151eb  mov     edx, 200h
0x1800151f0  jmp     loc_18001527D
0x1800151f5  mov     rax, qword ptr cs:GUID_IO_VOLUME_DISMOUNT_FAILED.Data1
0x1800151fc  sub     rax, [rdx+218h]
0x180015203  jnz     short loc_180015213
0x180015205  mov     rax, qword ptr cs:GUID_IO_VOLUME_DISMOUNT_FAILED.Data4
0x18001520c  sub     rax, [rdx+220h]
0x180015213  test    rax, rax
0x180015216  jnz     short loc_180015223
0x180015218  lea     rcx, [rdx+10h]
0x18001521c  mov     edx, 100h
0x180015221  jmp     short loc_18001527D
0x180015223  mov     rax, qword ptr cs:GUID_IO_VOLUME_PREPARING_EJECT.Data1
0x18001522a  sub     rax, [rdx+218h]
0x180015231  jnz     short loc_180015241
0x180015233  mov     rax, qword ptr cs:GUID_IO_VOLUME_PREPARING_EJECT.Data4
0x18001523a  sub     rax, [rdx+220h]
0x180015241  test    rax, rax
0x180015244  jnz     short loc_180015251
0x180015246  lea     rcx, [rdx+10h]
0x18001524a  mov     edx, 800h
0x18001524f  jmp     short loc_18001527D
0x180015251  mov     rax, qword ptr cs:GUID_IO_VOLUME_BACKGROUND_FORMAT.Data1
0x180015258  sub     rax, [rdx+218h]
0x18001525f  jnz     short loc_18001526F
0x180015261  mov     rax, qword ptr cs:GUID_IO_VOLUME_BACKGROUND_FORMAT.Data4
0x180015268  sub     rax, [rdx+220h]
0x18001526f  test    rax, rax
0x180015272  jnz     short loc_180015287
0x180015274  lea     rcx, [rdx+10h]; this
0x180015278  mov     edx, 1000h; unsigned __int16 *
0x18001527d  call    ?_AdviseVolumeGenericEvent@COMXProc@@YAJPEBGK@Z; COMXProc::_AdviseVolumeGenericEvent(ushort const *,ulong)
0x180015282  jmp     loc_180015398
0x180015287  mov     rax, qword ptr cs:?GUID_IO_VOLUME_ARRIVAL@Storage@@3U_GUID@@B.Data1; _GUID const Storage::GUID_IO_VOLUME_ARRIVAL ...
0x18001528e  sub     rax, [rdx+218h]
0x180015295  jnz     short loc_1800152A5
0x180015297  mov     rax, qword ptr cs:?GUID_IO_VOLUME_ARRIVAL@Storage@@3U_GUID@@B.Data4; _GUID const Storage::GUID_IO_VOLUME_ARRIVAL ...
0x18001529e  sub     rax, [rdx+220h]
0x1800152a5  test    rax, rax
0x1800152a8  jnz     short loc_1800152B2
0x1800152aa  lea     edx, [rax+1]; unsigned __int16 *
0x1800152ad  jmp     loc_180015390
0x1800152b2  mov     rax, qword ptr cs:?GUID_IO_VOLUME_REMOVAL@Storage@@3U_GUID@@B.Data1; _GUID const Storage::GUID_IO_VOLUME_REMOVAL ...
0x1800152b9  sub     rax, [rdx+218h]
0x1800152c0  jnz     short loc_1800152D0
0x1800152c2  mov     rax, qword ptr cs:?GUID_IO_VOLUME_REMOVAL@Storage@@3U_GUID@@B.Data4; _GUID const Storage::GUID_IO_VOLUME_REMOVAL ...
0x1800152c9  sub     rax, [rdx+220h]
0x1800152d0  test    rax, rax
0x1800152d3  jnz     short loc_1800152E3
0x1800152d5  lea     rcx, [rdx+10h]; this
0x1800152d9  call    ?_AdviseVolumeRemoved@COMXProc@@YAJPEBG@Z; COMXProc::_AdviseVolumeRemoved(ushort const *)
0x1800152de  jmp     loc_180015398
0x1800152e3  mov     rax, qword ptr cs:?GUID_IO_MOUNTPOINT_ARRIVAL@Storage@@3U_GUID@@B.Data1; _GUID const Storage::GUID_IO_MOUNTPOINT_ARRIVAL ...
0x1800152ea  sub     rax, [rdx+218h]
0x1800152f1  jnz     short loc_180015301
0x1800152f3  mov     rax, qword ptr cs:?GUID_IO_MOUNTPOINT_ARRIVAL@Storage@@3U_GUID@@B.Data4; _GUID const Storage::GUID_IO_MOUNTPOINT_ARRIVAL ...
0x1800152fa  sub     rax, [rdx+220h]
0x180015301  test    rax, rax
0x180015304  jnz     short loc_180015310
0x180015306  add     rdx, 10h
0x18001530a  lea     r8d, [rax+1]
0x18001530e  jmp     short loc_18001533A
0x180015310  mov     rax, qword ptr cs:?GUID_IO_MOUNTPOINT_REMOVAL@Storage@@3U_GUID@@B.Data1; _GUID const Storage::GUID_IO_MOUNTPOINT_REMOVAL ...
0x180015317  sub     rax, [rdx+218h]
0x18001531e  jnz     short loc_18001532E
0x180015320  mov     rax, qword ptr cs:?GUID_IO_MOUNTPOINT_REMOVAL@Storage@@3U_GUID@@B.Data4; _GUID const Storage::GUID_IO_MOUNTPOINT_REMOVAL ...
0x180015327  sub     rax, [rdx+220h]
0x18001532e  test    rax, rax
0x180015331  jnz     short loc_180015348
0x180015333  add     rdx, 10h; unsigned __int16 *
0x180015337  xor     r8d, r8d; unsigned __int16 *
0x18001533a  lea     rcx, [rbx+228h]; this
0x180015341  call    ?_AdviseMountPointHelper@COMXProc@@YAJPEBG0H@Z; COMXProc::_AdviseMountPointHelper(ushort const *,ushort const *,int)
0x180015346  jmp     short loc_180015398
0x180015348  mov     rax, qword ptr cs:GUID_IO_VOLUME_FVE_STATUS_CHANGE.Data1
0x18001534f  sub     rax, [rdx+218h]
0x180015356  jnz     short loc_180015366
0x180015358  mov     rax, qword ptr cs:GUID_IO_VOLUME_FVE_STATUS_CHANGE.Data4
0x18001535f  sub     rax, [rdx+220h]
0x180015366  test    rax, rax
0x180015369  jz      short loc_18001538E
0x18001536b  mov     rax, qword ptr cs:GUID_IO_VOLUME_PHYSICAL_CONFIGURATION_CHANGE.Data1
0x180015372  sub     rax, [rdx+218h]
0x180015379  jnz     short loc_180015389
0x18001537b  mov     rax, qword ptr cs:GUID_IO_VOLUME_PHYSICAL_CONFIGURATION_CHANGE.Data4
0x180015382  sub     rax, [rdx+220h]
0x180015389  test    rax, rax
0x18001538c  jnz     short loc_180015398
0x18001538e  xor     edx, edx; struct Storage::CVolumeEvent *
0x180015390  mov     rcx, rbx; this
0x180015393  call    ?_AdviseVolumeChangeHelper@COMXProc@@YAJPEAVCVolumeEvent@Storage@@H@Z; COMXProc::_AdviseVolumeChangeHelper(Storage::CVolumeEvent *,int)
0x180015398  mov     rbx, [rsp+28h+arg_0]
0x18001539d  xor     eax, eax
0x18001539f  mov     rsi, [rsp+28h+arg_18]
0x1800153a4  add     rsp, 20h
0x1800153a8  pop     rdi
0x1800153a9  retn
```
