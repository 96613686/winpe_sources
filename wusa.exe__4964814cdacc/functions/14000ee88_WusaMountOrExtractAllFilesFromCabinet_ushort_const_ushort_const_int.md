# WusaMountOrExtractAllFilesFromCabinet(ushort const *,ushort const *,int *)

- ea: `0x14000ee88`
- end: `0x14000f238`
- name: `?WusaMountOrExtractAllFilesFromCabinet@@YAJPEBG0PEAH@Z`
- size: `944`
- prototype: `__int64 __fastcall(LPCWSTR TargetPath, LPCWSTR pszPath, int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x1400075b0`
- `0x14000afc0`

## callees

- `0x14000e280`
- `0x14000ee88`
- `0x140013490`
- `0x140015010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x14000f218`
- `KERNEL32!LocalFree` at `0x14000f218`
- `KERNEL32!GetLastError` at `0x14000f08e`
- `KERNEL32!GetLastError` at `0x14000f0cb`
- `KERNEL32!GetLastError` at `0x14000f108`
- `KERNEL32!GetLastError` at `0x14000f145`
- `KERNEL32!GetLastError` at `0x14000f08e`
- `KERNEL32!GetLastError` at `0x14000f0cb`
- `KERNEL32!GetLastError` at `0x14000f108`
- `KERNEL32!GetLastError` at `0x14000f145`
- `msvcrt!_wcsicmp` at `0x14000eecb`
- `msvcrt!_wcsicmp` at `0x14000eee3`
- `msvcrt!_wcsicmp` at `0x14000eecb`
- `msvcrt!_wcsicmp` at `0x14000eee3`
- `SHLWAPI!PathFindExtensionW` at `0x14000eeb8`
- `SHLWAPI!PathFindExtensionW` at `0x14000eeb8`
- `dpx!DpxNewJob` at `0x14000eefb`
- `dpx!DpxNewJob` at `0x14000eefb`
- `WIMGAPI!WIMCreateFile` at `0x14000f080`
- `WIMGAPI!WIMCreateFile` at `0x14000f080`
- `WIMGAPI!WIMSetTemporaryPath` at `0x14000f0c1`
- `WIMGAPI!WIMSetTemporaryPath` at `0x14000f0c1`
- `WIMGAPI!WIMLoadImage` at `0x14000f0fa`
- `WIMGAPI!WIMLoadImage` at `0x14000f0fa`
- `WIMGAPI!WIMApplyImage` at `0x14000f13b`
- `WIMGAPI!WIMApplyImage` at `0x14000f13b`
- `WIMGAPI!WIMCloseHandle` at `0x14000f187`
- `WIMGAPI!WIMCloseHandle` at `0x14000f195`
- `WIMGAPI!WIMCloseHandle` at `0x14000f187`
- `WIMGAPI!WIMCloseHandle` at `0x14000f195`

## string_xrefs

- `0x14000ef0a`: `Failed to create extract job for location: %S`
- `0x14000ef16`: `WusaMountOrExtractAllFilesFromCabinet`
- `0x14000efaa`: `WusaMountOrExtractAllFilesFromCabinet`
- `0x14000f16a`: `WusaMountOrExtractAllFilesFromCabinet`
- `0x14000f204`: `WusaMountOrExtractAllFilesFromCabinet`
- `0x14000efd5`: `Failed to remove DPX container for cabinet: %ws`
- `0x14000f0aa`: `WIMCreateFile failed for %ws`
- `0x14000f0e4`: `WIMSetTemporaryPath failed!`

## pseudocode

