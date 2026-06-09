# HardErrorWorkerThread

- ea: `0x18000d6f0`
- end: `0x18000d72f`
- name: `HardErrorWorkerThread`
- size: `63`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000d6f0`
- `0x18000d924`

## import_xrefs

- `ntdll!RtlExitUserThread` at `0x18000d722`
- `ntdll!RtlExitUserThread` at `0x18000d722`
- `CSRSRV!CsrDereferenceThread` at `0x18000d714`
- `CSRSRV!CsrDereferenceThread` at `0x18000d714`
- `CSRSRV!CsrConnectToUser` at `0x18000d6f6`
- `CSRSRV!CsrConnectToUser` at `0x18000d6f6`

## pseudocode

```c
void HardErrorWorkerThread()
{
  __int64 v0; // rbx

  v0 = CsrConnectToUser();
  ProcessHardErrorRequest(0);
  if ( v0 )
    CsrDereferenceThread(v0);
  RtlExitUserThread(0);
  __debugbreak();
  JUMPOUT(0x18000D72FLL);
}

```

## disassembly

```asm
0x18000d6f0  push    rbx
0x18000d6f2  sub     rsp, 20h
0x18000d6f6  call    cs:__imp_CsrConnectToUser
0x18000d6fd  nop     dword ptr [rax+rax+00h]
0x18000d702  xor     ecx, ecx
0x18000d704  mov     rbx, rax
0x18000d707  call    ProcessHardErrorRequest
0x18000d70c  test    rbx, rbx
0x18000d70f  jz      short loc_18000D720
0x18000d711  mov     rcx, rbx
0x18000d714  call    cs:__imp_CsrDereferenceThread
0x18000d71b  nop     dword ptr [rax+rax+00h]
0x18000d720  xor     ecx, ecx; Status
0x18000d722  call    cs:__imp_RtlExitUserThread
0x18000d729  nop     dword ptr [rax+rax+00h]
0x18000d72e  int     3; Trap to Debugger
```
