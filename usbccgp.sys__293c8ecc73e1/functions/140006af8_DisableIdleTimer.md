# DisableIdleTimer

- ea: `0x140006af8`
- end: `0x140006d3a`
- name: `DisableIdleTimer`
- size: `578`
- prototype: ``
- caller_count: `6`
- callee_count: `6`
- tags: ``

## callers

- `0x140004078`
- `0x140004f50`
- `0x140006630`
- `0x140006d40`
- `0x14000b670`
- `0x140028800`

## callees

- `0x140006af8`
- `0x140007020`
- `0x140008040`
- `0x14000fa04`
- `0x140013d4c`
- `0x14002a018`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x140006ba9`
- `ntoskrnl!KeReleaseMutex` at `0x140006ba9`
- `ntoskrnl!KeWaitForSingleObject` at `0x140006b51`
- `ntoskrnl!KeWaitForSingleObject` at `0x140006ccb`
- `ntoskrnl!KeWaitForSingleObject` at `0x140006b51`
- `ntoskrnl!KeWaitForSingleObject` at `0x140006ccb`
- `ntoskrnl!DbgPrint` at `0x140006c9e`
- `ntoskrnl!DbgPrint` at `0x140006c9e`

## string_xrefs

- `0x140006c8f`: `\nUSBCCGP Watchdog: Thread 0x%p has waited %d minutes waiting to acquire %s\n`

## pseudocode

```c
void __fastcall DisableIdleTimer(__int64 a1, __int64 a2, int a3)
{
  char v3; // si
  __int64 v5; // r14
  struct _KMUTANT *v6; // rbp
  int v7; // edi
  NTSTATUS i; // eax
  int v9; // edx
  int v10; // r8d
  int v11; // edi
  int v12; // edx
  int v13; // r8d
  int Timeout; // [rsp+20h] [rbp-68h]
  _UNKNOWN *retaddr; // [rsp+88h] [rbp+0h]
  union _LARGE_INTEGER v16; // [rsp+90h] [rbp+8h] BYREF
  int v17; // [rsp+A0h] [rbp+18h]

  v17 = a3;
  v3 = a3;
  if ( *(_BYTE *)(a1 + 1376) == 1 )
    return;
  v5 = *(_QWORD *)(a1 + 1368);
  v6 = (struct _KMUTANT *)(a1 + 904);
  v16.QuadPart = -600000000;
  v7 = 0;
  for ( i = KeWaitForSingleObject((PVOID)(a1 + 904), Executive, 0, 0, &v16);
        i == 258;
        i = KeWaitForSingleObject(v6, Executive, 0, 0, &v16) )
  {
    DbgPrint(
      "\nUSBCCGP Watchdog: Thread 0x%p has waited %d minutes waiting to acquire %s\n",
      KeGetCurrentThread(),
      ++v7,
      "idleTimerStateMutex");
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_qds(v5, v12, v13, 63, Timeout, (char)KeGetCurrentThread(), v7, (__int64)"idleTimerStateMutex");
  }
  if ( i >= 0 )
    goto LABEL_5;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_SF_dqs(v5, v9, v10, 64, Timeout, i, (char)KeGetCurrentThread(), (__int64)"idleTimerStateMutex");
LABEL_5:
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_qccccqd(
        *(_QWORD *)(a1 + 1368),
        v9,
        v10,
        58,
        Timeout,
        *(_QWORD *)(a1 + 32),
        SHIBYTE(v17),
        SBYTE2(v17),
        SBYTE1(v17),
        v3,
        (char)retaddr,
        *(_DWORD *)(a1 + 896));
  }
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 896));
  v11 = *(_DWORD *)(a1 + 856);
  if ( ((v11 - 1) & 0xFFFFFFFD) == 0 )
  {
    *(_DWORD *)(a1 + 856) = 2;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = 4;
      WPP_RECORDER_SF_qLL(
        *(_QWORD *)(a1 + 1368),
        v9,
        7,
        59,
        (__int64)WPP_dd1e712d547938a03f2007c63d036cf9_Traceguids,
        *(_QWORD *)(a1 + 32),
        v11,
        2);
    }
    if ( v11 == 1 )
      StopIdleTimer(a1);
  }
  KeReleaseMutex(v6, 0);
}

