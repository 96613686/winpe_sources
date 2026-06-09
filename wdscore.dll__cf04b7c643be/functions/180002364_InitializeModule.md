# InitializeModule

- ea: `0x180002364`
- end: `0x1800026f4`
- name: `InitializeModule`
- size: `912`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, installer_update`

## callers

- `0x1800027dc`
- `0x180003958`

## callees

- `0x180002250`
- `0x180002364`
- `0x18000720c`
- `0x1800076a4`
- `0x180008a6c`
- `0x18001dc70`
- `0x180021e28`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800026be`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027a0b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800026be`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027a0b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800026aa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800279f7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800026aa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800279f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800023b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002464`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002503`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800025b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800023b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002464`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002503`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800025b5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800026d1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027a26`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800026d1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027a26`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000258e`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000258e`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800024e3`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800024e3`

## pseudocode

```c
__int64 __fastcall InitializeModule(__int64 a1, __int64 a2, unsigned int a3)
{
  unsigned int v3; // esi
  unsigned int v6; // r12d
  CHAR *v7; // r15
  DWORD LastError; // ebx
  int *v9; // rax
  DWORD v10; // ebx
  int *v11; // rcx
  HMODULE Library; // rax
  DWORD v13; // ebx
  int *v14; // rcx
  const CHAR *v15; // rax
  FARPROC ProcAddress; // rax
  const char *v17; // rbx
  DWORD v18; // edi
  int *v19; // rcx
  __int64 NonDeletedItem; // rax
  __int64 v21; // rax
  HANDLE ProcessHeap; // rax
  __int128 v24; // [rsp+68h] [rbp-60h] BYREF
  __int128 v25; // [rsp+78h] [rbp-50h]
  __int64 v26; // [rsp+88h] [rbp-40h]
  LPCWSTR lpModuleName; // [rsp+C8h] [rbp+0h]

  v3 = a3;
  v6 = 3;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  v7 = 0;
  LastError = GetLastError();
  v9 = (int *)ConstructPartialMsgW(0x4000000u, "InitializeModule: Initializing ExecQueue->csLock;");
  WdsSetupLogMessageW(
    v9,
    589824,
    (__int64)L"D",
    0,
    0x208u,
    L"onecore\\base\\ntsetup\\panther\\engine\\seq.c",
    L"InitializeModule",
    lpModuleName,
    LastError,
    0,
    0);
  pLock(a1);
  if ( *(_QWORD *)(a2 + 1648) )
  {
LABEL_11:
    *(_QWORD *)(a2 + 1656) = 0;
    if ( *(_DWORD *)(a1 + 136) && (NonDeletedItem = privateGetNonDeletedItem(**(_QWORD **)(a1 + 56), 1)) != 0 )
      v21 = *(_QWORD *)(NonDeletedItem + 48);
    else
      v21 = 0;
    *(_QWORD *)&v25 = v21;
    *((_QWORD *)&v25 + 1) = *(_QWORD *)(a2 + 1608);
    *(_QWORD *)&v24 = a2 + 44;
    *((_QWORD *)&v24 + 1) = a2 + 564;
    LODWORD(v26) = *(_DWORD *)(a1 + 140);
    v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int128 *, __int64))(a2 + 1648))(a2, v3, &v24, a2 + 1656);
    goto LABEL_16;
  }
  if ( !(unsigned int)pResolveBinaryName(a1, a2 + 44, a2 + 564, a2 + 1084) )
  {
    v10 = GetLastError();
    v11 = (int *)ConstructPartialMsgW(0x300006Au, "Failed to resolve binary for module '%s'", (const char *)(a2 + 44));
    WdsSetupLogMessageW(
      v11,
      589824,
      (__int64)L"D",
      0,
      0x221u,
      L"onecore\\base\\ntsetup\\panther\\engine\\seq.c",
      L"InitializeModule",
      lpModuleName,
      v10,
      0,
      0);
    goto LABEL_16;
  }
  Library = LoadLibraryExW((LPCWSTR)(a2 + 1084), 0, 8u);
  *(_QWORD *)(a2 + 1624) = Library;
  if ( !Library )
  {
    v13 = GetLastError();
    v14 = (int *)ConstructPartialMsgW(0x200006Bu, "InitializeModule - Failed to load %s", (const char *)(a2 + 1084));
    WdsSetupLogMessageW(
      v14,
      589824,
      (__int64)L"D",
      0,
      0x22Au,
      L"onecore\\base\\ntsetup\\panther\\engine\\seq.c",
      L"InitializeModule",
      lpModuleName,
      v13,
      0,
      0);
    goto LABEL_16;
  }
  v15 = (const CHAR *)ConvertWtoA(*(_QWORD *)(a2 + 1616));
  v7 = (CHAR *)v15;
  if ( v15 )
  {
    ProcAddress = GetProcAddress(*(HMODULE *)(a2 + 1624), v15);
    *(_QWORD *)(a2 + 1648) = ProcAddress;
    if ( !ProcAddress )
    {
      v17 = *(const char **)(a2 + 1616);
      v18 = GetLastError();
      v19 = (int *)ConstructPartialMsgW(0x200006Cu, "InitializeModule - Failed to find entry point %s", v17);
      WdsSetupLogMessageW(
        v19,
        589824,
        (__int64)L"D",
        0,
        0x237u,
        L"onecore\\base\\ntsetup\\panther\\engine\\seq.c",
        L"InitializeModule",
        lpModuleName,
        v18,
        0,
        0);
      goto LABEL_16;
    }
    v3 = a3;
    goto LABEL_11;
  }
