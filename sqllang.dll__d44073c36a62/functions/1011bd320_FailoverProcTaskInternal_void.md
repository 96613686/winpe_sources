# FailoverProcTaskInternal(void)

- ea: `0x1011bd320`
- end: `0x1011be63c`
- name: `?FailoverProcTaskInternal@@YAPEAXXZ`
- size: `4892`
- prototype: `void *(void)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1011be650`

## callees

- `0x100401070`
- `0x1004012d0`
- `0x100401340`
- `0x1004076a0`
- `0x100409cb0`
- `0x10040aaa0`
- `0x10040cd80`
- `0x1004131b0`
- `0x1004223e0`
- `0x100428720`
- `0x10042aa50`
- `0x100430960`
- `0x100430d60`
- `0x1006d9d20`
- `0x100a3c790`
- `0x1011bd320`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1011bd788`
- `KERNEL32!HeapFree` at `0x1011bd9a9`
- `KERNEL32!HeapFree` at `0x1011bde09`
- `KERNEL32!HeapFree` at `0x1011be006`
- `KERNEL32!HeapFree` at `0x1011be409`
- `KERNEL32!HeapFree` at `0x1011be5df`
- `KERNEL32!HeapFree` at `0x1011bd788`
- `KERNEL32!HeapFree` at `0x1011bd9a9`
- `KERNEL32!HeapFree` at `0x1011bde09`
- `KERNEL32!HeapFree` at `0x1011be006`
- `KERNEL32!HeapFree` at `0x1011be409`
- `KERNEL32!HeapFree` at `0x1011be5df`
- `KERNEL32!GetProcessHeap` at `0x1011bd775`
- `KERNEL32!GetProcessHeap` at `0x1011bd996`
- `KERNEL32!GetProcessHeap` at `0x1011bddf6`
- `KERNEL32!GetProcessHeap` at `0x1011bdff3`
- `KERNEL32!GetProcessHeap` at `0x1011be3f6`
- `KERNEL32!GetProcessHeap` at `0x1011be5cc`
- `KERNEL32!GetProcessHeap` at `0x1011bd775`
- `KERNEL32!GetProcessHeap` at `0x1011bd996`
- `KERNEL32!GetProcessHeap` at `0x1011bddf6`
- `KERNEL32!GetProcessHeap` at `0x1011bdff3`
- `KERNEL32!GetProcessHeap` at `0x1011be3f6`
- `KERNEL32!GetProcessHeap` at `0x1011be5cc`
- `KERNEL32!InitializeCriticalSection` at `0x1011bd4e5`
- `KERNEL32!InitializeCriticalSection` at `0x1011bd4e5`
- `KERNEL32!DeleteCriticalSection` at `0x1011bd796`
- `KERNEL32!DeleteCriticalSection` at `0x1011bd9b7`
- `KERNEL32!DeleteCriticalSection` at `0x1011bde17`
- `KERNEL32!DeleteCriticalSection` at `0x1011be014`
- `KERNEL32!DeleteCriticalSection` at `0x1011be417`
- `KERNEL32!DeleteCriticalSection` at `0x1011be5ed`
- `KERNEL32!DeleteCriticalSection` at `0x1011bd796`
- `KERNEL32!DeleteCriticalSection` at `0x1011bd9b7`
- `KERNEL32!DeleteCriticalSection` at `0x1011bde17`
- `KERNEL32!DeleteCriticalSection` at `0x1011be014`
- `KERNEL32!DeleteCriticalSection` at `0x1011be417`
- `KERNEL32!DeleteCriticalSection` at `0x1011be5ed`
- `sqldk!?g_pfnAutoSetupContextForInternalTasksFactory@@3P6APEAVIAutoSetupExecContextsForInternalTasksImpl@@W4thread_type@@FPEB_W@ZEA` at `0x1011bd48c`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x1011bddcc`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x1011bdfc9`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x1011be3cc`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x1011be5a2`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x1011bdb9c`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x1011bdc0c`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x1011bdb9c`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x1011bdc0c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1011bdad0`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1011be135`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1011bdad0`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1011be135`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x1011be48f`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x1011be48f`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1011bdb83`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1011bdbf3`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1011bdb83`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1011bdbf3`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x1011bd58d`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x1011bd58d`
- `sqldk!SystemThread_TlsIndex` at `0x1011bd366`
- `sqldk!SystemThread_TlsIndex` at `0x1011bd3e6`
- `sqldk!SystemThread_TlsIndex` at `0x1011bd548`
- `sqldk!SystemThread_TlsIndex` at `0x1011bd5a6`
- `sqldk!SystemThread_TlsIndex` at `0x1011bda2d`
- `sqldk!SystemThread_TlsIndex` at `0x1011bda5e`
- `sqldk!SystemThread_TlsIndex` at `0x1011be085`
- `sqldk!SystemThread_TlsIndex` at `0x1011be217`
- `sqldk!SystemThread_TlsIndex` at `0x1011be2e5`
- `sqldk!SystemThread_TlsIndex` at `0x1011be457`
- `sqldk!SystemThread_TlsOffset` at `0x1011bd36f`
- `sqldk!SystemThread_TlsOffset` at `0x1011bd3ef`
- `sqldk!SystemThread_TlsOffset` at `0x1011bd551`
- `sqldk!SystemThread_TlsOffset` at `0x1011bd5af`
- `sqldk!SystemThread_TlsOffset` at `0x1011bda36`
- `sqldk!SystemThread_TlsOffset` at `0x1011bda67`
- `sqldk!SystemThread_TlsOffset` at `0x1011be096`
- `sqldk!SystemThread_TlsOffset` at `0x1011be220`
- `sqldk!SystemThread_TlsOffset` at `0x1011be2ee`
- `sqldk!SystemThread_TlsOffset` at `0x1011be460`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1011bd38a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1011bd425`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1011bd56c`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1011bd5ca`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1011be23b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1011be479`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1011bd38a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1011bd425`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1011bd56c`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1011bd5ca`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1011be23b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1011be479`
- `sqldk!??_V@YAXPEAX@Z` at `0x1011bdd92`
- `sqldk!??_V@YAXPEAX@Z` at `0x1011bdd9c`
- `sqldk!??_V@YAXPEAX@Z` at `0x1011bdf8f`
- `sqldk!??_V@YAXPEAX@Z` at `0x1011bdf99`
- `sqldk!??_V@YAXPEAX@Z` at `0x1011be38d`
- `sqldk!??_V@YAXPEAX@Z` at `0x1011be39c`
- `sqldk!??_V@YAXPEAX@Z` at `0x1011be568`
- `sqldk!??_V@YAXPEAX@Z` at `0x1011be572`
- `sqldk!??_V@YAXPEAX@Z` at `0x1011bdd92`
- `sqldk!??_V@YAXPEAX@Z` at `0x1011bdd9c`
- `sqldk!??_V@YAXPEAX@Z` at `0x1011bdf8f`
- `sqldk!??_V@YAXPEAX@Z` at `0x1011bdf99`
- `sqldk!??_V@YAXPEAX@Z` at `0x1011be38d`
- `sqldk!??_V@YAXPEAX@Z` at `0x1011be39c`
- `sqldk!??_V@YAXPEAX@Z` at `0x1011be568`
- `sqldk!??_V@YAXPEAX@Z` at `0x1011be572`
- `sqlmin!?UpdateConfigValue@@YAXKAEAVCXVariant@@PEAVIMemObj@@PEAVBaseXact@@@Z` at `0x1011be264`
- `sqlmin!?UpdateConfigValue@@YAXKAEAVCXVariant@@PEAVIMemObj@@PEAVBaseXact@@@Z` at `0x1011be264`
- `sqlmin!?reconfig@@YAXPEAVBaseXact@@KHHH@Z` at `0x1011be28c`
- `sqlmin!?reconfig@@YAXPEAVBaseXact@@KHHH@Z` at `0x1011be334`
- `sqlmin!?reconfig@@YAXPEAVBaseXact@@KHHH@Z` at `0x1011be28c`
- `sqlmin!?reconfig@@YAXPEAVBaseXact@@KHHH@Z` at `0x1011be334`
- `sqlmin!?GetMasterDbId@@YAGXZ` at `0x1011bd9e5`
- `sqlmin!?GetMasterDbId@@YAGXZ` at `0x1011bd9e5`
- `hostregdll!HostReg_GetSecretElements` at `0x1011bd8a5`
- `hostregdll!HostReg_GetSecretElements` at `0x1011bd8a5`
- `hostregdll!HostReg_FreeElementData` at `0x1011bd984`
- `hostregdll!HostReg_FreeElementData` at `0x1011bdde4`
- `hostregdll!HostReg_FreeElementData` at `0x1011bdfe1`
- `hostregdll!HostReg_FreeElementData` at `0x1011be3e4`
- `hostregdll!HostReg_FreeElementData` at `0x1011be5ba`
- `hostregdll!HostReg_FreeElementData` at `0x1011bd984`
- `hostregdll!HostReg_FreeElementData` at `0x1011bdde4`
- `hostregdll!HostReg_FreeElementData` at `0x1011bdfe1`
- `hostregdll!HostReg_FreeElementData` at `0x1011be3e4`
- `hostregdll!HostReg_FreeElementData` at `0x1011be5ba`
- `hostregdll!HostReg_GetSecret` at `0x1011bd630`
- `hostregdll!HostReg_GetSecret` at `0x1011bd630`

