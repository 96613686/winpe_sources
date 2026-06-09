# xxxCreateThreadInfo

- ea: `0x140036aa4`
- end: `0x140038046`
- name: `xxxCreateThreadInfo`
- size: `5538`
- prototype: `__int64 __fastcall(PETHREAD Thread)`
- caller_count: `2`
- callee_count: `45`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1400361c0`
- `0x14009041c`

## callees

- `0x140009a60`
- `0x14001bdf0`
- `0x140033180`
- `0x140033268`
- `0x140033364`
- `0x140033d94`
- `0x1400369ec`
- `0x140036a18`
- `0x140036aa4`
- `0x14003804c`
- `0x140074b20`
- `0x140074bf0`
- `0x1400768a0`
- `0x140076968`
- `0x140076b80`
- `0x140078090`
- `0x1400983c0`
- `0x140098490`
- `0x1400a1aac`
- `0x1400cc720`
- `0x1400cfa50`
- `0x1400d67f0`
- `0x1400d7d00`
- `0x1400f59c0`
- `0x140110e44`
- `0x140111aa0`
- `0x14011c9d4`
- `0x140127d40`
- `0x14012c390`
- `0x140130530`
- `0x14013406c`
- `0x14013418c`
- `0x1401341ec`
- `0x140139dfc`
- `0x140147830`
- `0x14014de38`
- `0x140156ec0`
- `0x140172894`
- `0x140178730`
- `0x140194088`
- `0x1401a9f9c`
- `0x1401baae0`
- `0x1401c6c44`
- `0x140238240`
- `0x1402382c0`

## import_xrefs

- `ntoskrnl!PsGetProcessPeb` at `0x140036bf6`
- `ntoskrnl!PsGetProcessPeb` at `0x140037cfe`
- `ntoskrnl!PsGetProcessPeb` at `0x140036bf6`
- `ntoskrnl!PsGetProcessPeb` at `0x140037cfe`
- `ntoskrnl!PsGetCurrentProcess` at `0x14003764a`
- `ntoskrnl!PsGetCurrentProcess` at `0x14003764a`
- `ntoskrnl!ProbeForRead` at `0x140036c2b`
- `ntoskrnl!ProbeForRead` at `0x140036c81`
- `ntoskrnl!ProbeForRead` at `0x140036c2b`
- `ntoskrnl!ProbeForRead` at `0x140036c81`
- `ntoskrnl!KeBugCheckEx` at `0x140036e76`
- `ntoskrnl!KeBugCheckEx` at `0x140036ead`
- `ntoskrnl!KeBugCheckEx` at `0x140037991`
- `ntoskrnl!KeBugCheckEx` at `0x140036e76`
- `ntoskrnl!KeBugCheckEx` at `0x140036ead`
- `ntoskrnl!KeBugCheckEx` at `0x140037991`
- `ntoskrnl!PsGetThreadProcess` at `0x140036aba`
- `ntoskrnl!PsGetThreadProcess` at `0x140036aba`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140036b75`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140036ec8`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140037b45`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140036b75`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140036ec8`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140037b45`
- `ntoskrnl!ExRaiseStatus` at `0x140036e4b`
- `ntoskrnl!ExRaiseStatus` at `0x140036e85`
- `ntoskrnl!ExRaiseStatus` at `0x140036e4b`
- `ntoskrnl!ExRaiseStatus` at `0x140036e85`
- `ntoskrnl!PsGetThreadProcessId` at `0x140036efb`
- `ntoskrnl!PsGetThreadProcessId` at `0x140036efb`
- `ntoskrnl!PsGetProcessSectionBaseAddress` at `0x140037d12`
- `ntoskrnl!PsGetProcessSectionBaseAddress` at `0x140037d12`
- `ntoskrnl!ZwCreateEvent` at `0x1400371b3`
- `ntoskrnl!ZwCreateEvent` at `0x1400371b3`
- `ntoskrnl!ExEventObjectType` at `0x1400374f4`
- `ntoskrnl!ExEventObjectType` at `0x14003752c`
- `ntoskrnl!ZwTerminateProcess` at `0x140037aea`
- `ntoskrnl!ZwTerminateProcess` at `0x140037aea`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14003744f`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14003744f`
- `ntoskrnl!ExDesktopObjectType` at `0x1400375f1`
- `ntoskrnl!PsGetProcessId` at `0x1400376d4`
- `ntoskrnl!PsGetProcessId` at `0x1400376d4`
- `ntoskrnl!PsGetProcessInheritedFromUniqueProcessId` at `0x140037ef4`
- `ntoskrnl!PsGetProcessInheritedFromUniqueProcessId` at `0x140037ef4`
- `ntoskrnl!ObCloseHandle` at `0x140037d5b`
- `ntoskrnl!ObCloseHandle` at `0x140037d5b`
- `ntoskrnl!ObDuplicateObject` at `0x1400371ff`
- `ntoskrnl!ObDuplicateObject` at `0x1400371ff`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140037504`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140037605`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140037504`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140037605`
- `ntoskrnl!ObfDereferenceObject` at `0x140037633`
- `ntoskrnl!ObfDereferenceObject` at `0x140037633`
- `ntoskrnl!PsGetProcessWin32Process` at `0x140037bc3`
- `ntoskrnl!PsGetProcessWin32Process` at `0x140037bc3`
- `ntoskrnl!PsGetThreadId` at `0x1400370ba`
- `ntoskrnl!PsGetThreadId` at `0x1400370ba`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14003714d`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400372df`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400373a1`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400373f3`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140037545`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140037572`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140037678`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14003770c`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140037877`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140037910`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14003793f`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14003799e`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400379cb`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140037b8f`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14003714d`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400372df`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400373a1`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400373f3`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140037545`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140037572`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140037678`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14003770c`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140037877`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140037910`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14003793f`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14003799e`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400379cb`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140037b8f`
- `WIN32K!W32GetUserGdiSessionState` at `0x140036bc6`
- `WIN32K!W32GetUserGdiSessionState` at `0x14003728e`
- `WIN32K!W32GetUserGdiSessionState` at `0x140036bc6`
- `WIN32K!W32GetUserGdiSessionState` at `0x14003728e`
- `WIN32K!W32GetUserSessionState` at `0x140036b5d`
- `WIN32K!W32GetUserSessionState` at `0x140036baf`
- `WIN32K!W32GetUserSessionState` at `0x140036f0a`
- `WIN32K!W32GetUserSessionState` at `0x140036f35`
- `WIN32K!W32GetUserSessionState` at `0x140036f4f`
- `WIN32K!W32GetUserSessionState` at `0x140036f68`
- `WIN32K!W32GetUserSessionState` at `0x140036f7d`
- `WIN32K!W32GetUserSessionState` at `0x140036fab`
- `WIN32K!W32GetUserSessionState` at `0x1400370db`
- `WIN32K!W32GetUserSessionState` at `0x1400370f0`
- `WIN32K!W32GetUserSessionState` at `0x14003711e`
- `WIN32K!W32GetUserSessionState` at `0x14003737b`
- `WIN32K!W32GetUserSessionState` at `0x1400376bc`
- `WIN32K!W32GetUserSessionState` at `0x14003778f`
- `WIN32K!W32GetUserSessionState` at `0x140037809`
- `WIN32K!W32GetUserSessionState` at `0x140037841`
- `WIN32K!W32GetUserSessionState` at `0x1400379ff`
- `WIN32K!W32GetUserSessionState` at `0x140037a1e`
- `WIN32K!W32GetUserSessionState` at `0x140037a36`
- `WIN32K!W32GetUserSessionState` at `0x140037a48`
- `WIN32K!W32GetUserSessionState` at `0x140037af6`
- `WIN32K!W32GetUserSessionState` at `0x140037c1b`
- `WIN32K!W32GetUserSessionState` at `0x140037c30`
- `WIN32K!W32GetUserSessionState` at `0x140037c43`
- `WIN32K!W32GetUserSessionState` at `0x140037c56`
- `WIN32K!W32GetUserSessionState` at `0x140037c6f`
- `WIN32K!W32GetUserSessionState` at `0x140037c82`
- `WIN32K!W32GetUserSessionState` at `0x140037ec3`
- `WIN32K!W32GetUserSessionState` at `0x140037edc`
- `WIN32K!W32GetUserSessionState` at `0x140037f05`
- `WIN32K!W32GetUserSessionState` at `0x140037f18`
- `WIN32K!W32GetUserSessionState` at `0x140037f32`
- `WIN32K!W32GetUserSessionState` at `0x140036b5d`
- `WIN32K!W32GetUserSessionState` at `0x140036baf`
- `WIN32K!W32GetUserSessionState` at `0x140036f0a`
- `WIN32K!W32GetUserSessionState` at `0x140036f35`
- `WIN32K!W32GetUserSessionState` at `0x140036f4f`
- `WIN32K!W32GetUserSessionState` at `0x140036f68`
- `WIN32K!W32GetUserSessionState` at `0x140036f7d`
- `WIN32K!W32GetUserSessionState` at `0x140036fab`
- `WIN32K!W32GetUserSessionState` at `0x1400370db`
- `WIN32K!W32GetUserSessionState` at `0x1400370f0`
- `WIN32K!W32GetUserSessionState` at `0x14003711e`
- `WIN32K!W32GetUserSessionState` at `0x14003737b`
- `WIN32K!W32GetUserSessionState` at `0x1400376bc`
- `WIN32K!W32GetUserSessionState` at `0x14003778f`
- `WIN32K!W32GetUserSessionState` at `0x140037809`
- `WIN32K!W32GetUserSessionState` at `0x140037841`
- `WIN32K!W32GetUserSessionState` at `0x1400379ff`
- `WIN32K!W32GetUserSessionState` at `0x140037a1e`
- `WIN32K!W32GetUserSessionState` at `0x140037a36`
- `WIN32K!W32GetUserSessionState` at `0x140037a48`
- `WIN32K!W32GetUserSessionState` at `0x140037af6`
- `WIN32K!W32GetUserSessionState` at `0x140037c1b`
- `WIN32K!W32GetUserSessionState` at `0x140037c30`
- `WIN32K!W32GetUserSessionState` at `0x140037c43`
- `WIN32K!W32GetUserSessionState` at `0x140037c56`
- `WIN32K!W32GetUserSessionState` at `0x140037c6f`
- `WIN32K!W32GetUserSessionState` at `0x140037c82`
- `WIN32K!W32GetUserSessionState` at `0x140037ec3`
- `WIN32K!W32GetUserSessionState` at `0x140037edc`
- `WIN32K!W32GetUserSessionState` at `0x140037f05`
- `WIN32K!W32GetUserSessionState` at `0x140037f18`
- `WIN32K!W32GetUserSessionState` at `0x140037f32`

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
  struct _NT_TIB *v45; // rbx
  __int64 v46; // rdx
  __int64 v47; // rcx
  __int64 v48; // r8
  __int64 v49; // rax
  __int64 (*v50)(void); // rax
  int v51; // eax
  int v52; // r12d
  HANDLE *v53; // rbx
  NTSTATUS Event; // edi
  PEPROCESS v55; // r13
  int v56; // eax
  struct tagQ *v57; // rax
  struct tagQ *v58; // rbx
  __int64 v59; // rdx
  __int64 v60; // rcx
  __int64 v61; // r8
  _DWORD *v62; // r13
  __int64 (*v63)(void); // rax
  _QWORD *v64; // rdi
  int v65; // ebx
  __int64 (__fastcall *v66)(__int64, _QWORD *, HANDLE *, _QWORD, HANDLE *); // rax
  __int64 (*v67)(void); // rax
  unsigned int CurrentProcessId; // eax
  __int64 v69; // r8
  __int64 v71; // rdx
  __int64 v72; // r9
  __int64 (*v73)(void); // rax
  int v74; // eax
  __int64 (__fastcall *v75)(__int64); // rax
  __int64 v77; // rdx
  __int64 v78; // rcx
  __int64 v79; // r8
  __int64 (__fastcall *v80)(__int128 *); // rax
  HANDLE v81; // rbx
  void (*v82)(void); // rax
  __int64 v83; // rdx
  __int64 v84; // rcx
  __int64 v85; // r8
  __int64 v86; // rdx
  __int64 v87; // rcx
  __int64 v88; // r8
  char v89; // al
  int v90; // ebx
  __int64 v91; // rdx
  __int64 v92; // r8
  __int64 v93; // rcx
  __int64 v94; // rcx
  __int64 (*v95)(void); // rax
  __int64 v96; // rax
  __int64 (*v97)(void); // rax
  __int64 (*v98)(void); // rax
  struct tagTHREADINFO *v99; // rax
  __int64 (*v100)(void); // rax
  int v101; // eax
  void (__fastcall *v102)(_QWORD); // rax
  __int64 v103; // rax
  __int64 v104; // rdx
  __int64 v105; // rcx
  __int64 v106; // r8
  __int64 v107; // rdx
  __int64 v108; // rcx
  __int64 v109; // r8
  __int64 v110; // rax
  __int64 v111; // rdx
  __int64 v112; // rcx
  __int64 v113; // r8
  _QWORD *v114; // rbx
  __int64 v115; // rdx
  __int64 v116; // rcx
  __int64 v117; // r8
  __int64 v118; // r14
  __int64 v119; // rax
  __int64 v120; // rax
  __int64 v121; // rax
  char v122; // al
  void (__fastcall *v123)(__int64); // rax
  __int64 ProcessWin32Process; // rax
  __int64 v125; // rcx
  __int64 v126; // rdx
  __int64 v127; // rcx
  __int64 v128; // r8
  __int64 v129; // rbx
  __int64 v130; // rdx
  __int64 v131; // rcx
  __int64 v132; // r8
  __int64 v133; // rax
  __int64 v134; // rdx
  __int64 v135; // rdx
  __int64 v136; // rcx
  __int64 v137; // r8
  PEPROCESS v138; // rbx
  __int64 ProcessSectionBaseAddress; // rax
  unsigned int v140; // eax
  __int64 v141; // rbx
  __int64 v142; // rbx
  __int64 v143; // rdx
  __int64 v144; // rcx
  __int64 v145; // r8
  __int64 v146; // rcx
  __int64 v147; // rbx
  __int64 v148; // rdx
  __int64 v149; // r8
  char *v150; // [rsp+40h] [rbp-188h] BYREF
  __int64 v151; // [rsp+48h] [rbp-180h]
  PEPROCESS Process; // [rsp+50h] [rbp-178h]
  PVOID Object; // [rsp+58h] [rbp-170h] BYREF
  HANDLE v154; // [rsp+60h] [rbp-168h] BYREF
  _QWORD *v155; // [rsp+68h] [rbp-160h]
  ULONG_PTR v156[2]; // [rsp+70h] [rbp-158h] BYREF
  __int64 (__fastcall *v157)(PVOID); // [rsp+80h] [rbp-148h]
  ULONG_PTR BugCheckParameter2[2]; // [rsp+88h] [rbp-140h] BYREF
  __int64 (__fastcall *v159)(PVOID); // [rsp+98h] [rbp-130h]
  ULONG_PTR v160[2]; // [rsp+A0h] [rbp-128h] BYREF
  __int64 v161; // [rsp+B0h] [rbp-118h]
  __int64 v162; // [rsp+B8h] [rbp-110h]
  __int64 v163; // [rsp+C0h] [rbp-108h]
  _QWORD v164[12]; // [rsp+D0h] [rbp-F8h] BYREF
  __int128 v165; // [rsp+130h] [rbp-98h] BYREF
  __int128 v166; // [rsp+140h] [rbp-88h]
  __int128 v167; // [rsp+150h] [rbp-78h]
  _QWORD *v168; // [rsp+160h] [rbp-68h]
  char *v169; // [rsp+168h] [rbp-60h]
  volatile void *Address; // [rsp+1D8h] [rbp+10h] BYREF
  struct _NT_TIB *Self; // [rsp+1E0h] [rbp+18h]
  HANDLE Handle; // [rsp+1E8h] [rbp+20h] BYREF

  ThreadProcess = PsGetThreadProcess(Thread);
  Process = ThreadProcess;
  memset(v164, 0, 0x48u);
  Handle = 0;
  v154 = 0;
  Self = KeGetPcr()->NtTib.Self;
  Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(BugCheckParameter2);
  Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(v156);
  Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(v160);
  v165 = 0;
  v166 = 0;
  v167 = 0;
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
        v163 = 0;
        v162 = 0;
        UserSessionState = W32GetUserSessionState(v8, v9, v7);
        ++*(_DWORD *)(UserSessionState + 36240);
        v11 = 33554504;
        if ( ThreadProcess != *(struct _KPROCESS **)(W32GetUserGdiSessionState() + 40) )
          v11 = 0;
        ThreadWin32Thread = W32GetThreadWin32Thread(Thread);
        v164[6] = 0;
        Address = (volatile void *)PsGetProcessPeb(ThreadProcess);
        v164[10] = 1;
        ProbeForRead(Address, 1u, 1u);
        Address = (volatile void *)*((_QWORD *)Address + 4);
        v155 = v164;
        v168 = v164;
        v164[11] = 1;
        ProbeForRead(Address, 1u, 1u);
        v164[0] = *((_QWORD *)Address + 4);
        v164[1] = *((_QWORD *)Address + 5);
        v164[2] = *((_QWORD *)Address + 17);
        v164[3] = *((_QWORD *)Address + 18);
        v164[4] = *(_QWORD *)((char *)Address + 164);
        v169 = (char *)Address + 192;
        v14 = DuplicateUnicodeStringFromUser<0>((char *)Address + 192, v13, &v164[5]);
        if ( v14 < 0 )
          ExRaiseStatus(v14);
        v16 = v164[6];
        if ( v164[6] )
        {
          v163 = v164[6];
          if ( v159 != (__int64 (__fastcall *)(PVOID))-1LL )
          {
            BugCheckParameter4 = PtiCurrent();
            KeBugCheckEx(0x164u, 0x12u, (ULONG_PTR)BugCheckParameter2, v16, (ULONG_PTR)BugCheckParameter4);
          }
          v20 = PtiCurrent();
          BugCheckParameter2[0] = *((_QWORD *)v20 + 47);
          *((_QWORD *)v20 + 47) = BugCheckParameter2;
          BugCheckParameter2[1] = v16;
          v159 = GreDeleteFastMutex;
        }
        v150 = (char *)Address + 208;
        v17 = DuplicateUnicodeStringFromUser<0>((char *)Address + 208, v15, &v164[7]);
        if ( v17 < 0 )
          ExRaiseStatus(v17);
        v18 = v164[8];
        if ( v164[8] )
        {
          v162 = v164[8];
          if ( v157 != (__int64 (__fastcall *)(PVOID))-1LL )
          {
            v22 = PtiCurrent();
            KeBugCheckEx(0x164u, 0x12u, (ULONG_PTR)v156, v18, (ULONG_PTR)v22);
          }
          v19 = PtiCurrent();
          v156[0] = *((_QWORD *)v19 + 47);
          *((_QWORD *)v19 + 47) = v156;
          v156[1] = v18;
          v157 = GreDeleteFastMutex;
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
            v49 = W32GetUserSessionState(v47, v46, v48);
            if ( (*(_BYTE *)(HMPheFromObject(*(_QWORD *)(v49 + 14216)) + 25) & 1) != 0 )
            {
              LODWORD(Address) = 0x20000;
              MicrosoftTelemetryAssertTriggeredArgsKM("IXPTellMeIf", 0x20000, 1338);
            }
          }
          v150 = (char *)(ThreadWin32Thread + 472);
          v44 = *(_QWORD *)(W32GetUserSessionState(v47, v46, v48) + 14216);
LABEL_32:
          v151 = v44;
          HMAssignmentLock(&v150, 0);
          *(_QWORD *)(ThreadWin32Thread + 480) = ThreadWin32Thread + 1088;
          if ( (*(_DWORD *)(v24 + 12) & 0x800000) != 0 )
            _InterlockedOr((volatile signed __int32 *)(ThreadWin32Thread + 520), 0x2000000u);
          *(_QWORD *)(ThreadWin32Thread + 456) = v24;
          *(_QWORD *)(ThreadWin32Thread + 696) = *(_QWORD *)(v24 + 328);
          *(_QWORD *)(v24 + 328) = ThreadWin32Thread;
          ++*(_DWORD *)(v24 + 376);
          if ( Self )
          {
            v45 = Self;
            v45[2].StackBase = PsGetThreadId(*(PETHREAD *)ThreadWin32Thread);
          }
          *(_QWORD *)(ThreadWin32Thread + 512) = (char *)Self + 2048;
          *(_DWORD *)(*(_QWORD *)(ThreadWin32Thread + 512) + 232LL) = *(_DWORD *)(ThreadWin32Thread + 392);
          *(_DWORD *)(*(_QWORD *)(ThreadWin32Thread + 512) + 236LL) = 0;
          *(_QWORD *)(ThreadWin32Thread + 400) = *(_QWORD *)(ThreadWin32Thread + 512) + 232LL;
          *(_DWORD *)(*(_QWORD *)(ThreadWin32Thread + 512) + 240LL) = *(_DWORD *)(ThreadWin32Thread + 396);
          *(_DWORD *)(*(_QWORD *)(ThreadWin32Thread + 512) + 244LL) = 0;
          *(_QWORD *)(ThreadWin32Thread + 408) = *(_QWORD *)(ThreadWin32Thread + 512) + 240LL;
          if ( (*(_DWORD *)(v24 + 12) & 0x2000000) != 0 )
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
          v50 = *(__int64 (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable() + 48) + 896LL);
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
            v82 = *(void (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable() + 48) + 904LL);
            if ( v82 )
              v82();
          }
          LODWORD(Self) = v33 & 0xC;
          if ( (v33 & 0xC) == 0 )
          {
            v73 = *(__int64 (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable() + 48) + 912LL);
            v74 = v73 ? v73() : -1073741637;
            if ( v74 >= 0 )
            {
              v75 = *(__int64 (__fastcall **)(__int64))(*(_QWORD *)(W32GetWin32kBaseApiSetTable() + 48) + 920LL);
              if ( v75 ? v75(ThreadWin32Thread) : 0 )
                *(_DWORD *)(v24 + 12) |= 0x1000000u;
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
              LOBYTE(v72) = 1;
              Event = ProtectHandle(*v53, v71, ExEventObjectType, v72);
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
                v56 = *(_DWORD *)(v24 + 12);
                LODWORD(Address) = v56 & 0x4000;
                *(_DWORD *)(v24 + 12) = v56 | 0x4000;
                if ( !*(_DWORD *)(v24 + 772) && LODWORD(v164[4]) )
                {
                  *(_DWORD *)(v24 + 772) = 28;
                  *(_QWORD *)(v24 + 776) = v164[2];
                  *(_QWORD *)(v24 + 784) = v164[3];
                  *(_DWORD *)(v24 + 792) = v164[4];
                  *(_WORD *)(v24 + 796) = WORD2(v164[4]);
                }
                if ( (v56 & 0x4000) == 0 )
                {
                  if ( (v164[4] & 0x200) != 0 )
                    v140 = v164[0];
                  else
                    v140 = LOWORD(v164[7])
                         ? ParseReserved((const unsigned __int16 *volatile)v164[8], (const unsigned __int16 *)0x4000)
                         : 0;
                  *(_DWORD *)(v24 + 676) = v140;
                  if ( (v155[4] & 0x400) != 0 )
                  {
                    v141 = v155[1];
                    if ( HMValidateSharedHandle(v141) )
                      *(_QWORD *)(v24 + 680) = v141;
                  }
                }
                v57 = (struct tagQ *)AllocQueue(0, 0);
                v58 = v57;
                if ( v57 )
                {
                  tagTHREADINFO::AssignQueue((tagTHREADINFO *)ThreadWin32Thread, v57);
                  *((_QWORD *)v58 + 13) = ThreadWin32Thread;
                  *((_QWORD *)v58 + 12) = ThreadWin32Thread;
                  ApiSetEditionUpdateRawMouseMode(v58);
                  if ( v55 == *(PEPROCESS *)(W32GetUserGdiSessionState() + 40) )
                  {
                    *((_QWORD *)v58 + 68) = 0x2000;
                  }
                  else
                  {
                    *((_DWORD *)v58 + 136) = *(_DWORD *)(*(_QWORD *)(ThreadWin32Thread + 456) + 864LL);
                    *((_DWORD *)v58 + 137) = *(_DWORD *)(*(_QWORD *)(ThreadWin32Thread + 456) + 868LL);
                    v60 = *(unsigned int *)(*(_QWORD *)(ThreadWin32Thread + 456) + 872LL);
                    *((_DWORD *)v58 + 138) = v60;
                  }
                  if ( (_InterlockedCompareExchange((volatile signed __int32 *)(ThreadWin32Thread + 520), 0, 0) & 0xC) != 0
                    || !*(_QWORD *)(W32GetUserSessionState(v60, v59, v61) + 63288) )
                  {
                    v62 = 0;
                    goto LABEL_59;
                  }
                  v154 = 0;
                  v64 = v155;
                  v65 = *((_DWORD *)v155 + 8);
                  v66 = *(__int64 (__fastcall **)(__int64, _QWORD *, HANDLE *, _QWORD, HANDLE *))(*(_QWORD *)(W32GetWin32kBaseApiSetTable() + 48)
                                                                                                + 944LL);
                  if ( v66 )
                    Event = v66(-1, v64 + 5, &v154, v65 & 0x40000000, &Handle);
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
                          v69,
                          CurrentProcessId,
                          Event);
                      Event = -1073741502;
                      goto LABEL_78;
                    }
                    UserSessionSwitchLeaveCritWithNonPaged();
                    ZwTerminateProcess((HANDLE)0xFFFFFFFFFFFFFFFFLL, -1073741205);
                    v118 = W32GetUserSessionState(v116, v115, v117);
                    v119 = UserCritInternal::_anonymous_namespace_::EnterCritInternal(
                             v118,
                             1,
                             0,
                             _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_);
                    *(_QWORD *)(v118 + 16) = v119;
                    if ( v119 )
                    {
                      if ( (_InterlockedCompareExchange((volatile signed __int32 *)(v119 + 520), 0, 0) & 0x1000000) != 0
                        && *(char *)(v119 + 1360) >= 0 )
                      {
                        v120 = PsGetCurrentProcessWin32Process();
                        if ( !v120 )
                          goto LABEL_78;
                        v121 = -(__int64)(*(_QWORD *)v120 != 0) & v120;
                        if ( !v121 )
                          goto LABEL_78;
                        v122 = *(_BYTE *)(v121 + 1200);
                        if ( v122 != 1 )
                          goto LABEL_78;
                      }
                      else
                      {
                        v122 = 0;
                      }
                      if ( v122 )
                      {
                        while ( 1 )
                        {
                          v114 = *(_QWORD **)(v118 + 19544);
                          if ( !v114 )
                            break;
                          *(_QWORD *)(v118 + 19544) = v114[2];
                          v114[2] = 0;
                          if ( !*(_DWORD *)(*v114 + 8LL) )
                          {
                            LODWORD(Address) = 0x20000;
                            MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 4662);
                          }
                          HMUnlockObject(*v114);
                        }
                        DestroyDeferredUnlockObjectAssignmentList(v118 + 19576);
                        DestroyDeferredUnlockObjectAssignmentList(v118 + 19560);
                      }
                    }
                  }
                  else
                  {
                    v67 = *(__int64 (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable() + 48) + 952LL);
                    if ( v67 )
                      Event = v67();
                    else
                      Event = -1073741637;
                    if ( Event >= 0 )
                    {
                      AtomicExecutionCheck::AtomicExecutionCheck((AtomicExecutionCheck *)&v150);
                      Event = xxxSetProcessWindowStation(v154);
                      if ( (_BYTE)v150 )
                        --*(_DWORD *)(v151 + 28);
                      if ( Event >= 0 )
                      {
                        Object = 0;
                        Event = ObReferenceObjectByHandle(Handle, 0, (POBJECT_TYPE)ExDesktopObjectType, 1, &Object, 0);
                        v62 = Object;
                        if ( Event < 0 )
                          goto LABEL_79;
                        Win32RawLockedNtObject<tagDESKTOP>::ManualLock((ULONG_PTR)v160, (ULONG_PTR)Object);
                        ObfDereferenceObject(v62);
                        LODWORD(v166) = 1;
                        *((_QWORD *)&v166 + 1) = PsGetCurrentProcess();
                        *(_QWORD *)&v167 = v62;
                        *((_QWORD *)&v167 + 1) = 0x100000000LL;
                        v78 = *(_QWORD *)(W32GetWin32kBaseApiSetTable() + 48);
                        v80 = *(__int64 (__fastcall **)(__int128 *))(v78 + 968);
                        Event = v80 ? v80(&v165) : -1073741637;
                        if ( Event < 0 )
                          goto LABEL_79;
                        if ( !*(_QWORD *)(v24 + 384) )
                        {
                          v81 = *(HANDLE *)(W32GetUserSessionState(v78, v77, v79) + 63312);
                          if ( PsGetProcessId(Process) != v81 )
                          {
                            LockObjectAssignment(v24 + 344, v62);
                            *(_QWORD *)(v24 + 384) = Handle;
                          }
                        }
LABEL_59:
                        if ( (unsigned int)InitClientInfo(ThreadWin32Thread) )
                        {
                          AtomicExecutionCheck::AtomicExecutionCheck((AtomicExecutionCheck *)&v150);
                          v63 = *(__int64 (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable() + 48) + 976LL);
                          if ( v63 )
                            Event = v63();
                          else
                            Event = -1073741637;
                          if ( Event < 0 || (Event = zzzSetDesktop(ThreadWin32Thread, v62, Handle), Event < 0) )
                          {
                            if ( (_BYTE)v150 )
                            {
                              --*(_DWORD *)(v151 + 28);
                              v151 = 0;
                            }
                            goto LABEL_79;
                          }
                          if ( (_BYTE)v150 )
                            --*(_DWORD *)(v151 + 28);
                          W32GetUserSessionState(v84, v83, v85);
                          if ( *((int *)v155 + 8) >= 0 )
                          {
LABEL_117:
                            v89 = _InterlockedCompareExchange(
                                    (volatile signed __int32 *)(ThreadWin32Thread + 520),
                                    0,
                                    0);
                            v90 = (int)Address;
                            if ( (v89 & 0xC) == 0 && !(_DWORD)Address )
                            {
                              v103 = W32GetUserSessionState(v87, v86, v88);
                              ++*(_DWORD *)(v103 + 70592);
                              if ( (int)IszzzCalcStartCursorHideSupported() >= 0 )
                              {
                                ProcessWin32Process = PsGetProcessWin32Process(Process);
                                v125 = ProcessWin32Process;
                                if ( ProcessWin32Process )
                                  v125 = ((unsigned __int128)-(__int128)*(unsigned __int64 *)ProcessWin32Process >> 64)
                                       & ProcessWin32Process;
                                zzzCalcStartCursorHide(v125, 5000);
                              }
                              if ( !*(_DWORD *)(W32GetUserSessionState(v105, v104, v106) + 70592) )
                              {
                                LODWORD(Address) = 0x20000;
                                MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 1780);
                              }
                              v110 = W32GetUserSessionState(v108, v107, v109);
                              --*(_DWORD *)(v110 + 70592);
                              if ( *(_QWORD *)(W32GetUserSessionState(v112, v111, v113) + 63288) )
                              {
                                if ( !*(_QWORD *)(v24 + 656) )
                                {
                                  UserSetLastError(1003);
                                  goto LABEL_161;
                                }
                              }
                            }
                            ApiSetEditionInitInputHangInfo();
                            v93 = *(_QWORD *)(ThreadWin32Thread + 464);
                            if ( v93 )
                              SetUnavailableInputSource(v93 + 532);
                            if ( (*(_DWORD *)(v24 + 12) & 0x20000) != 0 )
                              _InterlockedOr((volatile signed __int32 *)(ThreadWin32Thread + 520), 0x4000u);
                            _InterlockedOr((volatile signed __int32 *)(ThreadWin32Thread + 520), 0x1000000u);
                            if ( (*(_DWORD *)(v24 + 12) & 0x140) == 0
                              && (*(_BYTE *)(v24 + 808) & 0x30) != 0x10
                              && ((v94 = *(_QWORD *)(W32GetUserSessionState(v93, v91, v92) + 18984)) != 0
                               && *(_QWORD *)(v94 + 456) == v24
                               || (unsigned int)LastWokenThread::Test(v24, 0) == 3) )
                            {
                              tagTHREADINFO::SetForegroundActivate(ThreadWin32Thread, 1);
                            }
                            if ( (**(_DWORD **)(W32GetUserSessionState(v93, v91, v92) + 19704) & 4) != 0 )
                            {
                              v100 = *(__int64 (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable() + 48) + 1032LL);
                              v101 = v100 ? v100() : -1073741637;
                              if ( v101 >= 0 )
                              {
                                v102 = *(void (__fastcall **)(_QWORD))(*(_QWORD *)(W32GetWin32kBaseApiSetTable() + 48)
                                                                     + 1040LL);
                                if ( v102 )
                                  v102(0);
                              }
                            }
                            if ( !(_DWORD)Self )
                            {
                              v97 = *(__int64 (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable() + 48) + 1048LL);
                              Event = v97 ? v97() : -1073741637;
                              if ( Event < 0 )
                                goto LABEL_79;
                              v98 = *(__int64 (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable() + 48) + 1056LL);
                              Event = v98 ? v98() : -1073741637;
                              if ( Event < 0 )
                                goto LABEL_79;
                            }
                            if ( !v90 && (*(_DWORD *)(v24 + 12) & 1) == 0 )
                            {
                              v95 = *(__int64 (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable() + 48) + 1064LL);
                              if ( v95 )
                                v52 = v95();
                              if ( v52 >= 0 )
                              {
                                v123 = *(void (__fastcall **)(__int64))(*(_QWORD *)(W32GetWin32kBaseApiSetTable() + 48)
                                                                      + 1072LL);
                                if ( v123 )
                                  v123(7);
                              }
                            }
                            if ( v62 )
                            {
                              if ( (v62[12] & 8) != 0 )
                              {
LABEL_161:
                                Event = -1073741823;
                                goto LABEL_79;
                              }
                              if ( v161 == -1 )
                              {
                                v99 = PtiCurrent();
                                KeBugCheckEx(0x164u, 0x12u, (ULONG_PTR)v160, 0, (ULONG_PTR)v99);
                              }
                              PopAndFreeW32ThreadLock(v160);
                              v161 = -1;
                            }
                            v96 = *(_QWORD *)(ThreadWin32Thread + 1360);
                            if ( (v96 & 1) != 0 )
                              *(_QWORD *)(ThreadWin32Thread + 1360) = v96 & 0xFFFFFFFFFFFFFFFEuLL;
                            goto LABEL_86;
                          }
                          if ( !(_DWORD)Address )
                          {
                            if ( !*(_QWORD *)(W32GetUserSessionState(v87, v86, v88) + 63312)
                              || (v142 = *(_QWORD *)(W32GetUserSessionState(v87, v86, v88) + 63312),
                                  PsGetProcessInheritedFromUniqueProcessId(Process) != v142) )
                            {
                              *((_DWORD *)v155 + 8) &= ~0x80000000;
                              goto LABEL_117;
                            }
                            *(_QWORD *)(W32GetUserSessionState(v87, v86, v88) + 62592) = v24;
                            v146 = *(_QWORD *)(W32GetUserSessionState(v144, v143, v145) + 19704);
                            v147 = *(_QWORD *)(v146 + 4960);
                            *(_QWORD *)(W32GetUserSessionState(v146, v148, v149) + 36056) = v147;
                            *(_DWORD *)(v24 + 12) |= 0x200000u;
                            EtwTraceScreenSaverProcessEvent(1);
                            ForegroundBoost::SetForegroundPriority(ThreadWin32Thread, 1, 8);
                            *(_DWORD *)(v24 + 12) |= 0x400000u;
                          }
                          _InterlockedOr((volatile signed __int32 *)(ThreadWin32Thread + 520), 0x2000000u);
                          goto LABEL_117;
                        }
LABEL_79:
                        if ( v62 )
                          Win32RawLockedItemBase<tagDESKTOP,&void UserDereferenceObject(void *),1,1,1>::UnlockWorker((ULONG_PTR)v160);
                        if ( v162 )
                          Win32RawLockedItemBase<DISPLAYCONFIG_DEVICE_INFO_HEADER,&void Win32FreePool(void *),1,1,1>::UnlockWorker((ULONG_PTR)v156);
                        if ( v163 )
                          Win32RawLockedItemBase<DISPLAYCONFIG_DEVICE_INFO_HEADER,&void Win32FreePool(void *),1,1,1>::UnlockWorker((ULONG_PTR)BugCheckParameter2);
                        xxxDestroyThreadInfo();
LABEL_86:
                        Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(v160);
                        Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(v156);
                        Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(BugCheckParameter2);
                        return (unsigned int)Event;
                      }
                    }
                    CloseProtectedHandle(Handle);
                    CloseProtectedHandle(v154);
                    Handle = 0;
                    v154 = 0;
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
          v62 = 0;
          goto LABEL_79;
        }
        if ( !*(_QWORD *)(W32GetUserSessionState(v35, v34, v36) + 14184) )
        {
          if ( *(_QWORD *)(W32GetUserSessionState(v38, v37, v39) + 14216) )
          {
            v129 = *(_QWORD *)(W32GetUserSessionState(v127, v126, v128) + 14216);
            v133 = W32GetUserSessionState(v131, v130, v132);
            v134 = 1;
          }
          else
          {
            if ( !*(_QWORD *)(W32GetUserSessionState(v127, v126, v128) + 14656) )
              goto LABEL_28;
            v129 = *(_QWORD *)(W32GetUserSessionState(v38, v37, v39) + 14656);
            v133 = W32GetUserSessionState(v136, v135, v137);
            v134 = 0;
          }
          v150 = (char *)(v133 + 14184);
          v151 = v129;
          HMAssignmentLock(&v150, v134);
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
        v150 = (char *)(ThreadWin32Thread + 472);
        v44 = *(_QWORD *)(W32GetUserSessionState(v41, v40, v42) + 14184);
        goto LABEL_32;
      }
    }
  }
  Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(v160);
  Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(v156);
  Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(BugCheckParameter2);
  return 3221225738LL;
}

```

