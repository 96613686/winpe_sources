# DllEntryPoint

- ea: `0x18001c580`
- end: `0x18001c5bd`
- name: `DllEntryPoint`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18001c580`
- `0x18001c5c4`
- `0x18001c9a4`

## pseudocode

```c
BOOL __stdcall DllEntryPoint(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  if ( fdwReason == 1 )
    sub_18001C9A4();
  return sub_18001C5C4(hinstDLL, fdwReason, lpReserved);
}

```

## disassembly

```asm
0x18001c580  mov     [rsp+arg_0], rbx
0x18001c585  mov     [rsp+arg_8], rsi
0x18001c58a  push    rdi
0x18001c58b  sub     rsp, 20h
0x18001c58f  mov     rdi, r8
0x18001c592  mov     ebx, edx
0x18001c594  mov     rsi, rcx
0x18001c597  cmp     edx, 1
0x18001c59a  jnz     short loc_18001C5A1
0x18001c59c  call    sub_18001C9A4
0x18001c5a1  mov     r8, rdi
0x18001c5a4  mov     edx, ebx
0x18001c5a6  mov     rcx, rsi
0x18001c5a9  mov     rbx, [rsp+28h+arg_0]
0x18001c5ae  mov     rsi, [rsp+28h+arg_8]
0x18001c5b3  add     rsp, 20h
0x18001c5b7  pop     rdi
0x18001c5b8  jmp     sub_18001C5C4
```
