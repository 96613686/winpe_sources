# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x18000bbbc`
- end: `0x18000bc95`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *this, char **, char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a7b4`

## callees

- `0x18000bbbc`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000bc1c`
- `msvcrt!memcpy_s` at `0x18000bc47`
- `msvcrt!memcpy_s` at `0x18000bc74`
- `msvcrt!memcpy_s` at `0x18000bc1c`
- `msvcrt!memcpy_s` at `0x18000bc47`
- `msvcrt!memcpy_s` at `0x18000bc74`

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
0x18000bbbc  push    rbx
0x18000bbbe  push    rsi
0x18000bbbf  push    rdi
0x18000bbc0  push    r12
0x18000bbc2  push    r14
0x18000bbc4  push    r15
0x18000bbc6  sub     rsp, 28h
0x18000bbca  mov     rsi, rcx
0x18000bbcd  mov     rdi, r8
0x18000bbd0  mov     rcx, [rdx]; Destination
0x18000bbd3  mov     r12, rdx
0x18000bbd6  cmp     byte ptr [rsi+2], 1
0x18000bbda  jnz     short loc_18000BBFE
0x18000bbdc  lea     rbx, [rcx+2]
0x18000bbe0  cmp     rbx, r8
0x18000bbe3  ja      short loc_18000BC63
0x18000bbe5  movzx   eax, word ptr [rsi+4]
0x18000bbe9  lea     r8, [rsp+58h+arg_0]
0x18000bbee  mov     r9d, 2
0x18000bbf4  mov     [rsp+58h+arg_0], ax
0x18000bbf9  mov     edx, r9d
0x18000bbfc  jmp     short loc_18000BC1C
0x18000bbfe  cmp     byte ptr [rsi+2], 2
0x18000bc02  mov     rbx, rcx
0x18000bc05  jnz     short loc_18000BC22
0x18000bc07  lea     rbx, [rcx+4]
0x18000bc0b  cmp     rbx, rdi
0x18000bc0e  ja      short loc_18000BC63
0x18000bc10  mov     edx, 4; DestinationSize
0x18000bc15  lea     r8, [rsi+4]; Source
0x18000bc19  mov     r9d, edx; SourceSize
0x18000bc1c  call    cs:__imp_memcpy_s
0x18000bc22  cmp     word ptr [rsi], 0
0x18000bc26  jnz     short loc_18000BC52
0x18000bc28  lea     r15, [rbx+2]
0x18000bc2c  cmp     r15, rdi
0x18000bc2f  ja      short loc_18000BC63
0x18000bc31  lea     r14, [rsi+8]
0x18000bc35  mov     rdx, rdi
0x18000bc38  sub     rdx, rbx; DestinationSize
0x18000bc3b  mov     r8, r14; Source
0x18000bc3e  mov     r9d, 2; SourceSize
0x18000bc44  mov     rcx, rbx; Destination
0x18000bc47  call    cs:__imp_memcpy_s
0x18000bc4d  mov     rbx, r15
0x18000bc50  jmp     short loc_18000BC56
0x18000bc52  lea     r14, [rsi+8]
0x18000bc56  movzx   r9d, word ptr [r14]; SourceSize
0x18000bc5a  lea     rax, [r9+rbx]
0x18000bc5e  cmp     rax, rdi
0x18000bc61  jbe     short loc_18000BC67
0x18000bc63  xor     al, al
0x18000bc65  jmp     short loc_18000BC87
0x18000bc67  mov     r8, [rsi+18h]; Source
0x18000bc6b  sub     rdi, rbx
0x18000bc6e  mov     rdx, rdi; DestinationSize
0x18000bc71  mov     rcx, rbx; Destination
0x18000bc74  call    cs:__imp_memcpy_s
0x18000bc7a  movzx   ecx, word ptr [r14]
0x18000bc7e  mov     al, 1
0x18000bc80  add     rcx, rbx
0x18000bc83  mov     [r12], rcx
0x18000bc87  add     rsp, 28h
0x18000bc8b  pop     r15
0x18000bc8d  pop     r14
0x18000bc8f  pop     r12
0x18000bc91  pop     rdi
0x18000bc92  pop     rsi
0x18000bc93  pop     rbx
0x18000bc94  retn
```
