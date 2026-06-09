# std::vector<Microsoft::WRL::ComPtr<Windows::UI::Composition::CSingleInputCompositeEffect>,std::allocator<Microsoft::WRL::ComPtr<Windows::UI::Composition::CSingleInputCompositeEffect>>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<Windows::UI::Composition::CSingleInputCompositeEffect> &>(Microsoft::WRL::ComPtr<Windows::UI::Composition::CSingleInputCompositeEffect> * const,Microsoft::WRL::ComPtr<Windows::UI::Composition::CSingleInputCompositeEffect> &)

- ea: `0x180004378`
- end: `0x180004483`
- name: `??$_Emplace_reallocate@AEAV?$ComPtr@VCSingleInputCompositeEffect@Composition@UI@Windows@@@WRL@Microsoft@@@?$vector@V?$ComPtr@VCSingleInputCompositeEffect@Composition@UI@Windows@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VCSingleInputCompositeEffect@Composition@UI@Windows@@@WRL@Microsoft@@@std@@@std@@AEAAPEAV?$ComPtr@VCSingleInputCompositeEffect@Composition@UI@Windows@@@WRL@Microsoft@@QEAV234@AEAV234@@Z`
- size: `267`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180004550`

## callees

- `0x180004378`
- `0x18000a88c`
- `0x18000ad10`
- `0x18000ad40`
- `0x18000c2f8`
- `0x18000dae4`
- `0x180019d18`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800043b1`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800043b1`

## pseudocode

```c
_QWORD *__fastcall std::vector<Microsoft::WRL::ComPtr<Windows::UI::Composition::CSingleInputCompositeEffect>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<Windows::UI::Composition::CSingleInputCompositeEffect> &>(
        __int64 *a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 v3; // rdi
  __int64 v5; // rax
  unsigned __int64 v8; // r15
  __int64 v9; // r14
  unsigned __int64 v10; // rcx
  __int64 v11; // r14
  unsigned __int64 v12; // rdx
  SIZE_T size_of; // rax
  __int64 v14; // rsi
  _QWORD *v15; // r14
  __int64 v16; // rdx
  _QWORD *v17; // r8
  __int64 v18; // rcx
  _QWORD *result; // rax

  v3 = 0x1FFFFFFFFFFFFFFFLL;
  v5 = (a1[1] - *a1) >> 3;
  if ( v5 == 0x1FFFFFFFFFFFFFFFLL )
    std::_Xlength_error("vector too long");
  v8 = v5 + 1;
  v9 = a2 - *a1;
  v10 = (a1[2] - *a1) >> 3;
  v11 = v9 >> 3;
  v12 = v10 >> 1;
  if ( v10 <= 0x1FFFFFFFFFFFFFFFLL - (v10 >> 1) )
  {
    v3 = v12 + v10;
    if ( v12 + v10 < v8 )
      v3 = v5 + 1;
  }
  size_of = std::_Get_size_of_n<8>(v3);
  v14 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
  v15 = (_QWORD *)(v14 + 8 * v11);
  *v15 = *a3;
  Microsoft::WRL::ComPtr<Windows::Graphics::Effects::IGraphicsEffect>::InternalAddRef(v15);
  v16 = a1[1];
  v17 = (_QWORD *)v14;
  v18 = *a1;
  if ( a2 != v16 )
  {
    std::_Uninitialized_move<Microsoft::WRL::ComPtr<Windows::UI::Composition::CSingleInputCompositeEffect> *,std::allocator<Microsoft::WRL::ComPtr<Windows::UI::Composition::CSingleInputCompositeEffect>>>(
      v18,
      a2,
      v14);
    v16 = a1[1];
    v17 = v15 + 1;
    v18 = a2;
  }
  std::_Uninitialized_move<Microsoft::WRL::ComPtr<Windows::UI::Composition::CSingleInputCompositeEffect> *,std::allocator<Microsoft::WRL::ComPtr<Windows::UI::Composition::CSingleInputCompositeEffect>>>(
    v18,
    v16,
    v17);
  if ( *a1 )
  {
    std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<Windows::UI::Composition::CSingleInputCompositeEffect>>>(
      *a1,
      a1[1]);
    std::_Deallocate<16>(*a1, (a1[2] - *a1) & 0xFFFFFFFFFFFFFFF8uLL);
  }
  *a1 = v14;
  a1[1] = v14 + 8 * v8;
  result = v15;
  a1[2] = v14 + 8 * v3;
  return result;
}

