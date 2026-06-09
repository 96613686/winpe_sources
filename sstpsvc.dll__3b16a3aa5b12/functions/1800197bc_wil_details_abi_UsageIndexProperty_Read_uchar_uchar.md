# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x1800197bc`
- end: `0x1800198a5`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180017e44`
- `0x180018c54`
- `0x1800190e4`
- `0x180019d60`
- `0x18001a70c`

## callees

- `0x1800197bc`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18001980b`
- `msvcrt!memcpy_s` at `0x180019840`
- `msvcrt!memcpy_s` at `0x18001986b`
- `msvcrt!memcpy_s` at `0x18001980b`
- `msvcrt!memcpy_s` at `0x180019840`
- `msvcrt!memcpy_s` at `0x18001986b`

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
0x1800197bc  mov     rax, rsp
0x1800197bf  mov     [rax+10h], rbx
0x1800197c3  mov     [rax+18h], rbp
0x1800197c7  push    rsi
0x1800197c8  push    rdi
0x1800197c9  push    r12
0x1800197cb  push    r14
0x1800197cd  push    r15
0x1800197cf  sub     rsp, 20h
0x1800197d3  xor     r15d, r15d
0x1800197d6  mov     rsi, r8
0x1800197d9  cmp     byte ptr [rcx+2], 1
0x1800197dd  mov     r12, rdx
0x1800197e0  mov     r8, [rdx]; Source
0x1800197e3  mov     rdi, rcx
0x1800197e6  jnz     short loc_18001981B
0x1800197e8  lea     rbx, [r8+2]
0x1800197ec  cmp     rbx, rsi
0x1800197ef  ja      loc_180019880
0x1800197f5  lea     ebp, [r15+2]
0x1800197f9  mov     [rcx+10h], r8
0x1800197fd  mov     r9d, ebp; SourceSize
0x180019800  mov     [rax+8], r15w
0x180019805  mov     edx, ebp; DestinationSize
0x180019807  lea     rcx, [rax+8]; Destination
0x18001980b  call    cs:__imp_memcpy_s
0x180019811  movzx   eax, [rsp+48h+arg_0]
0x180019816  mov     [rdi+4], eax
0x180019819  jmp     short loc_180019846
0x18001981b  mov     ebp, 2
0x180019820  mov     rbx, r8
0x180019823  cmp     [rcx+2], bpl
0x180019827  jnz     short loc_180019846
0x180019829  lea     rbx, [r8+4]
0x18001982d  cmp     rbx, rsi
0x180019830  ja      short loc_180019880
0x180019832  lea     edx, [rbp+2]; DestinationSize
0x180019835  mov     [rcx+10h], r8
0x180019839  mov     r9d, edx; SourceSize
0x18001983c  add     rcx, 4; Destination
0x180019840  call    cs:__imp_memcpy_s
0x180019846  movzx   eax, word ptr [rdi]
0x180019849  lea     r14, [rdi+8]
0x18001984d  mov     [r14], ax
0x180019851  test    ax, ax
0x180019854  jnz     short loc_180019874
0x180019856  lea     r15, [rbx+2]
0x18001985a  cmp     r15, rsi
0x18001985d  ja      short loc_180019880
0x18001985f  mov     r9, rbp; SourceSize
0x180019862  mov     r8, rbx; Source
0x180019865  mov     rdx, rbp; DestinationSize
0x180019868  mov     rcx, r14; Destination
0x18001986b  call    cs:__imp_memcpy_s
0x180019871  mov     rbx, r15
0x180019874  movzx   ecx, word ptr [r14]
0x180019878  add     rcx, rbx
0x18001987b  cmp     rcx, rsi
0x18001987e  jbe     short loc_180019884
0x180019880  xor     al, al
0x180019882  jmp     short loc_18001988E
0x180019884  mov     [rdi+18h], rbx
0x180019888  mov     al, 1
0x18001988a  mov     [r12], rcx
0x18001988e  mov     rbx, [rsp+48h+arg_8]
0x180019893  mov     rbp, [rsp+48h+arg_10]
0x180019898  add     rsp, 20h
0x18001989c  pop     r15
0x18001989e  pop     r14
0x1800198a0  pop     r12
0x1800198a2  pop     rdi
0x1800198a3  pop     rsi
0x1800198a4  retn
```
