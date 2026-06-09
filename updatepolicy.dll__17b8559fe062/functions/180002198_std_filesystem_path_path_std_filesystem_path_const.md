# std::filesystem::path::path(std::filesystem::path const &)

- ea: `0x180002198`
- end: `0x180002264`
- name: `??0path@filesystem@std@@QEAA@AEBV012@@Z`
- size: `204`
- prototype: `std::filesystem::path *__fastcall(std::filesystem::path *this, const struct std::filesystem::path *)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x180001fe4`
- `0x18000226c`
- `0x1800026f8`
- `0x180002bd8`

## callees

- `0x180002198`
- `0x180007818`
- `0x180007928`
- `0x180015870`

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
0x180002198  mov     [rsp+arg_10], rbx
0x18000219d  mov     [rsp+arg_18], rsi
0x1800021a2  push    rdi
0x1800021a3  sub     rsp, 30h
0x1800021a7  mov     [rsp+38h+var_18], rcx
0x1800021ac  mov     rsi, rdx
0x1800021af  xorps   xmm0, xmm0
0x1800021b2  mov     rbx, rcx
0x1800021b5  movups  xmmword ptr [rcx], xmm0
0x1800021b8  mov     qword ptr [rcx+10h], 0
0x1800021c0  mov     qword ptr [rcx+18h], 0
0x1800021c8  mov     rdi, [rdx+10h]
0x1800021cc  mov     edx, 7
0x1800021d1  cmp     [rsi+18h], rdx
0x1800021d5  jbe     short loc_1800021DA
0x1800021d7  mov     rsi, [rsi]
0x1800021da  mov     rax, 7FFFFFFFFFFFFFFEh
0x1800021e4  cmp     rdi, rax
0x1800021e7  ja      short loc_18000225E
0x1800021e9  cmp     rdi, rdx
0x1800021ec  ja      short loc_1800021FF
0x1800021ee  mov     [rcx+10h], rdi
0x1800021f2  mov     [rcx+18h], rdx
0x1800021f6  movups  xmm0, xmmword ptr [rsi]
0x1800021f9  movdqu  xmmword ptr [rcx], xmm0
0x1800021fd  jmp     short loc_18000224B
0x1800021ff  mov     rcx, rdi
0x180002202  or      rcx, rdx
0x180002205  cmp     rcx, rax
0x180002208  ja      short loc_180002219
0x18000220a  mov     edx, 0Ah
0x18000220f  mov     rax, rcx
0x180002212  cmp     rcx, rdx
0x180002215  cmovb   rax, rdx
0x180002219  lea     rdx, [rsp+38h+var_18]
0x18000221e  mov     [rsp+38h+var_18], rax
0x180002223  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@CAPEA_WAEAV?$allocator@_W@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<wchar_t> &,unsigned __int64 &)
0x180002228  mov     rcx, [rsp+38h+var_18]
0x18000222d  lea     r8, ds:2[rdi*2]; Size
0x180002235  mov     [rbx+18h], rcx
0x180002239  mov     rdx, rsi; Src
0x18000223c  mov     rcx, rax; void *
0x18000223f  mov     [rbx], rax
0x180002242  mov     [rbx+10h], rdi
0x180002246  call    memmove
0x18000224b  mov     rsi, [rsp+38h+arg_18]
0x180002250  mov     rax, rbx
0x180002253  mov     rbx, [rsp+38h+arg_10]
0x180002258  add     rsp, 30h
0x18000225c  pop     rdi
0x18000225d  retn
0x18000225e  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
