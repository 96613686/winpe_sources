# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x14000bffc`
- end: `0x14000c0d5`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140009950`

## callees

- `0x14000bffc`

## import_xrefs

- `msvcrt!memcpy_s` at `0x14000c05c`
- `msvcrt!memcpy_s` at `0x14000c087`
- `msvcrt!memcpy_s` at `0x14000c0b4`
- `msvcrt!memcpy_s` at `0x14000c05c`
- `msvcrt!memcpy_s` at `0x14000c087`
- `msvcrt!memcpy_s` at `0x14000c0b4`

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
0x14000bffc  push    rbx
0x14000bffe  push    rsi
0x14000bfff  push    rdi
0x14000c000  push    r12
0x14000c002  push    r14
0x14000c004  push    r15
0x14000c006  sub     rsp, 28h
0x14000c00a  mov     rsi, rcx
0x14000c00d  mov     rdi, r8
0x14000c010  mov     rcx, [rdx]; Destination
0x14000c013  mov     r12, rdx
0x14000c016  cmp     byte ptr [rsi+2], 1
0x14000c01a  jnz     short loc_14000C03E
0x14000c01c  lea     rbx, [rcx+2]
0x14000c020  cmp     rbx, r8
0x14000c023  ja      short loc_14000C0A3
0x14000c025  movzx   eax, word ptr [rsi+4]
0x14000c029  lea     r8, [rsp+58h+arg_0]
0x14000c02e  mov     r9d, 2
0x14000c034  mov     [rsp+58h+arg_0], ax
0x14000c039  mov     edx, r9d
0x14000c03c  jmp     short loc_14000C05C
0x14000c03e  cmp     byte ptr [rsi+2], 2
0x14000c042  mov     rbx, rcx
0x14000c045  jnz     short loc_14000C062
0x14000c047  lea     rbx, [rcx+4]
0x14000c04b  cmp     rbx, rdi
0x14000c04e  ja      short loc_14000C0A3
0x14000c050  mov     edx, 4; DestinationSize
0x14000c055  lea     r8, [rsi+4]; Source
0x14000c059  mov     r9d, edx; SourceSize
0x14000c05c  call    cs:__imp_memcpy_s
0x14000c062  cmp     word ptr [rsi], 0
0x14000c066  jnz     short loc_14000C092
0x14000c068  lea     r15, [rbx+2]
0x14000c06c  cmp     r15, rdi
0x14000c06f  ja      short loc_14000C0A3
0x14000c071  lea     r14, [rsi+8]
0x14000c075  mov     rdx, rdi
0x14000c078  sub     rdx, rbx; DestinationSize
0x14000c07b  mov     r8, r14; Source
0x14000c07e  mov     r9d, 2; SourceSize
0x14000c084  mov     rcx, rbx; Destination
0x14000c087  call    cs:__imp_memcpy_s
0x14000c08d  mov     rbx, r15
0x14000c090  jmp     short loc_14000C096
0x14000c092  lea     r14, [rsi+8]
0x14000c096  movzx   r9d, word ptr [r14]; SourceSize
0x14000c09a  lea     rax, [r9+rbx]
0x14000c09e  cmp     rax, rdi
0x14000c0a1  jbe     short loc_14000C0A7
0x14000c0a3  xor     al, al
0x14000c0a5  jmp     short loc_14000C0C7
0x14000c0a7  mov     r8, [rsi+18h]; Source
0x14000c0ab  sub     rdi, rbx
0x14000c0ae  mov     rdx, rdi; DestinationSize
0x14000c0b1  mov     rcx, rbx; Destination
0x14000c0b4  call    cs:__imp_memcpy_s
0x14000c0ba  movzx   ecx, word ptr [r14]
0x14000c0be  mov     al, 1
0x14000c0c0  add     rcx, rbx
0x14000c0c3  mov     [r12], rcx
0x14000c0c7  add     rsp, 28h
0x14000c0cb  pop     r15
0x14000c0cd  pop     r14
0x14000c0cf  pop     r12
0x14000c0d1  pop     rdi
0x14000c0d2  pop     rsi
0x14000c0d3  pop     rbx
0x14000c0d4  retn
```
