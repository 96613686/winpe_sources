# CSetupFilesCleanup::Initialize(HKEY__ *,ushort const *,ushort * *,ushort * *,ulong *)

- ea: `0x180005080`
- end: `0x1800055da`
- name: `?Initialize@CSetupFilesCleanup@@UEAAJPEAUHKEY__@@PEBGPEAPEAG2PEAK@Z`
- size: `1370`
- prototype: `__int64 __fastcall(CSetupFilesCleanup *this, HKEY hKey, LPCWSTR lpFileName, unsigned __int16 **, unsigned __int16 **, unsigned int *)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800019e4`
- `0x1800036e8`
- `0x180003b54`
- `0x1800040c0`
- `0x1800047ac`
- `0x180004c30`
- `0x180005080`
- `0x1800074e4`
- `0x18000912c`
- `0x180009214`
- `0x180009748`
- `0x1800099c0`
- `0x180009d30`
- `0x1800131a2`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000537f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800053da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800054c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005526`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000537f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800053da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800054c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005526`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000513d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000558f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800055a8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000513d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000558f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800055a8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000514b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000559d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800055b6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000514b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000559d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800055b6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005363`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005363`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180005310`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180005310`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000536c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000536c`
- `WDSCORE!CurrentIP` at `0x180005387`
- `WDSCORE!CurrentIP` at `0x1800053e2`
- `WDSCORE!CurrentIP` at `0x1800054cf`
- `WDSCORE!CurrentIP` at `0x18000552e`
- `WDSCORE!CurrentIP` at `0x180005387`
- `WDSCORE!CurrentIP` at `0x1800053e2`
- `WDSCORE!CurrentIP` at `0x1800054cf`
- `WDSCORE!CurrentIP` at `0x18000552e`
- `WDSCORE!WdsInitialize` at `0x180005122`
- `WDSCORE!WdsInitialize` at `0x180005122`
- `WDSCORE!WdsSetupLogMessageW` at `0x180005441`
- `WDSCORE!WdsSetupLogMessageW` at `0x180005520`
- `WDSCORE!WdsSetupLogMessageW` at `0x180005580`
- `WDSCORE!WdsSetupLogMessageW` at `0x180005441`
- `WDSCORE!WdsSetupLogMessageW` at `0x180005520`
- `WDSCORE!WdsSetupLogMessageW` at `0x180005580`

## string_xrefs

- `0x1800051ec`: `RemoveUninstall`
- `0x180005105`: `setupcln.dll`
- `0x180005200`: `SetupTemporaryInstallationFiles`
- `0x180005391`: `CSetupFilesCleanup::Initialize - Cannot delete plugin: %s due to one or more missing directories.`

## pseudocode

```c
__int64 __fastcall CSetupFilesCleanup::Initialize(
        CSetupFilesCleanup *this,
        HKEY hKey,
        LPCWSTR lpFileName,
        unsigned __int16 **a4,
        unsigned __int16 **a5,
        unsigned int *a6)
{
  __int64 Expand; // rax
  void *v11; // rbx
  HANDLE ProcessHeap; // rax
  TraceLoggingCorrelationVector *v13; // rax
  TraceLoggingCorrelationVector *v14; // rax
  __int64 v15; // rax
  int v16; // r14d
  void *String; // r15
  int Dword; // ebx
  int v19; // edi
  int v20; // r8d
  int v21; // eax
  BOOL v22; // edi
  bool v23; // zf
  BOOL v24; // ebx
  BOOL v25; // r11d
  BOOL v26; // r10d
  HANDLE MutexW; // rbx
  __int64 v28; // rcx
  DWORD v29; // edi
  __int64 v30; // rbx
  struct tagLOG_PARTIAL_MSG *v31; // rax
  DWORD LastError; // edi
  __int64 v33; // rbx
  struct tagLOG_PARTIAL_MSG *v34; // rax
  DWORD v35; // edi
  __int64 v36; // rbx
  struct tagLOG_PARTIAL_MSG *v37; // rax
  DWORD v38; // edi
  __int64 v39; // rbx
  struct tagLOG_PARTIAL_MSG *v40; // rax
  void *v41; // rbx
  HANDLE v42; // rax
  HANDLE v43; // rax
  unsigned int v45; // [rsp+40h] [rbp-99h]
  LPVOID lpMem; // [rsp+60h] [rbp-79h] BYREF
  int v47; // [rsp+68h] [rbp-71h]
  int v48; // [rsp+6Ch] [rbp-6Dh]
  int v49; // [rsp+70h] [rbp-69h]
  int v50; // [rsp+74h] [rbp-65h]
  int v51; // [rsp+78h] [rbp-61h] BYREF
  int v52; // [rsp+7Ch] [rbp-5Dh] BYREF
  TraceLoggingCorrelationVector *v53; // [rsp+80h] [rbp-59h]
  _DWORD v54[2]; // [rsp+90h] [rbp-49h] BYREF
  int *v55; // [rsp+98h] [rbp-41h]
  int *v56; // [rsp+A0h] [rbp-39h]
  __int64 v57; // [rsp+A8h] [rbp-31h]
  __int128 v58; // [rsp+B0h] [rbp-29h]
  __int64 v59; // [rsp+D0h] [rbp-9h]
  __int64 v60; // [rsp+D8h] [rbp-1h]
  unsigned int v62; // [rsp+148h] [rbp+6Fh]

  lpMem = 0;
  v51 = 0;
  v52 = 1;
  memset_0(v54, 0, 0x50u);
  if ( !a4 || !a5 || !a6 )
    return 2147942487LL;
  Expand = AllocateExpand();
  v11 = (void *)Expand;
  if ( Expand )
  {
    CreatePath(Expand);
    WdsInitialize(L"setupcln.dll", 1, v11, v11, 50393088, 0, 0);
    g_WdsLibLog = (__int64)WdsLibLogCallback;
    g_WdsNativeLibLog = (__int64)WdsLibLogCallback;
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v11);
  }
  v13 = (TraceLoggingCorrelationVector *)operator new(0x90u);
  v53 = v13;
  if ( v13 )
    v14 = TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(v13);
  else
    v14 = 0;
  *((_QWORD *)this + 10) = v14;
  v15 = FormFullPathName(lpFileName);
  v16 = HrPtr<unsigned short>(v15, &lpMem);
  String = (void *)RegGetStringEx(hKey);
  Dword = RegGetDword(hKey, 0, L"SetupPrevInst");
  v50 = RegGetDword(hKey, 0, L"ValidIfUpgrade");
  v19 = v50;
  v47 = RegGetDword(hKey, 0, L"ValidIfWebSetupNotRunning");
  LODWORD(v53) = RegGetDword(hKey, 0, L"ValidIfSetupNotRunning");
  v48 = RegGetDword(hKey, 0, L"RemoveUninstall");
  v49 = RegGetDword(hKey, 0, L"SetupTemporaryInstallationFiles");
  v20 = RegGetDword(hKey, 0, L"ResetLogs");
  v21 = 0;
  if ( v16 < 0 )
  {
    v62 = 0;
    SetupClnLogInitializationInfo(
      hKey,
      Dword != 0,
      v48 != 0,
      v19 != 0,
      v47 != 0,
      (*a6 >> 7) & 1,
      *((_DWORD *)this + 15));
  }
  else
  {
    *((_QWORD *)this + 2) = lpMem;
    v22 = Dword != 0;
    lpMem = 0;
    v23 = v49 == 0;
    *((_QWORD *)this + 4) = String;
    v24 = !v23;
    *((_DWORD *)this + 6) = v22;
    v25 = v50 != 0;
    *((_DWORD *)this + 15) = v24;
    v23 = v47 == 0;
    String = 0;
    *((_DWORD *)this + 10) = v25;
    v26 = !v23;
    v23 = (_DWORD)v53 == 0;
    *((_DWORD *)this + 11) = v26;
    LOBYTE(v21) = !v23;
    v23 = v48 == 0;
    *((_DWORD *)this + 12) = v21;
    *((_DWORD *)this + 13) = !v23;
    v45 = (*a6 >> 7) & 1;
    *((_DWORD *)this + 14) = v45;
    *((_DWORD *)this + 22) = v20 != 0;
    SetupClnLogInitializationInfo(hKey, v22, !v23, v25, v26, v45, v24);
    *a4 = 0;
    *a5 = 0;
    v62 = CSetupFilesCleanup::FullBlockChecks(this);
    if ( v62 )
    {
      LastError = GetLastError();
      v33 = CurrentIP();
      v34 = ConstructPartialMsgW(
              0x4000000u,
              "CSetupFilesCleanup::Initialize - Initialization failed because block check failed with %d",
              v62);
      WdsSetupLogMessageW(
        v34,
        0,
        L"D",
        0,
        488,
        L"base\\ntsetup\\setup\\tools\\setupcln\\setupcln.cpp",
        L"CSetupFilesCleanup::Initialize",
        v33,
        LastError,
        0,
        0);
    }
    else
    {
      MutexW = CreateMutexW(0, 1, L"Global\\Microsoft.Windows.Setup.SetupCln");
      v57 = *((_QWORD *)this + 2);
      v28 = *((_QWORD *)this + 10);
      v56 = &v51;
      v59 = v28;
      v55 = &v52;
      v54[0] = 0;
      v54[1] = 1;
      v58 = 0;
      v60 = 0;
      v16 = CSetupFilesCleanup::CleanVolume(this, (struct _SETUPCLN_PARAMS *)v54);
      if ( MutexW )
      {
        ReleaseMutex(MutexW);
        CloseHandle(MutexW);
      }
      if ( *v55 )
        goto LABEL_18;
      v29 = GetLastError();
      v30 = CurrentIP();
      v31 = ConstructPartialMsgW(
              0x4000000u,
              "CSetupFilesCleanup::Initialize - Cannot delete plugin: %s due to one or more missing directories.",
              *((const char **)this + 9));
      WdsSetupLogMessageW(
        v31,
        0,
        L"D",
        0,
        482,
        L"base\\ntsetup\\setup\\tools\\setupcln\\setupcln.cpp",
        L"CSetupFilesCleanup::Initialize",
        v30,
        v29,
        0,
        0);
    }
    v16 = 1;
  }
