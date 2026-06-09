# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::assign(char const *,unsigned __int64)

- ea: `0x140006fe8`
- end: `0x1400070df`
- name: `?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z`
- size: `247`
- prototype: `size_t *__fastcall(size_t *, char *Src, size_t Size)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x140007340`
- `0x1400073b0`
- `0x140007440`

## callees

- `0x140001936`
- `0x140006d2c`
- `0x140006ec0`
- `0x140006ef0`
- `0x140006fe8`

## pseudocode

```c
size_t *__fastcall std::string::assign(size_t *a1, char *Src, size_t Size)
{
  size_t *v5; // rbx
  char *v6; // rax
  void *v8; // rcx
  _BYTE *v9; // rax
  size_t v10; // rax

  v5 = a1;
  if ( Src )
  {
    v6 = a1[3] < 0x10 ? (char *)a1 : (char *)*a1;
    if ( Src >= v6 )
    {
      if ( a1[3] >= 0x10 )
        a1 = (size_t *)*a1;
      if ( (char *)a1 + v5[2] > Src )
        return (size_t *)std::string::assign(v5);
    }
  }
  if ( Size == -1 )
    std::string::_Xlen();
  if ( v5[3] >= Size )
  {
    if ( !Size )
    {
      if ( v5[3] < 0x10 )
        v9 = v5;
      else
        v9 = (_BYTE *)*v5;
      v5[2] = 0;
      *v9 = 0;
      return v5;
    }
    goto LABEL_13;
  }
  std::string::_Copy((const void **)v5, Size, v5[2]);
  if ( Size )
  {
LABEL_13:
    if ( v5[3] < 0x10 )
      v8 = v5;
    else
      v8 = (void *)*v5;
    memcpy_0(v8, Src, Size);
    if ( v5[3] < 0x10 )
      v10 = (size_t)v5;
    else
      v10 = *v5;
    v5[2] = Size;
    *(_BYTE *)(v10 + Size) = 0;
  }
  return v5;
}

```

## disassembly

```asm
0x140006fe8  mov     [rsp+arg_0], rbx
0x140006fed  mov     [rsp+arg_8], rsi
0x140006ff2  push    rdi
0x140006ff3  sub     rsp, 20h
0x140006ff7  mov     rdi, r8
0x140006ffa  mov     rsi, rdx
0x140006ffd  mov     rbx, rcx
0x140007000  test    rdx, rdx
0x140007003  jz      short loc_140007051
0x140007005  cmp     qword ptr [rcx+18h], 10h
0x14000700a  jb      short loc_140007011
0x14000700c  mov     rax, [rcx]
0x14000700f  jmp     short loc_140007014
0x140007011  mov     rax, rbx
0x140007014  cmp     rsi, rax
0x140007017  jb      short loc_140007051
0x140007019  cmp     qword ptr [rcx+18h], 10h
0x14000701e  jb      short loc_140007023
0x140007020  mov     rcx, [rcx]
0x140007023  add     rcx, [rbx+10h]
0x140007027  cmp     rcx, rsi
0x14000702a  jbe     short loc_140007051
0x14000702c  cmp     qword ptr [rbx+18h], 10h
0x140007031  jb      short loc_140007038
0x140007033  mov     rax, [rbx]
0x140007036  jmp     short loc_14000703B
0x140007038  mov     rax, rbx
0x14000703b  sub     rsi, rax
0x14000703e  mov     r9, rdi
0x140007041  mov     r8, rsi
0x140007044  mov     rdx, rbx
0x140007047  mov     rcx, rbx; void *
0x14000704a  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::string::assign(std::string const &,unsigned __int64,unsigned __int64)
0x14000704f  jmp     short loc_1400070C6
0x140007051  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x140007055  ja      short loc_1400070D6
0x140007057  cmp     [rbx+18h], rdi
0x14000705b  jnb     short loc_14000707D
0x14000705d  mov     r8, [rbx+10h]
0x140007061  mov     rdx, rdi
0x140007064  mov     rcx, rbx; Src
0x140007067  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x14000706c  test    rdi, rdi
0x14000706f  jz      short loc_1400070C3
0x140007071  cmp     qword ptr [rbx+18h], 10h
0x140007076  jb      short loc_14000709E
0x140007078  mov     rcx, [rbx]
0x14000707b  jmp     short loc_1400070A1
0x14000707d  test    rdi, rdi
0x140007080  jnz     short loc_140007071
0x140007082  cmp     qword ptr [rbx+18h], 10h
0x140007087  jb      short loc_14000708E
0x140007089  mov     rax, [rbx]
0x14000708c  jmp     short loc_140007091
0x14000708e  mov     rax, rbx
0x140007091  mov     qword ptr [rbx+10h], 0
0x140007099  mov     byte ptr [rax], 0
0x14000709c  jmp     short loc_1400070C3
0x14000709e  mov     rcx, rbx; void *
0x1400070a1  mov     r8, rdi; Size
0x1400070a4  mov     rdx, rsi; Src
0x1400070a7  call    memcpy_0
0x1400070ac  cmp     qword ptr [rbx+18h], 10h
0x1400070b1  jb      short loc_1400070B8
0x1400070b3  mov     rax, [rbx]
0x1400070b6  jmp     short loc_1400070BB
0x1400070b8  mov     rax, rbx
0x1400070bb  mov     [rbx+10h], rdi
0x1400070bf  mov     byte ptr [rax+rdi], 0
0x1400070c3  mov     rax, rbx
0x1400070c6  mov     rbx, [rsp+28h+arg_0]
0x1400070cb  mov     rsi, [rsp+28h+arg_8]
0x1400070d0  add     rsp, 20h
0x1400070d4  pop     rdi
0x1400070d5  retn
0x1400070d6  mov     rcx, rbx
0x1400070d9  call    ?_Xlen@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ; std::string::_Xlen(void)
```
