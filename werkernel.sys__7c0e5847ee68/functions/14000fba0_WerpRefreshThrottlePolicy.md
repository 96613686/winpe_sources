# WerpRefreshThrottlePolicy

- ea: `0x14000fba0`
- end: `0x14000fda2`
- name: `WerpRefreshThrottlePolicy`
- size: `514`
- prototype: `NTSTATUS()`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000f1f8`

## callees

- `0x14000f3e0`
- `0x14000f54c`
- `0x14000f5b4`
- `0x14000fba0`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x14000fcf5`
- `ntoskrnl!DbgPrintEx` at `0x14000fd61`
- `ntoskrnl!DbgPrintEx` at `0x14000fcf5`
- `ntoskrnl!DbgPrintEx` at `0x14000fd61`
- `ntoskrnl!ZwClose` at `0x14000fd84`
- `ntoskrnl!ZwClose` at `0x14000fd84`

## string_xrefs

- `0x14000fbda`: `\Registry\Machine\System\CurrentControlSet\Control\CrashControl\FullLiveKernelReports`
- `0x14000fbc7`: `ComponentThrottleThreshold`
- `0x14000fc0f`: `VrfComponentThrottleThreshold`
- `0x14000fce9`: `WERKERNELHOST: Registry PerComponentThreshold cannot be shorter than SystemThreshold.\n`
- `0x14000fd53`: `WERKERNELHOST: Registry VrfComponentThreshold cannot be shorter than VrfSystemThreshold.\n`

## pseudocode

```c
NTSTATUS WerpRefreshThrottlePolicy()
{
  NTSTATUS result; // eax
  struct _UNICODE_STRING v1; // [rsp+20h] [rbp-60h] BYREF
  struct _UNICODE_STRING v2; // [rsp+30h] [rbp-50h] BYREF
  struct _UNICODE_STRING v3; // [rsp+40h] [rbp-40h] BYREF
  struct _UNICODE_STRING v4; // [rsp+50h] [rbp-30h] BYREF
  struct _UNICODE_STRING v5; // [rsp+60h] [rbp-20h] BYREF
  struct _UNICODE_STRING v6; // [rsp+70h] [rbp-10h] BYREF
  unsigned int v7; // [rsp+90h] [rbp+10h] BYREF
  HANDLE Handle; // [rsp+98h] [rbp+18h] BYREF

  *(_QWORD *)&v1.Length = 2490404;
  v1.Buffer = L"FullLiveReportsMax";
  *(_QWORD *)&v4.Length = 3538996;
  v4.Buffer = L"ComponentThrottleThreshold";
  *(_QWORD *)&v2.Length = 4456514;
  v2.Buffer = L"SystemMemoryThrottleThresholdInGB";
  *(_QWORD *)&v3.Length = 3145774;
  v3.Buffer = L"SystemThrottleThreshold";
  *(_QWORD *)&v6.Length = 3932218;
  v6.Buffer = L"VrfComponentThrottleThreshold";
  *(_QWORD *)&v5.Length = 3538996;
  v5.Buffer = L"VrfSystemThrottleThreshold";
  Handle = 0;
  result = WerpGetRegistryKey(
             0,
             L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\CrashControl\\FullLiveKernelReports",
             0x20019u,
             &Handle);
  if ( result >= 0 )
  {
    WerpGetRegistryUlongValue(Handle, &v1, 1, &dword_1400093C8);
    v7 = 256;
    WerpGetRegistryUlongValue(Handle, &v2, 256, &v7);
    if ( v7 == -1 )
      qword_1400093D0 = -1;
    else
      qword_1400093D0 = (unsigned __int64)v7 << 30;
    WerpGetRegistryTimeoutValue(Handle, &v3, 0x30u, (__int64 *)&xmmword_1400093A8);
    WerpGetRegistryTimeoutValue(Handle, &v4, 0xA8u, (__int64 *)&xmmword_1400093A8 + 1);
    if ( *((__int64 *)&xmmword_1400093A8 + 1) < (__int64)xmmword_1400093A8 )
    {
      DbgPrintEx(5u, 1u, "WERKERNELHOST: Registry PerComponentThreshold cannot be shorter than SystemThreshold.\n");
      *((_QWORD *)&xmmword_1400093A8 + 1) = xmmword_1400093A8;
    }
    WerpGetRegistryTimeoutValue(Handle, &v5, 1u, (__int64 *)&xmmword_1400093B8);
    WerpGetRegistryTimeoutValue(Handle, &v6, 0x18u, (__int64 *)&xmmword_1400093B8 + 1);
    result = xmmword_1400093B8;
    if ( *((__int64 *)&xmmword_1400093B8 + 1) < (__int64)xmmword_1400093B8 )
    {
      DbgPrintEx(5u, 1u, "WERKERNELHOST: Registry VrfComponentThreshold cannot be shorter than VrfSystemThreshold.\n");
      result = xmmword_1400093B8;
      *((_QWORD *)&xmmword_1400093B8 + 1) = xmmword_1400093B8;
    }
  }
  if ( Handle )
    return ZwClose(Handle);
  return result;
}

```

