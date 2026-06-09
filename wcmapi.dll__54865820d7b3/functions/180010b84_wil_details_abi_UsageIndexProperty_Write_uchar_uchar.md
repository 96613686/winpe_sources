# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x180010b84`
- end: `0x180010c5b`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `215`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f4e8`

## callees

- `0x18000aaf4`
- `0x180010b84`

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
0x180010b84  push    rbx
0x180010b86  push    rsi
0x180010b87  push    rdi
0x180010b88  push    r12
0x180010b8a  push    r14
0x180010b8c  push    r15
0x180010b8e  sub     rsp, 28h
0x180010b92  mov     rsi, rcx
0x180010b95  mov     rdi, r8
0x180010b98  mov     rcx, [rdx]; Destination
0x180010b9b  mov     r12, rdx
0x180010b9e  cmp     byte ptr [rsi+2], 1
0x180010ba2  jnz     short loc_180010BC6
0x180010ba4  lea     rbx, [rcx+2]
0x180010ba8  cmp     rbx, r8
0x180010bab  ja      short loc_180010C29
0x180010bad  movzx   eax, word ptr [rsi+4]
0x180010bb1  lea     r8, [rsp+58h+arg_0]
0x180010bb6  mov     r9d, 2
0x180010bbc  mov     [rsp+58h+arg_0], ax
0x180010bc1  mov     edx, r9d
0x180010bc4  jmp     short loc_180010BE4
0x180010bc6  cmp     byte ptr [rsi+2], 2
0x180010bca  mov     rbx, rcx
0x180010bcd  jnz     short loc_180010BE9
0x180010bcf  lea     rbx, [rcx+4]
0x180010bd3  cmp     rbx, rdi
0x180010bd6  ja      short loc_180010C29
0x180010bd8  mov     edx, 4; DestinationSize
0x180010bdd  lea     r8, [rsi+4]; Source
0x180010be1  mov     r9d, edx; SourceSize
0x180010be4  call    memcpy_s
0x180010be9  cmp     word ptr [rsi], 0
0x180010bed  jnz     short loc_180010C18
0x180010bef  lea     r15, [rbx+2]
0x180010bf3  cmp     r15, rdi
0x180010bf6  ja      short loc_180010C29
0x180010bf8  lea     r14, [rsi+8]
0x180010bfc  mov     rdx, rdi
0x180010bff  sub     rdx, rbx; DestinationSize
0x180010c02  mov     r8, r14; Source
0x180010c05  mov     r9d, 2; SourceSize
0x180010c0b  mov     rcx, rbx; Destination
0x180010c0e  call    memcpy_s
0x180010c13  mov     rbx, r15
0x180010c16  jmp     short loc_180010C1C
0x180010c18  lea     r14, [rsi+8]
0x180010c1c  movzx   r9d, word ptr [r14]; SourceSize
0x180010c20  lea     rax, [r9+rbx]
0x180010c24  cmp     rax, rdi
0x180010c27  jbe     short loc_180010C2D
0x180010c29  xor     al, al
0x180010c2b  jmp     short loc_180010C4C
0x180010c2d  mov     r8, [rsi+18h]; Source
0x180010c31  sub     rdi, rbx
0x180010c34  mov     rdx, rdi; DestinationSize
0x180010c37  mov     rcx, rbx; Destination
0x180010c3a  call    memcpy_s
0x180010c3f  movzx   ecx, word ptr [r14]
0x180010c43  mov     al, 1
0x180010c45  add     rcx, rbx
0x180010c48  mov     [r12], rcx
0x180010c4c  add     rsp, 28h
0x180010c50  pop     r15
0x180010c52  pop     r14
0x180010c54  pop     r12
0x180010c56  pop     rdi
0x180010c57  pop     rsi
0x180010c58  pop     rbx
0x180010c59  retn
```
