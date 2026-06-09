# SXWriter::WriteAttribute(wchar_t const *,int,wchar_t const *,int,wchar_t const *,int,tagSXFORMATTYPE,void const *,int,bool)

- ea: `0x10040ab90`
- end: `0x10040ac0b`
- name: `?WriteAttribute@SXWriter@@AEAAJPEB_WH0H0HW4tagSXFORMATTYPE@@PEBXH_N@Z`
- size: `123`
- prototype: `__int64 __fastcall(SXWriter *, const wchar_t *, int, const wchar_t *, int, wchar_t *, int, int, unsigned __int64 *, int, char)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x10040a870`
- `0x10040a8e0`

## callees

- `0x1004091f0`
- `0x1004093d0`
- `0x10040ab90`
- `0x10040ac70`
- `0x10040ace0`

## pseudocode

```c
__int64 __fastcall SXWriter::WriteAttribute(
        SXWriter *a1,
        const wchar_t *a2,
        int a3,
        const wchar_t *a4,
        int a5,
        wchar_t *a6,
        int a7,
        int a8,
        unsigned __int64 *a9,
        int a10,
        char a11)
{
  SXWriter::WriteAttributeName(a1, a2, a3, a4, a5, a6, a7);
  if ( a11 )
    SXWriter::WriteTypedData((__int64)a1, a8, a9, a10);
  else
    SXWriter::WriteTextData(a1, 1, (const wchar_t *)a9, a10);
  return 0;
}

```

## disassembly

```asm
0x10040ab90  mov     [rsp+arg_0], rbx
0x10040ab95  push    rdi
0x10040ab96  sub     rsp, 60h
0x10040ab9a  mov     rdi, rcx
0x10040ab9d  xor     ebx, ebx
0x10040ab9f  mov     eax, [rsp+68h+arg_30]
0x10040aba6  mov     [rsp+68h+var_38], eax; int
0x10040abaa  mov     rax, [rsp+68h+arg_28]
0x10040abb2  mov     [rsp+68h+var_40], rax; wchar_t *
0x10040abb7  mov     eax, dword ptr [rsp+68h+arg_20]
0x10040abbe  mov     dword ptr [rsp+68h+var_48], eax; bool
0x10040abc2  call    ?WriteAttributeName@SXWriter@@AEAAXPEB_WH0H0H@Z; SXWriter::WriteAttributeName(wchar_t const *,int,wchar_t const *,int,wchar_t const *,int)
0x10040abc7  mov     r9d, [rsp+68h+arg_48]; int
0x10040abcf  mov     r8, [rsp+68h+arg_40]; wchar_t *
0x10040abd7  mov     rcx, rdi; this
0x10040abda  cmp     [rsp+68h+arg_50], bl
0x10040abe1  jz      short loc_10040ABF1
0x10040abe3  mov     edx, [rsp+68h+arg_38]
0x10040abea  call    ?WriteTypedData@SXWriter@@AEAAXW4tagSXFORMATTYPE@@PEBXH@Z; SXWriter::WriteTypedData(tagSXFORMATTYPE,void const *,int)
0x10040abef  jmp     short loc_10040ABF8
0x10040abf1  mov     dl, 1; bool
0x10040abf3  call    ?WriteTextData@SXWriter@@AEAAX_NPEB_WH0@Z; SXWriter::WriteTextData(bool,wchar_t const *,int,bool)
0x10040abf8  jmp     short loc_10040ABFE
0x10040abfa  mov     ebx, [rsp+68h+var_28]
0x10040abfe  mov     eax, ebx
0x10040ac00  mov     rbx, [rsp+68h+arg_0]
0x10040ac05  add     rsp, 60h
0x10040ac09  pop     rdi
0x10040ac0a  retn
0x100424a40  push    rbp
0x100424a42  sub     rsp, 40h
0x100424a46  mov     rbp, rdx
0x100424a49  mov     [rbp+58h], rcx
0x100424a4d  mov     [rbp+50h], rcx
0x100424a51  mov     rax, [rbp+50h]
0x100424a55  mov     rcx, [rax]
0x100424a58  mov     [rbp+48h], rcx
0x100424a5c  mov     rax, [rbp+48h]
0x100424a60  mov     eax, [rax]
0x100424a62  cmp     eax, 0C0000005h
0x100424a67  jz      short loc_100424A99
0x100424a69  add     eax, 1FFFFFFFh
0x100424a6e  cmp     eax, 1
0x100424a71  ja      short loc_100424A89
0x100424a73  mov     rax, [rbp+48h]
0x100424a77  cmp     dword ptr [rax+18h], 1
0x100424a7b  jnz     short loc_100424A89
0x100424a7d  mov     rax, [rbp+48h]
0x100424a81  mov     ecx, [rax+20h]
0x100424a84  mov     [rbp+40h], ecx
0x100424a87  jmp     short loc_100424A90
0x100424a89  mov     dword ptr [rbp+40h], 8000FFFFh
0x100424a90  mov     dword ptr [rbp+44h], 1
0x100424a97  jmp     short loc_100424AA0
0x100424a99  mov     dword ptr [rbp+44h], 0
0x100424aa0  mov     eax, [rbp+44h]
0x100424aa3  add     rsp, 40h
0x100424aa7  pop     rbp
0x100424aa8  retn
```
