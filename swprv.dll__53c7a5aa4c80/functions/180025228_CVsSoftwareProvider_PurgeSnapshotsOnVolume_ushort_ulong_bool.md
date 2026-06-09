# CVsSoftwareProvider::PurgeSnapshotsOnVolume(ushort *,ulong,bool)

- ea: `0x180025228`
- end: `0x180025c37`
- name: `?PurgeSnapshotsOnVolume@CVsSoftwareProvider@@CAXPEAGK_N@Z`
- size: `2575`
- prototype: `void __fastcall(unsigned __int16 *, unsigned int, bool)`
- caller_count: `3`
- callee_count: `22`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18000ffe0`
- `0x180024a6c`
- `0x1800250bc`

## callees

- `0x180001580`
- `0x18000212c`
- `0x180002f1c`
- `0x180003718`
- `0x1800039d8`
- `0x180003de8`
- `0x18000610c`
- `0x180007604`
- `0x18000dbd0`
- `0x180015864`
- `0x180016ff0`
- `0x18001b65c`
- `0x18001bdd8`
- `0x18001d648`
- `0x1800235e0`
- `0x180023834`
- `0x18002432c`
- `0x180025228`
- `0x180033a8c`
- `0x180033c78`
- `0x180034278`
- `0x1800367b8`

## string_xrefs

- `0x180025263`: `base\stor\vss\modules\softprv\src\delete.cxx`
- `0x180025b51`: `base\stor\vss\modules\softprv\src\delete.cxx`
- `0x180025716`: `Warning: snapshot %s cannot be opened`
- `0x18002559a`: `Timewarp snapshots to be deleted: %lu from %lu (max: %lu)`
- `0x1800258db`: `Deleting incomplete snapshot%s`
- `0x180025aff`: `StringCchCopy failed, %#x`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall CVsSoftwareProvider::PurgeSnapshotsOnVolume(unsigned __int16 *a1, int a2, char a3)
{
  const wchar_t *v3; // rax
  LPVOID *Ref; // rax
  unsigned __int64 v5; // r8
  char v6; // al
  unsigned __int16 *v7; // [rsp+20h] [rbp-858h]
  int v8; // [rsp+20h] [rbp-858h]
  int v9; // [rsp+20h] [rbp-858h]
  __int64 v10; // [rsp+28h] [rbp-850h]
  __int64 v11; // [rsp+38h] [rbp-840h]
  __int64 v12; // [rsp+38h] [rbp-840h]
  bool v14; // [rsp+51h] [rbp-827h] BYREF
  int v15; // [rsp+54h] [rbp-824h] BYREF
  unsigned int v16; // [rsp+58h] [rbp-820h]
  unsigned __int16 *v17; // [rsp+60h] [rbp-818h]
  unsigned __int64 m_tsCreationTimestamp; // [rsp+68h] [rbp-810h]
  unsigned int TimewarpSnapshotsCount; // [rsp+70h] [rbp-808h] BYREF
  unsigned __int16 *v20; // [rsp+78h] [rbp-800h]
  void **v21; // [rsp+80h] [rbp-7F8h] BYREF
  unsigned __int16 *v22; // [rsp+88h] [rbp-7F0h]
  const unsigned __int16 *v23; // [rsp+90h] [rbp-7E8h] BYREF
  const unsigned __int16 *v24; // [rsp+98h] [rbp-7E0h]
  const unsigned __int16 *v25; // [rsp+A0h] [rbp-7D8h]
  int v26; // [rsp+A8h] [rbp-7D0h]
  int v27; // [rsp+ACh] [rbp-7CCh]
  int v28; // [rsp+B0h] [rbp-7C8h]
  _BYTE v29[120]; // [rsp+B8h] [rbp-7C0h] BYREF
  int v30; // [rsp+130h] [rbp-748h]
  LPVOID v31; // [rsp+140h] [rbp-738h] BYREF
  int TimestampIoctl; // [rsp+148h] [rbp-730h]
  unsigned int v33; // [rsp+164h] [rbp-714h]
  unsigned int v34; // [rsp+1B0h] [rbp-6C8h] BYREF
  __int64 v35; // [rsp+1C0h] [rbp-6B8h] BYREF
  __int128 v36; // [rsp+1C8h] [rbp-6B0h]
  __int128 v37; // [rsp+1D8h] [rbp-6A0h]
  __int16 v38; // [rsp+1E8h] [rbp-690h]
  __int64 v39; // [rsp+1ECh] [rbp-68Ch]
  __int64 v40; // [rsp+1F8h] [rbp-680h]
  __int64 v41; // [rsp+200h] [rbp-678h]
  int v42; // [rsp+208h] [rbp-670h]
  __int64 v43; // [rsp+210h] [rbp-668h]
  __int16 v44; // [rsp+218h] [rbp-660h]
  void **v45; // [rsp+220h] [rbp-658h]
  __int64 v46; // [rsp+228h] [rbp-650h]
  _QWORD v47[2]; // [rsp+230h] [rbp-648h] BYREF
  __int64 v48; // [rsp+240h] [rbp-638h] BYREF
  __int128 v49; // [rsp+248h] [rbp-630h]
  __int128 v50; // [rsp+258h] [rbp-620h]
  __int16 v51; // [rsp+268h] [rbp-610h]
  __int64 v52; // [rsp+26Ch] [rbp-60Ch]
  __int64 v53; // [rsp+278h] [rbp-600h]
  __int64 v54; // [rsp+280h] [rbp-5F8h]
  int v55; // [rsp+288h] [rbp-5F0h]
  __int64 v56; // [rsp+290h] [rbp-5E8h]
  __int16 v57; // [rsp+298h] [rbp-5E0h]
  void **v58; // [rsp+2A0h] [rbp-5D8h]
  __int64 v59; // [rsp+2A8h] [rbp-5D0h]
  const unsigned __int16 *v60; // [rsp+2B0h] [rbp-5C8h] BYREF
  const unsigned __int16 *v61; // [rsp+2B8h] [rbp-5C0h]
  const unsigned __int16 *v62; // [rsp+2C0h] [rbp-5B8h]
  int v63; // [rsp+2C8h] [rbp-5B0h]
  int v64; // [rsp+2CCh] [rbp-5ACh]
  int v65; // [rsp+2D0h] [rbp-5A8h]
  _BYTE v66[120]; // [rsp+2D8h] [rbp-5A0h] BYREF
  int v67; // [rsp+350h] [rbp-528h]
  _com_error *v68; // [rsp+358h] [rbp-520h] BYREF
  const std::exception *v69; // [rsp+360h] [rbp-518h] BYREF
  _VSS_SNAPSHOT_PROP v70; // [rsp+370h] [rbp-508h] BYREF
  int v71; // [rsp+410h] [rbp-468h]
  unsigned __int16 v72[264]; // [rsp+420h] [rbp-458h] BYREF
  unsigned __int16 v73[264]; // [rsp+630h] [rbp-248h] BYREF

  v15 = a2;
  v17 = a1;
  v20 = a1;
  *(_QWORD *)&v70.m_SnapshotId.Data1 = L"base\\stor\\vss\\modules\\softprv\\src\\delete.cxx";
  *(_QWORD *)v70.m_SnapshotId.Data4 = L"CVsSoftwareProvider::PurgeSnapshotsOnVolume";
  *(_QWORD *)&v70.m_SnapshotSetId.Data1 = L"SPRDELEC";
  *(_DWORD *)v70.m_SnapshotSetId.Data4 = 418;
  *(_DWORD *)&v70.m_SnapshotSetId.Data4[4] = 2;
  v70.m_lSnapshotsCount = 255;
  v71 = 0x1000000;
  memset_0(&v70.m_pwszSnapshotDeviceObject, 0, 0x78u);
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v31, (__int64)&v70, 0);
  *(_QWORD *)&v70.m_SnapshotId.Data1 = L"base\\stor\\vss\\modules\\softprv\\src\\delete.cxx";
  *(_QWORD *)v70.m_SnapshotId.Data4 = L"CVsSoftwareProvider::PurgeSnapshotsOnVolume";
  *(_QWORD *)&v70.m_SnapshotSetId.Data1 = L"SPRDELEC";
  *(_DWORD *)v70.m_SnapshotSetId.Data4 = 422;
  *(_DWORD *)&v70.m_SnapshotSetId.Data4[4] = 2;
  v70.m_lSnapshotsCount = 255;
  v71 = 0x1000000;
  memset_0(&v70.m_pwszSnapshotDeviceObject, 0, 0x78u);
  v3 = L"TRUE";
  if ( !a3 )
    v3 = L"FALSE";
  CVssFunctionTracer::Trace(&v31, &v70, L"volume: %s, maxTimewarpSnaps: %d, purgeAtLoad: %s", v17, v15, v3);
  v35 = 0;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  v46 = 0;
  v45 = &CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::`vftable';
  v36 = 0;
  v37 = 0;
  v48 = 0;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  v54 = 0;
  v55 = 0;
  v56 = 0;
  v57 = 0;
  v59 = 0;
  v58 = &CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::`vftable';
  v49 = 0;
  v50 = 0;
  memset_0(v73, 0, 0x208u);
  *(_QWORD *)&v70.m_SnapshotId.Data1 = L"base\\stor\\vss\\modules\\softprv\\src\\delete.cxx";
  *(_QWORD *)v70.m_SnapshotId.Data4 = L"CVsSoftwareProvider::PurgeSnapshotsOnVolume";
  *(_QWORD *)&v70.m_SnapshotSetId.Data1 = L"SPRDELEC";
  *(_DWORD *)v70.m_SnapshotSetId.Data4 = 433;
  *(_DWORD *)&v70.m_SnapshotSetId.Data4[4] = 2;
  v70.m_lSnapshotsCount = 255;
  v71 = 0x1000000;
  memset_0(&v70.m_pwszSnapshotDeviceObject, 0, 0x78u);
  try
  {
    CVssFunctionTracer::AddContext((__int64)&v31, (const struct CVssDebugInfo *)&v70);
    CVssIOCTLChannel::Open((CVssIOCTLChannel *)&v35, (__int64)&v31, v17, 1, 1, 2, 0, v11, 0x80u);
    v16 = 0;
    if ( v15 != -1 )
    {
      TimewarpSnapshotsCount = CVsSoftwareProvider::GetTimewarpSnapshotsCount((struct CVssIOCTLChannel *)&v35);
      v16 = v15 < TimewarpSnapshotsCount ? TimewarpSnapshotsCount - v15 : 0;
      *(_QWORD *)&v70.m_SnapshotId.Data1 = L"base\\stor\\vss\\modules\\softprv\\src\\delete.cxx";
      *(_QWORD *)v70.m_SnapshotId.Data4 = L"CVsSoftwareProvider::PurgeSnapshotsOnVolume";
      *(_QWORD *)&v70.m_SnapshotSetId.Data1 = L"SPRDELEC";
      *(_DWORD *)v70.m_SnapshotSetId.Data4 = 450;
      *(_DWORD *)&v70.m_SnapshotSetId.Data4[4] = 2;
      v70.m_lSnapshotsCount = 255;
      v71 = 0x1000000;
      memset_0(&v70.m_pwszSnapshotDeviceObject, 0, 0x78u);
      LODWORD(v10) = v15;
      LODWORD(v7) = TimewarpSnapshotsCount;
      CVssFunctionTracer::Trace(&v31, &v70, L"Timewarp snapshots to be deleted: %lu from %lu (max: %lu)", v16, v7, v10);
    }
    m_tsCreationTimestamp = 0;
    LODWORD(v39) = 0;
    LODWORD(v41) = 0;
    CVssIOCTLChannel::Call(&v35, (__int64)&v31, 0x530018u, 1, 2, 0);
    TimewarpSnapshotsCount = 0;
    CVssIOCTLChannel::Unpack<unsigned long>(
      (CVssIOCTLChannel *)&v35,
      (struct CVssFunctionTracer *)&v31,
      &TimewarpSnapshotsCount);
    v22 = 0;
    v21 = &CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::`vftable';
    while ( 1 )
    {
      Ref = (LPVOID *)CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::ResetAndGetRef(&v21);
      if ( !CVssIOCTLChannel::UnpackZeroString((CVssIOCTLChannel *)&v35, (struct CVssFunctionTracer *)&v31, Ref) )
      {
LABEL_10:
        if ( a3 && v73[0] )
          CVsSoftwareProvider::CheckSetSnapshotReadOnly(v73);
        CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::~CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>(&v21);
        goto LABEL_42;
      }
      VssConcatenate((struct CVssFunctionTracer *)&v31, v72, v5, L"\\\\?\\GLOBALROOT", v22);
      TimestampIoctl = CVssIOCTLChannel::Open((CVssIOCTLChannel *)&v48, (__int64)&v31, v72, 0, 1, 2, 0, v12, 0x80u);
      if ( TimestampIoctl < 0 )
      {
        v23 = L"base\\stor\\vss\\modules\\softprv\\src\\delete.cxx";
        v24 = L"CVsSoftwareProvider::PurgeSnapshotsOnVolume";
        v25 = L"SPRDELEC";
        v26 = 486;
        v27 = 2;
        v28 = 255;
        v30 = 0x1000000;
        memset_0(v29, 0, sizeof(v29));
        CVssFunctionTracer::Trace(&v31, &v23, L"Warning: snapshot %s cannot be opened", v72);
        goto LABEL_10;
      }
      TimestampIoctl = CVssIOCTLChannel::Call(&v48, (__int64)&v31, 0x53019Cu, 0, 0, 0);
      if ( TimestampIoctl < 0 )
      {
        v23 = L"base\\stor\\vss\\modules\\softprv\\src\\delete.cxx";
        v24 = L"CVsSoftwareProvider::PurgeSnapshotsOnVolume";
        v25 = L"SPRDELEC";
        v26 = 494;
        v27 = 2;
        v28 = 255;
        v30 = 0x1000000;
        memset_0(v29, 0, sizeof(v29));
        CVssFunctionTracer::Trace(&v31, &v23, L"Warning: snapshot %s cannot be queried for properties", v72);
        goto LABEL_10;
      }
      v70.m_SnapshotId.Data1 = 0;
      memset_0(&v70.m_SnapshotId.Data2, 0, 0x7Cu);
      v15 = 0;
      v14 = 0;
      v47[0] = &CVssAuto<_VSS_SNAPSHOT_PROP *,CVssAutoGenericValue_Storage<_VSS_SNAPSHOT_PROP *,0,void (*)(_VSS_SNAPSHOT_PROP *),&void VssFreeSnapshotProperties(_VSS_SNAPSHOT_PROP *),_VSS_SNAPSHOT_PROP * & (*)(_VSS_SNAPSHOT_PROP * &),&public: static _VSS_SNAPSHOT_PROP * & DTyper<_VSS_SNAPSHOT_PROP *>::Identity(_VSS_SNAPSHOT_PROP * &)>>::`vftable';
      v47[1] = &v70;
      if ( CVssQueuedSnapshot::LoadStructure((struct CVssIOCTLChannel *)&v48, &v70, &v15, &v14, 0) )
      {
        if ( v14 )
          goto LABEL_23;
        if ( a3 )
        {
          if ( v70.m_eStatus != VSS_SS_CREATED )
          {
            v23 = L"base\\stor\\vss\\modules\\softprv\\src\\delete.cxx";
            v24 = L"CVsSoftwareProvider::PurgeSnapshotsOnVolume";
            v25 = L"SPRDELEC";
            v26 = 517;
            v27 = 2;
            v28 = 255;
            v30 = 0x1000000;
            memset_0(v29, 0, sizeof(v29));
            CVssFunctionTracer::Trace(&v31, &v23, L"Deleting incomplete snapshot%s", v72);
LABEL_23:
            CVsSoftwareProvider::DeleteSnapshot(v17, v22, v72, &v70, v8);
            goto LABEL_24;
          }
          v6 = v15;
          if ( (v15 & 8) == 0 )
          {
            v23 = L"base\\stor\\vss\\modules\\softprv\\src\\delete.cxx";
            v24 = L"CVsSoftwareProvider::PurgeSnapshotsOnVolume";
            v25 = L"SPRDELEC";
            v26 = 525;
            v27 = 2;
            v28 = 255;
            v30 = 0x1000000;
            memset_0(v29, 0, sizeof(v29));
            CVssFunctionTracer::Trace(&v31, &v23, L"Deleting AutoRelease snapshot %s", v72);
            goto LABEL_23;
          }
        }
        else
        {
          v6 = v15;
        }
        if ( v16 && (v6 & 4) != 0 )
        {
          v23 = L"base\\stor\\vss\\modules\\softprv\\src\\delete.cxx";
          v24 = L"CVsSoftwareProvider::PurgeSnapshotsOnVolume";
          v25 = L"SPRDELEC";
          v26 = 531;
          v27 = 2;
          v28 = 255;
          v30 = 0x1000000;
          memset_0(v29, 0, sizeof(v29));
          v9 = v16;
          CVssFunctionTracer::Trace(&v31, &v23, L"Deleting old Timewarp snapshot %s [index %lu]", v72);
          --v16;
          CVsSoftwareProvider::DeleteSnapshot(v17, v22, v72, &v70, v9);
        }
        else
        {
          TimestampIoctl = CVssQueuedSnapshot::LoadTimestampIoctl(
                             (struct CVssIOCTLChannel *)&v48,
                             &v70.m_tsCreationTimestamp);
          if ( TimestampIoctl >= 0 && m_tsCreationTimestamp < v70.m_tsCreationTimestamp )
          {
            m_tsCreationTimestamp = v70.m_tsCreationTimestamp;
            TimestampIoctl = StringCchCopyW(v73, 0x104u, v72);
            if ( TimestampIoctl < 0 )
            {
              v60 = L"base\\stor\\vss\\modules\\softprv\\src\\delete.cxx";
              v61 = L"CVsSoftwareProvider::PurgeSnapshotsOnVolume";
              v62 = L"SPRDELEC";
              v63 = 553;
              v64 = 2;
              v65 = 255;
              v67 = 0x1000000;
              memset_0(v66, 0, sizeof(v66));
              CVssFunctionTracer::Trace(&v31, &v60, L"StringCchCopy failed, %#x", (unsigned int)TimestampIoctl);
              v73[0] = 0;
            }
          }
        }
      }
LABEL_24:
      CVssAuto<_VSS_SNAPSHOT_PROP *,CVssAutoGenericValue_Storage<_VSS_SNAPSHOT_PROP *,0,void (*)(_VSS_SNAPSHOT_PROP *),&void VssFreeSnapshotProperties(_VSS_SNAPSHOT_PROP *),_VSS_SNAPSHOT_PROP * & (*)(_VSS_SNAPSHOT_PROP * &),&public: static _VSS_SNAPSHOT_PROP * & DTyper<_VSS_SNAPSHOT_PROP *>::Identity(_VSS_SNAPSHOT_PROP * &)>>::~CVssAuto<_VSS_SNAPSHOT_PROP *,CVssAutoGenericValue_Storage<_VSS_SNAPSHOT_PROP *,0,void (*)(_VSS_SNAPSHOT_PROP *),&void VssFreeSnapshotProperties(_VSS_SNAPSHOT_PROP *),_VSS_SNAPSHOT_PROP * & (*)(_VSS_SNAPSHOT_PROP * &),&public: static _VSS_SNAPSHOT_PROP * & DTyper<_VSS_SNAPSHOT_PROP *>::Identity(_VSS_SNAPSHOT_PROP * &)>>(v47);
    }
  }
  catch ( long v34 )
  {
    CVssFunctionTracer::HandleHresultException(
      (CVssFunctionTracer *)&v31,
      v34,
      L"base\\stor\\vss\\modules\\softprv\\src\\delete.cxx",
      L"SPRDELEC",
      L"CVsSoftwareProvider::PurgeSnapshotsOnVolume",
      0x23Du,
      v33);
    v17 = v20;
  }
  catch ( _com_error *v68 )
  {
    CVssFunctionTracer::HandleComException(
      (CVssFunctionTracer *)&v31,
      v68,
      L"base\\stor\\vss\\modules\\softprv\\src\\delete.cxx",
      L"SPRDELEC",
      L"CVsSoftwareProvider::PurgeSnapshotsOnVolume",
      0x23Du,
      v33);
  }
  catch ( std::bad_alloc )
  {
    CVssFunctionTracer::HandleStdBadAllocException(
      (CVssFunctionTracer *)&v31,
      L"base\\stor\\vss\\modules\\softprv\\src\\delete.cxx",
      L"SPRDELEC",
      L"CVsSoftwareProvider::PurgeSnapshotsOnVolume",
      0x23Du,
      v33);
    v17 = v20;
  }
  catch ( const std::exception *v69 )
  {
    CVssFunctionTracer::HandleStdGenericException(
      (CVssFunctionTracer *)&v31,
      v69,
      L"base\\stor\\vss\\modules\\softprv\\src\\delete.cxx",
      L"SPRDELEC",
      L"CVsSoftwareProvider::PurgeSnapshotsOnVolume",
      0x23Du,
      v33);
  }
