# CSDiagSchd::SchdpExecuteDiagnostics(void *)

- ea: `0x180007c60`
- end: `0x180008031`
- name: `?SchdpExecuteDiagnostics@CSDiagSchd@@CAKPEAX@Z`
- size: `977`
- prototype: `__int64 __fastcall(CSDiagSchd *Parameter)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800056b4`
- `0x1800066f4`
- `0x180007a48`
- `0x180007c60`
- `0x180008038`
- `0x18000b13c`
- `0x18000c836`
- `0x18000c860`
- `0x18000d010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180007f66`
- `KERNEL32!HeapFree` at `0x180007f8b`
- `KERNEL32!HeapFree` at `0x180007fb0`
- `KERNEL32!HeapFree` at `0x180007f66`
- `KERNEL32!HeapFree` at `0x180007f8b`
- `KERNEL32!HeapFree` at `0x180007fb0`
- `KERNEL32!GetProcessHeap` at `0x180007cc5`
- `KERNEL32!GetProcessHeap` at `0x180007d06`
- `KERNEL32!GetProcessHeap` at `0x180007f52`
- `KERNEL32!GetProcessHeap` at `0x180007f77`
- `KERNEL32!GetProcessHeap` at `0x180007f9c`
- `KERNEL32!GetProcessHeap` at `0x180007cc5`
- `KERNEL32!GetProcessHeap` at `0x180007d06`
- `KERNEL32!GetProcessHeap` at `0x180007f52`
- `KERNEL32!GetProcessHeap` at `0x180007f77`
- `KERNEL32!GetProcessHeap` at `0x180007f9c`
- `KERNEL32!HeapAlloc` at `0x180007cde`
- `KERNEL32!HeapAlloc` at `0x180007d1a`
- `KERNEL32!HeapAlloc` at `0x180007cde`
- `KERNEL32!HeapAlloc` at `0x180007d1a`
- `KERNEL32!GetLastError` at `0x180007d60`
- `KERNEL32!GetLastError` at `0x180007ee0`
- `KERNEL32!GetLastError` at `0x180007d60`
- `KERNEL32!GetLastError` at `0x180007ee0`
- `KERNEL32!GetModuleHandleExW` at `0x180007d50`
- `KERNEL32!GetModuleHandleExW` at `0x180007d50`
- `KERNEL32!FindFirstFileW` at `0x180007dfc`
- `KERNEL32!FindFirstFileW` at `0x180007dfc`
- `KERNEL32!FindNextFileW` at `0x180007ec0`
- `KERNEL32!FindNextFileW` at `0x180007ec0`
- `KERNEL32!FindClose` at `0x180007fc5`
- `KERNEL32!FindClose` at `0x180007fc5`
- `KERNEL32!FreeLibraryAndExitThread` at `0x180007ff0`
- `KERNEL32!FreeLibraryAndExitThread` at `0x180007ff0`

## pseudocode

