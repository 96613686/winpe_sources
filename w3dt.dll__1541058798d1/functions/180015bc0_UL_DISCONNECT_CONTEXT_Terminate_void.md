# UL_DISCONNECT_CONTEXT::Terminate(void)

- ea: `0x180015bc0`
- end: `0x180015be5`
- name: `?Terminate@UL_DISCONNECT_CONTEXT@@SAXXZ`
- size: `37`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001060`
- `0x180015a40`

## callees

- `0x180013544`
- `0x180015bc0`

## pseudocode

```c
void UL_DISCONNECT_CONTEXT::Terminate(void)
{
  if ( UL_DISCONNECT_CONTEXT::sm_pachDisconnects )
  {
    ALLOC_CACHE_HANDLER::`scalar deleting destructor'(UL_DISCONNECT_CONTEXT::sm_pachDisconnects);
    UL_DISCONNECT_CONTEXT::sm_pachDisconnects = 0;
  }
}

```

## disassembly

```asm
0x180015bc0  sub     rsp, 28h
0x180015bc4  mov     rcx, cs:?sm_pachDisconnects@UL_DISCONNECT_CONTEXT@@0PEAVALLOC_CACHE_HANDLER@@EA; this
0x180015bcb  test    rcx, rcx
0x180015bce  jz      short loc_180015BE0
0x180015bd0  call    ??_GALLOC_CACHE_HANDLER@@QEAAPEAXI@Z; ALLOC_CACHE_HANDLER::`scalar deleting destructor'(uint)
0x180015bd5  mov     cs:?sm_pachDisconnects@UL_DISCONNECT_CONTEXT@@0PEAVALLOC_CACHE_HANDLER@@EA, 0; ALLOC_CACHE_HANDLER * UL_DISCONNECT_CONTEXT::sm_pachDisconnects
0x180015be0  add     rsp, 28h
0x180015be4  retn
```
