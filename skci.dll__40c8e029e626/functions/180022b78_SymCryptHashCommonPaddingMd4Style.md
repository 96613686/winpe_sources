# SymCryptHashCommonPaddingMd4Style

- ea: `0x180022b78`
- end: `0x180022c23`
- name: `SymCryptHashCommonPaddingMd4Style`
- size: `171`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800229e0`

## callees

- `0x180009780`
- `0x180022080`
- `0x180022b78`
- `0x180033980`

## pseudocode

```c
__int64 __fastcall SymCryptHashCommonPaddingMd4Style(__int64 a1, unsigned int *a2)
{
  __int64 v2; // rax
  unsigned __int64 v4; // rax
  __int64 v6; // [rsp+20h] [rbp-38h] BYREF

  v2 = *a2;
  v6 = 0;
  *((_BYTE *)a2 + v2 + 32) = 0x80;
  v4 = v2 + 1;
  if ( v4 > 0x38 )
  {
    SymCryptWipeAsm((char *)a2 + v4 + 32, 64 - v4);
    ((void (__fastcall *)(unsigned int *, unsigned int *, __int64, __int64 *))SymCryptMd5AppendBlocks)(
      a2 + 24,
      a2 + 8,
      64,
      &v6);
    v4 = 0;
  }
  SymCryptWipeAsm((char *)a2 + v4 + 32, 64 - v4);
  *((_QWORD *)a2 + 11) = 8LL * *((_QWORD *)a2 + 2);
  return ((__int64 (__fastcall *)(unsigned int *, unsigned int *, __int64, __int64 *))SymCryptMd5AppendBlocks)(
           a2 + 24,
           a2 + 8,
           64,
           &v6);
}

```

## disassembly

```asm
0x180022b78  push    rbx
0x180022b7a  push    rbp
0x180022b7b  push    rsi
0x180022b7c  push    rdi
0x180022b7d  sub     rsp, 38h
0x180022b81  mov     rax, cs:__security_cookie
0x180022b88  xor     rax, rsp
0x180022b8b  mov     [rsp+58h+var_30], rax
0x180022b90  mov     eax, [rdx]
0x180022b92  mov     rbx, rdx
0x180022b95  mov     [rsp+58h+var_38], 0
0x180022b9e  mov     ebp, 40h ; '@'
0x180022ba3  mov     byte ptr [rax+rdx+20h], 80h
0x180022ba8  inc     rax
0x180022bab  cmp     rax, 38h ; '8'
0x180022baf  jbe     short loc_180022BD9
0x180022bb1  mov     edx, ebp
0x180022bb3  lea     rcx, [rbx+20h]
0x180022bb7  sub     rdx, rax
0x180022bba  add     rcx, rax
0x180022bbd  call    SymCryptWipeAsm
0x180022bc2  lea     r9, [rsp+58h+var_38]
0x180022bc7  mov     r8d, ebp
0x180022bca  lea     rdx, [rbx+20h]
0x180022bce  lea     rcx, [rbx+60h]
0x180022bd2  call    SymCryptMd5AppendBlocks
0x180022bd7  xor     eax, eax
0x180022bd9  mov     rdx, rbp
0x180022bdc  lea     rcx, [rbx+20h]
0x180022be0  sub     rdx, rax
0x180022be3  add     rcx, rax
0x180022be6  call    SymCryptWipeAsm
0x180022beb  mov     rax, [rbx+10h]
0x180022bef  lea     r9, [rsp+58h+var_38]
0x180022bf4  shl     rax, 3
0x180022bf8  lea     rdx, [rbx+20h]
0x180022bfc  mov     r8, rbp
0x180022bff  mov     [rbx+58h], rax
0x180022c03  lea     rcx, [rbx+60h]
0x180022c07  call    SymCryptMd5AppendBlocks
0x180022c0c  mov     rcx, [rsp+58h+var_30]
0x180022c11  xor     rcx, rsp; StackCookie
0x180022c14  call    __security_check_cookie
0x180022c19  add     rsp, 38h
0x180022c1d  pop     rdi
0x180022c1e  pop     rsi
0x180022c1f  pop     rbp
0x180022c20  pop     rbx
0x180022c21  retn
```
