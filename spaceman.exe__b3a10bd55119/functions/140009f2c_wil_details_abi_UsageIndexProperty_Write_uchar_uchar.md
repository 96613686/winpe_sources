# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x140009f2c`
- end: `0x14000a005`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *this, char **, char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140007fb0`

## callees

- `0x140009f2c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140009f8c`
- `msvcrt!memcpy_s` at `0x140009fb7`
- `msvcrt!memcpy_s` at `0x140009fe4`
- `msvcrt!memcpy_s` at `0x140009f8c`
- `msvcrt!memcpy_s` at `0x140009fb7`
- `msvcrt!memcpy_s` at `0x140009fe4`

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
0x140009f2c  push    rbx
0x140009f2e  push    rsi
0x140009f2f  push    rdi
0x140009f30  push    r12
0x140009f32  push    r14
0x140009f34  push    r15
0x140009f36  sub     rsp, 28h
0x140009f3a  mov     rsi, rcx
0x140009f3d  mov     rdi, r8
0x140009f40  mov     rcx, [rdx]; Destination
0x140009f43  mov     r12, rdx
0x140009f46  cmp     byte ptr [rsi+2], 1
0x140009f4a  jnz     short loc_140009F6E
0x140009f4c  lea     rbx, [rcx+2]
0x140009f50  cmp     rbx, r8
0x140009f53  ja      short loc_140009FD3
0x140009f55  movzx   eax, word ptr [rsi+4]
0x140009f59  lea     r8, [rsp+58h+arg_0]
0x140009f5e  mov     r9d, 2
0x140009f64  mov     [rsp+58h+arg_0], ax
0x140009f69  mov     edx, r9d
0x140009f6c  jmp     short loc_140009F8C
0x140009f6e  cmp     byte ptr [rsi+2], 2
0x140009f72  mov     rbx, rcx
0x140009f75  jnz     short loc_140009F92
0x140009f77  lea     rbx, [rcx+4]
0x140009f7b  cmp     rbx, rdi
0x140009f7e  ja      short loc_140009FD3
0x140009f80  mov     edx, 4; DestinationSize
0x140009f85  lea     r8, [rsi+4]; Source
0x140009f89  mov     r9d, edx; SourceSize
0x140009f8c  call    cs:__imp_memcpy_s
0x140009f92  cmp     word ptr [rsi], 0
0x140009f96  jnz     short loc_140009FC2
0x140009f98  lea     r15, [rbx+2]
0x140009f9c  cmp     r15, rdi
0x140009f9f  ja      short loc_140009FD3
0x140009fa1  lea     r14, [rsi+8]
0x140009fa5  mov     rdx, rdi
0x140009fa8  sub     rdx, rbx; DestinationSize
0x140009fab  mov     r8, r14; Source
0x140009fae  mov     r9d, 2; SourceSize
0x140009fb4  mov     rcx, rbx; Destination
0x140009fb7  call    cs:__imp_memcpy_s
0x140009fbd  mov     rbx, r15
0x140009fc0  jmp     short loc_140009FC6
0x140009fc2  lea     r14, [rsi+8]
0x140009fc6  movzx   r9d, word ptr [r14]; SourceSize
0x140009fca  lea     rax, [r9+rbx]
0x140009fce  cmp     rax, rdi
0x140009fd1  jbe     short loc_140009FD7
0x140009fd3  xor     al, al
0x140009fd5  jmp     short loc_140009FF7
0x140009fd7  mov     r8, [rsi+18h]; Source
0x140009fdb  sub     rdi, rbx
0x140009fde  mov     rdx, rdi; DestinationSize
0x140009fe1  mov     rcx, rbx; Destination
0x140009fe4  call    cs:__imp_memcpy_s
0x140009fea  movzx   ecx, word ptr [r14]
0x140009fee  mov     al, 1
0x140009ff0  add     rcx, rbx
0x140009ff3  mov     [r12], rcx
0x140009ff7  add     rsp, 28h
0x140009ffb  pop     r15
0x140009ffd  pop     r14
0x140009fff  pop     r12
0x14000a001  pop     rdi
0x14000a002  pop     rsi
0x14000a003  pop     rbx
0x14000a004  retn
```