## string_xrefs

- `0x1011bdb31`: `FailoverProcTaskInternal`
- `0x1011be1a5`: `FailoverProcTaskInternal`
- `0x1011bdac7`: `rwMode == CMsqlXact::ReadOnly || ctrOption == CMsqlXact::SupportCTR || !m_pMsqlXact->FSupportsCTR ()`
- `0x1011be12c`: `rwMode == CMsqlXact::ReadOnly || ctrOption == CMsqlXact::SupportCTR || !m_pMsqlXact->FSupportsCTR ()`

## pseudocode

```c
// Hidden C++ exception states: #wind=29
void *FailoverProcTaskInternal(void)
{
  __int64 v0; // rbx
  __int64 v1; // rax
  struct IMemObj *v2; // r13
  __int64 v3; // r14
  __int64 v4; // rbx
  unsigned int v5; // r14d
  __int64 v6; // rcx
  int v7; // r15d
  __int64 *v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rbx
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rbx
  __int64 v14; // rdx
  HANDLE ProcessHeap; // rax
  __int32 v16; // eax
  HANDLE v17; // rax
  const wchar_t *v18; // r15
  unsigned __int16 MasterDbId; // ax
  char v20; // bl
  __int64 v21; // r14
  __int64 v22; // rax
  unsigned int v23; // ebx
  unsigned __int64 v24; // rax
  unsigned __int64 v25; // kr10_8
  void *v26; // r12
  struct __crt_locale_pointers *DefaultLocale; // rax
  __int64 v28; // rcx
  unsigned int v29; // ebx
  unsigned __int64 v30; // rax
  int *v31; // r13
  struct __crt_locale_pointers *v32; // rax
  __int32 v33; // eax
  HANDLE v34; // rax
  __int32 v35; // eax
  HANDLE v36; // rax
  __int64 v37; // r8
  char v38; // bl
  __int64 v39; // rbx
  __int64 v40; // r8
  struct BaseXact *v41; // rax
  struct BaseXact *v42; // rax
  HANDLE v43; // rax
  void (__fastcall ***v44)(_QWORD, __int64); // rcx
  __int64 v45; // rbx
  struct Worker *v46; // rcx
  __int32 v47; // eax
  HANDLE v48; // rax
  void *result; // rax
  __int64 v50; // rax
  int v51; // [rsp+20h] [rbp-AE8h]
  int v52; // [rsp+20h] [rbp-AE8h]
  int v53; // [rsp+30h] [rbp-AD8h]
  int v54; // [rsp+50h] [rbp-AB8h] BYREF
  __m128i si128; // [rsp+58h] [rbp-AB0h] BYREF
  int v56; // [rsp+68h] [rbp-AA0h]
  __int64 v57; // [rsp+70h] [rbp-A98h] BYREF
  unsigned int v58; // [rsp+78h] [rbp-A90h]
  __int128 v59; // [rsp+80h] [rbp-A88h]
  wchar_t *v60; // [rsp+90h] [rbp-A78h]
  int *v61; // [rsp+98h] [rbp-A70h]
  __int64 v62; // [rsp+A0h] [rbp-A68h]
  int v63; // [rsp+A8h] [rbp-A60h] BYREF
  int v64; // [rsp+ACh] [rbp-A5Ch] BYREF
  int v65; // [rsp+B0h] [rbp-A58h]
  __int128 v66; // [rsp+B8h] [rbp-A50h]
  __int64 v67; // [rsp+C8h] [rbp-A40h]
  int v68; // [rsp+D0h] [rbp-A38h]
  __int16 v69; // [rsp+D4h] [rbp-A34h]
  const wchar_t *v70; // [rsp+D8h] [rbp-A30h]
  struct _RTL_CRITICAL_SECTION CriticalSection; // [rsp+E0h] [rbp-A28h] BYREF
  LPVOID lpMem; // [rsp+108h] [rbp-A00h]
  int v73; // [rsp+110h] [rbp-9F8h]
  void *v74; // [rsp+118h] [rbp-9F0h]
  int v75; // [rsp+120h] [rbp-9E8h] BYREF
  __int64 v76; // [rsp+128h] [rbp-9E0h]
  int v77; // [rsp+130h] [rbp-9D8h] BYREF
  int v78; // [rsp+134h] [rbp-9D4h]
  __int64 v79; // [rsp+138h] [rbp-9D0h]
  int v80; // [rsp+140h] [rbp-9C8h] BYREF
  __int64 v81; // [rsp+148h] [rbp-9C0h]
  __int64 v82; // [rsp+150h] [rbp-9B8h]
  __int64 v83; // [rsp+158h] [rbp-9B0h]
  __int64 v84; // [rsp+160h] [rbp-9A8h]
  bool v85; // [rsp+170h] [rbp-998h]
  char v86; // [rsp+180h] [rbp-988h] BYREF
  char v87[7]; // [rsp+181h] [rbp-987h] BYREF
  __int64 v88; // [rsp+188h] [rbp-980h]
  __int64 v89; // [rsp+190h] [rbp-978h]
  int v90; // [rsp+198h] [rbp-970h]
  _QWORD v91[2]; // [rsp+1A0h] [rbp-968h] BYREF
  __int128 v92; // [rsp+1B0h] [rbp-958h]
  const wchar_t **v93; // [rsp+1C0h] [rbp-948h]
  __int64 v94; // [rsp+1C8h] [rbp-940h]
  const wchar_t *v95; // [rsp+1D0h] [rbp-938h]
  __int128 v96; // [rsp+1D8h] [rbp-930h]
  wchar_t **v97; // [rsp+1E8h] [rbp-920h]
  char v98[8]; // [rsp+1F0h] [rbp-918h] BYREF
  int v99; // [rsp+1F8h] [rbp-910h]
  int v100; // [rsp+200h] [rbp-908h]
  __int64 **v101; // [rsp+208h] [rbp-900h]
  _BYTE *v102; // [rsp+210h] [rbp-8F8h]
  __int64 v103; // [rsp+218h] [rbp-8F0h]
  __int64 *v104; // [rsp+220h] [rbp-8E8h] BYREF
  __int64 v105; // [rsp+228h] [rbp-8E0h]
  _BYTE v106[528]; // [rsp+230h] [rbp-8D8h] BYREF
  __int64 v107; // [rsp+440h] [rbp-6C8h]
  __int64 v108; // [rsp+448h] [rbp-6C0h]
  __int64 v109; // [rsp+450h] [rbp-6B8h] BYREF
  __int32 v110; // [rsp+458h] [rbp-6B0h]
  __int32 v111; // [rsp+45Ch] [rbp-6ACh]
  __int32 v112; // [rsp+460h] [rbp-6A8h]
  __m128i v113; // [rsp+470h] [rbp-698h] BYREF
  int v114; // [rsp+480h] [rbp-688h]
  __int64 v115; // [rsp+490h] [rbp-678h]
  void *v116; // [rsp+498h] [rbp-670h]
  int *v117; // [rsp+4A0h] [rbp-668h]
  __int64 v118; // [rsp+4A8h] [rbp-660h]
  _QWORD *v119; // [rsp+4B0h] [rbp-658h]
  int v120; // [rsp+4B8h] [rbp-650h]
  _BYTE v121[16]; // [rsp+4C0h] [rbp-648h] BYREF
  _BYTE v122[24]; // [rsp+4D0h] [rbp-638h] BYREF
  _BYTE v123[40]; // [rsp+4E8h] [rbp-620h] BYREF
  _BYTE v124[48]; // [rsp+510h] [rbp-5F8h] BYREF
  _BYTE v125[1440]; // [rsp+540h] [rbp-5C8h] BYREF

  v115 = -2;
  v0 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v1 = *(_QWORD *)(v0 + 256);
  if ( !v1 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v1 = *(_QWORD *)(v0 + 256);
  }
  v2 = *(struct IMemObj **)(v1 + 1000);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v56 = 0;
  v67 = 0;
  v68 = 1;
  v69 = 0;
  v70 = L"Cloud Lifter failover proc";
  if ( !*(_QWORD *)(SystemThread_TlsOffset
                  + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)) )
  {
    v3 = SystemThread_TlsOffset + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex);
    v4 = *(_QWORD *)(v3 + 256);
    if ( !v4 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v4 = *(_QWORD *)(v3 + 256);
    }
    v62 = v4;
    v5 = *(_DWORD *)(v4 + 800);
    HIDWORD(v61) = (v5 >> 11) & 1;
    if ( (v5 & 4) != 0 && (v6 = *(_QWORD *)(v4 + 608)) != 0 )
    {
      v7 = 1;
      LODWORD(v61) = 1;
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v6 + 16LL))(v6, v4, 1);
    }
    else
    {
      v7 = 0;
      LODWORD(v61) = 0;
    }
    v67 = g_pfnAutoSetupContextForInternalTasksFactory(1, 0, L"Cloud Lifter failover proc");
    (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v67 + 8LL))(v67, 1, 0);
    if ( v7 )
    {
      v8 = *(__int64 **)(v4 + 608);
      v9 = *v8;
      if ( (v5 & 0x800) != 0 )
        (*(void (__fastcall **)(__int64 *, __int64))(v9 + 24))(v8, v4);
      else
        (*(void (__fastcall **)(__int64 *, __int64))(v9 + 8))(v8, v4);
    }
  }
  lpMem = 0;
  v73 = 0;
  InitializeCriticalSection(&CriticalSection);
  Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v75, 1);
  v61 = &v77;
  v80 = 536872228;
  v81 = 0;
  v83 = 0;
  v82 = 0;
  v84 = 0;
  v85 = 0;
  v10 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v11 = *(_QWORD *)(v10 + 256);
  if ( !v11 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v11 = *(_QWORD *)(v10 + 256);
  }
  v12 = *(_QWORD *)(v11 + 600);
  if ( v12 )
    v85 = (unsigned int)SOS_Task::PushWait(v12, &v80) == 0;
  v13 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v14 = *(_QWORD *)(v13 + 256);
  if ( !v14 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v14 = *(_QWORD *)(v13 + 256);
  }
  v79 = v14;
  v78 = (*(_DWORD *)(v14 + 800) >> 11) & 1;
  if ( v78 || (*(_BYTE *)(v14 + 800) & 4) == 0 )
  {
    v77 = 1;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v14 + 608) + 8LL))(*(_QWORD *)(v14 + 608));
  }
  else
  {
    v77 = 0;
  }
  if ( (int)HostReg_GetSecret(L"FailoverProcSettings", &CriticalSection, 0xFFFFFFFFLL) < 0 )
  {
    if ( (dword_102EDCA20 & 0x40) != 0 )
    {
      v99 = 0x10000;
      v100 = 0;
      v101 = &v104;
      v102 = v106;
      v107 = 0;
      v103 = 0;
      v108 = 0;
      v104 = &v109;
      v105 = 20;
      v109 = 0;
      v110 = si128.m128i_u16[0];
      v111 = si128.m128i_i32[1];
      v112 = si128.m128i_i32[3];
      XeSqlPkg::failover_proc_execution_status::Publish((XeSqlPkg::failover_proc_execution_status *)v98);
    }
    v61 = &v77;
    if ( v77 )
    {
      if ( v78 )
        *(_DWORD *)(v79 + 800) |= 0x800u;
      else
        (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v79 + 608) + 16LL))(
          *(_QWORD *)(v79 + 608),
          v79,
          1);
    }
    SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)&v80);
    *(_DWORD *)(v76 + 616) &= ~v75;
    if ( lpMem )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, lpMem);
    }
LABEL_33:
    DeleteCriticalSection(&CriticalSection);
    goto LABEL_135;
  }
  v61 = &v77;
  if ( v77 )
  {
    if ( v78 )
      *(_DWORD *)(v79 + 800) |= 0x800u;
    else
      (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v79 + 608) + 16LL))(
        *(_QWORD *)(v79 + 608),
        v79,
        1);
  }
  SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)&v80);
  *(_DWORD *)(v76 + 616) &= ~v75;
  v91[0] = 1;
  v91[1] = L"Name";
  v92 = 0;
  v93 = 0;
  v94 = 1;
  v95 = L"Text";
  v96 = 0;
  v97 = 0;
  v119 = v91;
  v120 = 2;
  if ( (unsigned int)HostReg_GetSecretElements(&CriticalSection, L"FailoverProc", 2, v91) )
  {
    if ( (dword_102EDCA20 & 0x40) != 0 )
    {
      v99 = 0x10000;
      v100 = 0;
      v101 = &v104;
      v102 = v106;
      v107 = 0;
      v103 = 0;
      v108 = 0;
      v104 = &v109;
      v105 = 20;
      v109 = 0x100000001LL;
      v16 = si128.m128i_i32[0];
      if ( v56 != 1 )
        v16 = si128.m128i_u16[0];
      v110 = v16;
      v111 = si128.m128i_i32[1];
      v112 = si128.m128i_i32[3];
      XeSqlPkg::failover_proc_execution_status::Publish((XeSqlPkg::failover_proc_execution_status *)v98);
    }
    HostReg_FreeElementData(2, v91);
    if ( lpMem )
    {
      v17 = GetProcessHeap();
      HeapFree(v17, 0, lpMem);
    }
    goto LABEL_33;
  }
  v18 = *v93;
  v60 = *v97;
  v54 = 0;
  MasterDbId = GetMasterDbId();
  CAutoDb::FUse((CAutoDb *)&v54, MasterDbId, 0, 1, 0, 0x80u);
  v57 = 0;
  v59 = 0;
  v58 = 1;
  *(_QWORD *)&v59 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                          + SystemThread_TlsOffset)
                              + 144LL);
  v20 = *(_BYTE *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset)
                 + 152LL);
  if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)v59 + 464LL))(v59) )
  {
    if ( v20 && (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)v59 + 488LL))(v59) )
      utassert_fail(
        1u,
        "rwMode == CMsqlXact::ReadOnly || ctrOption == CMsqlXact::SupportCTR || !m_pMsqlXact->FSupportsCTR ()",
        "automsqlxact.cpp",
        235,
        0);
    (*(void (__fastcall **)(_QWORD, __int64, __int64, char *))(*(_QWORD *)v59 + 232LL))(v59, 2, 1, (char *)&v57 + 4);
    v58 = 1;
    LODWORD(v57) = 3;
  }
  else
  {
    (*(void (__fastcall **)(_QWORD, const wchar_t *, __int64, __int64, int, int, _BYTE, _QWORD, bool))(*(_QWORD *)v59 + 8LL))(
      v59,
      L"FailoverProcTaskInternal",
      48,
      1,
      2,
      1,
      0,
      0,
      v20 != 0);
    LODWORD(v57) = 1;
  }
  v21 = -1;
  v22 = -1;
  do
    ++v22;
  while ( v18[v22] );
  v23 = v22 + 29;
  v25 = (unsigned int)(v22 + 29);
  v24 = 2 * v25;
  if ( !is_mul_ok(v25, 2u) )
    v24 = -1;
  v26 = operator new[](v24, v2, "sql\\ntdbms\\msql\\proc\\failoverproc.cpp", 149, 3u);
  v74 = v26;
  v116 = v26;
  DefaultLocale = GetDefaultLocale();
  StringCchPrintf_lW((wchar_t *)v26, v23, L"drop procedure if exists %ls", DefaultLocale, v18);
  v28 = -1;
  do
    ++v28;
  while ( v18[v28] );
  v29 = v28 + 9;
  v30 = 2LL * (unsigned int)(v28 + 9);
  if ( !is_mul_ok((unsigned int)(v28 + 9), 2u) )
    v30 = -1;
  v31 = (int *)operator new[](v30, v2, "sql\\ntdbms\\msql\\proc\\failoverproc.cpp", 161, 3u);
  v61 = v31;
  v117 = v31;
  v32 = GetDefaultLocale();
  StringCchPrintf_lW((wchar_t *)v31, v29, L"exec %ls", v32, v18);
  if ( (unsigned int)ExecSql((struct SQLError *)&si128, (const wchar_t *)v26, 0, 0, 0, 0) )
  {
    if ( (unsigned int)ExecSql((struct SQLError *)&si128, v60, 0, 0, 0, 0) )
    {
      CAutoMsqlXact::CommitNestedXact((CAutoMsqlXact *)&v57, 0);
      try
      {
        ExcHandler::ExcHandler(
          (ExcHandler *)v123,
          0,
          0,
          0,
          (int (*)(int, int, int, int, char *))MSQLErrorHandlerFunc,
          0);
        v63 = 0;
        v64 = 0;
        v66 = 0;
        v65 = 1;
        v37 = 8LL * SystemThread_TlsIndex;
        v60 = *(wchar_t **)(SystemThread_TlsOffset + *(_QWORD *)((char *)NtCurrentTeb()->ThreadLocalStoragePointer + v37));
        *(_QWORD *)&v66 = *((_QWORD *)v60 + 18);
        v60 = *(wchar_t **)(SystemThread_TlsOffset + *(_QWORD *)((char *)NtCurrentTeb()->ThreadLocalStoragePointer + v37));
        v38 = *((_BYTE *)v60 + 152);
        LODWORD(v60) = v38 != 0;
        if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)v66 + 464LL))(v66) )
        {
          if ( v38 && (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)v66 + 488LL))(v66) )
            utassert_fail(
              1u,
              "rwMode == CMsqlXact::ReadOnly || ctrOption == CMsqlXact::SupportCTR || !m_pMsqlXact->FSupportsCTR ()",
              "automsqlxact.cpp",
              235,
              0);
          (*(void (__fastcall **)(_QWORD, __int64, __int64, int *))(*(_QWORD *)v66 + 232LL))(v66, 2, 1, &v64);
          v65 = 1;
          v63 = 3;
        }
        else
        {
          LOBYTE(v53) = 0;
          (*(void (__fastcall **)(_QWORD, const wchar_t *, __int64, __int64, int, int, int, _QWORD, _DWORD))(*(_QWORD *)v66 + 8LL))(
            v66,
            L"FailoverProcTaskInternal",
            48,
            1,
            2,
            1,
            v53,
            0,
            (_DWORD)v60);
          v63 = 1;
        }
        v87[2] = 0;
        strcpy(v87, "h");
        v88 = 1;
        v89 = 0;
        v90 = 0;
        v86 = 0;
        v60 = (wchar_t *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v66 + 432LL))(v66);
        v39 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        v40 = *(_QWORD *)(v39 + 256);
        if ( !v40 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v40 = *(_QWORD *)(v39 + 256);
        }
        UpdateConfigValue(0x206u, (struct CXVariant *)&v86, *(struct IMemObj **)(v40 + 1000), (struct BaseXact *)v60);
        v41 = (struct BaseXact *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v66 + 432LL))(v66);
        reconfig(v41, 4u, 0, 1, 0);
        do
          ++v21;
        while ( v18[v21] );
        v60 = (wchar_t *)(2 * v21);
        WParseName::Parse((WParseName *)v124, v18, 2 * v21);
        CSQLObject::CSQLObject((CSQLObject *)v125, (const struct WParseName *)v124, 1, 0, 1);
        CSQLSource::Execute(
          (CSQLSource *)v125,
          *(const struct CCompExecCtxtBasic **)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                + SystemThread_TlsIndex)
                                              + SystemThread_TlsOffset),
          0,
          0);
        v42 = (struct BaseXact *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v66 + 432LL))(v66);
        reconfig(v42, 4u, 0, 1, 0);
        CAutoMsqlXact::CommitNestedXact((CAutoMsqlXact *)&v63, 0);
        CSQLObject::~CSQLObject((CSQLObject *)v125);
        if ( v63 )
          CAutoMsqlXact::RollbackNestedXact((CAutoMsqlXact *)&v63, 0);
        ExcHandler::~ExcHandler((ExcHandler *)v123);
      }
      catch ( SQLError v122 )
      {
        try
        {
          ExceptionBackout::ExceptionBackout((ExceptionBackout *)v121, (const struct SQLError *)v122);
          v50 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                      + SystemThread_TlsOffset)
                          + 128LL);
          *(_BYTE *)(v50 + 296) = 0;
          *(_DWORD *)(v50 + 76) &= ~0x2000000u;
          v113 = si128;
          v114 = v56;
          FireFailoverProcExecStatusEvent(4, &v113);
          v118 = 0;
          ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v121);
        }
        catch ( ShortStackException )
        {
          v26 = v74;
          v31 = v61;
          goto LABEL_120;
        }
        operator delete[](v61);
        operator delete[](v74);
        if ( (_DWORD)v57 )
          CAutoMsqlXact::RollbackNestedXact((CAutoMsqlXact *)&v57, 0);
        if ( v54 )
        {
          v54 = 0;
          g_dbtableFactory[6](0xFFFFFFFFLL, 16);
        }
        HostReg_FreeElementData(2, v91);
        if ( lpMem )
        {
          v43 = GetProcessHeap();
          HeapFree(v43, 0, lpMem);
        }
        DeleteCriticalSection(&CriticalSection);
        v44 = (void (__fastcall ***)(_QWORD, __int64))v67;
        if ( v67 )
          goto LABEL_136;
LABEL_137:
        result = 0;
      }
LABEL_120:
      v45 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v46 = *(struct Worker **)(v45 + 256);
      if ( !v46 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v46 = *(struct Worker **)(v45 + 256);
      }
      if ( *((_DWORD *)v46 + 139) )
        ExceptionPostCatchActions(v46);
      if ( (dword_102EDCA20 & 0x40) != 0 )
      {
        v99 = 0x10000;
        v100 = 0;
        v101 = &v104;
        v102 = v106;
        v107 = 0;
        v103 = 0;
        v108 = 0;
        v104 = &v109;
        v105 = 20;
        v109 = 0x500000005LL;
        v47 = si128.m128i_i32[0];
        if ( v56 != 1 )
          v47 = si128.m128i_u16[0];
        v110 = v47;
        v111 = si128.m128i_i32[1];
        v112 = si128.m128i_i32[3];
        XeSqlPkg::failover_proc_execution_status::Publish((XeSqlPkg::failover_proc_execution_status *)v98);
      }
      operator delete[](v31);
      operator delete[](v26);
      if ( (_DWORD)v57 )
        CAutoMsqlXact::RollbackNestedXact((CAutoMsqlXact *)&v57, 0);
      if ( v54 )
      {
        v54 = 0;
        g_dbtableFactory[6](0xFFFFFFFFLL, 16);
      }
      HostReg_FreeElementData(2, v91);
      if ( lpMem )
      {
        v48 = GetProcessHeap();
        HeapFree(v48, 0, lpMem);
      }
    }
    else
    {
      if ( (dword_102EDCA20 & 0x40) != 0 )
      {
        v99 = 0x10000;
        v100 = 0;
        v101 = &v104;
        v102 = v106;
        v107 = 0;
        v103 = 0;
        v108 = 0;
        v104 = &v109;
        v105 = 20;
        v109 = 0x300000003LL;
        v35 = si128.m128i_i32[0];
        if ( v56 != 1 )
          v35 = si128.m128i_u16[0];
        v110 = v35;
        v111 = si128.m128i_i32[1];
        v112 = si128.m128i_i32[3];
        XeSqlPkg::failover_proc_execution_status::Publish((XeSqlPkg::failover_proc_execution_status *)v98);
      }
      switch ( (_DWORD)v57 )
      {
        case 1:
        case 2:
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v59 + 32LL))(v59);
          break;
        case 3:
          LOBYTE(v52) = 0;
          (*(void (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, int))(*(_QWORD *)v59 + 248LL))(
            v59,
            2,
            v58,
            HIDWORD(v57),
            v52);
          break;
        case 4:
          LOBYTE(v52) = 0;
          (*(void (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, int))(*(_QWORD *)v59 + 248LL))(
            v59,
            1,
            v58,
            HIDWORD(v57),
            v52);
          break;
      }
      LODWORD(v57) = 0;
      operator delete[](v31);
      operator delete[](v26);
      if ( (_DWORD)v57 )
        CAutoMsqlXact::RollbackNestedXact((CAutoMsqlXact *)&v57, 0);
      if ( v54 )
      {
        v54 = 0;
        g_dbtableFactory[6](0xFFFFFFFFLL, 16);
      }
      HostReg_FreeElementData(2, v91);
      if ( !lpMem )
        goto LABEL_134;
      v36 = GetProcessHeap();
      HeapFree(v36, 0, lpMem);
    }
  }
  else
  {
    if ( (dword_102EDCA20 & 0x40) != 0 )
    {
      v99 = 0x10000;
      v100 = 0;
      v101 = &v104;
      v102 = v106;
      v107 = 0;
      v103 = 0;
      v108 = 0;
      v104 = &v109;
      v105 = 20;
      v109 = 0x200000002LL;
      v33 = si128.m128i_i32[0];
      if ( v56 != 1 )
        v33 = si128.m128i_u16[0];
      v110 = v33;
      v111 = si128.m128i_i32[1];
      v112 = si128.m128i_i32[3];
      XeSqlPkg::failover_proc_execution_status::Publish((XeSqlPkg::failover_proc_execution_status *)v98);
    }
    switch ( (_DWORD)v57 )
    {
      case 1:
      case 2:
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v59 + 32LL))(v59);
        break;
      case 3:
        LOBYTE(v51) = 0;
        (*(void (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, int))(*(_QWORD *)v59 + 248LL))(
          v59,
          2,
          v58,
          HIDWORD(v57),
          v51);
        break;
      case 4:
        LOBYTE(v51) = 0;
        (*(void (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, int))(*(_QWORD *)v59 + 248LL))(
          v59,
          1,
          v58,
          HIDWORD(v57),
          v51);
        break;
    }
    LODWORD(v57) = 0;
    operator delete[](v31);
    operator delete[](v26);
    if ( (_DWORD)v57 )
      CAutoMsqlXact::RollbackNestedXact((CAutoMsqlXact *)&v57, 0);
    if ( v54 )
    {
      v54 = 0;
      g_dbtableFactory[6](0xFFFFFFFFLL, 16);
    }
    HostReg_FreeElementData(2, v91);
    if ( !lpMem )
      goto LABEL_134;
    v34 = GetProcessHeap();
    HeapFree(v34, 0, lpMem);
  }
LABEL_134:
  DeleteCriticalSection(&CriticalSection);
LABEL_135:
  v44 = (void (__fastcall ***)(_QWORD, __int64))v67;
  if ( !v67 )
    goto LABEL_137;
LABEL_136:
  (**v44)(v44, 1);
  goto LABEL_137;
}

```

