# std::vector<Windows::UI::Composition::FlattenedEffectGraph::NamedInput,std::allocator<Windows::UI::Composition::FlattenedEffectGraph::NamedInput>>::reserve(unsigned __int64)

- ea: `0x18000aa58`
- end: `0x18000ab83`
- name: `?reserve@?$vector@UNamedInput@FlattenedEffectGraph@Composition@UI@Windows@@V?$allocator@UNamedInput@FlattenedEffectGraph@Composition@UI@Windows@@@std@@@std@@QEAAX_K@Z`
- size: `299`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180009730`

## callees

- `0x18000aa58`
- `0x18000ad40`
- `0x18000adc0`
- `0x180021084`
- `0x1800257b8`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000ab61`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000ab61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000aaf1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000aaf1`

## pseudocode

```c
void __fastcall std::vector<Windows::UI::Composition::FlattenedEffectGraph::NamedInput>::reserve(
        HSTRING **a1,
        unsigned __int64 a2)
{
  __int64 v4; // rbp
  SIZE_T size_of; // rax
  __int64 v6; // rax
  HSTRING *v7; // r9
  __int64 v8; // r15
  HSTRING *v9; // rdx
  _QWORD *v10; // r8
  char v11; // al
  HSTRING *v12; // rsi
  HSTRING *v13; // r14
  void *v14; // rcx
  __int64 v15; // rdx
  unsigned __int64 v16; // rdx
  unsigned __int64 v17; // [rsp+50h] [rbp+8h] BYREF
  void *v18; // [rsp+58h] [rbp+10h] BYREF

  if ( a2 > ((char *)a1[2] - (char *)*a1) >> 4 )
  {
    if ( a2 > 0xFFFFFFFFFFFFFFFLL )
      std::_Xlength_error("vector too long");
    v4 = (char *)a1[1] - (char *)*a1;
    size_of = std::_Get_size_of_n<16>(a2);
    v6 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
    v7 = a1[1];
    v8 = v6;
    v9 = *a1;
    v10 = (_QWORD *)v6;
    while ( v9 != v7 )
    {
      *v10 = *v9;
      v10 += 2;
      *v9 = 0;
      *((_DWORD *)v10 - 2) = *((_DWORD *)v9 + 2);
      v11 = *((_BYTE *)v9 + 12);
      v9 += 2;
      *((_BYTE *)v10 - 4) = v11;
    }
    v12 = *a1;
    if ( *a1 )
    {
      v13 = a1[1];
      while ( v12 != v13 )
      {
        if ( *v12 )
          WindowsDeleteString(*v12);
        v12 += 2;
      }
      v14 = *a1;
      v15 = (char *)a1[2] - (char *)*a1;
      v18 = *a1;
      v16 = v15 & 0xFFFFFFFFFFFFFFF0uLL;
      v17 = v16;
      if ( v16 >= 0x1000 )
      {
        std::_Adjust_manually_vector_aligned(&v18, &v17);
        v16 = v17;
        v14 = v18;
      }
      operator delete(v14, v16);
    }
    *a1 = (HSTRING *)v8;
    a1[1] = (HSTRING *)(v8 + (v4 & 0xFFFFFFFFFFFFFFF0uLL));
    a1[2] = (HSTRING *)(v8 + 16 * a2);
  }
}

