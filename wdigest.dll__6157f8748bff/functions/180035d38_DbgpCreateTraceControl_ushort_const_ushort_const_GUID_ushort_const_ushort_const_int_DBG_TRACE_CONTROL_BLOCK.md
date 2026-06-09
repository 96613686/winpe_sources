# _DbgpCreateTraceControl(ushort const *,ushort const *,_GUID *,ushort const *,ushort const *,int,_DBG_TRACE_CONTROL_BLOCK * *)

- ea: `0x180035d38`
- end: `0x180035fbf`
- name: `?_DbgpCreateTraceControl@@YAHPEBG0PEAU_GUID@@00HPEAPEAU_DBG_TRACE_CONTROL_BLOCK@@@Z`
- size: `647`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, struct _GUID *, const unsigned __int16 *, const unsigned __int16 *, int, struct _DBG_TRACE_CONTROL_BLOCK **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800369dc`

## callees

- `0x180012880`
- `0x180013304`
- `0x180035d38`
- `0x180035fc8`
- `0x180036360`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180035e25`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180035e25`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180035e3f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180035e3f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180035da8`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180035da8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180035f39`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180035f39`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035ef1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035ef1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035f0e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035f0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035f8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035f8b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180035e98`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180035e98`
- `ntdll!RtlAllocateHeap` at `0x180035d7e`
- `ntdll!RtlAllocateHeap` at `0x180035d7e`
- `ntdll!NtQuerySystemTime` at `0x180035f7e`
- `ntdll!NtQuerySystemTime` at `0x180035f7e`
- `ntdll!RtlNtStatusToDosError` at `0x180035e09`
- `ntdll!RtlNtStatusToDosError` at `0x180035e09`
- `ntdll!RtlDuplicateUnicodeString` at `0x180035dfd`
- `ntdll!RtlDuplicateUnicodeString` at `0x180035e6b`
- `ntdll!RtlDuplicateUnicodeString` at `0x180035dfd`
- `ntdll!RtlDuplicateUnicodeString` at `0x180035e6b`
- `ntdll!RtlInitUnicodeString` at `0x180035dc8`
- `ntdll!RtlInitUnicodeString` at `0x180035e57`
- `ntdll!RtlInitUnicodeString` at `0x180035eb6`
- `ntdll!RtlInitUnicodeString` at `0x180035dc8`
- `ntdll!RtlInitUnicodeString` at `0x180035e57`
- `ntdll!RtlInitUnicodeString` at `0x180035eb6`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180035f68`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180035f68`

## string_xrefs

- `0x180035e8a`: `System\CurrentControlSet\Control\SecurityProviders\WDigest`
- `0x180035e16`: `wdigest.dll`

## pseudocode

