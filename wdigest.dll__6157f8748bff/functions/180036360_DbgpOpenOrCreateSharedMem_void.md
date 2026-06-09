# _DbgpOpenOrCreateSharedMem(void)

- ea: `0x180036360`
- end: `0x180036566`
- name: `?_DbgpOpenOrCreateSharedMem@@YAPEAU_DBG_TCB_HEADER@@XZ`
- size: `518`
- prototype: `struct _DBG_TCB_HEADER *(void)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x180035d38`
- `0x180036570`
- `0x180036874`
- `0x1800369dc`

## callees

- `0x180013304`
- `0x180036310`
- `0x180036360`
- `0x180036720`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800364ed`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800364ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180036549`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180036549`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x1800363c7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x1800363c7`
- `ntdll!NtClose` at `0x18003652d`
- `ntdll!NtClose` at `0x18003652d`
- `ntdll!NtQuerySystemInformation` at `0x1800364e3`
- `ntdll!NtQuerySystemInformation` at `0x1800364e3`
- `ntdll!NtSetEvent` at `0x1800364fb`
- `ntdll!NtSetEvent` at `0x1800364fb`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1800364a1`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1800364a1`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18003653b`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18003653b`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180036451`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180036451`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x1800363dc`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x1800363dc`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x180036407`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x18003647d`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x180036407`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x18003647d`

## pseudocode

```c
struct _DBG_TCB_HEADER *_DbgpOpenOrCreateSharedMem(void)
{
  const WCHAR *TraceMappingName; // rsi
  HANDLE FileMappingW; // rdi
  struct _DBG_TCB_HEADER **v2; // rbx
  HANDLE v3; // rax
  struct _DBG_TCB_HEADER **v4; // rax
  struct _DBG_TCB_HEADER *v5; // rcx
  const WCHAR *v6; // rax
  struct _DBG_TCB_HEADER **v7; // rax
  struct _RTL_CRITICAL_SECTION *v8; // rax
  struct _RTL_CRITICAL_SECTION *v9; // rsi
  struct _SYSTEM_INFO SystemInfo; // [rsp+30h] [rbp-30h] BYREF
  int v12; // [rsp+80h] [rbp+20h] BYREF
  LONG PreviousState; // [rsp+88h] [rbp+28h] BYREF
  HANDLE EventHandle; // [rsp+90h] [rbp+30h] BYREF

  EventHandle = 0;
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  TraceMappingName = _DbgpGetTraceMappingName();
  v12 = 0;
  PreviousState = 0;
  if ( !DbgpGlobalControllerHeader )
  {
    FileMappingW = 0;
    v2 = 0;
    if ( _DbgpWaitForControllerEvent(&v12, &EventHandle) >= 0 )
    {
      GetSystemInfo(&SystemInfo);
      if ( v12 )
      {
        v3 = OpenFileMappingW(0xF001Fu, 0, TraceMappingName);
        FileMappingW = v3;
        if ( v3 )
        {
          v4 = (struct _DBG_TCB_HEADER **)MapViewOfFileEx(v3, 6u, 0, 0, SystemInfo.dwAllocationGranularity, 0);
          v2 = v4;
          if ( v4 )
          {
            v5 = (struct _DBG_TCB_HEADER *)v4;
            if ( v4 != (struct _DBG_TCB_HEADER **)v4[1] )
              v5 = v4[1];
            DbgpGlobalControllerHeader = v5;
          }
        }
      }
      else
      {
        v6 = _DbgpGetTraceMappingName();
        FileMappingW = CreateFileMappingW(
                         (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                         0,
                         0x4000004u,
                         0,
                         SystemInfo.dwAllocationGranularity,
                         v6);
        if ( FileMappingW )
        {
          v7 = (struct _DBG_TCB_HEADER **)MapViewOfFileEx(FileMappingW, 6u, 0, 0, SystemInfo.dwAllocationGranularity, 0);
          v2 = v7;
          if ( v7 )
          {
            v8 = (struct _RTL_CRITICAL_SECTION *)VirtualAlloc(v7, SystemInfo.dwPageSize, 0x1000u, 4u);
            v9 = v8;
            if ( v8 )
            {
              memset_0(v8, 0, 0x80u);
              LODWORD(v9->DebugInfo) = 1819440227;
              *(_QWORD *)&v9->LockCount = v9;
              *(_QWORD *)&v9[1].LockCount = v9 + 1;
              v9[1].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&v9[1];
              NtQuerySystemInformation(SystemKernelDebuggerInformation, &v9[1].OwningThread, 2u, 0);
              InitializeCriticalSection(v9 + 2);
              if ( NtSetEvent(EventHandle, &PreviousState) >= 0 )
              {
                v2 = 0;
                v9->LockSemaphore = EventHandle;
                EventHandle = 0;
                v9->OwningThread = FileMappingW;
                FileMappingW = 0;
                v9[1].SpinCount = 0;
                DbgpGlobalControllerHeader = (struct _DBG_TCB_HEADER *)v9;
              }
            }
          }
        }
      }
    }
    if ( EventHandle )
      NtClose(EventHandle);
    if ( v2 )
      UnmapViewOfFile(v2);
    if ( FileMappingW )
      CloseHandle(FileMappingW);
  }
  return DbgpGlobalControllerHeader;
}

```

