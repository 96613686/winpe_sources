# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x1800081cc`
- end: `0x1800082c4`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `248`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180005fa0`
- `0x180008a58`
- `0x180008e2c`

## callees

- `0x180002846`
- `0x1800081cc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008209`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000824b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000828a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008209`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000824b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000828a`

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
0x1800081cc  push    rbx
0x1800081ce  push    rbp
0x1800081cf  push    rsi
0x1800081d0  push    rdi
0x1800081d1  push    r14
0x1800081d3  push    r15
0x1800081d5  sub     rsp, 28h
0x1800081d9  mov     rax, [rdx]
0x1800081dc  xor     r15d, r15d
0x1800081df  cmp     byte ptr [rcx+2], 1
0x1800081e3  mov     rbp, r8
0x1800081e6  mov     r14, rdx
0x1800081e9  mov     rdi, rcx
0x1800081ec  jnz     short loc_180008225
0x1800081ee  lea     rbx, [rax+2]
0x1800081f2  cmp     rbx, r8
0x1800081f5  ja      loc_1800082AA
0x1800081fb  mov     [rcx+10h], rax
0x1800081ff  test    rax, rax
0x180008202  jz      short loc_180008209
0x180008204  movzx   ecx, word ptr [rax]
0x180008207  jmp     short loc_18000821D
0x180008209  call    cs:__imp__o__errno
0x18000820f  mov     dword ptr [rax], 16h
0x180008215  call    _invalid_parameter_noinfo
0x18000821a  mov     ecx, r15d
0x18000821d  movzx   eax, cx
0x180008220  mov     [rdi+4], eax
0x180008223  jmp     short loc_180008261
0x180008225  cmp     byte ptr [rcx+2], 2
0x180008229  jnz     short loc_18000825E
0x18000822b  lea     rbx, [rax+4]
0x18000822f  cmp     rbx, rbp
0x180008232  ja      short loc_1800082AA
0x180008234  mov     [rcx+10h], rax
0x180008238  add     rcx, 4
0x18000823c  jz      short loc_18000824B
0x18000823e  test    rax, rax
0x180008241  jz      short loc_180008249
0x180008243  mov     eax, [rax]
0x180008245  mov     [rcx], eax
0x180008247  jmp     short loc_180008261
0x180008249  mov     [rcx], eax
0x18000824b  call    cs:__imp__o__errno
0x180008251  mov     dword ptr [rax], 16h
0x180008257  call    _invalid_parameter_noinfo
0x18000825c  jmp     short loc_180008261
0x18000825e  mov     rbx, rax
0x180008261  movzx   eax, word ptr [rdi]
0x180008264  mov     [rdi+8], ax
0x180008268  test    ax, ax
0x18000826b  jnz     short loc_18000829E
0x18000826d  lea     rsi, [rbx+2]
0x180008271  cmp     rsi, rbp
0x180008274  ja      short loc_1800082AA
0x180008276  test    rbx, rbx
0x180008279  jz      short loc_180008284
0x18000827b  movzx   eax, word ptr [rbx]
0x18000827e  mov     [rdi+8], ax
0x180008282  jmp     short loc_18000829B
0x180008284  xor     eax, eax
0x180008286  mov     [rdi+8], ax
0x18000828a  call    cs:__imp__o__errno
0x180008290  mov     dword ptr [rax], 16h
0x180008296  call    _invalid_parameter_noinfo
0x18000829b  mov     rbx, rsi
0x18000829e  movzx   ecx, word ptr [rdi+8]
0x1800082a2  add     rcx, rbx
0x1800082a5  cmp     rcx, rbp
0x1800082a8  jbe     short loc_1800082AE
0x1800082aa  xor     al, al
0x1800082ac  jmp     short loc_1800082B7
0x1800082ae  mov     [rdi+18h], rbx
0x1800082b2  mov     al, 1
0x1800082b4  mov     [r14], rcx
0x1800082b7  add     rsp, 28h
0x1800082bb  pop     r15
0x1800082bd  pop     r14
0x1800082bf  pop     rdi
0x1800082c0  pop     rsi
0x1800082c1  pop     rbp
0x1800082c2  pop     rbx
0x1800082c3  retn
```
