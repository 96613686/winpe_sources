# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x14000a9c4`
- end: `0x14000aa9a`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `214`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *this, char **, char *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140009a10`

## callees

- `0x14000220c`
- `0x14000a9c4`

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
0x14000a9c4  push    rbx
0x14000a9c6  push    rsi
0x14000a9c7  push    rdi
0x14000a9c8  push    r12
0x14000a9ca  push    r14
0x14000a9cc  push    r15
0x14000a9ce  sub     rsp, 28h
0x14000a9d2  mov     rsi, rcx
0x14000a9d5  mov     rdi, r8
0x14000a9d8  mov     rcx, [rdx]; Destination
0x14000a9db  mov     r12, rdx
0x14000a9de  cmp     byte ptr [rsi+2], 1
0x14000a9e2  jnz     short loc_14000AA06
0x14000a9e4  lea     rbx, [rcx+2]
0x14000a9e8  cmp     rbx, r8
0x14000a9eb  ja      short loc_14000AA69
0x14000a9ed  movzx   eax, word ptr [rsi+4]
0x14000a9f1  lea     r8, [rsp+58h+arg_0]
0x14000a9f6  mov     r9d, 2
0x14000a9fc  mov     [rsp+58h+arg_0], ax
0x14000aa01  mov     edx, r9d
0x14000aa04  jmp     short loc_14000AA24
0x14000aa06  cmp     byte ptr [rsi+2], 2
0x14000aa0a  mov     rbx, rcx
0x14000aa0d  jnz     short loc_14000AA29
0x14000aa0f  lea     rbx, [rcx+4]
0x14000aa13  cmp     rbx, rdi
0x14000aa16  ja      short loc_14000AA69
0x14000aa18  mov     edx, 4; DestinationSize
0x14000aa1d  lea     r8, [rsi+4]; Source
0x14000aa21  mov     r9d, edx; SourceSize
0x14000aa24  call    memcpy_s
0x14000aa29  cmp     word ptr [rsi], 0
0x14000aa2d  jnz     short loc_14000AA58
0x14000aa2f  lea     r15, [rbx+2]
0x14000aa33  cmp     r15, rdi
0x14000aa36  ja      short loc_14000AA69
0x14000aa38  lea     r14, [rsi+8]
0x14000aa3c  mov     rdx, rdi
0x14000aa3f  sub     rdx, rbx; DestinationSize
0x14000aa42  mov     r8, r14; Source
0x14000aa45  mov     r9d, 2; SourceSize
0x14000aa4b  mov     rcx, rbx; Destination
0x14000aa4e  call    memcpy_s
0x14000aa53  mov     rbx, r15
0x14000aa56  jmp     short loc_14000AA5C
0x14000aa58  lea     r14, [rsi+8]
0x14000aa5c  movzx   r9d, word ptr [r14]; SourceSize
0x14000aa60  lea     rax, [r9+rbx]
0x14000aa64  cmp     rax, rdi
0x14000aa67  jbe     short loc_14000AA6D
0x14000aa69  xor     al, al
0x14000aa6b  jmp     short loc_14000AA8C
0x14000aa6d  mov     r8, [rsi+18h]; Source
0x14000aa71  sub     rdi, rbx
0x14000aa74  mov     rdx, rdi; DestinationSize
0x14000aa77  mov     rcx, rbx; Destination
0x14000aa7a  call    memcpy_s
0x14000aa7f  movzx   ecx, word ptr [r14]
0x14000aa83  mov     al, 1
0x14000aa85  add     rcx, rbx
0x14000aa88  mov     [r12], rcx
0x14000aa8c  add     rsp, 28h
0x14000aa90  pop     r15
0x14000aa92  pop     r14
0x14000aa94  pop     r12
0x14000aa96  pop     rdi
0x14000aa97  pop     rsi
0x14000aa98  pop     rbx
0x14000aa99  retn
```
