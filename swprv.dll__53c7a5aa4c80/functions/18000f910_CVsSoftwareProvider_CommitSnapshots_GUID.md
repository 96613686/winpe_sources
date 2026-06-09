# CVsSoftwareProvider::CommitSnapshots(_GUID)

- ea: `0x18000f910`
- end: `0x18000ffcc`
- name: `?CommitSnapshots@CVsSoftwareProvider@@UEAAJU_GUID@@@Z`
- size: `1724`
- prototype: `__int64 __fastcall(CVsSoftwareProvider *this, struct _GUID *)`
- caller_count: `0`
- callee_count: `20`
- tags: `broker_com_uri`

## callees

- `0x18000212c`
- `0x1800034cc`
- `0x1800036c4`
- `0x180003888`
- `0x18000f910`
- `0x180019008`
- `0x180019334`
- `0x180019458`
- `0x180019570`
- `0x18001995c`
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

- `0x18000f93a`: `CVsSoftwareProvider::CommitSnapshots`
- `0x18000fcef`: `CVsSoftwareProvider::CommitSnapshots`
- `0x18000fed4`: `CVsSoftwareProvider::CommitSnapshots`

## pseudocode

```c
__int64 __fastcall CVsSoftwareProvider::CommitSnapshots(CVsSoftwareProvider *this, struct _GUID *a2)
{
  struct _GUID *v2; // r14
  bool v3; // dl
  unsigned int v4; // ecx
  int v5; // eax
  CVssQueuedSnapshot *NextBySnapshotSet; // rax
  CVssQueuedSnapshot *v7; // rbx
  CVssQueuedSnapshot *v8; // rbx
  struct _VSS_SNAPSHOT_PROP *v9; // rax
  VSS_SNAPSHOT_STATE m_eStatus; // ebx
  unsigned int v11; // ebx
  __int64 v13; // [rsp+20h] [rbp-278h]
  __int64 v14; // [rsp+28h] [rbp-270h]
  __int64 v15; // [rsp+30h] [rbp-268h]
  __int64 v16; // [rsp+38h] [rbp-260h]
  __int64 v17; // [rsp+40h] [rbp-258h]
  __int64 v18; // [rsp+48h] [rbp-250h]
  __int64 v19; // [rsp+50h] [rbp-248h]
  __int64 v20; // [rsp+58h] [rbp-240h]
  __int64 v21; // [rsp+60h] [rbp-238h]
  __int64 v22; // [rsp+68h] [rbp-230h]
  __int64 v23; // [rsp+70h] [rbp-228h]
  __int64 v24; // [rsp+78h] [rbp-220h]
  __int64 v25; // [rsp+80h] [rbp-218h]
  __int64 v26; // [rsp+88h] [rbp-210h]
  __int64 v27; // [rsp+90h] [rbp-208h]
  __int64 v28; // [rsp+98h] [rbp-200h]
  __int64 v29; // [rsp+A0h] [rbp-1F8h]
  __int64 v30; // [rsp+A8h] [rbp-1F0h]
  __int64 v31; // [rsp+B0h] [rbp-1E8h]
  __int64 v32; // [rsp+B8h] [rbp-1E0h]
  __int64 v33; // [rsp+C0h] [rbp-1D8h]
  __int64 v34; // [rsp+C8h] [rbp-1D0h]
  __int64 v35; // [rsp+E0h] [rbp-1B8h]
  __int64 v36; // [rsp+E8h] [rbp-1B0h]
  const unsigned __int16 *v37; // [rsp+F0h] [rbp-1A8h] BYREF
  const unsigned __int16 *v38; // [rsp+F8h] [rbp-1A0h]
  const unsigned __int16 *v39; // [rsp+100h] [rbp-198h]
  int v40; // [rsp+108h] [rbp-190h]
  int v41; // [rsp+10Ch] [rbp-18Ch]
  int v42; // [rsp+110h] [rbp-188h]
  _BYTE v43[120]; // [rsp+118h] [rbp-180h] BYREF
  int v44; // [rsp+190h] [rbp-108h]
  int v45; // [rsp+198h] [rbp-100h] BYREF
  CVssQueuedSnapshot *v46; // [rsp+1A0h] [rbp-F8h]
  struct _GUID v47; // [rsp+1B0h] [rbp-E8h] BYREF
  _QWORD v48[2]; // [rsp+1C0h] [rbp-D8h] BYREF
  LPVOID v49; // [rsp+1D0h] [rbp-C8h] BYREF
  unsigned int v50; // [rsp+1D8h] [rbp-C0h]
  unsigned int v51; // [rsp+1F4h] [rbp-A4h]
  _com_error *v52; // [rsp+240h] [rbp-58h] BYREF
  const std::exception *v53; // [rsp+248h] [rbp-50h] BYREF
  LPCRITICAL_SECTION v54[9]; // [rsp+250h] [rbp-48h] BYREF
  struct _VSS_SNAPSHOT_PROP *SnapshotProperties; // [rsp+2B0h] [rbp+18h]
  CVssQueuedSnapshot *v57; // [rsp+2B8h] [rbp+20h] BYREF

  v2 = a2;
  v37 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
  v38 = L"CVsSoftwareProvider::CommitSnapshots";
  v39 = L"SPRPROVC";
  v40 = 839;
  v41 = 2;
  v42 = 255;
  v44 = 0x1000000;
  memset_0(v43, 0, sizeof(v43));
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v49, (__int64)&v37, 0);
  try
  {
    if ( !IsInGroup(v4, v3) )
    {
      v37 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
      v38 = L"CVsSoftwareProvider::CommitSnapshots";
      v39 = L"SPRPROVC";
      v40 = 845;
      v41 = 2;
      v42 = 255;
      v44 = 0x1000000;
      memset_0(v43, 0, sizeof(v43));
      CVssFunctionTracer::Throw(
        &v49,
        &v37,
        2147942405LL,
        L"The client process is not running under an administrator account");
    }
    v5 = memcmp_0(v2, &GUID_NULL, 0x10u);
    v37 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
    v38 = L"CVsSoftwareProvider::CommitSnapshots";
    v39 = L"SPRPROVC";
    v41 = 2;
    v42 = 255;
    v44 = 0x1000000;
    if ( !v5 )
    {
      v40 = 850;
      memset_0(v43, 0, sizeof(v43));
      CVssFunctionTracer::Throw(&v49, &v37, 2147942487LL, L"SnapshotSetId == GUID_NULL");
    }
    v40 = 853;
    memset_0(v43, 0, sizeof(v43));
    CVssFunctionTracer::Trace(
      &v49,
      &v37,
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
      (CVssAutomaticLock2 *)v54,
      (struct CVssCriticalSection *)CVsSoftwareProvider::m_cs);
    v37 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
    v38 = L"CVsSoftwareProvider::CommitSnapshots";
    v39 = L"SPRPROVC";
    v40 = 859;
    v41 = 2;
    v42 = 255;
    v44 = 0x1000000;
    memset_0(v43, 0, sizeof(v43));
    CVssFunctionTracer::AddOperation((struct CVssFunctionTracer *)&v49, (const struct CVssDebugInfo *)&v37, 433);
    v37 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
    v38 = L"CVsSoftwareProvider::CommitSnapshots";
    v39 = L"SPRPROVC";
    v40 = 860;
    v41 = 2;
    v42 = 255;
    v44 = 0x1000000;
    memset_0(v43, 0, sizeof(v43));
    CVssFunctionTracer::AddContext((__int64)&v49, (const struct CVssDebugInfo *)&v37);
    v48[0] = &CVssQueuedSnapshot::m_list;
    v48[1] = CVssQueuedSnapshot::m_list;
    while ( 1 )
    {
      v47 = *v2;
      NextBySnapshotSet = CVssSnapIterator::GetNextBySnapshotSet((CVssSnapIterator *)v48, &v47);
      v7 = NextBySnapshotSet;
      v46 = NextBySnapshotSet;
      v57 = NextBySnapshotSet;
      if ( NextBySnapshotSet )
        (*(void (__fastcall **)(CVssQueuedSnapshot *))(*(_QWORD *)NextBySnapshotSet + 8LL))(NextBySnapshotSet);
      if ( !v7 )
        break;
      SnapshotProperties = CVssQueuedSnapshot::GetSnapshotProperties(v7);
      v37 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
      v38 = L"CVsSoftwareProvider::CommitSnapshots";
      v39 = L"SPRPROVC";
      v40 = 880;
      v41 = 2;
      v42 = 255;
      v44 = 0x1000000;
      memset_0(v43, 0, sizeof(v43));
      LODWORD(v36) = SnapshotProperties->m_eStatus;
      LODWORD(v35) = SnapshotProperties->m_lSnapshotAttributes;
      LODWORD(v34) = SnapshotProperties->m_SnapshotId.Data4[7];
      LODWORD(v33) = SnapshotProperties->m_SnapshotId.Data4[6];
      LODWORD(v32) = SnapshotProperties->m_SnapshotId.Data4[5];
      LODWORD(v31) = SnapshotProperties->m_SnapshotId.Data4[4];
      LODWORD(v30) = SnapshotProperties->m_SnapshotId.Data4[3];
      LODWORD(v29) = SnapshotProperties->m_SnapshotId.Data4[2];
      LODWORD(v28) = SnapshotProperties->m_SnapshotId.Data4[1];
      LODWORD(v27) = SnapshotProperties->m_SnapshotId.Data4[0];
      LODWORD(v26) = SnapshotProperties->m_SnapshotId.Data3;
      LODWORD(v25) = SnapshotProperties->m_SnapshotId.Data2;
      LODWORD(v24) = SnapshotProperties->m_SnapshotId.Data1;
      LODWORD(v23) = SnapshotProperties->m_SnapshotSetId.Data4[7];
      LODWORD(v22) = SnapshotProperties->m_SnapshotSetId.Data4[6];
      LODWORD(v21) = SnapshotProperties->m_SnapshotSetId.Data4[5];
      LODWORD(v20) = SnapshotProperties->m_SnapshotSetId.Data4[4];
      LODWORD(v19) = SnapshotProperties->m_SnapshotSetId.Data4[3];
      LODWORD(v18) = SnapshotProperties->m_SnapshotSetId.Data4[2];
      LODWORD(v17) = SnapshotProperties->m_SnapshotSetId.Data4[1];
      LODWORD(v16) = SnapshotProperties->m_SnapshotSetId.Data4[0];
      LODWORD(v15) = SnapshotProperties->m_SnapshotSetId.Data3;
      LODWORD(v14) = SnapshotProperties->m_SnapshotSetId.Data2;
      LODWORD(v13) = SnapshotProperties->m_SnapshotSetId.Data1;
      CVssFunctionTracer::Trace(
        &v49,
        &v37,
        L"Field values for %p: \n"
         "  SnapshotSetId = {%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}\n"
         "  SnapshotId = {%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}\n"
         "  VolumeName = %s\n"
         "  Creation timestamp = 0x%016I64x\n"
         "  lAttributes = 0x%08lx\n"
         "  status = %d\n",
        SnapshotProperties,
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
        v33,
        v34,
        SnapshotProperties->m_pwszOriginalVolumeName,
        SnapshotProperties->m_tsCreationTimestamp,
        v35,
        v36);
      v8 = v46;
      v9 = CVssQueuedSnapshot::GetSnapshotProperties(v46);
      if ( v9->m_eStatus == VSS_SS_PRECOMMITTED )
      {
        CVssQueuedSnapshot::MarkAsProcessingCommit(v8);
        CVssQueuedSnapshot::CommitSnapshotIoctl(v8);
        CVssQueuedSnapshot::MarkAsCommitted(v8);
      }
      else if ( v9->m_eStatus != VSS_SS_COMMITTED )
      {
        m_eStatus = CVssQueuedSnapshot::GetSnapshotProperties(v8)->m_eStatus;
        v37 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
        v38 = L"CVsSoftwareProvider::CommitSnapshots";
        v39 = L"SPRPROVC";
        v40 = 919;
        v41 = 2;
        v42 = 255;
        v44 = 0x1000000;
        memset_0(v43, 0, sizeof(v43));
        LODWORD(v13) = m_eStatus;
        CVssFunctionTracer::TranslateGenericError(&v49, &v37, 2147549183LL, L"bad state %d", v13);
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v57);
      v2 = a2;
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v57);
    CVssAutomaticLock2::~CVssAutomaticLock2(v54);
  }
  catch ( long v45 )
  {
    CVssFunctionTracer::HandleHresultException(
      (CVssFunctionTracer *)&v49,
      v45,
      L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx",
      L"SPRPROVC",
      L"CVsSoftwareProvider::CommitSnapshots",
      0x39Bu,
      v51);
  }
  catch ( _com_error *v52 )
  {
    CVssFunctionTracer::HandleComException(
      (CVssFunctionTracer *)&v49,
      v52,
      L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx",
      L"SPRPROVC",
      L"CVsSoftwareProvider::CommitSnapshots",
      0x39Bu,
      v51);
  }
  catch ( std::bad_alloc )
  {
    CVssFunctionTracer::HandleStdBadAllocException(
      (CVssFunctionTracer *)&v49,
      L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx",
      L"SPRPROVC",
      L"CVsSoftwareProvider::CommitSnapshots",
      0x39Bu,
      v51);
  }
  catch ( const std::exception *v53 )
  {
    CVssFunctionTracer::HandleStdGenericException(
      (CVssFunctionTracer *)&v49,
      v53,
      L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx",
      L"SPRPROVC",
      L"CVsSoftwareProvider::CommitSnapshots",
      0x39Bu,
      v51);
  }
  if ( !IsInGroup(v4, v3) )
  {
    v37 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
    v38 = L"CVsSoftwareProvider::CommitSnapshots";
    v39 = L"SPRPROVC";
    v40 = 845;
    v41 = 2;
    v42 = 255;
    v44 = 0x1000000;
    memset_0(v43, 0, sizeof(v43));
    CVssFunctionTracer::Throw(
      &v49,
      &v37,
      2147942405LL,
      L"The client process is not running under an administrator account");
  }
  v5 = memcmp_0(v2, &GUID_NULL, 0x10u);
  v37 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
}

```

