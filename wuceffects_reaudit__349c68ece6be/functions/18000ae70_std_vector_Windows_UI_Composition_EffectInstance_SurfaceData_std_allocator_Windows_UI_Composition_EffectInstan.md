# std::vector<Windows::UI::Composition::EffectInstance::SurfaceData,std::allocator<Windows::UI::Composition::EffectInstance::SurfaceData>>::_Resize<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)

- ea: `0x18000ae70`
- end: `0x18000afcf`
- name: `??$_Resize@U_Value_init_tag@std@@@?$vector@USurfaceData@EffectInstance@Composition@UI@Windows@@V?$allocator@USurfaceData@EffectInstance@Composition@UI@Windows@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800160c4`

## callees

- `0x18000a88c`
- `0x18000ad40`
- `0x18000ae70`
- `0x18000afe0`
- `0x18000b00c`
- `0x180021ce0`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000af96`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000af96`

## pseudocode

```c
void __fastcall std::vector<Windows::UI::Composition::EffectInstance::SurfaceData>::_Resize<std::_Value_init_tag>(
        _QWORD *a1,
        unsigned __int64 a2)
{
  char *v3; // rcx
  unsigned __int64 v5; // rsi
  unsigned __int64 v6; // rax
  unsigned __int64 v7; // rdi
  SIZE_T size_of; // rax
  char *v9; // r15

  v3 = (char *)*a1;
  v5 = 0xAAAAAAAAAAAAAAABuLL * ((__int64)(a1[1] - (_QWORD)v3) >> 3);
  if ( a2 < v5 )
  {
    a1[1] = &v3[24 * a2];
  }
  else if ( a2 > v5 )
  {
    v6 = 0xAAAAAAAAAAAAAAABuLL * ((__int64)(a1[2] - (_QWORD)v3) >> 3);
    if ( a2 <= v6 )
    {
      a1[1] = std::_Uninitialized_value_construct_n<std::allocator<Windows::UI::Composition::EffectInstance::SurfaceData>>(
                a1[1],
                a2 - v5);
    }
    else
    {
      v7 = 0xAAAAAAAAAAAAAAALL;
      if ( a2 > 0xAAAAAAAAAAAAAAALL )
        std::_Xlength_error("vector too long");
      if ( v6 <= 0xAAAAAAAAAAAAAAALL - (v6 >> 1) )
      {
        v7 = (v6 >> 1) - 0x5555555555555555LL * ((__int64)(a1[2] - (_QWORD)v3) >> 3);
        if ( v7 < a2 )
          v7 = a2;
      }
      size_of = std::_Get_size_of_n<24>(v7);
      v9 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(size_of);
      std::_Uninitialized_value_construct_n<std::allocator<Windows::UI::Composition::EffectInstance::SurfaceData>>(
        &v9[24 * v5],
        a2 - v5);
      memmove_0(v9, (const void *)*a1, a1[1] - *a1);
      if ( *a1 )
        std::_Deallocate<16>(*a1, 8 * ((__int64)(a1[2] - *a1) >> 3));
      *a1 = v9;
      a1[1] = &v9[24 * a2];
      a1[2] = &v9[24 * v7];
    }
  }
}

```

## disassembly

