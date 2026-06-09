# xxxCreateThreadInfo

- ea: `0x14002d824`
- end: `0x14002edc6`
- name: `xxxCreateThreadInfo`
- size: `5538`
- prototype: `__int64 __fastcall(PETHREAD Thread)`
- caller_count: `2`
- callee_count: `45`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14002cf40`
- `0x14009961c`

## callees

- `0x140012c80`
- `0x140029f00`
- `0x140029fe8`
- `0x14002a0e4`
- `0x14002ab14`
- `0x14002d76c`
- `0x14002d798`
- `0x14002d824`
- `0x14002edcc`
- `0x14005c210`
- `0x14005f5b0`
- `0x140073980`
- `0x140073a50`
- `0x140075700`
- `0x1400757c8`
- `0x1400759e0`
- `0x140076ef0`
- `0x14008deb0`
- `0x1400a15c0`
- `0x1400a1690`
- `0x1400aacac`
- `0x1400e0460`
- `0x1400e1970`
- `0x1400f7aa0`
- `0x140111308`
- `0x140111f70`
- `0x14011c664`
- `0x140127ce0`
- `0x14012bdb0`
- `0x14012ff50`
- `0x140133a8c`
- `0x140133bac`
- `0x140133c0c`
- `0x14013981c`
- `0x140148380`
- `0x14014d388`
- `0x140156708`
- `0x140171b74`
- `0x140177bc0`
- `0x140193f58`
- `0x1401aa4fc`
- `0x1401bb040`
- `0x1401c71a4`
- `0x140238bf0`
- `0x140238c40`

## import_xrefs

- `ntoskrnl!PsGetProcessPeb` at `0x14002d976`
- `ntoskrnl!PsGetProcessPeb` at `0x14002ea7e`
- `ntoskrnl!PsGetProcessPeb` at `0x14002d976`
- `ntoskrnl!PsGetProcessPeb` at `0x14002ea7e`
- `ntoskrnl!PsGetCurrentProcess` at `0x14002e3ca`
- `ntoskrnl!PsGetCurrentProcess` at `0x14002e3ca`
- `ntoskrnl!ProbeForRead` at `0x14002d9ab`
- `ntoskrnl!ProbeForRead` at `0x14002da01`
- `ntoskrnl!ProbeForRead` at `0x14002d9ab`
- `ntoskrnl!ProbeForRead` at `0x14002da01`
- `ntoskrnl!KeBugCheckEx` at `0x14002dbf6`
- `ntoskrnl!KeBugCheckEx` at `0x14002dc2d`
- `ntoskrnl!KeBugCheckEx` at `0x14002e711`
- `ntoskrnl!KeBugCheckEx` at `0x14002dbf6`
- `ntoskrnl!KeBugCheckEx` at `0x14002dc2d`
- `ntoskrnl!KeBugCheckEx` at `0x14002e711`
- `ntoskrnl!PsGetThreadProcess` at `0x14002d83a`
- `ntoskrnl!PsGetThreadProcess` at `0x14002d83a`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14002d8f5`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14002dc48`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14002e8c5`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14002d8f5`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14002dc48`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14002e8c5`
- `ntoskrnl!ExRaiseStatus` at `0x14002dbcb`
- `ntoskrnl!ExRaiseStatus` at `0x14002dc05`
- `ntoskrnl!ExRaiseStatus` at `0x14002dbcb`
- `ntoskrnl!ExRaiseStatus` at `0x14002dc05`
- `ntoskrnl!PsGetThreadProcessId` at `0x14002dc7b`
- `ntoskrnl!PsGetThreadProcessId` at `0x14002dc7b`
- `ntoskrnl!PsGetProcessSectionBaseAddress` at `0x14002ea92`
- `ntoskrnl!PsGetProcessSectionBaseAddress` at `0x14002ea92`
- `ntoskrnl!ZwCreateEvent` at `0x14002df33`
- `ntoskrnl!ZwCreateEvent` at `0x14002df33`
- `ntoskrnl!ExEventObjectType` at `0x14002e274`
- `ntoskrnl!ExEventObjectType` at `0x14002e2ac`
- `ntoskrnl!ZwTerminateProcess` at `0x14002e86a`
- `ntoskrnl!ZwTerminateProcess` at `0x14002e86a`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14002e1cf`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14002e1cf`
- `ntoskrnl!ExDesktopObjectType` at `0x14002e371`
- `ntoskrnl!PsGetProcessId` at `0x14002e454`
- `ntoskrnl!PsGetProcessId` at `0x14002e454`
- `ntoskrnl!PsGetProcessInheritedFromUniqueProcessId` at `0x14002ec74`
- `ntoskrnl!PsGetProcessInheritedFromUniqueProcessId` at `0x14002ec74`
- `ntoskrnl!ObCloseHandle` at `0x14002eadb`
- `ntoskrnl!ObCloseHandle` at `0x14002eadb`
- `ntoskrnl!ObDuplicateObject` at `0x14002df7f`
- `ntoskrnl!ObDuplicateObject` at `0x14002df7f`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14002e284`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14002e385`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14002e284`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14002e385`
- `ntoskrnl!ObfDereferenceObject` at `0x14002e3b3`
- `ntoskrnl!ObfDereferenceObject` at `0x14002e3b3`
- `ntoskrnl!PsGetProcessWin32Process` at `0x14002e943`
- `ntoskrnl!PsGetProcessWin32Process` at `0x14002e943`
- `ntoskrnl!PsGetThreadId` at `0x14002de3a`
- `ntoskrnl!PsGetThreadId` at `0x14002de3a`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002decd`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002e05f`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002e121`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002e173`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002e2c5`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002e2f2`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002e3f8`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002e48c`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002e5f7`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002e690`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002e6bf`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002e71e`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002e74b`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002e90f`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002decd`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002e05f`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002e121`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002e173`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002e2c5`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002e2f2`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002e3f8`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002e48c`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002e5f7`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002e690`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002e6bf`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002e71e`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002e74b`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002e90f`
- `WIN32K!W32GetUserGdiSessionState` at `0x14002d946`
- `WIN32K!W32GetUserGdiSessionState` at `0x14002e00e`
- `WIN32K!W32GetUserGdiSessionState` at `0x14002d946`
- `WIN32K!W32GetUserGdiSessionState` at `0x14002e00e`
- `WIN32K!W32GetUserSessionState` at `0x14002d8dd`
- `WIN32K!W32GetUserSessionState` at `0x14002d92f`
- `WIN32K!W32GetUserSessionState` at `0x14002dc8a`
- `WIN32K!W32GetUserSessionState` at `0x14002dcb5`
- `WIN32K!W32GetUserSessionState` at `0x14002dccf`
- `WIN32K!W32GetUserSessionState` at `0x14002dce8`
- `WIN32K!W32GetUserSessionState` at `0x14002dcfd`
- `WIN32K!W32GetUserSessionState` at `0x14002dd2b`
- `WIN32K!W32GetUserSessionState` at `0x14002de5b`
- `WIN32K!W32GetUserSessionState` at `0x14002de70`
- `WIN32K!W32GetUserSessionState` at `0x14002de9e`
- `WIN32K!W32GetUserSessionState` at `0x14002e0fb`
- `WIN32K!W32GetUserSessionState` at `0x14002e43c`
- `WIN32K!W32GetUserSessionState` at `0x14002e50f`
- `WIN32K!W32GetUserSessionState` at `0x14002e589`
- `WIN32K!W32GetUserSessionState` at `0x14002e5c1`
- `WIN32K!W32GetUserSessionState` at `0x14002e77f`
- `WIN32K!W32GetUserSessionState` at `0x14002e79e`
- `WIN32K!W32GetUserSessionState` at `0x14002e7b6`
- `WIN32K!W32GetUserSessionState` at `0x14002e7c8`
- `WIN32K!W32GetUserSessionState` at `0x14002e876`
- `WIN32K!W32GetUserSessionState` at `0x14002e99b`
- `WIN32K!W32GetUserSessionState` at `0x14002e9b0`
- `WIN32K!W32GetUserSessionState` at `0x14002e9c3`
- `WIN32K!W32GetUserSessionState` at `0x14002e9d6`
- `WIN32K!W32GetUserSessionState` at `0x14002e9ef`
- `WIN32K!W32GetUserSessionState` at `0x14002ea02`
- `WIN32K!W32GetUserSessionState` at `0x14002ec43`
- `WIN32K!W32GetUserSessionState` at `0x14002ec5c`
- `WIN32K!W32GetUserSessionState` at `0x14002ec85`
- `WIN32K!W32GetUserSessionState` at `0x14002ec98`
- `WIN32K!W32GetUserSessionState` at `0x14002ecb2`
- `WIN32K!W32GetUserSessionState` at `0x14002d8dd`
- `WIN32K!W32GetUserSessionState` at `0x14002d92f`
- `WIN32K!W32GetUserSessionState` at `0x14002dc8a`
- `WIN32K!W32GetUserSessionState` at `0x14002dcb5`
- `WIN32K!W32GetUserSessionState` at `0x14002dccf`
- `WIN32K!W32GetUserSessionState` at `0x14002dce8`
- `WIN32K!W32GetUserSessionState` at `0x14002dcfd`
- `WIN32K!W32GetUserSessionState` at `0x14002dd2b`
- `WIN32K!W32GetUserSessionState` at `0x14002de5b`
- `WIN32K!W32GetUserSessionState` at `0x14002de70`
- `WIN32K!W32GetUserSessionState` at `0x14002de9e`
- `WIN32K!W32GetUserSessionState` at `0x14002e0fb`
- `WIN32K!W32GetUserSessionState` at `0x14002e43c`
- `WIN32K!W32GetUserSessionState` at `0x14002e50f`
- `WIN32K!W32GetUserSessionState` at `0x14002e589`
- `WIN32K!W32GetUserSessionState` at `0x14002e5c1`
- `WIN32K!W32GetUserSessionState` at `0x14002e77f`
- `WIN32K!W32GetUserSessionState` at `0x14002e79e`
- `WIN32K!W32GetUserSessionState` at `0x14002e7b6`
- `WIN32K!W32GetUserSessionState` at `0x14002e7c8`
- `WIN32K!W32GetUserSessionState` at `0x14002e876`
- `WIN32K!W32GetUserSessionState` at `0x14002e99b`
- `WIN32K!W32GetUserSessionState` at `0x14002e9b0`
- `WIN32K!W32GetUserSessionState` at `0x14002e9c3`
- `WIN32K!W32GetUserSessionState` at `0x14002e9d6`
- `WIN32K!W32GetUserSessionState` at `0x14002e9ef`
- `WIN32K!W32GetUserSessionState` at `0x14002ea02`
- `WIN32K!W32GetUserSessionState` at `0x14002ec43`
- `WIN32K!W32GetUserSessionState` at `0x14002ec5c`
- `WIN32K!W32GetUserSessionState` at `0x14002ec85`
- `WIN32K!W32GetUserSessionState` at `0x14002ec98`
- `WIN32K!W32GetUserSessionState` at `0x14002ecb2`

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
  __int64 v45; // rcx
  struct _NT_TIB *v46; // rbx
  __int64 v47; // rdx
  __int64 v48; // rcx
  __int64 v49; // r8
  __int64 v50; // rax
  __int64 v51; // rcx
  __int64 (*v52)(void); // rax
  int v53; // eax
  int v54; // r12d
  HANDLE *v55; // rbx
  NTSTATUS Event; // edi
  PEPROCESS v57; // r13
  __int64 v58; // r8
  int v59; // eax
  __int64 v60; // rdx
  struct tagQ *v61; // rax
  struct tagQ *v62; // rbx
  __int64 v63; // rdx
  __int64 v64; // rcx
  __int64 v65; // r8
  _DWORD *v66; // r13
  __int64 v67; // rcx
  __int64 (*v68)(void); // rax
  __int64 v69; // rcx
  _QWORD *v70; // rdi
  int v71; // ebx
  __int64 v72; // rcx
  __int64 (__fastcall *v73)(__int64, _QWORD *, HANDLE *, _QWORD, HANDLE *); // rax
  __int64 (*v74)(void); // rax
  unsigned int CurrentProcessId; // eax
  __int64 v76; // r8
  __int64 v78; // rdx
  __int64 v79; // r9
  __int64 v80; // rcx
  __int64 (*v81)(void); // rax
  int v82; // eax
  __int64 (__fastcall *v83)(__int64); // rax
  __int64 v85; // rcx
  __int64 v86; // rdx
  __int64 v87; // rcx
  __int64 v88; // r8
  __int64 (__fastcall *v89)(__int128 *); // rax
  HANDLE v90; // rbx
  void (*v91)(void); // rax
  __int64 v92; // rdx
  __int64 v93; // rcx
  __int64 v94; // r8
  __int64 v95; // rdx
  __int64 v96; // rcx
  __int64 v97; // r8
  char v98; // al
  int v99; // ebx
  __int64 v100; // rdx
  __int64 v101; // r8
  __int64 v102; // rcx
  __int64 v103; // rcx
  __int64 v104; // rcx
  __int64 v105; // rcx
  __int64 (*v106)(void); // rax
  __int64 v107; // rax
  __int64 v108; // rcx
  __int64 (*v109)(void); // rax
  __int64 (*v110)(void); // rax
  struct tagTHREADINFO *v111; // rax
  __int64 (*v112)(void); // rax
  int v113; // eax
  void (__fastcall *v114)(_QWORD); // rax
  __int64 v115; // rax
  __int64 v116; // rdx
  __int64 v117; // rcx
  __int64 v118; // r8
  __int64 v119; // rdx
  __int64 v120; // rcx
  __int64 v121; // r8
  __int64 v122; // rax
  __int64 v123; // rdx
  __int64 v124; // rcx
  __int64 v125; // r8
  _QWORD *v126; // rbx
  __int64 v127; // rdx
  __int64 v128; // rcx
  __int64 v129; // r8
  __int64 v130; // r14
  __int64 v131; // rax
  __int64 v132; // rax
  __int64 v133; // rax
  char v134; // al
  void (__fastcall *v135)(__int64); // rax
  __int64 ProcessWin32Process; // rax
  __int64 v137; // rcx
  __int64 v138; // rdx
  __int64 v139; // rcx
  __int64 v140; // r8
  __int64 v141; // rbx
  __int64 v142; // rdx
  __int64 v143; // rcx
  __int64 v144; // r8
  __int64 v145; // rax
  __int64 v146; // rdx
  __int64 v147; // rdx
  __int64 v148; // rcx
  __int64 v149; // r8
  PEPROCESS v150; // rbx
  __int64 ProcessSectionBaseAddress; // rax
  unsigned int v152; // eax
  __int64 v153; // rbx
  __int64 v154; // rbx
  __int64 v155; // rdx
  __int64 v156; // rcx
  __int64 v157; // r8
  __int64 v158; // rcx
  __int64 v159; // rbx
  __int64 v160; // rdx
  __int64 v161; // r8
  char *v162; // [rsp+40h] [rbp-188h] BYREF
  __int64 v163; // [rsp+48h] [rbp-180h]
  PEPROCESS Process; // [rsp+50h] [rbp-178h]
  PVOID Object; // [rsp+58h] [rbp-170h] BYREF
  HANDLE v166; // [rsp+60h] [rbp-168h] BYREF
  _QWORD *v167; // [rsp+68h] [rbp-160h]
  ULONG_PTR v168[2]; // [rsp+70h] [rbp-158h] BYREF
  __int64 (__fastcall *v169)(PVOID); // [rsp+80h] [rbp-148h]
  ULONG_PTR BugCheckParameter2[2]; // [rsp+88h] [rbp-140h] BYREF
  __int64 (__fastcall *v171)(PVOID); // [rsp+98h] [rbp-130h]
  ULONG_PTR v172[2]; // [rsp+A0h] [rbp-128h] BYREF
  __int64 v173; // [rsp+B0h] [rbp-118h]
  __int64 v174; // [rsp+B8h] [rbp-110h]
  __int64 v175; // [rsp+C0h] [rbp-108h]
  _QWORD v176[12]; // [rsp+D0h] [rbp-F8h] BYREF
  __int128 v177; // [rsp+130h] [rbp-98h] BYREF
  __int128 v178; // [rsp+140h] [rbp-88h]
  __int128 v179; // [rsp+150h] [rbp-78h]
  _QWORD *v180; // [rsp+160h] [rbp-68h]
  char *v181; // [rsp+168h] [rbp-60h]
  volatile void *Address; // [rsp+1D8h] [rbp+10h] BYREF
  struct _NT_TIB *Self; // [rsp+1E0h] [rbp+18h]
  HANDLE Handle; // [rsp+1E8h] [rbp+20h] BYREF

  ThreadProcess = PsGetThreadProcess(Thread);
  Process = ThreadProcess;
  memset(v176, 0, 0x48u);
  Handle = 0;
  v166 = 0;
  Self = KeGetPcr()->NtTib.Self;
  Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(BugCheckParameter2);
  Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(v168);
  Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(v172);
  v177 = 0;
  v178 = 0;
  v179 = 0;
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
        v175 = 0;
        v174 = 0;
        UserSessionState = W32GetUserSessionState(v8, v9, v7);
        ++*(_DWORD *)(UserSessionState + 36240);
        v11 = 33554504;
        if ( ThreadProcess != *(struct _KPROCESS **)(W32GetUserGdiSessionState() + 40) )
          v11 = 0;
        ThreadWin32Thread = W32GetThreadWin32Thread(Thread);
        v176[6] = 0;
        Address = (volatile void *)PsGetProcessPeb(ThreadProcess);
        v176[10] = 1;
        ProbeForRead(Address, 1u, 1u);
        Address = (volatile void *)*((_QWORD *)Address + 4);
        v167 = v176;
        v180 = v176;
        v176[11] = 1;
        ProbeForRead(Address, 1u, 1u);
        v176[0] = *((_QWORD *)Address + 4);
        v176[1] = *((_QWORD *)Address + 5);
        v176[2] = *((_QWORD *)Address + 17);
        v176[3] = *((_QWORD *)Address + 18);
        v176[4] = *(_QWORD *)((char *)Address + 164);
        v181 = (char *)Address + 192;
        v14 = DuplicateUnicodeStringFromUser<0>((char *)Address + 192, v13, &v176[5]);
        if ( v14 < 0 )
          ExRaiseStatus(v14);
        v16 = v176[6];
        if ( v176[6] )
        {
          v175 = v176[6];
          if ( v171 != (__int64 (__fastcall *)(PVOID))-1LL )
          {
            BugCheckParameter4 = PtiCurrent();
            KeBugCheckEx(0x164u, 0x12u, (ULONG_PTR)BugCheckParameter2, v16, (ULONG_PTR)BugCheckParameter4);
          }
          v20 = PtiCurrent();
          BugCheckParameter2[0] = *((_QWORD *)v20 + 47);
          *((_QWORD *)v20 + 47) = BugCheckParameter2;
          BugCheckParameter2[1] = v16;
          v171 = GreDeleteFastMutex;
        }
        v162 = (char *)Address + 208;
        v17 = DuplicateUnicodeStringFromUser<0>((char *)Address + 208, v15, &v176[7]);
        if ( v17 < 0 )
          ExRaiseStatus(v17);
        v18 = v176[8];
        if ( v176[8] )
        {
          v174 = v176[8];
          if ( v169 != (__int64 (__fastcall *)(PVOID))-1LL )
          {
            v22 = PtiCurrent();
            KeBugCheckEx(0x164u, 0x12u, (ULONG_PTR)v168, v18, (ULONG_PTR)v22);
          }
          v19 = PtiCurrent();
          v168[0] = *((_QWORD *)v19 + 47);
          *((_QWORD *)v19 + 47) = v168;
          v168[1] = v18;
          v169 = GreDeleteFastMutex;
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
            v50 = W32GetUserSessionState(v48, v47, v49);
            if ( (*(_BYTE *)(HMPheFromObject(*(_QWORD *)(v50 + 14216)) + 25) & 1) != 0 )
            {
              LODWORD(Address) = 0x20000;
              MicrosoftTelemetryAssertTriggeredArgsKM("IXPTellMeIf", 0x20000, 1338);
            }
          }
          v162 = (char *)(ThreadWin32Thread + 472);
          v44 = *(_QWORD *)(W32GetUserSessionState(v48, v47, v49) + 14216);
LABEL_32:
          v163 = v44;
          HMAssignmentLock(&v162, 0);
          *(_QWORD *)(ThreadWin32Thread + 480) = ThreadWin32Thread + 1088;
          if ( (*(_DWORD *)(v24 + 12) & 0x800000) != 0 )
            _InterlockedOr((volatile signed __int32 *)(ThreadWin32Thread + 520), 0x2000000u);
          *(_QWORD *)(ThreadWin32Thread + 456) = v24;
          *(_QWORD *)(ThreadWin32Thread + 696) = *(_QWORD *)(v24 + 328);
          *(_QWORD *)(v24 + 328) = ThreadWin32Thread;
          ++*(_DWORD *)(v24 + 376);
          if ( Self )
          {
            v46 = Self;
            v46[2].StackBase = PsGetThreadId(*(PETHREAD *)ThreadWin32Thread);
          }
          *(_QWORD *)(ThreadWin32Thread + 512) = (char *)Self + 2048;
          *(_DWORD *)(*(_QWORD *)(ThreadWin32Thread + 512) + 232LL) = *(_DWORD *)(ThreadWin32Thread + 392);
          *(_DWORD *)(*(_QWORD *)(ThreadWin32Thread + 512) + 236LL) = 0;
          *(_QWORD *)(ThreadWin32Thread + 400) = *(_QWORD *)(ThreadWin32Thread + 512) + 232LL;
          v45 = *(_QWORD *)(ThreadWin32Thread + 512);
          *(_DWORD *)(v45 + 240) = *(_DWORD *)(ThreadWin32Thread + 396);
          *(_DWORD *)(*(_QWORD *)(ThreadWin32Thread + 512) + 244LL) = 0;
          *(_QWORD *)(ThreadWin32Thread + 408) = *(_QWORD *)(ThreadWin32Thread + 512) + 240LL;
          if ( (*(_DWORD *)(v24 + 12) & 0x2000000) != 0 )
            _InterlockedOr((volatile signed __int32 *)(ThreadWin32Thread + 520), 0x20000000u);
          if ( !*(_DWORD *)(ThreadWin32Thread + 664) )
          {
            v150 = Process;
            if ( PsGetProcessPeb(Process) )
            {
              ProcessSectionBaseAddress = PsGetProcessSectionBaseAddress(v150);
              *(_DWORD *)(ThreadWin32Thread + 664) = RtlGetExpWinVer(ProcessSectionBaseAddress);
            }
            else
            {
              *(_DWORD *)(ThreadWin32Thread + 664) = 1536;
            }
          }
          v51 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v45) + 48);
          v52 = *(__int64 (**)(void))(v51 + 896);
          if ( v52 )
          {
            v53 = v52();
            v54 = -1073741637;
          }
          else
          {
            v54 = -1073741637;
            v53 = -1073741637;
          }
          if ( v53 >= 0 )
          {
            v51 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v51) + 48);
            v91 = *(void (**)(void))(v51 + 904);
            if ( v91 )
              v91();
          }
          LODWORD(Self) = v33 & 0xC;
          if ( (v33 & 0xC) == 0 )
          {
            v80 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v51) + 48);
            v81 = *(__int64 (**)(void))(v80 + 912);
            v82 = v81 ? v81() : -1073741637;
            if ( v82 >= 0 )
            {
              v83 = *(__int64 (__fastcall **)(__int64))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v80) + 48) + 920LL);
              if ( v83 ? v83(ThreadWin32Thread) : 0 )
                *(_DWORD *)(v24 + 12) |= 0x1000000u;
            }
          }
          v55 = (HANDLE *)(ThreadWin32Thread + 752);
          Event = ZwCreateEvent((PHANDLE)(ThreadWin32Thread + 752), 0x1F0003u, 0, SynchronizationEvent, 0);
          if ( Event >= 0 )
          {
            Address = 0;
            Event = ObReferenceObjectByHandle(*v55, 0x1F0003u, (POBJECT_TYPE)ExEventObjectType, 1, (PVOID *)&Address, 0);
            *(_QWORD *)(ThreadWin32Thread + 760) = Address;
            if ( Event < 0 )
            {
              if ( Event != -1073741816 )
                ObCloseHandle(*v55, 1);
            }
            else
            {
              LOBYTE(v79) = 1;
              Event = ProtectHandle(*v55, v78, ExEventObjectType, v79);
            }
          }
          if ( Event < 0 )
          {
            *v55 = 0;
          }
          else
          {
            Event = ObDuplicateObject(Process, *v55, Process, ThreadWin32Thread + 1632, 0, 512, 2, 0);
            if ( Event < 0 )
            {
              *(_QWORD *)(ThreadWin32Thread + 1632) = 0;
            }
            else
            {
              v57 = Process;
              Event = InitializeThreadInfoIocp(Process, (struct tagTHREADINFO *)ThreadWin32Thread);
              if ( Event >= 0 )
              {
                v59 = *(_DWORD *)(v24 + 12);
                v60 = 0x4000;
                LODWORD(Address) = v59 & 0x4000;
                *(_DWORD *)(v24 + 12) = v59 | 0x4000;
                if ( !*(_DWORD *)(v24 + 772) && LODWORD(v176[4]) )
                {
                  *(_DWORD *)(v24 + 772) = 28;
                  *(_QWORD *)(v24 + 776) = v176[2];
                  *(_QWORD *)(v24 + 784) = v176[3];
                  *(_DWORD *)(v24 + 792) = v176[4];
                  *(_WORD *)(v24 + 796) = WORD2(v176[4]);
                }
                if ( (v59 & 0x4000) == 0 )
                {
                  if ( (v176[4] & 0x200) != 0 )
                    v152 = v176[0];
                  else
                    v152 = LOWORD(v176[7])
                         ? ParseReserved((const unsigned __int16 *volatile)v176[8], (const unsigned __int16 *)0x4000)
                         : 0;
                  *(_DWORD *)(v24 + 676) = v152;
                  if ( (v167[4] & 0x400) != 0 )
                  {
                    v153 = v167[1];
                    if ( HMValidateSharedHandle(v153, v60, v58) )
                      *(_QWORD *)(v24 + 680) = v153;
                  }
                }
                v61 = (struct tagQ *)AllocQueue(0, 0);
                v62 = v61;
                if ( v61 )
                {
                  tagTHREADINFO::AssignQueue((tagTHREADINFO *)ThreadWin32Thread, v61);
                  *((_QWORD *)v62 + 13) = ThreadWin32Thread;
                  *((_QWORD *)v62 + 12) = ThreadWin32Thread;
                  ApiSetEditionUpdateRawMouseMode(v62);
                  if ( v57 == *(PEPROCESS *)(W32GetUserGdiSessionState() + 40) )
                  {
                    *((_QWORD *)v62 + 68) = 0x2000;
                  }
                  else
                  {
                    *((_DWORD *)v62 + 136) = *(_DWORD *)(*(_QWORD *)(ThreadWin32Thread + 456) + 864LL);
                    *((_DWORD *)v62 + 137) = *(_DWORD *)(*(_QWORD *)(ThreadWin32Thread + 456) + 868LL);
                    v64 = *(unsigned int *)(*(_QWORD *)(ThreadWin32Thread + 456) + 872LL);
                    *((_DWORD *)v62 + 138) = v64;
                  }
                  if ( (_InterlockedCompareExchange((volatile signed __int32 *)(ThreadWin32Thread + 520), 0, 0) & 0xC) != 0
                    || !*(_QWORD *)(W32GetUserSessionState(v64, v63, v65) + 63288) )
                  {
                    v66 = 0;
                    goto LABEL_59;
                  }
                  v166 = 0;
                  v70 = v167;
                  v71 = *((_DWORD *)v167 + 8);
                  v72 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v69) + 48);
                  v73 = *(__int64 (__fastcall **)(__int64, _QWORD *, HANDLE *, _QWORD, HANDLE *))(v72 + 944);
                  if ( v73 )
                    Event = v73(-1, v70 + 5, &v166, v71 & 0x40000000, &Handle);
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
                          v76,
                          CurrentProcessId,
                          Event);
                      Event = -1073741502;
                      goto LABEL_78;
                    }
                    UserSessionSwitchLeaveCritWithNonPaged();
                    ZwTerminateProcess((HANDLE)0xFFFFFFFFFFFFFFFFLL, -1073741205);
                    v130 = W32GetUserSessionState(v128, v127, v129);
                    v131 = UserCritInternal::_anonymous_namespace_::EnterCritInternal(
                             v130,
                             1,
                             0,
                             _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_);
                    *(_QWORD *)(v130 + 16) = v131;
                    if ( v131 )
                    {
                      if ( (_InterlockedCompareExchange((volatile signed __int32 *)(v131 + 520), 0, 0) & 0x1000000) != 0
                        && *(char *)(v131 + 1360) >= 0 )
                      {
                        v132 = PsGetCurrentProcessWin32Process();
                        if ( !v132 )
                          goto LABEL_78;
                        v133 = -(__int64)(*(_QWORD *)v132 != 0) & v132;
                        if ( !v133 )
                          goto LABEL_78;
                        v134 = *(_BYTE *)(v133 + 1200);
                        if ( v134 != 1 )
                          goto LABEL_78;
                      }
                      else
                      {
                        v134 = 0;
                      }
                      if ( v134 )
                      {
                        while ( 1 )
                        {
                          v126 = *(_QWORD **)(v130 + 19544);
                          if ( !v126 )
                            break;
                          *(_QWORD *)(v130 + 19544) = v126[2];
                          v126[2] = 0;
                          if ( !*(_DWORD *)(*v126 + 8LL) )
                          {
                            LODWORD(Address) = 0x20000;
                            MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 4662);
                          }
                          HMUnlockObject(*v126);
                        }
                        DestroyDeferredUnlockObjectAssignmentList(v130 + 19576);
                        DestroyDeferredUnlockObjectAssignmentList(v130 + 19560);
                      }
                    }
                  }
                  else
                  {
                    v74 = *(__int64 (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v72) + 48) + 952LL);
                    if ( v74 )
                      Event = v74();
                    else
                      Event = -1073741637;
                    if ( Event >= 0 )
                    {
                      AtomicExecutionCheck::AtomicExecutionCheck((AtomicExecutionCheck *)&v162);
                      Event = xxxSetProcessWindowStation(v166);
                      if ( (_BYTE)v162 )
                        --*(_DWORD *)(v163 + 28);
                      if ( Event >= 0 )
                      {
                        Object = 0;
                        Event = ObReferenceObjectByHandle(Handle, 0, (POBJECT_TYPE)ExDesktopObjectType, 1, &Object, 0);
                        v66 = Object;
                        if ( Event < 0 )
                          goto LABEL_79;
                        Win32RawLockedNtObject<tagDESKTOP>::ManualLock((ULONG_PTR)v172, (ULONG_PTR)Object);
                        ObfDereferenceObject(v66);
                        LODWORD(v178) = 1;
                        *((_QWORD *)&v178 + 1) = PsGetCurrentProcess();
                        *(_QWORD *)&v179 = v66;
                        *((_QWORD *)&v179 + 1) = 0x100000000LL;
                        v87 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v85) + 48);
                        v89 = *(__int64 (__fastcall **)(__int128 *))(v87 + 968);
                        Event = v89 ? v89(&v177) : -1073741637;
                        if ( Event < 0 )
                          goto LABEL_79;
                        if ( !*(_QWORD *)(v24 + 384) )
                        {
                          v90 = *(HANDLE *)(W32GetUserSessionState(v87, v86, v88) + 63312);
                          if ( PsGetProcessId(Process) != v90 )
                          {
                            LockObjectAssignment(v24 + 344, v66);
                            *(_QWORD *)(v24 + 384) = Handle;
                          }
                        }
LABEL_59:
                        if ( (unsigned int)InitClientInfo(ThreadWin32Thread) )
                        {
                          AtomicExecutionCheck::AtomicExecutionCheck((AtomicExecutionCheck *)&v162);
                          v68 = *(__int64 (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v67) + 48) + 976LL);
                          if ( v68 )
                            Event = v68();
                          else
                            Event = -1073741637;
                          if ( Event < 0 || (Event = zzzSetDesktop(ThreadWin32Thread, v66, Handle), Event < 0) )
                          {
                            if ( (_BYTE)v162 )
                            {
                              --*(_DWORD *)(v163 + 28);
                              v163 = 0;
                            }
                            goto LABEL_79;
                          }
                          if ( (_BYTE)v162 )
                            --*(_DWORD *)(v163 + 28);
                          W32GetUserSessionState(v93, v92, v94);
                          if ( *((int *)v167 + 8) >= 0 )
                          {
LABEL_117:
                            v98 = _InterlockedCompareExchange(
                                    (volatile signed __int32 *)(ThreadWin32Thread + 520),
                                    0,
                                    0);
                            v99 = (int)Address;
                            if ( (v98 & 0xC) == 0 && !(_DWORD)Address )
                            {
                              v115 = W32GetUserSessionState(v96, v95, v97);
                              ++*(_DWORD *)(v115 + 70592);
                              if ( (int)IszzzCalcStartCursorHideSupported() >= 0 )
                              {
                                ProcessWin32Process = PsGetProcessWin32Process(Process);
                                v137 = ProcessWin32Process;
                                if ( ProcessWin32Process )
                                  v137 = ((unsigned __int128)-(__int128)*(unsigned __int64 *)ProcessWin32Process >> 64)
                                       & ProcessWin32Process;
                                zzzCalcStartCursorHide(v137, 5000);
                              }
                              if ( !*(_DWORD *)(W32GetUserSessionState(v117, v116, v118) + 70592) )
                              {
                                LODWORD(Address) = 0x20000;
                                MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 1780);
                              }
                              v122 = W32GetUserSessionState(v120, v119, v121);
                              --*(_DWORD *)(v122 + 70592);
                              if ( *(_QWORD *)(W32GetUserSessionState(v124, v123, v125) + 63288) )
                              {
                                if ( !*(_QWORD *)(v24 + 656) )
                                {
                                  UserSetLastError(1003);
                                  goto LABEL_161;
                                }
                              }
                            }
                            ApiSetEditionInitInputHangInfo();
                            v102 = *(_QWORD *)(ThreadWin32Thread + 464);
                            if ( v102 )
                              SetUnavailableInputSource(v102 + 532);
                            if ( (*(_DWORD *)(v24 + 12) & 0x20000) != 0 )
                              _InterlockedOr((volatile signed __int32 *)(ThreadWin32Thread + 520), 0x4000u);
                            _InterlockedOr((volatile signed __int32 *)(ThreadWin32Thread + 520), 0x1000000u);
                            if ( (*(_DWORD *)(v24 + 12) & 0x140) == 0
                              && (*(_BYTE *)(v24 + 808) & 0x30) != 0x10
                              && ((v103 = *(_QWORD *)(W32GetUserSessionState(v102, v100, v101) + 18984)) != 0
                               && *(_QWORD *)(v103 + 456) == v24
                               || (unsigned int)LastWokenThread::Test(v24, 0) == 3) )
                            {
                              tagTHREADINFO::SetForegroundActivate(ThreadWin32Thread, 1);
                            }
                            v104 = *(_QWORD *)(W32GetUserSessionState(v102, v100, v101) + 19704);
                            if ( (*(_DWORD *)v104 & 4) != 0 )
                            {
                              v104 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v104) + 48);
                              v112 = *(__int64 (**)(void))(v104 + 1032);
                              v113 = v112 ? v112() : -1073741637;
                              if ( v113 >= 0 )
                              {
                                v104 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v104) + 48);
                                v114 = *(void (__fastcall **)(_QWORD))(v104 + 1040);
                                if ( v114 )
                                  v114(0);
                              }
                            }
                            if ( !(_DWORD)Self )
                            {
                              v108 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v104) + 48);
                              v109 = *(__int64 (**)(void))(v108 + 1048);
                              Event = v109 ? v109() : -1073741637;
                              if ( Event < 0 )
                                goto LABEL_79;
                              v104 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v108) + 48);
                              v110 = *(__int64 (**)(void))(v104 + 1056);
                              Event = v110 ? v110() : -1073741637;
                              if ( Event < 0 )
                                goto LABEL_79;
                            }
                            if ( !v99 && (*(_DWORD *)(v24 + 12) & 1) == 0 )
                            {
                              v105 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v104) + 48);
                              v106 = *(__int64 (**)(void))(v105 + 1064);
                              if ( v106 )
                                v54 = v106();
                              if ( v54 >= 0 )
                              {
                                v135 = *(void (__fastcall **)(__int64))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v105)
                                                                                  + 48)
                                                                      + 1072LL);
                                if ( v135 )
                                  v135(7);
                              }
                            }
                            if ( v66 )
                            {
                              if ( (v66[12] & 8) != 0 )
                              {
LABEL_161:
                                Event = -1073741823;
                                goto LABEL_79;
                              }
                              if ( v173 == -1 )
                              {
                                v111 = PtiCurrent();
                                KeBugCheckEx(0x164u, 0x12u, (ULONG_PTR)v172, 0, (ULONG_PTR)v111);
                              }
                              PopAndFreeW32ThreadLock(v172);
                              v173 = -1;
                            }
                            v107 = *(_QWORD *)(ThreadWin32Thread + 1360);
                            if ( (v107 & 1) != 0 )
                              *(_QWORD *)(ThreadWin32Thread + 1360) = v107 & 0xFFFFFFFFFFFFFFFEuLL;
                            goto LABEL_86;
                          }
                          if ( !(_DWORD)Address )
                          {
                            if ( !*(_QWORD *)(W32GetUserSessionState(v96, v95, v97) + 63312)
                              || (v154 = *(_QWORD *)(W32GetUserSessionState(v96, v95, v97) + 63312),
                                  PsGetProcessInheritedFromUniqueProcessId(Process) != v154) )
                            {
                              *((_DWORD *)v167 + 8) &= ~0x80000000;
                              goto LABEL_117;
                            }
                            *(_QWORD *)(W32GetUserSessionState(v96, v95, v97) + 62592) = v24;
                            v158 = *(_QWORD *)(W32GetUserSessionState(v156, v155, v157) + 19704);
                            v159 = *(_QWORD *)(v158 + 4960);
                            *(_QWORD *)(W32GetUserSessionState(v158, v160, v161) + 36056) = v159;
                            *(_DWORD *)(v24 + 12) |= 0x200000u;
                            EtwTraceScreenSaverProcessEvent(1);
                            ForegroundBoost::SetForegroundPriority(ThreadWin32Thread, 1, 8);
                            *(_DWORD *)(v24 + 12) |= 0x400000u;
                          }
                          _InterlockedOr((volatile signed __int32 *)(ThreadWin32Thread + 520), 0x2000000u);
                          goto LABEL_117;
                        }
LABEL_79:
                        if ( v66 )
                          Win32RawLockedItemBase<tagDESKTOP,&void UserDereferenceObject(void *),1,1,1>::UnlockWorker((ULONG_PTR)v172);
                        if ( v174 )
                          Win32RawLockedItemBase<DISPLAYCONFIG_DEVICE_INFO_HEADER,&void Win32FreePool(void *),1,1,1>::UnlockWorker((ULONG_PTR)v168);
                        if ( v175 )
                          Win32RawLockedItemBase<DISPLAYCONFIG_DEVICE_INFO_HEADER,&void Win32FreePool(void *),1,1,1>::UnlockWorker((ULONG_PTR)BugCheckParameter2);
                        xxxDestroyThreadInfo();
LABEL_86:
                        Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(v172);
                        Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(v168);
                        Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(BugCheckParameter2);
                        return (unsigned int)Event;
                      }
                    }
                    CloseProtectedHandle(Handle);
                    CloseProtectedHandle(v166);
                    Handle = 0;
                    v166 = 0;
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
          v66 = 0;
          goto LABEL_79;
        }
        if ( !*(_QWORD *)(W32GetUserSessionState(v35, v34, v36) + 14184) )
        {
          if ( *(_QWORD *)(W32GetUserSessionState(v38, v37, v39) + 14216) )
          {
            v141 = *(_QWORD *)(W32GetUserSessionState(v139, v138, v140) + 14216);
            v145 = W32GetUserSessionState(v143, v142, v144);
            v146 = 1;
          }
          else
          {
            if ( !*(_QWORD *)(W32GetUserSessionState(v139, v138, v140) + 14656) )
              goto LABEL_28;
            v141 = *(_QWORD *)(W32GetUserSessionState(v38, v37, v39) + 14656);
            v145 = W32GetUserSessionState(v148, v147, v149);
            v146 = 0;
          }
          v162 = (char *)(v145 + 14184);
          v163 = v141;
          HMAssignmentLock(&v162, v146);
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
        v162 = (char *)(ThreadWin32Thread + 472);
        v44 = *(_QWORD *)(W32GetUserSessionState(v41, v40, v42) + 14184);
        goto LABEL_32;
      }
    }
  }
  Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(v172);
  Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(v168);
  Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(BugCheckParameter2);
  return 3221225738LL;
}

```