## disassembly

```asm
0x18000f910  mov     rax, rsp
0x18000f913  mov     [rax+10h], rdx
0x18000f917  push    rbx
0x18000f918  push    rsi
0x18000f919  push    rdi
0x18000f91a  push    r12
0x18000f91c  push    r13
0x18000f91e  push    r14
0x18000f920  push    r15
0x18000f922  sub     rsp, 260h
0x18000f929  mov     r14, rdx
0x18000f92c  lea     r12, aBaseStorVssMod_9; "base\\stor\\vss\\modules\\softprv\\src"...
0x18000f933  mov     [rax-1A8h], r12
0x18000f93a  lea     r13, aCvssoftwarepro_17; "CVsSoftwareProvider::CommitSnapshots"
0x18000f941  mov     [rax-1A0h], r13
0x18000f948  lea     rbx, aSprprovc; "SPRPROVC"
0x18000f94f  mov     [rax-198h], rbx
0x18000f956  mov     dword ptr [rax-190h], 347h
0x18000f960  mov     edi, 2
0x18000f965  mov     [rax-18Ch], edi
0x18000f96b  mov     esi, 0FFh
0x18000f970  mov     [rax-188h], esi
0x18000f976  mov     dword ptr [rax-108h], 1000000h
0x18000f980  xor     edx, edx; Val
0x18000f982  lea     r8d, [rdi+76h]; Size
0x18000f986  lea     rcx, [rax-180h]; void *
0x18000f98d  call    memset_0
0x18000f992  xor     r8d, r8d
0x18000f995  lea     rdx, [rsp+298h+var_1A8]
0x18000f99d  lea     rcx, [rsp+298h+var_C8]
0x18000f9a5  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x18000f9aa  nop
0x18000f9ab  call    ?IsInGroup@@YA_NK_N@Z; IsInGroup(ulong,bool)
0x18000f9b0  test    al, al
0x18000f9b2  jnz     short loc_18000FA25
0x18000f9b4  mov     [rsp+298h+var_1A8], r12
0x18000f9bc  mov     [rsp+298h+var_1A0], r13
0x18000f9c4  mov     [rsp+298h+var_198], rbx
0x18000f9cc  mov     [rsp+298h+var_190], 34Dh
0x18000f9d7  mov     [rsp+298h+var_18C], edi
0x18000f9de  mov     [rsp+298h+var_188], esi
0x18000f9e5  mov     [rsp+298h+var_108], 1000000h
0x18000f9f0  xor     edx, edx; Val
0x18000f9f2  lea     r8d, [rdi+76h]; Size
0x18000f9f6  lea     rcx, [rsp+298h+var_180]; void *
0x18000f9fe  call    memset_0
0x18000fa03  lea     r9, aTheClientProce_0; "The client process is not running under"...
0x18000fa0a  mov     r8d, 80070005h
0x18000fa10  lea     rdx, [rsp+298h+var_1A8]
0x18000fa18  lea     rcx, [rsp+298h+var_C8]
0x18000fa20  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x18000fa25  mov     r8d, 10h; Size
0x18000fa2b  lea     rdx, GUID_NULL; Buf2
0x18000fa32  mov     rcx, r14; Buf1
0x18000fa35  call    memcmp_0
0x18000fa3a  mov     [rsp+298h+var_1A8], r12
0x18000fa42  mov     [rsp+298h+var_1A0], r13
0x18000fa4a  mov     [rsp+298h+var_198], rbx
0x18000fa52  mov     [rsp+298h+var_18C], edi
0x18000fa59  mov     [rsp+298h+var_188], esi
0x18000fa60  mov     [rsp+298h+var_108], 1000000h
0x18000fa6b  xor     edx, edx; Val
0x18000fa6d  lea     r8d, [rdx+78h]; Size
0x18000fa71  lea     rcx, [rsp+298h+var_180]; void *
0x18000fa79  test    eax, eax
0x18000fa7b  jnz     short loc_18000FAAF
0x18000fa7d  mov     [rsp+298h+var_190], 352h
0x18000fa88  call    memset_0
0x18000fa8d  lea     r9, aSnapshotsetidG; "SnapshotSetId == GUID_NULL"
0x18000fa94  mov     r8d, 80070057h
0x18000fa9a  lea     rdx, [rsp+298h+var_1A8]
0x18000faa2  lea     rcx, [rsp+298h+var_C8]
0x18000faaa  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x18000faaf  mov     [rsp+298h+var_190], 355h
0x18000faba  call    memset_0
0x18000fabf  movzx   eax, byte ptr [r14+0Fh]
0x18000fac4  movzx   ecx, byte ptr [r14+0Eh]
0x18000fac9  movzx   edx, byte ptr [r14+0Dh]
0x18000face  movzx   r8d, byte ptr [r14+0Ch]
0x18000fad3  movzx   r9d, byte ptr [r14+0Bh]
0x18000fad8  movzx   r10d, byte ptr [r14+0Ah]
0x18000fadd  movzx   r11d, byte ptr [r14+9]
0x18000fae2  movzx   ebx, byte ptr [r14+8]
0x18000fae7  movzx   edi, word ptr [r14+6]
0x18000faec  movzx   esi, word ptr [r14+4]
0x18000faf1  mov     dword ptr [rsp+298h+var_230], eax
0x18000faf5  mov     dword ptr [rsp+298h+var_238], ecx
0x18000faf9  mov     dword ptr [rsp+298h+var_240], edx
0x18000fafd  mov     dword ptr [rsp+298h+var_248], r8d
0x18000fb02  mov     dword ptr [rsp+298h+var_250], r9d
0x18000fb07  mov     dword ptr [rsp+298h+var_258], r10d
0x18000fb0c  mov     dword ptr [rsp+298h+var_260], r11d
0x18000fb11  mov     dword ptr [rsp+298h+var_268], ebx
0x18000fb15  mov     dword ptr [rsp+298h+var_270], edi
0x18000fb19  mov     dword ptr [rsp+298h+var_278], esi
0x18000fb1d  mov     r9d, [r14]
0x18000fb20  lea     r8, aParametersSnap_5; "Parameters: \n  SnapshotSetId = {%.8x-%"...
0x18000fb27  lea     rdx, [rsp+298h+var_1A8]
0x18000fb2f  lea     rcx, [rsp+298h+var_C8]
0x18000fb37  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x18000fb3c  lea     rdx, ?m_cs@CVsSoftwareProvider@@0VCVssCriticalSection@@A; struct CVssCriticalSection *
0x18000fb43  lea     rcx, [rsp+298h+var_48]; this
0x18000fb4b  call    ??0CVssAutomaticLock2@@QEAA@AEAVCVssCriticalSection@@@Z; CVssAutomaticLock2::CVssAutomaticLock2(CVssCriticalSection &)
0x18000fb50  nop
0x18000fb51  mov     [rsp+298h+var_1A8], r12
0x18000fb59  mov     [rsp+298h+var_1A0], r13
0x18000fb61  lea     rdi, aSprprovc; "SPRPROVC"
0x18000fb68  mov     [rsp+298h+var_198], rdi
0x18000fb70  mov     [rsp+298h+var_190], 35Bh
0x18000fb7b  mov     [rsp+298h+var_18C], 2
0x18000fb86  mov     [rsp+298h+var_188], 0FFh
0x18000fb91  mov     [rsp+298h+var_108], 1000000h
0x18000fb9c  mov     esi, 78h ; 'x'
0x18000fba1  mov     r8d, esi; Size
0x18000fba4  xor     edx, edx; Val
0x18000fba6  lea     rcx, [rsp+298h+var_180]; void *
0x18000fbae  call    memset_0
0x18000fbb3  mov     r8d, 1B1h
0x18000fbb9  lea     rdx, [rsp+298h+var_1A8]
0x18000fbc1  lea     rcx, [rsp+298h+var_C8]
0x18000fbc9  call    ?AddOperation@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@IZZ; CVssFunctionTracer::AddOperation(CVssDebugInfo,uint,...)
0x18000fbce  mov     [rsp+298h+var_1A8], r12
0x18000fbd6  mov     [rsp+298h+var_1A0], r13
0x18000fbde  mov     [rsp+298h+var_198], rdi
0x18000fbe6  mov     [rsp+298h+var_190], 35Ch
0x18000fbf1  mov     [rsp+298h+var_18C], 2
0x18000fbfc  mov     [rsp+298h+var_188], 0FFh
0x18000fc07  mov     [rsp+298h+var_108], 1000000h
0x18000fc12  mov     r8d, esi; Size
0x18000fc15  xor     edx, edx; Val
0x18000fc17  lea     rcx, [rsp+298h+var_180]; void *
0x18000fc1f  call    memset_0
0x18000fc24  lea     r9, aSystemProvider; "System Provider"
0x18000fc2b  mov     r8d, 1394h
0x18000fc31  lea     rdx, [rsp+298h+var_1A8]
0x18000fc39  lea     rcx, [rsp+298h+var_C8]
0x18000fc41  call    ?AddContext@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@IPEBG@Z; CVssFunctionTracer::AddContext(CVssDebugInfo,uint,ushort const *)
0x18000fc46  lea     rax, ?m_list@CVssQueuedSnapshot@@0V?$CVssDLList@PEAVCVssQueuedSnapshot@@@@A; CVssDLList<CVssQueuedSnapshot *> CVssQueuedSnapshot::m_list
0x18000fc4d  mov     [rsp+298h+var_D8], rax
0x18000fc55  mov     rax, cs:?m_list@CVssQueuedSnapshot@@0V?$CVssDLList@PEAVCVssQueuedSnapshot@@@@A; CVssDLList<CVssQueuedSnapshot *> CVssQueuedSnapshot::m_list
0x18000fc5c  mov     [rsp+298h+var_D0], rax
0x18000fc64  movups  xmm0, xmmword ptr [r14]
0x18000fc68  movdqu  xmmword ptr [rsp+298h+var_E8.Data1], xmm0
0x18000fc71  lea     rdx, [rsp+298h+var_E8]; struct _GUID
0x18000fc79  lea     rcx, [rsp+298h+var_D8]; this
0x18000fc81  call    ?GetNextBySnapshotSet@CVssSnapIterator@@QEAAPEAVCVssQueuedSnapshot@@U_GUID@@@Z; CVssSnapIterator::GetNextBySnapshotSet(_GUID)
0x18000fc86  mov     rbx, rax
0x18000fc89  mov     [rsp+298h+var_F8], rax
0x18000fc91  mov     [rsp+298h+arg_18], rax
0x18000fc99  test    rax, rax
0x18000fc9c  jz      short loc_18000FCAE
0x18000fc9e  mov     rax, [rax]
0x18000fca1  mov     rcx, rbx
0x18000fca4  mov     rax, [rax+8]
0x18000fca8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fcad  nop
0x18000fcae  test    rbx, rbx
0x18000fcb1  jnz     short loc_18000FCD4
0x18000fcb3  lea     rcx, [rsp+298h+arg_18]
0x18000fcbb  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000fcc0  nop
0x18000fcc1  lea     rcx, [rsp+298h+var_48]; this
0x18000fcc9  call    ??1CVssAutomaticLock2@@QEAA@XZ; CVssAutomaticLock2::~CVssAutomaticLock2(void)
0x18000fcce  nop
0x18000fccf  jmp     loc_18000FFA3
0x18000fcd4  mov     rcx, rbx; this
0x18000fcd7  call    ?GetSnapshotProperties@CVssQueuedSnapshot@@QEAAPEAU_VSS_SNAPSHOT_PROP@@XZ; CVssQueuedSnapshot::GetSnapshotProperties(void)
0x18000fcdc  mov     r13, rax
0x18000fcdf  mov     [rsp+298h+arg_10], rax
0x18000fce7  mov     [rsp+298h+var_1A8], r12
0x18000fcef  lea     rax, aCvssoftwarepro_17; "CVsSoftwareProvider::CommitSnapshots"
0x18000fcf6  mov     [rsp+298h+var_1A0], rax
0x18000fcfe  mov     [rsp+298h+var_198], rdi
0x18000fd06  mov     [rsp+298h+var_190], 370h
0x18000fd11  mov     [rsp+298h+var_18C], 2
0x18000fd1c  mov     [rsp+298h+var_188], 0FFh
0x18000fd27  mov     [rsp+298h+var_108], 1000000h
0x18000fd32  mov     r8, rsi; Size
0x18000fd35  xor     edx, edx; Val
0x18000fd37  lea     rcx, [rsp+298h+var_180]; void *
0x18000fd3f  call    memset_0
0x18000fd44  movzx   ecx, byte ptr [r13+0Fh]
0x18000fd49  movzx   edx, byte ptr [r13+0Eh]
0x18000fd4e  movzx   r8d, byte ptr [r13+0Dh]
0x18000fd53  movzx   r9d, byte ptr [r13+0Ch]
0x18000fd58  movzx   r10d, byte ptr [r13+0Bh]
0x18000fd5d  movzx   r11d, byte ptr [r13+0Ah]
0x18000fd62  movzx   edi, byte ptr [r13+9]
0x18000fd67  movzx   esi, byte ptr [r13+8]
0x18000fd6c  movzx   r14d, word ptr [r13+6]
0x18000fd71  movzx   r15d, word ptr [r13+4]
0x18000fd76  movzx   r12d, byte ptr [r13+1Fh]
0x18000fd7b  movzx   r13d, byte ptr [r13+1Eh]
0x18000fd80  mov     rax, [rsp+298h+arg_10]
0x18000fd88  mov     eax, [rax+78h]
0x18000fd8b  mov     dword ptr [rsp+298h+var_1B0], eax
0x18000fd92  mov     rax, [rsp+298h+arg_10]
0x18000fd9a  mov     eax, [rax+68h]
0x18000fd9d  mov     dword ptr [rsp+298h+var_1B8], eax
0x18000fda4  mov     rax, [rsp+298h+arg_10]
0x18000fdac  mov     rax, [rax+70h]
0x18000fdb0  mov     [rsp+298h+var_1C0], rax
0x18000fdb8  mov     rax, [rsp+298h+arg_10]
0x18000fdc0  mov     rax, [rax+30h]
0x18000fdc4  mov     [rsp+298h+var_1C8], rax
0x18000fdcc  mov     dword ptr [rsp+298h+var_1D0], ecx
0x18000fdd3  mov     dword ptr [rsp+298h+var_1D8], edx
0x18000fdda  mov     dword ptr [rsp+298h+var_1E0], r8d
0x18000fde2  mov     dword ptr [rsp+298h+var_1E8], r9d
0x18000fdea  mov     dword ptr [rsp+298h+var_1F0], r10d
0x18000fdf2  mov     dword ptr [rsp+298h+var_1F8], r11d
0x18000fdfa  mov     dword ptr [rsp+298h+var_200], edi
0x18000fe01  mov     dword ptr [rsp+298h+var_208], esi
0x18000fe08  mov     dword ptr [rsp+298h+var_210], r14d
0x18000fe10  mov     dword ptr [rsp+298h+var_218], r15d
0x18000fe18  mov     rcx, [rsp+298h+arg_10]
0x18000fe20  mov     eax, [rcx]
0x18000fe22  mov     dword ptr [rsp+298h+var_220], eax
0x18000fe26  mov     dword ptr [rsp+298h+var_228], r12d
0x18000fe2b  mov     dword ptr [rsp+298h+var_230], r13d
0x18000fe30  movzx   eax, byte ptr [rcx+1Dh]
0x18000fe34  mov     dword ptr [rsp+298h+var_238], eax
0x18000fe38  movzx   eax, byte ptr [rcx+1Ch]
0x18000fe3c  mov     dword ptr [rsp+298h+var_240], eax
0x18000fe40  movzx   eax, byte ptr [rcx+1Bh]
0x18000fe44  mov     dword ptr [rsp+298h+var_248], eax
0x18000fe48  movzx   eax, byte ptr [rcx+1Ah]
0x18000fe4c  mov     dword ptr [rsp+298h+var_250], eax
0x18000fe50  movzx   eax, byte ptr [rcx+19h]
0x18000fe54  mov     dword ptr [rsp+298h+var_258], eax
0x18000fe58  movzx   eax, byte ptr [rcx+18h]
0x18000fe5c  mov     dword ptr [rsp+298h+var_260], eax
0x18000fe60  movzx   eax, word ptr [rcx+16h]
0x18000fe64  mov     dword ptr [rsp+298h+var_268], eax
0x18000fe68  movzx   eax, word ptr [rcx+14h]
0x18000fe6c  mov     dword ptr [rsp+298h+var_270], eax
0x18000fe70  mov     eax, [rcx+10h]
0x18000fe73  mov     dword ptr [rsp+298h+var_278], eax
0x18000fe77  mov     r9, rcx
0x18000fe7a  lea     r8, aFieldValuesFor_0; "Field values for %p: \n  SnapshotSetId "...
0x18000fe81  lea     rdx, [rsp+298h+var_1A8]
0x18000fe89  lea     rcx, [rsp+298h+var_C8]
0x18000fe91  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x18000fe96  mov     rbx, [rsp+298h+var_F8]
0x18000fe9e  mov     rcx, rbx; this
0x18000fea1  call    ?GetSnapshotProperties@CVssQueuedSnapshot@@QEAAPEAU_VSS_SNAPSHOT_PROP@@XZ; CVssQueuedSnapshot::GetSnapshotProperties(void)
0x18000fea6  cmp     dword ptr [rax+78h], 5
0x18000feaa  jz      loc_18000FF57
0x18000feb0  cmp     dword ptr [rax+78h], 7
0x18000feb4  jz      loc_18000FF70
0x18000feba  mov     rcx, rbx; this
0x18000febd  call    ?GetSnapshotProperties@CVssQueuedSnapshot@@QEAAPEAU_VSS_SNAPSHOT_PROP@@XZ; CVssQueuedSnapshot::GetSnapshotProperties(void)
0x18000fec2  mov     ebx, [rax+78h]
0x18000fec5  lea     rax, aBaseStorVssMod_9; "base\\stor\\vss\\modules\\softprv\\src"...
0x18000fecc  mov     [rsp+298h+var_1A8], rax
0x18000fed4  lea     rax, aCvssoftwarepro_17; "CVsSoftwareProvider::CommitSnapshots"
0x18000fedb  mov     [rsp+298h+var_1A0], rax
0x18000fee3  lea     rax, aSprprovc; "SPRPROVC"
0x18000feea  mov     [rsp+298h+var_198], rax
0x18000fef2  mov     [rsp+298h+var_190], 397h
0x18000fefd  mov     [rsp+298h+var_18C], 2
0x18000ff08  mov     [rsp+298h+var_188], 0FFh
0x18000ff13  mov     [rsp+298h+var_108], 1000000h
0x18000ff1e  xor     edx, edx; Val
0x18000ff20  lea     r8d, [rdx+78h]; Size
0x18000ff24  lea     rcx, [rsp+298h+var_180]; void *
0x18000ff2c  call    memset_0
0x18000ff31  mov     dword ptr [rsp+298h+var_278], ebx
0x18000ff35  lea     r9, aBadStateD; "bad state %d"
0x18000ff3c  mov     r8d, 8000FFFFh
0x18000ff42  lea     rdx, [rsp+298h+var_1A8]
0x18000ff4a  lea     rcx, [rsp+298h+var_C8]
0x18000ff52  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x18000ff57  mov     rcx, rbx; this
0x18000ff5a  call    ?MarkAsProcessingCommit@CVssQueuedSnapshot@@QEAAXXZ; CVssQueuedSnapshot::MarkAsProcessingCommit(void)
0x18000ff5f  mov     rcx, rbx; this
0x18000ff62  call    ?CommitSnapshotIoctl@CVssQueuedSnapshot@@QEAAXXZ; CVssQueuedSnapshot::CommitSnapshotIoctl(void)
0x18000ff67  mov     rcx, rbx; this
0x18000ff6a  call    ?MarkAsCommitted@CVssQueuedSnapshot@@QEAAXXZ; CVssQueuedSnapshot::MarkAsCommitted(void)
0x18000ff6f  nop
0x18000ff70  lea     rcx, [rsp+298h+arg_18]
0x18000ff78  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000ff7d  mov     r14, [rsp+298h+arg_8]
0x18000ff85  lea     r12, aBaseStorVssMod_9; "base\\stor\\vss\\modules\\softprv\\src"...
0x18000ff8c  lea     rdi, aSprprovc; "SPRPROVC"
0x18000ff93  mov     esi, 78h ; 'x'
0x18000ff98  jmp     loc_18000FC64
0x18000ff9d  jmp     short loc_18000FFA3
0x18000ff9f  jmp     short loc_18000FFA3
0x18000ffa1  jmp     short $+2
0x18000ffa3  mov     ebx, [rsp+298h+var_C0]
0x18000ffaa  lea     rcx, [rsp+298h+var_C8]; this
0x18000ffb2  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x18000ffb7  mov     eax, ebx
0x18000ffb9  add     rsp, 260h
0x18000ffc0  pop     r15
0x18000ffc2  pop     r14
0x18000ffc4  pop     r13
0x18000ffc6  pop     r12
0x18000ffc8  pop     rdi
  ... truncated ...
```