```

## disassembly

```asm
0x140006af8  mov     r11, rsp
0x140006afb  mov     [r11+10h], rbx
0x140006aff  mov     [r11+20h], rbp
0x140006b03  mov     [r11+18h], r8d
0x140006b07  push    rsi
0x140006b08  push    rdi
0x140006b09  push    r12
0x140006b0b  push    r14
0x140006b0d  push    r15
0x140006b0f  sub     rsp, 60h
0x140006b13  cmp     byte ptr [rcx+560h], 1
0x140006b1a  mov     esi, r8d
0x140006b1d  mov     rbx, rcx
0x140006b20  jz      loc_140006BB5
0x140006b26  mov     r14, [rcx+558h]
0x140006b2d  lea     rbp, [rcx+388h]
0x140006b34  lea     rax, [r11+8]
0x140006b38  mov     qword ptr [r11+8], 0FFFFFFFFDC3CBA00h
0x140006b40  mov     rcx, rbp; Object
0x140006b43  mov     [r11-68h], rax
0x140006b47  xor     edi, edi
0x140006b49  xor     r9d, r9d; Alertable
0x140006b4c  xor     r8d, r8d; WaitMode
0x140006b4f  xor     edx, edx; WaitReason
0x140006b51  call    cs:__imp_KeWaitForSingleObject
0x140006b58  nop     dword ptr [rax+rax+00h]
0x140006b5d  lea     r12, aIdletimerstate; "idleTimerStateMutex"
0x140006b64  lea     r15, WPP_RECORDER_INITIALIZED
0x140006b6b  mov     ecx, eax
0x140006b6d  cmp     eax, 102h
0x140006b72  jz      loc_140006C86
0x140006b78  test    eax, eax
0x140006b7a  js      loc_140006D03
0x140006b80  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140006b87  jnz     loc_140006C29
0x140006b8d  lock inc dword ptr [rbx+380h]
0x140006b94  mov     edi, [rbx+358h]
0x140006b9a  lea     eax, [rdi-1]
0x140006b9d  test    eax, 0FFFFFFFDh
0x140006ba2  jz      short loc_140006BCF
0x140006ba4  xor     edx, edx; Wait
0x140006ba6  mov     rcx, rbp; Mutex
0x140006ba9  call    cs:__imp_KeReleaseMutex
0x140006bb0  nop     dword ptr [rax+rax+00h]
0x140006bb5  lea     r11, [rsp+88h+var_28]
0x140006bba  mov     rbx, [r11+38h]
0x140006bbe  mov     rbp, [r11+48h]
0x140006bc2  mov     rsp, r11
0x140006bc5  pop     r15
0x140006bc7  pop     r14
0x140006bc9  pop     r12
0x140006bcb  pop     rdi
0x140006bcc  pop     rsi
0x140006bcd  retn
0x140006bcf  mov     eax, 2
0x140006bd4  mov     [rbx+358h], eax
0x140006bda  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140006be1  jnz     short loc_140006BF2
0x140006be3  cmp     edi, 1
0x140006be6  jnz     short loc_140006BA4
0x140006be8  mov     rcx, rbx
0x140006beb  call    StopIdleTimer
0x140006bf0  jmp     short loc_140006BA4
0x140006bf2  mov     rcx, [rbx+558h]
0x140006bf9  mov     r9d, 3Bh ; ';'
0x140006bff  mov     dword ptr [rsp+88h+var_50], eax
0x140006c03  mov     dl, 4
0x140006c05  mov     rax, [rbx+20h]
0x140006c09  mov     dword ptr [rsp+88h+var_58], edi
0x140006c0d  mov     [rsp+88h+var_60], rax
0x140006c12  lea     r8d, [r9-34h]
0x140006c16  lea     rax, WPP_dd1e712d547938a03f2007c63d036cf9_Traceguids
0x140006c1d  mov     [rsp+88h+Timeout], rax
0x140006c22  call    WPP_RECORDER_SF_qLL
0x140006c27  jmp     short loc_140006BE3
0x140006c29  mov     eax, [rbx+380h]
0x140006c2f  mov     r9d, 3Ah ; ':'
0x140006c35  mov     rcx, [rsp+88h]
0x140006c3d  mov     [rsp+88h+var_30], eax
0x140006c41  mov     al, [rsp+88h+arg_11]
0x140006c48  mov     [rsp+88h+var_38], rcx
0x140006c4d  mov     rcx, [rbx+558h]
0x140006c54  mov     [rsp+88h+var_40], sil
0x140006c59  mov     [rsp+88h+var_48], al
0x140006c5d  mov     al, [rsp+88h+arg_12]
0x140006c64  mov     byte ptr [rsp+88h+var_50], al
0x140006c68  mov     al, [rsp+88h+arg_13]
0x140006c6f  mov     byte ptr [rsp+88h+var_58], al
0x140006c73  mov     rax, [rbx+20h]
0x140006c77  mov     [rsp+88h+var_60], rax
0x140006c7c  call    WPP_RECORDER_SF_qccccqd
0x140006c81  jmp     loc_140006B8D
0x140006c86  mov     rdx, gs:188h
0x140006c8f  lea     rcx, Format; "\nUSBCCGP Watchdog: Thread 0x%p has wai"...
0x140006c96  inc     edi
0x140006c98  mov     r9, r12
0x140006c9b  mov     r8d, edi
0x140006c9e  call    cs:__imp_DbgPrint
0x140006ca5  nop     dword ptr [rax+rax+00h]
0x140006caa  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140006cb1  jnz     short loc_140006CDC
0x140006cb3  lea     rax, [rsp+88h+arg_0]
0x140006cbb  xor     r9d, r9d; Alertable
0x140006cbe  xor     r8d, r8d; WaitMode
0x140006cc1  mov     [rsp+88h+Timeout], rax; Timeout
0x140006cc6  xor     edx, edx; WaitReason
0x140006cc8  mov     rcx, rbp; Object
0x140006ccb  call    cs:__imp_KeWaitForSingleObject
0x140006cd2  nop     dword ptr [rax+rax+00h]
0x140006cd7  jmp     loc_140006B6B
0x140006cdc  mov     rax, gs:188h
0x140006ce5  mov     r9d, 3Fh ; '?'
0x140006ceb  mov     [rsp+88h+var_50], r12
0x140006cf0  mov     rcx, r14
0x140006cf3  mov     dword ptr [rsp+88h+var_58], edi
0x140006cf7  mov     [rsp+88h+var_60], rax
0x140006cfc  call    WPP_RECORDER_SF_qds
0x140006d01  jmp     short loc_140006CB3
0x140006d03  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140006d0a  jz      loc_140006B8D
0x140006d10  mov     rax, gs:188h
0x140006d19  mov     r9d, 40h ; '@'
0x140006d1f  mov     [rsp+88h+var_50], r12
0x140006d24  mov     [rsp+88h+var_58], rax
0x140006d29  mov     dword ptr [rsp+88h+var_60], ecx
0x140006d2d  mov     rcx, r14
0x140006d30  call    WPP_RECORDER_SF_dqs
0x140006d35  jmp     loc_140006B80
```
