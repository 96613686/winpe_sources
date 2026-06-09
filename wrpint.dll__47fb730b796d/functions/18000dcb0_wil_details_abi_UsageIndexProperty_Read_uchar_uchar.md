# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x18000dcb0`
- end: `0x18000ddaf`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `255`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c518`
- `0x18000e378`
- `0x18000e75c`

## callees

- `0x180001df8`
- `0x18000dcb0`

## import_xrefs

- `msvcrt!_errno` at `0x18000dcf0`
- `msvcrt!_errno` at `0x18000dd32`
- `msvcrt!_errno` at `0x18000dd71`
- `msvcrt!_errno` at `0x18000dcf0`
- `msvcrt!_errno` at `0x18000dd32`
- `msvcrt!_errno` at `0x18000dd71`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Read(
        wil::details_abi::UsageIndexProperty *this,
        unsigned __int8 **a2,
        unsigned __int8 *a3)
{
  _DWORD *v3; // rax
  _WORD *v5; // rbx
  _DWORD *v6; // rcx
  __int16 v7; // ax
  unsigned __int8 *v8; // rcx
  bool result; // al

  v3 = *a2;
  if ( *((_BYTE *)this + 2) == 1 )
  {
    v5 = (_WORD *)v3 + 1;
    if ( (unsigned __int8 *)((char *)v3 + 2) > a3 )
      return 0;
    *((_QWORD *)this + 2) = v3;
    if ( !v3 )
    {
      *_errno() = 22;
      invalid_parameter_noinfo();
    }
    *((_DWORD *)this + 1) = *(unsigned __int16 *)v3;
  }
  else
  {
    if ( *((_BYTE *)this + 2) == 2 )
    {
      v5 = v3 + 1;
      if ( v3 + 1 > (_DWORD *)a3 )
        return 0;
      *((_QWORD *)this + 2) = v3;
      v6 = (_DWORD *)((char *)this + 4);
      if ( v6 )
      {
        if ( v3 )
        {
          *v6 = *v3;
          goto LABEL_14;
        }
        *v6 = 0;
      }
      *_errno() = 22;
      invalid_parameter_noinfo();
    }
    v5 = *a2;
  }
LABEL_14:
  v7 = *(_WORD *)this;
  *((_WORD *)this + 4) = *(_WORD *)this;
  if ( v7 )
    goto LABEL_19;
  if ( v5 + 1 > (_WORD *)a3 )
    return 0;
  if ( !v5 )
  {
    *((_WORD *)this + 4) = 0;
    *_errno() = 22;
    invalid_parameter_noinfo();
  }
  *((_WORD *)this + 4) = *v5++;
LABEL_19:
  v8 = (unsigned __int8 *)v5 + *((unsigned __int16 *)this + 4);
  if ( v8 > a3 )
    return 0;
  *((_QWORD *)this + 3) = v5;
  result = 1;
  *a2 = v8;
  return result;
}

```

## disassembly

```asm
0x18000dcb0  mov     [rsp+arg_10], rbx
0x18000dcb5  push    rbp
0x18000dcb6  push    rsi
0x18000dcb7  push    rdi
0x18000dcb8  push    r14
0x18000dcba  push    r15
0x18000dcbc  sub     rsp, 20h
0x18000dcc0  mov     rax, [rdx]
0x18000dcc3  xor     r15d, r15d
0x18000dcc6  cmp     byte ptr [rcx+2], 1
0x18000dcca  mov     rbp, r8
0x18000dccd  mov     r14, rdx
0x18000dcd0  mov     rdi, rcx
0x18000dcd3  jnz     short loc_18000DD0C
0x18000dcd5  lea     rbx, [rax+2]
0x18000dcd9  cmp     rbx, r8
0x18000dcdc  ja      loc_18000DD91
0x18000dce2  mov     [rcx+10h], rax
0x18000dce6  test    rax, rax
0x18000dce9  jz      short loc_18000DCF0
0x18000dceb  movzx   ecx, word ptr [rax]
0x18000dcee  jmp     short loc_18000DD04
0x18000dcf0  call    cs:__imp__errno
0x18000dcf6  mov     dword ptr [rax], 16h
0x18000dcfc  call    _invalid_parameter_noinfo
0x18000dd01  mov     ecx, r15d
0x18000dd04  movzx   eax, cx
0x18000dd07  mov     [rdi+4], eax
0x18000dd0a  jmp     short loc_18000DD48
0x18000dd0c  cmp     byte ptr [rcx+2], 2
0x18000dd10  jnz     short loc_18000DD45
0x18000dd12  lea     rbx, [rax+4]
0x18000dd16  cmp     rbx, rbp
0x18000dd19  ja      short loc_18000DD91
0x18000dd1b  mov     [rcx+10h], rax
0x18000dd1f  add     rcx, 4
0x18000dd23  jz      short loc_18000DD32
0x18000dd25  test    rax, rax
0x18000dd28  jz      short loc_18000DD30
0x18000dd2a  mov     eax, [rax]
0x18000dd2c  mov     [rcx], eax
0x18000dd2e  jmp     short loc_18000DD48
0x18000dd30  mov     [rcx], eax
0x18000dd32  call    cs:__imp__errno
0x18000dd38  mov     dword ptr [rax], 16h
0x18000dd3e  call    _invalid_parameter_noinfo
0x18000dd43  jmp     short loc_18000DD48
0x18000dd45  mov     rbx, rax
0x18000dd48  movzx   eax, word ptr [rdi]
0x18000dd4b  mov     [rdi+8], ax
0x18000dd4f  test    ax, ax
0x18000dd52  jnz     short loc_18000DD85
0x18000dd54  lea     rsi, [rbx+2]
0x18000dd58  cmp     rsi, rbp
0x18000dd5b  ja      short loc_18000DD91
0x18000dd5d  test    rbx, rbx
0x18000dd60  jz      short loc_18000DD6B
0x18000dd62  movzx   eax, word ptr [rbx]
0x18000dd65  mov     [rdi+8], ax
0x18000dd69  jmp     short loc_18000DD82
0x18000dd6b  xor     eax, eax
0x18000dd6d  mov     [rdi+8], ax
0x18000dd71  call    cs:__imp__errno
0x18000dd77  mov     dword ptr [rax], 16h
0x18000dd7d  call    _invalid_parameter_noinfo
0x18000dd82  mov     rbx, rsi
0x18000dd85  movzx   ecx, word ptr [rdi+8]
0x18000dd89  add     rcx, rbx
0x18000dd8c  cmp     rcx, rbp
0x18000dd8f  jbe     short loc_18000DD95
0x18000dd91  xor     al, al
0x18000dd93  jmp     short loc_18000DD9E
0x18000dd95  mov     [rdi+18h], rbx
0x18000dd99  mov     al, 1
0x18000dd9b  mov     [r14], rcx
0x18000dd9e  mov     rbx, [rsp+48h+arg_10]
0x18000dda3  add     rsp, 20h
0x18000dda7  pop     r15
0x18000dda9  pop     r14
0x18000ddab  pop     rdi
0x18000ddac  pop     rsi
0x18000ddad  pop     rbp
0x18000ddae  retn
```
