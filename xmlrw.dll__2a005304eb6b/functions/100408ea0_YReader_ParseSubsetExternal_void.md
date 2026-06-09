# YReader::ParseSubsetExternal(void)

- ea: `0x100408ea0`
- end: `0x1004090fd`
- name: `?ParseSubsetExternal@YReader@@AEAAXXZ`
- size: `605`
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
- `0x100408ea0`
- `0x10040a020`
- `0x10040a270`
- `0x10040a4c0`
- `0x1004394f0`
- `0x100439df0`

## pseudocode

```c
void __fastcall YReader::ParseSubsetExternal(const void **this)
{
  unsigned int v2; // eax
  unsigned int v3; // eax
  int v4; // eax
  int v5; // edi
  int v6; // eax
  __int128 v7; // xmm0
  __int128 v8; // [rsp+20h] [rbp-38h]
  __int128 v9; // [rsp+30h] [rbp-28h]
  __int128 v10; // [rsp+40h] [rbp-18h]

  v2 = YReader::GetTokenDeclOuter((YReader *)this) - 15;
  _mm_lfence();
  while ( 1 )
  {
    switch ( v2 )
    {
      case 0u:
        *(_QWORD *)&v9 = 0;
        DWORD2(v9) = 0;
        v10 = *((_OWORD *)this + 94);
        *((_OWORD *)this + 94) = v9;
        while ( (unsigned int)YReader::GetTokenDeclLiteral((YReader *)this) != 16 )
          ;
        goto LABEL_23;
      case 2u:
        YReader::ParsePiSubset((YReader *)this);
        goto LABEL_26;
      case 4u:
      case 6u:
        goto LABEL_26;
      case 5u:
        v4 = YReader::GetTokenDeclInner((YReader *)this) - 22;
        if ( v4 )
        {
          if ( v4 != 1 )
            goto LABEL_30;
          if ( (unsigned int)YReader::GetTokenDeclInner((YReader *)this) != 49 )
          {
LABEL_29:
            MXRRaiseException(-1072894423);
            __debugbreak();
          }
        }
        else
        {
          if ( (unsigned int)YReader::GetTokenDeclInner((YReader *)this) != 49 )
            goto LABEL_29;
          *(_QWORD *)&v8 = 0;
          v5 = 0;
          DWORD2(v8) = 0;
          v10 = *((_OWORD *)this + 94);
          *((_OWORD *)this + 94) = v8;
          while ( 1 )
          {
            while ( 1 )
            {
              v6 = YReader::GetTokenDeclOuter((YReader *)this) - 20;
              if ( v6 )
                break;
              ++v5;
            }
            if ( v6 != 1 )
              goto LABEL_30;
            if ( !v5 )
              break;
            --v5;
          }
LABEL_23:
          *((_OWORD *)this + 94) = v10;
        }
LABEL_26:
        v2 = YReader::GetTokenDeclOuter((YReader *)this) - 15;
        if ( v2 > 0x2C )
        {
LABEL_30:
          MXRRaiseException(-1072894419);
          __debugbreak();
        }
        return;
      case 9u:
        YReader::ParseDeclAttlist((struct IMalloc **)this);
        goto LABEL_26;
      case 0xBu:
        YReader::ParseDeclElement((struct IMalloc **)this);
        goto LABEL_26;
      case 0xCu:
        YReader::ParseDeclEntity((struct IMalloc **)this);
        goto LABEL_6;
      case 0xDu:
        YReader::ParseDeclNotation((struct IMalloc **)this);
LABEL_6:
        v3 = *((_DWORD *)this + 406);
        if ( v3 != dword_100450B38 || memcmp(this[202], CodeStringPtr::empty, 2LL * v3) )
          return;
        goto LABEL_26;
      case 0x2Cu:
        if ( *((_DWORD *)this + 118) != 1 )
          goto LABEL_26;
        v7 = *((_OWORD *)this + 95);
        this[230] = (const void *)*((_QWORD *)this[55] + 2);
        *((_OWORD *)this + 94) = v7;
        ((void (__fastcall *)(char *))this[188])((char *)this + *((int *)this + 378));
        return;
      default:
        goto LABEL_30;
    }
  }
}

```

## disassembly

