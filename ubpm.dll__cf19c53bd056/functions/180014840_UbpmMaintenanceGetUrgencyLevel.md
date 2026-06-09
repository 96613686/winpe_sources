# UbpmMaintenanceGetUrgencyLevel

- ea: `0x180014840`
- end: `0x180014b28`
- name: `UbpmMaintenanceGetUrgencyLevel`
- size: `744`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180013b60`

## callees

- `0x1800139cc`
- `0x180014840`
- `0x180015e10`
- `0x18001661c`
- `0x180016688`
- `0x18003488c`
- `0x18003d810`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x180014a01`
- `ntdll!RtlReleaseSRWLockShared` at `0x180014a01`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800149e9`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800149e9`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180014a1c`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180014a1c`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18001498a`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800149af`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800149d4`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18001498a`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800149af`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800149d4`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180014a34`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180014a34`

## pseudocode

```c
FILETIME __fastcall UbpmMaintenanceGetUrgencyLevel(__int64 a1, _BYTE *a2, FILETIME *a3)
{
  __int64 v6; // r14
  unsigned __int16 *v7; // r8
  __int64 v8; // r15
  __int64 v9; // r12
  FILETIME v10; // rax
  __int64 v11; // rcx
  char IsCritical; // al
  FILETIME result; // rax
  __int64 v14; // [rsp+30h] [rbp-99h]
  char v15[8]; // [rsp+50h] [rbp-79h] BYREF
  FILETIME v16; // [rsp+58h] [rbp-71h] BYREF
  FILETIME FileTime; // [rsp+60h] [rbp-69h] BYREF
  struct _FILETIME v18; // [rsp+68h] [rbp-61h] BYREF
  FILETIME v19; // [rsp+70h] [rbp-59h] BYREF
  FILETIME v20; // [rsp+78h] [rbp-51h] BYREF
  FILETIME v21; // [rsp+80h] [rbp-49h] BYREF
  FILETIME v22; // [rsp+88h] [rbp-41h] BYREF
  FILETIME v23; // [rsp+90h] [rbp-39h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+98h] [rbp-31h] BYREF
  _BYTE v25[36]; // [rsp+A8h] [rbp-21h] BYREF
  __int128 Source2; // [rsp+D0h] [rbp+7h] BYREF

  v15[0] = 0;
  v20 = 0;
  v18 = 0;
  memset(v25, 0, sizeof(v25));
  FileTime = 0;
  v19 = 0;
  Source2 = 0;
  v16 = 0;
  v6 = *(_QWORD *)DateTime::NowUTC(&SystemTime);
  v7 = *(unsigned __int16 **)(*(_QWORD *)(a1 + 24) + 48LL);
  v8 = 10000000 * (v7[6] + 60 * (v7[5] + 60 * (v7[4] + 24 * (v7[3] + 365LL * *v7 + 7LL * v7[2] + 30LL * v7[1]))));
  v9 = 10000000 * (v7[13] + 60 * (v7[12] + 60 * (v7[11] + 24 * (365LL * v7[7] + v7[10] + 7LL * v7[9] + 30LL * v7[8]))));
  if ( (unsigned int)UbpmStatsOperation(a1, 0, v25) )
  {
    v10 = 0;
    *(_DWORD *)v25 = 3;
    memset(&v25[4], 0, 32);
  }
  else
  {
    v10 = *(FILETIME *)&v25[4];
  }
  FileTime = v10;
  SystemTime = 0;
  if ( !FileTimeToSystemTime(&FileTime, &SystemTime) )
    FileTime = 0;
  v19 = *(FILETIME *)&v25[12];
  SystemTime = 0;
  if ( !FileTimeToSystemTime(&v19, &SystemTime) )
    v19 = 0;
  v16 = *(FILETIME *)&v25[28];
  SystemTime = 0;
  if ( !FileTimeToSystemTime(&v16, &SystemTime) )
    v16 = 0;
  RtlAcquireSRWLockShared(&g_SystemSetup);
  Source2 = xmmword_18004CA52;
  RtlReleaseSRWLockShared(&g_SystemSetup);
  SystemTime = 0;
  if ( RtlCompareMemory(&SystemTime, &Source2, 0x10u) == 16 )
  {
    v18 = 0;
  }
  else if ( !SystemTimeToFileTime((const SYSTEMTIME *)&Source2, &v18) )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v11);
    v18 = 0;
  }
  IsCritical = UbpmpMaintenanceTaskIsCritical(a1);
  v21 = v16;
  v22 = FileTime;
  v23 = v18;
  *(_QWORD *)&SystemTime.wYear = v6;
  UbpmpMaintenanceGetLevelForTime(v8, v9, (const FILETIME *)&SystemTime, &v23, &v22, &v21, v14, IsCritical, v15, &v20);
  *a2 = v15[0];
  result = v20;
  *a3 = v20;
  return result;
}

```

