# CReflectedDumpServerLauncher::LaunchServer(void *,ulong,ulong,ulong,ulong,wchar_t const *,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *)

- ea: `0x18001f040`
- end: `0x18001fb25`
- name: `?LaunchServer@CReflectedDumpServerLauncher@@QEAAJPEAXKKKKPEB_WPEA_K2222@Z`
- size: `2789`
- prototype: `void __fastcall __noreturn(CReflectedDumpServerLauncher *this, void *, DWORD, int, unsigned int, unsigned int, const wchar_t *, unsigned __int64 *, unsigned __int64 *, unsigned __int64 *, unsigned __int64 *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180019c08`

## callees

- `0x1800029d0`
- `0x1800035e8`
- `0x180006134`
- `0x18000caf0`
- `0x18000cb10`
- `0x18001e81c`
- `0x18001ec8c`
- `0x18001ed68`
- `0x18001f040`
- `0x18001fb2c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001f6f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001f76c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001f6f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001f76c`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18001f73b`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18001f73b`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18001f7a0`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18001f7a0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001f3ce`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001f3ee`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001f410`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001f432`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001f3ce`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001f3ee`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001f410`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001f432`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001f7d1`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001f7d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f4ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f4f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f500`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f50b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f514`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f58a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f593`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f59e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f5a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f5b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f5bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f84c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f855`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f860`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f86b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f874`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f87f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f892`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f8a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f8b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f8f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f8fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f909`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f914`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fa03`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fa18`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fa53`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001faf3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f4ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f4f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f500`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f50b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f514`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f58a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f593`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f59e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f5a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f5b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f5bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f84c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f855`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f860`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f86b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f874`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f87f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f892`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f8a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f8b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f8f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f8fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f909`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f914`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fa03`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fa18`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fa53`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001faf3`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18001f4cd`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18001f56b`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18001f82d`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18001f8d6`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18001f93b`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18001f970`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18001f9ab`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18001f9e6`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18001f4cd`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18001f56b`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18001f82d`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18001f8d6`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18001f93b`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18001f970`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18001f9ab`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18001f9e6`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18001f310`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18001f310`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18001f2e1`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18001f46a`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18001f2e1`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18001f46a`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001f19d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001f19d`
- `ntdll!NtTerminateProcess` at `0x18001f761`
- `ntdll!NtTerminateProcess` at `0x18001f761`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f250`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f4e1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f57f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f841`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f8ea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f94f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f984`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f9bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f9fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001fa4a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001fa7f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001fade`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f250`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f4e1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f57f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f841`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f8ea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f94f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f984`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f9bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f9fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001fa4a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001fa7f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001fade`
- `CRYPTSP!CryptReleaseContext` at `0x18001f21d`
- `CRYPTSP!CryptReleaseContext` at `0x18001f267`
- `CRYPTSP!CryptReleaseContext` at `0x18001f21d`
- `CRYPTSP!CryptReleaseContext` at `0x18001f267`
- `CRYPTSP!CryptGenRandom` at `0x18001f1f3`
- `CRYPTSP!CryptGenRandom` at `0x18001f1f3`
- `CRYPTSP!CryptAcquireContextW` at `0x18001f1ce`
- `CRYPTSP!CryptAcquireContextW` at `0x18001f1ce`
- `wer!WerpAddTerminationReason` at `0x18001f754`
- `wer!WerpAddTerminationReason` at `0x18001f754`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn CReflectedDumpServerLauncher::LaunchServer(
        CReflectedDumpServerLauncher *this,
        void *a2,
        DWORD a3,
        int a4,
        unsigned int a5,
        unsigned int a6,
        const wchar_t *a7,
        unsigned __int64 *a8,
        unsigned __int64 *a9,
        unsigned __int64 *a10,
        unsigned __int64 *a11,
        unsigned __int64 *a12)
{
  const char *v14; // r9
  char *v15; // r14
  const char *v16; // r9
  __int64 v17; // rdx
  int LastError; // ebx
  unsigned __int64 v19; // r9
  __int64 v20; // rdx
  int v21; // eax
  __int64 v22; // rcx
  int AdminAllAccessProcessReadOnlyAcl; // eax
  HANDLE v24; // rsi
  const char *v25; // r9
  _DWORD *v26; // rax
  const char *v27; // r9
  _WORD *v28; // rdi
  _WORD *v29; // r8
  const wchar_t *v30; // rax
  __int64 v31; // rcx
  __int64 v32; // rdx
  _WORD *v33; // rcx
  const char *v34; // r9
  HANDLE EventW; // r13
  const char *v36; // r9
  const char *v37; // r9
  const char *v38; // r9
  const char *v39; // r9
  int v40; // eax
  __int64 v41; // rcx
  void *v42; // rcx
  int WerfaultInProcessContext; // eax
  wil::details::in1diag3 *v44; // rcx
  __int64 v45; // r9
  __int64 v46; // rdx
  HANDLE v47; // rbx
  HANDLE CurrentProcess; // rax
  CReflectedDumpServerLauncher *v49; // rcx
  int v50; // eax
  __int64 v51; // rdx
  __int64 v52; // r9
  DWORD ProcessId; // eax
  HANDLE v54; // rax
  CReflectedDumpServerLauncher *v55; // rcx
  HANDLE v56; // rbx
  DWORD v57; // eax
  HANDLE v58; // rcx
  HANDLE v59; // rcx
  HANDLE v60; // rcx
  bool v61; // cc
  HANDLE v62; // rcx
  int dwFlags; // [rsp+20h] [rbp-E0h]
  int dwFlagsa; // [rsp+20h] [rbp-E0h]
  int dwFlagsb; // [rsp+20h] [rbp-E0h]
  HANDLE *dwFlagsc; // [rsp+20h] [rbp-E0h]
  HANDLE Process; // [rsp+30h] [rbp-D0h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-C8h] BYREF
  HCRYPTPROV phProv; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE v70; // [rsp+48h] [rbp-B8h]
  HANDLE hObject; // [rsp+50h] [rbp-B0h]
  HANDLE v72; // [rsp+58h] [rbp-A8h]
  HANDLE hThread; // [rsp+60h] [rbp-A0h] BYREF
  void *v74; // [rsp+68h] [rbp-98h]
  BYTE pbBuffer[8]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 *v76; // [rsp+78h] [rbp-88h]
  unsigned __int64 *v77; // [rsp+80h] [rbp-80h]
  unsigned __int64 *v78; // [rsp+88h] [rbp-78h]
  unsigned __int64 *v79; // [rsp+90h] [rbp-70h]
  unsigned __int64 *v80; // [rsp+98h] [rbp-68h]
  HANDLE Handles[2]; // [rsp+A0h] [rbp-60h] BYREF
  struct _SECURITY_ATTRIBUTES FileMappingAttributes; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v83[2]; // [rsp+D0h] [rbp-30h] BYREF
  int v84; // [rsp+E0h] [rbp-20h]
  HANDLE v85; // [rsp+E8h] [rbp-18h]
  unsigned __int64 *v86; // [rsp+F0h] [rbp-10h]
  int v87; // [rsp+F8h] [rbp-8h]
  HANDLE v88; // [rsp+100h] [rbp+0h]
  unsigned __int64 *v89; // [rsp+108h] [rbp+8h]
  int v90; // [rsp+110h] [rbp+10h]
  HANDLE v91; // [rsp+118h] [rbp+18h]
  unsigned __int64 *v92; // [rsp+120h] [rbp+20h]
  int v93; // [rsp+128h] [rbp+28h]
  HCRYPTPROV v94; // [rsp+130h] [rbp+30h]
  unsigned __int64 *v95; // [rsp+138h] [rbp+38h]
  int v96; // [rsp+140h] [rbp+40h]
  _QWORD v97[2]; // [rsp+150h] [rbp+50h] BYREF
  int v98; // [rsp+160h] [rbp+60h]
  void *v99; // [rsp+168h] [rbp+68h]
  _WORD *v100; // [rsp+170h] [rbp+70h]
  int v101; // [rsp+178h] [rbp+78h]
  HANDLE v102; // [rsp+180h] [rbp+80h]
  _WORD *v103; // [rsp+188h] [rbp+88h]
  int v104; // [rsp+190h] [rbp+90h]
  HANDLE v105; // [rsp+198h] [rbp+98h]
  _WORD *v106; // [rsp+1A0h] [rbp+A0h]
  int v107; // [rsp+1A8h] [rbp+A8h]
  HANDLE v108; // [rsp+1B0h] [rbp+B0h]
  _WORD *v109; // [rsp+1B8h] [rbp+B8h]
  int v110; // [rsp+1C0h] [rbp+C0h]
  HCRYPTPROV v111; // [rsp+1C8h] [rbp+C8h]
  _WORD *v112; // [rsp+1D0h] [rbp+D0h]
  int v113; // [rsp+1D8h] [rbp+D8h]
  WCHAR Name[64]; // [rsp+1E0h] [rbp+E0h] BYREF
  wchar_t v115[128]; // [rsp+260h] [rbp+160h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3A8h] [rbp+2A8h]

  v74 = a2;
  v76 = a8;
  v77 = a9;
  v78 = a10;
  v79 = a11;
  v80 = a12;
  Process = 0;
  hThread = 0;
  LODWORD(v70) = a4;
  memset_0(v115, 0, sizeof(v115));
  memset_0(Name, 0, sizeof(Name));
  *(_QWORD *)pbBuffer = 0;
  *(_OWORD *)Handles = 0;
  hMem = 0;
  memset(&FileMappingAttributes, 0, sizeof(FileMappingAttributes));
  if ( (unsigned int)_InterlockedIncrement((volatile signed __int32 *)this) > 1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x175,
      (unsigned int)"onecore\\windows\\feedback\\core\\wersvc\\lib\\reflectionserver.cpp",
      (const char *)0x800700AALL,
      dwFlags);
    goto LABEL_104;
  }
  if ( v74 && a3 && a8 && a9 && a10 && a11 && a12 )
  {
    *a8 = 0;
    *a9 = 0;
    *a10 = 0;
    *a11 = 0;
    *a12 = 0;
    v15 = (char *)OpenProcess(0x400u, 0, a3);
    if ( v15 != (char *)-1LL && v15 + 1 != (char *)1 )
    {
      phProv = 0;
      if ( CryptAcquireContextW(&phProv, 0, 0, 1u, 0xF0000000) )
      {
        if ( CryptGenRandom(phProv, 8u, pbBuffer) )
        {
          if ( phProv )
            CryptReleaseContext(phProv, 0);
          goto LABEL_23;
        }
        v17 = 56;
      }
      else
      {
        v17 = 54;
      }
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)v17,
                    (unsigned int)"onecore\\windows\\feedback\\core\\wersvc\\lib\\reflectionserver.cpp",
                    v16);
      if ( phProv )
        CryptReleaseContext(phProv, 0);
      if ( LastError < 0 )
      {
        v19 = (unsigned int)LastError;
        v20 = 405;
        goto LABEL_19;
      }
