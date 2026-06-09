# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::_Allocate_for_capacity<0>(std::allocator<wchar_t> &,unsigned __int64 &)

- ea: `0x180008fd0`
- end: `0x18000905e`
- name: `??$_Allocate_for_capacity@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@CAPEA_WAEAV?$allocator@_W@1@AEA_K@Z`
- size: `142`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x180006358`
- `0x1800084c4`
- `0x180008868`
- `0x180008928`
- `0x180008b78`
- `0x180008cb8`

## callees

- `0x180005524`
- `0x180008fd0`
- `0x18001010c`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18000902a`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18000902a`

## pseudocode

```c
_QWORD *__fastcall std::wstring::_Allocate_for_capacity<0>(__int64 a1, unsigned __int64 *a2)
{
  unsigned __int64 v2; // rcx
  _QWORD *v4; // rbx
  size_t v5; // rcx
  void *v6; // rax

  v2 = *a2 + 1;
  *a2 = v2;
  if ( v2 > 0x7FFFFFFFFFFFFFFFLL )
    goto LABEL_10;
  v4 = 0;
  v5 = 2 * v2;
  if ( !v5 )
    goto LABEL_9;
  if ( v5 < 0x1000 )
  {
    v4 = operator new(v5);
    goto LABEL_9;
  }
  if ( v5 + 39 < v5 )
LABEL_10:
    __scrt_throw_std_bad_array_new_length();
  v6 = operator new(v5 + 39);
  if ( !v6 )
    _invoke_watson(0, 0, 0, 0, 0);
  v4 = (_QWORD *)(((unsigned __int64)v6 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(v4 - 1) = v6;
LABEL_9:
  --*a2;
  return v4;
}

```

## disassembly

```asm
0x180008fd0  mov     [rsp+arg_0], rbx
0x180008fd5  push    rdi
0x180008fd6  sub     rsp, 30h
0x180008fda  mov     rcx, [rdx]
0x180008fdd  mov     rax, 7FFFFFFFFFFFFFFFh
0x180008fe7  inc     rcx
0x180008fea  mov     rdi, rdx
0x180008fed  mov     [rdx], rcx
0x180008ff0  cmp     rcx, rax
0x180008ff3  ja      short loc_180009058
0x180008ff5  xor     ebx, ebx
0x180008ff7  add     rcx, rcx; Size
0x180008ffa  jz      short loc_180009047
0x180008ffc  cmp     rcx, 1000h
0x180009003  jb      short loc_18000903F
0x180009005  lea     rax, [rcx+27h]
0x180009009  cmp     rax, rcx
0x18000900c  jbe     short loc_180009058
0x18000900e  mov     rcx, rax; Size
0x180009011  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009016  test    rax, rax
0x180009019  jnz     short loc_180009031
0x18000901b  xor     r9d, r9d; LineNo
0x18000901e  mov     [rsp+38h+Reserved], rbx; Reserved
0x180009023  xor     r8d, r8d; FileName
0x180009026  xor     edx, edx; FunctionName
0x180009028  xor     ecx, ecx; Expression
0x18000902a  call    cs:__imp__invoke_watson
0x180009031  lea     rbx, [rax+27h]
0x180009035  and     rbx, 0FFFFFFFFFFFFFFE0h
0x180009039  mov     [rbx-8], rax
0x18000903d  jmp     short loc_180009047
0x18000903f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009044  mov     rbx, rax
0x180009047  dec     qword ptr [rdi]
0x18000904a  mov     rax, rbx
0x18000904d  mov     rbx, [rsp+38h+arg_0]
0x180009052  add     rsp, 30h
0x180009056  pop     rdi
0x180009057  retn
0x180009058  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