```c
_BOOL8 __fastcall _DbgpCreateTraceControl(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        struct _GUID *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        int a6,
        struct _DBG_TRACE_CONTROL_BLOCK **a7)
{
  char *Heap; // rax
  char *v8; // rdi
  LSTATUS v9; // ebx
  int v10; // eax
  ULONG LastError; // eax
  HMODULE ModuleHandleW; // rax
  struct _RTL_CRITICAL_SECTION *SharedMem; // rax
  struct _RTL_CRITICAL_SECTION *v14; // rsi
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rdx
  HANDLE EventW; // rax
  __int64 v17; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-258h] BYREF
  WCHAR Filename[264]; // [rsp+40h] [rbp-248h] BYREF

  DestinationString = 0;
  Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0xF0u);
  v8 = Heap;
  if ( Heap )
  {
    memset_0(Heap, 0, 0xF0u);
    InitializeCriticalSection((LPCRITICAL_SECTION)(v8 + 192));
    *((_DWORD *)v8 + 4) = 1937339236;
    *((_DWORD *)v8 + 5) = 1819440227;
    RtlInitUnicodeString(&DestinationString, L"wdigest");
    if ( (DestinationString.Length & 0xFFFEu) >= 0x104 )
    {
      v9 = 87;
LABEL_20:
      _DbgpDeleteTraceControl((struct _DBG_TRACE_CONTROL_BLOCK *)v8);
      return v9 == 0;
    }
    v10 = RtlDuplicateUnicodeString(3u, &DestinationString, (PUNICODE_STRING)(v8 + 56));
    if ( v10 < 0 )
      goto LABEL_6;
    Filename[260] = 0;
    ModuleHandleW = GetModuleHandleW(L"wdigest.dll");
    if ( ModuleHandleW && GetModuleFileNameW(ModuleHandleW, Filename, 0x104u) )
    {
      RtlInitUnicodeString(&DestinationString, Filename);
      v10 = RtlDuplicateUnicodeString(3u, &DestinationString, (PUNICODE_STRING)(v8 + 40));
      if ( v10 < 0 )
      {
LABEL_6:
        LastError = RtlNtStatusToDosError(v10);
LABEL_19:
        v9 = LastError;
        goto LABEL_20;
      }
      v9 = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"System\\CurrentControlSet\\Control\\SecurityProviders\\WDigest",
             0,
             0x2000000u,
             (PHKEY)v8 + 21);
      if ( v9 )
        goto LABEL_20;
      RtlInitUnicodeString((PUNICODE_STRING)v8 + 11, L"Debuglevel");
      *((_QWORD *)v8 + 18) = _DbgpTraceControllerTimerCallback;
      *((_OWORD *)v8 + 7) = DigestGlobalDebugTraceControlGuid;
      SharedMem = (struct _RTL_CRITICAL_SECTION *)_DbgpOpenOrCreateSharedMem();
      v14 = SharedMem;
      if ( !SharedMem )
      {
        v9 = 1168;
        goto LABEL_20;
      }
      EnterCriticalSection(SharedMem + 2);
      DebugInfo = v14[3].DebugInfo;
      v14[3].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)((char *)&DebugInfo->Type + 1);
      *((_QWORD *)v8 + 29) = DebugInfo;
      LeaveCriticalSection(v14 + 2);
      if ( LOBYTE(v14[1].OwningThread) )
        *((_DWORD *)v8 + 8) = 3;
      *((_QWORD *)v8 + 17) = _DbgpTraceTimerCallback;
      EventW = CreateEventW(0, 0, 0, 0);
      *((_QWORD *)v8 + 19) = EventW;
      if ( EventW )
      {
        v17 = RegisterWaitForSingleObjectEx(
                EventW,
                _DbgpRegistryChangeNotifycationCallback,
                *((_QWORD *)v8 + 29),
                0xFFFFFFFFLL,
                128);
        *((_QWORD *)v8 + 20) = v17;
        if ( v17 )
        {
          NtQuerySystemTime((PLARGE_INTEGER)v8 + 3);
          v9 = 0;
          *a7 = (struct _DBG_TRACE_CONTROL_BLOCK *)v8;
          return v9 == 0;
        }
      }
    }
    LastError = GetLastError();
    goto LABEL_19;
  }
  v9 = 14;
  return v9 == 0;
}

```

## disassembly