```

## disassembly

```asm
0x18000aa58  mov     [rsp+arg_10], rbx
0x18000aa5d  push    rbp
0x18000aa5e  push    rsi
0x18000aa5f  push    rdi
0x18000aa60  push    r14
0x18000aa62  push    r15
0x18000aa64  sub     rsp, 20h
0x18000aa68  mov     rax, [rcx+10h]
0x18000aa6c  mov     rdi, rdx
0x18000aa6f  sub     rax, [rcx]
0x18000aa72  mov     rbx, rcx
0x18000aa75  sar     rax, 4
0x18000aa79  cmp     rdx, rax
0x18000aa7c  jbe     loc_18000AB49
0x18000aa82  mov     rax, 0FFFFFFFFFFFFFFFh
0x18000aa8c  cmp     rdx, rax
0x18000aa8f  ja      loc_18000AB5A
0x18000aa95  mov     rbp, [rcx+8]
0x18000aa99  sub     rbp, [rcx]
0x18000aa9c  mov     rcx, rdx
0x18000aa9f  call    ??$_Get_size_of_n@$0BA@@std@@YA_K_K@Z; std::_Get_size_of_n<16>(unsigned __int64)
0x18000aaa4  mov     rcx, rax; dwBytes
0x18000aaa7  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000aaac  mov     r9, [rbx+8]
0x18000aab0  mov     r15, rax
0x18000aab3  mov     rdx, [rbx]
0x18000aab6  mov     r8, rax
0x18000aab9  jmp     short loc_18000AADE
0x18000aabb  mov     rcx, [rdx]
0x18000aabe  mov     [r8], rcx
0x18000aac1  lea     r8, [r8+10h]
0x18000aac5  mov     qword ptr [rdx], 0
0x18000aacc  mov     ecx, [rdx+8]
0x18000aacf  mov     [r8-8], ecx
0x18000aad3  mov     al, [rdx+0Ch]
0x18000aad6  add     rdx, 10h
0x18000aada  mov     [r8-4], al
0x18000aade  cmp     rdx, r9
0x18000aae1  jnz     short loc_18000AABB
0x18000aae3  mov     rsi, [rbx]
0x18000aae6  test    rsi, rsi
0x18000aae9  jz      short loc_18000AB30
0x18000aaeb  mov     r14, [rbx+8]
0x18000aaef  jmp     short loc_18000AAFB
0x18000aaf1  call    cs:__imp_WindowsDeleteString
0x18000aaf7  add     rsi, 10h
0x18000aafb  cmp     rsi, r14
0x18000aafe  jz      short loc_18000AB0A
0x18000ab00  mov     rcx, [rsi]; string
0x18000ab03  test    rcx, rcx
0x18000ab06  jz      short loc_18000AAF7
0x18000ab08  jmp     short loc_18000AAF1
0x18000ab0a  mov     rcx, [rbx]; void *
0x18000ab0d  mov     rdx, [rbx+10h]
0x18000ab11  sub     rdx, rcx
0x18000ab14  mov     [rsp+48h+arg_8], rcx
0x18000ab19  and     rdx, 0FFFFFFFFFFFFFFF0h; unsigned __int64
0x18000ab1d  mov     [rsp+48h+arg_0], rdx
0x18000ab22  cmp     rdx, 1000h
0x18000ab29  jnb     short loc_18000AB68
0x18000ab2b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ab30  and     rbp, 0FFFFFFFFFFFFFFF0h
0x18000ab34  mov     [rbx], r15
0x18000ab37  add     rbp, r15
0x18000ab3a  shl     rdi, 4
0x18000ab3e  add     rdi, r15
0x18000ab41  mov     [rbx+8], rbp
0x18000ab45  mov     [rbx+10h], rdi
0x18000ab49  mov     rbx, [rsp+48h+arg_10]
0x18000ab4e  add     rsp, 20h
0x18000ab52  pop     r15
0x18000ab54  pop     r14
0x18000ab56  pop     rdi
0x18000ab57  pop     rsi
0x18000ab58  pop     rbp
0x18000ab59  retn
0x18000ab5a  lea     rcx, aVectorTooLong; "vector too long"
0x18000ab61  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000ab68  lea     rdx, [rsp+48h+arg_0]; unsigned __int64 *
0x18000ab6d  lea     rcx, [rsp+48h+arg_8]; void **
0x18000ab72  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x18000ab77  mov     rdx, [rsp+48h+arg_0]
0x18000ab7c  mov     rcx, [rsp+48h+arg_8]
0x18000ab81  jmp     short loc_18000AB2B
```
