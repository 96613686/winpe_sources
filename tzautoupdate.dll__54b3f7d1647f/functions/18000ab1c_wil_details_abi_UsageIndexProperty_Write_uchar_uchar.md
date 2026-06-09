# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x18000ab1c`
- end: `0x18000abf5`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *this, char **, char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180007e38`

## callees

- `0x18000ab1c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000ab7c`
- `msvcrt!memcpy_s` at `0x18000aba7`
- `msvcrt!memcpy_s` at `0x18000abd4`
- `msvcrt!memcpy_s` at `0x18000ab7c`
- `msvcrt!memcpy_s` at `0x18000aba7`
- `msvcrt!memcpy_s` at `0x18000abd4`

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
0x18000ab1c  push    rbx
0x18000ab1e  push    rsi
0x18000ab1f  push    rdi
0x18000ab20  push    r12
0x18000ab22  push    r14
0x18000ab24  push    r15
0x18000ab26  sub     rsp, 28h
0x18000ab2a  mov     rsi, rcx
0x18000ab2d  mov     rdi, r8
0x18000ab30  mov     rcx, [rdx]; Destination
0x18000ab33  mov     r12, rdx
0x18000ab36  cmp     byte ptr [rsi+2], 1
0x18000ab3a  jnz     short loc_18000AB5E
0x18000ab3c  lea     rbx, [rcx+2]
0x18000ab40  cmp     rbx, r8
0x18000ab43  ja      short loc_18000ABC3
0x18000ab45  movzx   eax, word ptr [rsi+4]
0x18000ab49  lea     r8, [rsp+58h+arg_0]
0x18000ab4e  mov     r9d, 2
0x18000ab54  mov     [rsp+58h+arg_0], ax
0x18000ab59  mov     edx, r9d
0x18000ab5c  jmp     short loc_18000AB7C
0x18000ab5e  cmp     byte ptr [rsi+2], 2
0x18000ab62  mov     rbx, rcx
0x18000ab65  jnz     short loc_18000AB82
0x18000ab67  lea     rbx, [rcx+4]
0x18000ab6b  cmp     rbx, rdi
0x18000ab6e  ja      short loc_18000ABC3
0x18000ab70  mov     edx, 4; DestinationSize
0x18000ab75  lea     r8, [rsi+4]; Source
0x18000ab79  mov     r9d, edx; SourceSize
0x18000ab7c  call    cs:__imp_memcpy_s
0x18000ab82  cmp     word ptr [rsi], 0
0x18000ab86  jnz     short loc_18000ABB2
0x18000ab88  lea     r15, [rbx+2]
0x18000ab8c  cmp     r15, rdi
0x18000ab8f  ja      short loc_18000ABC3
0x18000ab91  lea     r14, [rsi+8]
0x18000ab95  mov     rdx, rdi
0x18000ab98  sub     rdx, rbx; DestinationSize
0x18000ab9b  mov     r8, r14; Source
0x18000ab9e  mov     r9d, 2; SourceSize
0x18000aba4  mov     rcx, rbx; Destination
0x18000aba7  call    cs:__imp_memcpy_s
0x18000abad  mov     rbx, r15
0x18000abb0  jmp     short loc_18000ABB6
0x18000abb2  lea     r14, [rsi+8]
0x18000abb6  movzx   r9d, word ptr [r14]; SourceSize
0x18000abba  lea     rax, [r9+rbx]
0x18000abbe  cmp     rax, rdi
0x18000abc1  jbe     short loc_18000ABC7
0x18000abc3  xor     al, al
0x18000abc5  jmp     short loc_18000ABE7
0x18000abc7  mov     r8, [rsi+18h]; Source
0x18000abcb  sub     rdi, rbx
0x18000abce  mov     rdx, rdi; DestinationSize
0x18000abd1  mov     rcx, rbx; Destination
0x18000abd4  call    cs:__imp_memcpy_s
0x18000abda  movzx   ecx, word ptr [r14]
0x18000abde  mov     al, 1
0x18000abe0  add     rcx, rbx
0x18000abe3  mov     [r12], rcx
0x18000abe7  add     rsp, 28h
0x18000abeb  pop     r15
0x18000abed  pop     r14
0x18000abef  pop     r12
0x18000abf1  pop     rdi
0x18000abf2  pop     rsi
0x18000abf3  pop     rbx
0x18000abf4  retn
```
