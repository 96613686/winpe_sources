# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Allocate_for_capacity<0>(std::allocator<char> &,unsigned __int64 &)

- ea: `0x18000925c`
- end: `0x1800092d9`
- name: `??$_Allocate_for_capacity@$0A@@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@CAPEADAEAV?$allocator@D@1@AEA_K@Z`
- size: `125`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x180008718`
- `0x180008e10`
- `0x180008f24`
- `0x1800092e0`
- `0x180009414`
- `0x180009614`

## callees

- `0x180005524`
- `0x18000925c`
- `0x18001010c`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800092a5`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800092a5`

## pseudocode

```c
_QWORD *__fastcall std::string::_Allocate_for_capacity<0>(__int64 a1, size_t *a2)
{
  _QWORD *v2; // rbx
  bool v3; // zf
  size_t v4; // rcx
  void *v6; // rax

  v2 = 0;
  v3 = *a2 == -1;
  v4 = *a2 + 1;
  *a2 = v4;
  if ( !v3 )
  {
    if ( v4 < 0x1000 )
    {
      v2 = operator new(v4);
    }
    else
    {
      if ( v4 + 39 < v4 )
        __scrt_throw_std_bad_array_new_length();
      v6 = operator new(v4 + 39);
      if ( !v6 )
        _invoke_watson(0, 0, 0, 0, 0);
      v2 = (_QWORD *)(((unsigned __int64)v6 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
      *(v2 - 1) = v6;
    }
  }
  --*a2;
  return v2;
}

```

## disassembly

```asm
0x18000925c  mov     [rsp+arg_0], rbx
0x180009261  push    rdi
0x180009262  sub     rsp, 30h
0x180009266  mov     rcx, [rdx]
0x180009269  xor     ebx, ebx
0x18000926b  add     rcx, 1; Size
0x18000926f  mov     rdi, rdx
0x180009272  mov     [rdx], rcx
0x180009275  jz      short loc_1800092C2
0x180009277  cmp     rcx, 1000h
0x18000927e  jb      short loc_1800092BA
0x180009280  lea     rax, [rcx+27h]
0x180009284  cmp     rax, rcx
0x180009287  jbe     short loc_1800092D3
0x180009289  mov     rcx, rax; Size
0x18000928c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009291  test    rax, rax
0x180009294  jnz     short loc_1800092AC
0x180009296  xor     r9d, r9d; LineNo
0x180009299  mov     [rsp+38h+Reserved], rbx; Reserved
0x18000929e  xor     r8d, r8d; FileName
0x1800092a1  xor     edx, edx; FunctionName
0x1800092a3  xor     ecx, ecx; Expression
0x1800092a5  call    cs:__imp__invoke_watson
0x1800092ac  lea     rbx, [rax+27h]
0x1800092b0  and     rbx, 0FFFFFFFFFFFFFFE0h
0x1800092b4  mov     [rbx-8], rax
0x1800092b8  jmp     short loc_1800092C2
0x1800092ba  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800092bf  mov     rbx, rax
0x1800092c2  dec     qword ptr [rdi]
0x1800092c5  mov     rax, rbx
0x1800092c8  mov     rbx, [rsp+38h+arg_0]
0x1800092cd  add     rsp, 30h
0x1800092d1  pop     rdi
0x1800092d2  retn
0x1800092d3  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
