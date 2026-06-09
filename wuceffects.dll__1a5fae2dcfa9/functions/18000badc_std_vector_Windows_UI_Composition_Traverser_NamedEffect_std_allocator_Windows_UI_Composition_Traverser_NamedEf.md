# std::vector<Windows::UI::Composition::Traverser::NamedEffect,std::allocator<Windows::UI::Composition::Traverser::NamedEffect>>::_Emplace_one_at_back<>(void)

- ea: `0x18000badc`
- end: `0x18000bc00`
- name: `??$_Emplace_one_at_back@$$V@?$vector@UNamedEffect@Traverser@Composition@UI@Windows@@V?$allocator@UNamedEffect@Traverser@Composition@UI@Windows@@@std@@@std@@AEAAAEAUNamedEffect@Traverser@Composition@UI@Windows@@XZ`
- size: `292`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180005ce0`

## callees

- `0x18000ad40`
- `0x18000afe0`
- `0x18000b2e8`
- `0x18000badc`
- `0x18000bc08`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000bbf9`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000bbf9`

## pseudocode

```c
_QWORD *__fastcall std::vector<Windows::UI::Composition::Traverser::NamedEffect>::_Emplace_one_at_back<>(_QWORD *a1)
{
  _QWORD *v1; // r8
  _QWORD *v3; // rdi
  __int64 v4; // rsi
  __int64 v5; // r14
  unsigned __int64 v6; // rbp
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // rcx
  SIZE_T size_of; // rax
  __int64 v10; // r8
  _QWORD *v11; // r14
  _QWORD *v12; // rdx
  _QWORD *v13; // rcx
  __int64 v14; // r11
  _QWORD *result; // rax

  v1 = (_QWORD *)a1[2];
  v3 = (_QWORD *)a1[1];
  if ( v3 == v1 )
  {
    v4 = 0xAAAAAAAAAAAAAAALL;
    v5 = ((__int64)v3 - *a1) / 24;
    if ( v5 == 0xAAAAAAAAAAAAAAALL )
      std::_Xlength_error("vector too long");
    v6 = v5 + 1;
    v7 = 0xAAAAAAAAAAAAAAABuLL * (((__int64)v1 - *a1) >> 3);
    v8 = v7 >> 1;
    if ( v7 <= 0xAAAAAAAAAAAAAAALL - (v7 >> 1) )
    {
      v4 = v8 + v7;
      if ( v8 + v7 < v6 )
        v4 = v5 + 1;
    }
    size_of = std::_Get_size_of_n<24>(v4);
    v10 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
    v11 = (_QWORD *)(v10 + 24 * v5);
    v11[2] = 0;
    *v11 = 0;
    v11[1] = 0;
    v12 = (_QWORD *)a1[1];
    v13 = (_QWORD *)*a1;
    if ( v3 != v12 )
    {
      std::_Uninitialized_move<Windows::UI::Composition::Traverser::NamedEffect *>(v13, v3, v10);
      v12 = (_QWORD *)a1[1];
      v10 = (__int64)(v11 + 3);
      v13 = v3;
    }
    std::_Uninitialized_move<Windows::UI::Composition::Traverser::NamedEffect *>(v13, v12, v10);
    std::vector<Windows::UI::Composition::Traverser::NamedEffect>::_Change_array(a1, v14, v6, v4);
    return v11;
  }
  else
  {
    v3[2] = 0;
    *v3 = 0;
    v3[1] = 0;
    result = (_QWORD *)a1[1];
    a1[1] = result + 3;
  }
  return result;
}

