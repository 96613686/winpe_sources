# CSdController::_UpdatePersistentStatus(_SD_BACKUP_RESULT,long,long,ushort const *,ushort const *,ushort const *,ushort const *,int)

- ea: `0x180013d3c`
- end: `0x180014081`
- name: `?_UpdatePersistentStatus@CSdController@@AEAAJW4_SD_BACKUP_RESULT@@JJPEBG111H@Z`
- size: `837`
- prototype: `__int64 __fastcall(__int64, unsigned int, unsigned int, unsigned int, BYTE *lpData, BYTE *, BYTE *, BYTE *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180012948`

## callees

- `0x180013d3c`
- `0x18001586c`
- `0x180015974`
- `0x18001b544`
- `0x18001eb28`
- `0x18001ebf8`
- `0x18001eccc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014039`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014039`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013d9f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013d9f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180013df5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180013df5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013db3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014050`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013db3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014050`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180013ed8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180013f1c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180013f60`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180013fa4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180013fee`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180013fff`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180013ed8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180013f1c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180013f60`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180013fa4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180013fee`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180013fff`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180013d91`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180013d91`

## string_xrefs

- `0x180013d68`: `CSdController::_UpdatePersistentStatus`

## pseudocode

```c
__int64 __fastcall CSdController::_UpdatePersistentStatus(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        BYTE *lpData,
        BYTE *a6,
        BYTE *a7,
        BYTE *a8,
        int a9)
{
  unsigned __int64 v13; // rbx
  int v14; // eax
  int v15; // edx
  int v16; // r8d
  int v17; // r9d
  bool v18; // sf
  __int16 v19; // ax
  unsigned int v20; // ebx
  HKEY hKey; // [rsp+50h] [rbp-41h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+58h] [rbp-39h] BYREF
  int v24; // [rsp+60h] [rbp-31h] BYREF
  __int16 v25; // [rsp+64h] [rbp-2Dh]
  __int16 v26; // [rsp+66h] [rbp-2Bh]
  DWORD dwDisposition; // [rsp+D0h] [rbp+3Fh] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v24, "CSdController::_UpdatePersistentStatus", 1248, 0);
  hKey = 0;
  dwDisposition = 0;
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v13 = (unsigned __int64)SystemTimeAsFileTime;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 64));
  v14 = RegCreateKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WindowsBackup\\Status",
          0,
          0,
          0,
          0x2001Fu,
          0,
          &hKey,
          &dwDisposition);
  if ( v14 > 0 )
    v14 = (unsigned __int16)v14 | 0x80070000;
  v24 = v14;
  v18 = v14 < 0;
  v19 = 1281;
  if ( v18 )
    goto LABEL_4;
  v25 = 1281;
  v24 = SetRegKeyVirtualization(hKey, v15, v16, v17);
  v19 = 1282;
  if ( v24 < 0 )
    goto LABEL_4;
  v25 = 1282;
  v24 = SxRegWriteDWORD(hKey, L"LastResultCode", a2);
  v19 = 1284;
  if ( v24 < 0 )
    goto LABEL_4;
  v25 = 1284;
  v24 = SxRegWriteDWORD(hKey, L"LastResultHr", a3);
  v19 = 1285;
  if ( v24 < 0 )
    goto LABEL_4;
  v25 = 1285;
  v24 = SxRegWriteDWORD(hKey, L"LastResultDetailedHr", a4);
  v19 = 1286;
  if ( v24 < 0 )
    goto LABEL_4;
  v25 = 1286;
  v24 = SxRegWriteULONGLONG(hKey, L"LastResultTime", v13);
  v19 = 1288;
  if ( v24 < 0 )
    goto LABEL_4;
  v25 = 1288;
  RegDeleteValueW(hKey, L"LastResultString");
  if ( lpData && *(_WORD *)lpData )
  {
    v24 = SxRegWriteString(hKey, L"LastResultString", lpData);
    v19 = 1293;
    if ( v24 < 0 )
      goto LABEL_4;
    v25 = 1293;
  }
  RegDeleteValueW(hKey, L"LastResultTarget");
  if ( a6 && *(_WORD *)a6 )
  {
    v24 = SxRegWriteString(hKey, L"LastResultTarget", a6);
    v19 = 1299;
    if ( v24 < 0 )
      goto LABEL_4;
    v25 = 1299;
  }
  RegDeleteValueW(hKey, L"LastResultTargetPresentableName");
  if ( a7 && *(_WORD *)a7 )
  {
    v24 = SxRegWriteString(hKey, L"LastResultTargetPresentableName", a7);
    v19 = 1305;
    if ( v24 < 0 )
      goto LABEL_4;
    v25 = 1305;
  }
  RegDeleteValueW(hKey, L"LastResultTargetLabel");
  if ( a8 && *(_WORD *)a8 )
  {
    v24 = SxRegWriteString(hKey, L"LastResultTargetLabel", a8);
    v19 = 1311;
    if ( v24 < 0 )
      goto LABEL_4;
    v25 = 1311;
  }
  if ( a9 )
  {
    RegDeleteValueW(hKey, L"BackupSpaceUsed");
    RegDeleteValueW(hKey, L"LocalBackupSpaceUsed");
  }
  if ( !a2 || a2 == 12 )
  {
    v24 = SxRegWriteULONGLONG(hKey, L"LastSuccess", v13);
    v19 = 1325;
    if ( v24 >= 0 )
    {
      v25 = 1325;
      goto LABEL_32;
    }
LABEL_4:
    v26 = v19;
  }
