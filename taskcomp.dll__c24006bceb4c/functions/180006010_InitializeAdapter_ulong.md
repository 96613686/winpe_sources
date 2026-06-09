# InitializeAdapter(ulong)

- ea: `0x180006010`
- end: `0x1800060d9`
- name: `?InitializeAdapter@@YAJK@Z`
- size: `201`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180006010`
- `0x1800060e0`
- `0x18001124c`
- `0x1800168b8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180006097`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180006097`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800060a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800060a9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006034`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000605e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006034`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000605e`

## string_xrefs

- `0x18000602d`: `CompatibilityAdapter::Initialize() failed, exiting\n`
- `0x180006057`: `Failed to create or update sa.dat file, exiting\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall InitializeAdapter(unsigned int a1)
{
  int v1; // eax
  tsched *v2; // rcx
  int v3; // r8d
  char *v4; // r9
  unsigned int v5; // ebx
  int v7; // ebx
  signed int LastError; // eax
  int *lpThreadId; // [rsp+28h] [rbp-10h]
  char v10[32]; // [rsp+0h] [rbp-38h] BYREF
  int v11; // [rsp+48h] [rbp+10h] BYREF
  DWORD ThreadId; // [rsp+50h] [rbp+18h] BYREF

  try
  {
    v11 = 0;
    v1 = CompatibilityAdapter::Initialize(a1);
  }
  catch ( ... )
  {
    tsched::KnownExceptionToHResult(v2, v10, v3, v4, (unsigned __int8)&v11, lpThreadId);
  }
  v5 = v1;
  v11 = v1;
  if ( v1 >= 0 )
  {
    v7 = SADatCreate(g_TasksFolderInfo);
    v11 = v7;
    if ( v7 >= 0 )
    {
      ThreadId = 0;
      g_hMonitorThread = CreateThread(0, 0, CompatibilityAdapter::MonitorThread, 0, 0, &ThreadId);
      if ( !g_hMonitorThread )
      {
        LastError = GetLastError();
        v7 = LastError;
        if ( LastError > 0 )
          v7 = (unsigned __int16)LastError | 0x80070000;
        v11 = v7;
        CompatibilityAdapter::Cleanup(0);
      }
      return (unsigned int)v7;
    }
    else
    {
      OutputDebugStringW(L"Failed to create or update sa.dat file, exiting\n");
      CompatibilityAdapter::Cleanup(0);
      return (unsigned int)v7;
    }
  }
  else
  {
    OutputDebugStringW(L"CompatibilityAdapter::Initialize() failed, exiting\n");
    return v5;
  }
}

```

## disassembly

```asm
0x180006010  push    rbx
0x180006012  sub     rsp, 30h
0x180006016  mov     [rsp+38h+arg_8], 0
0x18000601e  call    ?Initialize@CompatibilityAdapter@@SAJK@Z; CompatibilityAdapter::Initialize(ulong)
0x180006023  mov     ebx, eax
0x180006025  mov     [rsp+38h+arg_8], eax
0x180006029  test    eax, eax
0x18000602b  jns     short loc_180006041
0x18000602d  lea     rcx, aCompatibilitya_0; "CompatibilityAdapter::Initialize() fail"...
0x180006034  call    cs:__imp_OutputDebugStringW
0x18000603a  mov     eax, ebx
0x18000603c  jmp     loc_1800060D2
0x180006041  mov     rcx, cs:?g_TasksFolderInfo@@3U_TasksFolderInfo@@A; unsigned __int16 *
0x180006048  call    ?SADatCreate@@YAJPEBGH@Z; SADatCreate(ushort const *,int)
0x18000604d  mov     ebx, eax
0x18000604f  mov     [rsp+38h+arg_8], eax
0x180006053  test    eax, eax
0x180006055  jns     short loc_18000606F
0x180006057  lea     rcx, aFailedToCreate; "Failed to create or update sa.dat file,"...
0x18000605e  call    cs:__imp_OutputDebugStringW
0x180006064  xor     ecx, ecx; int
0x180006066  call    ?Cleanup@CompatibilityAdapter@@SAJH@Z; CompatibilityAdapter::Cleanup(int)
0x18000606b  mov     eax, ebx
0x18000606d  jmp     short loc_1800060D2
0x18000606f  mov     [rsp+38h+ThreadId], 0
0x180006077  lea     rax, [rsp+38h+ThreadId]
0x18000607c  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x180006081  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x180006089  xor     r9d, r9d; lpParameter
0x18000608c  lea     r8, ?MonitorThread@CompatibilityAdapter@@SAJPEAX@Z; lpStartAddress
0x180006093  xor     edx, edx; dwStackSize
0x180006095  xor     ecx, ecx; lpThreadAttributes
0x180006097  call    cs:__imp_CreateThread
0x18000609d  mov     cs:?g_hMonitorThread@@3PEAXEA, rax; void * g_hMonitorThread
0x1800060a4  test    rax, rax
0x1800060a7  jnz     short loc_1800060CA
0x1800060a9  call    cs:__imp_GetLastError
0x1800060af  mov     ebx, eax
0x1800060b1  test    eax, eax
0x1800060b3  jle     short loc_1800060BE
0x1800060b5  movzx   ebx, ax
0x1800060b8  or      ebx, 80070000h
0x1800060be  mov     [rsp+38h+arg_8], ebx
0x1800060c2  xor     ecx, ecx; int
0x1800060c4  call    ?Cleanup@CompatibilityAdapter@@SAJH@Z; CompatibilityAdapter::Cleanup(int)
0x1800060c9  nop
0x1800060ca  jmp     short loc_1800060D0
0x1800060cc  mov     ebx, [rsp+38h+arg_8]
0x1800060d0  mov     eax, ebx
0x1800060d2  add     rsp, 30h
0x1800060d6  pop     rbx
0x1800060d7  retn
```