```c
__int64 __fastcall WusaMountOrExtractAllFilesFromCabinet(LPCWSTR TargetPath, LPCWSTR pszPath, int *a3)
{
  __int64 v3; // rsi
  __int64 v5; // r14
  const wchar_t *ExtensionW; // rbx
  int v9; // r12d
  signed int v10; // ebx
  int v11; // eax
  signed int LastError; // eax
  signed int v13; // eax
  signed int v14; // eax
  signed int v15; // eax
  HLOCAL v16; // rdi
  HLOCAL hMem; // [rsp+30h] [rbp-10h] BYREF
  IDpxJob *ppJob; // [rsp+90h] [rbp+50h] BYREF
  __int64 v20; // [rsp+98h] [rbp+58h] BYREF

  v3 = 0;
  ppJob = 0;
  v20 = 0;
  v5 = 0;
  ExtensionW = PathFindExtensionW(pszPath);
  if ( !_wcsicmp(ExtensionW, L".wim") || !_wcsicmp(ExtensionW, L".msu2") )
  {
    v10 = 0;
    v9 = 1;
LABEL_22:
    v3 = WIMCreateFile(pszPath, 0x80000000LL, 3);
    if ( v3 )
      goto LABEL_30;
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    if ( v10 >= 0 )
    {
LABEL_30:
      if ( (unsigned int)WIMSetTemporaryPath(v3, TargetPath) )
        goto LABEL_32;
      v13 = GetLastError();
      v10 = v13;
      if ( v13 > 0 )
        v10 = (unsigned __int16)v13 | 0x80070000;
      if ( v10 >= 0 )
      {
LABEL_32:
        v5 = WIMLoadImage(v3, 1);
        if ( v5 )
          goto LABEL_58;
        v14 = GetLastError();
        v10 = v14;
        if ( v14 > 0 )
          v10 = (unsigned __int16)v14 | 0x80070000;
        if ( v10 >= 0 )
        {
LABEL_58:
          if ( !(unsigned int)WIMApplyImage(v5, TargetPath, 2) )
          {
            v15 = GetLastError();
            v10 = v15;
            if ( v15 > 0 )
              v10 = (unsigned __int16)v15 | 0x80070000;
            if ( v10 < 0 )
              WusaLogDebugEventA(L"WusaMountOrExtractAllFilesFromCabinet", 559, "WIMApplyImage failed!");
          }
        }
        else
        {
          WusaLogDebugEventA(L"WusaMountOrExtractAllFilesFromCabinet", 553, "WIMLoadImage failed!");
        }
      }
      else
      {
        WusaLogDebugEventA(L"WusaMountOrExtractAllFilesFromCabinet", 546, "WIMSetTemporaryPath failed!");
      }
    }
    else
    {
      WusaLogDebugEventA(L"WusaMountOrExtractAllFilesFromCabinet", 538, "WIMCreateFile failed for %ws", pszPath);
    }
    goto LABEL_42;
  }
  v9 = 0;
  v10 = DpxNewJob(TargetPath, &ppJob);
  if ( v10 < 0 )
  {
    WusaLogDebugEventA(
      L"WusaMountOrExtractAllFilesFromCabinet",
      494,
      "Failed to create extract job for location: %S",
      TargetPath);
    goto LABEL_42;
  }
  v10 = ((__int64 (__fastcall *)(IDpxJob *, LPCWSTR, __int64 *))ppJob->lpVtbl->AddContainer)(ppJob, pszPath, &v20);
  if ( v10 < 0 )
  {
    WusaLogDebugEventA(
      L"WusaMountOrExtractAllFilesFromCabinet",
      497,
      "Failed to add container for cabinet: %S",
      pszPath);
    goto LABEL_42;
  }
  v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v20 + 56LL))(v20);
  if ( v10 < 0 )
  {
    WusaLogDebugEventA(L"WusaMountOrExtractAllFilesFromCabinet", 500, "Failed: ExtractAllFiles()");
    goto LABEL_42;
  }
  v11 = ((__int64 (__fastcall *)(IDpxJob *, _QWORD))ppJob->lpVtbl->Resume)(ppJob, 0);
  v10 = v11;
  if ( v11 == -905928699 )
  {
    v9 = 1;
    WusaLogDebugEventA(
      L"WusaMountOrExtractAllFilesFromCabinet",
      509,
      "Unsupported container type from cabinet %ws. Trying wim",
      pszPath);
    v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v20 + 112LL))(v20);
    if ( v10 < 0 )
    {
      WusaLogDebugEventA(
        L"WusaMountOrExtractAllFilesFromCabinet",
        512,
        "Failed to remove DPX container for cabinet: %ws",
        pszPath);
      goto LABEL_42;
    }
    v10 = ((__int64 (__fastcall *)(IDpxJob *))ppJob->lpVtbl->Cancel)(ppJob);
    if ( v10 < 0 )
    {
      WusaLogDebugEventA(
        L"WusaMountOrExtractAllFilesFromCabinet",
        515,
        "Failed to cancel DPX job for cabinet: %ws",
        pszPath);
      goto LABEL_42;
    }
    if ( v20 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      v20 = 0;
    }
    if ( ppJob )
    {
      ((void (__fastcall *)(IDpxJob *))ppJob->lpVtbl->Release)(ppJob);
      ppJob = 0;
    }
    goto LABEL_22;
  }
  if ( v11 < 0 )
    WusaLogDebugEventA(
      L"WusaMountOrExtractAllFilesFromCabinet",
      522,
      "Failed to extract files from cabinet %ws",
      pszPath);
LABEL_42:
  if ( a3 )
    *a3 = v9;
  if ( v5 )
    WIMCloseHandle(v5);
  if ( v3 )
    WIMCloseHandle(v3);
  if ( v20 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    v20 = 0;
  }
  if ( ppJob )
  {
    ((void (__fastcall *)(IDpxJob *))ppJob->lpVtbl->Release)(ppJob);
    ppJob = 0;
  }
  if ( v10 < 0 )
  {
    hMem = 0;
    WusaGetErrorMessage(v10, (unsigned __int16 **)&hMem);
    v16 = hMem;
    WusaLogDebugEventA(
      L"WusaMountOrExtractAllFilesFromCabinet",
      583,
      "Exit with error code 0X%x (%ls)",
      v10,
      (const wchar_t *)hMem);
    if ( v16 )
      LocalFree(v16);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14000ee88  mov     [rsp-38h+arg_0], rbx
0x14000ee8d  push    rbp
0x14000ee8e  push    rsi
0x14000ee8f  push    rdi
0x14000ee90  push    r12
0x14000ee92  push    r13
0x14000ee94  push    r14
0x14000ee96  push    r15
0x14000ee98  mov     rbp, rsp
0x14000ee9b  sub     rsp, 40h
0x14000ee9f  xor     esi, esi
0x14000eea1  mov     r15, rcx
0x14000eea4  mov     rcx, rdx; pszPath
0x14000eea7  mov     [rbp+ppJob], rsi
0x14000eeab  mov     [rbp+arg_18], rsi
0x14000eeaf  mov     r14d, esi
0x14000eeb2  mov     r13, r8
0x14000eeb5  mov     rdi, rdx
0x14000eeb8  call    cs:__imp_PathFindExtensionW
0x14000eebe  mov     rcx, rax; String1
0x14000eec1  lea     rdx, aWim; ".wim"
0x14000eec8  mov     rbx, rax
0x14000eecb  call    cs:__imp__wcsicmp
0x14000eed1  test    eax, eax
0x14000eed3  jz      loc_14000F060
0x14000eed9  lea     rdx, aMsu2; ".msu2"
0x14000eee0  mov     rcx, rbx; String1
0x14000eee3  call    cs:__imp__wcsicmp
0x14000eee9  test    eax, eax
0x14000eeeb  jz      loc_14000F060
0x14000eef1  lea     rdx, [rbp+ppJob]; ppJob
0x14000eef5  mov     rcx, r15; TargetPath
0x14000eef8  xor     r12d, r12d
0x14000eefb  call    cs:__imp_DpxNewJob
0x14000ef01  mov     ebx, eax
0x14000ef03  test    eax, eax
0x14000ef05  jns     short loc_14000EF27
0x14000ef07  mov     r9, r15
0x14000ef0a  lea     r8, aFailedToCreate_0; "Failed to create extract job for locati"...
0x14000ef11  mov     edx, 1EEh
0x14000ef16  lea     rcx, aWusamountorext; "WusaMountOrExtractAllFilesFromCabinet"
0x14000ef1d  call    WusaLogDebugEventA
0x14000ef22  jmp     loc_14000F176
0x14000ef27  mov     rcx, [rbp+ppJob]
0x14000ef2b  lea     r8, [rbp+arg_18]
0x14000ef2f  mov     rdx, rdi
0x14000ef32  mov     rax, [rcx]
0x14000ef35  mov     rax, [rax+20h]
0x14000ef39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ef3e  mov     ebx, eax
0x14000ef40  test    eax, eax
0x14000ef42  jns     short loc_14000EF55
0x14000ef44  mov     r9, rdi
0x14000ef47  lea     r8, aFailedToAddCon; "Failed to add container for cabinet: %S"
0x14000ef4e  mov     edx, 1F1h
0x14000ef53  jmp     short loc_14000EF16
0x14000ef55  mov     rcx, [rbp+arg_18]
0x14000ef59  mov     rax, [rcx]
0x14000ef5c  mov     rax, [rax+38h]
0x14000ef60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ef65  mov     ebx, eax
0x14000ef67  test    eax, eax
0x14000ef69  jns     short loc_14000EF7C
0x14000ef6b  lea     r8, aFailedExtracta; "Failed: ExtractAllFiles()"
0x14000ef72  mov     edx, 1F4h
0x14000ef77  jmp     loc_14000F16A
0x14000ef7c  mov     rcx, [rbp+ppJob]
0x14000ef80  xor     edx, edx
0x14000ef82  mov     rax, [rcx]
0x14000ef85  mov     rax, [rax+40h]
0x14000ef89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ef8e  mov     ebx, eax
0x14000ef90  cmp     eax, 0CA00A005h
0x14000ef95  jnz     loc_14000F044
0x14000ef9b  mov     r9, rdi
0x14000ef9e  lea     r8, aUnsupportedCon; "Unsupported container type from cabinet"...
0x14000efa5  mov     edx, 1FDh
0x14000efaa  lea     rcx, aWusamountorext; "WusaMountOrExtractAllFilesFromCabinet"
0x14000efb1  mov     r12d, 1
0x14000efb7  call    WusaLogDebugEventA
0x14000efbc  mov     rcx, [rbp+arg_18]
0x14000efc0  mov     rax, [rcx]
0x14000efc3  mov     rax, [rax+70h]
0x14000efc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000efcc  mov     ebx, eax
0x14000efce  test    eax, eax
0x14000efd0  jns     short loc_14000EFE6
0x14000efd2  mov     r9, rdi
0x14000efd5  lea     r8, aFailedToRemove; "Failed to remove DPX container for cabi"...
0x14000efdc  mov     edx, 200h
0x14000efe1  jmp     loc_14000EF16
0x14000efe6  mov     rcx, [rbp+ppJob]
0x14000efea  mov     rax, [rcx]
0x14000efed  mov     rax, [rax+50h]
0x14000eff1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000eff6  mov     ebx, eax
0x14000eff8  test    eax, eax
0x14000effa  jns     short loc_14000F010
0x14000effc  mov     r9, rdi
0x14000efff  lea     r8, aFailedToCancel; "Failed to cancel DPX job for cabinet: %"...
0x14000f006  mov     edx, 203h
0x14000f00b  jmp     loc_14000EF16
0x14000f010  mov     rcx, [rbp+arg_18]
0x14000f014  test    rcx, rcx
0x14000f017  jz      short loc_14000F029
0x14000f019  mov     rax, [rcx]
0x14000f01c  mov     rax, [rax+10h]
0x14000f020  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f025  mov     [rbp+arg_18], rsi
0x14000f029  mov     rcx, [rbp+ppJob]
0x14000f02d  test    rcx, rcx
0x14000f030  jz      short loc_14000F068
0x14000f032  mov     rax, [rcx]
0x14000f035  mov     rax, [rax+10h]
0x14000f039  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f03e  mov     [rbp+ppJob], rsi
0x14000f042  jmp     short loc_14000F068
0x14000f044  test    eax, eax
0x14000f046  jns     loc_14000F176
0x14000f04c  mov     r9, rdi
0x14000f04f  lea     r8, aFailedToExtrac; "Failed to extract files from cabinet %w"...
0x14000f056  mov     edx, 20Ah
0x14000f05b  jmp     loc_14000EF16
0x14000f060  mov     ebx, esi
0x14000f062  mov     r12d, 1
0x14000f068  xor     r9d, r9d
0x14000f06b  mov     [rsp+40h+var_18], rsi
0x14000f070  mov     edx, 80000000h
0x14000f075  mov     dword ptr [rsp+40h+var_20], esi
0x14000f079  mov     rcx, rdi
0x14000f07c  lea     r8d, [r9+3]
0x14000f080  call    cs:__imp_WIMCreateFile
0x14000f086  mov     rsi, rax
0x14000f089  test    rax, rax
0x14000f08c  jnz     short loc_14000F0BB
0x14000f08e  call    cs:__imp_GetLastError
0x14000f094  mov     ebx, eax
0x14000f096  test    eax, eax
0x14000f098  jle     short loc_14000F0A3
0x14000f09a  movzx   ebx, ax
0x14000f09d  or      ebx, 80070000h
0x14000f0a3  test    ebx, ebx
0x14000f0a5  jns     short loc_14000F0BB
0x14000f0a7  mov     r9, rdi
0x14000f0aa  lea     r8, aWimcreatefileF; "WIMCreateFile failed for %ws"
0x14000f0b1  mov     edx, 21Ah
0x14000f0b6  jmp     loc_14000EF16
0x14000f0bb  mov     rdx, r15
0x14000f0be  mov     rcx, rsi
0x14000f0c1  call    cs:__imp_WIMSetTemporaryPath
0x14000f0c7  test    eax, eax
0x14000f0c9  jnz     short loc_14000F0F2
0x14000f0cb  call    cs:__imp_GetLastError
0x14000f0d1  mov     ebx, eax
0x14000f0d3  test    eax, eax
0x14000f0d5  jle     short loc_14000F0E0
0x14000f0d7  movzx   ebx, ax
0x14000f0da  or      ebx, 80070000h
0x14000f0e0  test    ebx, ebx
0x14000f0e2  jns     short loc_14000F0F2
0x14000f0e4  lea     r8, aWimsettemporar; "WIMSetTemporaryPath failed!"
0x14000f0eb  mov     edx, 222h
0x14000f0f0  jmp     short loc_14000F16A
0x14000f0f2  mov     edx, 1
0x14000f0f7  mov     rcx, rsi
0x14000f0fa  call    cs:__imp_WIMLoadImage
0x14000f100  mov     r14, rax
0x14000f103  test    rax, rax
0x14000f106  jnz     short loc_14000F12F
0x14000f108  call    cs:__imp_GetLastError
0x14000f10e  mov     ebx, eax
0x14000f110  test    eax, eax
0x14000f112  jle     short loc_14000F11D
0x14000f114  movzx   ebx, ax
0x14000f117  or      ebx, 80070000h
0x14000f11d  test    ebx, ebx
0x14000f11f  jns     short loc_14000F12F
0x14000f121  lea     r8, aWimloadimageFa; "WIMLoadImage failed!"
0x14000f128  mov     edx, 229h
0x14000f12d  jmp     short loc_14000F16A
0x14000f12f  mov     r8d, 2
0x14000f135  mov     rdx, r15
0x14000f138  mov     rcx, r14
0x14000f13b  call    cs:__imp_WIMApplyImage
0x14000f141  test    eax, eax
0x14000f143  jnz     short loc_14000F176
0x14000f145  call    cs:__imp_GetLastError
0x14000f14b  mov     ebx, eax
0x14000f14d  test    eax, eax
0x14000f14f  jle     short loc_14000F15A
0x14000f151  movzx   ebx, ax
0x14000f154  or      ebx, 80070000h
0x14000f15a  test    ebx, ebx
0x14000f15c  jns     short loc_14000F176
0x14000f15e  lea     r8, aWimapplyimageF; "WIMApplyImage failed!"
0x14000f165  mov     edx, 22Fh
0x14000f16a  lea     rcx, aWusamountorext; "WusaMountOrExtractAllFilesFromCabinet"
0x14000f171  call    WusaLogDebugEventA
0x14000f176  test    r13, r13
0x14000f179  jz      short loc_14000F17F
0x14000f17b  mov     [r13+0], r12d
0x14000f17f  test    r14, r14
0x14000f182  jz      short loc_14000F18D
0x14000f184  mov     rcx, r14
0x14000f187  call    cs:__imp_WIMCloseHandle
0x14000f18d  test    rsi, rsi
0x14000f190  jz      short loc_14000F19B
0x14000f192  mov     rcx, rsi
0x14000f195  call    cs:__imp_WIMCloseHandle
0x14000f19b  mov     rcx, [rbp+arg_18]
0x14000f19f  test    rcx, rcx
0x14000f1a2  jz      short loc_14000F1B8
0x14000f1a4  mov     rax, [rcx]
0x14000f1a7  mov     rax, [rax+10h]
0x14000f1ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f1b0  mov     [rbp+arg_18], 0
0x14000f1b8  mov     rcx, [rbp+ppJob]
0x14000f1bc  test    rcx, rcx
0x14000f1bf  jz      short loc_14000F1D5
0x14000f1c1  mov     rax, [rcx]
0x14000f1c4  mov     rax, [rax+10h]
0x14000f1c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f1cd  mov     [rbp+ppJob], 0
0x14000f1d5  test    ebx, ebx
0x14000f1d7  jns     short loc_14000F21E
0x14000f1d9  lea     rdx, [rbp+hMem]; unsigned __int16 **
0x14000f1dd  mov     [rbp+hMem], 0
0x14000f1e5  mov     ecx, ebx; dwMessageId
0x14000f1e7  call    ?WusaGetErrorMessage@@YAJKPEAPEAG@Z; WusaGetErrorMessage(ulong,ushort * *)
0x14000f1ec  mov     rdi, [rbp+hMem]
0x14000f1f0  lea     r8, aExitWithErrorC; "Exit with error code 0X%x (%ls)"
0x14000f1f7  mov     r9d, ebx
0x14000f1fa  mov     [rsp+40h+var_20], rdi
0x14000f1ff  mov     edx, 247h
0x14000f204  lea     rcx, aWusamountorext; "WusaMountOrExtractAllFilesFromCabinet"
0x14000f20b  call    WusaLogDebugEventA
0x14000f210  test    rdi, rdi
0x14000f213  jz      short loc_14000F21E
0x14000f215  mov     rcx, rdi; hMem
0x14000f218  call    cs:__imp_LocalFree
0x14000f21e  mov     eax, ebx
0x14000f220  mov     rbx, [rsp+40h+arg_0]
0x14000f228  add     rsp, 40h
0x14000f22c  pop     r15
0x14000f22e  pop     r14
0x14000f230  pop     r13
0x14000f232  pop     r12
0x14000f234  pop     rdi
0x14000f235  pop     rsi
0x14000f236  pop     rbp
0x14000f237  retn
```
