# CVdsVolume::FormatRoutine(void *)

- ea: `0x140028b50`
- end: `0x140028f7d`
- name: `?FormatRoutine@CVdsVolume@@SAKPEAX@Z`
- size: `1069`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callees

- `0x14000f930`
- `0x14000f98c`
- `0x140010b04`
- `0x140012c9c`
- `0x140028b50`
- `0x140028f84`
- `0x140028fc8`
- `0x140035bd4`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140028cba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140028d26`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140028e07`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140028e11`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140028cba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140028d26`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140028e07`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140028e11`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140028c9a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140028d11`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140028dc2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140028ded`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140028c9a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140028d11`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140028dc2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140028ded`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140028ecd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140028ecd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140028c69`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140028c69`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140028d98`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140028d98`
- `vdsutil!?Remove@CRtlMap@@QEAAHAEAVCRtlEntry@@@Z` at `0x140028dfe`
- `vdsutil!?Remove@CRtlMap@@QEAAHAEAVCRtlEntry@@@Z` at `0x140028dfe`
- `vdsutil!?InsertUnique@CRtlMap@@QEAAHAEAVCRtlEntry@@0@Z` at `0x140028caf`
- `vdsutil!?InsertUnique@CRtlMap@@QEAAHAEAVCRtlEntry@@0@Z` at `0x140028caf`
- `vdsutil!?SetCompletionStatus@CVdsAsyncObjectBase@@QEAAXJK@Z` at `0x140028cec`
- `vdsutil!?SetCompletionStatus@CVdsAsyncObjectBase@@QEAAXJK@Z` at `0x140028e76`
- `vdsutil!?SetCompletionStatus@CVdsAsyncObjectBase@@QEAAXJK@Z` at `0x140028ef5`
- `vdsutil!?SetCompletionStatus@CVdsAsyncObjectBase@@QEAAXJK@Z` at `0x140028cec`
- `vdsutil!?SetCompletionStatus@CVdsAsyncObjectBase@@QEAAXJK@Z` at `0x140028e76`
- `vdsutil!?SetCompletionStatus@CVdsAsyncObjectBase@@QEAAXJK@Z` at `0x140028ef5`
- `vdsutil!?Signal@CVdsAsyncObjectBase@@QEAAXXZ` at `0x140028cf5`
- `vdsutil!?Signal@CVdsAsyncObjectBase@@QEAAXXZ` at `0x140028e7f`
- `vdsutil!?Signal@CVdsAsyncObjectBase@@QEAAXXZ` at `0x140028f00`
- `vdsutil!?Signal@CVdsAsyncObjectBase@@QEAAXXZ` at `0x140028cf5`
- `vdsutil!?Signal@CVdsAsyncObjectBase@@QEAAXXZ` at `0x140028e7f`
- `vdsutil!?Signal@CVdsAsyncObjectBase@@QEAAXXZ` at `0x140028f00`
- `vdsutil!GetFMIFSFormatEx2Routine` at `0x140028c41`
- `vdsutil!GetFMIFSFormatEx2Routine` at `0x140028c41`
- `vdsutil!GetFMIFSEnableCompressionRoutine` at `0x140028c4a`
- `vdsutil!GetFMIFSEnableCompressionRoutine` at `0x140028c4a`
- `vdsutil!RemoveTempVolumeName` at `0x140028e58`
- `vdsutil!RemoveTempVolumeName` at `0x140028e58`
- `vdsutil!VdsTraceEx` at `0x140028bdb`
- `vdsutil!VdsTraceEx` at `0x140028cd6`
- `vdsutil!VdsTraceEx` at `0x140028ee2`
- `vdsutil!VdsTraceEx` at `0x140028bdb`
- `vdsutil!VdsTraceEx` at `0x140028cd6`
- `vdsutil!VdsTraceEx` at `0x140028ee2`
- `vdsutil!AcquireRundownProtection` at `0x140028bbc`
- `vdsutil!AcquireRundownProtection` at `0x140028bbc`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140028bae`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140028bae`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140028e9c`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140028f18`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140028e9c`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140028f18`
- `vdsutil!ReleaseRundownProtection` at `0x140028e91`
- `vdsutil!ReleaseRundownProtection` at `0x140028f0d`
- `vdsutil!ReleaseRundownProtection` at `0x140028e91`
- `vdsutil!ReleaseRundownProtection` at `0x140028f0d`

