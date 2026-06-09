# ChpReleaseOpenChannelState

- ea: `0x140010f54`
- end: `0x140010f9d`
- name: `ChpReleaseOpenChannelState`
- size: `73`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1400103d0`
- `0x140010b08`
- `0x140010ca0`

## callees

- `0x14000fe8c`
- `0x140010f54`
- `0x140010fd0`

## pseudocode

```c
__int64 __fastcall ChpReleaseOpenChannelState(__int64 a1)
{
  if ( *(_QWORD *)(a1 + 712) )
  {
    ChFreeSendMessage();
    *(_QWORD *)(a1 + 712) = 0;
  }
  *(_DWORD *)(a1 + 252) = 0;
  return ChDereferenceChannelInternal(a1, 20, 583);
}

```

## disassembly

```asm
0x140010f54  push    rbx
0x140010f56  sub     rsp, 20h
0x140010f5a  mov     rbx, rcx
0x140010f5d  mov     rcx, [rcx+2C8h]
0x140010f64  test    rcx, rcx
0x140010f67  jz      short loc_140010F79
0x140010f69  call    ChFreeSendMessage
0x140010f6e  mov     qword ptr [rbx+2C8h], 0
0x140010f79  mov     edx, 14h
0x140010f7e  mov     dword ptr [rbx+0FCh], 0
0x140010f88  mov     r8d, 247h
0x140010f8e  mov     rcx, rbx
0x140010f91  call    ChDereferenceChannelInternal
0x140010f96  add     rsp, 20h
0x140010f9a  pop     rbx
0x140010f9b  retn
```
