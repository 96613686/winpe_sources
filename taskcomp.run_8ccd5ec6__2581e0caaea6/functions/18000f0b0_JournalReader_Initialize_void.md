# JournalReader::_Initialize(void)

- ea: `0x18000f0b0`
- end: `0x18000f8cb`
- name: `?_Initialize@JournalReader@@AEAAJXZ`
- size: `2075`
- prototype: `__int64 __fastcall(JournalReader *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x180011da4`

## callees

- `0x180005094`
- `0x180005224`
- `0x180007988`
- `0x180007994`
- `0x1800089f8`
- `0x18000cf80`
- `0x18000f0b0`
- `0x18000fc74`
- `0x180010570`
- `0x1800306c2`
- `0x180030700`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000f0ee`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000f0ee`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x18000f166`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x18000f1d5`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x18000f166`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x18000f1d5`
- `ntdll!NtQueryDirectoryFile` at `0x18000f4d6`
- `ntdll!NtQueryDirectoryFile` at `0x18000f4d6`
- `ntdll!RtlNtStatusToDosError` at `0x18000f4e8`
- `ntdll!RtlNtStatusToDosError` at `0x18000f4e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f143`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f1b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f224`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f2b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f330`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f400`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f5fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f6f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f82f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f864`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f88f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f143`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f1b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f224`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f2b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f330`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f400`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f5fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f6f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f82f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f864`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f88f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000f3ae`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000f43c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000f7e5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000f3ae`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000f43c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000f7e5`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18000f274`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18000f274`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x18000f2f2`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x18000f2f2`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000f5e8`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000f67a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000f6e7`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000f5e8`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000f67a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000f6e7`

## pseudocode

