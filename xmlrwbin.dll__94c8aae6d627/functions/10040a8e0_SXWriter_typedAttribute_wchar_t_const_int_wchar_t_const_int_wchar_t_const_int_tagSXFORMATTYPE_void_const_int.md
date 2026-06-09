# SXWriter::typedAttribute(wchar_t const *,int,wchar_t const *,int,wchar_t const *,int,tagSXFORMATTYPE,void const *,int)

- ea: `0x10040a8e0`
- end: `0x10040a944`
- name: `?typedAttribute@SXWriter@@UEAAJPEB_WH0H0HW4tagSXFORMATTYPE@@PEBXH@Z`
- size: `100`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x10040ab90`

## pseudocode

```c
__int64 __fastcall SXWriter::typedAttribute(
        __int64 a1,
        const wchar_t *a2,
        int a3,
        const wchar_t *a4,
        int a5,
        wchar_t *a6,
        int a7,
        int a8,
        unsigned __int64 *a9,
        int a10)
{
  *(_BYTE *)(a1 + 192) = 1;
  return SXWriter::WriteAttribute((SXWriter *)(a1 - 64), a2, a3, a4, a5, a6, a7, a8, a9, a10, 1);
}

```

## disassembly

```asm
0x10040a8e0  sub     rsp, 68h
0x10040a8e4  mov     eax, [rsp+68h+arg_48]
0x10040a8eb  mov     [rsp+68h+var_18], 1
0x10040a8f0  mov     [rsp+68h+var_20], eax
0x10040a8f4  mov     rax, [rsp+68h+arg_40]
0x10040a8fc  mov     [rsp+68h+var_28], rax
0x10040a901  mov     eax, [rsp+68h+arg_38]
0x10040a908  mov     [rsp+68h+var_30], eax
0x10040a90c  mov     eax, [rsp+68h+arg_30]
0x10040a913  mov     [rsp+68h+var_38], eax
0x10040a917  mov     rax, [rsp+68h+arg_28]
0x10040a91f  mov     [rsp+68h+var_40], rax
0x10040a924  mov     eax, [rsp+68h+arg_20]
0x10040a92b  mov     byte ptr [rcx+0C0h], 1
0x10040a932  add     rcx, 0FFFFFFFFFFFFFFC0h
0x10040a936  mov     [rsp+68h+var_48], eax
0x10040a93a  call    ?WriteAttribute@SXWriter@@AEAAJPEB_WH0H0HW4tagSXFORMATTYPE@@PEBXH_N@Z; SXWriter::WriteAttribute(wchar_t const *,int,wchar_t const *,int,wchar_t const *,int,tagSXFORMATTYPE,void const *,int,bool)
0x10040a93f  add     rsp, 68h
0x10040a943  retn
```
