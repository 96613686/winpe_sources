# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x180037ddc`
- end: `0x180037ec3`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `231`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180033dd8`
- `0x1800367bc`
- `0x180037360`
- `0x1800377a0`
- `0x180038be8`

## callees

- `0x18002a804`
- `0x180037ddc`

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
0x180037ddc  mov     rax, rsp
0x180037ddf  mov     [rax+10h], rbx
0x180037de3  mov     [rax+18h], rbp
0x180037de7  push    rsi
0x180037de8  push    rdi
0x180037de9  push    r12
0x180037deb  push    r14
0x180037ded  push    r15
0x180037def  sub     rsp, 20h
0x180037df3  xor     r15d, r15d
0x180037df6  mov     rsi, r8
0x180037df9  cmp     byte ptr [rcx+2], 1
0x180037dfd  mov     r12, rdx
0x180037e00  mov     r8, [rdx]; Source
0x180037e03  mov     rdi, rcx
0x180037e06  jnz     short loc_180037E3A
0x180037e08  lea     rbx, [r8+2]
0x180037e0c  cmp     rbx, rsi
0x180037e0f  ja      loc_180037E9D
0x180037e15  lea     ebp, [r15+2]
0x180037e19  mov     [rcx+10h], r8
0x180037e1d  mov     r9d, ebp; SourceSize
0x180037e20  mov     [rax+8], r15w
0x180037e25  mov     edx, ebp; DestinationSize
0x180037e27  lea     rcx, [rax+8]; Destination
0x180037e2b  call    memcpy_s
0x180037e30  movzx   eax, [rsp+48h+arg_0]
0x180037e35  mov     [rdi+4], eax
0x180037e38  jmp     short loc_180037E64
0x180037e3a  mov     ebp, 2
0x180037e3f  mov     rbx, r8
0x180037e42  cmp     [rcx+2], bpl
0x180037e46  jnz     short loc_180037E64
0x180037e48  lea     rbx, [r8+4]
0x180037e4c  cmp     rbx, rsi
0x180037e4f  ja      short loc_180037E9D
0x180037e51  lea     edx, [rbp+2]; DestinationSize
0x180037e54  mov     [rcx+10h], r8
0x180037e58  mov     r9d, edx; SourceSize
0x180037e5b  add     rcx, 4; Destination
0x180037e5f  call    memcpy_s
0x180037e64  movzx   eax, word ptr [rdi]
0x180037e67  lea     r14, [rdi+8]
0x180037e6b  mov     [r14], ax
0x180037e6f  test    ax, ax
0x180037e72  jnz     short loc_180037E91
0x180037e74  lea     r15, [rbx+2]
0x180037e78  cmp     r15, rsi
0x180037e7b  ja      short loc_180037E9D
0x180037e7d  mov     r9, rbp; SourceSize
0x180037e80  mov     r8, rbx; Source
0x180037e83  mov     rdx, rbp; DestinationSize
0x180037e86  mov     rcx, r14; Destination
0x180037e89  call    memcpy_s
0x180037e8e  mov     rbx, r15
0x180037e91  movzx   ecx, word ptr [r14]
0x180037e95  add     rcx, rbx
0x180037e98  cmp     rcx, rsi
0x180037e9b  jbe     short loc_180037EA1
0x180037e9d  xor     al, al
0x180037e9f  jmp     short loc_180037EAB
0x180037ea1  mov     [rdi+18h], rbx
0x180037ea5  mov     al, 1
0x180037ea7  mov     [r12], rcx
0x180037eab  mov     rbx, [rsp+48h+arg_8]
0x180037eb0  mov     rbp, [rsp+48h+arg_10]
0x180037eb5  add     rsp, 20h
0x180037eb9  pop     r15
0x180037ebb  pop     r14
0x180037ebd  pop     r12
0x180037ebf  pop     rdi
0x180037ec0  pop     rsi
0x180037ec1  retn
```
