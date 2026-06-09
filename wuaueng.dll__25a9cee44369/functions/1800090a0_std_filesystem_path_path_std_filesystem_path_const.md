# std::filesystem::path::path(std::filesystem::path const &)

- ea: `0x1800090a0`
- end: `0x18000916c`
- name: `??0path@filesystem@std@@QEAA@AEBV012@@Z`
- size: `204`
- prototype: `std::filesystem::path *__fastcall(std::filesystem::path *this, const struct std::filesystem::path *)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x180007ae8`
- `0x180007f60`
- `0x180008148`
- `0x1800098b8`

## callees

- `0x1800090a0`
- `0x18000a6e0`
- `0x18000a7c8`
- `0x180015df0`

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
    v7 = std::wstring::_Allocate_for_capacity<0>(v6, (unsigned __int64 *)&v9);
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
0x1800090a0  mov     [rsp+arg_10], rbx
0x1800090a5  mov     [rsp+arg_18], rsi
0x1800090aa  push    rdi
0x1800090ab  sub     rsp, 30h
0x1800090af  mov     [rsp+38h+var_18], rcx
0x1800090b4  mov     rsi, rdx
0x1800090b7  xorps   xmm0, xmm0
0x1800090ba  mov     rbx, rcx
0x1800090bd  movups  xmmword ptr [rcx], xmm0
0x1800090c0  mov     qword ptr [rcx+10h], 0
0x1800090c8  mov     qword ptr [rcx+18h], 0
0x1800090d0  mov     rdi, [rdx+10h]
0x1800090d4  mov     edx, 7
0x1800090d9  cmp     [rsi+18h], rdx
0x1800090dd  jbe     short loc_1800090E2
0x1800090df  mov     rsi, [rsi]
0x1800090e2  mov     rax, 7FFFFFFFFFFFFFFEh
0x1800090ec  cmp     rdi, rax
0x1800090ef  ja      short loc_180009166
0x1800090f1  cmp     rdi, rdx
0x1800090f4  ja      short loc_180009107
0x1800090f6  mov     [rcx+10h], rdi
0x1800090fa  mov     [rcx+18h], rdx
0x1800090fe  movups  xmm0, xmmword ptr [rsi]
0x180009101  movdqu  xmmword ptr [rcx], xmm0
0x180009105  jmp     short loc_180009153
0x180009107  mov     rcx, rdi
0x18000910a  or      rcx, rdx
0x18000910d  cmp     rcx, rax
0x180009110  ja      short loc_180009121
0x180009112  mov     edx, 0Ah
0x180009117  mov     rax, rcx
0x18000911a  cmp     rcx, rdx
0x18000911d  cmovb   rax, rdx
0x180009121  lea     rdx, [rsp+38h+var_18]
0x180009126  mov     [rsp+38h+var_18], rax
0x18000912b  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@CAPEA_WAEAV?$allocator@_W@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<wchar_t> &,unsigned __int64 &)
0x180009130  mov     rcx, [rsp+38h+var_18]
0x180009135  lea     r8, ds:2[rdi*2]; Size
0x18000913d  mov     [rbx+18h], rcx
0x180009141  mov     rdx, rsi; Src
0x180009144  mov     rcx, rax; void *
0x180009147  mov     [rbx], rax
0x18000914a  mov     [rbx+10h], rdi
0x18000914e  call    memmove
0x180009153  mov     rsi, [rsp+38h+arg_18]
0x180009158  mov     rax, rbx
0x18000915b  mov     rbx, [rsp+38h+arg_10]
0x180009160  add     rsp, 30h
0x180009164  pop     rdi
0x180009165  retn
0x180009166  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