LABEL_23:
      v21 = StringCchPrintfW(Name, 0x40u, L"Global\\%I64X", *(_QWORD *)pbBuffer);
      if ( v21 < 0 )
      {
        v19 = (unsigned int)v21;
        v20 = 410;
        goto LABEL_19;
      }
      AdminAllAccessProcessReadOnlyAcl = CReflectedDumpServerLauncher::GetAdminAllAccessProcessReadOnlyAcl(
                                           v22,
                                           v15,
                                           &hMem,
                                           &FileMappingAttributes);
      if ( AdminAllAccessProcessReadOnlyAcl < 0 )
      {
        v19 = (unsigned int)AdminAllAccessProcessReadOnlyAcl;
        v20 = 416;
LABEL_19:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v20,
          (unsigned int)"onecore\\windows\\feedback\\core\\wersvc\\lib\\reflectionserver.cpp",
          (const char *)v19,
          dwFlagsa);
        _InterlockedDecrement((volatile signed __int32 *)this);
        if ( hMem )
          LocalFree(hMem);
        goto LABEL_91;
      }
      v24 = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, &FileMappingAttributes, 4u, 0, 0x248u, Name);
      if ( (unsigned __int64)v24 + 1 <= 1 )
      {
        wil::details::in1diag3::Return_GetLastError(
          retaddr,
          (void *)0x1AC,
          (unsigned int)"onecore\\windows\\feedback\\core\\wersvc\\lib\\reflectionserver.cpp",
          v25);
        _InterlockedDecrement((volatile signed __int32 *)this);
        if ( hMem )
          LocalFree(hMem);
      }
      else
      {
        v26 = MapViewOfFile(v24, 2u, 0, 0, 0x248u);
        v28 = v26;
        if ( v26 )
        {
          *v26 = a3;
          v29 = v26 + 4;
          v26[1] = (_DWORD)v70;
          v26[2] = a5;
          v26[3] = a6;
          v30 = a7;
          v28[8] = 0;
          if ( a7 )
          {
            v31 = 2147483646;
            v32 = 260;
            do
            {
              if ( !v31 )
                break;
              if ( !*v30 )
                break;
              *v29++ = *v30++;
              --v31;
              --v32;
            }
            while ( v32 );
            v33 = v29 - 1;
            if ( v32 )
              v33 = v29;
            *v33 = 0;
            if ( !v32 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1C7,
                (unsigned int)"onecore\\windows\\feedback\\core\\wersvc\\lib\\reflectionserver.cpp",
                (const char *)0x8007007ALL,
                dwFlagsb);
LABEL_87:
              UnmapViewOfFile(v28);
              _InterlockedDecrement((volatile signed __int32 *)this);
              if ( hMem )
                LocalFree(hMem);
              v42 = v24;
              goto LABEL_90;
            }
          }
          EventW = CreateEventW(0, 1, 0, 0);
          if ( (unsigned __int64)EventW + 1 <= 1 )
          {
            wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x1CF,
              (unsigned int)"onecore\\windows\\feedback\\core\\wersvc\\lib\\reflectionserver.cpp",
              v34);
            goto LABEL_87;
          }
          v70 = CreateEventW(0, 1, 0, 0);
          if ( (unsigned __int64)v70 + 1 <= 1 )
          {
            wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x1D2,
              (unsigned int)"onecore\\windows\\feedback\\core\\wersvc\\lib\\reflectionserver.cpp",
              v36);
            UnmapViewOfFile(v28);
            _InterlockedDecrement((volatile signed __int32 *)this);
            if ( hMem )
              LocalFree(hMem);
            v59 = v24;
          }
          else
          {
            v72 = CreateEventW(0, 1, 0, 0);
            if ( (unsigned __int64)v72 + 1 <= 1 )
            {
              wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x1D5,
                (unsigned int)"onecore\\windows\\feedback\\core\\wersvc\\lib\\reflectionserver.cpp",
                v37);
              UnmapViewOfFile(v28);
              _InterlockedDecrement((volatile signed __int32 *)this);
              if ( hMem )
                LocalFree(hMem);
              v58 = v24;
            }
            else
            {
              hObject = CreateEventW(0, 1, 0, 0);
              if ( (unsigned __int64)hObject + 1 <= 1 )
              {
                wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x1D8,
                  (unsigned int)"onecore\\windows\\feedback\\core\\wersvc\\lib\\reflectionserver.cpp",
                  v38);
                UnmapViewOfFile(v28);
                _InterlockedDecrement((volatile signed __int32 *)this);
                if ( hMem )
                  LocalFree(hMem);
              }
              else
              {
                phProv = (HCRYPTPROV)CreateFileMappingW(
                                       (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                                       &FileMappingAttributes,
                                       4u,
                                       0,
                                       0x218u,
                                       0);
                if ( phProv + 1 > 1 )
                {
                  v40 = StringCchPrintfW(v115, 0x80u, L"%s %s", L"-pr");
                  if ( v40 < 0 )
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x1EC,
                      (unsigned int)"onecore\\windows\\feedback\\core\\wersvc\\lib\\reflectionserver.cpp",
                      (const char *)(unsigned int)v40,
                      (int)Name);
                    UnmapViewOfFile(v28);
                    _InterlockedDecrement((volatile signed __int32 *)this);
                    if ( hMem )
                      LocalFree(hMem);
                    CloseHandle(hObject);
                    CloseHandle(v24);
                    CloseHandle(v72);
                    CloseHandle(v70);
                    CloseHandle(EventW);
                    v42 = (void *)phProv;
                    goto LABEL_90;
                  }
                  dwFlagsc = &Process;
                  WerfaultInProcessContext = CReflectedDumpServerLauncher::CreateWerfaultInProcessContext(
                                               v41,
                                               v15,
                                               v115);
                  if ( WerfaultInProcessContext < 0 )
                  {
                    v44 = retaddr;
                    v45 = (unsigned int)WerfaultInProcessContext;
                    v46 = 498;
LABEL_49:
                    wil::details::in1diag3::Return_Hr(
                      v44,
                      (void *)v46,
                      (unsigned int)"onecore\\windows\\feedback\\core\\wersvc\\lib\\reflectionserver.cpp",
                      (const char *)v45,
                      (int)dwFlagsc);
                    goto LABEL_50;
                  }
                  v47 = Process;
                  v97[0] = hObject;
                  v97[1] = v28 + 288;
                  v99 = v74;
                  v100 = v28 + 268;
                  v103 = v28 + 272;
                  v106 = v28 + 276;
                  v109 = v28 + 280;
                  v112 = v28 + 284;
                  v83[1] = v76;
                  v86 = v77;
                  v89 = v78;
                  v92 = v79;
                  v95 = v80;
                  v98 = 1048578;
                  v101 = 1052672;
                  v102 = EventW;
                  v104 = 0x100000;
                  v105 = v70;
                  v107 = 1048578;
                  v108 = v72;
                  v110 = 1048578;
                  v111 = phProv;
                  v113 = 2;
                  v83[0] = EventW;
                  v84 = 1048578;
                  v85 = v70;
                  v87 = 0x100000;
                  v88 = Process;
                  v90 = 0x100000;
                  v91 = v72;
                  v93 = 1048578;
                  v94 = phProv;
                  v96 = 4;
                  CurrentProcess = GetCurrentProcess();
                  v50 = CReflectedDumpServerLauncher::DuplicateHandlesHelper(
                          v49,
                          CurrentProcess,
                          v47,
                          (struct CReflectedDumpServerLauncher::HANDLE_DUPLICATION_INFO *)v97,
                          6u);
                  if ( v50 >= 0 )
                  {
                    v54 = GetCurrentProcess();
                    v50 = CReflectedDumpServerLauncher::DuplicateHandlesHelper(
                            v55,
                            v54,
                            v74,
                            (struct CReflectedDumpServerLauncher::HANDLE_DUPLICATION_INFO *)v83,
                            5u);
                    if ( v50 >= 0 )
                    {
                      v56 = hThread;
                      ResumeThread(hThread);
                      Handles[0] = Process;
                      Handles[1] = hObject;
                      v57 = WaitForMultipleObjectsEx(2u, Handles, 0, 0xEA60u, 0);
                      v44 = retaddr;
                      if ( !v57 )
                      {
                        v46 = 561;
                        v45 = 2147549183LL;
                        goto LABEL_49;
                      }
                      if ( v57 == 1 )
                      {
                        wil::details::in1diag3::Log_HrMsg(
                          retaddr,
                          (void *)0x238,
                          (unsigned int)"onecore\\windows\\feedback\\core\\wersvc\\lib\\reflectionserver.cpp",
                          (const char *)0x80000000LL,
                          (int)"Reflection server started successfully",
                          (const char *)&hThread);
                        UnmapViewOfFile(v28);
                        _InterlockedDecrement((volatile signed __int32 *)this);
                        if ( hMem )
                          LocalFree(hMem);
                        CloseHandle(hObject);
                        CloseHandle(v24);
                        CloseHandle(v72);
                        CloseHandle(v70);
                        CloseHandle(EventW);
                        CloseHandle((HANDLE)phProv);
                        if ( (unsigned __int64)v56 + 1 > 1 )
                          CloseHandle(v56);
                        if ( (unsigned __int64)Process + 1 > 1 )
                          CloseHandle(Process);
                        CloseHandle(v15);
                        return;
                      }
                      v51 = 565;
                      v52 = 2147549183LL;
LABEL_57:
                      wil::details::in1diag3::Return_Hr(
                        v44,
                        (void *)v51,
                        (unsigned int)"onecore\\windows\\feedback\\core\\wersvc\\lib\\reflectionserver.cpp",
                        (const char *)v52,
                        (int)dwFlagsc);
                      if ( Process )
                      {
                        ProcessId = GetProcessId(Process);
                        WerpAddTerminationReason(ProcessId, 4, L"WerReflectionServer");
                        NtTerminateProcess(Process, 0);
                      }
LABEL_50:
                      UnmapViewOfFile(v28);
                      _InterlockedDecrement((volatile signed __int32 *)this);
                      if ( hMem )
                        LocalFree(hMem);
                      CloseHandle(hObject);
                      CloseHandle(v24);
                      CloseHandle(v72);
                      CloseHandle(v70);
                      CloseHandle(EventW);
                      CloseHandle((HANDLE)phProv);
                      v42 = hThread;
                      if ( (unsigned __int64)hThread + 1 <= 1 )
                        goto LABEL_91;
                      goto LABEL_90;
                    }
                    v51 = 541;
                  }
                  else
                  {
                    v51 = 536;
                  }
                  v44 = retaddr;
                  v52 = (unsigned int)v50;
                  goto LABEL_57;
                }
                wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x1E3,
                  (unsigned int)"onecore\\windows\\feedback\\core\\wersvc\\lib\\reflectionserver.cpp",
                  v39);
                UnmapViewOfFile(v28);
                _InterlockedDecrement((volatile signed __int32 *)this);
                if ( hMem )
                  LocalFree(hMem);
                CloseHandle(hObject);
              }
              CloseHandle(v24);
              v58 = v72;
            }
            CloseHandle(v58);
            v59 = v70;
          }
          CloseHandle(v59);
          v42 = EventW;
