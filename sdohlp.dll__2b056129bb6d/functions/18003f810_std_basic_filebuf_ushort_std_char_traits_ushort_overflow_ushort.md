# std::basic_filebuf<ushort,std::char_traits<ushort>>::overflow(ushort)

- ea: `0x18003f810`
- end: `0x18003fa43`
- name: `?overflow@?$basic_filebuf@GU?$char_traits@G@std@@@std@@MEAAGG@Z`
- size: `563`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180038ed4`
- `0x18003e6b0`
- `0x18003e6e4`
- `0x18003e7d8`
- `0x18003f810`
- `0x180055030`
- `0x180058010`

## import_xrefs

- `msvcrt!fwrite` at `0x18003f98c`
- `msvcrt!fwrite` at `0x18003f98c`
- `msvcrt!fputwc` at `0x18003f8b8`
- `msvcrt!fputwc` at `0x18003f9e5`
- `msvcrt!fputwc` at `0x18003f8b8`
- `msvcrt!fputwc` at `0x18003f9e5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::basic_filebuf<unsigned short>::overflow(__int64 a1, wchar_t a2)
{
  wchar_t v2; // bx
  unsigned __int64 v5; // r8
  int *v6; // rax
  __int64 v7; // r9
  _WORD **v8; // rdx
  wchar_t *v9; // r8
  __int64 v10; // rcx
  void **v11; // r11
  unsigned __int64 v12; // r10
  void **v13; // r8
  void **v14; // r9
  int v15; // eax
  __int64 v16; // rdx
  int v17; // eax
  void **v18; // rax
  signed __int64 v19; // r14
  void **v20; // rcx
  wchar_t v21; // [rsp+50h] [rbp-9h] BYREF
  char v22[6]; // [rsp+52h] [rbp-7h] BYREF
  void **v23; // [rsp+58h] [rbp-1h] BYREF
  wchar_t *v24; // [rsp+60h] [rbp+7h] BYREF
  void *Buffer[2]; // [rsp+68h] [rbp+Fh] BYREF
  unsigned __int64 v26; // [rsp+78h] [rbp+1Fh]
  unsigned __int64 v27; // [rsp+80h] [rbp+27h]

  v2 = a2;
  if ( a2 == 0xFFFF )
    return 0;
  v5 = **(_QWORD **)(a1 + 64);
  if ( v5 && (v6 = *(int **)(a1 + 88), v7 = *v6, v5 < v5 + 2 * v7) )
  {
    *v6 = v7 - 1;
    v8 = *(_WORD ***)(a1 + 64);
    v9 = (*v8)++;
    *v9 = v2;
  }
  else
  {
    if ( !*(_QWORD *)(a1 + 144) )
      return 0xFFFF;
    std::basic_filebuf<unsigned short>::_Reset_back();
    if ( *(_QWORD *)(v10 + 120) )
    {
      v21 = v2;
      v24 = 0;
      v23 = 0;
      std::string::string(Buffer, 8);
LABEL_13:
      v11 = (void **)Buffer[0];
      v12 = v27;
      while ( 1 )
      {
        v13 = Buffer;
        if ( v12 >= 0x10 )
          v13 = v11;
        v14 = Buffer;
        if ( v12 >= 0x10 )
          v14 = v11;
        v15 = (*(__int64 (__fastcall **)(_QWORD, __int64, wchar_t *, char *, wchar_t **, void **, char *, void ***))(**(_QWORD **)(a1 + 120) + 56LL))(
                *(_QWORD *)(a1 + 120),
                a1 + 132,
                &v21,
                v22,
                &v24,
                v14,
                (char *)v13 + v26,
                &v23);
        if ( v15 )
        {
          v17 = v15 - 1;
          if ( v17 )
            break;
        }
        v18 = Buffer;
        v11 = (void **)Buffer[0];
        v12 = v27;
        if ( v27 >= 0x10 )
          v18 = (void **)Buffer[0];
        v19 = (char *)v23 - (char *)v18;
        if ( v23 != v18 )
        {
          v20 = Buffer;
          if ( v27 >= 0x10 )
            v20 = (void **)Buffer[0];
          if ( v19 != fwrite(v20, 1u, (char *)v23 - (char *)v18, *(FILE **)(a1 + 144)) )
            goto LABEL_35;
          v12 = v27;
          v11 = (void **)Buffer[0];
        }
        *(_BYTE *)(a1 + 130) = 1;
        if ( v24 != &v21 )
          goto LABEL_36;
        if ( !v19 )
        {
          if ( v26 < 0x20 )
          {
            std::string::append(Buffer, 8, 0);
            goto LABEL_13;
          }
          goto LABEL_35;
        }
      }
      if ( v17 != 2 )
      {
LABEL_35:
        LOBYTE(v16) = 1;
        std::string::_Tidy(Buffer, v16, 0);
        return 0xFFFF;
      }
      if ( fputwc(v21, *(FILE **)(a1 + 144)) == 0xFFFF )
        v2 = -1;
LABEL_36:
      LOBYTE(v16) = 1;
      std::string::_Tidy(Buffer, v16, 0);
    }
    else if ( fputwc(v2, *(FILE **)(v10 + 144)) == 0xFFFF )
    {
      return (wchar_t)-1;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18003f810  mov     [rsp-8+arg_10], rbx
0x18003f815  mov     [rsp-8+arg_18], rsi
0x18003f81a  push    rbp
0x18003f81b  push    rdi
0x18003f81c  push    r12
0x18003f81e  push    r14
0x18003f820  push    r15
0x18003f822  lea     rbp, [rsp-37h]
0x18003f827  sub     rsp, 90h
0x18003f82e  mov     rax, cs:__security_cookie
0x18003f835  xor     rax, rsp
0x18003f838  mov     [rbp+57h+var_28], rax
0x18003f83c  movzx   ebx, dx
0x18003f83f  mov     rdi, rcx
0x18003f842  mov     r12d, 0FFFFh
0x18003f848  xor     esi, esi
0x18003f84a  cmp     r12w, dx
0x18003f84e  jnz     short loc_18003F858
0x18003f850  movzx   eax, si
0x18003f853  jmp     loc_18003FA1B
0x18003f858  mov     rax, [rcx+40h]
0x18003f85c  mov     r8, [rax]
0x18003f85f  test    r8, r8
0x18003f862  jz      short loc_18003F891
0x18003f864  mov     rax, [rcx+58h]
0x18003f868  movsxd  r9, dword ptr [rax]
0x18003f86b  lea     rdx, [r8+r9*2]
0x18003f86f  cmp     r8, rdx
0x18003f872  jnb     short loc_18003F891
0x18003f874  lea     ecx, [r9-1]
0x18003f878  mov     [rax], ecx
0x18003f87a  mov     rdx, [rdi+40h]
0x18003f87e  mov     r8, [rdx]
0x18003f881  lea     rcx, [r8+2]
0x18003f885  mov     [rdx], rcx
0x18003f888  mov     [r8], bx
0x18003f88c  jmp     loc_18003FA18
0x18003f891  cmp     [rcx+90h], rsi
0x18003f898  jnz     short loc_18003F8A3
0x18003f89a  movzx   eax, r12w
0x18003f89e  jmp     loc_18003FA1B
0x18003f8a3  call    ?_Reset_back@?$basic_filebuf@GU?$char_traits@G@std@@@std@@AEAAXXZ; std::basic_filebuf<ushort>::_Reset_back(void)
0x18003f8a8  cmp     [rcx+78h], rsi
0x18003f8ac  jnz     short loc_18003F8CC
0x18003f8ae  mov     rdx, [rcx+90h]; Stream
0x18003f8b5  movzx   ecx, bx; Character
0x18003f8b8  call    cs:__imp_fputwc
0x18003f8be  cmp     ax, r12w
0x18003f8c2  cmovz   bx, r12w
0x18003f8c7  jmp     loc_18003FA18
0x18003f8cc  mov     [rbp+57h+var_60], bx
0x18003f8d0  mov     [rbp+57h+var_50], rsi
0x18003f8d4  mov     [rbp+57h+var_58], rsi
0x18003f8d8  xor     r8d, r8d
0x18003f8db  lea     edx, [r8+8]
0x18003f8df  lea     rcx, [rbp+57h+Buffer]
0x18003f8e3  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@_KD@Z; std::string::string(unsigned __int64,char)
0x18003f8e8  nop
0x18003f8e9  mov     r11, [rbp+57h+Buffer]
0x18003f8ed  mov     r10, [rbp+57h+var_30]
0x18003f8f1  mov     rcx, [rdi+78h]
0x18003f8f5  lea     r8, [rbp+57h+Buffer]
0x18003f8f9  cmp     r10, 10h
0x18003f8fd  cmovnb  r8, r11
0x18003f901  mov     rdx, [rbp+57h+var_38]
0x18003f905  lea     r9, [rbp+57h+Buffer]
0x18003f909  cmovnb  r9, r11
0x18003f90d  mov     rax, [rcx]
0x18003f910  add     rdx, r8
0x18003f913  lea     r8, [rbp+57h+var_58]
0x18003f917  mov     [rsp+0B0h+var_78], r8
0x18003f91c  mov     [rsp+0B0h+var_80], rdx
0x18003f921  mov     [rsp+0B0h+var_88], r9
0x18003f926  lea     rdx, [rbp+57h+var_50]
0x18003f92a  mov     [rsp+0B0h+var_90], rdx
0x18003f92f  lea     r9, [rbp+57h+var_5E]
0x18003f933  lea     r8, [rbp+57h+var_60]
0x18003f937  lea     rdx, [rdi+84h]
0x18003f93e  mov     rax, [rax+38h]
0x18003f942  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f947  test    eax, eax
0x18003f949  jz      short loc_18003F954
0x18003f94b  sub     eax, 1
0x18003f94e  jnz     loc_18003F9D5
0x18003f954  lea     rax, [rbp+57h+Buffer]
0x18003f958  mov     r11, [rbp+57h+Buffer]
0x18003f95c  mov     r10, [rbp+57h+var_30]
0x18003f960  cmp     r10, 10h
0x18003f964  cmovnb  rax, r11
0x18003f968  mov     r14, [rbp+57h+var_58]
0x18003f96c  sub     r14, rax
0x18003f96f  jz      short loc_18003F99F
0x18003f971  lea     rcx, [rbp+57h+Buffer]
0x18003f975  cmp     r10, 10h
0x18003f979  cmovnb  rcx, r11; Buffer
0x18003f97d  mov     r9, [rdi+90h]; Stream
0x18003f984  mov     r8, r14; ElementCount
0x18003f987  mov     edx, 1; ElementSize
0x18003f98c  call    cs:__imp_fwrite
0x18003f992  cmp     r14, rax
0x18003f995  jnz     short loc_18003F9F7
0x18003f997  mov     r10, [rbp+57h+var_30]
0x18003f99b  mov     r11, [rbp+57h+Buffer]
0x18003f99f  mov     byte ptr [rdi+82h], 1
0x18003f9a6  lea     rax, [rbp+57h+var_60]
0x18003f9aa  cmp     [rbp+57h+var_50], rax
0x18003f9ae  jnz     short loc_18003FA0A
0x18003f9b0  test    r14, r14
0x18003f9b3  jnz     loc_18003F8F1
0x18003f9b9  cmp     [rbp+57h+var_38], 20h ; ' '
0x18003f9be  jnb     short loc_18003F9F7
0x18003f9c0  xor     r8d, r8d
0x18003f9c3  lea     edx, [r14+8]
0x18003f9c7  lea     rcx, [rbp+57h+Buffer]
0x18003f9cb  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@_KD@Z; std::string::append(unsigned __int64,char)
0x18003f9d0  jmp     loc_18003F8E9
0x18003f9d5  cmp     eax, 2
0x18003f9d8  jnz     short loc_18003F9F7
0x18003f9da  mov     rdx, [rdi+90h]; Stream
0x18003f9e1  movzx   ecx, [rbp+57h+var_60]; Character
0x18003f9e5  call    cs:__imp_fputwc
0x18003f9eb  nop
0x18003f9ec  cmp     ax, r12w
0x18003f9f0  cmovz   bx, r12w
0x18003f9f5  jmp     short loc_18003FA0A
0x18003f9f7  xor     r8d, r8d
0x18003f9fa  mov     dl, 1
0x18003f9fc  lea     rcx, [rbp+57h+Buffer]
0x18003fa00  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x18003fa05  jmp     loc_18003F89A
0x18003fa0a  xor     r8d, r8d
0x18003fa0d  mov     dl, 1
0x18003fa0f  lea     rcx, [rbp+57h+Buffer]
0x18003fa13  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x18003fa18  movzx   eax, bx
0x18003fa1b  mov     rcx, [rbp+57h+var_28]
0x18003fa1f  xor     rcx, rsp; StackCookie
0x18003fa22  call    __security_check_cookie
0x18003fa27  lea     r11, [rsp+0B0h+var_20]
0x18003fa2f  mov     rbx, [r11+40h]
0x18003fa33  mov     rsi, [r11+48h]
0x18003fa37  mov     rsp, r11
0x18003fa3a  pop     r15
0x18003fa3c  pop     r14
0x18003fa3e  pop     r12
0x18003fa40  pop     rdi
0x18003fa41  pop     rbp
0x18003fa42  retn
```
