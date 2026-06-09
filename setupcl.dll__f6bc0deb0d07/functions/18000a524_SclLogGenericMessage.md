# SclLogGenericMessage

- ea: `0x18000a524`
- end: `0x18000a55e`
- name: `SclLogGenericMessage`
- size: `58`
- prototype: `__int64(__int64, int, int, int, __int64, char *, ...)`
- caller_count: `64`
- callee_count: `2`
- tags: ``

## callers

- `0x180001010`
- `0x180001764`
- `0x180001848`
- `0x180001a18`
- `0x180002010`
- `0x180002cc8`
- `0x180003408`
- `0x180004428`
- `0x180004844`
- `0x180004c88`
- `0x18000505c`
- `0x180005144`
- `0x18000548c`
- `0x1800065f8`
- `0x180006f24`
- `0x1800072d0`
- `0x1800073c4`
- `0x1800077a0`
- `0x180007b30`
- `0x180007fb0`
- `0x1800088bc`
- `0x180008be0`
- `0x180008e40`
- `0x180009438`
- `0x18000952c`
- `0x180009668`
- `0x180009904`
- `0x18000a190`
- `0x18000a394`
- `0x18000ac28`
- `0x18000acec`
- `0x18000b21c`
- `0x18000b530`
- `0x18000b738`
- `0x18000b90c`
- `0x18000bc68`
- `0x18000c21c`
- `0x18000c73c`
- `0x18000d220`
- `0x18000d620`
- `0x18000e4e4`
- `0x18000e740`
- `0x18000e8d4`
- `0x18000ea28`
- `0x18000eb38`
- `0x18000ec38`
- `0x18000f110`
- `0x18000f22c`
- `0x18000f438`
- `0x18000f4e4`

## callees

- `0x18000a524`
- `0x18000a564`

## pseudocode

```c
__int64 SclLogGenericMessage(__int64 a1, int a2, int a3, int a4, __int64 a5, char *a6, ...)
{
  __int64 result; // rax
  va_list va; // [rsp+90h] [rbp+38h] BYREF

  va_start(va, a6);
  if ( a1 )
    return SclLogGenericMessageV(a1, a2, a3, a4, a5, a6, va);
  return result;
}

```

## disassembly

```asm
0x18000a524  mov     r11, rsp
0x18000a527  sub     rsp, 58h
0x18000a52b  mov     qword ptr [r11-18h], 0
0x18000a533  test    rcx, rcx
0x18000a536  jz      short loc_18000A559
0x18000a538  lea     rax, [r11+38h]
0x18000a53c  mov     [r11-28h], rax
0x18000a540  mov     rax, [r11+30h]
0x18000a544  mov     [r11-30h], rax
0x18000a548  mov     rax, [rsp+58h+arg_20]
0x18000a550  mov     [r11-38h], rax
0x18000a554  call    SclLogGenericMessageV
0x18000a559  add     rsp, 58h
0x18000a55d  retn
```
