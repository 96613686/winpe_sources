# WdcGetParentProcessImageName(ushort *,ulong)

- ea: `0x18002e1bc`
- end: `0x18002e437`
- name: `?WdcGetParentProcessImageName@@YAJPEAGK@Z`
- size: `635`
- prototype: `__int64 __fastcall(LPWSTR lpExeName, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18007625c`

## callees

- `0x18000b854`
- `0x180019990`
- `0x18002e1bc`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18002e248`
- `ntdll!RtlNtStatusToDosError` at `0x18002e248`
- `ntdll!NtQueryInformationProcess` at `0x18002e236`
- `ntdll!NtQueryInformationProcess` at `0x18002e236`
- `KERNEL32!CloseHandle` at `0x18002e421`
- `KERNEL32!CloseHandle` at `0x18002e421`
- `KERNEL32!GetLastError` at `0x18002e2bc`
- `KERNEL32!GetLastError` at `0x18002e305`
- `KERNEL32!GetLastError` at `0x18002e34d`
- `KERNEL32!GetLastError` at `0x18002e39b`
- `KERNEL32!GetLastError` at `0x18002e2bc`
- `KERNEL32!GetLastError` at `0x18002e305`
- `KERNEL32!GetLastError` at `0x18002e34d`
- `KERNEL32!GetLastError` at `0x18002e39b`
- `KERNEL32!OpenProcess` at `0x18002e2ae`
- `KERNEL32!OpenProcess` at `0x18002e2ae`
- `KERNEL32!GetProcessTimes` at `0x18002e2fb`
- `KERNEL32!GetProcessTimes` at `0x18002e343`
- `KERNEL32!GetProcessTimes` at `0x18002e2fb`
- `KERNEL32!GetProcessTimes` at `0x18002e343`
- `KERNEL32!QueryFullProcessImageNameW` at `0x18002e38d`
- `KERNEL32!QueryFullProcessImageNameW` at `0x18002e38d`
- `KERNEL32!GetCurrentProcess` at `0x18002e218`
- `KERNEL32!GetCurrentProcess` at `0x18002e325`
- `KERNEL32!GetCurrentProcess` at `0x18002e218`
- `KERNEL32!GetCurrentProcess` at `0x18002e325`

## pseudocode

```c
__int64 __fastcall WdcGetParentProcessImageName(LPWSTR lpExeName)
{
  HANDLE CurrentProcess; // rax
  NTSTATUS InformationProcess; // eax
  signed int v4; // eax
  signed int v5; // ebx
  int v6; // eax
  char *v7; // rax
  char *v8; // rdi
  signed int LastError; // eax
  signed int v10; // eax
  HANDLE v11; // rax
  signed int v12; // eax
  signed int v13; // eax
  WCHAR *v14; // rcx
  WCHAR *v15; // rdx
  PULONG ReturnLength; // [rsp+20h] [rbp-60h]
  PULONG ReturnLengtha; // [rsp+20h] [rbp-60h]
  DWORD dwSize; // [rsp+30h] [rbp-50h] BYREF
  struct _FILETIME ExitTime; // [rsp+38h] [rbp-48h] BYREF
  struct _FILETIME v21; // [rsp+40h] [rbp-40h] BYREF
  struct _FILETIME CreationTime; // [rsp+48h] [rbp-38h] BYREF
  _OWORD ProcessInformation[2]; // [rsp+50h] [rbp-30h] BYREF
  unsigned __int64 v24[2]; // [rsp+70h] [rbp-10h]
  DWORD dwProcessId; // [rsp+B8h] [rbp+38h] BYREF
  struct _FILETIME UserTime; // [rsp+C0h] [rbp+40h] BYREF
  struct _FILETIME KernelTime; // [rsp+C8h] [rbp+48h] BYREF

  dwSize = 260;
  memset(ProcessInformation, 0, sizeof(ProcessInformation));
  dwProcessId = 0;
  CreationTime = 0;
  *(_OWORD *)v24 = 0;
  v21 = 0;
  ExitTime = 0;
  KernelTime = 0;
  UserTime = 0;
  CurrentProcess = GetCurrentProcess();
  InformationProcess = NtQueryInformationProcess(CurrentProcess, ProcessBasicInformation, ProcessInformation, 0x30u, 0);
  if ( InformationProcess )
  {
    v4 = RtlNtStatusToDosError(InformationProcess);
    v5 = 0;
    if ( v4 )
    {
      if ( v4 > 0 )
        v5 = (unsigned __int16)v4 | 0x80070000;
      else
        v5 = v4;
    }
    if ( v5 < 0 )
      goto LABEL_7;
  }
  v6 = ULongLongToULong(v24[1], &dwProcessId);
  v5 = v6;
  if ( v6 < 0 )
  {
    LODWORD(ReturnLength) = v6;
    goto LABEL_8;
  }
  v7 = (char *)OpenProcess(0x400u, 0, dwProcessId);
  v8 = v7;
  if ( !v7 || v7 == (char *)-1LL )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      if ( v5 >= 0 )
        goto LABEL_19;
    }
    else
    {
      v5 = -2147467259;
    }
