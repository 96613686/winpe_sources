# ApplySettings::ProcessSystemInfo(std::basic_ifstream<ushort,std::char_traits<ushort>> &)

- ea: `0x1800468f4`
- end: `0x180046a2a`
- name: `?ProcessSystemInfo@ApplySettings@@AEAAJAEAV?$basic_ifstream@GU?$char_traits@G@std@@@std@@@Z`
- size: `310`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180043eec`

## callees

- `0x180038ad0`
- `0x1800407e0`
- `0x180042a80`
- `0x1800468f4`

## import_xrefs

- `msvcrt!wcstol` at `0x180046932`
- `msvcrt!wcstol` at `0x18004695a`
- `msvcrt!wcstol` at `0x180046980`
- `msvcrt!wcstol` at `0x180046932`
- `msvcrt!wcstol` at `0x18004695a`
- `msvcrt!wcstol` at `0x180046980`

## string_xrefs

- `0x1800469de`: `The operation is not supported. Cannot import configuration from ProcessorArchitecture[%d] to ProcessorArchitecture[%d].\n`

## pseudocode

```c
__int64 __fastcall ApplySettings::ProcessSystemInfo(__int64 a1, __int64 a2)
{
  __int64 v3; // rbx
  const wchar_t *v5; // rcx
  __int16 v6; // bp
  const wchar_t *v7; // rcx
  const wchar_t *v8; // rcx
  int v9; // ecx
  char v10; // al

  v3 = a1 + 16;
  std::getline<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(a2, a1 + 16);
  std::getline<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(a2, v3);
  if ( *(_QWORD *)(v3 + 24) < 8u )
    v5 = (const wchar_t *)v3;
  else
    v5 = *(const wchar_t **)v3;
  v6 = wcstol(v5, 0, *(_DWORD *)(a1 + 32));
  std::getline<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(a2, v3);
  if ( *(_QWORD *)(v3 + 24) < 8u )
    v7 = (const wchar_t *)v3;
  else
    v7 = *(const wchar_t **)v3;
  wcstol(v7, 0, *(_DWORD *)(a1 + 32));
  std::getline<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(a2, v3);
  if ( *(_QWORD *)(v3 + 24) < 8u )
    v8 = (const wchar_t *)v3;
  else
    v8 = *(const wchar_t **)v3;
  wcstol(v8, 0, *(_DWORD *)(a1 + 32));
  std::getline<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(a2, v3);
  v9 = *(unsigned __int16 *)(a1 + 146);
  if ( v6 == (_WORD)v9 )
  {
    v10 = 0;
LABEL_15:
    *(_BYTE *)(a1 + 148) = v10;
    return 0;
  }
  if ( !v6 && v9 == 9 )
  {
    v10 = 1;
    goto LABEL_15;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WppDbgPrint("The operation is not supported. Cannot import configuration from ProcessorArchitecture[%d] to ProcessorA"
                "rchitecture[%d].\n");
    WPP_SF_sdd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      63,
      (unsigned int)&WPP_70cc9e363f77355498ae630336bd681a_Traceguids,
      (unsigned int)"NPSDS",
      v6,
      *(_WORD *)(a1 + 146));
  }
  return 50;
}

