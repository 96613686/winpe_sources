# VmpReleaseRundownShared(VM_VOLUME_EXTENSION *)

- ea: `0x140003130`
- end: `0x14000314a`
- name: `?VmpReleaseRundownShared@@YAXPEAVVM_VOLUME_EXTENSION@@@Z`
- size: `26`
- prototype: `void __fastcall(struct VM_VOLUME_EXTENSION *)`
- caller_count: `4`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x14000e010`
- `0x140016130`
- `0x140016540`
- `0x140016aa0`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140003138`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140003138`

## pseudocode

```c
void __fastcall VmpReleaseRundownShared(PEX_RUNDOWN_REF_CACHE_AWARE *a1)
{
  ExReleaseRundownProtectionCacheAware(a1[14]);
}

```

## disassembly

```asm
0x140003130  sub     rsp, 28h
0x140003134  mov     rcx, [rcx+70h]; RunRefCacheAware
0x140003138  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x14000313f  nop     dword ptr [rax+rax+00h]
0x140003144  add     rsp, 28h
0x140003148  retn
```