LABEL_90:
          CloseHandle(v42);
LABEL_91:
          v60 = Process;
          v61 = (unsigned __int64)Process + 1 <= 1;
LABEL_92:
          if ( !v61 )
            CloseHandle(v60);
          v62 = v15;
          goto LABEL_107;
        }
        wil::details::in1diag3::Return_GetLastError(
          retaddr,
          (void *)0x1B5,
          (unsigned int)"onecore\\windows\\feedback\\core\\wersvc\\lib\\reflectionserver.cpp",
          v27);
        _InterlockedDecrement((volatile signed __int32 *)this);
        if ( hMem )
          LocalFree(hMem);
        CloseHandle(v24);
      }
      v60 = Process;
      v61 = (unsigned __int64)Process + 1 <= 1;
      goto LABEL_92;
    }
    wil::details::in1diag3::Return_GetLastError(
      retaddr,
      (void *)0x18F,
      (unsigned int)"onecore\\windows\\feedback\\core\\wersvc\\lib\\reflectionserver.cpp",
      v14);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x181,
      (unsigned int)"onecore\\windows\\feedback\\core\\wersvc\\lib\\reflectionserver.cpp",
      (const char *)0x80070057LL,
      dwFlags);
  }
  _InterlockedDecrement((volatile signed __int32 *)this);
