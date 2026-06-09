# RChangeServiceConfigW

- ea: `0x140068b60`
- end: `0x14006a7aa`
- name: `RChangeServiceConfigW`
- size: `7242`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, unsigned __int16 *, wchar_t *, __int64, unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned __int8 *, int, wchar_t *String1)`
- caller_count: `1`
- callee_count: `72`
- tags: `reparse_path, registry_config, loader_planting, service_task, installer_update`

## callers

- `0x1400748c0`

## callees

- `0x1400035a0`
- `0x140003e54`
- `0x140004c58`
- `0x140004c98`
- `0x1400083f0`
- `0x140008548`
- `0x14000ac50`
- `0x14000b7e4`
- `0x14000b958`
- `0x14000bebc`
- `0x14000c120`
- `0x14000c310`
- `0x14000c8f0`
- `0x14000c988`
- `0x14000ca18`
- `0x14000cee0`
- `0x14000cf60`
- `0x14000d1dc`
- `0x140011a78`
- `0x140013b0c`
- `0x140014bc4`
- `0x140015868`
- `0x140015a28`
- `0x140015b14`
- `0x140016804`
- `0x1400188fc`
- `0x140019014`
- `0x140019b14`
- `0x14001a230`
- `0x14001a350`
- `0x14001c87c`
- `0x14001e1c0`
- `0x14001f99c`
- `0x14001fdf0`
- `0x140020d84`
- `0x14002320c`
- `0x140023c94`
- `0x140023cb4`
- `0x140024864`
- `0x1400250c8`
- `0x1400275b8`
- `0x140028114`
- `0x14002cfac`
- `0x14002e930`
- `0x140035f80`
- `0x140036e10`
- `0x140038648`
- `0x140038698`
- `0x1400424a0`
- `0x1400427c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140068efc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140068efc`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x140068d47`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x140068d47`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14006a32d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14006a32d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14006a220`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14006a220`
- `ntdll!RtlAcquireResourceExclusive` at `0x140068f0c`
- `ntdll!RtlAcquireResourceExclusive` at `0x140068f0c`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x140068ef6`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x140068ef6`
- `ntdll!RtlReleaseResource` at `0x140068fcd`
- `ntdll!RtlReleaseResource` at `0x140069173`
- `ntdll!RtlReleaseResource` at `0x14006a213`
- `ntdll!RtlReleaseResource` at `0x140068fcd`
- `ntdll!RtlReleaseResource` at `0x140069173`
- `ntdll!RtlReleaseResource` at `0x14006a213`
- `ntdll!RtlAreAllAccessesGranted` at `0x140068cbc`
- `ntdll!RtlAreAllAccessesGranted` at `0x140068cbc`
- `ntdll!NtClose` at `0x14006a33d`
- `ntdll!NtClose` at `0x14006a33d`
- `ntdll!RtlNtStatusToDosError` at `0x14006a345`
- `ntdll!RtlNtStatusToDosError` at `0x14006a345`
- `ntdll!RtlFreeHeap` at `0x1400697a0`
- `ntdll!RtlFreeHeap` at `0x14006a245`
- `ntdll!RtlFreeHeap` at `0x14006a25d`
- `ntdll!RtlFreeHeap` at `0x14006a276`
- `ntdll!RtlFreeHeap` at `0x14006a28f`
- `ntdll!RtlFreeHeap` at `0x14006a2a8`
- `ntdll!RtlFreeHeap` at `0x14006a2c0`
- `ntdll!RtlFreeHeap` at `0x14006a2d9`
- `ntdll!RtlFreeHeap` at `0x14006a2f1`
- `ntdll!RtlFreeHeap` at `0x14006a30a`
- `ntdll!RtlFreeHeap` at `0x14006a323`
- `ntdll!RtlFreeHeap` at `0x1400697a0`
- `ntdll!RtlFreeHeap` at `0x14006a245`
- `ntdll!RtlFreeHeap` at `0x14006a25d`
- `ntdll!RtlFreeHeap` at `0x14006a276`
- `ntdll!RtlFreeHeap` at `0x14006a28f`
- `ntdll!RtlFreeHeap` at `0x14006a2a8`
- `ntdll!RtlFreeHeap` at `0x14006a2c0`
- `ntdll!RtlFreeHeap` at `0x14006a2d9`
- `ntdll!RtlFreeHeap` at `0x14006a2f1`
- `ntdll!RtlFreeHeap` at `0x14006a30a`
- `ntdll!RtlFreeHeap` at `0x14006a323`
- `ntdll!RtlAllocateHeap` at `0x140069717`
- `ntdll!RtlAllocateHeap` at `0x14006992d`
- `ntdll!RtlAllocateHeap` at `0x140069717`
- `ntdll!RtlAllocateHeap` at `0x14006992d`

## string_xrefs

- `0x14006a563`: `ImagePath`
- `0x140069b04`: `BinaryPathName`

## pseudocode

```c
__int64 __fastcall RChangeServiceConfigW(
        ACCESS_MASK *a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        unsigned __int16 *a5,
        wchar_t *a6,
        unsigned int *a7,
        unsigned __int16 *a8,
        unsigned int a9,
        unsigned __int16 *a10,
        unsigned __int8 *a11,
        unsigned int a12,
        wchar_t *String1)
{
  _QWORD *v18; // rcx
  int v19; // eax
  wchar_t *v20; // r12
  unsigned __int8 *v21; // rbx
  wchar_t *v22; // rdi
  unsigned int *v23; // r14
  wchar_t *v24; // r15
  __int64 v25; // rsi
  RPC_STATUS v26; // eax
  char v27; // cl
  __int64 v28; // r13
  unsigned int v29; // eax
  unsigned int v30; // ebx
  unsigned int ConfigValue; // edi
  unsigned __int8 *v32; // r13
  PVOID v33; // r14
  unsigned int v34; // eax
  wchar_t *v35; // rdi
  int v36; // eax
  unsigned int v37; // eax
  __int64 v38; // rax
  unsigned int RealServiceType; // eax
  bool v40; // zf
  PRPC_ASYNC_STATE v41; // rcx
  __int64 v42; // rdx
  const unsigned __int16 *v43; // rbx
  int v44; // eax
  __int64 v45; // r8
  __int64 v46; // rdx
  __int16 v47; // di
  __int16 v48; // r15
  char v49; // al
  unsigned __int16 *v50; // r13
  const unsigned __int16 *v51; // rax
  PRPC_ASYNC_STATE v52; // rcx
  __int64 v53; // rdx
  unsigned int v54; // r8d
  __int64 v55; // rdx
  __int64 v56; // r8
  unsigned int v57; // ebx
  unsigned int v58; // eax
  unsigned int v59; // edi
  __int64 v60; // rcx
  __int64 v61; // r8
  __int64 v62; // r9
  unsigned __int16 *v63; // rbx
  unsigned int ImageFileName; // eax
  PRPC_ASYNC_STATE v65; // rcx
  __int64 v66; // rdx
  __int64 v67; // r9
  const unsigned __int16 *v68; // rdi
  __int64 v69; // rax
  SIZE_T v70; // rbx
  PVOID Heap; // rax
  PRPC_ASYNC_STATE v72; // rcx
  __int64 v73; // rdx
  PVOID v74; // r8
  unsigned int v75; // eax
  unsigned __int16 *v76; // rdi
  unsigned int v77; // eax
  PRPC_ASYNC_STATE v78; // rcx
  __int64 v79; // rdx
  unsigned int v80; // r8d
  unsigned __int16 *v81; // rax
  unsigned __int16 *v82; // r10
  unsigned int v83; // eax
  __int64 v84; // r8
  unsigned __int16 *v85; // rbx
  __int64 v86; // rcx
  __int64 v87; // r8
  __int64 v88; // r9
  unsigned __int16 *v89; // rbx
  unsigned __int8 *v90; // rbx
  unsigned int v91; // eax
  unsigned __int16 *v92; // rdx
  unsigned int v93; // ebx
  unsigned int v94; // r8d
  unsigned int v95; // r12d
  unsigned int v96; // r9d
  unsigned __int16 *v97; // r12
  enum _TRI_BOOL *v98; // rax
  __int64 v99; // rcx
  __int64 v100; // r8
  __int64 v101; // r9
  wchar_t *v102; // rbx
  unsigned int v103; // eax
  unsigned int v104; // eax
  __int64 v105; // rdx
  __int64 v106; // r8
  unsigned __int16 *JITReadDisplayName; // rax
  __int64 v108; // rdx
  __int64 v109; // r8
  unsigned int v110; // r14d
  unsigned int v111; // r15d
  const unsigned __int16 *v112; // rbx
  unsigned __int16 *v113; // rax
  unsigned int v114; // eax
  unsigned __int16 *v115; // rax
  PRPC_ASYNC_STATE v116; // r10
  const wchar_t *v117; // r9
  const wchar_t *v118; // rcx
  const wchar_t *v119; // rax
  PVOID v120; // rbx
  PVOID ProcessHeap; // rcx
  PVOID v122; // r8
  NTSTATUS v123; // eax
  unsigned int v124; // r13d
  __int64 v125; // rdx
  const unsigned __int16 *v126; // rax
  unsigned int v127; // eax
  __int64 v128; // rdx
  unsigned __int16 *v129; // r14
  const unsigned __int16 *v130; // rax
  __int64 v131; // rdx
  unsigned __int16 *v132; // rax
  const unsigned __int16 *v133; // r8
  __int64 v134; // rdx
  unsigned __int16 *v135; // rax
  __int64 v136; // rdx
  unsigned __int16 *v137; // rax
  __int64 *v138; // r9
  unsigned int v139; // eax
  unsigned __int16 *v140; // r9
  __int64 v141; // rdx
  unsigned __int16 *v142; // rax
  __int64 v143; // rdx
  unsigned __int16 *v144; // rax
  unsigned __int16 *v145; // r14
  __int64 v146; // rdx
  unsigned __int16 *v147; // rax
  __int64 v148; // rdx
  unsigned __int16 *v149; // rax
  int v150; // r14d
  __int64 v151; // rdx
  __int64 v152; // r8
  unsigned __int16 *v153; // rax
  unsigned int v154; // eax
  __int64 v155; // rdx
  __int64 v156; // r8
  unsigned __int16 *v157; // rax
  unsigned int v158; // [rsp+30h] [rbp-D8h]
  unsigned __int16 *v159; // [rsp+38h] [rbp-D0h]
  __int64 v160; // [rsp+68h] [rbp-A0h] BYREF
  HANDLE Handle; // [rsp+70h] [rbp-98h] BYREF
  unsigned int v162; // [rsp+78h] [rbp-90h] BYREF
  unsigned int v163; // [rsp+80h] [rbp-88h] BYREF
  char v164[4]; // [rsp+88h] [rbp-80h] BYREF
  unsigned int v165; // [rsp+8Ch] [rbp-7Ch] BYREF
  PVOID v166; // [rsp+90h] [rbp-78h] BYREF
  PVOID v167; // [rsp+98h] [rbp-70h] BYREF
  PVOID v168; // [rsp+A0h] [rbp-68h]
  unsigned int v169; // [rsp+A8h] [rbp-60h] BYREF
  unsigned int Pid; // [rsp+ACh] [rbp-5Ch] BYREF
  PVOID P; // [rsp+B0h] [rbp-58h] BYREF
  wchar_t *v172; // [rsp+B8h] [rbp-50h] BYREF
  const wchar_t *v173; // [rsp+C0h] [rbp-48h] BYREF
  int v174; // [rsp+C8h] [rbp-40h]
  int v175; // [rsp+CCh] [rbp-3Ch] BYREF
  unsigned int v176; // [rsp+D0h] [rbp-38h] BYREF
  unsigned int v177; // [rsp+D4h] [rbp-34h] BYREF
  int v178; // [rsp+D8h] [rbp-30h] BYREF
  PVOID v179; // [rsp+E0h] [rbp-28h] BYREF
  PVOID v180; // [rsp+E8h] [rbp-20h] BYREF
  PVOID v181; // [rsp+F0h] [rbp-18h] BYREF
  int v182; // [rsp+F8h] [rbp-10h] BYREF
  unsigned int v183; // [rsp+FCh] [rbp-Ch] BYREF
  int v184; // [rsp+100h] [rbp-8h]
  const wchar_t *v185; // [rsp+108h] [rbp+0h] BYREF
  PVOID v186; // [rsp+110h] [rbp+8h]
  PVOID v187; // [rsp+118h] [rbp+10h] BYREF
  PVOID v188; // [rsp+120h] [rbp+18h] BYREF
  HLOCAL hMem; // [rsp+128h] [rbp+20h] BYREF
  unsigned __int16 *v190; // [rsp+130h] [rbp+28h] BYREF
  ACCESS_MASK *v191; // [rsp+188h] [rbp+80h] BYREF
  unsigned int v192; // [rsp+190h] [rbp+88h]
  unsigned int v193; // [rsp+198h] [rbp+90h]
  unsigned int v194; // [rsp+1A0h] [rbp+98h]

  v194 = a4;
  v193 = a3;
  v192 = a2;
  v191 = a1;
  v169 = -1;
  Handle = 0;
  v168 = 0;
  v172 = 0;
  v163 = 0;
  v162 = 0;
  v186 = 0;
  v190 = 0;
  v174 = 255;
  v182 = 255;
  v175 = 255;
  v187 = 0;
  v181 = 0;
  v179 = 0;
  v177 = 0;
  v176 = 0;
  v183 = 0;
  P = 0;
  v166 = 0;
  v188 = 0;
  v167 = 0;
  v165 = 0;
  hMem = 0;
  v180 = 0;
  v164[0] = 0;
  ScSetTcpKeepalive();
  if ( ScShutdownInProgress )
    return 1115;
  if ( !(unsigned int)ScIsValidServiceHandle(a1) )
    return 6;
  v19 = ScCheckServiceProtectedProcess(v18, 0);
  v20 = String1;
  v21 = a11;
  if ( v19 )
  {
    if ( a3 != 2 )
      return 5;
    if ( a2 != -1 )
      return 5;
    if ( a4 != -1 )
      return 5;
    if ( a5 )
      return 5;
    v22 = a6;
    if ( a6 )
      return 5;
    v23 = a7;
    if ( a7 )
      return 5;
    v24 = a8;
    if ( a8 || a10 || a11 || String1 )
      return 5;
  }
  else
  {
    v24 = a8;
    v22 = a6;
    v23 = a7;
  }
  if ( !RtlAreAllAccessesGranted(a1[2], 2u) )
    return 5;
  if ( v23 && (!v22 || !*v22) )
  {
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->StubInfo, 10, WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids);
    return 87;
  }
  v25 = *((_QWORD *)a1 + 2);
  Pid = 0;
  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->UserInfo) & 0x100) != 0 )
  {
    v26 = I_RpcBindingInqLocalClientPID(0, &Pid);
    v27 = 0;
    if ( !v26 )
      v27 = Pid;
    WPP_SF_Sd(
      WPP_GLOBAL_Control->StubInfo,
      11,
      (unsigned int)WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids,
      *(_QWORD *)(v25 + 56),
      v27);
  }
  v28 = -1;
  if ( !a10 )
  {
    v30 = 0;
    goto LABEL_54;
  }
  v29 = ScValidateAccount(a10, *(const unsigned __int16 **)(v25 + 56), v21);
  v30 = v29;
  if ( !v29 )
  {
    v34 = ScCanonAccountName(a10, &v172);
    ConfigValue = v34;
    if ( v34 )
    {
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 13, WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids, v34);
      v168 = v172;
      goto LABEL_39;
    }
    v35 = v172;
    v168 = v172;
    if ( !(unsigned int)ScIsLocalSystemAccount(v172)
      && !(unsigned int)ScIsAccountInNtAuthDomain(v35)
      && !(unsigned int)ScIsVirtualServiceAccountName(v35) )
    {
      v36 = ((__int64 (__fastcall *)(_QWORD, wchar_t *, char *))g_pScExtFunctionPointers[11])(0, v35, v164);
      if ( v36 )
      {
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        {
          WPP_SF_SSD(
            WPP_GLOBAL_Control->StubInfo,
            14,
            (unsigned int)WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids,
            (_DWORD)v168,
            *(_QWORD *)(v25 + 56),
            v36);
        }
      }
      else if ( v164[0] )
      {
        v174 = 1;
        v175 = 1;
      }
      else
      {
        if ( !v35 )
          goto LABEL_73;
        if ( !*v35 )
          goto LABEL_73;
        v38 = -1;
        do
          ++v38;
        while ( v35[v38] );
        if ( v35[(unsigned int)v38 - 1] != 36 )
        {
LABEL_73:
          v174 = 0;
          v175 = 0;
        }
      }
    }