## disassembly

```asm
0x14000fba0  mov     [rsp-8+arg_10], rdi
0x14000fba5  push    rbp
0x14000fba6  mov     rbp, rsp
0x14000fba9  sub     rsp, 80h
0x14000fbb0  lea     rax, aFulllivereport; "FullLiveReportsMax"
0x14000fbb7  mov     [rbp+var_60], 260024h
0x14000fbbf  mov     [rbp+var_58], rax
0x14000fbc3  lea     r9, [rbp+Handle]
0x14000fbc7  lea     rax, aComponentthrot; "ComponentThrottleThreshold"
0x14000fbce  mov     [rbp+var_30], 360034h
0x14000fbd6  mov     [rbp+var_28], rax
0x14000fbda  lea     rdx, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x14000fbe1  lea     rax, aSystemmemoryth; "SystemMemoryThrottleThresholdInGB"
0x14000fbe8  mov     [rbp+var_50], 440042h
0x14000fbf0  mov     [rbp+var_48], rax
0x14000fbf4  mov     r8d, 20019h
0x14000fbfa  lea     rax, aSystemthrottle; "SystemThrottleThreshold"
0x14000fc01  mov     [rbp+var_40], 30002Eh
0x14000fc09  mov     [rbp+var_38], rax
0x14000fc0d  xor     ecx, ecx
0x14000fc0f  lea     rax, aVrfcomponentth; "VrfComponentThrottleThreshold"
0x14000fc16  mov     [rbp+var_10], 3C003Ah
0x14000fc1e  mov     [rbp+var_8], rax
0x14000fc22  mov     edi, 30h ; '0'
0x14000fc27  lea     rax, aVrfsystemthrot; "VrfSystemThrottleThreshold"
0x14000fc2e  mov     [rbp+var_20], 360034h
0x14000fc36  mov     [rbp+var_18], rax
0x14000fc3a  mov     [rbp+Handle], 0
0x14000fc42  call    WerpGetRegistryKey
0x14000fc47  test    eax, eax
0x14000fc49  js      loc_14000FD7B
0x14000fc4f  mov     rcx, [rbp+Handle]
0x14000fc53  lea     r9, dword_1400093C8
0x14000fc5a  lea     r8d, [rdi-2Fh]
0x14000fc5e  lea     rdx, [rbp+var_60]
0x14000fc62  call    WerpGetRegistryUlongValue
0x14000fc67  mov     rcx, [rbp+Handle]
0x14000fc6b  lea     r9, [rbp+arg_0]
0x14000fc6f  mov     r8d, 100h
0x14000fc75  lea     rdx, [rbp+var_50]
0x14000fc79  mov     [rbp+arg_0], r8d
0x14000fc7d  call    WerpGetRegistryUlongValue
0x14000fc82  cmp     [rbp+arg_0], 0FFFFFFFFh
0x14000fc86  jz      short loc_14000FC98
0x14000fc88  mov     eax, [rbp+arg_0]
0x14000fc8b  shl     rax, 1Eh
0x14000fc8f  mov     cs:qword_1400093D0, rax
0x14000fc96  jmp     short loc_14000FCA3
0x14000fc98  mov     cs:qword_1400093D0, 0FFFFFFFFFFFFFFFFh
0x14000fca3  mov     rcx, [rbp+Handle]
0x14000fca7  lea     r9, xmmword_1400093A8
0x14000fcae  mov     r8d, edi
0x14000fcb1  lea     rdx, [rbp+var_40]
0x14000fcb5  call    WerpGetRegistryTimeoutValue
0x14000fcba  mov     rcx, [rbp+Handle]
0x14000fcbe  lea     r9, xmmword_1400093A8+8
0x14000fcc5  mov     r8d, 0A8h
0x14000fccb  lea     rdx, [rbp+var_30]
0x14000fccf  call    WerpGetRegistryTimeoutValue
0x14000fcd4  mov     rax, qword ptr cs:xmmword_1400093A8
0x14000fcdb  mov     edi, 5
0x14000fce0  cmp     qword ptr cs:xmmword_1400093A8+8, rax
0x14000fce7  jge     short loc_14000FD0F
0x14000fce9  lea     r8, aWerkernelhostR_3; "WERKERNELHOST: Registry PerComponentThr"...
0x14000fcf0  mov     ecx, edi; ComponentId
0x14000fcf2  lea     edx, [rdi-4]; Level
0x14000fcf5  call    cs:__imp_DbgPrintEx
0x14000fcfc  nop     dword ptr [rax+rax+00h]
0x14000fd01  mov     rax, qword ptr cs:xmmword_1400093A8
0x14000fd08  mov     qword ptr cs:xmmword_1400093A8+8, rax
0x14000fd0f  mov     rcx, [rbp+Handle]
0x14000fd13  lea     r9, xmmword_1400093B8
0x14000fd1a  mov     r8d, 1
0x14000fd20  lea     rdx, [rbp+var_20]
0x14000fd24  call    WerpGetRegistryTimeoutValue
0x14000fd29  mov     rcx, [rbp+Handle]
0x14000fd2d  lea     r9, xmmword_1400093B8+8
0x14000fd34  mov     r8d, 18h
0x14000fd3a  lea     rdx, [rbp+var_10]
0x14000fd3e  call    WerpGetRegistryTimeoutValue
0x14000fd43  mov     rax, qword ptr cs:xmmword_1400093B8
0x14000fd4a  cmp     qword ptr cs:xmmword_1400093B8+8, rax
0x14000fd51  jge     short loc_14000FD7B
0x14000fd53  lea     r8, aWerkernelhostR; "WERKERNELHOST: Registry VrfComponentThr"...
0x14000fd5a  mov     edx, 1; Level
0x14000fd5f  mov     ecx, edi; ComponentId
0x14000fd61  call    cs:__imp_DbgPrintEx
0x14000fd68  nop     dword ptr [rax+rax+00h]
0x14000fd6d  mov     rax, qword ptr cs:xmmword_1400093B8
0x14000fd74  mov     qword ptr cs:xmmword_1400093B8+8, rax
0x14000fd7b  mov     rcx, [rbp+Handle]; Handle
0x14000fd7f  test    rcx, rcx
0x14000fd82  jz      short loc_14000FD90
0x14000fd84  call    cs:__imp_ZwClose
0x14000fd8b  nop     dword ptr [rax+rax+00h]
0x14000fd90  mov     rdi, [rsp+80h+arg_10]
0x14000fd98  add     rsp, 80h
0x14000fd9f  pop     rbp
0x14000fda0  retn
```
