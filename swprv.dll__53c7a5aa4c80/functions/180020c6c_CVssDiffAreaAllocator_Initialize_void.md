# CVssDiffAreaAllocator::Initialize(void)

- ea: `0x180020c6c`
- end: `0x180021314`
- name: `?Initialize@CVssDiffAreaAllocator@@AEAAXXZ`
- size: `1704`
- prototype: `void __fastcall(CVssDiffAreaAllocator *__hidden this)`
- caller_count: `1`
- callee_count: `27`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x18001f47c`

## callees

- `0x180001acc`
- `0x18000212c`
- `0x1800036c4`
- `0x180003718`
- `0x180004a78`
- `0x180011178`
- `0x180019334`
- `0x180019458`
- `0x18001d7f0`
- `0x18001d8dc`
- `0x18001d988`
- `0x18001dd84`
- `0x18001de8c`
- `0x18001e53c`
- `0x18001e6f8`
- `0x18001e90c`
- `0x18001f198`
- `0x18001f3dc`
- `0x180020c6c`
- `0x180023310`
- `0x180033a8c`
- `0x180033c2c`
- `0x180033c78`
- `0x180034038`
- `0x1800358f4`
- `0x18003649c`
- `0x18004b010`

## string_xrefs

- `0x180020f9f`: `Volume %s appears as invalid or dismounted`
- `0x1800212be`: `Volume %s appears as invalid or dismounted`

## pseudocode

```c
void __fastcall CVssDiffAreaAllocator::Initialize(CVssDiffAreaAllocator *this)
{
  struct CVssQueuedSnapshot *NextBySnapshotSet; // rax
  CVssQueuedSnapshot *v3; // rbx
  struct _VSS_SNAPSHOT_PROP *SnapshotProperties; // rsi
  unsigned __int16 *v5; // rbx
  char VolumeInformationFlags; // al
  bool v7; // dl
  bool v8; // dl
  __int64 v9; // rax
  CVssDebugInfo *v10; // rax
  struct CVssQueuedSnapshot *v11; // rax
  CVssQueuedSnapshot *v12; // rbx
  struct _VSS_SNAPSHOT_PROP *v13; // rsi
  unsigned __int16 *v14; // rsi
  char v15; // al
  CVssDiffAreaAssociation *v16; // rax
  CVssDiffAreaAssociation *v17; // rbx
  unsigned int v18; // edx
  CVssDebugInfo *v19; // rax
  void **v20; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR lpDirectoryName; // [rsp+38h] [rbp-C8h]
  struct _RTL_CRITICAL_SECTION v22; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v23[120]; // [rsp+68h] [rbp-98h] BYREF
  int v24; // [rsp+E0h] [rbp-20h]
  void **v25; // [rsp+F0h] [rbp-10h] BYREF
  void *v26; // [rsp+F8h] [rbp-8h]
  void **v27; // [rsp+100h] [rbp+0h] BYREF
  LPCWSTR lpszVolumeMountPoint; // [rsp+108h] [rbp+8h]
  void **v29; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 *v30; // [rsp+118h] [rbp+18h]
  void **v31; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 *v32; // [rsp+128h] [rbp+28h]
  struct _GUID v33; // [rsp+130h] [rbp+30h] BYREF
  LPVOID v34[14]; // [rsp+140h] [rbp+40h] BYREF
  struct _RTL_CRITICAL_SECTION v35[5]; // [rsp+1B0h] [rbp+B0h] BYREF
  struct CVssQueuedSnapshot *v36; // [rsp+2A0h] [rbp+1A0h] BYREF
  CVssDiffAreaAssociation *v37; // [rsp+2A8h] [rbp+1A8h] BYREF
  CVssDiffAreaAssociation *v38; // [rsp+2B0h] [rbp+1B0h]

  v22.DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)L"base\\stor\\vss\\modules\\softprv\\src\\alloc.cxx";
  *(_QWORD *)&v22.LockCount = L"CVssDiffAreaAllocator::Initialize";
  v22.OwningThread = (HANDLE)L"SPRALLOC";
  v22.LockSemaphore = (HANDLE)0x200000126LL;
  LODWORD(v22.SpinCount) = 255;
  v24 = 0x1000000;
  memset_0(v23, 0, sizeof(v23));
  CVssFunctionTracer::CVssFunctionTracer((__int64)v34, (__int64)&v22, 0);
  v25 = &CVssQueuedSnapshot::m_list;
  v26 = CVssQueuedSnapshot::m_list;
  while ( 1 )
  {
    v33 = *(struct _GUID *)((char *)this + 4);
    NextBySnapshotSet = CVssSnapIterator::GetNextBySnapshotSet((CVssSnapIterator *)&v25, &v33);
    v3 = NextBySnapshotSet;
    v36 = NextBySnapshotSet;
    if ( NextBySnapshotSet )
      (*(void (__fastcall **)(struct CVssQueuedSnapshot *))(*(_QWORD *)NextBySnapshotSet + 8LL))(NextBySnapshotSet);
    if ( !v3 )
      break;
    SnapshotProperties = CVssQueuedSnapshot::GetSnapshotProperties(v3);
    if ( CVssQueuedSnapshot::GetSnapshotProperties(v3)->m_eStatus == VSS_SS_PREPARING )
    {
      v32 = 0;
      v31 = &CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::`vftable';
      CVssAutoString<CVssAutoCOMPtr<unsigned short *>>::CopyFrom(
        (__int64)&v31,
        SnapshotProperties->m_pwszOriginalVolumeName);
      v30 = 0;
      v29 = &CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::`vftable';
      v5 = v32;
      VolumeInformationFlags = CVsSoftwareProvider::GetVolumeInformationFlags(v32, -1, (__int64)&v29, 1, 31);
      if ( (VolumeInformationFlags & 1) == 0 )
      {
        v22.DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)L"base\\stor\\vss\\modules\\softprv\\src\\alloc.cxx";
        *(_QWORD *)&v22.LockCount = L"CVssDiffAreaAllocator::Initialize";
        v22.OwningThread = (HANDLE)L"SPRALLOC";
        v22.LockSemaphore = (HANDLE)0x20000014BLL;
        LODWORD(v22.SpinCount) = 255;
        v24 = 0x1000000;
        memset_0(v23, 0, sizeof(v23));
        v10 = CVssDebugInfo::operator<<((struct CVssDebugInfo *)&v22, (CVssDebugInfo *)v35, v5);
        CVssFunctionTracer::LogError(v34, 12308, v10);
        CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v22);
        v22.DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)L"base\\stor\\vss\\modules\\softprv\\src\\alloc.cxx";
        *(_QWORD *)&v22.LockCount = L"CVssDiffAreaAllocator::Initialize";
        v22.OwningThread = (HANDLE)L"SPRALLOC";
        v22.LockSemaphore = (HANDLE)0x20000014CLL;
        LODWORD(v22.SpinCount) = 255;
        v24 = 0x1000000;
        memset_0(v23, 0, sizeof(v23));
        CVssFunctionTracer::Throw(v34, &v22, 2147754760LL, L"Volume %s appears as invalid or dismounted", v5);
      }
      if ( (VolumeInformationFlags & 4) != 0 )
      {
        CVssDiffArea::CVssDiffArea((CVssDiffArea *)&v22, v7);
        lpDirectoryName = 0;
        v20 = &CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::`vftable';
        CVssDiffArea::InitializeForVolume((CVssDiffArea *)&v22, v5, 0);
        CVssDiffArea::GetDiffArea((CVssIOCTLChannel *)&v22, (__int64)&v20);
        if ( !lpDirectoryName )
          goto LABEL_14;
        v9 = -1;
        do
          ++v9;
        while ( lpDirectoryName[v9] );
        if ( v9 )
        {
          if ( !CVssDiffArea::IsExplicit((CVssDiffArea *)&v22) )
            CVssDiffAreaAllocator::VerifyDiffAreaMaxSizeOnVolume(this, lpDirectoryName, (struct CVssDiffArea *)&v22);
        }
        else
        {
LABEL_14:
          lpszVolumeMountPoint = 0;
          v27 = &CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::`vftable';
          CVssDiffArea::CVssDiffArea((CVssDiffArea *)v35, v8);
          CVssDiffArea::InitializeForSnapshot((CVssDiffArea *)v35, v30, 1, 1);
          CVssDiffArea::GetDiffArea((CVssIOCTLChannel *)v35, (__int64)&v27);
          CVssDiffArea::Clear((CVssDiffArea *)&v22);
          CVssDiffArea::AddVolume((CVssDiffArea *)&v22, lpszVolumeMountPoint);
          CVssDiffArea::~CVssDiffArea(v35);
          CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::~CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>(&v27);
        }
        CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::~CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>(&v20);
        CVssDiffArea::~CVssDiffArea(&v22);
      }
      CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::~CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>(&v29);
      CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::~CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>(&v31);
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v36);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v36);
  v25 = &CVssQueuedSnapshot::m_list;
  v26 = CVssQueuedSnapshot::m_list;
  while ( 1 )
  {
    v33 = *(struct _GUID *)((char *)this + 4);
    v11 = CVssSnapIterator::GetNextBySnapshotSet((CVssSnapIterator *)&v25, &v33);
    v12 = v11;
    v36 = v11;
    if ( v11 )
      (*(void (__fastcall **)(struct CVssQueuedSnapshot *))(*(_QWORD *)v11 + 8LL))(v11);
    if ( !v12 )
      break;
    v13 = CVssQueuedSnapshot::GetSnapshotProperties(v12);
    if ( CVssQueuedSnapshot::GetSnapshotProperties(v12)->m_eStatus == VSS_SS_PREPARING )
    {
      lpDirectoryName = 0;
      v20 = &CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::`vftable';
      CVssAutoString<CVssAutoCOMPtr<unsigned short *>>::CopyFrom((__int64)&v20, v13->m_pwszOriginalVolumeName);
      v14 = (unsigned __int16 *)lpDirectoryName;
      v15 = CVsSoftwareProvider::GetVolumeInformationFlags(lpDirectoryName, -1, 0, 1, 31);
      if ( (v15 & 1) == 0 )
      {
        v22.DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)L"base\\stor\\vss\\modules\\softprv\\src\\alloc.cxx";
        *(_QWORD *)&v22.LockCount = L"CVssDiffAreaAllocator::Initialize";
        v22.OwningThread = (HANDLE)L"SPRALLOC";
        v22.LockSemaphore = (HANDLE)0x200000192LL;
        LODWORD(v22.SpinCount) = 255;
        v24 = 0x1000000;
        memset_0(v23, 0, sizeof(v23));
        v19 = CVssDebugInfo::operator<<((struct CVssDebugInfo *)&v22, (CVssDebugInfo *)v35, v14);
        CVssFunctionTracer::LogError(v34, 12308, v19);
        CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v22);
        v22.DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)L"base\\stor\\vss\\modules\\softprv\\src\\alloc.cxx";
        *(_QWORD *)&v22.LockCount = L"CVssDiffAreaAllocator::Initialize";
        v22.OwningThread = (HANDLE)L"SPRALLOC";
        v22.LockSemaphore = (HANDLE)0x200000193LL;
        LODWORD(v22.SpinCount) = 255;
        v24 = 0x1000000;
        memset_0(v23, 0, sizeof(v23));
        CVssFunctionTracer::Throw(v34, &v22, 2147754760LL, L"Volume %s appears as invalid or dismounted", v14);
      }
      if ( (v15 & 4) == 0 )
      {
        v16 = (CVssDiffAreaAssociation *)operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
        v17 = v16;
        v38 = v16;
        if ( v16 )
        {
          *((_QWORD *)v16 + 1) = 0;
          *(_QWORD *)v16 = &CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::`vftable';
          *((_QWORD *)v16 + 3) = 0;
          *((_QWORD *)v16 + 2) = &CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::`vftable';
          *((_QWORD *)v16 + 4) = -1;
          *((_BYTE *)v16 + 40) = 0;
          CVssAutoString<CVssAutoCOMPtr<unsigned short *>>::CopyFrom((__int64)v16, v14);
        }
        else
        {
          v17 = 0;
        }
        v37 = v17;
        if ( !v17 )
        {
          v22.DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)L"base\\stor\\vss\\modules\\softprv\\src\\alloc.cxx";
          *(_QWORD *)&v22.LockCount = L"CVssDiffAreaAllocator::Initialize";
          v22.OwningThread = (HANDLE)L"SPRALLOC";
          v22.LockSemaphore = (HANDLE)0x2000001A1LL;
          LODWORD(v22.SpinCount) = 255;
          v24 = 0x1000000;
          memset_0(v23, 0, sizeof(v23));
          CVssFunctionTracer::Throw(v34, &v22, 2147942414LL, L"Memory allocation error");
        }
        if ( !(unsigned int)CVssSimpleMap<unsigned short *,CVssDiffAreaCandidate *>::Add((char *)this + 24, v14, v17) )
        {
          v22.DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)L"base\\stor\\vss\\modules\\softprv\\src\\alloc.cxx";
          *(_QWORD *)&v22.LockCount = L"CVssDiffAreaAllocator::Initialize";
          v22.OwningThread = (HANDLE)L"SPRALLOC";
          v22.LockSemaphore = (HANDLE)0x2000001A5LL;
          LODWORD(v22.SpinCount) = 255;
          v24 = 0x1000000;
          memset_0(v23, 0, sizeof(v23));
          CVssFunctionTracer::Throw(v34, &v22, 2147942414LL, L"Memory allocation error");
        }
        lpDirectoryName = 0;
        v37 = 0;
        std::unique_ptr<CVssDiffAreaAssociation>::~unique_ptr<CVssDiffAreaAssociation>(&v37, v18);
      }
      CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::~CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>(&v20);
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v36);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v36);
  if ( !*((_DWORD *)this + 10) )
    *((_BYTE *)this + 1) = 1;
  CVssFunctionTracer::~CVssFunctionTracer(v34);
}

```

## disassembly

```asm
0x180020c6c  mov     [rsp-8+arg_18], rbx
0x180020c71  push    rbp
0x180020c72  push    rsi
0x180020c73  push    rdi
0x180020c74  push    r12
0x180020c76  push    r13
0x180020c78  push    r14
0x180020c7a  push    r15
0x180020c7c  lea     rbp, [rsp-160h]
0x180020c84  sub     rsp, 260h
0x180020c8b  mov     rdi, rcx
0x180020c8e  lea     rax, aBaseStorVssMod_11; "base\\stor\\vss\\modules\\softprv\\src"...
0x180020c95  mov     [rsp+290h+var_250], rax
0x180020c9a  lea     rax, aCvssdiffareaal_12; "CVssDiffAreaAllocator::Initialize"
0x180020ca1  mov     [rsp+290h+var_248], rax
0x180020ca6  lea     rax, aSpralloc; "SPRALLOC"
0x180020cad  mov     [rsp+290h+var_240], rax
0x180020cb2  mov     [rsp+290h+var_238], 126h
0x180020cba  mov     [rsp+290h+var_234], 2
0x180020cc2  mov     [rsp+290h+var_230], 0FFh
0x180020cca  xor     r14d, r14d
0x180020ccd  mov     [rbp+190h+var_1B0], 1000000h
0x180020cd4  xor     edx, edx; Val
0x180020cd6  lea     r15d, [r14+1]
0x180020cda  lea     r8d, [r14+78h]; Size
0x180020cde  lea     rcx, [rsp+290h+var_228]; void *
0x180020ce3  call    memset_0
0x180020ce8  xor     r8d, r8d
0x180020ceb  lea     rdx, [rsp+290h+var_250]
0x180020cf0  lea     rcx, [rbp+190h+var_150]
0x180020cf4  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x180020cf9  nop
0x180020cfa  lea     rsi, ?m_list@CVssQueuedSnapshot@@0V?$CVssDLList@PEAVCVssQueuedSnapshot@@@@A; CVssDLList<CVssQueuedSnapshot *> CVssQueuedSnapshot::m_list
0x180020d01  mov     [rbp+190h+var_1A0], rsi
0x180020d05  mov     rax, cs:?m_list@CVssQueuedSnapshot@@0V?$CVssDLList@PEAVCVssQueuedSnapshot@@@@A; CVssDLList<CVssQueuedSnapshot *> CVssQueuedSnapshot::m_list
0x180020d0c  mov     [rbp+190h+var_198], rax
0x180020d10  lea     r12, ??_7?$CVssAuto@PEAGV?$CVssAllocatingPtr_Storage@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZP6APEAX_K@Z$1?CoTaskMemAlloc@@YAPEAX1@Z@@@@6B@; const CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>::`vftable'
0x180020d17  or      r13, 0FFFFFFFFFFFFFFFFh
0x180020d1b  movups  xmm0, xmmword ptr [rdi+4]
0x180020d1f  movdqu  xmmword ptr [rbp+190h+var_160.Data1], xmm0
0x180020d24  lea     rdx, [rbp+190h+var_160]; struct _GUID
0x180020d28  lea     rcx, [rbp+190h+var_1A0]; this
0x180020d2c  call    ?GetNextBySnapshotSet@CVssSnapIterator@@QEAAPEAVCVssQueuedSnapshot@@U_GUID@@@Z; CVssSnapIterator::GetNextBySnapshotSet(_GUID)
0x180020d31  mov     rbx, rax
0x180020d34  mov     [rbp+190h+arg_0], rax
0x180020d3b  test    rax, rax
0x180020d3e  jz      short loc_180020D50
0x180020d40  mov     rcx, [rax]
0x180020d43  mov     rax, [rcx+8]
0x180020d47  mov     rcx, rbx
0x180020d4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d4f  nop
0x180020d50  test    rbx, rbx
0x180020d53  jz      loc_180020FBB
0x180020d59  mov     rcx, rbx; this
0x180020d5c  call    ?GetSnapshotProperties@CVssQueuedSnapshot@@QEAAPEAU_VSS_SNAPSHOT_PROP@@XZ; CVssQueuedSnapshot::GetSnapshotProperties(void)
0x180020d61  mov     rsi, rax
0x180020d64  mov     rcx, rbx; this
0x180020d67  call    ?GetSnapshotProperties@CVssQueuedSnapshot@@QEAAPEAU_VSS_SNAPSHOT_PROP@@XZ; CVssQueuedSnapshot::GetSnapshotProperties(void)
0x180020d6c  cmp     [rax+78h], r15d
0x180020d70  jnz     loc_180020EC9
0x180020d76  mov     [rbp+190h+var_168], r14
0x180020d7a  mov     [rbp+190h+var_170], r12
0x180020d7e  mov     rdx, [rsi+30h]
0x180020d82  lea     rcx, [rbp+190h+var_170]
0x180020d86  call    ?CopyFrom@?$CVssAutoString@V?$CVssAutoCOMPtr@PEAG@@@@QEAAXPEBG@Z; CVssAutoString<CVssAutoCOMPtr<ushort *>>::CopyFrom(ushort const *)
0x180020d8b  mov     [rbp+190h+var_178], r14
0x180020d8f  mov     [rbp+190h+var_180], r12
0x180020d93  mov     rbx, [rbp+190h+var_168]
0x180020d97  mov     dword ptr [rsp+290h+var_270], 1Fh
0x180020d9f  mov     r9d, r15d
0x180020da2  lea     r8, [rbp+190h+var_180]
0x180020da6  mov     edx, r13d
0x180020da9  mov     rcx, rbx
0x180020dac  call    ?GetVolumeInformationFlags@CVsSoftwareProvider@@SAJPEBGJPEAV?$CVssAutoString@V?$CVssAutoCOMPtr@PEAG@@@@HJ@Z; CVsSoftwareProvider::GetVolumeInformationFlags(ushort const *,long,CVssAutoString<CVssAutoCOMPtr<ushort *>> *,int,long)
0x180020db1  test    r15b, al
0x180020db4  jz      loc_180020EDA
0x180020dba  test    al, 4
0x180020dbc  jz      loc_180020EB5
0x180020dc2  lea     rcx, [rsp+290h+var_250]; this
0x180020dc7  call    ??0CVssDiffArea@@QEAA@XZ; CVssDiffArea::CVssDiffArea(void)
0x180020dcc  nop
0x180020dcd  mov     [rsp+290h+lpDirectoryName], r14
0x180020dd2  mov     [rsp+290h+var_260], r12
0x180020dd7  xor     r8d, r8d; bool
0x180020dda  mov     rdx, rbx; unsigned __int16 *
0x180020ddd  lea     rcx, [rsp+290h+var_250]; this
0x180020de2  call    ?InitializeForVolume@CVssDiffArea@@QEAAXPEBG_N@Z; CVssDiffArea::InitializeForVolume(ushort const *,bool)
0x180020de7  lea     rdx, [rsp+290h+var_260]
0x180020dec  lea     rcx, [rsp+290h+var_250]; this
0x180020df1  call    ?GetDiffArea@CVssDiffArea@@QEAAXAEAV?$CVssAutoString@V?$CVssAutoCOMPtr@PEAG@@@@@Z; CVssDiffArea::GetDiffArea(CVssAutoString<CVssAutoCOMPtr<ushort *>> &)
0x180020df6  mov     rcx, [rsp+290h+lpDirectoryName]
0x180020dfb  test    rcx, rcx
0x180020dfe  jz      short loc_180020E34
0x180020e00  mov     rax, r13
0x180020e03  inc     rax
0x180020e06  cmp     [rcx+rax*2], r14w
0x180020e0b  jnz     short loc_180020E03
0x180020e0d  test    rax, rax
0x180020e10  jz      short loc_180020E34
0x180020e12  lea     rcx, [rsp+290h+var_250]; this
0x180020e17  call    ?IsExplicit@CVssDiffArea@@QEAA_NXZ; CVssDiffArea::IsExplicit(void)
0x180020e1c  test    al, al
0x180020e1e  jnz     short loc_180020E9F
0x180020e20  lea     r8, [rsp+290h+var_250]; struct CVssDiffArea *
0x180020e25  mov     rdx, [rsp+290h+lpDirectoryName]; lpDirectoryName
0x180020e2a  mov     rcx, rdi; this
0x180020e2d  call    ?VerifyDiffAreaMaxSizeOnVolume@CVssDiffAreaAllocator@@AEAAXPEAGPEAVCVssDiffArea@@@Z; CVssDiffAreaAllocator::VerifyDiffAreaMaxSizeOnVolume(ushort *,CVssDiffArea *)
0x180020e32  jmp     short loc_180020E9F
0x180020e34  mov     [rbp+190h+lpszVolumeMountPoint], r14
0x180020e38  mov     [rbp+190h+var_190], r12
0x180020e3c  lea     rcx, [rbp+190h+var_E0]; this
0x180020e43  call    ??0CVssDiffArea@@QEAA@XZ; CVssDiffArea::CVssDiffArea(void)
0x180020e48  nop
0x180020e49  mov     r9b, r15b; bool
0x180020e4c  mov     r8b, r15b; bool
0x180020e4f  mov     rdx, [rbp+190h+var_178]; unsigned __int16 *
0x180020e53  lea     rcx, [rbp+190h+var_E0]; this
0x180020e5a  call    ?InitializeForSnapshot@CVssDiffArea@@QEAAXPEBG_N1@Z; CVssDiffArea::InitializeForSnapshot(ushort const *,bool,bool)
0x180020e5f  lea     rdx, [rbp+190h+var_190]
0x180020e63  lea     rcx, [rbp+190h+var_E0]; this
0x180020e6a  call    ?GetDiffArea@CVssDiffArea@@QEAAXAEAV?$CVssAutoString@V?$CVssAutoCOMPtr@PEAG@@@@@Z; CVssDiffArea::GetDiffArea(CVssAutoString<CVssAutoCOMPtr<ushort *>> &)
0x180020e6f  lea     rcx, [rsp+290h+var_250]; this
0x180020e74  call    ?Clear@CVssDiffArea@@QEAAXXZ; CVssDiffArea::Clear(void)
0x180020e79  mov     rdx, [rbp+190h+lpszVolumeMountPoint]; lpszVolumeMountPoint
0x180020e7d  lea     rcx, [rsp+290h+var_250]; this
0x180020e82  call    ?AddVolume@CVssDiffArea@@QEAAXPEAG@Z; CVssDiffArea::AddVolume(ushort *)
0x180020e87  nop
0x180020e88  lea     rcx, [rbp+190h+var_E0]; this
0x180020e8f  call    ??1CVssDiffArea@@QEAA@XZ; CVssDiffArea::~CVssDiffArea(void)
0x180020e94  nop
0x180020e95  lea     rcx, [rbp+190h+var_190]
0x180020e99  call    ??1?$CVssAuto@PEAGV?$CVssAllocatingPtr_Storage@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZP6APEAX_K@Z$1?CoTaskMemAlloc@@YAPEAX1@Z@@@@UEAA@XZ; CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>::~CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>(void)
0x180020e9e  nop
0x180020e9f  lea     rcx, [rsp+290h+var_260]
0x180020ea4  call    ??1?$CVssAuto@PEAGV?$CVssAllocatingPtr_Storage@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZP6APEAX_K@Z$1?CoTaskMemAlloc@@YAPEAX1@Z@@@@UEAA@XZ; CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>::~CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>(void)
0x180020ea9  nop
0x180020eaa  lea     rcx, [rsp+290h+var_250]; this
0x180020eaf  call    ??1CVssDiffArea@@QEAA@XZ; CVssDiffArea::~CVssDiffArea(void)
0x180020eb4  nop
0x180020eb5  lea     rcx, [rbp+190h+var_180]
0x180020eb9  call    ??1?$CVssAuto@PEAGV?$CVssAllocatingPtr_Storage@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZP6APEAX_K@Z$1?CoTaskMemAlloc@@YAPEAX1@Z@@@@UEAA@XZ; CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>::~CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>(void)
0x180020ebe  nop
0x180020ebf  lea     rcx, [rbp+190h+var_170]
0x180020ec3  call    ??1?$CVssAuto@PEAGV?$CVssAllocatingPtr_Storage@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZP6APEAX_K@Z$1?CoTaskMemAlloc@@YAPEAX1@Z@@@@UEAA@XZ; CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>::~CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>(void)
0x180020ec8  nop
0x180020ec9  lea     rcx, [rbp+190h+arg_0]
0x180020ed0  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180020ed5  jmp     loc_180020D1B
0x180020eda  lea     rdi, aBaseStorVssMod_11; "base\\stor\\vss\\modules\\softprv\\src"...
0x180020ee1  mov     [rsp+290h+var_250], rdi
0x180020ee6  lea     r12, aCvssdiffareaal_12; "CVssDiffAreaAllocator::Initialize"
0x180020eed  mov     [rsp+290h+var_248], r12
0x180020ef2  lea     r13, aSpralloc; "SPRALLOC"
0x180020ef9  mov     [rsp+290h+var_240], r13
0x180020efe  mov     [rsp+290h+var_238], 14Bh
0x180020f06  mov     [rsp+290h+var_234], 2
0x180020f0e  mov     esi, 0FFh
0x180020f13  mov     [rsp+290h+var_230], esi
0x180020f17  mov     [rbp+190h+var_1B0], 1000000h
0x180020f1e  xor     edx, edx; Val
0x180020f20  lea     r8d, [rdx+78h]; Size
0x180020f24  lea     rcx, [rsp+290h+var_228]; void *
0x180020f29  call    memset_0
0x180020f2e  mov     r8, rbx; unsigned __int16 *
0x180020f31  lea     rdx, [rbp+190h+var_E0]; this
0x180020f38  lea     rcx, [rsp+290h+var_250]; struct CVssDebugInfo *
0x180020f3d  call    ??6CVssDebugInfo@@QEAA?AU0@PEBG@Z; CVssDebugInfo::operator<<(ushort const *)
0x180020f42  mov     r9d, r15d
0x180020f45  mov     r8, rax
0x180020f48  mov     edx, 3014h
0x180020f4d  lea     rcx, [rbp+190h+var_150]
0x180020f51  call    ?LogError@CVssFunctionTracer@@QEAAXKUCVssDebugInfo@@G@Z; CVssFunctionTracer::LogError(ulong,CVssDebugInfo,ushort)
0x180020f56  lea     rcx, [rsp+290h+var_250]; this
0x180020f5b  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x180020f60  mov     [rsp+290h+var_250], rdi
0x180020f65  mov     [rsp+290h+var_248], r12
0x180020f6a  mov     [rsp+290h+var_240], r13
0x180020f6f  mov     [rsp+290h+var_238], 14Ch
0x180020f77  mov     [rsp+290h+var_234], 2
0x180020f7f  mov     [rsp+290h+var_230], esi
0x180020f83  mov     [rbp+190h+var_1B0], 1000000h
0x180020f8a  xor     edx, edx; Val
0x180020f8c  lea     r8d, [rdx+78h]; Size
0x180020f90  lea     rcx, [rsp+290h+var_228]; void *
0x180020f95  call    memset_0
0x180020f9a  mov     [rsp+290h+var_270], rbx
0x180020f9f  lea     r9, aVolumeSAppears; "Volume %s appears as invalid or dismoun"...
0x180020fa6  mov     r8d, 80042308h
0x180020fac  lea     rdx, [rsp+290h+var_250]
0x180020fb1  lea     rcx, [rbp+190h+var_150]
0x180020fb5  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x180020fbb  lea     rcx, [rbp+190h+arg_0]
0x180020fc2  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180020fc7  lea     rax, ?m_list@CVssQueuedSnapshot@@0V?$CVssDLList@PEAVCVssQueuedSnapshot@@@@A; CVssDLList<CVssQueuedSnapshot *> CVssQueuedSnapshot::m_list
0x180020fce  mov     [rbp+190h+var_1A0], rax
0x180020fd2  mov     rax, cs:?m_list@CVssQueuedSnapshot@@0V?$CVssDLList@PEAVCVssQueuedSnapshot@@@@A; CVssDLList<CVssQueuedSnapshot *> CVssQueuedSnapshot::m_list
0x180020fd9  mov     [rbp+190h+var_198], rax
0x180020fdd  movups  xmm0, xmmword ptr [rdi+4]
0x180020fe1  movdqu  xmmword ptr [rbp+190h+var_160.Data1], xmm0
0x180020fe6  lea     rdx, [rbp+190h+var_160]; struct _GUID
0x180020fea  lea     rcx, [rbp+190h+var_1A0]; this
0x180020fee  call    ?GetNextBySnapshotSet@CVssSnapIterator@@QEAAPEAVCVssQueuedSnapshot@@U_GUID@@@Z; CVssSnapIterator::GetNextBySnapshotSet(_GUID)
0x180020ff3  mov     rbx, rax
0x180020ff6  mov     [rbp+190h+arg_0], rax
0x180020ffd  test    rax, rax
0x180021000  jz      short loc_180021012
0x180021002  mov     rcx, [rax]
0x180021005  mov     rax, [rcx+8]
0x180021009  mov     rcx, rbx
0x18002100c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021011  nop
0x180021012  test    rbx, rbx
0x180021015  jz      loc_1800212DA
0x18002101b  mov     rcx, rbx; this
0x18002101e  call    ?GetSnapshotProperties@CVssQueuedSnapshot@@QEAAPEAU_VSS_SNAPSHOT_PROP@@XZ; CVssQueuedSnapshot::GetSnapshotProperties(void)
0x180021023  mov     rsi, rax
0x180021026  mov     rcx, rbx; this
0x180021029  call    ?GetSnapshotProperties@CVssQueuedSnapshot@@QEAAPEAU_VSS_SNAPSHOT_PROP@@XZ; CVssQueuedSnapshot::GetSnapshotProperties(void)
0x18002102e  cmp     [rax+78h], r15d
0x180021032  jnz     short loc_180021082
0x180021034  mov     [rsp+290h+lpDirectoryName], r14
0x180021039  mov     [rsp+290h+var_260], r12
0x18002103e  mov     rdx, [rsi+30h]
0x180021042  lea     rcx, [rsp+290h+var_260]
0x180021047  call    ?CopyFrom@?$CVssAutoString@V?$CVssAutoCOMPtr@PEAG@@@@QEAAXPEBG@Z; CVssAutoString<CVssAutoCOMPtr<ushort *>>::CopyFrom(ushort const *)
0x18002104c  mov     rsi, [rsp+290h+lpDirectoryName]
0x180021051  mov     dword ptr [rsp+290h+var_270], 1Fh
0x180021059  mov     r9d, r15d
0x18002105c  xor     r8d, r8d
0x18002105f  mov     edx, r13d
0x180021062  mov     rcx, rsi
0x180021065  call    ?GetVolumeInformationFlags@CVsSoftwareProvider@@SAJPEBGJPEAV?$CVssAutoString@V?$CVssAutoCOMPtr@PEAG@@@@HJ@Z; CVsSoftwareProvider::GetVolumeInformationFlags(ushort const *,long,CVssAutoString<CVssAutoCOMPtr<ushort *>> *,int,long)
0x18002106a  test    r15b, al
0x18002106d  jz      loc_1800211F9
0x180021073  test    al, 4
0x180021075  jz      short loc_180021093
0x180021077  lea     rcx, [rsp+290h+var_260]
0x18002107c  call    ??1?$CVssAuto@PEAGV?$CVssAllocatingPtr_Storage@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZP6APEAX_K@Z$1?CoTaskMemAlloc@@YAPEAX1@Z@@@@UEAA@XZ; CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>::~CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>(void)
0x180021081  nop
0x180021082  lea     rcx, [rbp+190h+arg_0]
0x180021089  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002108e  jmp     loc_180020FDD
0x180021093  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002109a  mov     ecx, 30h ; '0'; unsigned __int64
0x18002109f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800210a4  mov     rbx, rax
0x1800210a7  mov     [rbp+190h+arg_10], rax
0x1800210ae  test    rax, rax
0x1800210b1  jz      short loc_1800210D8
0x1800210b3  mov     [rax+8], r14
0x1800210b7  mov     [rax], r12
0x1800210ba  mov     [rax+18h], r14
0x1800210be  mov     [rax+10h], r12
0x1800210c2  mov     [rax+20h], r13
0x1800210c6  mov     [rax+28h], r14b
0x1800210ca  mov     rdx, rsi
0x1800210cd  mov     rcx, rax
0x1800210d0  call    ?CopyFrom@?$CVssAutoString@V?$CVssAutoCOMPtr@PEAG@@@@QEAAXPEBG@Z; CVssAutoString<CVssAutoCOMPtr<ushort *>>::CopyFrom(ushort const *)
0x1800210d5  nop
0x1800210d6  jmp     short loc_1800210DB
0x1800210d8  mov     rbx, r14
0x1800210db  mov     [rbp+190h+arg_8], rbx
0x1800210e2  test    rbx, rbx
0x1800210e5  jz      loc_18002118A
0x1800210eb  lea     rcx, [rdi+18h]
0x1800210ef  mov     r8, rbx
0x1800210f2  mov     rdx, rsi
0x1800210f5  call    ?Add@?$CVssSimpleMap@PEAGPEAVCVssDiffAreaCandidate@@@@QEAAHPEAGPEAVCVssDiffAreaCandidate@@@Z; CVssSimpleMap<ushort *,CVssDiffAreaCandidate *>::Add(ushort *,CVssDiffAreaCandidate *)
0x1800210fa  test    eax, eax
0x1800210fc  jz      short loc_18002111B
0x1800210fe  mov     [rsp+290h+lpDirectoryName], r14
0x180021103  mov     [rbp+190h+arg_8], r14
0x18002110a  lea     rcx, [rbp+190h+arg_8]
0x180021111  call    ??1?$unique_ptr@VCVssDiffAreaAssociation@@U?$default_delete@VCVssDiffAreaAssociation@@@std@@@std@@QEAA@XZ; std::unique_ptr<CVssDiffAreaAssociation>::~unique_ptr<CVssDiffAreaAssociation>(void)
0x180021116  jmp     loc_180021077
0x18002111b  lea     rdi, aBaseStorVssMod_11; "base\\stor\\vss\\modules\\softprv\\src"...
0x180021122  mov     [rsp+290h+var_250], rdi
0x180021127  lea     r12, aCvssdiffareaal_12; "CVssDiffAreaAllocator::Initialize"
0x18002112e  mov     [rsp+290h+var_248], r12
0x180021133  lea     r13, aSpralloc; "SPRALLOC"
0x18002113a  mov     [rsp+290h+var_240], r13
0x18002113f  mov     [rsp+290h+var_238], 1A5h
0x180021147  mov     [rsp+290h+var_234], 2
0x18002114f  mov     [rsp+290h+var_230], 0FFh
0x180021157  mov     [rbp+190h+var_1B0], 1000000h
0x18002115e  xor     edx, edx; Val
0x180021160  lea     r8d, [rdx+78h]; Size
0x180021164  lea     rcx, [rsp+290h+var_228]; void *
0x180021169  call    memset_0
0x18002116e  lea     r9, aMemoryAllocati; "Memory allocation error"
0x180021175  mov     r8d, 8007000Eh
0x18002117b  lea     rdx, [rsp+290h+var_250]
0x180021180  lea     rcx, [rbp+190h+var_150]
0x180021184  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x18002118a  lea     rdi, aBaseStorVssMod_11; "base\\stor\\vss\\modules\\softprv\\src"...
0x180021191  mov     [rsp+290h+var_250], rdi
0x180021196  lea     r12, aCvssdiffareaal_12; "CVssDiffAreaAllocator::Initialize"
0x18002119d  mov     [rsp+290h+var_248], r12
0x1800211a2  lea     r13, aSpralloc; "SPRALLOC"
  ... truncated ...
```
