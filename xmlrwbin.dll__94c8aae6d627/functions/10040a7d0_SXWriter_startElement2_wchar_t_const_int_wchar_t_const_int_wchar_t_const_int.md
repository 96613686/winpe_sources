# SXWriter::startElement2(wchar_t const *,int,wchar_t const *,int,wchar_t const *,int)

- ea: `0x10040a7d0`
- end: `0x10040a86a`
- name: `?startElement2@SXWriter@@UEAAJPEB_WH0H0H@Z`
- size: `154`
- prototype: `__int64 __fastcall(SXWriter *__hidden this, const wchar_t *, int, const wchar_t *, int, const wchar_t *, int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x10040a7d0`
- `0x10040adb0`
- `0x100424580`

## pseudocode

```c
__int64 __fastcall SXWriter::startElement2(
        SXWriter *this,
        const wchar_t *a2,
        unsigned int a3,
        const wchar_t *a4,
        int a5,
        const wchar_t *a6,
        int a7)
{
  SXWriter::endAttributesCheck((SXWriter *)((char *)this - 64));
  return (*(__int64 (__fastcall **)(SXWriter *, const wchar_t *, _QWORD, const wchar_t *, int, const wchar_t *, int, _QWORD))(*(_QWORD *)this + 64LL))(
           this,
           a2,
           a3,
           a4,
           a5,
           a6,
           a7,
           0);
}

```

## disassembly

```asm
0x10040a7d0  mov     [rsp+arg_0], rbx
0x10040a7d5  mov     [rsp+arg_8], rsi
0x10040a7da  mov     [rsp+arg_10], rdi
0x10040a7df  push    r14
0x10040a7e1  sub     rsp, 80h
0x10040a7e8  mov     rdi, r9
0x10040a7eb  mov     esi, r8d
0x10040a7ee  mov     r14, rdx
0x10040a7f1  mov     rbx, rcx
0x10040a7f4  add     rcx, 0FFFFFFFFFFFFFFC0h; this
0x10040a7f8  call    ?endAttributesCheck@SXWriter@@AEAAXXZ; SXWriter::endAttributesCheck(void)
0x10040a7fd  mov     rax, [rbx]
0x10040a800  mov     [rsp+88h+var_50], 0
0x10040a809  mov     edx, [rsp+88h+arg_30]
0x10040a810  mov     [rsp+88h+var_58], edx
0x10040a814  mov     rcx, [rsp+88h+arg_28]
0x10040a81c  mov     [rsp+88h+var_60], rcx
0x10040a821  mov     ecx, [rsp+88h+arg_20]
0x10040a828  mov     [rsp+88h+var_68], ecx
0x10040a82c  mov     r9, rdi
0x10040a82f  mov     r8d, esi
0x10040a832  mov     rdx, r14
0x10040a835  mov     rcx, rbx
0x10040a838  mov     rax, [rax+40h]
0x10040a83c  call    cs:__guard_dispatch_icall_fptr
0x10040a842  mov     [rsp+88h+var_30], eax
0x10040a846  jmp     short loc_10040A850
0x10040a848  mov     eax, [rsp+88h+var_38]
0x10040a84c  mov     [rsp+88h+var_30], eax
0x10040a850  lea     r11, [rsp+88h+var_8]
0x10040a858  mov     rbx, [r11+10h]
0x10040a85c  mov     rsi, [r11+18h]
0x10040a860  mov     rdi, [r11+20h]
0x10040a864  mov     rsp, r11
0x10040a867  pop     r14
0x10040a869  retn
0x1004249d0  push    rbp
0x1004249d2  sub     rsp, 50h
0x1004249d6  mov     rbp, rdx
0x1004249d9  mov     [rbp+70h], rcx
0x1004249dd  mov     [rbp+68h], rcx
0x1004249e1  mov     rax, [rbp+68h]
0x1004249e5  mov     rcx, [rax]
0x1004249e8  mov     [rbp+60h], rcx
0x1004249ec  mov     rax, [rbp+60h]
0x1004249f0  mov     eax, [rax]
0x1004249f2  cmp     eax, 0C0000005h
0x1004249f7  jz      short loc_100424A29
0x1004249f9  add     eax, 1FFFFFFFh
0x1004249fe  cmp     eax, 1
0x100424a01  ja      short loc_100424A19
0x100424a03  mov     rax, [rbp+60h]
0x100424a07  cmp     dword ptr [rax+18h], 1
0x100424a0b  jnz     short loc_100424A19
0x100424a0d  mov     rax, [rbp+60h]
0x100424a11  mov     ecx, [rax+20h]
0x100424a14  mov     [rbp+50h], ecx
0x100424a17  jmp     short loc_100424A20
0x100424a19  mov     dword ptr [rbp+50h], 8000FFFFh
0x100424a20  mov     dword ptr [rbp+54h], 1
0x100424a27  jmp     short loc_100424A30
0x100424a29  mov     dword ptr [rbp+54h], 0
0x100424a30  mov     eax, [rbp+54h]
0x100424a33  add     rsp, 50h
0x100424a37  pop     rbp
0x100424a38  retn
```
