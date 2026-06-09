# std::filesystem::path::path(std::filesystem::path const &)

- ea: `0x140006ebc`
- end: `0x140006f88`
- name: `??0path@filesystem@std@@QEAA@AEBV012@@Z`
- size: `204`
- prototype: `_QWORD(std::filesystem::path *__hidden this, const struct std::filesystem::path *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140006d08`

## callees

- `0x1400069b0`
- `0x140006ebc`
- `0x1400098e8`
- `0x140020b20`

## pseudocode

```c
std::filesystem::path *__fastcall std::filesystem::path::path(
        std::filesystem::path *this,
        const struct std::filesystem::path *a2)
{
  const struct std::filesystem::path *v2; // rsi
  unsigned __int64 v4; // rdi
  __int64 v5; // rax
  unsigned __int64 v6; // rcx
  void *v7; // rax
  std::filesystem::path *v9; // [rsp+20h] [rbp-18h] BYREF

  v9 = this;
  v2 = a2;
  *(_OWORD *)this = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  v4 = *((_QWORD *)a2 + 2);
  if ( *((_QWORD *)a2 + 3) > 7u )
    v2 = *(const struct std::filesystem::path **)a2;
  v5 = 0x7FFFFFFFFFFFFFFELL;
  if ( v4 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlen_string();
  if ( v4 > 7 )
  {
    v6 = v4 | 7;
    if ( (v4 | 7) <= 0x7FFFFFFFFFFFFFFELL )
    {
      v5 = v4 | 7;
      if ( v6 < 0xA )
        v5 = 10;
    }
    v9 = (std::filesystem::path *)v5;
    v7 = (void *)std::wstring::_Allocate_for_capacity<0>(v6, &v9);
    *((_QWORD *)this + 3) = v9;
    *(_QWORD *)this = v7;
    *((_QWORD *)this + 2) = v4;
    memmove(v7, v2, 2 * v4 + 2);
  }
  else
  {
    *((_QWORD *)this + 2) = v4;
    *((_QWORD *)this + 3) = 7;
    *(_OWORD *)this = *(_OWORD *)v2;
  }
  return this;
}

```

## disassembly

```asm
0x140006ebc  mov     [rsp+arg_10], rbx
0x140006ec1  mov     [rsp+arg_18], rsi
0x140006ec6  push    rdi
0x140006ec7  sub     rsp, 30h
0x140006ecb  mov     [rsp+38h+var_18], rcx
0x140006ed0  mov     rsi, rdx
0x140006ed3  xorps   xmm0, xmm0
0x140006ed6  mov     rbx, rcx
0x140006ed9  movups  xmmword ptr [rcx], xmm0
0x140006edc  mov     qword ptr [rcx+10h], 0
0x140006ee4  mov     qword ptr [rcx+18h], 0
0x140006eec  mov     rdi, [rdx+10h]
0x140006ef0  mov     edx, 7
0x140006ef5  cmp     [rsi+18h], rdx
0x140006ef9  jbe     short loc_140006EFE
0x140006efb  mov     rsi, [rsi]
0x140006efe  mov     rax, 7FFFFFFFFFFFFFFEh
0x140006f08  cmp     rdi, rax
0x140006f0b  ja      short loc_140006F82
0x140006f0d  cmp     rdi, rdx
0x140006f10  ja      short loc_140006F23
0x140006f12  mov     [rcx+10h], rdi
0x140006f16  mov     [rcx+18h], rdx
0x140006f1a  movups  xmm0, xmmword ptr [rsi]
0x140006f1d  movdqu  xmmword ptr [rcx], xmm0
0x140006f21  jmp     short loc_140006F6F
0x140006f23  mov     rcx, rdi
0x140006f26  or      rcx, rdx
0x140006f29  cmp     rcx, rax
0x140006f2c  ja      short loc_140006F3D
0x140006f2e  mov     edx, 0Ah
0x140006f33  mov     rax, rcx
0x140006f36  cmp     rcx, rdx
0x140006f39  cmovb   rax, rdx
0x140006f3d  lea     rdx, [rsp+38h+var_18]
0x140006f42  mov     [rsp+38h+var_18], rax
0x140006f47  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@CAPEA_WAEAV?$allocator@_W@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<wchar_t> &,unsigned __int64 &)
0x140006f4c  mov     rcx, [rsp+38h+var_18]
0x140006f51  lea     r8, ds:2[rdi*2]; Size
0x140006f59  mov     [rbx+18h], rcx
0x140006f5d  mov     rdx, rsi; Src
0x140006f60  mov     rcx, rax; void *
0x140006f63  mov     [rbx], rax
0x140006f66  mov     [rbx+10h], rdi
0x140006f6a  call    memmove
0x140006f6f  mov     rsi, [rsp+38h+arg_18]
0x140006f74  mov     rax, rbx
0x140006f77  mov     rbx, [rsp+38h+arg_10]
0x140006f7c  add     rsp, 30h
0x140006f80  pop     rdi
0x140006f81  retn
0x140006f82  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
