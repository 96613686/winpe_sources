# AcquireMutex

- ea: `0x1400090e0`
- end: `0x140009205`
- name: `AcquireMutex`
- size: `293`
- prototype: `__int64 __fastcall(PVOID Object)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x140008fd0`
- `0x140010650`
- `0x140024230`
- `0x140029e6c`
- `0x140029f14`
- `0x14002d07c`
- `0x14002d86c`

## callees

- `0x1400090e0`
- `0x14000fa04`
- `0x140013d4c`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140009118`
- `ntoskrnl!KeWaitForSingleObject` at `0x140009192`
- `ntoskrnl!KeWaitForSingleObject` at `0x140009118`
- `ntoskrnl!KeWaitForSingleObject` at `0x140009192`
- `ntoskrnl!DbgPrint` at `0x140009168`
- `ntoskrnl!DbgPrint` at `0x140009168`

## string_xrefs

- `0x140009159`: `\nUSBCCGP Watchdog: Thread 0x%p has waited %d minutes waiting to acquire %s\n`

## pseudocode

```c
NTSTATUS __fastcall AcquireMutex(PVOID Object, const char *a2, int a3)
{
  int v6; // edi
  NTSTATUS result; // eax
  int v8; // edx
  int v9; // r8d
  int v10; // edx
  int v11; // r8d
  int Timeout; // [rsp+20h] [rbp-38h]
  union _LARGE_INTEGER v13; // [rsp+78h] [rbp+20h] BYREF

  v13.QuadPart = -600000000;
  v6 = 0;
  for ( result = KeWaitForSingleObject(Object, Executive, 0, 0, &v13);
        result == 258;
        result = KeWaitForSingleObject(Object, Executive, 0, 0, &v13) )
  {
    DbgPrint(
      "\nUSBCCGP Watchdog: Thread 0x%p has waited %d minutes waiting to acquire %s\n",
      KeGetCurrentThread(),
      ++v6,
      a2);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_qds(a3, v10, v11, 63, Timeout, (char)KeGetCurrentThread(), v6, (__int64)a2);
  }
  if ( result < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    return WPP_RECORDER_SF_dqs(a3, v8, v9, 64, Timeout, result, (char)KeGetCurrentThread(), (__int64)a2);
  return result;
}

```

## disassembly

```asm
0x1400090e0  mov     [rsp+arg_0], rbx
0x1400090e5  mov     [rsp+arg_8], rbp
0x1400090ea  push    rsi
0x1400090eb  push    rdi
0x1400090ec  push    r14
0x1400090ee  sub     rsp, 40h
0x1400090f2  mov     rbp, r8
0x1400090f5  mov     qword ptr [rsp+58h+arg_18], 0FFFFFFFFDC3CBA00h
0x1400090fe  mov     rsi, rdx
0x140009101  lea     rax, [rsp+58h+arg_18]
0x140009106  xor     r8d, r8d; WaitMode
0x140009109  mov     [rsp+58h+Timeout], rax; Timeout
0x14000910e  xor     edx, edx; WaitReason
0x140009110  xor     r9d, r9d; Alertable
0x140009113  mov     rbx, rcx
0x140009116  xor     edi, edi
0x140009118  call    cs:__imp_KeWaitForSingleObject
0x14000911f  nop     dword ptr [rax+rax+00h]
0x140009124  lea     r14, WPP_RECORDER_INITIALIZED
0x14000912b  cmp     eax, 102h
0x140009130  jz      short loc_140009150
0x140009132  test    eax, eax
0x140009134  js      loc_1400091CE
0x14000913a  mov     rbx, [rsp+58h+arg_0]
0x14000913f  mov     rbp, [rsp+58h+arg_8]
0x140009144  add     rsp, 40h
0x140009148  pop     r14
0x14000914a  pop     rdi
0x14000914b  pop     rsi
0x14000914c  retn
0x140009150  mov     rdx, gs:188h
0x140009159  lea     rcx, Format; "\nUSBCCGP Watchdog: Thread 0x%p has wai"...
0x140009160  inc     edi
0x140009162  mov     r9, rsi
0x140009165  mov     r8d, edi
0x140009168  call    cs:__imp_DbgPrint
0x14000916f  nop     dword ptr [rax+rax+00h]
0x140009174  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14000917b  jnz     short loc_1400091A7
0x14000917d  lea     rax, [rsp+58h+arg_18]
0x140009182  xor     r9d, r9d; Alertable
0x140009185  xor     r8d, r8d; WaitMode
0x140009188  mov     [rsp+58h+Timeout], rax; Timeout
0x14000918d  xor     edx, edx; WaitReason
0x14000918f  mov     rcx, rbx; Object
0x140009192  call    cs:__imp_KeWaitForSingleObject
0x140009199  nop     dword ptr [rax+rax+00h]
0x14000919e  cmp     eax, 102h
0x1400091a3  jnz     short loc_140009132
0x1400091a5  jmp     short loc_140009150
0x1400091a7  mov     rax, gs:188h
0x1400091b0  mov     r9d, 3Fh ; '?'
0x1400091b6  mov     [rsp+58h+var_20], rsi
0x1400091bb  mov     rcx, rbp
0x1400091be  mov     dword ptr [rsp+58h+var_28], edi
0x1400091c2  mov     [rsp+58h+var_30], rax
0x1400091c7  call    WPP_RECORDER_SF_qds
0x1400091cc  jmp     short loc_14000917D
0x1400091ce  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x1400091d5  jz      loc_14000913A
0x1400091db  mov     rcx, gs:188h
0x1400091e4  mov     r9d, 40h ; '@'
0x1400091ea  mov     [rsp+58h+var_20], rsi
0x1400091ef  mov     [rsp+58h+var_28], rcx
0x1400091f4  mov     rcx, rbp
0x1400091f7  mov     dword ptr [rsp+58h+var_30], eax
0x1400091fb  call    WPP_RECORDER_SF_dqs
0x140009200  jmp     loc_14000913A
```
