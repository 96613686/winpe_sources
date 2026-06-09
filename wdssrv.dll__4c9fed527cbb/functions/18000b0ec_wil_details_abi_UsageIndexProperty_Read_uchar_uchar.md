# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x18000b0ec`
- end: `0x18000b1e5`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `249`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800088dc`
- `0x18000bc4c`
- `0x18000c004`

## callees

- `0x18000b0ec`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000b13c`
- `msvcrt!memcpy_s` at `0x18000b174`
- `msvcrt!memcpy_s` at `0x18000b1a5`
- `msvcrt!memcpy_s` at `0x18000b13c`
- `msvcrt!memcpy_s` at `0x18000b174`
- `msvcrt!memcpy_s` at `0x18000b1a5`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Read(
        wil::details_abi::UsageIndexProperty *this,
        unsigned __int8 **a2,
        unsigned __int8 *a3)
{
  char *v5; // r8
  char *v7; // rbp
  __int16 v8; // ax
  char *v9; // rbp
  unsigned __int8 *v10; // rcx
  bool result; // al
  unsigned __int16 v12; // [rsp+50h] [rbp+8h] BYREF

  v5 = (char *)*a2;
  if ( *((_BYTE *)this + 2) == 1 )
  {
    v7 = v5 + 2;
    if ( v5 + 2 > (char *)a3 )
      return 0;
    *((_QWORD *)this + 2) = v5;
    v12 = 0;
    memcpy_s(&v12, 2u, v5, 2u);
    *((_DWORD *)this + 1) = v12;
  }
  else
  {
    if ( *((_BYTE *)this + 2) != 2 )
      goto LABEL_8;
    v7 = v5 + 4;
    if ( v5 + 4 > (char *)a3 )
      return 0;
    *((_QWORD *)this + 2) = v5;
    memcpy_s((char *)this + 4, 4u, v5, 4u);
  }
  v5 = v7;
LABEL_8:
  v8 = *(_WORD *)this;
  *((_WORD *)this + 4) = *(_WORD *)this;
  if ( v8 )
    goto LABEL_11;
  v9 = v5 + 2;
  if ( v5 + 2 > (char *)a3 )
    return 0;
  memcpy_s((char *)this + 8, 2u, v5, 2u);
  v5 = v9;
LABEL_11:
  v10 = (unsigned __int8 *)&v5[*((unsigned __int16 *)this + 4)];
  if ( v10 > a3 )
    return 0;
  *((_QWORD *)this + 3) = v5;
  result = 1;
  *a2 = v10;
  return result;
}

```

## disassembly

```asm
0x18000b0ec  mov     rax, rsp
0x18000b0ef  mov     [rax+10h], rbx
0x18000b0f3  mov     [rax+18h], rbp
0x18000b0f7  push    rsi
0x18000b0f8  push    rdi
0x18000b0f9  push    r12
0x18000b0fb  push    r14
0x18000b0fd  push    r15
0x18000b0ff  sub     rsp, 20h
0x18000b103  xor     r12d, r12d
0x18000b106  mov     rdi, r8
0x18000b109  cmp     byte ptr [rcx+2], 1
0x18000b10d  mov     r15, rdx
0x18000b110  mov     r8, [rdx]; Source
0x18000b113  mov     rbx, rcx
0x18000b116  jnz     short loc_18000B152
0x18000b118  lea     rbp, [r8+2]
0x18000b11c  cmp     rbp, rdi
0x18000b11f  ja      loc_18000B1C0
0x18000b125  lea     esi, [r12+2]
0x18000b12a  mov     [rcx+10h], r8
0x18000b12e  mov     r9d, esi; SourceSize
0x18000b131  mov     [rax+8], r12w
0x18000b136  mov     edx, esi; DestinationSize
0x18000b138  lea     rcx, [rax+8]; Destination
0x18000b13c  call    cs:__imp_memcpy_s
0x18000b143  nop     dword ptr [rax+rax+00h]
0x18000b148  movzx   eax, [rsp+48h+arg_0]
0x18000b14d  mov     [rbx+4], eax
0x18000b150  jmp     short loc_18000B180
0x18000b152  mov     esi, 2
0x18000b157  cmp     [rcx+2], sil
0x18000b15b  jnz     short loc_18000B183
0x18000b15d  lea     rbp, [r8+4]
0x18000b161  cmp     rbp, rdi
0x18000b164  ja      short loc_18000B1C0
0x18000b166  lea     edx, [rsi+2]; DestinationSize
0x18000b169  mov     [rcx+10h], r8
0x18000b16d  mov     r9d, edx; SourceSize
0x18000b170  add     rcx, 4; Destination
0x18000b174  call    cs:__imp_memcpy_s
0x18000b17b  nop     dword ptr [rax+rax+00h]
0x18000b180  mov     r8, rbp; Source
0x18000b183  movzx   eax, word ptr [rbx]
0x18000b186  lea     r14, [rbx+8]
0x18000b18a  mov     [r14], ax
0x18000b18e  test    ax, ax
0x18000b191  jnz     short loc_18000B1B4
0x18000b193  lea     rbp, [r8+2]
0x18000b197  cmp     rbp, rdi
0x18000b19a  ja      short loc_18000B1C0
0x18000b19c  mov     r9, rsi; SourceSize
0x18000b19f  mov     rdx, rsi; DestinationSize
0x18000b1a2  mov     rcx, r14; Destination
0x18000b1a5  call    cs:__imp_memcpy_s
0x18000b1ac  nop     dword ptr [rax+rax+00h]
0x18000b1b1  mov     r8, rbp
0x18000b1b4  movzx   ecx, word ptr [r14]
0x18000b1b8  add     rcx, r8
0x18000b1bb  cmp     rcx, rdi
0x18000b1be  jbe     short loc_18000B1C4
0x18000b1c0  xor     al, al
0x18000b1c2  jmp     short loc_18000B1CD
0x18000b1c4  mov     [rbx+18h], r8
0x18000b1c8  mov     al, 1
0x18000b1ca  mov     [r15], rcx
0x18000b1cd  mov     rbx, [rsp+48h+arg_8]
0x18000b1d2  mov     rbp, [rsp+48h+arg_10]
0x18000b1d7  add     rsp, 20h
0x18000b1db  pop     r15
0x18000b1dd  pop     r14
0x18000b1df  pop     r12
0x18000b1e1  pop     rdi
0x18000b1e2  pop     rsi
0x18000b1e3  retn
```
