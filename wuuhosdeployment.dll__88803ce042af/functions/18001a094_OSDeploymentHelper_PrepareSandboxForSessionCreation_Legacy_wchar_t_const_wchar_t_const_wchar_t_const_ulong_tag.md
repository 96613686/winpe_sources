# OSDeploymentHelper::PrepareSandboxForSessionCreation_Legacy(wchar_t const *,wchar_t const *,wchar_t const *,ulong,tagDSFile * *,void *,tagOptionalSessionInfo6 const &,wchar_t * *)

- ea: `0x18001a094`
- end: `0x18001a681`
- name: `?PrepareSandboxForSessionCreation_Legacy@OSDeploymentHelper@@YAJPEB_W00KPEAPEAUtagDSFile@@PEAXAEBUtagOptionalSessionInfo6@@PEAPEA_W@Z`
- size: `1517`
- prototype: `__int64 __fastcall(wchar_t *this, const wchar_t *, const wchar_t *, const wchar_t *, __int64, struct tagDSFile **, _QWORD *, const struct tagOptionalSessionInfo6 *)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, reparse_path, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180022a8c`

## callees

- `0x180003950`
- `0x180005f64`
- `0x18000956c`
- `0x18000af44`
- `0x18000c634`
- `0x18000c684`
- `0x18000cbc4`
- `0x18000d904`
- `0x18000dd4c`
- `0x18000e05c`
- `0x18000e4d4`
- `0x18000ed84`
- `0x18000f534`
- `0x18000fe08`
- `0x180010f54`
- `0x180015fc8`
- `0x18001a094`
- `0x180042630`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001a319`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001a319`

## string_xrefs

- `0x18001a398`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test`
- `0x18001a41d`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test`
- `0x18001a1d5`: `Using the inbox service stack dll file '%ws' `
- `0x18001a23f`: `Failed to find the service stack cab file '%ws'`
- `0x18001a335`: `Using the update's service stack dll file '%ws' `
- `0x18001a416`: `AlternateServiceStackDLLPath`
- `0x18001a468`: `Using test service stack dll file '%ws' for Update ID '%ws'`
- `0x18001a4bb`: `Failed to find the service stack dll file '%ws'`

## pseudocode

