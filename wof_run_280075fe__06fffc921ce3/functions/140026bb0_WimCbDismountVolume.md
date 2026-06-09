# WimCbDismountVolume

- ea: `0x140026bb0`
- end: `0x140026cf2`
- name: `WimCbDismountVolume`
- size: `322`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x14000fb90`
- `0x140022cf4`
- `0x140022e2c`
- `0x140026bb0`
- `0x14002deb0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140026cdb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140026cdb`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140026c2f`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140026c87`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140026ccf`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140026c2f`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140026c87`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140026ccf`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140026bf6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140026bf6`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140026c0e`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140026c54`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140026caf`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140026c0e`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140026c54`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140026caf`

## pseudocode

```c
void __fastcall WimCbDismountVolume(__int64 a1)
{
  _QWORD *i; // rbx
  __int64 v3; // r8
  volatile signed __int32 *v4; // rsi
  volatile signed __int32 *v5; // rbx

  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_Z(
      WPP_GLOBAL_Control->AttachedDevice,
      20,
      WPP_ea753fa6f9d83b7566c7b1a5ff90ffd6_Traceguids,
      a1 - (unsigned int)dword_14001A2FC + 64);
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a1 - (unsigned int)dword_14001A2FC));
  for ( i = *(_QWORD **)(a1 + 8); i != (_QWORD *)(a1 + 8); i = (_QWORD *)*i )
  {
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a1 - (unsigned int)dword_14001A2FC));
    WimFSFDismountOverlay((__int64)i, 1, v3);
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a1 - (unsigned int)dword_14001A2FC));
  }
  v4 = *(volatile signed __int32 **)(a1 + 24);
  if ( v4 != (volatile signed __int32 *)(a1 + 24) )
  {
    do
    {
      _InterlockedIncrement(v4 + 14);
      v5 = *(volatile signed __int32 **)v4;
      ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a1 - (unsigned int)dword_14001A2FC));
      WimFSFSuspendOverlaysForBackingFile(v4);
      WimFSFDereferenceBackingFile((PVOID)v4);
      ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a1 - (unsigned int)dword_14001A2FC));
      v4 = v5;
    }
    while ( v5 != (volatile signed __int32 *)(a1 + 24) );
  }
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a1 - (unsigned int)dword_14001A2FC));
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x140026bb0  push    rbx
0x140026bb2  push    rsi
0x140026bb3  push    rdi
0x140026bb4  push    r14
0x140026bb6  sub     rsp, 28h
0x140026bba  mov     rdi, rcx
0x140026bbd  mov     rcx, cs:WPP_GLOBAL_Control
0x140026bc4  mov     eax, [rcx+2Ch]
0x140026bc7  test    al, 8
0x140026bc9  jz      short loc_140026BF6
0x140026bcb  cmp     byte ptr [rcx+29h], 4
0x140026bcf  jb      short loc_140026BF6
0x140026bd1  mov     eax, cs:dword_14001A2FC
0x140026bd7  lea     r8, WPP_ea753fa6f9d83b7566c7b1a5ff90ffd6_Traceguids
0x140026bde  mov     rcx, [rcx+18h]
0x140026be2  mov     r9, rdi
0x140026be5  sub     r9, rax
0x140026be8  mov     edx, 14h
0x140026bed  add     r9, 40h ; '@'
0x140026bf1  call    WPP_SF_Z
0x140026bf6  call    cs:__imp_KeEnterCriticalRegion
0x140026bfd  nop     dword ptr [rax+rax+00h]
0x140026c02  mov     eax, cs:dword_14001A2FC
0x140026c08  mov     rcx, rdi
0x140026c0b  sub     rcx, rax; FastMutex
0x140026c0e  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140026c15  nop     dword ptr [rax+rax+00h]
0x140026c1a  lea     rsi, [rdi+8]
0x140026c1e  mov     rbx, [rsi]
0x140026c21  jmp     short loc_140026C63
0x140026c23  mov     eax, cs:dword_14001A2FC
0x140026c29  mov     rcx, rdi
0x140026c2c  sub     rcx, rax; FastMutex
0x140026c2f  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140026c36  nop     dword ptr [rax+rax+00h]
0x140026c3b  mov     edx, 1
0x140026c40  mov     rcx, rbx
0x140026c43  call    WimFSFDismountOverlay
0x140026c48  mov     eax, cs:dword_14001A2FC
0x140026c4e  mov     rcx, rdi
0x140026c51  sub     rcx, rax; FastMutex
0x140026c54  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140026c5b  nop     dword ptr [rax+rax+00h]
0x140026c60  mov     rbx, [rbx]
0x140026c63  cmp     rbx, rsi
0x140026c66  jnz     short loc_140026C23
0x140026c68  lea     r14, [rdi+18h]
0x140026c6c  mov     rsi, [r14]
0x140026c6f  cmp     rsi, r14
0x140026c72  jz      short loc_140026CC3
0x140026c74  lock inc dword ptr [rsi+38h]
0x140026c78  mov     eax, cs:dword_14001A2FC
0x140026c7e  mov     rcx, rdi
0x140026c81  mov     rbx, [rsi]
0x140026c84  sub     rcx, rax; FastMutex
0x140026c87  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140026c8e  nop     dword ptr [rax+rax+00h]
0x140026c93  mov     rcx, rsi
0x140026c96  call    WimFSFSuspendOverlaysForBackingFile
0x140026c9b  mov     rcx, rsi; P
0x140026c9e  call    WimFSFDereferenceBackingFile
0x140026ca3  mov     eax, cs:dword_14001A2FC
0x140026ca9  mov     rcx, rdi
0x140026cac  sub     rcx, rax; FastMutex
0x140026caf  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140026cb6  nop     dword ptr [rax+rax+00h]
0x140026cbb  mov     rsi, rbx
0x140026cbe  cmp     rbx, r14
0x140026cc1  jnz     short loc_140026C74
0x140026cc3  mov     eax, cs:dword_14001A2FC
0x140026cc9  sub     rdi, rax
0x140026ccc  mov     rcx, rdi; FastMutex
0x140026ccf  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140026cd6  nop     dword ptr [rax+rax+00h]
0x140026cdb  call    cs:__imp_KeLeaveCriticalRegion
0x140026ce2  nop     dword ptr [rax+rax+00h]
0x140026ce7  add     rsp, 28h
0x140026ceb  pop     r14
0x140026ced  pop     rdi
0x140026cee  pop     rsi
0x140026cef  pop     rbx
0x140026cf0  retn
```
