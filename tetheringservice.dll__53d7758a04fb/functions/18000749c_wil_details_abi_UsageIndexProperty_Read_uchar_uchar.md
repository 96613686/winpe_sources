# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x18000749c`
- end: `0x180007594`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `248`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180005ec4`
- `0x180007d34`
- `0x180008108`

## callees

- `0x180002ffa`
- `0x18000749c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800074d9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000751b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000755a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800074d9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000751b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000755a`

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
      *(_DWORD *)_o__errno(this, a2) = 22;
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
    *(_DWORD *)_o__errno(this, a2) = 22;
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
    *(_DWORD *)_o__errno(this, a2) = 22;
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
0x18000749c  push    rbx
0x18000749e  push    rbp
0x18000749f  push    rsi
0x1800074a0  push    rdi
0x1800074a1  push    r14
0x1800074a3  push    r15
0x1800074a5  sub     rsp, 28h
0x1800074a9  mov     rax, [rdx]
0x1800074ac  xor     r15d, r15d
0x1800074af  cmp     byte ptr [rcx+2], 1
0x1800074b3  mov     rbp, r8
0x1800074b6  mov     r14, rdx
0x1800074b9  mov     rdi, rcx
0x1800074bc  jnz     short loc_1800074F5
0x1800074be  lea     rbx, [rax+2]
0x1800074c2  cmp     rbx, r8
0x1800074c5  ja      loc_18000757A
0x1800074cb  mov     [rcx+10h], rax
0x1800074cf  test    rax, rax
0x1800074d2  jz      short loc_1800074D9
0x1800074d4  movzx   ecx, word ptr [rax]
0x1800074d7  jmp     short loc_1800074ED
0x1800074d9  call    cs:__imp__o__errno
0x1800074df  mov     dword ptr [rax], 16h
0x1800074e5  call    _invalid_parameter_noinfo
0x1800074ea  mov     ecx, r15d
0x1800074ed  movzx   eax, cx
0x1800074f0  mov     [rdi+4], eax
0x1800074f3  jmp     short loc_180007531
0x1800074f5  cmp     byte ptr [rcx+2], 2
0x1800074f9  jnz     short loc_18000752E
0x1800074fb  lea     rbx, [rax+4]
0x1800074ff  cmp     rbx, rbp
0x180007502  ja      short loc_18000757A
0x180007504  mov     [rcx+10h], rax
0x180007508  add     rcx, 4
0x18000750c  jz      short loc_18000751B
0x18000750e  test    rax, rax
0x180007511  jz      short loc_180007519
0x180007513  mov     eax, [rax]
0x180007515  mov     [rcx], eax
0x180007517  jmp     short loc_180007531
0x180007519  mov     [rcx], eax
0x18000751b  call    cs:__imp__o__errno
0x180007521  mov     dword ptr [rax], 16h
0x180007527  call    _invalid_parameter_noinfo
0x18000752c  jmp     short loc_180007531
0x18000752e  mov     rbx, rax
0x180007531  movzx   eax, word ptr [rdi]
0x180007534  mov     [rdi+8], ax
0x180007538  test    ax, ax
0x18000753b  jnz     short loc_18000756E
0x18000753d  lea     rsi, [rbx+2]
0x180007541  cmp     rsi, rbp
0x180007544  ja      short loc_18000757A
0x180007546  test    rbx, rbx
0x180007549  jz      short loc_180007554
0x18000754b  movzx   eax, word ptr [rbx]
0x18000754e  mov     [rdi+8], ax
0x180007552  jmp     short loc_18000756B
0x180007554  xor     eax, eax
0x180007556  mov     [rdi+8], ax
0x18000755a  call    cs:__imp__o__errno
0x180007560  mov     dword ptr [rax], 16h
0x180007566  call    _invalid_parameter_noinfo
0x18000756b  mov     rbx, rsi
0x18000756e  movzx   ecx, word ptr [rdi+8]
0x180007572  add     rcx, rbx
0x180007575  cmp     rcx, rbp
0x180007578  jbe     short loc_18000757E
0x18000757a  xor     al, al
0x18000757c  jmp     short loc_180007587
0x18000757e  mov     [rdi+18h], rbx
0x180007582  mov     al, 1
0x180007584  mov     [r14], rcx
0x180007587  add     rsp, 28h
0x18000758b  pop     r15
0x18000758d  pop     r14
0x18000758f  pop     rdi
0x180007590  pop     rsi
0x180007591  pop     rbp
0x180007592  pop     rbx
0x180007593  retn
```
