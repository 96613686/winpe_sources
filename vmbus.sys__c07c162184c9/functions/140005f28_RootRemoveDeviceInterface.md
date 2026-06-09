# RootRemoveDeviceInterface

- ea: `0x140005f28`
- end: `0x140005fc2`
- name: `RootRemoveDeviceInterface`
- size: `154`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400063d0`

## callees

- `0x140005b8c`
- `0x140005f28`
- `0x140005fc8`
- `0x140017190`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140005f5e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140005f5e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140005f9c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140005f9c`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140005f6e`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140005f6e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140005f90`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140005f90`

## pseudocode

```c
void __fastcall RootRemoveDeviceInterface(__int64 a1, wchar_t *a2)
{
  __int64 v4; // rdi
  UNICODE_STRING *DeviceInterfaceLocked; // rax

  v4 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01033 + 1616))(
         WdfDriverGlobals,
         a1,
         off_14001C0C8);
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v4 + 24));
  DeviceInterfaceLocked = (UNICODE_STRING *)RootDeviceFindDeviceInterfaceLocked(v4, 0, a2);
  if ( DeviceInterfaceLocked )
  {
    RootRemoveDeviceInterfaceLockedAndUnlock(a1, v4, DeviceInterfaceLocked);
  }
  else
  {
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v4 + 24));
    KeLeaveCriticalRegion();
  }
}

```

## disassembly

```asm
0x140005f28  push    rbx
0x140005f2a  push    rbp
0x140005f2b  push    rsi
0x140005f2c  push    rdi
0x140005f2d  sub     rsp, 28h
0x140005f31  mov     rax, cs:WdfFunctions_01033
0x140005f38  mov     rbx, rdx
0x140005f3b  mov     r8, cs:off_14001C0C8
0x140005f42  mov     rbp, rcx
0x140005f45  mov     rdx, rcx
0x140005f48  mov     rcx, cs:WdfDriverGlobals
0x140005f4f  mov     rax, [rax+650h]
0x140005f56  call    _guard_dispatch_icall
0x140005f5b  mov     rdi, rax
0x140005f5e  call    cs:__imp_KeEnterCriticalRegion
0x140005f65  nop     dword ptr [rax+rax+00h]
0x140005f6a  lea     rcx, [rdi+18h]; FastMutex
0x140005f6e  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140005f75  nop     dword ptr [rax+rax+00h]
0x140005f7a  mov     r8, rbx
0x140005f7d  xor     edx, edx
0x140005f7f  mov     rcx, rdi
0x140005f82  call    RootDeviceFindDeviceInterfaceLocked
0x140005f87  test    rax, rax
0x140005f8a  jnz     short loc_140005FAA
0x140005f8c  lea     rcx, [rdi+18h]; FastMutex
0x140005f90  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140005f97  nop     dword ptr [rax+rax+00h]
0x140005f9c  call    cs:__imp_KeLeaveCriticalRegion
0x140005fa3  nop     dword ptr [rax+rax+00h]
0x140005fa8  jmp     short loc_140005FB8
0x140005faa  mov     r8, rax
0x140005fad  mov     rdx, rdi
0x140005fb0  mov     rcx, rbp
0x140005fb3  call    RootRemoveDeviceInterfaceLockedAndUnlock
0x140005fb8  add     rsp, 28h
0x140005fbc  pop     rdi
0x140005fbd  pop     rsi
0x140005fbe  pop     rbp
0x140005fbf  pop     rbx
0x140005fc0  retn
```
