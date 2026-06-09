# CVsSoftwareProvider::PostCommitSnapshots(_GUID,long)

- ea: `0x180013080`
- end: `0x1800138b3`
- name: `?PostCommitSnapshots@CVsSoftwareProvider@@UEAAJU_GUID@@J@Z`
- size: `2099`
- prototype: `int(CVsSoftwareProvider *__hidden this, struct _GUID *__struct_ptr, int)`
- caller_count: `0`
- callee_count: `22`
- tags: `broker_com_uri`

## callees

- `0x18000212c`
- `0x1800034cc`
- `0x1800036c4`
- `0x180003888`
- `0x180010974`
- `0x180013080`
- `0x1800191e0`
- `0x180019334`
- `0x180019458`
- `0x1800196cc`
- `0x180019a08`
- `0x18001ac64`
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

- `0x1800130b5`: `CVsSoftwareProvider::PostCommitSnapshots`
- `0x18001325a`: `CVsSoftwareProvider::PostCommitSnapshots`
- `0x1800132ea`: `CVsSoftwareProvider::PostCommitSnapshots`
- `0x180013386`: `CVsSoftwareProvider::PostCommitSnapshots`
- `0x180013709`: `CVsSoftwareProvider::PostCommitSnapshots`
- `0x1800137d1`: `CVsSoftwareProvider::PostCommitSnapshots`
- `0x180013856`: `CVsSoftwareProvider::PostCommitSnapshots`
- `0x180013833`: `Snapshot postcommitted`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CVsSoftwareProvider::PostCommitSnapshots(CVsSoftwareProvider *this, struct _GUID *a2, int a3)
{
  struct _GUID *v4; // r14
  char v5; // al
  CVssQueuedSnapshot *NextBySnapshotSet; // rax
  CVssQueuedSnapshot *v7; // rbx
  CVssQueuedSnapshot *v8; // rbx
  struct _VSS_SNAPSHOT_PROP *v9; // rax
  VSS_SNAPSHOT_STATE m_eStatus; // ebx
  int ContextInternal; // eax
  CVssQueuedSnapshot *v12; // rcx
  unsigned int v13; // ebx
  __int64 v15; // [rsp+20h] [rbp-278h]
  __int64 v16; // [rsp+28h] [rbp-270h]
  __int64 v17; // [rsp+30h] [rbp-268h]
  __int64 v18; // [rsp+38h] [rbp-260h]
  __int64 v19; // [rsp+40h] [rbp-258h]
  __int64 v20; // [rsp+48h] [rbp-250h]
  __int64 v21; // [rsp+50h] [rbp-248h]
  __int64 v22; // [rsp+58h] [rbp-240h]
  __int64 v23; // [rsp+60h] [rbp-238h]
  __int64 v24; // [rsp+68h] [rbp-230h]
  __int64 v25; // [rsp+70h] [rbp-228h]
  __int64 v26; // [rsp+78h] [rbp-220h]
  __int64 v27; // [rsp+80h] [rbp-218h]
  __int64 v28; // [rsp+88h] [rbp-210h]
  __int64 v29; // [rsp+90h] [rbp-208h]
  __int64 v30; // [rsp+98h] [rbp-200h]
  __int64 v31; // [rsp+A0h] [rbp-1F8h]
  __int64 v32; // [rsp+A8h] [rbp-1F0h]
  __int64 v33; // [rsp+B0h] [rbp-1E8h]
  __int64 v34; // [rsp+B8h] [rbp-1E0h]
  __int64 v35; // [rsp+C0h] [rbp-1D8h]
  __int64 v36; // [rsp+C8h] [rbp-1D0h]
  __int64 v37; // [rsp+E0h] [rbp-1B8h]
  __int64 v38; // [rsp+E8h] [rbp-1B0h]
  const unsigned __int16 *v39; // [rsp+F0h] [rbp-1A8h] BYREF
  const unsigned __int16 *v40; // [rsp+F8h] [rbp-1A0h]
  const unsigned __int16 *v41; // [rsp+100h] [rbp-198h]
  int v42; // [rsp+108h] [rbp-190h]
  int v43; // [rsp+10Ch] [rbp-18Ch]
  int v44; // [rsp+110h] [rbp-188h]
  _BYTE v45[120]; // [rsp+118h] [rbp-180h] BYREF
  int v46; // [rsp+190h] [rbp-108h]
  CVssQueuedSnapshot *v47; // [rsp+198h] [rbp-100h] BYREF
  unsigned int v48; // [rsp+1A0h] [rbp-F8h] BYREF
  CVssQueuedSnapshot *v49; // [rsp+1A8h] [rbp-F0h]
  LPVOID v50; // [rsp+1B0h] [rbp-E8h] BYREF
  unsigned int v51; // [rsp+1B8h] [rbp-E0h]
  unsigned int v52; // [rsp+1D4h] [rbp-C4h]
  struct _GUID v53; // [rsp+220h] [rbp-78h] BYREF
  _QWORD v54[2]; // [rsp+230h] [rbp-68h] BYREF
  _com_error *v55; // [rsp+240h] [rbp-58h] BYREF
  const std::exception *v56; // [rsp+248h] [rbp-50h] BYREF
  LPCRITICAL_SECTION v57[9]; // [rsp+250h] [rbp-48h] BYREF
  struct _VSS_SNAPSHOT_PROP *SnapshotProperties; // [rsp+2B8h] [rbp+20h]

  v4 = a2;
  v39 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
  v40 = L"CVsSoftwareProvider::PostCommitSnapshots";
  v41 = L"SPRPROVC";
  v42 = 980;
  v43 = 2;
  v44 = 255;
  v46 = 0x1000000;
  memset_0(v45, 0, sizeof(v45));
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v50, (__int64)&v39, 0);
  try
  {
    v5 = IsInGroup();
    v39 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
    v40 = L"CVsSoftwareProvider::PostCommitSnapshots";
    v41 = L"SPRPROVC";
    v43 = 2;
    v44 = 255;
    v46 = 0x1000000;
    if ( !v5 )
    {
      v42 = 987;
      memset_0(v45, 0, sizeof(v45));
      CVssFunctionTracer::Throw(
        &v50,
        &v39,
        2147942405LL,
        L"The client process is not running under an administrator account");
    }
    v42 = 990;
    memset_0(v45, 0, sizeof(v45));
    CVssFunctionTracer::Trace(
      &v50,
      &v39,
      L"Parameters: \n  SnapshotSetId = {%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x} \n  lSnapshotsCount = %ld",
      v4->Data1,
      v4->Data2,
      v4->Data3,
      v4->Data4[0],
      v4->Data4[1],
      v4->Data4[2],
      v4->Data4[3],
      v4->Data4[4],
      v4->Data4[5],
      v4->Data4[6],
      v4->Data4[7],
      a3);
    if ( !memcmp_0(v4, &GUID_NULL, 0x10u) )
    {
      v39 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
      v40 = L"CVsSoftwareProvider::PostCommitSnapshots";
      v41 = L"SPRPROVC";
      v42 = 998;
      v43 = 2;
      v44 = 255;
      v46 = 0x1000000;
      memset_0(v45, 0, sizeof(v45));
      CVssFunctionTracer::Throw(&v50, &v39, 2147942487LL, L"SnapshotSetId == GUID_NULL");
    }
    if ( a3 < 0 )
    {
      v39 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
      v40 = L"CVsSoftwareProvider::PostCommitSnapshots";
      v41 = L"SPRPROVC";
      v42 = 1000;
      v43 = 2;
      v44 = 255;
      v46 = 0x1000000;
      memset_0(v45, 0, sizeof(v45));
      CVssFunctionTracer::Throw(&v50, &v39, 2147942487LL, L"lSnapshotsCount < 0");
    }
    CVssAutomaticLock2::CVssAutomaticLock2(
      (CVssAutomaticLock2 *)v57,
      (struct CVssCriticalSection *)CVsSoftwareProvider::m_cs);
    v39 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
    v40 = L"CVsSoftwareProvider::PostCommitSnapshots";
    v41 = L"SPRPROVC";
    v42 = 1004;
    v43 = 2;
    v44 = 255;
    v46 = 0x1000000;
    memset_0(v45, 0, sizeof(v45));
    CVssFunctionTracer::AddOperation((struct CVssFunctionTracer *)&v50, (const struct CVssDebugInfo *)&v39, 408);
    v39 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
    v40 = L"CVsSoftwareProvider::PostCommitSnapshots";
    v41 = L"SPRPROVC";
    v42 = 1005;
    v43 = 2;
    v44 = 255;
    v46 = 0x1000000;
    memset_0(v45, 0, sizeof(v45));
    CVssFunctionTracer::AddContext((__int64)&v50, (const struct CVssDebugInfo *)&v39);
    v54[0] = &CVssQueuedSnapshot::m_list;
    v54[1] = CVssQueuedSnapshot::m_list;
    while ( 1 )
    {
      v53 = *v4;
      NextBySnapshotSet = CVssSnapIterator::GetNextBySnapshotSet((CVssSnapIterator *)v54, &v53);
      v7 = NextBySnapshotSet;
      v49 = NextBySnapshotSet;
      v47 = NextBySnapshotSet;
      if ( NextBySnapshotSet )
        (*(void (__fastcall **)(CVssQueuedSnapshot *))(*(_QWORD *)NextBySnapshotSet + 8LL))(NextBySnapshotSet);
      if ( !v7 )
        break;
      SnapshotProperties = CVssQueuedSnapshot::GetSnapshotProperties(v7);
      v39 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
      v40 = L"CVsSoftwareProvider::PostCommitSnapshots";
      v41 = L"SPRPROVC";
      v42 = 1026;
      v43 = 2;
      v44 = 255;
      v46 = 0x1000000;
      memset_0(v45, 0, sizeof(v45));
      LODWORD(v38) = SnapshotProperties->m_eStatus;
      LODWORD(v37) = SnapshotProperties->m_lSnapshotAttributes;
      LODWORD(v36) = SnapshotProperties->m_SnapshotId.Data4[7];
      LODWORD(v35) = SnapshotProperties->m_SnapshotId.Data4[6];
      LODWORD(v34) = SnapshotProperties->m_SnapshotId.Data4[5];
      LODWORD(v33) = SnapshotProperties->m_SnapshotId.Data4[4];
      LODWORD(v32) = SnapshotProperties->m_SnapshotId.Data4[3];
      LODWORD(v31) = SnapshotProperties->m_SnapshotId.Data4[2];
      LODWORD(v30) = SnapshotProperties->m_SnapshotId.Data4[1];
      LODWORD(v29) = SnapshotProperties->m_SnapshotId.Data4[0];
      LODWORD(v28) = SnapshotProperties->m_SnapshotId.Data3;
      LODWORD(v27) = SnapshotProperties->m_SnapshotId.Data2;
      LODWORD(v26) = SnapshotProperties->m_SnapshotId.Data1;
      LODWORD(v25) = SnapshotProperties->m_SnapshotSetId.Data4[7];
      LODWORD(v24) = SnapshotProperties->m_SnapshotSetId.Data4[6];
      LODWORD(v23) = SnapshotProperties->m_SnapshotSetId.Data4[5];
      LODWORD(v22) = SnapshotProperties->m_SnapshotSetId.Data4[4];
      LODWORD(v21) = SnapshotProperties->m_SnapshotSetId.Data4[3];
      LODWORD(v20) = SnapshotProperties->m_SnapshotSetId.Data4[2];
      LODWORD(v19) = SnapshotProperties->m_SnapshotSetId.Data4[1];
      LODWORD(v18) = SnapshotProperties->m_SnapshotSetId.Data4[0];
      LODWORD(v17) = SnapshotProperties->m_SnapshotSetId.Data3;
      LODWORD(v16) = SnapshotProperties->m_SnapshotSetId.Data2;
      LODWORD(v15) = SnapshotProperties->m_SnapshotSetId.Data1;
      CVssFunctionTracer::Trace(
        &v50,
        &v39,
        L"Field values for %p: \n"
         "  SnapshotSetId = {%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}\n"
         "  SnapshotId = {%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}\n"
         "  VolumeName = %s\n"
         "  Creation timestamp = 0x%016I64x\n"
         "  lAttributes = 0x%08lx\n"
         "  status = %d\n",
        SnapshotProperties,
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
        v33,
        v34,
        v35,
        v36,
        SnapshotProperties->m_pwszOriginalVolumeName,
        SnapshotProperties->m_tsCreationTimestamp,
        v37,
        v38);
      v8 = v49;
      v9 = CVssQueuedSnapshot::GetSnapshotProperties(v49);
      if ( v9->m_eStatus == VSS_SS_COMMITTED )
      {
        CVssQueuedSnapshot::MarkAsProcessingPostCommit(v8);
        ContextInternal = CVsSoftwareProvider::GetContextInternal((CVsSoftwareProvider *)((char *)this - 8));
        CVssQueuedSnapshot::SetPostcommitInfo(v8, a3, ContextInternal);
        CVssQueuedSnapshot::EndCommitSnapshotIoctl(v8, SnapshotProperties);
        v39 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
        v40 = L"CVsSoftwareProvider::PostCommitSnapshots";
        v41 = L"SPRPROVC";
        v42 = 1057;
        v43 = 2;
        v44 = 255;
        v46 = 0x1000000;
        memset_0(v45, 0, sizeof(v45));
        CVssFunctionTracer::Trace(&v50, &v39, L"Snapshot postcommitted");
        CVssQueuedSnapshot::MarkAsPostCommitted(v12);
      }
      else if ( v9->m_eStatus != VSS_SS_POSTCOMMITTED )
      {
        m_eStatus = CVssQueuedSnapshot::GetSnapshotProperties(v8)->m_eStatus;
        v39 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
        v40 = L"CVsSoftwareProvider::PostCommitSnapshots";
        v41 = L"SPRPROVC";
        v42 = 1077;
        v43 = 2;
        v44 = 255;
        v46 = 0x1000000;
        memset_0(v45, 0, sizeof(v45));
        LODWORD(v15) = m_eStatus;
        CVssFunctionTracer::TranslateGenericError(&v50, &v39, 2147549183LL, L"bad state %d", v15);
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v47);
      v4 = a2;
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v47);
    CVssAutomaticLock2::~CVssAutomaticLock2(v57);
  }
  catch ( long v48 )
  {
    CVssFunctionTracer::HandleHresultException(
      (CVssFunctionTracer *)&v50,
      v48,
      L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx",
      L"SPRPROVC",
      L"CVsSoftwareProvider::PostCommitSnapshots",
      0x439u,
      v52);
  }
  catch ( _com_error *v55 )
  {
    CVssFunctionTracer::HandleComException(
      (CVssFunctionTracer *)&v50,
      v55,
      L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx",
      L"SPRPROVC",
      L"CVsSoftwareProvider::PostCommitSnapshots",
      0x439u,
      v52);
  }
  catch ( std::bad_alloc )
  {
    CVssFunctionTracer::HandleStdBadAllocException(
      (CVssFunctionTracer *)&v50,
      L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx",
      L"SPRPROVC",
      L"CVsSoftwareProvider::PostCommitSnapshots",
      0x439u,
      v52);
  }
  catch ( const std::exception *v56 )
  {
    CVssFunctionTracer::HandleStdGenericException(
      (CVssFunctionTracer *)&v50,
      v56,
      L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx",
      L"SPRPROVC",
      L"CVsSoftwareProvider::PostCommitSnapshots",
      0x439u,
      v52);
  }
  v13 = v51;
  CVssFunctionTracer::~CVssFunctionTracer(&v50);
  return v13;
}

