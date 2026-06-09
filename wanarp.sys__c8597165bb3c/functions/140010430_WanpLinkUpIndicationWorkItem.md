# WanpLinkUpIndicationWorkItem

- ea: `0x140010430`
- end: `0x140010441`
- name: `WanpLinkUpIndicationWorkItem`
- size: `17`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140010448`

## pseudocode

```c
void __fastcall WanpLinkUpIndicationWorkItem(__int64 *a1)
{
  WanpLinkUpIndicationWorkItemImpl(a1, 1);
}

```

## disassembly

```asm
0x140010430  sub     rsp, 28h
0x140010434  mov     dl, 1
0x140010436  call    WanpLinkUpIndicationWorkItemImpl
0x14001043b  add     rsp, 28h
0x14001043f  retn
```
