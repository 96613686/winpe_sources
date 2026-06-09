# SXWriter::characters(wchar_t const *,int)

- ea: `0x10040a660`
- end: `0x10040a6f9`
- name: `?characters@SXWriter@@UEAAJPEB_WH@Z`
- size: `153`
- prototype: `int(SXWriter *__hidden this, const wchar_t *, int)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1004091f0`
- `0x100409740`
- `0x10040a660`
- `0x10040adb0`
- `0x10040aee0`

## pseudocode

```c
__int64 __fastcall SXWriter::characters(SXWriter *this, const wchar_t *a2, unsigned int a3)
{
  unsigned int v6; // ebx
  SXWriter *v7; // rcx
  char v8; // dl

  v6 = 0;
  SXWriter::endAttributesCheck((SXWriter *)((char *)this - 64));
  if ( a2 )
  {
    v7 = (SXWriter *)((char *)this - 64);
    if ( *((_BYTE *)this + 184) )
    {
      *((_BYTE *)this + 185) = 0;
      SXWriter::WriteByte(v7, 242);
      v8 = 0;
      v7 = (SXWriter *)((char *)this - 64);
    }
    else
    {
      v8 = 1;
    }
    SXWriter::WriteTextData(v7, v8, a2, a3);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v6;
}

```

## disassembly

```asm
0x10040a660  mov     [rsp+arg_0], rbx
0x10040a665  mov     [rsp+arg_8], rsi
0x10040a66a  mov     [rsp+arg_10], rdi
0x10040a66f  mov     [rsp+arg_18], r14
0x10040a674  push    r15
0x10040a676  sub     rsp, 60h
0x10040a67a  mov     r15d, r8d
0x10040a67d  mov     r14, rdx
0x10040a680  mov     rsi, rcx
0x10040a683  xor     ebx, ebx
0x10040a685  mov     [rsp+68h+var_30], ebx
0x10040a689  add     rcx, 0FFFFFFFFFFFFFFC0h; this
0x10040a68d  call    ?endAttributesCheck@SXWriter@@AEAAXXZ; SXWriter::endAttributesCheck(void)
0x10040a692  test    r14, r14
0x10040a695  jnz     short loc_10040A6A2
0x10040a697  mov     ebx, 80070057h
0x10040a69c  mov     [rsp+68h+var_30], ebx
0x10040a6a0  jmp     short loc_10040A6DC
0x10040a6a2  lea     rcx, [rsi-40h]; this
0x10040a6a6  cmp     byte ptr [rsi+0B8h], 0
0x10040a6ad  jz      short loc_10040A6C5
0x10040a6af  mov     byte ptr [rsi+0B9h], 0
0x10040a6b6  mov     dl, 0F2h; unsigned __int8
0x10040a6b8  call    ?WriteByte@SXWriter@@IEAAXE@Z; SXWriter::WriteByte(uchar)
0x10040a6bd  xor     edx, edx
0x10040a6bf  lea     rcx, [rsi-40h]
0x10040a6c3  jmp     short loc_10040A6C7
0x10040a6c5  mov     dl, 1; bool
0x10040a6c7  mov     r9d, r15d; int
0x10040a6ca  mov     r8, r14; wchar_t *
0x10040a6cd  call    ?WriteTextData@SXWriter@@AEAAX_NPEB_WH0@Z; SXWriter::WriteTextData(bool,wchar_t const *,int,bool)
0x10040a6d2  jmp     short loc_10040A6DC
0x10040a6d4  mov     ebx, [rsp+68h+var_38]
0x10040a6d8  mov     [rsp+68h+var_30], ebx
0x10040a6dc  mov     eax, ebx
0x10040a6de  lea     r11, [rsp+68h+var_8]
0x10040a6e3  mov     rbx, [r11+10h]
0x10040a6e7  mov     rsi, [r11+18h]
0x10040a6eb  mov     rdi, [r11+20h]
0x10040a6ef  mov     r14, [r11+28h]
0x10040a6f3  mov     rsp, r11
0x10040a6f6  pop     r15
0x10040a6f8  retn
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
