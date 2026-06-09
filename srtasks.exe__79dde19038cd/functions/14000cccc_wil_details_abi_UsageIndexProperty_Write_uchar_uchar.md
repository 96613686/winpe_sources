# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x14000cccc`
- end: `0x14000cda5`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *this, char **, char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000b500`

## callees

- `0x14000cccc`

## import_xrefs

- `msvcrt!memcpy_s` at `0x14000cd2c`
- `msvcrt!memcpy_s` at `0x14000cd57`
- `msvcrt!memcpy_s` at `0x14000cd84`
- `msvcrt!memcpy_s` at `0x14000cd2c`
- `msvcrt!memcpy_s` at `0x14000cd57`
- `msvcrt!memcpy_s` at `0x14000cd84`

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
0x14000cccc  push    rbx
0x14000ccce  push    rsi
0x14000cccf  push    rdi
0x14000ccd0  push    r12
0x14000ccd2  push    r14
0x14000ccd4  push    r15
0x14000ccd6  sub     rsp, 28h
0x14000ccda  mov     rsi, rcx
0x14000ccdd  mov     rdi, r8
0x14000cce0  mov     rcx, [rdx]; Destination
0x14000cce3  mov     r12, rdx
0x14000cce6  cmp     byte ptr [rsi+2], 1
0x14000ccea  jnz     short loc_14000CD0E
0x14000ccec  lea     rbx, [rcx+2]
0x14000ccf0  cmp     rbx, r8
0x14000ccf3  ja      short loc_14000CD73
0x14000ccf5  movzx   eax, word ptr [rsi+4]
0x14000ccf9  lea     r8, [rsp+58h+arg_0]
0x14000ccfe  mov     r9d, 2
0x14000cd04  mov     [rsp+58h+arg_0], ax
0x14000cd09  mov     edx, r9d
0x14000cd0c  jmp     short loc_14000CD2C
0x14000cd0e  cmp     byte ptr [rsi+2], 2
0x14000cd12  mov     rbx, rcx
0x14000cd15  jnz     short loc_14000CD32
0x14000cd17  lea     rbx, [rcx+4]
0x14000cd1b  cmp     rbx, rdi
0x14000cd1e  ja      short loc_14000CD73
0x14000cd20  mov     edx, 4; DestinationSize
0x14000cd25  lea     r8, [rsi+4]; Source
0x14000cd29  mov     r9d, edx; SourceSize
0x14000cd2c  call    cs:__imp_memcpy_s
0x14000cd32  cmp     word ptr [rsi], 0
0x14000cd36  jnz     short loc_14000CD62
0x14000cd38  lea     r15, [rbx+2]
0x14000cd3c  cmp     r15, rdi
0x14000cd3f  ja      short loc_14000CD73
0x14000cd41  lea     r14, [rsi+8]
0x14000cd45  mov     rdx, rdi
0x14000cd48  sub     rdx, rbx; DestinationSize
0x14000cd4b  mov     r8, r14; Source
0x14000cd4e  mov     r9d, 2; SourceSize
0x14000cd54  mov     rcx, rbx; Destination
0x14000cd57  call    cs:__imp_memcpy_s
0x14000cd5d  mov     rbx, r15
0x14000cd60  jmp     short loc_14000CD66
0x14000cd62  lea     r14, [rsi+8]
0x14000cd66  movzx   r9d, word ptr [r14]; SourceSize
0x14000cd6a  lea     rax, [r9+rbx]
0x14000cd6e  cmp     rax, rdi
0x14000cd71  jbe     short loc_14000CD77
0x14000cd73  xor     al, al
0x14000cd75  jmp     short loc_14000CD97
0x14000cd77  mov     r8, [rsi+18h]; Source
0x14000cd7b  sub     rdi, rbx
0x14000cd7e  mov     rdx, rdi; DestinationSize
0x14000cd81  mov     rcx, rbx; Destination
0x14000cd84  call    cs:__imp_memcpy_s
0x14000cd8a  movzx   ecx, word ptr [r14]
0x14000cd8e  mov     al, 1
0x14000cd90  add     rcx, rbx
0x14000cd93  mov     [r12], rcx
0x14000cd97  add     rsp, 28h
0x14000cd9b  pop     r15
0x14000cd9d  pop     r14
0x14000cd9f  pop     r12
0x14000cda1  pop     rdi
0x14000cda2  pop     rsi
0x14000cda3  pop     rbx
0x14000cda4  retn
```
