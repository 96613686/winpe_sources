# EfiTranslateFilePath

- ea: `0x180014444`
- end: `0x1800144a0`
- name: `EfiTranslateFilePath`
- size: `92`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180012dfc`
- `0x180014784`

## callees

- `0x180014094`
- `0x180014444`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall EfiTranslateFilePath(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  if ( !EfipApisInitialized )
    EfiApiInitialize();
  if ( EfipTranslateFilePath )
    return EfipTranslateFilePath(a1, 3, a3, a4);
  else
    return 3221225474LL;
}

```

## disassembly

```asm
0x180014444  mov     [rsp+arg_0], rbx
0x180014449  mov     [rsp+arg_8], rsi
0x18001444e  push    rdi
0x18001444f  sub     rsp, 30h
0x180014453  cmp     cs:EfipApisInitialized, 0
0x18001445a  mov     rbx, r9
0x18001445d  mov     rdi, r8
0x180014460  mov     rsi, rcx
0x180014463  jnz     short loc_18001446A
0x180014465  call    EfiApiInitialize
0x18001446a  mov     rax, cs:EfipTranslateFilePath
0x180014471  test    rax, rax
0x180014474  jz      short loc_18001448B
0x180014476  mov     r9, rbx
0x180014479  mov     r8, rdi
0x18001447c  mov     edx, 3
0x180014481  mov     rcx, rsi
0x180014484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014489  jmp     short loc_180014490
0x18001448b  mov     eax, 0C0000002h
0x180014490  mov     rbx, [rsp+38h+arg_0]
0x180014495  mov     rsi, [rsp+38h+arg_8]
0x18001449a  add     rsp, 30h
0x18001449e  pop     rdi
0x18001449f  retn
```
