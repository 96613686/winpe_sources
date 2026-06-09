# InitializeWSDChallenge(void)

- ea: `0x18001f0d0`
- end: `0x18001f60d`
- name: `?InitializeWSDChallenge@@YAJXZ`
- size: `1341`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001f0a0`

## callees

- `0x18000ac34`
- `0x18000cba0`
- `0x18000d770`
- `0x18000d7b0`
- `0x18000da10`
- `0x18001f0d0`
- `0x180021fc0`
- `0x18002c868`
- `0x18002c8b0`
- `0x18002de18`
- `0x18002def8`
- `0x180033cc0`
- `0x180034658`
- `0x18003b64c`
- `0x180078010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001f5e1`
- `KERNEL32!LeaveCriticalSection` at `0x18001f5e1`
- `KERNEL32!LoadLibraryExW` at `0x18001f279`
- `KERNEL32!LoadLibraryExW` at `0x18001f279`
- `KERNEL32!GetSystemDirectoryW` at `0x18001f234`
- `KERNEL32!GetSystemDirectoryW` at `0x18001f234`
- `KERNEL32!GetLastError` at `0x18001f23e`
- `KERNEL32!GetLastError` at `0x18001f28b`
- `KERNEL32!GetLastError` at `0x18001f322`
- `KERNEL32!GetLastError` at `0x18001f3b6`
- `KERNEL32!GetLastError` at `0x18001f443`
- `KERNEL32!GetLastError` at `0x18001f23e`
- `KERNEL32!GetLastError` at `0x18001f28b`
- `KERNEL32!GetLastError` at `0x18001f322`
- `KERNEL32!GetLastError` at `0x18001f3b6`
- `KERNEL32!GetLastError` at `0x18001f443`
- `KERNEL32!GetProcAddress` at `0x18001f314`
- `KERNEL32!GetProcAddress` at `0x18001f3a4`
- `KERNEL32!GetProcAddress` at `0x18001f435`
- `KERNEL32!GetProcAddress` at `0x18001f314`
- `KERNEL32!GetProcAddress` at `0x18001f3a4`
- `KERNEL32!GetProcAddress` at `0x18001f435`

## string_xrefs

- `0x18001f2ac`: `LoadLibraryEx(%ws) failed (0x%08X), hr = 0x%08X`
- `0x18001f2d9`: `LoadLibraryEx(%ws) failed (0x%08X), hr = 0x%08X`
- `0x18001f1e4`: `Load WSD Challenge DLL...`
- `0x18001f20a`: `Load WSD Challenge DLL...`

## pseudocode

```c
__int64 InitializeWSDChallenge(void)
{
  signed int v0; // edi
  char *v1; // rbx
  void *v2; // rdx
  void *lpMem; // rax
  int v4; // edx
  int v5; // ecx
  int v6; // r15d
  char *v7; // rbx
  void *v8; // rdx
  void *v9; // rax
  int v10; // edx
  int v11; // ecx
  HMODULE Library; // rax
  char *v13; // rbx
  void *v14; // rdx
  void *v15; // rax
  int v16; // edx
  int v17; // ecx
  unsigned __int64 v18; // rdx
  const unsigned __int16 *v19; // r8
  signed int LastError; // eax
  signed int v21; // eax
  unsigned int v22; // esi
  char *v23; // rbx
  void *v24; // rdx
  void *v25; // rax
  int v26; // edx
  int v27; // ecx
  __int64 (*ProcAddress)(void); // r14
  signed int v29; // eax
  unsigned int v30; // esi
  char *v31; // rbx
  void *v32; // rdx
  void *v33; // rax
  int v34; // edx
  int v35; // ecx
  signed int v36; // eax
  unsigned int v37; // esi
  char *v38; // rbx
  void *v39; // rdx
  void *v40; // rax
  int v41; // edx
  int v42; // ecx
  FARPROC v43; // rbp
  signed int v44; // eax
  unsigned int v45; // esi
  char *v46; // rbx
  void *v47; // rdx
  void *v48; // rax
  int v49; // edx
  int v50; // ecx
  char *v51; // rbx
  void *v52; // rdx
  void *v53; // rax
  int v54; // edx
  int v55; // ecx
  char *v56; // rbx
  void *v57; // rdx
  char *v58; // rbx
  void *v59; // rdx
  void *v60; // rax
  int v61; // edx
  int v62; // ecx
  WCHAR Buffer[264]; // [rsp+30h] [rbp-268h] BYREF

  v0 = 0;
  memset_0(Buffer, 0, 0x20Au);
  v1 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                 0x80000000LL,
                 0,
                 "Intializing WSD Challenge for %ws..",
                 L"{6BDD1FC6-810F-11D0-BEC7-08002BE2092F}");
  WriteDbgTraceInfoWI("InitializeWSDChallenge", v1);
  WiaTrcLib::Free((WiaTrcLib *)v1, v2);
  lpMem = (void *)WiaTrace_TraceWithSubCompTraceLevel(
                    0x80000000LL,
                    0,
                    "Intializing WSD Challenge for %ws..",
                    L"{6BDD1FC6-810F-11D0-BEC7-08002BE2092F}");
  WiaTrace_ProcessTrace_Ex(v5, v4, (int)"InitializeWSDChallenge", 4, lpMem);
  v6 = CRIT_SECT::Lock((CRIT_SECT *)&g_csWSDChallenge);
  if ( g_bChallengeInitialized )
    goto LABEL_36;
  v7 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(0x80000000LL, 0, "Intialize WSD Challenge...");
  WriteDbgTraceInfoWI("InitializeWSDChallenge", v7);
  WiaTrcLib::Free((WiaTrcLib *)v7, v8);
  v9 = (void *)WiaTrace_TraceWithSubCompTraceLevel(0x80000000LL, 0, "Intialize WSD Challenge...");
  WiaTrace_ProcessTrace_Ex(v11, v10, (int)"InitializeWSDChallenge", 4, v9);
  Library = g_hChallengeDll;
  if ( !g_hChallengeDll )
  {
    v13 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(0x80000000LL, 0, "Load WSD Challenge DLL...");
    WriteDbgTraceInfoWI("InitializeWSDChallenge", v13);
    WiaTrcLib::Free((WiaTrcLib *)v13, v14);
    v15 = (void *)WiaTrace_TraceWithSubCompTraceLevel(0x80000000LL, 0, "Load WSD Challenge DLL...");
    WiaTrace_ProcessTrace_Ex(v17, v16, (int)"InitializeWSDChallenge", 4, v15);
    if ( !GetSystemDirectoryW(Buffer, 0x105u) )
    {
      LastError = GetLastError();
      v0 = LastError;
      if ( LastError > 0 )
        v0 = (unsigned __int16)LastError | 0x80070000;
      if ( v0 < 0 )
        goto LABEL_34;
    }
    v0 = StringCbCatW(Buffer, v18, v19);
    if ( v0 < 0 )
      goto LABEL_34;
    Library = LoadLibraryExW(Buffer, 0, 0x800u);
    g_hChallengeDll = Library;
    if ( !Library )
    {
      v21 = GetLastError();
      v22 = v21;
      if ( v21 > 0 )
        v0 = (unsigned __int16)v21 | 0x80070000;
      else
        v0 = v21;
      v23 = (char *)WiaTrace_TraceLog("LoadLibraryEx(%ws) failed (0x%08X), hr = 0x%08X");
      WriteDbgTraceErrorWI("InitializeWSDChallenge", v23);
      WiaTrcLib::Free((WiaTrcLib *)v23, v24);
      v25 = (void *)WiaTrace_Trace("LoadLibraryEx(%ws) failed (0x%08X), hr = 0x%08X", Buffer, v22, (unsigned int)v0);
      WiaTrace_ProcessTrace_Ex(v27, v26, (int)"InitializeWSDChallenge", 1, v25);
      if ( v0 < 0 )
        goto LABEL_34;
      Library = g_hChallengeDll;
    }
  }
  ProcAddress = GetProcAddress(Library, "WSDCHNGRInitialize");
  if ( ProcAddress )
    goto LABEL_41;
  v29 = GetLastError();
  v30 = v29;
  v0 = v29 > 0 ? (unsigned __int16)v29 | 0x80070000 : v29;
  v31 = (char *)WiaTrace_TraceLog("GetProcAddress(%ws) failed (0x%08X), hr = 0x%08X");
  WriteDbgTraceErrorWI("InitializeWSDChallenge", v31);
  WiaTrcLib::Free((WiaTrcLib *)v31, v32);
  v33 = (void *)WiaTrace_Trace(
                  "GetProcAddress(%ws) failed (0x%08X), hr = 0x%08X",
                  "WSDCHNGRInitialize",
                  v30,
                  (unsigned int)v0);
  WiaTrace_ProcessTrace_Ex(v35, v34, (int)"InitializeWSDChallenge", 1, v33);
  if ( v0 >= 0 )
  {
LABEL_41:
    g_pfnShutdownWSDChallenge = (int (*)(void))GetProcAddress(g_hChallengeDll, "WSDCHNGRShutdown");
    if ( g_pfnShutdownWSDChallenge )
      goto LABEL_42;
    v36 = GetLastError();
    v37 = v36;
    v0 = v36 > 0 ? (unsigned __int16)v36 | 0x80070000 : v36;
    v38 = (char *)WiaTrace_TraceLog("GetProcAddress(%ws) failed (0x%08X), hr = 0x%08X");
    WriteDbgTraceErrorWI("InitializeWSDChallenge", v38);
    WiaTrcLib::Free((WiaTrcLib *)v38, v39);
    v40 = (void *)WiaTrace_Trace(
                    "GetProcAddress(%ws) failed (0x%08X), hr = 0x%08X",
                    "WSDCHNGRShutdown",
                    v37,
                    (unsigned int)v0);
    WiaTrace_ProcessTrace_Ex(v42, v41, (int)"InitializeWSDChallenge", 1, v40);
    if ( v0 >= 0 )
    {
LABEL_42:
      v43 = GetProcAddress(g_hChallengeDll, "WSDCHNGRChallengeDeviceClass");
      if ( v43 )
        goto LABEL_29;
      v44 = GetLastError();
      v45 = v44;
      v0 = v44 > 0 ? (unsigned __int16)v44 | 0x80070000 : v44;
      v46 = (char *)WiaTrace_TraceLog("GetProcAddress(%ws) failed (0x%08X), hr = 0x%08X");
      WriteDbgTraceErrorWI("InitializeWSDChallenge", v46);
      WiaTrcLib::Free((WiaTrcLib *)v46, v47);
      v48 = (void *)WiaTrace_Trace(
                      "GetProcAddress(%ws) failed (0x%08X), hr = 0x%08X",
                      "WSDCHNGRChallengeDeviceClass",
                      v45,
                      (unsigned int)v0);
      WiaTrace_ProcessTrace_Ex(v50, v49, (int)"InitializeWSDChallenge", 1, v48);
      if ( v0 >= 0 )
      {
LABEL_29:
        v0 = ProcAddress();
        if ( v0 >= 0 )
        {
          v0 = ((__int64 (__fastcall *)(const wchar_t *))v43)(L"{6BDD1FC6-810F-11D0-BEC7-08002BE2092F}");
          if ( v0 >= 0 )
            goto LABEL_34;
          v56 = (char *)WiaTrace_TraceLog("WSDCHNRChallengeDeviceClass(%ws) failed, hr = 0x%08X");
          WriteDbgTraceErrorWI("InitializeWSDChallenge", v56);
          WiaTrcLib::Free((WiaTrcLib *)v56, v57);
          v53 = (void *)WiaTrace_Trace(
                          "WSDCHNRChallengeDeviceClass(%ws) failed, hr = 0x%08X",
                          L"{6BDD1FC6-810F-11D0-BEC7-08002BE2092F}",
                          (unsigned int)v0);
        }
        else
        {
          v51 = (char *)WiaTrace_TraceLog("WSDCHNRInitialize failed, hr = 0x%08X");
          WriteDbgTraceErrorWI("InitializeWSDChallenge", v51);
          WiaTrcLib::Free((WiaTrcLib *)v51, v52);
          v53 = (void *)WiaTrace_Trace("WSDCHNRInitialize failed, hr = 0x%08X", v0);
        }
        WiaTrace_ProcessTrace_Ex(v55, v54, (int)"InitializeWSDChallenge", 1, v53);
      }
    }
  }
