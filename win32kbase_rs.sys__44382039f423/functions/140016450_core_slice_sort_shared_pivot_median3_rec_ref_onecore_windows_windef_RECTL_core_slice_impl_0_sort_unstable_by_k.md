# core::slice::sort::shared::pivot::median3_rec_ref$_onecore_windows::windef::_RECTL__core::slice::impl$0::sort_unstable_by_key::closure_env$0_ref$_onecore_windows::windef::_RECTL__i32_rgncore::impl$1::subtract_complex::closure_env$0___

- ea: `0x140016450`
- end: `0x140016504`
- name: `core::slice::sort::shared::pivot::median3_rec_ref$_onecore_windows::windef::_RECTL__core::slice::impl$0::sort_unstable_by_key::closure_env$0_ref$_onecore_windows::windef::_RECTL__i32_rgncore::impl$1::subtract_complex::closure_env$0___`
- size: `180`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140016450`
- `0x140016650`

## callees

- `0x140016450`

## pseudocode

```c
__int64 __fastcall core::slice::sort::shared::pivot::median3_rec_ref__onecore_windows::windef::_RECTL__core::slice::impl_0::sort_unstable_by_key::closure_env_0_ref__onecore_windows::windef::_RECTL__i32_rgncore::impl_1::subtract_complex::closure_env_0___(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned __int64 a4)
{
  unsigned __int64 v6; // r9
  __int64 v7; // rbx
  __int64 v8; // r14
  __int64 v9; // r12
  __int64 v10; // rax
  int v11; // eax
  int v12; // edx
  bool v13; // r8
  int v14; // r9d
  char v15; // al

  if ( a4 >= 8 )
  {
    v6 = a4 >> 3;
    v7 = 32 * v6;
    v8 = 56 * v6;
    v9 = core::slice::sort::shared::pivot::median3_rec_ref__onecore_windows::windef::_RECTL__core::slice::impl_0::sort_unstable_by_key::closure_env_0_ref__onecore_windows::windef::_RECTL__i32_rgncore::impl_1::subtract_complex::closure_env_0___(
           a1,
           a1 + 32 * v6,
           a1 + 56 * v6);
    a2 = core::slice::sort::shared::pivot::median3_rec_ref__onecore_windows::windef::_RECTL__core::slice::impl_0::sort_unstable_by_key::closure_env_0_ref__onecore_windows::windef::_RECTL__i32_rgncore::impl_1::subtract_complex::closure_env_0___(
           a2,
           a2 + v7,
           a2 + v8);
    v10 = core::slice::sort::shared::pivot::median3_rec_ref__onecore_windows::windef::_RECTL__core::slice::impl_0::sort_unstable_by_key::closure_env_0_ref__onecore_windows::windef::_RECTL__i32_rgncore::impl_1::subtract_complex::closure_env_0___(
            a3,
            a3 + v7,
            a3 + v8);
    a1 = v9;
    a3 = v10;
  }
  v11 = *(_DWORD *)(*(_QWORD *)a1 + 4LL);
  v12 = *(_DWORD *)(*(_QWORD *)a2 + 4LL);
  v13 = v11 < v12;
  v14 = *(_DWORD *)(*(_QWORD *)a3 + 4LL);
  v15 = (v11 < v12) ^ (v11 < v14);
  if ( v13 != v12 < v14 )
    a2 = a3;
  if ( v15 )
    return a1;
  return a2;
}

```

## disassembly

```asm
0x140016450  push    r15
0x140016452  push    r14
0x140016454  push    r12
0x140016456  push    rsi
0x140016457  push    rdi
0x140016458  push    rbx
0x140016459  sub     rsp, 28h
0x14001645d  mov     rdi, r8
0x140016460  mov     rsi, rdx
0x140016463  cmp     r9, 8
0x140016467  jb      short loc_1400164BE
0x140016469  shr     r9, 3
0x14001646d  mov     rbx, r9
0x140016470  shl     rbx, 5
0x140016474  lea     rdx, [rcx+rbx]
0x140016478  imul    r14, r9, 38h ; '8'
0x14001647c  lea     r8, [rcx+r14]
0x140016480  mov     r15, r9
0x140016483  call    core__slice__sort__shared__pivot__median3_rec_ref$_onecore_windows__windef___RECTL__core__slice__impl$0__sort_unstable_by_key__closure_env$0_ref$_onecore_windows__windef___RECTL__i32_rgncore__impl$1__subtract_complex__closure_env$0___
0x140016488  mov     r12, rax
0x14001648b  lea     rdx, [rsi+rbx]
0x14001648f  lea     r8, [rsi+r14]
0x140016493  mov     rcx, rsi
0x140016496  mov     r9, r15
0x140016499  call    core__slice__sort__shared__pivot__median3_rec_ref$_onecore_windows__windef___RECTL__core__slice__impl$0__sort_unstable_by_key__closure_env$0_ref$_onecore_windows__windef___RECTL__i32_rgncore__impl$1__subtract_complex__closure_env$0___
0x14001649e  mov     rsi, rax
0x1400164a1  add     rbx, rdi
0x1400164a4  add     r14, rdi
0x1400164a7  mov     rcx, rdi
0x1400164aa  mov     rdx, rbx
0x1400164ad  mov     r8, r14
0x1400164b0  mov     r9, r15
0x1400164b3  call    core__slice__sort__shared__pivot__median3_rec_ref$_onecore_windows__windef___RECTL__core__slice__impl$0__sort_unstable_by_key__closure_env$0_ref$_onecore_windows__windef___RECTL__i32_rgncore__impl$1__subtract_complex__closure_env$0___
0x1400164b8  mov     rcx, r12
0x1400164bb  mov     rdi, rax
0x1400164be  mov     rax, [rcx]
0x1400164c1  mov     rdx, [rsi]
0x1400164c4  mov     eax, [rax+4]
0x1400164c7  mov     edx, [rdx+4]
0x1400164ca  cmp     eax, edx
0x1400164cc  setl    r8b
0x1400164d0  mov     r9, [rdi]
0x1400164d3  mov     r9d, [r9+4]
0x1400164d7  cmp     eax, r9d
0x1400164da  setl    al
0x1400164dd  xor     al, r8b
0x1400164e0  cmp     edx, r9d
0x1400164e3  setl    dl
0x1400164e6  xor     dl, r8b
0x1400164e9  cmovnz  rsi, rdi
0x1400164ed  test    al, al
0x1400164ef  cmovnz  rsi, rcx
0x1400164f3  mov     rax, rsi
0x1400164f6  add     rsp, 28h
0x1400164fa  pop     rbx
0x1400164fb  pop     rdi
0x1400164fc  pop     rsi
0x1400164fd  pop     r12
0x1400164ff  pop     r14
0x140016501  pop     r15
0x140016503  retn
```
