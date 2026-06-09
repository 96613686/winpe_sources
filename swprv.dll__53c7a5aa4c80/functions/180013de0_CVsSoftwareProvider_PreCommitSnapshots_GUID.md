# CVsSoftwareProvider::PreCommitSnapshots(_GUID)

- ea: `0x180013de0`
- end: `0x180014494`
- name: `?PreCommitSnapshots@CVsSoftwareProvider@@UEAAJU_GUID@@@Z`
- size: `1716`
- prototype: `int(CVsSoftwareProvider *__hidden this, struct _GUID *__struct_ptr)`
- caller_count: `0`
- callee_count: `19`
- tags: `broker_com_uri`

## callees

- `0x18000212c`
- `0x1800034cc`
- `0x1800036c4`
- `0x180003888`
- `0x180013de0`
- `0x180019334`
- `0x180019458`
- `0x180019758`
- `0x180019b60`
- `0x180033a8c`
- `0x180033c78`
- `0x180034278`
- `0x180034a4c`
- `0x18003649c`
- `0x1800367b8`
- `0x180037080`
- `0x18003d78c`
- `0x1800419fc`
- `0x18004b010`

## string_xrefs

- `0x180013e0a`: `CVsSoftwareProvider::PreCommitSnapshots`
- `0x1800141bf`: `CVsSoftwareProvider::PreCommitSnapshots`
- `0x1800143a4`: `CVsSoftwareProvider::PreCommitSnapshots`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CVsSoftwareProvider::PreCommitSnapshots(CVsSoftwareProvider *this, struct _GUID *a2)
{
  struct _GUID *v2; // r14
  int v3; // eax
  CVssQueuedSnapshot *NextBySnapshotSet; // rax
  CVssQueuedSnapshot *v5; // rbx
  CVssQueuedSnapshot *v6; // rbx
  struct _VSS_SNAPSHOT_PROP *v7; // rax
  VSS_SNAPSHOT_STATE m_eStatus; // ebx
  unsigned int v9; // ebx
  __int64 v11; // [rsp+20h] [rbp-278h]
  __int64 v12; // [rsp+28h] [rbp-270h]
  __int64 v13; // [rsp+30h] [rbp-268h]
  __int64 v14; // [rsp+38h] [rbp-260h]
  __int64 v15; // [rsp+40h] [rbp-258h]
  __int64 v16; // [rsp+48h] [rbp-250h]
  __int64 v17; // [rsp+50h] [rbp-248h]
  __int64 v18; // [rsp+58h] [rbp-240h]
  __int64 v19; // [rsp+60h] [rbp-238h]
  __int64 v20; // [rsp+68h] [rbp-230h]
  __int64 v21; // [rsp+70h] [rbp-228h]
  __int64 v22; // [rsp+78h] [rbp-220h]
  __int64 v23; // [rsp+80h] [rbp-218h]
  __int64 v24; // [rsp+88h] [rbp-210h]
  __int64 v25; // [rsp+90h] [rbp-208h]
  __int64 v26; // [rsp+98h] [rbp-200h]
  __int64 v27; // [rsp+A0h] [rbp-1F8h]
  __int64 v28; // [rsp+A8h] [rbp-1F0h]
  __int64 v29; // [rsp+B0h] [rbp-1E8h]
  __int64 v30; // [rsp+B8h] [rbp-1E0h]
  __int64 v31; // [rsp+C0h] [rbp-1D8h]
  __int64 v32; // [rsp+C8h] [rbp-1D0h]
  __int64 v33; // [rsp+E0h] [rbp-1B8h]
  __int64 v34; // [rsp+E8h] [rbp-1B0h]
  const unsigned __int16 *v35; // [rsp+F0h] [rbp-1A8h] BYREF
  const unsigned __int16 *v36; // [rsp+F8h] [rbp-1A0h]
  const unsigned __int16 *v37; // [rsp+100h] [rbp-198h]
  int v38; // [rsp+108h] [rbp-190h]
  int v39; // [rsp+10Ch] [rbp-18Ch]
  int v40; // [rsp+110h] [rbp-188h]
  _BYTE v41[120]; // [rsp+118h] [rbp-180h] BYREF
  int v42; // [rsp+190h] [rbp-108h]
  unsigned int v43; // [rsp+198h] [rbp-100h] BYREF
  CVssQueuedSnapshot *v44; // [rsp+1A0h] [rbp-F8h]
  struct _GUID v45; // [rsp+1B0h] [rbp-E8h] BYREF
  _QWORD v46[2]; // [rsp+1C0h] [rbp-D8h] BYREF
  LPVOID v47; // [rsp+1D0h] [rbp-C8h] BYREF
  unsigned int v48; // [rsp+1D8h] [rbp-C0h]
  unsigned int v49; // [rsp+1F4h] [rbp-A4h]
  _com_error *v50; // [rsp+240h] [rbp-58h] BYREF
  const std::exception *v51; // [rsp+248h] [rbp-50h] BYREF
  LPCRITICAL_SECTION v52[9]; // [rsp+250h] [rbp-48h] BYREF
  struct _VSS_SNAPSHOT_PROP *SnapshotProperties; // [rsp+2B0h] [rbp+18h]
  CVssQueuedSnapshot *v55; // [rsp+2B8h] [rbp+20h] BYREF

  v2 = a2;
  v35 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
  v36 = L"CVsSoftwareProvider::PreCommitSnapshots";
  v37 = L"SPRPROVC";
  v38 = 705;
  v39 = 2;
  v40 = 255;
  v42 = 0x1000000;
  memset_0(v41, 0, sizeof(v41));
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v47, (__int64)&v35, 0);
  try
  {
    if ( !IsInGroup() )
    {
      v35 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
      v36 = L"CVsSoftwareProvider::PreCommitSnapshots";
      v37 = L"SPRPROVC";
      v38 = 711;
      v39 = 2;
      v40 = 255;
      v42 = 0x1000000;
      memset_0(v41, 0, sizeof(v41));
      CVssFunctionTracer::Throw(
        (CVssFunctionTracer *)&v47,
        (const struct CVssDebugInfo *)&v35,
        -2147024891,
        L"The client process is not running under an administrator account");
    }
    v3 = memcmp_0(v2, &GUID_NULL, 0x10u);
    v35 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
    v36 = L"CVsSoftwareProvider::PreCommitSnapshots";
    v37 = L"SPRPROVC";
    v39 = 2;
    v40 = 255;
    v42 = 0x1000000;
    if ( !v3 )
    {
      v38 = 716;
      memset_0(v41, 0, sizeof(v41));
      CVssFunctionTracer::Throw(
        (CVssFunctionTracer *)&v47,
        (const struct CVssDebugInfo *)&v35,
        -2147024809,
        L"SnapshotSetId == GUID_NULL");
    }
    v38 = 719;
    memset_0(v41, 0, sizeof(v41));
    CVssFunctionTracer::Trace(
      &v47,
      &v35,
      L"Parameters: \n  SnapshotSetId = {%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}\n",
      v2->Data1,
      v2->Data2,
      v2->Data3,
      v2->Data4[0],
      v2->Data4[1],
      v2->Data4[2],
      v2->Data4[3],
      v2->Data4[4],
      v2->Data4[5],
      v2->Data4[6],
      v2->Data4[7]);
    CVssAutomaticLock2::CVssAutomaticLock2(
      (CVssAutomaticLock2 *)v52,
      (struct CVssCriticalSection *)CVsSoftwareProvider::m_cs);
    v35 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
    v36 = L"CVsSoftwareProvider::PreCommitSnapshots";
    v37 = L"SPRPROVC";
    v38 = 726;
    v39 = 2;
    v40 = 255;
    v42 = 0x1000000;
    memset_0(v41, 0, sizeof(v41));
    CVssFunctionTracer::AddOperation((struct CVssFunctionTracer *)&v47, (const struct CVssDebugInfo *)&v35, 407);
    v35 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
    v36 = L"CVsSoftwareProvider::PreCommitSnapshots";
    v37 = L"SPRPROVC";
    v38 = 727;
    v39 = 2;
    v40 = 255;
    v42 = 0x1000000;
    memset_0(v41, 0, sizeof(v41));
    CVssFunctionTracer::AddContext((__int64)&v47, (const struct CVssDebugInfo *)&v35);
    v46[0] = &CVssQueuedSnapshot::m_list;
    v46[1] = CVssQueuedSnapshot::m_list;
    while ( 1 )
    {
      v45 = *v2;
      NextBySnapshotSet = CVssSnapIterator::GetNextBySnapshotSet((CVssSnapIterator *)v46, &v45);
      v5 = NextBySnapshotSet;
      v44 = NextBySnapshotSet;
      v55 = NextBySnapshotSet;
      if ( NextBySnapshotSet )
        (*(void (__fastcall **)(CVssQueuedSnapshot *))(*(_QWORD *)NextBySnapshotSet + 8LL))(NextBySnapshotSet);
      if ( !v5 )
        break;
      SnapshotProperties = CVssQueuedSnapshot::GetSnapshotProperties(v5);
      v35 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
      v36 = L"CVsSoftwareProvider::PreCommitSnapshots";
      v37 = L"SPRPROVC";
      v38 = 747;
      v39 = 2;
      v40 = 255;
      v42 = 0x1000000;
      memset_0(v41, 0, sizeof(v41));
      LODWORD(v34) = SnapshotProperties->m_eStatus;
      LODWORD(v33) = SnapshotProperties->m_lSnapshotAttributes;
      LODWORD(v32) = SnapshotProperties->m_SnapshotId.Data4[7];
      LODWORD(v31) = SnapshotProperties->m_SnapshotId.Data4[6];
      LODWORD(v30) = SnapshotProperties->m_SnapshotId.Data4[5];
      LODWORD(v29) = SnapshotProperties->m_SnapshotId.Data4[4];
      LODWORD(v28) = SnapshotProperties->m_SnapshotId.Data4[3];
      LODWORD(v27) = SnapshotProperties->m_SnapshotId.Data4[2];
      LODWORD(v26) = SnapshotProperties->m_SnapshotId.Data4[1];
      LODWORD(v25) = SnapshotProperties->m_SnapshotId.Data4[0];
      LODWORD(v24) = SnapshotProperties->m_SnapshotId.Data3;
      LODWORD(v23) = SnapshotProperties->m_SnapshotId.Data2;
      LODWORD(v22) = SnapshotProperties->m_SnapshotId.Data1;
      LODWORD(v21) = SnapshotProperties->m_SnapshotSetId.Data4[7];
      LODWORD(v20) = SnapshotProperties->m_SnapshotSetId.Data4[6];
      LODWORD(v19) = SnapshotProperties->m_SnapshotSetId.Data4[5];
      LODWORD(v18) = SnapshotProperties->m_SnapshotSetId.Data4[4];
      LODWORD(v17) = SnapshotProperties->m_SnapshotSetId.Data4[3];
      LODWORD(v16) = SnapshotProperties->m_SnapshotSetId.Data4[2];
      LODWORD(v15) = SnapshotProperties->m_SnapshotSetId.Data4[1];
      LODWORD(v14) = SnapshotProperties->m_SnapshotSetId.Data4[0];
      LODWORD(v13) = SnapshotProperties->m_SnapshotSetId.Data3;
      LODWORD(v12) = SnapshotProperties->m_SnapshotSetId.Data2;
      LODWORD(v11) = SnapshotProperties->m_SnapshotSetId.Data1;
      CVssFunctionTracer::Trace(
        &v47,
        &v35,
        L"Field values for %p: \n"
         "  SnapshotSetId = {%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}\n"
         "  SnapshotId = {%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}\n"
         "  VolumeName = %s\n"
         "  Creation timestamp = 0x%016I64x\n"
         "  lAttributes = 0x%08lx\n"
         "  status = %d\n",
        SnapshotProperties,
        v11,
        v12,
        v13,
        v14,
        v15,
        v16,
        v17,
        v18,
        v19,
        v20,
        v21,
        v22,
        v23,
        v24,
        v25,
        v26,
        v27,
        v28,
        v29,
        v30,
        v31,
        v32,
        SnapshotProperties->m_pwszOriginalVolumeName,
        SnapshotProperties->m_tsCreationTimestamp,
        v33,
        v34);
      v6 = v44;
      v7 = CVssQueuedSnapshot::GetSnapshotProperties(v44);
      if ( v7->m_eStatus == VSS_SS_PREPARED )
      {
        CVssQueuedSnapshot::MarkAsProcessingPreCommit(v6);
        CVssQueuedSnapshot::MarkAsPreCommitted(v6);
      }
      else if ( v7->m_eStatus != VSS_SS_PRECOMMITTED )
      {
        m_eStatus = CVssQueuedSnapshot::GetSnapshotProperties(v6)->m_eStatus;
        v35 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
        v36 = L"CVsSoftwareProvider::PreCommitSnapshots";
        v37 = L"SPRPROVC";
        v38 = 783;
        v39 = 2;
        v40 = 255;
        v42 = 0x1000000;
        memset_0(v41, 0, sizeof(v41));
        LODWORD(v11) = m_eStatus;
        CVssFunctionTracer::TranslateGenericError(&v47, &v35, 2147549183LL, L"bad state %d", v11);
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v55);
      v2 = a2;
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v55);
    CVssAutomaticLock2::~CVssAutomaticLock2(v52);
  }
  catch ( long v43 )
  {
    CVssFunctionTracer::HandleHresultException(
      (CVssFunctionTracer *)&v47,
      v43,
      L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx",
      L"SPRPROVC",
      L"CVsSoftwareProvider::PreCommitSnapshots",
      0x313u,
      v49);
  }
  catch ( _com_error *v50 )
  {
    CVssFunctionTracer::HandleComException(
      (CVssFunctionTracer *)&v47,
      v50,
      L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx",
      L"SPRPROVC",
      L"CVsSoftwareProvider::PreCommitSnapshots",
      0x313u,
      v49);
  }
  catch ( std::bad_alloc )
  {
    CVssFunctionTracer::HandleStdBadAllocException(
      (CVssFunctionTracer *)&v47,
      L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx",
      L"SPRPROVC",
      L"CVsSoftwareProvider::PreCommitSnapshots",
      0x313u,
      v49);
  }
  catch ( const std::exception *v51 )
  {
    CVssFunctionTracer::HandleStdGenericException(
      (CVssFunctionTracer *)&v47,
      v51,
      L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx",
      L"SPRPROVC",
      L"CVsSoftwareProvider::PreCommitSnapshots",
      0x313u,
      v49);
  }
  v9 = v48;
  CVssFunctionTracer::~CVssFunctionTracer(&v47);
  return v9;
}