```

## disassembly

```asm
0x18000badc  push    rbx
0x18000bade  push    rbp
0x18000badf  push    rsi
0x18000bae0  push    rdi
0x18000bae1  push    r14
0x18000bae3  sub     rsp, 20h
0x18000bae7  mov     r8, [rcx+10h]
0x18000baeb  mov     rbx, rcx
0x18000baee  mov     rdi, [rcx+8]
0x18000baf2  cmp     rdi, r8
0x18000baf5  jnz     loc_18000BBD7
0x18000bafb  mov     rcx, rdi
0x18000bafe  mov     rax, 2AAAAAAAAAAAAAABh
0x18000bb08  sub     rcx, [rbx]
0x18000bb0b  mov     rsi, 0AAAAAAAAAAAAAAAh
0x18000bb15  imul    rcx
0x18000bb18  mov     r14, rdx
0x18000bb1b  sar     r14, 2
0x18000bb1f  mov     rax, r14
0x18000bb22  shr     rax, 3Fh
0x18000bb26  add     r14, rax
0x18000bb29  cmp     r14, rsi
0x18000bb2c  jz      loc_18000BBF2
0x18000bb32  sub     r8, [rbx]
0x18000bb35  lea     rbp, [r14+1]
0x18000bb39  sar     r8, 3
0x18000bb3d  mov     rax, 0AAAAAAAAAAAAAAABh
0x18000bb47  imul    r8, rax
0x18000bb4b  mov     rax, rsi
0x18000bb4e  mov     rcx, r8
0x18000bb51  shr     rcx, 1
0x18000bb54  sub     rax, rcx
0x18000bb57  cmp     r8, rax
0x18000bb5a  ja      short loc_18000BB67
0x18000bb5c  lea     rsi, [rcx+r8]
0x18000bb60  cmp     rsi, rbp
0x18000bb63  cmovb   rsi, rbp
0x18000bb67  mov     rcx, rsi
0x18000bb6a  call    ??$_Get_size_of_n@$0BI@@std@@YA_K_K@Z; std::_Get_size_of_n<24>(unsigned __int64)
0x18000bb6f  mov     rcx, rax; dwBytes
0x18000bb72  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000bb77  lea     rcx, [r14+r14*2]
0x18000bb7b  mov     r11, rax
0x18000bb7e  mov     r8, r11
0x18000bb81  lea     r14, [rax+rcx*8]
0x18000bb85  xor     eax, eax
0x18000bb87  mov     [r14+10h], rax
0x18000bb8b  mov     [r14], rax
0x18000bb8e  mov     [r14+8], rax
0x18000bb92  mov     rdx, [rbx+8]
0x18000bb96  mov     rcx, [rbx]
0x18000bb99  cmp     rdi, rdx
0x18000bb9c  jnz     short loc_18000BBC2
0x18000bb9e  call    ??$_Uninitialized_move@PEAUNamedEffect@Traverser@Composition@UI@Windows@@V?$allocator@UNamedEffect@Traverser@Composition@UI@Windows@@@std@@@std@@YAPEAUNamedEffect@Traverser@Composition@UI@Windows@@QEAU12345@0PEAU12345@AEAV?$allocator@UNamedEffect@Traverser@Composition@UI@Windows@@@0@@Z; std::_Uninitialized_move<Windows::UI::Composition::Traverser::NamedEffect *>(Windows::UI::Composition::Traverser::NamedEffect * const,Windows::UI::Composition::Traverser::NamedEffect * const,Windows::UI::Composition::Traverser::NamedEffect *,std::allocator<Windows::UI::Composition::Traverser::NamedEffect> &)
0x18000bba3  mov     r9, rsi
0x18000bba6  mov     r8, rbp
0x18000bba9  mov     rcx, rbx
0x18000bbac  mov     rdx, r11
0x18000bbaf  call    ?_Change_array@?$vector@UNamedEffect@Traverser@Composition@UI@Windows@@V?$allocator@UNamedEffect@Traverser@Composition@UI@Windows@@@std@@@std@@AEAAXQEAUNamedEffect@Traverser@Composition@UI@Windows@@_K1@Z; std::vector<Windows::UI::Composition::Traverser::NamedEffect>::_Change_array(Windows::UI::Composition::Traverser::NamedEffect * const,unsigned __int64,unsigned __int64)
0x18000bbb4  mov     rax, r14
0x18000bbb7  add     rsp, 20h
0x18000bbbb  pop     r14
0x18000bbbd  pop     rdi
0x18000bbbe  pop     rsi
0x18000bbbf  pop     rbp
0x18000bbc0  pop     rbx
0x18000bbc1  retn
0x18000bbc2  mov     rdx, rdi
0x18000bbc5  call    ??$_Uninitialized_move@PEAUNamedEffect@Traverser@Composition@UI@Windows@@V?$allocator@UNamedEffect@Traverser@Composition@UI@Windows@@@std@@@std@@YAPEAUNamedEffect@Traverser@Composition@UI@Windows@@QEAU12345@0PEAU12345@AEAV?$allocator@UNamedEffect@Traverser@Composition@UI@Windows@@@0@@Z; std::_Uninitialized_move<Windows::UI::Composition::Traverser::NamedEffect *>(Windows::UI::Composition::Traverser::NamedEffect * const,Windows::UI::Composition::Traverser::NamedEffect * const,Windows::UI::Composition::Traverser::NamedEffect *,std::allocator<Windows::UI::Composition::Traverser::NamedEffect> &)
0x18000bbca  mov     rdx, [rbx+8]
0x18000bbce  lea     r8, [r14+18h]
0x18000bbd2  mov     rcx, rdi
0x18000bbd5  jmp     short loc_18000BB9E
0x18000bbd7  xor     eax, eax
0x18000bbd9  mov     [rdi+10h], rax
0x18000bbdd  mov     [rdi], rax
0x18000bbe0  mov     [rdi+8], rax
0x18000bbe4  mov     rax, [rcx+8]
0x18000bbe8  lea     rdx, [rax+18h]
0x18000bbec  mov     [rcx+8], rdx
0x18000bbf0  jmp     short loc_18000BBB7
0x18000bbf2  lea     rcx, aVectorTooLong; "vector too long"
0x18000bbf9  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
