# SmpDeallocSavedRegistryEntry

- ea: `0x14000b408`
- end: `0x14000b45b`
- name: `SmpDeallocSavedRegistryEntry`
- size: `83`
- prototype: `__int64 __fastcall(PVOID BaseAddress)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x14000d494`
- `0x140012f60`

## callees

- `0x14000b408`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x14000b437`
- `ntdll!RtlFreeHeap` at `0x14000b44f`
- `ntdll!RtlFreeHeap` at `0x14000b437`
- `ntdll!RtlFreeHeap` at `0x14000b44f`
- `ntdll!RtlFreeUnicodeString` at `0x14000b419`
- `ntdll!RtlFreeUnicodeString` at `0x14000b419`

## pseudocode

```c
BOOLEAN __fastcall SmpDeallocSavedRegistryEntry(struct _UNICODE_STRING *BaseAddress)
{
  void *v2; // r8
  BOOLEAN result; // al

  if ( BaseAddress )
  {
    RtlFreeUnicodeString(BaseAddress + 2);
    v2 = *(void **)&BaseAddress[3].Length;
    if ( v2 )
      RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, v2);
    return RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, BaseAddress);
  }
  return result;
}

```

## disassembly

```asm
0x14000b408  test    rcx, rcx
0x14000b40b  jz      short locret_14000B45A
0x14000b40d  push    rbx
0x14000b40e  sub     rsp, 20h
0x14000b412  mov     rbx, rcx
0x14000b415  add     rcx, 20h ; ' '; UnicodeString
0x14000b419  call    cs:__imp_RtlFreeUnicodeString
0x14000b41f  mov     r8, [rbx+30h]; BaseAddress
0x14000b423  test    r8, r8
0x14000b426  jz      short loc_14000B43D
0x14000b428  mov     rcx, gs:60h
0x14000b431  xor     edx, edx; Flags
0x14000b433  mov     rcx, [rcx+30h]; HeapHandle
0x14000b437  call    cs:__imp_RtlFreeHeap
0x14000b43d  mov     rcx, gs:60h
0x14000b446  mov     r8, rbx; BaseAddress
0x14000b449  xor     edx, edx; Flags
0x14000b44b  mov     rcx, [rcx+30h]; HeapHandle
0x14000b44f  call    cs:__imp_RtlFreeHeap
0x14000b455  add     rsp, 20h
0x14000b459  pop     rbx
0x14000b45a  retn
```
