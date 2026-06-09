# SXWriter::attribute(wchar_t const *,int,wchar_t const *,int,wchar_t const *,int,wchar_t const *,int)

- ea: `0x10040a870`
- end: `0x10040a8d1`
- name: `?attribute@SXWriter@@UEAAJPEB_WH0H0H0H@Z`
- size: `97`
- prototype: `__int64 __fastcall(SXWriter *__hidden this, const wchar_t *, int, const wchar_t *, int, const wchar_t *, int, const wchar_t *, int)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x10040ab90`

## pseudocode

```c
__int64 __fastcall SXWriter::attribute(
        SXWriter *this,
        const wchar_t *a2,
        int a3,
        const wchar_t *a4,
        int a5,
        wchar_t *a6,
        int a7,
        wchar_t *a8,
        int a9)
{
  *((_BYTE *)this + 192) = 1;
  return SXWriter::WriteAttribute(
           (SXWriter *)((char *)this - 64),
           a2,
           a3,
           a4,
           a5,
           a6,
           a7,
           17,
           (unsigned __int64 *)a8,
           a9,
           0);
}

```

## disassembly

```asm
0x10040a870  sub     rsp, 68h
0x10040a874  mov     eax, [rsp+68h+arg_40]
0x10040a87b  mov     [rsp+68h+var_18], 0
0x10040a880  mov     [rsp+68h+var_20], eax
0x10040a884  mov     rax, [rsp+68h+arg_38]
0x10040a88c  mov     [rsp+68h+var_28], rax
0x10040a891  mov     eax, [rsp+68h+arg_30]
0x10040a898  mov     [rsp+68h+var_30], 11h
0x10040a8a0  mov     [rsp+68h+var_38], eax
0x10040a8a4  mov     rax, [rsp+68h+arg_28]
0x10040a8ac  mov     [rsp+68h+var_40], rax
0x10040a8b1  mov     eax, [rsp+68h+arg_20]
0x10040a8b8  mov     byte ptr [rcx+0C0h], 1
0x10040a8bf  add     rcx, 0FFFFFFFFFFFFFFC0h
0x10040a8c3  mov     [rsp+68h+var_48], eax
0x10040a8c7  call    ?WriteAttribute@SXWriter@@AEAAJPEB_WH0H0HW4tagSXFORMATTYPE@@PEBXH_N@Z; SXWriter::WriteAttribute(wchar_t const *,int,wchar_t const *,int,wchar_t const *,int,tagSXFORMATTYPE,void const *,int,bool)
0x10040a8cc  add     rsp, 68h
0x10040a8d0  retn
```
