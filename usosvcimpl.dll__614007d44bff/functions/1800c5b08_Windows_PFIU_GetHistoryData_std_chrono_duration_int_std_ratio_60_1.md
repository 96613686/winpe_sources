# Windows::PFIU::GetHistoryData(std::chrono::duration<int,std::ratio<60,1>>)

- ea: `0x1800c5b08`
- end: `0x1800c5ff3`
- name: `?GetHistoryData@PFIU@Windows@@YA?AV?$tuple@V?$unique_ptr@T_PFIU_HISTORY_ENTRY@@Uprocess_heap_deleter@wil@@@wistd@@_KV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@V?$duration@HU?$ratio@$0DM@$00@std@@@45@@std@@V?$duration@HU?$ratio@$0DM@$00@std@@@chrono@4@@Z`
- size: `1259`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800bba40`
- `0x1800bebb4`
- `0x1800bfcb0`

## callees

- `0x180010e80`
- `0x180010f24`
- `0x1800112d0`
- `0x18001b064`
- `0x18002bbc0`
- `0x180063000`
- `0x180063b00`
- `0x1800c5b08`
- `0x1800dd930`
- `0x1800e4630`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800c5cb5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800c5cb5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c5ca7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c5cce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c5ca7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c5cce`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c5cdc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c5cdc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5bb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5bb5`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800c5b98`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800c5b98`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800c5b6d`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800c5b6d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800c5c2c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800c5c8c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800c5ee7`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800c5c2c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800c5c8c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800c5ee7`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x1800c5c62`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x1800c5c62`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1800c5bd0`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1800c5d80`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1800c5dc4`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1800c5e31`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1800c5bd0`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1800c5d80`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1800c5dc4`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1800c5e31`
- `api-ms-win-core-timezone-l1-1-0!TzSpecificLocalTimeToSystemTime` at `0x1800c5f37`
- `api-ms-win-core-timezone-l1-1-0!TzSpecificLocalTimeToSystemTime` at `0x1800c5f37`

## string_xrefs

