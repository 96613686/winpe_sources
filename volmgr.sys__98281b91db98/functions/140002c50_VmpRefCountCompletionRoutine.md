# VmpRefCountCompletionRoutine

- ea: `0x140002c50`
- end: `0x140002c81`
- name: `VmpRefCountCompletionRoutine`
- size: `49`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140002c50`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140002c6d`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140002c6d`

## pseudocode

```c
__int64 __fastcall VmpRefCountCompletionRoutine(__int64 a1, __int64 a2)
{
  __int64 v2; // rcx

  v2 = *(_QWORD *)(a1 + 64);
  if ( *(_BYTE *)(a2 + 65) )
    *(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) |= 1u;
  ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v2 + 112));
  return 0;
}

```

## disassembly

```asm
0x140002c50  sub     rsp, 28h
0x140002c54  cmp     byte ptr [rdx+41h], 0
0x140002c58  mov     rcx, [rcx+40h]
0x140002c5c  jz      short loc_140002C69
0x140002c5e  mov     rax, [rdx+0B8h]
0x140002c65  or      byte ptr [rax+3], 1
0x140002c69  mov     rcx, [rcx+70h]; RunRefCacheAware
0x140002c6d  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x140002c74  nop     dword ptr [rax+rax+00h]
0x140002c79  xor     eax, eax
0x140002c7b  add     rsp, 28h
0x140002c7f  retn
```
