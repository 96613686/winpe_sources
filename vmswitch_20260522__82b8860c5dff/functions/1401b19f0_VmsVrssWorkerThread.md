# VmsVrssWorkerThread

- ea: `0x1401b19f0`
- end: `0x1401b1ba8`
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
- `0x1401b19f0`
- `0x1401b1bb0`
- `0x1401bbc40`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x1401b1add`
- `ntoskrnl!KeDelayExecutionThread` at `0x1401b1add`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x1401b1b1d`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x1401b1b1d`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1401b1a4f`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1401b1a5f`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1401b1a7b`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1401b1ab6`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1401b1aed`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1401b1a4f`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1401b1a5f`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1401b1a7b`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1401b1ab6`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1401b1aed`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x1401b1a38`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x1401b1a38`

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
0x1401b19f0  mov     r11, rsp
0x1401b19f3  mov     [r11+10h], rbx
0x1401b19f7  mov     [r11+18h], rsi
0x1401b19fb  push    rdi
0x1401b19fc  sub     rsp, 50h
0x1401b1a00  mov     rax, cs:__security_cookie
0x1401b1a07  xor     rax, rsp
0x1401b1a0a  mov     [rsp+58h+var_10], rax
0x1401b1a0f  movzx   eax, word ptr [rcx+4]
0x1401b1a13  mov     rdi, rcx
0x1401b1a16  mov     cl, [rcx+6]
0x1401b1a19  xorps   xmm0, xmm0
0x1401b1a1c  movups  [rsp+58h+var_20], xmm0
0x1401b1a21  mov     word ptr [rsp+58h+var_20+8], ax
0x1401b1a26  xor     edx, edx; PreviousAffinity
0x1401b1a28  mov     eax, 1
0x1401b1a2d  shl     rax, cl
0x1401b1a30  lea     rcx, [r11-20h]; Affinity
0x1401b1a34  mov     [r11-20h], rax
0x1401b1a38  call    cs:__imp_KeSetSystemGroupAffinityThread
0x1401b1a3f  nop     dword ptr [rax+rax+00h]
0x1401b1a44  xor     ecx, ecx; ProcNumber
0x1401b1a46  mov     qword ptr [rsp+58h+Interval], 0
0x1401b1a4f  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1401b1a56  nop     dword ptr [rax+rax+00h]
0x1401b1a5b  mov     ebx, [rdi]
0x1401b1a5d  xor     ecx, ecx; ProcNumber
0x1401b1a5f  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1401b1a66  nop     dword ptr [rax+rax+00h]
0x1401b1a6b  lea     rsi, WPP_8833d5a3b0633e58bb871197bf680e05_Traceguids
0x1401b1a72  jmp     loc_1401B1AF9
0x1401b1a77  mov     ebx, [rdi]
0x1401b1a79  xor     ecx, ecx; ProcNumber
0x1401b1a7b  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1401b1a82  nop     dword ptr [rax+rax+00h]
0x1401b1a87  cmp     ebx, eax
0x1401b1a89  jz      short loc_1401B1ACB
0x1401b1a8b  mov     rcx, cs:VmsIfrLog
0x1401b1a92  lea     rax, aCurrentprocess; "CurrentProcessor->Index == KeGetCurrent"...
0x1401b1a99  mov     r9d, 18h
0x1401b1a9f  mov     [rsp+58h+var_30], rax
0x1401b1aa4  mov     [rsp+58h+Context], rsi
0x1401b1aa9  lea     r8d, [r9-5]
0x1401b1aad  call    WPP_RECORDER_SF_s
0x1401b1ab2  mov     ebx, [rdi]
0x1401b1ab4  xor     ecx, ecx; ProcNumber
0x1401b1ab6  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1401b1abd  nop     dword ptr [rax+rax+00h]
0x1401b1ac2  cmp     ebx, eax
0x1401b1ac4  jz      short loc_1401B1ACB
0x1401b1ac6  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "CurrentProcessor->Index == KeGetCurrentProcessorNumberEx(((void *)0))")
0x1401b1acb  lea     r8, [rsp+58h+Interval]; Interval
0x1401b1ad0  mov     qword ptr [rsp+58h+Interval], 0FFFFFFFFFFFFD8F0h
0x1401b1ad9  xor     edx, edx; Alertable
0x1401b1adb  xor     ecx, ecx; WaitMode
0x1401b1add  call    cs:__imp_KeDelayExecutionThread
0x1401b1ae4  nop     dword ptr [rax+rax+00h]
0x1401b1ae9  mov     ebx, [rdi]
0x1401b1aeb  xor     ecx, ecx; ProcNumber
0x1401b1aed  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1401b1af4  nop     dword ptr [rax+rax+00h]
0x1401b1af9  cmp     ebx, eax
0x1401b1afb  jnz     loc_1401B1A77
0x1401b1b01  mov     r9b, 1; Wait
0x1401b1b04  mov     [rsp+58h+Context], 0; Context
0x1401b1b0d  mov     r8d, 0C000h; Size
0x1401b1b13  lea     rcx, VmsVrssWorkerThreadCallout; Callout
0x1401b1b1a  mov     rdx, rdi; Parameter
0x1401b1b1d  call    cs:__imp_KeExpandKernelStackAndCalloutEx
0x1401b1b24  nop     dword ptr [rax+rax+00h]
0x1401b1b29  test    eax, eax
0x1401b1b2b  jns     short loc_1401B1B82
0x1401b1b2d  mov     rcx, cs:VmsIfrLog
0x1401b1b34  mov     r9d, 0Fh
0x1401b1b3a  mov     dword ptr [rsp+58h+var_30], eax
0x1401b1b3e  mov     dl, 2
0x1401b1b40  mov     [rsp+58h+Context], rsi
0x1401b1b45  lea     r8d, [r9+5]
0x1401b1b49  call    WPP_RECORDER_SF_d
0x1401b1b4e  mov     rcx, cs:VmsIfrLog
0x1401b1b55  lea     rax, aFalse; "FALSE"
0x1401b1b5c  mov     r9d, 10h
0x1401b1b62  mov     [rsp+58h+var_30], rax
0x1401b1b67  mov     [rsp+58h+Context], rsi
0x1401b1b6c  lea     r8d, [r9+3]
0x1401b1b70  call    WPP_RECORDER_SF_s
0x1401b1b75  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "0")
0x1401b1b7a  mov     rcx, rdi; Parameter
0x1401b1b7d  call    VmsVrssWorkerThreadCallout
0x1401b1b82  lock or dword ptr [rdi+338h], 10h
0x1401b1b8a  mov     rcx, [rsp+58h+var_10]
0x1401b1b8f  xor     rcx, rsp; StackCookie
0x1401b1b92  call    __security_check_cookie
0x1401b1b97  mov     rbx, [rsp+58h+arg_8]
0x1401b1b9c  mov     rsi, [rsp+58h+arg_10]
0x1401b1ba1  add     rsp, 50h
0x1401b1ba5  pop     rdi
0x1401b1ba6  retn
```