## disassembly

```asm
0x180036360  mov     [rsp-18h+arg_18], rbx
0x180036365  push    rbp
0x180036366  push    rsi
0x180036367  push    rdi
0x180036368  mov     rbp, rsp
0x18003636b  sub     rsp, 60h
0x18003636f  xorps   xmm0, xmm0
0x180036372  mov     [rbp+EventHandle], 0
0x18003637a  movups  xmmword ptr [rbp+SystemInfo], xmm0
0x18003637e  movups  xmmword ptr [rbp+SystemInfo.lpMaximumApplicationAddress], xmm0
0x180036382  movups  xmmword ptr [rbp+SystemInfo.dwNumberOfProcessors], xmm0
0x180036386  call    ?_DbgpGetTraceMappingName@@YAPEBGXZ; _DbgpGetTraceMappingName(void)
0x18003638b  cmp     cs:?DbgpGlobalControllerHeader@@3PEAU_DBG_TCB_HEADER@@EA, 0; _DBG_TCB_HEADER * DbgpGlobalControllerHeader
0x180036393  mov     rsi, rax
0x180036396  mov     [rbp+arg_0], 0
0x18003639d  mov     [rbp+PreviousState], 0
0x1800363a4  jnz     loc_18003654F
0x1800363aa  lea     rdx, [rbp+EventHandle]; void **
0x1800363ae  xor     edi, edi
0x1800363b0  lea     rcx, [rbp+arg_0]; int *
0x1800363b4  xor     ebx, ebx
0x1800363b6  call    ?_DbgpWaitForControllerEvent@@YAJPEAHPEAPEAX@Z; _DbgpWaitForControllerEvent(int *,void * *)
0x1800363bb  test    eax, eax
0x1800363bd  js      loc_180036524
0x1800363c3  lea     rcx, [rbp+SystemInfo]; lpSystemInfo
0x1800363c7  call    cs:__imp_GetSystemInfo
0x1800363cd  cmp     [rbp+arg_0], ebx
0x1800363d0  jz      short loc_180036431
0x1800363d2  mov     r8, rsi; lpName
0x1800363d5  xor     edx, edx; bInheritHandle
0x1800363d7  mov     ecx, 0F001Fh; dwDesiredAccess
0x1800363dc  call    cs:__imp_OpenFileMappingW
0x1800363e2  mov     rdi, rax
0x1800363e5  test    rax, rax
0x1800363e8  jz      loc_180036524
0x1800363ee  mov     ecx, [rbp+SystemInfo.dwAllocationGranularity]
0x1800363f1  lea     edx, [rbx+6]; dwDesiredAccess
0x1800363f4  mov     [rsp+60h+lpBaseAddress], rbx; lpBaseAddress
0x1800363f9  xor     r9d, r9d; dwFileOffsetLow
0x1800363fc  mov     [rsp+60h+dwNumberOfBytesToMap], rcx; dwNumberOfBytesToMap
0x180036401  xor     r8d, r8d; dwFileOffsetHigh
0x180036404  mov     rcx, rax; hFileMappingObject
0x180036407  call    cs:__imp_MapViewOfFileEx
0x18003640d  mov     rbx, rax
0x180036410  test    rax, rax
0x180036413  jz      loc_180036524
0x180036419  cmp     rax, [rax+8]
0x18003641d  mov     rcx, rax
0x180036420  cmovnz  rcx, [rax+8]
0x180036425  mov     cs:?DbgpGlobalControllerHeader@@3PEAU_DBG_TCB_HEADER@@EA, rcx; _DBG_TCB_HEADER * DbgpGlobalControllerHeader
0x18003642c  jmp     loc_180036524
0x180036431  call    ?_DbgpGetTraceMappingName@@YAPEBGXZ; _DbgpGetTraceMappingName(void)
0x180036436  mov     [rsp+60h+lpBaseAddress], rax; lpName
0x18003643b  xor     r9d, r9d; dwMaximumSizeHigh
0x18003643e  mov     eax, [rbp+SystemInfo.dwAllocationGranularity]
0x180036441  xor     edx, edx; lpFileMappingAttributes
0x180036443  mov     r8d, 4000004h; flProtect
0x180036449  mov     dword ptr [rsp+60h+dwNumberOfBytesToMap], eax; dwMaximumSizeLow
0x18003644d  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x180036451  call    cs:__imp_CreateFileMappingW
0x180036457  mov     rdi, rax
0x18003645a  test    rax, rax
0x18003645d  jz      loc_180036524
0x180036463  mov     eax, [rbp+SystemInfo.dwAllocationGranularity]
0x180036466  xor     r9d, r9d; dwFileOffsetLow
0x180036469  mov     [rsp+60h+lpBaseAddress], rbx; lpBaseAddress
0x18003646e  xor     r8d, r8d; dwFileOffsetHigh
0x180036471  mov     rcx, rdi; hFileMappingObject
0x180036474  mov     [rsp+60h+dwNumberOfBytesToMap], rax; dwNumberOfBytesToMap
0x180036479  lea     edx, [r9+6]; dwDesiredAccess
0x18003647d  call    cs:__imp_MapViewOfFileEx
0x180036483  mov     rbx, rax
0x180036486  test    rax, rax
0x180036489  jz      loc_180036524
0x18003648f  mov     edx, [rbp+SystemInfo.dwPageSize]; dwSize
0x180036492  mov     r9d, 4; flProtect
0x180036498  mov     r8d, 1000h; flAllocationType
0x18003649e  mov     rcx, rax; lpAddress
0x1800364a1  call    cs:__imp_VirtualAlloc
0x1800364a7  mov     rsi, rax
0x1800364aa  test    rax, rax
0x1800364ad  jz      short loc_180036524
0x1800364af  xor     edx, edx; Val
0x1800364b1  mov     r8d, 80h; Size
0x1800364b7  mov     rcx, rax; void *
0x1800364ba  call    memset_0
0x1800364bf  lea     rcx, [rsi+28h]
0x1800364c3  mov     dword ptr [rsi], 6C727463h
0x1800364c9  xor     r9d, r9d; ReturnLength
0x1800364cc  mov     [rsi+8], rsi
0x1800364d0  mov     [rcx+8], rcx
0x1800364d4  lea     rdx, [rsi+38h]; SystemInformation
0x1800364d8  mov     [rcx], rcx
0x1800364db  lea     ecx, [r9+23h]; SystemInformationClass
0x1800364df  lea     r8d, [r9+2]; SystemInformationLength
0x1800364e3  call    cs:__imp_NtQuerySystemInformation
0x1800364e9  lea     rcx, [rsi+50h]; lpCriticalSection
0x1800364ed  call    cs:__imp_InitializeCriticalSection
0x1800364f3  mov     rcx, [rbp+EventHandle]; EventHandle
0x1800364f7  lea     rdx, [rbp+PreviousState]; PreviousState
0x1800364fb  call    cs:__imp_NtSetEvent
0x180036501  test    eax, eax
0x180036503  js      short loc_180036524
0x180036505  mov     rax, [rbp+EventHandle]
0x180036509  xor     ebx, ebx
0x18003650b  mov     [rsi+18h], rax
0x18003650f  mov     [rbp+EventHandle], rbx
0x180036513  mov     [rsi+10h], rdi
0x180036517  xor     edi, edi
0x180036519  mov     [rsi+48h], rbx
0x18003651d  mov     cs:?DbgpGlobalControllerHeader@@3PEAU_DBG_TCB_HEADER@@EA, rsi; _DBG_TCB_HEADER * DbgpGlobalControllerHeader
0x180036524  mov     rcx, [rbp+EventHandle]; Handle
0x180036528  test    rcx, rcx
0x18003652b  jz      short loc_180036533
0x18003652d  call    cs:__imp_NtClose
0x180036533  test    rbx, rbx
0x180036536  jz      short loc_180036541
0x180036538  mov     rcx, rbx; lpBaseAddress
0x18003653b  call    cs:__imp_UnmapViewOfFile
0x180036541  test    rdi, rdi
0x180036544  jz      short loc_18003654F
0x180036546  mov     rcx, rdi; hObject
0x180036549  call    cs:__imp_CloseHandle
0x18003654f  mov     rax, cs:?DbgpGlobalControllerHeader@@3PEAU_DBG_TCB_HEADER@@EA; _DBG_TCB_HEADER * DbgpGlobalControllerHeader
0x180036556  mov     rbx, [rsp+60h+arg_18]
0x18003655e  add     rsp, 60h
0x180036562  pop     rdi
0x180036563  pop     rsi
0x180036564  pop     rbp
0x180036565  retn
```
