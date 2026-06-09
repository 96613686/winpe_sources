# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x18000fb6c`
- end: `0x18000fc55`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d7c0`
- `0x18000ed5c`
- `0x18000f208`
- `0x1800101d8`
- `0x180011294`

## callees

- `0x18000fb6c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000fbbb`
- `msvcrt!memcpy_s` at `0x18000fbf0`
- `msvcrt!memcpy_s` at `0x18000fc1b`
- `msvcrt!memcpy_s` at `0x18000fbbb`
- `msvcrt!memcpy_s` at `0x18000fbf0`
- `msvcrt!memcpy_s` at `0x18000fc1b`

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
0x18000fb6c  mov     rax, rsp
0x18000fb6f  mov     [rax+10h], rbx
0x18000fb73  mov     [rax+18h], rbp
0x18000fb77  push    rsi
0x18000fb78  push    rdi
0x18000fb79  push    r12
0x18000fb7b  push    r14
0x18000fb7d  push    r15
0x18000fb7f  sub     rsp, 20h
0x18000fb83  xor     r15d, r15d
0x18000fb86  mov     rsi, r8
0x18000fb89  cmp     byte ptr [rcx+2], 1
0x18000fb8d  mov     r12, rdx
0x18000fb90  mov     r8, [rdx]; Source
0x18000fb93  mov     rdi, rcx
0x18000fb96  jnz     short loc_18000FBCB
0x18000fb98  lea     rbx, [r8+2]
0x18000fb9c  cmp     rbx, rsi
0x18000fb9f  ja      loc_18000FC30
0x18000fba5  lea     ebp, [r15+2]
0x18000fba9  mov     [rcx+10h], r8
0x18000fbad  mov     r9d, ebp; SourceSize
0x18000fbb0  mov     [rax+8], r15w
0x18000fbb5  mov     edx, ebp; DestinationSize
0x18000fbb7  lea     rcx, [rax+8]; Destination
0x18000fbbb  call    cs:__imp_memcpy_s
0x18000fbc1  movzx   eax, [rsp+48h+arg_0]
0x18000fbc6  mov     [rdi+4], eax
0x18000fbc9  jmp     short loc_18000FBF6
0x18000fbcb  mov     ebp, 2
0x18000fbd0  mov     rbx, r8
0x18000fbd3  cmp     [rcx+2], bpl
0x18000fbd7  jnz     short loc_18000FBF6
0x18000fbd9  lea     rbx, [r8+4]
0x18000fbdd  cmp     rbx, rsi
0x18000fbe0  ja      short loc_18000FC30
0x18000fbe2  lea     edx, [rbp+2]; DestinationSize
0x18000fbe5  mov     [rcx+10h], r8
0x18000fbe9  mov     r9d, edx; SourceSize
0x18000fbec  add     rcx, 4; Destination
0x18000fbf0  call    cs:__imp_memcpy_s
0x18000fbf6  movzx   eax, word ptr [rdi]
0x18000fbf9  lea     r14, [rdi+8]
0x18000fbfd  mov     [r14], ax
0x18000fc01  test    ax, ax
0x18000fc04  jnz     short loc_18000FC24
0x18000fc06  lea     r15, [rbx+2]
0x18000fc0a  cmp     r15, rsi
0x18000fc0d  ja      short loc_18000FC30
0x18000fc0f  mov     r9, rbp; SourceSize
0x18000fc12  mov     r8, rbx; Source
0x18000fc15  mov     rdx, rbp; DestinationSize
0x18000fc18  mov     rcx, r14; Destination
0x18000fc1b  call    cs:__imp_memcpy_s
0x18000fc21  mov     rbx, r15
0x18000fc24  movzx   ecx, word ptr [r14]
0x18000fc28  add     rcx, rbx
0x18000fc2b  cmp     rcx, rsi
0x18000fc2e  jbe     short loc_18000FC34
0x18000fc30  xor     al, al
0x18000fc32  jmp     short loc_18000FC3E
0x18000fc34  mov     [rdi+18h], rbx
0x18000fc38  mov     al, 1
0x18000fc3a  mov     [r12], rcx
0x18000fc3e  mov     rbx, [rsp+48h+arg_8]
0x18000fc43  mov     rbp, [rsp+48h+arg_10]
0x18000fc48  add     rsp, 20h
0x18000fc4c  pop     r15
0x18000fc4e  pop     r14
0x18000fc50  pop     r12
0x18000fc52  pop     rdi
0x18000fc53  pop     rsi
0x18000fc54  retn
```
