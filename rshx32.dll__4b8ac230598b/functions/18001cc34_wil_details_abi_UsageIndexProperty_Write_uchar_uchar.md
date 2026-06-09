# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x18001cc34`
- end: `0x18001cd0d`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *this, char **, char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001b934`

## callees

- `0x18001cc34`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18001cc94`
- `msvcrt!memcpy_s` at `0x18001ccbf`
- `msvcrt!memcpy_s` at `0x18001ccec`
- `msvcrt!memcpy_s` at `0x18001cc94`
- `msvcrt!memcpy_s` at `0x18001ccbf`
- `msvcrt!memcpy_s` at `0x18001ccec`

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
0x18001cc34  push    rbx
0x18001cc36  push    rsi
0x18001cc37  push    rdi
0x18001cc38  push    r12
0x18001cc3a  push    r14
0x18001cc3c  push    r15
0x18001cc3e  sub     rsp, 28h
0x18001cc42  mov     rsi, rcx
0x18001cc45  mov     rdi, r8
0x18001cc48  mov     rcx, [rdx]; Destination
0x18001cc4b  mov     r12, rdx
0x18001cc4e  cmp     byte ptr [rsi+2], 1
0x18001cc52  jnz     short loc_18001CC76
0x18001cc54  lea     rbx, [rcx+2]
0x18001cc58  cmp     rbx, r8
0x18001cc5b  ja      short loc_18001CCDB
0x18001cc5d  movzx   eax, word ptr [rsi+4]
0x18001cc61  lea     r8, [rsp+58h+arg_0]
0x18001cc66  mov     r9d, 2
0x18001cc6c  mov     [rsp+58h+arg_0], ax
0x18001cc71  mov     edx, r9d
0x18001cc74  jmp     short loc_18001CC94
0x18001cc76  cmp     byte ptr [rsi+2], 2
0x18001cc7a  mov     rbx, rcx
0x18001cc7d  jnz     short loc_18001CC9A
0x18001cc7f  lea     rbx, [rcx+4]
0x18001cc83  cmp     rbx, rdi
0x18001cc86  ja      short loc_18001CCDB
0x18001cc88  mov     edx, 4; DestinationSize
0x18001cc8d  lea     r8, [rsi+4]; Source
0x18001cc91  mov     r9d, edx; SourceSize
0x18001cc94  call    cs:__imp_memcpy_s
0x18001cc9a  cmp     word ptr [rsi], 0
0x18001cc9e  jnz     short loc_18001CCCA
0x18001cca0  lea     r15, [rbx+2]
0x18001cca4  cmp     r15, rdi
0x18001cca7  ja      short loc_18001CCDB
0x18001cca9  lea     r14, [rsi+8]
0x18001ccad  mov     rdx, rdi
0x18001ccb0  sub     rdx, rbx; DestinationSize
0x18001ccb3  mov     r8, r14; Source
0x18001ccb6  mov     r9d, 2; SourceSize
0x18001ccbc  mov     rcx, rbx; Destination
0x18001ccbf  call    cs:__imp_memcpy_s
0x18001ccc5  mov     rbx, r15
0x18001ccc8  jmp     short loc_18001CCCE
0x18001ccca  lea     r14, [rsi+8]
0x18001ccce  movzx   r9d, word ptr [r14]; SourceSize
0x18001ccd2  lea     rax, [r9+rbx]
0x18001ccd6  cmp     rax, rdi
0x18001ccd9  jbe     short loc_18001CCDF
0x18001ccdb  xor     al, al
0x18001ccdd  jmp     short loc_18001CCFF
0x18001ccdf  mov     r8, [rsi+18h]; Source
0x18001cce3  sub     rdi, rbx
0x18001cce6  mov     rdx, rdi; DestinationSize
0x18001cce9  mov     rcx, rbx; Destination
0x18001ccec  call    cs:__imp_memcpy_s
0x18001ccf2  movzx   ecx, word ptr [r14]
0x18001ccf6  mov     al, 1
0x18001ccf8  add     rcx, rbx
0x18001ccfb  mov     [r12], rcx
0x18001ccff  add     rsp, 28h
0x18001cd03  pop     r15
0x18001cd05  pop     r14
0x18001cd07  pop     r12
0x18001cd09  pop     rdi
0x18001cd0a  pop     rsi
0x18001cd0b  pop     rbx
0x18001cd0c  retn
```
