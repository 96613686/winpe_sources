# SXWriter::WriteAttribute(wchar_t const *,int,wchar_t const *,int,wchar_t const *,int,tagSXFORMATTYPE,int,IStream *)

- ea: `0x10040ac70`
- end: `0x10040acd9`
- name: `?WriteAttribute@SXWriter@@AEAAJPEB_WH0H0HW4tagSXFORMATTYPE@@HPEAUIStream@@@Z`
- size: `105`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x10040ac20`

## callees

- `0x1004095b0`
- `0x10040ac70`
- `0x10040ace0`

## pseudocode

```c
__int64 __fastcall SXWriter::WriteAttribute(
        SXWriter *a1,
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
  SXWriter::WriteAttributeName(a1, a2, a3, a4, a5, a6, a7);
  SXWriter::WriteTypedData(a1, a8, a9, a10);
  return 0;
}

```

## disassembly

```asm
0x10040ac70  mov     [rsp+arg_0], rbx
0x10040ac75  push    rdi
0x10040ac76  sub     rsp, 60h
0x10040ac7a  mov     rdi, rcx
0x10040ac7d  xor     ebx, ebx
0x10040ac7f  mov     eax, [rsp+68h+arg_30]
0x10040ac86  mov     [rsp+68h+var_38], eax; int
0x10040ac8a  mov     rax, [rsp+68h+arg_28]
0x10040ac92  mov     [rsp+68h+var_40], rax; wchar_t *
0x10040ac97  mov     eax, [rsp+68h+arg_20]
0x10040ac9e  mov     [rsp+68h+var_48], eax; int
0x10040aca2  call    ?WriteAttributeName@SXWriter@@AEAAXPEB_WH0H0H@Z; SXWriter::WriteAttributeName(wchar_t const *,int,wchar_t const *,int,wchar_t const *,int)
0x10040aca7  mov     r9, [rsp+68h+arg_48]
0x10040acaf  mov     r8d, [rsp+68h+arg_40]
0x10040acb7  mov     edx, [rsp+68h+arg_38]
0x10040acbe  mov     rcx, rdi
0x10040acc1  call    ?WriteTypedData@SXWriter@@AEAAXW4tagSXFORMATTYPE@@HPEAUIStream@@@Z; SXWriter::WriteTypedData(tagSXFORMATTYPE,int,IStream *)
0x10040acc6  jmp     short loc_10040ACCC
0x10040acc8  mov     ebx, [rsp+68h+var_28]
0x10040accc  mov     eax, ebx
0x10040acce  mov     rbx, [rsp+68h+arg_0]
0x10040acd3  add     rsp, 60h
0x10040acd7  pop     rdi
0x10040acd8  retn
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
