# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x180008e0c`
- end: `0x180008f04`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `248`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180006d4c`
- `0x180009638`
- `0x180009a0c`

## callees

- `0x18000218a`
- `0x180008e0c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008e49`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008e8b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008eca`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008e49`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008e8b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008eca`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Read(
        wil::details_abi::UsageIndexProperty *this,
        unsigned __int8 **a2,
        unsigned __int8 *a3)
{
  unsigned __int8 *v3; // rax
  wil::details_abi::UsageIndexProperty *v6; // rdi
  unsigned __int8 *v7; // rbx
  __int16 v8; // ax
  unsigned __int8 *v9; // rcx
  bool result; // al

  v3 = *a2;
  v6 = this;
  if ( *((_BYTE *)this + 2) == 1 )
  {
    v7 = v3 + 2;
    if ( v3 + 2 > a3 )
      return 0;
    *((_QWORD *)this + 2) = v3;
    if ( v3 )
    {
      this = (wil::details_abi::UsageIndexProperty *)*(unsigned __int16 *)v3;
    }
    else
    {
      *(_DWORD *)_o__errno(this, a2, a3) = 22;
      invalid_parameter_noinfo();
      this = 0;
    }
    *((_DWORD *)v6 + 1) = (unsigned __int16)this;
  }
  else if ( *((_BYTE *)this + 2) == 2 )
  {
    v7 = v3 + 4;
    if ( v3 + 4 > a3 )
      return 0;
    *((_QWORD *)this + 2) = v3;
    this = (wil::details_abi::UsageIndexProperty *)((char *)this + 4);
    if ( this )
    {
      if ( v3 )
      {
        *(_DWORD *)this = *(_DWORD *)v3;
        goto LABEL_15;
      }
      *(_DWORD *)this = 0;
    }
    *(_DWORD *)_o__errno(this, a2, a3) = 22;
    invalid_parameter_noinfo();
  }
  else
  {
    v7 = *a2;
  }
LABEL_15:
  v8 = *(_WORD *)v6;
  *((_WORD *)v6 + 4) = *(_WORD *)v6;
  if ( v8 )
    goto LABEL_21;
  if ( v7 + 2 > a3 )
    return 0;
  if ( v7 )
  {
    *((_WORD *)v6 + 4) = *(_WORD *)v7;
  }
  else
  {
    *((_WORD *)v6 + 4) = 0;
    *(_DWORD *)_o__errno(this, a2, a3) = 22;
    invalid_parameter_noinfo();
  }
  v7 += 2;
LABEL_21:
  v9 = &v7[*((unsigned __int16 *)v6 + 4)];
  if ( v9 > a3 )
    return 0;
  *((_QWORD *)v6 + 3) = v7;
  result = 1;
  *a2 = v9;
  return result;
}

```

## disassembly

```asm
0x180008e0c  push    rbx
0x180008e0e  push    rbp
0x180008e0f  push    rsi
0x180008e10  push    rdi
0x180008e11  push    r14
0x180008e13  push    r15
0x180008e15  sub     rsp, 28h
0x180008e19  mov     rax, [rdx]
0x180008e1c  xor     r15d, r15d
0x180008e1f  cmp     byte ptr [rcx+2], 1
0x180008e23  mov     rbp, r8
0x180008e26  mov     r14, rdx
0x180008e29  mov     rdi, rcx
0x180008e2c  jnz     short loc_180008E65
0x180008e2e  lea     rbx, [rax+2]
0x180008e32  cmp     rbx, r8
0x180008e35  ja      loc_180008EEA
0x180008e3b  mov     [rcx+10h], rax
0x180008e3f  test    rax, rax
0x180008e42  jz      short loc_180008E49
0x180008e44  movzx   ecx, word ptr [rax]
0x180008e47  jmp     short loc_180008E5D
0x180008e49  call    cs:__imp__o__errno
0x180008e4f  mov     dword ptr [rax], 16h
0x180008e55  call    _invalid_parameter_noinfo
0x180008e5a  mov     ecx, r15d
0x180008e5d  movzx   eax, cx
0x180008e60  mov     [rdi+4], eax
0x180008e63  jmp     short loc_180008EA1
0x180008e65  cmp     byte ptr [rcx+2], 2
0x180008e69  jnz     short loc_180008E9E
0x180008e6b  lea     rbx, [rax+4]
0x180008e6f  cmp     rbx, rbp
0x180008e72  ja      short loc_180008EEA
0x180008e74  mov     [rcx+10h], rax
0x180008e78  add     rcx, 4
0x180008e7c  jz      short loc_180008E8B
0x180008e7e  test    rax, rax
0x180008e81  jz      short loc_180008E89
0x180008e83  mov     eax, [rax]
0x180008e85  mov     [rcx], eax
0x180008e87  jmp     short loc_180008EA1
0x180008e89  mov     [rcx], eax
0x180008e8b  call    cs:__imp__o__errno
0x180008e91  mov     dword ptr [rax], 16h
0x180008e97  call    _invalid_parameter_noinfo
0x180008e9c  jmp     short loc_180008EA1
0x180008e9e  mov     rbx, rax
0x180008ea1  movzx   eax, word ptr [rdi]
0x180008ea4  mov     [rdi+8], ax
0x180008ea8  test    ax, ax
0x180008eab  jnz     short loc_180008EDE
0x180008ead  lea     rsi, [rbx+2]
0x180008eb1  cmp     rsi, rbp
0x180008eb4  ja      short loc_180008EEA
0x180008eb6  test    rbx, rbx
0x180008eb9  jz      short loc_180008EC4
0x180008ebb  movzx   eax, word ptr [rbx]
0x180008ebe  mov     [rdi+8], ax
0x180008ec2  jmp     short loc_180008EDB
0x180008ec4  xor     eax, eax
0x180008ec6  mov     [rdi+8], ax
0x180008eca  call    cs:__imp__o__errno
0x180008ed0  mov     dword ptr [rax], 16h
0x180008ed6  call    _invalid_parameter_noinfo
0x180008edb  mov     rbx, rsi
0x180008ede  movzx   ecx, word ptr [rdi+8]
0x180008ee2  add     rcx, rbx
0x180008ee5  cmp     rcx, rbp
0x180008ee8  jbe     short loc_180008EEE
0x180008eea  xor     al, al
0x180008eec  jmp     short loc_180008EF7
0x180008eee  mov     [rdi+18h], rbx
0x180008ef2  mov     al, 1
0x180008ef4  mov     [r14], rcx
0x180008ef7  add     rsp, 28h
0x180008efb  pop     r15
0x180008efd  pop     r14
0x180008eff  pop     rdi
0x180008f00  pop     rsi
0x180008f01  pop     rbp
0x180008f02  pop     rbx
0x180008f03  retn
```
