# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x18001ac80`
- end: `0x18001ad7c`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `252`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180019218`
- `0x18001a0b4`
- `0x18001a560`
- `0x18001b25c`
- `0x18001bc40`

## callees

- `0x18001ac80`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18001accf`
- `msvcrt!memcpy_s` at `0x18001ad0a`
- `msvcrt!memcpy_s` at `0x18001ad3b`
- `msvcrt!memcpy_s` at `0x18001accf`
- `msvcrt!memcpy_s` at `0x18001ad0a`
- `msvcrt!memcpy_s` at `0x18001ad3b`

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
0x18001ac80  mov     rax, rsp
0x18001ac83  mov     [rax+10h], rbx
0x18001ac87  mov     [rax+18h], rbp
0x18001ac8b  push    rsi
0x18001ac8c  push    rdi
0x18001ac8d  push    r12
0x18001ac8f  push    r14
0x18001ac91  push    r15
0x18001ac93  sub     rsp, 20h
0x18001ac97  xor     r15d, r15d
0x18001ac9a  mov     rsi, r8
0x18001ac9d  cmp     byte ptr [rcx+2], 1
0x18001aca1  mov     r12, rdx
0x18001aca4  mov     r8, [rdx]; Source
0x18001aca7  mov     rdi, rcx
0x18001acaa  jnz     short loc_18001ACE5
0x18001acac  lea     rbx, [r8+2]
0x18001acb0  cmp     rbx, rsi
0x18001acb3  ja      loc_18001AD56
0x18001acb9  lea     ebp, [r15+2]
0x18001acbd  mov     [rcx+10h], r8
0x18001acc1  mov     r9d, ebp; SourceSize
0x18001acc4  mov     [rax+8], r15w
0x18001acc9  mov     edx, ebp; DestinationSize
0x18001accb  lea     rcx, [rax+8]; Destination
0x18001accf  call    cs:__imp_memcpy_s
0x18001acd6  nop     dword ptr [rax+rax+00h]
0x18001acdb  movzx   eax, [rsp+48h+arg_0]
0x18001ace0  mov     [rdi+4], eax
0x18001ace3  jmp     short loc_18001AD16
0x18001ace5  mov     ebp, 2
0x18001acea  mov     rbx, r8
0x18001aced  cmp     [rcx+2], bpl
0x18001acf1  jnz     short loc_18001AD16
0x18001acf3  lea     rbx, [r8+4]
0x18001acf7  cmp     rbx, rsi
0x18001acfa  ja      short loc_18001AD56
0x18001acfc  lea     edx, [rbp+2]; DestinationSize
0x18001acff  mov     [rcx+10h], r8
0x18001ad03  mov     r9d, edx; SourceSize
0x18001ad06  add     rcx, 4; Destination
0x18001ad0a  call    cs:__imp_memcpy_s
0x18001ad11  nop     dword ptr [rax+rax+00h]
0x18001ad16  movzx   eax, word ptr [rdi]
0x18001ad19  lea     r14, [rdi+8]
0x18001ad1d  mov     [r14], ax
0x18001ad21  test    ax, ax
0x18001ad24  jnz     short loc_18001AD4A
0x18001ad26  lea     r15, [rbx+2]
0x18001ad2a  cmp     r15, rsi
0x18001ad2d  ja      short loc_18001AD56
0x18001ad2f  mov     r9, rbp; SourceSize
0x18001ad32  mov     r8, rbx; Source
0x18001ad35  mov     rdx, rbp; DestinationSize
0x18001ad38  mov     rcx, r14; Destination
0x18001ad3b  call    cs:__imp_memcpy_s
0x18001ad42  nop     dword ptr [rax+rax+00h]
0x18001ad47  mov     rbx, r15
0x18001ad4a  movzx   ecx, word ptr [r14]
0x18001ad4e  add     rcx, rbx
0x18001ad51  cmp     rcx, rsi
0x18001ad54  jbe     short loc_18001AD5A
0x18001ad56  xor     al, al
0x18001ad58  jmp     short loc_18001AD64
0x18001ad5a  mov     [rdi+18h], rbx
0x18001ad5e  mov     al, 1
0x18001ad60  mov     [r12], rcx
0x18001ad64  mov     rbx, [rsp+48h+arg_8]
0x18001ad69  mov     rbp, [rsp+48h+arg_10]
0x18001ad6e  add     rsp, 20h
0x18001ad72  pop     r15
0x18001ad74  pop     r14
0x18001ad76  pop     r12
0x18001ad78  pop     rdi
0x18001ad79  pop     rsi
0x18001ad7a  retn
```