LABEL_54:
    RtlAcquireSRWLockExclusive(&g_TriggerRegistrationLock);
    GetCurrentThreadId();
    RtlAcquireResourceExclusive(&ScServiceRecordLock, 1u);
    CScmLock::LockAutoExclusive(v25 + 312, &v160);
    if ( v192 == -1 )
    {
      RealServiceType = CServiceRecord::GetRealServiceType((CServiceRecord *)v25);
    }
    else
    {
      v37 = v192 & 0xFFFFFEFF;
      if ( (v192 & 0xFFFFFEFF) != 0x10
        && v37 != 32
        && v37 != 80
        && v37 != 96
        && v37 != 208
        && v37 != 224
        && v37 != 528
        && v192 - 1 > 1 )
      {
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 15, WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids, v192);
        }
        goto LABEL_66;
      }
      RealServiceType = v192;
    }
    v40 = *(_BYTE *)(v25 + 80) >= 0;
    Pid = RealServiceType;
    if ( !v40 )
    {
      v41 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        goto LABEL_66;
      v42 = 16;
LABEL_81:
      WPP_SF_S(v41->StubInfo, v42, WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids, *(_QWORD *)(v25 + 56));
LABEL_66:
      ConfigValue = 87;
      goto LABEL_67;
    }
    if ( (RealServiceType & 0x40) != 0 && (a10 || a11) )
    {
      v41 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        goto LABEL_66;
      v42 = 17;
      goto LABEL_81;
    }
    v178 = RealServiceType & 0x30;
    if ( (RealServiceType & 0x30) != 0 && v30 )
    {
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 18, WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids, v30);
      ConfigValue = v30;
      goto LABEL_67;
    }
    if ( (*(_DWORD *)(v25 + 52) & 1) != 0 )
    {
      CServiceRecord::LogPidsWithOpenHandles((CServiceRecord *)v25);
      ConfigValue = 1072;
      goto LABEL_67;
    }
    v43 = a6;
    if ( (*(_DWORD *)(v25 + 52) & 8) != 0
      && a6
      && (unsigned int)CNameEntryList<CNameEntry>::FindEntry(&OrderGroupList, a6, &v173) )
    {
      ConfigValue = 87;
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        WPP_SF_Sd(
          WPP_GLOBAL_Control->StubInfo,
          19,
          (unsigned int)WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids,
          *(_QWORD *)(v25 + 56),
          87);
      goto LABEL_67;
    }
    if ( !(unsigned int)ScIsIndirectString(v20, 0) )
    {
      ConfigValue = ScValidateDisplayName(v20, (struct CServiceRecord *)v25);
      if ( ConfigValue )
      {
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->StubInfo, 20, WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids);
        }
        goto LABEL_67;
      }
    }
    v44 = CServiceRecord::GetRealServiceType((CServiceRecord *)v25);
    ConfigValue = ScCheckServiceConfigParms(
                    1,
                    *(const unsigned __int16 **)(v25 + 56),
                    v44,
                    v192,
                    v193,
                    v194,
                    a5,
                    v43,
                    v24,
                    a9,
                    a10);
    if ( ConfigValue
      || (ConfigValue = CServiceRecord::OpenServiceConfigKey((CServiceRecord *)v25, 0x2001Fu, v45, (HKEY *)&Handle)) != 0 )
    {
LABEL_67:
      CScmSyncLockExclusive::InternalUnlock((CScmSyncLockExclusive *)&v160);
      RtlReleaseResource(&ScServiceRecordLock);
      v32 = (unsigned __int8 *)v166;
      v33 = v167;
LABEL_340:
      RtlReleaseSRWLockExclusive(&g_TriggerRegistrationLock);
      goto LABEL_341;
    }
    v47 = v192;
    v184 = 0;
    v48 = 0;
    if ( v192 == -1 )
    {
      v58 = CServiceRecord::GetRealServiceType((CServiceRecord *)v25);
      v163 = v58;
      if ( a10 && (v58 & 0x100) != 0 && !(unsigned int)ScIsLocalSystemAccount(a10) )
      {
        v52 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        {
          goto LABEL_116;
        }
        v53 = 24;
        goto LABEL_129;
      }
      v57 = v163;
    }
    else
    {
      if ( (v192 & 0x10) == 0
        && (*(unsigned __int16 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v25 + 128LL))(v25, v46, 0) )
      {
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        {
          v49 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v25 + 128LL))(v25);
          WPP_SF_SLd(
            WPP_GLOBAL_Control->StubInfo,
            21,
            (unsigned int)WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids,
            *(_QWORD *)(v25 + 56),
            v47,
            v49 - 1);
        }
        goto LABEL_116;
      }
      if ( (v47 & 0x100) != 0 )
      {
        if ( a10 )
        {
          v51 = (const unsigned __int16 *)v168;
          if ( !v168 )
          {
            ConfigValue = ScCanonAccountName(a10, &v172);
            if ( ConfigValue )
            {
              CScmSyncLockExclusive::InternalUnlock((CScmSyncLockExclusive *)&v160);
              v168 = v172;
LABEL_123:
              v50 = a6;
              goto LABEL_311;
            }
            v51 = v172;
            v168 = v172;
          }
          if ( !(unsigned int)ScIsLocalSystemAccount(v51) )
          {
            v52 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
              || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
            {
              goto LABEL_116;
            }
            v53 = 22;
LABEL_129:
            WPP_SF_(v52->StubInfo, v53, WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids);
LABEL_116:
            ConfigValue = 87;
LABEL_117:
            CScmSyncLockExclusive::InternalUnlock((CScmSyncLockExclusive *)&v160);
            v50 = a6;
            goto LABEL_311;
          }
        }
        else
        {
          ConfigValue = ScAllocateAndReadConfigValue((HKEY)Handle, L"ObjectName", (unsigned __int16 **)&v179, 0);
          if ( ConfigValue )
            goto LABEL_131;
          if ( !v179 || !(unsigned int)ScIsLocalSystemAccount((const unsigned __int16 *)v179) )
          {
            v52 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
              || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
            {
              goto LABEL_116;
            }
            v53 = 23;
            goto LABEL_129;
          }
        }
      }
      ConfigValue = ScReadServiceType((HKEY)Handle, &v162);
      if ( ConfigValue
        || (v163 = v192, (ConfigValue = ScRegSetValueExW((HKEY)Handle, L"Type", v54, 4u, &v163, 4u)) != 0) )
      {
        CScmSyncLockExclusive::InternalUnlock((CScmSyncLockExclusive *)&v160);
        v163 = v162;
        goto LABEL_123;
      }
      v57 = v162;
      v48 = 1;
      v163 = v162;
    }
    v59 = v193;
    if ( v193 == -1 )
    {
      v63 = a5;
    }
    else
    {
      if ( (unsigned int)dword_1400BA2A0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400BA2A0, 0x400000000000LL, v56) )
      {
        v162 = v59;
        v185 = L"StartType";
        v173 = *(const wchar_t **)(v25 + 56);
        v159 = (unsigned __int16 *)&v162;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          v60,
          (__int64)&word_1400AE6A6,
          v61,
          v62,
          &v173,
          &v185);
      }
      if ( (unsigned int)IsEventEnabled(&ServiceConfigChangeStartType) )
        EventWriteServiceConfigChangeStartType(*(const unsigned __int16 **)(v25 + 56), v59);
      ConfigValue = ScReadGlobalStartType(
                      *(struct _SERVICE_CONFIG_ROOT **)(v25 + 216),
                      (HKEY)Handle,
                      *(const unsigned __int16 **)(v25 + 56),
                      v57,
                      *(_DWORD *)(v25 + 168) & 1,
                      &v177);
      if ( ConfigValue )
        goto LABEL_131;
      ConfigValue = ScReadStartType(
                      *(struct _SERVICE_CONFIG_ROOT **)(v25 + 216),
                      (HKEY)Handle,
                      *(const unsigned __int16 **)(v25 + 56),
                      v57,
                      *(_DWORD *)(v25 + 168) & 1,
                      &v176);
      if ( ConfigValue )
        goto LABEL_131;
      ConfigValue = ScWriteStartType(
                      *(struct _SERVICE_CONFIG_ROOT **)(v25 + 216),
                      (HKEY)Handle,
                      *(const unsigned __int16 **)(v25 + 56),
                      v193,
                      v57,
                      *(_DWORD *)(v25 + 168) & 1);
      if ( ConfigValue )
        goto LABEL_131;
      v48 |= 2u;
      ConfigValue = ScReadStartType(
                      *(struct _SERVICE_CONFIG_ROOT **)(v25 + 216),
                      (HKEY)Handle,
                      *(const unsigned __int16 **)(v25 + 56),
                      v57,
                      *(_DWORD *)(v25 + 168) & 1,
                      &v169);
      if ( ConfigValue )
        goto LABEL_131;
      v63 = a5;
      if ( !a5 )
      {
        if ( !v177 )
        {
          if ( !v193 )
            goto LABEL_195;
          ImageFileName = ScGetImageFileName((HKEY)Handle, 0, (unsigned __int16 **)&P);
          ConfigValue = ImageFileName;
          if ( ImageFileName )
          {
            if ( ImageFileName != 3 )
            {
              v65 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
              {
                goto LABEL_117;
              }
              v66 = 25;
              goto LABEL_166;
            }
            v68 = (const unsigned __int16 *)P;
          }
          else
          {
            v68 = (const unsigned __int16 *)P;
            if ( !ScIsArcName((unsigned __int16 *)P) )
            {
              v69 = -1;
              do
                ++v69;
              while ( v68[v69] );
              v70 = (unsigned int)(2 * v69 + 26);
              Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v70);
              v181 = Heap;
              if ( !Heap )
              {
                v72 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                  || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
                {
                  goto LABEL_176;
                }
                v73 = 26;
                goto LABEL_175;
              }
              StringCbCopyW((unsigned __int16 *)Heap, v70, L"\\SystemRoot\\");
              StringCbCatW((unsigned __int16 *)v181, v70, v68);
              v63 = (unsigned __int16 *)v181;
              a5 = (unsigned __int16 *)v181;
            }
          }
          v74 = (PVOID)v68;
          goto LABEL_180;
        }
        if ( !v193 )
        {
          v75 = ScGetImageFileName((HKEY)Handle, 0, (unsigned __int16 **)&P);
          ConfigValue = v75;
          if ( v75 )
          {
            if ( v75 != 3 )
            {
              v65 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
              {
                goto LABEL_117;
              }
              v66 = 27;
              v67 = v75;
              goto LABEL_167;
            }
          }
          else
          {
            v76 = (unsigned __int16 *)P;
            if ( !ScIsArcName((unsigned __int16 *)P) )
            {
              v77 = ScConvertToBootPathName(v76, (unsigned __int16 **)&v181);
              ConfigValue = v77;
              if ( v77 )
              {
                v78 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                  || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
                {
                  goto LABEL_117;
                }
                v79 = 28;
LABEL_192:
                WPP_SF_d(v78->StubInfo, v79, WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids, v77);
                goto LABEL_117;
              }
              v63 = (unsigned __int16 *)v181;
              v74 = P;
              a5 = (unsigned __int16 *)v181;
LABEL_180:
              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v74);
            }
          }
        }
      }
    }
