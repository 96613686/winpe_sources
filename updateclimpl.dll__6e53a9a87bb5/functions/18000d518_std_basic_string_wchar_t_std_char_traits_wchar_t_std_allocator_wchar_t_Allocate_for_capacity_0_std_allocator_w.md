# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::_Allocate_for_capacity<0>(std::allocator<wchar_t> &,unsigned __int64 &)

- ea: `0x18000d518`
- end: `0x18000d5a6`
- name: `??$_Allocate_for_capacity@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@CAPEA_WAEAV?$allocator@_W@1@AEA_K@Z`
- size: `142`
- prototype: `_QWORD *__fastcall(__int64, unsigned __int64 *)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b090`
- `0x18000b1b4`
- `0x18000b2f4`
- `0x18000c2e0`
- `0x18000d5ac`

## callees

- `0x18000d4f0`
- `0x18000d518`
- `0x1800146e0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18000d572`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18000d572`

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
0x18000d518  mov     [rsp+arg_0], rbx
0x18000d51d  push    rdi
0x18000d51e  sub     rsp, 30h
0x18000d522  mov     rcx, [rdx]
0x18000d525  mov     rax, 7FFFFFFFFFFFFFFFh
0x18000d52f  inc     rcx
0x18000d532  mov     rdi, rdx
0x18000d535  mov     [rdx], rcx
0x18000d538  cmp     rcx, rax
0x18000d53b  ja      short loc_18000D5A0
0x18000d53d  xor     ebx, ebx
0x18000d53f  add     rcx, rcx; Size
0x18000d542  jz      short loc_18000D58F
0x18000d544  cmp     rcx, 1000h
0x18000d54b  jb      short loc_18000D587
0x18000d54d  lea     rax, [rcx+27h]
0x18000d551  cmp     rax, rcx
0x18000d554  jbe     short loc_18000D5A0
0x18000d556  mov     rcx, rax; Size
0x18000d559  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d55e  test    rax, rax
0x18000d561  jnz     short loc_18000D579
0x18000d563  xor     r9d, r9d; LineNo
0x18000d566  mov     [rsp+38h+Reserved], rbx; Reserved
0x18000d56b  xor     r8d, r8d; FileName
0x18000d56e  xor     edx, edx; FunctionName
0x18000d570  xor     ecx, ecx; Expression
0x18000d572  call    cs:__imp__invoke_watson
0x18000d579  lea     rbx, [rax+27h]
0x18000d57d  and     rbx, 0FFFFFFFFFFFFFFE0h
0x18000d581  mov     [rbx-8], rax
0x18000d585  jmp     short loc_18000D58F
0x18000d587  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d58c  mov     rbx, rax
0x18000d58f  dec     qword ptr [rdi]
0x18000d592  mov     rax, rbx
0x18000d595  mov     rbx, [rsp+38h+arg_0]
0x18000d59a  add     rsp, 30h
0x18000d59e  pop     rdi
0x18000d59f  retn
0x18000d5a0  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
