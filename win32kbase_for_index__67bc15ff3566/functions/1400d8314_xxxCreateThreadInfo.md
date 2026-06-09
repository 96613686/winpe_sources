# xxxCreateThreadInfo

- ea: `0x1400d8314`
- end: `0x1400d98b6`
- name: `xxxCreateThreadInfo`
- size: `5538`
- prototype: `__int64 __fastcall(PETHREAD Thread)`
- caller_count: `2`
- callee_count: `45`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14009ed0c`
- `0x1400d7a30`

## callees

- `0x1400095f0`
- `0x140029710`
- `0x140035ecc`
- `0x14004bf50`
- `0x14004c020`
- `0x14004dcd0`
- `0x14004dd98`
- `0x14004dfb0`
- `0x14004f4c0`
- `0x14006b500`
- `0x14006b5d0`
- `0x14006fff0`
- `0x1400700d8`
- `0x1400701d4`
- `0x140070518`
- `0x1400c2860`
- `0x1400c9b60`
- `0x1400cb0e0`
- `0x1400d825c`
- `0x1400d8288`
- `0x1400d8314`
- `0x1400d98bc`
- `0x1400eccac`
- `0x1400faaf0`
- `0x140113ca8`
- `0x140114910`
- `0x140120154`
- `0x140129da0`
- `0x14012e3b0`
- `0x140132030`
- `0x14013616c`
- `0x14013628c`
- `0x1401362ec`
- `0x14013bfac`
- `0x14014924c`
- `0x14014fdcc`
- `0x140159ca8`
- `0x1401741ec`
- `0x14017a710`
- `0x140196ba8`
- `0x1401aab9c`
- `0x1401bbc10`
- `0x1401c7c34`
- `0x1402389c0`
- `0x140238a40`

## import_xrefs

- `ntoskrnl!PsGetProcessPeb` at `0x1400d8466`
- `ntoskrnl!PsGetProcessPeb` at `0x1400d956e`
- `ntoskrnl!PsGetProcessPeb` at `0x1400d8466`
- `ntoskrnl!PsGetProcessPeb` at `0x1400d956e`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400d8eba`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400d8eba`
- `ntoskrnl!ProbeForRead` at `0x1400d849b`
- `ntoskrnl!ProbeForRead` at `0x1400d84f1`
- `ntoskrnl!ProbeForRead` at `0x1400d849b`
- `ntoskrnl!ProbeForRead` at `0x1400d84f1`
- `ntoskrnl!KeBugCheckEx` at `0x1400d86e6`
- `ntoskrnl!KeBugCheckEx` at `0x1400d871d`
- `ntoskrnl!KeBugCheckEx` at `0x1400d9201`
- `ntoskrnl!KeBugCheckEx` at `0x1400d86e6`
- `ntoskrnl!KeBugCheckEx` at `0x1400d871d`
- `ntoskrnl!KeBugCheckEx` at `0x1400d9201`
- `ntoskrnl!PsGetThreadProcess` at `0x1400d832a`
- `ntoskrnl!PsGetThreadProcess` at `0x1400d832a`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400d83e5`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400d8738`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400d93b5`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400d83e5`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400d8738`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400d93b5`
- `ntoskrnl!ExRaiseStatus` at `0x1400d86bb`
- `ntoskrnl!ExRaiseStatus` at `0x1400d86f5`
- `ntoskrnl!ExRaiseStatus` at `0x1400d86bb`
- `ntoskrnl!ExRaiseStatus` at `0x1400d86f5`
- `ntoskrnl!PsGetThreadProcessId` at `0x1400d876b`
- `ntoskrnl!PsGetThreadProcessId` at `0x1400d876b`
- `ntoskrnl!PsGetProcessSectionBaseAddress` at `0x1400d9582`
- `ntoskrnl!PsGetProcessSectionBaseAddress` at `0x1400d9582`
- `ntoskrnl!ZwCreateEvent` at `0x1400d8a23`
- `ntoskrnl!ZwCreateEvent` at `0x1400d8a23`
- `ntoskrnl!ExEventObjectType` at `0x1400d8d64`
- `ntoskrnl!ExEventObjectType` at `0x1400d8d9c`
- `ntoskrnl!ZwTerminateProcess` at `0x1400d935a`
- `ntoskrnl!ZwTerminateProcess` at `0x1400d935a`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1400d8cbf`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1400d8cbf`
- `ntoskrnl!ExDesktopObjectType` at `0x1400d8e61`
- `ntoskrnl!PsGetProcessId` at `0x1400d8f44`
- `ntoskrnl!PsGetProcessId` at `0x1400d8f44`
- `ntoskrnl!PsGetProcessInheritedFromUniqueProcessId` at `0x1400d9764`
- `ntoskrnl!PsGetProcessInheritedFromUniqueProcessId` at `0x1400d9764`
- `ntoskrnl!ObCloseHandle` at `0x1400d95cb`
- `ntoskrnl!ObCloseHandle` at `0x1400d95cb`
- `ntoskrnl!ObDuplicateObject` at `0x1400d8a6f`
- `ntoskrnl!ObDuplicateObject` at `0x1400d8a6f`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400d8d74`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400d8e75`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400d8d74`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400d8e75`
- `ntoskrnl!ObfDereferenceObject` at `0x1400d8ea3`
- `ntoskrnl!ObfDereferenceObject` at `0x1400d8ea3`
- `ntoskrnl!PsGetProcessWin32Process` at `0x1400d9433`
- `ntoskrnl!PsGetProcessWin32Process` at `0x1400d9433`
- `ntoskrnl!PsGetThreadId` at `0x1400d892a`
- `ntoskrnl!PsGetThreadId` at `0x1400d892a`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400d89bd`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400d8b4f`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400d8c11`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400d8c63`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400d8db5`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400d8de2`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400d8ee8`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400d8f7c`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400d90e7`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400d9180`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400d91af`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400d920e`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400d923b`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400d93ff`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400d89bd`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400d8b4f`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400d8c11`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400d8c63`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400d8db5`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400d8de2`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400d8ee8`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400d8f7c`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400d90e7`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400d9180`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400d91af`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400d920e`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400d923b`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400d93ff`
- `WIN32K!W32GetUserGdiSessionState` at `0x1400d8436`
- `WIN32K!W32GetUserGdiSessionState` at `0x1400d8afe`
- `WIN32K!W32GetUserGdiSessionState` at `0x1400d8436`
- `WIN32K!W32GetUserGdiSessionState` at `0x1400d8afe`
- `WIN32K!W32GetUserSessionState` at `0x1400d83cd`
- `WIN32K!W32GetUserSessionState` at `0x1400d841f`
- `WIN32K!W32GetUserSessionState` at `0x1400d877a`
- `WIN32K!W32GetUserSessionState` at `0x1400d87a5`
- `WIN32K!W32GetUserSessionState` at `0x1400d87bf`
- `WIN32K!W32GetUserSessionState` at `0x1400d87d8`
- `WIN32K!W32GetUserSessionState` at `0x1400d87ed`
- `WIN32K!W32GetUserSessionState` at `0x1400d881b`
- `WIN32K!W32GetUserSessionState` at `0x1400d894b`
- `WIN32K!W32GetUserSessionState` at `0x1400d8960`
- `WIN32K!W32GetUserSessionState` at `0x1400d898e`
- `WIN32K!W32GetUserSessionState` at `0x1400d8beb`
- `WIN32K!W32GetUserSessionState` at `0x1400d8f2c`
- `WIN32K!W32GetUserSessionState` at `0x1400d8fff`
- `WIN32K!W32GetUserSessionState` at `0x1400d9079`
- `WIN32K!W32GetUserSessionState` at `0x1400d90b1`
- `WIN32K!W32GetUserSessionState` at `0x1400d926f`
- `WIN32K!W32GetUserSessionState` at `0x1400d928e`
- `WIN32K!W32GetUserSessionState` at `0x1400d92a6`
- `WIN32K!W32GetUserSessionState` at `0x1400d92b8`
- `WIN32K!W32GetUserSessionState` at `0x1400d9366`
- `WIN32K!W32GetUserSessionState` at `0x1400d948b`
- `WIN32K!W32GetUserSessionState` at `0x1400d94a0`
- `WIN32K!W32GetUserSessionState` at `0x1400d94b3`
- `WIN32K!W32GetUserSessionState` at `0x1400d94c6`
- `WIN32K!W32GetUserSessionState` at `0x1400d94df`
- `WIN32K!W32GetUserSessionState` at `0x1400d94f2`
- `WIN32K!W32GetUserSessionState` at `0x1400d9733`
- `WIN32K!W32GetUserSessionState` at `0x1400d974c`
- `WIN32K!W32GetUserSessionState` at `0x1400d9775`
- `WIN32K!W32GetUserSessionState` at `0x1400d9788`
- `WIN32K!W32GetUserSessionState` at `0x1400d97a2`
- `WIN32K!W32GetUserSessionState` at `0x1400d83cd`
- `WIN32K!W32GetUserSessionState` at `0x1400d841f`
- `WIN32K!W32GetUserSessionState` at `0x1400d877a`
- `WIN32K!W32GetUserSessionState` at `0x1400d87a5`
- `WIN32K!W32GetUserSessionState` at `0x1400d87bf`
- `WIN32K!W32GetUserSessionState` at `0x1400d87d8`
- `WIN32K!W32GetUserSessionState` at `0x1400d87ed`
- `WIN32K!W32GetUserSessionState` at `0x1400d881b`
- `WIN32K!W32GetUserSessionState` at `0x1400d894b`
- `WIN32K!W32GetUserSessionState` at `0x1400d8960`
- `WIN32K!W32GetUserSessionState` at `0x1400d898e`
- `WIN32K!W32GetUserSessionState` at `0x1400d8beb`
- `WIN32K!W32GetUserSessionState` at `0x1400d8f2c`
- `WIN32K!W32GetUserSessionState` at `0x1400d8fff`
- `WIN32K!W32GetUserSessionState` at `0x1400d9079`
- `WIN32K!W32GetUserSessionState` at `0x1400d90b1`
- `WIN32K!W32GetUserSessionState` at `0x1400d926f`
- `WIN32K!W32GetUserSessionState` at `0x1400d928e`
- `WIN32K!W32GetUserSessionState` at `0x1400d92a6`
- `WIN32K!W32GetUserSessionState` at `0x1400d92b8`
- `WIN32K!W32GetUserSessionState` at `0x1400d9366`
- `WIN32K!W32GetUserSessionState` at `0x1400d948b`
- `WIN32K!W32GetUserSessionState` at `0x1400d94a0`
- `WIN32K!W32GetUserSessionState` at `0x1400d94b3`
- `WIN32K!W32GetUserSessionState` at `0x1400d94c6`
- `WIN32K!W32GetUserSessionState` at `0x1400d94df`
- `WIN32K!W32GetUserSessionState` at `0x1400d94f2`
- `WIN32K!W32GetUserSessionState` at `0x1400d9733`
- `WIN32K!W32GetUserSessionState` at `0x1400d974c`
- `WIN32K!W32GetUserSessionState` at `0x1400d9775`
- `WIN32K!W32GetUserSessionState` at `0x1400d9788`
- `WIN32K!W32GetUserSessionState` at `0x1400d97a2`

## pseudocode

```c
__int64 __fastcall xxxCreateThreadInfo(PETHREAD Thread)
{
  struct _KPROCESS *ThreadProcess; // rbx
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 CurrentProcessWin32Process; // rax
  __int64 v7; // r8
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 UserSessionState; // rax
  int v11; // r12d
  __int64 ThreadWin32Thread; // r14
  __int64 v13; // rdx
  NTSTATUS v14; // eax
  __int64 v15; // rdx
  ULONG_PTR v16; // rbx
  NTSTATUS v17; // eax
  ULONG_PTR v18; // rbx
  struct tagTHREADINFO *v19; // rax
  struct tagTHREADINFO *v20; // rax
  struct tagTHREADINFO *BugCheckParameter4; // rax
  struct tagTHREADINFO *v22; // rax
  __int64 v23; // rax
  __int64 v24; // r15
  int v25; // edi
  HANDLE ThreadProcessId; // rbx
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // r8
  __int64 v30; // rdx
  __int64 v31; // rcx
  __int64 v32; // r8
  unsigned int v33; // r13d
  __int64 v34; // rdx
  __int64 v35; // rcx
  __int64 v36; // r8
  __int64 v37; // rdx
  __int64 v38; // rcx
  __int64 v39; // r8
  __int64 v40; // rdx
  __int64 v41; // rcx
  __int64 v42; // r8
  __int64 v43; // rax
  __int64 v44; // rcx
  __int64 v45; // rdx
  __int64 v46; // rcx
  struct _NT_TIB *v47; // rbx
  __int64 v48; // rdx
  __int64 v49; // rcx
  __int64 v50; // r8
  __int64 v51; // rax
  __int64 v52; // rdx
  __int64 v53; // rcx
  __int64 (*v54)(void); // rax
  int v55; // eax
  int v56; // r12d
  HANDLE *v57; // rbx
  NTSTATUS Event; // edi
  PEPROCESS v59; // r13
  __int64 v60; // r8
  int v61; // eax
  __int64 v62; // rdx
  struct tagQ *v63; // rax
  struct tagQ *v64; // rbx
  __int64 v65; // rdx
  __int64 v66; // rcx
  __int64 v67; // r8
  _DWORD *v68; // r13
  __int64 v69; // rdx
  __int64 v70; // rcx
  __int64 (*v71)(void); // rax
  __int64 v72; // rdx
  __int64 v73; // rcx
  _QWORD *v74; // rdi
  int v75; // ebx
  __int64 v76; // rdx
  __int64 v77; // rcx
  __int64 (__fastcall *v78)(__int64, _QWORD *, HANDLE *, _QWORD, HANDLE *); // rax
  __int64 (*v79)(void); // rax
  unsigned int CurrentProcessId; // eax
  __int64 v81; // r8
  __int64 v83; // rdx
  __int64 v84; // r9
  __int64 v85; // rdx
  __int64 v86; // rcx
  __int64 (*v87)(void); // rax
  int v88; // eax
  __int64 (__fastcall *v89)(__int64); // rax
  __int64 v91; // rdx
  __int64 v92; // rcx
  __int64 v93; // rdx
  __int64 v94; // rcx
  __int64 v95; // r8
  __int64 (__fastcall *v96)(__int128 *); // rax
  HANDLE v97; // rbx
  void (*v98)(void); // rax
  __int64 v99; // rdx
  __int64 v100; // rcx
  __int64 v101; // r8
  __int64 v102; // rdx
  __int64 v103; // rcx
  __int64 v104; // r8
  char v105; // al
  int v106; // ebx
  __int64 v107; // rdx
  __int64 v108; // r8
  __int64 v109; // rcx
  __int64 v110; // rcx
  __int64 v111; // rdx
  __int64 v112; // rcx
  __int64 v113; // rdx
  __int64 v114; // rcx
  __int64 (*v115)(void); // rax
  __int64 v116; // rax
  __int64 v117; // rdx
  __int64 v118; // rcx
  __int64 (*v119)(void); // rax
  __int64 (*v120)(void); // rax
  struct tagTHREADINFO *v121; // rax
  __int64 (*v122)(void); // rax
  int v123; // eax
  void (__fastcall *v124)(_QWORD); // rax
  __int64 v125; // rax
  __int64 v126; // rdx
  __int64 v127; // rcx
  __int64 v128; // r8
  __int64 v129; // rdx
  __int64 v130; // rcx
  __int64 v131; // r8
  __int64 v132; // rax
  __int64 v133; // rdx
  __int64 v134; // rcx
  __int64 v135; // r8
  _QWORD *v136; // rbx
  __int64 v137; // rdx
  __int64 v138; // rcx
  __int64 v139; // r8
  __int64 v140; // r14
  __int64 v141; // rax
  __int64 v142; // rax
  __int64 v143; // rax
  char v144; // al
  void (__fastcall *v145)(__int64); // rax
  __int64 ProcessWin32Process; // rax
  __int64 v147; // rcx
  __int64 v148; // rdx
  __int64 v149; // rcx
  __int64 v150; // r8
  __int64 v151; // rbx
  __int64 v152; // rdx
  __int64 v153; // rcx
  __int64 v154; // r8
  __int64 v155; // rax
  __int64 v156; // rdx
  __int64 v157; // rdx
  __int64 v158; // rcx
  __int64 v159; // r8
  PEPROCESS v160; // rbx
  __int64 ProcessSectionBaseAddress; // rax
  unsigned int v162; // eax
  __int64 v163; // rbx
  __int64 v164; // rbx
  __int64 v165; // rdx
  __int64 v166; // rcx
  __int64 v167; // r8
  __int64 v168; // rcx
  __int64 v169; // rbx
  __int64 v170; // rdx
  __int64 v171; // r8
  char *v172; // [rsp+40h] [rbp-188h] BYREF
  __int64 v173; // [rsp+48h] [rbp-180h]
  PEPROCESS Process; // [rsp+50h] [rbp-178h]
  PVOID Object; // [rsp+58h] [rbp-170h] BYREF
  HANDLE v176; // [rsp+60h] [rbp-168h] BYREF
  _QWORD *v177; // [rsp+68h] [rbp-160h]
  ULONG_PTR v178[2]; // [rsp+70h] [rbp-158h] BYREF
  __int64 (__fastcall *v179)(PVOID); // [rsp+80h] [rbp-148h]
  ULONG_PTR BugCheckParameter2[2]; // [rsp+88h] [rbp-140h] BYREF
  __int64 (__fastcall *v181)(PVOID); // [rsp+98h] [rbp-130h]
  ULONG_PTR v182[2]; // [rsp+A0h] [rbp-128h] BYREF
  __int64 v183; // [rsp+B0h] [rbp-118h]
  __int64 v184; // [rsp+B8h] [rbp-110h]
  __int64 v185; // [rsp+C0h] [rbp-108h]
  _QWORD v186[12]; // [rsp+D0h] [rbp-F8h] BYREF
  __int128 v187; // [rsp+130h] [rbp-98h] BYREF
  __int128 v188; // [rsp+140h] [rbp-88h]
  __int128 v189; // [rsp+150h] [rbp-78h]
  _QWORD *v190; // [rsp+160h] [rbp-68h]
  char *v191; // [rsp+168h] [rbp-60h]
  volatile void *Address; // [rsp+1D8h] [rbp+10h] BYREF
  struct _NT_TIB *Self; // [rsp+1E0h] [rbp+18h]
  HANDLE Handle; // [rsp+1E8h] [rbp+20h] BYREF

  ThreadProcess = PsGetThreadProcess(Thread);
  Process = ThreadProcess;
  memset(v186, 0, 0x48u);
  Handle = 0;
  v176 = 0;
  Self = KeGetPcr()->NtTib.Self;
  Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(BugCheckParameter2);
  Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(v178);
  Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(v182);
  v187 = 0;
  v188 = 0;
  v189 = 0;
  if ( (Microsoft_Windows_Win32kEnableBits & 0x8000) != 0 )
    McTemplateK0_EtwWriteTransfer(v4, InitiateGuiThreadExecution, &W32kControlGuid);
  if ( !*(_DWORD *)(W32GetUserSessionState(v4, v3, v5) + 36232) )
  {
    CurrentProcessWin32Process = PsGetCurrentProcessWin32Process();
    if ( CurrentProcessWin32Process )
    {
      v8 = -*(_QWORD *)CurrentProcessWin32Process;
      v9 = -(__int64)(*(_QWORD *)CurrentProcessWin32Process != 0);
      if ( (v9 & CurrentProcessWin32Process) != 0 )
      {
        v185 = 0;
        v184 = 0;
        UserSessionState = W32GetUserSessionState(v8, v9, v7);
        ++*(_DWORD *)(UserSessionState + 36240);
        v11 = 33554504;
        if ( ThreadProcess != *(struct _KPROCESS **)(W32GetUserGdiSessionState() + 40) )
          v11 = 0;
        ThreadWin32Thread = W32GetThreadWin32Thread(Thread);
        v186[6] = 0;
        Address = (volatile void *)PsGetProcessPeb(ThreadProcess);
        v186[10] = 1;
        ProbeForRead(Address, 1u, 1u);
        Address = (volatile void *)*((_QWORD *)Address + 4);
        v177 = v186;
        v190 = v186;
        v186[11] = 1;
        ProbeForRead(Address, 1u, 1u);
        v186[0] = *((_QWORD *)Address + 4);
        v186[1] = *((_QWORD *)Address + 5);
        v186[2] = *((_QWORD *)Address + 17);
        v186[3] = *((_QWORD *)Address + 18);
        v186[4] = *(_QWORD *)((char *)Address + 164);
        v191 = (char *)Address + 192;
        v14 = DuplicateUnicodeStringFromUser<0>((char *)Address + 192, v13, &v186[5]);
        if ( v14 < 0 )
          ExRaiseStatus(v14);
        v16 = v186[6];
        if ( v186[6] )
        {
          v185 = v186[6];
          if ( v181 != (__int64 (__fastcall *)(PVOID))-1LL )
          {
            BugCheckParameter4 = PtiCurrent();
            KeBugCheckEx(0x164u, 0x12u, (ULONG_PTR)BugCheckParameter2, v16, (ULONG_PTR)BugCheckParameter4);
          }
          v20 = PtiCurrent();
          BugCheckParameter2[0] = *((_QWORD *)v20 + 47);
          *((_QWORD *)v20 + 47) = BugCheckParameter2;
          BugCheckParameter2[1] = v16;
          v181 = GreDeleteFastMutex;
        }
        v172 = (char *)Address + 208;
        v17 = DuplicateUnicodeStringFromUser<0>((char *)Address + 208, v15, &v186[7]);
        if ( v17 < 0 )
          ExRaiseStatus(v17);
        v18 = v186[8];
        if ( v186[8] )
        {
          v184 = v186[8];
          if ( v179 != (__int64 (__fastcall *)(PVOID))-1LL )
          {
            v22 = PtiCurrent();
            KeBugCheckEx(0x164u, 0x12u, (ULONG_PTR)v178, v18, (ULONG_PTR)v22);
          }
          v19 = PtiCurrent();
          v178[0] = *((_QWORD *)v19 + 47);
          *((_QWORD *)v19 + 47) = v178;
          v178[1] = v18;
          v179 = GreDeleteFastMutex;
        }
        v23 = PsGetCurrentProcessWin32Process();
        v24 = v23;
        if ( v23 )
          v24 = -(__int64)(*(_QWORD *)v23 != 0) & v23;
        v25 = v11 | 0x100;
        if ( *(char *)(v24 + 12) >= 0 )
          v25 = v11;
        ThreadProcessId = PsGetThreadProcessId(Thread);
        v33 = v25 | 0x2000000;
        if ( *(HANDLE *)(W32GetUserSessionState(v28, v27, v29) + 63312) != ThreadProcessId )
          v33 = v25;
        _InterlockedOr((volatile signed __int32 *)(ThreadWin32Thread + 520), v33);
        v35 = *(unsigned int *)(W32GetUserSessionState(v31, v30, v32) + 66792);
        if ( (v35 & 0x80u) != 0LL )
        {
          if ( *(_QWORD *)(W32GetUserSessionState(v35, v34, v36) + 14216) )
          {
            v51 = W32GetUserSessionState(v49, v48, v50);
            if ( (*(_BYTE *)(HMPheFromObject(*(_QWORD *)(v51 + 14216)) + 25) & 1) != 0 )
            {
              LODWORD(Address) = 0x20000;
              MicrosoftTelemetryAssertTriggeredArgsKM("IXPTellMeIf", 0x20000, 1338);
            }
          }
          v172 = (char *)(ThreadWin32Thread + 472);
          v44 = *(_QWORD *)(W32GetUserSessionState(v49, v48, v50) + 14216);
LABEL_32:
          v173 = v44;
          HMAssignmentLock(&v172, 0);
          *(_QWORD *)(ThreadWin32Thread + 480) = ThreadWin32Thread + 1088;
          if ( (*(_DWORD *)(v24 + 12) & 0x800000) != 0 )
            _InterlockedOr((volatile signed __int32 *)(ThreadWin32Thread + 520), 0x2000000u);
          *(_QWORD *)(ThreadWin32Thread + 456) = v24;
          *(_QWORD *)(ThreadWin32Thread + 696) = *(_QWORD *)(v24 + 328);
          *(_QWORD *)(v24 + 328) = ThreadWin32Thread;
          ++*(_DWORD *)(v24 + 376);
          if ( Self )
          {
            v47 = Self;
            v47[2].StackBase = PsGetThreadId(*(PETHREAD *)ThreadWin32Thread);
          }
          *(_QWORD *)(ThreadWin32Thread + 512) = (char *)Self + 2048;
          *(_DWORD *)(*(_QWORD *)(ThreadWin32Thread + 512) + 232LL) = *(_DWORD *)(ThreadWin32Thread + 392);
          *(_DWORD *)(*(_QWORD *)(ThreadWin32Thread + 512) + 236LL) = 0;
          *(_QWORD *)(ThreadWin32Thread + 400) = *(_QWORD *)(ThreadWin32Thread + 512) + 232LL;
          v46 = *(_QWORD *)(ThreadWin32Thread + 512);
          *(_DWORD *)(v46 + 240) = *(_DWORD *)(ThreadWin32Thread + 396);
          *(_DWORD *)(*(_QWORD *)(ThreadWin32Thread + 512) + 244LL) = 0;
          *(_QWORD *)(ThreadWin32Thread + 408) = *(_QWORD *)(ThreadWin32Thread + 512) + 240LL;
          if ( (*(_DWORD *)(v24 + 12) & 0x2000000) != 0 )
            _InterlockedOr((volatile signed __int32 *)(ThreadWin32Thread + 520), 0x20000000u);
          if ( !*(_DWORD *)(ThreadWin32Thread + 664) )
          {
            v160 = Process;
            if ( PsGetProcessPeb(Process) )
            {
              ProcessSectionBaseAddress = PsGetProcessSectionBaseAddress(v160);
              *(_DWORD *)(ThreadWin32Thread + 664) = RtlGetExpWinVer(ProcessSectionBaseAddress);
            }
            else
            {
              *(_DWORD *)(ThreadWin32Thread + 664) = 1536;
            }
          }
          v53 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v46, v45) + 48);
          v54 = *(__int64 (**)(void))(v53 + 896);
          if ( v54 )
          {
            v55 = v54();
            v56 = -1073741637;
          }
          else
          {
            v56 = -1073741637;
            v55 = -1073741637;
          }
          if ( v55 >= 0 )
          {
            v53 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v53, v52) + 48);
            v98 = *(void (**)(void))(v53 + 904);
            if ( v98 )
              v98();
          }
          LODWORD(Self) = v33 & 0xC;
          if ( (v33 & 0xC) == 0 )
          {
            v86 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v53, v52) + 48);
            v87 = *(__int64 (**)(void))(v86 + 912);
            v88 = v87 ? v87() : -1073741637;
            if ( v88 >= 0 )
            {
              v89 = *(__int64 (__fastcall **)(__int64))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v86, v85) + 48) + 920LL);
              if ( v89 ? v89(ThreadWin32Thread) : 0 )
                *(_DWORD *)(v24 + 12) |= 0x1000000u;
            }
          }
          v57 = (HANDLE *)(ThreadWin32Thread + 752);
          Event = ZwCreateEvent((PHANDLE)(ThreadWin32Thread + 752), 0x1F0003u, 0, SynchronizationEvent, 0);
          if ( Event >= 0 )
          {
            Address = 0;
            Event = ObReferenceObjectByHandle(*v57, 0x1F0003u, (POBJECT_TYPE)ExEventObjectType, 1, (PVOID *)&Address, 0);
            *(_QWORD *)(ThreadWin32Thread + 760) = Address;
            if ( Event < 0 )
            {
              if ( Event != -1073741816 )
                ObCloseHandle(*v57, 1);
            }
            else
            {
              LOBYTE(v84) = 1;
              Event = ProtectHandle(*v57, v83, ExEventObjectType, v84);
            }
          }
          if ( Event < 0 )
          {
            *v57 = 0;
          }
          else
          {
            Event = ObDuplicateObject(Process, *v57, Process, ThreadWin32Thread + 1632, 0, 512, 2, 0);
            if ( Event < 0 )
            {
              *(_QWORD *)(ThreadWin32Thread + 1632) = 0;
            }
            else
            {
              v59 = Process;
              Event = InitializeThreadInfoIocp(Process, (struct tagTHREADINFO *)ThreadWin32Thread);
              if ( Event >= 0 )
              {
                v61 = *(_DWORD *)(v24 + 12);
                v62 = 0x4000;
                LODWORD(Address) = v61 & 0x4000;
                *(_DWORD *)(v24 + 12) = v61 | 0x4000;
                if ( !*(_DWORD *)(v24 + 772) && LODWORD(v186[4]) )
                {
                  *(_DWORD *)(v24 + 772) = 28;
                  *(_QWORD *)(v24 + 776) = v186[2];
                  *(_QWORD *)(v24 + 784) = v186[3];
                  *(_DWORD *)(v24 + 792) = v186[4];
                  *(_WORD *)(v24 + 796) = WORD2(v186[4]);
                }
                if ( (v61 & 0x4000) == 0 )
                {
                  if ( (v186[4] & 0x200) != 0 )
                    v162 = v186[0];
                  else
                    v162 = LOWORD(v186[7])
                         ? ParseReserved((const unsigned __int16 *volatile)v186[8], (const unsigned __int16 *)0x4000)
                         : 0;
                  *(_DWORD *)(v24 + 676) = v162;
                  if ( (v177[4] & 0x400) != 0 )
                  {
                    v163 = v177[1];
                    if ( HMValidateSharedHandle(v163, v62, v60) )
                      *(_QWORD *)(v24 + 680) = v163;
                  }
                }
                v63 = (struct tagQ *)AllocQueue(0, 0);
                v64 = v63;
                if ( v63 )
                {
                  tagTHREADINFO::AssignQueue((tagTHREADINFO *)ThreadWin32Thread, v63);
                  *((_QWORD *)v64 + 13) = ThreadWin32Thread;
                  *((_QWORD *)v64 + 12) = ThreadWin32Thread;
                  ApiSetEditionUpdateRawMouseMode(v64);
                  if ( v59 == *(PEPROCESS *)(W32GetUserGdiSessionState() + 40) )
                  {
                    *((_QWORD *)v64 + 68) = 0x2000;
                  }
                  else
                  {
                    *((_DWORD *)v64 + 136) = *(_DWORD *)(*(_QWORD *)(ThreadWin32Thread + 456) + 864LL);
                    *((_DWORD *)v64 + 137) = *(_DWORD *)(*(_QWORD *)(ThreadWin32Thread + 456) + 868LL);
                    v66 = *(unsigned int *)(*(_QWORD *)(ThreadWin32Thread + 456) + 872LL);
                    *((_DWORD *)v64 + 138) = v66;
                  }
                  if ( (_InterlockedCompareExchange((volatile signed __int32 *)(ThreadWin32Thread + 520), 0, 0) & 0xC) != 0
                    || !*(_QWORD *)(W32GetUserSessionState(v66, v65, v67) + 63288) )
                  {
                    v68 = 0;
                    goto LABEL_59;
                  }
                  v176 = 0;
                  v74 = v177;
                  v75 = *((_DWORD *)v177 + 8);
                  v77 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v73, v72) + 48);
                  v78 = *(__int64 (__fastcall **)(__int64, _QWORD *, HANDLE *, _QWORD, HANDLE *))(v77 + 944);
                  if ( v78 )
                    Event = v78(-1, v74 + 5, &v176, v75 & 0x40000000, &Handle);
                  else
                    Event = -1073741637;
                  if ( Event < 0 )
                  {
                    if ( Event != -1073741205 )
                    {
                      CurrentProcessId = (unsigned int)PsGetCurrentProcessId();
                      if ( (Microsoft_Windows_Win32kEnableBits & 1) != 0 )
                        McTemplateK0dq_EtwWriteTransfer(
                          Microsoft_Windows_Win32kEnableBits,
                          DesktopResolutionFailure,
                          v81,
                          CurrentProcessId,
                          Event);
                      Event = -1073741502;
                      goto LABEL_78;
                    }
                    UserSessionSwitchLeaveCritWithNonPaged(v77);
                    ZwTerminateProcess((HANDLE)0xFFFFFFFFFFFFFFFFLL, -1073741205);
                    v140 = W32GetUserSessionState(v138, v137, v139);
                    v141 = UserCritInternal::_anonymous_namespace_::EnterCritInternal(
                             v140,
                             1,
                             0,
                             _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_);
                    *(_QWORD *)(v140 + 16) = v141;
                    if ( v141 )
                    {
                      if ( (_InterlockedCompareExchange((volatile signed __int32 *)(v141 + 520), 0, 0) & 0x1000000) != 0
                        && *(char *)(v141 + 1360) >= 0 )
                      {
                        v142 = PsGetCurrentProcessWin32Process();
                        if ( !v142 )
                          goto LABEL_78;
                        v143 = -(__int64)(*(_QWORD *)v142 != 0) & v142;
                        if ( !v143 )
                          goto LABEL_78;
                        v144 = *(_BYTE *)(v143 + 1200);
                        if ( v144 != 1 )
                          goto LABEL_78;
                      }
                      else
                      {
                        v144 = 0;
                      }
                      if ( v144 )
                      {
                        while ( 1 )
                        {
                          v136 = *(_QWORD **)(v140 + 19544);
                          if ( !v136 )
                            break;
                          *(_QWORD *)(v140 + 19544) = v136[2];
                          v136[2] = 0;
                          if ( !*(_DWORD *)(*v136 + 8LL) )
                          {
                            LODWORD(Address) = 0x20000;
                            MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 4662);
                          }
                          HMUnlockObject(*v136);
                        }
                        DestroyDeferredUnlockObjectAssignmentList(v140 + 19576);
                        DestroyDeferredUnlockObjectAssignmentList(v140 + 19560);
                      }
                    }
                  }
                  else
                  {
                    v79 = *(__int64 (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v77, v76) + 48) + 952LL);
                    if ( v79 )
                      Event = v79();
                    else
                      Event = -1073741637;
                    if ( Event >= 0 )
                    {
                      AtomicExecutionCheck::AtomicExecutionCheck((AtomicExecutionCheck *)&v172);
                      Event = xxxSetProcessWindowStation(v176);
                      if ( (_BYTE)v172 )
                        --*(_DWORD *)(v173 + 28);
                      if ( Event >= 0 )
                      {
                        Object = 0;
                        Event = ObReferenceObjectByHandle(Handle, 0, (POBJECT_TYPE)ExDesktopObjectType, 1, &Object, 0);
                        v68 = Object;
                        if ( Event < 0 )
                          goto LABEL_79;
                        Win32RawLockedNtObject<tagDESKTOP>::ManualLock((ULONG_PTR)v182, (ULONG_PTR)Object);
                        ObfDereferenceObject(v68);
                        LODWORD(v188) = 1;
                        *((_QWORD *)&v188 + 1) = PsGetCurrentProcess();
                        *(_QWORD *)&v189 = v68;
                        *((_QWORD *)&v189 + 1) = 0x100000000LL;
                        v94 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v92, v91) + 48);
                        v96 = *(__int64 (__fastcall **)(__int128 *))(v94 + 968);
                        Event = v96 ? v96(&v187) : -1073741637;
                        if ( Event < 0 )
                          goto LABEL_79;
                        if ( !*(_QWORD *)(v24 + 384) )
                        {
                          v97 = *(HANDLE *)(W32GetUserSessionState(v94, v93, v95) + 63312);
                          if ( PsGetProcessId(Process) != v97 )
                          {
                            LockObjectAssignment(v24 + 344, v68);
                            *(_QWORD *)(v24 + 384) = Handle;
                          }
                        }
LABEL_59:
                        if ( (unsigned int)InitClientInfo(ThreadWin32Thread) )
                        {
                          AtomicExecutionCheck::AtomicExecutionCheck((AtomicExecutionCheck *)&v172);
                          v71 = *(__int64 (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v70, v69) + 48) + 976LL);
                          if ( v71 )
                            Event = v71();
                          else
                            Event = -1073741637;
                          if ( Event < 0 || (Event = zzzSetDesktop(ThreadWin32Thread, v68, Handle), Event < 0) )
                          {
                            if ( (_BYTE)v172 )
                            {
                              --*(_DWORD *)(v173 + 28);
                              v173 = 0;
                            }
                            goto LABEL_79;
                          }
                          if ( (_BYTE)v172 )
                            --*(_DWORD *)(v173 + 28);
                          W32GetUserSessionState(v100, v99, v101);
                          if ( *((int *)v177 + 8) >= 0 )
                          {
LABEL_117:
                            v105 = _InterlockedCompareExchange(
                                     (volatile signed __int32 *)(ThreadWin32Thread + 520),
                                     0,
                                     0);
                            v106 = (int)Address;
                            if ( (v105 & 0xC) == 0 && !(_DWORD)Address )
                            {
                              v125 = W32GetUserSessionState(v103, v102, v104);
                              ++*(_DWORD *)(v125 + 70592);
                              if ( (int)IszzzCalcStartCursorHideSupported() >= 0 )
                              {
                                ProcessWin32Process = PsGetProcessWin32Process(Process);
                                v147 = ProcessWin32Process;
                                if ( ProcessWin32Process )
                                  v147 = ((unsigned __int128)-(__int128)*(unsigned __int64 *)ProcessWin32Process >> 64)
                                       & ProcessWin32Process;
                                zzzCalcStartCursorHide(v147, 5000);
                              }
                              if ( !*(_DWORD *)(W32GetUserSessionState(v127, v126, v128) + 70592) )
                              {
                                LODWORD(Address) = 0x20000;
                                MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 1780);
                              }
                              v132 = W32GetUserSessionState(v130, v129, v131);
                              --*(_DWORD *)(v132 + 70592);
                              if ( *(_QWORD *)(W32GetUserSessionState(v134, v133, v135) + 63288) )
                              {
                                if ( !*(_QWORD *)(v24 + 656) )
                                {
                                  UserSetLastError(1003);
                                  goto LABEL_161;
                                }
                              }
                            }
                            ApiSetEditionInitInputHangInfo();
                            v109 = *(_QWORD *)(ThreadWin32Thread + 464);
                            if ( v109 )
                              SetUnavailableInputSource(v109 + 532);
                            if ( (*(_DWORD *)(v24 + 12) & 0x20000) != 0 )
                              _InterlockedOr((volatile signed __int32 *)(ThreadWin32Thread + 520), 0x4000u);
                            _InterlockedOr((volatile signed __int32 *)(ThreadWin32Thread + 520), 0x1000000u);
                            if ( (*(_DWORD *)(v24 + 12) & 0x140) == 0
                              && (*(_BYTE *)(v24 + 808) & 0x30) != 0x10
                              && ((v110 = *(_QWORD *)(W32GetUserSessionState(v109, v107, v108) + 18984)) != 0
                               && *(_QWORD *)(v110 + 456) == v24
                               || (unsigned int)LastWokenThread::Test(v24, 0) == 3) )
                            {
                              tagTHREADINFO::SetForegroundActivate(ThreadWin32Thread, 1);
                            }
                            v112 = *(_QWORD *)(W32GetUserSessionState(v109, v107, v108) + 19704);
                            if ( (*(_DWORD *)v112 & 4) != 0 )
                            {
                              v112 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v112, v111) + 48);
                              v122 = *(__int64 (**)(void))(v112 + 1032);
                              v123 = v122 ? v122() : -1073741637;
                              if ( v123 >= 0 )
                              {
                                v112 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v112, v111) + 48);
                                v124 = *(void (__fastcall **)(_QWORD))(v112 + 1040);
                                if ( v124 )
                                  v124(0);
                              }
                            }
                            if ( !(_DWORD)Self )
                            {
                              v118 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v112, v111) + 48);
                              v119 = *(__int64 (**)(void))(v118 + 1048);
                              Event = v119 ? v119() : -1073741637;
                              if ( Event < 0 )
                                goto LABEL_79;
                              v112 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v118, v117) + 48);
                              v120 = *(__int64 (**)(void))(v112 + 1056);
                              Event = v120 ? v120() : -1073741637;
                              if ( Event < 0 )
                                goto LABEL_79;
                            }
                            if ( !v106 && (*(_DWORD *)(v24 + 12) & 1) == 0 )
                            {
                              v114 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v112, v111) + 48);
                              v115 = *(__int64 (**)(void))(v114 + 1064);
                              if ( v115 )
                                v56 = v115();
                              if ( v56 >= 0 )
                              {
                                v145 = *(void (__fastcall **)(__int64))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(
                                                                                      v114,
                                                                                      v113)
                                                                                  + 48)
                                                                      + 1072LL);
                                if ( v145 )
                                  v145(7);
                              }
                            }
                            if ( v68 )
                            {
                              if ( (v68[12] & 8) != 0 )
                              {
LABEL_161:
                                Event = -1073741823;
                                goto LABEL_79;
                              }
                              if ( v183 == -1 )
                              {
                                v121 = PtiCurrent();
                                KeBugCheckEx(0x164u, 0x12u, (ULONG_PTR)v182, 0, (ULONG_PTR)v121);
                              }
                              PopAndFreeW32ThreadLock(v182);
                              v183 = -1;
                            }
                            v116 = *(_QWORD *)(ThreadWin32Thread + 1360);
                            if ( (v116 & 1) != 0 )
                              *(_QWORD *)(ThreadWin32Thread + 1360) = v116 & 0xFFFFFFFFFFFFFFFEuLL;
                            goto LABEL_86;
                          }
                          if ( !(_DWORD)Address )
                          {
                            if ( !*(_QWORD *)(W32GetUserSessionState(v103, v102, v104) + 63312)
                              || (v164 = *(_QWORD *)(W32GetUserSessionState(v103, v102, v104) + 63312),
                                  PsGetProcessInheritedFromUniqueProcessId(Process) != v164) )
                            {
                              *((_DWORD *)v177 + 8) &= ~0x80000000;
                              goto LABEL_117;
                            }
                            *(_QWORD *)(W32GetUserSessionState(v103, v102, v104) + 62592) = v24;
                            v168 = *(_QWORD *)(W32GetUserSessionState(v166, v165, v167) + 19704);
                            v169 = *(_QWORD *)(v168 + 4960);
                            *(_QWORD *)(W32GetUserSessionState(v168, v170, v171) + 36056) = v169;
                            *(_DWORD *)(v24 + 12) |= 0x200000u;
                            EtwTraceScreenSaverProcessEvent(1);
                            ForegroundBoost::SetForegroundPriority(ThreadWin32Thread, 1, 8);
                            *(_DWORD *)(v24 + 12) |= 0x400000u;
                          }
                          _InterlockedOr((volatile signed __int32 *)(ThreadWin32Thread + 520), 0x2000000u);
                          goto LABEL_117;
                        }
