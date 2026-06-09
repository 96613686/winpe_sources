# DllEntryPoint

- ea: `0x180002890`
- end: `0x1800028cd`
- name: `DllEntryPoint`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180002754`
- `0x180002890`
- `0x18000302c`

## pseudocode

```c
BOOL __stdcall DllEntryPoint(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  if ( fdwReason == 1 )
    sub_18000302C();
  return sub_180002754(hinstDLL, fdwReason, lpReserved);
}

```

## disassembly

```asm
0x180002890  mov     [rsp+arg_0], rbx
0x180002895  mov     [rsp+arg_8], rsi
0x18000289a  push    rdi
0x18000289b  sub     rsp, 20h
0x18000289f  mov     rdi, r8
0x1800028a2  mov     ebx, edx
0x1800028a4  mov     rsi, rcx
0x1800028a7  cmp     edx, 1
0x1800028aa  jnz     short loc_1800028B1
0x1800028ac  call    sub_18000302C
0x1800028b1  mov     r8, rdi
0x1800028b4  mov     edx, ebx
0x1800028b6  mov     rcx, rsi
0x1800028b9  mov     rbx, [rsp+28h+arg_0]
0x1800028be  mov     rsi, [rsp+28h+arg_8]
0x1800028c3  add     rsp, 20h
0x1800028c7  pop     rdi
0x1800028c8  jmp     sub_180002754
```
