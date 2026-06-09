# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x18000eea0`
- end: `0x18000ef79`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000cf04`

## callees

- `0x18000eea0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000ef00`
- `msvcrt!memcpy_s` at `0x18000ef2b`
- `msvcrt!memcpy_s` at `0x18000ef58`
- `msvcrt!memcpy_s` at `0x18000ef00`
- `msvcrt!memcpy_s` at `0x18000ef2b`
- `msvcrt!memcpy_s` at `0x18000ef58`

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
0x18000eea0  push    rbx
0x18000eea2  push    rsi
0x18000eea3  push    rdi
0x18000eea4  push    r12
0x18000eea6  push    r14
0x18000eea8  push    r15
0x18000eeaa  sub     rsp, 28h
0x18000eeae  mov     rsi, rcx
0x18000eeb1  mov     rdi, r8
0x18000eeb4  mov     rcx, [rdx]; Destination
0x18000eeb7  mov     r12, rdx
0x18000eeba  cmp     byte ptr [rsi+2], 1
0x18000eebe  jnz     short loc_18000EEE2
0x18000eec0  lea     rbx, [rcx+2]
0x18000eec4  cmp     rbx, r8
0x18000eec7  ja      short loc_18000EF47
0x18000eec9  movzx   eax, word ptr [rsi+4]
0x18000eecd  lea     r8, [rsp+58h+arg_0]
0x18000eed2  mov     r9d, 2
0x18000eed8  mov     [rsp+58h+arg_0], ax
0x18000eedd  mov     edx, r9d
0x18000eee0  jmp     short loc_18000EF00
0x18000eee2  cmp     byte ptr [rsi+2], 2
0x18000eee6  mov     rbx, rcx
0x18000eee9  jnz     short loc_18000EF06
0x18000eeeb  lea     rbx, [rcx+4]
0x18000eeef  cmp     rbx, rdi
0x18000eef2  ja      short loc_18000EF47
0x18000eef4  mov     edx, 4; DestinationSize
0x18000eef9  lea     r8, [rsi+4]; Source
0x18000eefd  mov     r9d, edx; SourceSize
0x18000ef00  call    cs:__imp_memcpy_s
0x18000ef06  cmp     word ptr [rsi], 0
0x18000ef0a  jnz     short loc_18000EF36
0x18000ef0c  lea     r15, [rbx+2]
0x18000ef10  cmp     r15, rdi
0x18000ef13  ja      short loc_18000EF47
0x18000ef15  lea     r14, [rsi+8]
0x18000ef19  mov     rdx, rdi
0x18000ef1c  sub     rdx, rbx; DestinationSize
0x18000ef1f  mov     r8, r14; Source
0x18000ef22  mov     r9d, 2; SourceSize
0x18000ef28  mov     rcx, rbx; Destination
0x18000ef2b  call    cs:__imp_memcpy_s
0x18000ef31  mov     rbx, r15
0x18000ef34  jmp     short loc_18000EF3A
0x18000ef36  lea     r14, [rsi+8]
0x18000ef3a  movzx   r9d, word ptr [r14]; SourceSize
0x18000ef3e  lea     rax, [r9+rbx]
0x18000ef42  cmp     rax, rdi
0x18000ef45  jbe     short loc_18000EF4B
0x18000ef47  xor     al, al
0x18000ef49  jmp     short loc_18000EF6B
0x18000ef4b  mov     r8, [rsi+18h]; Source
0x18000ef4f  sub     rdi, rbx
0x18000ef52  mov     rdx, rdi; DestinationSize
0x18000ef55  mov     rcx, rbx; Destination
0x18000ef58  call    cs:__imp_memcpy_s
0x18000ef5e  movzx   ecx, word ptr [r14]
0x18000ef62  mov     al, 1
0x18000ef64  add     rcx, rbx
0x18000ef67  mov     [r12], rcx
0x18000ef6b  add     rsp, 28h
0x18000ef6f  pop     r15
0x18000ef71  pop     r14
0x18000ef73  pop     r12
0x18000ef75  pop     rdi
0x18000ef76  pop     rsi
0x18000ef77  pop     rbx
0x18000ef78  retn
```