## disassembly

```asm
0x14002d824  push    rbx
0x14002d826  push    rsi
0x14002d827  push    rdi
0x14002d828  push    r12
0x14002d82a  push    r13
0x14002d82c  push    r14
0x14002d82e  push    r15
0x14002d830  sub     rsp, 190h
0x14002d837  mov     r13, rcx
0x14002d83a  call    cs:__imp_PsGetThreadProcess
0x14002d841  nop     dword ptr [rax+rax+00h]
0x14002d846  mov     rbx, rax
0x14002d849  mov     [rsp+1C8h+Process], rax
0x14002d84e  xor     edx, edx; Val
0x14002d850  lea     r8d, [rdx+48h]; Size
0x14002d854  lea     rcx, [rsp+1C8h+var_F8]; void *
0x14002d85c  call    memset
0x14002d861  xor     esi, esi
0x14002d863  mov     [rsp+1C8h+Handle], rsi
0x14002d86b  mov     [rsp+1C8h+var_168], rsi
0x14002d870  mov     rax, gs:30h
0x14002d879  mov     [rsp+1C8h+arg_10], rax
0x14002d881  lea     rcx, [rsp+1C8h+BugCheckParameter2]
0x14002d889  call    ??0?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(void)
0x14002d88e  lea     rcx, [rsp+1C8h+var_158]
0x14002d893  call    ??0?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(void)
0x14002d898  lea     rcx, [rsp+1C8h+var_128]
0x14002d8a0  call    ??0?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(void)
0x14002d8a5  xorps   xmm1, xmm1
0x14002d8a8  movups  [rsp+1C8h+var_98], xmm1
0x14002d8b0  movups  [rsp+1C8h+var_88], xmm1
0x14002d8b8  movups  [rsp+1C8h+var_78], xmm1
0x14002d8c0  mov     al, byte ptr cs:Microsoft_Windows_Win32kEnableBits+1
0x14002d8c6  test    al, al
0x14002d8c8  jns     short loc_14002D8DD
0x14002d8ca  lea     r8, W32kControlGuid
0x14002d8d1  lea     rdx, InitiateGuiThreadExecution
0x14002d8d8  call    McTemplateK0_EtwWriteTransfer
0x14002d8dd  call    cs:__imp_W32GetUserSessionState
0x14002d8e4  nop     dword ptr [rax+rax+00h]
0x14002d8e9  cmp     [rax+8D88h], esi
0x14002d8ef  jnz     loc_14002ED98
0x14002d8f5  call    cs:__imp_PsGetCurrentProcessWin32Process
0x14002d8fc  nop     dword ptr [rax+rax+00h]
0x14002d901  test    rax, rax
0x14002d904  jz      loc_14002ED98
0x14002d90a  mov     rcx, [rax]
0x14002d90d  neg     rcx
0x14002d910  sbb     rdx, rdx
0x14002d913  and     rax, rdx
0x14002d916  test    rax, rax
0x14002d919  jz      loc_14002ED98
0x14002d91f  mov     [rsp+1C8h+var_108], rsi
0x14002d927  mov     [rsp+1C8h+var_110], rsi
0x14002d92f  call    cs:__imp_W32GetUserSessionState
0x14002d936  nop     dword ptr [rax+rax+00h]
0x14002d93b  mov     edi, 1
0x14002d940  add     [rax+8D90h], edi
0x14002d946  call    cs:__imp_W32GetUserGdiSessionState
0x14002d94d  nop     dword ptr [rax+rax+00h]
0x14002d952  mov     r12d, 2000048h
0x14002d958  cmp     rbx, [rax+28h]
0x14002d95c  cmovnz  r12d, esi
0x14002d960  mov     rcx, r13
0x14002d963  call    W32GetThreadWin32Thread
0x14002d968  mov     r14, rax
0x14002d96b  mov     [rsp+1C8h+BugCheckParameter3], rsi
0x14002d973  mov     rcx, rbx
0x14002d976  call    cs:__imp_PsGetProcessPeb
0x14002d97d  nop     dword ptr [rax+rax+00h]
0x14002d982  mov     [rsp+1C8h+Address], rax
0x14002d98a  mov     [rsp+1C8h+var_A8], 7D0h
0x14002d996  mov     rcx, [rsp+1C8h+Address]; Address
0x14002d99e  mov     [rsp+1C8h+var_A8], rdi
0x14002d9a6  mov     r8d, edi; Alignment
0x14002d9a9  mov     edx, edi; Length
0x14002d9ab  call    cs:__imp_ProbeForRead
0x14002d9b2  nop     dword ptr [rax+rax+00h]
0x14002d9b7  mov     rax, [rsp+1C8h+Address]
0x14002d9bf  mov     rcx, [rax+20h]
0x14002d9c3  mov     [rsp+1C8h+Address], rcx
0x14002d9cb  lea     rax, [rsp+1C8h+var_F8]
0x14002d9d3  mov     [rsp+1C8h+var_160], rax
0x14002d9d8  mov     [rsp+1C8h+var_68], rax
0x14002d9e0  mov     [rsp+1C8h+var_A0], 450h
0x14002d9ec  mov     rcx, [rsp+1C8h+Address]; Address
0x14002d9f4  mov     [rsp+1C8h+var_A0], rdi
0x14002d9fc  mov     r8d, edi; Alignment
0x14002d9ff  mov     edx, edi; Length
0x14002da01  call    cs:__imp_ProbeForRead
0x14002da08  nop     dword ptr [rax+rax+00h]
0x14002da0d  mov     rax, [rsp+1C8h+Address]
0x14002da15  mov     rcx, [rax+20h]
0x14002da19  mov     [rsp+1C8h+var_F8], rcx
0x14002da21  mov     rax, [rsp+1C8h+Address]
0x14002da29  mov     rcx, [rax+28h]
0x14002da2d  mov     [rsp+1C8h+var_F0], rcx
0x14002da35  mov     rax, [rsp+1C8h+Address]
0x14002da3d  mov     ecx, [rax+88h]
0x14002da43  mov     [rsp+1C8h+var_E8], ecx
0x14002da4a  mov     rax, [rsp+1C8h+Address]
0x14002da52  mov     ecx, [rax+8Ch]
0x14002da58  mov     [rsp+1C8h+var_E4], ecx
0x14002da5f  mov     rax, [rsp+1C8h+Address]
0x14002da67  mov     ecx, [rax+90h]
0x14002da6d  mov     [rsp+1C8h+var_E0], ecx
0x14002da74  mov     rax, [rsp+1C8h+Address]
0x14002da7c  mov     ecx, [rax+94h]
0x14002da82  mov     [rsp+1C8h+var_DC], ecx
0x14002da89  mov     rax, [rsp+1C8h+Address]
0x14002da91  mov     ecx, [rax+0A4h]
0x14002da97  mov     [rsp+1C8h+var_D8], ecx
0x14002da9e  mov     rax, [rsp+1C8h+Address]
0x14002daa6  mov     ecx, [rax+0A8h]
0x14002daac  mov     [rsp+1C8h+var_D4], ecx
0x14002dab3  mov     rcx, [rsp+1C8h+Address]
0x14002dabb  add     rcx, 0C0h
0x14002dac2  mov     [rsp+1C8h+var_60], rcx
0x14002daca  lea     r8, [rsp+1C8h+var_D0]
0x14002dad2  call    ??$DuplicateUnicodeStringFromUser@$0A@@@YAJV?$UserModePointer@UUSERMODE_UNICODE_STRING@@@@KPEAU_UNICODE_STRING@@@Z; DuplicateUnicodeStringFromUser<0>(UserModePointer<USERMODE_UNICODE_STRING>,ulong,_UNICODE_STRING *)
0x14002dad7  test    eax, eax
0x14002dad9  js      loc_14002DBC9
0x14002dadf  mov     rbx, [rsp+1C8h+BugCheckParameter3]
0x14002dae7  test    rbx, rbx
0x14002daea  jnz     loc_14002DB77
0x14002daf0  lea     rdi, GreDeleteFastMutex
0x14002daf7  mov     rcx, [rsp+1C8h+Address]
0x14002daff  add     rcx, 0D0h
0x14002db06  mov     [rsp+1C8h+var_188], rcx
0x14002db0b  lea     r8, [rsp+1C8h+var_C0]
0x14002db13  call    ??$DuplicateUnicodeStringFromUser@$0A@@@YAJV?$UserModePointer@UUSERMODE_UNICODE_STRING@@@@KPEAU_UNICODE_STRING@@@Z; DuplicateUnicodeStringFromUser<0>(UserModePointer<USERMODE_UNICODE_STRING>,ulong,_UNICODE_STRING *)
0x14002db18  test    eax, eax
0x14002db1a  js      loc_14002DC03
0x14002db20  mov     rbx, [rsp+1C8h+var_B8]
0x14002db28  test    rbx, rbx
0x14002db2b  jz      loc_14002DC3A
0x14002db31  mov     [rsp+1C8h+var_110], rbx
0x14002db39  cmp     [rsp+1C8h+var_148], 0FFFFFFFFFFFFFFFFh
0x14002db42  jnz     loc_14002DC11
0x14002db48  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x14002db4d  mov     rcx, [rax+178h]
0x14002db54  mov     [rsp+1C8h+var_158], rcx
0x14002db59  lea     rcx, [rsp+1C8h+var_158]
0x14002db5e  mov     [rax+178h], rcx
0x14002db65  mov     [rsp+1C8h+var_150], rbx
0x14002db6a  mov     [rsp+1C8h+var_148], rdi
0x14002db72  jmp     loc_14002DC3A
0x14002db77  mov     [rsp+1C8h+var_108], rbx
0x14002db7f  cmp     [rsp+1C8h+var_130], 0FFFFFFFFFFFFFFFFh
0x14002db88  jnz     short loc_14002DBD7
0x14002db8a  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x14002db8f  mov     rcx, [rax+178h]
0x14002db96  mov     [rsp+1C8h+BugCheckParameter2], rcx
0x14002db9e  lea     rcx, [rsp+1C8h+BugCheckParameter2]
0x14002dba6  mov     [rax+178h], rcx
0x14002dbad  mov     [rsp+1C8h+var_138], rbx
0x14002dbb5  lea     rdi, GreDeleteFastMutex
0x14002dbbc  mov     [rsp+1C8h+var_130], rdi
0x14002dbc4  jmp     loc_14002DAF7
0x14002dbc9  mov     ecx, eax; Status
0x14002dbcb  call    cs:__imp_ExRaiseStatus
0x14002dbd7  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x14002dbdc  mov     [rsp+1C8h+BugCheckParameter4], rax; BugCheckParameter4
0x14002dbe1  mov     r9, rbx; BugCheckParameter3
0x14002dbe4  lea     r8, [rsp+1C8h+BugCheckParameter2]; BugCheckParameter2
0x14002dbec  mov     edx, 12h; BugCheckParameter1
0x14002dbf1  mov     ecx, 164h; BugCheckCode
0x14002dbf6  call    cs:__imp_KeBugCheckEx
0x14002dc03  mov     ecx, eax; Status
0x14002dc05  call    cs:__imp_ExRaiseStatus
0x14002dc11  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x14002dc16  mov     [rsp+1C8h+BugCheckParameter4], rax; BugCheckParameter4
0x14002dc1b  mov     r9, rbx; BugCheckParameter3
0x14002dc1e  lea     r8, [rsp+1C8h+var_158]; BugCheckParameter2
0x14002dc23  mov     edx, 12h; BugCheckParameter1
0x14002dc28  mov     ecx, 164h; BugCheckCode
0x14002dc2d  call    cs:__imp_KeBugCheckEx
0x14002dc3a  jmp     short loc_14002DC48
0x14002dc3c  mov     edi, eax
0x14002dc3e  xor     esi, esi
0x14002dc40  mov     r13d, esi
0x14002dc43  jmp     loc_14002E1F3
0x14002dc48  call    cs:__imp_PsGetCurrentProcessWin32Process
0x14002dc4f  nop     dword ptr [rax+rax+00h]
0x14002dc54  mov     r15, rax
0x14002dc57  test    rax, rax
0x14002dc5a  jz      short loc_14002DC68
0x14002dc5c  mov     rax, [rax]
0x14002dc5f  neg     rax
0x14002dc62  sbb     rcx, rcx
0x14002dc65  and     r15, rcx
0x14002dc68  mov     edi, r12d
0x14002dc6b  bts     edi, 8
0x14002dc6f  test    byte ptr [r15+0Ch], 80h
0x14002dc74  cmovz   edi, r12d
0x14002dc78  mov     rcx, r13; Thread
0x14002dc7b  call    cs:__imp_PsGetThreadProcessId
0x14002dc82  nop     dword ptr [rax+rax+00h]
0x14002dc87  mov     rbx, rax
0x14002dc8a  call    cs:__imp_W32GetUserSessionState
0x14002dc91  nop     dword ptr [rax+rax+00h]
0x14002dc96  mov     r13d, edi
0x14002dc99  mov     r12d, 2000000h
0x14002dc9f  or      r13d, r12d
0x14002dca2  cmp     [rax+0F750h], rbx
0x14002dca9  cmovnz  r13d, edi
0x14002dcad  lock or [r14+208h], r13d
0x14002dcb5  call    cs:__imp_W32GetUserSessionState
0x14002dcbc  nop     dword ptr [rax+rax+00h]
0x14002dcc1  mov     ecx, [rax+104E8h]
0x14002dcc7  test    cl, cl
0x14002dcc9  js      loc_14002DE5B
0x14002dccf  call    cs:__imp_W32GetUserSessionState
0x14002dcd6  nop     dword ptr [rax+rax+00h]
0x14002dcdb  cmp     [rax+3768h], rsi
0x14002dce2  jz      loc_14002E99B
0x14002dce8  call    cs:__imp_W32GetUserSessionState
0x14002dcef  nop     dword ptr [rax+rax+00h]
0x14002dcf4  cmp     [rax+3768h], rsi
0x14002dcfb  jz      short loc_14002DD1F
0x14002dcfd  call    cs:__imp_W32GetUserSessionState
0x14002dd04  nop     dword ptr [rax+rax+00h]
0x14002dd09  mov     rcx, [rax+3768h]
0x14002dd10  call    _HMPheFromObject
0x14002dd15  test    byte ptr [rax+19h], 1
0x14002dd19  jnz     loc_14002EA2F
0x14002dd1f  lea     rax, [r14+1D8h]
0x14002dd26  mov     [rsp+1C8h+var_188], rax
0x14002dd2b  call    cs:__imp_W32GetUserSessionState
0x14002dd32  nop     dword ptr [rax+rax+00h]
0x14002dd37  mov     rcx, [rax+3768h]
0x14002dd3e  mov     [rsp+1C8h+var_180], rcx
0x14002dd43  xor     edx, edx
0x14002dd45  lea     rcx, [rsp+1C8h+var_188]
0x14002dd4a  call    HMAssignmentLock
0x14002dd4f  lea     rax, [r14+440h]
0x14002dd56  mov     [r14+1E0h], rax
0x14002dd5d  test    dword ptr [r15+0Ch], 800000h
0x14002dd65  jnz     loc_14002EA58
0x14002dd6b  mov     [r14+1C8h], r15
0x14002dd72  mov     rax, [r15+148h]
0x14002dd79  mov     [r14+2B8h], rax
0x14002dd80  mov     [r15+148h], r14
0x14002dd87  inc     dword ptr [r15+178h]
0x14002dd8e  mov     rax, [rsp+1C8h+arg_10]
0x14002dd96  test    rax, rax
0x14002dd99  jnz     loc_14002DE2F
0x14002dd9f  mov     rax, [rsp+1C8h+arg_10]
0x14002dda7  add     rax, 800h
0x14002ddad  mov     [r14+200h], rax
0x14002ddb4  mov     rcx, [r14+200h]
0x14002ddbb  mov     eax, [r14+188h]
0x14002ddc2  mov     [rcx+0E8h], eax
0x14002ddc8  mov     rax, [r14+200h]
0x14002ddcf  mov     [rax+0ECh], esi
0x14002ddd5  mov     rax, [r14+200h]
0x14002dddc  add     rax, 0E8h
0x14002dde2  mov     [r14+190h], rax
0x14002dde9  mov     rcx, [r14+200h]
0x14002ddf0  mov     eax, [r14+18Ch]
0x14002ddf7  mov     [rcx+0F0h], eax
0x14002ddfd  mov     rax, [r14+200h]
0x14002de04  mov     [rax+0F4h], esi
0x14002de0a  mov     rax, [r14+200h]
0x14002de11  add     rax, 0F0h
0x14002de17  mov     [r14+198h], rax
0x14002de1e  jmp     loc_14002DEB6
0x14002de23  mov     edi, eax
0x14002de25  xor     esi, esi
0x14002de27  mov     r13d, esi
0x14002de2a  jmp     loc_14002E1F3
0x14002de2f  mov     rcx, [r14]; Thread
0x14002de32  mov     rbx, [rsp+1C8h+arg_10]
0x14002de3a  call    cs:__imp_PsGetThreadId
0x14002de41  nop     dword ptr [rax+rax+00h]
0x14002de46  mov     [rbx+78h], rax
0x14002de4a  jmp     loc_14002DD9F
0x14002de4f  mov     edi, eax
0x14002de51  xor     esi, esi
0x14002de53  mov     r13d, esi
0x14002de56  jmp     loc_14002E1F3
0x14002de5b  call    cs:__imp_W32GetUserSessionState
0x14002de62  nop     dword ptr [rax+rax+00h]
0x14002de67  cmp     [rax+3788h], rsi
0x14002de6e  jz      short loc_14002DE92
0x14002de70  call    cs:__imp_W32GetUserSessionState
0x14002de77  nop     dword ptr [rax+rax+00h]
0x14002de7c  mov     rcx, [rax+3788h]
0x14002de83  call    _HMPheFromObject
0x14002de88  test    byte ptr [rax+19h], 1
0x14002de8c  jnz     loc_14002E972
0x14002de92  lea     rax, [r14+1D8h]
0x14002de99  mov     [rsp+1C8h+var_188], rax
0x14002de9e  call    cs:__imp_W32GetUserSessionState
0x14002dea5  nop     dword ptr [rax+rax+00h]
0x14002deaa  mov     rcx, [rax+3788h]
0x14002deb1  jmp     loc_14002DD3E
0x14002deb6  test    [r15+0Ch], r12d
0x14002deba  jnz     loc_14002EA65
0x14002dec0  cmp     [r14+298h], esi
  ... truncated ...
```
