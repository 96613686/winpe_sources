# StorageUsage::FindNextStorageTypeEx(_DATA_TYPE_NODE,ushort const *,ushort * *,unsigned __int64 *,unsigned __int64 *,bool)

- ea: `0x1800389c4`
- end: `0x180038d81`
- name: `?FindNextStorageTypeEx@StorageUsage@@QEAAJW4_DATA_TYPE_NODE@@PEBGPEAPEAGPEA_K3_N@Z`
- size: `957`
- prototype: `int __fastcall(__int64, __int64, const WCHAR *, HLOCAL *, _QWORD *, _QWORD *)`
- caller_count: `3`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180037410`
- `0x180037490`
- `0x1800374c0`

## callees

- `0x180003998`
- `0x18000d030`
- `0x180019210`
- `0x180030ab0`
- `0x1800386f0`
- `0x1800388b4`
- `0x1800389c4`
- `0x180038d88`
- `0x180039ff8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180038bb1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180038bb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038d07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038d07`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180038ad2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180038ad2`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180038d3c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180038d3c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180038c9d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180038c9d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038d2d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038d2d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180038bc7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180038bc7`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180038c08`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180038c08`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x180038c18`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x180038c18`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180038bd5`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180038bd5`
- `api-ms-win-core-datetime-l1-1-1!GetDateFormatEx` at `0x180038c55`
- `api-ms-win-core-datetime-l1-1-1!GetDateFormatEx` at `0x180038ccc`
- `api-ms-win-core-datetime-l1-1-1!GetDateFormatEx` at `0x180038c55`
- `api-ms-win-core-datetime-l1-1-1!GetDateFormatEx` at `0x180038ccc`
- `api-ms-win-core-datetime-l1-1-1!GetTimeFormatEx` at `0x180038c80`
- `api-ms-win-core-datetime-l1-1-1!GetTimeFormatEx` at `0x180038cfd`
- `api-ms-win-core-datetime-l1-1-1!GetTimeFormatEx` at `0x180038c80`
- `api-ms-win-core-datetime-l1-1-1!GetTimeFormatEx` at `0x180038cfd`
- `RPCRT4!RpcImpersonateClient` at `0x180038c20`
- `RPCRT4!RpcImpersonateClient` at `0x180038c20`

## string_xrefs

- `0x180038d51`: `onecore\drivers\storage\storsvc\service\storageusageclient.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
int __fastcall StorageUsage::FindNextStorageTypeEx(
        __int64 a1,
        __int64 a2,
        const WCHAR *a3,
        HLOCAL *a4,
        _QWORD *a5,
        _QWORD *a6)
{
  unsigned int v8; // r12d
  __int64 v10; // r9
  __int64 v11; // rdx
  int Value; // ebx
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // rcx
  int DirectorySizeUsingNode; // eax
  int v18; // r8d
  int v19; // r9d
  int v20; // ebx
  __int64 v21; // rdi
  __int64 v22; // rax
  __int64 v23; // r8
  int DateFormat; // eax
  __int64 cchDate; // rsi
  int TimeFormat; // eax
  int v27; // r14d
  WCHAR *v28; // rax
  signed int LastError; // eax
  unsigned int bIgnoreCase; // [rsp+20h] [rbp-81h]
  bool v32; // [rsp+40h] [rbp-61h] BYREF
  char v33; // [rsp+41h] [rbp-60h]
  __int64 v34; // [rsp+48h] [rbp-59h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+50h] [rbp-51h] BYREF
  struct _FILETIME FileTime; // [rsp+58h] [rbp-49h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+60h] [rbp-41h] BYREF
  __int128 v38; // [rsp+70h] [rbp-31h]
  SYSTEMTIME UniversalTime; // [rsp+80h] [rbp-21h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+47h]

  v8 = a2;
  v34 = 0;
  *(_QWORD *)&UniversalTime.wYear = 0;
  FileTime = 0;
  if ( !a5 || !a6 )
  {
    v10 = 87;
    v11 = 958;
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v11,
             (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storageusageclient.cpp",
             (const char *)v10,
             bIgnoreCase);
  }
  if ( (int)a2 < 34 )
  {
    v33 = 0;
    if ( a4 )
      *a4 = 0;
    if ( !*(_BYTE *)(a1 + 64) )
    {
      SystemTime = 0;
      v38 = 0;
      Value = StorageUsageCache::GetValue(
                *(_QWORD *)(a1 + 112),
                a2,
                *(unsigned int *)(a1 + 56),
                *(unsigned int *)(a1 + 60),
                &SystemTime);
      if ( Value >= 0 && (_BYTE)v38 )
      {
        v13 = *(_QWORD *)&SystemTime.wYear;
        if ( *(_QWORD *)&SystemTime.wYear == -1 )
        {
          Value = -2147023728;
          goto LABEL_38;
        }
        v14 = *(_QWORD *)&SystemTime.wHour;
        FileTime = *(struct _FILETIME *)((char *)&v38 + 4);
        goto LABEL_27;
      }
      if ( *(_BYTE *)(a1 + 65) )
      {
        Value = 0;
        *a5 = 0;
        *a6 = 0;
        return Value;
      }
    }
    if ( a3 && CompareStringOrdinal(a3, -1, L"ScanProgress", -1, 1) == 2 )
    {
      DirectorySizeUsingNode = StorageUsage::GetDirectorySizeUsingNode(
                                 v16,
                                 v15,
                                 v8,
                                 *(_QWORD *)(a1 + 24),
                                 &v34,
                                 &UniversalTime);
      v20 = DirectorySizeUsingNode;
      v21 = v34;
      if ( (unsigned int)dword_1800BF000 > 5 )
      {
        LODWORD(lpCriticalSection) = DirectorySizeUsingNode;
        *(_QWORD *)&SystemTime.wYear = v34;
        LODWORD(v34) = v8;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
          dword_1800BF000,
          (unsigned int)byte_1800A813B,
          v18,
          v19,
          (__int64)&v34,
          (__int64)&SystemTime,
          (__int64)&lpCriticalSection);
      }
      if ( v20 < 0 )
      {
        *a5 = 0;
        v22 = 0;
      }
      else
      {
        *a5 = v21;
        v22 = *(_QWORD *)&UniversalTime.wYear;
      }
      *a6 = v22;
      return 0;
    }
    SystemTime = 0;
    v32 = 0;
    StorageUsage::EnsureDirectoryScan((StorageUsage *)a1, &v32);
    Microsoft::WRL::Wrappers::CriticalSection::Lock(a1 + 72, &lpCriticalSection);
    LOBYTE(v23) = v32;
    Value = StorageUsage::CalculateStorageType(a1, v8, v23, &v34, &UniversalTime);
    if ( lpCriticalSection )
    {
      LeaveCriticalSection(lpCriticalSection);
      lpCriticalSection = 0;
    }
    if ( Value < 0 )
    {
LABEL_38:
      if ( !a4 )
        goto LABEL_41;
      goto LABEL_39;
    }
    GetSystemTime(&SystemTime);
    SystemTimeToFileTime(&SystemTime, &FileTime);
    v13 = v34;
    v14 = *(_QWORD *)&UniversalTime.wYear;
LABEL_27:
    *a5 = v13;
    *a6 = v14;
    if ( !a4 )
      return Value;
    UniversalTime = 0;
    SystemTime = 0;
    FileTimeToSystemTime(&FileTime, &UniversalTime);
    SystemTimeToTzSpecificLocalTime(0, &UniversalTime, &SystemTime);
    Value = RpcImpersonateClient(0);
    if ( Value < 0 )
      goto LABEL_39;
    v33 = 1;
    DateFormat = GetDateFormatEx(0, 1u, &SystemTime, 0, 0, 0, 0);
    cchDate = DateFormat;
    if ( DateFormat )
    {
      TimeFormat = GetTimeFormatEx(0, 2u, &SystemTime, 0, 0, 0);
      v27 = TimeFormat;
      if ( TimeFormat )
      {
        v28 = (WCHAR *)LocalAlloc(0x40u, 2LL * (TimeFormat + (int)cchDate + 1));
        *a4 = v28;
        if ( !v28 )
        {
          Value = -2147024882;
LABEL_39:
          if ( *a4 )
          {
            LocalFree(*a4);
            *a4 = 0;
          }
          goto LABEL_41;
        }
        if ( GetDateFormatEx(0, 1u, &SystemTime, 0, v28, cchDate, 0) )
        {
          *((_WORD *)*a4 + cchDate - 1) = 32;
          if ( GetTimeFormatEx(0, 2u, &SystemTime, 0, (LPWSTR)*a4 + cchDate, v27) )
            goto LABEL_42;
        }
      }
    }
    LastError = GetLastError();
    Value = LastError;
    if ( LastError > 0 )
      Value = (unsigned __int16)LastError | 0x80070000;
    if ( Value >= 0 )
    {
LABEL_41:
      if ( v33 )
LABEL_42:
        RevertToSelf();
      return Value;
    }
    goto LABEL_38;
  }
  v10 = 259;
  v11 = 963;
  return wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v11,
           (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storageusageclient.cpp",
           (const char *)v10,
           bIgnoreCase);
}