LABEL_7:
    LODWORD(ReturnLength) = v5;
LABEL_8:
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mon\\feedback.cpp",
      "WdcGetParentProcessImageName",
      0,
      L"FAILURE: 0x%08x",
      ReturnLength);
    return (unsigned int)v5;
  }
LABEL_19:
  if ( !GetProcessTimes(v8, &CreationTime, &ExitTime, &KernelTime, &UserTime) )
  {
    v10 = GetLastError();
    v5 = v10;
    if ( !v10 )
      goto LABEL_44;
    if ( v10 > 0 )
      v5 = (unsigned __int16)v10 | 0x80070000;
    if ( v5 < 0 )
      goto LABEL_45;
  }
  v11 = GetCurrentProcess();
  if ( GetProcessTimes(v11, &v21, &ExitTime, &KernelTime, &UserTime) )
    goto LABEL_29;
  v12 = GetLastError();
  v5 = v12;
  if ( !v12 )
  {
LABEL_44:
    v5 = -2147467259;
    goto LABEL_45;
  }
  if ( v12 > 0 )
    v5 = (unsigned __int16)v12 | 0x80070000;
  if ( v5 < 0 )
    goto LABEL_45;
LABEL_29:
  if ( *(_QWORD *)&CreationTime > *(__int64 *)&v21 )
  {
    v5 = -2147467259;
    goto LABEL_46;
  }
  if ( QueryFullProcessImageNameW(v8, 0, lpExeName, &dwSize) )
  {
    v5 = 0;
    goto LABEL_37;
  }
  v13 = GetLastError();
  v5 = v13;
  if ( !v13 )
    goto LABEL_44;
  if ( v13 > 0 )
    v5 = (unsigned __int16)v13 | 0x80070000;
  if ( v5 >= 0 )
  {
LABEL_37:
    v14 = &lpExeName[dwSize];
    while ( v14 != lpExeName )
    {
      v15 = v14--;
      if ( *v14 == 92 )
      {
        while ( *v15 )
          *lpExeName++ = *v15++;
        *lpExeName = 0;
        goto LABEL_46;
      }
    }
    goto LABEL_46;
  }
LABEL_45:
  LODWORD(ReturnLengtha) = v5;
  WdcDebugMessage(
    "base\\diagnosis\\pdui\\perfmon\\mon\\feedback.cpp",
    "WdcGetParentProcessImageName",
    0,
    L"FAILURE: 0x%08x",
    ReturnLengtha);
