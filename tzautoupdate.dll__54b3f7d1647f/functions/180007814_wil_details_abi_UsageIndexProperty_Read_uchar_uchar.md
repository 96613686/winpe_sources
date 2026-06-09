# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x180007814`
- end: `0x1800078fd`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18000556c`
- `0x180006950`
- `0x180006e28`
- `0x180007e38`
- `0x180008eb4`

## callees

- `0x180007814`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180007863`
- `msvcrt!memcpy_s` at `0x180007898`
- `msvcrt!memcpy_s` at `0x1800078c3`
- `msvcrt!memcpy_s` at `0x180007863`
- `msvcrt!memcpy_s` at `0x180007898`
- `msvcrt!memcpy_s` at `0x1800078c3`

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
0x180007814  mov     rax, rsp
0x180007817  mov     [rax+10h], rbx
0x18000781b  mov     [rax+18h], rbp
0x18000781f  push    rsi
0x180007820  push    rdi
0x180007821  push    r12
0x180007823  push    r14
0x180007825  push    r15
0x180007827  sub     rsp, 20h
0x18000782b  xor     r15d, r15d
0x18000782e  mov     rsi, r8
0x180007831  cmp     byte ptr [rcx+2], 1
0x180007835  mov     r12, rdx
0x180007838  mov     r8, [rdx]; Source
0x18000783b  mov     rdi, rcx
0x18000783e  jnz     short loc_180007873
0x180007840  lea     rbx, [r8+2]
0x180007844  cmp     rbx, rsi
0x180007847  ja      loc_1800078D8
0x18000784d  lea     ebp, [r15+2]
0x180007851  mov     [rcx+10h], r8
0x180007855  mov     r9d, ebp; SourceSize
0x180007858  mov     [rax+8], r15w
0x18000785d  mov     edx, ebp; DestinationSize
0x18000785f  lea     rcx, [rax+8]; Destination
0x180007863  call    cs:__imp_memcpy_s
0x180007869  movzx   eax, [rsp+48h+arg_0]
0x18000786e  mov     [rdi+4], eax
0x180007871  jmp     short loc_18000789E
0x180007873  mov     ebp, 2
0x180007878  mov     rbx, r8
0x18000787b  cmp     [rcx+2], bpl
0x18000787f  jnz     short loc_18000789E
0x180007881  lea     rbx, [r8+4]
0x180007885  cmp     rbx, rsi
0x180007888  ja      short loc_1800078D8
0x18000788a  lea     edx, [rbp+2]; DestinationSize
0x18000788d  mov     [rcx+10h], r8
0x180007891  mov     r9d, edx; SourceSize
0x180007894  add     rcx, 4; Destination
0x180007898  call    cs:__imp_memcpy_s
0x18000789e  movzx   eax, word ptr [rdi]
0x1800078a1  lea     r14, [rdi+8]
0x1800078a5  mov     [r14], ax
0x1800078a9  test    ax, ax
0x1800078ac  jnz     short loc_1800078CC
0x1800078ae  lea     r15, [rbx+2]
0x1800078b2  cmp     r15, rsi
0x1800078b5  ja      short loc_1800078D8
0x1800078b7  mov     r9, rbp; SourceSize
0x1800078ba  mov     r8, rbx; Source
0x1800078bd  mov     rdx, rbp; DestinationSize
0x1800078c0  mov     rcx, r14; Destination
0x1800078c3  call    cs:__imp_memcpy_s
0x1800078c9  mov     rbx, r15
0x1800078cc  movzx   ecx, word ptr [r14]
0x1800078d0  add     rcx, rbx
0x1800078d3  cmp     rcx, rsi
0x1800078d6  jbe     short loc_1800078DC
0x1800078d8  xor     al, al
0x1800078da  jmp     short loc_1800078E6
0x1800078dc  mov     [rdi+18h], rbx
0x1800078e0  mov     al, 1
0x1800078e2  mov     [r12], rcx
0x1800078e6  mov     rbx, [rsp+48h+arg_8]
0x1800078eb  mov     rbp, [rsp+48h+arg_10]
0x1800078f0  add     rsp, 20h
0x1800078f4  pop     r15
0x1800078f6  pop     r14
0x1800078f8  pop     r12
0x1800078fa  pop     rdi
0x1800078fb  pop     rsi
0x1800078fc  retn
```
