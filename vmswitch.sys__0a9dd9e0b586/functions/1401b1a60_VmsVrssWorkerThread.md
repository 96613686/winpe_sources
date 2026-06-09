# VmsVrssWorkerThread

- ea: `0x1401b1a60`
- end: `0x1401b1c18`
- name: `VmsVrssWorkerThread`
- size: `440`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140027a64`
- `0x14003a450`
- `0x14008497c`
- `0x1401b1a60`
- `0x1401b1c20`
- `0x1401bbcb0`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x1401b1b4d`
- `ntoskrnl!KeDelayExecutionThread` at `0x1401b1b4d`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x1401b1b8d`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x1401b1b8d`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1401b1abf`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1401b1acf`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1401b1aeb`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1401b1b26`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1401b1b5d`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1401b1abf`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1401b1acf`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1401b1aeb`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1401b1b26`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1401b1b5d`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x1401b1aa8`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x1401b1aa8`

## pseudocode

```c
void __fastcall VmsVrssWorkerThread(int *StartContext)
{
  WORD v1; // ax
  char v3; // cl
  int v4; // ebx
  ULONG i; // eax
  int v6; // ebx
  int v7; // edx
  int v8; // ebx
  NTSTATUS v9; // eax
  int v10; // edx
  int v11; // edx
  union _LARGE_INTEGER Interval; // [rsp+30h] [rbp-28h] BYREF
  struct _GROUP_AFFINITY v13; // [rsp+38h] [rbp-20h] BYREF

  v1 = *((_WORD *)StartContext + 2);
  v3 = *((_BYTE *)StartContext + 6);
  v13 = 0;
  v13.Group = v1;
  v13.Mask = 1LL << v3;
  KeSetSystemGroupAffinityThread(&v13, 0);
  Interval.QuadPart = 0;
  KeGetCurrentProcessorNumberEx(0);
  v4 = *StartContext;
  for ( i = KeGetCurrentProcessorNumberEx(0); v4 != i; i = KeGetCurrentProcessorNumberEx(0) )
  {
    v6 = *StartContext;
    if ( v6 != KeGetCurrentProcessorNumberEx(0) )
    {
      WPP_RECORDER_SF_s(
        VmsIfrLog,
        v7,
        19,
        24,
        (__int64)WPP_8833d5a3b0633e58bb871197bf680e05_Traceguids,
        (__int64)"CurrentProcessor->Index == KeGetCurrentProcessorNumberEx(NULL)");
      v8 = *StartContext;
      if ( v8 != KeGetCurrentProcessorNumberEx(0) )
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
    }
    Interval.QuadPart = -10000;
    KeDelayExecutionThread(0, 0, &Interval);
    v4 = *StartContext;
  }
  v9 = KeExpandKernelStackAndCalloutEx(VmsVrssWorkerThreadCallout, StartContext, 0xC000u, 1u, 0);
  if ( v9 < 0 )
  {
    LOBYTE(v10) = 2;
    WPP_RECORDER_SF_d(VmsIfrLog, v10, 20, 15, (__int64)WPP_8833d5a3b0633e58bb871197bf680e05_Traceguids, v9);
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      v11,
      19,
      16,
      (__int64)WPP_8833d5a3b0633e58bb871197bf680e05_Traceguids,
      (__int64)"FALSE");
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
    VmsVrssWorkerThreadCallout(StartContext);
  }
  _InterlockedOr(StartContext + 206, 0x10u);
}

```

## disassembly

