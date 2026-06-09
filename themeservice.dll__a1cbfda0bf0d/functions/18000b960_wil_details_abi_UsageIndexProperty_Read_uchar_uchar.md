# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x18000b960`
- end: `0x18000ba49`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180007188`
- `0x18000b200`
- `0x18000b4d0`
- `0x18000b608`
- `0x18000c0b4`

## callees

- `0x18000b960`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000b9af`
- `msvcrt!memcpy_s` at `0x18000b9e4`
- `msvcrt!memcpy_s` at `0x18000ba0f`
- `msvcrt!memcpy_s` at `0x18000b9af`
- `msvcrt!memcpy_s` at `0x18000b9e4`
- `msvcrt!memcpy_s` at `0x18000ba0f`

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
0x18000b960  mov     rax, rsp
0x18000b963  mov     [rax+10h], rbx
0x18000b967  mov     [rax+18h], rbp
0x18000b96b  push    rsi
0x18000b96c  push    rdi
0x18000b96d  push    r12
0x18000b96f  push    r14
0x18000b971  push    r15
0x18000b973  sub     rsp, 20h
0x18000b977  xor     r15d, r15d
0x18000b97a  mov     rsi, r8
0x18000b97d  cmp     byte ptr [rcx+2], 1
0x18000b981  mov     r12, rdx
0x18000b984  mov     r8, [rdx]; Source
0x18000b987  mov     rdi, rcx
0x18000b98a  jnz     short loc_18000B9BF
0x18000b98c  lea     rbx, [r8+2]
0x18000b990  cmp     rbx, rsi
0x18000b993  ja      loc_18000BA24
0x18000b999  lea     ebp, [r15+2]
0x18000b99d  mov     [rcx+10h], r8
0x18000b9a1  mov     r9d, ebp; SourceSize
0x18000b9a4  mov     [rax+8], r15w
0x18000b9a9  mov     edx, ebp; DestinationSize
0x18000b9ab  lea     rcx, [rax+8]; Destination
0x18000b9af  call    cs:__imp_memcpy_s
0x18000b9b5  movzx   eax, [rsp+48h+arg_0]
0x18000b9ba  mov     [rdi+4], eax
0x18000b9bd  jmp     short loc_18000B9EA
0x18000b9bf  mov     ebp, 2
0x18000b9c4  mov     rbx, r8
0x18000b9c7  cmp     [rcx+2], bpl
0x18000b9cb  jnz     short loc_18000B9EA
0x18000b9cd  lea     rbx, [r8+4]
0x18000b9d1  cmp     rbx, rsi
0x18000b9d4  ja      short loc_18000BA24
0x18000b9d6  lea     edx, [rbp+2]; DestinationSize
0x18000b9d9  mov     [rcx+10h], r8
0x18000b9dd  mov     r9d, edx; SourceSize
0x18000b9e0  add     rcx, 4; Destination
0x18000b9e4  call    cs:__imp_memcpy_s
0x18000b9ea  movzx   eax, word ptr [rdi]
0x18000b9ed  lea     r14, [rdi+8]
0x18000b9f1  mov     [r14], ax
0x18000b9f5  test    ax, ax
0x18000b9f8  jnz     short loc_18000BA18
0x18000b9fa  lea     r15, [rbx+2]
0x18000b9fe  cmp     r15, rsi
0x18000ba01  ja      short loc_18000BA24
0x18000ba03  mov     r9, rbp; SourceSize
0x18000ba06  mov     r8, rbx; Source
0x18000ba09  mov     rdx, rbp; DestinationSize
0x18000ba0c  mov     rcx, r14; Destination
0x18000ba0f  call    cs:__imp_memcpy_s
0x18000ba15  mov     rbx, r15
0x18000ba18  movzx   ecx, word ptr [r14]
0x18000ba1c  add     rcx, rbx
0x18000ba1f  cmp     rcx, rsi
0x18000ba22  jbe     short loc_18000BA28
0x18000ba24  xor     al, al
0x18000ba26  jmp     short loc_18000BA32
0x18000ba28  mov     [rdi+18h], rbx
0x18000ba2c  mov     al, 1
0x18000ba2e  mov     [r12], rcx
0x18000ba32  mov     rbx, [rsp+48h+arg_8]
0x18000ba37  mov     rbp, [rsp+48h+arg_10]
0x18000ba3c  add     rsp, 20h
0x18000ba40  pop     r15
0x18000ba42  pop     r14
0x18000ba44  pop     r12
0x18000ba46  pop     rdi
0x18000ba47  pop     rsi
0x18000ba48  retn
```
