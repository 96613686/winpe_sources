# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x180012148`
- end: `0x180012221`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800101d8`

## callees

- `0x180012148`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800121a8`
- `msvcrt!memcpy_s` at `0x1800121d3`
- `msvcrt!memcpy_s` at `0x180012200`
- `msvcrt!memcpy_s` at `0x1800121a8`
- `msvcrt!memcpy_s` at `0x1800121d3`
- `msvcrt!memcpy_s` at `0x180012200`

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
0x180012148  push    rbx
0x18001214a  push    rsi
0x18001214b  push    rdi
0x18001214c  push    r12
0x18001214e  push    r14
0x180012150  push    r15
0x180012152  sub     rsp, 28h
0x180012156  mov     rsi, rcx
0x180012159  mov     rdi, r8
0x18001215c  mov     rcx, [rdx]; Destination
0x18001215f  mov     r12, rdx
0x180012162  cmp     byte ptr [rsi+2], 1
0x180012166  jnz     short loc_18001218A
0x180012168  lea     rbx, [rcx+2]
0x18001216c  cmp     rbx, r8
0x18001216f  ja      short loc_1800121EF
0x180012171  movzx   eax, word ptr [rsi+4]
0x180012175  lea     r8, [rsp+58h+arg_0]
0x18001217a  mov     r9d, 2
0x180012180  mov     [rsp+58h+arg_0], ax
0x180012185  mov     edx, r9d
0x180012188  jmp     short loc_1800121A8
0x18001218a  cmp     byte ptr [rsi+2], 2
0x18001218e  mov     rbx, rcx
0x180012191  jnz     short loc_1800121AE
0x180012193  lea     rbx, [rcx+4]
0x180012197  cmp     rbx, rdi
0x18001219a  ja      short loc_1800121EF
0x18001219c  mov     edx, 4; DestinationSize
0x1800121a1  lea     r8, [rsi+4]; Source
0x1800121a5  mov     r9d, edx; SourceSize
0x1800121a8  call    cs:__imp_memcpy_s
0x1800121ae  cmp     word ptr [rsi], 0
0x1800121b2  jnz     short loc_1800121DE
0x1800121b4  lea     r15, [rbx+2]
0x1800121b8  cmp     r15, rdi
0x1800121bb  ja      short loc_1800121EF
0x1800121bd  lea     r14, [rsi+8]
0x1800121c1  mov     rdx, rdi
0x1800121c4  sub     rdx, rbx; DestinationSize
0x1800121c7  mov     r8, r14; Source
0x1800121ca  mov     r9d, 2; SourceSize
0x1800121d0  mov     rcx, rbx; Destination
0x1800121d3  call    cs:__imp_memcpy_s
0x1800121d9  mov     rbx, r15
0x1800121dc  jmp     short loc_1800121E2
0x1800121de  lea     r14, [rsi+8]
0x1800121e2  movzx   r9d, word ptr [r14]; SourceSize
0x1800121e6  lea     rax, [r9+rbx]
0x1800121ea  cmp     rax, rdi
0x1800121ed  jbe     short loc_1800121F3
0x1800121ef  xor     al, al
0x1800121f1  jmp     short loc_180012213
0x1800121f3  mov     r8, [rsi+18h]; Source
0x1800121f7  sub     rdi, rbx
0x1800121fa  mov     rdx, rdi; DestinationSize
0x1800121fd  mov     rcx, rbx; Destination
0x180012200  call    cs:__imp_memcpy_s
0x180012206  movzx   ecx, word ptr [r14]
0x18001220a  mov     al, 1
0x18001220c  add     rcx, rbx
0x18001220f  mov     [r12], rcx
0x180012213  add     rsp, 28h
0x180012217  pop     r15
0x180012219  pop     r14
0x18001221b  pop     r12
0x18001221d  pop     rdi
0x18001221e  pop     rsi
0x18001221f  pop     rbx
0x180012220  retn
```