## string_xrefs

- `0x140028cca`: `CVdsVolume::FormatRoutine,1: Thread Map is corrupt`
- `0x140028ed6`: `FormatRoutine: failed to get FormatEx2 or EnableVolumeCompression address`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall CVdsVolume::FormatRoutine(char *Parameter)
{
  int v2; // r15d
  char *v3; // rdi
  CVdsAsyncObjectBase *v4; // rbx
  char v5; // si
  __int64 v6; // rbx
  __int64 v7; // rax
  void (__fastcall *FMIFSFormatEx2Routine)(char *, _QWORD, __int64, char *, void *); // r12
  __int64 FMIFSEnableCompressionRoutine; // rax
  int inserted; // esi
  CVdsServiceModule *v11; // rcx
  __int64 v12; // rax
  CVdsServiceModule *v13; // rcx
  unsigned int v14; // ecx
  __int64 v15; // rax
  DWORD LastError; // eax
  char v18; // [rsp+30h] [rbp-89h]
  CVdsAsyncObjectBase *v19; // [rsp+38h] [rbp-81h] BYREF
  DWORD CurrentThreadId; // [rsp+40h] [rbp-79h]
  __int64 v21; // [rsp+48h] [rbp-71h] BYREF
  __int64 v22; // [rsp+50h] [rbp-69h] BYREF
  __int64 v23; // [rsp+58h] [rbp-61h] BYREF
  __int64 v24; // [rsp+60h] [rbp-59h] BYREF
  char *v25; // [rsp+68h] [rbp-51h] BYREF
  _BYTE v26[16]; // [rsp+70h] [rbp-49h] BYREF
  __int128 v27; // [rsp+80h] [rbp-39h] BYREF
  __int128 v28; // [rsp+90h] [rbp-29h]
  _QWORD v29[5]; // [rsp+A0h] [rbp-19h] BYREF

  v2 = 0;
  v3 = 0;
  v25 = 0;
  v4 = 0;
  v19 = 0;
  v24 = 0;
  v23 = 0;
  v22 = 0;
  v21 = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v26, 0x5Eu, "CVdsVolume::FormatRoutine()");
  v5 = AcquireRundownProtection(&g_RundownRef);
  v18 = v5;
  if ( v5 )
  {
    v3 = Parameter;
    v25 = Parameter;
    ATL::CComPtrBase<CVdsEnumObject>::Attach((__int64 *)&v19, *((_QWORD *)Parameter + 1));
    v6 = *((_QWORD *)Parameter + 138);
    v24 = v6;
    v23 = *((_QWORD *)Parameter + 140);
    if ( *(_QWORD *)Parameter )
      ATL::CComPtrBase<CVdsEnumObject>::Attach(&v22, *(_QWORD *)Parameter);
    v7 = *((_QWORD *)Parameter + 148);
    if ( v7 )
      v21 = v7 + 2;
    FMIFSFormatEx2Routine = (void (__fastcall *)(char *, _QWORD, __int64, char *, void *))GetFMIFSFormatEx2Routine();
    FMIFSEnableCompressionRoutine = GetFMIFSEnableCompressionRoutine();
    if ( !FMIFSFormatEx2Routine || !FMIFSEnableCompressionRoutine )
    {
      LastError = GetLastError();
      VdsTraceEx(94, 0, "FormatRoutine: failed to get FormatEx2 or EnableVolumeCompression address", LastError);
      CVdsAsyncObjectBase::SetCompletionStatus(v19, -2147467259, 0);
      CVdsAsyncObjectBase::Signal(v19);
      ReleaseRundownProtection(&g_RundownRef);
      CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v26);
      CVolumeLock::~CVolumeLock((CVolumeLock *)&v21);
      ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(&v22);
      CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>(&v23);
      CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>(&v24);
      goto LABEL_34;
    }
    *((_QWORD *)Parameter + 147) = FMIFSEnableCompressionRoutine;
    CurrentThreadId = GetCurrentThreadId();
    v27 = 0;
    v28 = 0;
    v29[0] = 0;
    v29[3] = 0;
    LODWORD(v28) = CurrentThreadId;
    v29[1] = 0;
    v29[2] = Parameter;
    EnterCriticalSection(&g_GlobalCriticalSection);
    inserted = CRtlMap::InsertUnique((CRtlMap *)g_mapFormatThreads, (struct CRtlEntry *)&v27, (struct CRtlEntry *)v29);
    LeaveCriticalSection(&g_GlobalCriticalSection);
    if ( inserted )
    {
      if ( *((_QWORD *)Parameter + 148) )
      {
        EnterCriticalSection(&g_GlobalCriticalSection);
        *(_WORD *)(*((_QWORD *)Parameter + 148) + 2LL) |= 1u;
        LeaveCriticalSection(&g_GlobalCriticalSection);
      }
      v12 = *((_QWORD *)Parameter + 2) - *(_QWORD *)&GUID_NULL.Data1;
      if ( !v12 )
        v12 = *((_QWORD *)Parameter + 3) - *(_QWORD *)GUID_NULL.Data4;
      if ( v12 )
        CVdsService::SendVolumeNotification((unsigned int)v11, (struct _GUID *)Parameter + 1);
      CVdsServiceModule::StopAcceptingStop(v11);
      do
      {
        *((_DWORD *)Parameter + 298) = 0;
        FMIFSFormatEx2Routine(Parameter + 32, 0, v6, Parameter + 1112, &CVdsVolume::FormatCallback);
        if ( *((_DWORD *)Parameter + 298) != -2147212269 )
          break;
        Sleep(0x32u);
        ++v2;
      }
      while ( v2 < 100 );
      CVdsServiceModule::ResumeAcceptingStop(v13);
      if ( *((_QWORD *)Parameter + 148) )
      {
        EnterCriticalSection(&g_GlobalCriticalSection);
        *(_WORD *)(*((_QWORD *)Parameter + 148) + 2LL) &= ~1u;
        v27 = 0;
        v28 = 0;
        LODWORD(v28) = CurrentThreadId;
        EnterCriticalSection(&g_GlobalCriticalSection);
        CRtlMap::Remove((CRtlMap *)g_mapFormatThreads, (struct CRtlEntry *)&v27);
        LeaveCriticalSection(&g_GlobalCriticalSection);
        LeaveCriticalSection(&g_GlobalCriticalSection);
      }
      v15 = *((_QWORD *)Parameter + 2) - *(_QWORD *)&GUID_NULL.Data1;
      if ( !v15 )
        v15 = *((_QWORD *)Parameter + 3) - *(_QWORD *)GUID_NULL.Data4;
      if ( v15 )
        CVdsService::SendVolumeNotification(v14, (struct _GUID *)Parameter + 1);
      v4 = v19;
    }
    else
    {
      VdsTraceEx(94, 0, "CVdsVolume::FormatRoutine,1: Thread Map is corrupt", 183);
      v4 = v19;
      CVdsAsyncObjectBase::SetCompletionStatus(v19, -2147212216, 0);
      CVdsAsyncObjectBase::Signal(v4);
    }
    v5 = v18;
  }
  else
  {
    VdsTraceEx(94, 3, "CVdsVolume::FormatRoutine exiting due to shutdown");
    MEMORY[0x4A8] = -2146959352;
  }
  if ( *((_WORD *)v3 + 276) )
    RemoveTempVolumeName(v3 + 32);
  CVdsAsyncObjectBase::SetCompletionStatus(v4, *((_DWORD *)v3 + 298), ((*((int *)v3 + 298) >> 31) & 0xFFFFFF9C) + 100);
  CVdsAsyncObjectBase::Signal(v4);
  if ( v5 )
    ReleaseRundownProtection(&g_RundownRef);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v26);
  CVolumeLock::~CVolumeLock((CVolumeLock *)&v21);
  ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(&v22);
  CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>(&v23);
  CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>(&v24);
