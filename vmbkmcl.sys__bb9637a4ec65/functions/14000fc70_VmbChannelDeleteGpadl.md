# VmbChannelDeleteGpadl

- ea: `0x14000fc70`
- end: `0x14000fc94`
- name: `VmbChannelDeleteGpadl`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140011ed0`

## pseudocode

```c
__int64 __fastcall VmbChannelDeleteGpadl(__int64 a1)
{
  _InterlockedDecrement((volatile signed __int32 *)(a1 + 2816));
  return (*(__int64 (__fastcall **)(_QWORD))(a1 + 2456))(*(_QWORD *)(a1 + 2368));
}

```

## disassembly

```asm
0x14000fc70  sub     rsp, 28h
0x14000fc74  lock dec dword ptr [rcx+0B00h]
0x14000fc7b  mov     rax, [rcx+998h]
0x14000fc82  mov     rcx, [rcx+940h]
0x14000fc89  call    _guard_dispatch_icall
0x14000fc8e  add     rsp, 28h
0x14000fc92  retn
```
