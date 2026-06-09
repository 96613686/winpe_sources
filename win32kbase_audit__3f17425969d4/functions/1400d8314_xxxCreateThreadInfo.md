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
  __int64 v5; // rcx
  __int64 CurrentProcessWin32Process; // rax
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 UserSessionState; // rax
  __int64 v10; // rcx
  int v11; // r12d
  __int64 ThreadWin32Thread; // r14
  __int64 v13; // rdx
  NTSTATUS v14; // eax
  __int64 v15; // rdx
  __int64 v16; // rcx
  ULONG_PTR v17; // rbx
  NTSTATUS v18; // eax
  ULONG_PTR *v19; // rcx
  ULONG_PTR v20; // rbx
  struct tagTHREADINFO *v21; // rax
  struct tagTHREADINFO *v22; // rax
  struct tagTHREADINFO *BugCheckParameter4; // rax
  struct tagTHREADINFO *v24; // rax
  __int64 v25; // rax
  __int64 v26; // r15
  int v27; // edi
  HANDLE ThreadProcessId; // rbx
  __int64 v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // rdx
  __int64 v32; // rcx
  unsigned int v33; // r13d
  __int64 v34; // rdx
  __int64 v35; // rcx
  __int64 v36; // rdx
  __int64 v37; // rcx
  __int64 v38; // rdx
  __int64 v39; // rcx
  __int64 v40; // rax
  __int64 v41; // rdx
  __int64 v42; // rcx
  __int64 v43; // rcx
  struct _NT_TIB *v44; // rbx
  __int64 v45; // rdx
  __int64 v46; // rcx
  __int64 v47; // rax
  __int64 v48; // rdx
  __int64 v49; // rcx
  __int64 (*v50)(void); // rax
  int v51; // eax
  int v52; // r12d
  HANDLE *v53; // rbx
  NTSTATUS Event; // edi
  PEPROCESS v55; // r13
  int v56; // eax
  __int64 v57; // rdx
  char *v58; // rax
  char *v59; // rbx
  __int64 v60; // rcx
  __int64 v61; // rdx
  __int64 v62; // rcx
  _DWORD *v63; // r13
  __int64 v64; // rcx
  __int64 (*v65)(void); // rax
  __int64 v66; // rcx
  _QWORD *v67; // rdi
  int v68; // ebx
  __int64 v69; // rdx
  __int64 v70; // rcx
  __int64 (__fastcall *v71)(__int64, _QWORD *, HANDLE *, _QWORD, HANDLE *); // rax
  __int64 (*v72)(void); // rax
  unsigned int CurrentProcessId; // eax
  __int64 v74; // r8
  __int64 v76; // rdx
  __int64 v77; // r9
  __int64 v78; // rcx
  __int64 (*v79)(void); // rax
  int v80; // eax
  __int64 (__fastcall *v81)(__int64); // rax
  __int64 v83; // rcx
  __int64 v84; // rcx
  __int64 v85; // rdx
  __int64 v86; // rcx
  __int64 (__fastcall *v87)(__int128 *); // rax
  HANDLE v88; // rbx
  void (*v89)(void); // rax
  __int64 v90; // rdx
  __int64 v91; // rcx
  __int64 v92; // rdx
  __int64 v93; // rcx
  char v94; // al
  int v95; // ebx
  __int64 v96; // rdx
  __int64 v97; // rcx
  __int64 v98; // rcx
  __int64 v99; // rcx
  __int64 (*v100)(void); // rax
  __int64 v101; // rax
  __int64 v102; // rcx
  __int64 (*v103)(void); // rax
  __int64 (*v104)(void); // rax
  struct tagTHREADINFO *v105; // rax
  __int64 (*v106)(void); // rax
  int v107; // eax
  void (__fastcall *v108)(_QWORD); // rax
  __int64 v109; // rax
  __int64 v110; // rdx
  __int64 v111; // rcx
  __int64 v112; // rdx
  __int64 v113; // rcx
  __int64 v114; // rax
  __int64 v115; // rdx
  __int64 v116; // rcx
  __int64 v117; // rdx
  __int64 *v118; // rbx
  __int64 v119; // rdx
  __int64 v120; // rcx
  _QWORD *v121; // r14
  __int64 v122; // rax
  __int64 v123; // rax
  __int64 v124; // rax
  char v125; // al
  void (__fastcall *v126)(__int64); // rax
  __int64 ProcessWin32Process; // rax
  __int64 v128; // rcx
  __int64 v129; // rdx
  __int64 v130; // rcx
  __int64 v131; // rbx
  __int64 v132; // rdx
  __int64 v133; // rcx
  __int64 v134; // rax
  __int64 v135; // rdx
  __int64 v136; // rdx
  __int64 v137; // rcx
  PEPROCESS v138; // rbx
  __int64 ProcessSectionBaseAddress; // rax
  unsigned int v140; // eax
  __int64 v141; // rbx
  __int64 v142; // rdx
  __int64 v143; // rbx
  __int64 v144; // rdx
  __int64 v145; // rcx
  __int64 v146; // rcx
  __int64 v147; // rbx
  __int64 v148; // rdx
  __int64 *v149; // [rsp+40h] [rbp-188h] BYREF
  __int64 v150; // [rsp+48h] [rbp-180h]
  PEPROCESS Process; // [rsp+50h] [rbp-178h]
  PVOID Object; // [rsp+58h] [rbp-170h] BYREF
  HANDLE v153; // [rsp+60h] [rbp-168h] BYREF
  _QWORD *v154; // [rsp+68h] [rbp-160h]
  ULONG_PTR v155[2]; // [rsp+70h] [rbp-158h] BYREF
  void (__fastcall *v156)(_DWORD *, __int64); // [rsp+80h] [rbp-148h]
  ULONG_PTR BugCheckParameter2[2]; // [rsp+88h] [rbp-140h] BYREF
  void (__fastcall *v158)(_DWORD *, __int64); // [rsp+98h] [rbp-130h]
  ULONG_PTR v159[2]; // [rsp+A0h] [rbp-128h] BYREF
  __int64 v160; // [rsp+B0h] [rbp-118h]
  __int64 v161; // [rsp+B8h] [rbp-110h]
  __int64 v162; // [rsp+C0h] [rbp-108h]
  _QWORD v163[12]; // [rsp+D0h] [rbp-F8h] BYREF
  __int128 v164; // [rsp+130h] [rbp-98h] BYREF
  __int128 v165; // [rsp+140h] [rbp-88h]
  __int128 v166; // [rsp+150h] [rbp-78h]
  _QWORD *v167; // [rsp+160h] [rbp-68h]
  char *v168; // [rsp+168h] [rbp-60h]
  volatile void *Address; // [rsp+1D8h] [rbp+10h] BYREF
  struct _NT_TIB *Self; // [rsp+1E0h] [rbp+18h]
  HANDLE Handle; // [rsp+1E8h] [rbp+20h] BYREF

  ThreadProcess = PsGetThreadProcess(Thread);
  Process = ThreadProcess;
  memset(v163, 0, 0x48u);
  Handle = 0;
  v153 = 0;
  Self = KeGetPcr()->NtTib.Self;
  Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>((__int64)BugCheckParameter2);
  Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>((__int64)v155);
  Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>((__int64)v159);
  v164 = 0;
  v165 = 0;
  v166 = 0;
  if ( (Microsoft_Windows_Win32kEnableBits & 0x8000) != 0 )
    McTemplateK0_EtwWriteTransfer(v4, (const EVENT_DESCRIPTOR *)InitiateGuiThreadExecution, &W32kControlGuid);
  if ( !*(_DWORD *)(W32GetUserSessionState(v4, v3) + 36232) )
  {
    CurrentProcessWin32Process = PsGetCurrentProcessWin32Process(v5);
    if ( CurrentProcessWin32Process )
    {
      v7 = -*(_QWORD *)CurrentProcessWin32Process;
      v8 = -(__int64)(*(_QWORD *)CurrentProcessWin32Process != 0);
      if ( (v8 & CurrentProcessWin32Process) != 0 )
      {
        v162 = 0;
        v161 = 0;
        UserSessionState = W32GetUserSessionState(v7, v8);
        ++*(_DWORD *)(UserSessionState + 36240);
        v11 = 33554504;
        if ( ThreadProcess != *(struct _KPROCESS **)(W32GetUserGdiSessionState(v10) + 40) )
          v11 = 0;
        ThreadWin32Thread = W32GetThreadWin32Thread((__int64)Thread);
        v163[6] = 0;
        Address = (volatile void *)PsGetProcessPeb(ThreadProcess);
        v163[10] = 1;
        ProbeForRead(Address, 1u, 1u);
        Address = (volatile void *)*((_QWORD *)Address + 4);
        v154 = v163;
        v167 = v163;
        v163[11] = 1;
        ProbeForRead(Address, 1u, 1u);
        v163[0] = *((_QWORD *)Address + 4);
        v163[1] = *((_QWORD *)Address + 5);
        v163[2] = *((_QWORD *)Address + 17);
        v163[3] = *((_QWORD *)Address + 18);
        v163[4] = *(_QWORD *)((char *)Address + 164);
        v168 = (char *)Address + 192;
        v14 = DuplicateUnicodeStringFromUser<0>((__int64)Address + 192, v13, (__int64)&v163[5]);
        if ( v14 < 0 )
          ExRaiseStatus(v14);
        v17 = v163[6];
        if ( v163[6] )
        {
          v162 = v163[6];
          if ( v158 != (void (__fastcall *)(_DWORD *, __int64))-1LL )
          {
            BugCheckParameter4 = PtiCurrent(v16);
            KeBugCheckEx(0x164u, 0x12u, (ULONG_PTR)BugCheckParameter2, v17, (ULONG_PTR)BugCheckParameter4);
          }
          v22 = PtiCurrent(v16);
          BugCheckParameter2[0] = *((_QWORD *)v22 + 47);
          *((_QWORD *)v22 + 47) = BugCheckParameter2;
          BugCheckParameter2[1] = v17;
          v158 = GreDeleteFastMutex;
        }
        v149 = (__int64 *)((char *)Address + 208);
        v18 = DuplicateUnicodeStringFromUser<0>((__int64)Address + 208, v15, (__int64)&v163[7]);
        if ( v18 < 0 )
          ExRaiseStatus(v18);
        v20 = v163[8];
        if ( v163[8] )
        {
          v161 = v163[8];
          if ( v156 != (void (__fastcall *)(_DWORD *, __int64))-1LL )
          {
            v24 = PtiCurrent((__int64)v19);
            KeBugCheckEx(0x164u, 0x12u, (ULONG_PTR)v155, v20, (ULONG_PTR)v24);
          }
          v21 = PtiCurrent((__int64)v19);
          v155[0] = *((_QWORD *)v21 + 47);
          v19 = v155;
          *((_QWORD *)v21 + 47) = v155;
          v155[1] = v20;
          v156 = GreDeleteFastMutex;
        }
        v25 = PsGetCurrentProcessWin32Process(v19);
        v26 = v25;
        if ( v25 )
          v26 = -(__int64)(*(_QWORD *)v25 != 0) & v25;
        v27 = v11 | 0x100;
        if ( *(char *)(v26 + 12) >= 0 )
          v27 = v11;
        ThreadProcessId = PsGetThreadProcessId(Thread);
        v33 = v27 | 0x2000000;
        if ( *(HANDLE *)(W32GetUserSessionState(v30, v29) + 63312) != ThreadProcessId )
          v33 = v27;
        _InterlockedOr((volatile signed __int32 *)(ThreadWin32Thread + 520), v33);
        v35 = *(unsigned int *)(W32GetUserSessionState(v32, v31) + 66792);
        if ( (v35 & 0x80u) != 0LL )
        {
          if ( *(_QWORD *)(W32GetUserSessionState(v35, v34) + 14216) )
          {
            v47 = W32GetUserSessionState(v46, v45);
            if ( (*(_BYTE *)(HMPheFromObject(*(_DWORD **)(v47 + 14216), v48) + 25) & 1) != 0 )
            {
              LODWORD(Address) = 0x20000;
              MicrosoftTelemetryAssertTriggeredArgsKM("IXPTellMeIf", 0x20000, 1338);
            }
          }
          v149 = (__int64 *)(ThreadWin32Thread + 472);
          v42 = *(_QWORD *)(W32GetUserSessionState(v46, v45) + 14216);
LABEL_32:
          v150 = v42;
          HMAssignmentLock(&v149, 0);
          *(_QWORD *)(ThreadWin32Thread + 480) = ThreadWin32Thread + 1088;
          if ( (*(_DWORD *)(v26 + 12) & 0x800000) != 0 )
            _InterlockedOr((volatile signed __int32 *)(ThreadWin32Thread + 520), 0x2000000u);
          *(_QWORD *)(ThreadWin32Thread + 456) = v26;
          *(_QWORD *)(ThreadWin32Thread + 696) = *(_QWORD *)(v26 + 328);
          *(_QWORD *)(v26 + 328) = ThreadWin32Thread;
          ++*(_DWORD *)(v26 + 376);
          if ( Self )
          {
            v44 = Self;
            v44[2].StackBase = PsGetThreadId(*(PETHREAD *)ThreadWin32Thread);
          }
          *(_QWORD *)(ThreadWin32Thread + 512) = (char *)Self + 2048;
          *(_DWORD *)(*(_QWORD *)(ThreadWin32Thread + 512) + 232LL) = *(_DWORD *)(ThreadWin32Thread + 392);
          *(_DWORD *)(*(_QWORD *)(ThreadWin32Thread + 512) + 236LL) = 0;
          *(_QWORD *)(ThreadWin32Thread + 400) = *(_QWORD *)(ThreadWin32Thread + 512) + 232LL;
          v43 = *(_QWORD *)(ThreadWin32Thread + 512);
          *(_DWORD *)(v43 + 240) = *(_DWORD *)(ThreadWin32Thread + 396);
          *(_DWORD *)(*(_QWORD *)(ThreadWin32Thread + 512) + 244LL) = 0;
          *(_QWORD *)(ThreadWin32Thread + 408) = *(_QWORD *)(ThreadWin32Thread + 512) + 240LL;
          if ( (*(_DWORD *)(v26 + 12) & 0x2000000) != 0 )
            _InterlockedOr((volatile signed __int32 *)(ThreadWin32Thread + 520), 0x20000000u);
          if ( !*(_DWORD *)(ThreadWin32Thread + 664) )
          {
            v138 = Process;
            if ( PsGetProcessPeb(Process) )
            {
              ProcessSectionBaseAddress = PsGetProcessSectionBaseAddress(v138);
              *(_DWORD *)(ThreadWin32Thread + 664) = RtlGetExpWinVer(ProcessSectionBaseAddress);
            }
            else
            {
              *(_DWORD *)(ThreadWin32Thread + 664) = 1536;
            }
          }
          v49 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v43) + 48);
          v50 = *(__int64 (**)(void))(v49 + 896);
          if ( v50 )
          {
            v51 = v50();
            v52 = -1073741637;
          }
          else
          {
            v52 = -1073741637;
            v51 = -1073741637;
          }
          if ( v51 >= 0 )
          {
            v49 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v49) + 48);
            v89 = *(void (**)(void))(v49 + 904);
            if ( v89 )
              v89();
          }
          LODWORD(Self) = v33 & 0xC;
          if ( (v33 & 0xC) == 0 )
          {
            v78 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v49) + 48);
            v79 = *(__int64 (**)(void))(v78 + 912);
            v80 = v79 ? v79() : -1073741637;
            if ( v80 >= 0 )
            {
              v81 = *(__int64 (__fastcall **)(__int64))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v78) + 48) + 920LL);
              if ( v81 ? v81(ThreadWin32Thread) : 0 )
                *(_DWORD *)(v26 + 12) |= 0x1000000u;
            }
          }
          v53 = (HANDLE *)(ThreadWin32Thread + 752);
          Event = ZwCreateEvent((PHANDLE)(ThreadWin32Thread + 752), 0x1F0003u, 0, SynchronizationEvent, 0);
          if ( Event >= 0 )
          {
            Address = 0;
            Event = ObReferenceObjectByHandle(*v53, 0x1F0003u, (POBJECT_TYPE)ExEventObjectType, 1, (PVOID *)&Address, 0);
            *(_QWORD *)(ThreadWin32Thread + 760) = Address;
            if ( Event < 0 )
            {
              if ( Event != -1073741816 )
                ObCloseHandle(*v53, 1);
            }
            else
            {
              LOBYTE(v77) = 1;
              Event = ProtectHandle(*v53, v76, ExEventObjectType, v77);
            }
          }
          if ( Event < 0 )
          {
            *v53 = 0;
          }
          else
          {
            Event = ObDuplicateObject(Process, *v53, Process, ThreadWin32Thread + 1632, 0, 512, 2, 0);
            if ( Event < 0 )
            {
              *(_QWORD *)(ThreadWin32Thread + 1632) = 0;
            }
            else
            {
              v55 = Process;
              Event = InitializeThreadInfoIocp(Process, (struct tagTHREADINFO *)ThreadWin32Thread);
              if ( Event >= 0 )
              {
                v56 = *(_DWORD *)(v26 + 12);
                v57 = 0x4000;
                LODWORD(Address) = v56 & 0x4000;
                *(_DWORD *)(v26 + 12) = v56 | 0x4000;
                if ( !*(_DWORD *)(v26 + 772) && LODWORD(v163[4]) )
                {
                  *(_DWORD *)(v26 + 772) = 28;
                  *(_QWORD *)(v26 + 776) = v163[2];
                  *(_QWORD *)(v26 + 784) = v163[3];
                  *(_DWORD *)(v26 + 792) = v163[4];
                  *(_WORD *)(v26 + 796) = WORD2(v163[4]);
                }
                if ( (v56 & 0x4000) == 0 )
                {
                  if ( (v163[4] & 0x200) != 0 )
                    v140 = v163[0];
                  else
                    v140 = LOWORD(v163[7])
                         ? ParseReserved((const unsigned __int16 *volatile)v163[8], (const unsigned __int16 *)0x4000)
                         : 0;
                  *(_DWORD *)(v26 + 676) = v140;
                  if ( (v154[4] & 0x400) != 0 )
                  {
                    v141 = v154[1];
                    if ( HMValidateSharedHandle(v141, v57) )
                      *(_QWORD *)(v26 + 680) = v141;
                  }
                }
                v58 = AllocQueue(0, 0);
                v59 = v58;
                if ( v58 )
                {
                  tagTHREADINFO::AssignQueue((tagTHREADINFO *)ThreadWin32Thread, (struct tagQ *)v58);
                  *((_QWORD *)v59 + 13) = ThreadWin32Thread;
                  *((_QWORD *)v59 + 12) = ThreadWin32Thread;
                  ApiSetEditionUpdateRawMouseMode(v59);
                  if ( v55 == *(PEPROCESS *)(W32GetUserGdiSessionState(v60) + 40) )
                  {
                    *((_QWORD *)v59 + 68) = 0x2000;
                  }
                  else
                  {
                    *((_DWORD *)v59 + 136) = *(_DWORD *)(*(_QWORD *)(ThreadWin32Thread + 456) + 864LL);
                    *((_DWORD *)v59 + 137) = *(_DWORD *)(*(_QWORD *)(ThreadWin32Thread + 456) + 868LL);
                    v62 = *(unsigned int *)(*(_QWORD *)(ThreadWin32Thread + 456) + 872LL);
                    *((_DWORD *)v59 + 138) = v62;
                  }
                  if ( (_InterlockedCompareExchange((volatile signed __int32 *)(ThreadWin32Thread + 520), 0, 0) & 0xC) != 0
                    || !*(_QWORD *)(W32GetUserSessionState(v62, v61) + 63288) )
                  {
                    v63 = 0;
                    goto LABEL_59;
                  }
                  v153 = 0;
                  v67 = v154;
                  v68 = *((_DWORD *)v154 + 8);
                  v70 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v66) + 48);
                  v71 = *(__int64 (__fastcall **)(__int64, _QWORD *, HANDLE *, _QWORD, HANDLE *))(v70 + 944);
                  if ( v71 )
                    Event = v71(-1, v67 + 5, &v153, v68 & 0x40000000, &Handle);
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
                          v74,
                          CurrentProcessId,
                          Event);
                      Event = -1073741502;
                      goto LABEL_78;
                    }
                    UserSessionSwitchLeaveCritWithNonPaged(v70, v69);
                    ZwTerminateProcess((HANDLE)0xFFFFFFFFFFFFFFFFLL, -1073741205);
                    v121 = (_QWORD *)W32GetUserSessionState(v120, v119);
                    v122 = UserCritInternal::_anonymous_namespace_::EnterCritInternal(
                             v121,
                             1,
                             0,
                             (void (__fastcall *)(_QWORD, __int64))_lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_);
                    v121[2] = v122;
                    if ( v122 )
                    {
                      if ( (_InterlockedCompareExchange((volatile signed __int32 *)(v122 + 520), 0, 0) & 0x1000000) != 0
                        && *(char *)(v122 + 1360) >= 0 )
                      {
                        v123 = PsGetCurrentProcessWin32Process(v122);
                        if ( !v123 )
                          goto LABEL_78;
                        v142 = -(__int64)(*(_QWORD *)v123 != 0);
                        v124 = v142 & v123;
                        if ( !v124 )
                          goto LABEL_78;
                        v125 = *(_BYTE *)(v124 + 1200);
                        if ( v125 != 1 )
                          goto LABEL_78;
                      }
                      else
                      {
                        v125 = 0;
                      }
                      if ( v125 )
                      {
                        while ( 1 )
                        {
                          v118 = (__int64 *)v121[2443];
                          if ( !v118 )
                            break;
                          v121[2443] = v118[2];
                          v118[2] = 0;
                          if ( !*(_DWORD *)(*v118 + 8) )
                          {
                            LODWORD(Address) = 0x20000;
                            MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 4662);
                          }
                          HMUnlockObject(*v118, v142);
                        }
                        DestroyDeferredUnlockObjectAssignmentList(v121 + 2447);
                        DestroyDeferredUnlockObjectAssignmentList(v121 + 2445);
                      }
                    }
                  }
                  else
                  {
                    v72 = *(__int64 (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v70) + 48) + 952LL);
                    if ( v72 )
                      Event = v72();
                    else
                      Event = -1073741637;
                    if ( Event >= 0 )
                    {
                      AtomicExecutionCheck::AtomicExecutionCheck((AtomicExecutionCheck *)&v149);
                      Event = xxxSetProcessWindowStation(v153);
                      if ( (_BYTE)v149 )
                        --*(_DWORD *)(v150 + 28);
                      if ( Event >= 0 )
                      {
                        Object = 0;
                        Event = ObReferenceObjectByHandle(Handle, 0, (POBJECT_TYPE)ExDesktopObjectType, 1, &Object, 0);
                        v63 = Object;
                        if ( Event < 0 )
                          goto LABEL_79;
                        Win32RawLockedNtObject<tagDESKTOP>::ManualLock((ULONG_PTR)v159, (ULONG_PTR)Object);
                        ObfDereferenceObject(v63);
                        LODWORD(v165) = 1;
                        *((_QWORD *)&v165 + 1) = PsGetCurrentProcess(v83);
                        *(_QWORD *)&v166 = v63;
                        *((_QWORD *)&v166 + 1) = 0x100000000LL;
                        v86 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v84) + 48);
                        v87 = *(__int64 (__fastcall **)(__int128 *))(v86 + 968);
                        Event = v87 ? v87(&v164) : -1073741637;
                        if ( Event < 0 )
                          goto LABEL_79;
                        if ( !*(_QWORD *)(v26 + 384) )
                        {
                          v88 = *(HANDLE *)(W32GetUserSessionState(v86, v85) + 63312);
                          if ( PsGetProcessId(Process) != v88 )
                          {
                            LockObjectAssignment((void **)(v26 + 344), v63);
                            *(_QWORD *)(v26 + 384) = Handle;
                          }
                        }
