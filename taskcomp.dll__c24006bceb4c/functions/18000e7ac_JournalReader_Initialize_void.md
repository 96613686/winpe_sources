# JournalReader::_Initialize(void)

- ea: `0x18000e7ac`
- end: `0x18000ef33`
- name: `?_Initialize@JournalReader@@AEAAJXZ`
- size: `1927`
- prototype: `signed int __fastcall(JournalReader *this)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x180011308`

## callees

- `0x180004e1c`
- `0x180004f88`
- `0x1800074c8`
- `0x1800074d4`
- `0x180008538`
- `0x18000c760`
- `0x18000e7ac`
- `0x18000f2dc`
- `0x18000fbb8`
- `0x18002e572`
- `0x18002e5b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000e7ea`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000e7ea`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x18000e856`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x18000e8b9`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x18000e856`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x18000e8b9`
- `ntdll!NtQueryDirectoryFile` at `0x18000eb84`
- `ntdll!NtQueryDirectoryFile` at `0x18000eb84`
- `ntdll!RtlNtStatusToDosError` at `0x18000eb90`
- `ntdll!RtlNtStatusToDosError` at `0x18000eb90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e839`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e89f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e902`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e984`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e9f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eaba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ec98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ed81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eeaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eed9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eefe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e839`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e89f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e902`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e984`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e9f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eaba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ec98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ed81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eeaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eed9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eefe`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000ea6e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000eaf0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000ee69`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000ea6e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000eaf0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000ee69`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18000e94c`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18000e94c`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x18000e9be`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x18000e9be`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000ec8a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000ed10`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000ed77`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000ec8a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000ed10`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000ed77`

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
0x18000e7ac  push    rbp
0x18000e7ae  push    rbx
0x18000e7af  push    rsi
0x18000e7b0  push    rdi
0x18000e7b1  push    r12
0x18000e7b3  push    r13
0x18000e7b5  push    r14
0x18000e7b7  push    r15
0x18000e7b9  lea     rbp, [rsp-1F8h]
0x18000e7c1  sub     rsp, 2F8h
0x18000e7c8  mov     rax, cs:__security_cookie
0x18000e7cf  xor     rax, rsp
0x18000e7d2  mov     [rbp+230h+var_50], rax
0x18000e7d9  mov     r14, cs:?s_pReader@JournalReader@@0PEAV1@EA; JournalReader * JournalReader::s_pReader
0x18000e7e0  xor     r9d, r9d; lpName
0x18000e7e3  xor     r8d, r8d; bInitialState
0x18000e7e6  xor     edx, edx; bManualReset
0x18000e7e8  xor     ecx, ecx; lpEventAttributes
0x18000e7ea  call    cs:__imp_CreateEventW
0x18000e7f0  lea     r13, [r14+8]
0x18000e7f4  mov     rbx, rax
0x18000e7f7  mov     rcx, r13; this
0x18000e7fa  call    ?Close@AutoHandle@wmi@@QEAAXXZ; wmi::AutoHandle::Close(void)
0x18000e7ff  xor     r12d, r12d
0x18000e802  mov     [r13+0], rbx
0x18000e806  test    rbx, rbx
0x18000e809  jnz     short loc_18000E847
0x18000e80b  mov     rax, cs:WPP_GLOBAL_Control
0x18000e812  lea     rsi, WPP_GLOBAL_Control
0x18000e819  cmp     rax, rsi
0x18000e81c  jz      loc_18000EEFE
0x18000e822  mov     dil, 2
0x18000e825  test    [rax+1Ch], dil
0x18000e829  jz      loc_18000EEFE
0x18000e82f  cmp     [rax+19h], dil
0x18000e833  jb      loc_18000EEFE
0x18000e839  call    cs:__imp_GetLastError
0x18000e83f  lea     edx, [rbx+0Ah]
0x18000e842  jmp     loc_18000EEE4
0x18000e847  mov     esi, 1F0003h
0x18000e84c  xor     r8d, r8d; dwFlags
0x18000e84f  mov     r9d, esi; dwDesiredAccess
0x18000e852  xor     edx, edx; lpTimerName
0x18000e854  xor     ecx, ecx; lpTimerAttributes
0x18000e856  call    cs:__imp_CreateWaitableTimerExW
0x18000e85c  lea     rcx, [r14+40h]; this
0x18000e860  mov     rdi, rax
0x18000e863  call    ?Close@AutoHandle@wmi@@QEAAXXZ; wmi::AutoHandle::Close(void)
0x18000e868  mov     [r14+40h], rdi
0x18000e86c  test    rdi, rdi
0x18000e86f  jnz     short loc_18000E8AF
0x18000e871  mov     rax, cs:WPP_GLOBAL_Control
0x18000e878  lea     rsi, WPP_GLOBAL_Control
0x18000e87f  cmp     rax, rsi
0x18000e882  jz      loc_18000EEFE
0x18000e888  mov     dil, 2
0x18000e88b  test    [rax+1Ch], dil
0x18000e88f  jz      loc_18000EEFE
0x18000e895  cmp     [rax+19h], dil
0x18000e899  jb      loc_18000EEFE
0x18000e89f  call    cs:__imp_GetLastError
0x18000e8a5  mov     edx, 0Bh
0x18000e8aa  jmp     loc_18000EEE4
0x18000e8af  mov     r9d, esi; dwDesiredAccess
0x18000e8b2  xor     r8d, r8d; dwFlags
0x18000e8b5  xor     edx, edx; lpTimerName
0x18000e8b7  xor     ecx, ecx; lpTimerAttributes
0x18000e8b9  call    cs:__imp_CreateWaitableTimerExW
0x18000e8bf  lea     rcx, [r14+48h]; this
0x18000e8c3  mov     rdi, rax
0x18000e8c6  call    ?Close@AutoHandle@wmi@@QEAAXXZ; wmi::AutoHandle::Close(void)
0x18000e8cb  mov     [r14+48h], rdi
0x18000e8cf  test    rdi, rdi
0x18000e8d2  jnz     short loc_18000E912
0x18000e8d4  mov     rax, cs:WPP_GLOBAL_Control
0x18000e8db  lea     rsi, WPP_GLOBAL_Control
0x18000e8e2  cmp     rax, rsi
0x18000e8e5  jz      loc_18000EEFE
0x18000e8eb  mov     dil, 2
0x18000e8ee  test    [rax+1Ch], dil
0x18000e8f2  jz      loc_18000EEFE
0x18000e8f8  cmp     [rax+19h], dil
0x18000e8fc  jb      loc_18000EEFE
0x18000e902  call    cs:__imp_GetLastError
0x18000e908  mov     edx, 0Ch
0x18000e90d  jmp     loc_18000EEE4
0x18000e912  movsd   xmm0, qword ptr cs:asc_1800508D8; "\\\\.\\"
0x18000e91a  lea     rcx, [rbp+230h+var_266]; void *
0x18000e91e  movzx   eax, word ptr cs:asc_1800508D8+8; ""
0x18000e925  xor     edx, edx; Val
0x18000e927  mov     r8d, 208h; Size
0x18000e92d  movsd   qword ptr [rbp+230h+RootPathName], xmm0
0x18000e932  mov     [rbp+230h+szVolumePathName], ax
0x18000e936  call    memset_0
0x18000e93b  mov     rcx, cs:?g_TasksFolderInfo@@3U_TasksFolderInfo@@A; lpszFileName
0x18000e942  lea     rdx, [rbp+230h+szVolumePathName]; lpszVolumePathName
0x18000e946  mov     r8d, 105h; cchBufferLength
0x18000e94c  call    cs:__imp_GetVolumePathNameW
0x18000e952  test    eax, eax
0x18000e954  jnz     short loc_18000E994
0x18000e956  mov     rax, cs:WPP_GLOBAL_Control
0x18000e95d  lea     rsi, WPP_GLOBAL_Control
0x18000e964  cmp     rax, rsi
0x18000e967  jz      loc_18000EEFE
0x18000e96d  mov     dil, 2
0x18000e970  test    [rax+1Ch], dil
0x18000e974  jz      loc_18000EEFE
0x18000e97a  cmp     [rax+19h], dil
0x18000e97e  jb      loc_18000EEFE
0x18000e984  call    cs:__imp_GetLastError
0x18000e98a  mov     edx, 0Dh
0x18000e98f  jmp     loc_18000EEE4
0x18000e994  mov     [rsp+330h+nFileSystemNameSize], r12d; nFileSystemNameSize
0x18000e999  lea     rax, [rsp+330h+MaximumComponentLength]
0x18000e99e  mov     [rsp+330h+lpFileSystemNameBuffer], r12; lpFileSystemNameBuffer
0x18000e9a3  lea     rcx, [rbp+230h+RootPathName]; lpRootPathName
0x18000e9a7  mov     [rsp+330h+lpFileSystemFlags], r12; lpFileSystemFlags
0x18000e9ac  xor     r9d, r9d; lpVolumeSerialNumber
0x18000e9af  xor     r8d, r8d; nVolumeNameSize
0x18000e9b2  mov     [rsp+330h+lpMaximumComponentLength], rax; lpMaximumComponentLength
0x18000e9b7  xor     edx, edx; lpVolumeNameBuffer
0x18000e9b9  mov     [rsp+330h+MaximumComponentLength], r12d
0x18000e9be  call    cs:__imp_GetVolumeInformationW
0x18000e9c4  test    eax, eax
0x18000e9c6  jnz     short loc_18000EA06
0x18000e9c8  mov     rax, cs:WPP_GLOBAL_Control
0x18000e9cf  lea     rsi, WPP_GLOBAL_Control
0x18000e9d6  cmp     rax, rsi
0x18000e9d9  jz      loc_18000EEFE
0x18000e9df  mov     dil, 2
0x18000e9e2  test    [rax+1Ch], dil
0x18000e9e6  jz      loc_18000EEFE
0x18000e9ec  cmp     [rax+19h], dil
0x18000e9f0  jb      loc_18000EEFE
0x18000e9f6  call    cs:__imp_GetLastError
0x18000e9fc  mov     edx, 0Eh
0x18000ea01  jmp     loc_18000EEE4
0x18000ea06  mov     eax, [rsp+330h+MaximumComponentLength]
0x18000ea0a  add     eax, 1Fh
0x18000ea0d  lea     ecx, [rax+rax*4]
0x18000ea10  shl     ecx, 2
0x18000ea13  mov     [r14+68h], ecx
0x18000ea17  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000ea1b  lea     rcx, [rbp+230h+RootPathName]
0x18000ea1f  inc     rax
0x18000ea22  cmp     [rcx+rax*2], r12w
0x18000ea27  jnz     short loc_18000EA1F
0x18000ea29  cmp     [rbp+rax*2+230h+var_272], 5Ch ; '\'
0x18000ea2f  jnz     short loc_18000EA4C
0x18000ea31  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x18000ea39  cmp     rcx, 212h
0x18000ea40  jnb     loc_18000EAC8
0x18000ea46  mov     [rbp+rcx+230h+RootPathName], r12w
0x18000ea4c  mov     edi, 3
0x18000ea51  mov     [rsp+330h+lpFileSystemNameBuffer], r12; hTemplateFile
0x18000ea56  mov     r8d, edi; dwShareMode
0x18000ea59  mov     dword ptr [rsp+330h+lpFileSystemFlags], r12d; dwFlagsAndAttributes
0x18000ea5e  xor     r9d, r9d; lpSecurityAttributes
0x18000ea61  mov     dword ptr [rsp+330h+lpMaximumComponentLength], edi; dwCreationDisposition
0x18000ea65  mov     edx, 80000000h; dwDesiredAccess
0x18000ea6a  lea     rcx, [rbp+230h+RootPathName]; lpFileName
0x18000ea6e  call    cs:__imp_CreateFileW
0x18000ea74  lea     r15, [r14+58h]
0x18000ea78  mov     rbx, rax
0x18000ea7b  mov     rcx, r15; this
0x18000ea7e  call    ?Close@AutoHandle@wmi@@QEAAXXZ; wmi::AutoHandle::Close(void)
0x18000ea83  mov     [r15], rbx
0x18000ea86  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000ea8a  jnz     short loc_18000EACE
0x18000ea8c  mov     rax, cs:WPP_GLOBAL_Control
0x18000ea93  lea     rsi, WPP_GLOBAL_Control
0x18000ea9a  cmp     rax, rsi
0x18000ea9d  jz      loc_18000EEFE
0x18000eaa3  mov     dil, 2
0x18000eaa6  test    [rax+1Ch], dil
0x18000eaaa  jz      loc_18000EEFE
0x18000eab0  cmp     [rax+19h], dil
0x18000eab4  jb      loc_18000EEFE
0x18000eaba  call    cs:__imp_GetLastError
0x18000eac0  lea     edx, [rbx+10h]
0x18000eac3  jmp     loc_18000EEE4
0x18000eac8  call    __report_rangecheckfailure
0x18000eace  mov     rcx, cs:?g_TasksFolderInfo@@3U_TasksFolderInfo@@A; lpFileName
0x18000ead5  xor     r9d, r9d; lpSecurityAttributes
0x18000ead8  mov     [rsp+330h+lpFileSystemNameBuffer], r12; hTemplateFile
0x18000eadd  mov     r8d, edi; dwShareMode
0x18000eae0  mov     dword ptr [rsp+330h+lpFileSystemFlags], 2000001h; dwFlagsAndAttributes
0x18000eae8  mov     dword ptr [rsp+330h+lpMaximumComponentLength], edi; dwCreationDisposition
0x18000eaec  lea     edx, [r9+1]; dwDesiredAccess
0x18000eaf0  call    cs:__imp_CreateFileW
0x18000eaf6  lea     r12, [r14+30h]
0x18000eafa  mov     rbx, rax
0x18000eafd  mov     rcx, r12; this
0x18000eb00  call    ?Close@AutoHandle@wmi@@QEAAXXZ; wmi::AutoHandle::Close(void)
0x18000eb05  lea     rax, [rbx-1]
0x18000eb09  mov     [r12], rbx
0x18000eb0d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000eb11  ja      loc_18000EEB7
0x18000eb17  mov     eax, [rsp+330h+MaximumComponentLength]
0x18000eb1b  xorps   xmm0, xmm0
0x18000eb1e  movups  xmmword ptr [rsp+330h+IoStatusBlock], xmm0
0x18000eb23  lea     edi, ds:58h[rax*2]
0x18000eb2a  mov     ecx, edi; unsigned __int64
0x18000eb2c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000eb31  mov     rbx, rax
0x18000eb34  test    rax, rax
0x18000eb37  jnz     short loc_18000EB4A
0x18000eb39  xor     ecx, ecx; Block
0x18000eb3b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000eb40  mov     eax, 8007000Eh
0x18000eb45  jmp     loc_18000EF10
0x18000eb4a  mov     rcx, [r12]; FileHandle
0x18000eb4e  lea     rax, [rsp+330h+IoStatusBlock]
0x18000eb53  mov     [rsp+330h+RestartScan], 0; RestartScan
0x18000eb58  xor     r9d, r9d; ApcContext
0x18000eb5b  mov     [rsp+330h+FileName], 0; FileName
0x18000eb64  xor     r8d, r8d; ApcRoutine
0x18000eb67  mov     [rsp+330h+ReturnSingleEntry], 1; ReturnSingleEntry
0x18000eb6c  xor     edx, edx; Event
0x18000eb6e  mov     [rsp+330h+nFileSystemNameSize], 26h ; '&'; FileInformationClass
0x18000eb76  mov     dword ptr [rsp+330h+lpFileSystemNameBuffer], edi; Length
0x18000eb7a  mov     [rsp+330h+lpFileSystemFlags], rbx; FileInformation
0x18000eb7f  mov     [rsp+330h+lpMaximumComponentLength], rax; IoStatusBlock
0x18000eb84  call    cs:__imp_NtQueryDirectoryFile
0x18000eb8a  test    eax, eax
0x18000eb8c  jns     short loc_18000EBF3
0x18000eb8e  mov     ecx, eax; Status
0x18000eb90  call    cs:__imp_RtlNtStatusToDosError
0x18000eb96  mov     r14d, eax
0x18000eb99  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eba0  lea     rsi, WPP_GLOBAL_Control
0x18000eba7  cmp     rcx, rsi
0x18000ebaa  jz      short loc_18000EBD3
0x18000ebac  mov     dil, 2
0x18000ebaf  test    [rcx+1Ch], dil
0x18000ebb3  jz      short loc_18000EBD3
0x18000ebb5  cmp     [rcx+19h], dil
0x18000ebb9  jb      short loc_18000EBD3
0x18000ebbb  mov     rcx, [rcx+10h]
0x18000ebbf  lea     r8, WPP_880a4eb608c037d792798d7e53d23858_Traceguids
0x18000ebc6  mov     edx, 11h
0x18000ebcb  mov     r9d, eax
0x18000ebce  call    WPP_SF_d
0x18000ebd3  test    r14d, r14d
0x18000ebd6  jle     short loc_18000EBE3
0x18000ebd8  movzx   r14d, r14w
0x18000ebdc  or      r14d, 80070000h
0x18000ebe3  mov     rcx, rbx; Block
0x18000ebe6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ebeb  mov     eax, r14d
0x18000ebee  jmp     loc_18000EF10
0x18000ebf3  mov     rax, [rbx+48h]
0x18000ebf7  mov     rcx, rbx; Block
0x18000ebfa  mov     [r14+60h], rax
0x18000ebfe  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ec03  xor     edx, edx; Val
0x18000ec05  lea     rcx, [rbp+230h+OutBuffer]; void *
0x18000ec09  lea     r8d, [rdx+40h]; Size
0x18000ec0d  call    memset_0
0x18000ec12  xor     ebx, ebx
0x18000ec14  mov     [rsp+330h+BytesReturned], ebx
0x18000ec18  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ec1f  lea     rsi, WPP_GLOBAL_Control
0x18000ec26  mov     dil, 2
0x18000ec29  cmp     rcx, rsi
0x18000ec2c  jz      short loc_18000EC4D
0x18000ec2e  test    [rcx+1Ch], dil
0x18000ec32  jz      short loc_18000EC4D
0x18000ec34  cmp     byte ptr [rcx+19h], 4
0x18000ec38  jb      short loc_18000EC4D
0x18000ec3a  mov     rcx, [rcx+10h]
0x18000ec3e  lea     edx, [rbx+12h]
0x18000ec41  lea     r8, WPP_880a4eb608c037d792798d7e53d23858_Traceguids
0x18000ec48  call    WPP_SF_
0x18000ec4d  xor     edx, edx; Val
0x18000ec4f  lea     rcx, [rbp+230h+OutBuffer]; void *
0x18000ec53  lea     r8d, [rdx+40h]; Size
0x18000ec57  call    memset_0
0x18000ec5c  mov     rcx, [r15]; hDevice
0x18000ec5f  lea     rax, [rsp+330h+BytesReturned]
0x18000ec64  mov     qword ptr [rsp+330h+nFileSystemNameSize], rbx; lpOverlapped
0x18000ec69  xor     r9d, r9d; nInBufferSize
0x18000ec6c  mov     [rsp+330h+lpFileSystemNameBuffer], rax; lpBytesReturned
0x18000ec71  xor     r8d, r8d; lpInBuffer
0x18000ec74  lea     rax, [rbp+230h+OutBuffer]
0x18000ec78  mov     dword ptr [rsp+330h+lpFileSystemFlags], 40h ; '@'; nOutBufferSize
0x18000ec80  mov     edx, 900F4h; dwIoControlCode
0x18000ec85  mov     [rsp+330h+lpMaximumComponentLength], rax; lpOutBuffer
0x18000ec8a  call    cs:__imp_DeviceIoControl
0x18000ec90  test    eax, eax
0x18000ec92  jnz     loc_18000EDCD
0x18000ec98  call    cs:__imp_GetLastError
0x18000ec9e  mov     ebx, eax
0x18000eca0  cmp     ax, 49Bh
0x18000eca4  jnz     loc_18000ED89
0x18000ecaa  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ecb1  cmp     rcx, rsi
0x18000ecb4  jz      short loc_18000ECD7
0x18000ecb6  test    [rcx+1Ch], dil
0x18000ecba  jz      short loc_18000ECD7
  ... truncated ...
```
