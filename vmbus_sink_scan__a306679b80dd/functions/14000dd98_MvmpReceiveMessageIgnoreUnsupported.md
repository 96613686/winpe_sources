# MvmpReceiveMessageIgnoreUnsupported

- ea: `0x14000dd98`
- end: `0x14000dddf`
- name: `MvmpReceiveMessageIgnoreUnsupported`
- size: `71`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x14000d300`
- `0x14000d410`
- `0x14000d620`
- `0x14000d910`
- `0x14000da50`

## callees

- `0x14000dd98`
- `0x14000e880`

## pseudocode

```c
char __fastcall MvmpReceiveMessageIgnoreUnsupported(__int64 a1, int a2, __int64 a3)
{
  char result; // al

  do
  {
    do
      result = MvmpReceiveMessageSynchronous(a1, a2, a3);
    while ( *(_DWORD *)(a3 + 4) == 1 );
  }
  while ( *(_DWORD *)(a3 + 4) == 2 );
  return result;
}

```

## disassembly

```asm
0x14000dd98  mov     [rsp+arg_0], rbx
0x14000dd9d  mov     [rsp+arg_8], rsi
0x14000dda2  push    rdi
0x14000dda3  sub     rsp, 20h
0x14000dda7  mov     rbx, r8
0x14000ddaa  mov     rdi, rdx
0x14000ddad  mov     rsi, rcx
0x14000ddb0  mov     r8, rbx
0x14000ddb3  mov     rdx, rdi
0x14000ddb6  mov     rcx, rsi
0x14000ddb9  call    MvmpReceiveMessageSynchronous
0x14000ddbe  mov     r9d, [rbx+4]
0x14000ddc2  sub     r9d, 1
0x14000ddc6  jz      short loc_14000DDB0
0x14000ddc8  cmp     r9d, 1
0x14000ddcc  jz      short loc_14000DDB0
0x14000ddce  mov     rbx, [rsp+28h+arg_0]
0x14000ddd3  mov     rsi, [rsp+28h+arg_8]
0x14000ddd8  add     rsp, 20h
0x14000dddc  pop     rdi
0x14000dddd  retn
```
