# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x180011a3c`
- end: `0x180011b22`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `230`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f800`
- `0x1800118b8`
- `0x180011978`
- `0x180015464`

## callees

- `0x18000f770`
- `0x180011a3c`

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
0x180011a3c  mov     rax, rsp
0x180011a3f  mov     [rax+10h], rbx
0x180011a43  mov     [rax+18h], rbp
0x180011a47  push    rsi
0x180011a48  push    rdi
0x180011a49  push    r12
0x180011a4b  push    r14
0x180011a4d  push    r15
0x180011a4f  sub     rsp, 20h
0x180011a53  xor     r15d, r15d
0x180011a56  mov     rsi, r8
0x180011a59  cmp     byte ptr [rcx+2], 1
0x180011a5d  mov     r12, rdx
0x180011a60  mov     r8, [rdx]; Source
0x180011a63  mov     rdi, rcx
0x180011a66  jnz     short loc_180011A9A
0x180011a68  lea     rbx, [r8+2]
0x180011a6c  cmp     rbx, rsi
0x180011a6f  ja      loc_180011AFD
0x180011a75  lea     ebp, [r15+2]
0x180011a79  mov     [rcx+10h], r8
0x180011a7d  mov     r9d, ebp; SourceSize
0x180011a80  mov     [rax+8], r15w
0x180011a85  mov     edx, ebp; DestinationSize
0x180011a87  lea     rcx, [rax+8]; Destination
0x180011a8b  call    memcpy_s
0x180011a90  movzx   eax, [rsp+48h+arg_0]
0x180011a95  mov     [rdi+4], eax
0x180011a98  jmp     short loc_180011AC4
0x180011a9a  mov     ebp, 2
0x180011a9f  mov     rbx, r8
0x180011aa2  cmp     [rcx+2], bpl
0x180011aa6  jnz     short loc_180011AC4
0x180011aa8  lea     rbx, [r8+4]
0x180011aac  cmp     rbx, rsi
0x180011aaf  ja      short loc_180011AFD
0x180011ab1  lea     edx, [rbp+2]; DestinationSize
0x180011ab4  mov     [rcx+10h], r8
0x180011ab8  mov     r9d, edx; SourceSize
0x180011abb  add     rcx, 4; Destination
0x180011abf  call    memcpy_s
0x180011ac4  movzx   eax, word ptr [rdi]
0x180011ac7  lea     r14, [rdi+8]
0x180011acb  mov     [r14], ax
0x180011acf  test    ax, ax
0x180011ad2  jnz     short loc_180011AF1
0x180011ad4  lea     r15, [rbx+2]
0x180011ad8  cmp     r15, rsi
0x180011adb  ja      short loc_180011AFD
0x180011add  mov     r9, rbp; SourceSize
0x180011ae0  mov     r8, rbx; Source
0x180011ae3  mov     rdx, rbp; DestinationSize
0x180011ae6  mov     rcx, r14; Destination
0x180011ae9  call    memcpy_s
0x180011aee  mov     rbx, r15
0x180011af1  movzx   ecx, word ptr [r14]
0x180011af5  add     rcx, rbx
0x180011af8  cmp     rcx, rsi
0x180011afb  jbe     short loc_180011B01
0x180011afd  xor     al, al
0x180011aff  jmp     short loc_180011B0B
0x180011b01  mov     [rdi+18h], rbx
0x180011b05  mov     al, 1
0x180011b07  mov     [r12], rcx
0x180011b0b  mov     rbx, [rsp+48h+arg_8]
0x180011b10  mov     rbp, [rsp+48h+arg_10]
0x180011b15  add     rsp, 20h
0x180011b19  pop     r15
0x180011b1b  pop     r14
0x180011b1d  pop     r12
0x180011b1f  pop     rdi
0x180011b20  pop     rsi
0x180011b21  retn
```
