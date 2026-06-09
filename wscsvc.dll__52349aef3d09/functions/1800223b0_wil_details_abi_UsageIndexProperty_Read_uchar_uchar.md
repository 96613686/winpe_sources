# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x1800223b0`
- end: `0x180022499`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1800222c8`
- `0x1800279dc`
- `0x180028c30`
- `0x18002c7ec`
- `0x18002e160`

## callees

- `0x1800223b0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800223ff`
- `msvcrt!memcpy_s` at `0x180022434`
- `msvcrt!memcpy_s` at `0x18002245f`
- `msvcrt!memcpy_s` at `0x1800223ff`
- `msvcrt!memcpy_s` at `0x180022434`
- `msvcrt!memcpy_s` at `0x18002245f`

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
0x1800223b0  mov     rax, rsp
0x1800223b3  mov     [rax+10h], rbx
0x1800223b7  mov     [rax+18h], rbp
0x1800223bb  push    rsi
0x1800223bc  push    rdi
0x1800223bd  push    r12
0x1800223bf  push    r14
0x1800223c1  push    r15
0x1800223c3  sub     rsp, 20h
0x1800223c7  xor     r15d, r15d
0x1800223ca  mov     rsi, r8
0x1800223cd  cmp     byte ptr [rcx+2], 1
0x1800223d1  mov     r12, rdx
0x1800223d4  mov     r8, [rdx]; Source
0x1800223d7  mov     rdi, rcx
0x1800223da  jnz     short loc_18002240F
0x1800223dc  lea     rbx, [r8+2]
0x1800223e0  cmp     rbx, rsi
0x1800223e3  ja      loc_180022474
0x1800223e9  lea     ebp, [r15+2]
0x1800223ed  mov     [rcx+10h], r8
0x1800223f1  mov     r9d, ebp; SourceSize
0x1800223f4  mov     [rax+8], r15w
0x1800223f9  mov     edx, ebp; DestinationSize
0x1800223fb  lea     rcx, [rax+8]; Destination
0x1800223ff  call    cs:__imp_memcpy_s
0x180022405  movzx   eax, [rsp+48h+arg_0]
0x18002240a  mov     [rdi+4], eax
0x18002240d  jmp     short loc_18002243A
0x18002240f  mov     ebp, 2
0x180022414  mov     rbx, r8
0x180022417  cmp     [rcx+2], bpl
0x18002241b  jnz     short loc_18002243A
0x18002241d  lea     rbx, [r8+4]
0x180022421  cmp     rbx, rsi
0x180022424  ja      short loc_180022474
0x180022426  lea     edx, [rbp+2]; DestinationSize
0x180022429  mov     [rcx+10h], r8
0x18002242d  mov     r9d, edx; SourceSize
0x180022430  add     rcx, 4; Destination
0x180022434  call    cs:__imp_memcpy_s
0x18002243a  movzx   eax, word ptr [rdi]
0x18002243d  lea     r14, [rdi+8]
0x180022441  mov     [r14], ax
0x180022445  test    ax, ax
0x180022448  jnz     short loc_180022468
0x18002244a  lea     r15, [rbx+2]
0x18002244e  cmp     r15, rsi
0x180022451  ja      short loc_180022474
0x180022453  mov     r9, rbp; SourceSize
0x180022456  mov     r8, rbx; Source
0x180022459  mov     rdx, rbp; DestinationSize
0x18002245c  mov     rcx, r14; Destination
0x18002245f  call    cs:__imp_memcpy_s
0x180022465  mov     rbx, r15
0x180022468  movzx   ecx, word ptr [r14]
0x18002246c  add     rcx, rbx
0x18002246f  cmp     rcx, rsi
0x180022472  jbe     short loc_180022478
0x180022474  xor     al, al
0x180022476  jmp     short loc_180022482
0x180022478  mov     [rdi+18h], rbx
0x18002247c  mov     al, 1
0x18002247e  mov     [r12], rcx
0x180022482  mov     rbx, [rsp+48h+arg_8]
0x180022487  mov     rbp, [rsp+48h+arg_10]
0x18002248c  add     rsp, 20h
0x180022490  pop     r15
0x180022492  pop     r14
0x180022494  pop     r12
0x180022496  pop     rdi
0x180022497  pop     rsi
0x180022498  retn
```
