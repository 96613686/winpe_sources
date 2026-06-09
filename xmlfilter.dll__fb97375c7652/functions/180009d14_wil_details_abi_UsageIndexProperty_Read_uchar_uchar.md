# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x180009d14`
- end: `0x180009e0c`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `248`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180006158`
- `0x18000a5a8`
- `0x18000a97c`

## callees

- `0x180002ae2`
- `0x180009d14`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180009d51`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180009d93`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180009dd2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180009d51`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180009d93`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180009dd2`

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
0x180009d14  push    rbx
0x180009d16  push    rbp
0x180009d17  push    rsi
0x180009d18  push    rdi
0x180009d19  push    r14
0x180009d1b  push    r15
0x180009d1d  sub     rsp, 28h
0x180009d21  mov     rax, [rdx]
0x180009d24  xor     r15d, r15d
0x180009d27  cmp     byte ptr [rcx+2], 1
0x180009d2b  mov     rbp, r8
0x180009d2e  mov     r14, rdx
0x180009d31  mov     rdi, rcx
0x180009d34  jnz     short loc_180009D6D
0x180009d36  lea     rbx, [rax+2]
0x180009d3a  cmp     rbx, r8
0x180009d3d  ja      loc_180009DF2
0x180009d43  mov     [rcx+10h], rax
0x180009d47  test    rax, rax
0x180009d4a  jz      short loc_180009D51
0x180009d4c  movzx   ecx, word ptr [rax]
0x180009d4f  jmp     short loc_180009D65
0x180009d51  call    cs:__imp__o__errno
0x180009d57  mov     dword ptr [rax], 16h
0x180009d5d  call    _invalid_parameter_noinfo
0x180009d62  mov     ecx, r15d
0x180009d65  movzx   eax, cx
0x180009d68  mov     [rdi+4], eax
0x180009d6b  jmp     short loc_180009DA9
0x180009d6d  cmp     byte ptr [rcx+2], 2
0x180009d71  jnz     short loc_180009DA6
0x180009d73  lea     rbx, [rax+4]
0x180009d77  cmp     rbx, rbp
0x180009d7a  ja      short loc_180009DF2
0x180009d7c  mov     [rcx+10h], rax
0x180009d80  add     rcx, 4
0x180009d84  jz      short loc_180009D93
0x180009d86  test    rax, rax
0x180009d89  jz      short loc_180009D91
0x180009d8b  mov     eax, [rax]
0x180009d8d  mov     [rcx], eax
0x180009d8f  jmp     short loc_180009DA9
0x180009d91  mov     [rcx], eax
0x180009d93  call    cs:__imp__o__errno
0x180009d99  mov     dword ptr [rax], 16h
0x180009d9f  call    _invalid_parameter_noinfo
0x180009da4  jmp     short loc_180009DA9
0x180009da6  mov     rbx, rax
0x180009da9  movzx   eax, word ptr [rdi]
0x180009dac  mov     [rdi+8], ax
0x180009db0  test    ax, ax
0x180009db3  jnz     short loc_180009DE6
0x180009db5  lea     rsi, [rbx+2]
0x180009db9  cmp     rsi, rbp
0x180009dbc  ja      short loc_180009DF2
0x180009dbe  test    rbx, rbx
0x180009dc1  jz      short loc_180009DCC
0x180009dc3  movzx   eax, word ptr [rbx]
0x180009dc6  mov     [rdi+8], ax
0x180009dca  jmp     short loc_180009DE3
0x180009dcc  xor     eax, eax
0x180009dce  mov     [rdi+8], ax
0x180009dd2  call    cs:__imp__o__errno
0x180009dd8  mov     dword ptr [rax], 16h
0x180009dde  call    _invalid_parameter_noinfo
0x180009de3  mov     rbx, rsi
0x180009de6  movzx   ecx, word ptr [rdi+8]
0x180009dea  add     rcx, rbx
0x180009ded  cmp     rcx, rbp
0x180009df0  jbe     short loc_180009DF6
0x180009df2  xor     al, al
0x180009df4  jmp     short loc_180009DFF
0x180009df6  mov     [rdi+18h], rbx
0x180009dfa  mov     al, 1
0x180009dfc  mov     [r14], rcx
0x180009dff  add     rsp, 28h
0x180009e03  pop     r15
0x180009e05  pop     r14
0x180009e07  pop     rdi
0x180009e08  pop     rsi
0x180009e09  pop     rbp
0x180009e0a  pop     rbx
0x180009e0b  retn
```
