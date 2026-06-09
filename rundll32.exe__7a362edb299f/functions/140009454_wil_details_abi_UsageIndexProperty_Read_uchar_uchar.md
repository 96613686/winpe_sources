# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x140009454`
- end: `0x14000953a`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `230`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140008edc`
- `0x140009a10`
- `0x140009d94`

## callees

- `0x14000220c`
- `0x140009454`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Read(
        wil::details_abi::UsageIndexProperty *this,
        unsigned __int8 **a2,
        unsigned __int8 *a3)
{
  char *v5; // r8
  char *v7; // rbx
  __int16 v8; // ax
  unsigned __int8 *v9; // rcx
  bool result; // al
  unsigned __int16 v11; // [rsp+50h] [rbp+8h] BYREF

  v5 = (char *)*a2;
  if ( *((_BYTE *)this + 2) == 1 )
  {
    v7 = v5 + 2;
    if ( v5 + 2 > (char *)a3 )
      return 0;
    *((_QWORD *)this + 2) = v5;
    v11 = 0;
    memcpy_s(&v11, 2u, v5, 2u);
    *((_DWORD *)this + 1) = v11;
  }
  else
  {
    v7 = (char *)*a2;
    if ( *((_BYTE *)this + 2) == 2 )
    {
      v7 = v5 + 4;
      if ( v5 + 4 > (char *)a3 )
        return 0;
      *((_QWORD *)this + 2) = v5;
      memcpy_s((char *)this + 4, 4u, v5, 4u);
    }
  }
  v8 = *(_WORD *)this;
  *((_WORD *)this + 4) = *(_WORD *)this;
  if ( v8 )
    goto LABEL_10;
  if ( v7 + 2 > (char *)a3 )
    return 0;
  memcpy_s((char *)this + 8, 2u, v7, 2u);
  v7 += 2;
LABEL_10:
  v9 = (unsigned __int8 *)&v7[*((unsigned __int16 *)this + 4)];
  if ( v9 > a3 )
    return 0;
  *((_QWORD *)this + 3) = v7;
  result = 1;
  *a2 = v9;
  return result;
}

```

## disassembly

```asm
0x140009454  mov     rax, rsp
0x140009457  mov     [rax+10h], rbx
0x14000945b  mov     [rax+18h], rbp
0x14000945f  push    rsi
0x140009460  push    rdi
0x140009461  push    r12
0x140009463  push    r14
0x140009465  push    r15
0x140009467  sub     rsp, 20h
0x14000946b  xor     r15d, r15d
0x14000946e  mov     rsi, r8
0x140009471  cmp     byte ptr [rcx+2], 1
0x140009475  mov     r12, rdx
0x140009478  mov     r8, [rdx]; Source
0x14000947b  mov     rdi, rcx
0x14000947e  jnz     short loc_1400094B2
0x140009480  lea     rbx, [r8+2]
0x140009484  cmp     rbx, rsi
0x140009487  ja      loc_140009515
0x14000948d  lea     ebp, [r15+2]
0x140009491  mov     [rcx+10h], r8
0x140009495  mov     r9d, ebp; SourceSize
0x140009498  mov     [rax+8], r15w
0x14000949d  mov     edx, ebp; DestinationSize
0x14000949f  lea     rcx, [rax+8]; Destination
0x1400094a3  call    memcpy_s
0x1400094a8  movzx   eax, [rsp+48h+arg_0]
0x1400094ad  mov     [rdi+4], eax
0x1400094b0  jmp     short loc_1400094DC
0x1400094b2  mov     ebp, 2
0x1400094b7  mov     rbx, r8
0x1400094ba  cmp     [rcx+2], bpl
0x1400094be  jnz     short loc_1400094DC
0x1400094c0  lea     rbx, [r8+4]
0x1400094c4  cmp     rbx, rsi
0x1400094c7  ja      short loc_140009515
0x1400094c9  lea     edx, [rbp+2]; DestinationSize
0x1400094cc  mov     [rcx+10h], r8
0x1400094d0  mov     r9d, edx; SourceSize
0x1400094d3  add     rcx, 4; Destination
0x1400094d7  call    memcpy_s
0x1400094dc  movzx   eax, word ptr [rdi]
0x1400094df  lea     r14, [rdi+8]
0x1400094e3  mov     [r14], ax
0x1400094e7  test    ax, ax
0x1400094ea  jnz     short loc_140009509
0x1400094ec  lea     r15, [rbx+2]
0x1400094f0  cmp     r15, rsi
0x1400094f3  ja      short loc_140009515
0x1400094f5  mov     r9, rbp; SourceSize
0x1400094f8  mov     r8, rbx; Source
0x1400094fb  mov     rdx, rbp; DestinationSize
0x1400094fe  mov     rcx, r14; Destination
0x140009501  call    memcpy_s
0x140009506  mov     rbx, r15
0x140009509  movzx   ecx, word ptr [r14]
0x14000950d  add     rcx, rbx
0x140009510  cmp     rcx, rsi
0x140009513  jbe     short loc_140009519
0x140009515  xor     al, al
0x140009517  jmp     short loc_140009523
0x140009519  mov     [rdi+18h], rbx
0x14000951d  mov     al, 1
0x14000951f  mov     [r12], rcx
0x140009523  mov     rbx, [rsp+48h+arg_8]
0x140009528  mov     rbp, [rsp+48h+arg_10]
0x14000952d  add     rsp, 20h
0x140009531  pop     r15
0x140009533  pop     r14
0x140009535  pop     r12
0x140009537  pop     rdi
0x140009538  pop     rsi
0x140009539  retn
```
