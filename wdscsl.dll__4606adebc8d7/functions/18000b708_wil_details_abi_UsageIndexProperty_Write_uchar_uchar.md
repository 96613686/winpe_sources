# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x18000b708`
- end: `0x18000b811`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `265`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180008e44`

## callees

- `0x18000b708`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000b776`
- `msvcrt!memcpy_s` at `0x18000b7aa`
- `msvcrt!memcpy_s` at `0x18000b7dd`
- `msvcrt!memcpy_s` at `0x18000b776`
- `msvcrt!memcpy_s` at `0x18000b7aa`
- `msvcrt!memcpy_s` at `0x18000b7dd`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Write(
        wil::details_abi::UsageIndexProperty *this,
        char **a2,
        char *a3)
{
  char *v4; // rbx
  char *v7; // r14
  char *v8; // r8
  rsize_t v9; // r9
  rsize_t v10; // rdx
  unsigned __int16 *v11; // r14
  rsize_t v12; // r9
  bool result; // al
  __int16 v14; // [rsp+40h] [rbp+8h] BYREF

  v4 = *a2;
  if ( *((_BYTE *)this + 2) == 1 )
  {
    v7 = v4 + 2;
    if ( v4 + 2 > a3 )
      return 0;
    v8 = (char *)&v14;
    v9 = 2;
    v14 = *((_WORD *)this + 2);
    v10 = 2;
  }
  else
  {
    if ( *((_BYTE *)this + 2) != 2 )
      goto LABEL_8;
    v7 = v4 + 4;
    if ( v4 + 4 > a3 )
      return 0;
    v10 = 4;
    v8 = (char *)this + 4;
    v9 = 4;
  }
  memcpy_s(v4, v10, v8, v9);
  v4 = v7;
LABEL_8:
  if ( !*(_WORD *)this )
  {
    if ( v4 + 2 <= a3 )
    {
      v11 = (unsigned __int16 *)((char *)this + 8);
      memcpy_s(v4, a3 - v4, (char *)this + 8, 2u);
      v4 += 2;
      goto LABEL_12;
    }
    return 0;
  }
  v11 = (unsigned __int16 *)((char *)this + 8);
LABEL_12:
  v12 = *v11;
  if ( &v4[v12] > a3 )
    return 0;
  memcpy_s(v4, a3 - v4, *((const void *const *)this + 3), v12);
  result = 1;
  *a2 = &v4[*v11];
  return result;
}

```

## disassembly

```asm
0x18000b708  mov     r11, rsp
0x18000b70b  mov     [r11+10h], rbx
0x18000b70f  mov     [r11+18h], rsi
0x18000b713  mov     [r11+20h], rdi
0x18000b717  push    r12
0x18000b719  push    r14
0x18000b71b  push    r15
0x18000b71d  sub     rsp, 20h
0x18000b721  cmp     byte ptr [rcx+2], 1
0x18000b725  mov     rdi, r8
0x18000b728  mov     rbx, [rdx]
0x18000b72b  mov     r12, rdx
0x18000b72e  mov     rsi, rcx
0x18000b731  jnz     short loc_18000B758
0x18000b733  lea     r14, [rbx+2]
0x18000b737  cmp     r14, r8
0x18000b73a  ja      loc_18000B7CC
0x18000b740  movzx   eax, word ptr [rcx+4]
0x18000b744  lea     r8, [r11+8]
0x18000b748  mov     r9d, 2
0x18000b74e  mov     [rsp+38h+arg_0], ax
0x18000b753  mov     edx, r9d
0x18000b756  jmp     short loc_18000B773
0x18000b758  cmp     byte ptr [rcx+2], 2
0x18000b75c  jnz     short loc_18000B785
0x18000b75e  lea     r14, [rbx+4]
0x18000b762  cmp     r14, rdi
0x18000b765  ja      short loc_18000B7CC
0x18000b767  mov     edx, 4; DestinationSize
0x18000b76c  lea     r8, [rcx+4]; Source
0x18000b770  mov     r9d, edx; SourceSize
0x18000b773  mov     rcx, rbx; Destination
0x18000b776  call    cs:__imp_memcpy_s
0x18000b77d  nop     dword ptr [rax+rax+00h]
0x18000b782  mov     rbx, r14
0x18000b785  cmp     word ptr [rsi], 0
0x18000b789  jnz     short loc_18000B7BB
0x18000b78b  lea     r15, [rbx+2]
0x18000b78f  cmp     r15, rdi
0x18000b792  ja      short loc_18000B7CC
0x18000b794  lea     r14, [rsi+8]
0x18000b798  mov     rdx, rdi
0x18000b79b  sub     rdx, rbx; DestinationSize
0x18000b79e  mov     r8, r14; Source
0x18000b7a1  mov     r9d, 2; SourceSize
0x18000b7a7  mov     rcx, rbx; Destination
0x18000b7aa  call    cs:__imp_memcpy_s
0x18000b7b1  nop     dword ptr [rax+rax+00h]
0x18000b7b6  mov     rbx, r15
0x18000b7b9  jmp     short loc_18000B7BF
0x18000b7bb  lea     r14, [rsi+8]
0x18000b7bf  movzx   r9d, word ptr [r14]; SourceSize
0x18000b7c3  lea     rax, [r9+rbx]
0x18000b7c7  cmp     rax, rdi
0x18000b7ca  jbe     short loc_18000B7D0
0x18000b7cc  xor     al, al
0x18000b7ce  jmp     short loc_18000B7F6
0x18000b7d0  mov     r8, [rsi+18h]; Source
0x18000b7d4  sub     rdi, rbx
0x18000b7d7  mov     rdx, rdi; DestinationSize
0x18000b7da  mov     rcx, rbx; Destination
0x18000b7dd  call    cs:__imp_memcpy_s
0x18000b7e4  nop     dword ptr [rax+rax+00h]
0x18000b7e9  movzx   ecx, word ptr [r14]
0x18000b7ed  mov     al, 1
0x18000b7ef  add     rcx, rbx
0x18000b7f2  mov     [r12], rcx
0x18000b7f6  mov     rbx, [rsp+38h+arg_8]
0x18000b7fb  mov     rsi, [rsp+38h+arg_10]
0x18000b800  mov     rdi, [rsp+38h+arg_18]
0x18000b805  add     rsp, 20h
0x18000b809  pop     r15
0x18000b80b  pop     r14
0x18000b80d  pop     r12
0x18000b80f  retn
```
