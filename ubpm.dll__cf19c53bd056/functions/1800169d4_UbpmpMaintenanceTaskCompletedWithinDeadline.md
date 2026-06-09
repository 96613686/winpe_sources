# UbpmpMaintenanceTaskCompletedWithinDeadline

- ea: `0x1800169d4`
- end: `0x180016b7d`
- name: `UbpmpMaintenanceTaskCompletedWithinDeadline`
- size: `425`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001c000`

## callees

- `0x180015e10`
- `0x1800169d4`
- `0x180016b90`
- `0x18003d810`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016b10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016b10`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180016a46`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180016a46`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180016aef`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180016b01`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180016aef`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180016b01`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180016a9a`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180016a9a`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180016acb`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180016add`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180016acb`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180016add`

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
0x1800169d4  mov     [rsp-8+arg_10], rbx
0x1800169d9  mov     [rsp-8+arg_18], rsi
0x1800169de  push    rbp
0x1800169df  push    rdi
0x1800169e0  push    r14
0x1800169e2  lea     rbp, [rsp-47h]
0x1800169e7  sub     rsp, 90h
0x1800169ee  mov     rax, cs:__security_cookie
0x1800169f5  xor     rax, rsp
0x1800169f8  mov     [rbp+57h+var_20], rax
0x1800169fc  xor     r14d, r14d
0x1800169ff  xor     eax, eax
0x180016a01  mov     [rbp+57h+var_38], eax
0x180016a04  xorps   xmm0, xmm0
0x180016a07  mov     [rdx], r14b
0x180016a0a  xorps   xmm1, xmm1
0x180016a0d  mov     rax, [rcx+18h]
0x180016a11  mov     rsi, rcx
0x180016a14  movups  [rbp+57h+var_58], xmm0
0x180016a18  mov     qword ptr [rbp+57h+FileTime1.dwLowDateTime], r14
0x180016a1c  mov     rdi, rdx
0x180016a1f  movups  xmmword ptr [rbp+57h+FileTime.dwLowDateTime], xmm0
0x180016a23  mov     qword ptr [rbp+57h+FileTime2.dwLowDateTime], r14
0x180016a27  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x180016a2b  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], r14
0x180016a2f  movups  xmmword ptr [rbp+57h+var_30.wYear], xmm1
0x180016a33  mov     rcx, [rax+30h]
0x180016a37  cmp     [rcx+0Eh], r14w
0x180016a3c  jz      loc_180016B3E
0x180016a42  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180016a46  call    cs:__imp_GetSystemTimeAsFileTime
0x180016a4c  lea     r8, [rbp+57h+var_58]
0x180016a50  xor     edx, edx
0x180016a52  mov     rcx, rsi
0x180016a55  call    UbpmStatsOperation
0x180016a5a  mov     ebx, eax
0x180016a5c  test    eax, eax
0x180016a5e  jnz     loc_180016B18
0x180016a64  cmp     [rbp+57h+var_38], r14d
0x180016a68  jz      loc_180016B18
0x180016a6e  cmp     [rbp+57h+FileTime.dwHighDateTime+8], r14d
0x180016a72  jz      loc_180016B18
0x180016a78  cmp     [rbp+57h+FileTime.dwLowDateTime+8], 8007050Bh
0x180016a7f  jz      loc_180016B18
0x180016a85  cmp     [rbp+57h+FileTime.dwLowDateTime+8], 8007042Bh
0x180016a8c  jz      loc_180016B18
0x180016a92  lea     rdx, [rbp+57h+SystemTime]; lpSystemTime
0x180016a96  lea     rcx, [rbp+57h+FileTime.dwHighDateTime+8]; lpFileTime
0x180016a9a  call    cs:__imp_FileTimeToSystemTime
0x180016aa0  test    eax, eax
0x180016aa2  jz      short loc_180016B10
0x180016aa4  mov     rax, [rsi+18h]
0x180016aa8  lea     r8, [rbp+57h+var_30]; struct _SYSTEMTIME *
0x180016aac  lea     rcx, [rbp+57h+SystemTime]; struct _SYSTEMTIME *
0x180016ab0  mov     rdx, [rax+30h]
0x180016ab4  add     rdx, 0Eh; struct _UBPM_TIMESPAN *
0x180016ab8  call    ?UbpmpUtilsAddPeriodToSystemTime@@YAKPEAU_SYSTEMTIME@@PEAU_UBPM_TIMESPAN@@0@Z; UbpmpUtilsAddPeriodToSystemTime(_SYSTEMTIME *,_UBPM_TIMESPAN *,_SYSTEMTIME *)
0x180016abd  mov     ebx, eax
0x180016abf  test    eax, eax
0x180016ac1  jnz     short loc_180016B18
0x180016ac3  lea     rdx, [rbp+57h+FileTime1]; lpFileTime
0x180016ac7  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x180016acb  call    cs:__imp_SystemTimeToFileTime
0x180016ad1  test    eax, eax
0x180016ad3  jz      short loc_180016B10
0x180016ad5  lea     rdx, [rbp+57h+FileTime2]; lpFileTime
0x180016ad9  lea     rcx, [rbp+57h+var_30]; lpSystemTime
0x180016add  call    cs:__imp_SystemTimeToFileTime
0x180016ae3  test    eax, eax
0x180016ae5  jz      short loc_180016B10
0x180016ae7  lea     rdx, [rbp+57h+SystemTimeAsFileTime]; lpFileTime2
0x180016aeb  lea     rcx, [rbp+57h+FileTime1]; lpFileTime1
0x180016aef  call    cs:__imp_CompareFileTime
0x180016af5  test    eax, eax
0x180016af7  jns     short loc_180016B18
0x180016af9  lea     rdx, [rbp+57h+FileTime2]; lpFileTime2
0x180016afd  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpFileTime1
0x180016b01  call    cs:__imp_CompareFileTime
0x180016b07  test    eax, eax
0x180016b09  jg      short loc_180016B18
0x180016b0b  mov     byte ptr [rdi], 1
0x180016b0e  jmp     short loc_180016B18
0x180016b10  call    cs:__imp_GetLastError
0x180016b16  mov     ebx, eax
0x180016b18  mov     eax, ebx
0x180016b1a  mov     rcx, [rbp+57h+var_20]
0x180016b1e  xor     rcx, rsp; StackCookie
0x180016b21  call    __security_check_cookie
0x180016b26  lea     r11, [rsp+0A0h+var_10]
0x180016b2e  mov     rbx, [r11+30h]
0x180016b32  mov     rsi, [r11+38h]
0x180016b36  mov     rsp, r11
0x180016b39  pop     r14
0x180016b3b  pop     rdi
0x180016b3c  pop     rbp
0x180016b3d  retn
0x180016b3e  cmp     [rcx+10h], r14w
0x180016b43  jnz     loc_180016A42
0x180016b49  cmp     [rcx+14h], r14w
0x180016b4e  jnz     loc_180016A42
0x180016b54  cmp     [rcx+16h], r14w
0x180016b59  jnz     loc_180016A42
0x180016b5f  cmp     [rcx+18h], r14w
0x180016b64  jnz     loc_180016A42
0x180016b6a  cmp     [rcx+1Ah], r14w
0x180016b6f  jnz     loc_180016A42
0x180016b75  mov     ebx, r14d
0x180016b78  mov     byte ptr [rdx], 1
0x180016b7b  jmp     short loc_180016B18
```
