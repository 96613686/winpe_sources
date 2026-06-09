# CVsSoftwareProvider::PostFinalCommitSnapshots(_GUID)

- ea: `0x1800138c0`
- end: `0x180013dd3`
- name: `?PostFinalCommitSnapshots@CVsSoftwareProvider@@UEAAJU_GUID@@@Z`
- size: `1299`
- prototype: `int(CVsSoftwareProvider *__hidden this, struct _GUID *__struct_ptr)`
- caller_count: `0`
- callee_count: `22`
- tags: `broker_com_uri`

## callees

- `0x18000212c`
- `0x1800034cc`
- `0x1800036c4`
- `0x180003888`
- `0x1800138c0`
- `0x180019334`
- `0x180019458`
- `0x18001961c`
- `0x180019ab4`
- `0x18001a01c`
- `0x18001a858`
- `0x18001abb8`
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

- `0x1800138e5`: `CVsSoftwareProvider::PostFinalCommitSnapshots`
- `0x180013d6b`: `Snapshot created`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CVsSoftwareProvider::PostFinalCommitSnapshots(CVsSoftwareProvider *this, struct _GUID *a2)
{
  char v3; // al
  struct CVssQueuedSnapshot *NextBySnapshotSet; // rax
  CVssQueuedSnapshot *v5; // rbx
  struct _VSS_SNAPSHOT_PROP *SnapshotProperties; // rdi
  struct _VSS_SNAPSHOT_PROP *v7; // rax
  VSS_SNAPSHOT_STATE m_eStatus; // ebx
  unsigned int v9; // ebx
  __int64 v11; // [rsp+20h] [rbp-1D8h]
  const unsigned __int16 *v12; // [rsp+70h] [rbp-188h] BYREF
  const unsigned __int16 *v13; // [rsp+78h] [rbp-180h]
  const unsigned __int16 *v14; // [rsp+80h] [rbp-178h]
  int v15; // [rsp+88h] [rbp-170h]
  int v16; // [rsp+8Ch] [rbp-16Ch]
  int v17; // [rsp+90h] [rbp-168h]
  _BYTE v18[120]; // [rsp+98h] [rbp-160h] BYREF
  int v19; // [rsp+110h] [rbp-E8h]
  unsigned int v20; // [rsp+118h] [rbp-E0h] BYREF
  _QWORD v21[2]; // [rsp+120h] [rbp-D8h] BYREF
  LPVOID v22; // [rsp+130h] [rbp-C8h] BYREF
  unsigned int v23; // [rsp+138h] [rbp-C0h]
  unsigned int v24; // [rsp+154h] [rbp-A4h]
  _com_error *v25; // [rsp+1A0h] [rbp-58h] BYREF
  const std::exception *v26; // [rsp+1A8h] [rbp-50h] BYREF
  struct _GUID v27; // [rsp+1B0h] [rbp-48h] BYREF
  LPCRITICAL_SECTION v28[7]; // [rsp+1C0h] [rbp-38h] BYREF
  struct CVssQueuedSnapshot *v29; // [rsp+210h] [rbp+18h] BYREF

  v12 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
  v13 = L"CVsSoftwareProvider::PostFinalCommitSnapshots";
  v14 = L"SPRPROVC";
  v15 = 1211;
  v16 = 2;
  v17 = 255;
  v19 = 0x1000000;
  memset_0(v18, 0, sizeof(v18));
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v22, (__int64)&v12, 0);
  try
  {
    v3 = IsInGroup();
    v12 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
    v13 = L"CVsSoftwareProvider::PostFinalCommitSnapshots";
    v14 = L"SPRPROVC";
    v16 = 2;
    v17 = 255;
    v19 = 0x1000000;
    if ( !v3 )
    {
      v15 = 1217;
      memset_0(v18, 0, sizeof(v18));
      CVssFunctionTracer::Throw(
        (CVssFunctionTracer *)&v22,
        (const struct CVssDebugInfo *)&v12,
        -2147024891,
        L"The client process is not running under an administrator account");
    }
    v15 = 1220;
    memset_0(v18, 0, sizeof(v18));
    CVssFunctionTracer::Trace(
      &v22,
      &v12,
      L"Parameters: \n  SnapshotSetId = {%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x} \n",
      a2->Data1,
      a2->Data2,
      a2->Data3,
      a2->Data4[0],
      a2->Data4[1],
      a2->Data4[2],
      a2->Data4[3],
      a2->Data4[4],
      a2->Data4[5],
      a2->Data4[6],
      a2->Data4[7]);
    if ( !memcmp_0(a2, &GUID_NULL, 0x10u) )
    {
      v12 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
      v13 = L"CVsSoftwareProvider::PostFinalCommitSnapshots";
      v14 = L"SPRPROVC";
      v15 = 1226;
      v16 = 2;
      v17 = 255;
      v19 = 0x1000000;
      memset_0(v18, 0, sizeof(v18));
      CVssFunctionTracer::Throw(
        (CVssFunctionTracer *)&v22,
        (const struct CVssDebugInfo *)&v12,
        -2147024809,
        L"SnapshotSetId == GUID_NULL");
    }
    CVssAutomaticLock2::CVssAutomaticLock2(
      (CVssAutomaticLock2 *)v28,
      (struct CVssCriticalSection *)CVsSoftwareProvider::m_cs);
    v12 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
    v13 = L"CVsSoftwareProvider::PostFinalCommitSnapshots";
    v14 = L"SPRPROVC";
    v15 = 1230;
    v16 = 2;
    v17 = 255;
    v19 = 0x1000000;
    memset_0(v18, 0, sizeof(v18));
    CVssFunctionTracer::AddOperation((struct CVssFunctionTracer *)&v22, (const struct CVssDebugInfo *)&v12, 410);
    v12 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
    v13 = L"CVsSoftwareProvider::PostFinalCommitSnapshots";
    v14 = L"SPRPROVC";
    v15 = 1231;
    v16 = 2;
    v17 = 255;
    v19 = 0x1000000;
    memset_0(v18, 0, sizeof(v18));
    CVssFunctionTracer::AddContext((__int64)&v22, (const struct CVssDebugInfo *)&v12);
    v21[0] = &CVssQueuedSnapshot::m_list;
    v21[1] = CVssQueuedSnapshot::m_list;
    while ( 1 )
    {
      v27 = *a2;
      NextBySnapshotSet = CVssSnapIterator::GetNextBySnapshotSet((CVssSnapIterator *)v21, &v27);
      v5 = NextBySnapshotSet;
      v29 = NextBySnapshotSet;
      if ( NextBySnapshotSet )
        (*(void (__fastcall **)(struct CVssQueuedSnapshot *))(*(_QWORD *)NextBySnapshotSet + 8LL))(NextBySnapshotSet);
      if ( !v5 )
        break;
      SnapshotProperties = CVssQueuedSnapshot::GetSnapshotProperties(v5);
      v7 = CVssQueuedSnapshot::GetSnapshotProperties(v5);
      if ( v7->m_eStatus == VSS_SS_PREFINALCOMMITTED )
      {
        CVssQueuedSnapshot::MarkAsProcessingPostFinalCommit(v5);
        CVssQueuedSnapshot::PostAutoRecoverSnapshot(v5);
        CVssQueuedSnapshot::SetPostFinalCommitInfo(v5);
        CVssQueuedSnapshot::SetAppInfoIoctl(v5, SnapshotProperties);
        v12 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
        v13 = L"CVsSoftwareProvider::PostFinalCommitSnapshots";
        v14 = L"SPRPROVC";
        v15 = 1267;
        v16 = 2;
        v17 = 255;
        v19 = 0x1000000;
        memset_0(v18, 0, sizeof(v18));
        CVssFunctionTracer::Trace(&v22, &v12, L"Snapshot created");
        CVssQueuedSnapshot::MarkAsCreated(v5);
      }
      else if ( v7->m_eStatus != VSS_SS_CREATED )
      {
        m_eStatus = CVssQueuedSnapshot::GetSnapshotProperties(v5)->m_eStatus;
        v12 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
        v13 = L"CVsSoftwareProvider::PostFinalCommitSnapshots";
        v14 = L"SPRPROVC";
        v15 = 1281;
        v16 = 2;
        v17 = 255;
        v19 = 0x1000000;
        memset_0(v18, 0, sizeof(v18));
        LODWORD(v11) = m_eStatus;
        CVssFunctionTracer::TranslateGenericError(&v22, &v12, 2147549183LL, L"bad state %d", v11);
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v29);
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v29);
    CVssAutomaticLock2::~CVssAutomaticLock2(v28);
  }
  catch ( long v20 )
  {
    CVssFunctionTracer::HandleHresultException(
      (CVssFunctionTracer *)&v22,
      v20,
      L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx",
      L"SPRPROVC",
      L"CVsSoftwareProvider::PostFinalCommitSnapshots",
      0x505u,
      v24);
  }
  catch ( _com_error *v25 )
  {
    CVssFunctionTracer::HandleComException(
      (CVssFunctionTracer *)&v22,
      v25,
      L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx",
      L"SPRPROVC",
      L"CVsSoftwareProvider::PostFinalCommitSnapshots",
      0x505u,
      v24);
  }
  catch ( std::bad_alloc )
  {
    CVssFunctionTracer::HandleStdBadAllocException(
      (CVssFunctionTracer *)&v22,
      L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx",
      L"SPRPROVC",
      L"CVsSoftwareProvider::PostFinalCommitSnapshots",
      0x505u,
      v24);
  }
  catch ( const std::exception *v26 )
  {
    CVssFunctionTracer::HandleStdGenericException(
      (CVssFunctionTracer *)&v22,
      v26,
      L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx",
      L"SPRPROVC",
      L"CVsSoftwareProvider::PostFinalCommitSnapshots",
      0x505u,
      v24);
  }
  v9 = v23;
  CVssFunctionTracer::~CVssFunctionTracer(&v22);
  return v9;
}

