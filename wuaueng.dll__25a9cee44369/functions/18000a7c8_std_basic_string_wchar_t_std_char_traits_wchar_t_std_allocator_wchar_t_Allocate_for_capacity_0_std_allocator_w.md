# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::_Allocate_for_capacity<0>(std::allocator<wchar_t> &,unsigned __int64 &)

- ea: `0x18000a7c8`
- end: `0x18000a856`
- name: `??$_Allocate_for_capacity@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@CAPEA_WAEAV?$allocator@_W@1@AEA_K@Z`
- size: `142`
- prototype: `_QWORD *__fastcall(__int64, unsigned __int64 *)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x180008f84`
- `0x1800090a0`
- `0x1800093b8`
- `0x1800094f8`
- `0x18000a620`
- `0x18000a85c`

## callees

- `0x18000a7a0`
- `0x18000a7c8`
- `0x1800100bc`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18000a822`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18000a822`

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
0x18000a7c8  mov     [rsp+arg_0], rbx
0x18000a7cd  push    rdi
0x18000a7ce  sub     rsp, 30h
0x18000a7d2  mov     rcx, [rdx]
0x18000a7d5  mov     rax, 7FFFFFFFFFFFFFFFh
0x18000a7df  inc     rcx
0x18000a7e2  mov     rdi, rdx
0x18000a7e5  mov     [rdx], rcx
0x18000a7e8  cmp     rcx, rax
0x18000a7eb  ja      short loc_18000A850
0x18000a7ed  xor     ebx, ebx
0x18000a7ef  add     rcx, rcx; Size
0x18000a7f2  jz      short loc_18000A83F
0x18000a7f4  cmp     rcx, 1000h
0x18000a7fb  jb      short loc_18000A837
0x18000a7fd  lea     rax, [rcx+27h]
0x18000a801  cmp     rax, rcx
0x18000a804  jbe     short loc_18000A850
0x18000a806  mov     rcx, rax; Size
0x18000a809  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a80e  test    rax, rax
0x18000a811  jnz     short loc_18000A829
0x18000a813  xor     r9d, r9d; LineNo
0x18000a816  mov     [rsp+38h+Reserved], rbx; Reserved
0x18000a81b  xor     r8d, r8d; FileName
0x18000a81e  xor     edx, edx; FunctionName
0x18000a820  xor     ecx, ecx; Expression
0x18000a822  call    cs:__imp__invoke_watson
0x18000a829  lea     rbx, [rax+27h]
0x18000a82d  and     rbx, 0FFFFFFFFFFFFFFE0h
0x18000a831  mov     [rbx-8], rax
0x18000a835  jmp     short loc_18000A83F
0x18000a837  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a83c  mov     rbx, rax
0x18000a83f  dec     qword ptr [rdi]
0x18000a842  mov     rax, rbx
0x18000a845  mov     rbx, [rsp+38h+arg_0]
0x18000a84a  add     rsp, 30h
0x18000a84e  pop     rdi
0x18000a84f  retn
0x18000a850  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
