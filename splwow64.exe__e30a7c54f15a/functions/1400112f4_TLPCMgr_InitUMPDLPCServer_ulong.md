# TLPCMgr::InitUMPDLPCServer(ulong)

- ea: `0x1400112f4`
- end: `0x140011404`
- name: `?InitUMPDLPCServer@TLPCMgr@@QEAAKK@Z`
- size: `272`
- prototype: `unsigned int __fastcall(TLPCMgr *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000cca0`

## callees

- `0x1400085d8`
- `0x1400112f4`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x14001138f`
- `KERNEL32!WaitForSingleObject` at `0x14001138f`
- `KERNEL32!GetLastError` at `0x1400113ab`
- `KERNEL32!GetLastError` at `0x1400113d4`
- `KERNEL32!GetLastError` at `0x1400113ab`
- `KERNEL32!GetLastError` at `0x1400113d4`
- `KERNEL32!CloseHandle` at `0x140011383`
- `KERNEL32!CloseHandle` at `0x1400113cc`
- `KERNEL32!CloseHandle` at `0x140011383`
- `KERNEL32!CloseHandle` at `0x1400113cc`
- `KERNEL32!CreateEventW` at `0x140011329`
- `KERNEL32!CreateEventW` at `0x140011329`
- `KERNEL32!CreateThread` at `0x140011373`
- `KERNEL32!CreateThread` at `0x140011373`

## string_xrefs

- `0x14001139f`: `Failed to create the LPC port.  Error %d.`
- `0x1400113b3`: `Failed to spin up the GDI thunking thread.  Error %d.`
- `0x1400113dd`: `Failed to create the synchronization event.  Error %d.`

## pseudocode

```c
__int64 __fastcall TLPCMgr::InitUMPDLPCServer(TLPCMgr *this, int a2)
{
  HANDLE EventW; // rax
  void *v5; // rdi
  HANDLE v6; // rax
  __int64 LastError; // rbx
  __int128 Parameter; // [rsp+30h] [rbp-28h] BYREF
  __int64 v10; // [rsp+40h] [rbp-18h]
  DWORD ThreadId; // [rsp+70h] [rbp+18h] BYREF

  ThreadId = 0;
  v10 = 0;
  Parameter = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  v5 = EventW;
  if ( EventW )
  {
    *((_QWORD *)&Parameter + 1) = EventW;
    *(_QWORD *)&Parameter = this;
    LODWORD(v10) = 0;
    HIDWORD(v10) = a2;
    v6 = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)GDIThunkingVIALPCThread, &Parameter, 0, &ThreadId);
    if ( v6 )
    {
      LODWORD(LastError) = 0;
      CloseHandle(v6);
      WaitForSingleObject(v5, 0xFFFFFFFF);
      if ( !*((_QWORD *)this + 8) )
      {
        LODWORD(LastError) = v10;
        SplWow64Telemetry::WriteDbgTraceError(
          "TLPCMgr::InitUMPDLPCServer",
          L"Failed to create the LPC port.  Error %d.",
          (unsigned int)v10);
      }
    }
    else
    {
      LastError = GetLastError();
      SplWow64Telemetry::WriteDbgTraceError(
        "TLPCMgr::InitUMPDLPCServer",
        L"Failed to spin up the GDI thunking thread.  Error %d.",
        LastError);
    }
    CloseHandle(v5);
  }
  else
  {
    LastError = GetLastError();
    SplWow64Telemetry::WriteDbgTraceError(
      "TLPCMgr::InitUMPDLPCServer",
      L"Failed to create the synchronization event.  Error %d.",
      LastError);
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1400112f4  mov     [rsp+arg_0], rbx
0x1400112f9  mov     [rsp+arg_8], rsi
0x1400112fe  push    rdi
0x1400112ff  sub     rsp, 50h
0x140011303  mov     ebx, edx
0x140011305  mov     [rsp+58h+ThreadId], 0
0x14001130d  mov     rsi, rcx
0x140011310  xorps   xmm0, xmm0
0x140011313  xor     eax, eax
0x140011315  xor     edx, edx; bManualReset
0x140011317  xor     ecx, ecx; lpEventAttributes
0x140011319  mov     [rsp+58h+var_18], rax
0x14001131e  xor     r9d, r9d; lpName
0x140011321  xor     r8d, r8d; bInitialState
0x140011324  movups  [rsp+58h+Parameter], xmm0
0x140011329  call    cs:__imp_CreateEventW
0x14001132f  mov     rdi, rax
0x140011332  test    rax, rax
0x140011335  jz      loc_1400113D4
0x14001133b  mov     qword ptr [rsp+58h+Parameter+8], rax
0x140011340  lea     r9, [rsp+58h+Parameter]; lpParameter
0x140011345  lea     rax, [rsp+58h+ThreadId]
0x14001134a  mov     qword ptr [rsp+58h+Parameter], rsi
0x14001134f  mov     [rsp+58h+lpThreadId], rax; lpThreadId
0x140011354  lea     r8, GDIThunkingVIALPCThread; lpStartAddress
0x14001135b  xor     edx, edx; dwStackSize
0x14001135d  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x140011365  xor     ecx, ecx; lpThreadAttributes
0x140011367  mov     dword ptr [rsp+58h+var_18], 0
0x14001136f  mov     dword ptr [rsp+58h+var_18+4], ebx
0x140011373  call    cs:__imp_CreateThread
0x140011379  test    rax, rax
0x14001137c  jz      short loc_1400113AB
0x14001137e  mov     rcx, rax; hObject
0x140011381  xor     ebx, ebx
0x140011383  call    cs:__imp_CloseHandle
0x140011389  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14001138c  mov     rcx, rdi; hHandle
0x14001138f  call    cs:__imp_WaitForSingleObject
0x140011395  cmp     [rsi+40h], rbx
0x140011399  jnz     short loc_1400113C9
0x14001139b  mov     ebx, dword ptr [rsp+58h+var_18]
0x14001139f  lea     rdx, aFailedToCreate_2; "Failed to create the LPC port.  Error %"...
0x1400113a6  mov     r8d, ebx
0x1400113a9  jmp     short loc_1400113BD
0x1400113ab  call    cs:__imp_GetLastError
0x1400113b1  mov     ebx, eax
0x1400113b3  lea     rdx, aFailedToSpinUp; "Failed to spin up the GDI thunking thre"...
0x1400113ba  mov     r8d, eax
0x1400113bd  lea     rcx, aTlpcmgrInitump; "TLPCMgr::InitUMPDLPCServer"
0x1400113c4  call    ?WriteDbgTraceError@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceError(char *,ushort *,...)
0x1400113c9  mov     rcx, rdi; hObject
0x1400113cc  call    cs:__imp_CloseHandle
0x1400113d2  jmp     short loc_1400113F2
0x1400113d4  call    cs:__imp_GetLastError
0x1400113da  mov     r8d, eax
0x1400113dd  lea     rdx, aFailedToCreate_1; "Failed to create the synchronization ev"...
0x1400113e4  lea     rcx, aTlpcmgrInitump; "TLPCMgr::InitUMPDLPCServer"
0x1400113eb  mov     ebx, eax
0x1400113ed  call    ?WriteDbgTraceError@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceError(char *,ushort *,...)
0x1400113f2  mov     rsi, [rsp+58h+arg_8]
0x1400113f7  mov     eax, ebx
0x1400113f9  mov     rbx, [rsp+58h+arg_0]
0x1400113fe  add     rsp, 50h
0x140011402  pop     rdi
0x140011403  retn
```