LABEL_59:
                        if ( (unsigned int)InitClientInfo(ThreadWin32Thread) )
                        {
                          AtomicExecutionCheck::AtomicExecutionCheck((AtomicExecutionCheck *)&v149);
                          v65 = *(__int64 (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v64) + 48) + 976LL);
                          if ( v65 )
                            Event = v65();
                          else
                            Event = -1073741637;
                          if ( Event < 0 || (Event = zzzSetDesktop(ThreadWin32Thread, v63, Handle), Event < 0) )
                          {
                            if ( (_BYTE)v149 )
                            {
                              --*(_DWORD *)(v150 + 28);
                              v150 = 0;
                            }
                            goto LABEL_79;
                          }
                          if ( (_BYTE)v149 )
                            --*(_DWORD *)(v150 + 28);
                          W32GetUserSessionState(v91, v90);
                          if ( *((int *)v154 + 8) >= 0 )
                          {
LABEL_117:
                            v94 = _InterlockedCompareExchange(
                                    (volatile signed __int32 *)(ThreadWin32Thread + 520),
                                    0,
                                    0);
                            v95 = (int)Address;
                            if ( (v94 & 0xC) == 0 && !(_DWORD)Address )
                            {
                              v109 = W32GetUserSessionState(v93, v92);
                              ++*(_DWORD *)(v109 + 70592);
                              if ( (int)IszzzCalcStartCursorHideSupported() >= 0 )
                              {
                                ProcessWin32Process = PsGetProcessWin32Process(Process);
                                v128 = ProcessWin32Process;
                                if ( ProcessWin32Process )
                                  v128 = ((unsigned __int128)-(__int128)*(unsigned __int64 *)ProcessWin32Process >> 64)
                                       & ProcessWin32Process;
                                zzzCalcStartCursorHide(v128, 5000);
                              }
                              if ( !*(_DWORD *)(W32GetUserSessionState(v111, v110) + 70592) )
                              {
                                LODWORD(Address) = 0x20000;
                                MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 1780);
                              }
                              v114 = W32GetUserSessionState(v113, v112);
                              --*(_DWORD *)(v114 + 70592);
                              if ( *(_QWORD *)(W32GetUserSessionState(v116, v115) + 63288) )
                              {
                                if ( !*(_QWORD *)(v26 + 656) )
                                {
                                  UserSetLastError(1003, v117);
                                  goto LABEL_161;
                                }
                              }
                            }
                            ApiSetEditionInitInputHangInfo();
                            v97 = *(_QWORD *)(ThreadWin32Thread + 464);
                            if ( v97 )
                              SetUnavailableInputSource(v97 + 532);
                            if ( (*(_DWORD *)(v26 + 12) & 0x20000) != 0 )
                              _InterlockedOr((volatile signed __int32 *)(ThreadWin32Thread + 520), 0x4000u);
                            _InterlockedOr((volatile signed __int32 *)(ThreadWin32Thread + 520), 0x1000000u);
                            if ( (*(_DWORD *)(v26 + 12) & 0x140) == 0
                              && (*(_BYTE *)(v26 + 808) & 0x30) != 0x10
                              && ((v98 = *(_QWORD *)(W32GetUserSessionState(v97, v96) + 18984)) != 0
                               && *(_QWORD *)(v98 + 456) == v26
                               || (unsigned int)LastWokenThread::Test(v26, 0) == 3) )
                            {
                              tagTHREADINFO::SetForegroundActivate(ThreadWin32Thread, 1);
                            }
                            v99 = *(_QWORD *)(W32GetUserSessionState(v97, v96) + 19704);
                            if ( (*(_DWORD *)v99 & 4) != 0 )
                            {
                              v99 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v99) + 48);
                              v106 = *(__int64 (**)(void))(v99 + 1032);
                              v107 = v106 ? v106() : -1073741637;
                              if ( v107 >= 0 )
                              {
                                v99 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v99) + 48);
                                v108 = *(void (__fastcall **)(_QWORD))(v99 + 1040);
                                if ( v108 )
                                  v108(0);
                              }
                            }
                            if ( !(_DWORD)Self )
                            {
                              v102 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v99) + 48);
                              v103 = *(__int64 (**)(void))(v102 + 1048);
                              Event = v103 ? v103() : -1073741637;
                              if ( Event < 0 )
                                goto LABEL_79;
                              v99 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v102) + 48);
                              v104 = *(__int64 (**)(void))(v99 + 1056);
                              Event = v104 ? v104() : -1073741637;
                              if ( Event < 0 )
                                goto LABEL_79;
                            }
                            if ( !v95 && (*(_DWORD *)(v26 + 12) & 1) == 0 )
                            {
                              v99 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v99) + 48);
                              v100 = *(__int64 (**)(void))(v99 + 1064);
                              if ( v100 )
                                v52 = v100();
                              if ( v52 >= 0 )
                              {
                                v99 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v99) + 48);
                                v126 = *(void (__fastcall **)(__int64))(v99 + 1072);
                                if ( v126 )
                                  v126(7);
                              }
                            }
                            if ( v63 )
                            {
                              if ( (v63[12] & 8) != 0 )
                              {
LABEL_161:
                                Event = -1073741823;
                                goto LABEL_79;
                              }
                              if ( v160 == -1 )
                              {
                                v105 = PtiCurrent(v99);
                                KeBugCheckEx(0x164u, 0x12u, (ULONG_PTR)v159, 0, (ULONG_PTR)v105);
                              }
                              PopAndFreeW32ThreadLock((__int64)v159);
                              v160 = -1;
                            }
                            v101 = *(_QWORD *)(ThreadWin32Thread + 1360);
                            if ( (v101 & 1) != 0 )
                              *(_QWORD *)(ThreadWin32Thread + 1360) = v101 & 0xFFFFFFFFFFFFFFFEuLL;
                            goto LABEL_86;
                          }
                          if ( !(_DWORD)Address )
                          {
                            if ( !*(_QWORD *)(W32GetUserSessionState(v93, v92) + 63312)
                              || (v143 = *(_QWORD *)(W32GetUserSessionState(v93, v92) + 63312),
                                  PsGetProcessInheritedFromUniqueProcessId(Process) != v143) )
                            {
                              *((_DWORD *)v154 + 8) &= ~0x80000000;
                              goto LABEL_117;
                            }
                            *(_QWORD *)(W32GetUserSessionState(v93, v92) + 62592) = v26;
                            v146 = *(_QWORD *)(W32GetUserSessionState(v145, v144) + 19704);
                            v147 = *(_QWORD *)(v146 + 4960);
                            *(_QWORD *)(W32GetUserSessionState(v146, v148) + 36056) = v147;
                            *(_DWORD *)(v26 + 12) |= 0x200000u;
                            EtwTraceScreenSaverProcessEvent(1);
                            ForegroundBoost::SetForegroundPriority(ThreadWin32Thread, 1u, 8u);
                            *(_DWORD *)(v26 + 12) |= 0x400000u;
                          }
                          _InterlockedOr((volatile signed __int32 *)(ThreadWin32Thread + 520), 0x2000000u);
                          goto LABEL_117;
                        }