```

## disassembly

```asm
0x1800468f4  push    rbx
0x1800468f6  push    rbp
0x1800468f7  push    rsi
0x1800468f8  push    rdi
0x1800468f9  sub     rsp, 38h
0x1800468fd  mov     rsi, rdx
0x180046900  lea     rbx, [rcx+10h]
0x180046904  mov     rdi, rcx
0x180046907  mov     rdx, rbx
0x18004690a  mov     rcx, rsi
0x18004690d  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@AEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &,std::wstring &)
0x180046912  mov     rdx, rbx
0x180046915  mov     rcx, rsi
0x180046918  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@AEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &,std::wstring &)
0x18004691d  cmp     qword ptr [rbx+18h], 8
0x180046922  jb      short loc_180046929
0x180046924  mov     rcx, [rbx]
0x180046927  jmp     short loc_18004692C
0x180046929  mov     rcx, rbx; String
0x18004692c  mov     r8d, [rdi+20h]; Radix
0x180046930  xor     edx, edx; EndPtr
0x180046932  call    cs:__imp_wcstol
0x180046938  mov     rdx, rbx
0x18004693b  mov     rcx, rsi
0x18004693e  mov     ebp, eax
0x180046940  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@AEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &,std::wstring &)
0x180046945  cmp     qword ptr [rbx+18h], 8
0x18004694a  jb      short loc_180046951
0x18004694c  mov     rcx, [rbx]
0x18004694f  jmp     short loc_180046954
0x180046951  mov     rcx, rbx; String
0x180046954  mov     r8d, [rdi+20h]; Radix
0x180046958  xor     edx, edx; EndPtr
0x18004695a  call    cs:__imp_wcstol
0x180046960  mov     rdx, rbx
0x180046963  mov     rcx, rsi
0x180046966  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@AEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &,std::wstring &)
0x18004696b  cmp     qword ptr [rbx+18h], 8
0x180046970  jb      short loc_180046977
0x180046972  mov     rcx, [rbx]
0x180046975  jmp     short loc_18004697A
0x180046977  mov     rcx, rbx; String
0x18004697a  mov     r8d, [rdi+20h]; Radix
0x18004697e  xor     edx, edx; EndPtr
0x180046980  call    cs:__imp_wcstol
0x180046986  mov     rdx, rbx
0x180046989  mov     rcx, rsi
0x18004698c  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@AEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &,std::wstring &)
0x180046991  movzx   ecx, word ptr [rdi+92h]
0x180046998  cmp     bp, cx
0x18004699b  jnz     short loc_1800469A1
0x18004699d  xor     eax, eax
0x18004699f  jmp     short loc_1800469AD
0x1800469a1  test    bp, bp
0x1800469a4  jnz     short loc_1800469B7
0x1800469a6  cmp     ecx, 9
0x1800469a9  jnz     short loc_1800469B7
0x1800469ab  mov     al, 1
0x1800469ad  mov     [rdi+94h], al
0x1800469b3  xor     eax, eax
0x1800469b5  jmp     short loc_180046A21
0x1800469b7  mov     rax, cs:WPP_GLOBAL_Control
0x1800469be  lea     rdx, WPP_GLOBAL_Control
0x1800469c5  cmp     rax, rdx
0x1800469c8  jz      short loc_180046A1C
0x1800469ca  cmp     byte ptr [rax+19h], 2
0x1800469ce  jb      short loc_180046A1C
0x1800469d0  test    byte ptr [rax+1Ch], 10h
0x1800469d4  jz      short loc_180046A1C
0x1800469d6  mov     r8d, ecx
0x1800469d9  movzx   ebx, bp
0x1800469dc  mov     edx, ebx
0x1800469de  lea     rcx, aTheOperationIs; "The operation is not supported. Cannot "...
0x1800469e5  call    WppDbgPrint
0x1800469ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800469f1  lea     r9, aNpsds; "NPSDS"
0x1800469f8  movzx   eax, word ptr [rdi+92h]
0x1800469ff  lea     r8, WPP_70cc9e363f77355498ae630336bd681a_Traceguids
0x180046a06  mov     [rsp+58h+var_30], eax
0x180046a0a  mov     edx, 3Fh ; '?'
0x180046a0f  mov     [rsp+58h+var_38], ebx
0x180046a13  mov     rcx, [rcx+10h]
0x180046a17  call    WPP_SF_sdd
0x180046a1c  mov     eax, 32h ; '2'
0x180046a21  add     rsp, 38h
0x180046a25  pop     rdi
0x180046a26  pop     rsi
0x180046a27  pop     rbp
0x180046a28  pop     rbx
0x180046a29  retn
```
