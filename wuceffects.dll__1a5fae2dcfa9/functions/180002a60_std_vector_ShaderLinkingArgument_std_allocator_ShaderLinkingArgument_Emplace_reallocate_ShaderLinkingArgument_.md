# std::vector<ShaderLinkingArgument,std::allocator<ShaderLinkingArgument>>::_Emplace_reallocate<ShaderLinkingArgument &>(ShaderLinkingArgument * const,ShaderLinkingArgument &)

- ea: `0x180002a60`
- end: `0x180002b63`
- name: `??$_Emplace_reallocate@AEAW4ShaderLinkingArgument@@@?$vector@W4ShaderLinkingArgument@@V?$allocator@W4ShaderLinkingArgument@@@std@@@std@@AEAAPEAW4ShaderLinkingArgument@@QEAW42@AEAW42@@Z`
- size: `259`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18000241c`
- `0x1800024f0`

## callees

- `0x180001088`
- `0x180002a60`
- `0x18000a88c`
- `0x18000ad40`
- `0x180021ce0`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180002a98`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180002a98`

## pseudocode

```c
char *__fastcall std::vector<enum ShaderLinkingArgument>::_Emplace_reallocate<enum ShaderLinkingArgument &>(
        _QWORD *a1,
        _BYTE *a2,
        _WORD *a3)
{
  __int64 v3; // rdi
  __int64 v5; // rax
  unsigned __int64 v8; // r14
  __int64 v9; // r15
  unsigned __int64 v10; // rcx
  __int64 v11; // r15
  unsigned __int64 v12; // rdx
  SIZE_T size_of; // rax
  char *v14; // rsi
  char *v15; // r15
  void *v16; // rcx
  _BYTE *v17; // r8
  _BYTE *v18; // rdx
  size_t v19; // r8
  char *result; // rax

  v3 = 0x7FFFFFFFFFFFFFFFLL;
  v5 = (__int64)(a1[1] - *a1) >> 1;
  if ( v5 == 0x7FFFFFFFFFFFFFFFLL )
    std::_Xlength_error("vector too long");
  v8 = v5 + 1;
  v9 = (__int64)&a2[-*a1];
  v10 = (__int64)(a1[2] - *a1) >> 1;
  v11 = v9 >> 1;
  v12 = v10 >> 1;
  if ( v10 <= 0x7FFFFFFFFFFFFFFFLL - (v10 >> 1) )
  {
    v3 = v12 + v10;
    if ( v12 + v10 < v8 )
      v3 = v5 + 1;
  }
  size_of = std::_Get_size_of_n<2>(v3);
  v14 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(size_of);
  v15 = &v14[2 * v11];
  *(_WORD *)v15 = *a3;
  v16 = v14;
  v17 = (_BYTE *)a1[1];
  v18 = (_BYTE *)*a1;
  if ( a2 == v17 )
  {
    v19 = v17 - v18;
  }
  else
  {
    memmove_0(v14, v18, (size_t)&a2[-*a1]);
    v16 = v15 + 2;
    v19 = a1[1] - (_QWORD)a2;
    v18 = a2;
  }
  memmove_0(v16, v18, v19);
  if ( *a1 )
    std::_Deallocate<16>(*a1, 2 * ((__int64)(a1[2] - *a1) >> 1));
  *a1 = v14;
  a1[1] = &v14[2 * v8];
  result = v15;
  a1[2] = &v14[2 * v3];
  return result;
}

```

## disassembly

```asm
0x180002a60  push    rbx
0x180002a62  push    rbp
0x180002a63  push    rsi
0x180002a64  push    rdi
0x180002a65  push    r12
0x180002a67  push    r14
0x180002a69  push    r15
0x180002a6b  sub     rsp, 20h
0x180002a6f  mov     rax, [rcx+8]
0x180002a73  mov     rdi, 7FFFFFFFFFFFFFFFh
0x180002a7d  sub     rax, [rcx]
0x180002a80  mov     r12, r8
0x180002a83  sar     rax, 1
0x180002a86  mov     rbp, rdx
0x180002a89  mov     rbx, rcx
0x180002a8c  cmp     rax, rdi
0x180002a8f  jnz     short loc_180002A9F
0x180002a91  lea     rcx, aVectorTooLong; "vector too long"
0x180002a98  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180002a9f  lea     r14, [rax+1]
0x180002aa3  mov     r15, rbp
0x180002aa6  sub     r15, [rcx]
0x180002aa9  mov     rax, rdi
0x180002aac  mov     rcx, [rcx+10h]
0x180002ab0  sub     rcx, [rbx]
0x180002ab3  sar     rcx, 1
0x180002ab6  mov     rdx, rcx
0x180002ab9  sar     r15, 1
0x180002abc  shr     rdx, 1
0x180002abf  sub     rax, rdx
0x180002ac2  cmp     rcx, rax
0x180002ac5  ja      short loc_180002AD2
0x180002ac7  lea     rdi, [rdx+rcx]
0x180002acb  cmp     rdi, r14
0x180002ace  cmovb   rdi, r14
0x180002ad2  mov     rcx, rdi
0x180002ad5  call    ??$_Get_size_of_n@$01@std@@YA_K_K@Z; std::_Get_size_of_n<2>(unsigned __int64)
0x180002ada  mov     rcx, rax; dwBytes
0x180002add  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180002ae2  movzx   ecx, word ptr [r12]
0x180002ae7  mov     rsi, rax
0x180002aea  lea     r15, [rax+r15*2]
0x180002aee  mov     [r15], cx
0x180002af2  mov     rcx, rax; void *
0x180002af5  mov     r8, [rbx+8]
0x180002af9  mov     rdx, [rbx]; Src
0x180002afc  cmp     rbp, r8
0x180002aff  jnz     short loc_180002B06
0x180002b01  sub     r8, rdx
0x180002b04  jmp     short loc_180002B1F
0x180002b06  mov     r8, rbp
0x180002b09  sub     r8, [rbx]; Size
0x180002b0c  call    memmove_0
0x180002b11  mov     r8, [rbx+8]
0x180002b15  lea     rcx, [r15+2]; void *
0x180002b19  sub     r8, rbp; Size
0x180002b1c  mov     rdx, rbp; Src
0x180002b1f  call    memmove_0
0x180002b24  mov     rcx, [rbx]
0x180002b27  test    rcx, rcx
0x180002b2a  jz      short loc_180002B3E
0x180002b2c  mov     rdx, [rbx+10h]
0x180002b30  sub     rdx, rcx
0x180002b33  sar     rdx, 1
0x180002b36  add     rdx, rdx
0x180002b39  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180002b3e  lea     rcx, [rsi+r14*2]
0x180002b42  mov     [rbx], rsi
0x180002b45  mov     [rbx+8], rcx
0x180002b49  mov     rax, r15
0x180002b4c  lea     rcx, [rsi+rdi*2]
0x180002b50  mov     [rbx+10h], rcx
0x180002b54  add     rsp, 20h
0x180002b58  pop     r15
0x180002b5a  pop     r14
0x180002b5c  pop     r12
0x180002b5e  pop     rdi
0x180002b5f  pop     rsi
0x180002b60  pop     rbp
0x180002b61  pop     rbx
0x180002b62  retn
```
