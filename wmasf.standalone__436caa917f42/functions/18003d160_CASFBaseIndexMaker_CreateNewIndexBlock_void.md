# CASFBaseIndexMaker::CreateNewIndexBlock(void)

- ea: `0x18003d160`
- end: `0x18003d2fc`
- name: `?CreateNewIndexBlock@CASFBaseIndexMaker@@MEAAJXZ`
- size: `412`
- prototype: `__int64 __fastcall(CASFBaseIndexMaker *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800015d0`
- `0x18002f694`
- `0x18002f704`
- `0x18003d160`
- `0x18003d80c`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFBaseIndexMaker::CreateNewIndexBlock(CASFBaseIndexMaker *this)
{
  int v2; // r14d
  unsigned int i; // esi
  __int64 Ptr; // rdi
  __int64 v5; // r11
  unsigned int v6; // r15d
  unsigned __int64 v7; // rcx
  unsigned __int64 v8; // r11
  __int64 v9; // r9
  __int64 v11; // rdx
  unsigned int v12; // eax
  unsigned int j; // r10d
  __int64 v14; // rax
  int v15; // r10d
  __int64 v16; // [rsp+30h] [rbp-38h] BYREF

  v16 = 0;
  v2 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 11) + 168LL))(*((_QWORD *)this + 11), &v16);
  if ( v2 >= 0 )
  {
    for ( i = 0; i < *((_DWORD *)this + 3250); ++i )
    {
      Ptr = CTDynArray<CASFBaseIndexMaker::STREAM_INFO,20>::GetPtr((char *)this + 352, i);
      if ( !Ptr )
        return 2147549183LL;
      if ( *(_WORD *)(Ptr + 4) == 255 )
      {
        v5 = 0;
      }
      else
      {
        v5 = -1;
        v6 = 0;
        *(_QWORD *)(Ptr + 576) = Ptr + 40;
        for ( *(_DWORD *)(Ptr + 584) = 0; v6 < *(_DWORD *)(Ptr + 592); v5 = v7 )
        {
          v7 = *(_QWORD *)(CTDynArray<CASFBaseIndexMaker::SEEK_POINT,20>::GetNextPtr(Ptr + 40) + 16);
          if ( v7 >= v8 )
            v7 = v8;
          ++v6;
        }
      }
      v9 = 0;
      if ( v5 != -1 )
        v9 = v5;
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD, __int64))(*(_QWORD *)v16 + 80LL))(
        v16,
        *(unsigned __int16 *)(Ptr + 2),
        *(unsigned __int16 *)(Ptr + 4),
        v9);
    }
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v16 + 96LL))(v16, *((unsigned int *)this + 18));
    if ( (int)CTSparseBlock<unsigned long,IASFIndexBlock *,20,0>::InsertValue((char *)this + 128, v11, v16) >= 0 )
    {
      v12 = *((_DWORD *)this + 86) + 1;
      if ( v12 <= 1 )
        v12 = 1;
      *((_DWORD *)this + 86) = v12;
    }
    for ( j = 0; j < *((_DWORD *)this + 3250); ++*(_DWORD *)(v14 + 12) )
    {
      v14 = CTDynArray<CASFBaseIndexMaker::STREAM_INFO,20>::GetPtr((char *)this + 352, j);
      j = v15 + 1;
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18003d160  mov     r11, rsp
0x18003d163  mov     [r11+10h], rbx
0x18003d167  mov     [r11+18h], rbp
0x18003d16b  push    rsi
0x18003d16c  push    rdi
0x18003d16d  push    r13
0x18003d16f  push    r14
0x18003d171  push    r15
0x18003d173  sub     rsp, 40h
0x18003d177  mov     rax, cs:__security_cookie
0x18003d17e  xor     rax, rsp
0x18003d181  mov     [rsp+68h+var_30], rax
0x18003d186  mov     rbx, rcx
0x18003d189  mov     qword ptr [r11-38h], 0
0x18003d191  mov     rcx, [rcx+58h]
0x18003d195  lea     rdx, [r11-38h]
0x18003d199  mov     rax, [rcx]
0x18003d19c  mov     rax, [rax+0A8h]
0x18003d1a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d1a8  mov     r14d, eax
0x18003d1ab  test    eax, eax
0x18003d1ad  js      loc_18003D2D3
0x18003d1b3  xor     esi, esi
0x18003d1b5  lea     r13d, [rsi+1]
0x18003d1b9  cmp     esi, [rbx+32C8h]
0x18003d1bf  jnb     loc_18003D26A
0x18003d1c5  lea     rcx, [rbx+160h]
0x18003d1cc  mov     edx, esi
0x18003d1ce  call    ?GetPtr@?$CTDynArray@USTREAM_INFO@CASFBaseIndexMaker@@$0BE@@@QEAAPEAUSTREAM_INFO@CASFBaseIndexMaker@@K@Z; CTDynArray<CASFBaseIndexMaker::STREAM_INFO,20>::GetPtr(ulong)
0x18003d1d3  mov     rdi, rax
0x18003d1d6  test    rax, rax
0x18003d1d9  jz      loc_18003D263
0x18003d1df  mov     eax, 0FFh
0x18003d1e4  cmp     ax, [rdi+4]
0x18003d1e8  jnz     short loc_18003D1EF
0x18003d1ea  xor     r11d, r11d
0x18003d1ed  jmp     short loc_18003D236
0x18003d1ef  lea     rbp, [rdi+28h]
0x18003d1f3  or      r11, 0FFFFFFFFFFFFFFFFh
0x18003d1f7  xor     r15d, r15d
0x18003d1fa  mov     [rbp+218h], rbp
0x18003d201  mov     dword ptr [rbp+220h], 0
0x18003d20b  cmp     [rdi+250h], r15d
0x18003d212  jbe     short loc_18003D236
0x18003d214  mov     rcx, rbp
0x18003d217  call    ?GetNextPtr@?$CTDynArray@USEEK_POINT@CASFBaseIndexMaker@@$0BE@@@QEAAPEAUSEEK_POINT@CASFBaseIndexMaker@@XZ; CTDynArray<CASFBaseIndexMaker::SEEK_POINT,20>::GetNextPtr(void)
0x18003d21c  mov     rcx, [rax+10h]
0x18003d220  cmp     rcx, r11
0x18003d223  cmovnb  rcx, r11
0x18003d227  add     r15d, r13d
0x18003d22a  mov     r11, rcx
0x18003d22d  cmp     r15d, [rdi+250h]
0x18003d234  jb      short loc_18003D214
0x18003d236  mov     rcx, [rsp+68h+var_38]
0x18003d23b  xor     r9d, r9d
0x18003d23e  movzx   r8d, word ptr [rdi+4]
0x18003d243  cmp     r11, 0FFFFFFFFFFFFFFFFh
0x18003d247  movzx   edx, word ptr [rdi+2]
0x18003d24b  cmovnz  r9, r11
0x18003d24f  mov     rax, [rcx]
0x18003d252  mov     rax, [rax+50h]
0x18003d256  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d25b  add     esi, r13d
0x18003d25e  jmp     loc_18003D1B9
0x18003d263  mov     eax, 8000FFFFh
0x18003d268  jmp     short loc_18003D2D6
0x18003d26a  mov     rcx, [rsp+68h+var_38]
0x18003d26f  mov     edx, [rbx+48h]
0x18003d272  mov     rax, [rcx]
0x18003d275  mov     rax, [rax+60h]
0x18003d279  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d27e  mov     r8, [rsp+68h+var_38]
0x18003d283  lea     rcx, [rbx+80h]
0x18003d28a  call    ?InsertValue@?$CTSparseBlock@KPEAUIASFIndexBlock@@$0BE@$0A@@@QEAAJKPEAUIASFIndexBlock@@@Z; CTSparseBlock<ulong,IASFIndexBlock *,20,0>::InsertValue(ulong,IASFIndexBlock *)
0x18003d28f  test    eax, eax
0x18003d291  js      short loc_18003D2A8
0x18003d293  mov     eax, [rbx+158h]
0x18003d299  inc     eax
0x18003d29b  cmp     eax, r13d
0x18003d29e  cmovbe  eax, r13d
0x18003d2a2  mov     [rbx+158h], eax
0x18003d2a8  xor     r10d, r10d
0x18003d2ab  cmp     [rbx+32C8h], r10d
0x18003d2b2  jbe     short loc_18003D2D3
0x18003d2b4  mov     edx, r10d
0x18003d2b7  lea     rcx, [rbx+160h]
0x18003d2be  call    ?GetPtr@?$CTDynArray@USTREAM_INFO@CASFBaseIndexMaker@@$0BE@@@QEAAPEAUSTREAM_INFO@CASFBaseIndexMaker@@K@Z; CTDynArray<CASFBaseIndexMaker::STREAM_INFO,20>::GetPtr(ulong)
0x18003d2c3  add     r10d, r13d
0x18003d2c6  add     [rax+0Ch], r13d
0x18003d2ca  cmp     r10d, [rbx+32C8h]
0x18003d2d1  jb      short loc_18003D2B4
0x18003d2d3  mov     eax, r14d
0x18003d2d6  mov     rcx, [rsp+68h+var_30]
0x18003d2db  xor     rcx, rsp; StackCookie
0x18003d2de  call    __security_check_cookie
0x18003d2e3  lea     r11, [rsp+68h+var_28]
0x18003d2e8  mov     rbx, [r11+38h]
0x18003d2ec  mov     rbp, [r11+40h]
0x18003d2f0  mov     rsp, r11
0x18003d2f3  pop     r15
0x18003d2f5  pop     r14
0x18003d2f7  pop     r13
0x18003d2f9  pop     rdi
0x18003d2fa  pop     rsi
0x18003d2fb  retn
```
