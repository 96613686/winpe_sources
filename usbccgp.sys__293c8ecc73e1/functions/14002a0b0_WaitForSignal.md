# WaitForSignal

- ea: `0x14002a0b0`
- end: `0x14002a1c4`
- name: `WaitForSignal`
- size: `276`
- prototype: `__int64 __fastcall(PVOID Object)`
- caller_count: `14`
- callee_count: `3`
- tags: ``

## callers

- `0x140004e30`
- `0x140004f50`
- `0x140006630`
- `0x140006d40`
- `0x140007170`
- `0x14000deb8`
- `0x140010d14`
- `0x1400124cc`
- `0x14001399c`
- `0x140022fe8`
- `0x1400258cc`
- `0x140029b50`
- `0x140029dac`
- `0x14002a018`

## callees

- `0x14000fa04`
- `0x140013d4c`
- `0x14002a0b0`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14002a0e6`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002a1b3`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002a0e6`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002a1b3`
- `ntoskrnl!DbgPrint` at `0x14002a164`
- `ntoskrnl!DbgPrint` at `0x14002a164`

## string_xrefs

- `0x14002a155`: `\nUSBCCGP Watchdog: Thread 0x%p has waited %d minutes for %s to be signalled\n`

## pseudocode

```c
NTSTATUS __fastcall WaitForSignal(PVOID Object, const char *a2, int a3)
{
  int v5; // ebx
  NTSTATUS result; // eax
  int v8; // edx
  int v9; // r8d
  int v10; // edx
  int v11; // r8d
  int Timeout; // [rsp+20h] [rbp-38h]
  union _LARGE_INTEGER v13; // [rsp+78h] [rbp+20h] BYREF

  v13.QuadPart = -600000000;
  v5 = 0;
  for ( result = KeWaitForSingleObject(Object, Executive, 0, 0, &v13);
        result == 258;
        result = KeWaitForSingleObject(Object, Executive, 0, 0, &v13) )
  {
    DbgPrint(
      "\nUSBCCGP Watchdog: Thread 0x%p has waited %d minutes for %s to be signalled\n",
      KeGetCurrentThread(),
      ++v5,
      a2);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_qds(a3, v10, v11, 61, Timeout, (char)KeGetCurrentThread(), v5, (__int64)a2);
  }
  if ( result < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    return WPP_RECORDER_SF_dqs(a3, v8, v9, 62, Timeout, result, (char)KeGetCurrentThread(), (__int64)a2);
  return result;
}

```

## disassembly

```asm
0x14002a0b0  mov     r11, rsp
0x14002a0b3  mov     [r11+8], rbx
0x14002a0b7  mov     [r11+10h], rbp
0x14002a0bb  push    rsi
0x14002a0bc  push    rdi
0x14002a0bd  push    r14
0x14002a0bf  sub     rsp, 40h
0x14002a0c3  mov     rsi, r8
0x14002a0c6  mov     qword ptr [r11+20h], 0FFFFFFFFDC3CBA00h
0x14002a0ce  mov     rdi, rdx
0x14002a0d1  lea     rax, [r11+20h]
0x14002a0d5  xor     r8d, r8d; WaitMode
0x14002a0d8  mov     [r11-38h], rax
0x14002a0dc  xor     edx, edx; WaitReason
0x14002a0de  xor     ebx, ebx
0x14002a0e0  xor     r9d, r9d; Alertable
0x14002a0e3  mov     rbp, rcx
0x14002a0e6  call    cs:__imp_KeWaitForSingleObject
0x14002a0ed  nop     dword ptr [rax+rax+00h]
0x14002a0f2  lea     r14, WPP_RECORDER_INITIALIZED
0x14002a0f9  mov     r10d, eax
0x14002a0fc  cmp     eax, 102h
0x14002a101  jz      short loc_14002A14C
0x14002a103  test    eax, eax
0x14002a105  js      short loc_14002A11B
0x14002a107  mov     rbx, [rsp+58h+arg_0]
0x14002a10c  mov     rbp, [rsp+58h+arg_8]
0x14002a111  add     rsp, 40h
0x14002a115  pop     r14
0x14002a117  pop     rdi
0x14002a118  pop     rsi
0x14002a119  retn
0x14002a11b  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14002a122  jz      short loc_14002A107
0x14002a124  mov     rax, gs:188h
0x14002a12d  mov     r9d, 3Eh ; '>'
0x14002a133  mov     [rsp+58h+var_20], rdi
0x14002a138  mov     rcx, rsi
0x14002a13b  mov     [rsp+58h+var_28], rax
0x14002a140  mov     dword ptr [rsp+58h+var_30], r10d
0x14002a145  call    WPP_RECORDER_SF_dqs
0x14002a14a  jmp     short loc_14002A107
0x14002a14c  mov     rdx, gs:188h
0x14002a155  lea     rcx, aUsbccgpWatchdo; "\nUSBCCGP Watchdog: Thread 0x%p has wai"...
0x14002a15c  inc     ebx
0x14002a15e  mov     r9, rdi
0x14002a161  mov     r8d, ebx
0x14002a164  call    cs:__imp_DbgPrint
0x14002a16b  nop     dword ptr [rax+rax+00h]
0x14002a170  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14002a177  jz      short loc_14002A19E
0x14002a179  mov     rax, gs:188h
0x14002a182  mov     r9d, 3Dh ; '='
0x14002a188  mov     [rsp+58h+var_20], rdi
0x14002a18d  mov     rcx, rsi
0x14002a190  mov     dword ptr [rsp+58h+var_28], ebx
0x14002a194  mov     [rsp+58h+var_30], rax
0x14002a199  call    WPP_RECORDER_SF_qds
0x14002a19e  lea     rax, [rsp+58h+arg_18]
0x14002a1a3  xor     r9d, r9d; Alertable
0x14002a1a6  xor     r8d, r8d; WaitMode
0x14002a1a9  mov     [rsp+58h+Timeout], rax; Timeout
0x14002a1ae  xor     edx, edx; WaitReason
0x14002a1b0  mov     rcx, rbp; Object
0x14002a1b3  call    cs:__imp_KeWaitForSingleObject
0x14002a1ba  nop     dword ptr [rax+rax+00h]
0x14002a1bf  jmp     loc_14002A0F9
```
