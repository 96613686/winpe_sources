# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x140008f08`
- end: `0x140008ff1`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140006b28`
- `0x140009950`
- `0x140009cd8`

## callees

- `0x140008f08`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140008f57`
- `msvcrt!memcpy_s` at `0x140008f8c`
- `msvcrt!memcpy_s` at `0x140008fb7`
- `msvcrt!memcpy_s` at `0x140008f57`
- `msvcrt!memcpy_s` at `0x140008f8c`
- `msvcrt!memcpy_s` at `0x140008fb7`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Read(
        wil::details_abi::UsageIndexProperty *this,
        unsigned __int8 **a2,
        unsigned __int8 *a3)
{
  char *v5; // r8
  char *v7; // rbx
  __int16 v8; // ax
  unsigned __int8 *v9; // rcx
  bool result; // al
  unsigned __int16 v11; // [rsp+50h] [rbp+8h] BYREF

  v5 = (char *)*a2;
  if ( *((_BYTE *)this + 2) == 1 )
  {
    v7 = v5 + 2;
    if ( v5 + 2 > (char *)a3 )
      return 0;
    *((_QWORD *)this + 2) = v5;
    v11 = 0;
    memcpy_s(&v11, 2u, v5, 2u);
    *((_DWORD *)this + 1) = v11;
  }
  else
  {
    v7 = (char *)*a2;
    if ( *((_BYTE *)this + 2) == 2 )
    {
      v7 = v5 + 4;
      if ( v5 + 4 > (char *)a3 )
        return 0;
      *((_QWORD *)this + 2) = v5;
      memcpy_s((char *)this + 4, 4u, v5, 4u);
    }
  }
  v8 = *(_WORD *)this;
  *((_WORD *)this + 4) = *(_WORD *)this;
  if ( v8 )
    goto LABEL_10;
  if ( v7 + 2 > (char *)a3 )
    return 0;
  memcpy_s((char *)this + 8, 2u, v7, 2u);
  v7 += 2;
LABEL_10:
  v9 = (unsigned __int8 *)&v7[*((unsigned __int16 *)this + 4)];
  if ( v9 > a3 )
    return 0;
  *((_QWORD *)this + 3) = v7;
  result = 1;
  *a2 = v9;
  return result;
}

```

## disassembly

```asm
0x140008f08  mov     rax, rsp
0x140008f0b  mov     [rax+10h], rbx
0x140008f0f  mov     [rax+18h], rbp
0x140008f13  push    rsi
0x140008f14  push    rdi
0x140008f15  push    r12
0x140008f17  push    r14
0x140008f19  push    r15
0x140008f1b  sub     rsp, 20h
0x140008f1f  xor     r15d, r15d
0x140008f22  mov     rsi, r8
0x140008f25  cmp     byte ptr [rcx+2], 1
0x140008f29  mov     r12, rdx
0x140008f2c  mov     r8, [rdx]; Source
0x140008f2f  mov     rdi, rcx
0x140008f32  jnz     short loc_140008F67
0x140008f34  lea     rbx, [r8+2]
0x140008f38  cmp     rbx, rsi
0x140008f3b  ja      loc_140008FCC
0x140008f41  lea     ebp, [r15+2]
0x140008f45  mov     [rcx+10h], r8
0x140008f49  mov     r9d, ebp; SourceSize
0x140008f4c  mov     [rax+8], r15w
0x140008f51  mov     edx, ebp; DestinationSize
0x140008f53  lea     rcx, [rax+8]; Destination
0x140008f57  call    cs:__imp_memcpy_s
0x140008f5d  movzx   eax, [rsp+48h+arg_0]
0x140008f62  mov     [rdi+4], eax
0x140008f65  jmp     short loc_140008F92
0x140008f67  mov     ebp, 2
0x140008f6c  mov     rbx, r8
0x140008f6f  cmp     [rcx+2], bpl
0x140008f73  jnz     short loc_140008F92
0x140008f75  lea     rbx, [r8+4]
0x140008f79  cmp     rbx, rsi
0x140008f7c  ja      short loc_140008FCC
0x140008f7e  lea     edx, [rbp+2]; DestinationSize
0x140008f81  mov     [rcx+10h], r8
0x140008f85  mov     r9d, edx; SourceSize
0x140008f88  add     rcx, 4; Destination
0x140008f8c  call    cs:__imp_memcpy_s
0x140008f92  movzx   eax, word ptr [rdi]
0x140008f95  lea     r14, [rdi+8]
0x140008f99  mov     [r14], ax
0x140008f9d  test    ax, ax
0x140008fa0  jnz     short loc_140008FC0
0x140008fa2  lea     r15, [rbx+2]
0x140008fa6  cmp     r15, rsi
0x140008fa9  ja      short loc_140008FCC
0x140008fab  mov     r9, rbp; SourceSize
0x140008fae  mov     r8, rbx; Source
0x140008fb1  mov     rdx, rbp; DestinationSize
0x140008fb4  mov     rcx, r14; Destination
0x140008fb7  call    cs:__imp_memcpy_s
0x140008fbd  mov     rbx, r15
0x140008fc0  movzx   ecx, word ptr [r14]
0x140008fc4  add     rcx, rbx
0x140008fc7  cmp     rcx, rsi
0x140008fca  jbe     short loc_140008FD0
0x140008fcc  xor     al, al
0x140008fce  jmp     short loc_140008FDA
0x140008fd0  mov     [rdi+18h], rbx
0x140008fd4  mov     al, 1
0x140008fd6  mov     [r12], rcx
0x140008fda  mov     rbx, [rsp+48h+arg_8]
0x140008fdf  mov     rbp, [rsp+48h+arg_10]
0x140008fe4  add     rsp, 20h
0x140008fe8  pop     r15
0x140008fea  pop     r14
0x140008fec  pop     r12
0x140008fee  pop     rdi
0x140008fef  pop     rsi
0x140008ff0  retn
```
