# PfXpUpdateOptimalLayout

- ea: `0x180018ec0`
- end: `0x180019322`
- name: `PfXpUpdateOptimalLayout`
- size: `1122`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800959a0`

## callees

- `0x180018ec0`
- `0x1800193bc`
- `0x180019490`
- `0x1800195c8`
- `0x180019650`
- `0x1800197c4`
- `0x180019b24`
- `0x180019dfc`
- `0x18001a1f0`
- `0x18002341c`
- `0x1800619b4`
- `0x180094894`
- `0x180095688`
- `0x180095c80`
- `0x1800b645a`
- `0x1800b64c0`

## import_xrefs

- `ntdll!NtQueryInformationThread` at `0x180018fd2`
- `ntdll!NtQueryInformationThread` at `0x180018fd2`
- `ntdll!RtlNtStatusToDosError` at `0x180018fde`
- `ntdll!RtlNtStatusToDosError` at `0x180018fde`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001928d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001928d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001906f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001921c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001906f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001921c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800191da`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800191da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180018faf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180018feb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800192ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180018faf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180018feb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800192ef`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800190ba`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800190ba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800192e3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800192e3`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetSystemPowerStatus` at `0x180018f94`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetSystemPowerStatus` at `0x180018f94`

## pseudocode

```c
__int64 __fastcall PfXpUpdateOptimalLayout(__int64 a1)
{
  void *v2; // rsi
  int v3; // r14d
  unsigned int LastDiskLayoutTime; // ebx
  __int64 v5; // r9
  HANDLE CurrentThread; // rax
  int v7; // eax
  HANDLE v8; // rax
  unsigned int LayoutFilePath; // eax
  __int64 v10; // r8
  char v11; // di
  __int64 v12; // r8
  _BOOL8 v13; // rdx
  FILETIME v14; // rbx
  struct _FILETIME v15; // rdi
  __int64 v16; // rax
  HANDLE v17; // rax
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  BYTE Data[4]; // [rsp+38h] [rbp-C8h] BYREF
  BYTE v21[4]; // [rsp+3Ch] [rbp-C4h] BYREF
  int ThreadInformation; // [rsp+40h] [rbp-C0h] BYREF
  DWORD Type; // [rsp+44h] [rbp-BCh] BYREF
  BYTE v24[4]; // [rsp+48h] [rbp-B8h] BYREF
  int v25; // [rsp+4Ch] [rbp-B4h] BYREF
  FILETIME FileTime1; // [rsp+50h] [rbp-B0h] BYREF
  FILETIME FileTime2; // [rsp+58h] [rbp-A8h] BYREF
  int v28; // [rsp+60h] [rbp-A0h] BYREF
  void *v29; // [rsp+68h] [rbp-98h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v31[16]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v32; // [rsp+90h] [rbp-70h] BYREF
  __int64 *v33; // [rsp+98h] [rbp-68h]
  __int64 v34; // [rsp+A8h] [rbp-58h]
  char v35; // [rsp+D4h] [rbp-2Ch]
  _BYTE v36[16]; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v37[5]; // [rsp+F0h] [rbp-10h] BYREF
  int v38; // [rsp+118h] [rbp+18h]
  char v39; // [rsp+134h] [rbp+34h]
  _SYSTEM_POWER_STATUS SystemPowerStatus; // [rsp+140h] [rbp+40h] BYREF

  FileTime1 = 0;
  SystemTimeAsFileTime = 0;
  *(_DWORD *)Data = 0;
  *(_DWORD *)v24 = 0;
  cbData = 0;
  Type = 0;
  v2 = 0;
  *(_DWORD *)v21 = 0;
  *(_QWORD *)&SystemPowerStatus.ACLineStatus = 0;
  SystemPowerStatus.BatteryFullLifeTime = 0;
  v29 = 0;
  v28 = 0;
  memset_0(v36, 0, 0x58u);
  v37[3] = 0;
  v37[1] = v37;
  v39 = 0;
  v37[0] = v37;
  memset_0(v31, 0, 0x58u);
  v34 = 0;
  v33 = &v32;
  v32 = (__int64)&v32;
  v3 = 8;
  v35 = 0;
  FileTime2 = 0;
  v25 = 0;
  if ( a1 && (!GetSystemPowerStatus(&SystemPowerStatus) || !SystemPowerStatus.ACLineStatus) )
    goto LABEL_3;
  CurrentThread = GetCurrentThread();
  ThreadInformation = 0;
  v7 = NtQueryInformationThread(CurrentThread, ThreadPagePriority, &ThreadInformation, 4u, 0);
  if ( v7 >= 0 )
    v3 = ThreadInformation;
  else
    RtlNtStatusToDosError(v7);
  v8 = GetCurrentThread();
  PfSetPagePriorityThread(v8);
  LastDiskLayoutTime = PfXpPreallocatePathList(v36);
  LODWORD(v5) = 0;
  if ( LastDiskLayoutTime )
    goto LABEL_37;
  LastDiskLayoutTime = PfXpPreallocatePathList(v31);
  LODWORD(v5) = 0;
  if ( LastDiskLayoutTime )
    goto LABEL_37;
  LastDiskLayoutTime = PfXpGetLastDiskLayoutTime(&FileTime2);
  LODWORD(v5) = 0;
  if ( LastDiskLayoutTime )
    goto LABEL_37;
  cbData = 4;
  if ( RegQueryValueExW(hKey, L"BootFilesOptimized", 0, &Type, Data, &cbData) )
    *(_DWORD *)Data = 0;
  LayoutFilePath = PfXpGetLayoutFilePath(&v29, &v28);
  v2 = v29;
  LastDiskLayoutTime = LayoutFilePath;
  LODWORD(v5) = 0;
  if ( LayoutFilePath )
    goto LABEL_37;
  if ( (unsigned int)PfsGetLastWriteTime(v29, &FileTime1, v10, 0) )
  {
    v11 = 1;
  }
  else
  {
    if ( CompareFileTime(&FileTime1, &FileTime2) <= 0 )
    {
      if ( (unsigned int)PfXpReadLayout(v2, v31, &FileTime1) )
      {
        PfXpCleanupPathList(v31);
        memset_0(v31, 0, LastDiskLayoutTime + 88);
        v34 = 0;
        v33 = &v32;
        v35 = 0;
        v32 = (__int64)&v32;
        LastDiskLayoutTime = PfXpPreallocatePathList(v31);
        v5 = 0;
        if ( LastDiskLayoutTime )
          goto LABEL_37;
      }
    }
    v11 = 0;
  }
  v38 = 9;
  v37[4] = PfXpLayoutFilterList;
  LastDiskLayoutTime = PfXpDetermineOptimalLayout(a1, v36, v21, v5);
  LODWORD(v5) = 0;
  if ( LastDiskLayoutTime )
    goto LABEL_37;
  if ( !(unsigned int)PfXpUpdateLayout(v31) )
  {
LABEL_3:
    LastDiskLayoutTime = 0;
LABEL_4:
    LODWORD(v5) = 0;
    goto LABEL_37;
  }
  LastDiskLayoutTime = PfXpSaveLayout(v2, v36, &FileTime1, &v25);
  v5 = 0;
  if ( !LastDiskLayoutTime )
  {
    v13 = 0;
    if ( !v11 )
      v13 = a1 != 0;
    if ( (*(_DWORD *)Data || !*(_DWORD *)v21) && v13 )
    {
      v14 = FileTime2;
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      v15 = SystemTimeAsFileTime;
      if ( *(_QWORD *)&SystemTimeAsFileTime > *(unsigned __int64 *)&v14 )
      {
        cbData = 4;
        v16 = RegQueryValueExW(hKey, L"MinRelayoutHours", 0, &Type, v24, &cbData)
            ? 2592000000000LL
            : 36000000000LL * *(unsigned int *)v24;
        if ( *(unsigned __int64 *)&v15 < v16 + *(_QWORD *)&v14 )
        {
          LastDiskLayoutTime = 1901;
          goto LABEL_4;
        }
      }
    }
    LastDiskLayoutTime = PfXpLaunchDefragger(a1, v13, v12, v5);
    LODWORD(v5) = 0;
    if ( !LastDiskLayoutTime )
    {
      RegSetValueExW(hKey, L"BootFilesOptimized", 0, 4u, v21, 4u);
      LastDiskLayoutTime = PfXpSetLastDiskLayoutTime(&FileTime1);
      LODWORD(v5) = 1;
    }
  }
LABEL_37:
  PfXpLogUpdateOptimalLayout((unsigned int)&FileTime2, 0, v25, v5, LastDiskLayoutTime);
  PfXpCleanupPathList(v36);
  PfXpCleanupPathList(v31);
  if ( v2 )
    HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v2);
  if ( v3 != 8 )
  {
    v17 = GetCurrentThread();
    PfSetPagePriorityThread(v17);
  }
  return LastDiskLayoutTime;
}