## disassembly

```asm
0x140036aa4  push    rbx
0x140036aa6  push    rsi
0x140036aa7  push    rdi
0x140036aa8  push    r12
0x140036aaa  push    r13
0x140036aac  push    r14
0x140036aae  push    r15
0x140036ab0  sub     rsp, 190h
0x140036ab7  mov     r13, rcx
0x140036aba  call    cs:__imp_PsGetThreadProcess
0x140036ac1  nop     dword ptr [rax+rax+00h]
0x140036ac6  mov     rbx, rax
0x140036ac9  mov     [rsp+1C8h+Process], rax
0x140036ace  xor     edx, edx; Val
0x140036ad0  lea     r8d, [rdx+48h]; Size
0x140036ad4  lea     rcx, [rsp+1C8h+var_F8]; void *
0x140036adc  call    memset
0x140036ae1  xor     esi, esi
0x140036ae3  mov     [rsp+1C8h+Handle], rsi
0x140036aeb  mov     [rsp+1C8h+var_168], rsi
0x140036af0  mov     rax, gs:30h
0x140036af9  mov     [rsp+1C8h+arg_10], rax
0x140036b01  lea     rcx, [rsp+1C8h+BugCheckParameter2]
0x140036b09  call    ??0?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(void)
0x140036b0e  lea     rcx, [rsp+1C8h+var_158]
0x140036b13  call    ??0?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(void)
0x140036b18  lea     rcx, [rsp+1C8h+var_128]
0x140036b20  call    ??0?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(void)
0x140036b25  xorps   xmm1, xmm1
0x140036b28  movups  [rsp+1C8h+var_98], xmm1
0x140036b30  movups  [rsp+1C8h+var_88], xmm1
0x140036b38  movups  [rsp+1C8h+var_78], xmm1
0x140036b40  mov     al, byte ptr cs:Microsoft_Windows_Win32kEnableBits+1
0x140036b46  test    al, al
0x140036b48  jns     short loc_140036B5D
0x140036b4a  lea     r8, W32kControlGuid
0x140036b51  lea     rdx, InitiateGuiThreadExecution
0x140036b58  call    McTemplateK0_EtwWriteTransfer
0x140036b5d  call    cs:__imp_W32GetUserSessionState
0x140036b64  nop     dword ptr [rax+rax+00h]
0x140036b69  cmp     [rax+8D88h], esi
0x140036b6f  jnz     loc_140038018
0x140036b75  call    cs:__imp_PsGetCurrentProcessWin32Process
0x140036b7c  nop     dword ptr [rax+rax+00h]
0x140036b81  test    rax, rax
0x140036b84  jz      loc_140038018
0x140036b8a  mov     rcx, [rax]
0x140036b8d  neg     rcx
0x140036b90  sbb     rdx, rdx
0x140036b93  and     rax, rdx
0x140036b96  test    rax, rax
0x140036b99  jz      loc_140038018
0x140036b9f  mov     [rsp+1C8h+var_108], rsi
0x140036ba7  mov     [rsp+1C8h+var_110], rsi
0x140036baf  call    cs:__imp_W32GetUserSessionState
0x140036bb6  nop     dword ptr [rax+rax+00h]
0x140036bbb  mov     edi, 1
0x140036bc0  add     [rax+8D90h], edi
0x140036bc6  call    cs:__imp_W32GetUserGdiSessionState
0x140036bcd  nop     dword ptr [rax+rax+00h]
0x140036bd2  mov     r12d, 2000048h
0x140036bd8  cmp     rbx, [rax+28h]
0x140036bdc  cmovnz  r12d, esi
0x140036be0  mov     rcx, r13
0x140036be3  call    W32GetThreadWin32Thread
0x140036be8  mov     r14, rax
0x140036beb  mov     [rsp+1C8h+BugCheckParameter3], rsi
0x140036bf3  mov     rcx, rbx
0x140036bf6  call    cs:__imp_PsGetProcessPeb
0x140036bfd  nop     dword ptr [rax+rax+00h]
0x140036c02  mov     [rsp+1C8h+Address], rax
0x140036c0a  mov     [rsp+1C8h+var_A8], 7D0h
0x140036c16  mov     rcx, [rsp+1C8h+Address]; Address
0x140036c1e  mov     [rsp+1C8h+var_A8], rdi
0x140036c26  mov     r8d, edi; Alignment
0x140036c29  mov     edx, edi; Length
0x140036c2b  call    cs:__imp_ProbeForRead
0x140036c32  nop     dword ptr [rax+rax+00h]
0x140036c37  mov     rax, [rsp+1C8h+Address]
0x140036c3f  mov     rcx, [rax+20h]
0x140036c43  mov     [rsp+1C8h+Address], rcx
0x140036c4b  lea     rax, [rsp+1C8h+var_F8]
0x140036c53  mov     [rsp+1C8h+var_160], rax
0x140036c58  mov     [rsp+1C8h+var_68], rax
0x140036c60  mov     [rsp+1C8h+var_A0], 450h
0x140036c6c  mov     rcx, [rsp+1C8h+Address]; Address
0x140036c74  mov     [rsp+1C8h+var_A0], rdi
0x140036c7c  mov     r8d, edi; Alignment
0x140036c7f  mov     edx, edi; Length
0x140036c81  call    cs:__imp_ProbeForRead
0x140036c88  nop     dword ptr [rax+rax+00h]
0x140036c8d  mov     rax, [rsp+1C8h+Address]
0x140036c95  mov     rcx, [rax+20h]
0x140036c99  mov     [rsp+1C8h+var_F8], rcx
0x140036ca1  mov     rax, [rsp+1C8h+Address]
0x140036ca9  mov     rcx, [rax+28h]
0x140036cad  mov     [rsp+1C8h+var_F0], rcx
0x140036cb5  mov     rax, [rsp+1C8h+Address]
0x140036cbd  mov     ecx, [rax+88h]
0x140036cc3  mov     [rsp+1C8h+var_E8], ecx
0x140036cca  mov     rax, [rsp+1C8h+Address]
0x140036cd2  mov     ecx, [rax+8Ch]
0x140036cd8  mov     [rsp+1C8h+var_E4], ecx
0x140036cdf  mov     rax, [rsp+1C8h+Address]
0x140036ce7  mov     ecx, [rax+90h]
0x140036ced  mov     [rsp+1C8h+var_E0], ecx
0x140036cf4  mov     rax, [rsp+1C8h+Address]
0x140036cfc  mov     ecx, [rax+94h]
0x140036d02  mov     [rsp+1C8h+var_DC], ecx
0x140036d09  mov     rax, [rsp+1C8h+Address]
0x140036d11  mov     ecx, [rax+0A4h]
0x140036d17  mov     [rsp+1C8h+var_D8], ecx
0x140036d1e  mov     rax, [rsp+1C8h+Address]
0x140036d26  mov     ecx, [rax+0A8h]
0x140036d2c  mov     [rsp+1C8h+var_D4], ecx
0x140036d33  mov     rcx, [rsp+1C8h+Address]
0x140036d3b  add     rcx, 0C0h
0x140036d42  mov     [rsp+1C8h+var_60], rcx
0x140036d4a  lea     r8, [rsp+1C8h+var_D0]
0x140036d52  call    ??$DuplicateUnicodeStringFromUser@$0A@@@YAJV?$UserModePointer@UUSERMODE_UNICODE_STRING@@@@KPEAU_UNICODE_STRING@@@Z; DuplicateUnicodeStringFromUser<0>(UserModePointer<USERMODE_UNICODE_STRING>,ulong,_UNICODE_STRING *)
0x140036d57  test    eax, eax
0x140036d59  js      loc_140036E49
0x140036d5f  mov     rbx, [rsp+1C8h+BugCheckParameter3]
0x140036d67  test    rbx, rbx
0x140036d6a  jnz     loc_140036DF7
0x140036d70  lea     rdi, GreDeleteFastMutex
0x140036d77  mov     rcx, [rsp+1C8h+Address]
0x140036d7f  add     rcx, 0D0h
0x140036d86  mov     [rsp+1C8h+var_188], rcx
0x140036d8b  lea     r8, [rsp+1C8h+var_C0]
0x140036d93  call    ??$DuplicateUnicodeStringFromUser@$0A@@@YAJV?$UserModePointer@UUSERMODE_UNICODE_STRING@@@@KPEAU_UNICODE_STRING@@@Z; DuplicateUnicodeStringFromUser<0>(UserModePointer<USERMODE_UNICODE_STRING>,ulong,_UNICODE_STRING *)
0x140036d98  test    eax, eax
0x140036d9a  js      loc_140036E83
0x140036da0  mov     rbx, [rsp+1C8h+var_B8]
0x140036da8  test    rbx, rbx
0x140036dab  jz      loc_140036EBA
0x140036db1  mov     [rsp+1C8h+var_110], rbx
0x140036db9  cmp     [rsp+1C8h+var_148], 0FFFFFFFFFFFFFFFFh
0x140036dc2  jnz     loc_140036E91
0x140036dc8  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x140036dcd  mov     rcx, [rax+178h]
0x140036dd4  mov     [rsp+1C8h+var_158], rcx
0x140036dd9  lea     rcx, [rsp+1C8h+var_158]
0x140036dde  mov     [rax+178h], rcx
0x140036de5  mov     [rsp+1C8h+var_150], rbx
0x140036dea  mov     [rsp+1C8h+var_148], rdi
0x140036df2  jmp     loc_140036EBA
0x140036df7  mov     [rsp+1C8h+var_108], rbx
0x140036dff  cmp     [rsp+1C8h+var_130], 0FFFFFFFFFFFFFFFFh
0x140036e08  jnz     short loc_140036E57
0x140036e0a  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x140036e0f  mov     rcx, [rax+178h]
0x140036e16  mov     [rsp+1C8h+BugCheckParameter2], rcx
0x140036e1e  lea     rcx, [rsp+1C8h+BugCheckParameter2]
0x140036e26  mov     [rax+178h], rcx
0x140036e2d  mov     [rsp+1C8h+var_138], rbx
0x140036e35  lea     rdi, GreDeleteFastMutex
0x140036e3c  mov     [rsp+1C8h+var_130], rdi
0x140036e44  jmp     loc_140036D77
0x140036e49  mov     ecx, eax; Status
0x140036e4b  call    cs:__imp_ExRaiseStatus
0x140036e57  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x140036e5c  mov     [rsp+1C8h+BugCheckParameter4], rax; BugCheckParameter4
0x140036e61  mov     r9, rbx; BugCheckParameter3
0x140036e64  lea     r8, [rsp+1C8h+BugCheckParameter2]; BugCheckParameter2
0x140036e6c  mov     edx, 12h; BugCheckParameter1
0x140036e71  mov     ecx, 164h; BugCheckCode
0x140036e76  call    cs:__imp_KeBugCheckEx
0x140036e83  mov     ecx, eax; Status
0x140036e85  call    cs:__imp_ExRaiseStatus
0x140036e91  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x140036e96  mov     [rsp+1C8h+BugCheckParameter4], rax; BugCheckParameter4
0x140036e9b  mov     r9, rbx; BugCheckParameter3
0x140036e9e  lea     r8, [rsp+1C8h+var_158]; BugCheckParameter2
0x140036ea3  mov     edx, 12h; BugCheckParameter1
0x140036ea8  mov     ecx, 164h; BugCheckCode
0x140036ead  call    cs:__imp_KeBugCheckEx
0x140036eba  jmp     short loc_140036EC8
0x140036ebc  mov     edi, eax
0x140036ebe  xor     esi, esi
0x140036ec0  mov     r13d, esi
0x140036ec3  jmp     loc_140037473
0x140036ec8  call    cs:__imp_PsGetCurrentProcessWin32Process
0x140036ecf  nop     dword ptr [rax+rax+00h]
0x140036ed4  mov     r15, rax
0x140036ed7  test    rax, rax
0x140036eda  jz      short loc_140036EE8
0x140036edc  mov     rax, [rax]
0x140036edf  neg     rax
0x140036ee2  sbb     rcx, rcx
0x140036ee5  and     r15, rcx
0x140036ee8  mov     edi, r12d
0x140036eeb  bts     edi, 8
0x140036eef  test    byte ptr [r15+0Ch], 80h
0x140036ef4  cmovz   edi, r12d
0x140036ef8  mov     rcx, r13; Thread
0x140036efb  call    cs:__imp_PsGetThreadProcessId
0x140036f02  nop     dword ptr [rax+rax+00h]
0x140036f07  mov     rbx, rax
0x140036f0a  call    cs:__imp_W32GetUserSessionState
0x140036f11  nop     dword ptr [rax+rax+00h]
0x140036f16  mov     r13d, edi
0x140036f19  mov     r12d, 2000000h
0x140036f1f  or      r13d, r12d
0x140036f22  cmp     [rax+0F750h], rbx
0x140036f29  cmovnz  r13d, edi
0x140036f2d  lock or [r14+208h], r13d
0x140036f35  call    cs:__imp_W32GetUserSessionState
0x140036f3c  nop     dword ptr [rax+rax+00h]
0x140036f41  mov     ecx, [rax+104E8h]
0x140036f47  test    cl, cl
0x140036f49  js      loc_1400370DB
0x140036f4f  call    cs:__imp_W32GetUserSessionState
0x140036f56  nop     dword ptr [rax+rax+00h]
0x140036f5b  cmp     [rax+3768h], rsi
0x140036f62  jz      loc_140037C1B
0x140036f68  call    cs:__imp_W32GetUserSessionState
0x140036f6f  nop     dword ptr [rax+rax+00h]
0x140036f74  cmp     [rax+3768h], rsi
0x140036f7b  jz      short loc_140036F9F
0x140036f7d  call    cs:__imp_W32GetUserSessionState
0x140036f84  nop     dword ptr [rax+rax+00h]
0x140036f89  mov     rcx, [rax+3768h]
0x140036f90  call    _HMPheFromObject
0x140036f95  test    byte ptr [rax+19h], 1
0x140036f99  jnz     loc_140037CAF
0x140036f9f  lea     rax, [r14+1D8h]
0x140036fa6  mov     [rsp+1C8h+var_188], rax
0x140036fab  call    cs:__imp_W32GetUserSessionState
0x140036fb2  nop     dword ptr [rax+rax+00h]
0x140036fb7  mov     rcx, [rax+3768h]
0x140036fbe  mov     [rsp+1C8h+var_180], rcx
0x140036fc3  xor     edx, edx
0x140036fc5  lea     rcx, [rsp+1C8h+var_188]
0x140036fca  call    HMAssignmentLock
0x140036fcf  lea     rax, [r14+440h]
0x140036fd6  mov     [r14+1E0h], rax
0x140036fdd  test    dword ptr [r15+0Ch], 800000h
0x140036fe5  jnz     loc_140037CD8
0x140036feb  mov     [r14+1C8h], r15
0x140036ff2  mov     rax, [r15+148h]
0x140036ff9  mov     [r14+2B8h], rax
0x140037000  mov     [r15+148h], r14
0x140037007  inc     dword ptr [r15+178h]
0x14003700e  mov     rax, [rsp+1C8h+arg_10]
0x140037016  test    rax, rax
0x140037019  jnz     loc_1400370AF
0x14003701f  mov     rax, [rsp+1C8h+arg_10]
0x140037027  add     rax, 800h
0x14003702d  mov     [r14+200h], rax
0x140037034  mov     rcx, [r14+200h]
0x14003703b  mov     eax, [r14+188h]
0x140037042  mov     [rcx+0E8h], eax
0x140037048  mov     rax, [r14+200h]
0x14003704f  mov     [rax+0ECh], esi
0x140037055  mov     rax, [r14+200h]
0x14003705c  add     rax, 0E8h
0x140037062  mov     [r14+190h], rax
0x140037069  mov     rcx, [r14+200h]
0x140037070  mov     eax, [r14+18Ch]
0x140037077  mov     [rcx+0F0h], eax
0x14003707d  mov     rax, [r14+200h]
0x140037084  mov     [rax+0F4h], esi
0x14003708a  mov     rax, [r14+200h]
0x140037091  add     rax, 0F0h
0x140037097  mov     [r14+198h], rax
0x14003709e  jmp     loc_140037136
0x1400370a3  mov     edi, eax
0x1400370a5  xor     esi, esi
0x1400370a7  mov     r13d, esi
0x1400370aa  jmp     loc_140037473
0x1400370af  mov     rcx, [r14]; Thread
0x1400370b2  mov     rbx, [rsp+1C8h+arg_10]
0x1400370ba  call    cs:__imp_PsGetThreadId
0x1400370c1  nop     dword ptr [rax+rax+00h]
0x1400370c6  mov     [rbx+78h], rax
0x1400370ca  jmp     loc_14003701F
0x1400370cf  mov     edi, eax
0x1400370d1  xor     esi, esi
0x1400370d3  mov     r13d, esi
0x1400370d6  jmp     loc_140037473
0x1400370db  call    cs:__imp_W32GetUserSessionState
0x1400370e2  nop     dword ptr [rax+rax+00h]
0x1400370e7  cmp     [rax+3788h], rsi
0x1400370ee  jz      short loc_140037112
0x1400370f0  call    cs:__imp_W32GetUserSessionState
0x1400370f7  nop     dword ptr [rax+rax+00h]
0x1400370fc  mov     rcx, [rax+3788h]
0x140037103  call    _HMPheFromObject
0x140037108  test    byte ptr [rax+19h], 1
0x14003710c  jnz     loc_140037BF2
0x140037112  lea     rax, [r14+1D8h]
0x140037119  mov     [rsp+1C8h+var_188], rax
0x14003711e  call    cs:__imp_W32GetUserSessionState
0x140037125  nop     dword ptr [rax+rax+00h]
0x14003712a  mov     rcx, [rax+3788h]
0x140037131  jmp     loc_140036FBE
0x140037136  test    [r15+0Ch], r12d
0x14003713a  jnz     loc_140037CE5
0x140037140  cmp     [r14+298h], esi
  ... truncated ...
```
