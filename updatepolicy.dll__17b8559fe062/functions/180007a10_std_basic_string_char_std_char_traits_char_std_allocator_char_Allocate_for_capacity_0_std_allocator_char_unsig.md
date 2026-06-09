# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Allocate_for_capacity<0>(std::allocator<char> &,unsigned __int64 &)

- ea: `0x180007a10`
- end: `0x180007a8d`
- name: `??$_Allocate_for_capacity@$0A@@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@CAPEADAEAV?$allocator@D@1@AEA_K@Z`
- size: `125`
- prototype: `_QWORD *__fastcall(__int64, size_t *)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x1800047dc`
- `0x180004d90`
- `0x18000509c`
- `0x1800051d0`
- `0x1800053d4`
- `0x180007a94`

## callees

- `0x1800079e8`
- `0x180007a10`
- `0x18000ed9c`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180007a59`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180007a59`

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
0x180007a10  mov     [rsp+arg_0], rbx
0x180007a15  push    rdi
0x180007a16  sub     rsp, 30h
0x180007a1a  mov     rcx, [rdx]
0x180007a1d  xor     ebx, ebx
0x180007a1f  add     rcx, 1; Size
0x180007a23  mov     rdi, rdx
0x180007a26  mov     [rdx], rcx
0x180007a29  jz      short loc_180007A76
0x180007a2b  cmp     rcx, 1000h
0x180007a32  jb      short loc_180007A6E
0x180007a34  lea     rax, [rcx+27h]
0x180007a38  cmp     rax, rcx
0x180007a3b  jbe     short loc_180007A87
0x180007a3d  mov     rcx, rax; Size
0x180007a40  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007a45  test    rax, rax
0x180007a48  jnz     short loc_180007A60
0x180007a4a  xor     r9d, r9d; LineNo
0x180007a4d  mov     [rsp+38h+Reserved], rbx; Reserved
0x180007a52  xor     r8d, r8d; FileName
0x180007a55  xor     edx, edx; FunctionName
0x180007a57  xor     ecx, ecx; Expression
0x180007a59  call    cs:__imp__invoke_watson
0x180007a60  lea     rbx, [rax+27h]
0x180007a64  and     rbx, 0FFFFFFFFFFFFFFE0h
0x180007a68  mov     [rbx-8], rax
0x180007a6c  jmp     short loc_180007A76
0x180007a6e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007a73  mov     rbx, rax
0x180007a76  dec     qword ptr [rdi]
0x180007a79  mov     rax, rbx
0x180007a7c  mov     rbx, [rsp+38h+arg_0]
0x180007a81  add     rsp, 30h
0x180007a85  pop     rdi
0x180007a86  retn
0x180007a87  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
