# CdsQueryParser::ProcessLogOp(void)

- ea: `0x14006e3bc`
- end: `0x14006e63b`
- name: `?ProcessLogOp@CdsQueryParser@@AEAAJXZ`
- size: `639`
- prototype: `__int64 __fastcall(CdsQueryParser *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x14006dc3c`

## callees

- `0x140003750`
- `0x14000c920`
- `0x140027310`
- `0x14003e5f4`
- `0x14003f17c`
- `0x140047798`
- `0x14006d9c4`
- `0x14006e3bc`
- `0x14006fdd0`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x14006e4a6`
- `KERNEL32!CompareStringW` at `0x14006e521`
- `KERNEL32!CompareStringW` at `0x14006e4a6`
- `KERNEL32!CompareStringW` at `0x14006e521`

## pseudocode

```c
__int64 __fastcall CdsQueryParser::ProcessLogOp(CdsQueryParser *this)
{
  PVOID *v2; // rax
  __int64 v3; // rdx
  PCNZWCH *v4; // rax
  int v5; // ebx
  __int64 v6; // rdx
  PCNZWCH *v7; // rax
  int v8; // ebx
  __int64 v9; // rdx
  int v10; // ebx
  unsigned __int16 v11; // ax
  bool v12; // zf
  __int64 v14; // [rsp+50h] [rbp+8h] BYREF

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 256, &WPP_0792b396bb7638c3e84271d90cfade20_Traceguids);
      v2 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 && *((_BYTE *)v2 + 25) >= 5u )
    {
      WPP_SF_S(v2[2], 257, &WPP_0792b396bb7638c3e84271d90cfade20_Traceguids, *((_QWORD *)this + 3));
      v2 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( !*((_BYTE *)this + 32) )
  {
    if ( v2 == &WPP_GLOBAL_Control || (*((_BYTE *)v2 + 28) & 8) == 0 || *((_BYTE *)v2 + 25) < 2u )
      goto LABEL_36;
    v3 = 258;
    goto LABEL_13;
  }
  v4 = (PCNZWCH *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Left(
                    (char *)this + 24,
                    &v14,
                    3);
  v5 = CompareStringW(0x7Fu, 1u, *v4, -1, L"and", -1);
  ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v14);
  if ( v5 == 2 )
  {
    *((_DWORD *)this + 22) = 0;
    v2 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      v6 = 259;
LABEL_24:
      WPP_SF_(v2[2], v6, &WPP_0792b396bb7638c3e84271d90cfade20_Traceguids);
      v2 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  else
  {
    v7 = (PCNZWCH *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Left(
                      (char *)this + 24,
                      &v14,
                      2);
    v8 = CompareStringW(0x7Fu, 1u, *v7, -1, L"or", -1);
    ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v14);
    if ( v8 != 2 )
    {
      v2 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_36;
      }
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        261,
        &WPP_0792b396bb7638c3e84271d90cfade20_Traceguids,
        *((_QWORD *)this + 3));
      goto LABEL_35;
    }
    CdsParseLevel::StartNewProduct((CdsQueryParser *)((char *)this + 88));
    *((_DWORD *)this + 22) = 0;
    v2 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      v6 = 260;
      goto LABEL_24;
    }
  }
  v9 = *((unsigned int *)this + 3);
  if ( (int)v9 >= *((_DWORD *)this + 2)
    || (v10 = 0,
        v11 = ATL::CSimpleStringT<unsigned short,0>::operator[](this, v9),
        v12 = !IsCDSSearchCriteriaWhiteSpace(v11),
        v2 = (PVOID *)WPP_GLOBAL_Control,
        v12) )
  {
    if ( v2 == &WPP_GLOBAL_Control || (*((_BYTE *)v2 + 28) & 8) == 0 || *((_BYTE *)v2 + 25) < 2u )
      goto LABEL_36;
    v3 = 262;
LABEL_13:
    WPP_SF_(v2[2], v3, &WPP_0792b396bb7638c3e84271d90cfade20_Traceguids);
LABEL_35:
    v2 = (PVOID *)WPP_GLOBAL_Control;
LABEL_36:
    v10 = -2147220628;
  }
  if ( v2 != &WPP_GLOBAL_Control
    && (*((_BYTE *)v2 + 28) & 1) != 0
    && *((unsigned __int8 *)v2 + 25) >= ((v10 >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_d(v2[2], 263, &WPP_0792b396bb7638c3e84271d90cfade20_Traceguids, (unsigned int)v10);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14006e3bc  mov     [rsp+arg_8], rbx
0x14006e3c1  mov     [rsp+arg_10], rbp
0x14006e3c6  push    rsi
0x14006e3c7  push    rdi
0x14006e3c8  push    r14
0x14006e3ca  sub     rsp, 30h
0x14006e3ce  mov     rdi, rcx
0x14006e3d1  mov     rax, cs:WPP_GLOBAL_Control
0x14006e3d8  lea     rbp, WPP_GLOBAL_Control
0x14006e3df  lea     r14, WPP_0792b396bb7638c3e84271d90cfade20_Traceguids
0x14006e3e6  cmp     rax, rbp
0x14006e3e9  jz      short loc_14006E436
0x14006e3eb  test    byte ptr [rax+1Ch], 1
0x14006e3ef  jz      short loc_14006E409
0x14006e3f1  mov     rcx, [rax+10h]
0x14006e3f5  mov     edx, 100h
0x14006e3fa  mov     r8, r14
0x14006e3fd  call    WPP_SF_
0x14006e402  mov     rax, cs:WPP_GLOBAL_Control
0x14006e409  cmp     rax, rbp
0x14006e40c  jz      short loc_14006E436
0x14006e40e  test    byte ptr [rax+1Ch], 8
0x14006e412  jz      short loc_14006E436
0x14006e414  cmp     byte ptr [rax+19h], 5
0x14006e418  jb      short loc_14006E436
0x14006e41a  mov     r9, [rdi+18h]
0x14006e41e  mov     edx, 101h
0x14006e423  mov     rcx, [rax+10h]
0x14006e427  mov     r8, r14
0x14006e42a  call    WPP_SF_S
0x14006e42f  mov     rax, cs:WPP_GLOBAL_Control
0x14006e436  cmp     byte ptr [rdi+20h], 0
0x14006e43a  jnz     short loc_14006E46F
0x14006e43c  cmp     rax, rbp
0x14006e43f  jz      loc_14006E5EF
0x14006e445  test    byte ptr [rax+1Ch], 8
0x14006e449  jz      loc_14006E5EF
0x14006e44f  cmp     byte ptr [rax+19h], 2
0x14006e453  jb      loc_14006E5EF
0x14006e459  mov     edx, 102h
0x14006e45e  mov     rcx, [rax+10h]
0x14006e462  mov     r8, r14
0x14006e465  call    WPP_SF_
0x14006e46a  jmp     loc_14006E5E8
0x14006e46f  lea     rsi, [rdi+18h]
0x14006e473  mov     r8d, 3
0x14006e479  mov     rcx, rsi
0x14006e47c  lea     rdx, [rsp+48h+arg_0]
0x14006e481  call    ?Left@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::Left(int)
0x14006e486  or      edx, 0FFFFFFFFh
0x14006e489  lea     rcx, aAnd_2; "and"
0x14006e490  mov     [rsp+48h+cchCount2], edx; cchCount2
0x14006e494  mov     r9d, edx; cchCount1
0x14006e497  mov     [rsp+48h+lpString2], rcx; lpString2
0x14006e49c  mov     r8, [rax]; lpString1
0x14006e49f  lea     edx, [r9+2]; dwCmpFlags
0x14006e4a3  lea     ecx, [rdx+7Eh]; Locale
0x14006e4a6  call    cs:__imp_CompareStringW
0x14006e4ac  lea     rcx, [rsp+48h+arg_0]
0x14006e4b1  mov     ebx, eax
0x14006e4b3  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14006e4b8  cmp     ebx, 2
0x14006e4bb  jnz     short loc_14006E4EF
0x14006e4bd  mov     dword ptr [rdi+58h], 0
0x14006e4c4  mov     rax, cs:WPP_GLOBAL_Control
0x14006e4cb  cmp     rax, rbp
0x14006e4ce  jz      loc_14006E57C
0x14006e4d4  test    byte ptr [rax+1Ch], 8
0x14006e4d8  jz      loc_14006E57C
0x14006e4de  cmp     byte ptr [rax+19h], 5
0x14006e4e2  jb      loc_14006E57C
0x14006e4e8  mov     edx, 103h
0x14006e4ed  jmp     short loc_14006E569
0x14006e4ef  mov     r8d, 2
0x14006e4f5  lea     rdx, [rsp+48h+arg_0]
0x14006e4fa  mov     rcx, rsi
0x14006e4fd  call    ?Left@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::Left(int)
0x14006e502  lea     rdx, aOr; "or"
0x14006e509  or      r9d, 0FFFFFFFFh; cchCount1
0x14006e50d  mov     [rsp+48h+cchCount2], r9d; cchCount2
0x14006e512  mov     [rsp+48h+lpString2], rdx; lpString2
0x14006e517  mov     r8, [rax]; lpString1
0x14006e51a  lea     edx, [r9+2]; dwCmpFlags
0x14006e51e  lea     ecx, [rdx+7Eh]; Locale
0x14006e521  call    cs:__imp_CompareStringW
0x14006e527  lea     rcx, [rsp+48h+arg_0]
0x14006e52c  mov     ebx, eax
0x14006e52e  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14006e533  cmp     ebx, 2
0x14006e536  jnz     loc_14006E5BC
0x14006e53c  lea     rcx, [rdi+58h]; this
0x14006e540  call    ?StartNewProduct@CdsParseLevel@@QEAAXXZ; CdsParseLevel::StartNewProduct(void)
0x14006e545  mov     dword ptr [rdi+58h], 0
0x14006e54c  mov     rax, cs:WPP_GLOBAL_Control
0x14006e553  cmp     rax, rbp
0x14006e556  jz      short loc_14006E57C
0x14006e558  test    byte ptr [rax+1Ch], 8
0x14006e55c  jz      short loc_14006E57C
0x14006e55e  cmp     byte ptr [rax+19h], 5
0x14006e562  jb      short loc_14006E57C
0x14006e564  mov     edx, 104h
0x14006e569  mov     rcx, [rax+10h]
0x14006e56d  mov     r8, r14
0x14006e570  call    WPP_SF_
0x14006e575  mov     rax, cs:WPP_GLOBAL_Control
0x14006e57c  mov     edx, [rdi+0Ch]
0x14006e57f  cmp     edx, [rdi+8]
0x14006e582  jge     short loc_14006E5A1
0x14006e584  mov     rcx, rdi
0x14006e587  xor     ebx, ebx
0x14006e589  call    ??A?$CSimpleStringT@G$0A@@ATL@@QEBAGH@Z; ATL::CSimpleStringT<ushort,0>::operator[](int)
0x14006e58e  movzx   ecx, ax; unsigned __int16
0x14006e591  call    ?IsCDSSearchCriteriaWhiteSpace@@YA_NG@Z; IsCDSSearchCriteriaWhiteSpace(ushort)
0x14006e596  test    al, al
0x14006e598  mov     rax, cs:WPP_GLOBAL_Control
0x14006e59f  jnz     short loc_14006E5F4
0x14006e5a1  cmp     rax, rbp
0x14006e5a4  jz      short loc_14006E5EF
0x14006e5a6  test    byte ptr [rax+1Ch], 8
0x14006e5aa  jz      short loc_14006E5EF
0x14006e5ac  cmp     byte ptr [rax+19h], 2
0x14006e5b0  jb      short loc_14006E5EF
0x14006e5b2  mov     edx, 106h
0x14006e5b7  jmp     loc_14006E45E
0x14006e5bc  mov     rax, cs:WPP_GLOBAL_Control
0x14006e5c3  cmp     rax, rbp
0x14006e5c6  jz      short loc_14006E5EF
0x14006e5c8  test    byte ptr [rax+1Ch], 8
0x14006e5cc  jz      short loc_14006E5EF
0x14006e5ce  cmp     byte ptr [rax+19h], 2
0x14006e5d2  jb      short loc_14006E5EF
0x14006e5d4  mov     r9, [rsi]
0x14006e5d7  mov     edx, 105h
0x14006e5dc  mov     rcx, [rax+10h]
0x14006e5e0  mov     r8, r14
0x14006e5e3  call    WPP_SF_S
0x14006e5e8  mov     rax, cs:WPP_GLOBAL_Control
0x14006e5ef  mov     ebx, 8004036Ch
0x14006e5f4  cmp     rax, rbp
0x14006e5f7  jz      short loc_14006E626
0x14006e5f9  test    byte ptr [rax+1Ch], 1
0x14006e5fd  jz      short loc_14006E626
0x14006e5ff  movzx   ecx, byte ptr [rax+19h]
0x14006e603  mov     edx, ebx
0x14006e605  sar     edx, 1Fh
0x14006e608  and     edx, 0FFFFFFFDh
0x14006e60b  add     edx, 5
0x14006e60e  cmp     ecx, edx
0x14006e610  jb      short loc_14006E626
0x14006e612  mov     rcx, [rax+10h]
0x14006e616  mov     edx, 107h
0x14006e61b  mov     r9d, ebx
0x14006e61e  mov     r8, r14
0x14006e621  call    WPP_SF_d
0x14006e626  mov     rbp, [rsp+48h+arg_10]
0x14006e62b  mov     eax, ebx
0x14006e62d  mov     rbx, [rsp+48h+arg_8]
0x14006e632  add     rsp, 30h
0x14006e636  pop     r14
0x14006e638  pop     rdi
0x14006e639  pop     rsi
0x14006e63a  retn
```