```

## disassembly

```asm
0x180004378  push    rbx
0x18000437a  push    rbp
0x18000437b  push    rsi
0x18000437c  push    rdi
0x18000437d  push    r12
0x18000437f  push    r14
0x180004381  push    r15
0x180004383  sub     rsp, 20h
0x180004387  mov     rax, [rcx+8]
0x18000438b  mov     rdi, 1FFFFFFFFFFFFFFFh
0x180004395  sub     rax, [rcx]
0x180004398  mov     r12, r8
0x18000439b  sar     rax, 3
0x18000439f  mov     rbp, rdx
0x1800043a2  mov     rbx, rcx
0x1800043a5  cmp     rax, rdi
0x1800043a8  jnz     short loc_1800043B8
0x1800043aa  lea     rcx, aVectorTooLong; "vector too long"
0x1800043b1  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1800043b8  lea     r15, [rax+1]
0x1800043bc  mov     r14, rbp
0x1800043bf  sub     r14, [rcx]
0x1800043c2  mov     rax, rdi
0x1800043c5  mov     rcx, [rcx+10h]
0x1800043c9  sub     rcx, [rbx]
0x1800043cc  sar     rcx, 3
0x1800043d0  mov     rdx, rcx
0x1800043d3  sar     r14, 3
0x1800043d7  shr     rdx, 1
0x1800043da  sub     rax, rdx
0x1800043dd  cmp     rcx, rax
0x1800043e0  ja      short loc_1800043ED
0x1800043e2  lea     rdi, [rdx+rcx]
0x1800043e6  cmp     rdi, r15
0x1800043e9  cmovb   rdi, r15
0x1800043ed  mov     rcx, rdi
0x1800043f0  call    ??$_Get_size_of_n@$07@std@@YA_K_K@Z; std::_Get_size_of_n<8>(unsigned __int64)
0x1800043f5  mov     rcx, rax; dwBytes
0x1800043f8  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800043fd  mov     rcx, [r12]
0x180004401  mov     rsi, rax
0x180004404  lea     r14, [rax+r14*8]
0x180004408  mov     [r14], rcx
0x18000440b  mov     rcx, r14
0x18000440e  call    ?InternalAddRef@?$ComPtr@UIGraphicsEffect@Effects@Graphics@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Graphics::Effects::IGraphicsEffect>::InternalAddRef(void)
0x180004413  mov     rdx, [rbx+8]
0x180004417  mov     r8, rsi
0x18000441a  mov     rcx, [rbx]
0x18000441d  cmp     rbp, rdx
0x180004420  jz      short loc_180004435
0x180004422  mov     rdx, rbp
0x180004425  call    ??$_Uninitialized_move@PEAV?$ComPtr@VCSingleInputCompositeEffect@Composition@UI@Windows@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VCSingleInputCompositeEffect@Composition@UI@Windows@@@WRL@Microsoft@@@std@@@std@@YAPEAV?$ComPtr@VCSingleInputCompositeEffect@Composition@UI@Windows@@@WRL@Microsoft@@QEAV123@0PEAV123@AEAV?$allocator@V?$ComPtr@VCSingleInputCompositeEffect@Composition@UI@Windows@@@WRL@Microsoft@@@0@@Z; std::_Uninitialized_move<Microsoft::WRL::ComPtr<Windows::UI::Composition::CSingleInputCompositeEffect> *,std::allocator<Microsoft::WRL::ComPtr<Windows::UI::Composition::CSingleInputCompositeEffect>>>(Microsoft::WRL::ComPtr<Windows::UI::Composition::CSingleInputCompositeEffect> * const,Microsoft::WRL::ComPtr<Windows::UI::Composition::CSingleInputCompositeEffect> * const,Microsoft::WRL::ComPtr<Windows::UI::Composition::CSingleInputCompositeEffect> *,std::allocator<Microsoft::WRL::ComPtr<Windows::UI::Composition::CSingleInputCompositeEffect>> &)
0x18000442a  mov     rdx, [rbx+8]
0x18000442e  lea     r8, [r14+8]
0x180004432  mov     rcx, rbp
0x180004435  call    ??$_Uninitialized_move@PEAV?$ComPtr@VCSingleInputCompositeEffect@Composition@UI@Windows@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VCSingleInputCompositeEffect@Composition@UI@Windows@@@WRL@Microsoft@@@std@@@std@@YAPEAV?$ComPtr@VCSingleInputCompositeEffect@Composition@UI@Windows@@@WRL@Microsoft@@QEAV123@0PEAV123@AEAV?$allocator@V?$ComPtr@VCSingleInputCompositeEffect@Composition@UI@Windows@@@WRL@Microsoft@@@0@@Z; std::_Uninitialized_move<Microsoft::WRL::ComPtr<Windows::UI::Composition::CSingleInputCompositeEffect> *,std::allocator<Microsoft::WRL::ComPtr<Windows::UI::Composition::CSingleInputCompositeEffect>>>(Microsoft::WRL::ComPtr<Windows::UI::Composition::CSingleInputCompositeEffect> * const,Microsoft::WRL::ComPtr<Windows::UI::Composition::CSingleInputCompositeEffect> * const,Microsoft::WRL::ComPtr<Windows::UI::Composition::CSingleInputCompositeEffect> *,std::allocator<Microsoft::WRL::ComPtr<Windows::UI::Composition::CSingleInputCompositeEffect>> &)
0x18000443a  mov     rcx, [rbx]
0x18000443d  test    rcx, rcx
0x180004440  jz      short loc_18000445E
0x180004442  mov     rdx, [rbx+8]
0x180004446  call    ??$_Destroy_range@V?$allocator@V?$ComPtr@VCSingleInputCompositeEffect@Composition@UI@Windows@@@WRL@Microsoft@@@std@@@std@@YAXPEAV?$ComPtr@VCSingleInputCompositeEffect@Composition@UI@Windows@@@WRL@Microsoft@@QEAV123@AEAV?$allocator@V?$ComPtr@VCSingleInputCompositeEffect@Composition@UI@Windows@@@WRL@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<Windows::UI::Composition::CSingleInputCompositeEffect>>>(Microsoft::WRL::ComPtr<Windows::UI::Composition::CSingleInputCompositeEffect> *,Microsoft::WRL::ComPtr<Windows::UI::Composition::CSingleInputCompositeEffect> * const,std::allocator<Microsoft::WRL::ComPtr<Windows::UI::Composition::CSingleInputCompositeEffect>> &)
0x18000444b  mov     rdx, [rbx+10h]
0x18000444f  sub     rdx, [rbx]
0x180004452  mov     rcx, [rbx]
0x180004455  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180004459  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000445e  lea     rcx, [rsi+r15*8]
0x180004462  mov     [rbx], rsi
0x180004465  mov     [rbx+8], rcx
0x180004469  mov     rax, r14
0x18000446c  lea     rcx, [rsi+rdi*8]
0x180004470  mov     [rbx+10h], rcx
0x180004474  add     rsp, 20h
0x180004478  pop     r15
0x18000447a  pop     r14
0x18000447c  pop     r12
0x18000447e  pop     rdi
0x18000447f  pop     rsi
0x180004480  pop     rbp
0x180004481  pop     rbx
0x180004482  retn
```
