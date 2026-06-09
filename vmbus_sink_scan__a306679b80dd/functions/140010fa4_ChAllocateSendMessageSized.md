# ChAllocateSendMessageSized

- ea: `0x140010fa4`
- end: `0x140010fca`
- name: `ChAllocateSendMessageSized`
- size: `38`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x14000f158`
- `0x1400104c8`
- `0x140010834`
- `0x140011c40`
- `0x140011dd8`
- `0x14002dbf0`
- `0x14002de40`

## callees

- `0x140010fa4`
- `0x14001270c`

## pseudocode

```c
_QWORD *__fastcall ChAllocateSendMessageSized(__int64 a1, int a2, int a3)
{
  _QWORD *result; // rax

  result = XPartAllocateSendMessage(a1, a2, 0, 0);
  if ( result )
  {
    result = (_QWORD *)result[6];
    *(_DWORD *)result = a3;
  }
  return result;
}

```

## disassembly

```asm
0x140010fa4  push    rbx
0x140010fa6  sub     rsp, 20h
0x140010faa  mov     ebx, r8d
0x140010fad  xor     r9d, r9d
0x140010fb0  xor     r8d, r8d
0x140010fb3  call    XPartAllocateSendMessage
0x140010fb8  test    rax, rax
0x140010fbb  jz      short loc_140010FC3
0x140010fbd  mov     rax, [rax+30h]
0x140010fc1  mov     [rax], ebx
0x140010fc3  add     rsp, 20h
0x140010fc7  pop     rbx
0x140010fc8  retn
```