LABEL_46:
  if ( (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v8);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18002e1bc  mov     [rsp-28h+dwProcessId], edx
0x18002e1c0  push    rbp
0x18002e1c1  push    rbx
0x18002e1c2  push    rsi
0x18002e1c3  push    rdi
0x18002e1c4  push    r15
0x18002e1c6  mov     rbp, rsp
0x18002e1c9  sub     rsp, 80h
0x18002e1d0  xorps   xmm0, xmm0
0x18002e1d3  mov     [rbp+dwSize], 104h
0x18002e1da  movups  [rbp+ProcessInformation], xmm0
0x18002e1de  mov     rsi, rcx
0x18002e1e1  mov     [rbp+dwProcessId], 0
0x18002e1e8  movups  [rbp+var_20], xmm0
0x18002e1ec  mov     qword ptr [rbp+CreationTime.dwLowDateTime], 0
0x18002e1f4  movups  xmmword ptr [rbp+var_10], xmm0
0x18002e1f8  mov     qword ptr [rbp+var_40.dwLowDateTime], 0
0x18002e200  mov     qword ptr [rbp+ExitTime.dwLowDateTime], 0
0x18002e208  mov     qword ptr [rbp+KernelTime.dwLowDateTime], 0
0x18002e210  mov     qword ptr [rbp+UserTime.dwLowDateTime], 0
0x18002e218  call    cs:__imp_GetCurrentProcess
0x18002e21e  mov     r9d, 30h ; '0'; ProcessInformationLength
0x18002e224  mov     [rsp+80h+ReturnLength], 0; ReturnLength
0x18002e22d  mov     rcx, rax; ProcessHandle
0x18002e230  lea     r8, [rbp+ProcessInformation]; ProcessInformation
0x18002e234  xor     edx, edx; ProcessInformationClass
0x18002e236  call    cs:__imp_NtQueryInformationProcess
0x18002e23c  mov     r15d, 80070000h
0x18002e242  test    eax, eax
0x18002e244  jz      short loc_18002E28A
0x18002e246  mov     ecx, eax; Status
0x18002e248  call    cs:__imp_RtlNtStatusToDosError
0x18002e24e  xor     ebx, ebx
0x18002e250  test    eax, eax
0x18002e252  jz      short loc_18002E260
0x18002e254  jg      short loc_18002E25A
0x18002e256  mov     ebx, eax
0x18002e258  jmp     short loc_18002E260
0x18002e25a  movzx   ebx, ax
0x18002e25d  or      ebx, r15d
0x18002e260  test    ebx, ebx
0x18002e262  jns     short loc_18002E28A
0x18002e264  mov     dword ptr [rsp+80h+ReturnLength], ebx
0x18002e268  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18002e26f  xor     r8d, r8d; int
0x18002e272  lea     rdx, aWdcgetparentpr; "WdcGetParentProcessImageName"
0x18002e279  lea     rcx, aBaseDiagnosisP_34; "base\\diagnosis\\pdui\\perfmon\\mon\\fe"...
0x18002e280  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18002e285  jmp     loc_18002E427
0x18002e28a  mov     rcx, [rbp+var_10+8]; unsigned __int64
0x18002e28e  lea     rdx, [rbp+dwProcessId]; unsigned int *
0x18002e292  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18002e297  mov     ebx, eax
0x18002e299  test    eax, eax
0x18002e29b  jns     short loc_18002E2A3
0x18002e29d  mov     dword ptr [rsp+80h+ReturnLength], eax
0x18002e2a1  jmp     short loc_18002E268
0x18002e2a3  mov     r8d, [rbp+dwProcessId]; dwProcessId
0x18002e2a7  xor     edx, edx; bInheritHandle
0x18002e2a9  mov     ecx, 400h; dwDesiredAccess
0x18002e2ae  call    cs:__imp_OpenProcess
0x18002e2b4  mov     rdi, rax
0x18002e2b7  test    rax, rax
0x18002e2ba  jnz     short loc_18002E2DD
0x18002e2bc  call    cs:__imp_GetLastError
0x18002e2c2  mov     ebx, eax
0x18002e2c4  test    eax, eax
0x18002e2c6  jz      short loc_18002E2D6
0x18002e2c8  jle     short loc_18002E2D0
0x18002e2ca  movzx   ebx, ax
0x18002e2cd  or      ebx, r15d
0x18002e2d0  test    ebx, ebx
0x18002e2d2  jns     short loc_18002E2E3
0x18002e2d4  jmp     short loc_18002E264
0x18002e2d6  mov     ebx, 80004005h
0x18002e2db  jmp     short loc_18002E264
0x18002e2dd  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18002e2e1  jz      short loc_18002E2BC
0x18002e2e3  lea     rax, [rbp+UserTime]
0x18002e2e7  mov     rcx, rdi; hProcess
0x18002e2ea  lea     r9, [rbp+KernelTime]; lpKernelTime
0x18002e2ee  mov     [rsp+80h+ReturnLength], rax; lpUserTime
0x18002e2f3  lea     r8, [rbp+ExitTime]; lpExitTime
0x18002e2f7  lea     rdx, [rbp+CreationTime]; lpCreationTime
0x18002e2fb  call    cs:__imp_GetProcessTimes
0x18002e301  test    eax, eax
0x18002e303  jnz     short loc_18002E325
0x18002e305  call    cs:__imp_GetLastError
0x18002e30b  mov     ebx, eax
0x18002e30d  test    eax, eax
0x18002e30f  jz      loc_18002E3EC
0x18002e315  jle     short loc_18002E31D
0x18002e317  movzx   ebx, ax
0x18002e31a  or      ebx, r15d
0x18002e31d  test    ebx, ebx
0x18002e31f  js      loc_18002E3F1
0x18002e325  call    cs:__imp_GetCurrentProcess
0x18002e32b  mov     rcx, rax; hProcess
0x18002e32e  lea     r9, [rbp+KernelTime]; lpKernelTime
0x18002e332  lea     rax, [rbp+UserTime]
0x18002e336  lea     r8, [rbp+ExitTime]; lpExitTime
0x18002e33a  mov     [rsp+80h+ReturnLength], rax; lpUserTime
0x18002e33f  lea     rdx, [rbp+var_40]; lpCreationTime
0x18002e343  call    cs:__imp_GetProcessTimes
0x18002e349  test    eax, eax
0x18002e34b  jnz     short loc_18002E36D
0x18002e34d  call    cs:__imp_GetLastError
0x18002e353  mov     ebx, eax
0x18002e355  test    eax, eax
0x18002e357  jz      loc_18002E3EC
0x18002e35d  jle     short loc_18002E365
0x18002e35f  movzx   ebx, ax
0x18002e362  or      ebx, r15d
0x18002e365  test    ebx, ebx
0x18002e367  js      loc_18002E3F1
0x18002e36d  mov     rax, qword ptr [rbp+var_40.dwLowDateTime]
0x18002e371  cmp     qword ptr [rbp+CreationTime.dwLowDateTime], rax
0x18002e375  jle     short loc_18002E381
0x18002e377  mov     ebx, 80004005h
0x18002e37c  jmp     loc_18002E414
0x18002e381  lea     r9, [rbp+dwSize]; lpdwSize
0x18002e385  mov     r8, rsi; lpExeName
0x18002e388  xor     edx, edx; dwFlags
0x18002e38a  mov     rcx, rdi; hProcess
0x18002e38d  call    cs:__imp_QueryFullProcessImageNameW
0x18002e393  test    eax, eax
0x18002e395  jz      short loc_18002E39B
0x18002e397  xor     ebx, ebx
0x18002e399  jmp     short loc_18002E3B3
0x18002e39b  call    cs:__imp_GetLastError
0x18002e3a1  mov     ebx, eax
0x18002e3a3  test    eax, eax
0x18002e3a5  jz      short loc_18002E3EC
0x18002e3a7  jle     short loc_18002E3AF
0x18002e3a9  movzx   ebx, ax
0x18002e3ac  or      ebx, r15d
0x18002e3af  test    ebx, ebx
0x18002e3b1  js      short loc_18002E3F1
0x18002e3b3  mov     eax, [rbp+dwSize]
0x18002e3b6  lea     rcx, [rsi+rax*2]
0x18002e3ba  cmp     rcx, rsi
0x18002e3bd  jz      short loc_18002E414
0x18002e3bf  mov     rdx, rcx
0x18002e3c2  mov     eax, 5Ch ; '\'
0x18002e3c7  sub     rcx, 2
0x18002e3cb  cmp     ax, [rcx]
0x18002e3ce  jnz     short loc_18002E3BA
0x18002e3d0  jmp     short loc_18002E3DD
0x18002e3d2  mov     [rsi], cx
0x18002e3d5  lea     rdx, [rdx+2]
0x18002e3d9  add     rsi, 2
0x18002e3dd  movzx   ecx, word ptr [rdx]
0x18002e3e0  xor     eax, eax
0x18002e3e2  cmp     ax, cx
0x18002e3e5  jnz     short loc_18002E3D2
0x18002e3e7  mov     [rsi], ax
0x18002e3ea  jmp     short loc_18002E414
0x18002e3ec  mov     ebx, 80004005h
0x18002e3f1  mov     eax, ebx
0x18002e3f3  mov     dword ptr [rsp+80h+ReturnLength], ebx
0x18002e3f7  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18002e3fe  xor     r8d, r8d; int
0x18002e401  lea     rdx, aWdcgetparentpr; "WdcGetParentProcessImageName"
0x18002e408  lea     rcx, aBaseDiagnosisP_34; "base\\diagnosis\\pdui\\perfmon\\mon\\fe"...
0x18002e40f  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18002e414  lea     rax, [rdi-1]
0x18002e418  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002e41c  ja      short loc_18002E427
0x18002e41e  mov     rcx, rdi; hObject
0x18002e421  call    cs:__imp_CloseHandle
0x18002e427  mov     eax, ebx
0x18002e429  add     rsp, 80h
0x18002e430  pop     r15
0x18002e432  pop     rdi
0x18002e433  pop     rsi
0x18002e434  pop     rbx
0x18002e435  pop     rbp
0x18002e436  retn
```
