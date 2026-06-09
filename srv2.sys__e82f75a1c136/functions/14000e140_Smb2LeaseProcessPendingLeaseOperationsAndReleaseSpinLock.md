# Smb2LeaseProcessPendingLeaseOperationsAndReleaseSpinLock

- ea: `0x14000e140`
- end: `0x14000e335`
- name: `Smb2LeaseProcessPendingLeaseOperationsAndReleaseSpinLock`
- size: `501`
- prototype: ``
- caller_count: `14`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000989c`
- `0x14000ac30`
- `0x14000ad08`
- `0x14000c680`
- `0x14000ca00`
- `0x14000cdf0`
- `0x14000dfb0`
- `0x14000e5f0`
- `0x140015af8`
- `0x14001c2d0`
- `0x14002eccc`
- `0x14002edbc`
- `0x14002f01c`
- `0x14002f0a4`

## callees

- `0x140004020`
- `0x140004960`
- `0x1400051dc`
- `0x14000e140`
- `0x14000e470`
- `0x140016180`
- `0x1400229ac`

## import_xrefs

- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14000e224`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14000e224`
- `ntoskrnl!RtlInitAnsiString` at `0x14000e2ae`
- `ntoskrnl!RtlInitAnsiString` at `0x14000e2ae`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000e17e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000e1dc`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000e17e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000e1dc`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14000e23f`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14000e23f`
- `HAL!KeQueryPerformanceCounter` at `0x14000e277`
- `HAL!KeQueryPerformanceCounter` at `0x14000e277`

## string_xrefs

- `0x14000e294`: `Srv2PostToThreadPool`

## pseudocode

```c
void __fastcall Smb2LeaseProcessPendingLeaseOperationsAndReleaseSpinLock(__int64 a1, KIRQL a2)
{
  int v4; // ecx
  int v5; // r8d
  bool v6; // zf
  __int64 v7; // rdi
  __int64 v8; // rdi
  LARGE_INTEGER PerformanceCounter; // rax
  __int64 v10; // rdx
  __int64 v11; // rax
  int v12; // edx
  int v13; // ecx
  struct _STRING DestinationString; // [rsp+40h] [rbp-18h] BYREF

  v4 = *(_DWORD *)(a1 + 144);
  if ( (v4 & 2) == 0 && (*(_DWORD *)(a1 + 140) & 2) != 0 )
  {
    v5 = *(_DWORD *)(a1 + 104);
    if ( v5 != 128 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qDD(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_3d8eb6e120b9357e636b6f5c4c47d988_Traceguids, a1, v5, 128);
        v4 = *(_DWORD *)(a1 + 144);
      }
      *(_DWORD *)(a1 + 104) = 128;
    }
  }
  if ( (v4 & 1) == 0 && (unsigned int)Smb2LeaseSelectNextPendingOperation(a1) )
  {
    *(_DWORD *)(a1 + 144) |= 1u;
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 96), a2);
    *(_QWORD *)(a1 + 48) = Smb2LeasePendingOperationsStateMachineCallback;
    Smb2ReferenceLease(a1);
    v6 = *(_DWORD *)(a1 + 8) == 5;
    *(_DWORD *)(a1 + 72) = 0;
    if ( v6 )
    {
      v6 = *(_BYTE *)(a1 + 600) == 0;
      DestinationString = 0;
      if ( !v6 )
      {
        PerformanceCounter = KeQueryPerformanceCounter(0);
        LOBYTE(v10) = 1;
        v11 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))SRV2_PERF_UPDATE_PERF_COUNTER)(
                a1 + 584,
                v10,
                (LARGE_INTEGER)PerformanceCounter.QuadPart);
        *(_BYTE *)(a1 + 712) = 1;
        *(_QWORD *)(a1 + 720) = v11;
        RtlInitAnsiString(&DestinationString, "Srv2PostToThreadPool");
        if ( (Microsoft_Windows_SMBServerEnableBits & 4) != 0 )
          McTemplateK0qqhsr2_EtwWriteTransfer(
            v13,
            v12,
            a1 + 584,
            1,
            135,
            DestinationString.Length,
            (__int64)DestinationString.Buffer);
      }
    }
    v7 = *(_QWORD *)(*(_QWORD *)(a1 + 64) + 136LL);
    v8 = *(_QWORD *)(v7 + 8LL * KeGetCurrentNodeNumber() + 8);
    if ( !ExpInterlockedPushEntrySList((PSLIST_HEADER)v8, (PSLIST_ENTRY)(a1 + 32)) )
    {
      if ( *(_WORD *)(v8 + 66) )
        RfspThreadPoolNodeWakeIdleWorker((struct _KEVENT *)v8);
    }
  }
  else
  {
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 96), a2);
  }
}