LABEL_42:
  if ( TimestampIoctl < 0 )
  {
    v60 = L"base\\stor\\vss\\modules\\softprv\\src\\delete.cxx";
    v61 = L"CVsSoftwareProvider::PurgeSnapshotsOnVolume";
    v62 = L"SPRDELEC";
    v63 = 576;
    v64 = 2;
    v65 = 255;
    v67 = 0x1000000;
    memset_0(v66, 0, sizeof(v66));
    CVssFunctionTracer::Trace(
      &v31,
      &v60,
      L"Error 0x%08lx detected while purging snapshots on %s volume ",
      (unsigned int)TimestampIoctl,
      v17);
  }
  CVssIOCTLChannel::~CVssIOCTLChannel((CVssIOCTLChannel *)&v48);
  CVssIOCTLChannel::~CVssIOCTLChannel((CVssIOCTLChannel *)&v35);
  CVssFunctionTracer::~CVssFunctionTracer(&v31);
}

```

## disassembly

```asm
0x180025228  mov     r11, rsp
0x18002522b  mov     [r11+18h], rbx
0x18002522f  push    rsi
0x180025230  push    rdi
0x180025231  push    r13
0x180025233  push    r14
0x180025235  push    r15
0x180025237  sub     rsp, 850h
0x18002523e  mov     rax, cs:__security_cookie
0x180025245  xor     rax, rsp
0x180025248  mov     [rsp+878h+var_38], rax
0x180025250  mov     [rsp+878h+var_828], r8b
0x180025255  mov     [rsp+878h+var_824], edx
0x180025259  mov     [rsp+878h+var_818], rcx
0x18002525e  mov     [rsp+878h+var_800], rcx
0x180025263  lea     rsi, aBaseStorVssMod_5; "base\\stor\\vss\\modules\\softprv\\src"...
0x18002526a  mov     [r11-508h], rsi
0x180025271  lea     r14, aCvssoftwarepro_23; "CVsSoftwareProvider::PurgeSnapshotsOnVo"...
0x180025278  mov     [r11-500h], r14
0x18002527f  lea     r15, aSprdelec; "SPRDELEC"
0x180025286  mov     [r11-4F8h], r15
0x18002528d  mov     dword ptr [rsp+878h+var_508.m_SnapshotSetId.Data4], 1A2h
0x180025298  mov     edi, 2
0x18002529d  mov     dword ptr [rsp+878h+var_508.m_SnapshotSetId.Data4+4], edi
0x1800252a4  mov     [rsp+878h+var_508.m_lSnapshotsCount], 0FFh
0x1800252af  xor     ebx, ebx
0x1800252b1  mov     [rsp+878h+var_468], 1000000h
0x1800252bc  lea     r13d, [rdi+76h]
0x1800252c0  mov     r8d, r13d; Size
0x1800252c3  xor     edx, edx; Val
0x1800252c5  lea     rcx, [r11-4E0h]; void *
0x1800252cc  call    memset_0
0x1800252d1  xor     r8d, r8d
0x1800252d4  lea     rdx, [rsp+878h+var_508]
0x1800252dc  lea     rcx, [rsp+878h+var_738]
0x1800252e4  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x1800252e9  nop
0x1800252ea  mov     qword ptr [rsp+878h+var_508.m_SnapshotId.Data1], rsi
0x1800252f2  mov     qword ptr [rsp+878h+var_508.m_SnapshotId.Data4], r14
0x1800252fa  mov     qword ptr [rsp+878h+var_508.m_SnapshotSetId.Data1], r15
0x180025302  mov     dword ptr [rsp+878h+var_508.m_SnapshotSetId.Data4], 1A6h
0x18002530d  mov     dword ptr [rsp+878h+var_508.m_SnapshotSetId.Data4+4], edi
0x180025314  mov     [rsp+878h+var_508.m_lSnapshotsCount], 0FFh
0x18002531f  mov     [rsp+878h+var_468], 1000000h
0x18002532a  mov     r8d, r13d; Size
0x18002532d  xor     edx, edx; Val
0x18002532f  lea     rcx, [rsp+878h+var_508.m_pwszSnapshotDeviceObject]; void *
0x180025337  call    memset_0
0x18002533c  lea     rcx, aFalse; "FALSE"
0x180025343  lea     rax, aTrue; "TRUE"
0x18002534a  cmp     [rsp+878h+var_828], bl
0x18002534e  cmovz   rax, rcx
0x180025352  mov     [rsp+878h+var_850], rax
0x180025357  mov     eax, [rsp+878h+var_824]
0x18002535b  mov     dword ptr [rsp+878h+var_858], eax
0x18002535f  mov     r9, [rsp+878h+var_818]
0x180025364  lea     r8, aVolumeSMaxtime; "volume: %s, maxTimewarpSnaps: %d, purge"...
0x18002536b  lea     rdx, [rsp+878h+var_508]
0x180025373  lea     rcx, [rsp+878h+var_738]
0x18002537b  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x180025380  mov     [rsp+878h+var_6B8], rbx
0x180025388  mov     [rsp+878h+var_690], bx
0x180025390  mov     [rsp+878h+var_68C], rbx
0x180025398  mov     [rsp+878h+var_680], rbx
0x1800253a0  mov     [rsp+878h+var_678], rbx
0x1800253a8  mov     [rsp+878h+var_670], ebx
0x1800253af  mov     [rsp+878h+var_668], rbx
0x1800253b7  mov     [rsp+878h+var_660], bx
0x1800253bf  mov     [rsp+878h+var_650], rbx
0x1800253c7  lea     rax, ??_7?$CVssAuto@PEAGV?$CVssAllocatingPtr_Storage@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZP6APEAX_K@Z$1?CoTaskMemAlloc@@YAPEAX1@Z@@@@6B@; const CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>::`vftable'
0x1800253ce  mov     [rsp+878h+var_658], rax
0x1800253d6  xorps   xmm0, xmm0
0x1800253d9  movups  [rsp+878h+var_6B0], xmm0
0x1800253e1  movups  [rsp+878h+var_6A0], xmm0
0x1800253e9  mov     [rsp+878h+var_638], rbx
0x1800253f1  mov     [rsp+878h+var_610], bx
0x1800253f9  mov     [rsp+878h+var_60C], rbx
0x180025401  mov     [rsp+878h+var_600], rbx
0x180025409  mov     [rsp+878h+var_5F8], rbx
0x180025411  mov     [rsp+878h+var_5F0], ebx
0x180025418  mov     [rsp+878h+var_5E8], rbx
0x180025420  mov     [rsp+878h+var_5E0], bx
0x180025428  mov     [rsp+878h+var_5D0], rbx
0x180025430  mov     [rsp+878h+var_5D8], rax
0x180025438  movups  [rsp+878h+var_630], xmm0
0x180025440  movups  [rsp+878h+var_620], xmm0
0x180025448  xor     edx, edx; Val
0x18002544a  mov     r8d, 208h; Size
0x180025450  lea     rcx, [rsp+878h+var_248]; void *
0x180025458  call    memset_0
0x18002545d  mov     qword ptr [rsp+878h+var_508.m_SnapshotId.Data1], rsi
0x180025465  mov     qword ptr [rsp+878h+var_508.m_SnapshotId.Data4], r14
0x18002546d  mov     qword ptr [rsp+878h+var_508.m_SnapshotSetId.Data1], r15
0x180025475  mov     dword ptr [rsp+878h+var_508.m_SnapshotSetId.Data4], 1B1h
0x180025480  mov     dword ptr [rsp+878h+var_508.m_SnapshotSetId.Data4+4], edi
0x180025487  mov     [rsp+878h+var_508.m_lSnapshotsCount], 0FFh
0x180025492  mov     [rsp+878h+var_468], 1000000h
0x18002549d  mov     r8d, r13d; Size
0x1800254a0  xor     edx, edx; Val
0x1800254a2  lea     rcx, [rsp+878h+var_508.m_pwszSnapshotDeviceObject]; void *
0x1800254aa  call    memset_0
0x1800254af  mov     r9, [rsp+878h+var_818]
0x1800254b4  mov     r8d, 1392h
0x1800254ba  lea     rdx, [rsp+878h+var_508]
0x1800254c2  lea     rcx, [rsp+878h+var_738]
0x1800254ca  call    ?AddContext@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@IPEBG@Z; CVssFunctionTracer::AddContext(CVssDebugInfo,uint,ushort const *)
0x1800254cf  mov     [rsp+878h+var_838], 80h
0x1800254d7  mov     dword ptr [rsp+878h+var_848], ebx
0x1800254db  mov     dword ptr [rsp+878h+var_850], edi
0x1800254df  mov     byte ptr [rsp+878h+var_858], 1
0x1800254e4  mov     r9b, 1
0x1800254e7  mov     r8, [rsp+878h+var_818]
0x1800254ec  lea     rdx, [rsp+878h+var_738]
0x1800254f4  lea     rcx, [rsp+878h+var_6B8]
0x1800254fc  call    ?Open@CVssIOCTLChannel@@QEAAJAEAVCVssFunctionTracer@@PEBG_N2W4_VSS_ICHANNEL_LOGGING@@KKK@Z; CVssIOCTLChannel::Open(CVssFunctionTracer &,ushort const *,bool,bool,_VSS_ICHANNEL_LOGGING,ulong,ulong,ulong)
0x180025501  mov     [rsp+878h+var_820], ebx
0x180025505  cmp     [rsp+878h+var_824], 0FFFFFFFFh
0x18002550a  jz      loc_1800255B6
0x180025510  lea     rcx, [rsp+878h+var_6B8]; this
0x180025518  call    ?GetTimewarpSnapshotsCount@CVsSoftwareProvider@@CAKAEAVCVssIOCTLChannel@@@Z; CVsSoftwareProvider::GetTimewarpSnapshotsCount(CVssIOCTLChannel &)
0x18002551d  mov     [rsp+878h+var_808], eax
0x180025521  mov     ecx, eax
0x180025523  sub     ecx, [rsp+878h+var_824]
0x180025527  cmp     [rsp+878h+var_824], eax
0x18002552b  sbb     eax, eax
0x18002552d  and     eax, ecx
0x18002552f  mov     [rsp+878h+var_820], eax
0x180025533  mov     qword ptr [rsp+878h+var_508.m_SnapshotId.Data1], rsi
0x18002553b  mov     qword ptr [rsp+878h+var_508.m_SnapshotId.Data4], r14
0x180025543  mov     qword ptr [rsp+878h+var_508.m_SnapshotSetId.Data1], r15
0x18002554b  mov     dword ptr [rsp+878h+var_508.m_SnapshotSetId.Data4], 1C2h
0x180025556  mov     dword ptr [rsp+878h+var_508.m_SnapshotSetId.Data4+4], edi
0x18002555d  mov     [rsp+878h+var_508.m_lSnapshotsCount], 0FFh
0x180025568  mov     [rsp+878h+var_468], 1000000h
0x180025573  mov     r8d, r13d; Size
0x180025576  xor     edx, edx; Val
0x180025578  lea     rcx, [rsp+878h+var_508.m_pwszSnapshotDeviceObject]; void *
0x180025580  call    memset_0
0x180025585  mov     eax, [rsp+878h+var_824]
0x180025589  mov     dword ptr [rsp+878h+var_850], eax
0x18002558d  mov     eax, [rsp+878h+var_808]
0x180025591  mov     dword ptr [rsp+878h+var_858], eax
0x180025595  mov     r9d, [rsp+878h+var_820]
0x18002559a  lea     r8, aTimewarpSnapsh; "Timewarp snapshots to be deleted: %lu f"...
0x1800255a1  lea     rdx, [rsp+878h+var_508]
0x1800255a9  lea     rcx, [rsp+878h+var_738]
0x1800255b1  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x1800255b6  mov     [rsp+878h+var_810], rbx
0x1800255bb  mov     dword ptr [rsp+878h+var_68C], ebx
0x1800255c2  mov     dword ptr [rsp+878h+var_678], ebx
0x1800255c9  mov     [rsp+878h+var_848], rbx
0x1800255ce  mov     byte ptr [rsp+878h+var_850], bl
0x1800255d2  mov     dword ptr [rsp+878h+var_858], edi
0x1800255d6  mov     r9b, 1
0x1800255d9  mov     r8d, 530018h
0x1800255df  lea     rdx, [rsp+878h+var_738]
0x1800255e7  lea     rcx, [rsp+878h+var_6B8]
0x1800255ef  call    ?Call@CVssIOCTLChannel@@QEAAJAEAVCVssFunctionTracer@@K_NW4_VSS_ICHANNEL_LOGGING@@1PEAX@Z; CVssIOCTLChannel::Call(CVssFunctionTracer &,ulong,bool,_VSS_ICHANNEL_LOGGING,bool,void *)
0x1800255f4  mov     [rsp+878h+var_808], ebx
0x1800255f8  lea     r8, [rsp+878h+var_808]
0x1800255fd  lea     rdx, [rsp+878h+var_738]
0x180025605  lea     rcx, [rsp+878h+var_6B8]
0x18002560d  call    ??$Unpack@K@CVssIOCTLChannel@@QEAAXAEAVCVssFunctionTracer@@PEAKK_N@Z; CVssIOCTLChannel::Unpack<ulong>(CVssFunctionTracer &,ulong *,ulong,bool)
0x180025612  mov     [rsp+878h+var_7F0], rbx
0x18002561a  lea     rax, ??_7?$CVssAuto@PEAGV?$CVssAllocatingPtr_Storage@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZP6APEAX_K@Z$1?CoTaskMemAlloc@@YAPEAX1@Z@@@@6B@; const CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>::`vftable'
0x180025621  mov     [rsp+878h+var_7F8], rax
0x180025629  lea     rcx, [rsp+878h+var_7F8]
0x180025631  call    ?ResetAndGetRef@?$CVssAuto@PEAGV?$CVssAllocatingPtr_Storage@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZP6APEAX_K@Z$1?CoTaskMemAlloc@@YAPEAX1@Z@@@@QEAAAEAPEAGXZ; CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>::ResetAndGetRef(void)
0x180025636  mov     r8, rax; unsigned __int16 **
0x180025639  lea     rdx, [rsp+878h+var_738]; struct CVssFunctionTracer *
0x180025641  lea     rcx, [rsp+878h+var_6B8]; this
0x180025649  call    ?UnpackZeroString@CVssIOCTLChannel@@QEAAPEBGAEAVCVssFunctionTracer@@AEAPEAG@Z; CVssIOCTLChannel::UnpackZeroString(CVssFunctionTracer &,ushort * &)
0x18002564e  test    rax, rax
0x180025651  jz      loc_18002573A
0x180025657  mov     rax, [rsp+878h+var_7F0]
0x18002565f  mov     [rsp+878h+var_858], rax; unsigned __int16 *
0x180025664  lea     r9, aGlobalroot_3; "\\\\?\\GLOBALROOT"
0x18002566b  lea     rdx, [rsp+878h+var_458]; unsigned __int16 *
0x180025673  lea     rcx, [rsp+878h+var_738]; struct CVssFunctionTracer *
0x18002567b  call    ?VssConcatenate@@YAXAEAVCVssFunctionTracer@@PEAG_KPEBG3@Z; VssConcatenate(CVssFunctionTracer &,ushort *,unsigned __int64,ushort const *,ushort const *)
0x180025680  mov     [rsp+878h+var_838], 80h
0x180025688  mov     dword ptr [rsp+878h+var_848], ebx
0x18002568c  mov     dword ptr [rsp+878h+var_850], edi
0x180025690  mov     byte ptr [rsp+878h+var_858], 1
0x180025695  xor     r9d, r9d
0x180025698  lea     r8, [rsp+878h+var_458]
0x1800256a0  lea     rdx, [rsp+878h+var_738]
0x1800256a8  lea     rcx, [rsp+878h+var_638]
0x1800256b0  call    ?Open@CVssIOCTLChannel@@QEAAJAEAVCVssFunctionTracer@@PEBG_N2W4_VSS_ICHANNEL_LOGGING@@KKK@Z; CVssIOCTLChannel::Open(CVssFunctionTracer &,ushort const *,bool,bool,_VSS_ICHANNEL_LOGGING,ulong,ulong,ulong)
0x1800256b5  mov     [rsp+878h+var_730], eax
0x1800256bc  test    eax, eax
0x1800256be  jns     loc_18002576B
0x1800256c4  mov     [rsp+878h+var_7E8], rsi
0x1800256cc  mov     [rsp+878h+var_7E0], r14
0x1800256d4  mov     [rsp+878h+var_7D8], r15
0x1800256dc  mov     [rsp+878h+var_7D0], 1E6h
0x1800256e7  mov     [rsp+878h+var_7CC], edi
0x1800256ee  mov     [rsp+878h+var_7C8], 0FFh
0x1800256f9  mov     [rsp+878h+var_748], 1000000h
0x180025704  mov     r8, r13; Size
0x180025707  xor     edx, edx; Val
0x180025709  lea     rcx, [rsp+878h+var_7C0]; void *
0x180025711  call    memset_0
0x180025716  lea     r8, aWarningSnapsho_0; "Warning: snapshot %s cannot be opened"
0x18002571d  lea     r9, [rsp+878h+var_458]
0x180025725  lea     rdx, [rsp+878h+var_7E8]
0x18002572d  lea     rcx, [rsp+878h+var_738]
0x180025735  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x18002573a  cmp     [rsp+878h+var_828], bl
0x18002573e  jz      short loc_180025758
0x180025740  cmp     [rsp+878h+var_248], bx
0x180025748  jz      short loc_180025758
0x18002574a  lea     rcx, [rsp+878h+var_248]; unsigned __int16 *
0x180025752  call    ?CheckSetSnapshotReadOnly@CVsSoftwareProvider@@CAXPEAG@Z; CVsSoftwareProvider::CheckSetSnapshotReadOnly(ushort *)
0x180025757  nop
0x180025758  lea     rcx, [rsp+878h+var_7F8]
0x180025760  call    ??1?$CVssAuto@PEAGV?$CVssAllocatingPtr_Storage@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZP6APEAX_K@Z$1?CoTaskMemAlloc@@YAPEAX1@Z@@@@UEAA@XZ; CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>::~CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>(void)
0x180025765  nop
0x180025766  jmp     loc_180025B58
0x18002576b  mov     [rsp+878h+var_848], rbx
0x180025770  mov     byte ptr [rsp+878h+var_850], bl
0x180025774  mov     dword ptr [rsp+878h+var_858], ebx
0x180025778  xor     r9d, r9d
0x18002577b  mov     r8d, 53019Ch
0x180025781  lea     rdx, [rsp+878h+var_738]
0x180025789  lea     rcx, [rsp+878h+var_638]
0x180025791  call    ?Call@CVssIOCTLChannel@@QEAAJAEAVCVssFunctionTracer@@K_NW4_VSS_ICHANNEL_LOGGING@@1PEAX@Z; CVssIOCTLChannel::Call(CVssFunctionTracer &,ulong,bool,_VSS_ICHANNEL_LOGGING,bool,void *)
0x180025796  mov     [rsp+878h+var_730], eax
0x18002579d  test    eax, eax
0x18002579f  jns     short loc_1800257FF
0x1800257a1  mov     [rsp+878h+var_7E8], rsi
0x1800257a9  mov     [rsp+878h+var_7E0], r14
0x1800257b1  mov     [rsp+878h+var_7D8], r15
0x1800257b9  mov     [rsp+878h+var_7D0], 1EEh
0x1800257c4  mov     [rsp+878h+var_7CC], edi
0x1800257cb  mov     [rsp+878h+var_7C8], 0FFh
0x1800257d6  mov     [rsp+878h+var_748], 1000000h
0x1800257e1  mov     r8, r13; Size
0x1800257e4  xor     edx, edx; Val
0x1800257e6  lea     rcx, [rsp+878h+var_7C0]; void *
0x1800257ee  call    memset_0
0x1800257f3  lea     r8, aWarningSnapsho; "Warning: snapshot %s cannot be queried "...
0x1800257fa  jmp     loc_18002571D
0x1800257ff  mov     [rsp+878h+var_508.m_SnapshotId.Data1], ebx
0x180025806  xor     edx, edx; Val
0x180025808  lea     r8d, [rdx+7Ch]; Size
0x18002580c  lea     rcx, [rsp+878h+var_508.m_SnapshotId.Data2]; void *
0x180025814  call    memset_0
0x180025819  mov     [rsp+878h+var_824], ebx
0x18002581d  mov     [rsp+878h+var_827], bl
0x180025821  lea     rax, ??_7?$CVssAuto@PEAU_VSS_SNAPSHOT_PROP@@V?$CVssAutoGenericValue_Storage@PEAU_VSS_SNAPSHOT_PROP@@$0A@P6AXPEAU1@@Z$1?VssFreeSnapshotProperties@@YAX0@ZP6AAEAPEAU1@AEAPEAU1@@Z$1?Identity@?$DTyper@PEAU_VSS_SNAPSHOT_PROP@@@@SAAEAPEAU1@1@Z@@@@6B@; const CVssAuto<_VSS_SNAPSHOT_PROP *,CVssAutoGenericValue_Storage<_VSS_SNAPSHOT_PROP *,0,void (*)(_VSS_SNAPSHOT_PROP *),&VssFreeSnapshotProperties(_VSS_SNAPSHOT_PROP *),_VSS_SNAPSHOT_PROP * & (*)(_VSS_SNAPSHOT_PROP * &),&DTyper<_VSS_SNAPSHOT_PROP *>::Identity(_VSS_SNAPSHOT_PROP * &)>>::`vftable'
0x180025828  mov     [rsp+878h+var_648], rax
0x180025830  lea     rax, [rsp+878h+var_508]
0x180025838  mov     [rsp+878h+var_640], rax
0x180025840  mov     byte ptr [rsp+878h+var_858], bl; int
0x180025844  lea     r9, [rsp+878h+var_827]; bool *
0x180025849  lea     r8, [rsp+878h+var_824]; int *
0x18002584e  lea     rdx, [rsp+878h+var_508]; struct _VSS_SNAPSHOT_PROP *
0x180025856  lea     rcx, [rsp+878h+var_638]; struct CVssIOCTLChannel *
0x18002585e  call    ?LoadStructure@CVssQueuedSnapshot@@SA_NAEAVCVssIOCTLChannel@@PEAU_VSS_SNAPSHOT_PROP@@PEAJPEA_N_N@Z; CVssQueuedSnapshot::LoadStructure(CVssIOCTLChannel &,_VSS_SNAPSHOT_PROP *,long *,bool *,bool)
0x180025863  test    al, al
0x180025865  jz      loc_180025989
0x18002586b  cmp     [rsp+878h+var_827], bl
0x18002586f  jnz     loc_180025966
0x180025875  cmp     [rsp+878h+var_828], bl
0x180025879  jz      loc_18002599B
0x18002587f  cmp     [rsp+878h+var_508.m_eStatus], 0Ch
0x180025887  jz      short loc_1800258E4
0x180025889  mov     [rsp+878h+var_7E8], rsi
0x180025891  mov     [rsp+878h+var_7E0], r14
0x180025899  mov     [rsp+878h+var_7D8], r15
0x1800258a1  mov     [rsp+878h+var_7D0], 205h
0x1800258ac  mov     [rsp+878h+var_7CC], edi
0x1800258b3  mov     [rsp+878h+var_7C8], 0FFh
0x1800258be  mov     [rsp+878h+var_748], 1000000h
0x1800258c9  mov     r8, r13; Size
0x1800258cc  xor     edx, edx; Val
0x1800258ce  lea     rcx, [rsp+878h+var_7C0]; void *
0x1800258d6  call    memset_0
0x1800258db  lea     r8, aDeletingIncomp; "Deleting incomplete snapshot%s"
0x1800258e2  jmp     short loc_180025949
0x1800258e4  mov     eax, [rsp+878h+var_824]
0x1800258e8  test    al, 8
0x1800258ea  jnz     loc_18002599F
0x1800258f0  mov     [rsp+878h+var_7E8], rsi
0x1800258f8  mov     [rsp+878h+var_7E0], r14
0x180025900  mov     [rsp+878h+var_7D8], r15
0x180025908  mov     [rsp+878h+var_7D0], 20Dh
0x180025913  mov     [rsp+878h+var_7CC], edi
0x18002591a  mov     [rsp+878h+var_7C8], 0FFh
0x180025925  mov     [rsp+878h+var_748], 1000000h
0x180025930  mov     r8, r13; Size
0x180025933  xor     edx, edx; Val
0x180025935  lea     rcx, [rsp+878h+var_7C0]; void *
0x18002593d  call    memset_0
0x180025942  lea     r8, aDeletingAutore; "Deleting AutoRelease snapshot %s"
0x180025949  lea     r9, [rsp+878h+var_458]
0x180025951  lea     rdx, [rsp+878h+var_7E8]
0x180025959  lea     rcx, [rsp+878h+var_738]
0x180025961  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
  ... truncated ...
```
