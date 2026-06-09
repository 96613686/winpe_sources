# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x18000a198`
- end: `0x18000a281`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180008628`
- `0x180009514`
- `0x1800099bc`
- `0x18000a7b4`
- `0x18000b15c`

## callees

- `0x18000a198`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000a1e7`
- `msvcrt!memcpy_s` at `0x18000a21c`
- `msvcrt!memcpy_s` at `0x18000a247`
- `msvcrt!memcpy_s` at `0x18000a1e7`
- `msvcrt!memcpy_s` at `0x18000a21c`
- `msvcrt!memcpy_s` at `0x18000a247`

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
0x18000a198  mov     rax, rsp
0x18000a19b  mov     [rax+10h], rbx
0x18000a19f  mov     [rax+18h], rbp
0x18000a1a3  push    rsi
0x18000a1a4  push    rdi
0x18000a1a5  push    r12
0x18000a1a7  push    r14
0x18000a1a9  push    r15
0x18000a1ab  sub     rsp, 20h
0x18000a1af  xor     r15d, r15d
0x18000a1b2  mov     rsi, r8
0x18000a1b5  cmp     byte ptr [rcx+2], 1
0x18000a1b9  mov     r12, rdx
0x18000a1bc  mov     r8, [rdx]; Source
0x18000a1bf  mov     rdi, rcx
0x18000a1c2  jnz     short loc_18000A1F7
0x18000a1c4  lea     rbx, [r8+2]
0x18000a1c8  cmp     rbx, rsi
0x18000a1cb  ja      loc_18000A25C
0x18000a1d1  lea     ebp, [r15+2]
0x18000a1d5  mov     [rcx+10h], r8
0x18000a1d9  mov     r9d, ebp; SourceSize
0x18000a1dc  mov     [rax+8], r15w
0x18000a1e1  mov     edx, ebp; DestinationSize
0x18000a1e3  lea     rcx, [rax+8]; Destination
0x18000a1e7  call    cs:__imp_memcpy_s
0x18000a1ed  movzx   eax, [rsp+48h+arg_0]
0x18000a1f2  mov     [rdi+4], eax
0x18000a1f5  jmp     short loc_18000A222
0x18000a1f7  mov     ebp, 2
0x18000a1fc  mov     rbx, r8
0x18000a1ff  cmp     [rcx+2], bpl
0x18000a203  jnz     short loc_18000A222
0x18000a205  lea     rbx, [r8+4]
0x18000a209  cmp     rbx, rsi
0x18000a20c  ja      short loc_18000A25C
0x18000a20e  lea     edx, [rbp+2]; DestinationSize
0x18000a211  mov     [rcx+10h], r8
0x18000a215  mov     r9d, edx; SourceSize
0x18000a218  add     rcx, 4; Destination
0x18000a21c  call    cs:__imp_memcpy_s
0x18000a222  movzx   eax, word ptr [rdi]
0x18000a225  lea     r14, [rdi+8]
0x18000a229  mov     [r14], ax
0x18000a22d  test    ax, ax
0x18000a230  jnz     short loc_18000A250
0x18000a232  lea     r15, [rbx+2]
0x18000a236  cmp     r15, rsi
0x18000a239  ja      short loc_18000A25C
0x18000a23b  mov     r9, rbp; SourceSize
0x18000a23e  mov     r8, rbx; Source
0x18000a241  mov     rdx, rbp; DestinationSize
0x18000a244  mov     rcx, r14; Destination
0x18000a247  call    cs:__imp_memcpy_s
0x18000a24d  mov     rbx, r15
0x18000a250  movzx   ecx, word ptr [r14]
0x18000a254  add     rcx, rbx
0x18000a257  cmp     rcx, rsi
0x18000a25a  jbe     short loc_18000A260
0x18000a25c  xor     al, al
0x18000a25e  jmp     short loc_18000A26A
0x18000a260  mov     [rdi+18h], rbx
0x18000a264  mov     al, 1
0x18000a266  mov     [r12], rcx
0x18000a26a  mov     rbx, [rsp+48h+arg_8]
0x18000a26f  mov     rbp, [rsp+48h+arg_10]
0x18000a274  add     rsp, 20h
0x18000a278  pop     r15
0x18000a27a  pop     r14
0x18000a27c  pop     r12
0x18000a27e  pop     rdi
0x18000a27f  pop     rsi
0x18000a280  retn
```
