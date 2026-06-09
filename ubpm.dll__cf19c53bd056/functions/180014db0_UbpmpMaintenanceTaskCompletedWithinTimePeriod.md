# UbpmpMaintenanceTaskCompletedWithinTimePeriod

- ea: `0x180014db0`
- end: `0x1800151be`
- name: `UbpmpMaintenanceTaskCompletedWithinTimePeriod`
- size: `1038`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18002c480`

## callees

- `0x180014db0`
- `0x180015e10`
- `0x1800160b0`
- `0x18003d810`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x180014e7e`
- `ntdll!RtlReleaseSRWLockShared` at `0x180014e7e`
- `ntdll!RtlAcquireSRWLockShared` at `0x180014e19`
- `ntdll!RtlAcquireSRWLockShared` at `0x180014e19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014fa6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800151a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014fa6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800151a7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180014e0c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180014e0c`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180014fea`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180015045`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180015057`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180015095`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800150ab`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800150ca`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180014fea`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180015045`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180015057`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180015095`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800150ab`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800150ca`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180014f97`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180014f97`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180014ec5`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180014fbe`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180014fd4`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18001516c`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180014ec5`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180014fbe`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180014fd4`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18001516c`

## pseudocode

```c
__int64 __fastcall UbpmpMaintenanceTaskCompletedWithinTimePeriod(__int64 a1, _BYTE *a2)
{
  __int64 v4; // rax
  _WORD *v5; // rbx
  unsigned __int64 v6; // rdx
  DWORD LastError; // ebx
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // rdx
  unsigned __int64 v11; // r8
  int v12; // r8d
  struct _FILETIME FileTime; // [rsp+30h] [rbp-39h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp-31h] BYREF
  FILETIME FileTime1; // [rsp+40h] [rbp-29h] BYREF
  FILETIME v16; // [rsp+48h] [rbp-21h] BYREF
  SYSTEMTIME SystemTime; // [rsp+50h] [rbp-19h] BYREF
  SYSTEMTIME v18; // [rsp+60h] [rbp-9h] BYREF
  FILETIME FileTime2[2]; // [rsp+70h] [rbp+7h] BYREF
  FILETIME v20[2]; // [rsp+80h] [rbp+17h] BYREF
  int v21; // [rsp+90h] [rbp+27h]

  FileTime1 = 0;
  v16 = 0;
  SystemTimeAsFileTime = 0;
  v21 = 0;
  SystemTime = 0;
  *a2 = 0;
  v18 = 0;
  *(_OWORD *)&FileTime2[0].dwLowDateTime = 0;
  *(_OWORD *)&v20[0].dwLowDateTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  RtlAcquireSRWLockShared(&g_SystemSetup);
  SystemTime = (SYSTEMTIME)xmmword_18004CA52;
  RtlReleaseSRWLockShared(&g_SystemSetup);
  if ( !*(_DWORD *)&SystemTime.wYear && !SystemTime.wDay )
    goto LABEL_18;
  v4 = *(_QWORD *)(a1 + 24);
  FileTime = 0;
  v5 = *(_WORD **)(v4 + 48);
  if ( *v5 || v5[1] )
  {
    if ( (unsigned __int16)(SystemTime.wYear + *v5 + ((unsigned __int16)v5[1] + SystemTime.wMonth - 1) / 12) < SystemTime.wYear )
      return 534;
    v18.wYear = SystemTime.wYear + *v5 + ((unsigned __int16)v5[1] + SystemTime.wMonth - 1) / 12;
    v12 = SystemTime.wMonth - 1 + (unsigned __int16)v5[1];
    v18.wDay = SystemTime.wDay;
    v18.wHour = SystemTime.wHour;
    v18.wMinute = SystemTime.wMinute;
    v18.wSecond = SystemTime.wSecond;
    v18.wMilliseconds = SystemTime.wMilliseconds;
    v18.wMonth = v12 % 12 + 1;
    while ( !SystemTimeToFileTime(&v18, &FileTime) )
    {
      if ( v18.wDay <= 0x1Cu )
        return 87;
      --v18.wDay;
    }
  }
  else if ( !SystemTimeToFileTime(&SystemTime, &FileTime) )
  {
    goto LABEL_14;
  }
  v6 = *(_QWORD *)&FileTime + 6048000000000LL * (unsigned __int16)v5[2];
  if ( v6 < *(_QWORD *)&FileTime )
    return 534;
  v9 = v6 + 864000000000LL * (unsigned __int16)v5[3];
  if ( v9 < v6 )
    return 534;
  v10 = v9 + 36000000000LL * (unsigned __int16)v5[4];
  if ( v10 < v9 )
    return 534;
  v11 = v10 + 600000000LL * (unsigned __int16)v5[5];
  if ( v11 < v10 || v11 + 10000000LL * (unsigned __int16)v5[6] < v11 )
    return 534;
  FileTime = (struct _FILETIME)(v11 + 10000000LL * (unsigned __int16)v5[6]);
  if ( !FileTimeToSystemTime(&FileTime, &v18) )
  {
LABEL_14:
    LastError = GetLastError();
    if ( LastError )
      return LastError;
    goto LABEL_15;
  }
  LastError = 0;
LABEL_15:
  if ( !SystemTimeToFileTime(&SystemTime, &FileTime1) || !SystemTimeToFileTime(&v18, &v16) )
    return GetLastError();
  if ( CompareFileTime(&FileTime1, &SystemTimeAsFileTime) < 0 && CompareFileTime(&SystemTimeAsFileTime, &v16) <= 0 )
    goto LABEL_28;
LABEL_18:
  LastError = UbpmStatsOperation(a1, 0, FileTime2);
  if ( !LastError )
  {
    if ( v21 )
    {
      if ( v20[1].dwHighDateTime )
      {
        if ( v20[1].dwLowDateTime != -2147023605
          && v20[1].dwLowDateTime != -2147023829
          && (CompareFileTime(&SystemTimeAsFileTime, (const FILETIME *)&FileTime2[0].dwHighDateTime) < 0
           || CompareFileTime(&SystemTimeAsFileTime, (const FILETIME *)&v20[1].dwHighDateTime) < 0
           || (LastError = UbpmpMaintenanceComputeCompletionPeriod(
                             &SystemTimeAsFileTime,
                             (FILETIME *)&FileTime2[0].dwHighDateTime,
                             (__int64)&v16)) == 0
           && CompareFileTime(&FileTime1, (const FILETIME *)&v20[1].dwHighDateTime) < 0
           && CompareFileTime((const FILETIME *)&v20[1].dwHighDateTime, &v16) <= 0) )
        {
LABEL_28:
          *a2 = 1;
        }
      }
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x180014db0  mov     [rsp-8+arg_10], rbx
0x180014db5  push    rbp
0x180014db6  push    rsi
0x180014db7  push    rdi
0x180014db8  push    r14
0x180014dba  push    r15
0x180014dbc  lea     rbp, [rsp-37h]
0x180014dc1  sub     rsp, 0A0h
0x180014dc8  mov     rax, cs:__security_cookie
0x180014dcf  xor     rax, rsp
0x180014dd2  mov     [rbp+57h+var_28], rax
0x180014dd6  xorps   xmm0, xmm0
0x180014dd9  xor     r15d, r15d
0x180014ddc  xor     eax, eax
0x180014dde  mov     qword ptr [rbp+57h+FileTime1.dwLowDateTime], r15
0x180014de2  mov     rdi, rcx
0x180014de5  mov     qword ptr [rbp+57h+var_78.dwLowDateTime], r15
0x180014de9  xorps   xmm1, xmm1
0x180014dec  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], r15
0x180014df0  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180014df4  mov     [rbp+57h+var_30], eax
0x180014df7  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x180014dfb  mov     [rdx], al
0x180014dfd  mov     r14, rdx
0x180014e00  movups  xmmword ptr [rbp+57h+var_60.wYear], xmm1
0x180014e04  movups  xmmword ptr [rbp+57h+FileTime2.dwLowDateTime], xmm0
0x180014e08  movups  xmmword ptr [rbp+57h+var_40.dwLowDateTime], xmm0
0x180014e0c  call    cs:__imp_GetSystemTimeAsFileTime
0x180014e12  lea     rcx, ?g_SystemSetup@@3U_UBPM_UTILS_SETUP_PARAMS@@A; _UBPM_UTILS_SETUP_PARAMS g_SystemSetup
0x180014e19  call    cs:__imp_RtlAcquireSRWLockShared
0x180014e1f  movzx   eax, word ptr cs:xmmword_18004CA52
0x180014e26  lea     rcx, ?g_SystemSetup@@3U_UBPM_UTILS_SETUP_PARAMS@@A; _UBPM_UTILS_SETUP_PARAMS g_SystemSetup
0x180014e2d  mov     [rbp+57h+SystemTime.wYear], ax
0x180014e31  movzx   eax, word ptr cs:xmmword_18004CA52+2
0x180014e38  mov     [rbp+57h+SystemTime.wMonth], ax
0x180014e3c  movzx   eax, word ptr cs:xmmword_18004CA52+4
0x180014e43  mov     [rbp+57h+SystemTime.wDayOfWeek], ax
0x180014e47  movzx   eax, word ptr cs:xmmword_18004CA52+6
0x180014e4e  mov     [rbp+57h+SystemTime.wDay], ax
0x180014e52  movzx   eax, word ptr cs:xmmword_18004CA52+8
0x180014e59  mov     [rbp+57h+SystemTime.wHour], ax
0x180014e5d  movzx   eax, word ptr cs:xmmword_18004CA52+0Ah
0x180014e64  mov     [rbp+57h+SystemTime.wMinute], ax
0x180014e68  movzx   eax, word ptr cs:xmmword_18004CA52+0Ch
0x180014e6f  mov     [rbp+57h+SystemTime.wSecond], ax
0x180014e73  movzx   eax, word ptr cs:xmmword_18004CA52+0Eh
0x180014e7a  mov     [rbp+57h+SystemTime.wMilliseconds], ax
0x180014e7e  call    cs:__imp_RtlReleaseSRWLockShared
0x180014e84  movzx   r10d, [rbp+57h+SystemTime.wYear]
0x180014e89  movzx   r11d, [rbp+57h+SystemTime.wDay]
0x180014e8e  test    r10w, r10w
0x180014e92  jz      loc_18001518D
0x180014e98  mov     rax, [rdi+18h]
0x180014e9c  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], r15
0x180014ea0  mov     rbx, [rax+30h]
0x180014ea4  movzx   r9d, word ptr [rbx]
0x180014ea8  test    r9w, r9w
0x180014eac  jnz     loc_1800150DA
0x180014eb2  cmp     [rbx+2], r15w
0x180014eb7  jnz     loc_1800150DA
0x180014ebd  lea     rdx, [rbp+57h+FileTime]; lpFileTime
0x180014ec1  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x180014ec5  call    cs:__imp_SystemTimeToFileTime
0x180014ecb  test    eax, eax
0x180014ecd  jz      loc_180014FA6
0x180014ed3  mov     eax, [rbp+57h+FileTime.dwLowDateTime]
0x180014ed6  mov     rdx, 58028E44000h
0x180014ee0  mov     ecx, [rbp+57h+FileTime.dwHighDateTime]
0x180014ee3  shl     rcx, 20h
0x180014ee7  or      rcx, rax
0x180014eea  movzx   eax, word ptr [rbx+4]
0x180014eee  imul    rdx, rax
0x180014ef2  add     rdx, rcx
0x180014ef5  cmp     rdx, rcx
0x180014ef8  jnb     short loc_180014F24
0x180014efa  mov     ebx, 216h
0x180014eff  mov     eax, ebx
0x180014f01  mov     rcx, [rbp+57h+var_28]
0x180014f05  xor     rcx, rsp; StackCookie
0x180014f08  call    __security_check_cookie
0x180014f0d  mov     rbx, [rsp+0C0h+arg_10]
0x180014f15  add     rsp, 0A0h
0x180014f1c  pop     r15
0x180014f1e  pop     r14
0x180014f20  pop     rdi
0x180014f21  pop     rsi
0x180014f22  pop     rbp
0x180014f23  retn
0x180014f24  movzx   eax, word ptr [rbx+6]
0x180014f28  mov     rcx, 0C92A69C000h
0x180014f32  imul    rcx, rax
0x180014f36  add     rcx, rdx
0x180014f39  cmp     rcx, rdx
0x180014f3c  jb      short loc_180014EFA
0x180014f3e  movzx   eax, word ptr [rbx+8]
0x180014f42  mov     rdx, 861C46800h
0x180014f4c  imul    rdx, rax
0x180014f50  add     rdx, rcx
0x180014f53  cmp     rdx, rcx
0x180014f56  jb      short loc_180014EFA
0x180014f58  movzx   eax, word ptr [rbx+0Ah]
0x180014f5c  imul    r8, rax, 23C34600h
0x180014f63  add     r8, rdx
0x180014f66  cmp     r8, rdx
0x180014f69  jb      short loc_180014EFA
0x180014f6b  movzx   eax, word ptr [rbx+0Ch]
0x180014f6f  imul    rax, 989680h
0x180014f76  add     rax, r8
0x180014f79  cmp     rax, r8
0x180014f7c  jb      loc_180014EFA
0x180014f82  mov     rcx, rax
0x180014f85  mov     [rbp+57h+FileTime.dwLowDateTime], eax
0x180014f88  shr     rcx, 20h
0x180014f8c  lea     rdx, [rbp+57h+var_60]; lpSystemTime
0x180014f90  mov     [rbp+57h+FileTime.dwHighDateTime], ecx
0x180014f93  lea     rcx, [rbp+57h+FileTime]; lpFileTime
0x180014f97  call    cs:__imp_FileTimeToSystemTime
0x180014f9d  test    eax, eax
0x180014f9f  jz      short loc_180014FA6
0x180014fa1  mov     ebx, r15d
0x180014fa4  jmp     short loc_180014FB6
0x180014fa6  call    cs:__imp_GetLastError
0x180014fac  mov     ebx, eax
0x180014fae  test    eax, eax
0x180014fb0  jnz     loc_180014EFF
0x180014fb6  lea     rdx, [rbp+57h+FileTime1]; lpFileTime
0x180014fba  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x180014fbe  call    cs:__imp_SystemTimeToFileTime
0x180014fc4  test    eax, eax
0x180014fc6  jz      loc_1800151A7
0x180014fcc  lea     rdx, [rbp+57h+var_78]; lpFileTime
0x180014fd0  lea     rcx, [rbp+57h+var_60]; lpSystemTime
0x180014fd4  call    cs:__imp_SystemTimeToFileTime
0x180014fda  test    eax, eax
0x180014fdc  jz      loc_1800151A7
0x180014fe2  lea     rdx, [rbp+57h+SystemTimeAsFileTime]; lpFileTime2
0x180014fe6  lea     rcx, [rbp+57h+FileTime1]; lpFileTime1
0x180014fea  call    cs:__imp_CompareFileTime
0x180014ff0  test    eax, eax
0x180014ff2  js      loc_1800150C2
0x180014ff8  lea     r8, [rbp+57h+FileTime2]
0x180014ffc  xor     edx, edx
0x180014ffe  mov     rcx, rdi
0x180015001  call    UbpmStatsOperation
0x180015006  mov     ebx, eax
0x180015008  test    eax, eax
0x18001500a  jnz     loc_180014EFF
0x180015010  cmp     [rbp+57h+var_30], r15d
0x180015014  jz      loc_180014EFF
0x18001501a  cmp     [rbp+57h+var_40.dwHighDateTime+8], r15d
0x18001501e  jz      loc_180014EFF
0x180015024  mov     eax, [rbp+57h+var_40.dwLowDateTime+8]
0x180015027  cmp     eax, 8007050Bh
0x18001502c  jz      loc_180014EFF
0x180015032  cmp     eax, 8007042Bh
0x180015037  jz      loc_180014EFF
0x18001503d  lea     rdx, [rbp+57h+FileTime2.dwHighDateTime]; lpFileTime2
0x180015041  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpFileTime1
0x180015045  call    cs:__imp_CompareFileTime
0x18001504b  test    eax, eax
0x18001504d  js      short loc_1800150B9
0x18001504f  lea     rdx, [rbp+57h+var_40.dwHighDateTime+8]; lpFileTime2
0x180015053  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpFileTime1
0x180015057  call    cs:__imp_CompareFileTime
0x18001505d  test    eax, eax
0x18001505f  js      short loc_1800150B9
0x180015061  mov     r8, [rdi+18h]
0x180015065  lea     rax, [rbp+57h+var_78]
0x180015069  lea     r9, [rbp+57h+FileTime1]
0x18001506d  mov     [rsp+0C0h+var_A0], rax; __int64
0x180015072  lea     rdx, [rbp+57h+FileTime2.dwHighDateTime]; lpFileTime
0x180015076  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpFileTime2
0x18001507a  mov     r8, [r8+30h]
0x18001507e  call    UbpmpMaintenanceComputeCompletionPeriod
0x180015083  mov     ebx, eax
0x180015085  test    eax, eax
0x180015087  jnz     loc_180014EFF
0x18001508d  lea     rdx, [rbp+57h+var_40.dwHighDateTime+8]; lpFileTime2
0x180015091  lea     rcx, [rbp+57h+FileTime1]; lpFileTime1
0x180015095  call    cs:__imp_CompareFileTime
0x18001509b  test    eax, eax
0x18001509d  jns     loc_180014EFF
0x1800150a3  lea     rdx, [rbp+57h+var_78]; lpFileTime2
0x1800150a7  lea     rcx, [rbp+57h+var_40.dwHighDateTime+8]; lpFileTime1
0x1800150ab  call    cs:__imp_CompareFileTime
0x1800150b1  test    eax, eax
0x1800150b3  jg      loc_180014EFF
0x1800150b9  mov     byte ptr [r14], 1
0x1800150bd  jmp     loc_180014EFF
0x1800150c2  lea     rdx, [rbp+57h+var_78]; lpFileTime2
0x1800150c6  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpFileTime1
0x1800150ca  call    cs:__imp_CompareFileTime
0x1800150d0  test    eax, eax
0x1800150d2  jg      loc_180014FF8
0x1800150d8  jmp     short loc_1800150B9
0x1800150da  movzx   eax, word ptr [rbx+2]
0x1800150de  movzx   esi, [rbp+57h+SystemTime.wMonth]
0x1800150e2  lea     ecx, [rsi-1]
0x1800150e5  add     ecx, eax
0x1800150e7  mov     eax, 2AAAAAABh
0x1800150ec  imul    ecx
0x1800150ee  sar     edx, 1
0x1800150f0  mov     ecx, edx
0x1800150f2  shr     ecx, 1Fh
0x1800150f5  add     edx, ecx
0x1800150f7  add     dx, r9w
0x1800150fb  add     dx, r10w
0x1800150ff  cmp     dx, r10w
0x180015103  jb      loc_180014EFA
0x180015109  mov     [rbp+57h+var_60.wYear], dx
0x18001510d  dec     esi
0x18001510f  movzx   r8d, word ptr [rbx+2]
0x180015114  mov     eax, 2AAAAAABh
0x180015119  add     r8d, esi
0x18001511c  mov     [rbp+57h+var_60.wDay], r11w
0x180015121  imul    r8d
0x180015124  mov     esi, 0FFFFh
0x180015129  sar     edx, 1
0x18001512b  mov     eax, edx
0x18001512d  shr     eax, 1Fh
0x180015130  add     edx, eax
0x180015132  lea     eax, [rdx+rdx*2]
0x180015135  shl     eax, 2
0x180015138  sub     r8d, eax
0x18001513b  movzx   eax, [rbp+57h+SystemTime.wHour]
0x18001513f  mov     [rbp+57h+var_60.wHour], ax
0x180015143  inc     r8w
0x180015147  movzx   eax, [rbp+57h+SystemTime.wMinute]
0x18001514b  mov     [rbp+57h+var_60.wMinute], ax
0x18001514f  movzx   eax, [rbp+57h+SystemTime.wSecond]
0x180015153  mov     [rbp+57h+var_60.wSecond], ax
0x180015157  movzx   eax, [rbp+57h+SystemTime.wMilliseconds]
0x18001515b  mov     [rbp+57h+var_60.wMilliseconds], ax
0x18001515f  mov     [rbp+57h+var_60.wMonth], r8w
0x180015164  lea     rdx, [rbp+57h+FileTime]; lpFileTime
0x180015168  lea     rcx, [rbp+57h+var_60]; lpSystemTime
0x18001516c  call    cs:__imp_SystemTimeToFileTime
0x180015172  test    eax, eax
0x180015174  jnz     loc_180014ED3
0x18001517a  movzx   eax, [rbp+57h+var_60.wDay]
0x18001517e  cmp     ax, 1Ch
0x180015182  jbe     short loc_1800151B4
0x180015184  add     ax, si
0x180015187  mov     [rbp+57h+var_60.wDay], ax
0x18001518b  jmp     short loc_180015164
0x18001518d  cmp     [rbp+57h+SystemTime.wMonth], r15w
0x180015192  jnz     loc_180014E98
0x180015198  test    r11w, r11w
0x18001519c  jnz     loc_180014E98
0x1800151a2  jmp     loc_180014FF8
0x1800151a7  call    cs:__imp_GetLastError
0x1800151ad  mov     ebx, eax
0x1800151af  jmp     loc_180014EFF
0x1800151b4  mov     ebx, 57h ; 'W'
0x1800151b9  jmp     loc_180014EFF
```
