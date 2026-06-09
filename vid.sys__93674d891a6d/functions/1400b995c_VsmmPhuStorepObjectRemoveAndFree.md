# VsmmPhuStorepObjectRemoveAndFree

- ea: `0x1400b995c`
- end: `0x1400b99dc`
- name: `VsmmPhuStorepObjectRemoveAndFree`
- size: `128`
- prototype: ``
- caller_count: `11`
- callee_count: `2`
- tags: ``

## callers

- `0x140078a58`
- `0x1400b2be4`
- `0x1400b3090`
- `0x1400b3164`
- `0x1400b3458`
- `0x1400b4aa0`
- `0x1400b59ac`
- `0x1400b5ccc`
- `0x1400b6858`
- `0x1400b9670`
- `0x1400b9dac`

## callees

- `0x1400b995c`
- `0x1400ba7e4`

## import_xrefs

- `ntoskrnl!RtlRbRemoveNode` at `0x1400b99a0`
- `ntoskrnl!RtlRbRemoveNode` at `0x1400b99a0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b99b4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b99b4`

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
0x1400b995c  mov     [rsp+arg_0], rbx
0x1400b9961  mov     [rsp+arg_8], rsi
0x1400b9966  push    rdi
0x1400b9967  sub     rsp, 20h
0x1400b996b  mov     r8d, [rdx+20h]
0x1400b996f  mov     rdi, rdx
0x1400b9972  mov     rsi, rcx
0x1400b9975  sub     r8d, 1
0x1400b9979  jz      short loc_1400B9994
0x1400b997b  sub     r8d, 1
0x1400b997f  jz      short loc_1400B998D
0x1400b9981  cmp     r8d, 1
0x1400b9985  jnz     short loc_1400B99CB
0x1400b9987  lea     ebx, [r8+5Fh]
0x1400b998b  jmp     short loc_1400B9999
0x1400b998d  mov     ebx, 0C0h
0x1400b9992  jmp     short loc_1400B9999
0x1400b9994  mov     ebx, 80h
0x1400b9999  add     rcx, 4E0h
0x1400b99a0  call    cs:__imp_RtlRbRemoveNode
0x1400b99a7  nop     dword ptr [rax+rax+00h]
0x1400b99ac  mov     edx, 6D4D6456h; Tag
0x1400b99b1  mov     rcx, rdi; P
0x1400b99b4  call    cs:__imp_ExFreePoolWithTag
0x1400b99bb  nop     dword ptr [rax+rax+00h]
0x1400b99c0  mov     rdx, rbx
0x1400b99c3  mov     rcx, rsi
0x1400b99c6  call    VsmmPhuStorepSerializationChargeDecrease
0x1400b99cb  mov     rbx, [rsp+28h+arg_0]
0x1400b99d0  mov     rsi, [rsp+28h+arg_8]
0x1400b99d5  add     rsp, 20h
0x1400b99d9  pop     rdi
0x1400b99da  retn
```
