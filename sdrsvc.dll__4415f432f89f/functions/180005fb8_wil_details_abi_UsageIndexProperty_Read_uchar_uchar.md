# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x180005fb8`
- end: `0x1800060a1`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180004710`
- `0x1800067d4`
- `0x180006b5c`

## callees

- `0x180005fb8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180006007`
- `msvcrt!memcpy_s` at `0x18000603c`
- `msvcrt!memcpy_s` at `0x180006067`
- `msvcrt!memcpy_s` at `0x180006007`
- `msvcrt!memcpy_s` at `0x18000603c`
- `msvcrt!memcpy_s` at `0x180006067`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Read(
        wil::details_abi::UsageIndexProperty *this,
        unsigned __int8 **a2,
        unsigned __int8 *a3)
{
  char *v5; // r8
  char *v7; // rbx
  __int16 v8; // ax
  unsigned __int8 *v9; // rcx
  bool result; // al
  unsigned __int16 v11; // [rsp+50h] [rbp+8h] BYREF

  v5 = (char *)*a2;
  if ( *((_BYTE *)this + 2) == 1 )
  {
    v7 = v5 + 2;
    if ( v5 + 2 > (char *)a3 )
      return 0;
    *((_QWORD *)this + 2) = v5;
    v11 = 0;
    memcpy_s(&v11, 2u, v5, 2u);
    *((_DWORD *)this + 1) = v11;
  }
  else
  {
    v7 = (char *)*a2;
    if ( *((_BYTE *)this + 2) == 2 )
    {
      v7 = v5 + 4;
      if ( v5 + 4 > (char *)a3 )
        return 0;
      *((_QWORD *)this + 2) = v5;
      memcpy_s((char *)this + 4, 4u, v5, 4u);
    }
  }
  v8 = *(_WORD *)this;
  *((_WORD *)this + 4) = *(_WORD *)this;
  if ( v8 )
    goto LABEL_10;
  if ( v7 + 2 > (char *)a3 )
    return 0;
  memcpy_s((char *)this + 8, 2u, v7, 2u);
  v7 += 2;
LABEL_10:
  v9 = (unsigned __int8 *)&v7[*((unsigned __int16 *)this + 4)];
  if ( v9 > a3 )
    return 0;
  *((_QWORD *)this + 3) = v7;
  result = 1;
  *a2 = v9;
  return result;
}

```

## disassembly

```asm
0x180005fb8  mov     rax, rsp
0x180005fbb  mov     [rax+10h], rbx
0x180005fbf  mov     [rax+18h], rbp
0x180005fc3  push    rsi
0x180005fc4  push    rdi
0x180005fc5  push    r12
0x180005fc7  push    r14
0x180005fc9  push    r15
0x180005fcb  sub     rsp, 20h
0x180005fcf  xor     r15d, r15d
0x180005fd2  mov     rsi, r8
0x180005fd5  cmp     byte ptr [rcx+2], 1
0x180005fd9  mov     r12, rdx
0x180005fdc  mov     r8, [rdx]; Source
0x180005fdf  mov     rdi, rcx
0x180005fe2  jnz     short loc_180006017
0x180005fe4  lea     rbx, [r8+2]
0x180005fe8  cmp     rbx, rsi
0x180005feb  ja      loc_18000607C
0x180005ff1  lea     ebp, [r15+2]
0x180005ff5  mov     [rcx+10h], r8
0x180005ff9  mov     r9d, ebp; SourceSize
0x180005ffc  mov     [rax+8], r15w
0x180006001  mov     edx, ebp; DestinationSize
0x180006003  lea     rcx, [rax+8]; Destination
0x180006007  call    cs:__imp_memcpy_s
0x18000600d  movzx   eax, [rsp+48h+arg_0]
0x180006012  mov     [rdi+4], eax
0x180006015  jmp     short loc_180006042
0x180006017  mov     ebp, 2
0x18000601c  mov     rbx, r8
0x18000601f  cmp     [rcx+2], bpl
0x180006023  jnz     short loc_180006042
0x180006025  lea     rbx, [r8+4]
0x180006029  cmp     rbx, rsi
0x18000602c  ja      short loc_18000607C
0x18000602e  lea     edx, [rbp+2]; DestinationSize
0x180006031  mov     [rcx+10h], r8
0x180006035  mov     r9d, edx; SourceSize
0x180006038  add     rcx, 4; Destination
0x18000603c  call    cs:__imp_memcpy_s
0x180006042  movzx   eax, word ptr [rdi]
0x180006045  lea     r14, [rdi+8]
0x180006049  mov     [r14], ax
0x18000604d  test    ax, ax
0x180006050  jnz     short loc_180006070
0x180006052  lea     r15, [rbx+2]
0x180006056  cmp     r15, rsi
0x180006059  ja      short loc_18000607C
0x18000605b  mov     r9, rbp; SourceSize
0x18000605e  mov     r8, rbx; Source
0x180006061  mov     rdx, rbp; DestinationSize
0x180006064  mov     rcx, r14; Destination
0x180006067  call    cs:__imp_memcpy_s
0x18000606d  mov     rbx, r15
0x180006070  movzx   ecx, word ptr [r14]
0x180006074  add     rcx, rbx
0x180006077  cmp     rcx, rsi
0x18000607a  jbe     short loc_180006080
0x18000607c  xor     al, al
0x18000607e  jmp     short loc_18000608A
0x180006080  mov     [rdi+18h], rbx
0x180006084  mov     al, 1
0x180006086  mov     [r12], rcx
0x18000608a  mov     rbx, [rsp+48h+arg_8]
0x18000608f  mov     rbp, [rsp+48h+arg_10]
0x180006094  add     rsp, 20h
0x180006098  pop     r15
0x18000609a  pop     r14
0x18000609c  pop     r12
0x18000609e  pop     rdi
0x18000609f  pop     rsi
0x1800060a0  retn
```
