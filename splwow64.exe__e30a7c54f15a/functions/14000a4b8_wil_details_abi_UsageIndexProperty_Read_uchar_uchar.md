# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x14000a4b8`
- end: `0x14000a5b0`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `248`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140009838`
- `0x14000ac84`
- `0x14000b058`

## callees

- `0x1400027fe`
- `0x14000a4b8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000a4f5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000a537`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000a576`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000a4f5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000a537`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000a576`

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
0x14000a4b8  push    rbx
0x14000a4ba  push    rbp
0x14000a4bb  push    rsi
0x14000a4bc  push    rdi
0x14000a4bd  push    r14
0x14000a4bf  push    r15
0x14000a4c1  sub     rsp, 28h
0x14000a4c5  mov     rax, [rdx]
0x14000a4c8  xor     r15d, r15d
0x14000a4cb  cmp     byte ptr [rcx+2], 1
0x14000a4cf  mov     rbp, r8
0x14000a4d2  mov     r14, rdx
0x14000a4d5  mov     rdi, rcx
0x14000a4d8  jnz     short loc_14000A511
0x14000a4da  lea     rbx, [rax+2]
0x14000a4de  cmp     rbx, r8
0x14000a4e1  ja      loc_14000A596
0x14000a4e7  mov     [rcx+10h], rax
0x14000a4eb  test    rax, rax
0x14000a4ee  jz      short loc_14000A4F5
0x14000a4f0  movzx   ecx, word ptr [rax]
0x14000a4f3  jmp     short loc_14000A509
0x14000a4f5  call    cs:__imp__o__errno
0x14000a4fb  mov     dword ptr [rax], 16h
0x14000a501  call    _invalid_parameter_noinfo
0x14000a506  mov     ecx, r15d
0x14000a509  movzx   eax, cx
0x14000a50c  mov     [rdi+4], eax
0x14000a50f  jmp     short loc_14000A54D
0x14000a511  cmp     byte ptr [rcx+2], 2
0x14000a515  jnz     short loc_14000A54A
0x14000a517  lea     rbx, [rax+4]
0x14000a51b  cmp     rbx, rbp
0x14000a51e  ja      short loc_14000A596
0x14000a520  mov     [rcx+10h], rax
0x14000a524  add     rcx, 4
0x14000a528  jz      short loc_14000A537
0x14000a52a  test    rax, rax
0x14000a52d  jz      short loc_14000A535
0x14000a52f  mov     eax, [rax]
0x14000a531  mov     [rcx], eax
0x14000a533  jmp     short loc_14000A54D
0x14000a535  mov     [rcx], eax
0x14000a537  call    cs:__imp__o__errno
0x14000a53d  mov     dword ptr [rax], 16h
0x14000a543  call    _invalid_parameter_noinfo
0x14000a548  jmp     short loc_14000A54D
0x14000a54a  mov     rbx, rax
0x14000a54d  movzx   eax, word ptr [rdi]
0x14000a550  mov     [rdi+8], ax
0x14000a554  test    ax, ax
0x14000a557  jnz     short loc_14000A58A
0x14000a559  lea     rsi, [rbx+2]
0x14000a55d  cmp     rsi, rbp
0x14000a560  ja      short loc_14000A596
0x14000a562  test    rbx, rbx
0x14000a565  jz      short loc_14000A570
0x14000a567  movzx   eax, word ptr [rbx]
0x14000a56a  mov     [rdi+8], ax
0x14000a56e  jmp     short loc_14000A587
0x14000a570  xor     eax, eax
0x14000a572  mov     [rdi+8], ax
0x14000a576  call    cs:__imp__o__errno
0x14000a57c  mov     dword ptr [rax], 16h
0x14000a582  call    _invalid_parameter_noinfo
0x14000a587  mov     rbx, rsi
0x14000a58a  movzx   ecx, word ptr [rdi+8]
0x14000a58e  add     rcx, rbx
0x14000a591  cmp     rcx, rbp
0x14000a594  jbe     short loc_14000A59A
0x14000a596  xor     al, al
0x14000a598  jmp     short loc_14000A5A3
0x14000a59a  mov     [rdi+18h], rbx
0x14000a59e  mov     al, 1
0x14000a5a0  mov     [r14], rcx
0x14000a5a3  add     rsp, 28h
0x14000a5a7  pop     r15
0x14000a5a9  pop     r14
0x14000a5ab  pop     rdi
0x14000a5ac  pop     rsi
0x14000a5ad  pop     rbp
0x14000a5ae  pop     rbx
0x14000a5af  retn
```
