# VsmmPhuStorepObjectRemoveAndFree

- ea: `0x1400b7ac8`
- end: `0x1400b7b48`
- name: `VsmmPhuStorepObjectRemoveAndFree`
- size: `128`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `11`
- callee_count: `2`
- tags: ``

## callers

- `0x140077b7c`
- `0x1400b0d94`
- `0x1400b1240`
- `0x1400b1314`
- `0x1400b1608`
- `0x1400b2bc8`
- `0x1400b3ab0`
- `0x1400b3dcc`
- `0x1400b4958`
- `0x1400b77dc`
- `0x1400b7f18`

## callees

- `0x1400b7ac8`
- `0x1400b8954`

## import_xrefs

- `ntoskrnl!RtlRbRemoveNode` at `0x1400b7b0c`
- `ntoskrnl!RtlRbRemoveNode` at `0x1400b7b0c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b7b20`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b7b20`

## pseudocode

```c
__int64 __fastcall VsmmPhuStorepObjectRemoveAndFree(__int64 a1, _DWORD *a2)
{
  __int64 v4; // rbx
  __int64 result; // rax

  switch ( a2[8] )
  {
    case 1:
      v4 = 128;
      break;
    case 2:
      v4 = 192;
      break;
    case 3:
      v4 = 96;
      break;
    default:
      return result;
  }
  RtlRbRemoveNode(a1 + 1248, a2);
  ExFreePoolWithTag(a2, 0x6D4D6456u);
  return VsmmPhuStorepSerializationChargeDecrease(a1, v4);
}

```

## disassembly

```asm
0x1400b7ac8  mov     [rsp+arg_0], rbx
0x1400b7acd  mov     [rsp+arg_8], rsi
0x1400b7ad2  push    rdi
0x1400b7ad3  sub     rsp, 20h
0x1400b7ad7  mov     r8d, [rdx+20h]
0x1400b7adb  mov     rdi, rdx
0x1400b7ade  mov     rsi, rcx
0x1400b7ae1  sub     r8d, 1
0x1400b7ae5  jz      short loc_1400B7B00
0x1400b7ae7  sub     r8d, 1
0x1400b7aeb  jz      short loc_1400B7AF9
0x1400b7aed  cmp     r8d, 1
0x1400b7af1  jnz     short loc_1400B7B37
0x1400b7af3  lea     ebx, [r8+5Fh]
0x1400b7af7  jmp     short loc_1400B7B05
0x1400b7af9  mov     ebx, 0C0h
0x1400b7afe  jmp     short loc_1400B7B05
0x1400b7b00  mov     ebx, 80h
0x1400b7b05  add     rcx, 4E0h
0x1400b7b0c  call    cs:__imp_RtlRbRemoveNode
0x1400b7b13  nop     dword ptr [rax+rax+00h]
0x1400b7b18  mov     edx, 6D4D6456h; Tag
0x1400b7b1d  mov     rcx, rdi; P
0x1400b7b20  call    cs:__imp_ExFreePoolWithTag
0x1400b7b27  nop     dword ptr [rax+rax+00h]
0x1400b7b2c  mov     rdx, rbx
0x1400b7b2f  mov     rcx, rsi
0x1400b7b32  call    VsmmPhuStorepSerializationChargeDecrease
0x1400b7b37  mov     rbx, [rsp+28h+arg_0]
0x1400b7b3c  mov     rsi, [rsp+28h+arg_8]
0x1400b7b41  add     rsp, 20h
0x1400b7b45  pop     rdi
0x1400b7b46  retn
```