LABEL_16:
  if ( v7 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v7);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 184));
  return v6;
}

```

## disassembly

```asm
0x180002364  mov     r11, rsp
0x180002367  mov     [r11+18h], r8d
0x18000236b  mov     [r11+8], rcx
0x18000236f  push    rbx
0x180002370  push    rsi
0x180002371  push    rdi
0x180002372  push    r12
0x180002374  push    r13
0x180002376  push    r14
0x180002378  push    r15
0x18000237a  sub     rsp, 90h
0x180002381  mov     esi, r8d
0x180002384  mov     r14, rdx
0x180002387  mov     r13, rcx
0x18000238a  mov     r12d, 3
0x180002390  xorps   xmm0, xmm0
0x180002393  xor     eax, eax
0x180002395  movups  [rsp+0C8h+var_60], xmm0
0x18000239a  movups  [rsp+0C8h+var_50], xmm0
0x18000239f  mov     [r11-40h], rax
0x1800023a3  xor     r15d, r15d
0x1800023a6  mov     [r11-68h], r15
0x1800023aa  mov     rdi, [rsp+0C8h]
0x1800023b2  call    cs:__imp_GetLastError
0x1800023b9  nop     dword ptr [rax+rax+00h]
0x1800023be  mov     ebx, eax
0x1800023c0  lea     rdx, aInitializemodu; "InitializeModule: Initializing ExecQueu"...
0x1800023c7  mov     ecx, 4000000h; unsigned int
0x1800023cc  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800023d1  mov     rcx, rax; int
0x1800023d4  mov     [rsp+0C8h+var_78], r15d; int
0x1800023d9  mov     [rsp+0C8h+var_80], r15; __int64
0x1800023de  mov     [rsp+0C8h+var_88], ebx; int
0x1800023e2  mov     [rsp+0C8h+lpModuleName], rdi; lpModuleName
0x1800023e7  lea     rax, aInitializemodu_2; "InitializeModule"
0x1800023ee  mov     [rsp+0C8h+var_98], rax; __int64
0x1800023f3  lea     rax, aOnecoreBaseNts_3; "onecore\\base\\ntsetup\\panther\\engine"...
0x1800023fa  mov     [rsp+0C8h+var_A0], rax; unsigned __int16 *
0x1800023ff  mov     [rsp+0C8h+var_A8], 208h; int
0x180002407  xor     r9d, r9d; int
0x18000240a  lea     r8, aD_1; "D"
0x180002411  mov     edx, 90000h; int
0x180002416  call    WdsSetupLogMessageW
0x18000241b  mov     rcx, r13
0x18000241e  call    pLock
0x180002423  lea     rdi, [r14+2Ch]
0x180002427  mov     [rsp+0C8h+arg_18], rdi
0x18000242f  cmp     [r14+670h], r15
0x180002436  jnz     loc_180002620
0x18000243c  lea     rsi, [r14+43Ch]
0x180002443  mov     r9, rsi
0x180002446  lea     r8, [r14+234h]
0x18000244d  mov     rdx, rdi
0x180002450  mov     rcx, r13
0x180002453  call    pResolveBinaryName
0x180002458  test    eax, eax
0x18000245a  jnz     short loc_1800024DA
0x18000245c  mov     rdi, [rsp+0C8h]
0x180002464  call    cs:__imp_GetLastError
0x18000246b  nop     dword ptr [rax+rax+00h]
0x180002470  mov     ebx, eax
0x180002472  mov     r8, [rsp+0C8h+arg_18]
0x18000247a  lea     rdx, aFailedToResolv; "Failed to resolve binary for module '%s"...
0x180002481  mov     ecx, 300006Ah; unsigned int
0x180002486  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000248b  mov     rcx, rax; int
0x18000248e  mov     [rsp+0C8h+var_78], r15d; int
0x180002493  mov     [rsp+0C8h+var_80], r15; __int64
0x180002498  mov     [rsp+0C8h+var_88], ebx; int
0x18000249c  mov     [rsp+0C8h+lpModuleName], rdi; lpModuleName
0x1800024a1  lea     rax, aInitializemodu_2; "InitializeModule"
0x1800024a8  mov     [rsp+0C8h+var_98], rax; __int64
0x1800024ad  lea     rax, aOnecoreBaseNts_3; "onecore\\base\\ntsetup\\panther\\engine"...
0x1800024b4  mov     [rsp+0C8h+var_A0], rax; unsigned __int16 *
0x1800024b9  mov     [rsp+0C8h+var_A8], 221h; int
0x1800024c1  xor     r9d, r9d; int
0x1800024c4  lea     r8, aD_1; "D"
0x1800024cb  mov     edx, 90000h; int
0x1800024d0  call    WdsSetupLogMessageW
0x1800024d5  jmp     loc_1800026A5
0x1800024da  xor     edx, edx; hFile
0x1800024dc  lea     r8d, [rdx+8]; dwFlags
0x1800024e0  mov     rcx, rsi; lpLibFileName
0x1800024e3  call    cs:__imp_LoadLibraryExW
0x1800024ea  nop     dword ptr [rax+rax+00h]
0x1800024ef  mov     [r14+658h], rax
0x1800024f6  test    rax, rax
0x1800024f9  jnz     short loc_180002567
0x1800024fb  mov     rdi, [rsp+0C8h]
0x180002503  call    cs:__imp_GetLastError
0x18000250a  nop     dword ptr [rax+rax+00h]
0x18000250f  mov     ebx, eax
0x180002511  mov     r8, rsi
0x180002514  lea     rdx, aInitializemodu_0; "InitializeModule - Failed to load %s"
0x18000251b  mov     ecx, 200006Bh; unsigned int
0x180002520  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180002525  mov     rcx, rax
0x180002528  mov     [rsp+0C8h+var_78], 0
0x180002530  mov     [rsp+0C8h+var_80], 0
0x180002539  mov     [rsp+0C8h+var_88], ebx
0x18000253d  mov     [rsp+0C8h+lpModuleName], rdi
0x180002542  lea     rax, aInitializemodu_2; "InitializeModule"
0x180002549  mov     [rsp+0C8h+var_98], rax
0x18000254e  lea     rax, aOnecoreBaseNts_3; "onecore\\base\\ntsetup\\panther\\engine"...
0x180002555  mov     [rsp+0C8h+var_A0], rax
0x18000255a  mov     [rsp+0C8h+var_A8], 22Ah
0x180002562  jmp     loc_1800024C1
0x180002567  mov     rcx, [r14+650h]
0x18000256e  call    ConvertWtoA
0x180002573  mov     r15, rax
0x180002576  mov     [rsp+0C8h+var_68], rax
0x18000257b  test    rax, rax
0x18000257e  jz      loc_1800026A5
0x180002584  mov     rdx, rax; lpProcName
0x180002587  mov     rcx, [r14+658h]; hModule
0x18000258e  call    cs:__imp_GetProcAddress
0x180002595  nop     dword ptr [rax+rax+00h]
0x18000259a  mov     [r14+670h], rax
0x1800025a1  test    rax, rax
0x1800025a4  jnz     short loc_180002619
0x1800025a6  mov     rsi, [rsp+0C8h]
0x1800025ae  mov     rbx, [r14+650h]
0x1800025b5  call    cs:__imp_GetLastError
0x1800025bc  nop     dword ptr [rax+rax+00h]
0x1800025c1  mov     edi, eax
0x1800025c3  mov     r8, rbx
0x1800025c6  lea     rdx, aInitializemodu_1; "InitializeModule - Failed to find entry"...
0x1800025cd  mov     ecx, 200006Ch; unsigned int
0x1800025d2  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800025d7  mov     rcx, rax
0x1800025da  mov     [rsp+0C8h+var_78], 0
0x1800025e2  mov     [rsp+0C8h+var_80], 0
0x1800025eb  mov     [rsp+0C8h+var_88], edi
0x1800025ef  mov     [rsp+0C8h+lpModuleName], rsi
0x1800025f4  lea     rax, aInitializemodu_2; "InitializeModule"
0x1800025fb  mov     [rsp+0C8h+var_98], rax
0x180002600  lea     rax, aOnecoreBaseNts_3; "onecore\\base\\ntsetup\\panther\\engine"...
0x180002607  mov     [rsp+0C8h+var_A0], rax
0x18000260c  mov     [rsp+0C8h+var_A8], 237h
0x180002614  jmp     loc_1800024C1
0x180002619  mov     esi, [rsp+0C8h+arg_10]
0x180002620  lea     rbx, [r14+678h]
0x180002627  mov     qword ptr [rbx], 0
0x18000262e  cmp     dword ptr [r13+88h], 0
0x180002636  jz      short loc_180002654
0x180002638  mov     rcx, [r13+38h]
0x18000263c  mov     edx, 1
0x180002641  mov     rcx, [rcx]
0x180002644  call    privateGetNonDeletedItem
0x180002649  test    rax, rax
0x18000264c  jz      short loc_180002654
0x18000264e  mov     rax, [rax+30h]
0x180002652  jmp     short loc_180002656
0x180002654  xor     eax, eax
0x180002656  mov     qword ptr [rsp+0C8h+var_50], rax
0x18000265b  mov     rax, [r14+648h]
0x180002662  mov     qword ptr [rsp+0C8h+var_50+8], rax
0x18000266a  mov     qword ptr [rsp+0C8h+var_60], rdi
0x18000266f  lea     rax, [r14+234h]
0x180002676  mov     qword ptr [rsp+0C8h+var_60+8], rax
0x18000267b  mov     eax, [r13+8Ch]
0x180002682  mov     dword ptr [rsp+0C8h+var_40], eax
0x180002689  mov     r9, rbx
0x18000268c  lea     r8, [rsp+0C8h+var_60]
0x180002691  mov     edx, esi
0x180002693  mov     rcx, r14
0x180002696  mov     rax, [r14+670h]
0x18000269d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026a2  mov     r12d, eax
0x1800026a5  test    r15, r15
0x1800026a8  jz      short loc_1800026CA
0x1800026aa  call    cs:__imp_GetProcessHeap
0x1800026b1  nop     dword ptr [rax+rax+00h]
0x1800026b6  mov     rcx, rax; hHeap
0x1800026b9  mov     r8, r15; lpMem
0x1800026bc  xor     edx, edx; dwFlags
0x1800026be  call    cs:__imp_HeapFree
0x1800026c5  nop     dword ptr [rax+rax+00h]
0x1800026ca  lea     rcx, [r13+0B8h]; lpCriticalSection
0x1800026d1  call    cs:__imp_LeaveCriticalSection
0x1800026d8  nop     dword ptr [rax+rax+00h]
0x1800026dd  mov     eax, r12d
0x1800026e0  add     rsp, 90h
0x1800026e7  pop     r15
0x1800026e9  pop     r14
0x1800026eb  pop     r13
0x1800026ed  pop     r12
0x1800026ef  pop     rdi
0x1800026f0  pop     rsi
0x1800026f1  pop     rbx
0x1800026f2  retn
0x1800279e4  push    rbx
0x1800279e6  push    rbp
0x1800279e7  sub     rsp, 68h
0x1800279eb  mov     rbp, rdx
0x1800279ee  mov     rbx, [rbp+60h]
0x1800279f2  test    rbx, rbx
0x1800279f5  jz      short loc_180027A18
0x1800279f7  call    cs:__imp_GetProcessHeap
0x1800279fe  nop     dword ptr [rax+rax+00h]
0x180027a03  mov     rcx, rax; hHeap
0x180027a06  mov     r8, rbx; lpMem
0x180027a09  xor     edx, edx; dwFlags
0x180027a0b  call    cs:__imp_HeapFree
0x180027a12  nop     dword ptr [rax+rax+00h]
0x180027a17  nop
0x180027a18  mov     rcx, [rbp+0D0h]
0x180027a1f  add     rcx, 0B8h; lpCriticalSection
0x180027a26  call    cs:__imp_LeaveCriticalSection
0x180027a2d  nop     dword ptr [rax+rax+00h]
0x180027a32  nop
0x180027a33  add     rsp, 68h
0x180027a37  pop     rbp
0x180027a38  pop     rbx
0x180027a39  retn
```
