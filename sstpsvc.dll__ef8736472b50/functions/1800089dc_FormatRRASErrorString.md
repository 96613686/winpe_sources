# FormatRRASErrorString

- ea: `0x1800089dc`
- end: `0x180008a12`
- name: `FormatRRASErrorString`
- size: `54`
- prototype: ``
- caller_count: `63`
- callee_count: `1`
- tags: ``

## callers

- `0x1800012b0`
- `0x180001b40`
- `0x180001fe0`
- `0x180002320`
- `0x180002aac`
- `0x180003010`
- `0x180003620`
- `0x180003bc0`
- `0x180004950`
- `0x180004bdc`
- `0x180004d10`
- `0x180004fb0`
- `0x180005110`
- `0x18000530c`
- `0x1800056e0`
- `0x1800059f0`
- `0x180005e30`
- `0x180006960`
- `0x1800071cc`
- `0x1800080dc`
- `0x18000823c`
- `0x180009c3c`
- `0x18000a300`
- `0x18000a59c`
- `0x18000a710`
- `0x18000aa44`
- `0x18000abe0`
- `0x18000accc`
- `0x18000adb8`
- `0x18000afb0`
- `0x18000b9c8`
- `0x18000bd24`
- `0x18000c4c4`
- `0x18000c768`
- `0x18000ca68`
- `0x18000d2ec`
- `0x18000d444`
- `0x18000d730`
- `0x18000d978`
- `0x18000da7c`
- `0x18000dd70`
- `0x18000df08`
- `0x18000ebd0`
- `0x18000f6e0`
- `0x18001072c`
- `0x180010d80`
- `0x180010fe8`
- `0x1800111f4`
- `0x180011444`
- `0x180011a14`

## callees

- `0x180008a64`

## pseudocode

```c
HRESULT FormatRRASErrorString(wchar_t *a1, const wchar_t *a2, ...)
{
  size_t *v3; // [rsp+60h] [rbp+18h] BYREF
  va_list va; // [rsp+60h] [rbp+18h]
  va_list va1; // [rsp+68h] [rbp+20h] BYREF

  va_start(va1, a2);
  va_start(va, a2);
  v3 = va_arg(va1, size_t *);
  return StringVPrintfWorkerW(a1, 0x400u, v3, a2, va);
}

```

## disassembly

```asm
0x1800089dc  mov     r11, rsp
0x1800089df  mov     [r11+10h], rdx
0x1800089e3  mov     [r11+18h], r8
0x1800089e7  mov     [r11+20h], r9
0x1800089eb  sub     rsp, 48h
0x1800089ef  lea     rax, [r11+18h]
0x1800089f3  mov     qword ptr [r11-18h], 0
0x1800089fb  mov     r9, rdx; pszFormat
0x1800089fe  mov     [r11-28h], rax
0x180008a02  mov     edx, 400h; cchDest
0x180008a07  call    StringVPrintfWorkerW
0x180008a0c  add     rsp, 48h
0x180008a10  retn
```
