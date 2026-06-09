# DllGetActivationFactory$catch$3

- ea: `0x18000cff5`
- end: `0x18000d01b`
- name: `DllGetActivationFactory$catch$3`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000b554`

## pseudocode

```c
__int64 __fastcall DllGetActivationFactory_catch_3(wil *a1, __int64 a2)
{
  *(_DWORD *)(a2 + 32) = wil::ResultFromCaughtException(a1);
  return 0;
}

```

## disassembly

```asm
0x18000cff5  mov     [rsp+arg_8], rdx
0x18000cffa  push    rbp
0x18000cffb  sub     rsp, 20h
0x18000cfff  mov     rbp, rdx
0x18000d002  call    ?ResultFromCaughtException@wil@@YAJXZ; wil::ResultFromCaughtException(void)
0x18000d007  mov     [rbp+20h], eax
0x18000d00a  mov     rax, 0
0x18000d014  add     rsp, 20h
0x18000d018  pop     rbp
0x18000d019  retn
```
