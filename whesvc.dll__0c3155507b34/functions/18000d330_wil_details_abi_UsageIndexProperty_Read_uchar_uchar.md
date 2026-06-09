# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x18000d330`
- end: `0x18000d428`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `248`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000cc14`
- `0x18000db08`
- `0x18000dedc`

## callees

- `0x180003d0a`
- `0x18000d330`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000d36d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000d3af`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000d3ee`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000d36d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000d3af`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000d3ee`

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
0x18000d330  push    rbx
0x18000d332  push    rbp
0x18000d333  push    rsi
0x18000d334  push    rdi
0x18000d335  push    r14
0x18000d337  push    r15
0x18000d339  sub     rsp, 28h
0x18000d33d  mov     rax, [rdx]
0x18000d340  xor     r15d, r15d
0x18000d343  cmp     byte ptr [rcx+2], 1
0x18000d347  mov     rbp, r8
0x18000d34a  mov     r14, rdx
0x18000d34d  mov     rdi, rcx
0x18000d350  jnz     short loc_18000D389
0x18000d352  lea     rbx, [rax+2]
0x18000d356  cmp     rbx, r8
0x18000d359  ja      loc_18000D40E
0x18000d35f  mov     [rcx+10h], rax
0x18000d363  test    rax, rax
0x18000d366  jz      short loc_18000D36D
0x18000d368  movzx   ecx, word ptr [rax]
0x18000d36b  jmp     short loc_18000D381
0x18000d36d  call    cs:__imp__o__errno
0x18000d373  mov     dword ptr [rax], 16h
0x18000d379  call    _invalid_parameter_noinfo
0x18000d37e  mov     ecx, r15d
0x18000d381  movzx   eax, cx
0x18000d384  mov     [rdi+4], eax
0x18000d387  jmp     short loc_18000D3C5
0x18000d389  cmp     byte ptr [rcx+2], 2
0x18000d38d  jnz     short loc_18000D3C2
0x18000d38f  lea     rbx, [rax+4]
0x18000d393  cmp     rbx, rbp
0x18000d396  ja      short loc_18000D40E
0x18000d398  mov     [rcx+10h], rax
0x18000d39c  add     rcx, 4
0x18000d3a0  jz      short loc_18000D3AF
0x18000d3a2  test    rax, rax
0x18000d3a5  jz      short loc_18000D3AD
0x18000d3a7  mov     eax, [rax]
0x18000d3a9  mov     [rcx], eax
0x18000d3ab  jmp     short loc_18000D3C5
0x18000d3ad  mov     [rcx], eax
0x18000d3af  call    cs:__imp__o__errno
0x18000d3b5  mov     dword ptr [rax], 16h
0x18000d3bb  call    _invalid_parameter_noinfo
0x18000d3c0  jmp     short loc_18000D3C5
0x18000d3c2  mov     rbx, rax
0x18000d3c5  movzx   eax, word ptr [rdi]
0x18000d3c8  mov     [rdi+8], ax
0x18000d3cc  test    ax, ax
0x18000d3cf  jnz     short loc_18000D402
0x18000d3d1  lea     rsi, [rbx+2]
0x18000d3d5  cmp     rsi, rbp
0x18000d3d8  ja      short loc_18000D40E
0x18000d3da  test    rbx, rbx
0x18000d3dd  jz      short loc_18000D3E8
0x18000d3df  movzx   eax, word ptr [rbx]
0x18000d3e2  mov     [rdi+8], ax
0x18000d3e6  jmp     short loc_18000D3FF
0x18000d3e8  xor     eax, eax
0x18000d3ea  mov     [rdi+8], ax
0x18000d3ee  call    cs:__imp__o__errno
0x18000d3f4  mov     dword ptr [rax], 16h
0x18000d3fa  call    _invalid_parameter_noinfo
0x18000d3ff  mov     rbx, rsi
0x18000d402  movzx   ecx, word ptr [rdi+8]
0x18000d406  add     rcx, rbx
0x18000d409  cmp     rcx, rbp
0x18000d40c  jbe     short loc_18000D412
0x18000d40e  xor     al, al
0x18000d410  jmp     short loc_18000D41B
0x18000d412  mov     [rdi+18h], rbx
0x18000d416  mov     al, 1
0x18000d418  mov     [r14], rcx
0x18000d41b  add     rsp, 28h
0x18000d41f  pop     r15
0x18000d421  pop     r14
0x18000d423  pop     rdi
0x18000d424  pop     rsi
0x18000d425  pop     rbp
0x18000d426  pop     rbx
0x18000d427  retn
```
