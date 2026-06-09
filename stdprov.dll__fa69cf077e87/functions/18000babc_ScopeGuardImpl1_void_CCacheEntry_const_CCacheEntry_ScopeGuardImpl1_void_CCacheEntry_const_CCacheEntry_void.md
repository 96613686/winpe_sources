# ScopeGuardImpl1<void (*)(CCacheEntry const *),CCacheEntry *>::~ScopeGuardImpl1<void (*)(CCacheEntry const *),CCacheEntry *>(void)

- ea: `0x18000babc`
- end: `0x18000badb`
- name: `??1?$ScopeGuardImpl1@P6AXPEBVCCacheEntry@@@ZPEAV1@@@QEAA@XZ`
- size: `31`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x1800043c0`
- `0x18000f770`
- `0x180015cc0`
- `0x1800164b2`
- `0x1800164de`
- `0x18001662f`
- `0x18001665b`
- `0x180016a78`
- `0x180016a9c`

## callees

- `0x18000babc`
- `0x180017010`

## pseudocode

```c
__int64 __fastcall ScopeGuardImpl1<void (*)(CCacheEntry const *),CCacheEntry *>::~ScopeGuardImpl1<void (*)(CCacheEntry const *),CCacheEntry *>(
        __int64 a1)
{
  __int64 result; // rax

  result = a1;
  if ( !*(_BYTE *)a1 )
    return (*(__int64 (__fastcall **)(_QWORD))(a1 + 8))(*(_QWORD *)(a1 + 16));
  return result;
}

```

## disassembly

```asm
0x18000babc  sub     rsp, 28h
0x18000bac0  mov     rax, rcx
0x18000bac3  cmp     byte ptr [rcx], 0
0x18000bac6  jnz     short loc_18000BAD6
0x18000bac8  mov     rcx, [rcx+10h]
0x18000bacc  mov     rax, [rax+8]
0x18000bad0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bad5  nop
0x18000bad6  add     rsp, 28h
0x18000bada  retn
```
