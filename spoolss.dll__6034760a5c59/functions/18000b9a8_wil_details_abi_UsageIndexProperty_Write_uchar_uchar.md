# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x18000b9a8`
- end: `0x18000ba7e`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `214`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003af0`

## callees

- `0x18000b9a8`
- `0x18000f1d8`

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
0x18000b9a8  push    rbx
0x18000b9aa  push    rsi
0x18000b9ab  push    rdi
0x18000b9ac  push    r12
0x18000b9ae  push    r14
0x18000b9b0  push    r15
0x18000b9b2  sub     rsp, 28h
0x18000b9b6  mov     rsi, rcx
0x18000b9b9  mov     rdi, r8
0x18000b9bc  mov     rcx, [rdx]; Destination
0x18000b9bf  mov     r12, rdx
0x18000b9c2  cmp     byte ptr [rsi+2], 1
0x18000b9c6  jnz     short loc_18000B9EA
0x18000b9c8  lea     rbx, [rcx+2]
0x18000b9cc  cmp     rbx, r8
0x18000b9cf  ja      short loc_18000BA4D
0x18000b9d1  movzx   eax, word ptr [rsi+4]
0x18000b9d5  lea     r8, [rsp+58h+arg_0]
0x18000b9da  mov     r9d, 2
0x18000b9e0  mov     [rsp+58h+arg_0], ax
0x18000b9e5  mov     edx, r9d
0x18000b9e8  jmp     short loc_18000BA08
0x18000b9ea  cmp     byte ptr [rsi+2], 2
0x18000b9ee  mov     rbx, rcx
0x18000b9f1  jnz     short loc_18000BA0D
0x18000b9f3  lea     rbx, [rcx+4]
0x18000b9f7  cmp     rbx, rdi
0x18000b9fa  ja      short loc_18000BA4D
0x18000b9fc  mov     edx, 4; DestinationSize
0x18000ba01  lea     r8, [rsi+4]; Source
0x18000ba05  mov     r9d, edx; SourceSize
0x18000ba08  call    memcpy_s
0x18000ba0d  cmp     word ptr [rsi], 0
0x18000ba11  jnz     short loc_18000BA3C
0x18000ba13  lea     r15, [rbx+2]
0x18000ba17  cmp     r15, rdi
0x18000ba1a  ja      short loc_18000BA4D
0x18000ba1c  lea     r14, [rsi+8]
0x18000ba20  mov     rdx, rdi
0x18000ba23  sub     rdx, rbx; DestinationSize
0x18000ba26  mov     r8, r14; Source
0x18000ba29  mov     r9d, 2; SourceSize
0x18000ba2f  mov     rcx, rbx; Destination
0x18000ba32  call    memcpy_s
0x18000ba37  mov     rbx, r15
0x18000ba3a  jmp     short loc_18000BA40
0x18000ba3c  lea     r14, [rsi+8]
0x18000ba40  movzx   r9d, word ptr [r14]; SourceSize
0x18000ba44  lea     rax, [r9+rbx]
0x18000ba48  cmp     rax, rdi
0x18000ba4b  jbe     short loc_18000BA51
0x18000ba4d  xor     al, al
0x18000ba4f  jmp     short loc_18000BA70
0x18000ba51  mov     r8, [rsi+18h]; Source
0x18000ba55  sub     rdi, rbx
0x18000ba58  mov     rdx, rdi; DestinationSize
0x18000ba5b  mov     rcx, rbx; Destination
0x18000ba5e  call    memcpy_s
0x18000ba63  movzx   ecx, word ptr [r14]
0x18000ba67  mov     al, 1
0x18000ba69  add     rcx, rbx
0x18000ba6c  mov     [r12], rcx
0x18000ba70  add     rsp, 28h
0x18000ba74  pop     r15
0x18000ba76  pop     r14
0x18000ba78  pop     r12
0x18000ba7a  pop     rdi
0x18000ba7b  pop     rsi
0x18000ba7c  pop     rbx
0x18000ba7d  retn
```