LABEL_79:
                        if ( v68 )
                          Win32RawLockedItemBase<tagDESKTOP,&void UserDereferenceObject(void *),1,1,1>::UnlockWorker((ULONG_PTR)v182);
                        if ( v184 )
                          Win32RawLockedItemBase<DISPLAYCONFIG_DEVICE_INFO_HEADER,&void Win32FreePool(void *),1,1,1>::UnlockWorker((ULONG_PTR)v178);
                        if ( v185 )
                          Win32RawLockedItemBase<DISPLAYCONFIG_DEVICE_INFO_HEADER,&void Win32FreePool(void *),1,1,1>::UnlockWorker((ULONG_PTR)BugCheckParameter2);
                        xxxDestroyThreadInfo();
LABEL_86:
                        Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(v182);
                        Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(v178);
                        Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(BugCheckParameter2);
                        return (unsigned int)Event;
                      }
                    }
                    CloseProtectedHandle(Handle);
                    CloseProtectedHandle(v176);
                    Handle = 0;
                    v176 = 0;
                  }
                }
                else
                {
                  Event = -1073741801;
                }
              }
            }
          }
LABEL_78:
          v68 = 0;
          goto LABEL_79;
        }
        if ( !*(_QWORD *)(W32GetUserSessionState(v35, v34, v36) + 14184) )
        {
          if ( *(_QWORD *)(W32GetUserSessionState(v38, v37, v39) + 14216) )
          {
            v151 = *(_QWORD *)(W32GetUserSessionState(v149, v148, v150) + 14216);
            v155 = W32GetUserSessionState(v153, v152, v154);
            v156 = 1;
          }
          else
          {
            if ( !*(_QWORD *)(W32GetUserSessionState(v149, v148, v150) + 14656) )
              goto LABEL_28;
            v151 = *(_QWORD *)(W32GetUserSessionState(v38, v37, v39) + 14656);
            v155 = W32GetUserSessionState(v158, v157, v159);
            v156 = 0;
          }
          v172 = (char *)(v155 + 14184);
          v173 = v151;
          HMAssignmentLock(&v172, v156);
        }