```

## disassembly

```asm
0x14000e140  mov     [rsp+arg_0], rbx
0x14000e145  push    rdi
0x14000e146  sub     rsp, 50h
0x14000e14a  mov     rbx, rcx
0x14000e14d  movzx   edi, dl
0x14000e150  mov     ecx, [rcx+90h]
0x14000e156  test    cl, 2
0x14000e159  jnz     short loc_14000E165
0x14000e15b  mov     eax, [rbx+8Ch]
0x14000e161  test    al, 2
0x14000e163  jnz     short loc_14000E196
0x14000e165  test    cl, 1
0x14000e168  jnz     short loc_14000E176
0x14000e16a  mov     rcx, rbx
0x14000e16d  call    Smb2LeaseSelectNextPendingOperation
0x14000e172  test    eax, eax
0x14000e174  jnz     short loc_14000E1CD
0x14000e176  lea     rcx, [rbx+60h]; SpinLock
0x14000e17a  movzx   edx, dil; NewIrql
0x14000e17e  call    cs:__imp_KeReleaseSpinLock
0x14000e185  nop     dword ptr [rax+rax+00h]
0x14000e18a  mov     rbx, [rsp+58h+arg_0]
0x14000e18f  add     rsp, 50h
0x14000e193  pop     rdi
0x14000e194  retn
0x14000e196  mov     r8d, [rbx+68h]
0x14000e19a  cmp     r8d, 80h
0x14000e1a1  jz      short loc_14000E165
0x14000e1a3  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000e1aa  lea     rax, WPP_GLOBAL_Control
0x14000e1b1  cmp     r10, rax
0x14000e1b4  jz      short loc_14000E1C4
0x14000e1b6  test    dword ptr [r10+2Ch], 40000000h
0x14000e1be  jnz     loc_14000E2FA
0x14000e1c4  mov     dword ptr [rbx+68h], 80h
0x14000e1cb  jmp     short loc_14000E165
0x14000e1cd  or      dword ptr [rbx+90h], 1
0x14000e1d4  lea     rcx, [rbx+60h]; SpinLock
0x14000e1d8  movzx   edx, dil; NewIrql
0x14000e1dc  call    cs:__imp_KeReleaseSpinLock
0x14000e1e3  nop     dword ptr [rax+rax+00h]
0x14000e1e8  lea     rax, Smb2LeasePendingOperationsStateMachineCallback
0x14000e1ef  mov     rcx, rbx
0x14000e1f2  mov     [rbx+30h], rax
0x14000e1f6  call    Smb2ReferenceLease
0x14000e1fb  cmp     dword ptr [rbx+8], 5
0x14000e1ff  mov     dword ptr [rbx+48h], 0
0x14000e206  jnz     short loc_14000E219
0x14000e208  cmp     byte ptr [rbx+258h], 0
0x14000e20f  xorps   xmm0, xmm0
0x14000e212  movups  xmmword ptr [rsp+58h+DestinationString.Length], xmm0
0x14000e217  jnz     short loc_14000E275
0x14000e219  mov     rax, [rbx+40h]
0x14000e21d  mov     rdi, [rax+88h]
0x14000e224  call    cs:__imp_KeGetCurrentNodeNumber
0x14000e22b  nop     dword ptr [rax+rax+00h]
0x14000e230  movzx   eax, ax
0x14000e233  lea     rdx, [rbx+20h]; ListEntry
0x14000e237  mov     rdi, [rdi+rax*8+8]
0x14000e23c  mov     rcx, rdi; ListHead
0x14000e23f  call    cs:__imp_ExpInterlockedPushEntrySList
0x14000e246  nop     dword ptr [rax+rax+00h]
0x14000e24b  test    rax, rax
0x14000e24e  jnz     loc_14000E18A
0x14000e254  movzx   edx, word ptr [rdi+42h]
0x14000e258  cmp     ax, dx
0x14000e25b  jz      loc_14000E18A
0x14000e261  mov     rcx, rdi
0x14000e264  call    RfspThreadPoolNodeWakeIdleWorker
0x14000e269  mov     rbx, [rsp+58h+arg_0]
0x14000e26e  add     rsp, 50h
0x14000e272  pop     rdi
0x14000e273  retn
0x14000e275  xor     ecx, ecx; PerformanceFrequency
0x14000e277  call    cs:__imp_KeQueryPerformanceCounter
0x14000e27e  nop     dword ptr [rax+rax+00h]
0x14000e283  mov     dl, 1
0x14000e285  lea     rcx, [rbx+248h]
0x14000e28c  mov     r8, rax
0x14000e28f  call    SRV2_PERF_UPDATE_PERF_COUNTER
0x14000e294  lea     rdx, SourceString; "Srv2PostToThreadPool"
0x14000e29b  mov     byte ptr [rbx+2C8h], 1
0x14000e2a2  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x14000e2a7  mov     [rbx+2D0h], rax
0x14000e2ae  call    cs:__imp_RtlInitAnsiString
0x14000e2b5  nop     dword ptr [rax+rax+00h]
0x14000e2ba  test    cs:Microsoft_Windows_SMBServerEnableBits, 4
0x14000e2c1  jz      loc_14000E219
0x14000e2c7  mov     rax, [rsp+58h+DestinationString.Buffer]
0x14000e2cc  lea     r8, [rbx+248h]
0x14000e2d3  mov     [rsp+58h+var_28], rax
0x14000e2d8  mov     r9d, 1
0x14000e2de  movzx   eax, [rsp+58h+DestinationString.Length]
0x14000e2e3  mov     word ptr [rsp+58h+var_30], ax
0x14000e2e8  mov     [rsp+58h+var_38], 187h
0x14000e2f0  call    McTemplateK0qqhsr2_EtwWriteTransfer
0x14000e2f5  jmp     loc_14000E219
0x14000e2fa  cmp     byte ptr [r10+29h], 2
0x14000e2ff  jb      loc_14000E1C4
0x14000e305  mov     rcx, [r10+18h]
0x14000e309  mov     edx, 21h ; '!'
0x14000e30e  mov     [rsp+58h+var_30], 80h
0x14000e316  mov     r9, rbx
0x14000e319  mov     [rsp+58h+var_38], r8d
0x14000e31e  lea     r8, WPP_3d8eb6e120b9357e636b6f5c4c47d988_Traceguids
0x14000e325  call    WPP_SF_qDD
0x14000e32a  mov     ecx, [rbx+90h]
0x14000e330  jmp     loc_14000E1C4
```