LABEL_195:
    if ( v194 != -1 )
    {
      ConfigValue = ScReadErrorControl((HKEY)Handle, &v183);
      if ( ConfigValue )
        goto LABEL_131;
      v162 = v194;
      ConfigValue = ScRegSetValueExW((HKEY)Handle, L"ErrorControl", v80, 4u, &v162, 4u);
      if ( ConfigValue )
        goto LABEL_131;
      v48 |= 4u;
    }
    if ( v20 )
    {
      CServiceRecord::GetJITReadDisplayName((CServiceRecord *)v25, v55, v56);
      if ( *v20 && wcsicmp(v20, *(const wchar_t **)(v25 + 56)) )
      {
        do
          ++v28;
        while ( v20[v28] );
        v81 = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned int)(2 * v28 + 2));
        if ( !v81 )
        {
          v72 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
          {
            goto LABEL_176;
          }
          v73 = 29;
LABEL_175:
          WPP_SF_(v72->StubInfo, v73, WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids);
LABEL_176:
          ConfigValue = 8;
          goto LABEL_117;
        }
        StringCbCopyW(v81, (unsigned int)(2 * v28 + 2), v20);
      }
      else
      {
        v82 = 0;
      }
      CServiceRecord::UpdateDisplayName((CServiceRecord *)v25, v82, (unsigned __int16 **)&v180);
      v48 |= 0x400u;
      ConfigValue = ScReadOptionalString((HKEY)Handle, L"DisplayName", (unsigned __int16 **)&v188, 0);
      if ( ConfigValue )
        goto LABEL_131;
      v83 = ScWriteOptionalString((HKEY)Handle, L"DisplayName", v20);
      v20 = 0;
      ConfigValue = v83;
      if ( v83 )
        goto LABEL_131;
      v63 = a5;
      v48 |= 0x800u;
    }
    if ( v63 )
    {
      ImageFileName = ScGetImageFileName((HKEY)Handle, 0, (unsigned __int16 **)&P);
      ConfigValue = ImageFileName;
      if ( ImageFileName && ImageFileName != 3 )
      {
        v65 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        {
          goto LABEL_117;
        }
        v66 = 30;
        goto LABEL_166;
      }
      if ( (v163 & 0xB) == 0 )
      {
        if ( (unsigned int)dword_1400BA2A0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400BA2A0, 0x400000000000LL, v84) )
        {
          v162 = -1;
          v173 = L"BinaryPathName";
          v185 = *(const wchar_t **)(v25 + 56);
          v159 = (unsigned __int16 *)&v162;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            v86,
            (__int64)byte_1400AE65D,
            v87,
            v88,
            &v185,
            &v173);
        }
        if ( P )
        {
          v89 = a5;
          if ( (unsigned int)ScImagePathsMatch(a5, (const unsigned __int16 *)P) )
            goto LABEL_245;
        }
        else
        {
          v89 = a5;
        }
        ImageFileName = ScWriteImageFileName((HKEY)Handle, v89);
        ConfigValue = ImageFileName;
        if ( ImageFileName )
        {
          v65 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
          {
            goto LABEL_117;
          }
          v66 = 33;
LABEL_166:
          v67 = ImageFileName;
LABEL_167:
          WPP_SF_d(v65->StubInfo, v66, WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids, v67);
          goto LABEL_117;
        }
        if ( (unsigned int)IsEventEnabled(&ServiceConfigChangeBinaryPathName) )
          EventWriteServiceConfigChange(&ServiceConfigChangeBinaryPathName, *(const unsigned __int16 **)(v25 + 56), v89);
        goto LABEL_244;
      }
      v77 = ScCanonDriverImagePath(v193, v63, (unsigned __int16 **)&v187);
      ConfigValue = v77;
      if ( v77 )
      {
        v78 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        {
          goto LABEL_117;
        }
        v79 = 31;
        goto LABEL_192;
      }
      if ( !P )
      {
        v85 = (unsigned __int16 *)v187;
        goto LABEL_227;
      }
      v85 = (unsigned __int16 *)v187;
      if ( !(unsigned int)ScImagePathsMatch((const unsigned __int16 *)v187, (const unsigned __int16 *)P) )
      {
LABEL_227:
        ImageFileName = ScWriteImageFileName((HKEY)Handle, v85);
        ConfigValue = ImageFileName;
        if ( ImageFileName )
        {
          v65 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
          {
            goto LABEL_117;
          }
          v66 = 32;
          goto LABEL_166;
        }
LABEL_244:
        v48 |= 8u;
      }
    }