LABEL_34:
  g_bChallengeInitialized = v0 >= 0;
  if ( v0 < 0 )
  {
    v58 = (char *)WiaTrace_TraceLog("Failed to initialize WSD Challenge for %ws, hr = 0x%08X");
    WriteDbgTraceErrorWI("InitializeWSDChallenge", v58);
    WiaTrcLib::Free((WiaTrcLib *)v58, v59);
    v60 = (void *)WiaTrace_Trace(
                    "Failed to initialize WSD Challenge for %ws, hr = 0x%08X",
                    L"{6BDD1FC6-810F-11D0-BEC7-08002BE2092F}",
                    (unsigned int)v0);
    WiaTrace_ProcessTrace_Ex(v62, v61, (int)"InitializeWSDChallenge", 1, v60);
    ShutdownWSDChallenge(0);
  }
LABEL_36:
  if ( v6 )
    LeaveCriticalSection(&g_csWSDChallenge);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x18001f0d0  push    rbx
0x18001f0d2  push    rbp
0x18001f0d3  push    rsi
0x18001f0d4  push    rdi
0x18001f0d5  push    r12
0x18001f0d7  push    r13
0x18001f0d9  push    r14
0x18001f0db  push    r15
0x18001f0dd  sub     rsp, 258h
0x18001f0e4  mov     rax, cs:__security_cookie
0x18001f0eb  xor     rax, rsp
0x18001f0ee  mov     [rsp+298h+var_58], rax
0x18001f0f6  xor     edx, edx; Val
0x18001f0f8  lea     rcx, [rsp+298h+Buffer]; void *
0x18001f0fd  mov     r8d, 20Ah; Size
0x18001f103  xor     edi, edi
0x18001f105  call    memset_0
0x18001f10a  mov     esi, 80000000h
0x18001f10f  lea     r9, a6bdd1fc6810f11; "{6BDD1FC6-810F-11D0-BEC7-08002BE2092F}"
0x18001f116  mov     ecx, esi
0x18001f118  lea     r8, aIntializingWsd; "Intializing WSD Challenge for %ws.."
0x18001f11f  xor     edx, edx
0x18001f121  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x18001f126  lea     r12, aInitializewsdc; "InitializeWSDChallenge"
0x18001f12d  mov     rdx, rax; char *
0x18001f130  mov     rcx, r12; char *
0x18001f133  mov     rbx, rax
0x18001f136  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x18001f13b  mov     rcx, rbx; this
0x18001f13e  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18001f143  lea     r9, a6bdd1fc6810f11; "{6BDD1FC6-810F-11D0-BEC7-08002BE2092F}"
0x18001f14a  xor     edx, edx
0x18001f14c  lea     r8, aIntializingWsd; "Intializing WSD Challenge for %ws.."
0x18001f153  mov     ecx, esi
0x18001f155  call    WiaTrace_TraceWithSubCompTraceLevel
0x18001f15a  lea     ebp, [rdi+4]
0x18001f15d  mov     [rsp+298h+lpMem], rax; lpMem
0x18001f162  mov     r9d, ebp; int
0x18001f165  mov     r8, r12; int
0x18001f168  call    WiaTrace_ProcessTrace_Ex
0x18001f16d  lea     rcx, ?g_csWSDChallenge@@3VCRIT_SECT@@A; this
0x18001f174  call    ?Lock@CRIT_SECT@@QEAAHXZ; CRIT_SECT::Lock(void)
0x18001f179  cmp     cs:?g_bChallengeInitialized@@3HA, edi; int g_bChallengeInitialized
0x18001f17f  mov     r15d, eax
0x18001f182  jnz     loc_18001F5D5
0x18001f188  lea     r8, aIntializeWsdCh; "Intialize WSD Challenge..."
0x18001f18f  xor     edx, edx
0x18001f191  mov     ecx, esi
0x18001f193  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x18001f198  mov     rdx, rax; char *
0x18001f19b  mov     rcx, r12; char *
0x18001f19e  mov     rbx, rax
0x18001f1a1  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x18001f1a6  mov     rcx, rbx; this
0x18001f1a9  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18001f1ae  lea     r8, aIntializeWsdCh; "Intialize WSD Challenge..."
0x18001f1b5  xor     edx, edx
0x18001f1b7  mov     ecx, esi
0x18001f1b9  call    WiaTrace_TraceWithSubCompTraceLevel
0x18001f1be  mov     r9d, ebp; int
0x18001f1c1  mov     [rsp+298h+lpMem], rax; lpMem
0x18001f1c6  mov     r8, r12; int
0x18001f1c9  call    WiaTrace_ProcessTrace_Ex
0x18001f1ce  mov     rax, cs:?g_hChallengeDll@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hChallengeDll
0x18001f1d5  mov     r13d, 80070000h
0x18001f1db  test    rax, rax
0x18001f1de  jnz     loc_18001F307
0x18001f1e4  lea     r8, aLoadWsdChallen; "Load WSD Challenge DLL..."
0x18001f1eb  xor     edx, edx
0x18001f1ed  mov     ecx, esi
0x18001f1ef  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x18001f1f4  mov     rdx, rax; char *
0x18001f1f7  mov     rcx, r12; char *
0x18001f1fa  mov     rbx, rax
0x18001f1fd  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x18001f202  mov     rcx, rbx; this
0x18001f205  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18001f20a  lea     r8, aLoadWsdChallen; "Load WSD Challenge DLL..."
0x18001f211  xor     edx, edx
0x18001f213  mov     ecx, esi
0x18001f215  call    WiaTrace_TraceWithSubCompTraceLevel
0x18001f21a  mov     r9d, ebp; int
0x18001f21d  mov     [rsp+298h+lpMem], rax; lpMem
0x18001f222  mov     r8, r12; int
0x18001f225  call    WiaTrace_ProcessTrace_Ex
0x18001f22a  mov     edx, 105h; uSize
0x18001f22f  lea     rcx, [rsp+298h+Buffer]; lpBuffer
0x18001f234  call    cs:__imp_GetSystemDirectoryW
0x18001f23a  test    eax, eax
0x18001f23c  jnz     short loc_18001F258
0x18001f23e  call    cs:__imp_GetLastError
0x18001f244  mov     edi, eax
0x18001f246  test    eax, eax
0x18001f248  jle     short loc_18001F250
0x18001f24a  movzx   edi, ax
0x18001f24d  or      edi, r13d
0x18001f250  test    edi, edi
0x18001f252  js      loc_18001F568
0x18001f258  lea     rcx, [rsp+298h+Buffer]; unsigned __int16 *
0x18001f25d  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x18001f262  mov     edi, eax
0x18001f264  test    eax, eax
0x18001f266  js      loc_18001F568
0x18001f26c  xor     edx, edx; hFile
0x18001f26e  lea     rcx, [rsp+298h+Buffer]; lpLibFileName
0x18001f273  mov     r8d, 800h; dwFlags
0x18001f279  call    cs:__imp_LoadLibraryExW
0x18001f27f  mov     cs:?g_hChallengeDll@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hChallengeDll
0x18001f286  test    rax, rax
0x18001f289  jnz     short loc_18001F307
0x18001f28b  call    cs:__imp_GetLastError
0x18001f291  mov     esi, eax
0x18001f293  test    eax, eax
0x18001f295  jg      short loc_18001F29B
0x18001f297  mov     edi, eax
0x18001f299  jmp     short loc_18001F2A1
0x18001f29b  movzx   edi, si
0x18001f29e  or      edi, r13d
0x18001f2a1  mov     r9d, edi
0x18001f2a4  lea     rdx, [rsp+298h+Buffer]
0x18001f2a9  mov     r8d, esi
0x18001f2ac  lea     rcx, aLoadlibraryexW; "LoadLibraryEx(%ws) failed (0x%08X), hr "...
0x18001f2b3  call    WiaTrace_TraceLog
0x18001f2b8  mov     rdx, rax; char *
0x18001f2bb  mov     rcx, r12; char *
0x18001f2be  mov     rbx, rax
0x18001f2c1  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18001f2c6  mov     rcx, rbx; this
0x18001f2c9  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18001f2ce  mov     r9d, edi
0x18001f2d1  lea     rdx, [rsp+298h+Buffer]
0x18001f2d6  mov     r8d, esi
0x18001f2d9  lea     rcx, aLoadlibraryexW; "LoadLibraryEx(%ws) failed (0x%08X), hr "...
0x18001f2e0  call    WiaTrace_Trace
0x18001f2e5  mov     r9d, 1; int
0x18001f2eb  mov     [rsp+298h+lpMem], rax; lpMem
0x18001f2f0  mov     r8, r12; int
0x18001f2f3  call    WiaTrace_ProcessTrace_Ex
0x18001f2f8  test    edi, edi
0x18001f2fa  js      loc_18001F568
0x18001f300  mov     rax, cs:?g_hChallengeDll@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hChallengeDll
0x18001f307  lea     rbp, aWsdchngrinitia; "WSDCHNGRInitialize"
0x18001f30e  mov     rcx, rax; hModule
0x18001f311  mov     rdx, rbp; lpProcName
0x18001f314  call    cs:__imp_GetProcAddress
0x18001f31a  mov     r14, rax
0x18001f31d  test    rax, rax
0x18001f320  jnz     short loc_18001F393
0x18001f322  call    cs:__imp_GetLastError
0x18001f328  mov     esi, eax
0x18001f32a  test    eax, eax
0x18001f32c  jg      short loc_18001F332
0x18001f32e  mov     edi, eax
0x18001f330  jmp     short loc_18001F338
0x18001f332  movzx   edi, si
0x18001f335  or      edi, r13d
0x18001f338  mov     r9d, edi
0x18001f33b  lea     rcx, aGetprocaddress; "GetProcAddress(%ws) failed (0x%08X), hr"...
0x18001f342  mov     r8d, esi
0x18001f345  mov     rdx, rbp
0x18001f348  call    WiaTrace_TraceLog
0x18001f34d  mov     rdx, rax; char *
0x18001f350  mov     rcx, r12; char *
0x18001f353  mov     rbx, rax
0x18001f356  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18001f35b  mov     rcx, rbx; this
0x18001f35e  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18001f363  mov     r9d, edi
0x18001f366  lea     rcx, aGetprocaddress; "GetProcAddress(%ws) failed (0x%08X), hr"...
0x18001f36d  mov     r8d, esi
0x18001f370  mov     rdx, rbp
0x18001f373  call    WiaTrace_Trace
0x18001f378  mov     r9d, 1; int
0x18001f37e  mov     [rsp+298h+lpMem], rax; lpMem
0x18001f383  mov     r8, r12; int
0x18001f386  call    WiaTrace_ProcessTrace_Ex
0x18001f38b  test    edi, edi
0x18001f38d  js      loc_18001F568
0x18001f393  mov     rcx, cs:?g_hChallengeDll@@3PEAUHINSTANCE__@@EA; hModule
0x18001f39a  lea     rbp, aWsdchngrshutdo; "WSDCHNGRShutdown"
0x18001f3a1  mov     rdx, rbp; lpProcName
0x18001f3a4  call    cs:__imp_GetProcAddress
0x18001f3aa  mov     cs:?g_pfnShutdownWSDChallenge@@3P6AJXZEA, rax; long (*g_pfnShutdownWSDChallenge)(void)
0x18001f3b1  test    rax, rax
0x18001f3b4  jnz     short loc_18001F427
0x18001f3b6  call    cs:__imp_GetLastError
0x18001f3bc  mov     esi, eax
0x18001f3be  test    eax, eax
0x18001f3c0  jg      short loc_18001F3C6
0x18001f3c2  mov     edi, eax
0x18001f3c4  jmp     short loc_18001F3CC
0x18001f3c6  movzx   edi, si
0x18001f3c9  or      edi, r13d
0x18001f3cc  mov     r9d, edi
0x18001f3cf  lea     rcx, aGetprocaddress; "GetProcAddress(%ws) failed (0x%08X), hr"...
0x18001f3d6  mov     r8d, esi
0x18001f3d9  mov     rdx, rbp
0x18001f3dc  call    WiaTrace_TraceLog
0x18001f3e1  mov     rdx, rax; char *
0x18001f3e4  mov     rcx, r12; char *
0x18001f3e7  mov     rbx, rax
0x18001f3ea  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18001f3ef  mov     rcx, rbx; this
0x18001f3f2  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18001f3f7  mov     r9d, edi
0x18001f3fa  lea     rcx, aGetprocaddress; "GetProcAddress(%ws) failed (0x%08X), hr"...
0x18001f401  mov     r8d, esi
0x18001f404  mov     rdx, rbp
0x18001f407  call    WiaTrace_Trace
0x18001f40c  mov     r9d, 1; int
0x18001f412  mov     [rsp+298h+lpMem], rax; lpMem
0x18001f417  mov     r8, r12; int
0x18001f41a  call    WiaTrace_ProcessTrace_Ex
0x18001f41f  test    edi, edi
0x18001f421  js      loc_18001F568
0x18001f427  mov     rcx, cs:?g_hChallengeDll@@3PEAUHINSTANCE__@@EA; hModule
0x18001f42e  lea     rdx, aWsdchngrchalle; "WSDCHNGRChallengeDeviceClass"
0x18001f435  call    cs:__imp_GetProcAddress
0x18001f43b  mov     rbp, rax
0x18001f43e  test    rax, rax
0x18001f441  jnz     short loc_18001F4BC
0x18001f443  call    cs:__imp_GetLastError
0x18001f449  mov     esi, eax
0x18001f44b  test    eax, eax
0x18001f44d  jg      short loc_18001F453
0x18001f44f  mov     edi, eax
0x18001f451  jmp     short loc_18001F459
0x18001f453  movzx   edi, si
0x18001f456  or      edi, r13d
0x18001f459  mov     r9d, edi
0x18001f45c  lea     rdx, aWsdchngrchalle; "WSDCHNGRChallengeDeviceClass"
0x18001f463  mov     r8d, esi
0x18001f466  lea     rcx, aGetprocaddress; "GetProcAddress(%ws) failed (0x%08X), hr"...
0x18001f46d  call    WiaTrace_TraceLog
0x18001f472  mov     rdx, rax; char *
0x18001f475  mov     rcx, r12; char *
0x18001f478  mov     rbx, rax
0x18001f47b  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18001f480  mov     rcx, rbx; this
0x18001f483  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18001f488  mov     r9d, edi
0x18001f48b  lea     rdx, aWsdchngrchalle; "WSDCHNGRChallengeDeviceClass"
0x18001f492  mov     r8d, esi
0x18001f495  lea     rcx, aGetprocaddress; "GetProcAddress(%ws) failed (0x%08X), hr"...
0x18001f49c  call    WiaTrace_Trace
0x18001f4a1  mov     r9d, 1; int
0x18001f4a7  mov     [rsp+298h+lpMem], rax; lpMem
0x18001f4ac  mov     r8, r12; int
0x18001f4af  call    WiaTrace_ProcessTrace_Ex
0x18001f4b4  test    edi, edi
0x18001f4b6  js      loc_18001F568
0x18001f4bc  mov     rax, r14
0x18001f4bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f4c4  mov     edi, eax
0x18001f4c6  test    eax, eax
0x18001f4c8  jns     short loc_18001F4FE
0x18001f4ca  mov     edx, eax
0x18001f4cc  lea     rcx, aWsdchnrinitial; "WSDCHNRInitialize failed, hr = 0x%08X"
0x18001f4d3  call    WiaTrace_TraceLog
0x18001f4d8  mov     rdx, rax; char *
0x18001f4db  mov     rcx, r12; char *
0x18001f4de  mov     rbx, rax
0x18001f4e1  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18001f4e6  mov     rcx, rbx; this
0x18001f4e9  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18001f4ee  mov     edx, edi
0x18001f4f0  lea     rcx, aWsdchnrinitial; "WSDCHNRInitialize failed, hr = 0x%08X"
0x18001f4f7  call    WiaTrace_Trace
0x18001f4fc  jmp     short loc_18001F555
0x18001f4fe  lea     rcx, a6bdd1fc6810f11; "{6BDD1FC6-810F-11D0-BEC7-08002BE2092F}"
0x18001f505  mov     rax, rbp
0x18001f508  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f50d  mov     edi, eax
0x18001f50f  test    eax, eax
0x18001f511  jns     short loc_18001F568
0x18001f513  mov     r8d, eax
0x18001f516  lea     rdx, a6bdd1fc6810f11; "{6BDD1FC6-810F-11D0-BEC7-08002BE2092F}"
0x18001f51d  lea     rcx, aWsdchnrchallen; "WSDCHNRChallengeDeviceClass(%ws) failed"...
0x18001f524  call    WiaTrace_TraceLog
0x18001f529  mov     rdx, rax; char *
0x18001f52c  mov     rcx, r12; char *
0x18001f52f  mov     rbx, rax
0x18001f532  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18001f537  mov     rcx, rbx; this
0x18001f53a  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18001f53f  mov     r8d, edi
0x18001f542  lea     rdx, a6bdd1fc6810f11; "{6BDD1FC6-810F-11D0-BEC7-08002BE2092F}"
0x18001f549  lea     rcx, aWsdchnrchallen; "WSDCHNRChallengeDeviceClass(%ws) failed"...
0x18001f550  call    WiaTrace_Trace
0x18001f555  mov     r9d, 1; int
0x18001f55b  mov     [rsp+298h+lpMem], rax; lpMem
0x18001f560  mov     r8, r12; int
0x18001f563  call    WiaTrace_ProcessTrace_Ex
0x18001f568  mov     eax, edi
0x18001f56a  not     eax
0x18001f56c  shr     eax, 1Fh
0x18001f56f  mov     cs:?g_bChallengeInitialized@@3HA, eax; int g_bChallengeInitialized
0x18001f575  test    edi, edi
0x18001f577  jns     short loc_18001F5D5
0x18001f579  mov     r8d, edi
  ... truncated ...
```
