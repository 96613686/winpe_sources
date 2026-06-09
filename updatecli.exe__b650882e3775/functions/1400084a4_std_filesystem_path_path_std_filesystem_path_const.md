# std::filesystem::path::path(std::filesystem::path const &)

- ea: `0x1400084a4`
- end: `0x140008570`
- name: `??0path@filesystem@std@@QEAA@AEBV012@@Z`
- size: `204`
- prototype: `std::filesystem::path *__fastcall(std::filesystem::path *this, const struct std::filesystem::path *)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x140008334`
- `0x1400083c4`
- `0x140008a34`
- `0x1400093c0`

## callees

- `0x140007000`
- `0x1400084a4`
- `0x14000a2dc`
- `0x14000ac74`

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
  _QWORD *v7; // rax
  std::filesystem::path *v9; // [rsp+30h] [rbp+8h] BYREF

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
    v7 = std::wstring::_Allocate_for_capacity<0>(v6, &v9);
    *((_QWORD *)this + 3) = v9;
    *(_QWORD *)this = v7;
    *((_QWORD *)this + 2) = v4;
    memcpy_0(v7, v2, 2 * v4 + 2);
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
0x1400084a4  mov     [rsp+arg_8], rbx
0x1400084a9  mov     [rsp+arg_10], rsi
0x1400084ae  mov     [rsp+arg_0], rcx
0x1400084b3  push    rdi
0x1400084b4  sub     rsp, 20h
0x1400084b8  mov     rsi, rdx
0x1400084bb  xorps   xmm0, xmm0
0x1400084be  movups  xmmword ptr [rcx], xmm0
0x1400084c1  mov     qword ptr [rcx+10h], 0
0x1400084c9  mov     rbx, rcx
0x1400084cc  mov     qword ptr [rcx+18h], 0
0x1400084d4  mov     rdi, [rdx+10h]
0x1400084d8  mov     edx, 7
0x1400084dd  cmp     [rsi+18h], rdx
0x1400084e1  jbe     short loc_1400084E6
0x1400084e3  mov     rsi, [rsi]
0x1400084e6  mov     rax, 7FFFFFFFFFFFFFFEh
0x1400084f0  cmp     rdi, rax
0x1400084f3  ja      short loc_14000856A
0x1400084f5  cmp     rdi, rdx
0x1400084f8  ja      short loc_14000850B
0x1400084fa  mov     [rcx+10h], rdi
0x1400084fe  mov     [rcx+18h], rdx
0x140008502  movups  xmm0, xmmword ptr [rsi]
0x140008505  movdqu  xmmword ptr [rcx], xmm0
0x140008509  jmp     short loc_140008557
0x14000850b  mov     rcx, rdi
0x14000850e  or      rcx, rdx
0x140008511  cmp     rcx, rax
0x140008514  ja      short loc_140008525
0x140008516  mov     edx, 0Ah
0x14000851b  mov     rax, rcx
0x14000851e  cmp     rcx, rdx
0x140008521  cmovb   rax, rdx
0x140008525  lea     rdx, [rsp+28h+arg_0]
0x14000852a  mov     [rsp+28h+arg_0], rax
0x14000852f  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CAPEAGAEAV?$allocator@G@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<ushort> &,unsigned __int64 &)
0x140008534  mov     rcx, [rsp+28h+arg_0]
0x140008539  lea     r8, ds:2[rdi*2]; Size
0x140008541  mov     [rbx+18h], rcx
0x140008545  mov     rdx, rsi; Src
0x140008548  mov     rcx, rax; void *
0x14000854b  mov     [rbx], rax
0x14000854e  mov     [rbx+10h], rdi
0x140008552  call    memcpy_0
0x140008557  mov     rsi, [rsp+28h+arg_10]
0x14000855c  mov     rax, rbx
0x14000855f  mov     rbx, [rsp+28h+arg_8]
0x140008564  add     rsp, 20h
0x140008568  pop     rdi
0x140008569  retn
0x14000856a  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
