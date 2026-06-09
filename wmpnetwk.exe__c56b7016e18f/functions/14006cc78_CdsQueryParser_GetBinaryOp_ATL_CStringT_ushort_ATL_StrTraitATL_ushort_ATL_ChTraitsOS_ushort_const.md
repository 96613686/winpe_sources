# CdsQueryParser::GetBinaryOp(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &)

- ea: `0x14006cc78`
- end: `0x14006ce99`
- name: `?GetBinaryOp@CdsQueryParser@@CA?AW4Op@CdsBinaryOp@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@Z`
- size: `545`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14006e644`

## callees

- `0x140003750`
- `0x14000c920`
- `0x140034e14`
- `0x14003e5f4`
- `0x14003f17c`
- `0x14006cc78`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x14006cda4`
- `KERNEL32!CompareStringW` at `0x14006cdf7`
- `KERNEL32!CompareStringW` at `0x14006ce3d`
- `KERNEL32!CompareStringW` at `0x14006cda4`
- `KERNEL32!CompareStringW` at `0x14006cdf7`
- `KERNEL32!CompareStringW` at `0x14006ce3d`

## pseudocode

```c
__int64 __fastcall CdsQueryParser::GetBinaryOp(_QWORD *a1)
{
  unsigned int v2; // esi
  int v3; // edi
  PCNZWCH *v4; // rax
  int v5; // ebx
  PCNZWCH *v6; // rax
  int v7; // ebx
  PCNZWCH *v8; // rax
  int v9; // ebx
  __int64 v11; // [rsp+78h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 264, &WPP_0792b396bb7638c3e84271d90cfade20_Traceguids, *a1);
  }
  if ( (unsigned __int8)ATL::operator==(a1, L"=") )
  {
    v2 = 1;
  }
  else if ( (unsigned __int8)ATL::operator==(a1, L"!=") )
  {
    v2 = 2;
  }
  else if ( (unsigned __int8)ATL::operator==(a1, "<") )
  {
    v2 = 3;
  }
  else if ( (unsigned __int8)ATL::operator==(a1, L"<=") )
  {
    v2 = 4;
  }
  else if ( (unsigned __int8)ATL::operator==(a1, L">") )
  {
    v2 = 5;
  }
  else if ( (unsigned __int8)ATL::operator==(a1, L">=") )
  {
    v2 = 6;
  }
  else
  {
    v3 = 8;
    v4 = (PCNZWCH *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Left(
                      a1,
                      &v11,
                      8);
    v5 = CompareStringW(0x7Fu, 1u, *v4, -1, L"contains", -1);
    ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v11);
    if ( v5 == 2 )
    {
      v2 = 7;
    }
    else
    {
      v6 = (PCNZWCH *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Left(
                        a1,
                        &v11,
                        14);
      v7 = CompareStringW(0x7Fu, 1u, *v6, -1, L"doesNotContain", -1);
      ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v11);
      if ( v7 != 2 )
      {
        v3 = 0;
        v8 = (PCNZWCH *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Left(
                          a1,
                          &v11,
                          11);
        v9 = CompareStringW(0x7Fu, 1u, *v8, -1, L"derivedfrom", -1);
        ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v11);
        if ( v9 == 2 )
          v3 = 9;
      }
      v2 = v3;
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 265, &WPP_0792b396bb7638c3e84271d90cfade20_Traceguids, v2);
  }
  return v2;
}

```

## disassembly

