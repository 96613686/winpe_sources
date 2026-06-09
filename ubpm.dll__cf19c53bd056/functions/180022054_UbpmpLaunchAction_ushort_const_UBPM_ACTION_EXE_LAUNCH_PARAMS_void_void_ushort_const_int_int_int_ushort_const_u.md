# UbpmpLaunchAction(ushort const *,_UBPM_ACTION_EXE_LAUNCH_PARAMS *,void * *,void *,ushort const *,int,int,int,ushort const *,ulong,ushort const *,void * *,ulong *,void * *,void * *,void * *,HKEY__ * *,void * *,ulong *,void * * *,unsigned __int64 *,_UBPM_TASK_HOST_APPCONTAINER_CONTEXT * *)

- ea: `0x180022054`
- end: `0x180023343`
- name: `?UbpmpLaunchAction@@YAKPEBGPEAU_UBPM_ACTION_EXE_LAUNCH_PARAMS@@PEAPEAXPEAX0HHH0K02PEAK222PEAPEAUHKEY__@@24PEAPEAPEAXPEA_KPEAPEAU_UBPM_TASK_HOST_APPCONTAINER_CONTEXT@@@Z`
- size: `4847`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _UBPM_ACTION_EXE_LAUNCH_PARAMS *, void **, void *, wchar_t *Str, unsigned int, int, int, unsigned __int16 *, char, const unsigned __int16 *, void **, unsigned int *, void **, void **, void **, HKEY *, void **, unsigned int *, void ***, unsigned __int64 *, struct _UBPM_TASK_HOST_APPCONTAINER_CONTEXT **)`
- caller_count: `3`
- callee_count: `20`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180021060`
- `0x180023e04`
- `0x180023f68`

## callees

- `0x18000f9a0`
- `0x180016d80`
- `0x180019480`
- `0x180019d90`
- `0x18001e9f4`
- `0x180022054`
- `0x1800241f0`
- `0x180024aa0`
- `0x180025430`
- `0x18002576c`
- `0x180025b8c`
- `0x1800260fc`
- `0x18002f774`
- `0x180032e38`
- `0x180034ec4`
- `0x180034f3c`
- `0x18003bc7c`
- `0x18003c08c`
- `0x18003c5bc`
- `0x18003d810`

## import_xrefs

- `msvcrt!wcschr` at `0x180022898`
- `msvcrt!wcschr` at `0x180022898`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180022c0b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180022ceb`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180022dc5`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180022c0b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180022ceb`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180022dc5`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180022e99`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180022e99`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180022bcf`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180022bcf`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180022c5c`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180022d3d`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180022e1f`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180022c5c`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180022d3d`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180022e1f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800231bc`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180023258`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800231bc`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180023258`
- `ntdll!RtlPublishWnfStateData` at `0x1800229f6`
- `ntdll!RtlPublishWnfStateData` at `0x180023047`
- `ntdll!RtlPublishWnfStateData` at `0x1800229f6`
- `ntdll!RtlPublishWnfStateData` at `0x180023047`
- `ntdll!RtlNtStatusToDosError` at `0x1800229fe`
- `ntdll!RtlNtStatusToDosError` at `0x18002304f`
- `ntdll!RtlNtStatusToDosError` at `0x1800229fe`
- `ntdll!RtlNtStatusToDosError` at `0x18002304f`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x180022537`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x180022537`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1800225dd`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1800225dd`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x180023284`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x180023284`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180023168`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180023168`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180022b17`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180022b17`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180022f4d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180022f4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800224f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022541`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800225e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022858`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022a4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022a8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022b21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022c22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022c6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022d02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022d47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022de0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022e29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022ea3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022f59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800230c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800230d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023172`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800224f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022541`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800225e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022858`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022a4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022a8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022b21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022c22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022c6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022d02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022d47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022de0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022e29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022ea3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022f59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800230c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800230d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023172`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180022a41`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800230a5`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180022a41`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800230a5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180022a84`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800230b8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180022a84`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800230b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022a99`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022acd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800230cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002326e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023318`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022a99`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022acd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800230cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002326e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023318`
- `profapi!__imp_CreateEnvBlock` at `0x1800224ce`
- `profapi!__imp_CreateEnvBlock` at `0x1800224ce`
- `profapi!__imp_DestroyEnvBlock` at `0x1800232ed`
- `profapi!__imp_DestroyEnvBlock` at `0x1800232ed`
- `profapi!__imp_LoadProfileBasic` at `0x1800223d6`
- `profapi!__imp_LoadProfileBasic` at `0x1800223d6`
- `profapi!__imp_UnloadProfileBasic` at `0x180023309`
- `profapi!__imp_UnloadProfileBasic` at `0x180023309`

## pseudocode

