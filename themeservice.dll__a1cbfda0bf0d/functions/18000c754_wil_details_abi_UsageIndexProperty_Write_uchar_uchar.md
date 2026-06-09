# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x18000c754`
- end: `0x18000c82d`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *this, char **, char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180007188`

## callees

- `0x18000c754`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000c7b4`
- `msvcrt!memcpy_s` at `0x18000c7df`
- `msvcrt!memcpy_s` at `0x18000c80c`
- `msvcrt!memcpy_s` at `0x18000c7b4`
- `msvcrt!memcpy_s` at `0x18000c7df`
- `msvcrt!memcpy_s` at `0x18000c80c`

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
0x18000c754  push    rbx
0x18000c756  push    rsi
0x18000c757  push    rdi
0x18000c758  push    r12
0x18000c75a  push    r14
0x18000c75c  push    r15
0x18000c75e  sub     rsp, 28h
0x18000c762  mov     rsi, rcx
0x18000c765  mov     rdi, r8
0x18000c768  mov     rcx, [rdx]; Destination
0x18000c76b  mov     r12, rdx
0x18000c76e  cmp     byte ptr [rsi+2], 1
0x18000c772  jnz     short loc_18000C796
0x18000c774  lea     rbx, [rcx+2]
0x18000c778  cmp     rbx, r8
0x18000c77b  ja      short loc_18000C7FB
0x18000c77d  movzx   eax, word ptr [rsi+4]
0x18000c781  lea     r8, [rsp+58h+arg_0]
0x18000c786  mov     r9d, 2
0x18000c78c  mov     [rsp+58h+arg_0], ax
0x18000c791  mov     edx, r9d
0x18000c794  jmp     short loc_18000C7B4
0x18000c796  cmp     byte ptr [rsi+2], 2
0x18000c79a  mov     rbx, rcx
0x18000c79d  jnz     short loc_18000C7BA
0x18000c79f  lea     rbx, [rcx+4]
0x18000c7a3  cmp     rbx, rdi
0x18000c7a6  ja      short loc_18000C7FB
0x18000c7a8  mov     edx, 4; DestinationSize
0x18000c7ad  lea     r8, [rsi+4]; Source
0x18000c7b1  mov     r9d, edx; SourceSize
0x18000c7b4  call    cs:__imp_memcpy_s
0x18000c7ba  cmp     word ptr [rsi], 0
0x18000c7be  jnz     short loc_18000C7EA
0x18000c7c0  lea     r15, [rbx+2]
0x18000c7c4  cmp     r15, rdi
0x18000c7c7  ja      short loc_18000C7FB
0x18000c7c9  lea     r14, [rsi+8]
0x18000c7cd  mov     rdx, rdi
0x18000c7d0  sub     rdx, rbx; DestinationSize
0x18000c7d3  mov     r8, r14; Source
0x18000c7d6  mov     r9d, 2; SourceSize
0x18000c7dc  mov     rcx, rbx; Destination
0x18000c7df  call    cs:__imp_memcpy_s
0x18000c7e5  mov     rbx, r15
0x18000c7e8  jmp     short loc_18000C7EE
0x18000c7ea  lea     r14, [rsi+8]
0x18000c7ee  movzx   r9d, word ptr [r14]; SourceSize
0x18000c7f2  lea     rax, [r9+rbx]
0x18000c7f6  cmp     rax, rdi
0x18000c7f9  jbe     short loc_18000C7FF
0x18000c7fb  xor     al, al
0x18000c7fd  jmp     short loc_18000C81F
0x18000c7ff  mov     r8, [rsi+18h]; Source
0x18000c803  sub     rdi, rbx
0x18000c806  mov     rdx, rdi; DestinationSize
0x18000c809  mov     rcx, rbx; Destination
0x18000c80c  call    cs:__imp_memcpy_s
0x18000c812  movzx   ecx, word ptr [r14]
0x18000c816  mov     al, 1
0x18000c818  add     rcx, rbx
0x18000c81b  mov     [r12], rcx
0x18000c81f  add     rsp, 28h
0x18000c823  pop     r15
0x18000c825  pop     r14
0x18000c827  pop     r12
0x18000c829  pop     rdi
0x18000c82a  pop     rsi
0x18000c82b  pop     rbx
0x18000c82c  retn
```
