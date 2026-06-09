# std::filesystem::path::path(std::filesystem::path const &)

- ea: `0x180006358`
- end: `0x180006424`
- name: `??0path@filesystem@std@@QEAA@AEBV012@@Z`
- size: `204`
- prototype: `_QWORD(std::filesystem::path *__hidden this, const struct std::filesystem::path *)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x1800061a4`
- `0x18000642c`
- `0x1800068b8`
- `0x180006d98`

## callees

- `0x1800055d4`
- `0x180006358`
- `0x180008fd0`
- `0x180015e40`

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
0x180006358  mov     [rsp+arg_10], rbx
0x18000635d  mov     [rsp+arg_18], rsi
0x180006362  push    rdi
0x180006363  sub     rsp, 30h
0x180006367  mov     [rsp+38h+var_18], rcx
0x18000636c  mov     rsi, rdx
0x18000636f  xorps   xmm0, xmm0
0x180006372  mov     rbx, rcx
0x180006375  movups  xmmword ptr [rcx], xmm0
0x180006378  mov     qword ptr [rcx+10h], 0
0x180006380  mov     qword ptr [rcx+18h], 0
0x180006388  mov     rdi, [rdx+10h]
0x18000638c  mov     edx, 7
0x180006391  cmp     [rsi+18h], rdx
0x180006395  jbe     short loc_18000639A
0x180006397  mov     rsi, [rsi]
0x18000639a  mov     rax, 7FFFFFFFFFFFFFFEh
0x1800063a4  cmp     rdi, rax
0x1800063a7  ja      short loc_18000641E
0x1800063a9  cmp     rdi, rdx
0x1800063ac  ja      short loc_1800063BF
0x1800063ae  mov     [rcx+10h], rdi
0x1800063b2  mov     [rcx+18h], rdx
0x1800063b6  movups  xmm0, xmmword ptr [rsi]
0x1800063b9  movdqu  xmmword ptr [rcx], xmm0
0x1800063bd  jmp     short loc_18000640B
0x1800063bf  mov     rcx, rdi
0x1800063c2  or      rcx, rdx
0x1800063c5  cmp     rcx, rax
0x1800063c8  ja      short loc_1800063D9
0x1800063ca  mov     edx, 0Ah
0x1800063cf  mov     rax, rcx
0x1800063d2  cmp     rcx, rdx
0x1800063d5  cmovb   rax, rdx
0x1800063d9  lea     rdx, [rsp+38h+var_18]
0x1800063de  mov     [rsp+38h+var_18], rax
0x1800063e3  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@CAPEA_WAEAV?$allocator@_W@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<wchar_t> &,unsigned __int64 &)
0x1800063e8  mov     rcx, [rsp+38h+var_18]
0x1800063ed  lea     r8, ds:2[rdi*2]; Size
0x1800063f5  mov     [rbx+18h], rcx
0x1800063f9  mov     rdx, rsi; Src
0x1800063fc  mov     rcx, rax; void *
0x1800063ff  mov     [rbx], rax
0x180006402  mov     [rbx+10h], rdi
0x180006406  call    memmove
0x18000640b  mov     rsi, [rsp+38h+arg_18]
0x180006410  mov     rax, rbx
0x180006413  mov     rbx, [rsp+38h+arg_10]
0x180006418  add     rsp, 30h
0x18000641c  pop     rdi
0x18000641d  retn
0x18000641e  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