```asm
0x100408ea0  mov     [rsp+arg_0], rbx
0x100408ea5  mov     [rsp+arg_8], rbp
0x100408eaa  mov     [rsp+arg_10], rsi
0x100408eaf  push    rdi
0x100408eb0  sub     rsp, 50h
0x100408eb4  mov     rbx, rcx
0x100408eb7  call    ?GetTokenDeclOuter@YReader@@AEAAHXZ; YReader::GetTokenDeclOuter(void)
0x100408ebc  sub     eax, 0Fh; switch 45 cases
0x100408ebf  cmp     eax, 2Ch
0x100408ec2  ja      def_100408EE8; jumptable 0000000100408EE8 default case, cases 16,18,22,23,25,29-58
0x100408ec8  lfence
0x100408ecb  lea     rsi, __ImageBase
0x100408ed2  xor     ebp, ebp
0x100408ed4  cdqe
0x100408ed6  movzx   eax, ds:(byte_1004090D0 - 100400000h)[rsi+rax]
0x100408ede  mov     ecx, ds:(jpt_100408EE8 - 100400000h)[rsi+rax*4]
0x100408ee5  add     rcx, rsi
0x100408ee8  jmp     rcx; switch jump
0x100408eea  mov     rcx, rbx; jumptable 0000000100408EE8 case 24
0x100408eed  call    ?ParseDeclAttlist@YReader@@AEAAXXZ; YReader::ParseDeclAttlist(void)
0x100408ef2  jmp     loc_10040903E; jumptable 0000000100408EE8 cases 19,21
0x100408ef7  mov     rcx, rbx; jumptable 0000000100408EE8 case 26
0x100408efa  call    ?ParseDeclElement@YReader@@AEAAXXZ; YReader::ParseDeclElement(void)
0x100408eff  jmp     loc_10040903E; jumptable 0000000100408EE8 cases 19,21
0x100408f04  mov     rcx, rbx; jumptable 0000000100408EE8 case 27
0x100408f07  call    ?ParseDeclEntity@YReader@@AEAAXXZ; YReader::ParseDeclEntity(void)
0x100408f0c  mov     eax, [rbx+658h]
0x100408f12  cmp     eax, cs:dword_100450B38
0x100408f18  jnz     short loc_100408F3B
0x100408f1a  mov     rdx, cs:?empty@CodeStringPtr@@2UStringPtr@@A; Buf2
0x100408f21  mov     r8d, eax
0x100408f24  mov     rcx, [rbx+650h]; Buf1
0x100408f2b  add     r8, r8; Size
0x100408f2e  call    memcmp
0x100408f33  test    eax, eax
0x100408f35  jz      loc_10040903E; jumptable 0000000100408EE8 cases 19,21
0x100408f3b  mov     rbx, [rsp+58h+arg_0]
0x100408f40  mov     rbp, [rsp+58h+arg_8]
0x100408f45  mov     rsi, [rsp+58h+arg_10]
0x100408f4a  add     rsp, 50h
0x100408f4e  pop     rdi
0x100408f4f  retn
0x100408f50  mov     rcx, rbx; jumptable 0000000100408EE8 case 28
0x100408f53  call    ?ParseDeclNotation@YReader@@AEAAXXZ; YReader::ParseDeclNotation(void)
0x100408f58  jmp     short loc_100408F0C
0x100408f5a  mov     rcx, rbx; jumptable 0000000100408EE8 case 20
0x100408f5d  call    ?GetTokenDeclInner@YReader@@AEAAHXZ; YReader::GetTokenDeclInner(void)
0x100408f62  sub     eax, 16h
0x100408f65  jz      short loc_100408F86
0x100408f67  cmp     eax, 1
0x100408f6a  jnz     def_100408EE8; jumptable 0000000100408EE8 default case, cases 16,18,22,23,25,29-58
0x100408f70  mov     rcx, rbx; this
0x100408f73  call    ?GetTokenDeclInner@YReader@@AEAAHXZ; YReader::GetTokenDeclInner(void)
0x100408f78  cmp     eax, 31h ; '1'
0x100408f7b  jnz     loc_10040908F
0x100408f81  jmp     loc_10040903E; jumptable 0000000100408EE8 cases 19,21
0x100408f86  mov     rcx, rbx; this
0x100408f89  call    ?GetTokenDeclInner@YReader@@AEAAHXZ; YReader::GetTokenDeclInner(void)
0x100408f8e  cmp     eax, 31h ; '1'
0x100408f91  jnz     loc_10040908F
0x100408f97  movups  xmm0, xmmword ptr [rbx+5E0h]
0x100408f9e  mov     qword ptr [rsp+58h+var_38], rbp
0x100408fa3  mov     edi, ebp
0x100408fa5  mov     dword ptr [rsp+58h+var_38+8], ebp
0x100408fa9  movups  [rsp+58h+var_18], xmm0
0x100408fae  movups  xmm0, [rsp+58h+var_38]
0x100408fb3  movups  xmmword ptr [rbx+5E0h], xmm0
0x100408fba  nop     word ptr [rax+rax+00h]
0x100408fc0  mov     rcx, rbx; this
0x100408fc3  call    ?GetTokenDeclOuter@YReader@@AEAAHXZ; YReader::GetTokenDeclOuter(void)
0x100408fc8  sub     eax, 14h
0x100408fcb  jz      short loc_100408FE3
0x100408fcd  cmp     eax, 1
0x100408fd0  jnz     def_100408EE8; jumptable 0000000100408EE8 default case, cases 16,18,22,23,25,29-58
0x100408fd6  test    edi, edi
0x100408fd8  jz      short loc_10040901D
0x100408fda  mov     eax, 0FFFFFFFFh
0x100408fdf  add     edi, eax
0x100408fe1  jmp     short loc_100408FC0
0x100408fe3  mov     eax, 1
0x100408fe8  add     edi, eax
0x100408fea  jmp     short loc_100408FC0
0x100408fec  movups  xmm0, xmmword ptr [rbx+5E0h]; jumptable 0000000100408EE8 case 15
0x100408ff3  mov     qword ptr [rsp+58h+var_28], rbp
0x100408ff8  mov     dword ptr [rsp+58h+var_28+8], ebp
0x100408ffc  movups  [rsp+58h+var_18], xmm0
0x100409001  movups  xmm0, [rsp+58h+var_28]
0x100409006  movups  xmmword ptr [rbx+5E0h], xmm0
0x10040900d  nop     dword ptr [rax]
0x100409010  mov     rcx, rbx; this
0x100409013  call    ?GetTokenDeclLiteral@YReader@@AEAAHXZ; YReader::GetTokenDeclLiteral(void)
0x100409018  cmp     eax, 10h
0x10040901b  jnz     short loc_100409010
0x10040901d  movups  xmm0, [rsp+58h+var_18]
0x100409022  movups  xmmword ptr [rbx+5E0h], xmm0
0x100409029  jmp     short loc_10040903E; jumptable 0000000100408EE8 cases 19,21
0x10040902b  mov     rcx, rbx; jumptable 0000000100408EE8 case 17
0x10040902e  call    ?ParsePiSubset@YReader@@AEAAXXZ; YReader::ParsePiSubset(void)
0x100409033  jmp     short loc_10040903E; jumptable 0000000100408EE8 cases 19,21
0x100409035  cmp     dword ptr [rbx+1D8h], 1; jumptable 0000000100408EE8 case 59
0x10040903c  jz      short loc_100409053
0x10040903e  mov     rcx, rbx; jumptable 0000000100408EE8 cases 19,21
0x100409041  call    ?GetTokenDeclOuter@YReader@@AEAAHXZ; YReader::GetTokenDeclOuter(void)
0x100409046  sub     eax, 0Fh
0x100409049  cmp     eax, 2Ch ; ','
0x10040904c  ja      short def_100408EE8; jumptable 0000000100408EE8 default case, cases 16,18,22,23,25,29-58
0x10040904e  jmp     loc_100408ED4
0x100409053  mov     rax, [rbx+1B8h]
0x10040905a  movups  xmm0, xmmword ptr [rbx+5F0h]
0x100409061  mov     rcx, [rax+10h]
0x100409065  mov     [rbx+730h], rcx
0x10040906c  movups  xmmword ptr [rbx+5E0h], xmm0
0x100409073  movsxd  rcx, dword ptr [rbx+5E8h]
0x10040907a  mov     rax, [rbx+5E0h]
0x100409081  add     rcx, rbx
0x100409084  call    cs:__guard_dispatch_icall_fptr
0x10040908a  jmp     loc_100408F3B
0x10040908f  mov     ecx, 0C00CEE29h; int
0x100409094  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x100409099  int     3; Trap to Debugger
0x10040909a  mov     ecx, 0C00CEE2Dh; jumptable 0000000100408EE8 default case, cases 16,18,22,23,25,29-58
0x10040909f  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x1004090a4  int     3; Trap to Debugger
```
