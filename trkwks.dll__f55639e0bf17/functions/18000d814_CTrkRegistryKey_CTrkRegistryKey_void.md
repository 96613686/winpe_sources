# CTrkRegistryKey::~CTrkRegistryKey(void)

- ea: `0x18000d814`
- end: `0x18000d832`
- name: `??1CTrkRegistryKey@@QEAA@XZ`
- size: `30`
- prototype: `void __fastcall(CTrkRegistryKey *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000c638`
- `0x18000ef50`

## callees

- `0x18000d838`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d82b`

## pseudocode

```c
void __fastcall CTrkRegistryKey::~CTrkRegistryKey(CTrkRegistryKey *this)
{
  CTrkRegistryKey::Close(this);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
}

```

## disassembly

```asm
0x18000d814  push    rbx
0x18000d816  sub     rsp, 20h
0x18000d81a  mov     rbx, rcx
0x18000d81d  call    ?Close@CTrkRegistryKey@@AEAAXXZ; CTrkRegistryKey::Close(void)
0x18000d822  lea     rcx, [rbx+8]
0x18000d826  add     rsp, 20h
0x18000d82a  pop     rbx
0x18000d82b  jmp     cs:__imp_DeleteCriticalSection
```