LABEL_28:
        if ( *(_QWORD *)(W32GetUserSessionState(v38, v37, v39) + 14184) )
        {
          v43 = W32GetUserSessionState(v41, v40, v42);
          if ( (*(_BYTE *)(HMPheFromObject(*(_QWORD *)(v43 + 14184)) + 25) & 1) != 0 )
          {
            LODWORD(Address) = 0x20000;
            MicrosoftTelemetryAssertTriggeredArgsKM("IXPTellMeIf", 0x20000, 1356);
          }
        }
        v172 = (char *)(ThreadWin32Thread + 472);
        v44 = *(_QWORD *)(W32GetUserSessionState(v41, v40, v42) + 14184);
        goto LABEL_32;
      }
    }
  }
  Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(v182);
  Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(v178);
  Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(BugCheckParameter2);
  return 3221225738LL;
}

```

## disassembly

```asm
0x1400d8314  push    rbx
0x1400d8316  push    rsi
0x1400d8317  push    rdi
0x1400d8318  push    r12
0x1400d831a  push    r13
0x1400d831c  push    r14
0x1400d831e  push    r15
0x1400d8320  sub     rsp, 190h
0x1400d8327  mov     r13, rcx
0x1400d832a  call    cs:__imp_PsGetThreadProcess
0x1400d8331  nop     dword ptr [rax+rax+00h]
0x1400d8336  mov     rbx, rax
0x1400d8339  mov     [rsp+1C8h+Process], rax
0x1400d833e  xor     edx, edx; Val
0x1400d8340  lea     r8d, [rdx+48h]; Size
0x1400d8344  lea     rcx, [rsp+1C8h+var_F8]; void *
0x1400d834c  call    memset
0x1400d8351  xor     esi, esi
0x1400d8353  mov     [rsp+1C8h+Handle], rsi
0x1400d835b  mov     [rsp+1C8h+var_168], rsi
0x1400d8360  mov     rax, gs:30h
0x1400d8369  mov     [rsp+1C8h+arg_10], rax
0x1400d8371  lea     rcx, [rsp+1C8h+BugCheckParameter2]
0x1400d8379  call    ??0?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(void)
0x1400d837e  lea     rcx, [rsp+1C8h+var_158]
0x1400d8383  call    ??0?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(void)
0x1400d8388  lea     rcx, [rsp+1C8h+var_128]
0x1400d8390  call    ??0?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(void)
0x1400d8395  xorps   xmm1, xmm1
0x1400d8398  movups  [rsp+1C8h+var_98], xmm1
0x1400d83a0  movups  [rsp+1C8h+var_88], xmm1
0x1400d83a8  movups  [rsp+1C8h+var_78], xmm1
0x1400d83b0  mov     al, byte ptr cs:Microsoft_Windows_Win32kEnableBits+1
0x1400d83b6  test    al, al
0x1400d83b8  jns     short loc_1400D83CD
0x1400d83ba  lea     r8, W32kControlGuid
0x1400d83c1  lea     rdx, InitiateGuiThreadExecution
0x1400d83c8  call    McTemplateK0_EtwWriteTransfer
0x1400d83cd  call    cs:__imp_W32GetUserSessionState
0x1400d83d4  nop     dword ptr [rax+rax+00h]
0x1400d83d9  cmp     [rax+8D88h], esi
0x1400d83df  jnz     loc_1400D9888
0x1400d83e5  call    cs:__imp_PsGetCurrentProcessWin32Process
0x1400d83ec  nop     dword ptr [rax+rax+00h]
0x1400d83f1  test    rax, rax
0x1400d83f4  jz      loc_1400D9888
0x1400d83fa  mov     rcx, [rax]
0x1400d83fd  neg     rcx
0x1400d8400  sbb     rdx, rdx
0x1400d8403  and     rax, rdx
0x1400d8406  test    rax, rax
0x1400d8409  jz      loc_1400D9888
0x1400d840f  mov     [rsp+1C8h+var_108], rsi
0x1400d8417  mov     [rsp+1C8h+var_110], rsi
0x1400d841f  call    cs:__imp_W32GetUserSessionState
0x1400d8426  nop     dword ptr [rax+rax+00h]
0x1400d842b  mov     edi, 1
0x1400d8430  add     [rax+8D90h], edi
0x1400d8436  call    cs:__imp_W32GetUserGdiSessionState
0x1400d843d  nop     dword ptr [rax+rax+00h]
0x1400d8442  mov     r12d, 2000048h
0x1400d8448  cmp     rbx, [rax+28h]
0x1400d844c  cmovnz  r12d, esi
0x1400d8450  mov     rcx, r13
0x1400d8453  call    W32GetThreadWin32Thread
0x1400d8458  mov     r14, rax
0x1400d845b  mov     [rsp+1C8h+BugCheckParameter3], rsi
0x1400d8463  mov     rcx, rbx
0x1400d8466  call    cs:__imp_PsGetProcessPeb
0x1400d846d  nop     dword ptr [rax+rax+00h]
0x1400d8472  mov     [rsp+1C8h+Address], rax
0x1400d847a  mov     [rsp+1C8h+var_A8], 7D0h
0x1400d8486  mov     rcx, [rsp+1C8h+Address]; Address
0x1400d848e  mov     [rsp+1C8h+var_A8], rdi
0x1400d8496  mov     r8d, edi; Alignment
0x1400d8499  mov     edx, edi; Length
0x1400d849b  call    cs:__imp_ProbeForRead
0x1400d84a2  nop     dword ptr [rax+rax+00h]
0x1400d84a7  mov     rax, [rsp+1C8h+Address]
0x1400d84af  mov     rcx, [rax+20h]
0x1400d84b3  mov     [rsp+1C8h+Address], rcx
0x1400d84bb  lea     rax, [rsp+1C8h+var_F8]
0x1400d84c3  mov     [rsp+1C8h+var_160], rax
0x1400d84c8  mov     [rsp+1C8h+var_68], rax
0x1400d84d0  mov     [rsp+1C8h+var_A0], 448h
0x1400d84dc  mov     rcx, [rsp+1C8h+Address]; Address
0x1400d84e4  mov     [rsp+1C8h+var_A0], rdi
0x1400d84ec  mov     r8d, edi; Alignment
0x1400d84ef  mov     edx, edi; Length
0x1400d84f1  call    cs:__imp_ProbeForRead
0x1400d84f8  nop     dword ptr [rax+rax+00h]
0x1400d84fd  mov     rax, [rsp+1C8h+Address]
0x1400d8505  mov     rcx, [rax+20h]
0x1400d8509  mov     [rsp+1C8h+var_F8], rcx
0x1400d8511  mov     rax, [rsp+1C8h+Address]
0x1400d8519  mov     rcx, [rax+28h]
0x1400d851d  mov     [rsp+1C8h+var_F0], rcx
0x1400d8525  mov     rax, [rsp+1C8h+Address]
0x1400d852d  mov     ecx, [rax+88h]
0x1400d8533  mov     [rsp+1C8h+var_E8], ecx
0x1400d853a  mov     rax, [rsp+1C8h+Address]
0x1400d8542  mov     ecx, [rax+8Ch]
0x1400d8548  mov     [rsp+1C8h+var_E4], ecx
0x1400d854f  mov     rax, [rsp+1C8h+Address]
0x1400d8557  mov     ecx, [rax+90h]
0x1400d855d  mov     [rsp+1C8h+var_E0], ecx
0x1400d8564  mov     rax, [rsp+1C8h+Address]
0x1400d856c  mov     ecx, [rax+94h]
0x1400d8572  mov     [rsp+1C8h+var_DC], ecx
0x1400d8579  mov     rax, [rsp+1C8h+Address]
0x1400d8581  mov     ecx, [rax+0A4h]
0x1400d8587  mov     [rsp+1C8h+var_D8], ecx
0x1400d858e  mov     rax, [rsp+1C8h+Address]
0x1400d8596  mov     ecx, [rax+0A8h]
0x1400d859c  mov     [rsp+1C8h+var_D4], ecx
0x1400d85a3  mov     rcx, [rsp+1C8h+Address]
0x1400d85ab  add     rcx, 0C0h
0x1400d85b2  mov     [rsp+1C8h+var_60], rcx
0x1400d85ba  lea     r8, [rsp+1C8h+var_D0]
0x1400d85c2  call    ??$DuplicateUnicodeStringFromUser@$0A@@@YAJV?$UserModePointer@UUSERMODE_UNICODE_STRING@@@@KPEAU_UNICODE_STRING@@@Z; DuplicateUnicodeStringFromUser<0>(UserModePointer<USERMODE_UNICODE_STRING>,ulong,_UNICODE_STRING *)
0x1400d85c7  test    eax, eax
0x1400d85c9  js      loc_1400D86B9
0x1400d85cf  mov     rbx, [rsp+1C8h+BugCheckParameter3]
0x1400d85d7  test    rbx, rbx
0x1400d85da  jnz     loc_1400D8667
0x1400d85e0  lea     rdi, GreDeleteFastMutex
0x1400d85e7  mov     rcx, [rsp+1C8h+Address]
0x1400d85ef  add     rcx, 0D0h
0x1400d85f6  mov     [rsp+1C8h+var_188], rcx
0x1400d85fb  lea     r8, [rsp+1C8h+var_C0]
0x1400d8603  call    ??$DuplicateUnicodeStringFromUser@$0A@@@YAJV?$UserModePointer@UUSERMODE_UNICODE_STRING@@@@KPEAU_UNICODE_STRING@@@Z; DuplicateUnicodeStringFromUser<0>(UserModePointer<USERMODE_UNICODE_STRING>,ulong,_UNICODE_STRING *)
0x1400d8608  test    eax, eax
0x1400d860a  js      loc_1400D86F3
0x1400d8610  mov     rbx, [rsp+1C8h+var_B8]
0x1400d8618  test    rbx, rbx
0x1400d861b  jz      loc_1400D872A
0x1400d8621  mov     [rsp+1C8h+var_110], rbx
0x1400d8629  cmp     [rsp+1C8h+var_148], 0FFFFFFFFFFFFFFFFh
0x1400d8632  jnz     loc_1400D8701
0x1400d8638  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1400d863d  mov     rcx, [rax+178h]
0x1400d8644  mov     [rsp+1C8h+var_158], rcx
0x1400d8649  lea     rcx, [rsp+1C8h+var_158]
0x1400d864e  mov     [rax+178h], rcx
0x1400d8655  mov     [rsp+1C8h+var_150], rbx
0x1400d865a  mov     [rsp+1C8h+var_148], rdi
0x1400d8662  jmp     loc_1400D872A
0x1400d8667  mov     [rsp+1C8h+var_108], rbx
0x1400d866f  cmp     [rsp+1C8h+var_130], 0FFFFFFFFFFFFFFFFh
0x1400d8678  jnz     short loc_1400D86C7
0x1400d867a  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1400d867f  mov     rcx, [rax+178h]
0x1400d8686  mov     [rsp+1C8h+BugCheckParameter2], rcx
0x1400d868e  lea     rcx, [rsp+1C8h+BugCheckParameter2]
0x1400d8696  mov     [rax+178h], rcx
0x1400d869d  mov     [rsp+1C8h+var_138], rbx
0x1400d86a5  lea     rdi, GreDeleteFastMutex
0x1400d86ac  mov     [rsp+1C8h+var_130], rdi
0x1400d86b4  jmp     loc_1400D85E7
0x1400d86b9  mov     ecx, eax; Status
0x1400d86bb  call    cs:__imp_ExRaiseStatus
0x1400d86c7  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1400d86cc  mov     [rsp+1C8h+BugCheckParameter4], rax; BugCheckParameter4
0x1400d86d1  mov     r9, rbx; BugCheckParameter3
0x1400d86d4  lea     r8, [rsp+1C8h+BugCheckParameter2]; BugCheckParameter2
0x1400d86dc  mov     edx, 12h; BugCheckParameter1
0x1400d86e1  mov     ecx, 164h; BugCheckCode
0x1400d86e6  call    cs:__imp_KeBugCheckEx
0x1400d86f3  mov     ecx, eax; Status
0x1400d86f5  call    cs:__imp_ExRaiseStatus
0x1400d8701  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1400d8706  mov     [rsp+1C8h+BugCheckParameter4], rax; BugCheckParameter4
0x1400d870b  mov     r9, rbx; BugCheckParameter3
0x1400d870e  lea     r8, [rsp+1C8h+var_158]; BugCheckParameter2
0x1400d8713  mov     edx, 12h; BugCheckParameter1
0x1400d8718  mov     ecx, 164h; BugCheckCode
0x1400d871d  call    cs:__imp_KeBugCheckEx
0x1400d872a  jmp     short loc_1400D8738
0x1400d872c  mov     edi, eax
0x1400d872e  xor     esi, esi
0x1400d8730  mov     r13d, esi
0x1400d8733  jmp     loc_1400D8CE3
0x1400d8738  call    cs:__imp_PsGetCurrentProcessWin32Process
0x1400d873f  nop     dword ptr [rax+rax+00h]
0x1400d8744  mov     r15, rax
0x1400d8747  test    rax, rax
0x1400d874a  jz      short loc_1400D8758
0x1400d874c  mov     rax, [rax]
0x1400d874f  neg     rax
0x1400d8752  sbb     rcx, rcx
0x1400d8755  and     r15, rcx
0x1400d8758  mov     edi, r12d
0x1400d875b  bts     edi, 8
0x1400d875f  test    byte ptr [r15+0Ch], 80h
0x1400d8764  cmovz   edi, r12d
0x1400d8768  mov     rcx, r13; Thread
0x1400d876b  call    cs:__imp_PsGetThreadProcessId
0x1400d8772  nop     dword ptr [rax+rax+00h]
0x1400d8777  mov     rbx, rax
0x1400d877a  call    cs:__imp_W32GetUserSessionState
0x1400d8781  nop     dword ptr [rax+rax+00h]
0x1400d8786  mov     r13d, edi
0x1400d8789  mov     r12d, 2000000h
0x1400d878f  or      r13d, r12d
0x1400d8792  cmp     [rax+0F750h], rbx
0x1400d8799  cmovnz  r13d, edi
0x1400d879d  lock or [r14+208h], r13d
0x1400d87a5  call    cs:__imp_W32GetUserSessionState
0x1400d87ac  nop     dword ptr [rax+rax+00h]
0x1400d87b1  mov     ecx, [rax+104E8h]
0x1400d87b7  test    cl, cl
0x1400d87b9  js      loc_1400D894B
0x1400d87bf  call    cs:__imp_W32GetUserSessionState
0x1400d87c6  nop     dword ptr [rax+rax+00h]
0x1400d87cb  cmp     [rax+3768h], rsi
0x1400d87d2  jz      loc_1400D948B
0x1400d87d8  call    cs:__imp_W32GetUserSessionState
0x1400d87df  nop     dword ptr [rax+rax+00h]
0x1400d87e4  cmp     [rax+3768h], rsi
0x1400d87eb  jz      short loc_1400D880F
0x1400d87ed  call    cs:__imp_W32GetUserSessionState
0x1400d87f4  nop     dword ptr [rax+rax+00h]
0x1400d87f9  mov     rcx, [rax+3768h]
0x1400d8800  call    _HMPheFromObject
0x1400d8805  test    byte ptr [rax+19h], 1
0x1400d8809  jnz     loc_1400D951F
0x1400d880f  lea     rax, [r14+1D8h]
0x1400d8816  mov     [rsp+1C8h+var_188], rax
0x1400d881b  call    cs:__imp_W32GetUserSessionState
0x1400d8822  nop     dword ptr [rax+rax+00h]
0x1400d8827  mov     rcx, [rax+3768h]
0x1400d882e  mov     [rsp+1C8h+var_180], rcx
0x1400d8833  xor     edx, edx
0x1400d8835  lea     rcx, [rsp+1C8h+var_188]
0x1400d883a  call    HMAssignmentLock
0x1400d883f  lea     rax, [r14+440h]
0x1400d8846  mov     [r14+1E0h], rax
0x1400d884d  test    dword ptr [r15+0Ch], 800000h
0x1400d8855  jnz     loc_1400D9548
0x1400d885b  mov     [r14+1C8h], r15
0x1400d8862  mov     rax, [r15+148h]
0x1400d8869  mov     [r14+2B8h], rax
0x1400d8870  mov     [r15+148h], r14
0x1400d8877  inc     dword ptr [r15+178h]
0x1400d887e  mov     rax, [rsp+1C8h+arg_10]
0x1400d8886  test    rax, rax
0x1400d8889  jnz     loc_1400D891F
0x1400d888f  mov     rax, [rsp+1C8h+arg_10]
0x1400d8897  add     rax, 800h
0x1400d889d  mov     [r14+200h], rax
0x1400d88a4  mov     rcx, [r14+200h]
0x1400d88ab  mov     eax, [r14+188h]
0x1400d88b2  mov     [rcx+0E8h], eax
0x1400d88b8  mov     rax, [r14+200h]
0x1400d88bf  mov     [rax+0ECh], esi
0x1400d88c5  mov     rax, [r14+200h]
0x1400d88cc  add     rax, 0E8h
0x1400d88d2  mov     [r14+190h], rax
0x1400d88d9  mov     rcx, [r14+200h]
0x1400d88e0  mov     eax, [r14+18Ch]
0x1400d88e7  mov     [rcx+0F0h], eax
0x1400d88ed  mov     rax, [r14+200h]
0x1400d88f4  mov     [rax+0F4h], esi
0x1400d88fa  mov     rax, [r14+200h]
0x1400d8901  add     rax, 0F0h
0x1400d8907  mov     [r14+198h], rax
0x1400d890e  jmp     loc_1400D89A6
0x1400d8913  mov     edi, eax
0x1400d8915  xor     esi, esi
0x1400d8917  mov     r13d, esi
0x1400d891a  jmp     loc_1400D8CE3
0x1400d891f  mov     rcx, [r14]; Thread
0x1400d8922  mov     rbx, [rsp+1C8h+arg_10]
0x1400d892a  call    cs:__imp_PsGetThreadId
0x1400d8931  nop     dword ptr [rax+rax+00h]
0x1400d8936  mov     [rbx+78h], rax
0x1400d893a  jmp     loc_1400D888F
0x1400d893f  mov     edi, eax
0x1400d8941  xor     esi, esi
0x1400d8943  mov     r13d, esi
0x1400d8946  jmp     loc_1400D8CE3
0x1400d894b  call    cs:__imp_W32GetUserSessionState
0x1400d8952  nop     dword ptr [rax+rax+00h]
0x1400d8957  cmp     [rax+3788h], rsi
0x1400d895e  jz      short loc_1400D8982
0x1400d8960  call    cs:__imp_W32GetUserSessionState
0x1400d8967  nop     dword ptr [rax+rax+00h]
0x1400d896c  mov     rcx, [rax+3788h]
0x1400d8973  call    _HMPheFromObject
0x1400d8978  test    byte ptr [rax+19h], 1
0x1400d897c  jnz     loc_1400D9462
0x1400d8982  lea     rax, [r14+1D8h]
0x1400d8989  mov     [rsp+1C8h+var_188], rax
0x1400d898e  call    cs:__imp_W32GetUserSessionState
0x1400d8995  nop     dword ptr [rax+rax+00h]
0x1400d899a  mov     rcx, [rax+3788h]
0x1400d89a1  jmp     loc_1400D882E
0x1400d89a6  test    [r15+0Ch], r12d
0x1400d89aa  jnz     loc_1400D9555
0x1400d89b0  cmp     [r14+298h], esi
  ... truncated ...
```
