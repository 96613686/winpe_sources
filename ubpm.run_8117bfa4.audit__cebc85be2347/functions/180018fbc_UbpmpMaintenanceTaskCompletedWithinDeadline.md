# UbpmpMaintenanceTaskCompletedWithinDeadline

- ea: `0x180018fbc`
- end: `0x180019194`
- name: `UbpmpMaintenanceTaskCompletedWithinDeadline`
- size: `472`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000cce0`

## callees

- `0x1800182a0`
- `0x180018db0`
- `0x180018fbc`
- `0x180040260`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019120`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019120`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001902e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001902e`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800190f3`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001910b`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800190f3`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001910b`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180019088`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180019088`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800190c3`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800190db`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800190c3`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800190db`

## pseudocode

```c
__int64 __fastcall UbpmpMaintenanceTaskCompletedWithinDeadline(__int64 a1, _BYTE *a2)
{
  __int64 v2; // rax
  _WORD *v5; // rcx
  unsigned int v6; // ebx
  struct _FILETIME SystemTimeAsFileTime; // [rsp+20h] [rbp-29h] BYREF
  FILETIME FileTime1; // [rsp+28h] [rbp-21h] BYREF
  FILETIME FileTime2; // [rsp+30h] [rbp-19h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+38h] [rbp-11h] BYREF
  __int128 v12; // [rsp+48h] [rbp-1h] BYREF
  FILETIME FileTime[2]; // [rsp+58h] [rbp+Fh] BYREF
  int v14; // [rsp+68h] [rbp+1Fh]
  SYSTEMTIME v15; // [rsp+70h] [rbp+27h] BYREF

  v14 = 0;
  *a2 = 0;
  v2 = *(_QWORD *)(a1 + 24);
  v12 = 0;
  FileTime1 = 0;
  *(_OWORD *)&FileTime[0].dwLowDateTime = 0;
  FileTime2 = 0;
  SystemTime = 0;
  SystemTimeAsFileTime = 0;
  v15 = 0;
  v5 = *(_WORD **)(v2 + 48);
  if ( !v5[7] && !v5[8] && !v5[10] && !v5[11] && !v5[12] && !v5[13] )
  {
    v6 = 0;
    *a2 = 1;
    return v6;
  }
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v6 = UbpmStatsOperation(a1, 0, &v12);
  if ( !v6
    && v14
    && FileTime[1].dwHighDateTime
    && FileTime[1].dwLowDateTime != -2147023605
    && FileTime[1].dwLowDateTime != -2147023829 )
  {
    if ( !FileTimeToSystemTime((const FILETIME *)&FileTime[1].dwHighDateTime, &SystemTime) )
      return GetLastError();
    v6 = UbpmpUtilsAddPeriodToSystemTime(
           &SystemTime,
           (struct _UBPM_TIMESPAN *)(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 48LL) + 14LL),
           &v15);
    if ( v6 )
      return v6;
    if ( !SystemTimeToFileTime(&SystemTime, &FileTime1) || !SystemTimeToFileTime(&v15, &FileTime2) )
      return GetLastError();
    if ( CompareFileTime(&FileTime1, &SystemTimeAsFileTime) < 0
      && CompareFileTime(&SystemTimeAsFileTime, &FileTime2) <= 0 )
    {
      *a2 = 1;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180018fbc  mov     [rsp-8+arg_10], rbx
0x180018fc1  mov     [rsp-8+arg_18], rsi
0x180018fc6  push    rbp
0x180018fc7  push    rdi
0x180018fc8  push    r14
0x180018fca  lea     rbp, [rsp-47h]
0x180018fcf  sub     rsp, 90h
0x180018fd6  mov     rax, cs:__security_cookie
0x180018fdd  xor     rax, rsp
0x180018fe0  mov     [rbp+57h+var_20], rax
0x180018fe4  xor     r14d, r14d
0x180018fe7  xor     eax, eax
0x180018fe9  mov     [rbp+57h+var_38], eax
0x180018fec  xorps   xmm0, xmm0
0x180018fef  mov     [rdx], r14b
0x180018ff2  xorps   xmm1, xmm1
0x180018ff5  mov     rax, [rcx+18h]
0x180018ff9  mov     rsi, rcx
0x180018ffc  movups  [rbp+57h+var_58], xmm0
0x180019000  mov     qword ptr [rbp+57h+FileTime1.dwLowDateTime], r14
0x180019004  mov     rdi, rdx
0x180019007  movups  xmmword ptr [rbp+57h+FileTime.dwLowDateTime], xmm0
0x18001900b  mov     qword ptr [rbp+57h+FileTime2.dwLowDateTime], r14
0x18001900f  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x180019013  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], r14
0x180019017  movups  xmmword ptr [rbp+57h+var_30.wYear], xmm1
0x18001901b  mov     rcx, [rax+30h]
0x18001901f  cmp     [rcx+0Eh], r14w
0x180019024  jz      loc_180019155
0x18001902a  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001902e  call    cs:__imp_GetSystemTimeAsFileTime
0x180019035  nop     dword ptr [rax+rax+00h]
0x18001903a  lea     r8, [rbp+57h+var_58]
0x18001903e  xor     edx, edx
0x180019040  mov     rcx, rsi
0x180019043  call    UbpmStatsOperation
0x180019048  mov     ebx, eax
0x18001904a  test    eax, eax
0x18001904c  jnz     loc_18001912E
0x180019052  cmp     [rbp+57h+var_38], r14d
0x180019056  jz      loc_18001912E
0x18001905c  cmp     [rbp+57h+FileTime.dwHighDateTime+8], r14d
0x180019060  jz      loc_18001912E
0x180019066  cmp     [rbp+57h+FileTime.dwLowDateTime+8], 8007050Bh
0x18001906d  jz      loc_18001912E
0x180019073  cmp     [rbp+57h+FileTime.dwLowDateTime+8], 8007042Bh
0x18001907a  jz      loc_18001912E
0x180019080  lea     rdx, [rbp+57h+SystemTime]; lpSystemTime
0x180019084  lea     rcx, [rbp+57h+FileTime.dwHighDateTime+8]; lpFileTime
0x180019088  call    cs:__imp_FileTimeToSystemTime
0x18001908f  nop     dword ptr [rax+rax+00h]
0x180019094  test    eax, eax
0x180019096  jz      loc_180019120
0x18001909c  mov     rax, [rsi+18h]
0x1800190a0  lea     r8, [rbp+57h+var_30]; struct _SYSTEMTIME *
0x1800190a4  lea     rcx, [rbp+57h+SystemTime]; struct _SYSTEMTIME *
0x1800190a8  mov     rdx, [rax+30h]
0x1800190ac  add     rdx, 0Eh; struct _UBPM_TIMESPAN *
0x1800190b0  call    ?UbpmpUtilsAddPeriodToSystemTime@@YAKPEAU_SYSTEMTIME@@PEAU_UBPM_TIMESPAN@@0@Z; UbpmpUtilsAddPeriodToSystemTime(_SYSTEMTIME *,_UBPM_TIMESPAN *,_SYSTEMTIME *)
0x1800190b5  mov     ebx, eax
0x1800190b7  test    eax, eax
0x1800190b9  jnz     short loc_18001912E
0x1800190bb  lea     rdx, [rbp+57h+FileTime1]; lpFileTime
0x1800190bf  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x1800190c3  call    cs:__imp_SystemTimeToFileTime
0x1800190ca  nop     dword ptr [rax+rax+00h]
0x1800190cf  test    eax, eax
0x1800190d1  jz      short loc_180019120
0x1800190d3  lea     rdx, [rbp+57h+FileTime2]; lpFileTime
0x1800190d7  lea     rcx, [rbp+57h+var_30]; lpSystemTime
0x1800190db  call    cs:__imp_SystemTimeToFileTime
0x1800190e2  nop     dword ptr [rax+rax+00h]
0x1800190e7  test    eax, eax
0x1800190e9  jz      short loc_180019120
0x1800190eb  lea     rdx, [rbp+57h+SystemTimeAsFileTime]; lpFileTime2
0x1800190ef  lea     rcx, [rbp+57h+FileTime1]; lpFileTime1
0x1800190f3  call    cs:__imp_CompareFileTime
0x1800190fa  nop     dword ptr [rax+rax+00h]
0x1800190ff  test    eax, eax
0x180019101  jns     short loc_18001912E
0x180019103  lea     rdx, [rbp+57h+FileTime2]; lpFileTime2
0x180019107  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpFileTime1
0x18001910b  call    cs:__imp_CompareFileTime
0x180019112  nop     dword ptr [rax+rax+00h]
0x180019117  test    eax, eax
0x180019119  jg      short loc_18001912E
0x18001911b  mov     byte ptr [rdi], 1
0x18001911e  jmp     short loc_18001912E
0x180019120  call    cs:__imp_GetLastError
0x180019127  nop     dword ptr [rax+rax+00h]
0x18001912c  mov     ebx, eax
0x18001912e  mov     eax, ebx
0x180019130  mov     rcx, [rbp+57h+var_20]
0x180019134  xor     rcx, rsp; StackCookie
0x180019137  call    __security_check_cookie
0x18001913c  lea     r11, [rsp+0A0h+var_10]
0x180019144  mov     rbx, [r11+30h]
0x180019148  mov     rsi, [r11+38h]
0x18001914c  mov     rsp, r11
0x18001914f  pop     r14
0x180019151  pop     rdi
0x180019152  pop     rbp
0x180019153  retn
0x180019155  cmp     [rcx+10h], r14w
0x18001915a  jnz     loc_18001902A
0x180019160  cmp     [rcx+14h], r14w
0x180019165  jnz     loc_18001902A
0x18001916b  cmp     [rcx+16h], r14w
0x180019170  jnz     loc_18001902A
0x180019176  cmp     [rcx+18h], r14w
0x18001917b  jnz     loc_18001902A
0x180019181  cmp     [rcx+1Ah], r14w
0x180019186  jnz     loc_18001902A
0x18001918c  mov     ebx, r14d
0x18001918f  mov     byte ptr [rdx], 1
0x180019192  jmp     short loc_18001912E
```
