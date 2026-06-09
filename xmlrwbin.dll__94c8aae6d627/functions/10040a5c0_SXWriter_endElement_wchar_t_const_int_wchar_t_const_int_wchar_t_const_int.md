# SXWriter::endElement(wchar_t const *,int,wchar_t const *,int,wchar_t const *,int)

- ea: `0x10040a5c0`
- end: `0x10040a64f`
- name: `?endElement@SXWriter@@UEAAJPEB_WH0H0H@Z`
- size: `143`
- prototype: `__int64 __fastcall(SXWriter *__hidden this, const wchar_t *, int, const wchar_t *, int, const wchar_t *, int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x100409740`
- `0x10040a5c0`
- `0x10040adb0`

## pseudocode

```c
__int64 __fastcall SXWriter::endElement(
        SXWriter *this,
        const wchar_t *a2,
        __int64 a3,
        const wchar_t *a4,
        int a5,
        const wchar_t *a6)
{
  unsigned int v8; // ebx
  SXWriter *v9; // rdi

  v8 = 0;
  v9 = (SXWriter *)((char *)this - 64);
  SXWriter::endAttributesCheck((SXWriter *)((char *)this - 64));
  if ( a2 )
  {
    if ( a4 )
    {
      if ( a6 )
        SXWriter::WriteByte(v9, 247);
      else
        return (unsigned int)-2147024809;
    }
    else
    {
      return (unsigned int)-2147024809;
    }
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
0x10040a5c0  mov     [rsp+arg_0], rbx
0x10040a5c5  mov     [rsp+arg_8], rsi
0x10040a5ca  mov     [rsp+arg_10], rdi
0x10040a5cf  push    r14
0x10040a5d1  sub     rsp, 50h
0x10040a5d5  mov     rsi, r9
0x10040a5d8  mov     r14, rdx
0x10040a5db  xor     ebx, ebx
0x10040a5dd  mov     [rsp+58h+var_38], ebx
0x10040a5e1  lea     rdi, [rcx-40h]
0x10040a5e5  mov     rcx, rdi; this
0x10040a5e8  call    ?endAttributesCheck@SXWriter@@AEAAXXZ; SXWriter::endAttributesCheck(void)
0x10040a5ed  test    r14, r14
0x10040a5f0  jnz     short loc_10040A5FD
0x10040a5f2  mov     ebx, 80070057h
0x10040a5f7  mov     [rsp+58h+var_38], ebx
0x10040a5fb  jmp     short loc_10040A637
0x10040a5fd  test    rsi, rsi
0x10040a600  jnz     short loc_10040A60D
0x10040a602  mov     ebx, 80070057h
0x10040a607  mov     [rsp+58h+var_38], ebx
0x10040a60b  jmp     short loc_10040A637
0x10040a60d  cmp     [rsp+58h+arg_28], 0
0x10040a616  jnz     short loc_10040A623
0x10040a618  mov     ebx, 80070057h
0x10040a61d  mov     [rsp+58h+var_38], ebx
0x10040a621  jmp     short loc_10040A637
0x10040a623  mov     dl, 0F7h; unsigned __int8
0x10040a625  mov     rcx, rdi; this
0x10040a628  call    ?WriteByte@SXWriter@@IEAAXE@Z; SXWriter::WriteByte(uchar)
0x10040a62d  jmp     short loc_10040A637
0x10040a62f  mov     ebx, [rsp+58h+var_34]
0x10040a633  mov     [rsp+58h+var_38], ebx
0x10040a637  mov     eax, ebx
0x10040a639  mov     rbx, [rsp+58h+arg_0]
0x10040a63e  mov     rsi, [rsp+58h+arg_8]
0x10040a643  mov     rdi, [rsp+58h+arg_10]
0x10040a648  add     rsp, 50h
0x10040a64c  pop     r14
0x10040a64e  retn
0x100424690  push    rbp
0x100424692  sub     rsp, 20h
0x100424696  mov     rbp, rdx
0x100424699  mov     [rbp+40h], rcx
0x10042469d  mov     [rbp+38h], rcx
0x1004246a1  mov     rax, [rbp+38h]
0x1004246a5  mov     rcx, [rax]
0x1004246a8  mov     [rbp+30h], rcx
0x1004246ac  mov     rax, [rbp+30h]
0x1004246b0  mov     eax, [rax]
0x1004246b2  cmp     eax, 0C0000005h
0x1004246b7  jz      short loc_1004246E9
0x1004246b9  add     eax, 1FFFFFFFh
0x1004246be  cmp     eax, 1
0x1004246c1  ja      short loc_1004246D9
0x1004246c3  mov     rax, [rbp+30h]
0x1004246c7  cmp     dword ptr [rax+18h], 1
0x1004246cb  jnz     short loc_1004246D9
0x1004246cd  mov     rax, [rbp+30h]
0x1004246d1  mov     ecx, [rax+20h]
0x1004246d4  mov     [rbp+24h], ecx
0x1004246d7  jmp     short loc_1004246E0
0x1004246d9  mov     dword ptr [rbp+24h], 8000FFFFh
0x1004246e0  mov     dword ptr [rbp+28h], 1
0x1004246e7  jmp     short loc_1004246F0
0x1004246e9  mov     dword ptr [rbp+28h], 0
0x1004246f0  mov     eax, [rbp+28h]
0x1004246f3  add     rsp, 20h
0x1004246f7  pop     rbp
0x1004246f8  retn
```
