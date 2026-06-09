# CompleteFunctionIdleIrp

- ea: `0x140006f58`
- end: `0x140007019`
- name: `CompleteFunctionIdleIrp`
- size: `193`
- prototype: `__int64 __fastcall(PVOID PeekContext)`
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140005fc4`
- `0x140007844`
- `0x140007e70`
- `0x14000d630`
- `0x14000e128`
- `0x14002ced0`

## callees

- `0x1400054a0`
- `0x140006f58`
- `0x14000b4bc`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140006fe1`
- `ntoskrnl!IofCompleteRequest` at `0x140006fe1`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140007008`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140007008`
- `ntoskrnl!IoCsqRemoveNextIrp` at `0x140006f77`
- `ntoskrnl!IoCsqRemoveNextIrp` at `0x140006f77`

## pseudocode

```c
void __fastcall CompleteFunctionIdleIrp(char *PeekContext, int a2)
{
  __int64 v2; // rsi
  PIRP v4; // rax
  int v5; // edx
  IRP *v6; // rbx

  v2 = *((_QWORD *)PeekContext + 29);
  v4 = IoCsqRemoveNextIrp((PIO_CSQ)(PeekContext + 120), PeekContext);
  v6 = v4;
  if ( v4 )
  {
    v4->IoStatus.Status = a2;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v5) = 4;
      WPP_RECORDER_SF_qD(
        *(_QWORD *)(v2 + 1368),
        v5,
        7,
        33,
        (__int64)WPP_dd1e712d547938a03f2007c63d036cf9_Traceguids,
        (char)v4,
        a2);
    }
    IofCompleteRequest(v6, 0);
    UsbcReleaseRemoveLock(v2, v6);
    IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v2 + 200), v6, 0x20u);
  }
}

```

## disassembly

```asm
0x140006f58  mov     [rsp+arg_0], rbx
0x140006f5d  mov     [rsp+arg_8], rsi
0x140006f62  push    rdi
0x140006f63  sub     rsp, 40h
0x140006f67  mov     rsi, [rcx+0E8h]
0x140006f6e  mov     edi, edx
0x140006f70  mov     rdx, rcx; PeekContext
0x140006f73  add     rcx, 78h ; 'x'; Csq
0x140006f77  call    cs:__imp_IoCsqRemoveNextIrp
0x140006f7e  nop     dword ptr [rax+rax+00h]
0x140006f83  mov     rbx, rax
0x140006f86  test    rax, rax
0x140006f89  jnz     short loc_140006F9C
0x140006f8b  mov     rbx, [rsp+48h+arg_0]
0x140006f90  mov     rsi, [rsp+48h+arg_8]
0x140006f95  add     rsp, 40h
0x140006f99  pop     rdi
0x140006f9a  retn
0x140006f9c  mov     [rax+30h], edi
0x140006f9f  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140006fa6  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140006fad  jz      short loc_140006FDC
0x140006faf  mov     rcx, [rsi+558h]
0x140006fb6  lea     rax, WPP_dd1e712d547938a03f2007c63d036cf9_Traceguids
0x140006fbd  mov     r9d, 21h ; '!'
0x140006fc3  mov     [rsp+48h+var_18], edi
0x140006fc7  mov     [rsp+48h+var_20], rbx
0x140006fcc  mov     dl, 4
0x140006fce  mov     [rsp+48h+var_28], rax
0x140006fd3  lea     r8d, [r9-1Ah]
0x140006fd7  call    WPP_RECORDER_SF_qD
0x140006fdc  xor     edx, edx; PriorityBoost
0x140006fde  mov     rcx, rbx; Irp
0x140006fe1  call    cs:__imp_IofCompleteRequest
0x140006fe8  nop     dword ptr [rax+rax+00h]
0x140006fed  mov     rdx, rbx
0x140006ff0  mov     rcx, rsi
0x140006ff3  call    UsbcReleaseRemoveLock
0x140006ff8  lea     rcx, [rsi+0C8h]; RemoveLock
0x140006fff  mov     r8d, 20h ; ' '; RemlockSize
0x140007005  mov     rdx, rbx; Tag
0x140007008  call    cs:__imp_IoReleaseRemoveLockEx
0x14000700f  nop     dword ptr [rax+rax+00h]
0x140007014  jmp     loc_140006F8B
```