```c
__int64 __fastcall UbpmpLaunchAction(
        const unsigned __int16 *a1,
        struct _UBPM_ACTION_EXE_LAUNCH_PARAMS *a2,
        void **a3,
        void *a4,
        wchar_t *Str,
        unsigned int a6,
        int a7,
        int a8,
        unsigned __int16 *a9,
        char a10,
        const unsigned __int16 *a11,
        void **a12,
        unsigned int *a13,
        void **a14,
        void **a15,
        void **a16,
        HKEY *a17,
        void **a18,
        unsigned int *a19,
        void ***a20,
        unsigned __int64 *a21,
        struct _UBPM_TASK_HOST_APPCONTAINER_CONTEXT **a22)
{
  const WCHAR *lpCurrentDirectory; // r14
  const unsigned __int16 *v24; // rsi
  PVOID *v26; // rdx
  unsigned int v27; // ebx
  __int64 v28; // rcx
  int v29; // eax
  unsigned int *v30; // r9
  void *v31; // r13
  int v32; // r15d
  PSID v33; // r10
  unsigned __int16 *v34; // rax
  char v35; // di
  unsigned int v36; // eax
  bool v37; // cl
  unsigned int *v38; // rcx
  void **v39; // r14
  void **v40; // rax
  __int64 v41; // rax
  unsigned __int64 v42; // rax
  HANDLE *v43; // r14
  unsigned int *v44; // rax
  int v45; // eax
  int v46; // edx
  char IsEnabled; // al
  char v48; // r15
  __int64 v49; // r8
  HANDLE v50; // rdx
  char LastError; // al
  PSID v52; // r14
  _QWORD *v53; // rcx
  int v54; // edx
  __int64 v55; // r14
  __int64 v56; // r8
  unsigned __int16 *v57; // r15
  __int64 v58; // r8
  _QWORD *v59; // rcx
  int v60; // edx
  const unsigned __int16 *v61; // r15
  __int64 v62; // r8
  unsigned __int16 *v63; // r15
  __int64 v64; // rax
  unsigned int v65; // ecx
  unsigned int v66; // eax
  char v67; // al
  _QWORD *v68; // rcx
  int v69; // edx
  unsigned __int64 v70; // r14
  HANDLE *v71; // rax
  _QWORD *v72; // rcx
  __int64 v73; // rdx
  __int64 v74; // r9
  NTSTATUS v75; // eax
  HANDLE v76; // rax
  void *v77; // r14
  PSID v78; // r15
  DWORD LengthSid; // ebx
  void *v80; // rax
  PSID *v81; // r15
  DWORD v82; // ebx
  void *v83; // rax
  DWORD v84; // ebx
  HANDLE v85; // rcx
  const wchar_t **v86; // rax
  const wchar_t *v87; // r8
  BOOL v88; // eax
  __int64 v89; // rdx
  unsigned __int16 *v90; // r15
  unsigned int AppContainerImpersonated; // eax
  NTSTATUS v92; // eax
  HANDLE v93; // rax
  void *v94; // r14
  _QWORD *v95; // rcx
  int v96; // edx
  HANDLE v97; // rcx
  HKEY *v98; // rcx
  PSID v99; // rcx
  void **v100; // rax
  __int64 v101; // rax
  char v103; // [rsp+60h] [rbp-A0h]
  bool v104; // [rsp+61h] [rbp-9Fh]
  int v105; // [rsp+64h] [rbp-9Ch]
  HANDLE *v106; // [rsp+68h] [rbp-98h]
  const WCHAR *v107; // [rsp+70h] [rbp-90h]
  LPVOID lpEnvironment; // [rsp+78h] [rbp-88h] BYREF
  int v109; // [rsp+80h] [rbp-80h]
  unsigned __int16 *v110; // [rsp+88h] [rbp-78h]
  HANDLE hObject; // [rsp+90h] [rbp-70h] BYREF
  void *v112; // [rsp+98h] [rbp-68h] BYREF
  __int64 v113; // [rsp+A0h] [rbp-60h] BYREF
  void *phNewToken; // [rsp+A8h] [rbp-58h] BYREF
  PSID pSourceSid; // [rsp+B0h] [rbp-50h]
  LPWSTR lpCommandLine; // [rsp+B8h] [rbp-48h]
  HKEY v117; // [rsp+C0h] [rbp-40h] BYREF
  void **v118; // [rsp+C8h] [rbp-38h]
  HKEY *v119; // [rsp+D0h] [rbp-30h]
  void *v120; // [rsp+D8h] [rbp-28h] BYREF
  void **v121; // [rsp+E0h] [rbp-20h] BYREF
  int v122; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v123; // [rsp+F0h] [rbp-10h]
  PSID pSid1; // [rsp+F8h] [rbp-8h]
  void **v125; // [rsp+100h] [rbp+0h]
  unsigned int *v126; // [rsp+108h] [rbp+8h]
  void **v127; // [rsp+110h] [rbp+10h]
  void **v128; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v129; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 *v130; // [rsp+128h] [rbp+28h] BYREF
  const WCHAR *v131; // [rsp+130h] [rbp+30h] BYREF
  void *v132; // [rsp+138h] [rbp+38h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+140h] [rbp+40h] BYREF
  unsigned __int16 *v134; // [rsp+158h] [rbp+58h]
  ULONG_PTR Size; // [rsp+160h] [rbp+60h] BYREF
  PSID pSid; // [rsp+168h] [rbp+68h]
  void **v137; // [rsp+170h] [rbp+70h]
  void ***v138; // [rsp+178h] [rbp+78h]
  struct _UBPM_TASK_HOST_APPCONTAINER_CONTEXT **v139; // [rsp+180h] [rbp+80h]
  __int128 Value; // [rsp+188h] [rbp+88h] BYREF
  __int64 v141; // [rsp+198h] [rbp+98h]
  _BYTE StartupInfo[112]; // [rsp+1A0h] [rbp+A0h] BYREF
  _OWORD v143[3]; // [rsp+210h] [rbp+110h] BYREF

  lpCurrentDirectory = a11;
  v24 = Str;
  v26 = (PVOID *)a21;
  v110 = a9;
  v27 = 0;
  v28 = *((_QWORD *)a2 + 4);
  v125 = a12;
  v126 = a13;
  v137 = a14;
  v127 = a15;
  v118 = a16;
  v119 = a17;
  v128 = a18;
  v138 = a20;
  v139 = a22;
  v29 = 0;
  pSid = a4;
  v30 = a19;
  v106 = a3;
  v107 = a11;
  lpEnvironment = 0;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  if ( v28 )
  {
    LOBYTE(v29) = *(_DWORD *)(v28 + 32) == 2;
    v105 = v29;
  }
  else
  {
    v105 = 0;
  }
  v112 = 0;
  v31 = 0;
  pSourceSid = 0;
  v117 = 0;
  v132 = 0;
  v120 = 0;
  hObject = 0;
  phNewToken = 0;
  lpCommandLine = 0;
  if ( v28 )
  {
    v32 = *(_DWORD *)(v28 + 36);
    LOBYTE(a3) = *(_BYTE *)(v28 + 49);
    v33 = *(PSID *)(*(_QWORD *)(v28 + 8) + 8LL);
  }
  else
  {
    v33 = ::pSid;
    LOBYTE(a3) = 0;
    v32 = 0;
  }
  v121 = 0;
  v129 = 0;
  v130 = 0;
  v131 = 0;
  if ( v28 )
  {
    v123 = *(_QWORD *)(v28 + 104);
    v109 = *(_DWORD *)(v28 + 96);
    v34 = *(unsigned __int16 **)(v28 + 88);
    pSid1 = *(PSID *)(v28 + 80);
    v134 = v34;
  }
  else
  {
    v123 = 0;
    v109 = 0;
    v134 = 0;
    pSid1 = 0;
  }
  v35 = 1;
  v36 = *(_DWORD *)a2 - 1;
  Size = 48;
  *(_QWORD *)StartupInfo = 112;
  v37 = v36 <= 1;
  v104 = v36 <= 1;
  v122 = 0;
  v113 = 0;
  v103 = 0;
  v141 = 0;
  memset(&StartupInfo[8], 0, 52);
  *(_DWORD *)&StartupInfo[60] = (a8 != 0) + 128;
  memset(&StartupInfo[64], 0, 48);
  memset(v143, 0, sizeof(v143));
  Value = 0;
  if ( v36 > 1 )
  {
    v63 = 0;
    goto LABEL_127;
  }
  if ( v125 )
  {
    v38 = v126;
    if ( v126 )
    {
      v39 = v127;
      if ( v127 )
      {
        if ( v118 && v119 && v128 && a21 )
        {
          *v125 = 0;
          v40 = v118;
          *v38 = 0;
          *v39 = 0;
          *v40 = 0;
          *v119 = 0;
          *v128 = 0;
          v41 = *((_QWORD *)a2 + 4);
          if ( v41 )
            v42 = *(_QWORD *)(v41 + 40);
          else
            v42 = 0;
          v43 = v106;
          *a21 = v42;
          if ( v106 )
          {
            v44 = (unsigned int *)&v122;
            if ( a19 )
              v44 = a19;
            v27 = UbpmpTokenCheckHarden(a2, a1, v33, a6, a21, (_BYTE)a3, v106, v44, &v121, &v112);
            if ( v27 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                WPP_SF_Sd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  95,
                  (unsigned int)WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
                  (_DWORD)Str,
                  v27);
LABEL_28:
              v31 = v112;
LABEL_248:
              v48 = v103;
              goto LABEL_249;
            }
            if ( !v105 )
            {
              v45 = LoadProfileBasic(*v106, &v117);
              if ( v45 < 0 )
              {
                v26 = &WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  WPP_SF_SL(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    96,
                    (unsigned int)WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
                    (_DWORD)Str,
                    v45);
              }
            }
            if ( v32 || (a10 & 0x10) != 0 )
            {
              if ( (v32 & 1) != 0 || (v46 = 0, (a10 & 0x10) != 0) )
                v46 = 1;
              v43 = v106;
              v27 = UbpmDeriveToken(*v106, v46, &hObject);
              if ( v27 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  WPP_SF_SdL(*((_QWORD *)WPP_GLOBAL_Control + 2), (_DWORD)v26, (_DWORD)a3, (_DWORD)Str, v27, v32);
                goto LABEL_28;
              }
            }
            else
            {
              v43 = v106;
            }
            v31 = v112;
          }
          IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(
                        `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl,
                        v26,
                        a3,
                        v30);
          v48 = 0;
          v49 = 0;
          if ( IsEnabled )
          {
            v50 = hObject;
            LOBYTE(v49) = v43 == 0;
            if ( hObject )
            {
LABEL_52:
              if ( (int)CreateEnvBlock(&lpEnvironment, v50, v49) < 0
                && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                LastError = GetLastError();
                WPP_SF_Sd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  98,
                  (unsigned int)WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
                  (_DWORD)Str,
                  LastError);
              }
              v52 = pSid1;
              if ( pSid1 )
              {
                if ( !InitializeProcThreadAttributeList((LPPROC_THREAD_ATTRIBUTE_LIST)v143, 1u, 0, &Size) )
                {
                  v27 = GetLastError();
                  v53 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                    goto LABEL_249;
                  v54 = 99;
                  goto LABEL_61;
                }
                *(_QWORD *)&StartupInfo[104] = v143;
                LODWORD(v141) = v109;
                *((_QWORD *)&Value + 1) = v123;
                *(_QWORD *)&Value = v52;
                if ( !UpdateProcThreadAttribute((LPPROC_THREAD_ATTRIBUTE_LIST)v143, 0, 0x20009u, &Value, 0x18u, 0, 0) )
                {
                  v27 = GetLastError();
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    WPP_SF_Sd(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      101,
                      (unsigned int)WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
                      (_DWORD)Str,
                      v27);
                  v48 = 1;
                  goto LABEL_249;
                }
                v48 = 1;
                v103 = 1;
              }
              v55 = -1;
              if ( Str )
              {
                v56 = -1;
                do
                  ++v56;
                while ( Str[v56] );
                v27 = UbpmpExpandEnvironmentStrings(lpEnvironment, Str, v56, &v129);
                if ( v27 )
                {
                  v53 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                    goto LABEL_249;
                  v54 = 102;
LABEL_61:
                  WPP_SF_Sd(
                    v53[2],
                    v54,
                    (unsigned int)WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
                    (_DWORD)Str,
                    v27);
                  goto LABEL_249;
                }
                v24 = v129;
              }
              v57 = v110;
              if ( v110 || (v57 = (unsigned __int16 *)*((_QWORD *)a2 + 2), (v110 = v57) != 0) )
              {
                v58 = -1;
                do
                  ++v58;
                while ( v57[v58] );
                v27 = UbpmpExpandEnvironmentStrings(lpEnvironment, v57, v58, &v130);
                if ( v27 )
                {
                  v59 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                    goto LABEL_248;
                  v60 = 103;
                  goto LABEL_84;
                }
                v110 = v130;
              }
              v61 = a11;
              if ( a11 || (v61 = (const unsigned __int16 *)*((_QWORD *)a2 + 3), (v107 = v61) != 0) )
              {
                v62 = -1;
                do
                  ++v62;
                while ( v61[v62] );
                v27 = UbpmpExpandEnvironmentStrings(lpEnvironment, v61, v62, &v131);
                if ( v27 )
                {
                  v59 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                    goto LABEL_248;
                  v60 = 104;
                  goto LABEL_84;
                }
                v107 = v131;
              }
              v63 = v110;
              if ( UbpmUtilsStrStartWithAnother(v110, v24) )
              {
                lpCommandLine = v63;
              }
              else
              {
                v64 = -1;
                do
                  ++v64;
                while ( v24[v64] );
                v65 = 2 * v64 + 2;
                if ( v63 )
                {
                  do
                    ++v55;
                  while ( v63[v55] );
                  v66 = v65 + 2 * (v55 + 1);
                  if ( v66 < v65 )
                  {
                    v67 = 22;
                    v27 = 534;
                    v68 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                      goto LABEL_248;
                    v69 = 105;
                    goto LABEL_105;
                  }
                }
                else
                {
                  v66 = 2 * v64 + 2;
                }
                v70 = v66 + 6;
                if ( (unsigned int)v70 < v66 )
                {
                  v67 = 22;
                  v27 = 534;
                  v68 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                    goto LABEL_248;
                  v69 = 106;
                  goto LABEL_105;
                }
                lpCommandLine = (LPWSTR)UbpmAlloc((unsigned int)v70);
                v63 = lpCommandLine;
                if ( !lpCommandLine )
                {
                  v27 = GetLastError();
                  v59 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                    goto LABEL_248;
                  v60 = 107;
                  goto LABEL_84;
                }
                if ( *v24 == 34 || !wcschr(v24, 0x20u) )
                {
                  StringCbCopyW(v63, v70, v24);
                }
                else
                {
                  StringCbCopyW(v63, v70, L"\"");
                  StringCbCatW(v63, v70, v24);
                  StringCbCatW(v63, v70, L"\"");
                }
                if ( v110 )
                {
                  StringCbCatW(v63, v70, L" ");
                  StringCbCatW(v63, v70, v110);
                }
              }
              lpCurrentDirectory = v107;
              v37 = v104;
LABEL_127:
              v71 = v106;
              if ( !v106 )
              {
                switch ( *(_DWORD *)a2 )
                {
                  case 1:
                  case 2:
                    if ( CreateProcessW(
                           0,
                           v63,
                           0,
                           0,
                           0,
                           0x84404u,
                           lpEnvironment,
                           lpCurrentDirectory,
                           (LPSTARTUPINFOW)StartupInfo,
                           &ProcessInformation) )
                    {
                      *v125 = ProcessInformation.hProcess;
                      *v126 = ProcessInformation.dwProcessId;
                      *v127 = ProcessInformation.hThread;
                      *v118 = ::pSid;
                      *v119 = 0;
                      goto LABEL_248;
                    }
                    v27 = GetLastError();
                    v59 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                      goto LABEL_248;
                    v60 = 108;
                    break;
                  case 3:
                    v76 = OpenEventW(2u, 0, v24);
                    v77 = v76;
                    if ( v76 )
                    {
                      if ( SetEvent(v76) )
                      {
                        CloseHandle(v77);
                        goto LABEL_248;
                      }
                      v27 = GetLastError();
                      CloseHandle(v77);
                      v59 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                        goto LABEL_248;
                      v60 = 110;
                    }
                    else
                    {
                      v27 = GetLastError();
                      v59 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                        goto LABEL_248;
                      v60 = 109;
                    }
                    break;
                  case 4:
                    v75 = RtlPublishWnfStateData(
                            **((_QWORD **)a2 + 1),
                            0,
                            *(_QWORD *)(*((_QWORD *)a2 + 1) + 16LL),
                            *(unsigned int *)(*((_QWORD *)a2 + 1) + 8LL),
                            0);
                    v27 = RtlNtStatusToDosError(v75);
                    if ( !v27 )
                      goto LABEL_248;
                    v72 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                      goto LABEL_248;
                    v73 = 111;
LABEL_140:
                    v74 = v27;
LABEL_135:
                    WPP_SF_d(v72[2], v73, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, v74);
                    goto LABEL_248;
                  default:
                    v27 = 87;
                    v72 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                      goto LABEL_248;
                    v73 = 112;
                    v74 = 87;
                    goto LABEL_135;
                }
LABEL_84:
                WPP_SF_Sd(v59[2], v60, (unsigned int)WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, (_DWORD)v24, v27);
                goto LABEL_248;
              }
              if ( v37 )
              {
                v71 = v106;
                *(_QWORD *)&StartupInfo[16] = (unsigned __int64)L"winsta0\\default" & -(__int64)(v105 != 0);
              }
              if ( !v31 )
              {
                v78 = pSid;
                if ( pSid )
                {
                  if ( !IsValidSid(pSid) )
                  {
                    v67 = 87;
                    v27 = 87;
                    v68 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                      goto LABEL_248;
                    v69 = 113;
LABEL_105:
                    WPP_SF_Sd(
                      v68[2],
                      v69,
                      (unsigned int)WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
                      (_DWORD)v24,
                      v67);
                    goto LABEL_248;
                  }
                  LengthSid = GetLengthSid(v78);
                  v80 = UbpmAlloc(LengthSid);
                  v31 = v80;
                  if ( !v80 )
                  {
                    v27 = GetLastError();
                    v59 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                      goto LABEL_248;
                    v60 = 114;
                    goto LABEL_84;
                  }
                  if ( !CopySid(LengthSid, v80, v78) )
                  {
                    v27 = GetLastError();
                    v59 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                      goto LABEL_248;
                    v60 = 115;
                    goto LABEL_84;
                  }
                }
                else
                {
                  UbpmUtilsQueryToken(*v71, TokenLogonSid, &v132);
                  v81 = (PSID *)v132;
                  if ( !*(_DWORD *)v132 )
                  {
                    v27 = 1168;
                    v59 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                      goto LABEL_248;
                    v60 = 116;
                    goto LABEL_84;
                  }
                  v82 = GetLengthSid(*((PSID *)v132 + 1));
                  v83 = UbpmAlloc(v82);
                  v31 = v83;
                  if ( !v83 )
                  {
                    v27 = GetLastError();
                    v59 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                      goto LABEL_248;
                    v60 = 117;
                    goto LABEL_84;
                  }
                  if ( !CopySid(v82, v83, v81[1]) )
                  {
                    v27 = GetLastError();
                    v59 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                      goto LABEL_248;
                    v60 = 118;
                    goto LABEL_84;
                  }
                }
              }
              v27 = UbpmUtilsQueryToken(*v106, TokenUser, &v120);
              if ( v27 )
              {
                v59 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                  goto LABEL_248;
                v60 = 119;
                goto LABEL_84;
              }
              v84 = GetLengthSid(*(PSID *)v120);
              pSourceSid = UbpmAlloc(v84);
              if ( !pSourceSid )
              {
                v27 = GetLastError();
                v59 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                  goto LABEL_248;
                v60 = 120;
                goto LABEL_84;
              }
              if ( !CopySid(v84, pSourceSid, *(PSID *)v120) )
              {
                v27 = GetLastError();
                v59 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                  goto LABEL_248;
                v60 = 121;
                goto LABEL_84;
              }
              v85 = hObject;
              if ( !hObject )
                v85 = *v106;
              if ( !DuplicateTokenEx(v85, 0x2000000u, 0, SecurityImpersonation, TokenImpersonation, &phNewToken) )
              {
                v27 = GetLastError();
                v72 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                  goto LABEL_248;
                v73 = 122;
                goto LABEL_140;
              }
              v27 = UbpmFileAccessCheck(phNewToken);
              if ( v27 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  v86 = (const wchar_t **)*((_QWORD *)a2 + 5);
                  if ( v86 )
                    v87 = *v86;
                  else
                    v87 = L"NULL";
                  WPP_SF_SSd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    123,
                    (unsigned int)WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
                    (_DWORD)v24,
                    (__int64)v87,
                    v27);
                }
                goto LABEL_248;
              }
              v88 = SetThreadToken(0, phNewToken);
              v89 = 0;
              if ( !v88 )
              {
                v27 = GetLastError();
                v72 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                  goto LABEL_248;
                v73 = 124;
                goto LABEL_140;
              }
              v90 = v134;
              if ( v134 )
              {
                AppContainerImpersonated = UbpmpCreateAppContainerImpersonated(
                                             v134,
                                             pSourceSid,
                                             pSid1,
                                             v123,
                                             (__int64)&v113);
                v89 = 0;
                v27 = AppContainerImpersonated;
                if ( AppContainerImpersonated )
                {
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    WPP_SF_SSd(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      125,
                      (unsigned int)WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
                      (_DWORD)v24,
                      (__int64)v90,
                      AppContainerImpersonated);
                  goto LABEL_244;
                }
              }
              switch ( *(_DWORD *)a2 )
              {
                case 1:
                case 2:
                  v97 = hObject;
                  if ( !hObject )
                    v97 = *v106;
                  if ( CreateProcessAsUserW(
                         v97,
                         0,
                         lpCommandLine,
                         0,
                         0,
                         0,
                         (v105 != 0 ? 32 : 0x4000) | 0x80404,
                         lpEnvironment,
                         v107,
                         (LPSTARTUPINFOW)StartupInfo,
                         &ProcessInformation) )
                  {
                    goto LABEL_242;
                  }
                  v27 = GetLastError();
                  v95 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                    goto LABEL_244;
                  v96 = 126;
                  break;
                case 3:
                  v93 = OpenEventW(2u, 0, v24);
                  v27 = 0;
                  v94 = v93;
                  if ( v93 )
                  {
                    if ( !SetEvent(v93) )
                      v27 = GetLastError();
                    CloseHandle(v94);
                  }
                  else
                  {
                    v27 = GetLastError();
                  }
                  if ( !v27 )
                    goto LABEL_242;
                  v95 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                    goto LABEL_244;
                  v96 = 127;
                  break;
                case 4:
                  v92 = RtlPublishWnfStateData(
                          **((_QWORD **)a2 + 1),
                          0,
                          *(_QWORD *)(*((_QWORD *)a2 + 1) + 16LL),
                          *(unsigned int *)(*((_QWORD *)a2 + 1) + 8LL),
                          0);
                  v27 = RtlNtStatusToDosError(v92);
                  if ( v27 )
                  {
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        128,
                        WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
                        v27);
                    goto LABEL_244;
                  }
