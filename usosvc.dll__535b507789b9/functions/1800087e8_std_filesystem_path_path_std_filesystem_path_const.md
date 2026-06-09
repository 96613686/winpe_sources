# std::filesystem::path::path(std::filesystem::path const &)

- ea: `0x1800087e8`
- end: `0x1800088b4`
- name: `??0path@filesystem@std@@QEAA@AEBV012@@Z`
- size: `204`
- prototype: `std::filesystem::path *__fastcall(std::filesystem::path *this, const struct std::filesystem::path *)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x180008678`
- `0x180008708`
- `0x180008c74`
- `0x180009540`

## callees

- `0x180007344`
- `0x1800087e8`
- `0x18000a348`
- `0x18000e454`

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
0x1800087e8  mov     [rsp+arg_8], rbx
0x1800087ed  mov     [rsp+arg_10], rsi
0x1800087f2  mov     [rsp+arg_0], rcx
0x1800087f7  push    rdi
0x1800087f8  sub     rsp, 20h
0x1800087fc  mov     rsi, rdx
0x1800087ff  xorps   xmm0, xmm0
0x180008802  movups  xmmword ptr [rcx], xmm0
0x180008805  mov     qword ptr [rcx+10h], 0
0x18000880d  mov     rbx, rcx
0x180008810  mov     qword ptr [rcx+18h], 0
0x180008818  mov     rdi, [rdx+10h]
0x18000881c  mov     edx, 7
0x180008821  cmp     [rsi+18h], rdx
0x180008825  jbe     short loc_18000882A
0x180008827  mov     rsi, [rsi]
0x18000882a  mov     rax, 7FFFFFFFFFFFFFFEh
0x180008834  cmp     rdi, rax
0x180008837  ja      short loc_1800088AE
0x180008839  cmp     rdi, rdx
0x18000883c  ja      short loc_18000884F
0x18000883e  mov     [rcx+10h], rdi
0x180008842  mov     [rcx+18h], rdx
0x180008846  movups  xmm0, xmmword ptr [rsi]
0x180008849  movdqu  xmmword ptr [rcx], xmm0
0x18000884d  jmp     short loc_18000889B
0x18000884f  mov     rcx, rdi
0x180008852  or      rcx, rdx
0x180008855  cmp     rcx, rax
0x180008858  ja      short loc_180008869
0x18000885a  mov     edx, 0Ah
0x18000885f  mov     rax, rcx
0x180008862  cmp     rcx, rdx
0x180008865  cmovb   rax, rdx
0x180008869  lea     rdx, [rsp+28h+arg_0]
0x18000886e  mov     [rsp+28h+arg_0], rax
0x180008873  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CAPEAGAEAV?$allocator@G@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<ushort> &,unsigned __int64 &)
0x180008878  mov     rcx, [rsp+28h+arg_0]
0x18000887d  lea     r8, ds:2[rdi*2]; Size
0x180008885  mov     [rbx+18h], rcx
0x180008889  mov     rdx, rsi; Src
0x18000888c  mov     rcx, rax; void *
0x18000888f  mov     [rbx], rax
0x180008892  mov     [rbx+10h], rdi
0x180008896  call    memcpy_0
0x18000889b  mov     rsi, [rsp+28h+arg_10]
0x1800088a0  mov     rax, rbx
0x1800088a3  mov     rbx, [rsp+28h+arg_8]
0x1800088a8  add     rsp, 20h
0x1800088ac  pop     rdi
0x1800088ad  retn
0x1800088ae  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