## disassembly

```asm
0x180014840  push    rbp
0x180014842  push    rbx
0x180014843  push    rsi
0x180014844  push    rdi
0x180014845  push    r12
0x180014847  push    r14
0x180014849  push    r15
0x18001484b  lea     rbp, [rsp-27h]
0x180014850  sub     rsp, 0F0h
0x180014857  mov     rax, cs:__security_cookie
0x18001485e  xor     rax, rsp
0x180014861  mov     [rbp+57h+var_40], rax
0x180014865  xor     eax, eax
0x180014867  mov     [rbp+57h+var_D0], 0
0x18001486b  xorps   xmm0, xmm0
0x18001486e  mov     [rbp+57h+var_A8], rax
0x180014872  mov     rbx, rcx
0x180014875  mov     dword ptr [rbp+57h+var_68+10h], eax
0x180014878  lea     rcx, [rbp+57h+SystemTime]
0x18001487c  mov     qword ptr [rbp+57h+var_B8.dwLowDateTime], rax
0x180014880  movups  [rbp+57h+var_78], xmm0
0x180014884  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], rax
0x180014888  mov     rsi, r8
0x18001488b  movups  xmmword ptr [rbp+57h+var_68], xmm0
0x18001488f  mov     qword ptr [rbp+57h+var_B0.dwLowDateTime], rax
0x180014893  mov     rdi, rdx
0x180014896  movups  [rbp+57h+Source2], xmm0
0x18001489a  mov     qword ptr [rbp+57h+var_C8.dwLowDateTime], rax
0x18001489e  call    ?NowUTC@DateTime@@SA?AV1@XZ; DateTime::NowUTC(void)
0x1800148a3  mov     r14, [rax]
0x1800148a6  mov     rax, [rbx+18h]
0x1800148aa  mov     r8, [rax+30h]
0x1800148ae  movzx   eax, word ptr [r8+2]
0x1800148b3  imul    rdx, rax, 1Eh
0x1800148b7  movzx   eax, word ptr [r8+4]
0x1800148bc  imul    rcx, rax, 7
0x1800148c0  movzx   eax, word ptr [r8]
0x1800148c4  add     rdx, rcx
0x1800148c7  imul    rcx, rax, 16Dh
0x1800148ce  movzx   eax, word ptr [r8+6]
0x1800148d3  add     rdx, rcx
0x1800148d6  add     rdx, rax
0x1800148d9  movzx   eax, word ptr [r8+8]
0x1800148de  lea     rcx, [rdx+rdx*2]
0x1800148e2  lea     rcx, [rax+rcx*8]
0x1800148e6  movzx   eax, word ptr [r8+0Ah]
0x1800148eb  imul    rdx, rcx, 3Ch ; '<'
0x1800148ef  add     rdx, rax
0x1800148f2  movzx   eax, word ptr [r8+0Ch]
0x1800148f7  imul    rcx, rdx, 3Ch ; '<'
0x1800148fb  add     rcx, rax
0x1800148fe  movzx   eax, word ptr [r8+10h]
0x180014903  imul    rdx, rax, 1Eh
0x180014907  imul    r15, rcx, 989680h
0x18001490e  movzx   eax, word ptr [r8+12h]
0x180014913  imul    rcx, rax, 7
0x180014917  movzx   eax, word ptr [r8+14h]
0x18001491c  add     rdx, rcx
0x18001491f  add     rdx, rax
0x180014922  movzx   eax, word ptr [r8+0Eh]
0x180014927  imul    rcx, rax, 16Dh
0x18001492e  movzx   eax, word ptr [r8+16h]
0x180014933  add     rdx, rcx
0x180014936  lea     rcx, [rdx+rdx*2]
0x18001493a  lea     rcx, [rax+rcx*8]
0x18001493e  movzx   eax, word ptr [r8+18h]
0x180014943  imul    rdx, rcx, 3Ch ; '<'
0x180014947  add     rdx, rax
0x18001494a  movzx   eax, word ptr [r8+1Ah]
0x18001494f  imul    rcx, rdx, 3Ch ; '<'
0x180014953  lea     r8, [rbp+57h+var_78]
0x180014957  xor     edx, edx
0x180014959  add     rcx, rax
0x18001495c  imul    r12, rcx, 989680h
0x180014963  mov     rcx, rbx
0x180014966  call    UbpmStatsOperation
0x18001496b  test    eax, eax
0x18001496d  jnz     loc_180014AD9
0x180014973  mov     rax, qword ptr [rbp+57h+var_78+4]
0x180014977  xorps   xmm0, xmm0
0x18001497a  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], rax
0x18001497e  lea     rdx, [rbp+57h+SystemTime]; lpSystemTime
0x180014982  lea     rcx, [rbp+57h+FileTime]; lpFileTime
0x180014986  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x18001498a  call    cs:__imp_FileTimeToSystemTime
0x180014990  test    eax, eax
0x180014992  jz      loc_180014AF7
0x180014998  mov     rax, qword ptr [rbp+57h+var_78+0Ch]
0x18001499c  lea     rdx, [rbp+57h+SystemTime]; lpSystemTime
0x1800149a0  xorps   xmm0, xmm0
0x1800149a3  mov     qword ptr [rbp+57h+var_B0.dwLowDateTime], rax
0x1800149a7  lea     rcx, [rbp+57h+var_B0]; lpFileTime
0x1800149ab  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x1800149af  call    cs:__imp_FileTimeToSystemTime
0x1800149b5  test    eax, eax
0x1800149b7  jz      loc_180014B02
0x1800149bd  mov     rax, qword ptr [rbp+57h+var_68+0Ch]
0x1800149c1  lea     rdx, [rbp+57h+SystemTime]; lpSystemTime
0x1800149c5  xorps   xmm0, xmm0
0x1800149c8  mov     qword ptr [rbp+57h+var_C8.dwLowDateTime], rax
0x1800149cc  lea     rcx, [rbp+57h+var_C8]; lpFileTime
0x1800149d0  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x1800149d4  call    cs:__imp_FileTimeToSystemTime
0x1800149da  test    eax, eax
0x1800149dc  jz      loc_180014B0D
0x1800149e2  lea     rcx, ?g_SystemSetup@@3U_UBPM_UTILS_SETUP_PARAMS@@A; _UBPM_UTILS_SETUP_PARAMS g_SystemSetup
0x1800149e9  call    cs:__imp_RtlAcquireSRWLockShared
0x1800149ef  movups  xmm0, cs:xmmword_18004CA52
0x1800149f6  lea     rcx, ?g_SystemSetup@@3U_UBPM_UTILS_SETUP_PARAMS@@A; _UBPM_UTILS_SETUP_PARAMS g_SystemSetup
0x1800149fd  movups  [rbp+57h+Source2], xmm0
0x180014a01  call    cs:__imp_RtlReleaseSRWLockShared
0x180014a07  xorps   xmm0, xmm0
0x180014a0a  lea     rdx, [rbp+57h+Source2]; Source2
0x180014a0e  mov     r8d, 10h; Length
0x180014a14  lea     rcx, [rbp+57h+SystemTime]; Source1
0x180014a18  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x180014a1c  call    cs:__imp_RtlCompareMemory
0x180014a22  cmp     rax, 10h
0x180014a26  jz      loc_180014ACC
0x180014a2c  lea     rdx, [rbp+57h+var_B8]; lpFileTime
0x180014a30  lea     rcx, [rbp+57h+Source2]; lpSystemTime
0x180014a34  call    cs:__imp_SystemTimeToFileTime
0x180014a3a  test    eax, eax
0x180014a3c  jz      loc_180014B18
0x180014a42  mov     rcx, rbx
0x180014a45  call    UbpmpMaintenanceTaskIsCritical
0x180014a4a  mov     rcx, qword ptr [rbp+57h+var_C8.dwLowDateTime]
0x180014a4e  lea     rdx, [rbp+57h+var_A8]
0x180014a52  mov     r8, qword ptr [rbp+57h+var_B8.dwLowDateTime]
0x180014a56  lea     r9, [rbp+57h+var_90]
0x180014a5a  mov     [rsp+120h+var_D8], rdx
0x180014a5f  lea     rdx, [rbp+57h+var_D0]
0x180014a63  mov     [rsp+120h+var_E0], rdx
0x180014a68  mov     rdx, r12
0x180014a6b  mov     [rsp+120h+var_E8], al
0x180014a6f  lea     rax, [rbp+57h+var_A0]
0x180014a73  mov     [rbp+57h+var_A0], rcx
0x180014a77  mov     rcx, qword ptr [rbp+57h+FileTime.dwLowDateTime]
0x180014a7b  mov     [rsp+120h+var_F8], rax
0x180014a80  lea     rax, [rbp+57h+var_98]
0x180014a84  mov     [rbp+57h+var_98], rcx
0x180014a88  mov     rcx, r15
0x180014a8b  mov     [rbp+57h+var_90], r8
0x180014a8f  lea     r8, [rbp+57h+SystemTime]
0x180014a93  mov     [rsp+120h+var_100], rax
0x180014a98  mov     qword ptr [rbp+57h+SystemTime.wYear], r14
0x180014a9c  call    UbpmpMaintenanceGetLevelForTime
0x180014aa1  movzx   eax, [rbp+57h+var_D0]
0x180014aa5  mov     [rdi], al
0x180014aa7  mov     rax, [rbp+57h+var_A8]
0x180014aab  mov     [rsi], rax
0x180014aae  mov     rcx, [rbp+57h+var_40]
0x180014ab2  xor     rcx, rsp; StackCookie
0x180014ab5  call    __security_check_cookie
0x180014aba  add     rsp, 0F0h
0x180014ac1  pop     r15
0x180014ac3  pop     r14
0x180014ac5  pop     r12
0x180014ac7  pop     rdi
0x180014ac8  pop     rsi
0x180014ac9  pop     rbx
0x180014aca  pop     rbp
0x180014acb  retn
0x180014acc  mov     qword ptr [rbp+57h+var_B8.dwLowDateTime], 0
0x180014ad4  jmp     loc_180014A42
0x180014ad9  xor     eax, eax
0x180014adb  mov     dword ptr [rbp+57h+var_78], 3
0x180014ae2  mov     qword ptr [rbp+57h+var_78+4], rax
0x180014ae6  mov     qword ptr [rbp+57h+var_78+0Ch], rax
0x180014aea  mov     qword ptr [rbp+57h+var_68+4], rax
0x180014aee  mov     qword ptr [rbp+57h+var_68+0Ch], rax
0x180014af2  jmp     loc_180014977
0x180014af7  xor     eax, eax
0x180014af9  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], rax
0x180014afd  jmp     loc_180014998
0x180014b02  xor     eax, eax
0x180014b04  mov     qword ptr [rbp+57h+var_B0.dwLowDateTime], rax
0x180014b08  jmp     loc_1800149BD
0x180014b0d  xor     eax, eax
0x180014b0f  mov     qword ptr [rbp+57h+var_C8.dwLowDateTime], rax
0x180014b13  jmp     loc_1800149E2
0x180014b18  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180014b1d  xor     eax, eax
0x180014b1f  mov     qword ptr [rbp+57h+var_B8.dwLowDateTime], rax
0x180014b23  jmp     loc_180014A42
```
