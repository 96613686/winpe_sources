# VmbChannelGetPacketDescriptor

- ea: `0x140005f80`
- end: `0x140005f96`
- name: `VmbChannelGetPacketDescriptor`
- size: `22`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140005f80`

## pseudocode

```c
__int64 __fastcall VmbChannelGetPacketDescriptor(__int64 a1, _DWORD *a2)
{
  __int64 result; // rax

  result = a1 + 160;
  if ( a2 )
    *a2 = 8 * *(unsigned __int16 *)(a1 + 164);
  return result;
}

```

## disassembly

```asm
0x140005f80  lea     rax, [rcx+0A0h]
0x140005f87  test    rdx, rdx
0x140005f8a  jz      short locret_140005F95
0x140005f8c  movzx   ecx, word ptr [rax+4]
0x140005f90  shl     ecx, 3
0x140005f93  mov     [rdx], ecx
0x140005f95  retn
```