```asm
0x14006cc78  push    rbx
0x14006cc7a  push    rsi
0x14006cc7b  push    rdi
0x14006cc7c  push    r12
0x14006cc7e  push    r14
0x14006cc80  push    r15
0x14006cc82  sub     rsp, 38h
0x14006cc86  mov     r14, rcx
0x14006cc89  mov     rcx, cs:WPP_GLOBAL_Control
0x14006cc90  lea     r12, WPP_GLOBAL_Control
0x14006cc97  cmp     rcx, r12
0x14006cc9a  jz      short loc_14006CCC0
0x14006cc9c  test    byte ptr [rcx+1Ch], 1
0x14006cca0  jz      short loc_14006CCC0
0x14006cca2  cmp     byte ptr [rcx+19h], 5
0x14006cca6  jb      short loc_14006CCC0
0x14006cca8  mov     r9, [r14]
0x14006ccab  lea     r8, WPP_0792b396bb7638c3e84271d90cfade20_Traceguids
0x14006ccb2  mov     rcx, [rcx+10h]
0x14006ccb6  mov     edx, 108h
0x14006ccbb  call    WPP_SF_S
0x14006ccc0  lea     rdx, asc_1400A28A4; "="
0x14006ccc7  mov     rcx, r14
0x14006ccca  call    ??8ATL@@YA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@0@PEBG@Z; ATL::operator==(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,ushort const *)
0x14006cccf  test    al, al
0x14006ccd1  jz      short loc_14006CCDD
0x14006ccd3  mov     esi, 1
0x14006ccd8  jmp     loc_14006CE59
0x14006ccdd  lea     rdx, asc_1400A9578; "!="
0x14006cce4  mov     rcx, r14
0x14006cce7  call    ??8ATL@@YA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@0@PEBG@Z; ATL::operator==(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,ushort const *)
0x14006ccec  test    al, al
0x14006ccee  jz      short loc_14006CCFA
0x14006ccf0  mov     esi, 2
0x14006ccf5  jmp     loc_14006CE59
0x14006ccfa  lea     rdx, ?s_chBase64EncodingTable@?1??Base64Encode@ATL@@YAHPEBEHPEADPEAHK@Z@4QBDB+40h; "<"
0x14006cd01  mov     rcx, r14
0x14006cd04  call    ??8ATL@@YA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@0@PEBG@Z; ATL::operator==(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,ushort const *)
0x14006cd09  test    al, al
0x14006cd0b  jz      short loc_14006CD17
0x14006cd0d  mov     esi, 3
0x14006cd12  jmp     loc_14006CE59
0x14006cd17  lea     rdx, asc_1400A9580; "<="
0x14006cd1e  mov     rcx, r14
0x14006cd21  call    ??8ATL@@YA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@0@PEBG@Z; ATL::operator==(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,ushort const *)
0x14006cd26  test    al, al
0x14006cd28  jz      short loc_14006CD34
0x14006cd2a  mov     esi, 4
0x14006cd2f  jmp     loc_14006CE59
0x14006cd34  lea     rdx, asc_1400A3CBC; ">"
0x14006cd3b  mov     rcx, r14
0x14006cd3e  call    ??8ATL@@YA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@0@PEBG@Z; ATL::operator==(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,ushort const *)
0x14006cd43  test    al, al
0x14006cd45  jz      short loc_14006CD51
0x14006cd47  mov     esi, 5
0x14006cd4c  jmp     loc_14006CE59
0x14006cd51  lea     rdx, asc_1400A9588; ">="
0x14006cd58  mov     rcx, r14
0x14006cd5b  call    ??8ATL@@YA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@0@PEBG@Z; ATL::operator==(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,ushort const *)
0x14006cd60  test    al, al
0x14006cd62  jz      short loc_14006CD6E
0x14006cd64  mov     esi, 6
0x14006cd69  jmp     loc_14006CE59
0x14006cd6e  mov     edi, 8
0x14006cd73  lea     rdx, [rsp+68h+arg_8]
0x14006cd78  mov     r8d, edi
0x14006cd7b  mov     rcx, r14
0x14006cd7e  call    ?Left@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::Left(int)
0x14006cd83  lea     rcx, aContains_0; "contains"
0x14006cd8a  or      r15d, 0FFFFFFFFh
0x14006cd8e  mov     [rsp+68h+cchCount2], r15d; cchCount2
0x14006cd93  lea     edx, [rdi-7]; dwCmpFlags
0x14006cd96  mov     [rsp+68h+lpString2], rcx; lpString2
0x14006cd9b  mov     r9d, r15d; cchCount1
0x14006cd9e  mov     r8, [rax]; lpString1
0x14006cda1  lea     ecx, [rdi+77h]; Locale
0x14006cda4  call    cs:__imp_CompareStringW
0x14006cdaa  lea     rcx, [rsp+68h+arg_8]
0x14006cdaf  mov     ebx, eax
0x14006cdb1  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14006cdb6  lea     esi, [rdi-6]
0x14006cdb9  cmp     ebx, esi
0x14006cdbb  jnz     short loc_14006CDC5
0x14006cdbd  lea     esi, [rdi-1]
0x14006cdc0  jmp     loc_14006CE59
0x14006cdc5  mov     r8d, 0Eh
0x14006cdcb  lea     rdx, [rsp+68h+arg_8]
0x14006cdd0  mov     rcx, r14
0x14006cdd3  call    ?Left@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::Left(int)
0x14006cdd8  lea     rcx, aDoesnotcontain; "doesNotContain"
0x14006cddf  mov     [rsp+68h+cchCount2], r15d; cchCount2
0x14006cde4  mov     edx, 1; dwCmpFlags
0x14006cde9  mov     [rsp+68h+lpString2], rcx; lpString2
0x14006cdee  mov     r9d, r15d; cchCount1
0x14006cdf1  mov     r8, [rax]; lpString1
0x14006cdf4  lea     ecx, [rdx+7Eh]; Locale
0x14006cdf7  call    cs:__imp_CompareStringW
0x14006cdfd  lea     rcx, [rsp+68h+arg_8]
0x14006ce02  mov     ebx, eax
0x14006ce04  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14006ce09  cmp     ebx, esi
0x14006ce0b  jz      short loc_14006CE57
0x14006ce0d  xor     edi, edi
0x14006ce0f  lea     rdx, [rsp+68h+arg_8]
0x14006ce14  mov     rcx, r14
0x14006ce17  lea     r8d, [rdi+0Bh]
0x14006ce1b  call    ?Left@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::Left(int)
0x14006ce20  lea     rdx, aDerivedfrom; "derivedfrom"
0x14006ce27  mov     [rsp+68h+cchCount2], r15d; cchCount2
0x14006ce2c  mov     [rsp+68h+lpString2], rdx; lpString2
0x14006ce31  lea     ecx, [rdi+7Fh]; Locale
0x14006ce34  lea     edx, [rdi+1]; dwCmpFlags
0x14006ce37  mov     r9d, r15d; cchCount1
0x14006ce3a  mov     r8, [rax]; lpString1
0x14006ce3d  call    cs:__imp_CompareStringW
0x14006ce43  lea     rcx, [rsp+68h+arg_8]
0x14006ce48  mov     ebx, eax
0x14006ce4a  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14006ce4f  cmp     ebx, esi
0x14006ce51  lea     eax, [rdi+9]
0x14006ce54  cmovz   edi, eax
0x14006ce57  mov     esi, edi
0x14006ce59  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ce60  cmp     rcx, r12
0x14006ce63  jz      short loc_14006CE89
0x14006ce65  test    byte ptr [rcx+1Ch], 1
0x14006ce69  jz      short loc_14006CE89
0x14006ce6b  cmp     byte ptr [rcx+19h], 5
0x14006ce6f  jb      short loc_14006CE89
0x14006ce71  mov     rcx, [rcx+10h]
0x14006ce75  lea     r8, WPP_0792b396bb7638c3e84271d90cfade20_Traceguids
0x14006ce7c  mov     edx, 109h
0x14006ce81  mov     r9d, esi
0x14006ce84  call    WPP_SF_d
0x14006ce89  mov     eax, esi
0x14006ce8b  add     rsp, 38h
0x14006ce8f  pop     r15
0x14006ce91  pop     r14
0x14006ce93  pop     r12
0x14006ce95  pop     rdi
0x14006ce96  pop     rsi
0x14006ce97  pop     rbx
0x14006ce98  retn
```
