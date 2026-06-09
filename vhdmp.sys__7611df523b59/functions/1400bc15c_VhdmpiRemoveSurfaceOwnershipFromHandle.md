# VhdmpiRemoveSurfaceOwnershipFromHandle

- ea: `0x1400bc15c`
- end: `0x1400bc25d`
- name: `VhdmpiRemoveSurfaceOwnershipFromHandle`
- size: `257`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14009d7a4`
- `0x1400bcaa8`

## callees

- `0x14001b7fc`
- `0x14001bc68`
- `0x140026280`
- `0x140049070`
- `0x1400bbfc8`
- `0x1400bc108`
- `0x1400bc15c`

## import_xrefs

- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1400bc185`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1400bc185`
- `ntoskrnl!ExRundownCompleted` at `0x1400bc194`
- `ntoskrnl!ExRundownCompleted` at `0x1400bc194`
- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x1400bc1ae`
- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x1400bc1ae`

## pseudocode

```c
__int64 __fastcall VhdmpiRemoveSurfaceOwnershipFromHandle(__int64 a1, __int64 a2)
{
  __int64 v2; // r15
  char v5; // r14
  __int64 v6; // rdx
  __int64 v7; // r8
  void *v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rdx
  __int64 v11; // r8

  v2 = *(_QWORD *)(a1 + 56);
  v5 = 0;
  VhdmpiDisableCachedRundowns(a1);
  ExWaitForRundownProtectionRelease((PEX_RUNDOWN_REF)(a1 + 272));
  ExRundownCompleted((PEX_RUNDOWN_REF)(a1 + 272));
  v8 = *(void **)(a1 + 96);
  if ( v8 )
  {
    ObfDereferenceObjectWithTag(v8, 0x75444856u);
    *(_QWORD *)(a1 + 96) = 0;
  }
  VhdmpiAcquirePassiveLock(v2 + 112, v6, v7);
  if ( *(_QWORD *)(a1 + 80) == a2 )
  {
    v9 = *(_QWORD *)(a2 + 48);
    if ( v9 <= 0 )
      __fastfail(0xEu);
    if ( v9 <= 1 )
    {
      *(_BYTE *)(a2 + 65) = 1;
      v5 = 1;
    }
    else
    {
      VhdmpiReleaseSurfaceBackingStoreChainAccess(
        (struct VHD_SECURITY_CONTEXT *)(a1 + 16),
        *(struct _VHD_BACKING_STORE_HEADER **)(v2 + 144));
      VhdmpiAcquirePassiveLock(v2 + 184, v10, v11);
      --*(_QWORD *)(a2 + 48);
      *(_QWORD *)(a1 + 80) = 0;
      VhdmpiReleasePassiveLock(v2 + 184);
    }
  }
  VhdmpiReleasePassiveLock(v2 + 112);
  if ( v5 )
    VhdmpiHaltSurfaceOrWait((struct _VHD_SURFACE *)a2);
  return VhdmpiEnableCachedRundowns(a1);
}

```

## disassembly

```asm
0x1400bc15c  push    rbx
0x1400bc15e  push    rbp
0x1400bc15f  push    rsi
0x1400bc160  push    rdi
0x1400bc161  push    r14
0x1400bc163  push    r15
0x1400bc165  sub     rsp, 28h
0x1400bc169  mov     r15, [rcx+38h]
0x1400bc16d  mov     rsi, rdx
0x1400bc170  mov     rdi, rcx
0x1400bc173  xor     r14b, r14b
0x1400bc176  call    VhdmpiDisableCachedRundowns
0x1400bc17b  lea     rbx, [rdi+110h]
0x1400bc182  mov     rcx, rbx; RunRef
0x1400bc185  call    cs:__imp_ExWaitForRundownProtectionRelease
0x1400bc18c  nop     dword ptr [rax+rax+00h]
0x1400bc191  mov     rcx, rbx; RunRef
0x1400bc194  call    cs:__imp_ExRundownCompleted
0x1400bc19b  nop     dword ptr [rax+rax+00h]
0x1400bc1a0  mov     rcx, [rdi+60h]; Object
0x1400bc1a4  test    rcx, rcx
0x1400bc1a7  jz      short loc_1400BC1C2
0x1400bc1a9  mov     edx, 75444856h; Tag
0x1400bc1ae  call    cs:__imp_ObfDereferenceObjectWithTag
0x1400bc1b5  nop     dword ptr [rax+rax+00h]
0x1400bc1ba  mov     qword ptr [rdi+60h], 0
0x1400bc1c2  lea     rcx, [r15+70h]
0x1400bc1c6  call    VhdmpiAcquirePassiveLock
0x1400bc1cb  cmp     [rdi+50h], rsi
0x1400bc1cf  jnz     short loc_1400BC22F
0x1400bc1d1  mov     rax, [rsi+30h]
0x1400bc1d5  test    rax, rax
0x1400bc1d8  jg      short loc_1400BC1E1
0x1400bc1da  mov     ecx, 0Eh
0x1400bc1df  int     29h; Win8: RtlFailFast(ecx)
0x1400bc1e1  cmp     rax, 1
0x1400bc1e5  jle     short loc_1400BC228
0x1400bc1e7  mov     r8d, [rsi+38h]
0x1400bc1eb  lea     rcx, [rdi+10h]; struct VHD_SECURITY_CONTEXT *
0x1400bc1ef  mov     rdx, [r15+90h]; struct _VHD_BACKING_STORE_HEADER *
0x1400bc1f6  shr     r8d, 8
0x1400bc1fa  and     r8d, 1
0x1400bc1fe  call    VhdmpiReleaseSurfaceBackingStoreChainAccess
0x1400bc203  lea     rbx, [r15+0B8h]
0x1400bc20a  mov     rcx, rbx
0x1400bc20d  call    VhdmpiAcquirePassiveLock
0x1400bc212  dec     qword ptr [rsi+30h]
0x1400bc216  mov     rcx, rbx
0x1400bc219  mov     qword ptr [rdi+50h], 0
0x1400bc221  call    VhdmpiReleasePassiveLock
0x1400bc226  jmp     short loc_1400BC22F
0x1400bc228  mov     byte ptr [rsi+41h], 1
0x1400bc22c  mov     r14b, 1
0x1400bc22f  lea     rcx, [r15+70h]
0x1400bc233  call    VhdmpiReleasePassiveLock
0x1400bc238  test    r14b, r14b
0x1400bc23b  jz      short loc_1400BC247
0x1400bc23d  mov     dl, 1
0x1400bc23f  mov     rcx, rsi; struct _VHD_SURFACE *
0x1400bc242  call    VhdmpiHaltSurfaceOrWait
0x1400bc247  mov     rcx, rdi
0x1400bc24a  call    VhdmpiEnableCachedRundowns
0x1400bc24f  add     rsp, 28h
0x1400bc253  pop     r15
0x1400bc255  pop     r14
0x1400bc257  pop     rdi
0x1400bc258  pop     rsi
0x1400bc259  pop     rbp
0x1400bc25a  pop     rbx
0x1400bc25b  retn
```