LABEL_32:
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 64));
  v20 = v24;
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v24);
  return v20;
}

```

## disassembly

```asm
0x180013d3c  mov     [rsp-8+arg_8], rbx
0x180013d41  mov     [rsp-8+arg_10], rsi
0x180013d46  push    rbp
0x180013d47  push    rdi
0x180013d48  push    r12
0x180013d4a  push    r14
0x180013d4c  push    r15
0x180013d4e  lea     rbp, [rsp-0Fh]
0x180013d53  sub     rsp, 0A0h
0x180013d5a  mov     r15d, r9d
0x180013d5d  mov     r14d, r8d
0x180013d60  mov     esi, edx
0x180013d62  mov     rdi, rcx
0x180013d65  xor     r9d, r9d; unsigned __int16
0x180013d68  lea     rdx, aCsdcontrollerU; "CSdController::_UpdatePersistentStatus"
0x180013d6f  mov     r8d, 4E0h; unsigned __int16
0x180013d75  lea     rcx, [rbp+2Fh+var_60]; this
0x180013d79  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180013d7e  xor     r12d, r12d
0x180013d81  lea     rcx, [rbp+2Fh+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180013d85  mov     [rbp+2Fh+hKey], r12
0x180013d89  mov     [rbp+2Fh+dwDisposition], r12d
0x180013d8d  mov     qword ptr [rbp+2Fh+SystemTimeAsFileTime.dwLowDateTime], r12
0x180013d91  call    cs:__imp_GetSystemTimeAsFileTime
0x180013d97  mov     rbx, qword ptr [rbp+2Fh+SystemTimeAsFileTime.dwLowDateTime]
0x180013d9b  lea     rcx, [rdi+40h]; lpCriticalSection
0x180013d9f  call    cs:__imp_EnterCriticalSection
0x180013da5  mov     rcx, [rbp+2Fh+hKey]; hKey
0x180013da9  lea     rax, [rcx-1]
0x180013dad  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180013db1  ja      short loc_180013DBD
0x180013db3  call    cs:__imp_RegCloseKey
0x180013db9  mov     [rbp+2Fh+hKey], r12
0x180013dbd  lea     rax, [rbp+2Fh+dwDisposition]
0x180013dc1  xor     r9d, r9d; lpClass
0x180013dc4  mov     [rsp+0C0h+lpdwDisposition], rax; lpdwDisposition
0x180013dc9  lea     rdx, c_wszSafedocsStatusKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180013dd0  lea     rax, [rbp+2Fh+hKey]
0x180013dd4  xor     r8d, r8d; Reserved
0x180013dd7  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180013ddc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180013de3  mov     [rsp+0C0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x180013de8  mov     [rsp+0C0h+samDesired], 2001Fh; samDesired
0x180013df0  mov     [rsp+0C0h+dwOptions], r12d; dwOptions
0x180013df5  call    cs:__imp_RegCreateKeyExW
0x180013dfb  test    eax, eax
0x180013dfd  jle     short loc_180013E07
0x180013dff  movzx   eax, ax
0x180013e02  or      eax, 80070000h
0x180013e07  mov     [rbp+2Fh+var_60], eax
0x180013e0a  test    eax, eax
0x180013e0c  mov     eax, 501h
0x180013e11  jns     short loc_180013E1C
0x180013e13  mov     [rbp+2Fh+var_5A], ax
0x180013e17  jmp     loc_180014035
0x180013e1c  mov     rcx, [rbp+2Fh+hKey]; KeyHandle
0x180013e20  mov     [rbp+2Fh+var_5C], ax
0x180013e24  call    ?SetRegKeyVirtualization@@YAJPEAUHKEY__@@HHH@Z; SetRegKeyVirtualization(HKEY__ *,int,int,int)
0x180013e29  mov     [rbp+2Fh+var_60], eax
0x180013e2c  test    eax, eax
0x180013e2e  mov     eax, 502h
0x180013e33  js      short loc_180013E13
0x180013e35  mov     rcx, [rbp+2Fh+hKey]; hKey
0x180013e39  lea     rdx, c_wszSafedocsScheduleLastResultCode; "LastResultCode"
0x180013e40  mov     r8d, esi; unsigned int
0x180013e43  mov     [rbp+2Fh+var_5C], ax
0x180013e47  call    ?SxRegWriteDWORD@@YAJPEAUHKEY__@@PEBGK@Z; SxRegWriteDWORD(HKEY__ *,ushort const *,ulong)
0x180013e4c  mov     [rbp+2Fh+var_60], eax
0x180013e4f  test    eax, eax
0x180013e51  mov     eax, 504h
0x180013e56  js      short loc_180013E13
0x180013e58  mov     rcx, [rbp+2Fh+hKey]; hKey
0x180013e5c  lea     rdx, c_wszSafedocsScheduleLastResultHr; "LastResultHr"
0x180013e63  mov     r8d, r14d; unsigned int
0x180013e66  mov     [rbp+2Fh+var_5C], ax
0x180013e6a  call    ?SxRegWriteDWORD@@YAJPEAUHKEY__@@PEBGK@Z; SxRegWriteDWORD(HKEY__ *,ushort const *,ulong)
0x180013e6f  mov     [rbp+2Fh+var_60], eax
0x180013e72  test    eax, eax
0x180013e74  mov     eax, 505h
0x180013e79  js      short loc_180013E13
0x180013e7b  mov     rcx, [rbp+2Fh+hKey]; hKey
0x180013e7f  lea     rdx, c_wszSafedocsScheduleLastResultDetailedHr; "LastResultDetailedHr"
0x180013e86  mov     r8d, r15d; unsigned int
0x180013e89  mov     [rbp+2Fh+var_5C], ax
0x180013e8d  call    ?SxRegWriteDWORD@@YAJPEAUHKEY__@@PEBGK@Z; SxRegWriteDWORD(HKEY__ *,ushort const *,ulong)
0x180013e92  mov     [rbp+2Fh+var_60], eax
0x180013e95  test    eax, eax
0x180013e97  mov     eax, 506h
0x180013e9c  js      loc_180013E13
0x180013ea2  mov     rcx, [rbp+2Fh+hKey]; hKey
0x180013ea6  lea     rdx, c_wszSafedocsScheduleLastResultTime; "LastResultTime"
0x180013ead  mov     r8, rbx; unsigned __int64
0x180013eb0  mov     [rbp+2Fh+var_5C], ax
0x180013eb4  call    ?SxRegWriteULONGLONG@@YAJPEAUHKEY__@@PEBG_K@Z; SxRegWriteULONGLONG(HKEY__ *,ushort const *,unsigned __int64)
0x180013eb9  mov     [rbp+2Fh+var_60], eax
0x180013ebc  test    eax, eax
0x180013ebe  mov     eax, 508h
0x180013ec3  js      loc_180013E13
0x180013ec9  mov     rcx, [rbp+2Fh+hKey]; hKey
0x180013ecd  lea     rdx, c_wszSafedocsScheduleLastResultString; "LastResultString"
0x180013ed4  mov     [rbp+2Fh+var_5C], ax
0x180013ed8  call    cs:__imp_RegDeleteValueW
0x180013ede  mov     r8, [rbp+2Fh+lpData]; lpData
0x180013ee2  test    r8, r8
0x180013ee5  jz      short loc_180013F11
0x180013ee7  cmp     [r8], r12w
0x180013eeb  jz      short loc_180013F11
0x180013eed  mov     rcx, [rbp+2Fh+hKey]; hKey
0x180013ef1  lea     rdx, c_wszSafedocsScheduleLastResultString; "LastResultString"
0x180013ef8  call    ?SxRegWriteString@@YAJPEAUHKEY__@@PEBG1@Z; SxRegWriteString(HKEY__ *,ushort const *,ushort const *)
0x180013efd  mov     [rbp+2Fh+var_60], eax
0x180013f00  test    eax, eax
0x180013f02  mov     eax, 50Dh
0x180013f07  js      loc_180013E13
0x180013f0d  mov     [rbp+2Fh+var_5C], ax
0x180013f11  mov     rcx, [rbp+2Fh+hKey]; hKey
0x180013f15  lea     rdx, c_wszSafedocsScheduleLastResultTarget; "LastResultTarget"
0x180013f1c  call    cs:__imp_RegDeleteValueW
0x180013f22  mov     r8, [rbp+2Fh+arg_28]; lpData
0x180013f26  test    r8, r8
0x180013f29  jz      short loc_180013F55
0x180013f2b  cmp     [r8], r12w
0x180013f2f  jz      short loc_180013F55
0x180013f31  mov     rcx, [rbp+2Fh+hKey]; hKey
0x180013f35  lea     rdx, c_wszSafedocsScheduleLastResultTarget; "LastResultTarget"
0x180013f3c  call    ?SxRegWriteString@@YAJPEAUHKEY__@@PEBG1@Z; SxRegWriteString(HKEY__ *,ushort const *,ushort const *)
0x180013f41  mov     [rbp+2Fh+var_60], eax
0x180013f44  test    eax, eax
0x180013f46  mov     eax, 513h
0x180013f4b  js      loc_180013E13
0x180013f51  mov     [rbp+2Fh+var_5C], ax
0x180013f55  mov     rcx, [rbp+2Fh+hKey]; hKey
0x180013f59  lea     rdx, c_wszSafedocsScheduleLastResultTargetPresName; "LastResultTargetPresentableName"
0x180013f60  call    cs:__imp_RegDeleteValueW
0x180013f66  mov     r8, [rbp+2Fh+arg_30]; lpData
0x180013f6a  test    r8, r8
0x180013f6d  jz      short loc_180013F99
0x180013f6f  cmp     [r8], r12w
0x180013f73  jz      short loc_180013F99
0x180013f75  mov     rcx, [rbp+2Fh+hKey]; hKey
0x180013f79  lea     rdx, c_wszSafedocsScheduleLastResultTargetPresName; "LastResultTargetPresentableName"
0x180013f80  call    ?SxRegWriteString@@YAJPEAUHKEY__@@PEBG1@Z; SxRegWriteString(HKEY__ *,ushort const *,ushort const *)
0x180013f85  mov     [rbp+2Fh+var_60], eax
0x180013f88  test    eax, eax
0x180013f8a  mov     eax, 519h
0x180013f8f  js      loc_180013E13
0x180013f95  mov     [rbp+2Fh+var_5C], ax
0x180013f99  mov     rcx, [rbp+2Fh+hKey]; hKey
0x180013f9d  lea     rdx, c_wszSafedocsScheduleLastResultTargetLabel; "LastResultTargetLabel"
0x180013fa4  call    cs:__imp_RegDeleteValueW
0x180013faa  mov     r8, [rbp+2Fh+arg_38]; lpData
0x180013fae  test    r8, r8
0x180013fb1  jz      short loc_180013FDD
0x180013fb3  cmp     [r8], r12w
0x180013fb7  jz      short loc_180013FDD
0x180013fb9  mov     rcx, [rbp+2Fh+hKey]; hKey
0x180013fbd  lea     rdx, c_wszSafedocsScheduleLastResultTargetLabel; "LastResultTargetLabel"
0x180013fc4  call    ?SxRegWriteString@@YAJPEAUHKEY__@@PEBG1@Z; SxRegWriteString(HKEY__ *,ushort const *,ushort const *)
0x180013fc9  mov     [rbp+2Fh+var_60], eax
0x180013fcc  test    eax, eax
0x180013fce  mov     eax, 51Fh
0x180013fd3  js      loc_180013E13
0x180013fd9  mov     [rbp+2Fh+var_5C], ax
0x180013fdd  cmp     [rbp+2Fh+arg_40], r12d
0x180013fe1  jz      short loc_180014005
0x180013fe3  mov     rcx, [rbp+2Fh+hKey]; hKey
0x180013fe7  lea     rdx, c_wszSafedocsScheduleTotalBackupSpaceUsed; "BackupSpaceUsed"
0x180013fee  call    cs:__imp_RegDeleteValueW
0x180013ff4  mov     rcx, [rbp+2Fh+hKey]; hKey
0x180013ff8  lea     rdx, c_wszSafedocsScheduleLocalBackupSpaceUsed; "LocalBackupSpaceUsed"
0x180013fff  call    cs:__imp_RegDeleteValueW
0x180014005  test    esi, esi
0x180014007  jz      short loc_18001400E
0x180014009  cmp     esi, 0Ch
0x18001400c  jnz     short loc_180014035
0x18001400e  mov     rcx, [rbp+2Fh+hKey]; hKey
0x180014012  lea     rdx, c_wszSafedocsScheduleLastSuccess; "LastSuccess"
0x180014019  mov     r8, rbx; unsigned __int64
0x18001401c  call    ?SxRegWriteULONGLONG@@YAJPEAUHKEY__@@PEBG_K@Z; SxRegWriteULONGLONG(HKEY__ *,ushort const *,unsigned __int64)
0x180014021  mov     [rbp+2Fh+var_60], eax
0x180014024  test    eax, eax
0x180014026  mov     eax, 52Dh
0x18001402b  js      loc_180013E13
0x180014031  mov     [rbp+2Fh+var_5C], ax
0x180014035  lea     rcx, [rdi+40h]; lpCriticalSection
0x180014039  call    cs:__imp_LeaveCriticalSection
0x18001403f  mov     rcx, [rbp+2Fh+hKey]; hKey
0x180014043  mov     ebx, [rbp+2Fh+var_60]
0x180014046  lea     rdx, [rcx-1]
0x18001404a  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18001404e  ja      short loc_18001405A
0x180014050  call    cs:__imp_RegCloseKey
0x180014056  mov     [rbp+2Fh+hKey], r12
0x18001405a  lea     rcx, [rbp+2Fh+var_60]; this
0x18001405e  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180014063  lea     r11, [rsp+0C0h+var_20]
0x18001406b  mov     eax, ebx
0x18001406d  mov     rbx, [r11+38h]
0x180014071  mov     rsi, [r11+40h]
0x180014075  mov     rsp, r11
0x180014078  pop     r15
0x18001407a  pop     r14
0x18001407c  pop     r12
0x18001407e  pop     rdi
0x18001407f  pop     rbp
0x180014080  retn
```
