# VhdmpiRemoveSurfaceOwnershipFromHandle

- ea: `0x1400bc14c`
- end: `0x1400bc24d`
- name: `VhdmpiRemoveSurfaceOwnershipFromHandle`
- size: `257`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14009d7a4`
- `0x1400bca98`

## callees

- `0x14001bc1c`
- `0x14001c088`
- `0x1400266a0`
- `0x140049460`
- `0x1400bbfb8`
- `0x1400bc0f8`
- `0x1400bc14c`

## import_xrefs

- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1400bc175`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1400bc175`
- `ntoskrnl!ExRundownCompleted` at `0x1400bc184`
- `ntoskrnl!ExRundownCompleted` at `0x1400bc184`
- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x1400bc19e`
- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x1400bc19e`

## pseudocode

```c
__int64 __fastcall VhdmpiRemoveSurfaceOwnershipFromHandle(__int64 a1, __int64 a2)
{
  __int64 v2; // r15
  char v5; // r14
  void *v6; // rcx
  __int64 v7; // rax

  v2 = *(_QWORD *)(a1 + 56);
  v5 = 0;
  VhdmpiDisableCachedRundowns();
  ExWaitForRundownProtectionRelease((PEX_RUNDOWN_REF)(a1 + 272));
  ExRundownCompleted((PEX_RUNDOWN_REF)(a1 + 272));
  v6 = *(void **)(a1 + 96);
  if ( v6 )
  {
    ObfDereferenceObjectWithTag(v6, 0x75444856u);
    *(_QWORD *)(a1 + 96) = 0;
  }
  VhdmpiAcquirePassiveLock(v2 + 112);
  if ( *(_QWORD *)(a1 + 80) == a2 )
  {
    v7 = *(_QWORD *)(a2 + 48);
    if ( v7 <= 0 )
      __fastfail(0xEu);
    if ( v7 <= 1 )
    {
      *(_BYTE *)(a2 + 65) = 1;
      v5 = 1;
    }
    else
    {
      VhdmpiReleaseSurfaceBackingStoreChainAccess(
        (struct VHD_SECURITY_CONTEXT *)(a1 + 16),
        *(struct _VHD_BACKING_STORE_HEADER **)(v2 + 144));
      VhdmpiAcquirePassiveLock(v2 + 184);
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
0x1400bc14c  push    rbx
0x1400bc14e  push    rbp
0x1400bc14f  push    rsi
0x1400bc150  push    rdi
0x1400bc151  push    r14
0x1400bc153  push    r15
0x1400bc155  sub     rsp, 28h
0x1400bc159  mov     r15, [rcx+38h]
0x1400bc15d  mov     rsi, rdx
0x1400bc160  mov     rdi, rcx
0x1400bc163  xor     r14b, r14b
0x1400bc166  call    VhdmpiDisableCachedRundowns
0x1400bc16b  lea     rbx, [rdi+110h]
0x1400bc172  mov     rcx, rbx; RunRef
0x1400bc175  call    cs:__imp_ExWaitForRundownProtectionRelease
0x1400bc17c  nop     dword ptr [rax+rax+00h]
0x1400bc181  mov     rcx, rbx; RunRef
0x1400bc184  call    cs:__imp_ExRundownCompleted
0x1400bc18b  nop     dword ptr [rax+rax+00h]
0x1400bc190  mov     rcx, [rdi+60h]; Object
0x1400bc194  test    rcx, rcx
0x1400bc197  jz      short loc_1400BC1B2
0x1400bc199  mov     edx, 75444856h; Tag
0x1400bc19e  call    cs:__imp_ObfDereferenceObjectWithTag
0x1400bc1a5  nop     dword ptr [rax+rax+00h]
0x1400bc1aa  mov     qword ptr [rdi+60h], 0
0x1400bc1b2  lea     rcx, [r15+70h]
0x1400bc1b6  call    VhdmpiAcquirePassiveLock
0x1400bc1bb  cmp     [rdi+50h], rsi
0x1400bc1bf  jnz     short loc_1400BC21F
0x1400bc1c1  mov     rax, [rsi+30h]
0x1400bc1c5  test    rax, rax
0x1400bc1c8  jg      short loc_1400BC1D1
0x1400bc1ca  mov     ecx, 0Eh
0x1400bc1cf  int     29h; Win8: RtlFailFast(ecx)
0x1400bc1d1  cmp     rax, 1
0x1400bc1d5  jle     short loc_1400BC218
0x1400bc1d7  mov     r8d, [rsi+38h]
0x1400bc1db  lea     rcx, [rdi+10h]; struct VHD_SECURITY_CONTEXT *
0x1400bc1df  mov     rdx, [r15+90h]; struct _VHD_BACKING_STORE_HEADER *
0x1400bc1e6  shr     r8d, 8
0x1400bc1ea  and     r8d, 1
0x1400bc1ee  call    VhdmpiReleaseSurfaceBackingStoreChainAccess
0x1400bc1f3  lea     rbx, [r15+0B8h]
0x1400bc1fa  mov     rcx, rbx
0x1400bc1fd  call    VhdmpiAcquirePassiveLock
0x1400bc202  dec     qword ptr [rsi+30h]
0x1400bc206  mov     rcx, rbx
0x1400bc209  mov     qword ptr [rdi+50h], 0
0x1400bc211  call    VhdmpiReleasePassiveLock
0x1400bc216  jmp     short loc_1400BC21F
0x1400bc218  mov     byte ptr [rsi+41h], 1
0x1400bc21c  mov     r14b, 1
0x1400bc21f  lea     rcx, [r15+70h]
0x1400bc223  call    VhdmpiReleasePassiveLock
0x1400bc228  test    r14b, r14b
0x1400bc22b  jz      short loc_1400BC237
0x1400bc22d  mov     dl, 1
0x1400bc22f  mov     rcx, rsi; struct _VHD_SURFACE *
0x1400bc232  call    VhdmpiHaltSurfaceOrWait
0x1400bc237  mov     rcx, rdi
0x1400bc23a  call    VhdmpiEnableCachedRundowns
0x1400bc23f  add     rsp, 28h
0x1400bc243  pop     r15
0x1400bc245  pop     r14
0x1400bc247  pop     rdi
0x1400bc248  pop     rsi
0x1400bc249  pop     rbp
0x1400bc24a  pop     rbx
0x1400bc24b  retn
```
