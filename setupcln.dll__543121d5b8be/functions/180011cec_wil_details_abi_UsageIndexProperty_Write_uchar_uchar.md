# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x180011cec`
- end: `0x180011dc5`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *this, char **, char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180010654`

## callees

- `0x180011cec`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180011d4c`
- `msvcrt!memcpy_s` at `0x180011d77`
- `msvcrt!memcpy_s` at `0x180011da4`
- `msvcrt!memcpy_s` at `0x180011d4c`
- `msvcrt!memcpy_s` at `0x180011d77`
- `msvcrt!memcpy_s` at `0x180011da4`

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
0x180011cec  push    rbx
0x180011cee  push    rsi
0x180011cef  push    rdi
0x180011cf0  push    r12
0x180011cf2  push    r14
0x180011cf4  push    r15
0x180011cf6  sub     rsp, 28h
0x180011cfa  mov     rsi, rcx
0x180011cfd  mov     rdi, r8
0x180011d00  mov     rcx, [rdx]; Destination
0x180011d03  mov     r12, rdx
0x180011d06  cmp     byte ptr [rsi+2], 1
0x180011d0a  jnz     short loc_180011D2E
0x180011d0c  lea     rbx, [rcx+2]
0x180011d10  cmp     rbx, r8
0x180011d13  ja      short loc_180011D93
0x180011d15  movzx   eax, word ptr [rsi+4]
0x180011d19  lea     r8, [rsp+58h+arg_0]
0x180011d1e  mov     r9d, 2
0x180011d24  mov     [rsp+58h+arg_0], ax
0x180011d29  mov     edx, r9d
0x180011d2c  jmp     short loc_180011D4C
0x180011d2e  cmp     byte ptr [rsi+2], 2
0x180011d32  mov     rbx, rcx
0x180011d35  jnz     short loc_180011D52
0x180011d37  lea     rbx, [rcx+4]
0x180011d3b  cmp     rbx, rdi
0x180011d3e  ja      short loc_180011D93
0x180011d40  mov     edx, 4; DestinationSize
0x180011d45  lea     r8, [rsi+4]; Source
0x180011d49  mov     r9d, edx; SourceSize
0x180011d4c  call    cs:__imp_memcpy_s
0x180011d52  cmp     word ptr [rsi], 0
0x180011d56  jnz     short loc_180011D82
0x180011d58  lea     r15, [rbx+2]
0x180011d5c  cmp     r15, rdi
0x180011d5f  ja      short loc_180011D93
0x180011d61  lea     r14, [rsi+8]
0x180011d65  mov     rdx, rdi
0x180011d68  sub     rdx, rbx; DestinationSize
0x180011d6b  mov     r8, r14; Source
0x180011d6e  mov     r9d, 2; SourceSize
0x180011d74  mov     rcx, rbx; Destination
0x180011d77  call    cs:__imp_memcpy_s
0x180011d7d  mov     rbx, r15
0x180011d80  jmp     short loc_180011D86
0x180011d82  lea     r14, [rsi+8]
0x180011d86  movzx   r9d, word ptr [r14]; SourceSize
0x180011d8a  lea     rax, [r9+rbx]
0x180011d8e  cmp     rax, rdi
0x180011d91  jbe     short loc_180011D97
0x180011d93  xor     al, al
0x180011d95  jmp     short loc_180011DB7
0x180011d97  mov     r8, [rsi+18h]; Source
0x180011d9b  sub     rdi, rbx
0x180011d9e  mov     rdx, rdi; DestinationSize
0x180011da1  mov     rcx, rbx; Destination
0x180011da4  call    cs:__imp_memcpy_s
0x180011daa  movzx   ecx, word ptr [r14]
0x180011dae  mov     al, 1
0x180011db0  add     rcx, rbx
0x180011db3  mov     [r12], rcx
0x180011db7  add     rsp, 28h
0x180011dbb  pop     r15
0x180011dbd  pop     r14
0x180011dbf  pop     r12
0x180011dc1  pop     rdi
0x180011dc2  pop     rsi
0x180011dc3  pop     rbx
0x180011dc4  retn
```