## disassembly

```asm
0x1011bd320  mov     rax, rsp
0x1011bd323  push    r13
0x1011bd325  push    r14
0x1011bd327  push    r15
0x1011bd329  sub     rsp, 0AF0h
0x1011bd330  mov     qword ptr [rax-678h], 0FFFFFFFFFFFFFFFEh
0x1011bd33b  mov     [rax+8], rbx
0x1011bd33f  mov     [rax+10h], rsi
0x1011bd343  mov     [rax+18h], rdi
0x1011bd347  mov     [rax+20h], r12
0x1011bd34b  mov     rax, cs:__security_cookie
0x1011bd352  xor     rax, rsp
0x1011bd355  mov     [rsp+0B08h+var_28], rax
0x1011bd35d  mov     rdx, gs:58h
0x1011bd366  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1011bd36d  mov     ecx, [rax]
0x1011bd36f  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1011bd376  mov     ebx, [rax]
0x1011bd378  add     rbx, [rdx+rcx*8]
0x1011bd37c  mov     rax, [rbx+100h]
0x1011bd383  test    rax, rax
0x1011bd386  jnz     short loc_1011BD397
0x1011bd388  xor     ecx, ecx
0x1011bd38a  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1011bd390  mov     rax, [rbx+100h]
0x1011bd397  mov     r13, [rax+3E8h]
0x1011bd39e  movdqa  xmm0, cs:__xmm@00000000ffffffffffffffff00000000
0x1011bd3a6  movdqu  [rsp+0B08h+var_AB0], xmm0
0x1011bd3ac  xor     edi, edi
0x1011bd3ae  mov     [rsp+0B08h+var_AA0], edi
0x1011bd3b2  mov     [rsp+0B08h+var_A40], rdi
0x1011bd3ba  mov     esi, 1
0x1011bd3bf  mov     [rsp+0B08h+var_A38], esi
0x1011bd3c6  mov     [rsp+0B08h+var_A34], di
0x1011bd3ce  lea     r12, aCloudLifterFai; "Cloud Lifter failover proc"
0x1011bd3d5  mov     [rsp+0B08h+var_A30], r12
0x1011bd3dd  mov     rdx, gs:58h
0x1011bd3e6  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1011bd3ed  mov     ecx, [rax]
0x1011bd3ef  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1011bd3f6  mov     r8d, [rax]
0x1011bd3f9  mov     rax, [rdx+rcx*8]
0x1011bd3fd  cmp     [r8+rax], rdi
0x1011bd401  jnz     loc_1011BD4CE
0x1011bd407  mov     rax, gs:58h
0x1011bd410  mov     r14, [rax+rcx*8]
0x1011bd414  add     r14, r8
0x1011bd417  mov     rbx, [r14+100h]
0x1011bd41e  test    rbx, rbx
0x1011bd421  jnz     short loc_1011BD432
0x1011bd423  xor     ecx, ecx
0x1011bd425  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1011bd42b  mov     rbx, [r14+100h]
0x1011bd432  mov     [rsp+0B08h+var_A68], rbx
0x1011bd43a  mov     r14d, [rbx+320h]
0x1011bd441  mov     eax, r14d
0x1011bd444  shr     eax, 0Bh
0x1011bd447  and     eax, 1
0x1011bd44a  mov     dword ptr [rsp+0B08h+var_A70+4], eax
0x1011bd451  test    r14b, 4
0x1011bd455  jz      short loc_1011BD47B
0x1011bd457  mov     rcx, [rbx+260h]
0x1011bd45e  test    rcx, rcx
0x1011bd461  jz      short loc_1011BD47B
0x1011bd463  mov     r15d, esi
0x1011bd466  mov     dword ptr [rsp+0B08h+var_A70], esi
0x1011bd46d  mov     rax, [rcx]
0x1011bd470  mov     r8d, esi
0x1011bd473  mov     rdx, rbx
0x1011bd476  call    qword ptr [rax+10h]
0x1011bd479  jmp     short loc_1011BD485
0x1011bd47b  mov     r15d, edi
0x1011bd47e  mov     dword ptr [rsp+0B08h+var_A70], edi
0x1011bd485  xor     edx, edx
0x1011bd487  mov     r8, r12
0x1011bd48a  mov     ecx, esi
0x1011bd48c  mov     rax, cs:__imp_?g_pfnAutoSetupContextForInternalTasksFactory@@3P6APEAVIAutoSetupExecContextsForInternalTasksImpl@@W4thread_type@@FPEB_W@ZEA; IAutoSetupExecContextsForInternalTasksImpl * (*g_pfnAutoSetupContextForInternalTasksFactory)(thread_type,short,wchar_t const *)
0x1011bd493  call    qword ptr [rax]
0x1011bd495  mov     [rsp+0B08h+var_A40], rax
0x1011bd49d  mov     r9, [rax]
0x1011bd4a0  xor     r8d, r8d
0x1011bd4a3  mov     edx, esi
0x1011bd4a5  mov     rcx, rax
0x1011bd4a8  call    qword ptr [r9+8]
0x1011bd4ac  nop
0x1011bd4ad  test    r15d, r15d
0x1011bd4b0  jz      short loc_1011BD4CE
0x1011bd4b2  mov     rcx, [rbx+260h]
0x1011bd4b9  mov     rax, [rcx]
0x1011bd4bc  mov     rdx, rbx
0x1011bd4bf  bt      r14d, 0Bh
0x1011bd4c4  jnb     short loc_1011BD4CB
0x1011bd4c6  call    qword ptr [rax+18h]
0x1011bd4c9  jmp     short loc_1011BD4CE
0x1011bd4cb  call    qword ptr [rax+8]
0x1011bd4ce  mov     [rsp+0B08h+lpMem], rdi
0x1011bd4d6  mov     [rsp+0B08h+var_9F8], edi
0x1011bd4dd  lea     rcx, [rsp+0B08h+CriticalSection]; lpCriticalSection
0x1011bd4e5  call    cs:__imp_InitializeCriticalSection
0x1011bd4eb  nop
0x1011bd4ec  mov     edx, esi
0x1011bd4ee  lea     rcx, [rsp+0B08h+var_9E8]
0x1011bd4f6  call    ??0TaskAutoOnFlags@Worker@@QEAA@W4TASK_FLAGS@@@Z; Worker::TaskAutoOnFlags::TaskAutoOnFlags(TASK_FLAGS)
0x1011bd4fb  nop
0x1011bd4fc  lea     rax, [rsp+0B08h+var_9D8]
0x1011bd504  mov     [rsp+0B08h+var_A70], rax
0x1011bd50c  mov     [rsp+0B08h+var_9C8], 20000524h
0x1011bd517  mov     [rsp+0B08h+var_9C0], rdi
0x1011bd51f  mov     [rsp+0B08h+var_9B0], rdi
0x1011bd527  mov     [rsp+0B08h+var_9B8], rdi
0x1011bd52f  mov     [rsp+0B08h+var_9A8], rdi
0x1011bd537  mov     [rsp+0B08h+var_998], 0
0x1011bd53f  mov     rdx, gs:58h
0x1011bd548  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1011bd54f  mov     ecx, [rax]
0x1011bd551  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1011bd558  mov     ebx, [rax]
0x1011bd55a  add     rbx, [rdx+rcx*8]
0x1011bd55e  mov     rax, [rbx+100h]
0x1011bd565  test    rax, rax
0x1011bd568  jnz     short loc_1011BD579
0x1011bd56a  xor     ecx, ecx
0x1011bd56c  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1011bd572  mov     rax, [rbx+100h]
0x1011bd579  mov     rcx, [rax+258h]
0x1011bd580  test    rcx, rcx
0x1011bd583  jz      short loc_1011BD59D
0x1011bd585  lea     rdx, [rsp+0B08h+var_9C8]
0x1011bd58d  call    cs:__imp_?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z; SOS_Task::PushWait(SOS_ExternalAutoWait *)
0x1011bd593  test    eax, eax
0x1011bd595  setz    [rsp+0B08h+var_998]
0x1011bd59d  mov     rdx, gs:58h
0x1011bd5a6  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1011bd5ad  mov     ecx, [rax]
0x1011bd5af  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1011bd5b6  mov     ebx, [rax]
0x1011bd5b8  add     rbx, [rdx+rcx*8]
0x1011bd5bc  mov     rdx, [rbx+100h]
0x1011bd5c3  test    rdx, rdx
0x1011bd5c6  jnz     short loc_1011BD5D7
0x1011bd5c8  xor     ecx, ecx
0x1011bd5ca  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1011bd5d0  mov     rdx, [rbx+100h]
0x1011bd5d7  mov     [rsp+0B08h+var_9D0], rdx
0x1011bd5df  mov     eax, [rdx+320h]
0x1011bd5e5  shr     eax, 0Bh
0x1011bd5e8  and     eax, 1
0x1011bd5eb  mov     [rsp+0B08h+var_9D4], eax
0x1011bd5f2  jnz     short loc_1011BD606
0x1011bd5f4  test    byte ptr [rdx+320h], 4
0x1011bd5fb  jz      short loc_1011BD606
0x1011bd5fd  mov     [rsp+0B08h+var_9D8], edi
0x1011bd604  jmp     short loc_1011BD61B
0x1011bd606  mov     [rsp+0B08h+var_9D8], esi
0x1011bd60d  mov     rcx, [rdx+260h]
0x1011bd614  mov     rax, [rcx]
0x1011bd617  call    qword ptr [rax+8]
0x1011bd61a  nop
0x1011bd61b  mov     r8d, 0FFFFFFFFh
0x1011bd621  lea     rdx, [rsp+0B08h+CriticalSection]
0x1011bd629  lea     rcx, aFailoverprocse; "FailoverProcSettings"
0x1011bd630  call    cs:__imp_HostReg_GetSecret
0x1011bd636  test    eax, eax
0x1011bd638  jns     loc_1011BD7A2
0x1011bd63e  test    byte ptr cs:dword_102EDCA20, 40h
0x1011bd645  jz      loc_1011BD6FC
0x1011bd64b  mov     [rsp+0B08h+var_910], 10000h
0x1011bd656  mov     [rsp+0B08h+var_908], edi
0x1011bd65d  lea     rax, [rsp+0B08h+var_8E8]
0x1011bd665  mov     [rsp+0B08h+var_900], rax
0x1011bd66d  lea     rax, [rsp+0B08h+var_8D8]
0x1011bd675  mov     [rsp+0B08h+var_8F8], rax
0x1011bd67d  mov     [rsp+0B08h+var_6C8], rdi
0x1011bd685  mov     [rsp+0B08h+var_8F0], rdi
0x1011bd68d  mov     [rsp+0B08h+var_6C0], rdi
0x1011bd695  lea     rax, [rsp+0B08h+var_6B8]
0x1011bd69d  mov     [rsp+0B08h+var_8E8], rax
0x1011bd6a5  mov     [rsp+0B08h+var_8E0], 14h
0x1011bd6b1  mov     [rsp+0B08h+var_6B8], rdi
0x1011bd6b9  cmp     [rsp+0B08h+var_AA0], 1
0x1011bd6be  mov     eax, dword ptr [rsp+0B08h+var_AB0]
0x1011bd6c2  jz      short loc_1011BD6C7
0x1011bd6c4  movzx   eax, ax
0x1011bd6c7  mov     [rsp+0B08h+var_6B0], eax
0x1011bd6ce  mov     rax, qword ptr [rsp+0B08h+var_AB0]
0x1011bd6d3  shr     rax, 20h
0x1011bd6d7  mov     [rsp+0B08h+var_6AC], eax
0x1011bd6de  mov     rax, qword ptr [rsp+0B08h+var_AB0+8]
0x1011bd6e3  shr     rax, 20h
0x1011bd6e7  mov     [rsp+0B08h+var_6A8], eax
0x1011bd6ee  lea     rcx, [rsp+0B08h+var_918]; this
0x1011bd6f6  call    ?Publish@failover_proc_execution_status@XeSqlPkg@@QEAAXXZ; XeSqlPkg::failover_proc_execution_status::Publish(void)
0x1011bd6fb  nop
0x1011bd6fc  lea     rax, [rsp+0B08h+var_9D8]
0x1011bd704  mov     [rsp+0B08h+var_A70], rax
0x1011bd70c  cmp     [rsp+0B08h+var_9D8], 0
0x1011bd714  jz      short loc_1011BD745
0x1011bd716  mov     rdx, [rsp+0B08h+var_9D0]
0x1011bd71e  mov     rcx, [rdx+260h]
0x1011bd725  cmp     [rsp+0B08h+var_9D4], 0
0x1011bd72d  jz      short loc_1011BD73B
0x1011bd72f  or      dword ptr [rdx+320h], 800h
0x1011bd739  jmp     short loc_1011BD745
0x1011bd73b  mov     rax, [rcx]
0x1011bd73e  mov     r8d, esi
0x1011bd741  call    qword ptr [rax+10h]
0x1011bd744  nop
0x1011bd745  lea     rcx, [rsp+0B08h+var_9C8]; this
0x1011bd74d  call    ??1SOS_ExternalAutoWait@@QEAA@XZ; SOS_ExternalAutoWait::~SOS_ExternalAutoWait(void)
0x1011bd752  nop
0x1011bd753  mov     ecx, [rsp+0B08h+var_9E8]
0x1011bd75a  not     ecx
0x1011bd75c  mov     rax, [rsp+0B08h+var_9E0]
0x1011bd764  and     [rax+268h], ecx
0x1011bd76a  cmp     [rsp+0B08h+lpMem], 0
0x1011bd773  jz      short loc_1011BD78E
0x1011bd775  call    cs:__imp_GetProcessHeap
0x1011bd77b  mov     rcx, rax; hHeap
0x1011bd77e  mov     r8, [rsp+0B08h+lpMem]; lpMem
0x1011bd786  xor     edx, edx; dwFlags
0x1011bd788  call    cs:__imp_HeapFree
0x1011bd78e  lea     rcx, [rsp+0B08h+CriticalSection]; lpCriticalSection
0x1011bd796  call    cs:__imp_DeleteCriticalSection
0x1011bd79c  nop
0x1011bd79d  jmp     loc_1011BE5F4
0x1011bd7a2  lea     rax, [rsp+0B08h+var_9D8]
0x1011bd7aa  mov     [rsp+0B08h+var_A70], rax
0x1011bd7b2  cmp     [rsp+0B08h+var_9D8], 0
0x1011bd7ba  jz      short loc_1011BD7EB
0x1011bd7bc  mov     rdx, [rsp+0B08h+var_9D0]
0x1011bd7c4  mov     rcx, [rdx+260h]
0x1011bd7cb  cmp     [rsp+0B08h+var_9D4], 0
0x1011bd7d3  jz      short loc_1011BD7E1
0x1011bd7d5  or      dword ptr [rdx+320h], 800h
0x1011bd7df  jmp     short loc_1011BD7EB
0x1011bd7e1  mov     rax, [rcx]
0x1011bd7e4  mov     r8d, esi
0x1011bd7e7  call    qword ptr [rax+10h]
0x1011bd7ea  nop
0x1011bd7eb  lea     rcx, [rsp+0B08h+var_9C8]; this
0x1011bd7f3  call    ??1SOS_ExternalAutoWait@@QEAA@XZ; SOS_ExternalAutoWait::~SOS_ExternalAutoWait(void)
0x1011bd7f8  nop
0x1011bd7f9  mov     ecx, [rsp+0B08h+var_9E8]
0x1011bd800  not     ecx
0x1011bd802  mov     rax, [rsp+0B08h+var_9E0]
0x1011bd80a  and     [rax+268h], ecx
0x1011bd810  mov     [rsp+0B08h+var_968], 1
0x1011bd81c  lea     rax, aName; "Name"
0x1011bd823  mov     [rsp+0B08h+var_960], rax
0x1011bd82b  xorps   xmm0, xmm0
0x1011bd82e  xor     eax, eax
0x1011bd830  movups  [rsp+0B08h+var_958], xmm0
0x1011bd838  mov     [rsp+0B08h+var_948], rax
0x1011bd840  mov     [rsp+0B08h+var_940], 1
0x1011bd84c  lea     rax, aText_3; "Text"
0x1011bd853  mov     [rsp+0B08h+var_938], rax
0x1011bd85b  xor     eax, eax
0x1011bd85d  movups  [rsp+0B08h+var_930], xmm0
0x1011bd865  mov     [rsp+0B08h+var_920], rax
0x1011bd86d  lea     rax, [rsp+0B08h+var_968]
0x1011bd875  mov     [rsp+0B08h+var_658], rax
0x1011bd87d  mov     [rsp+0B08h+var_650], 2
0x1011bd888  lea     r9, [rsp+0B08h+var_968]
0x1011bd890  mov     r8d, 2
0x1011bd896  lea     rdx, aFailoverproc; "FailoverProc"
0x1011bd89d  lea     rcx, [rsp+0B08h+CriticalSection]
0x1011bd8a5  call    cs:__imp_HostReg_GetSecretElements
0x1011bd8ab  test    eax, eax
0x1011bd8ad  jz      loc_1011BD9C3
0x1011bd8b3  test    byte ptr cs:dword_102EDCA20, 40h
0x1011bd8ba  jz      loc_1011BD977
0x1011bd8c0  mov     [rsp+0B08h+var_910], 10000h
0x1011bd8cb  mov     [rsp+0B08h+var_908], edi
0x1011bd8d2  lea     rax, [rsp+0B08h+var_8E8]
0x1011bd8da  mov     [rsp+0B08h+var_900], rax
0x1011bd8e2  lea     rax, [rsp+0B08h+var_8D8]
0x1011bd8ea  mov     [rsp+0B08h+var_8F8], rax
0x1011bd8f2  mov     [rsp+0B08h+var_6C8], rdi
0x1011bd8fa  mov     [rsp+0B08h+var_8F0], rdi
0x1011bd902  mov     [rsp+0B08h+var_6C0], rdi
0x1011bd90a  lea     rax, [rsp+0B08h+var_6B8]
0x1011bd912  mov     [rsp+0B08h+var_8E8], rax
0x1011bd91a  mov     [rsp+0B08h+var_8E0], 14h
0x1011bd926  mov     dword ptr [rsp+0B08h+var_6B8], esi
0x1011bd92d  mov     dword ptr [rsp+0B08h+var_6B8+4], esi
0x1011bd934  cmp     [rsp+0B08h+var_AA0], 1
0x1011bd939  mov     eax, dword ptr [rsp+0B08h+var_AB0]
0x1011bd93d  jz      short loc_1011BD942
0x1011bd93f  movzx   eax, ax
0x1011bd942  mov     [rsp+0B08h+var_6B0], eax
0x1011bd949  mov     rax, qword ptr [rsp+0B08h+var_AB0]
0x1011bd94e  shr     rax, 20h
0x1011bd952  mov     [rsp+0B08h+var_6AC], eax
0x1011bd959  mov     rax, qword ptr [rsp+0B08h+var_AB0+8]
0x1011bd95e  shr     rax, 20h
0x1011bd962  mov     [rsp+0B08h+var_6A8], eax
0x1011bd969  lea     rcx, [rsp+0B08h+var_918]; this
0x1011bd971  call    ?Publish@failover_proc_execution_status@XeSqlPkg@@QEAAXXZ; XeSqlPkg::failover_proc_execution_status::Publish(void)
0x1011bd976  nop
0x1011bd977  lea     rdx, [rsp+0B08h+var_968]
  ... truncated ...
```
