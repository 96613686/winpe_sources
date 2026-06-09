# SXWriter::comment(wchar_t const *,int)

- ea: `0x10040aee0`
- end: `0x10040af5c`
- name: `?comment@SXWriter@@UEAAJPEB_WH@Z`
- size: `124`
- prototype: `int(SXWriter *__hidden this, const wchar_t *, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1004091f0`
- `0x100409740`
- `0x10040adb0`
- `0x10040aee0`

## pseudocode

```c
__int64 __fastcall SXWriter::comment(SXWriter *this, const wchar_t *a2, unsigned int a3)
{
  unsigned int v5; // edi
  SXWriter *v6; // rbx

  v5 = 0;
  if ( a2 )
  {
    v6 = (SXWriter *)((char *)this - 32);
    SXWriter::endAttributesCheck((SXWriter *)((char *)this - 32));
    SXWriter::WriteByte(v6, 243);
    SXWriter::WriteTextData(v6, 0, a2, a3);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v5;
}

```

## disassembly

```asm
0x10040aee0  mov     [rsp+arg_0], rbx
0x10040aee5  mov     [rsp+arg_8], rsi
0x10040aeea  mov     [rsp+arg_10], rdi
0x10040aeef  push    r14
0x10040aef1  sub     rsp, 60h
0x10040aef5  mov     r14d, r8d
0x10040aef8  mov     rsi, rdx
0x10040aefb  xor     edi, edi
0x10040aefd  mov     [rsp+68h+var_30], edi
0x10040af01  test    rdx, rdx
0x10040af04  jnz     short loc_10040AF11
0x10040af06  mov     edi, 80070057h
0x10040af0b  mov     [rsp+68h+var_30], edi
0x10040af0f  jmp     short loc_10040AF41
0x10040af11  lea     rbx, [rcx-20h]
0x10040af15  mov     rcx, rbx; this
0x10040af18  call    ?endAttributesCheck@SXWriter@@AEAAXXZ; SXWriter::endAttributesCheck(void)
0x10040af1d  mov     dl, 0F3h; unsigned __int8
0x10040af1f  mov     rcx, rbx; this
0x10040af22  call    ?WriteByte@SXWriter@@IEAAXE@Z; SXWriter::WriteByte(uchar)
0x10040af27  mov     r9d, r14d; int
0x10040af2a  mov     r8, rsi; wchar_t *
0x10040af2d  xor     edx, edx; bool
0x10040af2f  mov     rcx, rbx; this
0x10040af32  call    ?WriteTextData@SXWriter@@AEAAX_NPEB_WH0@Z; SXWriter::WriteTextData(bool,wchar_t const *,int,bool)
0x10040af37  jmp     short loc_10040AF41
0x10040af39  mov     edi, [rsp+68h+var_38]
0x10040af3d  mov     [rsp+68h+var_30], edi
0x10040af41  mov     eax, edi
0x10040af43  mov     rbx, [rsp+68h+arg_0]
0x10040af48  mov     rsi, [rsp+68h+arg_8]
0x10040af4d  mov     rdi, [rsp+68h+arg_10]
0x10040af55  add     rsp, 60h
0x10040af59  pop     r14
0x10040af5b  retn
0x100424960  push    rbp
0x100424962  sub     rsp, 30h
0x100424966  mov     rbp, rdx
0x100424969  mov     [rbp+50h], rcx
0x10042496d  mov     [rbp+48h], rcx
0x100424971  mov     rax, [rbp+48h]
0x100424975  mov     rcx, [rax]
0x100424978  mov     [rbp+40h], rcx
0x10042497c  mov     rax, [rbp+40h]
0x100424980  mov     eax, [rax]
0x100424982  cmp     eax, 0C0000005h
0x100424987  jz      short loc_1004249B9
0x100424989  add     eax, 1FFFFFFFh
0x10042498e  cmp     eax, 1
0x100424991  ja      short loc_1004249A9
0x100424993  mov     rax, [rbp+40h]
0x100424997  cmp     dword ptr [rax+18h], 1
0x10042499b  jnz     short loc_1004249A9
0x10042499d  mov     rax, [rbp+40h]
0x1004249a1  mov     ecx, [rax+20h]
0x1004249a4  mov     [rbp+30h], ecx
0x1004249a7  jmp     short loc_1004249B0
0x1004249a9  mov     dword ptr [rbp+30h], 8000FFFFh
0x1004249b0  mov     dword ptr [rbp+34h], 1
0x1004249b7  jmp     short loc_1004249C0
0x1004249b9  mov     dword ptr [rbp+34h], 0
0x1004249c0  mov     eax, [rbp+34h]
0x1004249c3  add     rsp, 30h
0x1004249c7  pop     rbp
0x1004249c8  retn
```