LABEL_242:
                  RevertToSelf();
                  v35 = 0;
                  if ( v104 )
                  {
                    *v125 = ProcessInformation.hProcess;
                    *v126 = ProcessInformation.dwProcessId;
                    *v127 = ProcessInformation.hThread;
                    *v137 = hObject;
                    v98 = v119;
                    *v118 = v31;
                    v31 = 0;
                    *v98 = v117;
                    v99 = pSourceSid;
                    hObject = 0;
                    v117 = 0;
                    pSourceSid = 0;
                    *v128 = v99;
                    v100 = v121;
                    v121 = 0;
                    *v138 = v100;
                    v101 = v113;
                    v113 = 0;
                    *v139 = (struct _UBPM_TASK_HOST_APPCONTAINER_CONTEXT *)v101;
                  }
                  goto LABEL_244;
                default:
                  v27 = 87;
LABEL_244:
                  if ( v113 )
                    UbpmpDeleteAppContainerImpersonated(&v113, v89);
                  if ( v35 )
                    RevertToSelf();
                  goto LABEL_248;
              }
              WPP_SF_Sd(v95[2], v96, (unsigned int)WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, (_DWORD)v24, v27);
              goto LABEL_244;
            }
          }
          else
          {
            LOBYTE(v49) = v43 == 0;
          }
          if ( v43 )
            v50 = *v43;
          else
            v50 = g_Globals;
          goto LABEL_52;
        }
      }
    }
  }
  v27 = 87;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    goto LABEL_253;
  WPP_SF_Sd(
    *((_QWORD *)WPP_GLOBAL_Control + 2),
    94,
    (unsigned int)WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
    (_DWORD)Str,
    87);
  v48 = 0;
