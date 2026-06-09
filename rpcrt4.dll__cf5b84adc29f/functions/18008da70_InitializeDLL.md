# _InitializeDLL

- ea: `0x18008da70`
- end: `0x18008dbd6`
- name: `_InitializeDLL`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18008da30`

## callees

- `0x1800292c0`
- `0x18005cf88`
- `0x18008da70`
- `0x18008dbdc`
- `0x1800a529c`
- `0x1800a5534`
- `0x1800a5bc8`
- `0x1800bba10`
- `0x1800ce564`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x18008db79`
- `ntdll!RtlDeleteCriticalSection` at `0x18008db79`
- `ntdll!RtlInitializeCriticalSectionAndSpinCount` at `0x18008daa6`
- `ntdll!RtlInitializeCriticalSectionAndSpinCount` at `0x18008daa6`
- `ntdll!RtlImageNtHeader` at `0x18008dae3`
- `ntdll!RtlImageNtHeader` at `0x18008dae3`
- `ntdll!EtwEventUnregister` at `0x18008dbc5`
- `ntdll!EtwEventUnregister` at `0x18008dbc5`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18008dac3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18008dac3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18008dba3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18008dba3`

## pseudocode

```c
char __fastcall InitializeDLL(__int64 a1, int a2, __int64 a3)
{
  int v4; // edx
  struct _PEB *v6; // rcx
  PIMAGE_NT_HEADERS v7; // rax
  __int64 v8; // rcx
  __int64 SizeOfStackCommit; // rdx
  unsigned int v10; // edx
  THREAD *ThreadPointer; // rcx

  if ( a2 )
  {
    v4 = a2 - 1;
    if ( v4 )
    {
      if ( v4 == 2 )
      {
        ThreadPointer = RpcpGetThreadPointer();
        NtCurrentTeb()->ReservedForNtRpc = 0;
        if ( ThreadPointer )
          THREAD::`scalar deleting destructor'(ThreadPointer, v10);
      }
    }
    else
    {
      TlgRegisterAggregateProviderEx();
      RtlInitializeCriticalSectionAndSpinCount(&GlobalMutex, 0);
      GlobalMutexInitialized = 1;
      InitializeCriticalSection(&NdrOle_CS);
      v6 = NtCurrentPeb();
      byte_1800FEEC4 = 1;
      v7 = RtlImageNtHeader(v6->ImageBaseAddress);
      SizeOfStackCommit = 1024;
      if ( v7->OptionalHeader.SizeOfStackCommit < 0x400 )
        SizeOfStackCommit = v7->OptionalHeader.SizeOfStackCommit;
      SafeAllocaInitialize(v8, SizeOfStackCommit);
    }
  }
  else
  {
    TlgUnregisterAggregateProvider();
    if ( !a3 )
    {
      RpcpExtFreeExtensions();
      if ( GlobalMutexInitialized == 1 )
      {
        RtlDeleteCriticalSection(&GlobalMutex);
        GlobalMutexInitialized = 0;
      }
      if ( byte_1800FEEC4 )
      {
        DeleteCriticalSection(&NdrOle_CS);
        byte_1800FEEC4 = 0;
      }
    }
    if ( g_SqmEnabled )
      UploadAllSqmData();
    if ( RpcEtwGuid_Context )
      EtwEventUnregister();
    McGenEventUnregister_EtwEventUnregister();
  }
  return 1;
}

```

## disassembly

```asm
0x18008da70  push    rbx
0x18008da72  sub     rsp, 20h
0x18008da76  mov     rbx, r8
0x18008da79  test    edx, edx
0x18008da7b  jz      loc_18008DB04
0x18008da81  sub     edx, 1
0x18008da84  jz      short loc_18008DA98
0x18008da86  cmp     edx, 2
0x18008da89  jz      loc_18008DB35
0x18008da8f  mov     al, 1
0x18008da91  add     rsp, 20h
0x18008da95  pop     rbx
0x18008da96  retn
0x18008da98  call    TlgRegisterAggregateProviderEx
0x18008da9d  xor     edx, edx; SpinCount
0x18008da9f  lea     rcx, ?GlobalMutex@@3PADA; CriticalSection
0x18008daa6  call    cs:__imp_RtlInitializeCriticalSectionAndSpinCount
0x18008daad  nop     dword ptr [rax+rax+00h]
0x18008dab2  lea     rcx, ?NdrOle_CS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18008dab9  mov     cs:?GlobalMutexInitialized@@3HA, 1; int GlobalMutexInitialized
0x18008dac3  call    cs:__imp_InitializeCriticalSection
0x18008daca  nop     dword ptr [rax+rax+00h]
0x18008dacf  mov     rcx, gs:60h
0x18008dad8  mov     cs:byte_1800FEEC4, 1
0x18008dadf  mov     rcx, [rcx+10h]; BaseAddress
0x18008dae3  call    cs:__imp_RtlImageNtHeader
0x18008daea  nop     dword ptr [rax+rax+00h]
0x18008daef  mov     edx, 400h
0x18008daf4  cmp     [rax+68h], rdx
0x18008daf8  cmovb   rdx, [rax+68h]
0x18008dafd  call    SafeAllocaInitialize
0x18008db02  jmp     short loc_18008DA8F
0x18008db04  call    TlgUnregisterAggregateProvider
0x18008db09  test    rbx, rbx
0x18008db0c  jz      short loc_18008DB64
0x18008db0e  cmp     cs:?g_SqmEnabled@@3HA, 0; int g_SqmEnabled
0x18008db15  jnz     loc_18008DBBB
0x18008db1b  mov     rcx, cs:RpcEtwGuid_Context
0x18008db22  test    rcx, rcx
0x18008db25  jnz     loc_18008DBC5
0x18008db2b  call    McGenEventUnregister_EtwEventUnregister
0x18008db30  jmp     loc_18008DA8F
0x18008db35  call    ?RpcpGetThreadPointer@@YAPEAVTHREAD@@XZ; RpcpGetThreadPointer(void)
0x18008db3a  mov     rcx, rax; this
0x18008db3d  mov     rax, gs:30h
0x18008db46  mov     qword ptr [rax+1698h], 0
0x18008db51  test    rcx, rcx
0x18008db54  jz      loc_18008DA8F
0x18008db5a  call    ??_GTHREAD@@QEAAPEAXI@Z; THREAD::`scalar deleting destructor'(uint)
0x18008db5f  jmp     loc_18008DA8F
0x18008db64  call    RpcpExtFreeExtensions
0x18008db69  cmp     cs:?GlobalMutexInitialized@@3HA, 1; int GlobalMutexInitialized
0x18008db70  jnz     short loc_18008DB8F
0x18008db72  lea     rcx, ?GlobalMutex@@3PADA; CriticalSection
0x18008db79  call    cs:__imp_RtlDeleteCriticalSection
0x18008db80  nop     dword ptr [rax+rax+00h]
0x18008db85  mov     cs:?GlobalMutexInitialized@@3HA, 0; int GlobalMutexInitialized
0x18008db8f  cmp     cs:byte_1800FEEC4, 0
0x18008db96  jz      loc_18008DB0E
0x18008db9c  lea     rcx, ?NdrOle_CS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18008dba3  call    cs:__imp_DeleteCriticalSection
0x18008dbaa  nop     dword ptr [rax+rax+00h]
0x18008dbaf  mov     cs:byte_1800FEEC4, 0
0x18008dbb6  jmp     loc_18008DB0E
0x18008dbbb  call    ?UploadAllSqmData@@YAXXZ; UploadAllSqmData(void)
0x18008dbc0  jmp     loc_18008DB1B
0x18008dbc5  call    cs:__imp_EtwEventUnregister
0x18008dbcc  nop     dword ptr [rax+rax+00h]
0x18008dbd1  jmp     loc_18008DB2B
```