```asm
0x180035d38  push    rbx
0x180035d3a  push    rsi
0x180035d3b  push    rdi
0x180035d3c  push    r14
0x180035d3e  sub     rsp, 268h
0x180035d45  mov     rax, cs:__security_cookie
0x180035d4c  xor     rax, rsp
0x180035d4f  mov     [rsp+288h+var_38], rax
0x180035d57  mov     r14, [rsp+288h+arg_30]
0x180035d5f  xorps   xmm0, xmm0
0x180035d62  movups  xmmword ptr [rsp+288h+DestinationString.Length], xmm0
0x180035d67  mov     rcx, gs:60h
0x180035d70  mov     ebx, 0F0h
0x180035d75  mov     r8d, ebx; Size
0x180035d78  xor     edx, edx; Flags
0x180035d7a  mov     rcx, [rcx+30h]; HeapHandle
0x180035d7e  call    cs:__imp_RtlAllocateHeap
0x180035d84  mov     rdi, rax
0x180035d87  test    rax, rax
0x180035d8a  jnz     short loc_180035D94
0x180035d8c  lea     ebx, [rax+0Eh]
0x180035d8f  jmp     loc_180035F9B
0x180035d94  mov     r8, rbx; Size
0x180035d97  xor     edx, edx; Val
0x180035d99  mov     rcx, rdi; void *
0x180035d9c  call    memset_0
0x180035da1  lea     rcx, [rdi+0C0h]; lpCriticalSection
0x180035da8  call    cs:__imp_InitializeCriticalSection
0x180035dae  lea     rdx, aWdigest_0; "wdigest"
0x180035db5  mov     dword ptr [rdi+10h], 73797364h
0x180035dbc  lea     rcx, [rsp+288h+DestinationString]; DestinationString
0x180035dc1  mov     dword ptr [rdi+14h], 6C727463h
0x180035dc8  call    cs:__imp_RtlInitUnicodeString
0x180035dce  movzx   eax, [rsp+288h+DestinationString.Length]
0x180035dd3  mov     ecx, 0FFFEh
0x180035dd8  and     ax, cx
0x180035ddb  mov     ebx, 104h
0x180035de0  cmp     ax, bx
0x180035de3  jb      short loc_180035DEF
0x180035de5  mov     ebx, 57h ; 'W'
0x180035dea  jmp     loc_180035F93
0x180035def  lea     r8, [rdi+38h]; DestinationString
0x180035df3  mov     ecx, 3; Flags
0x180035df8  lea     rdx, [rsp+288h+DestinationString]; SourceString
0x180035dfd  call    cs:__imp_RtlDuplicateUnicodeString
0x180035e03  test    eax, eax
0x180035e05  jns     short loc_180035E14
0x180035e07  mov     ecx, eax; Status
0x180035e09  call    cs:__imp_RtlNtStatusToDosError
0x180035e0f  jmp     loc_180035F91
0x180035e14  xor     eax, eax
0x180035e16  lea     rcx, aWdigestDll_0; "wdigest.dll"
0x180035e1d  mov     [rsp+288h+var_40], ax
0x180035e25  call    cs:__imp_GetModuleHandleW
0x180035e2b  test    rax, rax
0x180035e2e  jz      loc_180035F8B
0x180035e34  mov     r8d, ebx; nSize
0x180035e37  lea     rdx, [rsp+288h+Filename]; lpFilename
0x180035e3c  mov     rcx, rax; hModule
0x180035e3f  call    cs:__imp_GetModuleFileNameW
0x180035e45  test    eax, eax
0x180035e47  jz      loc_180035F8B
0x180035e4d  lea     rdx, [rsp+288h+Filename]; SourceString
0x180035e52  lea     rcx, [rsp+288h+DestinationString]; DestinationString
0x180035e57  call    cs:__imp_RtlInitUnicodeString
0x180035e5d  lea     r8, [rdi+28h]; DestinationString
0x180035e61  mov     ecx, 3; Flags
0x180035e66  lea     rdx, [rsp+288h+DestinationString]; SourceString
0x180035e6b  call    cs:__imp_RtlDuplicateUnicodeString
0x180035e71  test    eax, eax
0x180035e73  js      short loc_180035E07
0x180035e75  lea     rax, [rdi+0A8h]
0x180035e7c  mov     r9d, 2000000h; samDesired
0x180035e82  xor     r8d, r8d; ulOptions
0x180035e85  mov     [rsp+288h+phkResult], rax; phkResult
0x180035e8a  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Sec"...
0x180035e91  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180035e98  call    cs:__imp_RegOpenKeyExW
0x180035e9e  mov     ebx, eax
0x180035ea0  test    eax, eax
0x180035ea2  jnz     loc_180035F93
0x180035ea8  lea     rcx, [rdi+0B0h]; DestinationString
0x180035eaf  lea     rdx, aDebuglevel; "Debuglevel"
0x180035eb6  call    cs:__imp_RtlInitUnicodeString
0x180035ebc  movups  xmm0, cs:DigestGlobalDebugTraceControlGuid
0x180035ec3  lea     rax, ?_DbgpTraceControllerTimerCallback@@YAXPEAXE@Z; _DbgpTraceControllerTimerCallback(void *,uchar)
0x180035eca  mov     [rdi+90h], rax
0x180035ed1  movdqu  xmmword ptr [rdi+70h], xmm0
0x180035ed6  call    ?_DbgpOpenOrCreateSharedMem@@YAPEAU_DBG_TCB_HEADER@@XZ; _DbgpOpenOrCreateSharedMem(void)
0x180035edb  mov     rsi, rax
0x180035ede  test    rax, rax
0x180035ee1  jnz     short loc_180035EED
0x180035ee3  mov     ebx, 490h
0x180035ee8  jmp     loc_180035F93
0x180035eed  lea     rcx, [rax+50h]; lpCriticalSection
0x180035ef1  call    cs:__imp_EnterCriticalSection
0x180035ef7  mov     rdx, [rsi+78h]
0x180035efb  lea     rcx, [rsi+50h]; lpCriticalSection
0x180035eff  lea     rax, [rdx+1]
0x180035f03  mov     [rsi+78h], rax
0x180035f07  mov     [rdi+0E8h], rdx
0x180035f0e  call    cs:__imp_LeaveCriticalSection
0x180035f14  cmp     byte ptr [rsi+38h], 0
0x180035f18  jz      short loc_180035F21
0x180035f1a  mov     dword ptr [rdi+20h], 3
0x180035f21  lea     rax, ?_DbgpTraceTimerCallback@@YAXPEAXE@Z; _DbgpTraceTimerCallback(void *,uchar)
0x180035f28  xor     r9d, r9d; lpName
0x180035f2b  xor     r8d, r8d; bInitialState
0x180035f2e  mov     [rdi+88h], rax
0x180035f35  xor     edx, edx; bManualReset
0x180035f37  xor     ecx, ecx; lpEventAttributes
0x180035f39  call    cs:__imp_CreateEventW
0x180035f3f  mov     [rdi+98h], rax
0x180035f46  test    rax, rax
0x180035f49  jz      short loc_180035F8B
0x180035f4b  mov     r8, [rdi+0E8h]
0x180035f52  lea     rdx, ?_DbgpRegistryChangeNotifycationCallback@@YAXPEAXE@Z; _DbgpRegistryChangeNotifycationCallback(void *,uchar)
0x180035f59  or      r9d, 0FFFFFFFFh
0x180035f5d  mov     dword ptr [rsp+288h+phkResult], 80h
0x180035f65  mov     rcx, rax
0x180035f68  call    cs:__imp_RegisterWaitForSingleObjectEx
0x180035f6e  mov     [rdi+0A0h], rax
0x180035f75  test    rax, rax
0x180035f78  jz      short loc_180035F8B
0x180035f7a  lea     rcx, [rdi+18h]; SystemTime
0x180035f7e  call    cs:__imp_NtQuerySystemTime
0x180035f84  xor     ebx, ebx
0x180035f86  mov     [r14], rdi
0x180035f89  jmp     short loc_180035F9B
0x180035f8b  call    cs:__imp_GetLastError
0x180035f91  mov     ebx, eax
0x180035f93  mov     rcx, rdi; struct _DBG_TRACE_CONTROL_BLOCK *
0x180035f96  call    ?_DbgpDeleteTraceControl@@YAXPEAU_DBG_TRACE_CONTROL_BLOCK@@@Z; _DbgpDeleteTraceControl(_DBG_TRACE_CONTROL_BLOCK *)
0x180035f9b  xor     eax, eax
0x180035f9d  test    ebx, ebx
0x180035f9f  setz    al
0x180035fa2  mov     rcx, [rsp+288h+var_38]
0x180035faa  xor     rcx, rsp; StackCookie
0x180035fad  call    __security_check_cookie
0x180035fb2  add     rsp, 268h
0x180035fb9  pop     r14
0x180035fbb  pop     rdi
0x180035fbc  pop     rsi
0x180035fbd  pop     rbx
0x180035fbe  retn
```