LABEL_18:
  v35 = GetLastError();
  v36 = CurrentIP();
  v37 = ConstructPartialMsgW(0x4000000u, "Initialization status:%x", v16);
  WdsSetupLogMessageW(
    v37,
    0,
    L"D",
    0,
    508,
    L"base\\ntsetup\\setup\\tools\\setupcln\\setupcln.cpp",
    L"CSetupFilesCleanup::Initialize",
    v36,
    v35,
    0,
    0);
  v38 = GetLastError();
  v39 = CurrentIP();
  v40 = ConstructPartialMsgW(0x4000000u, "Initialization Block status: %d", v62);
  WdsSetupLogMessageW(
    v40,
    0,
    L"D",
    0,
    509,
    L"base\\ntsetup\\setup\\tools\\setupcln\\setupcln.cpp",
    L"CSetupFilesCleanup::Initialize",
    v39,
    v38,
    0,
    0);
  v41 = lpMem;
  if ( lpMem )
  {
    v42 = GetProcessHeap();
    HeapFree(v42, 0, v41);
  }
  if ( String )
  {
    v43 = GetProcessHeap();
    HeapFree(v43, 0, String);
  }
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x180005080  mov     [rsp-8+arg_18], r9
0x180005085  push    rbp
0x180005086  push    rbx
0x180005087  push    rsi
0x180005088  push    rdi
0x180005089  push    r12
0x18000508b  push    r13
0x18000508d  push    r14
0x18000508f  push    r15
0x180005091  lea     rbp, [rsp-0Fh]
0x180005096  sub     rsp, 0E8h
0x18000509d  xor     r14d, r14d
0x1800050a0  mov     rdi, r8
0x1800050a3  mov     r13, rdx
0x1800050a6  mov     [rbp+47h+lpMem], r14
0x1800050aa  mov     rsi, rcx
0x1800050ad  mov     [rbp+47h+var_A8], r14d
0x1800050b1  xor     edx, edx; Val
0x1800050b3  lea     rcx, [rbp+47h+var_90]; void *
0x1800050b7  lea     r15d, [r14+1]
0x1800050bb  mov     rbx, r9
0x1800050be  lea     r8d, [r14+50h]; Size
0x1800050c2  mov     [rbp+47h+var_A4], r15d
0x1800050c6  call    memset_0
0x1800050cb  test    rbx, rbx
0x1800050ce  jz      loc_1800055C1
0x1800050d4  cmp     [rbp+47h+arg_20], r14
0x1800050d8  jz      loc_1800055C1
0x1800050de  mov     r12, [rbp+47h+arg_28]
0x1800050e2  test    r12, r12
0x1800050e5  jz      loc_1800055C1
0x1800050eb  call    AllocateExpand
0x1800050f0  mov     rbx, rax
0x1800050f3  test    rax, rax
0x1800050f6  jz      short loc_180005151
0x1800050f8  mov     rcx, rax
0x1800050fb  call    CreatePath
0x180005100  mov     qword ptr [rsp+120h+var_F0], r14
0x180005105  lea     rcx, ModuleName; "setupcln.dll"
0x18000510c  mov     [rsp+120h+var_F8], r14d
0x180005111  mov     r9, rbx
0x180005114  mov     r8, rbx
0x180005117  mov     [rsp+120h+var_100], 300F000h
0x18000511f  mov     edx, r15d
0x180005122  call    cs:__imp_WdsInitialize
0x180005128  lea     rax, WdsLibLogCallback
0x18000512f  mov     cs:g_WdsLibLog, rax
0x180005136  mov     cs:g_WdsNativeLibLog, rax
0x18000513d  call    cs:__imp_GetProcessHeap
0x180005143  mov     r8, rbx; lpMem
0x180005146  xor     edx, edx; dwFlags
0x180005148  mov     rcx, rax; hHeap
0x18000514b  call    cs:__imp_HeapFree
0x180005151  mov     ecx, 90h; Size
0x180005156  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000515b  mov     [rbp+47h+var_A0], rax
0x18000515f  test    rax, rax
0x180005162  jz      short loc_18000516E
0x180005164  mov     rcx, rax; this
0x180005167  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x18000516c  jmp     short loc_180005171
0x18000516e  mov     rax, r14
0x180005171  mov     rcx, rdi; lpFileName
0x180005174  mov     [rsi+50h], rax
0x180005178  call    FormFullPathName
0x18000517d  mov     rcx, rax
0x180005180  lea     rdx, [rbp+47h+lpMem]
0x180005184  call    ??$HrPtr@G@@YAJPEAGAEAPEAG@Z; HrPtr<ushort>(ushort *,ushort * &)
0x180005189  lea     r8, aSetupdirectori; "SetupDirectories"
0x180005190  mov     rcx, r13; hKey
0x180005193  mov     r14d, eax
0x180005196  call    RegGetStringEx
0x18000519b  lea     r8, aSetupprevinst; "SetupPrevInst"
0x1800051a2  xor     edx, edx
0x1800051a4  mov     rcx, r13
0x1800051a7  mov     r15, rax
0x1800051aa  call    RegGetDword
0x1800051af  lea     r8, aValidifupgrade; "ValidIfUpgrade"
0x1800051b6  xor     edx, edx
0x1800051b8  mov     rcx, r13
0x1800051bb  mov     ebx, eax
0x1800051bd  call    RegGetDword
0x1800051c2  lea     r8, aValidifwebsetu; "ValidIfWebSetupNotRunning"
0x1800051c9  mov     [rbp+47h+var_AC], eax
0x1800051cc  xor     edx, edx
0x1800051ce  mov     rcx, r13
0x1800051d1  mov     edi, eax
0x1800051d3  call    RegGetDword
0x1800051d8  lea     r8, aValidifsetupno; "ValidIfSetupNotRunning"
0x1800051df  mov     [rbp+47h+var_B8], eax
0x1800051e2  xor     edx, edx
0x1800051e4  mov     rcx, r13
0x1800051e7  call    RegGetDword
0x1800051ec  lea     r8, aRemoveuninstal; "RemoveUninstall"
0x1800051f3  mov     dword ptr [rbp+47h+var_A0], eax
0x1800051f6  xor     edx, edx
0x1800051f8  mov     rcx, r13
0x1800051fb  call    RegGetDword
0x180005200  lea     r8, aSetuptemporary; "SetupTemporaryInstallationFiles"
0x180005207  mov     [rbp+47h+var_B4], eax
0x18000520a  xor     edx, edx
0x18000520c  mov     rcx, r13
0x18000520f  call    RegGetDword
0x180005214  lea     r8, aResetlogs; "ResetLogs"
0x18000521b  mov     [rbp+47h+var_B0], eax
0x18000521e  xor     edx, edx
0x180005220  mov     rcx, r13
0x180005223  call    RegGetDword
0x180005228  mov     r8d, eax
0x18000522b  xor     eax, eax
0x18000522d  test    r14d, r14d
0x180005230  js      loc_18000544F
0x180005236  mov     rcx, [rbp+47h+lpMem]
0x18000523a  test    ebx, ebx
0x18000523c  mov     edi, eax
0x18000523e  mov     [rsi+10h], rcx
0x180005242  setnz   dil
0x180005246  mov     [rbp+47h+lpMem], rax
0x18000524a  cmp     [rbp+47h+var_B0], eax
0x18000524d  mov     ebx, eax
0x18000524f  mov     r11d, eax
0x180005252  mov     [rsi+20h], r15
0x180005256  setnz   bl
0x180005259  mov     [rsi+18h], edi
0x18000525c  cmp     [rbp+47h+var_AC], eax
0x18000525f  mov     r10d, eax
0x180005262  mov     [rsp+120h+var_D8], ebx; int
0x180005266  mov     r9, r15
0x180005269  setnz   r11b
0x18000526d  mov     [rsi+3Ch], ebx
0x180005270  cmp     [rbp+47h+var_B8], eax
0x180005273  mov     r15d, eax
0x180005276  mov     [rsi+28h], r11d
0x18000527a  setnz   r10b
0x18000527e  xor     r14d, r14d
0x180005281  cmp     dword ptr [rbp+47h+var_A0], r14d
0x180005285  mov     edx, r14d
0x180005288  mov     [rsi+2Ch], r10d
0x18000528c  setnz   al
0x18000528f  cmp     [rbp+47h+var_B4], r14d
0x180005293  mov     [rsi+30h], eax
0x180005296  mov     eax, r14d
0x180005299  setnz   dl
0x18000529c  mov     [rsi+34h], edx
0x18000529f  mov     ecx, [r12]
0x1800052a3  shr     ecx, 7
0x1800052a6  and     ecx, 1
0x1800052a9  mov     [rsp+120h+var_E0], ecx; int
0x1800052ad  test    r8d, r8d
0x1800052b0  mov     [rsp+120h+var_E8], r10d; int
0x1800052b5  lea     r8, [rsi+40h]
0x1800052b9  mov     [rsp+120h+var_F0], r11d; int
0x1800052be  setnz   al
0x1800052c1  mov     [rsp+120h+var_F8], edx; int
0x1800052c5  lea     rdx, [rsi+48h]
0x1800052c9  mov     [rsi+38h], ecx
0x1800052cc  mov     rcx, r13; hKey
0x1800052cf  mov     [rsi+58h], eax
0x1800052d2  mov     [rsp+120h+var_100], edi; int
0x1800052d6  call    SetupClnLogInitializationInfo
0x1800052db  mov     rax, [rbp+47h+arg_18]
0x1800052df  xor     r13d, r13d
0x1800052e2  mov     rcx, rsi; this
0x1800052e5  mov     [rax], r13
0x1800052e8  mov     rax, [rbp+47h+arg_20]
0x1800052ec  mov     [rax], r13
0x1800052ef  call    ?FullBlockChecks@CSetupFilesCleanup@@QEAAKXZ; CSetupFilesCleanup::FullBlockChecks(void)
0x1800052f4  mov     dword ptr [rbp+47h+arg_18], eax
0x1800052f7  mov     r14d, eax
0x1800052fa  test    eax, eax
0x1800052fc  jnz     loc_1800053DA
0x180005302  lea     edi, [rax+1]
0x180005305  xor     ecx, ecx; lpMutexAttributes
0x180005307  mov     edx, edi; bInitialOwner
0x180005309  lea     r8, Name; "Global\\Microsoft.Windows.Setup.SetupCl"...
0x180005310  call    cs:__imp_CreateMutexW
0x180005316  mov     rcx, [rsi+10h]
0x18000531a  lea     rdx, [rbp+47h+var_90]; struct _SETUPCLN_PARAMS *
0x18000531e  mov     rbx, rax
0x180005321  mov     [rbp+47h+var_78], rcx
0x180005325  mov     rcx, [rsi+50h]
0x180005329  lea     rax, [rbp+47h+var_A8]
0x18000532d  mov     [rbp+47h+var_80], rax
0x180005331  xorps   xmm0, xmm0
0x180005334  lea     rax, [rbp+47h+var_A4]
0x180005338  mov     [rbp+47h+var_50], rcx
0x18000533c  mov     rcx, rsi; this
0x18000533f  mov     [rbp+47h+var_88], rax
0x180005343  mov     [rbp+47h+var_90], r13d
0x180005347  mov     [rbp+47h+var_8C], edi
0x18000534a  movdqa  [rbp+47h+var_70], xmm0
0x18000534f  mov     [rbp+47h+var_48], r13
0x180005353  call    ?CleanVolume@CSetupFilesCleanup@@QEAAJPEAU_SETUPCLN_PARAMS@@@Z; CSetupFilesCleanup::CleanVolume(_SETUPCLN_PARAMS *)
0x180005358  mov     r14d, eax
0x18000535b  test    rbx, rbx
0x18000535e  jz      short loc_180005372
0x180005360  mov     rcx, rbx; hMutex
0x180005363  call    cs:__imp_ReleaseMutex
0x180005369  mov     rcx, rbx; hObject
0x18000536c  call    cs:__imp_CloseHandle
0x180005372  mov     rax, [rbp+47h+var_88]
0x180005376  cmp     [rax], r13d
0x180005379  jnz     loc_1800054B9
0x18000537f  call    cs:__imp_GetLastError
0x180005385  mov     edi, eax
0x180005387  call    cs:__imp_CurrentIP
0x18000538d  mov     r8, [rsi+48h]
0x180005391  lea     rdx, aCsetupfilescle_16; "CSetupFilesCleanup::Initialize - Cannot"...
0x180005398  mov     ecx, 4000000h; unsigned int
0x18000539d  mov     rbx, rax
0x1800053a0  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800053a5  mov     [rsp+120h+var_D0], r13d
0x1800053aa  lea     rsi, aCsetupfilescle_9; "CSetupFilesCleanup::Initialize"
0x1800053b1  mov     qword ptr [rsp+120h+var_D8], r13
0x1800053b6  lea     r12, aBaseNtsetupSet; "base\\ntsetup\\setup\\tools\\setupcln\\"...
0x1800053bd  mov     [rsp+120h+var_E0], edi
0x1800053c1  mov     qword ptr [rsp+120h+var_E8], rbx
0x1800053c6  mov     qword ptr [rsp+120h+var_F0], rsi
0x1800053cb  mov     qword ptr [rsp+120h+var_F8], r12
0x1800053d0  mov     [rsp+120h+var_100], 1E2h
0x1800053d8  jmp     short loc_180005432
0x1800053da  call    cs:__imp_GetLastError
0x1800053e0  mov     edi, eax
0x1800053e2  call    cs:__imp_CurrentIP
0x1800053e8  mov     r8d, r14d
0x1800053eb  lea     rdx, aCsetupfilescle; "CSetupFilesCleanup::Initialize - Initia"...
0x1800053f2  mov     ecx, 4000000h; unsigned int
0x1800053f7  mov     rbx, rax
0x1800053fa  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800053ff  mov     [rsp+120h+var_D0], r13d
0x180005404  lea     rsi, aCsetupfilescle_9; "CSetupFilesCleanup::Initialize"
0x18000540b  mov     qword ptr [rsp+120h+var_D8], r13
0x180005410  lea     r12, aBaseNtsetupSet; "base\\ntsetup\\setup\\tools\\setupcln\\"...
0x180005417  mov     [rsp+120h+var_E0], edi
0x18000541b  mov     qword ptr [rsp+120h+var_E8], rbx
0x180005420  mov     qword ptr [rsp+120h+var_F0], rsi
0x180005425  mov     qword ptr [rsp+120h+var_F8], r12
0x18000542a  mov     [rsp+120h+var_100], 1E8h
0x180005432  xor     r9d, r9d
0x180005435  lea     r8, aD; "D"
0x18000543c  xor     edx, edx
0x18000543e  mov     rcx, rax
0x180005441  call    cs:__imp_WdsSetupLogMessageW
0x180005447  mov     r14d, 1
0x18000544d  jmp     short loc_1800054C7
0x18000544f  mov     r10d, [r12]
0x180005453  mov     r9d, eax
0x180005456  shr     r10d, 7
0x18000545a  mov     r8d, eax
0x18000545d  and     r10d, 1
0x180005461  mov     dword ptr [rbp+47h+arg_18], eax
0x180005464  cmp     [rbp+47h+var_B8], eax
0x180005467  mov     edx, eax
0x180005469  mov     ecx, eax
0x18000546b  setnz   r9b
0x18000546f  test    edi, edi
0x180005471  setnz   r8b
0x180005475  cmp     [rbp+47h+var_B4], eax
0x180005478  mov     eax, [rsi+3Ch]
0x18000547b  mov     [rsp+120h+var_D8], eax; int
0x18000547f  setnz   dl
0x180005482  mov     [rsp+120h+var_E0], r10d; int
0x180005487  test    ebx, ebx
0x180005489  mov     [rsp+120h+var_E8], r9d; int
0x18000548e  mov     r9, r15
0x180005491  setnz   cl
0x180005494  mov     [rsp+120h+var_F0], r8d; int
0x180005499  mov     [rsp+120h+var_F8], edx; int
0x18000549d  xor     r8d, r8d
0x1800054a0  mov     [rsp+120h+var_100], ecx; int
0x1800054a4  xor     edx, edx
0x1800054a6  mov     rcx, r13; hKey
0x1800054a9  call    SetupClnLogInitializationInfo
0x1800054ae  mov     rax, [rbp+47h+lpMem]
0x1800054b2  xor     r13d, r13d
0x1800054b5  mov     [rbp+47h+lpMem], rax
0x1800054b9  lea     r12, aBaseNtsetupSet; "base\\ntsetup\\setup\\tools\\setupcln\\"...
0x1800054c0  lea     rsi, aCsetupfilescle_9; "CSetupFilesCleanup::Initialize"
0x1800054c7  call    cs:__imp_GetLastError
0x1800054cd  mov     edi, eax
0x1800054cf  call    cs:__imp_CurrentIP
0x1800054d5  mov     r8d, r14d
0x1800054d8  lea     rdx, aInitialization; "Initialization status:%x"
0x1800054df  mov     ecx, 4000000h; unsigned int
0x1800054e4  mov     rbx, rax
0x1800054e7  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800054ec  mov     [rsp+120h+var_D0], r13d
0x1800054f1  lea     r8, aD; "D"
0x1800054f8  mov     qword ptr [rsp+120h+var_D8], r13
0x1800054fd  xor     r9d, r9d
0x180005500  mov     [rsp+120h+var_E0], edi
0x180005504  xor     edx, edx
0x180005506  mov     qword ptr [rsp+120h+var_E8], rbx
0x18000550b  mov     rcx, rax
0x18000550e  mov     qword ptr [rsp+120h+var_F0], rsi
0x180005513  mov     qword ptr [rsp+120h+var_F8], r12
0x180005518  mov     [rsp+120h+var_100], 1FCh
0x180005520  call    cs:__imp_WdsSetupLogMessageW
0x180005526  call    cs:__imp_GetLastError
0x18000552c  mov     edi, eax
  ... truncated ...
```
