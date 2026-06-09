# DllGetActivationFactory$catch$3

- ea: `0x18000d2d9`
- end: `0x18000d2ff`
- name: `DllGetActivationFactory$catch$3`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000b804`

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
0x18000d2d9  mov     [rsp+arg_8], rdx
0x18000d2de  push    rbp
0x18000d2df  sub     rsp, 20h
0x18000d2e3  mov     rbp, rdx
0x18000d2e6  call    ?ResultFromCaughtException@wil@@YAJXZ; wil::ResultFromCaughtException(void)
0x18000d2eb  mov     [rbp+20h], eax
0x18000d2ee  mov     rax, 0
0x18000d2f8  add     rsp, 20h
0x18000d2fc  pop     rbp
0x18000d2fd  retn
```