LABEL_34:
  ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>((__int64 *)&v19);
  CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>((__int64 *)&v25);
  return 0;
}

```

## disassembly

```asm
0x140028b50  push    rbp
0x140028b52  push    rbx
0x140028b53  push    rsi
0x140028b54  push    rdi
0x140028b55  push    r12
0x140028b57  push    r13
0x140028b59  push    r14
0x140028b5b  push    r15
0x140028b5d  lea     rbp, [rsp-1Fh]
0x140028b62  sub     rsp, 0D8h
0x140028b69  mov     rax, cs:__security_cookie
0x140028b70  xor     rax, rsp
0x140028b73  mov     [rbp+57h+var_48], rax
0x140028b77  mov     r14, rcx
0x140028b7a  xor     r15d, r15d
0x140028b7d  mov     edi, r15d
0x140028b80  mov     [rbp+57h+var_A8], r15
0x140028b84  mov     ebx, r15d
0x140028b87  mov     [rsp+110h+var_D8], rbx
0x140028b8c  mov     [rbp+57h+var_B0], r15
0x140028b90  mov     [rbp+57h+var_B8], r15
0x140028b94  mov     [rbp+57h+var_C0], r15
0x140028b98  mov     [rbp+57h+var_C8], r15
0x140028b9c  lea     r8, aCvdsvolumeForm_18; "CVdsVolume::FormatRoutine()"
0x140028ba3  lea     r13d, [r15+5Eh]
0x140028ba7  mov     edx, r13d
0x140028baa  lea     rcx, [rbp+57h+var_A0]
0x140028bae  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140028bb4  nop
0x140028bb5  lea     rcx, ?g_RundownRef@@3U_RUNDOWN_REF@@A; _RUNDOWN_REF g_RundownRef
0x140028bbc  call    cs:__imp_AcquireRundownProtection
0x140028bc2  mov     sil, al
0x140028bc5  mov     [rsp+110h+var_E0], al
0x140028bc9  test    al, al
0x140028bcb  jnz     short loc_140028BF1
0x140028bcd  lea     r8, aCvdsvolumeForm_27; "CVdsVolume::FormatRoutine exiting due t"...
0x140028bd4  lea     edx, [r15+3]
0x140028bd8  mov     ecx, r13d
0x140028bdb  call    cs:__imp_VdsTraceEx
0x140028be1  mov     dword ptr ds:4A8h, 80080008h
0x140028bec  jmp     loc_140028E47
0x140028bf1  mov     rdi, r14
0x140028bf4  mov     [rbp+57h+var_A8], r14
0x140028bf8  mov     rdx, [r14+8]
0x140028bfc  lea     rcx, [rsp+110h+var_D8]
0x140028c01  call    ?Attach@?$CComPtrBase@VCVdsEnumObject@@@ATL@@QEAAXPEAVCVdsEnumObject@@@Z; ATL::CComPtrBase<CVdsEnumObject>::Attach(CVdsEnumObject *)
0x140028c06  mov     rbx, [r14+450h]
0x140028c0d  mov     [rbp+57h+var_B0], rbx
0x140028c11  mov     rax, [r14+460h]
0x140028c18  mov     [rbp+57h+var_B8], rax
0x140028c1c  mov     rdx, [r14]
0x140028c1f  test    rdx, rdx
0x140028c22  jz      short loc_140028C2D
0x140028c24  lea     rcx, [rbp+57h+var_C0]
0x140028c28  call    ?Attach@?$CComPtrBase@VCVdsEnumObject@@@ATL@@QEAAXPEAVCVdsEnumObject@@@Z; ATL::CComPtrBase<CVdsEnumObject>::Attach(CVdsEnumObject *)
0x140028c2d  mov     rax, [r14+4A0h]
0x140028c34  test    rax, rax
0x140028c37  jz      short loc_140028C41
0x140028c39  add     rax, 2
0x140028c3d  mov     [rbp+57h+var_C8], rax
0x140028c41  call    cs:__imp_GetFMIFSFormatEx2Routine
0x140028c47  mov     r12, rax
0x140028c4a  call    cs:__imp_GetFMIFSEnableCompressionRoutine
0x140028c50  test    r12, r12
0x140028c53  jz      loc_140028ECD
0x140028c59  test    rax, rax
0x140028c5c  jz      loc_140028ECD
0x140028c62  mov     [r14+498h], rax
0x140028c69  call    cs:__imp_GetCurrentThreadId
0x140028c6f  mov     [rbp+57h+var_D0], eax
0x140028c72  xorps   xmm0, xmm0
0x140028c75  movups  [rbp+57h+var_90], xmm0
0x140028c79  movups  [rbp+57h+var_80], xmm0
0x140028c7d  mov     [rbp+57h+var_70], r15
0x140028c81  mov     [rbp+57h+var_58], r15
0x140028c85  mov     dword ptr [rbp+57h+var_80], eax
0x140028c88  mov     [rbp+57h+var_68], r15
0x140028c8c  mov     [rbp+57h+var_60], r14
0x140028c90  lea     r13, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_GlobalCriticalSection
0x140028c97  mov     rcx, r13; lpCriticalSection
0x140028c9a  call    cs:__imp_EnterCriticalSection
0x140028ca0  lea     r8, [rbp+57h+var_70]
0x140028ca4  lea     rdx, [rbp+57h+var_90]
0x140028ca8  lea     rcx, ?g_mapFormatThreads@@3VCRtlMap@@A; CRtlMap g_mapFormatThreads
0x140028caf  call    cs:__imp_?InsertUnique@CRtlMap@@QEAAHAEAVCRtlEntry@@0@Z; CRtlMap::InsertUnique(CRtlEntry &,CRtlEntry &)
0x140028cb5  mov     esi, eax
0x140028cb7  mov     rcx, r13; lpCriticalSection
0x140028cba  call    cs:__imp_LeaveCriticalSection
0x140028cc0  test    esi, esi
0x140028cc2  jnz     short loc_140028D00
0x140028cc4  mov     r9d, 0B7h
0x140028cca  lea     r8, aCvdsvolumeForm_28; "CVdsVolume::FormatRoutine,1: Thread Map"...
0x140028cd1  xor     edx, edx
0x140028cd3  lea     ecx, [rsi+5Eh]
0x140028cd6  call    cs:__imp_VdsTraceEx
0x140028cdc  xor     r8d, r8d
0x140028cdf  mov     edx, 80042448h
0x140028ce4  mov     rbx, [rsp+110h+var_D8]
0x140028ce9  mov     rcx, rbx
0x140028cec  call    cs:__imp_?SetCompletionStatus@CVdsAsyncObjectBase@@QEAAXJK@Z; CVdsAsyncObjectBase::SetCompletionStatus(long,ulong)
0x140028cf2  mov     rcx, rbx
0x140028cf5  call    cs:__imp_?Signal@CVdsAsyncObjectBase@@QEAAXXZ; CVdsAsyncObjectBase::Signal(void)
0x140028cfb  jmp     loc_140028E42
0x140028d00  mov     esi, 1
0x140028d05  cmp     [r14+4A0h], r15
0x140028d0c  jz      short loc_140028D2C
0x140028d0e  mov     rcx, r13; lpCriticalSection
0x140028d11  call    cs:__imp_EnterCriticalSection
0x140028d17  nop
0x140028d18  mov     rax, [r14+4A0h]
0x140028d1f  or      [rax+2], si
0x140028d23  mov     rcx, r13; lpCriticalSection
0x140028d26  call    cs:__imp_LeaveCriticalSection
0x140028d2c  mov     rax, [r14+10h]
0x140028d30  sub     rax, qword ptr cs:GUID_NULL.Data1
0x140028d37  jnz     short loc_140028D44
0x140028d39  mov     rax, [r14+18h]
0x140028d3d  sub     rax, qword ptr cs:GUID_NULL.Data4
0x140028d44  test    rax, rax
0x140028d47  jz      short loc_140028D52
0x140028d49  lea     rdx, [r14+10h]; struct _GUID *
0x140028d4d  call    ?SendVolumeNotification@CVdsService@@SAXKAEAU_GUID@@@Z; CVdsService::SendVolumeNotification(ulong,_GUID &)
0x140028d52  call    ?StopAcceptingStop@CVdsServiceModule@@QEAAXXZ; CVdsServiceModule::StopAcceptingStop(void)
0x140028d57  mov     dword ptr [r14+4A8h], 0
0x140028d62  lea     rax, ?FormatCallback@CVdsVolume@@SAEW4_FMIFS_PACKET_TYPE@@KPEAX@Z; CVdsVolume::FormatCallback(_FMIFS_PACKET_TYPE,ulong,void *)
0x140028d69  mov     [rsp+110h+var_F0], rax
0x140028d6e  lea     r9, [r14+458h]
0x140028d75  mov     r8, rbx
0x140028d78  xor     edx, edx
0x140028d7a  lea     rcx, [r14+20h]
0x140028d7e  mov     rax, r12
0x140028d81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140028d86  cmp     dword ptr [r14+4A8h], 80042413h
0x140028d91  jnz     short loc_140028DA7
0x140028d93  mov     ecx, 32h ; '2'; dwMilliseconds
0x140028d98  call    cs:__imp_Sleep
0x140028d9e  inc     r15d
0x140028da1  cmp     r15d, 64h ; 'd'
0x140028da5  jl      short loc_140028D57
0x140028da7  call    ?ResumeAcceptingStop@CVdsServiceModule@@QEAAXXZ; CVdsServiceModule::ResumeAcceptingStop(void)
0x140028dac  xor     r15d, r15d
0x140028daf  cmp     [r14+4A0h], r15
0x140028db6  jz      short loc_140028E17
0x140028db8  lea     rbx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_GlobalCriticalSection
0x140028dbf  mov     rcx, rbx; lpCriticalSection
0x140028dc2  call    cs:__imp_EnterCriticalSection
0x140028dc8  nop
0x140028dc9  mov     rax, [r14+4A0h]
0x140028dd0  mov     edx, 0FFFEh
0x140028dd5  and     [rax+2], dx
0x140028dd9  xorps   xmm0, xmm0
0x140028ddc  movups  [rbp+57h+var_90], xmm0
0x140028de0  movups  [rbp+57h+var_80], xmm0
0x140028de4  mov     eax, [rbp+57h+var_D0]
0x140028de7  mov     dword ptr [rbp+57h+var_80], eax
0x140028dea  mov     rcx, rbx; lpCriticalSection
0x140028ded  call    cs:__imp_EnterCriticalSection
0x140028df3  lea     rdx, [rbp+57h+var_90]
0x140028df7  lea     rcx, ?g_mapFormatThreads@@3VCRtlMap@@A; CRtlMap g_mapFormatThreads
0x140028dfe  call    cs:__imp_?Remove@CRtlMap@@QEAAHAEAVCRtlEntry@@@Z; CRtlMap::Remove(CRtlEntry &)
0x140028e04  mov     rcx, rbx; lpCriticalSection
0x140028e07  call    cs:__imp_LeaveCriticalSection
0x140028e0d  nop
0x140028e0e  mov     rcx, rbx; lpCriticalSection
0x140028e11  call    cs:__imp_LeaveCriticalSection
0x140028e17  mov     rax, [r14+10h]
0x140028e1b  sub     rax, qword ptr cs:GUID_NULL.Data1
0x140028e22  jnz     short loc_140028E2F
0x140028e24  mov     rax, [r14+18h]
0x140028e28  sub     rax, qword ptr cs:GUID_NULL.Data4
0x140028e2f  test    rax, rax
0x140028e32  jz      short loc_140028E3D
0x140028e34  lea     rdx, [r14+10h]; struct _GUID *
0x140028e38  call    ?SendVolumeNotification@CVdsService@@SAXKAEAU_GUID@@@Z; CVdsService::SendVolumeNotification(ulong,_GUID &)
0x140028e3d  mov     rbx, [rsp+110h+var_D8]
0x140028e42  mov     sil, [rsp+110h+var_E0]
0x140028e47  lea     rdx, [rdi+228h]
0x140028e4e  cmp     r15w, [rdx]
0x140028e52  jz      short loc_140028E5E
0x140028e54  lea     rcx, [rdi+20h]
0x140028e58  call    cs:__imp_RemoveTempVolumeName
0x140028e5e  mov     edx, [rdi+4A8h]
0x140028e64  mov     r8d, edx
0x140028e67  sar     r8d, 1Fh
0x140028e6b  and     r8d, 0FFFFFF9Ch
0x140028e6f  add     r8d, 64h ; 'd'
0x140028e73  mov     rcx, rbx
0x140028e76  call    cs:__imp_?SetCompletionStatus@CVdsAsyncObjectBase@@QEAAXJK@Z; CVdsAsyncObjectBase::SetCompletionStatus(long,ulong)
0x140028e7c  mov     rcx, rbx
0x140028e7f  call    cs:__imp_?Signal@CVdsAsyncObjectBase@@QEAAXXZ; CVdsAsyncObjectBase::Signal(void)
0x140028e85  test    sil, sil
0x140028e88  jz      short loc_140028E98
0x140028e8a  lea     rcx, ?g_RundownRef@@3U_RUNDOWN_REF@@A; _RUNDOWN_REF g_RundownRef
0x140028e91  call    cs:__imp_ReleaseRundownProtection
0x140028e97  nop
0x140028e98  lea     rcx, [rbp+57h+var_A0]
0x140028e9c  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140028ea2  nop
0x140028ea3  lea     rcx, [rbp+57h+var_C8]; this
0x140028ea7  call    ??1CVolumeLock@@QEAA@XZ; CVolumeLock::~CVolumeLock(void)
0x140028eac  nop
0x140028ead  lea     rcx, [rbp+57h+var_C0]
0x140028eb1  call    ??1?$CComPtrBase@VCVdsEnumObject@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(void)
0x140028eb6  nop
0x140028eb7  lea     rcx, [rbp+57h+var_B8]
0x140028ebb  call    ??1?$CVdsHeapPtr@U_EXTEND_VOLUME_HANDLER_PARAMETER@@@@QEAA@XZ; CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>(void)
0x140028ec0  nop
0x140028ec1  lea     rcx, [rbp+57h+var_B0]
0x140028ec5  call    ??1?$CVdsHeapPtr@U_EXTEND_VOLUME_HANDLER_PARAMETER@@@@QEAA@XZ; CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>(void)
0x140028eca  nop
0x140028ecb  jmp     short loc_140028F47
0x140028ecd  call    cs:__imp_GetLastError
0x140028ed3  mov     r9d, eax
0x140028ed6  lea     r8, aFormatroutineF; "FormatRoutine: failed to get FormatEx2 "...
0x140028edd  xor     edx, edx
0x140028edf  mov     ecx, r13d
0x140028ee2  call    cs:__imp_VdsTraceEx
0x140028ee8  xor     r8d, r8d
0x140028eeb  mov     edx, 80004005h
0x140028ef0  mov     rcx, [rsp+110h+var_D8]
0x140028ef5  call    cs:__imp_?SetCompletionStatus@CVdsAsyncObjectBase@@QEAAXJK@Z; CVdsAsyncObjectBase::SetCompletionStatus(long,ulong)
0x140028efb  mov     rcx, [rsp+110h+var_D8]
0x140028f00  call    cs:__imp_?Signal@CVdsAsyncObjectBase@@QEAAXXZ; CVdsAsyncObjectBase::Signal(void)
0x140028f06  lea     rcx, ?g_RundownRef@@3U_RUNDOWN_REF@@A; _RUNDOWN_REF g_RundownRef
0x140028f0d  call    cs:__imp_ReleaseRundownProtection
0x140028f13  nop
0x140028f14  lea     rcx, [rbp+57h+var_A0]
0x140028f18  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140028f1e  nop
0x140028f1f  lea     rcx, [rbp+57h+var_C8]; this
0x140028f23  call    ??1CVolumeLock@@QEAA@XZ; CVolumeLock::~CVolumeLock(void)
0x140028f28  nop
0x140028f29  lea     rcx, [rbp+57h+var_C0]
0x140028f2d  call    ??1?$CComPtrBase@VCVdsEnumObject@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(void)
0x140028f32  nop
0x140028f33  lea     rcx, [rbp+57h+var_B8]
0x140028f37  call    ??1?$CVdsHeapPtr@U_EXTEND_VOLUME_HANDLER_PARAMETER@@@@QEAA@XZ; CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>(void)
0x140028f3c  nop
0x140028f3d  lea     rcx, [rbp+57h+var_B0]
0x140028f41  call    ??1?$CVdsHeapPtr@U_EXTEND_VOLUME_HANDLER_PARAMETER@@@@QEAA@XZ; CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>(void)
0x140028f46  nop
0x140028f47  lea     rcx, [rsp+110h+var_D8]
0x140028f4c  call    ??1?$CComPtrBase@VCVdsEnumObject@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(void)
0x140028f51  nop
0x140028f52  lea     rcx, [rbp+57h+var_A8]
0x140028f56  call    ??1?$CVdsHeapPtr@U_EXTEND_VOLUME_HANDLER_PARAMETER@@@@QEAA@XZ; CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>(void)
0x140028f5b  xor     eax, eax
0x140028f5d  mov     rcx, [rbp+57h+var_48]
0x140028f61  xor     rcx, rsp; StackCookie
0x140028f64  call    __security_check_cookie
0x140028f69  add     rsp, 0D8h
0x140028f70  pop     r15
0x140028f72  pop     r14
0x140028f74  pop     r13
0x140028f76  pop     r12
0x140028f78  pop     rdi
0x140028f79  pop     rsi
0x140028f7a  pop     rbx
0x140028f7b  pop     rbp
0x140028f7c  retn
```