```

## disassembly

```asm
0x180018ec0  push    rbp
0x180018ec2  push    rbx
0x180018ec3  push    rsi
0x180018ec4  push    rdi
0x180018ec5  push    r12
0x180018ec7  push    r13
0x180018ec9  push    r14
0x180018ecb  push    r15
0x180018ecd  lea     rbp, [rsp-68h]
0x180018ed2  sub     rsp, 168h
0x180018ed9  mov     rax, cs:__security_cookie
0x180018ee0  xor     rax, rsp
0x180018ee3  mov     [rbp+0A0h+var_50], rax
0x180018ee7  xor     r13d, r13d
0x180018eea  xor     eax, eax
0x180018eec  mov     r15, rcx
0x180018eef  mov     qword ptr [rsp+1A0h+FileTime1.dwLowDateTime], r13
0x180018ef4  xor     edx, edx; Val
0x180018ef6  mov     qword ptr [rsp+1A0h+SystemTimeAsFileTime.dwLowDateTime], r13
0x180018efb  lea     rcx, [rbp+0A0h+var_C0]; void *
0x180018eff  mov     dword ptr [rsp+1A0h+Data], r13d
0x180018f04  lea     ebx, [rax+58h]
0x180018f07  mov     dword ptr [rsp+1A0h+var_158], r13d
0x180018f0c  mov     r8d, ebx; Size
0x180018f0f  mov     [rsp+1A0h+cbData], r13d
0x180018f14  mov     [rsp+1A0h+Type], r13d
0x180018f19  mov     esi, r13d
0x180018f1c  mov     dword ptr [rsp+1A0h+var_164], r13d
0x180018f21  mov     qword ptr [rbp+0A0h+SystemPowerStatus.ACLineStatus], rax
0x180018f25  mov     [rbp+0A0h+SystemPowerStatus.BatteryFullLifeTime], eax
0x180018f28  mov     [rsp+1A0h+var_138], r13
0x180018f2d  mov     [rsp+1A0h+var_140], r13d
0x180018f32  call    memset_0
0x180018f37  lea     rax, [rbp+0A0h+var_B0]
0x180018f3b  mov     [rbp+0A0h+var_98], r13
0x180018f3f  mov     [rbp+0A0h+var_A8], rax
0x180018f43  lea     rcx, [rbp+0A0h+var_120]; void *
0x180018f47  lea     rax, [rbp+0A0h+var_B0]
0x180018f4b  mov     [rbp+0A0h+var_6C], r13b
0x180018f4f  mov     r8d, ebx; Size
0x180018f52  mov     [rbp+0A0h+var_B0], rax
0x180018f56  xor     edx, edx; Val
0x180018f58  call    memset_0
0x180018f5d  mov     [rbp+0A0h+var_F8], r13
0x180018f61  lea     rax, [rbp+0A0h+var_110]
0x180018f65  mov     [rbp+0A0h+var_108], rax
0x180018f69  lea     rax, [rbp+0A0h+var_110]
0x180018f6d  mov     [rbp+0A0h+var_110], rax
0x180018f71  lea     r14d, [r13+8]
0x180018f75  mov     [rbp+0A0h+var_CC], r13b
0x180018f79  mov     r12b, r13b
0x180018f7c  mov     qword ptr [rsp+1A0h+FileTime2.dwLowDateTime], r13
0x180018f81  mov     [rsp+1A0h+var_170], r13b
0x180018f86  mov     [rsp+1A0h+var_154], r13d
0x180018f8b  test    r15, r15
0x180018f8e  jz      short loc_180018FAF
0x180018f90  lea     rcx, [rbp+0A0h+SystemPowerStatus]; lpSystemPowerStatus
0x180018f94  call    cs:__imp_GetSystemPowerStatus
0x180018f9a  test    eax, eax
0x180018f9c  jnz     short loc_180018FA9
0x180018f9e  mov     ebx, r13d
0x180018fa1  mov     r9d, r13d
0x180018fa4  jmp     loc_1800192A5
0x180018fa9  cmp     [rbp+0A0h+SystemPowerStatus.ACLineStatus], r13b
0x180018fad  jz      short loc_180018F9E
0x180018faf  call    cs:__imp_GetCurrentThread
0x180018fb5  mov     edi, 4
0x180018fba  mov     [rsp+1A0h+ThreadInformation], r13d
0x180018fbf  mov     r9d, edi; ThreadInformationLength
0x180018fc2  mov     [rsp+1A0h+ReturnLength], r13; ReturnLength
0x180018fc7  lea     r8, [rsp+1A0h+ThreadInformation]; ThreadInformation
0x180018fcc  mov     rcx, rax; ThreadHandle
0x180018fcf  lea     edx, [rdi+14h]; ThreadInformationClass
0x180018fd2  call    cs:__imp_NtQueryInformationThread
0x180018fd8  test    eax, eax
0x180018fda  jns     short loc_180018FE6
0x180018fdc  mov     ecx, eax; Status
0x180018fde  call    cs:__imp_RtlNtStatusToDosError
0x180018fe4  jmp     short loc_180018FEB
0x180018fe6  mov     r14d, [rsp+1A0h+ThreadInformation]
0x180018feb  call    cs:__imp_GetCurrentThread
0x180018ff1  mov     rcx, rax; ThreadHandle
0x180018ff4  mov     edx, 1
0x180018ff9  call    PfSetPagePriorityThread
0x180018ffe  lea     rcx, [rbp+0A0h+var_C0]
0x180019002  call    PfXpPreallocatePathList
0x180019007  mov     ebx, eax
0x180019009  mov     r9d, r13d
0x18001900c  test    eax, eax
0x18001900e  jnz     loc_1800192A5
0x180019014  lea     rcx, [rbp+0A0h+var_120]
0x180019018  call    PfXpPreallocatePathList
0x18001901d  mov     ebx, eax
0x18001901f  mov     r9d, r13d
0x180019022  test    eax, eax
0x180019024  jnz     loc_1800192A5
0x18001902a  lea     rcx, [rsp+1A0h+FileTime2]; lpFileTime1
0x18001902f  call    PfXpGetLastDiskLayoutTime
0x180019034  mov     ebx, eax
0x180019036  mov     r9d, r13d
0x180019039  test    eax, eax
0x18001903b  jnz     loc_1800192A5
0x180019041  mov     rcx, cs:hKey; hKey
0x180019048  lea     rax, [rsp+1A0h+cbData]
0x18001904d  mov     [rsp+1A0h+lpcbData], rax; lpcbData
0x180019052  lea     r9, [rsp+1A0h+Type]; lpType
0x180019057  lea     rax, [rsp+1A0h+Data]
0x18001905c  mov     [rsp+1A0h+cbData], edi
0x180019060  xor     r8d, r8d; lpReserved
0x180019063  mov     [rsp+1A0h+ReturnLength], rax; lpData
0x180019068  lea     rdx, ValueName; "BootFilesOptimized"
0x18001906f  call    cs:__imp_RegQueryValueExW
0x180019075  test    eax, eax
0x180019077  jz      short loc_18001907E
0x180019079  mov     dword ptr [rsp+1A0h+Data], r13d
0x18001907e  lea     rdx, [rsp+1A0h+var_140]
0x180019083  lea     rcx, [rsp+1A0h+var_138]
0x180019088  call    PfXpGetLayoutFilePath
0x18001908d  mov     rsi, [rsp+1A0h+var_138]
0x180019092  mov     ebx, eax
0x180019094  mov     r9d, r13d
0x180019097  test    eax, eax
0x180019099  jnz     loc_1800192A5
0x18001909f  lea     rdx, [rsp+1A0h+FileTime1]
0x1800190a4  mov     rcx, rsi
0x1800190a7  call    PfsGetLastWriteTime
0x1800190ac  test    eax, eax
0x1800190ae  jnz     short loc_180019124
0x1800190b0  lea     rdx, [rsp+1A0h+FileTime2]; lpFileTime2
0x1800190b5  lea     rcx, [rsp+1A0h+FileTime1]; lpFileTime1
0x1800190ba  call    cs:__imp_CompareFileTime
0x1800190c0  test    eax, eax
0x1800190c2  jg      short loc_18001911F
0x1800190c4  lea     r8, [rsp+1A0h+FileTime1]
0x1800190c9  mov     rcx, rsi
0x1800190cc  lea     rdx, [rbp+0A0h+var_120]
0x1800190d0  call    PfXpReadLayout
0x1800190d5  test    eax, eax
0x1800190d7  jz      short loc_18001911F
0x1800190d9  lea     rcx, [rbp+0A0h+var_120]
0x1800190dd  call    PfXpCleanupPathList
0x1800190e2  xor     edx, edx; Val
0x1800190e4  lea     r8d, [rbx+58h]; Size
0x1800190e8  lea     rcx, [rbp+0A0h+var_120]; void *
0x1800190ec  call    memset_0
0x1800190f1  lea     rax, [rbp+0A0h+var_110]
0x1800190f5  mov     [rbp+0A0h+var_F8], r13
0x1800190f9  mov     [rbp+0A0h+var_108], rax
0x1800190fd  lea     rcx, [rbp+0A0h+var_120]
0x180019101  lea     rax, [rbp+0A0h+var_110]
0x180019105  mov     [rbp+0A0h+var_CC], r13b
0x180019109  mov     [rbp+0A0h+var_110], rax
0x18001910d  call    PfXpPreallocatePathList
0x180019112  mov     ebx, eax
0x180019114  mov     r9d, r13d
0x180019117  test    eax, eax
0x180019119  jnz     loc_1800192A5
0x18001911f  mov     dil, r13b
0x180019122  jmp     short loc_180019127
0x180019124  mov     dil, 1
0x180019127  lea     rax, PfXpLayoutFilterList; "\b\b"
0x18001912e  mov     [rbp+0A0h+var_88], 9
0x180019135  lea     r8, [rsp+1A0h+var_164]
0x18001913a  mov     [rbp+0A0h+var_90], rax
0x18001913e  lea     rdx, [rbp+0A0h+var_C0]
0x180019142  mov     rcx, r15
0x180019145  call    PfXpDetermineOptimalLayout
0x18001914a  mov     ebx, eax
0x18001914c  mov     r9d, r13d
0x18001914f  test    eax, eax
0x180019151  jnz     loc_1800192A5
0x180019157  lea     r8, [rsp+1A0h+var_170]
0x18001915c  lea     rdx, [rbp+0A0h+var_C0]
0x180019160  lea     rcx, [rbp+0A0h+var_120]; void *
0x180019164  call    PfXpUpdateLayout
0x180019169  mov     r12b, [rsp+1A0h+var_170]
0x18001916e  test    eax, eax
0x180019170  jnz     short loc_180019181
0x180019172  test    r12b, r12b
0x180019175  jz      loc_180018F9E
0x18001917b  lea     rdx, [rbp+0A0h+var_120]
0x18001917f  jmp     short loc_180019185
0x180019181  lea     rdx, [rbp+0A0h+var_C0]
0x180019185  lea     r9, [rsp+1A0h+var_154]
0x18001918a  mov     rcx, rsi
0x18001918d  lea     r8, [rsp+1A0h+FileTime1]
0x180019192  call    PfXpSaveLayout
0x180019197  mov     ebx, eax
0x180019199  mov     r9d, r13d
0x18001919c  test    eax, eax
0x18001919e  jnz     loc_1800192A5
0x1800191a4  test    r15, r15
0x1800191a7  mov     edx, r13d
0x1800191aa  setnz   al
0x1800191ad  test    dil, dil
0x1800191b0  movzx   ecx, al
0x1800191b3  cmovz   edx, ecx
0x1800191b6  cmp     dword ptr [rsp+1A0h+Data], r13d
0x1800191bb  jnz     short loc_1800191C8
0x1800191bd  cmp     dword ptr [rsp+1A0h+var_164], r13d
0x1800191c2  jnz     loc_180019257
0x1800191c8  test    dl, dl
0x1800191ca  jz      loc_180019257
0x1800191d0  mov     rbx, qword ptr [rsp+1A0h+FileTime2.dwLowDateTime]
0x1800191d5  lea     rcx, [rsp+1A0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800191da  call    cs:__imp_GetSystemTimeAsFileTime
0x1800191e0  mov     rdi, qword ptr [rsp+1A0h+SystemTimeAsFileTime.dwLowDateTime]
0x1800191e5  cmp     rdi, rbx
0x1800191e8  jbe     short loc_180019257
0x1800191ea  mov     rcx, cs:hKey; hKey
0x1800191f1  lea     rax, [rsp+1A0h+cbData]
0x1800191f6  mov     [rsp+1A0h+lpcbData], rax; lpcbData
0x1800191fb  lea     r9, [rsp+1A0h+Type]; lpType
0x180019200  lea     rax, [rsp+1A0h+var_158]
0x180019205  mov     [rsp+1A0h+cbData], 4
0x18001920d  xor     r8d, r8d; lpReserved
0x180019210  mov     [rsp+1A0h+ReturnLength], rax; lpData
0x180019215  lea     rdx, aMinrelayouthou; "MinRelayoutHours"
0x18001921c  call    cs:__imp_RegQueryValueExW
0x180019222  test    eax, eax
0x180019224  jnz     short loc_18001923A
0x180019226  mov     eax, dword ptr [rsp+1A0h+var_158]
0x18001922a  mov     rcx, 861C46800h
0x180019234  imul    rax, rcx
0x180019238  jmp     short loc_180019244
0x18001923a  mov     rax, 25B7F3D4000h
0x180019244  lea     rcx, [rax+rbx]
0x180019248  cmp     rdi, rcx
0x18001924b  jnb     short loc_180019257
0x18001924d  mov     ebx, 76Dh
0x180019252  jmp     loc_180018FA1
0x180019257  mov     rcx, r15
0x18001925a  call    PfXpLaunchDefragger
0x18001925f  mov     ebx, eax
0x180019261  mov     r9d, r13d
0x180019264  test    eax, eax
0x180019266  jnz     short loc_1800192A5
0x180019268  lea     ecx, [rax+4]
0x18001926b  xor     r8d, r8d; Reserved
0x18001926e  mov     dword ptr [rsp+1A0h+lpcbData], ecx; cbData
0x180019272  lea     rax, [rsp+1A0h+var_164]
0x180019277  mov     r9d, ecx; dwType
0x18001927a  mov     [rsp+1A0h+ReturnLength], rax; lpData
0x18001927f  mov     rcx, cs:hKey; hKey
0x180019286  lea     rdx, ValueName; "BootFilesOptimized"
0x18001928d  call    cs:__imp_RegSetValueExW
0x180019293  lea     rcx, [rsp+1A0h+FileTime1]; lpFileTime
0x180019298  call    PfXpSetLastDiskLayoutTime
0x18001929d  mov     ebx, eax
0x18001929f  mov     r9d, 1
0x1800192a5  mov     r8d, [rsp+1A0h+var_154]
0x1800192aa  lea     rcx, [rsp+1A0h+FileTime2]
0x1800192af  movzx   edx, r12b
0x1800192b3  mov     dword ptr [rsp+1A0h+ReturnLength], ebx
0x1800192b7  call    PfXpLogUpdateOptimalLayout
0x1800192bc  lea     rcx, [rbp+0A0h+var_C0]
0x1800192c0  call    PfXpCleanupPathList
0x1800192c5  lea     rcx, [rbp+0A0h+var_120]
0x1800192c9  call    PfXpCleanupPathList
0x1800192ce  test    rsi, rsi
0x1800192d1  jz      short loc_1800192E9
0x1800192d3  mov     rcx, cs:PfSvcGlobals
0x1800192da  mov     r8, rsi; lpMem
0x1800192dd  xor     edx, edx; dwFlags
0x1800192df  mov     rcx, [rcx+58h]; hHeap
0x1800192e3  call    cs:__imp_HeapFree
0x1800192e9  cmp     r14d, 8
0x1800192ed  jz      short loc_180019300
0x1800192ef  call    cs:__imp_GetCurrentThread
0x1800192f5  mov     rcx, rax; ThreadHandle
0x1800192f8  mov     edx, r14d
0x1800192fb  call    PfSetPagePriorityThread
0x180019300  mov     eax, ebx
0x180019302  mov     rcx, [rbp+0A0h+var_50]
0x180019306  xor     rcx, rsp; StackCookie
0x180019309  call    __security_check_cookie
0x18001930e  add     rsp, 168h
0x180019315  pop     r15
0x180019317  pop     r14
0x180019319  pop     r13
0x18001931b  pop     r12
0x18001931d  pop     rdi
0x18001931e  pop     rsi
0x18001931f  pop     rbx
0x180019320  pop     rbp
0x180019321  retn
```