- `0x1800c5b64`: `ServicesActive`
- `0x1800c5f8c`: `C:\__w\1\s\src\orchestrator\system\windows\common\Time.cpp`
- `0x1800c5fa1`: `C:\__w\1\s\src\orchestrator\system\windows\predictions\PFIUCommon.cpp`
- `0x1800c5fba`: `C:\__w\1\s\src\orchestrator\system\windows\predictions\PFIUCommon.cpp`
- `0x1800c5fcc`: `C:\__w\1\s\src\orchestrator\system\windows\predictions\PFIUCommon.cpp`
- `0x1800c5fe1`: `C:\__w\1\s\src\orchestrator\system\windows\predictions\PFIUCommon.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Windows::PFIU::GetHistoryData(__int64 a1, int a2)
{
  void *v4; // r14
  SC_HANDLE v5; // rax
  SC_HANDLE v6; // rdi
  bool v7; // r12
  SC_HANDLE v8; // rsi
  DWORD LastError; // eax
  unsigned __int64 v10; // rdx
  char v11; // al
  const char *v12; // r9
  unsigned int v13; // esi
  HANDLE ProcessHeap; // rax
  LPVOID v15; // rsi
  const char *v16; // r9
  void *v17; // r13
  HANDLE v18; // rax
  int v19; // eax
  unsigned __int64 v20; // rdx
  char v21; // al
  unsigned __int64 v22; // rdx
  char v23; // al
  unsigned __int64 v24; // rdx
  char v25; // al
  unsigned int pcbBytesNeeded; // [rsp+28h] [rbp-A9h]
  unsigned int v28[4]; // [rsp+48h] [rbp-89h] BYREF
  __int128 v29; // [rsp+58h] [rbp-79h] BYREF
  SC_HANDLE v30; // [rsp+88h] [rbp-49h]
  int v31; // [rsp+A8h] [rbp-29h] BYREF
  SIZE_T dwBytes; // [rsp+ACh] [rbp-25h] BYREF
  __int64 v33; // [rsp+B8h] [rbp-19h] BYREF
  DWORD v34; // [rsp+C0h] [rbp-11h] BYREF
  SYSTEMTIME LocalTime; // [rsp+C8h] [rbp-9h]
  BYTE Buffer[16]; // [rsp+D8h] [rbp+7h] BYREF
  __int128 v37; // [rsp+E8h] [rbp+17h]
  int v38; // [rsp+F8h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+130h] [rbp+5Fh]

  v4 = 0;
  *(_QWORD *)v28 = 0;
  dwBytes = 1;
  v31 = 0;
  LocalTime = 0;
  v5 = OpenSCManagerW(0, L"ServicesActive", 1u);
  v6 = v5;
  v30 = v5;
  v7 = v5 != 0;
  if ( v5 )
  {
    v8 = OpenServiceW(v5, L"Sysmain", 4u);
    *(_QWORD *)&v29 = v8;
    if ( !v8 )
    {
      LastError = GetLastError();
      if ( LastError != 1060 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x34,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\predictions\\PFIUCommon.cpp",
          (const char *)LastError,
          pcbBytesNeeded);
      *(_QWORD *)v28 = 0;
      GetSystemTimePreciseAsFileTime(v28);
      v10 = v28[0] + ((unsigned __int64)v28[1] << 32) - 116444736000000000LL;
      if ( a2 == 60 )
      {
        v11 = 0;
      }
      else
      {
        v11 = -1;
        if ( a2 <= 60 )
          v11 = 1;
      }
      if ( v11 < 0 )
        a2 = 60;
      *(_DWORD *)a1 = a2;
      *(_QWORD *)(a1 + 8) = v10;
      *(_QWORD *)(a1 + 16) = 0;
      *(_QWORD *)(a1 + 24) = 0;
      goto LABEL_47;
    }
    *(_OWORD *)Buffer = 0;
    v37 = 0;
    v38 = 0;
    v34 = 0;
    if ( !QueryServiceStatusEx(v8, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &v34) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x3A,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\predictions\\PFIUCommon.cpp",
        v12);
    if ( ((*(_DWORD *)&Buffer[4] - 1) & 0xFFFFFFFD) == 0 )
    {
      *(_QWORD *)v28 = 0;
      GetSystemTimePreciseAsFileTime(v28);
      v22 = v28[0] + ((unsigned __int64)v28[1] << 32) - 116444736000000000LL;
      if ( a2 == 60 )
      {
        v23 = 0;
      }
      else
      {
        v23 = -1;
        if ( a2 <= 60 )
          v23 = 1;
      }
      if ( v23 < 0 )
        a2 = 60;
      *(_DWORD *)a1 = a2;
      *(_QWORD *)(a1 + 8) = v22;
      *(_QWORD *)(a1 + 16) = 0;
      *(_QWORD *)(a1 + 24) = 0;
      CloseServiceHandle(v8);
      goto LABEL_47;
    }
    CloseServiceHandle(v8);
  }
  v33 = 0;
  Windows::DockedHelpers::GetDockedSystem(&v33);
  do
  {
    v13 = dwBytes;
    ProcessHeap = GetProcessHeap();
    v15 = HeapAlloc(ProcessHeap, 0, v13);
    v17 = v4;
    v4 = v15;
    *(_QWORD *)v28 = v15;
    if ( v17 )
    {
      v18 = GetProcessHeap();
      HeapFree(v18, 0, v17);
    }
    if ( !v15 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x49,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\predictions\\PFIUCommon.cpp",
        v16);
    v19 = (*(__int64 (__fastcall **)(__int64, LPVOID, SIZE_T *, char *))(*(_QWORD *)v33 + 48LL))(
            v33,
            v15,
            &dwBytes,
            (char *)&dwBytes + 4);
    if ( !v19 )
      goto LABEL_23;
  }
  while ( v19 == -2147024774 );
  if ( v19 != -2147024699 && v19 != -2147023888 )
  {
    if ( v19 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x54,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\predictions\\PFIUCommon.cpp",
        (const char *)(unsigned int)v19,
        (int)&v31);
LABEL_23:
    *(_QWORD *)&v29 = L"PFIU minutesPerEntry was <= 0";
    *((_QWORD *)&v29 + 1) = 29;
    SystemInterface::Log<>(&v29);
    *(_QWORD *)v28 = 0;
    GetSystemTimePreciseAsFileTime(v28);
    v20 = v28[0] + ((unsigned __int64)v28[1] << 32) - 116444736000000000LL;
    if ( a2 == 60 )
    {
      v21 = 0;
    }
    else
    {
      v21 = -1;
      if ( a2 <= 60 )
        v21 = 1;
    }
    if ( v21 < 0 )
      a2 = 60;
    *(_DWORD *)a1 = a2;
    *(_QWORD *)(a1 + 8) = v20;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)v28 = 0;
    *(_QWORD *)(a1 + 24) = v15;
    if ( v33 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    goto LABEL_47;
  }
  *(_QWORD *)v28 = 0;
  GetSystemTimePreciseAsFileTime(v28);
  v24 = v28[0] + ((unsigned __int64)v28[1] << 32) - 116444736000000000LL;
  if ( a2 == 60 )
  {
    v25 = 0;
  }
  else
  {
    v25 = -1;
    if ( a2 <= 60 )
      v25 = 1;
  }
  if ( v25 < 0 )
    a2 = 60;
  *(_DWORD *)a1 = a2;
  *(_QWORD *)(a1 + 8) = v24;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)v28 = 0;
  *(_QWORD *)(a1 + 24) = v15;
  if ( v33 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
LABEL_47:
  if ( v7 )
    CloseServiceHandle(v6);
  return a1;
}

```

