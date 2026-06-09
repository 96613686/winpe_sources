# DateTimeEventWrite(_EVENT_DESCRIPTOR const *,ulong,_EVENT_DATA_DESCRIPTOR *)

- ea: `0x18000ed64`
- end: `0x18000ed8b`
- name: `?DateTimeEventWrite@@YAXPEBU_EVENT_DESCRIPTOR@@KPEAU_EVENT_DATA_DESCRIPTOR@@@Z`
- size: `39`
- prototype: `void __fastcall(const struct _EVENT_DESCRIPTOR *, unsigned int, struct _EVENT_DATA_DESCRIPTOR *)`
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000edbc`
- `0x18000eec0`
- `0x18000ef8c`
- `0x18000f060`
- `0x18001bb7c`
- `0x18001f360`
- `0x18001fd0c`

## callees

- `0x18000ed64`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18000ed80`
- `ntdll!EtwEventWrite` at `0x18000ed80`

## pseudocode

```c
void __fastcall DateTimeEventWrite(
        const struct _EVENT_DESCRIPTOR *a1,
        unsigned int a2,
        struct _EVENT_DATA_DESCRIPTOR *a3)
{
  if ( g_hEtwRegHandle )
    EtwEventWrite(g_hEtwRegHandle, a1, a2, a3);
}

```

## disassembly

```asm
0x18000ed64  sub     rsp, 28h
0x18000ed68  mov     rax, rcx
0x18000ed6b  mov     rcx, cs:?g_hEtwRegHandle@@3_KA; unsigned __int64 g_hEtwRegHandle
0x18000ed72  test    rcx, rcx
0x18000ed75  jz      short loc_18000ED86
0x18000ed77  mov     r9, r8
0x18000ed7a  mov     r8d, edx
0x18000ed7d  mov     rdx, rax
0x18000ed80  call    cs:__imp_EtwEventWrite
0x18000ed86  add     rsp, 28h
0x18000ed8a  retn
```
