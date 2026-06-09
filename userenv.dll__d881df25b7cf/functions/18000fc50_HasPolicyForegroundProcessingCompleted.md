# HasPolicyForegroundProcessingCompleted

- ea: `0x18000fc50`
- end: `0x18000fc57`
- name: `HasPolicyForegroundProcessingCompleted`
- size: `7`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## import_xrefs

- `api-ms-win-security-grouppolicy-l1-1-0!HasPolicyForegroundProcessingCompletedInternal` at `0x18000fc50`

## pseudocode

```c
// attributes: thunk
__int64 HasPolicyForegroundProcessingCompleted()
{
  return HasPolicyForegroundProcessingCompletedInternal();
}

```

## disassembly

```asm
0x18000fc50  jmp     cs:__imp_HasPolicyForegroundProcessingCompletedInternal
```
