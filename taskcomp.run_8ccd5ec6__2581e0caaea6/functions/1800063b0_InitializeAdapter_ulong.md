# InitializeAdapter(ulong)

- ea: `0x1800063b0`
- end: `0x180006491`
- name: `?InitializeAdapter@@YAJK@Z`
- size: `225`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1800063b0`
- `0x180006498`
- `0x180011ce0`
- `0x1800177d4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180006443`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180006443`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000645b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000645b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800063d4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006404`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800063d4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006404`

## string_xrefs

- `0x1800063cd`: `CompatibilityAdapter::Initialize() failed, exiting\n`
- `0x1800063fd`: `Failed to create or update sa.dat file, exiting\n`

## pseudocode

```c
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
0x1800063b0  push    rbx
0x1800063b2  sub     rsp, 30h
0x1800063b6  mov     [rsp+38h+arg_8], 0
0x1800063be  call    ?Initialize@CompatibilityAdapter@@SAJK@Z; CompatibilityAdapter::Initialize(ulong)
0x1800063c3  mov     ebx, eax
0x1800063c5  mov     [rsp+38h+arg_8], eax
0x1800063c9  test    eax, eax
0x1800063cb  jns     short loc_1800063E7
0x1800063cd  lea     rcx, aCompatibilitya_0; "CompatibilityAdapter::Initialize() fail"...
0x1800063d4  call    cs:__imp_OutputDebugStringW
0x1800063db  nop     dword ptr [rax+rax+00h]
0x1800063e0  mov     eax, ebx
0x1800063e2  jmp     loc_18000648A
0x1800063e7  mov     rcx, cs:?g_TasksFolderInfo@@3U_TasksFolderInfo@@A; unsigned __int16 *
0x1800063ee  call    ?SADatCreate@@YAJPEBGH@Z; SADatCreate(ushort const *,int)
0x1800063f3  mov     ebx, eax
0x1800063f5  mov     [rsp+38h+arg_8], eax
0x1800063f9  test    eax, eax
0x1800063fb  jns     short loc_18000641B
0x1800063fd  lea     rcx, aFailedToCreate; "Failed to create or update sa.dat file,"...
0x180006404  call    cs:__imp_OutputDebugStringW
0x18000640b  nop     dword ptr [rax+rax+00h]
0x180006410  xor     ecx, ecx; int
0x180006412  call    ?Cleanup@CompatibilityAdapter@@SAJH@Z; CompatibilityAdapter::Cleanup(int)
0x180006417  mov     eax, ebx
0x180006419  jmp     short loc_18000648A
0x18000641b  mov     [rsp+38h+ThreadId], 0
0x180006423  lea     rax, [rsp+38h+ThreadId]
0x180006428  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x18000642d  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x180006435  xor     r9d, r9d; lpParameter
0x180006438  lea     r8, ?MonitorThread@CompatibilityAdapter@@SAJPEAX@Z; lpStartAddress
0x18000643f  xor     edx, edx; dwStackSize
0x180006441  xor     ecx, ecx; lpThreadAttributes
0x180006443  call    cs:__imp_CreateThread
0x18000644a  nop     dword ptr [rax+rax+00h]
0x18000644f  mov     cs:?g_hMonitorThread@@3PEAXEA, rax; void * g_hMonitorThread
0x180006456  test    rax, rax
0x180006459  jnz     short loc_180006482
0x18000645b  call    cs:__imp_GetLastError
0x180006462  nop     dword ptr [rax+rax+00h]
0x180006467  mov     ebx, eax
0x180006469  test    eax, eax
0x18000646b  jle     short loc_180006476
0x18000646d  movzx   ebx, ax
0x180006470  or      ebx, 80070000h
0x180006476  mov     [rsp+38h+arg_8], ebx
0x18000647a  xor     ecx, ecx; int
0x18000647c  call    ?Cleanup@CompatibilityAdapter@@SAJH@Z; CompatibilityAdapter::Cleanup(int)
0x180006481  nop
0x180006482  jmp     short loc_180006488
0x180006484  mov     ebx, [rsp+38h+arg_8]
0x180006488  mov     eax, ebx
0x18000648a  add     rsp, 30h
0x18000648e  pop     rbx
0x18000648f  retn
```