```c
__int64 __fastcall OSDeploymentHelper::PrepareSandboxForSessionCreation_Legacy(
        wchar_t *this,
        const wchar_t *a2,
        const wchar_t *a3,
        const wchar_t *a4,
        __int64 a5,
        struct tagDSFile **a6,
        _QWORD *a7,
        const struct tagOptionalSessionInfo6 *a8)
{
  WCHAR *v11; // rbx
  __int64 v12; // rdx
  unsigned int v13; // ebx
  int CombinedPath; // eax
  unsigned __int64 v16; // rdx
  int SystemFilePath; // r15d
  wchar_t *v18; // r14
  __int64 v19; // rdx
  unsigned __int64 v20; // r9
  bool v21; // cl
  wchar_t *v22; // rdi
  __int64 v23; // rdx
  int v24; // eax
  int v25; // esi
  int v26; // eax
  void *v27; // r8
  const wchar_t *v28; // r9
  int v29; // eax
  int v30; // eax
  const wchar_t *v31; // rsi
  __int64 v32; // rdx
  wchar_t *v33; // rcx
  const wchar_t *v34; // r8
  wchar_t v35; // ax
  wchar_t *v36; // rax
  __int64 v37; // rcx
  PCNZWCH v38; // rcx
  WCHAR *v39; // rdi
  unsigned int v40; // edx
  void *v41; // r8
  int DirectoryW; // eax
  unsigned int v43; // r12d
  void *v44; // rsi
  WCHAR *v45; // rax
  __int64 v46; // rdx
  void *v47; // [rsp+20h] [rbp-E0h]
  PCNZWCH v48; // [rsp+30h] [rbp-D0h]
  PCNZWCH v49; // [rsp+40h] [rbp-C0h] BYREF
  PCNZWCH lpString1; // [rsp+48h] [rbp-B8h] BYREF
  void *lpMem; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v52; // [rsp+58h] [rbp-A8h]
  wchar_t *v53; // [rsp+60h] [rbp-A0h]
  const struct tagOptionalSessionInfo6 *v54; // [rsp+68h] [rbp-98h]
  wchar_t v55[264]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  v52 = (unsigned int)a4;
  v53 = this;
  v54 = a8;
  v11 = 0;
  if ( !this )
  {
    v12 = 403;
LABEL_3:
    v13 = -2147024809;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Helper\\OSDeploymentHelper.cpp",
      (const char *)v13,
      (int)v47);
    return v13;
  }
  if ( !a3 )
  {
    v12 = 404;
    goto LABEL_3;
  }
  if ( !a8 )
  {
    v13 = -2147467261;
    v12 = 405;
    goto LABEL_4;
  }
  lpString1 = 0;
  CombinedPath = CreateCombinedPath(this, L"Metadata", (wchar_t **)&lpString1);
  SystemFilePath = CombinedPath;
  v18 = (wchar_t *)lpString1;
  if ( CombinedPath >= 0 )
  {
    v49 = 0;
    if ( !a2 )
    {
      SystemFilePath = GetSystemFilePath(v55, v16, a3);
      if ( SystemFilePath < 0 )
      {
        v19 = 417;
LABEL_16:
        v20 = (unsigned int)SystemFilePath;
LABEL_62:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v19,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Helper\\OSDeploymentHelper.cpp",
          (const char *)v20,
          (int)v47);
        goto LABEL_73;
      }
      SystemFilePath = DuplicateString<wchar_t *,wchar_t *>(v55, &v49);
      v11 = (WCHAR *)v49;
      if ( SystemFilePath < 0 )
      {
        v19 = 419;
        goto LABEL_16;
      }
      v48 = v49;
      v47 = 0;
      WUTrace(0, 0, 4096, 4);
      goto LABEL_35;
    }
    lpMem = 0;
    SystemFilePath = CreateCombinedPath(v53, a2, (wchar_t **)&lpMem);
    v22 = (wchar_t *)lpMem;
    if ( SystemFilePath >= 0 )
    {
      SystemFilePath = CheckIfFileExists((const wchar_t *)lpMem);
      if ( SystemFilePath >= 0 )
      {
        v24 = CreateCombinedPath(v18, a3, (wchar_t **)&v49);
        SystemFilePath = v24;
        v25 = 0;
        if ( v24 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1BE,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Helper\\OSDeploymentHelper.cpp",
            (const char *)(unsigned int)v24,
            (int)v47);
          v11 = (WCHAR *)v49;
          goto LABEL_84;
        }
        v26 = CheckIfDirExists(v18);
        v11 = (WCHAR *)v49;
        if ( v26 < 0
          || (v29 = SusDeleteFileRetryIfSharingViolation(v49, 6u, v27), SystemFilePath = v29, v29 > -2147024895)
          && (unsigned int)(v29 + 2147024892) > 0x7FF8FFFB )
        {
          while ( 1 )
          {
            v30 = DecompressCabFile(v22, v18, (unsigned int)v27, v28, v47);
            SystemFilePath = v30;
            if ( v30 >= 0 )
              break;
            if ( v30 == -2147024864 )
            {
              Sleep(0x2710u);
              if ( (unsigned int)++v25 < 6 )
                continue;
            }
            v23 = 481;
            goto LABEL_83;
          }
          v48 = v11;
          v47 = 0;
          WUTrace(0, 0, 4096, 4);
          if ( v22 )
            CSusBaseAllocTag<942762101>::operator delete(v22);
LABEL_35:
          if ( (unsigned int)AreTestKeysAllowed(v21) )
          {
            v31 = L"Global";
            if ( a6 && a7[1] )
              v31 = (const wchar_t *)a7[1];
            v32 = 260;
            v33 = v55;
            v34 = (const wchar_t *)((char *)L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test"
                                  - (char *)v55);
            do
            {
              if ( v32 == -2147483386 )
                break;
              v35 = *(const wchar_t *)((char *)v34 + (_QWORD)v33);
              if ( !v35 )
                break;
              *v33++ = v35;
              --v32;
            }
            while ( v32 );
            v36 = v33 - 1;
            if ( v32 )
              v36 = v33;
            *v36 = 0;
            WUPathCchAppend(v55, v32, v34);
            lpString1 = 0;
            if ( (int)RegQueryStringValue(v37, v55, v31, &lpString1) >= 0 )
              goto LABEL_50;
            v38 = lpString1;
            if ( lpString1 )
            {
              CSusBaseAllocTag<942762101>::operator delete((void *)lpString1);
              lpString1 = 0;
            }
            if ( (int)RegQueryStringValue(
                        v38,
                        L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test",
                        L"AlternateServiceStackDLLPath",
                        &lpString1) >= 0 )
            {
LABEL_50:
              if ( v11 )
              {
                CSusBaseAllocTag<942762101>::operator delete(v11);
                v49 = 0;
              }
              v39 = (WCHAR *)lpString1;
              if ( (int)DuplicateString<wchar_t *,wchar_t *>(lpString1, &v49) >= 0 )
              {
                v48 = v39;
                v47 = 0;
                WUTrace(0, 0, 4096, 4);
              }
              v11 = (WCHAR *)v49;
            }
            else
            {
              v39 = (WCHAR *)lpString1;
            }
            if ( v39 )
              CSusBaseAllocTag<942762101>::operator delete(v39);
          }
          SystemFilePath = CheckIfFileExists(v11);
          if ( SystemFilePath < 0 )
          {
            wil::details::in1diag3::Return_HrMsg(
              retaddr,
              (void *)0x212,
              (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Helper\\OSDeploymentHelper.cpp",
              (const char *)(unsigned int)SystemFilePath,
              (int)"Failed to find the service stack dll file '%ws'",
              (const char *)v11,
              v48);
            goto LABEL_73;
          }
          if ( !v52 )
          {
LABEL_72:
            v45 = v11;
            v11 = 0;
            *(_QWORD *)v54 = v45;
            SystemFilePath = 0;
LABEL_73:
            if ( v11 )
              CSusBaseAllocTag<942762101>::operator delete(v11);
            goto LABEL_75;
          }
          DirectoryW = SusMakeDirectoryW(v18, v40, v41);
          SystemFilePath = DirectoryW;
          if ( DirectoryW < 0 )
          {
            v20 = (unsigned int)DirectoryW;
            v19 = 535;
            goto LABEL_62;
          }
          v43 = 0;
          while ( 1 )
          {
            lpMem = 0;
            SystemFilePath = CreateCombinedPath(v53, *(const wchar_t **)(*(_QWORD *)a5 + 72LL), (wchar_t **)&lpMem);
            v22 = (wchar_t *)lpMem;
            if ( SystemFilePath < 0 )
            {
              v23 = 542;
              goto LABEL_83;
            }
            lpMem = 0;
            SystemFilePath = CreateCombinedPath(v18, *(const wchar_t **)(*(_QWORD *)a5 + 72LL), (wchar_t **)&lpMem);
            v44 = lpMem;
            if ( SystemFilePath < 0 )
              break;
            SystemFilePath = SusCopyFileRetryIfSharingViolation(v22, (LPCWSTR)lpMem, 0, 0xAu, v47);
            if ( SystemFilePath < 0 )
            {
              v46 = 551;
              goto LABEL_80;
            }
            if ( v44 )
              CSusBaseAllocTag<942762101>::operator delete(v44);
            if ( v22 )
              CSusBaseAllocTag<942762101>::operator delete(v22);
            ++v43;
            a5 += 8;
            if ( v43 >= v52 )
              goto LABEL_72;
          }
          v46 = 546;
LABEL_80:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v46,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Helper\\OSDeploymentHelper.cpp",
            (const char *)(unsigned int)SystemFilePath,
            (int)v47);
          if ( v44 )
            CSusBaseAllocTag<942762101>::operator delete(v44);
LABEL_84:
          if ( v22 )
            CSusBaseAllocTag<942762101>::operator delete(v22);
          goto LABEL_73;
        }
        v23 = 459;
      }
      else
      {
        LODWORD(v47) = SystemFilePath;
        WUTrace(0, 0, 4096, 1);
        if ( (unsigned int)(SystemFilePath + 2147024894) <= 1 )
          goto LABEL_84;
        v23 = 443;
      }
    }
    else
    {
      v23 = 429;
    }
LABEL_83:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v23,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Helper\\OSDeploymentHelper.cpp",
      (const char *)(unsigned int)SystemFilePath,
      (int)v47);
    goto LABEL_84;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x198,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Helper\\OSDeploymentHelper.cpp",
    (const char *)(unsigned int)CombinedPath,
    (int)v47);
LABEL_75:
  if ( v18 )
    CSusBaseAllocTag<942762101>::operator delete(v18);
  return (unsigned int)SystemFilePath;
}

```

