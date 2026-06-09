# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x180012aac`
- end: `0x180012b95`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18001138c`
- `0x1800130e0`
- `0x180013468`

## callees

- `0x180012aac`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180012afb`
- `msvcrt!memcpy_s` at `0x180012b30`
- `msvcrt!memcpy_s` at `0x180012b5b`
- `msvcrt!memcpy_s` at `0x180012afb`
- `msvcrt!memcpy_s` at `0x180012b30`
- `msvcrt!memcpy_s` at `0x180012b5b`

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
0x180012aac  mov     rax, rsp
0x180012aaf  mov     [rax+10h], rbx
0x180012ab3  mov     [rax+18h], rbp
0x180012ab7  push    rsi
0x180012ab8  push    rdi
0x180012ab9  push    r12
0x180012abb  push    r14
0x180012abd  push    r15
0x180012abf  sub     rsp, 20h
0x180012ac3  xor     r15d, r15d
0x180012ac6  mov     rsi, r8
0x180012ac9  cmp     byte ptr [rcx+2], 1
0x180012acd  mov     r12, rdx
0x180012ad0  mov     r8, [rdx]; Source
0x180012ad3  mov     rdi, rcx
0x180012ad6  jnz     short loc_180012B0B
0x180012ad8  lea     rbx, [r8+2]
0x180012adc  cmp     rbx, rsi
0x180012adf  ja      loc_180012B70
0x180012ae5  lea     ebp, [r15+2]
0x180012ae9  mov     [rcx+10h], r8
0x180012aed  mov     r9d, ebp; SourceSize
0x180012af0  mov     [rax+8], r15w
0x180012af5  mov     edx, ebp; DestinationSize
0x180012af7  lea     rcx, [rax+8]; Destination
0x180012afb  call    cs:__imp_memcpy_s
0x180012b01  movzx   eax, [rsp+48h+arg_0]
0x180012b06  mov     [rdi+4], eax
0x180012b09  jmp     short loc_180012B36
0x180012b0b  mov     ebp, 2
0x180012b10  mov     rbx, r8
0x180012b13  cmp     [rcx+2], bpl
0x180012b17  jnz     short loc_180012B36
0x180012b19  lea     rbx, [r8+4]
0x180012b1d  cmp     rbx, rsi
0x180012b20  ja      short loc_180012B70
0x180012b22  lea     edx, [rbp+2]; DestinationSize
0x180012b25  mov     [rcx+10h], r8
0x180012b29  mov     r9d, edx; SourceSize
0x180012b2c  add     rcx, 4; Destination
0x180012b30  call    cs:__imp_memcpy_s
0x180012b36  movzx   eax, word ptr [rdi]
0x180012b39  lea     r14, [rdi+8]
0x180012b3d  mov     [r14], ax
0x180012b41  test    ax, ax
0x180012b44  jnz     short loc_180012B64
0x180012b46  lea     r15, [rbx+2]
0x180012b4a  cmp     r15, rsi
0x180012b4d  ja      short loc_180012B70
0x180012b4f  mov     r9, rbp; SourceSize
0x180012b52  mov     r8, rbx; Source
0x180012b55  mov     rdx, rbp; DestinationSize
0x180012b58  mov     rcx, r14; Destination
0x180012b5b  call    cs:__imp_memcpy_s
0x180012b61  mov     rbx, r15
0x180012b64  movzx   ecx, word ptr [r14]
0x180012b68  add     rcx, rbx
0x180012b6b  cmp     rcx, rsi
0x180012b6e  jbe     short loc_180012B74
0x180012b70  xor     al, al
0x180012b72  jmp     short loc_180012B7E
0x180012b74  mov     [rdi+18h], rbx
0x180012b78  mov     al, 1
0x180012b7a  mov     [r12], rcx
0x180012b7e  mov     rbx, [rsp+48h+arg_8]
0x180012b83  mov     rbp, [rsp+48h+arg_10]
0x180012b88  add     rsp, 20h
0x180012b8c  pop     r15
0x180012b8e  pop     r14
0x180012b90  pop     r12
0x180012b92  pop     rdi
0x180012b93  pop     rsi
0x180012b94  retn
```
