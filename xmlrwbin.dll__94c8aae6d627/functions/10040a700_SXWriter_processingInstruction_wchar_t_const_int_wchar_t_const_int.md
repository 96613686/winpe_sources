# SXWriter::processingInstruction(wchar_t const *,int,wchar_t const *,int)

- ea: `0x10040a700`
- end: `0x10040a7c0`
- name: `?processingInstruction@SXWriter@@UEAAJPEB_WH0H@Z`
- size: `192`
- prototype: `int(SXWriter *__hidden this, const wchar_t *, int, const wchar_t *, int)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x1004091f0`
- `0x100409740`
- `0x100409840`
- `0x10040a3c0`
- `0x10040a470`
- `0x10040a700`
- `0x10040adb0`
- `0x10040aee0`

## pseudocode

```c
__int64 __fastcall SXWriter::processingInstruction(
        SXWriter *this,
        const wchar_t *a2,
        unsigned int a3,
        const wchar_t *a4,
        unsigned int a5)
{
  unsigned int v8; // edi
  SXWriter *v9; // rbx
  unsigned int v11[9]; // [rsp+3Ch] [rbp-2Ch] BYREF

  v8 = 0;
  if ( a2 )
  {
    v9 = (SXWriter *)((char *)this - 64);
    SXWriter::endAttributesCheck((SXWriter *)((char *)this - 64));
    while ( (unsigned int)SXWriter::getOrWriteToken(v9, a2, a3, v11) )
      SXWriter::MakeNewTokenTable(v9);
    SXWriter::WriteByte(v9, 244);
    SXWriter::WriteMb32(v9, v11[0]);
    SXWriter::WriteTextData(v9, 0, a4, a5);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v8;
}

```

## disassembly

```asm
0x10040a700  mov     [rsp+arg_0], rbx
0x10040a705  mov     [rsp+arg_8], rsi
0x10040a70a  mov     [rsp+arg_10], rdi
0x10040a70f  mov     [rsp+arg_18], r14
0x10040a714  push    r15
0x10040a716  sub     rsp, 60h
0x10040a71a  mov     r15, r9
0x10040a71d  mov     r14d, r8d
0x10040a720  mov     rsi, rdx
0x10040a723  xor     edi, edi
0x10040a725  mov     [rsp+68h+var_30], edi
0x10040a729  test    rdx, rdx
0x10040a72c  jnz     short loc_10040A739
0x10040a72e  mov     edi, 80070057h
0x10040a733  mov     [rsp+68h+var_30], edi
0x10040a737  jmp     short loc_10040A7A3
0x10040a739  lea     rbx, [rcx-40h]
0x10040a73d  mov     rcx, rbx; this
0x10040a740  call    ?endAttributesCheck@SXWriter@@AEAAXXZ; SXWriter::endAttributesCheck(void)
0x10040a745  nop     word ptr [rax+rax+00000000h]
0x10040a750  lea     r9, [rsp+68h+var_2C]; unsigned int *
0x10040a755  mov     r8d, r14d; unsigned int
0x10040a758  mov     rdx, rsi; Src
0x10040a75b  mov     rcx, rbx; this
0x10040a75e  call    ?getOrWriteToken@SXWriter@@AEAAHPEB_WKPEAK@Z; SXWriter::getOrWriteToken(wchar_t const *,ulong,ulong *)
0x10040a763  mov     rcx, rbx; this
0x10040a766  test    eax, eax
0x10040a768  jz      short loc_10040A771
0x10040a76a  call    ?MakeNewTokenTable@SXWriter@@AEAAXXZ; SXWriter::MakeNewTokenTable(void)
0x10040a76f  jmp     short loc_10040A750
0x10040a771  mov     dl, 0F4h; unsigned __int8
0x10040a773  call    ?WriteByte@SXWriter@@IEAAXE@Z; SXWriter::WriteByte(uchar)
0x10040a778  mov     edx, [rsp+68h+var_2C]; unsigned int
0x10040a77c  mov     rcx, rbx; this
0x10040a77f  call    ?WriteMb32@SXWriter@@IEAAXK@Z; SXWriter::WriteMb32(ulong)
0x10040a784  mov     r9d, [rsp+68h+arg_20]; int
0x10040a78c  mov     r8, r15; wchar_t *
0x10040a78f  xor     edx, edx; bool
0x10040a791  mov     rcx, rbx; this
0x10040a794  call    ?WriteTextData@SXWriter@@AEAAX_NPEB_WH0@Z; SXWriter::WriteTextData(bool,wchar_t const *,int,bool)
0x10040a799  jmp     short loc_10040A7A3
0x10040a79b  mov     edi, [rsp+68h+var_38]
0x10040a79f  mov     [rsp+68h+var_30], edi
0x10040a7a3  mov     eax, edi
0x10040a7a5  lea     r11, [rsp+68h+var_8]
0x10040a7aa  mov     rbx, [r11+10h]
0x10040a7ae  mov     rsi, [r11+18h]
0x10040a7b2  mov     rdi, [r11+20h]
0x10040a7b6  mov     r14, [r11+28h]
0x10040a7ba  mov     rsp, r11
0x10040a7bd  pop     r15
0x10040a7bf  retn
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
