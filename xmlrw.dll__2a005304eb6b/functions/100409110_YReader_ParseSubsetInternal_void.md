# YReader::ParseSubsetInternal(void)

- ea: `0x100409110`
- end: `0x100409389`
- name: `?ParseSubsetInternal@YReader@@AEAAXXZ`
- size: `633`
- prototype: `void __fastcall(YReader *__hidden this)`
- caller_count: `0`
- callee_count: `12`
- tags: ``

## callees

- `0x100401780`
- `0x100405110`
- `0x100405fc0`
- `0x1004064a0`
- `0x100406cc0`
- `0x100408760`
- `0x100409110`
- `0x10040a020`
- `0x10040a270`
- `0x10040a4c0`
- `0x1004394f0`
- `0x100439df0`

## pseudocode

```c
void __fastcall YReader::ParseSubsetInternal(const void **this)
{
  unsigned int v2; // eax
  __int64 v3; // rcx
  __int128 v4; // xmm0
  __int128 v5; // xmm0
  unsigned int v6; // eax
  int v7; // ecx
  void (__fastcall **v8)(YReader *__hidden); // rax
  __int128 v9; // [rsp+20h] [rbp-48h]
  void (__fastcall *v10)(YReader *__hidden); // [rsp+30h] [rbp-38h] BYREF
  int v11; // [rsp+38h] [rbp-30h]
  void (__fastcall *v12)(YReader *__hidden); // [rsp+40h] [rbp-28h] BYREF
  int v13; // [rsp+48h] [rbp-20h]
  __int128 v14; // [rsp+50h] [rbp-18h]

  v2 = YReader::GetTokenDeclOuter((YReader *)this) - 15;
  _mm_lfence();
  while ( 2 )
  {
    switch ( v2 )
    {
      case 0u:
        *(_QWORD *)&v9 = 0;
        DWORD2(v9) = 0;
        v14 = *((_OWORD *)this + 94);
        *((_OWORD *)this + 94) = v9;
        while ( (unsigned int)YReader::GetTokenDeclLiteral((YReader *)this) != 16 )
          ;
        *((_OWORD *)this + 94) = v14;
        goto LABEL_18;
      case 2u:
        YReader::ParsePiSubset((YReader *)this);
        goto LABEL_18;
      case 4u:
        v3 = *((_QWORD *)this[58] + (unsigned int)(*((_DWORD *)this + 118) - 1));
        if ( *(_QWORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 40LL))(v3) + 96) )
          goto LABEL_18;
        DWORD2(v9) = 0;
        *(_QWORD *)&v9 = YReader::ParseSubsetInternal;
        v4 = v9;
        *(_QWORD *)&v9 = YReader::ParseSubsetExternal;
        DWORD2(v9) = 0;
        *((_OWORD *)this + 95) = v4;
        v5 = v9;
        goto LABEL_5;
      case 9u:
        YReader::ParseDeclAttlist((struct IMalloc **)this);
        goto LABEL_18;
      case 0xBu:
        YReader::ParseDeclElement((struct IMalloc **)this);
        goto LABEL_18;
      case 0xCu:
        YReader::ParseDeclEntity((struct IMalloc **)this);
        goto LABEL_10;
      case 0xDu:
        YReader::ParseDeclNotation((struct IMalloc **)this);
LABEL_10:
        v6 = *((_DWORD *)this + 406);
        if ( v6 == dword_100450B38 && !memcmp(this[202], CodeStringPtr::empty, 2LL * v6) )
          goto LABEL_18;
        return;
      case 0x28u:
        if ( *((_DWORD *)this + 118) != 1 )
          goto LABEL_28;
        if ( (unsigned int)YReader::GetTokenDeclInner((YReader *)this) != 48 )
        {
          MXRRaiseException(-1072894429);
          __debugbreak();
        }
        this[230] = (const void *)*((_QWORD *)this[55] + 2);
        v7 = *(_DWORD *)((*((__int64 (__fastcall **)(char *))this[157] + 7))((char *)this + 1256) + 8);
        if ( v7 )
        {
          v13 = 0;
          v12 = YReader::ParseDtdExternal;
        }
        else
        {
          v11 = 0;
          v10 = YReader::ParseProlog;
        }
        v8 = &v10;
        if ( v7 )
          v8 = &v12;
        v5 = *(_OWORD *)v8;
LABEL_5:
        *((_OWORD *)this + 94) = v5;
        ((void (__fastcall *)(char *))this[188])((char *)this + *((int *)this + 378));
        return;
      case 0x2Cu:
LABEL_18:
        v2 = YReader::GetTokenDeclOuter((YReader *)this) - 15;
        if ( v2 <= 0x2C )
          continue;
        goto LABEL_28;
      default:
LABEL_28:
        MXRRaiseException(-1072894419);
        __debugbreak();
    }
  }
}

```

