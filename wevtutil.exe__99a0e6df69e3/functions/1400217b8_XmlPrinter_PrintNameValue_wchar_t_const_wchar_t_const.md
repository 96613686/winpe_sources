# XmlPrinter::PrintNameValue(wchar_t const *,wchar_t const *)

- ea: `0x1400217b8`
- end: `0x1400217c7`
- name: `?PrintNameValue@XmlPrinter@@QEAAXPEB_W0@Z`
- size: `15`
- prototype: `void __fastcall(XmlPrinter *__hidden this, const wchar_t *, const wchar_t *)`
- caller_count: `10`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000b470`
- `0x14000db10`
- `0x14000e550`
- `0x14002164c`
- `0x1400260f8`
- `0x1400262e4`
- `0x14002689c`
- `0x140026bb8`
- `0x140026dc4`
- `0x140026fe8`

## callees

- `0x140029664`
- `0x14002987c`

## pseudocode

```c
void __fastcall XmlPrinter::PrintNameValue(HANDLE *this, const wchar_t *a2, const wchar_t *a3)
{
  if ( *((_BYTE *)this + 33) )
    XmlPrinter::PrintAttribute(this, a2, a3);
  else
    XmlPrinter::PrintElement((XmlPrinter *)this, a2, a3);
}

```

## disassembly

```asm
0x1400217b8  cmp     byte ptr [rcx+21h], 0
0x1400217bc  jnz     ?PrintAttribute@XmlPrinter@@QEAAXPEB_W0@Z; XmlPrinter::PrintAttribute(wchar_t const *,wchar_t const *)
0x1400217c2  jmp     ?PrintElement@XmlPrinter@@QEAAXPEB_W0@Z; XmlPrinter::PrintElement(wchar_t const *,wchar_t const *)
```
