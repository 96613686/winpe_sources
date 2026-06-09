# DllEntryPoint

- ea: `0x180003640`
- end: `0x18000367d`
- name: `DllEntryPoint`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180003504`
- `0x180003640`
- `0x180003be0`

## pseudocode

```c
BOOL __stdcall DllEntryPoint(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  if ( fdwReason == 1 )
    sub_180003BE0();
  return sub_180003504(hinstDLL, fdwReason, lpReserved);
}

```

## disassembly

```asm
0x180003640  mov     [rsp+arg_0], rbx
0x180003645  mov     [rsp+arg_8], rsi
0x18000364a  push    rdi
0x18000364b  sub     rsp, 20h
0x18000364f  mov     rdi, r8
0x180003652  mov     ebx, edx
0x180003654  mov     rsi, rcx
0x180003657  cmp     edx, 1
0x18000365a  jnz     short loc_180003661
0x18000365c  call    sub_180003BE0
0x180003661  mov     r8, rdi
0x180003664  mov     edx, ebx
0x180003666  mov     rcx, rsi
0x180003669  mov     rbx, [rsp+28h+arg_0]
0x18000366e  mov     rsi, [rsp+28h+arg_8]
0x180003673  add     rsp, 20h
0x180003677  pop     rdi
0x180003678  jmp     sub_180003504
```
