# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Allocate_for_capacity<0>(std::allocator<char> &,unsigned __int64 &)

- ea: `0x180007d98`
- end: `0x180007e15`
- name: `??$_Allocate_for_capacity@$0A@@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@CAPEADAEAV?$allocator@D@1@AEA_K@Z`
- size: `125`
- prototype: `_QWORD *__fastcall(__int64, size_t *)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x180006cec`
- `0x1800073dc`
- `0x180007574`
- `0x1800076c4`
- `0x180007bbc`
- `0x180007e1c`

## callees

- `0x180007d98`
- `0x18000a7a0`
- `0x1800100bc`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180007de1`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180007de1`

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
0x180007d98  mov     [rsp+arg_0], rbx
0x180007d9d  push    rdi
0x180007d9e  sub     rsp, 30h
0x180007da2  mov     rcx, [rdx]
0x180007da5  xor     ebx, ebx
0x180007da7  add     rcx, 1; Size
0x180007dab  mov     rdi, rdx
0x180007dae  mov     [rdx], rcx
0x180007db1  jz      short loc_180007DFE
0x180007db3  cmp     rcx, 1000h
0x180007dba  jb      short loc_180007DF6
0x180007dbc  lea     rax, [rcx+27h]
0x180007dc0  cmp     rax, rcx
0x180007dc3  jbe     short loc_180007E0F
0x180007dc5  mov     rcx, rax; Size
0x180007dc8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007dcd  test    rax, rax
0x180007dd0  jnz     short loc_180007DE8
0x180007dd2  xor     r9d, r9d; LineNo
0x180007dd5  mov     [rsp+38h+Reserved], rbx; Reserved
0x180007dda  xor     r8d, r8d; FileName
0x180007ddd  xor     edx, edx; FunctionName
0x180007ddf  xor     ecx, ecx; Expression
0x180007de1  call    cs:__imp__invoke_watson
0x180007de8  lea     rbx, [rax+27h]
0x180007dec  and     rbx, 0FFFFFFFFFFFFFFE0h
0x180007df0  mov     [rbx-8], rax
0x180007df4  jmp     short loc_180007DFE
0x180007df6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007dfb  mov     rbx, rax
0x180007dfe  dec     qword ptr [rdi]
0x180007e01  mov     rax, rbx
0x180007e04  mov     rbx, [rsp+38h+arg_0]
0x180007e09  add     rsp, 30h
0x180007e0d  pop     rdi
0x180007e0e  retn
0x180007e0f  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
