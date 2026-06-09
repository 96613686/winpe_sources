# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x18000e8e0`
- end: `0x18000e9c9`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b304`
- `0x18000f1ac`
- `0x18000f534`

## callees

- `0x18000e8e0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000e92f`
- `msvcrt!memcpy_s` at `0x18000e964`
- `msvcrt!memcpy_s` at `0x18000e98f`
- `msvcrt!memcpy_s` at `0x18000e92f`
- `msvcrt!memcpy_s` at `0x18000e964`
- `msvcrt!memcpy_s` at `0x18000e98f`

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
0x18000e8e0  mov     rax, rsp
0x18000e8e3  mov     [rax+10h], rbx
0x18000e8e7  mov     [rax+18h], rbp
0x18000e8eb  push    rsi
0x18000e8ec  push    rdi
0x18000e8ed  push    r12
0x18000e8ef  push    r14
0x18000e8f1  push    r15
0x18000e8f3  sub     rsp, 20h
0x18000e8f7  xor     r15d, r15d
0x18000e8fa  mov     rsi, r8
0x18000e8fd  cmp     byte ptr [rcx+2], 1
0x18000e901  mov     r12, rdx
0x18000e904  mov     r8, [rdx]; Source
0x18000e907  mov     rdi, rcx
0x18000e90a  jnz     short loc_18000E93F
0x18000e90c  lea     rbx, [r8+2]
0x18000e910  cmp     rbx, rsi
0x18000e913  ja      loc_18000E9A4
0x18000e919  lea     ebp, [r15+2]
0x18000e91d  mov     [rcx+10h], r8
0x18000e921  mov     r9d, ebp; SourceSize
0x18000e924  mov     [rax+8], r15w
0x18000e929  mov     edx, ebp; DestinationSize
0x18000e92b  lea     rcx, [rax+8]; Destination
0x18000e92f  call    cs:__imp_memcpy_s
0x18000e935  movzx   eax, [rsp+48h+arg_0]
0x18000e93a  mov     [rdi+4], eax
0x18000e93d  jmp     short loc_18000E96A
0x18000e93f  mov     ebp, 2
0x18000e944  mov     rbx, r8
0x18000e947  cmp     [rcx+2], bpl
0x18000e94b  jnz     short loc_18000E96A
0x18000e94d  lea     rbx, [r8+4]
0x18000e951  cmp     rbx, rsi
0x18000e954  ja      short loc_18000E9A4
0x18000e956  lea     edx, [rbp+2]; DestinationSize
0x18000e959  mov     [rcx+10h], r8
0x18000e95d  mov     r9d, edx; SourceSize
0x18000e960  add     rcx, 4; Destination
0x18000e964  call    cs:__imp_memcpy_s
0x18000e96a  movzx   eax, word ptr [rdi]
0x18000e96d  lea     r14, [rdi+8]
0x18000e971  mov     [r14], ax
0x18000e975  test    ax, ax
0x18000e978  jnz     short loc_18000E998
0x18000e97a  lea     r15, [rbx+2]
0x18000e97e  cmp     r15, rsi
0x18000e981  ja      short loc_18000E9A4
0x18000e983  mov     r9, rbp; SourceSize
0x18000e986  mov     r8, rbx; Source
0x18000e989  mov     rdx, rbp; DestinationSize
0x18000e98c  mov     rcx, r14; Destination
0x18000e98f  call    cs:__imp_memcpy_s
0x18000e995  mov     rbx, r15
0x18000e998  movzx   ecx, word ptr [r14]
0x18000e99c  add     rcx, rbx
0x18000e99f  cmp     rcx, rsi
0x18000e9a2  jbe     short loc_18000E9A8
0x18000e9a4  xor     al, al
0x18000e9a6  jmp     short loc_18000E9B2
0x18000e9a8  mov     [rdi+18h], rbx
0x18000e9ac  mov     al, 1
0x18000e9ae  mov     [r12], rcx
0x18000e9b2  mov     rbx, [rsp+48h+arg_8]
0x18000e9b7  mov     rbp, [rsp+48h+arg_10]
0x18000e9bc  add     rsp, 20h
0x18000e9c0  pop     r15
0x18000e9c2  pop     r14
0x18000e9c4  pop     r12
0x18000e9c6  pop     rdi
0x18000e9c7  pop     rsi
0x18000e9c8  retn
```