## disassembly

```asm
0x1800c5b08  mov     rax, rsp
0x1800c5b0b  mov     [rax+10h], rbx
0x1800c5b0f  mov     [rax+18h], rsi
0x1800c5b13  mov     [rax+20h], rdi
0x1800c5b17  push    rbp
0x1800c5b18  push    r12
0x1800c5b1a  push    r13
0x1800c5b1c  push    r14
0x1800c5b1e  push    r15
0x1800c5b20  lea     rbp, [rax-5Fh]
0x1800c5b24  sub     rsp, 100h
0x1800c5b2b  mov     rax, cs:__security_cookie
0x1800c5b32  xor     rax, rsp
0x1800c5b35  mov     [rbp+57h+var_28], rax
0x1800c5b39  mov     ebx, edx
0x1800c5b3b  mov     r15, rcx
0x1800c5b3e  mov     qword ptr [rsp+120h+var_E0], rcx
0x1800c5b43  xor     r14d, r14d
0x1800c5b46  mov     qword ptr [rsp+120h+var_E0], r14
0x1800c5b4b  lea     eax, [r14+1]
0x1800c5b4f  mov     dword ptr [rbp+57h+dwBytes], eax
0x1800c5b52  mov     dword ptr [rbp+57h+dwBytes+4], r14d
0x1800c5b56  mov     [rbp+57h+var_80], r14d
0x1800c5b5a  xorps   xmm0, xmm0
0x1800c5b5d  movups  xmmword ptr [rbp+57h+LocalTime.wYear], xmm0
0x1800c5b61  mov     r8d, eax; dwDesiredAccess
0x1800c5b64  lea     rdx, DatabaseName; "ServicesActive"
0x1800c5b6b  xor     ecx, ecx; lpMachineName
0x1800c5b6d  call    cs:__imp_OpenSCManagerW
0x1800c5b73  mov     rdi, rax
0x1800c5b76  mov     [rbp+57h+var_A0], rax
0x1800c5b7a  test    rax, rax
0x1800c5b7d  setnz   r12b
0x1800c5b81  test    rax, rax
0x1800c5b84  jz      loc_1800C5C92
0x1800c5b8a  lea     r8d, [r14+4]; dwDesiredAccess
0x1800c5b8e  lea     rdx, aSysmain; "Sysmain"
0x1800c5b95  mov     rcx, rax; hSCManager
0x1800c5b98  call    cs:__imp_OpenServiceW
0x1800c5b9e  mov     rsi, rax
0x1800c5ba1  mov     [rbp+57h+var_D0], rax
0x1800c5ba5  test    rax, rax
0x1800c5ba8  setnz   r13b
0x1800c5bac  test    rax, rax
0x1800c5baf  jnz     loc_1800C5C37
0x1800c5bb5  call    cs:__imp_GetLastError
0x1800c5bbb  cmp     eax, 424h
0x1800c5bc0  jnz     loc_1800C5FB3
0x1800c5bc6  mov     qword ptr [rsp+120h+var_E0], rsi
0x1800c5bcb  lea     rcx, [rsp+120h+var_E0]
0x1800c5bd0  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x1800c5bd6  mov     eax, [rsp+120h+var_E0+4]
0x1800c5bda  shl     rax, 20h
0x1800c5bde  mov     ecx, [rsp+120h+var_E0]
0x1800c5be2  mov     rdx, 0FE624E212AC18000h
0x1800c5bec  add     rdx, rax
0x1800c5bef  add     rdx, rcx
0x1800c5bf2  lea     ecx, [rsi+3Ch]
0x1800c5bf5  cmp     ebx, ecx
0x1800c5bf7  jnz     short loc_1800C5BFE
0x1800c5bf9  mov     al, sil
0x1800c5bfc  jmp     short loc_1800C5C0D
0x1800c5bfe  mov     eax, 0FFh
0x1800c5c03  mov     r8d, 1
0x1800c5c09  cmovle  eax, r8d
0x1800c5c0d  test    al, al
0x1800c5c0f  cmovs   ebx, ecx
0x1800c5c12  mov     [r15], ebx
0x1800c5c15  mov     [r15+8], rdx
0x1800c5c19  mov     [r15+10h], rsi
0x1800c5c1d  mov     [r15+18h], rsi
0x1800c5c21  test    r13b, r13b
0x1800c5c24  jz      loc_1800C5EDF
0x1800c5c2a  xor     ecx, ecx; hSCObject
0x1800c5c2c  call    cs:__imp_CloseServiceHandle
0x1800c5c32  jmp     loc_1800C5EDF
0x1800c5c37  xorps   xmm0, xmm0
0x1800c5c3a  xor     eax, eax
0x1800c5c3c  movups  xmmword ptr [rbp+57h+Buffer], xmm0
0x1800c5c40  movups  [rbp+57h+var_40], xmm0
0x1800c5c44  mov     [rbp+57h+var_30], eax
0x1800c5c47  mov     [rbp+57h+var_68], eax
0x1800c5c4a  lea     rax, [rbp+57h+var_68]
0x1800c5c4e  mov     [rsp+120h+pcbBytesNeeded], rax; pcbBytesNeeded
0x1800c5c53  mov     r9d, 24h ; '$'; cbBufSize
0x1800c5c59  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x1800c5c5d  xor     edx, edx; InfoLevel
0x1800c5c5f  mov     rcx, rsi; hService
0x1800c5c62  call    cs:__imp_QueryServiceStatusEx
0x1800c5c68  mov     rcx, [rbp+5Fh]; this
0x1800c5c6c  test    eax, eax
0x1800c5c6e  jz      loc_1800C5FCC
0x1800c5c74  mov     eax, dword ptr [rbp+57h+Buffer+4]
0x1800c5c77  dec     eax
0x1800c5c79  test    eax, 0FFFFFFFDh
0x1800c5c7e  jz      loc_1800C5DB7
0x1800c5c84  test    r13b, r13b
0x1800c5c87  jz      short loc_1800C5C92
0x1800c5c89  mov     rcx, rsi; hSCObject
0x1800c5c8c  call    cs:__imp_CloseServiceHandle
0x1800c5c92  mov     [rbp+57h+var_70], 0
0x1800c5c9a  lea     rcx, [rbp+57h+var_70]
0x1800c5c9e  call    ?GetDockedSystem@DockedHelpers@Windows@@YA?AV?$com_ptr_t@UIDockedSystem@@Uerr_exception_policy@wil@@@wil@@XZ; Windows::DockedHelpers::GetDockedSystem(void)
0x1800c5ca3  nop
0x1800c5ca4  mov     esi, dword ptr [rbp+57h+dwBytes]
0x1800c5ca7  call    cs:__imp_GetProcessHeap
0x1800c5cad  mov     r8d, esi; dwBytes
0x1800c5cb0  xor     edx, edx; dwFlags
0x1800c5cb2  mov     rcx, rax; hHeap
0x1800c5cb5  call    cs:__imp_HeapAlloc
0x1800c5cbb  mov     rsi, rax
0x1800c5cbe  mov     r13, r14
0x1800c5cc1  mov     r14, rax
0x1800c5cc4  mov     qword ptr [rsp+120h+var_E0], rax
0x1800c5cc9  test    r13, r13
0x1800c5ccc  jz      short loc_1800C5CE2
0x1800c5cce  call    cs:__imp_GetProcessHeap
0x1800c5cd4  mov     rcx, rax; hHeap
0x1800c5cd7  mov     r8, r13; lpMem
0x1800c5cda  xor     edx, edx; dwFlags
0x1800c5cdc  call    cs:__imp_HeapFree
0x1800c5ce2  mov     rcx, [rbp+5Fh]; this
0x1800c5ce6  xor     r13d, r13d
0x1800c5ce9  test    rsi, rsi
0x1800c5cec  jz      loc_1800C5FA1
0x1800c5cf2  mov     rcx, [rbp+57h+var_70]
0x1800c5cf6  mov     rax, [rcx]
0x1800c5cf9  lea     rdx, [rbp+57h+LocalTime]
0x1800c5cfd  mov     [rsp+120h+var_F8], rdx
0x1800c5d02  lea     rdx, [rbp+57h+var_80]
0x1800c5d06  mov     [rsp+120h+pcbBytesNeeded], rdx; int
0x1800c5d0b  lea     r9, [rbp+57h+dwBytes+4]
0x1800c5d0f  lea     r8, [rbp+57h+dwBytes]
0x1800c5d13  mov     rdx, rsi
0x1800c5d16  mov     rax, [rax+30h]
0x1800c5d1a  call    _guard_dispatch_icall
0x1800c5d1f  test    eax, eax
0x1800c5d21  jz      short loc_1800C5D50
0x1800c5d23  cmp     eax, 8007007Ah
0x1800c5d28  jz      loc_1800C5CA4
0x1800c5d2e  cmp     eax, 800700C5h
0x1800c5d33  jz      loc_1800C5E27
0x1800c5d39  cmp     eax, 800703F0h
0x1800c5d3e  jz      loc_1800C5E27
0x1800c5d44  mov     rcx, [rbp+5Fh]; this
0x1800c5d48  test    eax, eax
0x1800c5d4a  js      loc_1800C5FDE
0x1800c5d50  cmp     [rbp+57h+var_80], r13d
0x1800c5d54  ja      loc_1800C5F1E
0x1800c5d5a  lea     rax, aPfiuMinutesper_0; "PFIU minutesPerEntry was <= 0"
0x1800c5d61  mov     [rbp+57h+var_D0], rax
0x1800c5d65  mov     [rbp+57h+var_C8], 1Dh
0x1800c5d6d  lea     rcx, [rbp+57h+var_D0]
0x1800c5d71  call    ??$Log@$$V@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; SystemInterface::Log<>(std::wstring_view)
0x1800c5d76  mov     qword ptr [rsp+120h+var_E0], r13
0x1800c5d7b  lea     rcx, [rsp+120h+var_E0]
0x1800c5d80  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x1800c5d86  mov     eax, [rsp+120h+var_E0+4]
0x1800c5d8a  shl     rax, 20h
0x1800c5d8e  mov     ecx, [rsp+120h+var_E0]
0x1800c5d92  mov     rdx, 0FE624E212AC18000h
0x1800c5d9c  add     rdx, rax
0x1800c5d9f  add     rdx, rcx
0x1800c5da2  mov     ecx, 3Ch ; '<'
0x1800c5da7  cmp     ebx, ecx
0x1800c5da9  jnz     loc_1800C5EA1
0x1800c5daf  mov     al, r13b
0x1800c5db2  jmp     loc_1800C5EB0
0x1800c5db7  xor     r14d, r14d
0x1800c5dba  mov     qword ptr [rsp+120h+var_E0], r14
0x1800c5dbf  lea     rcx, [rsp+120h+var_E0]
0x1800c5dc4  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x1800c5dca  mov     eax, [rsp+120h+var_E0+4]
0x1800c5dce  shl     rax, 20h
0x1800c5dd2  mov     ecx, [rsp+120h+var_E0]
0x1800c5dd6  mov     rdx, 0FE624E212AC18000h
0x1800c5de0  add     rdx, rax
0x1800c5de3  add     rdx, rcx
0x1800c5de6  lea     ecx, [r14+3Ch]
0x1800c5dea  cmp     ebx, ecx
0x1800c5dec  jnz     short loc_1800C5DF3
0x1800c5dee  mov     al, r14b
0x1800c5df1  jmp     short loc_1800C5E02
0x1800c5df3  mov     eax, 0FFh
0x1800c5df8  mov     r8d, 1
0x1800c5dfe  cmovle  eax, r8d
0x1800c5e02  test    al, al
0x1800c5e04  cmovs   ebx, ecx
0x1800c5e07  mov     [r15], ebx
0x1800c5e0a  mov     [r15+8], rdx
0x1800c5e0e  mov     [r15+10h], r14
0x1800c5e12  mov     [r15+18h], r14
0x1800c5e16  test    r13b, r13b
0x1800c5e19  jz      loc_1800C5EDF
0x1800c5e1f  mov     rcx, rsi
0x1800c5e22  jmp     loc_1800C5C2C
0x1800c5e27  mov     qword ptr [rsp+120h+var_E0], r13
0x1800c5e2c  lea     rcx, [rsp+120h+var_E0]
0x1800c5e31  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x1800c5e37  mov     eax, [rsp+120h+var_E0+4]
0x1800c5e3b  shl     rax, 20h
0x1800c5e3f  mov     ecx, [rsp+120h+var_E0]
0x1800c5e43  mov     rdx, 0FE624E212AC18000h
0x1800c5e4d  add     rdx, rax
0x1800c5e50  add     rdx, rcx
0x1800c5e53  mov     ecx, 3Ch ; '<'
0x1800c5e58  cmp     ebx, ecx
0x1800c5e5a  jnz     short loc_1800C5E61
0x1800c5e5c  mov     al, r13b
0x1800c5e5f  jmp     short loc_1800C5E70
0x1800c5e61  mov     eax, 0FFh
0x1800c5e66  mov     r8d, 1
0x1800c5e6c  cmovle  eax, r8d
0x1800c5e70  test    al, al
0x1800c5e72  cmovs   ebx, ecx
0x1800c5e75  mov     [r15], ebx
0x1800c5e78  mov     [r15+8], rdx
0x1800c5e7c  mov     [r15+10h], r13
0x1800c5e80  mov     qword ptr [rsp+120h+var_E0], r13
0x1800c5e85  mov     [r15+18h], rsi
0x1800c5e89  mov     rcx, [rbp+57h+var_70]
0x1800c5e8d  test    rcx, rcx
0x1800c5e90  jz      short loc_1800C5E9F
0x1800c5e92  mov     rax, [rcx]
0x1800c5e95  mov     rax, [rax+10h]
0x1800c5e99  call    _guard_dispatch_icall
0x1800c5e9e  nop
0x1800c5e9f  jmp     short loc_1800C5EDF
0x1800c5ea1  mov     eax, 0FFh
0x1800c5ea6  mov     r8d, 1
0x1800c5eac  cmovle  eax, r8d
0x1800c5eb0  test    al, al
0x1800c5eb2  cmovs   ebx, ecx
0x1800c5eb5  mov     [r15], ebx
0x1800c5eb8  mov     [r15+8], rdx
0x1800c5ebc  mov     [r15+10h], r13
0x1800c5ec0  mov     qword ptr [rsp+120h+var_E0], r13
0x1800c5ec5  mov     [r15+18h], rsi
0x1800c5ec9  mov     rcx, [rbp+57h+var_70]
0x1800c5ecd  test    rcx, rcx
0x1800c5ed0  jz      short loc_1800C5EDF
0x1800c5ed2  mov     rax, [rcx]
0x1800c5ed5  mov     rax, [rax+10h]
0x1800c5ed9  call    _guard_dispatch_icall
0x1800c5ede  nop
0x1800c5edf  test    r12b, r12b
0x1800c5ee2  jz      short loc_1800C5EEE
0x1800c5ee4  mov     rcx, rdi; hSCObject
0x1800c5ee7  call    cs:__imp_CloseServiceHandle
0x1800c5eed  nop
0x1800c5eee  mov     rax, r15
0x1800c5ef1  mov     rcx, [rbp+57h+var_28]
0x1800c5ef5  xor     rcx, rsp; StackCookie
0x1800c5ef8  call    __security_check_cookie
0x1800c5efd  lea     r11, [rsp+120h+var_20]
0x1800c5f05  mov     rbx, [r11+38h]
0x1800c5f09  mov     rsi, [r11+40h]
0x1800c5f0d  mov     rdi, [r11+48h]
0x1800c5f11  mov     rsp, r11
0x1800c5f14  pop     r15
0x1800c5f16  pop     r14
0x1800c5f18  pop     r13
0x1800c5f1a  pop     r12
0x1800c5f1c  pop     rbp
0x1800c5f1d  retn
0x1800c5f1e  mov     r14d, dword ptr [rbp+57h+dwBytes+4]
0x1800c5f22  xorps   xmm0, xmm0
0x1800c5f25  movups  xmmword ptr [rbp+57h+UniversalTime.wYear], xmm0
0x1800c5f29  mov     rbx, [rbp+5Fh]
0x1800c5f2d  lea     r8, [rbp+57h+UniversalTime]; lpUniversalTime
0x1800c5f31  lea     rdx, [rbp+57h+LocalTime]; lpLocalTime
0x1800c5f35  xor     ecx, ecx; lpTimeZoneInformation
0x1800c5f37  call    cs:__imp_TzSpecificLocalTimeToSystemTime
0x1800c5f3d  test    eax, eax
0x1800c5f3f  jz      short loc_1800C5F8C
0x1800c5f41  movaps  xmm0, xmmword ptr [rbp+57h+UniversalTime.wYear]
0x1800c5f45  movdqa  [rbp+57h+var_90], xmm0
0x1800c5f4a  lea     rdx, [rbp+57h+var_90]
0x1800c5f4e  lea     rcx, [rbp+57h+var_D0]
0x1800c5f52  call    ?from_systemtime@Time@Windows@@YA?AV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@AEBU_SYSTEMTIME@@@Z; Windows::Time::from_systemtime(_SYSTEMTIME const &)
0x1800c5f57  mov     ecx, [rbp+57h+var_80]
0x1800c5f5a  mov     [r15], ecx
0x1800c5f5d  mov     rax, [rax]
0x1800c5f60  mov     [r15+8], rax
0x1800c5f64  mov     [r15+10h], r14
0x1800c5f68  mov     qword ptr [rsp+120h+var_E0], r13
0x1800c5f6d  mov     [r15+18h], rsi
0x1800c5f71  mov     rcx, [rbp+57h+var_70]
0x1800c5f75  test    rcx, rcx
0x1800c5f78  jz      short loc_1800C5F87
0x1800c5f7a  mov     rax, [rcx]
0x1800c5f7d  mov     rax, [rax+10h]
0x1800c5f81  call    _guard_dispatch_icall
0x1800c5f86  nop
0x1800c5f87  jmp     loc_1800C5EDF
0x1800c5f8c  lea     r8, aCW1SSrcOrchest_41; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1800c5f93  mov     edx, 4Dh ; 'M'; void *
0x1800c5f98  mov     rcx, rbx; this
0x1800c5f9b  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800c5fa1  lea     r8, aCW1SSrcOrchest_8; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
  ... truncated ...
```