LABEL_245:
    v90 = (unsigned __int8 *)a8;
    if ( !a8 )
      goto LABEL_249;
    ScReadDependencies((HKEY)Handle, (unsigned __int16 **)&v166, *(const unsigned __int16 **)(v25 + 56));
    ConfigValue = ScUpdateServiceRecordConfig(
                    (struct CServiceRecord *)v25,
                    0xFFFFFFFF,
                    0xFFFFFFFF,
                    0xFFFFFFFF,
                    (enum _TRI_BOOL *)v20,
                    v20,
                    v90);
    if ( !ConfigValue )
    {
      v48 |= 0x40u;
      ConfigValue = ScWriteDependencies((HKEY)Handle, (unsigned __int16 *)v90, a9);
      if ( !ConfigValue )
      {
        v48 |= 0x80u;
LABEL_249:
        v50 = a6;
        if ( a6 )
        {
          v91 = ScAllocateAndReadConfigValue((HKEY)Handle, L"Group", &v190, 0);
          v92 = v190;
          v93 = *(_DWORD *)(v25 + 44);
          if ( v91 )
            v92 = v20;
          v184 = *(_DWORD *)(v25 + 44);
          v186 = v92;
          if ( !v92 || wcsicmp(v50, v92) )
          {
            ConfigValue = ScWriteGroupForThisService((HKEY)Handle, v50);
            if ( ConfigValue )
              goto LABEL_298;
            v48 |= 0x10u;
            ConfigValue = ScUpdateRegistryGroupPointer((struct CServiceRecord *)v25, v50);
            if ( ConfigValue )
              goto LABEL_298;
            v48 |= 0x200u;
            if ( *v50 == (_WORD)v20 || a7 == (unsigned int *)v20 )
            {
              v95 = v165;
            }
            else
            {
              ScGetUniqueTag(v50, &v165);
              v95 = v165;
              if ( v165 )
              {
                v158 = ConfigValue + 4;
                v96 = ConfigValue + 4;
LABEL_257:
                v162 = v95;
                ConfigValue = ScRegSetValueExW((HKEY)Handle, L"Tag", v94, v96, &v162, v158);
                if ( ConfigValue )
                  goto LABEL_298;
                goto LABEL_267;
              }
            }
            ScDeleteTag((HKEY)Handle);
LABEL_267:
            *(_DWORD *)(v25 + 44) = v95;
            v48 |= 0x20u;
            goto LABEL_268;
          }
          if ( a7 != (unsigned int *)v20 )
          {
            v165 = v93;
            if ( !v93 )
            {
              ScGetUniqueTag(v50, &v165);
              v95 = v165;
              v158 = 4;
              v96 = 4;
              goto LABEL_257;
            }
          }
        }
LABEL_268:
        v97 = a10;
        if ( (Pid & 0xB) != 0 && a10 )
        {
          ConfigValue = ScAllocateAndReadConfigValue((HKEY)Handle, L"ObjectName", (unsigned __int16 **)&v167, 0);
          if ( (ConfigValue & 0xFFFFFFFD) != 0 )
            goto LABEL_298;
          ConfigValue = ScWriteStartName((HKEY)Handle, v97);
          if ( ConfigValue )
            goto LABEL_298;
          v48 |= 0x100u;
        }
        v98 = 0;
        if ( !v178 || !v97 && !a11 )
          goto LABEL_304;
        if ( (unsigned int)dword_1400BA2A0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400BA2A0, 0x400000000000LL, 0) )
        {
          v178 = -1;
          v173 = L"AccountInfo";
          v185 = *(const wchar_t **)(v25 + 56);
          v159 = (unsigned __int16 *)&v178;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            v99,
            (__int64)&dword_1400AE614,
            v100,
            v101,
            &v185,
            &v173);
        }
        if ( (unsigned int)IsEventEnabled(&ServiceConfigChangeAccountInfo) )
          EventWriteServiceConfigChange(&ServiceConfigChangeAccountInfo, *(const unsigned __int16 **)(v25 + 56), v97);
        v102 = (wchar_t *)v179;
        if ( !v179 )
        {
          ConfigValue = ScAllocateAndReadConfigValue((HKEY)Handle, L"ObjectName", (unsigned __int16 **)&v179, 0);
          if ( ConfigValue )
            goto LABEL_298;
          v102 = (wchar_t *)v179;
          if ( !v179 )
            goto LABEL_284;
        }
        ConfigValue = ScReadServiceManagedAccount((HKEY)Handle, (enum _TRI_BOOL *)&v182);
        if ( ConfigValue )
          goto LABEL_298;
        if ( v97 )
        {
          v102 = (wchar_t *)v168;
          if ( v168 )
          {
LABEL_292:
            if ( a11 )
            {
              if ( (unsigned int)ScIsVirtualServiceAccountName(v102) )
              {
LABEL_284:
                ConfigValue = 1057;
                goto LABEL_298;
              }
              v103 = ScDecryptPassword(v191, a11, a12, &hMem);
              ConfigValue = v103;
              if ( v103 )
              {
                if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                  && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
                {
                  WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 34, WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids, v103);
                }
                goto LABEL_298;
              }
            }
            v104 = ScChangeAccount(v25, Handle, v179, v102, v182, v174, hMem);
            ConfigValue = v104;
            if ( v104 )
            {
              if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
              {
                WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 35, WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids, v104);
              }
              goto LABEL_298;
            }
            v98 = (enum _TRI_BOOL *)&v175;