## disassembly

```asm
0x100409110  mov     [rsp+arg_0], rbx
0x100409115  mov     [rsp+arg_8], rsi
0x10040911a  push    rdi
0x10040911b  sub     rsp, 60h
0x10040911f  mov     rbx, rcx
0x100409122  call    ?GetTokenDeclOuter@YReader@@AEAAHXZ; YReader::GetTokenDeclOuter(void)
0x100409127  sub     eax, 0Fh; switch 45 cases
0x10040912a  cmp     eax, 2Ch
0x10040912d  ja      def_100409154; jumptable 0000000100409154 default case, cases 16,18,20-23,25,29-54,56-58
0x100409133  lfence
0x100409136  lea     rdi, __ImageBase
0x10040913d  xor     esi, esi
0x10040913f  nop
0x100409140  cdqe
0x100409142  movzx   eax, ds:(byte_10040935C - 100400000h)[rdi+rax]
0x10040914a  mov     ecx, ds:(jpt_100409154 - 100400000h)[rdi+rax*4]
0x100409151  add     rcx, rdi
0x100409154  jmp     rcx; switch jump
0x100409156  mov     ecx, [rbx+1D8h]; jumptable 0000000100409154 case 19
0x10040915c  mov     rax, [rbx+1D0h]
0x100409163  dec     ecx
0x100409165  mov     rcx, [rax+rcx*8]
0x100409169  mov     rax, [rcx]
0x10040916c  mov     rax, [rax+28h]
0x100409170  call    cs:__guard_dispatch_icall_fptr
0x100409176  cmp     [rax+60h], rsi
0x10040917a  jnz     loc_100409283; jumptable 0000000100409154 case 59
0x100409180  mov     dword ptr [rsp+68h+var_48+8], esi
0x100409184  lea     rax, ?ParseSubsetInternal@YReader@@AEAAXXZ; YReader::ParseSubsetInternal(void)
0x10040918b  mov     qword ptr [rsp+68h+var_48], rax
0x100409190  lea     rax, ?ParseSubsetExternal@YReader@@AEAAXXZ; YReader::ParseSubsetExternal(void)
0x100409197  movups  xmm0, [rsp+68h+var_48]
0x10040919c  mov     qword ptr [rsp+68h+var_48], rax
0x1004091a1  mov     dword ptr [rsp+68h+var_48+8], esi
0x1004091a5  movups  xmmword ptr [rbx+5F0h], xmm0
0x1004091ac  movups  xmm0, [rsp+68h+var_48]
0x1004091b1  movups  xmmword ptr [rbx+5E0h], xmm0
0x1004091b8  movsxd  rcx, dword ptr [rbx+5E8h]
0x1004091bf  mov     rax, [rbx+5E0h]
0x1004091c6  add     rcx, rbx
0x1004091c9  call    cs:__guard_dispatch_icall_fptr
0x1004091cf  mov     rbx, [rsp+68h+arg_0]
0x1004091d4  mov     rsi, [rsp+68h+arg_8]
0x1004091d9  add     rsp, 60h
0x1004091dd  pop     rdi
0x1004091de  retn
0x1004091df  mov     rcx, rbx; jumptable 0000000100409154 case 24
0x1004091e2  call    ?ParseDeclAttlist@YReader@@AEAAXXZ; YReader::ParseDeclAttlist(void)
0x1004091e7  jmp     loc_100409283; jumptable 0000000100409154 case 59
0x1004091ec  mov     rcx, rbx; jumptable 0000000100409154 case 26
0x1004091ef  call    ?ParseDeclElement@YReader@@AEAAXXZ; YReader::ParseDeclElement(void)
0x1004091f4  jmp     loc_100409283; jumptable 0000000100409154 case 59
0x1004091f9  mov     rcx, rbx; jumptable 0000000100409154 case 27
0x1004091fc  call    ?ParseDeclEntity@YReader@@AEAAXXZ; YReader::ParseDeclEntity(void)
0x100409201  mov     eax, [rbx+658h]
0x100409207  cmp     eax, cs:dword_100450B38
0x10040920d  jnz     short loc_1004091CF
0x10040920f  mov     rdx, cs:?empty@CodeStringPtr@@2UStringPtr@@A; Buf2
0x100409216  mov     r8d, eax
0x100409219  mov     rcx, [rbx+650h]; Buf1
0x100409220  add     r8, r8; Size
0x100409223  call    memcmp
0x100409228  test    eax, eax
0x10040922a  jnz     short loc_1004091CF
0x10040922c  jmp     short loc_100409283; jumptable 0000000100409154 case 59
0x10040922e  mov     rcx, rbx; jumptable 0000000100409154 case 28
0x100409231  call    ?ParseDeclNotation@YReader@@AEAAXXZ; YReader::ParseDeclNotation(void)
0x100409236  jmp     short loc_100409201
0x100409238  movups  xmm0, xmmword ptr [rbx+5E0h]; jumptable 0000000100409154 case 15
0x10040923f  mov     qword ptr [rsp+68h+var_48], rsi
0x100409244  mov     dword ptr [rsp+68h+var_48+8], esi
0x100409248  movups  [rsp+68h+var_18], xmm0
0x10040924d  movups  xmm0, [rsp+68h+var_48]
0x100409252  movups  xmmword ptr [rbx+5E0h], xmm0
0x100409259  nop     dword ptr [rax+00000000h]
0x100409260  mov     rcx, rbx; this
0x100409263  call    ?GetTokenDeclLiteral@YReader@@AEAAHXZ; YReader::GetTokenDeclLiteral(void)
0x100409268  cmp     eax, 10h
0x10040926b  jnz     short loc_100409260
0x10040926d  movups  xmm0, [rsp+68h+var_18]
0x100409272  movups  xmmword ptr [rbx+5E0h], xmm0
0x100409279  jmp     short loc_100409283; jumptable 0000000100409154 case 59
0x10040927b  mov     rcx, rbx; jumptable 0000000100409154 case 17
0x10040927e  call    ?ParsePiSubset@YReader@@AEAAXXZ; YReader::ParsePiSubset(void)
0x100409283  mov     rcx, rbx; jumptable 0000000100409154 case 59
0x100409286  call    ?GetTokenDeclOuter@YReader@@AEAAHXZ; YReader::GetTokenDeclOuter(void)
0x10040928b  sub     eax, 0Fh
0x10040928e  cmp     eax, 2Ch ; ','
0x100409291  ja      def_100409154; jumptable 0000000100409154 default case, cases 16,18,20-23,25,29-54,56-58
0x100409297  jmp     loc_100409140
0x10040929c  cmp     dword ptr [rbx+1D8h], 1; jumptable 0000000100409154 case 55
0x1004092a3  jnz     short def_100409154; jumptable 0000000100409154 default case, cases 16,18,20-23,25,29-54,56-58
0x1004092a5  mov     rcx, rbx; this
0x1004092a8  call    ?GetTokenDeclInner@YReader@@AEAAHXZ; YReader::GetTokenDeclInner(void)
0x1004092ad  cmp     eax, 30h ; '0'
0x1004092b0  jnz     short loc_100409324
0x1004092b2  mov     rax, [rbx+1B8h]
0x1004092b9  mov     rcx, [rax+10h]
0x1004092bd  mov     [rbx+730h], rcx
0x1004092c4  lea     rcx, [rbx+4E8h]
0x1004092cb  mov     rax, [rcx]
0x1004092ce  mov     rax, [rax+38h]
0x1004092d2  call    cs:__guard_dispatch_icall_fptr
0x1004092d8  mov     ecx, [rax+8]
0x1004092db  test    ecx, ecx
0x1004092dd  jz      short loc_1004092F1
0x1004092df  lea     rax, ?ParseDtdExternal@YReader@@AEAAXXZ; YReader::ParseDtdExternal(void)
0x1004092e6  mov     [rsp+68h+var_20], esi
0x1004092ea  mov     [rsp+68h+var_28], rax
0x1004092ef  jmp     short loc_100409301
0x1004092f1  lea     rax, ?ParseProlog@YReader@@AEAAXXZ; YReader::ParseProlog(void)
0x1004092f8  mov     [rsp+68h+var_30], esi
0x1004092fc  mov     [rsp+68h+var_38], rax
0x100409301  test    ecx, ecx
0x100409303  lea     rax, [rsp+68h+var_38]
0x100409308  lea     rdx, [rsp+68h+var_28]
0x10040930d  cmovnz  rax, rdx
0x100409311  movups  xmm0, xmmword ptr [rax]
0x100409314  jmp     loc_1004091B1
0x100409319  mov     ecx, 0C00CEE2Dh; jumptable 0000000100409154 default case, cases 16,18,20-23,25,29-54,56-58
0x10040931e  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x100409323  int     3; Trap to Debugger
0x100409324  mov     ecx, 0C00CEE23h; int
0x100409329  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x10040932e  int     3; Trap to Debugger
```
