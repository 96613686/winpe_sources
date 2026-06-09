# std::vector<Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty,std::allocator<Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty>>::reserve(unsigned __int64)

- ea: `0x18000a8d0`
- end: `0x18000aa4f`
- name: `?reserve@?$vector@UAnimatableProperty@FlattenedEffectGraph@Composition@UI@Windows@@V?$allocator@UAnimatableProperty@FlattenedEffectGraph@Composition@UI@Windows@@@std@@@std@@QEAAX_K@Z`
- size: `383`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180009730`

## callees

- `0x18000a8d0`
- `0x18000ad40`
- `0x18000afe0`
- `0x18000bc6c`
- `0x180021084`
- `0x1800257b8`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000a9f4`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000a9f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a982`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a982`

## pseudocode

```c
unsigned __int64 __fastcall std::vector<Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty>::reserve(
        HSTRING **a1,
        unsigned __int64 a2)
{
  unsigned __int64 result; // rax
  unsigned __int64 v5; // r14
  SIZE_T size_of; // rax
  __int64 v7; // rax
  HSTRING *v8; // r9
  __int64 v9; // r15
  HSTRING *v10; // rdx
  __int64 v11; // r8
  HSTRING *v12; // rdi
  HSTRING *v13; // rbp
  void *v14; // rcx
  __int64 v15; // rax
  unsigned __int64 v16; // rdx
  unsigned __int64 v17; // [rsp+50h] [rbp+8h] BYREF
  void *v18; // [rsp+58h] [rbp+10h] BYREF

  result = 0xAAAAAAAAAAAAAAABuLL * (a1[2] - *a1);
  if ( a2 > result )
  {
    if ( a2 > 0xAAAAAAAAAAAAAAALL )
      std::_Xlength_error("vector too long");
    v5 = 0xAAAAAAAAAAAAAAABuLL * (a1[1] - *a1);
    size_of = std::_Get_size_of_n<24>(a2);
    v7 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
    v8 = a1[1];
    v9 = v7;
    v10 = *a1;
    v11 = v7;
    while ( v10 != v8 )
    {
      *(_QWORD *)v11 = *v10;
      *v10 = 0;
      *(_DWORD *)(v11 + 8) = *((_DWORD *)v10 + 2);
      *(_DWORD *)(v11 + 12) = *((_DWORD *)v10 + 3);
      *(_DWORD *)(v11 + 16) = *((_DWORD *)v10 + 4);
      *(_DWORD *)(v11 + 20) = *((_DWORD *)v10 + 5);
      v11 += 24;
      v10 += 3;
    }
    std::_Destroy_range<std::allocator<Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty>>(v11, v11);
    v12 = *a1;
    if ( *a1 )
    {
      v13 = a1[1];
      while ( v12 != v13 )
      {
        if ( *v12 )
          WindowsDeleteString(*v12);
        v12 += 3;
      }
      v14 = *a1;
      v15 = (char *)a1[2] - (char *)*a1;
      v18 = *a1;
      v16 = 8 * (v15 >> 3);
      v17 = v16;
      if ( v16 >= 0x1000 )
      {
        std::_Adjust_manually_vector_aligned(&v18, &v17);
        v16 = v17;
        v14 = v18;
      }
      operator delete(v14, v16);
    }
    *a1 = (HSTRING *)v9;
    a1[1] = (HSTRING *)(v9 + 24 * v5);
    result = 3 * a2;
    a1[2] = (HSTRING *)(v9 + 24 * a2);
  }
  return result;
}

```

## disassembly

