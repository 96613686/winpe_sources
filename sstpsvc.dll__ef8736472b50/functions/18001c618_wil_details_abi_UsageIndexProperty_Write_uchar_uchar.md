# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x18001c618`
- end: `0x18001c708`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `240`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001b25c`

## callees

- `0x18001c618`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18001c67c`
- `msvcrt!memcpy_s` at `0x18001c6ad`
- `msvcrt!memcpy_s` at `0x18001c6e0`
- `msvcrt!memcpy_s` at `0x18001c67c`
- `msvcrt!memcpy_s` at `0x18001c6ad`
- `msvcrt!memcpy_s` at `0x18001c6e0`

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
0x18001c618  push    rbx
0x18001c61a  push    rsi
0x18001c61b  push    rdi
0x18001c61c  push    r12
0x18001c61e  push    r14
0x18001c620  push    r15
0x18001c622  sub     rsp, 28h
0x18001c626  mov     rsi, rcx
0x18001c629  mov     rdi, r8
0x18001c62c  mov     rcx, [rdx]; Destination
0x18001c62f  mov     r12, rdx
0x18001c632  cmp     byte ptr [rsi+2], 1
0x18001c636  jnz     short loc_18001C65E
0x18001c638  lea     rbx, [rcx+2]
0x18001c63c  cmp     rbx, r8
0x18001c63f  ja      loc_18001C6CF
0x18001c645  movzx   eax, word ptr [rsi+4]
0x18001c649  lea     r8, [rsp+58h+arg_0]
0x18001c64e  mov     r9d, 2
0x18001c654  mov     [rsp+58h+arg_0], ax
0x18001c659  mov     edx, r9d
0x18001c65c  jmp     short loc_18001C67C
0x18001c65e  cmp     byte ptr [rsi+2], 2
0x18001c662  mov     rbx, rcx
0x18001c665  jnz     short loc_18001C688
0x18001c667  lea     rbx, [rcx+4]
0x18001c66b  cmp     rbx, rdi
0x18001c66e  ja      short loc_18001C6CF
0x18001c670  mov     edx, 4; DestinationSize
0x18001c675  lea     r8, [rsi+4]; Source
0x18001c679  mov     r9d, edx; SourceSize
0x18001c67c  call    cs:__imp_memcpy_s
0x18001c683  nop     dword ptr [rax+rax+00h]
0x18001c688  cmp     word ptr [rsi], 0
0x18001c68c  jnz     short loc_18001C6BE
0x18001c68e  lea     r15, [rbx+2]
0x18001c692  cmp     r15, rdi
0x18001c695  ja      short loc_18001C6CF
0x18001c697  lea     r14, [rsi+8]
0x18001c69b  mov     rdx, rdi
0x18001c69e  sub     rdx, rbx; DestinationSize
0x18001c6a1  mov     r8, r14; Source
0x18001c6a4  mov     r9d, 2; SourceSize
0x18001c6aa  mov     rcx, rbx; Destination
0x18001c6ad  call    cs:__imp_memcpy_s
0x18001c6b4  nop     dword ptr [rax+rax+00h]
0x18001c6b9  mov     rbx, r15
0x18001c6bc  jmp     short loc_18001C6C2
0x18001c6be  lea     r14, [rsi+8]
0x18001c6c2  movzx   r9d, word ptr [r14]; SourceSize
0x18001c6c6  lea     rax, [r9+rbx]
0x18001c6ca  cmp     rax, rdi
0x18001c6cd  jbe     short loc_18001C6D3
0x18001c6cf  xor     al, al
0x18001c6d1  jmp     short loc_18001C6F9
0x18001c6d3  mov     r8, [rsi+18h]; Source
0x18001c6d7  sub     rdi, rbx
0x18001c6da  mov     rdx, rdi; DestinationSize
0x18001c6dd  mov     rcx, rbx; Destination
0x18001c6e0  call    cs:__imp_memcpy_s
0x18001c6e7  nop     dword ptr [rax+rax+00h]
0x18001c6ec  movzx   ecx, word ptr [r14]
0x18001c6f0  mov     al, 1
0x18001c6f2  add     rcx, rbx
0x18001c6f5  mov     [r12], rcx
0x18001c6f9  add     rsp, 28h
0x18001c6fd  pop     r15
0x18001c6ff  pop     r14
0x18001c701  pop     r12
0x18001c703  pop     rdi
0x18001c704  pop     rsi
0x18001c705  pop     rbx
0x18001c706  retn
```
