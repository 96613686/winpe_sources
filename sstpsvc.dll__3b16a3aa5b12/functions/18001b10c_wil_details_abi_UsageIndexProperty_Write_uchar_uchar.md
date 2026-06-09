# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x18001b10c`
- end: `0x18001b1e5`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180019d60`

## callees

- `0x18001b10c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18001b16c`
- `msvcrt!memcpy_s` at `0x18001b197`
- `msvcrt!memcpy_s` at `0x18001b1c4`
- `msvcrt!memcpy_s` at `0x18001b16c`
- `msvcrt!memcpy_s` at `0x18001b197`
- `msvcrt!memcpy_s` at `0x18001b1c4`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Write(
        wil::details_abi::UsageIndexProperty *this,
        char **a2,
        char *a3)
{
  char *v5; // rcx
  char *v7; // rbx
  char *v8; // r8
  rsize_t v9; // r9
  rsize_t v10; // rdx
  unsigned __int16 *v11; // r14
  rsize_t v12; // r9
  bool result; // al
  __int16 v14; // [rsp+60h] [rbp+8h] BYREF

  v5 = *a2;
  if ( *((_BYTE *)this + 2) == 1 )
  {
    v7 = v5 + 2;
    if ( v5 + 2 > a3 )
      return 0;
    v8 = (char *)&v14;
    v9 = 2;
    v14 = *((_WORD *)this + 2);
    v10 = 2;
  }
  else
  {
    v7 = *a2;
    if ( *((_BYTE *)this + 2) != 2 )
      goto LABEL_8;
    v7 = v5 + 4;
    if ( v5 + 4 > a3 )
      return 0;
    v10 = 4;
    v8 = (char *)this + 4;
    v9 = 4;
  }
  memcpy_s(v5, v10, v8, v9);
LABEL_8:
  if ( !*(_WORD *)this )
  {
    if ( v7 + 2 <= a3 )
    {
      v11 = (unsigned __int16 *)((char *)this + 8);
      memcpy_s(v7, a3 - v7, (char *)this + 8, 2u);
      v7 += 2;
      goto LABEL_12;
    }
    return 0;
  }
  v11 = (unsigned __int16 *)((char *)this + 8);
LABEL_12:
  v12 = *v11;
  if ( &v7[v12] > a3 )
    return 0;
  memcpy_s(v7, a3 - v7, *((const void *const *)this + 3), v12);
  result = 1;
  *a2 = &v7[*v11];
  return result;
}

```

## disassembly

```asm
0x18001b10c  push    rbx
0x18001b10e  push    rsi
0x18001b10f  push    rdi
0x18001b110  push    r12
0x18001b112  push    r14
0x18001b114  push    r15
0x18001b116  sub     rsp, 28h
0x18001b11a  mov     rsi, rcx
0x18001b11d  mov     rdi, r8
0x18001b120  mov     rcx, [rdx]; Destination
0x18001b123  mov     r12, rdx
0x18001b126  cmp     byte ptr [rsi+2], 1
0x18001b12a  jnz     short loc_18001B14E
0x18001b12c  lea     rbx, [rcx+2]
0x18001b130  cmp     rbx, r8
0x18001b133  ja      short loc_18001B1B3
0x18001b135  movzx   eax, word ptr [rsi+4]
0x18001b139  lea     r8, [rsp+58h+arg_0]
0x18001b13e  mov     r9d, 2
0x18001b144  mov     [rsp+58h+arg_0], ax
0x18001b149  mov     edx, r9d
0x18001b14c  jmp     short loc_18001B16C
0x18001b14e  cmp     byte ptr [rsi+2], 2
0x18001b152  mov     rbx, rcx
0x18001b155  jnz     short loc_18001B172
0x18001b157  lea     rbx, [rcx+4]
0x18001b15b  cmp     rbx, rdi
0x18001b15e  ja      short loc_18001B1B3
0x18001b160  mov     edx, 4; DestinationSize
0x18001b165  lea     r8, [rsi+4]; Source
0x18001b169  mov     r9d, edx; SourceSize
0x18001b16c  call    cs:__imp_memcpy_s
0x18001b172  cmp     word ptr [rsi], 0
0x18001b176  jnz     short loc_18001B1A2
0x18001b178  lea     r15, [rbx+2]
0x18001b17c  cmp     r15, rdi
0x18001b17f  ja      short loc_18001B1B3
0x18001b181  lea     r14, [rsi+8]
0x18001b185  mov     rdx, rdi
0x18001b188  sub     rdx, rbx; DestinationSize
0x18001b18b  mov     r8, r14; Source
0x18001b18e  mov     r9d, 2; SourceSize
0x18001b194  mov     rcx, rbx; Destination
0x18001b197  call    cs:__imp_memcpy_s
0x18001b19d  mov     rbx, r15
0x18001b1a0  jmp     short loc_18001B1A6
0x18001b1a2  lea     r14, [rsi+8]
0x18001b1a6  movzx   r9d, word ptr [r14]; SourceSize
0x18001b1aa  lea     rax, [r9+rbx]
0x18001b1ae  cmp     rax, rdi
0x18001b1b1  jbe     short loc_18001B1B7
0x18001b1b3  xor     al, al
0x18001b1b5  jmp     short loc_18001B1D7
0x18001b1b7  mov     r8, [rsi+18h]; Source
0x18001b1bb  sub     rdi, rbx
0x18001b1be  mov     rdx, rdi; DestinationSize
0x18001b1c1  mov     rcx, rbx; Destination
0x18001b1c4  call    cs:__imp_memcpy_s
0x18001b1ca  movzx   ecx, word ptr [r14]
0x18001b1ce  mov     al, 1
0x18001b1d0  add     rcx, rbx
0x18001b1d3  mov     [r12], rcx
0x18001b1d7  add     rsp, 28h
0x18001b1db  pop     r15
0x18001b1dd  pop     r14
0x18001b1df  pop     r12
0x18001b1e1  pop     rdi
0x18001b1e2  pop     rsi
0x18001b1e3  pop     rbx
0x18001b1e4  retn
```