```c
signed int __fastcall JournalReader::_Initialize(JournalReader *this)
{
  JournalReader *v1; // r14
  wmi::AutoHandle *v2; // r13
  HANDLE EventW; // rbx
  DWORD LastError; // eax
  __int64 v5; // rdx
  HANDLE WaitableTimer; // rdi
  HANDLE v7; // rdi
  __int64 v8; // rax
  unsigned __int64 v9; // rcx
  HANDLE *v10; // r15
  HANDLE FileW; // rbx
  HANDLE *v12; // r12
  char *v13; // rbx
  ULONG v14; // edi
  _QWORD *v15; // rbx
  signed int result; // eax
  int v17; // eax
  ULONG v18; // eax
  signed int v19; // r14d
  signed int v20; // ebx
  HANDLE v21; // rcx
  HANDLE v22; // rcx
  void *v23; // rax
  char *v24; // rbx
  DWORD BytesReturned; // [rsp+60h] [rbp-A0h] BYREF
  DWORD MaximumComponentLength; // [rsp+64h] [rbp-9Ch] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+68h] [rbp-98h] BYREF
  _QWORD OutBuffer[8]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR RootPathName[5]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v30[534]; // [rsp+CAh] [rbp-36h] BYREF

  v1 = JournalReader::s_pReader;
  v2 = (JournalReader *)((char *)JournalReader::s_pReader + 8);
  EventW = CreateEventW(0, 0, 0, 0);
  wmi::AutoHandle::Close(v2);
  *(_QWORD *)v2 = EventW;
  if ( !EventW )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_89;
    }
    LastError = GetLastError();
    v5 = 10;
LABEL_88:
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v5, WPP_880a4eb608c037d792798d7e53d23858_Traceguids, LastError);
LABEL_89:
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  WaitableTimer = CreateWaitableTimerExW(0, 0, 0, 0x1F0003u);
  wmi::AutoHandle::Close((JournalReader *)((char *)v1 + 64));
  *((_QWORD *)v1 + 8) = WaitableTimer;
  if ( !WaitableTimer )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_89;
    }
    LastError = GetLastError();
    v5 = 11;
    goto LABEL_88;
  }
  v7 = CreateWaitableTimerExW(0, 0, 0, 0x1F0003u);
  wmi::AutoHandle::Close((JournalReader *)((char *)v1 + 72));
  *((_QWORD *)v1 + 9) = v7;
  if ( !v7 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_89;
    }
    LastError = GetLastError();
    v5 = 12;
    goto LABEL_88;
  }
  wcscpy(RootPathName, L"\\\\.\\");
  memset_0(v30, 0, 0x208u);
  if ( !GetVolumePathNameW(g_TasksFolderInfo, &RootPathName[4], 0x105u) )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_89;
    }
    LastError = GetLastError();
    v5 = 13;
    goto LABEL_88;
  }
  MaximumComponentLength = 0;
  if ( !GetVolumeInformationW(RootPathName, 0, 0, 0, &MaximumComponentLength, 0, 0, 0) )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_89;
    }
    LastError = GetLastError();
    v5 = 14;
    goto LABEL_88;
  }
  *((_DWORD *)v1 + 26) = 20 * (MaximumComponentLength + 31);
  v8 = -1;
  do
    ++v8;
  while ( RootPathName[v8] );
  if ( *((_WORD *)&OutBuffer[7] + v8 + 3) == 92 )
  {
    v9 = 2 * v8 - 2;
    if ( v9 >= 0x212 )
      _report_rangecheckfailure();
    *(WCHAR *)((char *)RootPathName + v9) = 0;
  }
  v10 = (HANDLE *)((char *)v1 + 88);
  FileW = CreateFileW(RootPathName, 0x80000000, 3u, 0, 3u, 0, 0);
  wmi::AutoHandle::Close((JournalReader *)((char *)v1 + 88));
  *((_QWORD *)v1 + 11) = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_89;
    }
    LastError = GetLastError();
    v5 = 15;
    goto LABEL_88;
  }
  v12 = (HANDLE *)((char *)v1 + 48);
  v13 = (char *)CreateFileW(g_TasksFolderInfo, 1u, 3u, 0, 3u, 0x2000001u, 0);
  wmi::AutoHandle::Close((JournalReader *)((char *)v1 + 48));
  *((_QWORD *)v1 + 6) = v13;
  if ( (unsigned __int64)(v13 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_89;
    }
    LastError = GetLastError();
    v5 = 16;
    goto LABEL_88;
  }
  IoStatusBlock = 0;
  v14 = 2 * MaximumComponentLength + 88;
  v15 = operator new[](v14);
  if ( !v15 )
  {
    operator delete(0);
    return -2147024882;
  }
  v17 = NtQueryDirectoryFile(*v12, 0, 0, 0, &IoStatusBlock, v15, v14, FileIdFullDirectoryInformation, 1u, 0, 0);
  if ( v17 < 0 )
  {
    v18 = RtlNtStatusToDosError(v17);
    v19 = v18;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_880a4eb608c037d792798d7e53d23858_Traceguids, v18);
    }
    if ( v19 > 0 )
      v19 = (unsigned __int16)v19 | 0x80070000;
    operator delete(v15);
    return v19;
  }
  *((_QWORD *)v1 + 12) = v15[9];
  operator delete(v15);
  memset_0(OutBuffer, 0, sizeof(OutBuffer));
  BytesReturned = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_880a4eb608c037d792798d7e53d23858_Traceguids);
  }
  memset_0(OutBuffer, 0, sizeof(OutBuffer));
  if ( DeviceIoControl(*v10, 0x900F4u, 0, 0, OutBuffer, 0x40u, &BytesReturned, 0) )
    goto LABEL_73;
  v20 = GetLastError();
  if ( (_WORD)v20 != 1179 )
    goto LABEL_66;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_880a4eb608c037d792798d7e53d23858_Traceguids);
  }
  v21 = *v10;
  IoStatusBlock.Pointer = 0;
  IoStatusBlock.Information = 0;
  BytesReturned = 0;
  if ( DeviceIoControl(v21, 0x900E7u, &IoStatusBlock, 0x10u, 0, 0, &BytesReturned, 0) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_880a4eb608c037d792798d7e53d23858_Traceguids);
    }
    v22 = *v10;
    BytesReturned = 0;
    if ( DeviceIoControl(v22, 0x900F4u, 0, 0, OutBuffer, 0x40u, &BytesReturned, 0) )
    {
LABEL_73:
      *((_QWORD *)v1 + 14) = OutBuffer[0];
      *((_QWORD *)v1 + 15) = OutBuffer[2];
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_880a4eb608c037d792798d7e53d23858_Traceguids);
      }
      *((_QWORD *)v1 + 2) = 0;
      *((_QWORD *)v1 + 3) = 0;
      *((_QWORD *)v1 + 4) = 0;
      *((_QWORD *)v1 + 5) = *(_QWORD *)v2;
      v23 = operator new[](0x22Au);
      wmi::AutoVectorPtr<unsigned char>::operator=((char *)v1 + 56, v23);
      if ( *((_QWORD *)v1 + 7) )
      {
        v24 = (char *)CreateFileW(g_TasksFolderInfo, 1u, 3u, 0, 3u, 0x42000000u, 0);
        wmi::AutoHandle::Close((JournalReader *)((char *)v1 + 48));
        *v12 = v24;
        if ( (unsigned __int64)(v24 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          return JournalReader::_ReadNext(v1);
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_89;
        }
        LastError = GetLastError();
        v5 = 23;
        goto LABEL_88;
      }
      return -2147024882;
    }
  }
  v20 = GetLastError();
LABEL_66:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      21,
      WPP_880a4eb608c037d792798d7e53d23858_Traceguids,
      (unsigned int)v20);
  }
  if ( v20 > 0 )
    return (unsigned __int16)v20 | 0x80070000;
  return v20;
}

```

