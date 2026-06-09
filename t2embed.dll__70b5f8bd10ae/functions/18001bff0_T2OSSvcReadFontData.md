# T2OSSvcReadFontData

- ea: `0x18001bff0`
- end: `0x18001c01d`
- name: `T2OSSvcReadFontData`
- size: `45`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18001862c`
- `0x180019e18`
- `0x180021aa4`
- `0x180021d54`

## callees

- `0x18001bff0`
- `0x18002b010`

## pseudocode

```c
__int64 __fastcall T2OSSvcReadFontData(
        __int64 (__fastcall *a1)(__int64, __int64, _QWORD),
        __int64 a2,
        __int64 a3,
        unsigned int a4)
{
  __int64 result; // rax

  result = 0;
  if ( a1 )
    return a1(a2, a3, a4);
  return result;
}

```

## disassembly

```asm
0x18001bff0  push    rbx
0x18001bff2  sub     rsp, 20h
0x18001bff6  xor     eax, eax
0x18001bff8  mov     r11, r8
0x18001bffb  mov     rbx, rdx
0x18001bffe  mov     r10, rcx
0x18001c001  test    rcx, rcx
0x18001c004  jz      short loc_18001C017
0x18001c006  mov     r8d, r9d
0x18001c009  mov     rdx, r11
0x18001c00c  mov     rcx, rbx
0x18001c00f  mov     rax, r10
0x18001c012  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c017  add     rsp, 20h
0x18001c01b  pop     rbx
0x18001c01c  retn
```