```c
__int64 __fastcall CSDiagSchd::SchdpExecuteDiagnostics(CSDiagSchd *Parameter)
{
  void *v2; // rsi
  unsigned __int16 *v3; // rdi
  __int64 FirstFileW; // r14
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v6; // r15
  int v7; // r9d
  int v8; // r8d
  signed int v9; // ebx
  HANDLE v10; // rax
  const unsigned __int16 *v11; // rdx
  signed int LastError; // eax
  int v13; // eax
  __int64 v14; // r8
  int v15; // eax
  int v16; // eax
  int v17; // r9d
  int v18; // r8d
  signed int v19; // eax
  HANDLE v20; // rax
  HANDLE v21; // rax
  HANDLE v22; // rax
  HMODULE phModule; // [rsp+38h] [rbp-D0h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+48h] [rbp-C0h] BYREF
  LPVOID lpMem[2]; // [rsp+298h] [rbp+190h] BYREF

  lpMem[0] = 0;
  v2 = 0;
  v3 = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = -1;
  phModule = 0;
  ProcessHeap = GetProcessHeap();
  v6 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 0x208u);
  if ( !v6 )
  {
    v7 = -2147024882;
    v8 = 419;
    v9 = -2147024882;
    goto LABEL_34;
  }
  v10 = GetProcessHeap();
  v3 = (unsigned __int16 *)HeapAlloc(v10, 0, 0x208u);
  if ( !v3 )
  {
    v7 = -2147024882;
    v8 = 420;
    v9 = -2147024882;
    goto LABEL_34;
  }
  if ( !GetModuleHandleExW(0, L"sdiagschd", &phModule) )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( v9 < 0 )
    {
      v8 = 423;
      goto LABEL_33;
    }
  }
  v13 = CSDiagSchd::SchdpStringExpand((unsigned __int16 **)lpMem, v11);
  v9 = v13;
  if ( v13 < 0 )
  {
    SdpDebugTrace(1u, L"CSDiagSchd::SchdpExecuteDiagnostics", 426, v13);
    v2 = lpMem[0];
    goto LABEL_35;
  }
  v2 = lpMem[0];
  v15 = StringCchPrintfW(v3, 0x104u, L"%s\\*", lpMem[0]);
  v9 = v15;
  if ( v15 < 0 )
  {
    v7 = v15;
    v8 = 432;
    goto LABEL_34;
  }
  FirstFileW = (__int64)FindFirstFileW(v3, &FindFileData);
  if ( (unsigned __int64)(FirstFileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    while ( 1 )
    {
      if ( (FindFileData.dwFileAttributes & 0x10) == 0
        || FindFileData.cFileName[0] == 46
        && (!FindFileData.cFileName[1] || FindFileData.cFileName[1] == 46 && !FindFileData.cFileName[2]) )
      {
        goto LABEL_26;
      }
      v16 = StringCchPrintfW(v6, 0x104u, L"%s\\%s", v2, FindFileData.cFileName);
      if ( v16 < 0 )
        break;
      v9 = CSDiagSchd::SchdpExecuteDiagnosticPackage(Parameter, v6);
      if ( v9 == -2147023673 )
      {
        v7 = -2147023673;
        v8 = 451;
        goto LABEL_34;
      }
      if ( v9 < 0 )
      {
        v17 = v9;
        v18 = 454;
        goto LABEL_25;
      }
LABEL_26:
      if ( !FindNextFileW((HANDLE)FirstFileW, &FindFileData) )
        goto LABEL_35;
    }
    v17 = v16;
    v18 = 447;
LABEL_25:
    SdpDebugTrace(2u, L"CSDiagSchd::SchdpExecuteDiagnostics", v18, v17);
    v9 = 0;
    goto LABEL_26;
  }
  v19 = GetLastError();
  v9 = v19;
  if ( v19 > 0 )
    v9 = (unsigned __int16)v19 | 0x80070000;
  v8 = 435;
  if ( v9 >= 0 )
    v9 = -2147467259;
LABEL_33:
  v7 = v9;
LABEL_34:
  SdpDebugTrace(1u, L"CSDiagSchd::SchdpExecuteDiagnostics", v8, v7);
LABEL_35:
  if ( (Microsoft_Windows_Diagnosis_ScheduledEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &SCHEDULED_DIAGNOSTICS_PROVIDER_Context,
      &SCHEDULED_DIAGNOSTICS_EVENT_COMPLETED,
      v14,
      1,
      lpMem);
  if ( v2 )
  {
    v20 = GetProcessHeap();
    HeapFree(v20, 0, v2);
  }
  if ( v6 )
  {
    v21 = GetProcessHeap();
    HeapFree(v21, 0, v6);
  }
  if ( v3 )
  {
    v22 = GetProcessHeap();
    HeapFree(v22, 0, v3);
  }
  if ( FirstFileW != -1 )
    FindClose((HANDLE)FirstFileW);
  (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)Parameter + 4) + 32LL))(
    *((_QWORD *)Parameter + 4),
    (unsigned int)v9);
  if ( phModule )
    FreeLibraryAndExitThread(phModule, (unsigned __int16)v9);
  return (unsigned __int16)v9;
}

```

## disassembly

