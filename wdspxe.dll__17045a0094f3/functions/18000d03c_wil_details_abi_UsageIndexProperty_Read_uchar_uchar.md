# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x18000d03c`
- end: `0x18000d135`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `249`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b290`
- `0x18000d924`
- `0x18000dcdc`

## callees

- `0x18000d03c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000d08c`
- `msvcrt!memcpy_s` at `0x18000d0c4`
- `msvcrt!memcpy_s` at `0x18000d0f5`
- `msvcrt!memcpy_s` at `0x18000d08c`
- `msvcrt!memcpy_s` at `0x18000d0c4`
- `msvcrt!memcpy_s` at `0x18000d0f5`

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
0x18000d03c  mov     rax, rsp
0x18000d03f  mov     [rax+10h], rbx
0x18000d043  mov     [rax+18h], rbp
0x18000d047  push    rsi
0x18000d048  push    rdi
0x18000d049  push    r12
0x18000d04b  push    r14
0x18000d04d  push    r15
0x18000d04f  sub     rsp, 20h
0x18000d053  xor     r12d, r12d
0x18000d056  mov     rdi, r8
0x18000d059  cmp     byte ptr [rcx+2], 1
0x18000d05d  mov     r15, rdx
0x18000d060  mov     r8, [rdx]; Source
0x18000d063  mov     rbx, rcx
0x18000d066  jnz     short loc_18000D0A2
0x18000d068  lea     rbp, [r8+2]
0x18000d06c  cmp     rbp, rdi
0x18000d06f  ja      loc_18000D110
0x18000d075  lea     esi, [r12+2]
0x18000d07a  mov     [rcx+10h], r8
0x18000d07e  mov     r9d, esi; SourceSize
0x18000d081  mov     [rax+8], r12w
0x18000d086  mov     edx, esi; DestinationSize
0x18000d088  lea     rcx, [rax+8]; Destination
0x18000d08c  call    cs:__imp_memcpy_s
0x18000d093  nop     dword ptr [rax+rax+00h]
0x18000d098  movzx   eax, [rsp+48h+arg_0]
0x18000d09d  mov     [rbx+4], eax
0x18000d0a0  jmp     short loc_18000D0D0
0x18000d0a2  mov     esi, 2
0x18000d0a7  cmp     [rcx+2], sil
0x18000d0ab  jnz     short loc_18000D0D3
0x18000d0ad  lea     rbp, [r8+4]
0x18000d0b1  cmp     rbp, rdi
0x18000d0b4  ja      short loc_18000D110
0x18000d0b6  lea     edx, [rsi+2]; DestinationSize
0x18000d0b9  mov     [rcx+10h], r8
0x18000d0bd  mov     r9d, edx; SourceSize
0x18000d0c0  add     rcx, 4; Destination
0x18000d0c4  call    cs:__imp_memcpy_s
0x18000d0cb  nop     dword ptr [rax+rax+00h]
0x18000d0d0  mov     r8, rbp; Source
0x18000d0d3  movzx   eax, word ptr [rbx]
0x18000d0d6  lea     r14, [rbx+8]
0x18000d0da  mov     [r14], ax
0x18000d0de  test    ax, ax
0x18000d0e1  jnz     short loc_18000D104
0x18000d0e3  lea     rbp, [r8+2]
0x18000d0e7  cmp     rbp, rdi
0x18000d0ea  ja      short loc_18000D110
0x18000d0ec  mov     r9, rsi; SourceSize
0x18000d0ef  mov     rdx, rsi; DestinationSize
0x18000d0f2  mov     rcx, r14; Destination
0x18000d0f5  call    cs:__imp_memcpy_s
0x18000d0fc  nop     dword ptr [rax+rax+00h]
0x18000d101  mov     r8, rbp
0x18000d104  movzx   ecx, word ptr [r14]
0x18000d108  add     rcx, r8
0x18000d10b  cmp     rcx, rdi
0x18000d10e  jbe     short loc_18000D114
0x18000d110  xor     al, al
0x18000d112  jmp     short loc_18000D11D
0x18000d114  mov     [rbx+18h], r8
0x18000d118  mov     al, 1
0x18000d11a  mov     [r15], rcx
0x18000d11d  mov     rbx, [rsp+48h+arg_8]
0x18000d122  mov     rbp, [rsp+48h+arg_10]
0x18000d127  add     rsp, 20h
0x18000d12b  pop     r15
0x18000d12d  pop     r14
0x18000d12f  pop     r12
0x18000d131  pop     rdi
0x18000d132  pop     rsi
0x18000d133  retn
```