LABEL_304:
            if ( *(_DWORD *)(v25 + 84) == 1 )
            {
              ConfigValue = ScUpdateServiceRecordConfig((struct CServiceRecord *)v25, v192, v169, v194, v98, v50, 0);
              if ( ConfigValue )
                goto LABEL_298;
            }
            else
            {
              CServiceRecord::SetStatusFlag((CServiceRecord *)v25, 2u);
            }
            JITReadDisplayName = CServiceRecord::GetJITReadDisplayName((CServiceRecord *)v25, v105, v106);
            if ( !(unsigned int)ScIsIndirectString(JITReadDisplayName, 0)
              || (ConfigValue = ScAdjustServiceDisplayName((HKEY)Handle, (struct CServiceRecord *)v25)) == 0 )
            {
              CScmSyncLockExclusive::InternalUnlock((CScmSyncLockExclusive *)&v160);
              ConfigValue = ScProcessServiceDisabled((struct CServiceRecord *)v25, v169, (HKEY)Handle);
LABEL_311:
              CScmLock::LockAutoExclusive(v25 + 312, &v173);
              if ( ConfigValue )
              {
                v124 = v163;
                if ( (v48 & 1) != 0 )
                {
                  LODWORD(v191) = v163;
                  if ( ScRegSetValueExW((HKEY)Handle, L"Type", v109, 4u, &v191, 4u) )
                  {
                    if ( v180 )
                      v126 = (const unsigned __int16 *)v180;
                    else
                      v126 = CServiceRecord::GetJITReadDisplayName((CServiceRecord *)v25, v125, 0);
                    ScLogServiceEvent(0x25u, v126, 0x50u, 0, 0, 0);
                  }
                }
                if ( (v48 & 2) != 0 )
                {
                  v127 = ScWriteStartType(
                           *(struct _SERVICE_CONFIG_ROOT **)(v25 + 216),
                           (HKEY)Handle,
                           *(const unsigned __int16 **)(v25 + 56),
                           v177,
                           v124,
                           *(_DWORD *)(v25 + 168) & 1);
                  v129 = (unsigned __int16 *)v180;
                  if ( v127 )
                  {
                    if ( v180 )
                      v130 = (const unsigned __int16 *)v180;
                    else
                      v130 = CServiceRecord::GetJITReadDisplayName((CServiceRecord *)v25, v128, v109);
                    ScLogServiceEvent(0x25u, v130, 0x51u, 0, 0, 0);
                  }
                }
                else
                {
                  v129 = (unsigned __int16 *)v180;
                }
                if ( (v48 & 4) != 0 )
                {
                  LODWORD(v191) = v183;
                  if ( ScRegSetValueExW((HKEY)Handle, L"ErrorControl", v109, 4u, &v191, 4u) )
                  {
                    if ( v129 )
                      v132 = v129;
                    else
                      v132 = CServiceRecord::GetJITReadDisplayName((CServiceRecord *)v25, v131, v109);
                    ScLogServiceEvent(0x25u, v132, 0x52u, 0, 0, 0);
                  }
                }
                if ( (v48 & 0x800) != 0 )
                {
                  v133 = (const unsigned __int16 *)&dword_14009C804;
                  if ( v188 )
                    v133 = (const unsigned __int16 *)v188;
                  if ( ScWriteOptionalString((HKEY)Handle, L"DisplayName", v133) )
                  {
                    if ( v129 )
                      v135 = v129;
                    else
                      v135 = CServiceRecord::GetJITReadDisplayName((CServiceRecord *)v25, v134, v109);
                    ScLogServiceEvent(0x25u, v135, 0x53u, 0, 0, 0);
                  }
                }
                if ( (v48 & 0x400) != 0 )
                  CServiceRecord::UpdateDisplayName((CServiceRecord *)v25, v129, (unsigned __int16 **)&v180);
                if ( (v48 & 8) != 0 )
                {
                  if ( P )
                  {
                    if ( ScWriteImageFileName((HKEY)Handle, (unsigned __int16 *)P) )
                    {
                      v137 = CServiceRecord::GetJITReadDisplayName((CServiceRecord *)v25, v136, v109);
                      ScLogServiceEvent(0x25u, v137, 0x54u, 0, 0, 0);
                    }
                  }
                  else
                  {
                    ScRegDeleteValue((HKEY)Handle, L"ImagePath");
                  }
                }
                v32 = (unsigned __int8 *)v166;
                if ( (v48 & 0x80u) != 0 )
                {
                  v138 = &qword_1400A6950;
                  if ( v166 )
                    v138 = (__int64 *)v166;
                  v139 = ScWStrArraySize(v138);
                  if ( ScWriteDependencies((HKEY)Handle, v140, v139) )
                  {
                    v142 = CServiceRecord::GetJITReadDisplayName((CServiceRecord *)v25, v141, v109);
                    ScLogServiceEvent(0x25u, v142, 0x55u, 0, 0, 0);
                  }
                }
                if ( (v48 & 0x40) != 0
                  && ScUpdateServiceRecordConfig(
                       (struct CServiceRecord *)v25,
                       0xFFFFFFFF,
                       0xFFFFFFFF,
                       0xFFFFFFFF,
                       0,
                       0,
                       v32) )
                {
                  v144 = CServiceRecord::GetJITReadDisplayName((CServiceRecord *)v25, v143, v109);
                  ScLogServiceEvent(0x25u, v144, 0x55u, 0, 0, 0);
                }
                v145 = (unsigned __int16 *)v186;
                if ( (v48 & 0x10) != 0 )
                {
                  if ( v186 )
                  {
                    if ( ScWriteGroupForThisService((HKEY)Handle, (unsigned __int16 *)v186) )
                    {
                      v147 = CServiceRecord::GetJITReadDisplayName((CServiceRecord *)v25, v146, v109);
                      ScLogServiceEvent(0x25u, v147, 0x56u, 0, 0, 0);
                    }
                  }
                  else
                  {
                    ScRegDeleteValue((HKEY)Handle, L"Group");
                  }
                }
                if ( (v48 & 0x200) != 0 && ScUpdateRegistryGroupPointer((struct CServiceRecord *)v25, v145) )
                {
                  v149 = CServiceRecord::GetJITReadDisplayName((CServiceRecord *)v25, v148, v109);
                  ScLogServiceEvent(0x25u, v149, 0x56u, 0, 0, 0);
                }
                if ( (v48 & 0x20) != 0 )
                {
                  v150 = v184;
                  if ( v184 )
                  {
                    LODWORD(v191) = v184;
                    if ( ScRegSetValueExW((HKEY)Handle, L"Tag", v109, 4u, &v191, 4u) )
                    {
                      v153 = CServiceRecord::GetJITReadDisplayName((CServiceRecord *)v25, v151, v152);
                      ScLogServiceEvent(0x25u, v153, 0x57u, 0, 0, 0);
                    }
                  }
                  else
                  {
                    ScDeleteTag((HKEY)Handle);
                  }
                  *(_DWORD *)(v25 + 44) = v150;
                }
                if ( (v48 & 0x100) != 0 )
                {
                  v33 = v167;
                  if ( v167 )
                    v154 = ScWriteStartName((HKEY)Handle, (unsigned __int16 *)v167);
                  else
                    v154 = ScDeleteStartName((HKEY)Handle);
                  if ( v154 )
                  {
                    v157 = CServiceRecord::GetJITReadDisplayName((CServiceRecord *)v25, v155, v156);
                    ScLogServiceEvent(0x25u, v157, 0x58u, 0, 0, 0);
                  }
                  goto LABEL_339;
                }
              }
              else
              {
                v110 = v169;
                if ( v169 != -1 )
                {
                  v111 = v176;
                  if ( v169 != v176 )
                  {
                    v112 = *(const unsigned __int16 **)(v25 + 56);
                    v113 = CServiceRecord::GetJITReadDisplayName((CServiceRecord *)v25, v108, v109);
                    ScLogServiceEvent(0x28u, v113, v111, v110, v112, 0);
                  }
                }
                if ( (*(_DWORD *)(v25 + 52) & 8) != 0 && v169 == 2 && v176 != 2 )
                  CServiceRecord::SetStatusFlag((CServiceRecord *)v25, 0x10u);
                v114 = v192;
                if ( v192 != -1 && (v192 & 0x100) != 0 && (v163 & 0x100) == 0 )
                {
                  v115 = CServiceRecord::GetJITReadDisplayName((CServiceRecord *)v25, v108, v109);
                  ScLogEvent(0x1Eu, v115);
                  v114 = v192;
                }
                v116 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control )
                {
                  if ( (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
                  {
                    LODWORD(v159) = v194;
                    WPP_SF_qLLL(WPP_GLOBAL_Control->StubInfo, 36, v109, v191, v114, v193, v159);
                    v116 = WPP_GLOBAL_Control;
                  }
                  if ( v116 != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(v116->UserInfo) & 4) != 0 )
                  {
                    v117 = L"NULL";
                    v118 = L"NULL";
                    if ( a10 )
                      v118 = a10;
                    v119 = L"NULL";
                    if ( a5 )
                      v119 = a5;
                    if ( v50 )
                      LODWORD(v117) = (_DWORD)v50;
                    WPP_SF_SSS(
                      v116->StubInfo,
                      37,
                      (unsigned int)WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids,
                      (_DWORD)v117,
                      (__int64)v119,
                      (__int64)v118);
                  }
                }
                if ( a7 )
                  *a7 = v165;
                ScNotifyServicePropertyChange((struct CServiceRecord *)v25);
                v32 = (unsigned __int8 *)v166;
              }
              v33 = v167;
LABEL_339:
              CScmSyncLockExclusive::InternalUnlock((CScmSyncLockExclusive *)&v173);
              RtlReleaseResource(&ScServiceRecordLock);
              goto LABEL_340;
            }
