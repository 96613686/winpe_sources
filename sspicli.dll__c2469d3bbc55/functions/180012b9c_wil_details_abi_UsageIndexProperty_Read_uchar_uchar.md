# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x180012b9c`
- end: `0x180012c85`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180012620`
- `0x180012784`
- `0x18001297c`
- `0x180012a64`
- `0x180016a3c`

## callees

- `0x180012b9c`

## import_xrefs

- `api-ms-win-core-crt-l1-1-0!memcpy_s` at `0x180012beb`
- `api-ms-win-core-crt-l1-1-0!memcpy_s` at `0x180012c20`
- `api-ms-win-core-crt-l1-1-0!memcpy_s` at `0x180012c4b`
- `api-ms-win-core-crt-l1-1-0!memcpy_s` at `0x180012beb`
- `api-ms-win-core-crt-l1-1-0!memcpy_s` at `0x180012c20`
- `api-ms-win-core-crt-l1-1-0!memcpy_s` at `0x180012c4b`

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
0x180012b9c  mov     rax, rsp
0x180012b9f  mov     [rax+10h], rbx
0x180012ba3  mov     [rax+18h], rbp
0x180012ba7  push    rsi
0x180012ba8  push    rdi
0x180012ba9  push    r12
0x180012bab  push    r14
0x180012bad  push    r15
0x180012baf  sub     rsp, 20h
0x180012bb3  xor     r15d, r15d
0x180012bb6  mov     rsi, r8
0x180012bb9  cmp     byte ptr [rcx+2], 1
0x180012bbd  mov     r12, rdx
0x180012bc0  mov     r8, [rdx]; Source
0x180012bc3  mov     rdi, rcx
0x180012bc6  jnz     short loc_180012BFB
0x180012bc8  lea     rbx, [r8+2]
0x180012bcc  cmp     rbx, rsi
0x180012bcf  ja      loc_180012C60
0x180012bd5  lea     ebp, [r15+2]
0x180012bd9  mov     [rcx+10h], r8
0x180012bdd  mov     r9d, ebp; SourceSize
0x180012be0  mov     [rax+8], r15w
0x180012be5  mov     edx, ebp; DestinationSize
0x180012be7  lea     rcx, [rax+8]; Destination
0x180012beb  call    cs:__imp_memcpy_s
0x180012bf1  movzx   eax, [rsp+48h+arg_0]
0x180012bf6  mov     [rdi+4], eax
0x180012bf9  jmp     short loc_180012C26
0x180012bfb  mov     ebp, 2
0x180012c00  mov     rbx, r8
0x180012c03  cmp     [rcx+2], bpl
0x180012c07  jnz     short loc_180012C26
0x180012c09  lea     rbx, [r8+4]
0x180012c0d  cmp     rbx, rsi
0x180012c10  ja      short loc_180012C60
0x180012c12  lea     edx, [rbp+2]; DestinationSize
0x180012c15  mov     [rcx+10h], r8
0x180012c19  mov     r9d, edx; SourceSize
0x180012c1c  add     rcx, 4; Destination
0x180012c20  call    cs:__imp_memcpy_s
0x180012c26  movzx   eax, word ptr [rdi]
0x180012c29  lea     r14, [rdi+8]
0x180012c2d  mov     [r14], ax
0x180012c31  test    ax, ax
0x180012c34  jnz     short loc_180012C54
0x180012c36  lea     r15, [rbx+2]
0x180012c3a  cmp     r15, rsi
0x180012c3d  ja      short loc_180012C60
0x180012c3f  mov     r9, rbp; SourceSize
0x180012c42  mov     r8, rbx; Source
0x180012c45  mov     rdx, rbp; DestinationSize
0x180012c48  mov     rcx, r14; Destination
0x180012c4b  call    cs:__imp_memcpy_s
0x180012c51  mov     rbx, r15
0x180012c54  movzx   ecx, word ptr [r14]
0x180012c58  add     rcx, rbx
0x180012c5b  cmp     rcx, rsi
0x180012c5e  jbe     short loc_180012C64
0x180012c60  xor     al, al
0x180012c62  jmp     short loc_180012C6E
0x180012c64  mov     [rdi+18h], rbx
0x180012c68  mov     al, 1
0x180012c6a  mov     [r12], rcx
0x180012c6e  mov     rbx, [rsp+48h+arg_8]
0x180012c73  mov     rbp, [rsp+48h+arg_10]
0x180012c78  add     rsp, 20h
0x180012c7c  pop     r15
0x180012c7e  pop     r14
0x180012c80  pop     r12
0x180012c82  pop     rdi
0x180012c83  pop     rsi
0x180012c84  retn
```
