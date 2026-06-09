# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x180006948`
- end: `0x180006a2e`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `230`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180004d80`
- `0x180007164`
- `0x1800074e8`

## callees

- `0x180001f8c`
- `0x180006948`

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
0x180006948  mov     rax, rsp
0x18000694b  mov     [rax+10h], rbx
0x18000694f  mov     [rax+18h], rbp
0x180006953  push    rsi
0x180006954  push    rdi
0x180006955  push    r12
0x180006957  push    r14
0x180006959  push    r15
0x18000695b  sub     rsp, 20h
0x18000695f  xor     r15d, r15d
0x180006962  mov     rsi, r8
0x180006965  cmp     byte ptr [rcx+2], 1
0x180006969  mov     r12, rdx
0x18000696c  mov     r8, [rdx]; Source
0x18000696f  mov     rdi, rcx
0x180006972  jnz     short loc_1800069A6
0x180006974  lea     rbx, [r8+2]
0x180006978  cmp     rbx, rsi
0x18000697b  ja      loc_180006A09
0x180006981  lea     ebp, [r15+2]
0x180006985  mov     [rcx+10h], r8
0x180006989  mov     r9d, ebp; SourceSize
0x18000698c  mov     [rax+8], r15w
0x180006991  mov     edx, ebp; DestinationSize
0x180006993  lea     rcx, [rax+8]; Destination
0x180006997  call    memcpy_s
0x18000699c  movzx   eax, [rsp+48h+arg_0]
0x1800069a1  mov     [rdi+4], eax
0x1800069a4  jmp     short loc_1800069D0
0x1800069a6  mov     ebp, 2
0x1800069ab  mov     rbx, r8
0x1800069ae  cmp     [rcx+2], bpl
0x1800069b2  jnz     short loc_1800069D0
0x1800069b4  lea     rbx, [r8+4]
0x1800069b8  cmp     rbx, rsi
0x1800069bb  ja      short loc_180006A09
0x1800069bd  lea     edx, [rbp+2]; DestinationSize
0x1800069c0  mov     [rcx+10h], r8
0x1800069c4  mov     r9d, edx; SourceSize
0x1800069c7  add     rcx, 4; Destination
0x1800069cb  call    memcpy_s
0x1800069d0  movzx   eax, word ptr [rdi]
0x1800069d3  lea     r14, [rdi+8]
0x1800069d7  mov     [r14], ax
0x1800069db  test    ax, ax
0x1800069de  jnz     short loc_1800069FD
0x1800069e0  lea     r15, [rbx+2]
0x1800069e4  cmp     r15, rsi
0x1800069e7  ja      short loc_180006A09
0x1800069e9  mov     r9, rbp; SourceSize
0x1800069ec  mov     r8, rbx; Source
0x1800069ef  mov     rdx, rbp; DestinationSize
0x1800069f2  mov     rcx, r14; Destination
0x1800069f5  call    memcpy_s
0x1800069fa  mov     rbx, r15
0x1800069fd  movzx   ecx, word ptr [r14]
0x180006a01  add     rcx, rbx
0x180006a04  cmp     rcx, rsi
0x180006a07  jbe     short loc_180006A0D
0x180006a09  xor     al, al
0x180006a0b  jmp     short loc_180006A17
0x180006a0d  mov     [rdi+18h], rbx
0x180006a11  mov     al, 1
0x180006a13  mov     [r12], rcx
0x180006a17  mov     rbx, [rsp+48h+arg_8]
0x180006a1c  mov     rbp, [rsp+48h+arg_10]
0x180006a21  add     rsp, 20h
0x180006a25  pop     r15
0x180006a27  pop     r14
0x180006a29  pop     r12
0x180006a2b  pop     rdi
0x180006a2c  pop     rsi
0x180006a2d  retn
```
