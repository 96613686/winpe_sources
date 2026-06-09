# SlbNatIpsInitializeProvider

- ea: `0x14002f3b4`
- end: `0x14002f45b`
- name: `SlbNatIpsInitializeProvider`
- size: `167`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14002fe34`

## callees

- `0x14002f3b4`

## import_xrefs

- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14002f43a`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14002f43a`
- `ntoskrnl!IoAllocateWorkItem` at `0x14002f41b`
- `ntoskrnl!IoAllocateWorkItem` at `0x14002f41b`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x14002f3e6`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x14002f3e6`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x14002f408`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x14002f408`

## pseudocode

```c
__int64 SlbNatIpsInitializeProvider()
{
  struct _EX_RUNDOWN_REF_CACHE_AWARE *CacheAwareRundownProtection; // rax

  SlbNatIpsIpv4Provider = 0;
  LOWORD(SlbNatIpsIpv4Provider) = 2;
  *(_OWORD *)&ProviderBindingContext = 0;
  xmmword_140026A40 = 0;
  CacheAwareRundownProtection = ExAllocateCacheAwareRundownProtection((POOL_TYPE)512, 0x70694E53u);
  *((_QWORD *)&SlbNatIpsIpv4Provider + 1) = CacheAwareRundownProtection;
  if ( !CacheAwareRundownProtection )
    return 3221225626LL;
  ExWaitForRundownProtectionReleaseCacheAware(CacheAwareRundownProtection);
  *((_QWORD *)&xmmword_140026A40 + 1) = IoAllocateWorkItem(deviceObject);
  if ( !*((_QWORD *)&xmmword_140026A40 + 1) )
  {
    ExFreeCacheAwareRundownProtection(*((PEX_RUNDOWN_REF_CACHE_AWARE *)&SlbNatIpsIpv4Provider + 1));
    *((_QWORD *)&SlbNatIpsIpv4Provider + 1) = 0;
    return 3221225626LL;
  }
  return 0;
}

```

## disassembly

```asm
0x14002f3b4  sub     rsp, 28h
0x14002f3b8  xorps   xmm0, xmm0
0x14002f3bb  mov     eax, 2
0x14002f3c0  movups  cs:SlbNatIpsIpv4Provider, xmm0
0x14002f3c7  mov     edx, 70694E53h; PoolTag
0x14002f3cc  mov     word ptr cs:SlbNatIpsIpv4Provider, ax
0x14002f3d3  mov     ecx, 200h; PoolType
0x14002f3d8  movups  cs:ProviderBindingContext, xmm0
0x14002f3df  movups  cs:xmmword_140026A40, xmm0
0x14002f3e6  call    cs:__imp_ExAllocateCacheAwareRundownProtection
0x14002f3ed  nop     dword ptr [rax+rax+00h]
0x14002f3f2  mov     qword ptr cs:SlbNatIpsIpv4Provider+8, rax
0x14002f3f9  test    rax, rax
0x14002f3fc  jnz     short loc_14002F405
0x14002f3fe  mov     eax, 0C000009Ah
0x14002f403  jmp     short loc_14002F455
0x14002f405  mov     rcx, rax; RunRef
0x14002f408  call    cs:__imp_ExWaitForRundownProtectionReleaseCacheAware
0x14002f40f  nop     dword ptr [rax+rax+00h]
0x14002f414  mov     rcx, cs:deviceObject; DeviceObject
0x14002f41b  call    cs:__imp_IoAllocateWorkItem
0x14002f422  nop     dword ptr [rax+rax+00h]
0x14002f427  mov     qword ptr cs:xmmword_140026A40+8, rax
0x14002f42e  test    rax, rax
0x14002f431  jnz     short loc_14002F453
0x14002f433  mov     rcx, qword ptr cs:SlbNatIpsIpv4Provider+8; RunRefCacheAware
0x14002f43a  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x14002f441  nop     dword ptr [rax+rax+00h]
0x14002f446  mov     qword ptr cs:SlbNatIpsIpv4Provider+8, 0
0x14002f451  jmp     short loc_14002F3FE
0x14002f453  xor     eax, eax
0x14002f455  add     rsp, 28h
0x14002f459  retn
```