```asm
0x18000a8d0  mov     [rsp+arg_10], rbx
0x18000a8d5  mov     [rsp+arg_18], rbp
0x18000a8da  push    rsi
0x18000a8db  push    rdi
0x18000a8dc  push    r12
0x18000a8de  push    r14
0x18000a8e0  push    r15
0x18000a8e2  sub     rsp, 20h
0x18000a8e6  mov     rax, [rcx+10h]
0x18000a8ea  mov     r12, 0AAAAAAAAAAAAAAABh
0x18000a8f4  sub     rax, [rcx]
0x18000a8f7  mov     rsi, rdx
0x18000a8fa  sar     rax, 3
0x18000a8fe  mov     rbx, rcx
0x18000a901  imul    rax, r12
0x18000a905  cmp     rdx, rax
0x18000a908  ja      short loc_18000A921
0x18000a90a  mov     rbx, [rsp+48h+arg_10]
0x18000a90f  mov     rbp, [rsp+48h+arg_18]
0x18000a914  add     rsp, 20h
0x18000a918  pop     r15
0x18000a91a  pop     r14
0x18000a91c  pop     r12
0x18000a91e  pop     rdi
0x18000a91f  pop     rsi
0x18000a920  retn
0x18000a921  mov     rax, 0AAAAAAAAAAAAAAAh
0x18000a92b  cmp     rsi, rax
0x18000a92e  ja      loc_18000A9ED
0x18000a934  mov     r14, [rcx+8]
0x18000a938  sub     r14, [rcx]
0x18000a93b  mov     rcx, rsi
0x18000a93e  sar     r14, 3
0x18000a942  imul    r14, r12
0x18000a946  call    ??$_Get_size_of_n@$0BI@@std@@YA_K_K@Z; std::_Get_size_of_n<24>(unsigned __int64)
0x18000a94b  mov     rcx, rax; dwBytes
0x18000a94e  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000a953  mov     r9, [rbx+8]
0x18000a957  mov     r15, rax
0x18000a95a  mov     rdx, [rbx]
0x18000a95d  mov     r8, rax
0x18000a960  cmp     rdx, r9
0x18000a963  jnz     loc_18000A9FB
0x18000a969  mov     rdx, r8
0x18000a96c  mov     rcx, r8
0x18000a96f  call    ??$_Destroy_range@V?$allocator@UAnimatableProperty@FlattenedEffectGraph@Composition@UI@Windows@@@std@@@std@@YAXPEAUAnimatableProperty@FlattenedEffectGraph@Composition@UI@Windows@@QEAU12345@AEAV?$allocator@UAnimatableProperty@FlattenedEffectGraph@Composition@UI@Windows@@@0@@Z; std::_Destroy_range<std::allocator<Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty>>(Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty *,Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty * const,std::allocator<Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty> &)
0x18000a974  mov     rdi, [rbx]
0x18000a977  test    rdi, rdi
0x18000a97a  jz      short loc_18000A9CD
0x18000a97c  mov     rbp, [rbx+8]
0x18000a980  jmp     short loc_18000A98C
0x18000a982  call    cs:__imp_WindowsDeleteString
0x18000a988  add     rdi, 18h
0x18000a98c  cmp     rdi, rbp
0x18000a98f  jz      short loc_18000A99B
0x18000a991  mov     rcx, [rdi]; string
0x18000a994  test    rcx, rcx
0x18000a997  jz      short loc_18000A988
0x18000a999  jmp     short loc_18000A982
0x18000a99b  mov     rcx, [rbx]; void *
0x18000a99e  mov     rax, [rbx+10h]
0x18000a9a2  sub     rax, rcx
0x18000a9a5  mov     [rsp+48h+arg_8], rcx
0x18000a9aa  sar     rax, 3
0x18000a9ae  imul    rax, r12
0x18000a9b2  lea     rdx, [rax+rax*2]
0x18000a9b6  shl     rdx, 3; unsigned __int64
0x18000a9ba  mov     [rsp+48h+arg_0], rdx
0x18000a9bf  cmp     rdx, 1000h
0x18000a9c6  jnb     short loc_18000AA31
0x18000a9c8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a9cd  lea     rax, [r14+r14*2]
0x18000a9d1  mov     [rbx], r15
0x18000a9d4  lea     rcx, [r15+rax*8]
0x18000a9d8  mov     [rbx+8], rcx
0x18000a9dc  lea     rax, [rsi+rsi*2]
0x18000a9e0  lea     rcx, [r15+rax*8]
0x18000a9e4  mov     [rbx+10h], rcx
0x18000a9e8  jmp     loc_18000A90A
0x18000a9ed  lea     rcx, aVectorTooLong; "vector too long"
0x18000a9f4  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000a9fb  mov     rcx, [rdx]
0x18000a9fe  mov     [r8], rcx
0x18000aa01  mov     qword ptr [rdx], 0
0x18000aa08  mov     ecx, [rdx+8]
0x18000aa0b  mov     [r8+8], ecx
0x18000aa0f  mov     eax, [rdx+0Ch]
0x18000aa12  mov     [r8+0Ch], eax
0x18000aa16  mov     eax, [rdx+10h]
0x18000aa19  mov     [r8+10h], eax
0x18000aa1d  mov     eax, [rdx+14h]
0x18000aa20  mov     [r8+14h], eax
0x18000aa24  add     r8, 18h
0x18000aa28  add     rdx, 18h
0x18000aa2c  jmp     loc_18000A960
0x18000aa31  lea     rdx, [rsp+48h+arg_0]; unsigned __int64 *
0x18000aa36  lea     rcx, [rsp+48h+arg_8]; void **
0x18000aa3b  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x18000aa40  mov     rdx, [rsp+48h+arg_0]
0x18000aa45  mov     rcx, [rsp+48h+arg_8]
0x18000aa4a  jmp     loc_18000A9C8
```
