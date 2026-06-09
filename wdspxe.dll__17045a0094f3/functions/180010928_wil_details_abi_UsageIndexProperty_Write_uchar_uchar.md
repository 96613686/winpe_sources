# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x180010928`
- end: `0x180010a31`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `265`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d924`

## callees

- `0x180010928`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180010996`
- `msvcrt!memcpy_s` at `0x1800109ca`
- `msvcrt!memcpy_s` at `0x1800109fd`
- `msvcrt!memcpy_s` at `0x180010996`
- `msvcrt!memcpy_s` at `0x1800109ca`
- `msvcrt!memcpy_s` at `0x1800109fd`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Write(
        wil::details_abi::UsageIndexProperty *this,
        char **a2,
        char *a3)
{
  char *v4; // rbx
  char *v7; // r14
  char *v8; // r8
  rsize_t v9; // r9
  rsize_t v10; // rdx
  unsigned __int16 *v11; // r14
  rsize_t v12; // r9
  bool result; // al
  __int16 v14; // [rsp+40h] [rbp+8h] BYREF

  v4 = *a2;
  if ( *((_BYTE *)this + 2) == 1 )
  {
    v7 = v4 + 2;
    if ( v4 + 2 > a3 )
      return 0;
    v8 = (char *)&v14;
    v9 = 2;
    v14 = *((_WORD *)this + 2);
    v10 = 2;
  }
  else
  {
    if ( *((_BYTE *)this + 2) != 2 )
      goto LABEL_8;
    v7 = v4 + 4;
    if ( v4 + 4 > a3 )
      return 0;
    v10 = 4;
    v8 = (char *)this + 4;
    v9 = 4;
  }
  memcpy_s(v4, v10, v8, v9);
  v4 = v7;
LABEL_8:
  if ( !*(_WORD *)this )
  {
    if ( v4 + 2 <= a3 )
    {
      v11 = (unsigned __int16 *)((char *)this + 8);
      memcpy_s(v4, a3 - v4, (char *)this + 8, 2u);
      v4 += 2;
      goto LABEL_12;
    }
    return 0;
  }
  v11 = (unsigned __int16 *)((char *)this + 8);
LABEL_12:
  v12 = *v11;
  if ( &v4[v12] > a3 )
    return 0;
  memcpy_s(v4, a3 - v4, *((const void *const *)this + 3), v12);
  result = 1;
  *a2 = &v4[*v11];
  return result;
}

```

## disassembly

```asm
0x180010928  mov     r11, rsp
0x18001092b  mov     [r11+10h], rbx
0x18001092f  mov     [r11+18h], rsi
0x180010933  mov     [r11+20h], rdi
0x180010937  push    r12
0x180010939  push    r14
0x18001093b  push    r15
0x18001093d  sub     rsp, 20h
0x180010941  cmp     byte ptr [rcx+2], 1
0x180010945  mov     rdi, r8
0x180010948  mov     rbx, [rdx]
0x18001094b  mov     r12, rdx
0x18001094e  mov     rsi, rcx
0x180010951  jnz     short loc_180010978
0x180010953  lea     r14, [rbx+2]
0x180010957  cmp     r14, r8
0x18001095a  ja      loc_1800109EC
0x180010960  movzx   eax, word ptr [rcx+4]
0x180010964  lea     r8, [r11+8]
0x180010968  mov     r9d, 2
0x18001096e  mov     [rsp+38h+arg_0], ax
0x180010973  mov     edx, r9d
0x180010976  jmp     short loc_180010993
0x180010978  cmp     byte ptr [rcx+2], 2
0x18001097c  jnz     short loc_1800109A5
0x18001097e  lea     r14, [rbx+4]
0x180010982  cmp     r14, rdi
0x180010985  ja      short loc_1800109EC
0x180010987  mov     edx, 4; DestinationSize
0x18001098c  lea     r8, [rcx+4]; Source
0x180010990  mov     r9d, edx; SourceSize
0x180010993  mov     rcx, rbx; Destination
0x180010996  call    cs:__imp_memcpy_s
0x18001099d  nop     dword ptr [rax+rax+00h]
0x1800109a2  mov     rbx, r14
0x1800109a5  cmp     word ptr [rsi], 0
0x1800109a9  jnz     short loc_1800109DB
0x1800109ab  lea     r15, [rbx+2]
0x1800109af  cmp     r15, rdi
0x1800109b2  ja      short loc_1800109EC
0x1800109b4  lea     r14, [rsi+8]
0x1800109b8  mov     rdx, rdi
0x1800109bb  sub     rdx, rbx; DestinationSize
0x1800109be  mov     r8, r14; Source
0x1800109c1  mov     r9d, 2; SourceSize
0x1800109c7  mov     rcx, rbx; Destination
0x1800109ca  call    cs:__imp_memcpy_s
0x1800109d1  nop     dword ptr [rax+rax+00h]
0x1800109d6  mov     rbx, r15
0x1800109d9  jmp     short loc_1800109DF
0x1800109db  lea     r14, [rsi+8]
0x1800109df  movzx   r9d, word ptr [r14]; SourceSize
0x1800109e3  lea     rax, [r9+rbx]
0x1800109e7  cmp     rax, rdi
0x1800109ea  jbe     short loc_1800109F0
0x1800109ec  xor     al, al
0x1800109ee  jmp     short loc_180010A16
0x1800109f0  mov     r8, [rsi+18h]; Source
0x1800109f4  sub     rdi, rbx
0x1800109f7  mov     rdx, rdi; DestinationSize
0x1800109fa  mov     rcx, rbx; Destination
0x1800109fd  call    cs:__imp_memcpy_s
0x180010a04  nop     dword ptr [rax+rax+00h]
0x180010a09  movzx   ecx, word ptr [r14]
0x180010a0d  mov     al, 1
0x180010a0f  add     rcx, rbx
0x180010a12  mov     [r12], rcx
0x180010a16  mov     rbx, [rsp+38h+arg_8]
0x180010a1b  mov     rsi, [rsp+38h+arg_10]
0x180010a20  mov     rdi, [rsp+38h+arg_18]
0x180010a25  add     rsp, 20h
0x180010a29  pop     r15
0x180010a2b  pop     r14
0x180010a2d  pop     r12
0x180010a2f  retn
```
