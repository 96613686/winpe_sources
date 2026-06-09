# SXWriter::typedAttributeStream(wchar_t const *,int,wchar_t const *,int,wchar_t const *,int,tagSXFORMATTYPE,int,IStream *)

- ea: `0x10040ac20`
- end: `0x10040ac30`
- name: `?typedAttributeStream@SXWriter@@UEAAJPEB_WH0H0HW4tagSXFORMATTYPE@@HPEAUIStream@@@Z`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x10040ac70`

## pseudocode

```c
__int64 __fastcall SXWriter::typedAttributeStream(
        __int64 a1,
        wchar_t *a2,
        int a3,
        wchar_t *a4,
        int a5,
        wchar_t *a6,
        int a7,
        int a8,
        int a9,
        struct IStream *a10)
{
  *(_BYTE *)(a1 + 192) = 1;
  return SXWriter::WriteAttribute((SXWriter *)(a1 - 64), a2, a3, a4, a5, a6, a7, a8, a9, a10);
}

```

## disassembly

```asm
0x10040ac20  mov     byte ptr [rcx+0C0h], 1
0x10040ac27  add     rcx, 0FFFFFFFFFFFFFFC0h
0x10040ac2b  jmp     ?WriteAttribute@SXWriter@@AEAAJPEB_WH0H0HW4tagSXFORMATTYPE@@HPEAUIStream@@@Z; SXWriter::WriteAttribute(wchar_t const *,int,wchar_t const *,int,wchar_t const *,int,tagSXFORMATTYPE,int,IStream *)
```
