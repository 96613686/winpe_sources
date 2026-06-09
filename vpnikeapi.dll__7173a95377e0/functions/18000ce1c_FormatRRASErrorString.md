# FormatRRASErrorString

- ea: `0x18000ce1c`
- end: `0x18000ce51`
- name: `FormatRRASErrorString`
- size: `53`
- prototype: `HRESULT(wchar_t *, const wchar_t *, ...)`
- caller_count: `27`
- callee_count: `1`
- tags: ``

## callers

- `0x1800011c0`
- `0x1800013c0`
- `0x180002360`
- `0x180002660`
- `0x180002910`
- `0x180002b70`
- `0x180002f80`
- `0x180003120`
- `0x1800032c0`
- `0x180003470`
- `0x180003620`
- `0x1800038d0`
- `0x180003b80`
- `0x180003e30`
- `0x180004110`
- `0x1800044a0`
- `0x180004780`
- `0x180004a20`
- `0x180004cd0`
- `0x180004f80`
- `0x1800052f0`
- `0x1800055b0`
- `0x180005880`
- `0x180005b30`
- `0x180005de0`
- `0x1800060c0`
- `0x18000c330`

## callees

- `0x18000c7fc`

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
0x18000ce1c  mov     r11, rsp
0x18000ce1f  mov     [r11+10h], rdx
0x18000ce23  mov     [r11+18h], r8
0x18000ce27  mov     [r11+20h], r9
0x18000ce2b  sub     rsp, 48h
0x18000ce2f  lea     rax, [r11+18h]
0x18000ce33  mov     qword ptr [r11-18h], 0
0x18000ce3b  mov     r9, rdx; pszFormat
0x18000ce3e  mov     [r11-28h], rax
0x18000ce42  mov     edx, 400h; cchDest
0x18000ce47  call    StringVPrintfWorkerW
0x18000ce4c  add     rsp, 48h
0x18000ce50  retn
```
