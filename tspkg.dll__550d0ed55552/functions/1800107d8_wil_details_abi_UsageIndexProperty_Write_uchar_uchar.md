# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x1800107d8`
- end: `0x1800108ae`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `214`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ae64`

## callees

- `0x1800107d8`
- `0x180010e4c`

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
0x1800107d8  push    rbx
0x1800107da  push    rsi
0x1800107db  push    rdi
0x1800107dc  push    r12
0x1800107de  push    r14
0x1800107e0  push    r15
0x1800107e2  sub     rsp, 28h
0x1800107e6  mov     rsi, rcx
0x1800107e9  mov     rdi, r8
0x1800107ec  mov     rcx, [rdx]; Destination
0x1800107ef  mov     r12, rdx
0x1800107f2  cmp     byte ptr [rsi+2], 1
0x1800107f6  jnz     short loc_18001081A
0x1800107f8  lea     rbx, [rcx+2]
0x1800107fc  cmp     rbx, r8
0x1800107ff  ja      short loc_18001087D
0x180010801  movzx   eax, word ptr [rsi+4]
0x180010805  lea     r8, [rsp+58h+arg_0]
0x18001080a  mov     r9d, 2
0x180010810  mov     [rsp+58h+arg_0], ax
0x180010815  mov     edx, r9d
0x180010818  jmp     short loc_180010838
0x18001081a  cmp     byte ptr [rsi+2], 2
0x18001081e  mov     rbx, rcx
0x180010821  jnz     short loc_18001083D
0x180010823  lea     rbx, [rcx+4]
0x180010827  cmp     rbx, rdi
0x18001082a  ja      short loc_18001087D
0x18001082c  mov     edx, 4; DestinationSize
0x180010831  lea     r8, [rsi+4]; Source
0x180010835  mov     r9d, edx; SourceSize
0x180010838  call    memcpy_s
0x18001083d  cmp     word ptr [rsi], 0
0x180010841  jnz     short loc_18001086C
0x180010843  lea     r15, [rbx+2]
0x180010847  cmp     r15, rdi
0x18001084a  ja      short loc_18001087D
0x18001084c  lea     r14, [rsi+8]
0x180010850  mov     rdx, rdi
0x180010853  sub     rdx, rbx; DestinationSize
0x180010856  mov     r8, r14; Source
0x180010859  mov     r9d, 2; SourceSize
0x18001085f  mov     rcx, rbx; Destination
0x180010862  call    memcpy_s
0x180010867  mov     rbx, r15
0x18001086a  jmp     short loc_180010870
0x18001086c  lea     r14, [rsi+8]
0x180010870  movzx   r9d, word ptr [r14]; SourceSize
0x180010874  lea     rax, [r9+rbx]
0x180010878  cmp     rax, rdi
0x18001087b  jbe     short loc_180010881
0x18001087d  xor     al, al
0x18001087f  jmp     short loc_1800108A0
0x180010881  mov     r8, [rsi+18h]; Source
0x180010885  sub     rdi, rbx
0x180010888  mov     rdx, rdi; DestinationSize
0x18001088b  mov     rcx, rbx; Destination
0x18001088e  call    memcpy_s
0x180010893  movzx   ecx, word ptr [r14]
0x180010897  mov     al, 1
0x180010899  add     rcx, rbx
0x18001089c  mov     [r12], rcx
0x1800108a0  add     rsp, 28h
0x1800108a4  pop     r15
0x1800108a6  pop     r14
0x1800108a8  pop     r12
0x1800108aa  pop     rdi
0x1800108ab  pop     rsi
0x1800108ac  pop     rbx
0x1800108ad  retn
```