```

## disassembly

```asm
0x180013080  mov     rax, rsp
0x180013083  mov     [rax+18h], r8d
0x180013087  mov     [rax+10h], rdx
0x18001308b  mov     [rax+8], rcx
0x18001308f  push    rbx
0x180013090  push    rsi
0x180013091  push    rdi
0x180013092  push    r12
0x180013094  push    r13
0x180013096  push    r14
0x180013098  push    r15
0x18001309a  sub     rsp, 260h
0x1800130a1  mov     r15d, r8d
0x1800130a4  mov     r14, rdx
0x1800130a7  lea     r13, aBaseStorVssMod_9; "base\\stor\\vss\\modules\\softprv\\src"...
0x1800130ae  mov     [rax-1A8h], r13
0x1800130b5  lea     rbx, aCvssoftwarepro_13; "CVsSoftwareProvider::PostCommitSnapshot"...
0x1800130bc  mov     [rax-1A0h], rbx
0x1800130c3  lea     rdi, aSprprovc; "SPRPROVC"
0x1800130ca  mov     [rax-198h], rdi
0x1800130d1  mov     dword ptr [rax-190h], 3D4h
0x1800130db  mov     esi, 2
0x1800130e0  mov     [rax-18Ch], esi
0x1800130e6  mov     dword ptr [rax-188h], 0FFh
0x1800130f0  mov     dword ptr [rax-108h], 1000000h
0x1800130fa  xor     edx, edx; Val
0x1800130fc  lea     r8d, [rsi+76h]; Size
0x180013100  lea     rcx, [rax-180h]; void *
0x180013107  call    memset_0
0x18001310c  xor     r8d, r8d
0x18001310f  lea     rdx, [rsp+298h+var_1A8]
0x180013117  lea     rcx, [rsp+298h+var_E8]
0x18001311f  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x180013124  nop
0x180013125  call    ?IsInGroup@@YA_NK_N@Z; IsInGroup(ulong,bool)
0x18001312a  mov     [rsp+298h+var_1A8], r13
0x180013132  mov     [rsp+298h+var_1A0], rbx
0x18001313a  mov     [rsp+298h+var_198], rdi
0x180013142  mov     [rsp+298h+var_18C], esi
0x180013149  mov     [rsp+298h+var_188], 0FFh
0x180013154  mov     [rsp+298h+var_108], 1000000h
0x18001315f  xor     edx, edx; Val
0x180013161  lea     r8d, [rsi+76h]; Size
0x180013165  lea     rcx, [rsp+298h+var_180]; void *
0x18001316d  test    al, al
0x18001316f  jnz     short loc_1800131A3
0x180013171  mov     [rsp+298h+var_190], 3DBh
0x18001317c  call    memset_0
0x180013181  lea     r9, aTheClientProce_0; "The client process is not running under"...
0x180013188  mov     r8d, 80070005h
0x18001318e  lea     rdx, [rsp+298h+var_1A8]
0x180013196  lea     rcx, [rsp+298h+var_E8]
0x18001319e  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x1800131a3  mov     [rsp+298h+var_190], 3DEh
0x1800131ae  call    memset_0
0x1800131b3  movzx   eax, byte ptr [r14+0Fh]
0x1800131b8  movzx   ecx, byte ptr [r14+0Eh]
0x1800131bd  movzx   edx, byte ptr [r14+0Dh]
0x1800131c2  movzx   r8d, byte ptr [r14+0Ch]
0x1800131c7  movzx   r9d, byte ptr [r14+0Bh]
0x1800131cc  movzx   r10d, byte ptr [r14+0Ah]
0x1800131d1  movzx   r11d, byte ptr [r14+9]
0x1800131d6  movzx   ebx, byte ptr [r14+8]
0x1800131db  movzx   edi, word ptr [r14+6]
0x1800131e0  movzx   esi, word ptr [r14+4]
0x1800131e5  mov     dword ptr [rsp+298h+var_228], r15d
0x1800131ea  mov     dword ptr [rsp+298h+var_230], eax
0x1800131ee  mov     dword ptr [rsp+298h+var_238], ecx
0x1800131f2  mov     dword ptr [rsp+298h+var_240], edx
0x1800131f6  mov     dword ptr [rsp+298h+var_248], r8d
0x1800131fb  mov     dword ptr [rsp+298h+var_250], r9d
0x180013200  mov     dword ptr [rsp+298h+var_258], r10d
0x180013205  mov     dword ptr [rsp+298h+var_260], r11d
0x18001320a  mov     dword ptr [rsp+298h+var_268], ebx
0x18001320e  mov     dword ptr [rsp+298h+var_270], edi
0x180013212  mov     dword ptr [rsp+298h+var_278], esi
0x180013216  mov     r9d, [r14]
0x180013219  lea     r8, aParametersSnap_0; "Parameters: \n  SnapshotSetId = {%.8x-%"...
0x180013220  lea     rdx, [rsp+298h+var_1A8]
0x180013228  lea     rcx, [rsp+298h+var_E8]
0x180013230  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x180013235  mov     r8d, 10h; Size
0x18001323b  lea     rdx, GUID_NULL; Buf2
0x180013242  mov     rcx, r14; Buf1
0x180013245  call    memcmp_0
0x18001324a  test    eax, eax
0x18001324c  jnz     loc_1800132D9
0x180013252  mov     [rsp+298h+var_1A8], r13
0x18001325a  lea     rax, aCvssoftwarepro_13; "CVsSoftwareProvider::PostCommitSnapshot"...
0x180013261  mov     [rsp+298h+var_1A0], rax
0x180013269  lea     rax, aSprprovc; "SPRPROVC"
0x180013270  mov     [rsp+298h+var_198], rax
0x180013278  mov     [rsp+298h+var_190], 3E6h
0x180013283  mov     [rsp+298h+var_18C], 2
0x18001328e  mov     [rsp+298h+var_188], 0FFh
0x180013299  mov     [rsp+298h+var_108], 1000000h
0x1800132a4  xor     edx, edx; Val
0x1800132a6  lea     r8d, [rdx+78h]; Size
0x1800132aa  lea     rcx, [rsp+298h+var_180]; void *
0x1800132b2  call    memset_0
0x1800132b7  lea     r9, aSnapshotsetidG; "SnapshotSetId == GUID_NULL"
0x1800132be  mov     r8d, 80070057h
0x1800132c4  lea     rdx, [rsp+298h+var_1A8]
0x1800132cc  lea     rcx, [rsp+298h+var_E8]
0x1800132d4  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x1800132d9  test    r15d, r15d
0x1800132dc  jns     loc_180013369
0x1800132e2  mov     [rsp+298h+var_1A8], r13
0x1800132ea  lea     rax, aCvssoftwarepro_13; "CVsSoftwareProvider::PostCommitSnapshot"...
0x1800132f1  mov     [rsp+298h+var_1A0], rax
0x1800132f9  lea     rax, aSprprovc; "SPRPROVC"
0x180013300  mov     [rsp+298h+var_198], rax
0x180013308  mov     [rsp+298h+var_190], 3E8h
0x180013313  mov     [rsp+298h+var_18C], 2
0x18001331e  mov     [rsp+298h+var_188], 0FFh
0x180013329  mov     [rsp+298h+var_108], 1000000h
0x180013334  xor     edx, edx; Val
0x180013336  lea     r8d, [rdx+78h]; Size
0x18001333a  lea     rcx, [rsp+298h+var_180]; void *
0x180013342  call    memset_0
0x180013347  lea     r9, aLsnapshotscoun; "lSnapshotsCount < 0"
0x18001334e  mov     r8d, 80070057h
0x180013354  lea     rdx, [rsp+298h+var_1A8]
0x18001335c  lea     rcx, [rsp+298h+var_E8]
0x180013364  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x180013369  lea     rdx, ?m_cs@CVsSoftwareProvider@@0VCVssCriticalSection@@A; struct CVssCriticalSection *
0x180013370  lea     rcx, [rsp+298h+var_48]; this
0x180013378  call    ??0CVssAutomaticLock2@@QEAA@AEAVCVssCriticalSection@@@Z; CVssAutomaticLock2::CVssAutomaticLock2(CVssCriticalSection &)
0x18001337d  nop
0x18001337e  mov     [rsp+298h+var_1A8], r13
0x180013386  lea     rdi, aCvssoftwarepro_13; "CVsSoftwareProvider::PostCommitSnapshot"...
0x18001338d  mov     [rsp+298h+var_1A0], rdi
0x180013395  lea     rsi, aSprprovc; "SPRPROVC"
0x18001339c  mov     [rsp+298h+var_198], rsi
0x1800133a4  mov     [rsp+298h+var_190], 3ECh
0x1800133af  mov     [rsp+298h+var_18C], 2
0x1800133ba  mov     [rsp+298h+var_188], 0FFh
0x1800133c5  mov     [rsp+298h+var_108], 1000000h
0x1800133d0  mov     r15d, 78h ; 'x'
0x1800133d6  mov     r8d, r15d; Size
0x1800133d9  xor     edx, edx; Val
0x1800133db  lea     rcx, [rsp+298h+var_180]; void *
0x1800133e3  call    memset_0
0x1800133e8  mov     r8d, 198h
0x1800133ee  lea     rdx, [rsp+298h+var_1A8]
0x1800133f6  lea     rcx, [rsp+298h+var_E8]
0x1800133fe  call    ?AddOperation@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@IZZ; CVssFunctionTracer::AddOperation(CVssDebugInfo,uint,...)
0x180013403  mov     [rsp+298h+var_1A8], r13
0x18001340b  mov     [rsp+298h+var_1A0], rdi
0x180013413  mov     [rsp+298h+var_198], rsi
0x18001341b  mov     [rsp+298h+var_190], 3EDh
0x180013426  mov     [rsp+298h+var_18C], 2
0x180013431  mov     [rsp+298h+var_188], 0FFh
0x18001343c  mov     [rsp+298h+var_108], 1000000h
0x180013447  mov     r8d, r15d; Size
0x18001344a  xor     edx, edx; Val
0x18001344c  lea     rcx, [rsp+298h+var_180]; void *
0x180013454  call    memset_0
0x180013459  lea     r9, aSystemProvider; "System Provider"
0x180013460  mov     r8d, 1394h
0x180013466  lea     rdx, [rsp+298h+var_1A8]
0x18001346e  lea     rcx, [rsp+298h+var_E8]
0x180013476  call    ?AddContext@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@IPEBG@Z; CVssFunctionTracer::AddContext(CVssDebugInfo,uint,ushort const *)
0x18001347b  lea     rax, ?m_list@CVssQueuedSnapshot@@0V?$CVssDLList@PEAVCVssQueuedSnapshot@@@@A; CVssDLList<CVssQueuedSnapshot *> CVssQueuedSnapshot::m_list
0x180013482  mov     [rsp+298h+var_68], rax
0x18001348a  mov     rax, cs:?m_list@CVssQueuedSnapshot@@0V?$CVssDLList@PEAVCVssQueuedSnapshot@@@@A; CVssDLList<CVssQueuedSnapshot *> CVssQueuedSnapshot::m_list
0x180013491  mov     [rsp+298h+var_60], rax
0x180013499  movups  xmm0, xmmword ptr [r14]
0x18001349d  movdqu  xmmword ptr [rsp+298h+var_78.Data1], xmm0
0x1800134a6  lea     rdx, [rsp+298h+var_78]; struct _GUID
0x1800134ae  lea     rcx, [rsp+298h+var_68]; this
0x1800134b6  call    ?GetNextBySnapshotSet@CVssSnapIterator@@QEAAPEAVCVssQueuedSnapshot@@U_GUID@@@Z; CVssSnapIterator::GetNextBySnapshotSet(_GUID)
0x1800134bb  mov     rbx, rax
0x1800134be  mov     [rsp+298h+var_F0], rax
0x1800134c6  mov     [rsp+298h+var_100], rax
0x1800134ce  test    rax, rax
0x1800134d1  jz      short loc_1800134E3
0x1800134d3  mov     rax, [rax]
0x1800134d6  mov     rcx, rbx
0x1800134d9  mov     rax, [rax+8]
0x1800134dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800134e2  nop
0x1800134e3  test    rbx, rbx
0x1800134e6  jnz     short loc_180013509
0x1800134e8  lea     rcx, [rsp+298h+var_100]
0x1800134f0  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800134f5  nop
0x1800134f6  lea     rcx, [rsp+298h+var_48]; this
0x1800134fe  call    ??1CVssAutomaticLock2@@QEAA@XZ; CVssAutomaticLock2::~CVssAutomaticLock2(void)
0x180013503  nop
0x180013504  jmp     loc_18001388A
0x180013509  mov     rcx, rbx; this
0x18001350c  call    ?GetSnapshotProperties@CVssQueuedSnapshot@@QEAAPEAU_VSS_SNAPSHOT_PROP@@XZ; CVssQueuedSnapshot::GetSnapshotProperties(void)
0x180013511  mov     r13, rax
0x180013514  mov     [rsp+298h+arg_18], rax
0x18001351c  lea     rax, aBaseStorVssMod_9; "base\\stor\\vss\\modules\\softprv\\src"...
0x180013523  mov     [rsp+298h+var_1A8], rax
0x18001352b  mov     [rsp+298h+var_1A0], rdi
0x180013533  mov     [rsp+298h+var_198], rsi
0x18001353b  mov     [rsp+298h+var_190], 402h
0x180013546  mov     [rsp+298h+var_18C], 2
0x180013551  mov     [rsp+298h+var_188], 0FFh
0x18001355c  mov     [rsp+298h+var_108], 1000000h
0x180013567  mov     r8, r15; Size
0x18001356a  xor     edx, edx; Val
0x18001356c  lea     rcx, [rsp+298h+var_180]; void *
0x180013574  call    memset_0
0x180013579  movzx   ecx, byte ptr [r13+0Fh]
0x18001357e  movzx   edx, byte ptr [r13+0Eh]
0x180013583  movzx   r8d, byte ptr [r13+0Dh]
0x180013588  movzx   r9d, byte ptr [r13+0Ch]
0x18001358d  movzx   r10d, byte ptr [r13+0Bh]
0x180013592  movzx   r11d, byte ptr [r13+0Ah]
0x180013597  movzx   edi, byte ptr [r13+9]
0x18001359c  movzx   esi, byte ptr [r13+8]
0x1800135a1  movzx   r14d, word ptr [r13+6]
0x1800135a6  movzx   r15d, word ptr [r13+4]
0x1800135ab  movzx   r12d, byte ptr [r13+1Fh]
0x1800135b0  movzx   r13d, byte ptr [r13+1Eh]
0x1800135b5  mov     rax, [rsp+298h+arg_18]
0x1800135bd  mov     eax, [rax+78h]
0x1800135c0  mov     dword ptr [rsp+298h+var_1B0], eax
0x1800135c7  mov     rax, [rsp+298h+arg_18]
0x1800135cf  mov     eax, [rax+68h]
0x1800135d2  mov     dword ptr [rsp+298h+var_1B8], eax
0x1800135d9  mov     rax, [rsp+298h+arg_18]
0x1800135e1  mov     rax, [rax+70h]
0x1800135e5  mov     [rsp+298h+var_1C0], rax
0x1800135ed  mov     rax, [rsp+298h+arg_18]
0x1800135f5  mov     rax, [rax+30h]
0x1800135f9  mov     [rsp+298h+var_1C8], rax
0x180013601  mov     dword ptr [rsp+298h+var_1D0], ecx
0x180013608  mov     dword ptr [rsp+298h+var_1D8], edx
0x18001360f  mov     dword ptr [rsp+298h+var_1E0], r8d
0x180013617  mov     dword ptr [rsp+298h+var_1E8], r9d
0x18001361f  mov     dword ptr [rsp+298h+var_1F0], r10d
0x180013627  mov     dword ptr [rsp+298h+var_1F8], r11d
0x18001362f  mov     dword ptr [rsp+298h+var_200], edi
0x180013636  mov     dword ptr [rsp+298h+var_208], esi
0x18001363d  mov     dword ptr [rsp+298h+var_210], r14d
0x180013645  mov     dword ptr [rsp+298h+var_218], r15d
0x18001364d  mov     rdi, [rsp+298h+arg_18]
0x180013655  mov     eax, [rdi]
0x180013657  mov     dword ptr [rsp+298h+var_220], eax
0x18001365b  mov     dword ptr [rsp+298h+var_228], r12d
0x180013660  mov     dword ptr [rsp+298h+var_230], r13d
0x180013665  movzx   eax, byte ptr [rdi+1Dh]
0x180013669  mov     dword ptr [rsp+298h+var_238], eax
0x18001366d  movzx   eax, byte ptr [rdi+1Ch]
0x180013671  mov     dword ptr [rsp+298h+var_240], eax
0x180013675  movzx   eax, byte ptr [rdi+1Bh]
0x180013679  mov     dword ptr [rsp+298h+var_248], eax
0x18001367d  movzx   eax, byte ptr [rdi+1Ah]
0x180013681  mov     dword ptr [rsp+298h+var_250], eax
0x180013685  movzx   eax, byte ptr [rdi+19h]
0x180013689  mov     dword ptr [rsp+298h+var_258], eax
0x18001368d  movzx   eax, byte ptr [rdi+18h]
0x180013691  mov     dword ptr [rsp+298h+var_260], eax
0x180013695  movzx   eax, word ptr [rdi+16h]
0x180013699  mov     dword ptr [rsp+298h+var_268], eax
0x18001369d  movzx   eax, word ptr [rdi+14h]
0x1800136a1  mov     dword ptr [rsp+298h+var_270], eax
0x1800136a5  mov     eax, [rdi+10h]
0x1800136a8  mov     dword ptr [rsp+298h+var_278], eax
0x1800136ac  mov     r9, rdi
0x1800136af  lea     r8, aFieldValuesFor_0; "Field values for %p: \n  SnapshotSetId "...
0x1800136b6  lea     rdx, [rsp+298h+var_1A8]
0x1800136be  lea     rcx, [rsp+298h+var_E8]
0x1800136c6  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x1800136cb  mov     rbx, [rsp+298h+var_F0]
0x1800136d3  mov     rcx, rbx; this
0x1800136d6  call    ?GetSnapshotProperties@CVssQueuedSnapshot@@QEAAPEAU_VSS_SNAPSHOT_PROP@@XZ; CVssQueuedSnapshot::GetSnapshotProperties(void)
0x1800136db  cmp     dword ptr [rax+78h], 7
0x1800136df  jz      loc_18001378C
0x1800136e5  cmp     dword ptr [rax+78h], 0Fh
0x1800136e9  jz      loc_180013856
0x1800136ef  mov     rcx, rbx; this
0x1800136f2  call    ?GetSnapshotProperties@CVssQueuedSnapshot@@QEAAPEAU_VSS_SNAPSHOT_PROP@@XZ; CVssQueuedSnapshot::GetSnapshotProperties(void)
0x1800136f7  mov     ebx, [rax+78h]
0x1800136fa  lea     rax, aBaseStorVssMod_9; "base\\stor\\vss\\modules\\softprv\\src"...
0x180013701  mov     [rsp+298h+var_1A8], rax
0x180013709  lea     rax, aCvssoftwarepro_13; "CVsSoftwareProvider::PostCommitSnapshot"...
0x180013710  mov     [rsp+298h+var_1A0], rax
0x180013718  lea     rax, aSprprovc; "SPRPROVC"
0x18001371f  mov     [rsp+298h+var_198], rax
0x180013727  mov     [rsp+298h+var_190], 435h
0x180013732  mov     [rsp+298h+var_18C], 2
0x18001373d  mov     [rsp+298h+var_188], 0FFh
0x180013748  mov     [rsp+298h+var_108], 1000000h
0x180013753  xor     edx, edx; Val
0x180013755  lea     r8d, [rdx+78h]; Size
0x180013759  lea     rcx, [rsp+298h+var_180]; void *
0x180013761  call    memset_0
0x180013766  mov     dword ptr [rsp+298h+var_278], ebx
0x18001376a  lea     r9, aBadStateD; "bad state %d"
0x180013771  mov     r8d, 8000FFFFh
0x180013777  lea     rdx, [rsp+298h+var_1A8]
0x18001377f  lea     rcx, [rsp+298h+var_E8]
0x180013787  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x18001378c  mov     rcx, rbx; this
  ... truncated ...
```
