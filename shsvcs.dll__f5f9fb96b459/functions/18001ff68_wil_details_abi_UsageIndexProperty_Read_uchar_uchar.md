# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x18001ff68`
- end: `0x180020051`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18001e268`
- `0x18001f230`
- `0x18001f670`
- `0x180020584`
- `0x180021234`

## callees

- `0x18001ff68`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18001ffb7`
- `msvcrt!memcpy_s` at `0x18001ffec`
- `msvcrt!memcpy_s` at `0x180020017`
- `msvcrt!memcpy_s` at `0x18001ffb7`
- `msvcrt!memcpy_s` at `0x18001ffec`
- `msvcrt!memcpy_s` at `0x180020017`

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
0x18001ff68  mov     rax, rsp
0x18001ff6b  mov     [rax+10h], rbx
0x18001ff6f  mov     [rax+18h], rbp
0x18001ff73  push    rsi
0x18001ff74  push    rdi
0x18001ff75  push    r12
0x18001ff77  push    r14
0x18001ff79  push    r15
0x18001ff7b  sub     rsp, 20h
0x18001ff7f  xor     r15d, r15d
0x18001ff82  mov     rsi, r8
0x18001ff85  cmp     byte ptr [rcx+2], 1
0x18001ff89  mov     r12, rdx
0x18001ff8c  mov     r8, [rdx]; Source
0x18001ff8f  mov     rdi, rcx
0x18001ff92  jnz     short loc_18001FFC7
0x18001ff94  lea     rbx, [r8+2]
0x18001ff98  cmp     rbx, rsi
0x18001ff9b  ja      loc_18002002C
0x18001ffa1  lea     ebp, [r15+2]
0x18001ffa5  mov     [rcx+10h], r8
0x18001ffa9  mov     r9d, ebp; SourceSize
0x18001ffac  mov     [rax+8], r15w
0x18001ffb1  mov     edx, ebp; DestinationSize
0x18001ffb3  lea     rcx, [rax+8]; Destination
0x18001ffb7  call    cs:__imp_memcpy_s
0x18001ffbd  movzx   eax, [rsp+48h+arg_0]
0x18001ffc2  mov     [rdi+4], eax
0x18001ffc5  jmp     short loc_18001FFF2
0x18001ffc7  mov     ebp, 2
0x18001ffcc  mov     rbx, r8
0x18001ffcf  cmp     [rcx+2], bpl
0x18001ffd3  jnz     short loc_18001FFF2
0x18001ffd5  lea     rbx, [r8+4]
0x18001ffd9  cmp     rbx, rsi
0x18001ffdc  ja      short loc_18002002C
0x18001ffde  lea     edx, [rbp+2]; DestinationSize
0x18001ffe1  mov     [rcx+10h], r8
0x18001ffe5  mov     r9d, edx; SourceSize
0x18001ffe8  add     rcx, 4; Destination
0x18001ffec  call    cs:__imp_memcpy_s
0x18001fff2  movzx   eax, word ptr [rdi]
0x18001fff5  lea     r14, [rdi+8]
0x18001fff9  mov     [r14], ax
0x18001fffd  test    ax, ax
0x180020000  jnz     short loc_180020020
0x180020002  lea     r15, [rbx+2]
0x180020006  cmp     r15, rsi
0x180020009  ja      short loc_18002002C
0x18002000b  mov     r9, rbp; SourceSize
0x18002000e  mov     r8, rbx; Source
0x180020011  mov     rdx, rbp; DestinationSize
0x180020014  mov     rcx, r14; Destination
0x180020017  call    cs:__imp_memcpy_s
0x18002001d  mov     rbx, r15
0x180020020  movzx   ecx, word ptr [r14]
0x180020024  add     rcx, rbx
0x180020027  cmp     rcx, rsi
0x18002002a  jbe     short loc_180020030
0x18002002c  xor     al, al
0x18002002e  jmp     short loc_18002003A
0x180020030  mov     [rdi+18h], rbx
0x180020034  mov     al, 1
0x180020036  mov     [r12], rcx
0x18002003a  mov     rbx, [rsp+48h+arg_8]
0x18002003f  mov     rbp, [rsp+48h+arg_10]
0x180020044  add     rsp, 20h
0x180020048  pop     r15
0x18002004a  pop     r14
0x18002004c  pop     r12
0x18002004e  pop     rdi
0x18002004f  pop     rsi
0x180020050  retn
```