```

## disassembly

```asm
0x180013de0  mov     rax, rsp
0x180013de3  mov     [rax+10h], rdx
0x180013de7  push    rbx
0x180013de8  push    rsi
0x180013de9  push    rdi
0x180013dea  push    r12
0x180013dec  push    r13
0x180013dee  push    r14
0x180013df0  push    r15
0x180013df2  sub     rsp, 260h
0x180013df9  mov     r14, rdx
0x180013dfc  lea     r12, aBaseStorVssMod_9; "base\\stor\\vss\\modules\\softprv\\src"...
0x180013e03  mov     [rax-1A8h], r12
0x180013e0a  lea     r13, aCvssoftwarepro_21; "CVsSoftwareProvider::PreCommitSnapshots"
0x180013e11  mov     [rax-1A0h], r13
0x180013e18  lea     rbx, aSprprovc; "SPRPROVC"
0x180013e1f  mov     [rax-198h], rbx
0x180013e26  mov     dword ptr [rax-190h], 2C1h
0x180013e30  mov     edi, 2
0x180013e35  mov     [rax-18Ch], edi
0x180013e3b  mov     esi, 0FFh
0x180013e40  mov     [rax-188h], esi
0x180013e46  mov     dword ptr [rax-108h], 1000000h
0x180013e50  xor     edx, edx; Val
0x180013e52  lea     r8d, [rdi+76h]; Size
0x180013e56  lea     rcx, [rax-180h]; void *
0x180013e5d  call    memset_0
0x180013e62  xor     r8d, r8d
0x180013e65  lea     rdx, [rsp+298h+var_1A8]
0x180013e6d  lea     rcx, [rsp+298h+var_C8]
0x180013e75  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x180013e7a  nop
0x180013e7b  call    ?IsInGroup@@YA_NK_N@Z; IsInGroup(ulong,bool)
0x180013e80  test    al, al
0x180013e82  jnz     short loc_180013EF5
0x180013e84  mov     [rsp+298h+var_1A8], r12
0x180013e8c  mov     [rsp+298h+var_1A0], r13
0x180013e94  mov     [rsp+298h+var_198], rbx
0x180013e9c  mov     [rsp+298h+var_190], 2C7h
0x180013ea7  mov     [rsp+298h+var_18C], edi
0x180013eae  mov     [rsp+298h+var_188], esi
0x180013eb5  mov     [rsp+298h+var_108], 1000000h
0x180013ec0  xor     edx, edx; Val
0x180013ec2  lea     r8d, [rdi+76h]; Size
0x180013ec6  lea     rcx, [rsp+298h+var_180]; void *
0x180013ece  call    memset_0
0x180013ed3  lea     r9, aTheClientProce_0; "The client process is not running under"...
0x180013eda  mov     r8d, 80070005h
0x180013ee0  lea     rdx, [rsp+298h+var_1A8]
0x180013ee8  lea     rcx, [rsp+298h+var_C8]
0x180013ef0  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x180013ef5  mov     r8d, 10h; Size
0x180013efb  lea     rdx, GUID_NULL; Buf2
0x180013f02  mov     rcx, r14; Buf1
0x180013f05  call    memcmp_0
0x180013f0a  mov     [rsp+298h+var_1A8], r12
0x180013f12  mov     [rsp+298h+var_1A0], r13
0x180013f1a  mov     [rsp+298h+var_198], rbx
0x180013f22  mov     [rsp+298h+var_18C], edi
0x180013f29  mov     [rsp+298h+var_188], esi
0x180013f30  mov     [rsp+298h+var_108], 1000000h
0x180013f3b  xor     edx, edx; Val
0x180013f3d  lea     r8d, [rdx+78h]; Size
0x180013f41  lea     rcx, [rsp+298h+var_180]; void *
0x180013f49  test    eax, eax
0x180013f4b  jnz     short loc_180013F7F
0x180013f4d  mov     [rsp+298h+var_190], 2CCh
0x180013f58  call    memset_0
0x180013f5d  lea     r9, aSnapshotsetidG; "SnapshotSetId == GUID_NULL"
0x180013f64  mov     r8d, 80070057h
0x180013f6a  lea     rdx, [rsp+298h+var_1A8]
0x180013f72  lea     rcx, [rsp+298h+var_C8]
0x180013f7a  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x180013f7f  mov     [rsp+298h+var_190], 2CFh
0x180013f8a  call    memset_0
0x180013f8f  movzx   eax, byte ptr [r14+0Fh]
0x180013f94  movzx   ecx, byte ptr [r14+0Eh]
0x180013f99  movzx   edx, byte ptr [r14+0Dh]
0x180013f9e  movzx   r8d, byte ptr [r14+0Ch]
0x180013fa3  movzx   r9d, byte ptr [r14+0Bh]
0x180013fa8  movzx   r10d, byte ptr [r14+0Ah]
0x180013fad  movzx   r11d, byte ptr [r14+9]
0x180013fb2  movzx   ebx, byte ptr [r14+8]
0x180013fb7  movzx   edi, word ptr [r14+6]
0x180013fbc  movzx   esi, word ptr [r14+4]
0x180013fc1  mov     dword ptr [rsp+298h+var_230], eax
0x180013fc5  mov     dword ptr [rsp+298h+var_238], ecx
0x180013fc9  mov     dword ptr [rsp+298h+var_240], edx
0x180013fcd  mov     dword ptr [rsp+298h+var_248], r8d
0x180013fd2  mov     dword ptr [rsp+298h+var_250], r9d
0x180013fd7  mov     dword ptr [rsp+298h+var_258], r10d
0x180013fdc  mov     dword ptr [rsp+298h+var_260], r11d
0x180013fe1  mov     dword ptr [rsp+298h+var_268], ebx
0x180013fe5  mov     dword ptr [rsp+298h+var_270], edi
0x180013fe9  mov     dword ptr [rsp+298h+var_278], esi
0x180013fed  mov     r9d, [r14]
0x180013ff0  lea     r8, aParametersSnap_5; "Parameters: \n  SnapshotSetId = {%.8x-%"...
0x180013ff7  lea     rdx, [rsp+298h+var_1A8]
0x180013fff  lea     rcx, [rsp+298h+var_C8]
0x180014007  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x18001400c  lea     rdx, ?m_cs@CVsSoftwareProvider@@0VCVssCriticalSection@@A; struct CVssCriticalSection *
0x180014013  lea     rcx, [rsp+298h+var_48]; this
0x18001401b  call    ??0CVssAutomaticLock2@@QEAA@AEAVCVssCriticalSection@@@Z; CVssAutomaticLock2::CVssAutomaticLock2(CVssCriticalSection &)
0x180014020  nop
0x180014021  mov     [rsp+298h+var_1A8], r12
0x180014029  mov     [rsp+298h+var_1A0], r13
0x180014031  lea     rdi, aSprprovc; "SPRPROVC"
0x180014038  mov     [rsp+298h+var_198], rdi
0x180014040  mov     [rsp+298h+var_190], 2D6h
0x18001404b  mov     [rsp+298h+var_18C], 2
0x180014056  mov     [rsp+298h+var_188], 0FFh
0x180014061  mov     [rsp+298h+var_108], 1000000h
0x18001406c  mov     esi, 78h ; 'x'
0x180014071  mov     r8d, esi; Size
0x180014074  xor     edx, edx; Val
0x180014076  lea     rcx, [rsp+298h+var_180]; void *
0x18001407e  call    memset_0
0x180014083  mov     r8d, 197h
0x180014089  lea     rdx, [rsp+298h+var_1A8]
0x180014091  lea     rcx, [rsp+298h+var_C8]
0x180014099  call    ?AddOperation@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@IZZ; CVssFunctionTracer::AddOperation(CVssDebugInfo,uint,...)
0x18001409e  mov     [rsp+298h+var_1A8], r12
0x1800140a6  mov     [rsp+298h+var_1A0], r13
0x1800140ae  mov     [rsp+298h+var_198], rdi
0x1800140b6  mov     [rsp+298h+var_190], 2D7h
0x1800140c1  mov     [rsp+298h+var_18C], 2
0x1800140cc  mov     [rsp+298h+var_188], 0FFh
0x1800140d7  mov     [rsp+298h+var_108], 1000000h
0x1800140e2  mov     r8d, esi; Size
0x1800140e5  xor     edx, edx; Val
0x1800140e7  lea     rcx, [rsp+298h+var_180]; void *
0x1800140ef  call    memset_0
0x1800140f4  lea     r9, aSystemProvider; "System Provider"
0x1800140fb  mov     r8d, 1394h
0x180014101  lea     rdx, [rsp+298h+var_1A8]
0x180014109  lea     rcx, [rsp+298h+var_C8]
0x180014111  call    ?AddContext@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@IPEBG@Z; CVssFunctionTracer::AddContext(CVssDebugInfo,uint,ushort const *)
0x180014116  lea     rax, ?m_list@CVssQueuedSnapshot@@0V?$CVssDLList@PEAVCVssQueuedSnapshot@@@@A; CVssDLList<CVssQueuedSnapshot *> CVssQueuedSnapshot::m_list
0x18001411d  mov     [rsp+298h+var_D8], rax
0x180014125  mov     rax, cs:?m_list@CVssQueuedSnapshot@@0V?$CVssDLList@PEAVCVssQueuedSnapshot@@@@A; CVssDLList<CVssQueuedSnapshot *> CVssQueuedSnapshot::m_list
0x18001412c  mov     [rsp+298h+var_D0], rax
0x180014134  movups  xmm0, xmmword ptr [r14]
0x180014138  movdqu  xmmword ptr [rsp+298h+var_E8.Data1], xmm0
0x180014141  lea     rdx, [rsp+298h+var_E8]; struct _GUID
0x180014149  lea     rcx, [rsp+298h+var_D8]; this
0x180014151  call    ?GetNextBySnapshotSet@CVssSnapIterator@@QEAAPEAVCVssQueuedSnapshot@@U_GUID@@@Z; CVssSnapIterator::GetNextBySnapshotSet(_GUID)
0x180014156  mov     rbx, rax
0x180014159  mov     [rsp+298h+var_F8], rax
0x180014161  mov     [rsp+298h+arg_18], rax
0x180014169  test    rax, rax
0x18001416c  jz      short loc_18001417E
0x18001416e  mov     rax, [rax]
0x180014171  mov     rcx, rbx
0x180014174  mov     rax, [rax+8]
0x180014178  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001417d  nop
0x18001417e  test    rbx, rbx
0x180014181  jnz     short loc_1800141A4
0x180014183  lea     rcx, [rsp+298h+arg_18]
0x18001418b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180014190  nop
0x180014191  lea     rcx, [rsp+298h+var_48]; this
0x180014199  call    ??1CVssAutomaticLock2@@QEAA@XZ; CVssAutomaticLock2::~CVssAutomaticLock2(void)
0x18001419e  nop
0x18001419f  jmp     loc_18001446B
0x1800141a4  mov     rcx, rbx; this
0x1800141a7  call    ?GetSnapshotProperties@CVssQueuedSnapshot@@QEAAPEAU_VSS_SNAPSHOT_PROP@@XZ; CVssQueuedSnapshot::GetSnapshotProperties(void)
0x1800141ac  mov     r13, rax
0x1800141af  mov     [rsp+298h+arg_10], rax
0x1800141b7  mov     [rsp+298h+var_1A8], r12
0x1800141bf  lea     rax, aCvssoftwarepro_21; "CVsSoftwareProvider::PreCommitSnapshots"
0x1800141c6  mov     [rsp+298h+var_1A0], rax
0x1800141ce  mov     [rsp+298h+var_198], rdi
0x1800141d6  mov     [rsp+298h+var_190], 2EBh
0x1800141e1  mov     [rsp+298h+var_18C], 2
0x1800141ec  mov     [rsp+298h+var_188], 0FFh
0x1800141f7  mov     [rsp+298h+var_108], 1000000h
0x180014202  mov     r8, rsi; Size
0x180014205  xor     edx, edx; Val
0x180014207  lea     rcx, [rsp+298h+var_180]; void *
0x18001420f  call    memset_0
0x180014214  movzx   ecx, byte ptr [r13+0Fh]
0x180014219  movzx   edx, byte ptr [r13+0Eh]
0x18001421e  movzx   r8d, byte ptr [r13+0Dh]
0x180014223  movzx   r9d, byte ptr [r13+0Ch]
0x180014228  movzx   r10d, byte ptr [r13+0Bh]
0x18001422d  movzx   r11d, byte ptr [r13+0Ah]
0x180014232  movzx   edi, byte ptr [r13+9]
0x180014237  movzx   esi, byte ptr [r13+8]
0x18001423c  movzx   r14d, word ptr [r13+6]
0x180014241  movzx   r15d, word ptr [r13+4]
0x180014246  movzx   r12d, byte ptr [r13+1Fh]
0x18001424b  movzx   r13d, byte ptr [r13+1Eh]
0x180014250  mov     rax, [rsp+298h+arg_10]
0x180014258  mov     eax, [rax+78h]
0x18001425b  mov     dword ptr [rsp+298h+var_1B0], eax
0x180014262  mov     rax, [rsp+298h+arg_10]
0x18001426a  mov     eax, [rax+68h]
0x18001426d  mov     dword ptr [rsp+298h+var_1B8], eax
0x180014274  mov     rax, [rsp+298h+arg_10]
0x18001427c  mov     rax, [rax+70h]
0x180014280  mov     [rsp+298h+var_1C0], rax
0x180014288  mov     rax, [rsp+298h+arg_10]
0x180014290  mov     rax, [rax+30h]
0x180014294  mov     [rsp+298h+var_1C8], rax
0x18001429c  mov     dword ptr [rsp+298h+var_1D0], ecx
0x1800142a3  mov     dword ptr [rsp+298h+var_1D8], edx
0x1800142aa  mov     dword ptr [rsp+298h+var_1E0], r8d
0x1800142b2  mov     dword ptr [rsp+298h+var_1E8], r9d
0x1800142ba  mov     dword ptr [rsp+298h+var_1F0], r10d
0x1800142c2  mov     dword ptr [rsp+298h+var_1F8], r11d
0x1800142ca  mov     dword ptr [rsp+298h+var_200], edi
0x1800142d1  mov     dword ptr [rsp+298h+var_208], esi
0x1800142d8  mov     dword ptr [rsp+298h+var_210], r14d
0x1800142e0  mov     dword ptr [rsp+298h+var_218], r15d
0x1800142e8  mov     rcx, [rsp+298h+arg_10]
0x1800142f0  mov     eax, [rcx]
0x1800142f2  mov     dword ptr [rsp+298h+var_220], eax
0x1800142f6  mov     dword ptr [rsp+298h+var_228], r12d
0x1800142fb  mov     dword ptr [rsp+298h+var_230], r13d
0x180014300  movzx   eax, byte ptr [rcx+1Dh]
0x180014304  mov     dword ptr [rsp+298h+var_238], eax
0x180014308  movzx   eax, byte ptr [rcx+1Ch]
0x18001430c  mov     dword ptr [rsp+298h+var_240], eax
0x180014310  movzx   eax, byte ptr [rcx+1Bh]
0x180014314  mov     dword ptr [rsp+298h+var_248], eax
0x180014318  movzx   eax, byte ptr [rcx+1Ah]
0x18001431c  mov     dword ptr [rsp+298h+var_250], eax
0x180014320  movzx   eax, byte ptr [rcx+19h]
0x180014324  mov     dword ptr [rsp+298h+var_258], eax
0x180014328  movzx   eax, byte ptr [rcx+18h]
0x18001432c  mov     dword ptr [rsp+298h+var_260], eax
0x180014330  movzx   eax, word ptr [rcx+16h]
0x180014334  mov     dword ptr [rsp+298h+var_268], eax
0x180014338  movzx   eax, word ptr [rcx+14h]
0x18001433c  mov     dword ptr [rsp+298h+var_270], eax
0x180014340  mov     eax, [rcx+10h]
0x180014343  mov     dword ptr [rsp+298h+var_278], eax
0x180014347  mov     r9, rcx
0x18001434a  lea     r8, aFieldValuesFor_0; "Field values for %p: \n  SnapshotSetId "...
0x180014351  lea     rdx, [rsp+298h+var_1A8]
0x180014359  lea     rcx, [rsp+298h+var_C8]
0x180014361  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x180014366  mov     rbx, [rsp+298h+var_F8]
0x18001436e  mov     rcx, rbx; this
0x180014371  call    ?GetSnapshotProperties@CVssQueuedSnapshot@@QEAAPEAU_VSS_SNAPSHOT_PROP@@XZ; CVssQueuedSnapshot::GetSnapshotProperties(void)
0x180014376  cmp     dword ptr [rax+78h], 3
0x18001437a  jz      loc_180014427
0x180014380  cmp     dword ptr [rax+78h], 5
0x180014384  jz      loc_180014438
0x18001438a  mov     rcx, rbx; this
0x18001438d  call    ?GetSnapshotProperties@CVssQueuedSnapshot@@QEAAPEAU_VSS_SNAPSHOT_PROP@@XZ; CVssQueuedSnapshot::GetSnapshotProperties(void)
0x180014392  mov     ebx, [rax+78h]
0x180014395  lea     rax, aBaseStorVssMod_9; "base\\stor\\vss\\modules\\softprv\\src"...
0x18001439c  mov     [rsp+298h+var_1A8], rax
0x1800143a4  lea     rax, aCvssoftwarepro_21; "CVsSoftwareProvider::PreCommitSnapshots"
0x1800143ab  mov     [rsp+298h+var_1A0], rax
0x1800143b3  lea     rax, aSprprovc; "SPRPROVC"
0x1800143ba  mov     [rsp+298h+var_198], rax
0x1800143c2  mov     [rsp+298h+var_190], 30Fh
0x1800143cd  mov     [rsp+298h+var_18C], 2
0x1800143d8  mov     [rsp+298h+var_188], 0FFh
0x1800143e3  mov     [rsp+298h+var_108], 1000000h
0x1800143ee  xor     edx, edx; Val
0x1800143f0  lea     r8d, [rdx+78h]; Size
0x1800143f4  lea     rcx, [rsp+298h+var_180]; void *
0x1800143fc  call    memset_0
0x180014401  mov     dword ptr [rsp+298h+var_278], ebx
0x180014405  lea     r9, aBadStateD; "bad state %d"
0x18001440c  mov     r8d, 8000FFFFh
0x180014412  lea     rdx, [rsp+298h+var_1A8]
0x18001441a  lea     rcx, [rsp+298h+var_C8]
0x180014422  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x180014427  mov     rcx, rbx; this
0x18001442a  call    ?MarkAsProcessingPreCommit@CVssQueuedSnapshot@@QEAAXXZ; CVssQueuedSnapshot::MarkAsProcessingPreCommit(void)
0x18001442f  mov     rcx, rbx; this
0x180014432  call    ?MarkAsPreCommitted@CVssQueuedSnapshot@@QEAAXXZ; CVssQueuedSnapshot::MarkAsPreCommitted(void)
0x180014437  nop
0x180014438  lea     rcx, [rsp+298h+arg_18]
0x180014440  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180014445  mov     r14, [rsp+298h+arg_8]
0x18001444d  lea     r12, aBaseStorVssMod_9; "base\\stor\\vss\\modules\\softprv\\src"...
0x180014454  lea     rdi, aSprprovc; "SPRPROVC"
0x18001445b  mov     esi, 78h ; 'x'
0x180014460  jmp     loc_180014134
0x180014465  jmp     short loc_18001446B
0x180014467  jmp     short loc_18001446B
0x180014469  jmp     short $+2
0x18001446b  mov     ebx, [rsp+298h+var_C0]
0x180014472  lea     rcx, [rsp+298h+var_C8]; this
0x18001447a  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x18001447f  mov     eax, ebx
0x180014481  add     rsp, 260h
0x180014488  pop     r15
0x18001448a  pop     r14
0x18001448c  pop     r13
0x18001448e  pop     r12
0x180014490  pop     rdi
0x180014491  pop     rsi
0x180014492  pop     rbx
  ... truncated ...
```
