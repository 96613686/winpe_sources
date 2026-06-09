# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x180028724`
- end: `0x180028826`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `258`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x1800277a4`
- `0x180027a7c`
- `0x180027c64`
- `0x180028cf4`
- `0x180029878`

## callees

- `0x1800050f0`
- `0x180005c4c`
- `0x180028724`

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
  unsigned __int16 v11; // [rsp+20h] [rbp-38h] BYREF

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
0x180028724  mov     r11, rsp
0x180028727  mov     [r11+18h], rbx
0x18002872b  mov     [r11+20h], rbp
0x18002872f  push    rsi
0x180028730  push    rdi
0x180028731  push    r12
0x180028733  push    r14
0x180028735  push    r15
0x180028737  sub     rsp, 30h
0x18002873b  mov     rax, cs:__security_cookie
0x180028742  xor     rax, rsp
0x180028745  mov     [rsp+58h+var_30], rax
0x18002874a  xor     r15d, r15d
0x18002874d  mov     rsi, r8
0x180028750  cmp     byte ptr [rcx+2], 1
0x180028754  mov     r12, rdx
0x180028757  mov     r8, [rdx]; Source
0x18002875a  mov     rdi, rcx
0x18002875d  jnz     short loc_180028791
0x18002875f  lea     rbx, [r8+2]
0x180028763  cmp     rbx, rsi
0x180028766  ja      loc_1800287F4
0x18002876c  lea     ebp, [r15+2]
0x180028770  mov     [rcx+10h], r8
0x180028774  mov     r9d, ebp; SourceSize
0x180028777  mov     [r11-38h], r15w
0x18002877c  mov     edx, ebp; DestinationSize
0x18002877e  lea     rcx, [r11-38h]; Destination
0x180028782  call    memcpy_s
0x180028787  movzx   eax, [rsp+58h+var_38]
0x18002878c  mov     [rdi+4], eax
0x18002878f  jmp     short loc_1800287BB
0x180028791  mov     ebp, 2
0x180028796  mov     rbx, r8
0x180028799  cmp     [rcx+2], bpl
0x18002879d  jnz     short loc_1800287BB
0x18002879f  lea     rbx, [r8+4]
0x1800287a3  cmp     rbx, rsi
0x1800287a6  ja      short loc_1800287F4
0x1800287a8  lea     edx, [rbp+2]; DestinationSize
0x1800287ab  mov     [rcx+10h], r8
0x1800287af  mov     r9d, edx; SourceSize
0x1800287b2  add     rcx, 4; Destination
0x1800287b6  call    memcpy_s
0x1800287bb  movzx   eax, word ptr [rdi]
0x1800287be  lea     r14, [rdi+8]
0x1800287c2  mov     [r14], ax
0x1800287c6  test    ax, ax
0x1800287c9  jnz     short loc_1800287E8
0x1800287cb  lea     r15, [rbx+2]
0x1800287cf  cmp     r15, rsi
0x1800287d2  ja      short loc_1800287F4
0x1800287d4  mov     r9, rbp; SourceSize
0x1800287d7  mov     r8, rbx; Source
0x1800287da  mov     rdx, rbp; DestinationSize
0x1800287dd  mov     rcx, r14; Destination
0x1800287e0  call    memcpy_s
0x1800287e5  mov     rbx, r15
0x1800287e8  movzx   ecx, word ptr [r14]
0x1800287ec  add     rcx, rbx
0x1800287ef  cmp     rcx, rsi
0x1800287f2  jbe     short loc_1800287F8
0x1800287f4  xor     al, al
0x1800287f6  jmp     short loc_180028802
0x1800287f8  mov     [rdi+18h], rbx
0x1800287fc  mov     al, 1
0x1800287fe  mov     [r12], rcx
0x180028802  mov     rcx, [rsp+58h+var_30]
0x180028807  xor     rcx, rsp; StackCookie
0x18002880a  call    __security_check_cookie
0x18002880f  mov     rbx, [rsp+58h+arg_10]
0x180028814  mov     rbp, [rsp+58h+arg_18]
0x180028819  add     rsp, 30h
0x18002881d  pop     r15
0x18002881f  pop     r14
0x180028821  pop     r12
0x180028823  pop     rdi
0x180028824  pop     rsi
0x180028825  retn
```
