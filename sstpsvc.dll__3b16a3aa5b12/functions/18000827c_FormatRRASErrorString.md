# FormatRRASErrorString

- ea: `0x18000827c`
- end: `0x1800082b1`
- name: `FormatRRASErrorString`
- size: `53`
- prototype: `__int64(_QWORD, _QWORD, ...)`
- caller_count: `63`
- callee_count: `1`
- tags: ``

## callers

- `0x180001240`
- `0x180001a80`
- `0x180001ee0`
- `0x1800021f0`
- `0x180002908`
- `0x180002e00`
- `0x1800033b0`
- `0x180003920`
- `0x1800045b0`
- `0x180004824`
- `0x180004940`
- `0x180004bc0`
- `0x180004d10`
- `0x180004ef4`
- `0x180005280`
- `0x180005560`
- `0x180005920`
- `0x1800063a0`
- `0x180006b64`
- `0x180007944`
- `0x180007a84`
- `0x1800093ac`
- `0x180009a00`
- `0x180009c7c`
- `0x180009dd8`
- `0x18000a0d4`
- `0x18000a270`
- `0x18000a35c`
- `0x18000a448`
- `0x18000a620`
- `0x18000afbc`
- `0x18000b2e0`
- `0x18000b9fc`
- `0x18000bc78`
- `0x18000bf68`
- `0x18000c788`
- `0x18000c8d0`
- `0x18000cba4`
- `0x18000cdd8`
- `0x18000cec8`
- `0x18000d1a0`
- `0x18000d324`
- `0x18000df30`
- `0x18000e9a0`
- `0x18000f974`
- `0x18000ff74`
- `0x1800101dc`
- `0x1800103e8`
- `0x180010634`
- `0x180010b84`

## callees

- `0x180008300`

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
0x18000827c  mov     r11, rsp
0x18000827f  mov     [r11+10h], rdx
0x180008283  mov     [r11+18h], r8
0x180008287  mov     [r11+20h], r9
0x18000828b  sub     rsp, 48h
0x18000828f  lea     rax, [r11+18h]
0x180008293  mov     qword ptr [r11-18h], 0
0x18000829b  mov     r9, rdx; pszFormat
0x18000829e  mov     [r11-28h], rax
0x1800082a2  mov     edx, 400h; cchDest
0x1800082a7  call    StringVPrintfWorkerW
0x1800082ac  add     rsp, 48h
0x1800082b0  retn
```