```

## disassembly

```asm
0x1800138c0  mov     rax, rsp
0x1800138c3  mov     [rax+8], rbx
0x1800138c7  push    rsi
0x1800138c8  push    rdi
0x1800138c9  push    r12
0x1800138cb  push    r13
0x1800138cd  push    r14
0x1800138cf  sub     rsp, 1D0h
0x1800138d6  mov     r14, rdx
0x1800138d9  lea     r12, aBaseStorVssMod_9; "base\\stor\\vss\\modules\\softprv\\src"...
0x1800138e0  mov     [rsp+1F8h+var_188], r12
0x1800138e5  lea     r13, aCvssoftwarepro_22; "CVsSoftwareProvider::PostFinalCommitSna"...
0x1800138ec  mov     [rsp+1F8h+var_180], r13
0x1800138f1  lea     rbx, aSprprovc; "SPRPROVC"
0x1800138f8  mov     [rax-178h], rbx
0x1800138ff  mov     dword ptr [rax-170h], 4BBh
0x180013909  mov     edi, 2
0x18001390e  mov     [rax-16Ch], edi
0x180013914  mov     esi, 0FFh
0x180013919  mov     [rax-168h], esi
0x18001391f  mov     dword ptr [rax-0E8h], 1000000h
0x180013929  xor     edx, edx; Val
0x18001392b  lea     r8d, [rdi+76h]; Size
0x18001392f  lea     rcx, [rax-160h]; void *
0x180013936  call    memset_0
0x18001393b  xor     r8d, r8d
0x18001393e  lea     rdx, [rsp+1F8h+var_188]
0x180013943  lea     rcx, [rsp+1F8h+var_C8]
0x18001394b  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x180013950  nop
0x180013951  call    ?IsInGroup@@YA_NK_N@Z; IsInGroup(ulong,bool)
0x180013956  mov     [rsp+1F8h+var_188], r12
0x18001395b  mov     [rsp+1F8h+var_180], r13
0x180013960  mov     [rsp+1F8h+var_178], rbx
0x180013968  mov     [rsp+1F8h+var_16C], edi
0x18001396f  mov     [rsp+1F8h+var_168], esi
0x180013976  mov     [rsp+1F8h+var_E8], 1000000h
0x180013981  xor     edx, edx; Val
0x180013983  lea     r8d, [rdi+76h]; Size
0x180013987  lea     rcx, [rsp+1F8h+var_160]; void *
0x18001398f  test    al, al
0x180013991  jnz     short loc_1800139C2
0x180013993  mov     [rsp+1F8h+var_170], 4C1h
0x18001399e  call    memset_0
0x1800139a3  lea     r9, aTheClientProce_0; "The client process is not running under"...
0x1800139aa  mov     r8d, 80070005h
0x1800139b0  lea     rdx, [rsp+1F8h+var_188]
0x1800139b5  lea     rcx, [rsp+1F8h+var_C8]
0x1800139bd  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x1800139c2  mov     [rsp+1F8h+var_170], 4C4h
0x1800139cd  call    memset_0
0x1800139d2  movzx   eax, byte ptr [r14+0Fh]
0x1800139d7  movzx   ecx, byte ptr [r14+0Eh]
0x1800139dc  movzx   edx, byte ptr [r14+0Dh]
0x1800139e1  movzx   r8d, byte ptr [r14+0Ch]
0x1800139e6  movzx   r9d, byte ptr [r14+0Bh]
0x1800139eb  movzx   r10d, byte ptr [r14+0Ah]
0x1800139f0  movzx   r11d, byte ptr [r14+9]
0x1800139f5  movzx   ebx, byte ptr [r14+8]
0x1800139fa  movzx   edi, word ptr [r14+6]
0x1800139ff  movzx   esi, word ptr [r14+4]
0x180013a04  mov     [rsp+1F8h+var_190], eax
0x180013a08  mov     [rsp+1F8h+var_198], ecx
0x180013a0c  mov     [rsp+1F8h+var_1A0], edx
0x180013a10  mov     [rsp+1F8h+var_1A8], r8d
0x180013a15  mov     [rsp+1F8h+var_1B0], r9d
0x180013a1a  mov     [rsp+1F8h+var_1B8], r10d
0x180013a1f  mov     [rsp+1F8h+var_1C0], r11d
0x180013a24  mov     [rsp+1F8h+var_1C8], ebx
0x180013a28  mov     [rsp+1F8h+var_1D0], edi
0x180013a2c  mov     dword ptr [rsp+1F8h+var_1D8], esi
0x180013a30  mov     r9d, [r14]
0x180013a33  lea     r8, aParametersSnap_4; "Parameters: \n  SnapshotSetId = {%.8x-%"...
0x180013a3a  lea     rdx, [rsp+1F8h+var_188]
0x180013a3f  lea     rcx, [rsp+1F8h+var_C8]
0x180013a47  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x180013a4c  mov     r8d, 10h; Size
0x180013a52  lea     rdx, GUID_NULL; Buf2
0x180013a59  mov     rcx, r14; Buf1
0x180013a5c  call    memcmp_0
0x180013a61  test    eax, eax
0x180013a63  jnz     short loc_180013ADC
0x180013a65  mov     [rsp+1F8h+var_188], r12
0x180013a6a  mov     [rsp+1F8h+var_180], r13
0x180013a6f  lea     rsi, aSprprovc; "SPRPROVC"
0x180013a76  mov     [rsp+1F8h+var_178], rsi
0x180013a7e  mov     [rsp+1F8h+var_170], 4CAh
0x180013a89  mov     [rsp+1F8h+var_16C], 2
0x180013a94  mov     [rsp+1F8h+var_168], 0FFh
0x180013a9f  mov     [rsp+1F8h+var_E8], 1000000h
0x180013aaa  xor     edx, edx; Val
0x180013aac  lea     r8d, [rax+78h]; Size
0x180013ab0  lea     rcx, [rsp+1F8h+var_160]; void *
0x180013ab8  call    memset_0
0x180013abd  lea     r9, aSnapshotsetidG; "SnapshotSetId == GUID_NULL"
0x180013ac4  mov     r8d, 80070057h
0x180013aca  lea     rdx, [rsp+1F8h+var_188]
0x180013acf  lea     rcx, [rsp+1F8h+var_C8]
0x180013ad7  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x180013adc  lea     rdx, ?m_cs@CVsSoftwareProvider@@0VCVssCriticalSection@@A; struct CVssCriticalSection *
0x180013ae3  lea     rcx, [rsp+1F8h+var_38]; this
0x180013aeb  call    ??0CVssAutomaticLock2@@QEAA@AEAVCVssCriticalSection@@@Z; CVssAutomaticLock2::CVssAutomaticLock2(CVssCriticalSection &)
0x180013af0  nop
0x180013af1  mov     [rsp+1F8h+var_188], r12
0x180013af6  mov     [rsp+1F8h+var_180], r13
0x180013afb  lea     rsi, aSprprovc; "SPRPROVC"
0x180013b02  mov     [rsp+1F8h+var_178], rsi
0x180013b0a  mov     [rsp+1F8h+var_170], 4CEh
0x180013b15  mov     ebx, 2
0x180013b1a  mov     [rsp+1F8h+var_16C], ebx
0x180013b21  mov     edi, 0FFh
0x180013b26  mov     [rsp+1F8h+var_168], edi
0x180013b2d  mov     [rsp+1F8h+var_E8], 1000000h
0x180013b38  xor     edx, edx; Val
0x180013b3a  lea     r8d, [rbx+76h]; Size
0x180013b3e  lea     rcx, [rsp+1F8h+var_160]; void *
0x180013b46  call    memset_0
0x180013b4b  mov     r8d, 19Ah
0x180013b51  lea     rdx, [rsp+1F8h+var_188]
0x180013b56  lea     rcx, [rsp+1F8h+var_C8]
0x180013b5e  call    ?AddOperation@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@IZZ; CVssFunctionTracer::AddOperation(CVssDebugInfo,uint,...)
0x180013b63  mov     [rsp+1F8h+var_188], r12
0x180013b68  mov     [rsp+1F8h+var_180], r13
0x180013b6d  mov     [rsp+1F8h+var_178], rsi
0x180013b75  mov     [rsp+1F8h+var_170], 4CFh
0x180013b80  mov     [rsp+1F8h+var_16C], ebx
0x180013b87  mov     [rsp+1F8h+var_168], edi
0x180013b8e  mov     [rsp+1F8h+var_E8], 1000000h
0x180013b99  xor     edx, edx; Val
0x180013b9b  lea     r8d, [rbx+76h]; Size
0x180013b9f  lea     rcx, [rsp+1F8h+var_160]; void *
0x180013ba7  call    memset_0
0x180013bac  lea     r9, aSystemProvider; "System Provider"
0x180013bb3  mov     r8d, 1394h
0x180013bb9  lea     rdx, [rsp+1F8h+var_188]
0x180013bbe  lea     rcx, [rsp+1F8h+var_C8]
0x180013bc6  call    ?AddContext@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@IPEBG@Z; CVssFunctionTracer::AddContext(CVssDebugInfo,uint,ushort const *)
0x180013bcb  lea     rax, ?m_list@CVssQueuedSnapshot@@0V?$CVssDLList@PEAVCVssQueuedSnapshot@@@@A; CVssDLList<CVssQueuedSnapshot *> CVssQueuedSnapshot::m_list
0x180013bd2  mov     [rsp+1F8h+var_D8], rax
0x180013bda  mov     rax, cs:?m_list@CVssQueuedSnapshot@@0V?$CVssDLList@PEAVCVssQueuedSnapshot@@@@A; CVssDLList<CVssQueuedSnapshot *> CVssQueuedSnapshot::m_list
0x180013be1  mov     [rsp+1F8h+var_D0], rax
0x180013be9  movups  xmm0, xmmword ptr [r14]
0x180013bed  movdqu  xmmword ptr [rsp+1F8h+var_48.Data1], xmm0
0x180013bf6  lea     rdx, [rsp+1F8h+var_48]; struct _GUID
0x180013bfe  lea     rcx, [rsp+1F8h+var_D8]; this
0x180013c06  call    ?GetNextBySnapshotSet@CVssSnapIterator@@QEAAPEAVCVssQueuedSnapshot@@U_GUID@@@Z; CVssSnapIterator::GetNextBySnapshotSet(_GUID)
0x180013c0b  mov     rbx, rax
0x180013c0e  mov     [rsp+1F8h+arg_10], rax
0x180013c16  test    rax, rax
0x180013c19  jz      short loc_180013C2B
0x180013c1b  mov     rax, [rax]
0x180013c1e  mov     rcx, rbx
0x180013c21  mov     rax, [rax+8]
0x180013c25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c2a  nop
0x180013c2b  test    rbx, rbx
0x180013c2e  jnz     short loc_180013C51
0x180013c30  lea     rcx, [rsp+1F8h+arg_10]
0x180013c38  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180013c3d  nop
0x180013c3e  lea     rcx, [rsp+1F8h+var_38]; this
0x180013c46  call    ??1CVssAutomaticLock2@@QEAA@XZ; CVssAutomaticLock2::~CVssAutomaticLock2(void)
0x180013c4b  nop
0x180013c4c  jmp     loc_180013DA5
0x180013c51  mov     rcx, rbx; this
0x180013c54  call    ?GetSnapshotProperties@CVssQueuedSnapshot@@QEAAPEAU_VSS_SNAPSHOT_PROP@@XZ; CVssQueuedSnapshot::GetSnapshotProperties(void)
0x180013c59  mov     rdi, rax
0x180013c5c  mov     rcx, rbx; this
0x180013c5f  call    ?GetSnapshotProperties@CVssQueuedSnapshot@@QEAAPEAU_VSS_SNAPSHOT_PROP@@XZ; CVssQueuedSnapshot::GetSnapshotProperties(void)
0x180013c64  cmp     dword ptr [rax+78h], 0Ah
0x180013c68  jz      loc_180013CF7
0x180013c6e  cmp     dword ptr [rax+78h], 0Ch
0x180013c72  jz      loc_180013D8D
0x180013c78  mov     rcx, rbx; this
0x180013c7b  call    ?GetSnapshotProperties@CVssQueuedSnapshot@@QEAAPEAU_VSS_SNAPSHOT_PROP@@XZ; CVssQueuedSnapshot::GetSnapshotProperties(void)
0x180013c80  mov     ebx, [rax+78h]
0x180013c83  mov     [rsp+1F8h+var_188], r12
0x180013c88  mov     [rsp+1F8h+var_180], r13
0x180013c8d  mov     [rsp+1F8h+var_178], rsi
0x180013c95  mov     [rsp+1F8h+var_170], 501h
0x180013ca0  mov     [rsp+1F8h+var_16C], 2
0x180013cab  mov     [rsp+1F8h+var_168], 0FFh
0x180013cb6  mov     [rsp+1F8h+var_E8], 1000000h
0x180013cc1  xor     edx, edx; Val
0x180013cc3  lea     r8d, [rdx+78h]; Size
0x180013cc7  lea     rcx, [rsp+1F8h+var_160]; void *
0x180013ccf  call    memset_0
0x180013cd4  mov     dword ptr [rsp+1F8h+var_1D8], ebx
0x180013cd8  lea     r9, aBadStateD; "bad state %d"
0x180013cdf  mov     r8d, 8000FFFFh
0x180013ce5  lea     rdx, [rsp+1F8h+var_188]
0x180013cea  lea     rcx, [rsp+1F8h+var_C8]
0x180013cf2  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x180013cf7  mov     rcx, rbx; this
0x180013cfa  call    ?MarkAsProcessingPostFinalCommit@CVssQueuedSnapshot@@QEAAXXZ; CVssQueuedSnapshot::MarkAsProcessingPostFinalCommit(void)
0x180013cff  mov     rcx, rbx; this
0x180013d02  call    ?PostAutoRecoverSnapshot@CVssQueuedSnapshot@@QEAAXXZ; CVssQueuedSnapshot::PostAutoRecoverSnapshot(void)
0x180013d07  mov     rcx, rbx; this
0x180013d0a  call    ?SetPostFinalCommitInfo@CVssQueuedSnapshot@@QEAAXXZ; CVssQueuedSnapshot::SetPostFinalCommitInfo(void)
0x180013d0f  mov     rdx, rdi; struct _VSS_SNAPSHOT_PROP *
0x180013d12  mov     rcx, rbx; this
0x180013d15  call    ?SetAppInfoIoctl@CVssQueuedSnapshot@@QEAAXPEAU_VSS_SNAPSHOT_PROP@@@Z; CVssQueuedSnapshot::SetAppInfoIoctl(_VSS_SNAPSHOT_PROP *)
0x180013d1a  mov     [rsp+1F8h+var_188], r12
0x180013d1f  mov     [rsp+1F8h+var_180], r13
0x180013d24  mov     [rsp+1F8h+var_178], rsi
0x180013d2c  mov     [rsp+1F8h+var_170], 4F3h
0x180013d37  mov     [rsp+1F8h+var_16C], 2
0x180013d42  mov     [rsp+1F8h+var_168], 0FFh
0x180013d4d  mov     [rsp+1F8h+var_E8], 1000000h
0x180013d58  xor     edx, edx; Val
0x180013d5a  lea     r8d, [rdx+78h]; Size
0x180013d5e  lea     rcx, [rsp+1F8h+var_160]; void *
0x180013d66  call    memset_0
0x180013d6b  lea     r8, aSnapshotCreate; "Snapshot created"
0x180013d72  lea     rdx, [rsp+1F8h+var_188]
0x180013d77  lea     rcx, [rsp+1F8h+var_C8]
0x180013d7f  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x180013d84  mov     rcx, rbx; this
0x180013d87  call    ?MarkAsCreated@CVssQueuedSnapshot@@QEAAXXZ; CVssQueuedSnapshot::MarkAsCreated(void)
0x180013d8c  nop
0x180013d8d  lea     rcx, [rsp+1F8h+arg_10]
0x180013d95  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180013d9a  jmp     loc_180013BE9
0x180013d9f  jmp     short loc_180013DA5
0x180013da1  jmp     short loc_180013DA5
0x180013da3  jmp     short $+2
0x180013da5  mov     ebx, [rsp+1F8h+var_C0]
0x180013dac  lea     rcx, [rsp+1F8h+var_C8]; this
0x180013db4  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x180013db9  mov     eax, ebx
0x180013dbb  mov     rbx, [rsp+1F8h+arg_0]
0x180013dc3  add     rsp, 1D0h
0x180013dca  pop     r14
0x180013dcc  pop     r13
0x180013dce  pop     r12
0x180013dd0  pop     rdi
0x180013dd1  pop     rsi
0x180013dd2  retn
```