LABEL_249:
  if ( phNewToken )
  {
    CloseHandle(phNewToken);
    phNewToken = 0;
  }
  if ( v48 )
    DeleteProcThreadAttributeList((LPPROC_THREAD_ATTRIBUTE_LIST)v143);
LABEL_253:
  UBPM_MIDL_user_free(v129);
  UBPM_MIDL_user_free(v130);
  UBPM_MIDL_user_free(v131);
  UBPM_MIDL_user_free(v31);
  UBPM_MIDL_user_free(pSourceSid);
  UBPM_MIDL_user_free(v132);
  UBPM_MIDL_user_free(v120);
  UBPM_MIDL_user_free(v121);
  if ( lpCommandLine != v110 )
    UBPM_MIDL_user_free(lpCommandLine);
  if ( lpEnvironment )
    DestroyEnvBlock();
  if ( v117 && *v106 )
    UnloadProfileBasic();
  if ( hObject )
    CloseHandle(hObject);
  return v27;
}

```

## disassembly

```asm
0x180022054  push    rbp
0x180022056  push    rbx
0x180022057  push    rsi
0x180022058  push    rdi
0x180022059  push    r12
0x18002205b  push    r13
0x18002205d  push    r14
0x18002205f  push    r15
0x180022061  lea     rbp, [rsp-158h]
0x180022069  sub     rsp, 258h
0x180022070  mov     rax, cs:__security_cookie
0x180022077  xor     rax, rsp
0x18002207a  mov     [rbp+190h+var_50], rax
0x180022081  mov     rax, [rbp+190h+arg_40]
0x180022088  xor     edi, edi
0x18002208a  mov     r14, [rbp+190h+arg_50]
0x180022091  mov     r12, rdx
0x180022094  mov     rsi, [rbp+190h+Str]
0x18002209b  mov     r11, rcx
0x18002209e  mov     rdx, [rbp+190h+arg_A0]
0x1800220a5  xorps   xmm0, xmm0
0x1800220a8  mov     [rbp+190h+var_208], rax
0x1800220ac  mov     ebx, edi
0x1800220ae  mov     rax, [rbp+190h+arg_58]
0x1800220b5  mov     rcx, [r12+20h]
0x1800220ba  mov     [rbp+190h+var_190], rax
0x1800220be  mov     rax, [rbp+190h+arg_60]
0x1800220c5  mov     [rbp+190h+var_188], rax
0x1800220c9  mov     rax, [rbp+190h+arg_68]
0x1800220d0  mov     [rbp+190h+var_120], rax
0x1800220d4  mov     rax, [rbp+190h+arg_70]
0x1800220db  mov     [rbp+190h+var_180], rax
0x1800220df  mov     rax, [rbp+190h+arg_78]
0x1800220e6  mov     [rbp+190h+var_1C8], rax
0x1800220ea  mov     rax, [rbp+190h+arg_80]
0x1800220f1  mov     [rbp+190h+var_1C0], rax
0x1800220f5  mov     rax, [rbp+190h+arg_88]
0x1800220fc  mov     [rbp+190h+var_178], rax
0x180022100  mov     rax, [rbp+190h+arg_98]
0x180022107  mov     [rbp+190h+var_118], rax
0x18002210b  mov     rax, [rbp+190h+arg_A8]
0x180022112  mov     [rbp+190h+var_110], rax
0x180022119  xor     eax, eax
0x18002211b  mov     [rbp+190h+pSid], r9
0x18002211f  mov     r9, [rbp+190h+arg_90]
0x180022126  mov     [rsp+290h+var_228], r8
0x18002212b  mov     [rsp+290h+var_220], r14
0x180022130  mov     qword ptr [rbp+190h+ProcessInformation.dwProcessId], rax
0x180022134  mov     [rsp+290h+lpEnvironment], rdi
0x180022139  movups  xmmword ptr [rbp+190h+ProcessInformation.hProcess], xmm0
0x18002213d  test    rcx, rcx
0x180022140  jz      short loc_18002214F
0x180022142  cmp     dword ptr [rcx+20h], 2
0x180022146  setz    al
0x180022149  mov     [rsp+290h+var_22C], eax
0x18002214d  jmp     short loc_180022153
0x18002214f  mov     [rsp+290h+var_22C], edi
0x180022153  mov     [rbp+190h+var_1F8], rdi
0x180022157  mov     r13, rdi
0x18002215a  mov     [rbp+190h+pSourceSid], rdi
0x18002215e  mov     [rbp+190h+var_1D0], rdi
0x180022162  mov     [rbp+190h+var_158], rdi
0x180022166  mov     [rbp+190h+var_1B8], rdi
0x18002216a  mov     [rbp+190h+hObject], rdi
0x18002216e  mov     [rbp+190h+phNewToken], rdi
0x180022172  mov     [rbp+190h+lpCommandLine], rdi
0x180022176  test    rcx, rcx
0x180022179  jz      short loc_18002218D
0x18002217b  mov     rax, [rcx+8]
0x18002217f  mov     r15d, [rcx+24h]
0x180022183  mov     r8b, [rcx+31h]
0x180022187  mov     r10, [rax+8]
0x18002218b  jmp     short loc_18002219A
0x18002218d  mov     r10, cs:pSid
0x180022194  mov     r8b, dil
0x180022197  mov     r15d, edi
0x18002219a  mov     [rbp+190h+var_1B0], rdi
0x18002219e  mov     [rbp+190h+var_170], rdi
0x1800221a2  mov     [rbp+190h+var_168], rdi
0x1800221a6  mov     [rbp+190h+var_160], rdi
0x1800221aa  test    rcx, rcx
0x1800221ad  jz      short loc_1800221CF
0x1800221af  mov     rax, [rcx+68h]
0x1800221b3  mov     [rbp+190h+var_1A0], rax
0x1800221b7  mov     eax, [rcx+60h]
0x1800221ba  mov     [rbp+190h+var_210], eax
0x1800221bd  mov     rax, [rcx+58h]
0x1800221c1  mov     rcx, [rcx+50h]
0x1800221c5  mov     [rbp+190h+pSid1], rcx
0x1800221c9  mov     [rbp+190h+var_138], rax
0x1800221cd  jmp     short loc_1800221DE
0x1800221cf  mov     [rbp+190h+var_1A0], rdi
0x1800221d3  mov     [rbp+190h+var_210], edi
0x1800221d6  mov     [rbp+190h+var_138], rdi
0x1800221da  mov     [rbp+190h+pSid1], rdi
0x1800221de  mov     eax, [r12]
0x1800221e2  mov     edi, 1
0x1800221e7  sub     eax, edi
0x1800221e9  mov     [rbp+190h+Size], 30h ; '0'
0x1800221f1  cmp     eax, edi
0x1800221f3  mov     qword ptr [rbp+190h+StartupInfo], 70h ; 'p'
0x1800221fe  xorps   xmm1, xmm1
0x180022201  movdqa  xmmword ptr [rbp+190h+StartupInfo+10h], xmm0
0x180022209  setbe   cl
0x18002220c  movdqa  xmmword ptr [rbp+190h+StartupInfo+50h], xmm0
0x180022214  xor     eax, eax
0x180022216  mov     [rsp+290h+var_22F], cl
0x18002221a  neg     [rbp+190h+arg_38]
0x180022220  mov     [rbp+190h+var_1A8], eax
0x180022223  mov     [rbp+190h+var_1F0], rax
0x180022227  mov     [rsp+290h+var_230], al
0x18002222b  mov     [rbp+190h+var_F8], rax
0x180022232  mov     qword ptr [rbp+190h+StartupInfo+8], rax
0x180022239  mov     qword ptr [rbp+190h+StartupInfo+20h], rax
0x180022240  mov     qword ptr [rbp+190h+StartupInfo+28h], rax
0x180022247  mov     qword ptr [rbp+190h+StartupInfo+30h], rax
0x18002224e  mov     dword ptr [rbp+190h+StartupInfo+38h], eax
0x180022254  sbb     eax, eax
0x180022256  neg     eax
0x180022258  movdqa  xmmword ptr [rbp+190h+StartupInfo+60h], xmm1
0x180022260  sub     eax, 0FFFFFF80h
0x180022263  mov     dword ptr [rbp+190h+StartupInfo+3Ch], eax
0x180022269  xor     eax, eax
0x18002226b  mov     qword ptr [rbp+190h+StartupInfo+40h], rax
0x180022272  mov     qword ptr [rbp+190h+StartupInfo+48h], rax
0x180022279  movups  [rbp+190h+var_80], xmm0
0x180022280  movups  [rbp+190h+var_70], xmm0
0x180022287  movups  [rbp+190h+var_60], xmm0
0x18002228e  movups  [rbp+190h+Value], xmm0
0x180022295  test    cl, cl
0x180022297  jz      loc_180022968
0x18002229d  mov     rax, [rbp+190h+var_190]
0x1800222a1  test    rax, rax
0x1800222a4  jz      loc_18002291E
0x1800222aa  mov     rcx, [rbp+190h+var_188]
0x1800222ae  test    rcx, rcx
0x1800222b1  jz      loc_18002291E
0x1800222b7  mov     r14, [rbp+190h+var_180]
0x1800222bb  test    r14, r14
0x1800222be  jz      loc_18002291E
0x1800222c4  cmp     [rbp+190h+var_1C8], rbx
0x1800222c8  jz      loc_18002291E
0x1800222ce  cmp     [rbp+190h+var_1C0], rbx
0x1800222d2  jz      loc_18002291E
0x1800222d8  cmp     [rbp+190h+var_178], rbx
0x1800222dc  jz      loc_18002291E
0x1800222e2  test    rdx, rdx
0x1800222e5  jz      loc_18002291E
0x1800222eb  mov     [rax], rbx
0x1800222ee  mov     rax, [rbp+190h+var_1C8]
0x1800222f2  mov     [rcx], ebx
0x1800222f4  xor     ecx, ecx
0x1800222f6  mov     [r14], rcx
0x1800222f9  mov     [rax], rcx
0x1800222fc  mov     rax, [rbp+190h+var_1C0]
0x180022300  mov     [rax], rcx
0x180022303  mov     rax, [rbp+190h+var_178]
0x180022307  mov     [rax], rcx
0x18002230a  mov     rax, [r12+20h]
0x18002230f  test    rax, rax
0x180022312  jz      short loc_18002231A
0x180022314  mov     rax, [rax+28h]
0x180022318  jmp     short loc_18002231D
0x18002231a  mov     rax, rcx
0x18002231d  mov     r14, [rsp+290h+var_228]
0x180022322  mov     [rdx], rax
0x180022325  test    r14, r14
0x180022328  jz      loc_180022489
0x18002232e  test    r9, r9
0x180022331  lea     rcx, [rbp+190h+var_1F8]
0x180022335  mov     [rsp+290h+lpProcessInformation], rcx
0x18002233a  lea     rax, [rbp+190h+var_1A8]
0x18002233e  cmovnz  rax, r9
0x180022342  lea     rcx, [rbp+190h+var_1B0]
0x180022346  mov     r9d, [rbp+190h+arg_28]
0x18002234d  mov     [rsp+290h+lpStartupInfo], rcx
0x180022352  mov     rcx, r12
0x180022355  mov     [rsp+290h+lpCurrentDirectory], rax
0x18002235a  mov     [rsp+290h+lpReturnSize], r14
0x18002235f  mov     byte ptr [rsp+290h+lpPreviousValue], r8b
0x180022364  mov     r8, r10
0x180022367  mov     [rsp+290h+cbSize], rdx
0x18002236c  mov     rdx, r11
0x18002236f  call    UbpmpTokenCheckHarden
0x180022374  mov     ebx, eax
0x180022376  test    eax, eax
0x180022378  jz      short loc_1800223B8
0x18002237a  mov     rcx, cs:WPP_GLOBAL_Control
0x180022381  lea     rax, WPP_GLOBAL_Control
0x180022388  cmp     rcx, rax
0x18002238b  jz      short loc_1800223AF
0x18002238d  test    [rcx+1Ch], dil
0x180022391  jz      short loc_1800223AF
0x180022393  mov     rcx, [rcx+10h]
0x180022397  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x18002239e  mov     edx, 5Fh ; '_'
0x1800223a3  mov     dword ptr [rsp+290h+cbSize], ebx
0x1800223a7  mov     r9, rsi
0x1800223aa  call    WPP_SF_Sd
0x1800223af  mov     r13, [rbp+190h+var_1F8]
0x1800223b3  jmp     loc_18002325E
0x1800223b8  mov     r14d, dword ptr [rbp+190h+arg_48]
0x1800223bf  and     r14d, 10h
0x1800223c3  cmp     [rsp+290h+var_22C], r13d
0x1800223c8  jnz     short loc_180022415
0x1800223ca  mov     rcx, [rsp+290h+var_228]
0x1800223cf  lea     rdx, [rbp+190h+var_1D0]
0x1800223d3  mov     rcx, [rcx]
0x1800223d6  call    cs:__imp_LoadProfileBasic
0x1800223dc  test    eax, eax
0x1800223de  jns     short loc_180022415
0x1800223e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800223e7  lea     rdx, WPP_GLOBAL_Control
0x1800223ee  cmp     rcx, rdx
0x1800223f1  jz      short loc_180022415
0x1800223f3  test    [rcx+1Ch], dil
0x1800223f7  jz      short loc_180022415
0x1800223f9  mov     rcx, [rcx+10h]
0x1800223fd  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x180022404  mov     edx, 60h ; '`'
0x180022409  mov     dword ptr [rsp+290h+cbSize], eax
0x18002240d  mov     r9, rsi
0x180022410  call    WPP_SF_SL
0x180022415  test    r15d, r15d
0x180022418  jnz     short loc_18002241F
0x18002241a  test    r14d, r14d
0x18002241d  jz      short loc_180022480
0x18002241f  test    dil, r15b
0x180022422  jnz     short loc_18002242C
0x180022424  mov     edx, r13d
0x180022427  test    r14d, r14d
0x18002242a  jz      short loc_18002242E
0x18002242c  mov     edx, edi
0x18002242e  mov     r14, [rsp+290h+var_228]
0x180022433  lea     r8, [rbp+190h+hObject]
0x180022437  mov     rcx, [r14]; ExistingTokenHandle
0x18002243a  call    UbpmDeriveToken
0x18002243f  mov     ebx, eax
0x180022441  test    eax, eax
0x180022443  jz      short loc_180022485
0x180022445  mov     rcx, cs:WPP_GLOBAL_Control
0x18002244c  lea     rax, WPP_GLOBAL_Control
0x180022453  cmp     rcx, rax
0x180022456  jz      loc_1800223AF
0x18002245c  test    [rcx+1Ch], dil
0x180022460  jz      loc_1800223AF
0x180022466  mov     rcx, [rcx+10h]
0x18002246a  mov     r9, rsi
0x18002246d  mov     dword ptr [rsp+290h+lpPreviousValue], r15d
0x180022472  mov     dword ptr [rsp+290h+cbSize], ebx
0x180022476  call    WPP_SF_SdL
0x18002247b  jmp     loc_1800223AF
0x180022480  mov     r14, [rsp+290h+var_228]
0x180022485  mov     r13, [rbp+190h+var_1F8]
0x180022489  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ShadowAdmin@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin> `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl(void)'::`2'::impl
0x180022490  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(void)
0x180022495  xor     r15d, r15d
0x180022498  mov     r8d, r15d
0x18002249b  test    al, al
0x18002249d  jz      short loc_1800224B1
0x18002249f  mov     rdx, [rbp+190h+hObject]
0x1800224a3  test    r14, r14
0x1800224a6  setz    r8b
0x1800224aa  test    rdx, rdx
0x1800224ad  jz      short loc_1800224B8
0x1800224af  jmp     short loc_1800224C9
0x1800224b1  test    r14, r14
0x1800224b4  setz    r8b
0x1800224b8  test    r14, r14
0x1800224bb  jz      short loc_1800224C2
0x1800224bd  mov     rdx, [r14]
0x1800224c0  jmp     short loc_1800224C9
0x1800224c2  mov     rdx, cs:?g_Globals@@3U_UBPM_GLOBAL_DATA@@A; _UBPM_GLOBAL_DATA g_Globals
0x1800224c9  lea     rcx, [rsp+290h+lpEnvironment]
0x1800224ce  call    cs:__imp_CreateEnvBlock
0x1800224d4  test    eax, eax
0x1800224d6  jns     short loc_18002251A
0x1800224d8  mov     rax, cs:WPP_GLOBAL_Control
0x1800224df  lea     rcx, WPP_GLOBAL_Control
0x1800224e6  cmp     rax, rcx
0x1800224e9  jz      short loc_18002251A
0x1800224eb  test    [rax+1Ch], dil
0x1800224ef  jz      short loc_18002251A
0x1800224f1  call    cs:__imp_GetLastError
0x1800224f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800224fe  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x180022505  mov     edx, 62h ; 'b'
0x18002250a  mov     dword ptr [rsp+290h+cbSize], eax
0x18002250e  mov     r9, rsi
0x180022511  mov     rcx, [rcx+10h]
0x180022515  call    WPP_SF_Sd
0x18002251a  mov     r14, [rbp+190h+pSid1]
0x18002251e  test    r14, r14
0x180022521  jz      loc_180022634
0x180022527  lea     r9, [rbp+190h+Size]; lpSize
0x18002252b  xor     r8d, r8d; dwFlags
0x18002252e  mov     edx, edi; dwAttributeCount
0x180022530  lea     rcx, [rbp+190h+var_80]; lpAttributeList
0x180022537  call    cs:__imp_InitializeProcThreadAttributeList
0x18002253d  test    eax, eax
  ... truncated ...
```