## disassembly

```asm
0x18001a094  mov     [rsp-8+arg_18], rbx
0x18001a099  push    rbp
0x18001a09a  push    rsi
0x18001a09b  push    rdi
0x18001a09c  push    r12
0x18001a09e  push    r13
0x18001a0a0  push    r14
0x18001a0a2  push    r15
0x18001a0a4  lea     rbp, [rsp-190h]
0x18001a0ac  sub     rsp, 290h
0x18001a0b3  mov     rax, cs:__security_cookie
0x18001a0ba  xor     rax, rsp
0x18001a0bd  mov     [rbp+1C0h+var_40], rax
0x18001a0c4  mov     [rsp+2C0h+var_268], r9d
0x18001a0c9  mov     rsi, r8
0x18001a0cc  mov     rdi, rdx
0x18001a0cf  mov     rax, rcx
0x18001a0d2  mov     [rsp+2C0h+var_260], rcx
0x18001a0d7  mov     r13, [rbp+1C0h+arg_20]
0x18001a0de  mov     r12, [rbp+1C0h+arg_30]
0x18001a0e5  mov     rcx, [rbp+1C0h+arg_38]
0x18001a0ec  mov     [rsp+2C0h+var_258], rcx
0x18001a0f1  xor     ebx, ebx
0x18001a0f3  test    rax, rax
0x18001a0f6  jnz     short loc_18001A11F
0x18001a0f8  mov     edx, 193h; void *
0x18001a0fd  mov     ebx, 80070057h
0x18001a102  mov     rcx, [rbp+1C8h]; this
0x18001a109  mov     r9d, ebx; char *
0x18001a10c  lea     r8, aCW1SSrcClientE_13; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18001a113  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a118  mov     eax, ebx
0x18001a11a  jmp     loc_18001A5F4
0x18001a11f  test    rsi, rsi
0x18001a122  jnz     short loc_18001A12B
0x18001a124  mov     edx, 194h
0x18001a129  jmp     short loc_18001A0FD
0x18001a12b  test    rcx, rcx
0x18001a12e  jnz     short loc_18001A13C
0x18001a130  mov     ebx, 80004003h
0x18001a135  mov     edx, 195h
0x18001a13a  jmp     short loc_18001A102
0x18001a13c  mov     [rsp+2C0h+lpString1], rbx
0x18001a141  lea     r8, [rsp+2C0h+lpString1]; wchar_t **
0x18001a146  lea     rdx, aMetadata; "Metadata"
0x18001a14d  mov     rcx, rax; wchar_t *
0x18001a150  call    ?CreateCombinedPath@@YAJPEB_W0PEAPEA_W@Z; CreateCombinedPath(wchar_t const *,wchar_t const *,wchar_t * *)
0x18001a155  mov     r15d, eax
0x18001a158  mov     r14, [rsp+2C0h+lpString1]
0x18001a15d  test    eax, eax
0x18001a15f  jns     short loc_18001A181
0x18001a161  mov     rcx, [rbp+1C8h]; this
0x18001a168  mov     r9d, eax; char *
0x18001a16b  lea     r8, aCW1SSrcClientE_13; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18001a172  mov     edx, 198h; void *
0x18001a177  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a17c  jmp     loc_18001A5E4
0x18001a181  mov     [rsp+2C0h+var_280], rbx
0x18001a186  xor     eax, eax
0x18001a188  test    rdi, rdi
0x18001a18b  jnz     short loc_18001A1FE
0x18001a18d  mov     r8, rsi; wchar_t *
0x18001a190  lea     rcx, [rsp+2C0h+var_250]; wchar_t *
0x18001a195  call    ?GetSystemFilePath@@YAJPEA_W_KPEB_W@Z; GetSystemFilePath(wchar_t *,unsigned __int64,wchar_t const *)
0x18001a19a  mov     r15d, eax
0x18001a19d  test    eax, eax
0x18001a19f  jns     short loc_18001A1A8
0x18001a1a1  mov     edx, 1A1h
0x18001a1a6  jmp     short loc_18001A1C8
0x18001a1a8  lea     rdx, [rsp+2C0h+var_280]
0x18001a1ad  lea     rcx, [rsp+2C0h+var_250]
0x18001a1b2  call    ??$DuplicateString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z; DuplicateString<wchar_t *,wchar_t *>(wchar_t *,wchar_t * *)
0x18001a1b7  mov     r15d, eax
0x18001a1ba  mov     rbx, [rsp+2C0h+var_280]
0x18001a1bf  test    eax, eax
0x18001a1c1  jns     short loc_18001A1D0
0x18001a1c3  mov     edx, 1A3h
0x18001a1c8  mov     r9d, r15d
0x18001a1cb  jmp     loc_18001A501
0x18001a1d0  mov     [rsp+2C0h+var_290], rbx
0x18001a1d5  lea     rax, aUsingTheInboxS; "Using the inbox service stack dll file "...
0x18001a1dc  mov     [rsp+2C0h+var_298], rax
0x18001a1e1  mov     [rsp+2C0h+var_2A0], rdi
0x18001a1e6  xor     edx, edx
0x18001a1e8  xor     ecx, ecx
0x18001a1ea  lea     r9d, [rdx+4]
0x18001a1ee  mov     r8d, 1000h
0x18001a1f4  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18001a1f9  jmp     loc_18001A366
0x18001a1fe  mov     [rsp+2C0h+lpMem], rax
0x18001a203  lea     r8, [rsp+2C0h+lpMem]; wchar_t **
0x18001a208  mov     rdx, rdi; wchar_t *
0x18001a20b  mov     rcx, [rsp+2C0h+var_260]; wchar_t *
0x18001a210  call    ?CreateCombinedPath@@YAJPEB_W0PEAPEA_W@Z; CreateCombinedPath(wchar_t const *,wchar_t const *,wchar_t * *)
0x18001a215  mov     r15d, eax
0x18001a218  mov     rdi, [rsp+2C0h+lpMem]
0x18001a21d  test    eax, eax
0x18001a21f  jns     short loc_18001A22B
0x18001a221  mov     edx, 1ADh
0x18001a226  jmp     loc_18001A654
0x18001a22b  mov     rcx, rdi; wchar_t *
0x18001a22e  call    ?CheckIfFileExists@@YAJPEB_W@Z; CheckIfFileExists(wchar_t const *)
0x18001a233  mov     r15d, eax
0x18001a236  test    eax, eax
0x18001a238  jns     short loc_18001A27D
0x18001a23a  mov     [rsp+2C0h+var_290], rdi
0x18001a23f  lea     rax, aFailedToFindTh_0; "Failed to find the service stack cab fi"...
0x18001a246  mov     [rsp+2C0h+var_298], rax
0x18001a24b  mov     dword ptr [rsp+2C0h+var_2A0], r15d
0x18001a250  xor     edx, edx
0x18001a252  xor     ecx, ecx
0x18001a254  lea     r9d, [rdx+1]
0x18001a258  mov     r8d, 1000h
0x18001a25e  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18001a263  lea     eax, [r15+7FF8FFFEh]
0x18001a26a  cmp     eax, 1
0x18001a26d  jbe     loc_18001A66A
0x18001a273  mov     edx, 1BBh
0x18001a278  jmp     loc_18001A654
0x18001a27d  lea     r8, [rsp+2C0h+var_280]; wchar_t **
0x18001a282  mov     rdx, rsi; wchar_t *
0x18001a285  mov     rcx, r14; wchar_t *
0x18001a288  call    ?CreateCombinedPath@@YAJPEB_W0PEAPEA_W@Z; CreateCombinedPath(wchar_t const *,wchar_t const *,wchar_t * *)
0x18001a28d  mov     r15d, eax
0x18001a290  xor     esi, esi
0x18001a292  test    eax, eax
0x18001a294  jns     short loc_18001A2BB
0x18001a296  mov     rcx, [rbp+1C8h]; this
0x18001a29d  mov     r9d, eax; char *
0x18001a2a0  lea     r8, aCW1SSrcClientE_13; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18001a2a7  mov     edx, 1BEh; void *
0x18001a2ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a2b1  mov     rbx, [rsp+2C0h+var_280]
0x18001a2b6  jmp     loc_18001A66A
0x18001a2bb  mov     rcx, r14; wchar_t *
0x18001a2be  call    ?CheckIfDirExists@@YAJPEB_W@Z; CheckIfDirExists(wchar_t const *)
0x18001a2c3  mov     rbx, [rsp+2C0h+var_280]
0x18001a2c8  test    eax, eax
0x18001a2ca  js      short loc_18001A2F9
0x18001a2cc  mov     edx, 6; unsigned int
0x18001a2d1  mov     rcx, rbx; lpString1
0x18001a2d4  call    ?SusDeleteFileRetryIfSharingViolation@@YAJPEB_WKPEAX@Z; SusDeleteFileRetryIfSharingViolation(wchar_t const *,ulong,void *)
0x18001a2d9  mov     r15d, eax
0x18001a2dc  cmp     eax, 80070001h
0x18001a2e1  jle     short loc_18001A2EF
0x18001a2e3  add     eax, 7FF8FFFCh
0x18001a2e8  cmp     eax, 7FF8FFFBh
0x18001a2ed  ja      short loc_18001A2F9
0x18001a2ef  mov     edx, 1CBh
0x18001a2f4  jmp     loc_18001A654
0x18001a2f9  mov     rdx, r14; wchar_t *
0x18001a2fc  mov     rcx, rdi; wchar_t *
0x18001a2ff  call    ?DecompressCabFile@@YAJPEB_W0K0PEAX@Z; DecompressCabFile(wchar_t const *,wchar_t const *,ulong,wchar_t const *,void *)
0x18001a304  mov     r15d, eax
0x18001a307  xor     ecx, ecx
0x18001a309  test    eax, eax
0x18001a30b  jns     short loc_18001A330
0x18001a30d  cmp     eax, 80070020h
0x18001a312  jnz     short loc_18001A326
0x18001a314  mov     ecx, 2710h; dwMilliseconds
0x18001a319  call    cs:__imp_Sleep
0x18001a31f  inc     esi
0x18001a321  cmp     esi, 6
0x18001a324  jb      short loc_18001A2F9
0x18001a326  mov     edx, 1E1h
0x18001a32b  jmp     loc_18001A654
0x18001a330  mov     [rsp+2C0h+var_290], rbx
0x18001a335  lea     rax, aUsingTheUpdate; "Using the update's service stack dll fi"...
0x18001a33c  mov     [rsp+2C0h+var_298], rax
0x18001a341  mov     [rsp+2C0h+var_2A0], rcx
0x18001a346  xor     edx, edx
0x18001a348  lea     r9d, [rdx+4]
0x18001a34c  mov     r8d, 1000h
0x18001a352  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18001a357  test    rdi, rdi
0x18001a35a  jz      short loc_18001A364
0x18001a35c  mov     rcx, rdi; lpMem
0x18001a35f  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x18001a364  xor     edi, edi
0x18001a366  call    ?AreTestKeysAllowed@@YAH_N@Z; AreTestKeysAllowed(bool)
0x18001a36b  test    eax, eax
0x18001a36d  jz      loc_18001A4A0
0x18001a373  lea     rsi, aGlobal; "Global"
0x18001a37a  cmp     [rbp+1C0h+arg_28], rdi
0x18001a381  jz      short loc_18001A38E
0x18001a383  cmp     [r12+8], rdi
0x18001a388  cmovnz  rsi, [r12+8]
0x18001a38e  mov     edx, 104h
0x18001a393  lea     rcx, [rsp+2C0h+var_250]
0x18001a398  lea     r8, ?c_szRegWUTest@@3QB_WB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18001a39f  lea     rax, [rsp+2C0h+var_250]
0x18001a3a4  sub     r8, rax; wchar_t *
0x18001a3a7  lea     rax, [rdx+7FFFFEFAh]
0x18001a3ae  test    rax, rax
0x18001a3b1  jz      short loc_18001A3CA
0x18001a3b3  movzx   eax, word ptr [rcx+r8]
0x18001a3b8  test    ax, ax
0x18001a3bb  jz      short loc_18001A3CA
0x18001a3bd  mov     [rcx], ax
0x18001a3c0  add     rcx, 2
0x18001a3c4  sub     rdx, 1; unsigned int
0x18001a3c8  jnz     short loc_18001A3A7
0x18001a3ca  lea     rax, [rcx-2]
0x18001a3ce  test    rdx, rdx
0x18001a3d1  cmovnz  rax, rcx
0x18001a3d5  mov     [rax], di
0x18001a3d8  lea     rcx, [rsp+2C0h+var_250]; wchar_t *
0x18001a3dd  call    ?WUPathCchAppend@@YAJPEA_WKPEB_W@Z; WUPathCchAppend(wchar_t *,ulong,wchar_t const *)
0x18001a3e2  mov     [rsp+2C0h+lpString1], rdi
0x18001a3e7  lea     r9, [rsp+2C0h+lpString1]
0x18001a3ec  mov     r8, rsi
0x18001a3ef  lea     rdx, [rsp+2C0h+var_250]
0x18001a3f4  call    ?RegQueryStringValue@@YAJPEAUHKEY__@@PEB_W1PEAPEA_WW4RegistryHiveType@@@Z; RegQueryStringValue(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t * *,RegistryHiveType)
0x18001a3f9  test    eax, eax
0x18001a3fb  jns     short loc_18001A434
0x18001a3fd  mov     rcx, [rsp+2C0h+lpString1]; lpMem
0x18001a402  test    rcx, rcx
0x18001a405  jz      short loc_18001A411
0x18001a407  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x18001a40c  mov     [rsp+2C0h+lpString1], rdi
0x18001a411  lea     r9, [rsp+2C0h+lpString1]
0x18001a416  lea     r8, aAlternateservi; "AlternateServiceStackDLLPath"
0x18001a41d  lea     rdx, ?c_szRegWUTest@@3QB_WB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18001a424  call    ?RegQueryStringValue@@YAJPEAUHKEY__@@PEB_W1PEAPEA_WW4RegistryHiveType@@@Z; RegQueryStringValue(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t * *,RegistryHiveType)
0x18001a429  test    eax, eax
0x18001a42b  jns     short loc_18001A434
0x18001a42d  mov     rdi, [rsp+2C0h+lpString1]
0x18001a432  jmp     short loc_18001A491
0x18001a434  test    rbx, rbx
0x18001a437  jz      short loc_18001A446
0x18001a439  mov     rcx, rbx; lpMem
0x18001a43c  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x18001a441  mov     [rsp+2C0h+var_280], rdi
0x18001a446  lea     rdx, [rsp+2C0h+var_280]
0x18001a44b  mov     rdi, [rsp+2C0h+lpString1]
0x18001a450  mov     rcx, rdi
0x18001a453  call    ??$DuplicateString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z; DuplicateString<wchar_t *,wchar_t *>(wchar_t *,wchar_t * *)
0x18001a458  xor     ebx, ebx
0x18001a45a  test    eax, eax
0x18001a45c  js      short loc_18001A48C
0x18001a45e  mov     [rsp+2C0h+var_288], rsi
0x18001a463  mov     [rsp+2C0h+var_290], rdi
0x18001a468  lea     rax, aUsingTestServi; "Using test service stack dll file '%ws'"...
0x18001a46f  mov     [rsp+2C0h+var_298], rax
0x18001a474  mov     [rsp+2C0h+var_2A0], rbx; int
0x18001a479  xor     edx, edx
0x18001a47b  xor     ecx, ecx
0x18001a47d  lea     r9d, [rbx+4]
0x18001a481  mov     r8d, 1000h
0x18001a487  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18001a48c  mov     rbx, [rsp+2C0h+var_280]
0x18001a491  test    rdi, rdi
0x18001a494  jz      short loc_18001A49E
0x18001a496  mov     rcx, rdi; lpMem
0x18001a499  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x18001a49e  xor     edi, edi
0x18001a4a0  mov     rcx, rbx; wchar_t *
0x18001a4a3  call    ?CheckIfFileExists@@YAJPEB_W@Z; CheckIfFileExists(wchar_t const *)
0x18001a4a8  mov     r15d, eax
0x18001a4ab  test    eax, eax
0x18001a4ad  jns     short loc_18001A4E0
0x18001a4af  mov     rcx, [rbp+1C8h]; this
0x18001a4b6  mov     [rsp+2C0h+var_298], rbx; char *
0x18001a4bb  lea     rax, aFailedToFindTh_1; "Failed to find the service stack dll fi"...
0x18001a4c2  mov     [rsp+2C0h+var_2A0], rax; int
0x18001a4c7  mov     r9d, r15d; char *
0x18001a4ca  lea     r8, aCW1SSrcClientE_13; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18001a4d1  mov     edx, 212h; void *
0x18001a4d6  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001a4db  jmp     loc_18001A5D6
0x18001a4e0  cmp     [rsp+2C0h+var_268], edi
0x18001a4e4  jbe     loc_18001A5C5
0x18001a4ea  mov     rcx, r14; lpString1
0x18001a4ed  call    ?SusMakeDirectoryW@@YAJPEB_WKPEAX@Z; SusMakeDirectoryW(wchar_t const *,ulong,void *)
0x18001a4f2  mov     r15d, eax
0x18001a4f5  test    eax, eax
0x18001a4f7  jns     short loc_18001A519
0x18001a4f9  mov     r9d, eax; char *
0x18001a4fc  mov     edx, 217h; void *
0x18001a501  lea     r8, aCW1SSrcClientE_13; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18001a508  mov     rcx, [rbp+1C8h]; this
0x18001a50f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a514  jmp     loc_18001A5D6
0x18001a519  mov     r12d, edi
0x18001a51c  mov     [rsp+2C0h+lpMem], rdi
0x18001a521  mov     rdx, [r13+0]
0x18001a525  lea     r8, [rsp+2C0h+lpMem]; wchar_t **
0x18001a52a  mov     rdx, [rdx+48h]; wchar_t *
0x18001a52e  mov     rcx, [rsp+2C0h+var_260]; wchar_t *
0x18001a533  call    ?CreateCombinedPath@@YAJPEB_W0PEAPEA_W@Z; CreateCombinedPath(wchar_t const *,wchar_t const *,wchar_t * *)
0x18001a538  mov     r15d, eax
0x18001a53b  mov     rdi, [rsp+2C0h+lpMem]
0x18001a540  xor     eax, eax
0x18001a542  test    r15d, r15d
0x18001a545  js      loc_18001A64F
0x18001a54b  mov     [rsp+2C0h+lpMem], rax
0x18001a550  mov     rdx, [r13+0]
0x18001a554  lea     r8, [rsp+2C0h+lpMem]; wchar_t **
0x18001a559  mov     rdx, [rdx+48h]; wchar_t *
0x18001a55d  mov     rcx, r14; wchar_t *
  ... truncated ...
```
