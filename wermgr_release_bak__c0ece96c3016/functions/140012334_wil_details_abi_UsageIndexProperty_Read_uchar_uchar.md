# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x140012334`
- end: `0x14001242c`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `248`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140011480`
- `0x140012970`
- `0x140012d44`

## callees

- `0x140002f0e`
- `0x140012334`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140012371`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400123b3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400123f2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140012371`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400123b3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400123f2`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Read(
        wil::details_abi::UsageIndexProperty *this,
        unsigned __int8 **a2,
        unsigned __int8 *a3)
{
  unsigned __int16 *v3; // rax
  unsigned __int16 *v7; // rbx
  unsigned __int16 v8; // cx
  _DWORD *v9; // rcx
  __int16 v10; // ax
  unsigned __int8 *v11; // rcx
  bool result; // al

  v3 = (unsigned __int16 *)*a2;
  if ( *((_BYTE *)this + 2) == 1 )
  {
    v7 = v3 + 1;
    if ( v3 + 1 > (unsigned __int16 *)a3 )
      return 0;
    *((_QWORD *)this + 2) = v3;
    if ( v3 )
    {
      v8 = *v3;
    }
    else
    {
      *(_DWORD *)_o__errno() = 22;
      invalid_parameter_noinfo();
      v8 = 0;
    }
    *((_DWORD *)this + 1) = v8;
  }
  else if ( *((_BYTE *)this + 2) == 2 )
  {
    v7 = v3 + 2;
    if ( v3 + 2 > (unsigned __int16 *)a3 )
      return 0;
    *((_QWORD *)this + 2) = v3;
    v9 = (_DWORD *)((char *)this + 4);
    if ( v9 )
    {
      if ( v3 )
      {
        *v9 = *(_DWORD *)v3;
        goto LABEL_15;
      }
      *v9 = 0;
    }
    *(_DWORD *)_o__errno() = 22;
    invalid_parameter_noinfo();
  }
  else
  {
    v7 = (unsigned __int16 *)*a2;
  }
LABEL_15:
  v10 = *(_WORD *)this;
  *((_WORD *)this + 4) = *(_WORD *)this;
  if ( v10 )
    goto LABEL_21;
  if ( v7 + 1 > (unsigned __int16 *)a3 )
    return 0;
  if ( v7 )
  {
    *((_WORD *)this + 4) = *v7;
  }
  else
  {
    *((_WORD *)this + 4) = 0;
    *(_DWORD *)_o__errno() = 22;
    invalid_parameter_noinfo();
  }
  ++v7;
LABEL_21:
  v11 = (unsigned __int8 *)v7 + *((unsigned __int16 *)this + 4);
  if ( v11 > a3 )
    return 0;
  *((_QWORD *)this + 3) = v7;
  result = 1;
  *a2 = v11;
  return result;
}

```

## disassembly

```asm
0x140012334  push    rbx
0x140012336  push    rbp
0x140012337  push    rsi
0x140012338  push    rdi
0x140012339  push    r14
0x14001233b  push    r15
0x14001233d  sub     rsp, 28h
0x140012341  mov     rax, [rdx]
0x140012344  xor     r15d, r15d
0x140012347  cmp     byte ptr [rcx+2], 1
0x14001234b  mov     rbp, r8
0x14001234e  mov     r14, rdx
0x140012351  mov     rdi, rcx
0x140012354  jnz     short loc_14001238D
0x140012356  lea     rbx, [rax+2]
0x14001235a  cmp     rbx, r8
0x14001235d  ja      loc_140012412
0x140012363  mov     [rcx+10h], rax
0x140012367  test    rax, rax
0x14001236a  jz      short loc_140012371
0x14001236c  movzx   ecx, word ptr [rax]
0x14001236f  jmp     short loc_140012385
0x140012371  call    cs:__imp__o__errno
0x140012377  mov     dword ptr [rax], 16h
0x14001237d  call    _invalid_parameter_noinfo
0x140012382  mov     ecx, r15d
0x140012385  movzx   eax, cx
0x140012388  mov     [rdi+4], eax
0x14001238b  jmp     short loc_1400123C9
0x14001238d  cmp     byte ptr [rcx+2], 2
0x140012391  jnz     short loc_1400123C6
0x140012393  lea     rbx, [rax+4]
0x140012397  cmp     rbx, rbp
0x14001239a  ja      short loc_140012412
0x14001239c  mov     [rcx+10h], rax
0x1400123a0  add     rcx, 4
0x1400123a4  jz      short loc_1400123B3
0x1400123a6  test    rax, rax
0x1400123a9  jz      short loc_1400123B1
0x1400123ab  mov     eax, [rax]
0x1400123ad  mov     [rcx], eax
0x1400123af  jmp     short loc_1400123C9
0x1400123b1  mov     [rcx], eax
0x1400123b3  call    cs:__imp__o__errno
0x1400123b9  mov     dword ptr [rax], 16h
0x1400123bf  call    _invalid_parameter_noinfo
0x1400123c4  jmp     short loc_1400123C9
0x1400123c6  mov     rbx, rax
0x1400123c9  movzx   eax, word ptr [rdi]
0x1400123cc  mov     [rdi+8], ax
0x1400123d0  test    ax, ax
0x1400123d3  jnz     short loc_140012406
0x1400123d5  lea     rsi, [rbx+2]
0x1400123d9  cmp     rsi, rbp
0x1400123dc  ja      short loc_140012412
0x1400123de  test    rbx, rbx
0x1400123e1  jz      short loc_1400123EC
0x1400123e3  movzx   eax, word ptr [rbx]
0x1400123e6  mov     [rdi+8], ax
0x1400123ea  jmp     short loc_140012403
0x1400123ec  xor     eax, eax
0x1400123ee  mov     [rdi+8], ax
0x1400123f2  call    cs:__imp__o__errno
0x1400123f8  mov     dword ptr [rax], 16h
0x1400123fe  call    _invalid_parameter_noinfo
0x140012403  mov     rbx, rsi
0x140012406  movzx   ecx, word ptr [rdi+8]
0x14001240a  add     rcx, rbx
0x14001240d  cmp     rcx, rbp
0x140012410  jbe     short loc_140012416
0x140012412  xor     al, al
0x140012414  jmp     short loc_14001241F
0x140012416  mov     [rdi+18h], rbx
0x14001241a  mov     al, 1
0x14001241c  mov     [r14], rcx
0x14001241f  add     rsp, 28h
0x140012423  pop     r15
0x140012425  pop     r14
0x140012427  pop     rdi
0x140012428  pop     rsi
0x140012429  pop     rbp
0x14001242a  pop     rbx
0x14001242b  retn
```
