# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x180008c2c`
- end: `0x180008d02`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `214`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180007164`

## callees

- `0x180001f8c`
- `0x180008c2c`

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
0x180008c2c  push    rbx
0x180008c2e  push    rsi
0x180008c2f  push    rdi
0x180008c30  push    r12
0x180008c32  push    r14
0x180008c34  push    r15
0x180008c36  sub     rsp, 28h
0x180008c3a  mov     rsi, rcx
0x180008c3d  mov     rdi, r8
0x180008c40  mov     rcx, [rdx]; Destination
0x180008c43  mov     r12, rdx
0x180008c46  cmp     byte ptr [rsi+2], 1
0x180008c4a  jnz     short loc_180008C6E
0x180008c4c  lea     rbx, [rcx+2]
0x180008c50  cmp     rbx, r8
0x180008c53  ja      short loc_180008CD1
0x180008c55  movzx   eax, word ptr [rsi+4]
0x180008c59  lea     r8, [rsp+58h+arg_0]
0x180008c5e  mov     r9d, 2
0x180008c64  mov     [rsp+58h+arg_0], ax
0x180008c69  mov     edx, r9d
0x180008c6c  jmp     short loc_180008C8C
0x180008c6e  cmp     byte ptr [rsi+2], 2
0x180008c72  mov     rbx, rcx
0x180008c75  jnz     short loc_180008C91
0x180008c77  lea     rbx, [rcx+4]
0x180008c7b  cmp     rbx, rdi
0x180008c7e  ja      short loc_180008CD1
0x180008c80  mov     edx, 4; DestinationSize
0x180008c85  lea     r8, [rsi+4]; Source
0x180008c89  mov     r9d, edx; SourceSize
0x180008c8c  call    memcpy_s
0x180008c91  cmp     word ptr [rsi], 0
0x180008c95  jnz     short loc_180008CC0
0x180008c97  lea     r15, [rbx+2]
0x180008c9b  cmp     r15, rdi
0x180008c9e  ja      short loc_180008CD1
0x180008ca0  lea     r14, [rsi+8]
0x180008ca4  mov     rdx, rdi
0x180008ca7  sub     rdx, rbx; DestinationSize
0x180008caa  mov     r8, r14; Source
0x180008cad  mov     r9d, 2; SourceSize
0x180008cb3  mov     rcx, rbx; Destination
0x180008cb6  call    memcpy_s
0x180008cbb  mov     rbx, r15
0x180008cbe  jmp     short loc_180008CC4
0x180008cc0  lea     r14, [rsi+8]
0x180008cc4  movzx   r9d, word ptr [r14]; SourceSize
0x180008cc8  lea     rax, [r9+rbx]
0x180008ccc  cmp     rax, rdi
0x180008ccf  jbe     short loc_180008CD5
0x180008cd1  xor     al, al
0x180008cd3  jmp     short loc_180008CF4
0x180008cd5  mov     r8, [rsi+18h]; Source
0x180008cd9  sub     rdi, rbx
0x180008cdc  mov     rdx, rdi; DestinationSize
0x180008cdf  mov     rcx, rbx; Destination
0x180008ce2  call    memcpy_s
0x180008ce7  movzx   ecx, word ptr [r14]
0x180008ceb  mov     al, 1
0x180008ced  add     rcx, rbx
0x180008cf0  mov     [r12], rcx
0x180008cf4  add     rsp, 28h
0x180008cf8  pop     r15
0x180008cfa  pop     r14
0x180008cfc  pop     r12
0x180008cfe  pop     rdi
0x180008cff  pop     rsi
0x180008d00  pop     rbx
0x180008d01  retn
```
