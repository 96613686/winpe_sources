# CSessionConfig::Initialize(void)

- ea: `0x18002cf64`
- end: `0x18002cfe8`
- name: `?Initialize@CSessionConfig@@QEAAJXZ`
- size: `132`
- prototype: `__int64 __fastcall(CSessionConfig *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18002ce80`

## callees

- `0x18000196c`
- `0x180025a7c`
- `0x18002cf64`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cfda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cfda`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002cf97`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002cf97`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002cfc8`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002cfc8`

## pseudocode

```c
__int64 __fastcall CSessionConfig::Initialize(CSessionConfig *this)
{
  HANDLE EventW; // rax
  HANDLE Thread; // rax
  int v5; // [rsp+40h] [rbp+8h] BYREF

  v5 = 0;
  TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_180084288);
  CSLQuery::IsAutomatedAppServerInstallation(&v5);
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 199) = EventW;
  if ( !EventW
    || (Thread = CreateThread(0, 0, CSessionConfig::s_ConfigTaskThread, this, 0, 0),
        (*((_QWORD *)this + 200) = Thread) == 0) )
  {
    GetLastError();
  }
  return 0;
}

```

## disassembly

```asm
0x18002cf64  push    rbx
0x18002cf66  sub     rsp, 30h
0x18002cf6a  mov     rbx, rcx
0x18002cf6d  mov     [rsp+38h+arg_0], 0
0x18002cf75  lea     rcx, dword_180084288; CallbackContext
0x18002cf7c  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18002cf81  lea     rcx, [rsp+38h+arg_0]; int *
0x18002cf86  call    ?IsAutomatedAppServerInstallation@CSLQuery@@SAJPEAH@Z; CSLQuery::IsAutomatedAppServerInstallation(int *)
0x18002cf8b  xor     r9d, r9d; lpName
0x18002cf8e  xor     r8d, r8d; bInitialState
0x18002cf91  xor     ecx, ecx; lpEventAttributes
0x18002cf93  lea     edx, [r9+1]; bManualReset
0x18002cf97  call    cs:__imp_CreateEventW
0x18002cf9d  mov     [rbx+638h], rax
0x18002cfa4  test    rax, rax
0x18002cfa7  jz      short loc_18002CFDA
0x18002cfa9  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x18002cfb2  lea     r8, ?s_ConfigTaskThread@CSessionConfig@@CAKPEAX@Z; lpStartAddress
0x18002cfb9  mov     r9, rbx; lpParameter
0x18002cfbc  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x18002cfc4  xor     edx, edx; dwStackSize
0x18002cfc6  xor     ecx, ecx; lpThreadAttributes
0x18002cfc8  call    cs:__imp_CreateThread
0x18002cfce  mov     [rbx+640h], rax
0x18002cfd5  test    rax, rax
0x18002cfd8  jnz     short loc_18002CFE0
0x18002cfda  call    cs:__imp_GetLastError
0x18002cfe0  xor     eax, eax
0x18002cfe2  add     rsp, 30h
0x18002cfe6  pop     rbx
0x18002cfe7  retn
```