LABEL_104:
  if ( hMem )
    LocalFree(hMem);
  v62 = Process;
  if ( (unsigned __int64)Process + 1 > 1 )
LABEL_107:
    CloseHandle(v62);
}

```

## disassembly

```asm
0x18001f040  mov     [rsp-8+arg_18], rbx
0x18001f045  push    rbp
0x18001f046  push    rsi
0x18001f047  push    rdi
0x18001f048  push    r12
0x18001f04a  push    r13
0x18001f04c  push    r14
0x18001f04e  push    r15
0x18001f050  lea     rbp, [rsp-270h]
0x18001f058  sub     rsp, 370h
0x18001f05f  mov     rax, cs:__security_cookie
0x18001f066  xor     rax, rsp
0x18001f069  mov     [rbp+2A0h+var_40], rax
0x18001f070  mov     rbx, [rbp+2A0h+arg_38]
0x18001f077  xor     eax, eax
0x18001f079  mov     rdi, [rbp+2A0h+arg_40]
0x18001f080  mov     r13d, r8d
0x18001f083  mov     rsi, [rbp+2A0h+arg_48]
0x18001f08a  mov     r15, rcx
0x18001f08d  mov     r14, [rbp+2A0h+arg_50]
0x18001f094  lea     rcx, [rbp+2A0h+var_140]; void *
0x18001f09b  mov     r12, [rbp+2A0h+arg_58]
0x18001f0a2  mov     r8d, 100h; Size
0x18001f0a8  mov     [rsp+3A0h+var_338], rdx
0x18001f0ad  xor     edx, edx; Val
0x18001f0af  mov     [rsp+3A0h+var_328], rbx
0x18001f0b4  mov     [rbp+2A0h+var_320], rdi
0x18001f0b8  mov     [rbp+2A0h+var_318], rsi
0x18001f0bc  mov     [rbp+2A0h+var_310], r14
0x18001f0c0  mov     [rbp+2A0h+var_308], r12
0x18001f0c4  mov     [rsp+3A0h+Process], rax
0x18001f0c9  mov     [rsp+3A0h+hThread], rax
0x18001f0ce  mov     dword ptr [rsp+3A0h+var_358], r9d
0x18001f0d3  call    memset_0
0x18001f0d8  xor     edx, edx; Val
0x18001f0da  lea     rcx, [rbp+2A0h+Name]; void *
0x18001f0e1  mov     r8d, 80h; Size
0x18001f0e7  call    memset_0
0x18001f0ec  xor     ecx, ecx
0x18001f0ee  xorps   xmm0, xmm0
0x18001f0f1  xor     eax, eax
0x18001f0f3  mov     qword ptr [rsp+3A0h+pbBuffer], rcx
0x18001f0f8  xorps   xmm1, xmm1
0x18001f0fb  mov     qword ptr [rbp+2A0h+FileMappingAttributes.bInheritHandle], rax
0x18001f0ff  movups  xmmword ptr [rbp+2A0h+Handles], xmm0
0x18001f103  lea     eax, [rcx+1]
0x18001f106  mov     [rsp+3A0h+hMem], rcx
0x18001f10b  movups  xmmword ptr [rbp+2A0h+FileMappingAttributes.nLength], xmm1
0x18001f10f  lock xadd [r15], eax
0x18001f114  inc     eax
0x18001f116  cmp     eax, 1
0x18001f119  jbe     short loc_18001F140
0x18001f11b  mov     rcx, [rbp+2A8h]; this
0x18001f122  lea     r8, aOnecoreWindows_1
0x18001f129  mov     ebx, 800700AAh
0x18001f12e  mov     edx, 175h; void *
0x18001f133  mov     r9d, ebx; char *
0x18001f136  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x18001f13b  jmp     loc_18001FAD4
0x18001f140  cmp     [rsp+3A0h+var_338], rcx
0x18001f145  jz      loc_18001FAB0
0x18001f14b  test    r13d, r13d
0x18001f14e  jz      loc_18001FAB0
0x18001f154  test    rbx, rbx
0x18001f157  jz      loc_18001FAB0
0x18001f15d  test    rdi, rdi
0x18001f160  jz      loc_18001FAB0
0x18001f166  test    rsi, rsi
0x18001f169  jz      loc_18001FAB0
0x18001f16f  test    r14, r14
0x18001f172  jz      loc_18001FAB0
0x18001f178  test    r12, r12
0x18001f17b  jz      loc_18001FAB0
0x18001f181  mov     [rbx], rcx
0x18001f184  mov     r8d, r13d; dwProcessId
0x18001f187  mov     [rdi], rcx
0x18001f18a  xor     edx, edx; bInheritHandle
0x18001f18c  xor     edi, edi
0x18001f18e  mov     ecx, 400h; dwDesiredAccess
0x18001f193  mov     [rsi], rdi
0x18001f196  mov     [r14], rdi
0x18001f199  mov     [r12], rdi
0x18001f19d  call    cs:__imp_OpenProcess
0x18001f1a3  mov     r14, rax
0x18001f1a6  inc     rax
0x18001f1a9  cmp     rax, 1
0x18001f1ad  jbe     loc_18001FA94
0x18001f1b3  lea     r9d, [rdi+1]; dwProvType
0x18001f1b7  mov     [rsp+3A0h+phProv], rdi
0x18001f1bc  xor     r8d, r8d; szProvider
0x18001f1bf  mov     [rsp+3A0h+dwFlags], 0F0000000h; int
0x18001f1c7  xor     edx, edx; szContainer
0x18001f1c9  lea     rcx, [rsp+3A0h+phProv]; phProv
0x18001f1ce  call    cs:__imp_CryptAcquireContextW
0x18001f1d4  lea     r12, aOnecoreWindows_1
0x18001f1db  test    eax, eax
0x18001f1dd  jnz     short loc_18001F1E4
0x18001f1df  lea     edx, [rdi+36h]
0x18001f1e2  jmp     short loc_18001F200
0x18001f1e4  mov     rcx, [rsp+3A0h+phProv]; hProv
0x18001f1e9  lea     r8, [rsp+3A0h+pbBuffer]; pbBuffer
0x18001f1ee  mov     edx, 8; dwLen
0x18001f1f3  call    cs:__imp_CryptGenRandom
0x18001f1f9  test    eax, eax
0x18001f1fb  jnz     short loc_18001F25B
0x18001f1fd  lea     edx, [rax+38h]; void *
0x18001f200  mov     rcx, [rbp+2A8h]; this
0x18001f207  mov     r8, r12; unsigned int
0x18001f20a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z
0x18001f20f  mov     rcx, [rsp+3A0h+phProv]; hProv
0x18001f214  mov     ebx, eax
0x18001f216  test    rcx, rcx
0x18001f219  jz      short loc_18001F223
0x18001f21b  xor     edx, edx; dwFlags
0x18001f21d  call    cs:__imp_CryptReleaseContext
0x18001f223  test    ebx, ebx
0x18001f225  jns     short loc_18001F26D
0x18001f227  mov     r9d, ebx; char *
0x18001f22a  mov     edx, 195h; void *
0x18001f22f  mov     rcx, [rbp+2A8h]; this
0x18001f236  mov     r8, r12; unsigned int
0x18001f239  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x18001f23e  lock dec dword ptr [r15]
0x18001f242  mov     rcx, [rsp+3A0h+hMem]; hMem
0x18001f247  test    rcx, rcx
0x18001f24a  jz      loc_18001FA09
0x18001f250  call    cs:__imp_LocalFree
0x18001f256  jmp     loc_18001FA09
0x18001f25b  mov     rcx, [rsp+3A0h+phProv]; hProv
0x18001f260  test    rcx, rcx
0x18001f263  jz      short loc_18001F26D
0x18001f265  xor     edx, edx; dwFlags
0x18001f267  call    cs:__imp_CryptReleaseContext
0x18001f26d  mov     r9, qword ptr [rsp+3A0h+pbBuffer]
0x18001f272  lea     r8, aGlobalI64x
0x18001f279  mov     edx, 40h ; '@'; unsigned __int64
0x18001f27e  lea     rcx, [rbp+2A0h+Name]; wchar_t *
0x18001f285  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ
0x18001f28a  mov     ebx, eax
0x18001f28c  test    eax, eax
0x18001f28e  jns     short loc_18001F29A
0x18001f290  mov     r9d, eax
0x18001f293  mov     edx, 19Ah
0x18001f298  jmp     short loc_18001F22F
0x18001f29a  lea     r9, [rbp+2A0h+FileMappingAttributes]
0x18001f29e  mov     rdx, r14
0x18001f2a1  lea     r8, [rsp+3A0h+hMem]
0x18001f2a6  call    ?GetAdminAllAccessProcessReadOnlyAcl@CReflectedDumpServerLauncher@@AEAAJPEAXAEAV?$unique_ptr@XU?$generic_delete@XU?$generic_deallocate@$MP6APEAXPEAX@Z1?LocalFree@@YAPEAX0@ZPEAX@tlx@@@tlx@@@utl@@PEAU_SECURITY_ATTRIBUTES@@@Z
0x18001f2ab  mov     ebx, eax
0x18001f2ad  test    eax, eax
0x18001f2af  jns     short loc_18001F2BE
0x18001f2b1  mov     r9d, eax
0x18001f2b4  mov     edx, 1A0h
0x18001f2b9  jmp     loc_18001F22F
0x18001f2be  xor     r9d, r9d; dwMaximumSizeHigh
0x18001f2c1  lea     rax, [rbp+2A0h+Name]
0x18001f2c8  mov     [rsp+3A0h+lpName], rax; lpName
0x18001f2cd  lea     rdx, [rbp+2A0h+FileMappingAttributes]; lpFileMappingAttributes
0x18001f2d1  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x18001f2d5  mov     [rsp+3A0h+dwFlags], 248h; dwMaximumSizeLow
0x18001f2dd  lea     r8d, [r9+4]; flProtect
0x18001f2e1  call    cs:__imp_CreateFileMappingW
0x18001f2e7  mov     rsi, rax
0x18001f2ea  mov     ebx, 1
0x18001f2ef  inc     rax
0x18001f2f2  cmp     rax, rbx
0x18001f2f5  jbe     loc_18001FA5B
0x18001f2fb  xor     r9d, r9d; dwFileOffsetLow
0x18001f2fe  mov     qword ptr [rsp+3A0h+dwFlags], 248h; int
0x18001f307  xor     r8d, r8d; dwFileOffsetHigh
0x18001f30a  lea     edx, [rbx+1]; dwDesiredAccess
0x18001f30d  mov     rcx, rsi; hFileMappingObject
0x18001f310  call    cs:__imp_MapViewOfFile
0x18001f316  xor     r10d, r10d
0x18001f319  mov     rdi, rax
0x18001f31c  test    rax, rax
0x18001f31f  jz      loc_18001FA26
0x18001f325  mov     [rax], r13d
0x18001f328  lea     r8, [rdi+10h]
0x18001f32c  mov     eax, dword ptr [rsp+3A0h+var_358]
0x18001f330  mov     [rdi+4], eax
0x18001f333  mov     eax, [rbp+2A0h+arg_20]
0x18001f339  mov     [rdi+8], eax
0x18001f33c  mov     eax, [rbp+2A0h+arg_28]
0x18001f342  mov     [rdi+0Ch], eax
0x18001f345  mov     rax, [rbp+2A0h+arg_30]
0x18001f34c  mov     [r8], r10w
0x18001f350  test    rax, rax
0x18001f353  jz      short loc_18001F3C4
0x18001f355  mov     ecx, 7FFFFFFEh
0x18001f35a  mov     edx, 104h
0x18001f35f  test    rcx, rcx
0x18001f362  jz      short loc_18001F382
0x18001f364  movzx   r9d, word ptr [rax]
0x18001f368  test    r9w, r9w
0x18001f36c  jz      short loc_18001F382
0x18001f36e  mov     [r8], r9w
0x18001f372  add     rax, 2
0x18001f376  add     r8, 2
0x18001f37a  sub     rcx, rbx
0x18001f37d  sub     rdx, rbx
0x18001f380  jnz     short loc_18001F35F
0x18001f382  mov     rax, rdx
0x18001f385  lea     rcx, [r8-2]
0x18001f389  neg     rax
0x18001f38c  sbb     ebx, ebx
0x18001f38e  not     ebx
0x18001f390  and     ebx, 8007007Ah
0x18001f396  test    rdx, rdx
0x18001f399  cmovnz  rcx, r8
0x18001f39d  mov     [rcx], r10w
0x18001f3a1  jnz     short loc_18001F3BF
0x18001f3a3  mov     rcx, [rbp+2A8h]; this
0x18001f3aa  mov     r9d, ebx; char *
0x18001f3ad  mov     r8, r12; unsigned int
0x18001f3b0  mov     edx, 1C7h; void *
0x18001f3b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x18001f3ba  jmp     loc_18001F9E3
0x18001f3bf  mov     ebx, 1
0x18001f3c4  xor     r9d, r9d; lpName
0x18001f3c7  xor     r8d, r8d; bInitialState
0x18001f3ca  mov     edx, ebx; bManualReset
0x18001f3cc  xor     ecx, ecx; lpEventAttributes
0x18001f3ce  call    cs:__imp_CreateEventW
0x18001f3d4  mov     r13, rax
0x18001f3d7  lea     rcx, [rax+1]
0x18001f3db  cmp     rcx, rbx
0x18001f3de  jbe     loc_18001F9CD
0x18001f3e4  xor     r9d, r9d; lpName
0x18001f3e7  xor     r8d, r8d; bInitialState
0x18001f3ea  mov     edx, ebx; bManualReset
0x18001f3ec  xor     ecx, ecx; lpEventAttributes
0x18001f3ee  call    cs:__imp_CreateEventW
0x18001f3f4  mov     [rsp+3A0h+var_358], rax
0x18001f3f9  lea     rcx, [rax+1]
0x18001f3fd  cmp     rcx, rbx
0x18001f400  jbe     loc_18001F992
0x18001f406  xor     r9d, r9d; lpName
0x18001f409  xor     r8d, r8d; bInitialState
0x18001f40c  mov     edx, ebx; bManualReset
0x18001f40e  xor     ecx, ecx; lpEventAttributes
0x18001f410  call    cs:__imp_CreateEventW
0x18001f416  mov     [rsp+3A0h+var_348], rax
0x18001f41b  lea     rcx, [rax+1]
0x18001f41f  cmp     rcx, rbx
0x18001f422  jbe     loc_18001F957
0x18001f428  xor     r9d, r9d; lpName
0x18001f42b  xor     r8d, r8d; bInitialState
0x18001f42e  mov     edx, ebx; bManualReset
0x18001f430  xor     ecx, ecx; lpEventAttributes
0x18001f432  call    cs:__imp_CreateEventW
0x18001f438  mov     [rsp+3A0h+hObject], rax
0x18001f43d  lea     rcx, [rax+1]
0x18001f441  cmp     rcx, rbx
0x18001f444  jbe     loc_18001F922
0x18001f44a  xor     r9d, r9d; dwMaximumSizeHigh
0x18001f44d  mov     [rsp+3A0h+lpName], 0; lpName
0x18001f456  lea     rdx, [rbp+2A0h+FileMappingAttributes]; lpFileMappingAttributes
0x18001f45a  mov     [rsp+3A0h+dwFlags], 218h; dwMaximumSizeLow
0x18001f462  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x18001f466  lea     r8d, [r9+4]; flProtect
0x18001f46a  call    cs:__imp_CreateFileMappingW
0x18001f470  mov     [rsp+3A0h+phProv], rax
0x18001f475  lea     rcx, [rax+1]
0x18001f479  cmp     rcx, rbx
0x18001f47c  jbe     loc_18001F8BD
0x18001f482  lea     rax, [rbp+2A0h+Name]
0x18001f489  mov     edx, 80h; unsigned __int64
0x18001f48e  lea     r9, aPr
0x18001f495  mov     qword ptr [rsp+3A0h+dwFlags], rax; int
0x18001f49a  lea     r8, aSS_0
0x18001f4a1  lea     rcx, [rbp+2A0h+var_140]; wchar_t *
0x18001f4a8  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ
0x18001f4ad  mov     ebx, eax
0x18001f4af  test    eax, eax
0x18001f4b1  jns     short loc_18001F524
0x18001f4b3  mov     rcx, [rbp+2A8h]; this
0x18001f4ba  mov     r9d, eax; char *
0x18001f4bd  mov     r8, r12; unsigned int
0x18001f4c0  mov     edx, 1ECh; void *
0x18001f4c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x18001f4ca  mov     rcx, rdi; lpBaseAddress
0x18001f4cd  call    cs:__imp_UnmapViewOfFile
0x18001f4d3  lock dec dword ptr [r15]
0x18001f4d7  mov     rcx, [rsp+3A0h+hMem]; hMem
0x18001f4dc  test    rcx, rcx
0x18001f4df  jz      short loc_18001F4E7
0x18001f4e1  call    cs:__imp_LocalFree
0x18001f4e7  mov     rcx, [rsp+3A0h+hObject]; hObject
0x18001f4ec  call    cs:__imp_CloseHandle
0x18001f4f2  mov     rcx, rsi; hObject
0x18001f4f5  call    cs:__imp_CloseHandle
0x18001f4fb  mov     rcx, [rsp+3A0h+var_348]; hObject
0x18001f500  call    cs:__imp_CloseHandle
0x18001f506  mov     rcx, [rsp+3A0h+var_358]; hObject
0x18001f50b  call    cs:__imp_CloseHandle
0x18001f511  mov     rcx, r13; hObject
0x18001f514  call    cs:__imp_CloseHandle
0x18001f51a  mov     rcx, [rsp+3A0h+phProv]
0x18001f51f  jmp     loc_18001FA03
  ... truncated ...
```