LABEL_79:
                        if ( v63 )
                          Win32RawLockedItemBase<tagDESKTOP,&void UserDereferenceObject(void *),1,1,1>::UnlockWorker((ULONG_PTR)v159);
                        if ( v161 )
                          Win32RawLockedItemBase<DISPLAYCONFIG_DEVICE_INFO_HEADER,&void Win32FreePool(void *),1,1,1>::UnlockWorker(
                            (ULONG_PTR)v155,
                            0);
                        if ( v162 )
                          Win32RawLockedItemBase<DISPLAYCONFIG_DEVICE_INFO_HEADER,&void Win32FreePool(void *),1,1,1>::UnlockWorker(
                            (ULONG_PTR)BugCheckParameter2,
                            0);
                        xxxDestroyThreadInfo();
LABEL_86:
                        Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>((__int64)v159);
                        Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>((__int64)v155);
                        Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>((__int64)BugCheckParameter2);
                        return (unsigned int)Event;
                      }
                    }
                    CloseProtectedHandle(Handle);
                    CloseProtectedHandle(v153);
                    Handle = 0;
                    v153 = 0;
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
          v63 = 0;
          goto LABEL_79;
        }
        if ( !*(_QWORD *)(W32GetUserSessionState(v35, v34) + 14184) )
        {
          if ( *(_QWORD *)(W32GetUserSessionState(v37, v36) + 14216) )
          {
            v131 = *(_QWORD *)(W32GetUserSessionState(v130, v129) + 14216);
            v134 = W32GetUserSessionState(v133, v132);
            v135 = 1;
          }
          else
          {
            if ( !*(_QWORD *)(W32GetUserSessionState(v130, v129) + 14656) )
              goto LABEL_28;
            v131 = *(_QWORD *)(W32GetUserSessionState(v37, v36) + 14656);
            v134 = W32GetUserSessionState(v137, v136);
            v135 = 0;
          }
          v149 = (__int64 *)(v134 + 14184);
          v150 = v131;
          HMAssignmentLock(&v149, v135);
        }
LABEL_28:
        if ( *(_QWORD *)(W32GetUserSessionState(v37, v36) + 14184) )
        {
          v40 = W32GetUserSessionState(v39, v38);
          if ( (*(_BYTE *)(HMPheFromObject(*(_DWORD **)(v40 + 14184), v41) + 25) & 1) != 0 )
          {
            LODWORD(Address) = 0x20000;
            MicrosoftTelemetryAssertTriggeredArgsKM("IXPTellMeIf", 0x20000, 1356);
          }
        }
        v149 = (__int64 *)(ThreadWin32Thread + 472);
        v42 = *(_QWORD *)(W32GetUserSessionState(v39, v38) + 14184);
        goto LABEL_32;
      }
    }
  }
  Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>((__int64)v159);
  Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>((__int64)v155);
  Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>((__int64)BugCheckParameter2);
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
