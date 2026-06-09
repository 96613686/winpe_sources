# __GSHandlerCheckCommon

- ea: `0x140020328`
- end: `0x140020388`
- name: `__GSHandlerCheckCommon`
- size: `96`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140020304`
- `0x140020464`
- `0x1400205e0`

## callees

- `0x14001aa60`
- `0x140020328`

## pseudocode

```c
__int64 __fastcall _GSHandlerCheckCommon(__int64 a1, __int64 a2)
{
  __int64 v2; // rcx
  __int64 result; // rax

  v2 = *(unsigned int *)(*(_QWORD *)(a2 + 16) + 8LL);
  result = *(_QWORD *)(a2 + 8);
  if ( (*(_BYTE *)(v2 + result + 3) & 0xF) != 0 )
    return *(_BYTE *)(v2 + result + 3) & 0xF0;
  return result;
}

```

## disassembly

```asm
0x140020328  push    rbx
0x14002032a  mov     r11d, [r8]
0x14002032d  mov     rbx, rdx
0x140020330  and     r11d, 0FFFFFFF8h
0x140020334  mov     r9, rcx
0x140020337  test    byte ptr [r8], 4
0x14002033b  mov     r10, rcx
0x14002033e  jz      short loc_140020353
0x140020340  mov     eax, [r8+8]
0x140020344  movsxd  r10, dword ptr [r8+4]
0x140020348  neg     eax
0x14002034a  add     r10, rcx
0x14002034d  movsxd  rcx, eax
0x140020350  and     r10, rcx
0x140020353  movsxd  rax, r11d
0x140020356  mov     rdx, [rax+r10]
0x14002035a  mov     rax, [rbx+10h]
0x14002035e  mov     ecx, [rax+8]
0x140020361  mov     rax, [rbx+8]
0x140020365  test    byte ptr [rcx+rax+3], 0Fh
0x14002036a  jz      short loc_14002037C
0x14002036c  movzx   eax, byte ptr [rcx+rax+3]
0x140020371  mov     ecx, 0FFFFFFF0h
0x140020376  and     rax, rcx
0x140020379  add     r9, rax
0x14002037c  xor     r9, rdx
0x14002037f  mov     rcx, r9; StackCookie
0x140020382  pop     rbx
0x140020383  jmp     __security_check_cookie
```
