# VmbChannelUpdateInterruptProcessor

- ea: `0x1400101c0`
- end: `0x1400101dd`
- name: `VmbChannelUpdateInterruptProcessor`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x140011ed0`

## pseudocode

```c
__int64 __fastcall VmbChannelUpdateInterruptProcessor(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(a1 + 2648))(*(_QWORD *)(a1 + 2368));
}

```

## disassembly

```asm
0x1400101c0  sub     rsp, 28h
0x1400101c4  mov     rax, [rcx+0A58h]
0x1400101cb  mov     rcx, [rcx+940h]
0x1400101d2  call    _guard_dispatch_icall
0x1400101d7  add     rsp, 28h
0x1400101db  retn
```
