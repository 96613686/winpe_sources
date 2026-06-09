# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x18000992c`
- end: `0x180009a12`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `230`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180003af0`
- `0x180007c64`
- `0x180008e38`
- `0x1800092bc`
- `0x18000ad50`

## callees

- `0x18000992c`
- `0x18000f1d8`

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
0x18000992c  mov     rax, rsp
0x18000992f  mov     [rax+10h], rbx
0x180009933  mov     [rax+18h], rbp
0x180009937  push    rsi
0x180009938  push    rdi
0x180009939  push    r12
0x18000993b  push    r14
0x18000993d  push    r15
0x18000993f  sub     rsp, 20h
0x180009943  xor     r15d, r15d
0x180009946  mov     rsi, r8
0x180009949  cmp     byte ptr [rcx+2], 1
0x18000994d  mov     r12, rdx
0x180009950  mov     r8, [rdx]; Source
0x180009953  mov     rdi, rcx
0x180009956  jnz     short loc_18000998A
0x180009958  lea     rbx, [r8+2]
0x18000995c  cmp     rbx, rsi
0x18000995f  ja      loc_1800099ED
0x180009965  lea     ebp, [r15+2]
0x180009969  mov     [rcx+10h], r8
0x18000996d  mov     r9d, ebp; SourceSize
0x180009970  mov     [rax+8], r15w
0x180009975  mov     edx, ebp; DestinationSize
0x180009977  lea     rcx, [rax+8]; Destination
0x18000997b  call    memcpy_s
0x180009980  movzx   eax, [rsp+48h+arg_0]
0x180009985  mov     [rdi+4], eax
0x180009988  jmp     short loc_1800099B4
0x18000998a  mov     ebp, 2
0x18000998f  mov     rbx, r8
0x180009992  cmp     [rcx+2], bpl
0x180009996  jnz     short loc_1800099B4
0x180009998  lea     rbx, [r8+4]
0x18000999c  cmp     rbx, rsi
0x18000999f  ja      short loc_1800099ED
0x1800099a1  lea     edx, [rbp+2]; DestinationSize
0x1800099a4  mov     [rcx+10h], r8
0x1800099a8  mov     r9d, edx; SourceSize
0x1800099ab  add     rcx, 4; Destination
0x1800099af  call    memcpy_s
0x1800099b4  movzx   eax, word ptr [rdi]
0x1800099b7  lea     r14, [rdi+8]
0x1800099bb  mov     [r14], ax
0x1800099bf  test    ax, ax
0x1800099c2  jnz     short loc_1800099E1
0x1800099c4  lea     r15, [rbx+2]
0x1800099c8  cmp     r15, rsi
0x1800099cb  ja      short loc_1800099ED
0x1800099cd  mov     r9, rbp; SourceSize
0x1800099d0  mov     r8, rbx; Source
0x1800099d3  mov     rdx, rbp; DestinationSize
0x1800099d6  mov     rcx, r14; Destination
0x1800099d9  call    memcpy_s
0x1800099de  mov     rbx, r15
0x1800099e1  movzx   ecx, word ptr [r14]
0x1800099e5  add     rcx, rbx
0x1800099e8  cmp     rcx, rsi
0x1800099eb  jbe     short loc_1800099F1
0x1800099ed  xor     al, al
0x1800099ef  jmp     short loc_1800099FB
0x1800099f1  mov     [rdi+18h], rbx
0x1800099f5  mov     al, 1
0x1800099f7  mov     [r12], rcx
0x1800099fb  mov     rbx, [rsp+48h+arg_8]
0x180009a00  mov     rbp, [rsp+48h+arg_10]
0x180009a05  add     rsp, 20h
0x180009a09  pop     r15
0x180009a0b  pop     r14
0x180009a0d  pop     r12
0x180009a0f  pop     rdi
0x180009a10  pop     rsi
0x180009a11  retn
```
