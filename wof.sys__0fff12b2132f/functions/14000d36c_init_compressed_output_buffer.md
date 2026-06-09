# init_compressed_output_buffer

- ea: `0x14000d36c`
- end: `0x14000d3b2`
- name: `init_compressed_output_buffer`
- size: `70`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000a578`

## callees

- `0x14000d36c`
- `0x140011640`

## pseudocode

```c
__int64 __fastcall init_compressed_output_buffer(__int64 a1)
{
  __int64 result; // rax

  result = (*(__int64 (__fastcall **)(__int64))(a1 + 17312))(38912);
  *(_QWORD *)(a1 + 2176) = result;
  if ( result )
  {
    *(_QWORD *)(a1 + 2184) = result;
    *(_QWORD *)(a1 + 2192) = result + 38848;
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x14000d36c  push    rbx
0x14000d36e  sub     rsp, 20h
0x14000d372  mov     rax, [rcx+43A0h]
0x14000d379  mov     rbx, rcx
0x14000d37c  mov     ecx, 9800h
0x14000d381  call    _guard_dispatch_icall
0x14000d386  mov     [rbx+880h], rax
0x14000d38d  test    rax, rax
0x14000d390  jz      short loc_14000D3AB
0x14000d392  mov     [rbx+888h], rax
0x14000d399  add     rax, 97C0h
0x14000d39f  mov     [rbx+890h], rax
0x14000d3a6  mov     eax, 1
0x14000d3ab  add     rsp, 20h
0x14000d3af  pop     rbx
0x14000d3b0  retn
```
