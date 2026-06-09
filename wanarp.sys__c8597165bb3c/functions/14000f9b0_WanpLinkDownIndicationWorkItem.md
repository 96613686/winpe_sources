# WanpLinkDownIndicationWorkItem

- ea: `0x14000f9b0`
- end: `0x14000f9c1`
- name: `WanpLinkDownIndicationWorkItem`
- size: `17`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x14000f9c8`

## pseudocode

```c
void __fastcall WanpLinkDownIndicationWorkItem(void *a1)
{
  WanpLinkDownIndicationWorkItemImpl(a1, 1);
}

```

## disassembly

```asm
0x14000f9b0  sub     rsp, 28h
0x14000f9b4  mov     dl, 1
0x14000f9b6  call    WanpLinkDownIndicationWorkItemImpl
0x14000f9bb  add     rsp, 28h
0x14000f9bf  retn
```