```asm
0x180007c60  mov     rax, rsp
0x180007c63  mov     [rax+10h], rbx
0x180007c67  mov     [rax+18h], rsi
0x180007c6b  mov     [rax+20h], rdi
0x180007c6f  push    rbp
0x180007c70  push    r12
0x180007c72  push    r13
0x180007c74  push    r14
0x180007c76  push    r15
0x180007c78  lea     rbp, [rax-1D8h]
0x180007c7f  sub     rsp, 2B0h
0x180007c86  mov     rax, cs:__security_cookie
0x180007c8d  xor     rax, rsp
0x180007c90  mov     [rbp+1D0h+var_30], rax
0x180007c97  xor     r12d, r12d
0x180007c9a  mov     r13, rcx
0x180007c9d  lea     rcx, [rsp+2D0h+FindFileData]; void *
0x180007ca2  mov     [rbp+1D0h+lpMem], r12
0x180007ca9  xor     edx, edx; Val
0x180007cab  mov     r8d, 250h; Size
0x180007cb1  mov     esi, r12d
0x180007cb4  mov     edi, r12d
0x180007cb7  call    memset_0
0x180007cbc  or      r14, 0FFFFFFFFFFFFFFFFh
0x180007cc0  mov     [rsp+2D0h+phModule], r12
0x180007cc5  call    cs:__imp_GetProcessHeap
0x180007ccc  nop     dword ptr [rax+rax+00h]
0x180007cd1  mov     ebx, 208h
0x180007cd6  xor     edx, edx; dwFlags
0x180007cd8  mov     rcx, rax; hHeap
0x180007cdb  mov     r8d, ebx; dwBytes
0x180007cde  call    cs:__imp_HeapAlloc
0x180007ce5  nop     dword ptr [rax+rax+00h]
0x180007cea  mov     r15, rax
0x180007ced  test    rax, rax
0x180007cf0  jnz     short loc_180007D06
0x180007cf2  mov     r9d, 8007000Eh
0x180007cf8  mov     r8d, 1A3h
0x180007cfe  mov     ebx, r9d
0x180007d01  jmp     loc_180007F0E
0x180007d06  call    cs:__imp_GetProcessHeap
0x180007d0d  nop     dword ptr [rax+rax+00h]
0x180007d12  mov     r8, rbx; dwBytes
0x180007d15  xor     edx, edx; dwFlags
0x180007d17  mov     rcx, rax; hHeap
0x180007d1a  call    cs:__imp_HeapAlloc
0x180007d21  nop     dword ptr [rax+rax+00h]
0x180007d26  mov     rdi, rax
0x180007d29  test    rax, rax
0x180007d2c  jnz     short loc_180007D42
0x180007d2e  mov     r9d, 8007000Eh
0x180007d34  mov     r8d, 1A4h
0x180007d3a  mov     ebx, r9d
0x180007d3d  jmp     loc_180007F0E
0x180007d42  lea     r8, [rsp+2D0h+phModule]; phModule
0x180007d47  xor     ecx, ecx; dwFlags
0x180007d49  lea     rdx, ModuleName; "sdiagschd"
0x180007d50  call    cs:__imp_GetModuleHandleExW
0x180007d57  nop     dword ptr [rax+rax+00h]
0x180007d5c  test    eax, eax
0x180007d5e  jnz     short loc_180007D8A
0x180007d60  call    cs:__imp_GetLastError
0x180007d67  nop     dword ptr [rax+rax+00h]
0x180007d6c  mov     ebx, eax
0x180007d6e  test    eax, eax
0x180007d70  jle     short loc_180007D7B
0x180007d72  movzx   ebx, ax
0x180007d75  or      ebx, 80070000h
0x180007d7b  test    ebx, ebx
0x180007d7d  jns     short loc_180007D8A
0x180007d7f  mov     r8d, 1A7h
0x180007d85  jmp     loc_180007F0B
0x180007d8a  lea     rcx, [rbp+1D0h+lpMem]; unsigned __int16 **
0x180007d91  call    ?SchdpStringExpand@CSDiagSchd@@CAJPEAPEAGPEBG@Z; CSDiagSchd::SchdpStringExpand(ushort * *,ushort const *)
0x180007d96  mov     ebx, eax
0x180007d98  test    eax, eax
0x180007d9a  jns     short loc_180007DC2
0x180007d9c  mov     r9d, eax; int
0x180007d9f  lea     rdx, aCsdiagschdSchd_0; "CSDiagSchd::SchdpExecuteDiagnostics"
0x180007da6  mov     r8d, 1AAh; int
0x180007dac  mov     ecx, 1; Level
0x180007db1  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180007db6  mov     rsi, [rbp+1D0h+lpMem]
0x180007dbd  jmp     loc_180007F1F
0x180007dc2  mov     rsi, [rbp+1D0h+lpMem]
0x180007dc9  lea     r8, aS; "%s\\*"
0x180007dd0  mov     r9, rsi
0x180007dd3  mov     edx, 104h; unsigned __int64
0x180007dd8  mov     rcx, rdi; unsigned __int16 *
0x180007ddb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180007de0  mov     ebx, eax
0x180007de2  test    eax, eax
0x180007de4  jns     short loc_180007DF4
0x180007de6  mov     r9d, eax
0x180007de9  mov     r8d, 1B0h
0x180007def  jmp     loc_180007F0E
0x180007df4  lea     rdx, [rsp+2D0h+FindFileData]; lpFindFileData
0x180007df9  mov     rcx, rdi; lpFileName
0x180007dfc  call    cs:__imp_FindFirstFileW
0x180007e03  nop     dword ptr [rax+rax+00h]
0x180007e08  mov     r14, rax
0x180007e0b  lea     rcx, [rax-1]
0x180007e0f  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180007e13  ja      loc_180007EE0
0x180007e19  mov     ecx, [rsp+2D0h+FindFileData.dwFileAttributes]
0x180007e1d  mov     edx, 2Eh ; '.'
0x180007e22  test    cl, 10h
0x180007e25  jz      loc_180007EB8
0x180007e2b  movzx   eax, [rsp+2D0h+FindFileData.cFileName+2]
0x180007e30  cmp     dx, [rsp+2D0h+FindFileData.cFileName]
0x180007e35  jnz     short loc_180007E51
0x180007e37  cmp     r12w, ax
0x180007e3b  jz      short loc_180007EB8
0x180007e3d  cmp     dx, [rsp+2D0h+FindFileData.cFileName]
0x180007e42  jnz     short loc_180007E51
0x180007e44  cmp     dx, ax
0x180007e47  jnz     short loc_180007E51
0x180007e49  cmp     r12w, [rsp+2D0h+FindFileData.cFileName+4]
0x180007e4f  jz      short loc_180007EB8
0x180007e51  lea     rax, [rsp+2D0h+FindFileData.cFileName]
0x180007e56  mov     r9, rsi
0x180007e59  lea     r8, aSS; "%s\\%s"
0x180007e60  mov     [rsp+2D0h+var_2B0], rax
0x180007e65  mov     edx, 104h; unsigned __int64
0x180007e6a  mov     rcx, r15; unsigned __int16 *
0x180007e6d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180007e72  test    eax, eax
0x180007e74  jns     short loc_180007E81
0x180007e76  mov     r9d, eax
0x180007e79  mov     r8d, 1BFh
0x180007e7f  jmp     short loc_180007EA4
0x180007e81  mov     rdx, r15; unsigned __int16 *
0x180007e84  mov     rcx, r13; this
0x180007e87  call    ?SchdpExecuteDiagnosticPackage@CSDiagSchd@@AEAAJQEAG@Z; CSDiagSchd::SchdpExecuteDiagnosticPackage(ushort * const)
0x180007e8c  mov     ebx, eax
0x180007e8e  mov     eax, 800704C7h
0x180007e93  cmp     ebx, eax
0x180007e95  jz      short loc_180007ED5
0x180007e97  test    ebx, ebx
0x180007e99  jns     short loc_180007EB8
0x180007e9b  mov     r9d, ebx; int
0x180007e9e  mov     r8d, 1C6h; int
0x180007ea4  lea     rdx, aCsdiagschdSchd_0; "CSDiagSchd::SchdpExecuteDiagnostics"
0x180007eab  mov     ecx, 2; Level
0x180007eb0  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180007eb5  mov     ebx, r12d
0x180007eb8  lea     rdx, [rsp+2D0h+FindFileData]; lpFindFileData
0x180007ebd  mov     rcx, r14; hFindFile
0x180007ec0  call    cs:__imp_FindNextFileW
0x180007ec7  nop     dword ptr [rax+rax+00h]
0x180007ecc  test    eax, eax
0x180007ece  jz      short loc_180007F1F
0x180007ed0  jmp     loc_180007E19
0x180007ed5  mov     r9d, eax
0x180007ed8  mov     r8d, 1C3h
0x180007ede  jmp     short loc_180007F0E
0x180007ee0  call    cs:__imp_GetLastError
0x180007ee7  nop     dword ptr [rax+rax+00h]
0x180007eec  mov     ebx, eax
0x180007eee  test    eax, eax
0x180007ef0  jle     short loc_180007EFB
0x180007ef2  movzx   ebx, ax
0x180007ef5  or      ebx, 80070000h
0x180007efb  test    ebx, ebx
0x180007efd  mov     eax, 80004005h
0x180007f02  mov     r8d, 1B3h; int
0x180007f08  cmovns  ebx, eax
0x180007f0b  mov     r9d, ebx; int
0x180007f0e  lea     rdx, aCsdiagschdSchd_0; "CSDiagSchd::SchdpExecuteDiagnostics"
0x180007f15  mov     ecx, 1; Level
0x180007f1a  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180007f1f  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScheduledEnableBits, 2
0x180007f26  jz      short loc_180007F4D
0x180007f28  lea     rax, [rbp+1D0h+lpMem]
0x180007f2f  mov     r9d, 1
0x180007f35  lea     rdx, SCHEDULED_DIAGNOSTICS_EVENT_COMPLETED
0x180007f3c  mov     [rsp+2D0h+var_2B0], rax
0x180007f41  lea     rcx, SCHEDULED_DIAGNOSTICS_PROVIDER_Context
0x180007f48  call    McGenEventWrite_EventWriteTransfer
0x180007f4d  test    rsi, rsi
0x180007f50  jz      short loc_180007F72
0x180007f52  call    cs:__imp_GetProcessHeap
0x180007f59  nop     dword ptr [rax+rax+00h]
0x180007f5e  mov     r8, rsi; lpMem
0x180007f61  xor     edx, edx; dwFlags
0x180007f63  mov     rcx, rax; hHeap
0x180007f66  call    cs:__imp_HeapFree
0x180007f6d  nop     dword ptr [rax+rax+00h]
0x180007f72  test    r15, r15
0x180007f75  jz      short loc_180007F97
0x180007f77  call    cs:__imp_GetProcessHeap
0x180007f7e  nop     dword ptr [rax+rax+00h]
0x180007f83  mov     r8, r15; lpMem
0x180007f86  xor     edx, edx; dwFlags
0x180007f88  mov     rcx, rax; hHeap
0x180007f8b  call    cs:__imp_HeapFree
0x180007f92  nop     dword ptr [rax+rax+00h]
0x180007f97  test    rdi, rdi
0x180007f9a  jz      short loc_180007FBC
0x180007f9c  call    cs:__imp_GetProcessHeap
0x180007fa3  nop     dword ptr [rax+rax+00h]
0x180007fa8  mov     r8, rdi; lpMem
0x180007fab  xor     edx, edx; dwFlags
0x180007fad  mov     rcx, rax; hHeap
0x180007fb0  call    cs:__imp_HeapFree
0x180007fb7  nop     dword ptr [rax+rax+00h]
0x180007fbc  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180007fc0  jz      short loc_180007FD1
0x180007fc2  mov     rcx, r14; hFindFile
0x180007fc5  call    cs:__imp_FindClose
0x180007fcc  nop     dword ptr [rax+rax+00h]
0x180007fd1  mov     rcx, [r13+20h]
0x180007fd5  mov     edx, ebx
0x180007fd7  mov     rax, [rcx]
0x180007fda  mov     rax, [rax+20h]
0x180007fde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fe3  mov     rcx, [rsp+2D0h+phModule]; hLibModule
0x180007fe8  test    rcx, rcx
0x180007feb  jz      short loc_180007FFD
0x180007fed  movzx   edx, bx; dwExitCode
0x180007ff0  call    cs:__imp_FreeLibraryAndExitThread
0x180007ffd  movzx   eax, bx
0x180008000  mov     rcx, [rbp+1D0h+var_30]
0x180008007  xor     rcx, rsp; StackCookie
0x18000800a  call    __security_check_cookie
0x18000800f  lea     r11, [rsp+2D0h+var_20]
0x180008017  mov     rbx, [r11+38h]
0x18000801b  mov     rsi, [r11+40h]
0x18000801f  mov     rdi, [r11+48h]
0x180008023  mov     rsp, r11
0x180008026  pop     r15
0x180008028  pop     r14
0x18000802a  pop     r13
0x18000802c  pop     r12
0x18000802e  pop     rbp
0x18000802f  retn
```
