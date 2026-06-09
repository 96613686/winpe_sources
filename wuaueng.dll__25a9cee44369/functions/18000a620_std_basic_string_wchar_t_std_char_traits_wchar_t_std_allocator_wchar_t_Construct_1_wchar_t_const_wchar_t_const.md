# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)

- ea: `0x18000a620`
- end: `0x18000a6d7`
- name: `??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z`
- size: `183`
- prototype: `__int64 __fastcall(__int64, const void *, unsigned __int64)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x180005524`
- `0x180008148`
- `0x180008848`
- `0x180008ebc`
- `0x180009a60`
- `0x18000a430`

## callees

- `0x18000a620`
- `0x18000a6e0`
- `0x18000a7c8`
- `0x180015df0`

## pseudocode

```c
__int64 __fastcall std::wstring::_Construct<1,wchar_t const *>(__int64 a1, const void *a2, unsigned __int64 a3)
{
  __int64 v5; // rdx
  _QWORD *v6; // rsi
  __int64 v7; // rbx
  __int64 result; // rax
  _QWORD *v9; // rax
  unsigned __int64 v10; // rcx
  _QWORD *v11; // rdi
  size_t v12; // rbx
  unsigned __int64 v13[5]; // [rsp+20h] [rbp-28h] BYREF

  v5 = 0x7FFFFFFFFFFFFFFELL;
  v6 = (_QWORD *)a1;
  if ( a3 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlen_string();
  if ( a3 > 7 )
  {
    if ( (a3 | 7) <= 0x7FFFFFFFFFFFFFFELL )
    {
      a1 = 10;
      v5 = a3 | 7;
      if ( (a3 | 7) < 0xA )
        v5 = 10;
    }
    v13[0] = v5;
    v9 = std::wstring::_Allocate_for_capacity<0>(a1, v13);
    v10 = v13[0];
    v6[2] = a3;
    v11 = v9;
    v6[3] = v10;
    v12 = 2 * a3;
    *v6 = v9;
    memmove(v9, a2, v12);
    result = 0;
    *(_WORD *)((char *)v11 + v12) = 0;
  }
  else
  {
    *(_QWORD *)(a1 + 16) = a3;
    v7 = 2 * a3;
    *(_QWORD *)(a1 + 24) = 7;
    memmove((void *)a1, a2, 2 * a3);
    result = 0;
    *(_WORD *)((char *)v6 + v7) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000a620  mov     [rsp+arg_18], rbx
0x18000a625  push    rbp
0x18000a626  push    rsi
0x18000a627  push    rdi
0x18000a628  sub     rsp, 30h
0x18000a62c  mov     rbp, rdx
0x18000a62f  mov     rbx, r8
0x18000a632  mov     rdx, 7FFFFFFFFFFFFFFEh
0x18000a63c  mov     rsi, rcx
0x18000a63f  cmp     r8, rdx
0x18000a642  ja      loc_18000A6D1
0x18000a648  cmp     rbx, 7
0x18000a64c  ja      short loc_18000A670
0x18000a64e  mov     [rcx+10h], rbx
0x18000a652  mov     rdx, rbp; Src
0x18000a655  add     rbx, rbx
0x18000a658  mov     qword ptr [rcx+18h], 7
0x18000a660  mov     r8, rbx; Size
0x18000a663  call    memmove
0x18000a668  xor     eax, eax
0x18000a66a  mov     [rbx+rsi], ax
0x18000a66e  jmp     short loc_18000A6C4
0x18000a670  mov     rax, rbx
0x18000a673  or      rax, 7
0x18000a677  cmp     rax, rdx
0x18000a67a  ja      short loc_18000A68B
0x18000a67c  mov     ecx, 0Ah
0x18000a681  mov     rdx, rax
0x18000a684  cmp     rax, rcx
0x18000a687  cmovb   rdx, rcx
0x18000a68b  mov     [rsp+48h+var_28], rdx
0x18000a690  lea     rdx, [rsp+48h+var_28]
0x18000a695  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@CAPEA_WAEAV?$allocator@_W@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<wchar_t> &,unsigned __int64 &)
0x18000a69a  mov     rcx, [rsp+48h+var_28]
0x18000a69f  mov     rdx, rbp; Src
0x18000a6a2  mov     [rsi+10h], rbx
0x18000a6a6  mov     rdi, rax
0x18000a6a9  mov     [rsi+18h], rcx
0x18000a6ad  add     rbx, rbx
0x18000a6b0  mov     rcx, rax; void *
0x18000a6b3  mov     [rsi], rax
0x18000a6b6  mov     r8, rbx; Size
0x18000a6b9  call    memmove
0x18000a6be  xor     eax, eax
0x18000a6c0  mov     [rbx+rdi], ax
0x18000a6c4  mov     rbx, [rsp+48h+arg_18]
0x18000a6c9  add     rsp, 30h
0x18000a6cd  pop     rdi
0x18000a6ce  pop     rsi
0x18000a6cf  pop     rbp
0x18000a6d0  retn
0x18000a6d1  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