LABEL_298:
            CScmSyncLockExclusive::InternalUnlock((CScmSyncLockExclusive *)&v160);
            goto LABEL_311;
          }
          ConfigValue = ScCanonAccountName(v97, &v172);
          if ( ConfigValue )
          {
            CScmSyncLockExclusive::InternalUnlock((CScmSyncLockExclusive *)&v160);
            v168 = v172;
            goto LABEL_311;
          }
          v102 = v172;
        }
        v168 = v102;
        goto LABEL_292;
      }
    }
LABEL_131:
    CScmSyncLockExclusive::InternalUnlock((CScmSyncLockExclusive *)&v160);
    goto LABEL_123;
  }
  if ( v29 == 1057 )
    goto LABEL_54;
  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 12, WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids, v29);
  ConfigValue = v30;
LABEL_39:
  v32 = (unsigned __int8 *)v166;
  v33 = v167;
LABEL_341:
  v120 = v168;
  ProcessHeap = NtCurrentPeb()->ProcessHeap;
  v122 = v179;
  if ( v168 != v179 )
  {
    RtlFreeHeap(ProcessHeap, 0, v179);
    v122 = v120;
    ProcessHeap = NtCurrentPeb()->ProcessHeap;
  }
  RtlFreeHeap(ProcessHeap, 0, v122);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v180);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v188);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v32);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v186);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v33);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v187);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v181);
  LocalFree(hMem);
  if ( Handle )
  {
    v123 = NtClose(Handle);
    RtlNtStatusToDosError(v123);
  }
  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->UserInfo) & 0x100) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 38, WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids, ConfigValue);
  }
  return ConfigValue;
}

