# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x18000c2e0`
- end: `0x18000c3b7`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `215`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003df4`

## callees

- `0x18000c2e0`
- `0x18001028c`

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
0x18000c2e0  push    rbx
0x18000c2e2  push    rsi
0x18000c2e3  push    rdi
0x18000c2e4  push    r12
0x18000c2e6  push    r14
0x18000c2e8  push    r15
0x18000c2ea  sub     rsp, 28h
0x18000c2ee  mov     rsi, rcx
0x18000c2f1  mov     rdi, r8
0x18000c2f4  mov     rcx, [rdx]; Destination
0x18000c2f7  mov     r12, rdx
0x18000c2fa  cmp     byte ptr [rsi+2], 1
0x18000c2fe  jnz     short loc_18000C322
0x18000c300  lea     rbx, [rcx+2]
0x18000c304  cmp     rbx, r8
0x18000c307  ja      short loc_18000C385
0x18000c309  movzx   eax, word ptr [rsi+4]
0x18000c30d  lea     r8, [rsp+58h+arg_0]
0x18000c312  mov     r9d, 2
0x18000c318  mov     [rsp+58h+arg_0], ax
0x18000c31d  mov     edx, r9d
0x18000c320  jmp     short loc_18000C340
0x18000c322  cmp     byte ptr [rsi+2], 2
0x18000c326  mov     rbx, rcx
0x18000c329  jnz     short loc_18000C345
0x18000c32b  lea     rbx, [rcx+4]
0x18000c32f  cmp     rbx, rdi
0x18000c332  ja      short loc_18000C385
0x18000c334  mov     edx, 4; DestinationSize
0x18000c339  lea     r8, [rsi+4]; Source
0x18000c33d  mov     r9d, edx; SourceSize
0x18000c340  call    memcpy_s
0x18000c345  cmp     word ptr [rsi], 0
0x18000c349  jnz     short loc_18000C374
0x18000c34b  lea     r15, [rbx+2]
0x18000c34f  cmp     r15, rdi
0x18000c352  ja      short loc_18000C385
0x18000c354  lea     r14, [rsi+8]
0x18000c358  mov     rdx, rdi
0x18000c35b  sub     rdx, rbx; DestinationSize
0x18000c35e  mov     r8, r14; Source
0x18000c361  mov     r9d, 2; SourceSize
0x18000c367  mov     rcx, rbx; Destination
0x18000c36a  call    memcpy_s
0x18000c36f  mov     rbx, r15
0x18000c372  jmp     short loc_18000C378
0x18000c374  lea     r14, [rsi+8]
0x18000c378  movzx   r9d, word ptr [r14]; SourceSize
0x18000c37c  lea     rax, [r9+rbx]
0x18000c380  cmp     rax, rdi
0x18000c383  jbe     short loc_18000C389
0x18000c385  xor     al, al
0x18000c387  jmp     short loc_18000C3A8
0x18000c389  mov     r8, [rsi+18h]; Source
0x18000c38d  sub     rdi, rbx
0x18000c390  mov     rdx, rdi; DestinationSize
0x18000c393  mov     rcx, rbx; Destination
0x18000c396  call    memcpy_s
0x18000c39b  movzx   ecx, word ptr [r14]
0x18000c39f  mov     al, 1
0x18000c3a1  add     rcx, rbx
0x18000c3a4  mov     [r12], rcx
0x18000c3a8  add     rsp, 28h
0x18000c3ac  pop     r15
0x18000c3ae  pop     r14
0x18000c3b0  pop     r12
0x18000c3b2  pop     rdi
0x18000c3b3  pop     rsi
0x18000c3b4  pop     rbx
0x18000c3b5  retn
```