```

## disassembly

```asm
0x1800389c4  push    rbp
0x1800389c6  push    rbx
0x1800389c7  push    rsi
0x1800389c8  push    rdi
0x1800389c9  push    r12
0x1800389cb  push    r13
0x1800389cd  push    r14
0x1800389cf  push    r15
0x1800389d1  lea     rbp, [rsp-7]
0x1800389d6  sub     rsp, 0A8h
0x1800389dd  mov     rax, cs:__security_cookie
0x1800389e4  xor     rax, rsp
0x1800389e7  mov     [rbp+3Fh+var_50], rax
0x1800389eb  mov     rdi, r9
0x1800389ee  mov     r13, r8
0x1800389f1  mov     r12d, edx
0x1800389f4  mov     rsi, rcx
0x1800389f7  mov     r14, [rbp+3Fh+arg_20]
0x1800389fb  mov     r15, [rbp+3Fh+arg_28]
0x1800389ff  xor     eax, eax
0x180038a01  mov     [rbp+3Fh+var_98], rax
0x180038a05  mov     qword ptr [rbp+3Fh+UniversalTime.wYear], rax
0x180038a09  mov     qword ptr [rbp+3Fh+FileTime.dwLowDateTime], rax
0x180038a0d  test    r14, r14
0x180038a10  jz      loc_180038D46
0x180038a16  test    r15, r15
0x180038a19  jz      loc_180038D46
0x180038a1f  cmp     edx, 22h ; '"'
0x180038a22  jl      short loc_180038A34
0x180038a24  mov     r9d, 103h
0x180038a2a  mov     edx, 3C3h
0x180038a2f  jmp     loc_180038D51
0x180038a34  mov     [rbp+3Fh+var_9F], al
0x180038a37  test    rdi, rdi
0x180038a3a  jz      short loc_180038A3F
0x180038a3c  mov     [r9], rax
0x180038a3f  cmp     [rcx+40h], al
0x180038a42  jnz     short loc_180038AB0
0x180038a44  xorps   xmm0, xmm0
0x180038a47  movups  xmmword ptr [rbp+3Fh+SystemTime.wYear], xmm0
0x180038a4b  movups  [rbp+3Fh+var_70], xmm0
0x180038a4f  lea     rax, [rbp+3Fh+SystemTime]
0x180038a53  mov     qword ptr [rsp+0E0h+bIgnoreCase], rax
0x180038a58  mov     r9d, [rcx+3Ch]
0x180038a5c  mov     r8d, [rcx+38h]
0x180038a60  mov     rcx, [rcx+70h]
0x180038a64  call    ?GetValue@StorageUsageCache@@QEAAJW4_DATA_TYPE_NODE@@KKPEAU_STORAGE_TYPE_CACHE_VALUES@@@Z; StorageUsageCache::GetValue(_DATA_TYPE_NODE,ulong,ulong,_STORAGE_TYPE_CACHE_VALUES *)
0x180038a69  mov     ebx, eax
0x180038a6b  xor     eax, eax
0x180038a6d  test    ebx, ebx
0x180038a6f  js      short loc_180038A9E
0x180038a71  cmp     byte ptr [rbp+3Fh+var_70], al
0x180038a74  jz      short loc_180038A9E
0x180038a76  mov     rcx, qword ptr [rbp+3Fh+SystemTime.wYear]
0x180038a7a  xor     r13d, r13d
0x180038a7d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180038a81  jnz     short loc_180038A8D
0x180038a83  mov     ebx, 80070490h
0x180038a88  jmp     loc_180038D20
0x180038a8d  mov     rdx, qword ptr [rbp+3Fh+SystemTime.wHour]
0x180038a91  mov     rax, qword ptr [rbp+3Fh+var_70+4]
0x180038a95  mov     qword ptr [rbp+3Fh+FileTime.dwLowDateTime], rax
0x180038a99  jmp     loc_180038BE3
0x180038a9e  cmp     [rsi+41h], al
0x180038aa1  jz      short loc_180038AB0
0x180038aa3  mov     ebx, eax
0x180038aa5  mov     [r14], rax
0x180038aa8  mov     [r15], rax
0x180038aab  jmp     loc_180038D42
0x180038ab0  test    r13, r13
0x180038ab3  jz      loc_180038B62
0x180038ab9  mov     [rsp+0E0h+bIgnoreCase], 1; bIgnoreCase
0x180038ac1  or      r9d, 0FFFFFFFFh; cchCount2
0x180038ac5  lea     r8, aScanprogress; "ScanProgress"
0x180038acc  or      edx, r9d; cchCount1
0x180038acf  mov     rcx, r13; lpString1
0x180038ad2  call    cs:__imp_CompareStringOrdinal
0x180038ad8  cmp     eax, 2
0x180038adb  jnz     loc_180038B62
0x180038ae1  lea     rax, [rbp+3Fh+UniversalTime]
0x180038ae5  mov     qword ptr [rsp+0E0h+cchDate], rax
0x180038aea  lea     rax, [rbp+3Fh+var_98]
0x180038aee  mov     qword ptr [rsp+0E0h+bIgnoreCase], rax
0x180038af3  mov     r9, [rsi+18h]
0x180038af7  mov     r8d, r12d
0x180038afa  call    ?GetDirectorySizeUsingNode@StorageUsage@@QEAAJKW4_DATA_TYPE_NODE@@PEAVCTreeWalker@@PEA_K2@Z; StorageUsage::GetDirectorySizeUsingNode(ulong,_DATA_TYPE_NODE,CTreeWalker *,unsigned __int64 *,unsigned __int64 *)
0x180038aff  mov     ebx, eax
0x180038b01  mov     ecx, cs:dword_1800BF000
0x180038b07  mov     rdi, [rbp+3Fh+var_98]
0x180038b0b  cmp     ecx, 5
0x180038b0e  jbe     short loc_180038B42
0x180038b10  mov     dword ptr [rbp+3Fh+lpCriticalSection], eax
0x180038b13  mov     qword ptr [rbp+3Fh+SystemTime.wYear], rdi
0x180038b17  mov     dword ptr [rbp+3Fh+var_98], r12d
0x180038b1b  lea     rax, [rbp+3Fh+lpCriticalSection]
0x180038b1f  mov     [rsp+0E0h+lpCalendar], rax
0x180038b24  lea     rax, [rbp+3Fh+SystemTime]
0x180038b28  mov     qword ptr [rsp+0E0h+cchDate], rax
0x180038b2d  lea     rax, [rbp+3Fh+var_98]
0x180038b31  mov     qword ptr [rsp+0E0h+bIgnoreCase], rax
0x180038b36  lea     rdx, byte_1800A813B
0x180038b3d  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180038b42  test    ebx, ebx
0x180038b44  js      short loc_180038B4F
0x180038b46  mov     [r14], rdi
0x180038b49  mov     rax, qword ptr [rbp+3Fh+UniversalTime.wYear]
0x180038b4d  jmp     short loc_180038B58
0x180038b4f  mov     qword ptr [r14], 0
0x180038b56  xor     eax, eax
0x180038b58  mov     [r15], rax
0x180038b5b  xor     ebx, ebx
0x180038b5d  jmp     loc_180038D42
0x180038b62  xorps   xmm0, xmm0
0x180038b65  movups  xmmword ptr [rbp+3Fh+SystemTime.wYear], xmm0
0x180038b69  xor     r13d, r13d
0x180038b6c  mov     [rbp+3Fh+var_A0], r13b
0x180038b70  lea     rdx, [rbp+3Fh+var_A0]; bool *
0x180038b74  mov     rcx, rsi; this
0x180038b77  call    ?EnsureDirectoryScan@StorageUsage@@QEAAXPEA_N@Z; StorageUsage::EnsureDirectoryScan(bool *)
0x180038b7c  lea     rcx, [rsi+48h]
0x180038b80  lea     rdx, [rbp+3Fh+lpCriticalSection]
0x180038b84  call    ?Lock@CriticalSection@Wrappers@WRL@Microsoft@@QEAA?AVSyncLockCriticalSection@Details@234@XZ; Microsoft::WRL::Wrappers::CriticalSection::Lock(void)
0x180038b89  nop
0x180038b8a  lea     rax, [rbp+3Fh+UniversalTime]
0x180038b8e  mov     qword ptr [rsp+0E0h+bIgnoreCase], rax
0x180038b93  lea     r9, [rbp+3Fh+var_98]
0x180038b97  mov     r8b, [rbp+3Fh+var_A0]
0x180038b9b  mov     edx, r12d
0x180038b9e  mov     rcx, rsi
0x180038ba1  call    ?CalculateStorageType@StorageUsage@@QEAAJW4_DATA_TYPE_NODE@@_NPEA_K2@Z; StorageUsage::CalculateStorageType(_DATA_TYPE_NODE,bool,unsigned __int64 *,unsigned __int64 *)
0x180038ba6  mov     ebx, eax
0x180038ba8  mov     rcx, [rbp+3Fh+lpCriticalSection]; lpCriticalSection
0x180038bac  test    rcx, rcx
0x180038baf  jz      short loc_180038BBB
0x180038bb1  call    cs:__imp_LeaveCriticalSection
0x180038bb7  mov     [rbp+3Fh+lpCriticalSection], r13
0x180038bbb  test    ebx, ebx
0x180038bbd  js      loc_180038D20
0x180038bc3  lea     rcx, [rbp+3Fh+SystemTime]; lpSystemTime
0x180038bc7  call    cs:__imp_GetSystemTime
0x180038bcd  lea     rdx, [rbp+3Fh+FileTime]; lpFileTime
0x180038bd1  lea     rcx, [rbp+3Fh+SystemTime]; lpSystemTime
0x180038bd5  call    cs:__imp_SystemTimeToFileTime
0x180038bdb  mov     rcx, [rbp+3Fh+var_98]
0x180038bdf  mov     rdx, qword ptr [rbp+3Fh+UniversalTime.wYear]
0x180038be3  mov     [r14], rcx
0x180038be6  mov     [r15], rdx
0x180038be9  test    rdi, rdi
0x180038bec  jz      loc_180038D42
0x180038bf2  xorps   xmm0, xmm0
0x180038bf5  movups  xmmword ptr [rbp+3Fh+UniversalTime.wYear], xmm0
0x180038bf9  xorps   xmm1, xmm1
0x180038bfc  movups  xmmword ptr [rbp+3Fh+SystemTime.wYear], xmm1
0x180038c00  lea     rdx, [rbp+3Fh+UniversalTime]; lpSystemTime
0x180038c04  lea     rcx, [rbp+3Fh+FileTime]; lpFileTime
0x180038c08  call    cs:__imp_FileTimeToSystemTime
0x180038c0e  lea     r8, [rbp+3Fh+SystemTime]; lpLocalTime
0x180038c12  lea     rdx, [rbp+3Fh+UniversalTime]; lpUniversalTime
0x180038c16  xor     ecx, ecx; lpTimeZoneInformation
0x180038c18  call    cs:__imp_SystemTimeToTzSpecificLocalTime
0x180038c1e  xor     ecx, ecx; BindingHandle
0x180038c20  call    cs:__imp_RpcImpersonateClient
0x180038c26  mov     ebx, eax
0x180038c28  test    eax, eax
0x180038c2a  js      loc_180038D25
0x180038c30  mov     r15d, 1
0x180038c36  mov     [rbp+3Fh+var_9F], r15b
0x180038c3a  mov     [rsp+0E0h+lpCalendar], r13; lpCalendar
0x180038c3f  mov     [rsp+0E0h+cchDate], r13d; cchDate
0x180038c44  mov     qword ptr [rsp+0E0h+bIgnoreCase], r13; lpDateStr
0x180038c49  xor     r9d, r9d; lpFormat
0x180038c4c  lea     r8, [rbp+3Fh+SystemTime]; lpDate
0x180038c50  mov     edx, r15d; dwFlags
0x180038c53  xor     ecx, ecx; lpLocaleName
0x180038c55  call    cs:__imp_GetDateFormatEx
0x180038c5b  movsxd  rsi, eax
0x180038c5e  test    eax, eax
0x180038c60  jz      loc_180038D07
0x180038c66  mov     [rsp+0E0h+cchDate], r13d; cchTime
0x180038c6b  mov     qword ptr [rsp+0E0h+bIgnoreCase], r13; lpTimeStr
0x180038c70  xor     r9d, r9d; lpFormat
0x180038c73  lea     r8, [rbp+3Fh+SystemTime]; lpTime
0x180038c77  lea     r12d, [r15+1]
0x180038c7b  mov     edx, r12d; dwFlags
0x180038c7e  xor     ecx, ecx; lpLocaleName
0x180038c80  call    cs:__imp_GetTimeFormatEx
0x180038c86  mov     r14d, eax
0x180038c89  test    eax, eax
0x180038c8b  jz      short loc_180038D07
0x180038c8d  lea     eax, [rsi+1]
0x180038c90  add     eax, r14d
0x180038c93  movsxd  rdx, eax
0x180038c96  add     rdx, rdx; uBytes
0x180038c99  lea     ecx, [r15+3Fh]; uFlags
0x180038c9d  call    cs:__imp_LocalAlloc
0x180038ca3  mov     [rdi], rax
0x180038ca6  test    rax, rax
0x180038ca9  jnz     short loc_180038CB2
0x180038cab  mov     ebx, 8007000Eh
0x180038cb0  jmp     short loc_180038D25
0x180038cb2  mov     [rsp+0E0h+lpCalendar], r13; lpCalendar
0x180038cb7  mov     [rsp+0E0h+cchDate], esi; cchDate
0x180038cbb  mov     qword ptr [rsp+0E0h+bIgnoreCase], rax; lpDateStr
0x180038cc0  xor     r9d, r9d; lpFormat
0x180038cc3  lea     r8, [rbp+3Fh+SystemTime]; lpDate
0x180038cc7  mov     edx, r15d; dwFlags
0x180038cca  xor     ecx, ecx; lpLocaleName
0x180038ccc  call    cs:__imp_GetDateFormatEx
0x180038cd2  test    eax, eax
0x180038cd4  jz      short loc_180038D07
0x180038cd6  mov     rax, [rdi]
0x180038cd9  mov     word ptr [rax+rsi*2-2], 20h ; ' '
0x180038ce0  mov     rax, [rdi]
0x180038ce3  lea     rcx, [rax+rsi*2]
0x180038ce7  mov     [rsp+0E0h+cchDate], r14d; cchTime
0x180038cec  mov     qword ptr [rsp+0E0h+bIgnoreCase], rcx; lpTimeStr
0x180038cf1  xor     r9d, r9d; lpFormat
0x180038cf4  lea     r8, [rbp+3Fh+SystemTime]; lpTime
0x180038cf8  mov     edx, r12d; dwFlags
0x180038cfb  xor     ecx, ecx; lpLocaleName
0x180038cfd  call    cs:__imp_GetTimeFormatEx
0x180038d03  test    eax, eax
0x180038d05  jnz     short loc_180038D3C
0x180038d07  call    cs:__imp_GetLastError
0x180038d0d  test    eax, eax
0x180038d0f  mov     ebx, eax
0x180038d11  jle     short loc_180038D1C
0x180038d13  movzx   ebx, ax
0x180038d16  or      ebx, 80070000h
0x180038d1c  test    ebx, ebx
0x180038d1e  jns     short loc_180038D36
0x180038d20  test    rdi, rdi
0x180038d23  jz      short loc_180038D36
0x180038d25  mov     rcx, [rdi]; hMem
0x180038d28  test    rcx, rcx
0x180038d2b  jz      short loc_180038D36
0x180038d2d  call    cs:__imp_LocalFree
0x180038d33  mov     [rdi], r13
0x180038d36  cmp     [rbp+3Fh+var_9F], r13b
0x180038d3a  jz      short loc_180038D42
0x180038d3c  call    cs:__imp_RevertToSelf
0x180038d42  mov     eax, ebx
0x180038d44  jmp     short loc_180038D61
0x180038d46  mov     r9d, 57h ; 'W'; char *
0x180038d4c  mov     edx, 3BEh; void *
0x180038d51  lea     r8, aOnecoreDrivers_11; "onecore\\drivers\\storage\\storsvc\\ser"...
0x180038d58  mov     rcx, [rbp+47h]; this
0x180038d5c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180038d61  mov     rcx, [rbp+3Fh+var_50]
0x180038d65  xor     rcx, rsp; StackCookie
0x180038d68  call    __security_check_cookie
0x180038d6d  add     rsp, 0A8h
0x180038d74  pop     r15
0x180038d76  pop     r14
0x180038d78  pop     r13
0x180038d7a  pop     r12
0x180038d7c  pop     rdi
0x180038d7d  pop     rsi
0x180038d7e  pop     rbx
0x180038d7f  pop     rbp
0x180038d80  retn
```