```

## disassembly

```asm
0x140068b60  mov     rax, rsp
0x140068b63  mov     [rax+20h], r9d
0x140068b67  mov     [rax+18h], r8d
0x140068b6b  mov     [rax+10h], edx
0x140068b6e  mov     [rax+8], rcx
0x140068b72  push    rbp
0x140068b73  push    rbx
0x140068b74  push    rsi
0x140068b75  push    rdi
0x140068b76  push    r12
0x140068b78  push    r13
0x140068b7a  push    r14
0x140068b7c  push    r15
0x140068b7e  lea     rbp, [rax-78h]
0x140068b82  sub     rsp, 138h
0x140068b89  xor     r13d, r13d
0x140068b8c  mov     [rbp+70h+var_D0], 0FFFFFFFFh
0x140068b93  mov     eax, r13d
0x140068b96  mov     [rsp+170h+Handle], r13
0x140068b9b  mov     [rbp+70h+var_D8], rax
0x140068b9f  mov     r15d, r9d
0x140068ba2  mov     [rbp+70h+var_C0], rax
0x140068ba6  mov     r14d, r8d
0x140068ba9  mov     [rsp+170h+var_F8], eax
0x140068bad  mov     edi, edx
0x140068baf  mov     [rsp+170h+var_100], eax
0x140068bb3  mov     rsi, rcx
0x140068bb6  mov     [rbp+70h+var_68], rax
0x140068bba  mov     [rbp+70h+var_48], rax
0x140068bbe  mov     eax, 0FFh
0x140068bc3  mov     [rbp+70h+var_B0], eax
0x140068bc6  mov     [rbp+70h+var_80], eax
0x140068bc9  mov     [rbp+70h+var_AC], eax
0x140068bcc  mov     [rbp+70h+var_60], r13
0x140068bd0  mov     [rbp+70h+var_88], r13
0x140068bd4  mov     [rbp+70h+var_98], r13
0x140068bd8  mov     [rbp+70h+var_A4], r13d
0x140068bdc  mov     [rbp+70h+var_A8], r13d
0x140068be0  mov     [rbp+70h+var_7C], r13d
0x140068be4  mov     [rbp+70h+P], r13
0x140068be8  mov     [rbp+70h+var_E8], r13
0x140068bec  mov     [rbp+70h+var_58], r13
0x140068bf0  mov     [rbp+70h+var_E0], r13
0x140068bf4  mov     [rbp+70h+var_EC], r13d
0x140068bf8  mov     [rbp+70h+hMem], r13
0x140068bfc  mov     [rbp+70h+var_90], r13
0x140068c00  mov     [rbp+70h+var_F0], r13b
0x140068c04  call    ?ScSetTcpKeepalive@@YAXXZ; ScSetTcpKeepalive(void)
0x140068c09  cmp     cs:?ScShutdownInProgress@@3KA, r13d; ulong ScShutdownInProgress
0x140068c10  jz      short loc_140068C1C
0x140068c12  mov     eax, 45Bh
0x140068c17  jmp     loc_14006A37A
0x140068c1c  mov     rcx, rsi; void *
0x140068c1f  call    ?ScIsValidServiceHandle@@YAHPEAX@Z; ScIsValidServiceHandle(void *)
0x140068c24  test    eax, eax
0x140068c26  jnz     short loc_140068C32
0x140068c28  mov     eax, 6
0x140068c2d  jmp     loc_14006A37A
0x140068c32  xor     edx, edx; unsigned __int8
0x140068c34  call    ?ScCheckServiceProtectedProcess@@YAKPEAXE@Z; ScCheckServiceProtectedProcess(void *,uchar)
0x140068c39  mov     r12, [rbp+70h+String1]
0x140068c40  mov     rbx, [rbp+70h+arg_50]
0x140068c47  test    eax, eax
0x140068c49  jz      short loc_140068C9F
0x140068c4b  cmp     r14d, 2
0x140068c4f  jnz     short loc_140068CC6
0x140068c51  or      eax, 0FFFFFFFFh
0x140068c54  cmp     edi, eax
0x140068c56  jnz     short loc_140068CC6
0x140068c58  cmp     r15d, eax
0x140068c5b  jnz     short loc_140068CC6
0x140068c5d  cmp     [rbp+70h+arg_20], r13
0x140068c64  jnz     short loc_140068CC6
0x140068c66  mov     rdi, [rbp+70h+arg_28]
0x140068c6d  test    rdi, rdi
0x140068c70  jnz     short loc_140068CC6
0x140068c72  mov     r14, [rbp+70h+arg_30]
0x140068c79  test    r14, r14
0x140068c7c  jnz     short loc_140068CC6
0x140068c7e  mov     r15, [rbp+70h+arg_38]
0x140068c85  test    r15, r15
0x140068c88  jnz     short loc_140068CC6
0x140068c8a  cmp     [rbp+70h+arg_48], r13
0x140068c91  jnz     short loc_140068CC6
0x140068c93  test    rbx, rbx
0x140068c96  jnz     short loc_140068CC6
0x140068c98  test    r12, r12
0x140068c9b  jnz     short loc_140068CC6
0x140068c9d  jmp     short loc_140068CB4
0x140068c9f  mov     r15, [rbp+70h+arg_38]
0x140068ca6  mov     rdi, [rbp+70h+arg_28]
0x140068cad  mov     r14, [rbp+70h+arg_30]
0x140068cb4  mov     ecx, [rsi+8]; GrantedAccess
0x140068cb7  mov     edx, 2; DesiredAccess
0x140068cbc  call    cs:__imp_RtlAreAllAccessesGranted
0x140068cc2  test    al, al
0x140068cc4  jnz     short loc_140068CD0
0x140068cc6  mov     eax, 5
0x140068ccb  jmp     loc_14006A37A
0x140068cd0  test    r14, r14
0x140068cd3  jz      short loc_140068D1D
0x140068cd5  test    rdi, rdi
0x140068cd8  jz      short loc_140068CE0
0x140068cda  cmp     [rdi], r13w
0x140068cde  jnz     short loc_140068D1D
0x140068ce0  mov     rcx, cs:WPP_GLOBAL_Control
0x140068ce7  lea     r12, WPP_GLOBAL_Control
0x140068cee  cmp     rcx, r12
0x140068cf1  jz      short loc_140068D13
0x140068cf3  mov     r14d, 1
0x140068cf9  test    [rcx+1Ch], r14b
0x140068cfd  jz      short loc_140068D13
0x140068cff  mov     rcx, [rcx+10h]
0x140068d03  lea     edx, [r14+9]
0x140068d07  lea     r8, WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids
0x140068d0e  call    WPP_SF_
0x140068d13  mov     eax, 57h ; 'W'
0x140068d18  jmp     loc_14006A37A
0x140068d1d  mov     rsi, [rsi+10h]
0x140068d21  mov     [rbp+70h+Pid], r13d
0x140068d25  mov     rax, cs:WPP_GLOBAL_Control
0x140068d2c  lea     rdi, WPP_GLOBAL_Control
0x140068d33  cmp     rax, rdi
0x140068d36  jz      short loc_140068D7A
0x140068d38  test    dword ptr [rax+1Ch], 100h
0x140068d3f  jz      short loc_140068D7A
0x140068d41  lea     rdx, [rbp+70h+Pid]; Pid
0x140068d45  xor     ecx, ecx; Binding
0x140068d47  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x140068d4d  mov     r9, [rsi+38h]
0x140068d51  lea     r8, WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids
0x140068d58  test    eax, eax
0x140068d5a  mov     ecx, r13d
0x140068d5d  mov     edx, 0Bh
0x140068d62  cmovz   ecx, [rbp+70h+Pid]
0x140068d66  mov     dword ptr [rsp+170h+var_150], ecx
0x140068d6a  mov     rcx, cs:WPP_GLOBAL_Control
0x140068d71  mov     rcx, [rcx+10h]
0x140068d75  call    WPP_SF_Sd
0x140068d7a  mov     rax, [rbp+70h+arg_48]
0x140068d81  or      r13, 0FFFFFFFFFFFFFFFFh
0x140068d85  xor     ecx, ecx
0x140068d87  mov     r14d, 1
0x140068d8d  test    rax, rax
0x140068d90  jz      loc_14006901A
0x140068d96  mov     rdx, [rsi+38h]; unsigned __int16 *
0x140068d9a  mov     r8, rbx; unsigned __int8 *
0x140068d9d  mov     rcx, rax; unsigned __int16 *
0x140068da0  call    ?ScValidateAccount@@YAKPEAGPEBGPEAE@Z; ScValidateAccount(ushort *,ushort const *,uchar *)
0x140068da5  mov     ebx, eax
0x140068da7  test    eax, eax
0x140068da9  jz      short loc_140068DF5
0x140068dab  cmp     eax, 421h
0x140068db0  jz      loc_140068EEF
0x140068db6  mov     rcx, cs:WPP_GLOBAL_Control
0x140068dbd  cmp     rcx, rdi
0x140068dc0  jz      short loc_140068DDF
0x140068dc2  test    [rcx+1Ch], r14b
0x140068dc6  jz      short loc_140068DDF
0x140068dc8  mov     rcx, [rcx+10h]
0x140068dcc  lea     edx, [r14+0Bh]
0x140068dd0  mov     r9d, eax
0x140068dd3  lea     r8, WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids
0x140068dda  call    WPP_SF_d
0x140068ddf  mov     edi, ebx
0x140068de1  lea     r12, WPP_GLOBAL_Control
0x140068de8  mov     r13, [rbp+70h+var_E8]
0x140068dec  mov     r14, [rbp+70h+var_E0]
0x140068df0  jmp     loc_14006A226
0x140068df5  mov     rcx, [rbp+70h+arg_48]; unsigned __int16 *
0x140068dfc  lea     rdx, [rbp+70h+var_C0]; unsigned __int16 **
0x140068e00  call    ?ScCanonAccountName@@YAKPEAGPEAPEAG@Z; ScCanonAccountName(ushort *,ushort * *)
0x140068e05  mov     edi, eax
0x140068e07  test    eax, eax
0x140068e09  jz      short loc_140068E46
0x140068e0b  mov     rcx, cs:WPP_GLOBAL_Control
0x140068e12  lea     r12, WPP_GLOBAL_Control
0x140068e19  cmp     rcx, r12
0x140068e1c  jz      short loc_140068E3C
0x140068e1e  test    [rcx+1Ch], r14b
0x140068e22  jz      short loc_140068E3C
0x140068e24  mov     rcx, [rcx+10h]
0x140068e28  lea     r8, WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids
0x140068e2f  mov     edx, 0Dh
0x140068e34  mov     r9d, eax
0x140068e37  call    WPP_SF_d
0x140068e3c  mov     rax, [rbp+70h+var_C0]
0x140068e40  mov     [rbp+70h+var_D8], rax
0x140068e44  jmp     short loc_140068DE8
0x140068e46  mov     rdi, [rbp+70h+var_C0]
0x140068e4a  mov     rcx, rdi; unsigned __int16 *
0x140068e4d  mov     [rbp+70h+var_D8], rdi
0x140068e51  call    ?ScIsLocalSystemAccount@@YAHPEBG@Z; ScIsLocalSystemAccount(ushort const *)
0x140068e56  test    eax, eax
0x140068e58  jnz     loc_140068EE8
0x140068e5e  mov     rcx, rdi; unsigned __int16 *
0x140068e61  call    ?ScIsAccountInNtAuthDomain@@YAHPEBG@Z; ScIsAccountInNtAuthDomain(ushort const *)
0x140068e66  test    eax, eax
0x140068e68  jnz     short loc_140068EE8
0x140068e6a  mov     rcx, rdi; String1
0x140068e6d  call    ?ScIsVirtualServiceAccountName@@YAHPEBG@Z; ScIsVirtualServiceAccountName(ushort const *)
0x140068e72  test    eax, eax
0x140068e74  jnz     short loc_140068EE8
0x140068e76  mov     rax, cs:?g_pScExtFunctionPointers@@3PEAPEAXEA; void * * g_pScExtFunctionPointers
0x140068e7d  lea     r8, [rbp+70h+var_F0]
0x140068e81  mov     rdx, rdi
0x140068e84  xor     ecx, ecx
0x140068e86  mov     rax, [rax+58h]
0x140068e8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140068e8f  xor     ecx, ecx
0x140068e91  test    eax, eax
0x140068e93  jz      short loc_140068ED6
0x140068e95  mov     rcx, cs:WPP_GLOBAL_Control
0x140068e9c  lea     rdi, WPP_GLOBAL_Control
0x140068ea3  cmp     rcx, rdi
0x140068ea6  jz      short loc_140068EEF
0x140068ea8  test    [rcx+1Ch], r14b
0x140068eac  jz      short loc_140068EEF
0x140068eae  mov     r9, [rbp+70h+var_D8]
0x140068eb2  lea     r8, WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids
0x140068eb9  mov     rcx, [rcx+10h]
0x140068ebd  mov     edx, 0Eh
0x140068ec2  mov     dword ptr [rsp+170h+var_148], eax
0x140068ec6  mov     rax, [rsi+38h]
0x140068eca  mov     [rsp+170h+var_150], rax
0x140068ecf  call    WPP_SF_SSD
0x140068ed4  jmp     short loc_140068EEF
0x140068ed6  cmp     [rbp+70h+var_F0], cl
0x140068ed9  jz      loc_140068FE7
0x140068edf  mov     eax, r14d
0x140068ee2  mov     [rbp+70h+var_B0], eax
0x140068ee5  mov     [rbp+70h+var_AC], eax
0x140068ee8  lea     rdi, WPP_GLOBAL_Control
0x140068eef  lea     rcx, g_TriggerRegistrationLock
0x140068ef6  call    cs:__imp_RtlAcquireSRWLockExclusive
0x140068efc  call    cs:__imp_GetCurrentThreadId
0x140068f02  mov     dl, r14b; Wait
0x140068f05  lea     rcx, ?ScServiceRecordLock@@3VCServiceRecordLock@@A; Resource
0x140068f0c  call    cs:__imp_RtlAcquireResourceExclusive
0x140068f12  lea     rcx, [rsi+138h]
0x140068f19  lea     rdx, [rsp+170h+var_110]
0x140068f1e  call    ?LockAutoExclusive@CScmLock@@QEAA?AVCScmSyncLockExclusive@@XZ; CScmLock::LockAutoExclusive(void)
0x140068f23  mov     r8d, [rbp+70h+arg_8]
0x140068f2a  cmp     r8d, 0FFFFFFFFh
0x140068f2e  jz      loc_140069026
0x140068f34  mov     eax, r8d
0x140068f37  btr     eax, 8
0x140068f3b  cmp     eax, 10h
0x140068f3e  jz      loc_140069021
0x140068f44  cmp     eax, 20h ; ' '
0x140068f47  jz      loc_140069021
0x140068f4d  cmp     eax, 50h ; 'P'
0x140068f50  jz      loc_140069021
0x140068f56  cmp     eax, 60h ; '`'
0x140068f59  jz      loc_140069021
0x140068f5f  cmp     eax, 0D0h
0x140068f64  jz      loc_140069021
0x140068f6a  cmp     eax, 0E0h
0x140068f6f  jz      loc_140069021
0x140068f75  cmp     eax, 210h
0x140068f7a  jz      loc_140069021
0x140068f80  lea     eax, [r8-1]
0x140068f84  cmp     eax, r14d
0x140068f87  jbe     loc_140069021
0x140068f8d  mov     rcx, cs:WPP_GLOBAL_Control
0x140068f94  cmp     rcx, rdi
0x140068f97  jz      short loc_140068FB7
0x140068f99  test    [rcx+1Ch], r14b
0x140068f9d  jz      short loc_140068FB7
0x140068f9f  mov     rcx, [rcx+10h]
0x140068fa3  mov     r9d, r8d
0x140068fa6  lea     r8, WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids
0x140068fad  mov     edx, 0Fh
0x140068fb2  call    WPP_SF_d
0x140068fb7  mov     edi, 57h ; 'W'
0x140068fbc  lea     rcx, [rsp+170h+var_110]; this
0x140068fc1  call    ?InternalUnlock@CScmSyncLockExclusive@@IEAAXXZ; CScmSyncLockExclusive::InternalUnlock(void)
0x140068fc6  lea     rcx, ?ScServiceRecordLock@@3VCServiceRecordLock@@A; Resource
0x140068fcd  call    cs:__imp_RtlReleaseResource
0x140068fd3  lea     r12, WPP_GLOBAL_Control
0x140068fda  mov     r13, [rbp+70h+var_E8]
0x140068fde  mov     r14, [rbp+70h+var_E0]
0x140068fe2  jmp     loc_14006A219
0x140068fe7  test    rdi, rdi
0x140068fea  jz      short loc_14006900F
0x140068fec  cmp     [rdi], cx
0x140068fef  jz      short loc_14006900F
0x140068ff1  mov     rax, r13
0x140068ff4  inc     rax
0x140068ff7  cmp     [rdi+rax*2], cx
0x140068ffb  jnz     short loc_140068FF4
0x140068ffd  mov     eax, eax
0x140068fff  mov     edx, 24h ; '$'
0x140069004  cmp     [rdi+rax*2-2], dx
0x140069009  jz      loc_140068EE8
0x14006900f  mov     [rbp+70h+var_B0], ecx
0x140069012  mov     [rbp+70h+var_AC], ecx
0x140069015  jmp     loc_140068EE8
0x14006901a  mov     ebx, ecx
0x14006901c  jmp     loc_140068EEF
  ... truncated ...
```