```asm
0x1401b1a60  mov     r11, rsp
0x1401b1a63  mov     [r11+10h], rbx
0x1401b1a67  mov     [r11+18h], rsi
0x1401b1a6b  push    rdi
0x1401b1a6c  sub     rsp, 50h
0x1401b1a70  mov     rax, cs:__security_cookie
0x1401b1a77  xor     rax, rsp
0x1401b1a7a  mov     [rsp+58h+var_10], rax
0x1401b1a7f  movzx   eax, word ptr [rcx+4]
0x1401b1a83  mov     rdi, rcx
0x1401b1a86  mov     cl, [rcx+6]
0x1401b1a89  xorps   xmm0, xmm0
0x1401b1a8c  movups  [rsp+58h+var_20], xmm0
0x1401b1a91  mov     word ptr [rsp+58h+var_20+8], ax
0x1401b1a96  xor     edx, edx; PreviousAffinity
0x1401b1a98  mov     eax, 1
0x1401b1a9d  shl     rax, cl
0x1401b1aa0  lea     rcx, [r11-20h]; Affinity
0x1401b1aa4  mov     [r11-20h], rax
0x1401b1aa8  call    cs:__imp_KeSetSystemGroupAffinityThread
0x1401b1aaf  nop     dword ptr [rax+rax+00h]
0x1401b1ab4  xor     ecx, ecx; ProcNumber
0x1401b1ab6  mov     qword ptr [rsp+58h+Interval], 0
0x1401b1abf  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1401b1ac6  nop     dword ptr [rax+rax+00h]
0x1401b1acb  mov     ebx, [rdi]
0x1401b1acd  xor     ecx, ecx; ProcNumber
0x1401b1acf  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1401b1ad6  nop     dword ptr [rax+rax+00h]
0x1401b1adb  lea     rsi, WPP_8833d5a3b0633e58bb871197bf680e05_Traceguids
0x1401b1ae2  jmp     loc_1401B1B69
0x1401b1ae7  mov     ebx, [rdi]
0x1401b1ae9  xor     ecx, ecx; ProcNumber
0x1401b1aeb  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1401b1af2  nop     dword ptr [rax+rax+00h]
0x1401b1af7  cmp     ebx, eax
0x1401b1af9  jz      short loc_1401B1B3B
0x1401b1afb  mov     rcx, cs:VmsIfrLog
0x1401b1b02  lea     rax, aCurrentprocess; "CurrentProcessor->Index == KeGetCurrent"...
0x1401b1b09  mov     r9d, 18h
0x1401b1b0f  mov     [rsp+58h+var_30], rax
0x1401b1b14  mov     [rsp+58h+Context], rsi
0x1401b1b19  lea     r8d, [r9-5]
0x1401b1b1d  call    WPP_RECORDER_SF_s
0x1401b1b22  mov     ebx, [rdi]
0x1401b1b24  xor     ecx, ecx; ProcNumber
0x1401b1b26  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1401b1b2d  nop     dword ptr [rax+rax+00h]
0x1401b1b32  cmp     ebx, eax
0x1401b1b34  jz      short loc_1401B1B3B
0x1401b1b36  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "CurrentProcessor->Index == KeGetCurrentProcessorNumberEx(((void *)0))")
0x1401b1b3b  lea     r8, [rsp+58h+Interval]; Interval
0x1401b1b40  mov     qword ptr [rsp+58h+Interval], 0FFFFFFFFFFFFD8F0h
0x1401b1b49  xor     edx, edx; Alertable
0x1401b1b4b  xor     ecx, ecx; WaitMode
0x1401b1b4d  call    cs:__imp_KeDelayExecutionThread
0x1401b1b54  nop     dword ptr [rax+rax+00h]
0x1401b1b59  mov     ebx, [rdi]
0x1401b1b5b  xor     ecx, ecx; ProcNumber
0x1401b1b5d  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1401b1b64  nop     dword ptr [rax+rax+00h]
0x1401b1b69  cmp     ebx, eax
0x1401b1b6b  jnz     loc_1401B1AE7
0x1401b1b71  mov     r9b, 1; Wait
0x1401b1b74  mov     [rsp+58h+Context], 0; Context
0x1401b1b7d  mov     r8d, 0C000h; Size
0x1401b1b83  lea     rcx, VmsVrssWorkerThreadCallout; Callout
0x1401b1b8a  mov     rdx, rdi; Parameter
0x1401b1b8d  call    cs:__imp_KeExpandKernelStackAndCalloutEx
0x1401b1b94  nop     dword ptr [rax+rax+00h]
0x1401b1b99  test    eax, eax
0x1401b1b9b  jns     short loc_1401B1BF2
0x1401b1b9d  mov     rcx, cs:VmsIfrLog
0x1401b1ba4  mov     r9d, 0Fh
0x1401b1baa  mov     dword ptr [rsp+58h+var_30], eax
0x1401b1bae  mov     dl, 2
0x1401b1bb0  mov     [rsp+58h+Context], rsi
0x1401b1bb5  lea     r8d, [r9+5]
0x1401b1bb9  call    WPP_RECORDER_SF_d
0x1401b1bbe  mov     rcx, cs:VmsIfrLog
0x1401b1bc5  lea     rax, aFalse; "FALSE"
0x1401b1bcc  mov     r9d, 10h
0x1401b1bd2  mov     [rsp+58h+var_30], rax
0x1401b1bd7  mov     [rsp+58h+Context], rsi
0x1401b1bdc  lea     r8d, [r9+3]
0x1401b1be0  call    WPP_RECORDER_SF_s
0x1401b1be5  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "0")
0x1401b1bea  mov     rcx, rdi; Parameter
0x1401b1bed  call    VmsVrssWorkerThreadCallout
0x1401b1bf2  lock or dword ptr [rdi+338h], 10h
0x1401b1bfa  mov     rcx, [rsp+58h+var_10]
0x1401b1bff  xor     rcx, rsp; StackCookie
0x1401b1c02  call    __security_check_cookie
0x1401b1c07  mov     rbx, [rsp+58h+arg_8]
0x1401b1c0c  mov     rsi, [rsp+58h+arg_10]
0x1401b1c11  add     rsp, 50h
0x1401b1c15  pop     rdi
0x1401b1c16  retn
```
