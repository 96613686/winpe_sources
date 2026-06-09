# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x18000c5c4`
- end: `0x18000c6bc`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `248`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000bddc`
- `0x18000cba8`
- `0x18000cf7c`

## callees

- `0x18000313a`
- `0x18000c5c4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000c601`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000c643`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000c682`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000c601`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000c643`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000c682`

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
0x18000c5c4  push    rbx
0x18000c5c6  push    rbp
0x18000c5c7  push    rsi
0x18000c5c8  push    rdi
0x18000c5c9  push    r14
0x18000c5cb  push    r15
0x18000c5cd  sub     rsp, 28h
0x18000c5d1  mov     rax, [rdx]
0x18000c5d4  xor     r15d, r15d
0x18000c5d7  cmp     byte ptr [rcx+2], 1
0x18000c5db  mov     rbp, r8
0x18000c5de  mov     r14, rdx
0x18000c5e1  mov     rdi, rcx
0x18000c5e4  jnz     short loc_18000C61D
0x18000c5e6  lea     rbx, [rax+2]
0x18000c5ea  cmp     rbx, r8
0x18000c5ed  ja      loc_18000C6A2
0x18000c5f3  mov     [rcx+10h], rax
0x18000c5f7  test    rax, rax
0x18000c5fa  jz      short loc_18000C601
0x18000c5fc  movzx   ecx, word ptr [rax]
0x18000c5ff  jmp     short loc_18000C615
0x18000c601  call    cs:__imp__o__errno
0x18000c607  mov     dword ptr [rax], 16h
0x18000c60d  call    _invalid_parameter_noinfo
0x18000c612  mov     ecx, r15d
0x18000c615  movzx   eax, cx
0x18000c618  mov     [rdi+4], eax
0x18000c61b  jmp     short loc_18000C659
0x18000c61d  cmp     byte ptr [rcx+2], 2
0x18000c621  jnz     short loc_18000C656
0x18000c623  lea     rbx, [rax+4]
0x18000c627  cmp     rbx, rbp
0x18000c62a  ja      short loc_18000C6A2
0x18000c62c  mov     [rcx+10h], rax
0x18000c630  add     rcx, 4
0x18000c634  jz      short loc_18000C643
0x18000c636  test    rax, rax
0x18000c639  jz      short loc_18000C641
0x18000c63b  mov     eax, [rax]
0x18000c63d  mov     [rcx], eax
0x18000c63f  jmp     short loc_18000C659
0x18000c641  mov     [rcx], eax
0x18000c643  call    cs:__imp__o__errno
0x18000c649  mov     dword ptr [rax], 16h
0x18000c64f  call    _invalid_parameter_noinfo
0x18000c654  jmp     short loc_18000C659
0x18000c656  mov     rbx, rax
0x18000c659  movzx   eax, word ptr [rdi]
0x18000c65c  mov     [rdi+8], ax
0x18000c660  test    ax, ax
0x18000c663  jnz     short loc_18000C696
0x18000c665  lea     rsi, [rbx+2]
0x18000c669  cmp     rsi, rbp
0x18000c66c  ja      short loc_18000C6A2
0x18000c66e  test    rbx, rbx
0x18000c671  jz      short loc_18000C67C
0x18000c673  movzx   eax, word ptr [rbx]
0x18000c676  mov     [rdi+8], ax
0x18000c67a  jmp     short loc_18000C693
0x18000c67c  xor     eax, eax
0x18000c67e  mov     [rdi+8], ax
0x18000c682  call    cs:__imp__o__errno
0x18000c688  mov     dword ptr [rax], 16h
0x18000c68e  call    _invalid_parameter_noinfo
0x18000c693  mov     rbx, rsi
0x18000c696  movzx   ecx, word ptr [rdi+8]
0x18000c69a  add     rcx, rbx
0x18000c69d  cmp     rcx, rbp
0x18000c6a0  jbe     short loc_18000C6A6
0x18000c6a2  xor     al, al
0x18000c6a4  jmp     short loc_18000C6AF
0x18000c6a6  mov     [rdi+18h], rbx
0x18000c6aa  mov     al, 1
0x18000c6ac  mov     [r14], rcx
0x18000c6af  add     rsp, 28h
0x18000c6b3  pop     r15
0x18000c6b5  pop     r14
0x18000c6b7  pop     rdi
0x18000c6b8  pop     rsi
0x18000c6b9  pop     rbp
0x18000c6ba  pop     rbx
0x18000c6bb  retn
```