## disassembly

```asm
0x18000f0b0  push    rbp
0x18000f0b2  push    rbx
0x18000f0b3  push    rsi
0x18000f0b4  push    rdi
0x18000f0b5  push    r12
0x18000f0b7  push    r13
0x18000f0b9  push    r14
0x18000f0bb  push    r15
0x18000f0bd  lea     rbp, [rsp-1F8h]
0x18000f0c5  sub     rsp, 2F8h
0x18000f0cc  mov     rax, cs:__security_cookie
0x18000f0d3  xor     rax, rsp
0x18000f0d6  mov     [rbp+230h+var_50], rax
0x18000f0dd  mov     r14, cs:?s_pReader@JournalReader@@0PEAV1@EA; JournalReader * JournalReader::s_pReader
0x18000f0e4  xor     r9d, r9d; lpName
0x18000f0e7  xor     r8d, r8d; bInitialState
0x18000f0ea  xor     edx, edx; bManualReset
0x18000f0ec  xor     ecx, ecx; lpEventAttributes
0x18000f0ee  call    cs:__imp_CreateEventW
0x18000f0f5  nop     dword ptr [rax+rax+00h]
0x18000f0fa  lea     r13, [r14+8]
0x18000f0fe  mov     rbx, rax
0x18000f101  mov     rcx, r13; this
0x18000f104  call    ?Close@AutoHandle@wmi@@QEAAXXZ; wmi::AutoHandle::Close(void)
0x18000f109  xor     r12d, r12d
0x18000f10c  mov     [r13+0], rbx
0x18000f110  test    rbx, rbx
0x18000f113  jnz     short loc_18000F157
0x18000f115  mov     rax, cs:WPP_GLOBAL_Control
0x18000f11c  lea     rsi, WPP_GLOBAL_Control
0x18000f123  cmp     rax, rsi
0x18000f126  jz      loc_18000F88F
0x18000f12c  mov     dil, 2
0x18000f12f  test    [rax+1Ch], dil
0x18000f133  jz      loc_18000F88F
0x18000f139  cmp     [rax+19h], dil
0x18000f13d  jb      loc_18000F88F
0x18000f143  call    cs:__imp_GetLastError
0x18000f14a  nop     dword ptr [rax+rax+00h]
0x18000f14f  lea     edx, [rbx+0Ah]
0x18000f152  jmp     loc_18000F875
0x18000f157  mov     esi, 1F0003h
0x18000f15c  xor     r8d, r8d; dwFlags
0x18000f15f  mov     r9d, esi; dwDesiredAccess
0x18000f162  xor     edx, edx; lpTimerName
0x18000f164  xor     ecx, ecx; lpTimerAttributes
0x18000f166  call    cs:__imp_CreateWaitableTimerExW
0x18000f16d  nop     dword ptr [rax+rax+00h]
0x18000f172  lea     rcx, [r14+40h]; this
0x18000f176  mov     rdi, rax
0x18000f179  call    ?Close@AutoHandle@wmi@@QEAAXXZ; wmi::AutoHandle::Close(void)
0x18000f17e  mov     [r14+40h], rdi
0x18000f182  test    rdi, rdi
0x18000f185  jnz     short loc_18000F1CB
0x18000f187  mov     rax, cs:WPP_GLOBAL_Control
0x18000f18e  lea     rsi, WPP_GLOBAL_Control
0x18000f195  cmp     rax, rsi
0x18000f198  jz      loc_18000F88F
0x18000f19e  mov     dil, 2
0x18000f1a1  test    [rax+1Ch], dil
0x18000f1a5  jz      loc_18000F88F
0x18000f1ab  cmp     [rax+19h], dil
0x18000f1af  jb      loc_18000F88F
0x18000f1b5  call    cs:__imp_GetLastError
0x18000f1bc  nop     dword ptr [rax+rax+00h]
0x18000f1c1  mov     edx, 0Bh
0x18000f1c6  jmp     loc_18000F875
0x18000f1cb  mov     r9d, esi; dwDesiredAccess
0x18000f1ce  xor     r8d, r8d; dwFlags
0x18000f1d1  xor     edx, edx; lpTimerName
0x18000f1d3  xor     ecx, ecx; lpTimerAttributes
0x18000f1d5  call    cs:__imp_CreateWaitableTimerExW
0x18000f1dc  nop     dword ptr [rax+rax+00h]
0x18000f1e1  lea     rcx, [r14+48h]; this
0x18000f1e5  mov     rdi, rax
0x18000f1e8  call    ?Close@AutoHandle@wmi@@QEAAXXZ; wmi::AutoHandle::Close(void)
0x18000f1ed  mov     [r14+48h], rdi
0x18000f1f1  test    rdi, rdi
0x18000f1f4  jnz     short loc_18000F23A
0x18000f1f6  mov     rax, cs:WPP_GLOBAL_Control
0x18000f1fd  lea     rsi, WPP_GLOBAL_Control
0x18000f204  cmp     rax, rsi
0x18000f207  jz      loc_18000F88F
0x18000f20d  mov     dil, 2
0x18000f210  test    [rax+1Ch], dil
0x18000f214  jz      loc_18000F88F
0x18000f21a  cmp     [rax+19h], dil
0x18000f21e  jb      loc_18000F88F
0x18000f224  call    cs:__imp_GetLastError
0x18000f22b  nop     dword ptr [rax+rax+00h]
0x18000f230  mov     edx, 0Ch
0x18000f235  jmp     loc_18000F875
0x18000f23a  movsd   xmm0, qword ptr cs:asc_1800528E8; "\\\\.\\"
0x18000f242  lea     rcx, [rbp+230h+var_266]; void *
0x18000f246  movzx   eax, word ptr cs:asc_1800528E8+8; ""
0x18000f24d  xor     edx, edx; Val
0x18000f24f  mov     r8d, 208h; Size
0x18000f255  movsd   qword ptr [rbp+230h+RootPathName], xmm0
0x18000f25a  mov     [rbp+230h+szVolumePathName], ax
0x18000f25e  call    memset_0
0x18000f263  mov     rcx, cs:?g_TasksFolderInfo@@3U_TasksFolderInfo@@A; lpszFileName
0x18000f26a  lea     rdx, [rbp+230h+szVolumePathName]; lpszVolumePathName
0x18000f26e  mov     r8d, 105h; cchBufferLength
0x18000f274  call    cs:__imp_GetVolumePathNameW
0x18000f27b  nop     dword ptr [rax+rax+00h]
0x18000f280  test    eax, eax
0x18000f282  jnz     short loc_18000F2C8
0x18000f284  mov     rax, cs:WPP_GLOBAL_Control
0x18000f28b  lea     rsi, WPP_GLOBAL_Control
0x18000f292  cmp     rax, rsi
0x18000f295  jz      loc_18000F88F
0x18000f29b  mov     dil, 2
0x18000f29e  test    [rax+1Ch], dil
0x18000f2a2  jz      loc_18000F88F
0x18000f2a8  cmp     [rax+19h], dil
0x18000f2ac  jb      loc_18000F88F
0x18000f2b2  call    cs:__imp_GetLastError
0x18000f2b9  nop     dword ptr [rax+rax+00h]
0x18000f2be  mov     edx, 0Dh
0x18000f2c3  jmp     loc_18000F875
0x18000f2c8  mov     [rsp+330h+nFileSystemNameSize], r12d; nFileSystemNameSize
0x18000f2cd  lea     rax, [rsp+330h+MaximumComponentLength]
0x18000f2d2  mov     [rsp+330h+lpFileSystemNameBuffer], r12; lpFileSystemNameBuffer
0x18000f2d7  lea     rcx, [rbp+230h+RootPathName]; lpRootPathName
0x18000f2db  mov     [rsp+330h+lpFileSystemFlags], r12; lpFileSystemFlags
0x18000f2e0  xor     r9d, r9d; lpVolumeSerialNumber
0x18000f2e3  xor     r8d, r8d; nVolumeNameSize
0x18000f2e6  mov     [rsp+330h+lpMaximumComponentLength], rax; lpMaximumComponentLength
0x18000f2eb  xor     edx, edx; lpVolumeNameBuffer
0x18000f2ed  mov     [rsp+330h+MaximumComponentLength], r12d
0x18000f2f2  call    cs:__imp_GetVolumeInformationW
0x18000f2f9  nop     dword ptr [rax+rax+00h]
0x18000f2fe  test    eax, eax
0x18000f300  jnz     short loc_18000F346
0x18000f302  mov     rax, cs:WPP_GLOBAL_Control
0x18000f309  lea     rsi, WPP_GLOBAL_Control
0x18000f310  cmp     rax, rsi
0x18000f313  jz      loc_18000F88F
0x18000f319  mov     dil, 2
0x18000f31c  test    [rax+1Ch], dil
0x18000f320  jz      loc_18000F88F
0x18000f326  cmp     [rax+19h], dil
0x18000f32a  jb      loc_18000F88F
0x18000f330  call    cs:__imp_GetLastError
0x18000f337  nop     dword ptr [rax+rax+00h]
0x18000f33c  mov     edx, 0Eh
0x18000f341  jmp     loc_18000F875
0x18000f346  mov     eax, [rsp+330h+MaximumComponentLength]
0x18000f34a  add     eax, 1Fh
0x18000f34d  lea     ecx, [rax+rax*4]
0x18000f350  shl     ecx, 2
0x18000f353  mov     [r14+68h], ecx
0x18000f357  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000f35b  lea     rcx, [rbp+230h+RootPathName]
0x18000f35f  inc     rax
0x18000f362  cmp     [rcx+rax*2], r12w
0x18000f367  jnz     short loc_18000F35F
0x18000f369  cmp     [rbp+rax*2+230h+var_272], 5Ch ; '\'
0x18000f36f  jnz     short loc_18000F38C
0x18000f371  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x18000f379  cmp     rcx, 212h
0x18000f380  jnb     loc_18000F414
0x18000f386  mov     [rbp+rcx+230h+RootPathName], r12w
0x18000f38c  mov     edi, 3
0x18000f391  mov     [rsp+330h+lpFileSystemNameBuffer], r12; hTemplateFile
0x18000f396  mov     r8d, edi; dwShareMode
0x18000f399  mov     dword ptr [rsp+330h+lpFileSystemFlags], r12d; dwFlagsAndAttributes
0x18000f39e  xor     r9d, r9d; lpSecurityAttributes
0x18000f3a1  mov     dword ptr [rsp+330h+lpMaximumComponentLength], edi; dwCreationDisposition
0x18000f3a5  mov     edx, 80000000h; dwDesiredAccess
0x18000f3aa  lea     rcx, [rbp+230h+RootPathName]; lpFileName
0x18000f3ae  call    cs:__imp_CreateFileW
0x18000f3b5  nop     dword ptr [rax+rax+00h]
0x18000f3ba  lea     r15, [r14+58h]
0x18000f3be  mov     rbx, rax
0x18000f3c1  mov     rcx, r15; this
0x18000f3c4  call    ?Close@AutoHandle@wmi@@QEAAXXZ; wmi::AutoHandle::Close(void)
0x18000f3c9  mov     [r15], rbx
0x18000f3cc  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000f3d0  jnz     short loc_18000F41A
0x18000f3d2  mov     rax, cs:WPP_GLOBAL_Control
0x18000f3d9  lea     rsi, WPP_GLOBAL_Control
0x18000f3e0  cmp     rax, rsi
0x18000f3e3  jz      loc_18000F88F
0x18000f3e9  mov     dil, 2
0x18000f3ec  test    [rax+1Ch], dil
0x18000f3f0  jz      loc_18000F88F
0x18000f3f6  cmp     [rax+19h], dil
0x18000f3fa  jb      loc_18000F88F
0x18000f400  call    cs:__imp_GetLastError
0x18000f407  nop     dword ptr [rax+rax+00h]
0x18000f40c  lea     edx, [rbx+10h]
0x18000f40f  jmp     loc_18000F875
0x18000f414  call    __report_rangecheckfailure
0x18000f41a  mov     rcx, cs:?g_TasksFolderInfo@@3U_TasksFolderInfo@@A; lpFileName
0x18000f421  xor     r9d, r9d; lpSecurityAttributes
0x18000f424  mov     [rsp+330h+lpFileSystemNameBuffer], r12; hTemplateFile
0x18000f429  mov     r8d, edi; dwShareMode
0x18000f42c  mov     dword ptr [rsp+330h+lpFileSystemFlags], 2000001h; dwFlagsAndAttributes
0x18000f434  mov     dword ptr [rsp+330h+lpMaximumComponentLength], edi; dwCreationDisposition
0x18000f438  lea     edx, [r9+1]; dwDesiredAccess
0x18000f43c  call    cs:__imp_CreateFileW
0x18000f443  nop     dword ptr [rax+rax+00h]
0x18000f448  lea     r12, [r14+30h]
0x18000f44c  mov     rbx, rax
0x18000f44f  mov     rcx, r12; this
0x18000f452  call    ?Close@AutoHandle@wmi@@QEAAXXZ; wmi::AutoHandle::Close(void)
0x18000f457  lea     rax, [rbx-1]
0x18000f45b  mov     [r12], rbx
0x18000f45f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000f463  ja      loc_18000F842
0x18000f469  mov     eax, [rsp+330h+MaximumComponentLength]
0x18000f46d  xorps   xmm0, xmm0
0x18000f470  movups  xmmword ptr [rsp+330h+IoStatusBlock], xmm0
0x18000f475  lea     edi, ds:58h[rax*2]
0x18000f47c  mov     ecx, edi; unsigned __int64
0x18000f47e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000f483  mov     rbx, rax
0x18000f486  test    rax, rax
0x18000f489  jnz     short loc_18000F49C
0x18000f48b  xor     ecx, ecx; Block
0x18000f48d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000f492  mov     eax, 8007000Eh
0x18000f497  jmp     loc_18000F8A7
0x18000f49c  mov     rcx, [r12]; FileHandle
0x18000f4a0  lea     rax, [rsp+330h+IoStatusBlock]
0x18000f4a5  mov     [rsp+330h+RestartScan], 0; RestartScan
0x18000f4aa  xor     r9d, r9d; ApcContext
0x18000f4ad  mov     [rsp+330h+FileName], 0; FileName
0x18000f4b6  xor     r8d, r8d; ApcRoutine
0x18000f4b9  mov     [rsp+330h+ReturnSingleEntry], 1; ReturnSingleEntry
0x18000f4be  xor     edx, edx; Event
0x18000f4c0  mov     [rsp+330h+nFileSystemNameSize], 26h ; '&'; FileInformationClass
0x18000f4c8  mov     dword ptr [rsp+330h+lpFileSystemNameBuffer], edi; Length
0x18000f4cc  mov     [rsp+330h+lpFileSystemFlags], rbx; FileInformation
0x18000f4d1  mov     [rsp+330h+lpMaximumComponentLength], rax; IoStatusBlock
0x18000f4d6  call    cs:__imp_NtQueryDirectoryFile
0x18000f4dd  nop     dword ptr [rax+rax+00h]
0x18000f4e2  test    eax, eax
0x18000f4e4  jns     short loc_18000F551
0x18000f4e6  mov     ecx, eax; Status
0x18000f4e8  call    cs:__imp_RtlNtStatusToDosError
0x18000f4ef  nop     dword ptr [rax+rax+00h]
0x18000f4f4  mov     r14d, eax
0x18000f4f7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f4fe  lea     rsi, WPP_GLOBAL_Control
0x18000f505  cmp     rcx, rsi
0x18000f508  jz      short loc_18000F531
0x18000f50a  mov     dil, 2
0x18000f50d  test    [rcx+1Ch], dil
0x18000f511  jz      short loc_18000F531
0x18000f513  cmp     [rcx+19h], dil
0x18000f517  jb      short loc_18000F531
0x18000f519  mov     rcx, [rcx+10h]
0x18000f51d  lea     r8, WPP_880a4eb608c037d792798d7e53d23858_Traceguids
0x18000f524  mov     edx, 11h
0x18000f529  mov     r9d, eax
0x18000f52c  call    WPP_SF_d
0x18000f531  test    r14d, r14d
0x18000f534  jle     short loc_18000F541
0x18000f536  movzx   r14d, r14w
0x18000f53a  or      r14d, 80070000h
0x18000f541  mov     rcx, rbx; Block
0x18000f544  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000f549  mov     eax, r14d
0x18000f54c  jmp     loc_18000F8A7
0x18000f551  mov     rax, [rbx+48h]
0x18000f555  mov     rcx, rbx; Block
0x18000f558  mov     [r14+60h], rax
0x18000f55c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000f561  xor     edx, edx; Val
0x18000f563  lea     rcx, [rbp+230h+OutBuffer]; void *
0x18000f567  lea     r8d, [rdx+40h]; Size
0x18000f56b  call    memset_0
0x18000f570  xor     ebx, ebx
0x18000f572  mov     [rsp+330h+BytesReturned], ebx
0x18000f576  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f57d  lea     rsi, WPP_GLOBAL_Control
0x18000f584  mov     dil, 2
0x18000f587  cmp     rcx, rsi
0x18000f58a  jz      short loc_18000F5AB
0x18000f58c  test    [rcx+1Ch], dil
0x18000f590  jz      short loc_18000F5AB
0x18000f592  cmp     byte ptr [rcx+19h], 4
0x18000f596  jb      short loc_18000F5AB
0x18000f598  mov     rcx, [rcx+10h]
0x18000f59c  lea     edx, [rbx+12h]
0x18000f59f  lea     r8, WPP_880a4eb608c037d792798d7e53d23858_Traceguids
0x18000f5a6  call    WPP_SF_
0x18000f5ab  xor     edx, edx; Val
0x18000f5ad  lea     rcx, [rbp+230h+OutBuffer]; void *
0x18000f5b1  lea     r8d, [rdx+40h]; Size
0x18000f5b5  call    memset_0
0x18000f5ba  mov     rcx, [r15]; hDevice
0x18000f5bd  lea     rax, [rsp+330h+BytesReturned]
0x18000f5c2  mov     qword ptr [rsp+330h+nFileSystemNameSize], rbx; lpOverlapped
0x18000f5c7  xor     r9d, r9d; nInBufferSize
0x18000f5ca  mov     [rsp+330h+lpFileSystemNameBuffer], rax; lpBytesReturned
0x18000f5cf  xor     r8d, r8d; lpInBuffer
0x18000f5d2  lea     rax, [rbp+230h+OutBuffer]
  ... truncated ...
```
