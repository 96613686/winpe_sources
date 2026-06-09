# SclLogTimingEvent

- ea: `0x18000a69c`
- end: `0x18000a6e6`
- name: `SclLogTimingEvent`
- size: `74`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800065f8`
- `0x180010f44`
- `0x1800111bc`
- `0x1800117e4`

## callees

- `0x18000a69c`
- `0x180018010`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18000a6bb`
- `ntdll!EtwEventWrite` at `0x18000a6bb`

## pseudocode

```c

```

## disassembly

```asm
0x18000a69c  mov     [rsp+arg_0], rbx
0x18000a6a1  push    rdi
0x18000a6a2  sub     rsp, 20h
0x18000a6a6  mov     rbx, rcx
0x18000a6a9  mov     rdi, r8
0x18000a6ac  mov     rcx, [rcx+20h]
0x18000a6b0  test    rcx, rcx
0x18000a6b3  jz      short loc_18000A6C1
0x18000a6b5  xor     r9d, r9d
0x18000a6b8  xor     r8d, r8d
0x18000a6bb  call    cs:__imp_EtwEventWrite
0x18000a6c1  mov     rax, [rbx+10h]
0x18000a6c5  test    rax, rax
0x18000a6c8  jz      short loc_18000A6DB
0x18000a6ca  mov     r8, [rbx+18h]
0x18000a6ce  mov     rdx, rdi
0x18000a6d1  mov     ecx, 1
0x18000a6d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6db  mov     rbx, [rsp+28h+arg_0]
0x18000a6e0  add     rsp, 20h
0x18000a6e4  pop     rdi
0x18000a6e5  retn
```
