# SlbNatIpsInitializeProvider

- ea: `0x1400304e4`
- end: `0x14003058b`
- name: `SlbNatIpsInitializeProvider`
- size: `167`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140030f64`

## callees

- `0x1400304e4`

## import_xrefs

- `ntoskrnl!IoAllocateWorkItem` at `0x14003054b`
- `ntoskrnl!IoAllocateWorkItem` at `0x14003054b`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x140030516`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x140030516`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x140030538`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x140030538`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14003056a`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14003056a`

## pseudocode

```c
__int64 SlbNatIpsInitializeProvider()
{
  struct _EX_RUNDOWN_REF_CACHE_AWARE *CacheAwareRundownProtection; // rax

  SlbNatIpsIpv4Provider = 0;
  LOWORD(SlbNatIpsIpv4Provider) = 2;
  *(_OWORD *)&ProviderBindingContext = 0;
  xmmword_140027A40 = 0;
  CacheAwareRundownProtection = ExAllocateCacheAwareRundownProtection((POOL_TYPE)512, 0x70694E53u);
  *((_QWORD *)&SlbNatIpsIpv4Provider + 1) = CacheAwareRundownProtection;
  if ( !CacheAwareRundownProtection )
    return 3221225626LL;
  ExWaitForRundownProtectionReleaseCacheAware(CacheAwareRundownProtection);
  *((_QWORD *)&xmmword_140027A40 + 1) = IoAllocateWorkItem(deviceObject);
  if ( !*((_QWORD *)&xmmword_140027A40 + 1) )
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
0x1400304e4  sub     rsp, 28h
0x1400304e8  xorps   xmm0, xmm0
0x1400304eb  mov     eax, 2
0x1400304f0  movups  cs:SlbNatIpsIpv4Provider, xmm0
0x1400304f7  mov     edx, 70694E53h; PoolTag
0x1400304fc  mov     word ptr cs:SlbNatIpsIpv4Provider, ax
0x140030503  mov     ecx, 200h; PoolType
0x140030508  movups  cs:ProviderBindingContext, xmm0
0x14003050f  movups  cs:xmmword_140027A40, xmm0
0x140030516  call    cs:__imp_ExAllocateCacheAwareRundownProtection
0x14003051d  nop     dword ptr [rax+rax+00h]
0x140030522  mov     qword ptr cs:SlbNatIpsIpv4Provider+8, rax
0x140030529  test    rax, rax
0x14003052c  jnz     short loc_140030535
0x14003052e  mov     eax, 0C000009Ah
0x140030533  jmp     short loc_140030585
0x140030535  mov     rcx, rax; RunRef
0x140030538  call    cs:__imp_ExWaitForRundownProtectionReleaseCacheAware
0x14003053f  nop     dword ptr [rax+rax+00h]
0x140030544  mov     rcx, cs:deviceObject; DeviceObject
0x14003054b  call    cs:__imp_IoAllocateWorkItem
0x140030552  nop     dword ptr [rax+rax+00h]
0x140030557  mov     qword ptr cs:xmmword_140027A40+8, rax
0x14003055e  test    rax, rax
0x140030561  jnz     short loc_140030583
0x140030563  mov     rcx, qword ptr cs:SlbNatIpsIpv4Provider+8; RunRefCacheAware
0x14003056a  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x140030571  nop     dword ptr [rax+rax+00h]
0x140030576  mov     qword ptr cs:SlbNatIpsIpv4Provider+8, 0
0x140030581  jmp     short loc_14003052E
0x140030583  xor     eax, eax
0x140030585  add     rsp, 28h
0x140030589  retn
```
