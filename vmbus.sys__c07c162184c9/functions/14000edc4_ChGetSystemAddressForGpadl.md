# ChGetSystemAddressForGpadl

- ea: `0x14000edc4`
- end: `0x14000eebf`
- name: `ChGetSystemAddressForGpadl`
- size: `251`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140007090`
- `0x14000b4f0`

## callees

- `0x1400038cc`
- `0x14000edc4`
- `0x14000f794`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x14000ee9f`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000ee9f`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000ee00`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000ee00`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000ee8d`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000ee8d`

## pseudocode

```c
void __fastcall ChGetSystemAddressForGpadl(__int64 a1, unsigned int a2, _QWORD *a3)
{
  __int64 v4; // rbx
  __int64 v7; // rcx
  PVOID v8; // rax
  __int64 v9; // [rsp+50h] [rbp+8h] BYREF

  *a3 = 0;
  v4 = *(_QWORD *)(a1 + 216);
  v9 = 0;
  ExAcquireFastMutex((PFAST_MUTEX)(v4 + 432));
  if ( (int)ChpLookupGpadlByHandleLocked(v4, a1, a2, &v9) >= 0 )
  {
    v7 = *(_QWORD *)(v9 + 24);
    if ( (*(_BYTE *)(v7 + 10) & 5) != 0 )
      v8 = *(PVOID *)(v7 + 24);
    else
      v8 = MmMapLockedPagesSpecifyCache((PMDL)v7, 0, MmCached, 0, 0, 0x40000010u);
    *a3 = v8;
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0
         && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_b9c76b9a14f83c2168b65499a7c535e1_Traceguids, a2);
  }
  ExReleaseFastMutex((PFAST_MUTEX)(v4 + 432));
}

```

## disassembly

```asm
0x14000edc4  mov     [rsp+arg_8], rbx
0x14000edc9  mov     [rsp+arg_10], rbp
0x14000edce  push    rsi
0x14000edcf  push    rdi
0x14000edd0  push    r14
0x14000edd2  sub     rsp, 30h
0x14000edd6  mov     qword ptr [r8], 0
0x14000eddd  mov     rdi, rcx
0x14000ede0  mov     rbx, [rcx+0D8h]
0x14000ede7  mov     rsi, r8
0x14000edea  mov     r14d, edx
0x14000eded  mov     [rsp+48h+arg_0], 0
0x14000edf6  lea     rbp, [rbx+1B0h]
0x14000edfd  mov     rcx, rbp; FastMutex
0x14000ee00  call    cs:__imp_ExAcquireFastMutex
0x14000ee07  nop     dword ptr [rax+rax+00h]
0x14000ee0c  lea     r9, [rsp+48h+arg_0]
0x14000ee11  mov     r8d, r14d
0x14000ee14  mov     rdx, rdi
0x14000ee17  mov     rcx, rbx
0x14000ee1a  call    ChpLookupGpadlByHandleLocked
0x14000ee1f  test    eax, eax
0x14000ee21  jns     short loc_14000EE5F
0x14000ee23  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ee2a  lea     rax, WPP_GLOBAL_Control
0x14000ee31  cmp     rcx, rax
0x14000ee34  jz      short loc_14000EE9C
0x14000ee36  test    dword ptr [rcx+2Ch], 200000h
0x14000ee3d  jz      short loc_14000EE9C
0x14000ee3f  cmp     byte ptr [rcx+29h], 2
0x14000ee43  jb      short loc_14000EE9C
0x14000ee45  mov     rcx, [rcx+18h]
0x14000ee49  lea     r8, WPP_b9c76b9a14f83c2168b65499a7c535e1_Traceguids
0x14000ee50  mov     edx, 0Ah
0x14000ee55  mov     r9d, r14d
0x14000ee58  call    WPP_SF_d
0x14000ee5d  jmp     short loc_14000EE9C
0x14000ee5f  mov     rax, [rsp+48h+arg_0]
0x14000ee64  mov     rcx, [rax+18h]; MemoryDescriptorList
0x14000ee68  test    byte ptr [rcx+0Ah], 5
0x14000ee6c  jz      short loc_14000EE74
0x14000ee6e  mov     rax, [rcx+18h]
0x14000ee72  jmp     short loc_14000EE99
0x14000ee74  xor     r9d, r9d; RequestedAddress
0x14000ee77  mov     [rsp+48h+Priority], 40000010h; Priority
0x14000ee7f  xor     edx, edx; AccessMode
0x14000ee81  mov     [rsp+48h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14000ee89  lea     r8d, [r9+1]; CacheType
0x14000ee8d  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14000ee94  nop     dword ptr [rax+rax+00h]
0x14000ee99  mov     [rsi], rax
0x14000ee9c  mov     rcx, rbp; FastMutex
0x14000ee9f  call    cs:__imp_ExReleaseFastMutex
0x14000eea6  nop     dword ptr [rax+rax+00h]
0x14000eeab  mov     rbx, [rsp+48h+arg_8]
0x14000eeb0  mov     rbp, [rsp+48h+arg_10]
0x14000eeb5  add     rsp, 30h
0x14000eeb9  pop     r14
0x14000eebb  pop     rdi
0x14000eebc  pop     rsi
0x14000eebd  retn
```