```asm
0x18000ae70  mov     [rsp+arg_10], rbx
0x18000ae75  push    rbp
0x18000ae76  push    rsi
0x18000ae77  push    r14
0x18000ae79  sub     rsp, 20h
0x18000ae7d  mov     r14, rcx
0x18000ae80  mov     rbp, 0AAAAAAAAAAAAAAABh
0x18000ae8a  mov     rcx, [rcx]
0x18000ae8d  mov     rbx, rdx
0x18000ae90  mov     r8, [r14+8]
0x18000ae94  mov     rsi, r8
0x18000ae97  sub     rsi, rcx
0x18000ae9a  sar     rsi, 3
0x18000ae9e  imul    rsi, rbp
0x18000aea2  cmp     rdx, rsi
0x18000aea5  jb      loc_18000AF75
0x18000aeab  jbe     loc_18000AF67
0x18000aeb1  mov     rax, [r14+10h]
0x18000aeb5  sub     rax, rcx
0x18000aeb8  sar     rax, 3
0x18000aebc  imul    rax, rbp
0x18000aec0  cmp     rdx, rax
0x18000aec3  jbe     loc_18000AFBB
0x18000aec9  mov     [rsp+38h+arg_0], rdi
0x18000aece  mov     rdi, 0AAAAAAAAAAAAAAAh
0x18000aed8  cmp     rdx, rdi
0x18000aedb  ja      loc_18000AF8F
0x18000aee1  mov     rdx, rax
0x18000aee4  mov     [rsp+38h+arg_8], r15
0x18000aee9  shr     rdx, 1
0x18000aeec  mov     rcx, rdi
0x18000aeef  sub     rcx, rdx
0x18000aef2  cmp     rax, rcx
0x18000aef5  ja      short loc_18000AF02
0x18000aef7  lea     rdi, [rdx+rax]
0x18000aefb  cmp     rdi, rbx
0x18000aefe  cmovb   rdi, rbx
0x18000af02  mov     rcx, rdi
0x18000af05  call    ??$_Get_size_of_n@$0BI@@std@@YA_K_K@Z; std::_Get_size_of_n<24>(unsigned __int64)
0x18000af0a  mov     rcx, rax; dwBytes
0x18000af0d  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000af12  mov     rdx, rbx
0x18000af15  lea     rcx, [rsi+rsi*2]
0x18000af19  sub     rdx, rsi
0x18000af1c  mov     r15, rax
0x18000af1f  lea     rcx, [rax+rcx*8]
0x18000af23  call    ??$_Uninitialized_value_construct_n@V?$allocator@USurfaceData@EffectInstance@Composition@UI@Windows@@@std@@@std@@YAPEAUSurfaceData@EffectInstance@Composition@UI@Windows@@PEAU12345@_KAEAV?$allocator@USurfaceData@EffectInstance@Composition@UI@Windows@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<Windows::UI::Composition::EffectInstance::SurfaceData>>(Windows::UI::Composition::EffectInstance::SurfaceData *,unsigned __int64,std::allocator<Windows::UI::Composition::EffectInstance::SurfaceData> &)
0x18000af28  mov     rdx, [r14]; Src
0x18000af2b  mov     rcx, r15; void *
0x18000af2e  mov     r8, [r14+8]
0x18000af32  sub     r8, rdx; Size
0x18000af35  call    memmove_0
0x18000af3a  mov     rcx, [r14]
0x18000af3d  test    rcx, rcx
0x18000af40  jnz     short loc_18000AF9D
0x18000af42  mov     [r14], r15
0x18000af45  lea     rax, [rbx+rbx*2]
0x18000af49  lea     rcx, [r15+rax*8]
0x18000af4d  lea     rax, [rdi+rdi*2]
0x18000af51  mov     [r14+8], rcx
0x18000af55  mov     rdi, [rsp+38h+arg_0]
0x18000af5a  lea     rcx, [r15+rax*8]
0x18000af5e  mov     r15, [rsp+38h+arg_8]
0x18000af63  mov     [r14+10h], rcx
0x18000af67  mov     rbx, [rsp+38h+arg_10]
0x18000af6c  add     rsp, 20h
0x18000af70  pop     r14
0x18000af72  pop     rsi
0x18000af73  pop     rbp
0x18000af74  retn
0x18000af75  mov     rbx, [rsp+38h+arg_10]
0x18000af7a  lea     rax, [rdx+rdx*2]
0x18000af7e  lea     rcx, [rcx+rax*8]
0x18000af82  mov     [r14+8], rcx
0x18000af86  add     rsp, 20h
0x18000af8a  pop     r14
0x18000af8c  pop     rsi
0x18000af8d  pop     rbp
0x18000af8e  retn
0x18000af8f  lea     rcx, aVectorTooLong; "vector too long"
0x18000af96  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000af9d  mov     rax, [r14+10h]
0x18000afa1  sub     rax, rcx
0x18000afa4  sar     rax, 3
0x18000afa8  imul    rax, rbp
0x18000afac  lea     rdx, [rax+rax*2]
0x18000afb0  shl     rdx, 3
0x18000afb4  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000afb9  jmp     short loc_18000AF42
0x18000afbb  sub     rbx, rsi
0x18000afbe  mov     rcx, r8
0x18000afc1  mov     rdx, rbx
0x18000afc4  call    ??$_Uninitialized_value_construct_n@V?$allocator@USurfaceData@EffectInstance@Composition@UI@Windows@@@std@@@std@@YAPEAUSurfaceData@EffectInstance@Composition@UI@Windows@@PEAU12345@_KAEAV?$allocator@USurfaceData@EffectInstance@Composition@UI@Windows@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<Windows::UI::Composition::EffectInstance::SurfaceData>>(Windows::UI::Composition::EffectInstance::SurfaceData *,unsigned __int64,std::allocator<Windows::UI::Composition::EffectInstance::SurfaceData> &)
0x18000afc9  mov     [r14+8], rax
0x18000afcd  jmp     short loc_18000AF67
```
