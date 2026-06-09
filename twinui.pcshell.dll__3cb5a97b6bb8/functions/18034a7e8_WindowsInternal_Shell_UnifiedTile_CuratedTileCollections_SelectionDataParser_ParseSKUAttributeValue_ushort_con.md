# WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::SelectionDataParser::ParseSKUAttributeValue(ushort const *,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::SelectionData &)

- ea: `0x18034a7e8`
- end: `0x18034aa5b`
- name: `?ParseSKUAttributeValue@SelectionDataParser@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@AEAAJPEBGAEAUSelectionData@2345@@Z`
- size: `627`
- prototype: `int(WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::SelectionDataParser *__hidden this, const unsigned __int16 *, struct WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::SelectionData *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18034a7b0`

## callees

- `0x1800237c8`
- `0x180204d38`
- `0x18034a7e8`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18034a81f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18034a84a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18034a873`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18034a8b0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18034a8f3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18034a91c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18034a945`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18034a982`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18034a9a8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18034a9ce`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18034a9f4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18034a81f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18034a84a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18034a873`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18034a8b0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18034a8f3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18034a91c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18034a945`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18034a982`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18034a9a8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18034a9ce`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18034a9f4`

## string_xrefs

- `0x18034aa33`: `shellcommon\shell\tiles\curatedtilecollections\collectioninitialization\helpers\selectiondataparser.cpp`
- `0x18034a815`: `DesktopEnterprise`
- `0x18034a83e`: `DesktopEnterpriseN`

## pseudocode

```c
__int64 __fastcall WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::SelectionDataParser::ParseSKUAttributeValue(
        WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::SelectionDataParser *this,
        const unsigned __int16 *a2,
        struct WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::SelectionData *a3)
{
  int v5; // eax
  char *v6; // rcx
  int *v7; // rdx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+30h]
  WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::SelectionDataParser *v11; // [rsp+70h] [rbp+38h] BYREF

  v11 = this;
  if ( CompareStringOrdinal(a2, -1, L"DesktopEnterprise", -1, 1) == 2 )
  {
    v5 = 3;
    goto LABEL_26;
  }
  if ( CompareStringOrdinal(a2, -1, L"DesktopEnterpriseN", -1, 1) == 2 )
  {
    v5 = 5;
    goto LABEL_26;
  }
  if ( CompareStringOrdinal(a2, -1, L"Desktop", -1, 1) == 2 )
  {
    v6 = (char *)a3 + 40;
    LODWORD(v11) = 2;
    v7 = (int *)*((_QWORD *)a3 + 6);
    if ( v7 == *((int **)a3 + 7) )
      goto LABEL_29;
    *v7 = 2;
LABEL_28:
    *((_QWORD *)v6 + 1) += 4LL;
LABEL_30:
    *((_BYTE *)a3 + 3) = 1;
    return 0;
  }
  if ( CompareStringOrdinal(a2, -1, L"DesktopN", -1, 1) == 2 )
  {
    v6 = (char *)a3 + 40;
    LODWORD(v11) = 4;
    v7 = (int *)*((_QWORD *)a3 + 6);
    if ( v7 == *((int **)a3 + 7) )
      goto LABEL_29;
    *v7 = 4;
    goto LABEL_28;
  }
  if ( CompareStringOrdinal(a2, -1, L"DesktopCloud", -1, 1) == 2 )
  {
    v5 = 11;
    goto LABEL_26;
  }
  if ( CompareStringOrdinal(a2, -1, L"DesktopCloudN", -1, 1) == 2 )
  {
    v5 = 12;
    goto LABEL_26;
  }
  if ( CompareStringOrdinal(a2, -1, L"DesktopARM", -1, 1) == 2 )
  {
    v6 = (char *)a3 + 40;
    LODWORD(v11) = 1;
    v7 = (int *)*((_QWORD *)a3 + 6);
    if ( v7 == *((int **)a3 + 7) )
      goto LABEL_29;
    *v7 = 1;
    goto LABEL_28;
  }
  if ( CompareStringOrdinal(a2, -1, L"Mobile", -1, 1) == 2 )
  {
    v5 = 8;
    goto LABEL_26;
  }
  if ( CompareStringOrdinal(a2, -1, L"Server", -1, 1) == 2 )
  {
    v5 = 6;
    goto LABEL_26;
  }
  if ( CompareStringOrdinal(a2, -1, L"ServerSolution", -1, 1) == 2 )
  {
    v5 = 7;
    goto LABEL_26;
  }
  if ( CompareStringOrdinal(a2, -1, L"LongTermServicingBranch", -1, 1) == 2 )
  {
    v5 = 10;
LABEL_26:
    v6 = (char *)a3 + 40;
    LODWORD(v11) = v5;
    v7 = (int *)*((_QWORD *)a3 + 6);
    if ( v7 != *((int **)a3 + 7) )
    {
      *v7 = v5;
      goto LABEL_28;
    }
LABEL_29:
    std::vector<enum WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionSKU>::_Emplace_reallocate<enum WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionSKU const &>(
      v6,
      v7,
      &v11);
    goto LABEL_30;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xAD,
    (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitialization\\helpers\\selectiondataparser.cpp",
    (const char *)0xC00CE225LL,
    bIgnoreCase);
  return 3222069797LL;
}

```

## disassembly

```asm
0x18034a7e8  mov     [rsp-30h+arg_0], rcx
0x18034a7ed  push    rbp
0x18034a7ee  push    rbx
0x18034a7ef  push    rsi
0x18034a7f0  push    rdi
0x18034a7f1  push    r14
0x18034a7f3  push    r15
0x18034a7f5  mov     rbp, rsp
0x18034a7f8  sub     rsp, 38h
0x18034a7fc  mov     rdi, rdx
0x18034a7ff  or      esi, 0FFFFFFFFh
0x18034a802  mov     rbx, r8
0x18034a805  mov     r15d, 1
0x18034a80b  mov     r9d, esi; cchCount2
0x18034a80e  mov     [rsp+38h+bIgnoreCase], r15d; bIgnoreCase
0x18034a813  mov     edx, esi; cchCount1
0x18034a815  lea     r8, aDesktopenterpr; "DesktopEnterprise"
0x18034a81c  mov     rcx, rdi; lpString1
0x18034a81f  call    cs:__imp_CompareStringOrdinal
0x18034a825  lea     r14d, [r15+1]
0x18034a829  cmp     eax, r14d
0x18034a82c  jnz     short loc_18034A836
0x18034a82e  lea     eax, [rsi+4]
0x18034a831  jmp     loc_18034AA04
0x18034a836  mov     r9d, esi; cchCount2
0x18034a839  mov     [rsp+38h+bIgnoreCase], r15d; bIgnoreCase
0x18034a83e  lea     r8, aDesktopenterpr_0; "DesktopEnterpriseN"
0x18034a845  mov     edx, esi; cchCount1
0x18034a847  mov     rcx, rdi; lpString1
0x18034a84a  call    cs:__imp_CompareStringOrdinal
0x18034a850  cmp     eax, r14d
0x18034a853  jnz     short loc_18034A85F
0x18034a855  mov     eax, 5
0x18034a85a  jmp     loc_18034AA04
0x18034a85f  mov     r9d, esi; cchCount2
0x18034a862  mov     [rsp+38h+bIgnoreCase], r15d; bIgnoreCase
0x18034a867  lea     r8, aDesktop; "Desktop"
0x18034a86e  mov     edx, esi; cchCount1
0x18034a870  mov     rcx, rdi; lpString1
0x18034a873  call    cs:__imp_CompareStringOrdinal
0x18034a879  cmp     eax, r14d
0x18034a87c  jnz     short loc_18034A89C
0x18034a87e  lea     rcx, [rbx+28h]
0x18034a882  mov     dword ptr [rbp+arg_0], r14d
0x18034a886  mov     rdx, [rcx+8]
0x18034a88a  cmp     rdx, [rcx+10h]
0x18034a88e  jz      loc_18034AA1E
0x18034a894  mov     [rdx], r14d
0x18034a897  jmp     loc_18034AA17
0x18034a89c  mov     r9d, esi; cchCount2
0x18034a89f  mov     [rsp+38h+bIgnoreCase], r15d; bIgnoreCase
0x18034a8a4  lea     r8, aDesktopn; "DesktopN"
0x18034a8ab  mov     edx, esi; cchCount1
0x18034a8ad  mov     rcx, rdi; lpString1
0x18034a8b0  call    cs:__imp_CompareStringOrdinal
0x18034a8b6  cmp     eax, r14d
0x18034a8b9  jnz     short loc_18034A8DF
0x18034a8bb  lea     rcx, [rbx+28h]
0x18034a8bf  mov     dword ptr [rbp+arg_0], 4
0x18034a8c6  mov     rdx, [rcx+8]
0x18034a8ca  cmp     rdx, [rcx+10h]
0x18034a8ce  jz      loc_18034AA1E
0x18034a8d4  mov     dword ptr [rdx], 4
0x18034a8da  jmp     loc_18034AA17
0x18034a8df  mov     r9d, esi; cchCount2
0x18034a8e2  mov     [rsp+38h+bIgnoreCase], r15d; bIgnoreCase
0x18034a8e7  lea     r8, aDesktopcloud; "DesktopCloud"
0x18034a8ee  mov     edx, esi; cchCount1
0x18034a8f0  mov     rcx, rdi; lpString1
0x18034a8f3  call    cs:__imp_CompareStringOrdinal
0x18034a8f9  cmp     eax, r14d
0x18034a8fc  jnz     short loc_18034A908
0x18034a8fe  mov     eax, 0Bh
0x18034a903  jmp     loc_18034AA04
0x18034a908  mov     r9d, esi; cchCount2
0x18034a90b  mov     [rsp+38h+bIgnoreCase], r15d; bIgnoreCase
0x18034a910  lea     r8, aDesktopcloudn; "DesktopCloudN"
0x18034a917  mov     edx, esi; cchCount1
0x18034a919  mov     rcx, rdi; lpString1
0x18034a91c  call    cs:__imp_CompareStringOrdinal
0x18034a922  cmp     eax, r14d
0x18034a925  jnz     short loc_18034A931
0x18034a927  mov     eax, 0Ch
0x18034a92c  jmp     loc_18034AA04
0x18034a931  mov     r9d, esi; cchCount2
0x18034a934  mov     [rsp+38h+bIgnoreCase], r15d; bIgnoreCase
0x18034a939  lea     r8, aDesktoparm; "DesktopARM"
0x18034a940  mov     edx, esi; cchCount1
0x18034a942  mov     rcx, rdi; lpString1
0x18034a945  call    cs:__imp_CompareStringOrdinal
0x18034a94b  cmp     eax, r14d
0x18034a94e  jnz     short loc_18034A96E
0x18034a950  lea     rcx, [rbx+28h]
0x18034a954  mov     dword ptr [rbp+arg_0], r15d
0x18034a958  mov     rdx, [rcx+8]
0x18034a95c  cmp     rdx, [rcx+10h]
0x18034a960  jz      loc_18034AA1E
0x18034a966  mov     [rdx], r15d
0x18034a969  jmp     loc_18034AA17
0x18034a96e  mov     r9d, esi; cchCount2
0x18034a971  mov     [rsp+38h+bIgnoreCase], r15d; bIgnoreCase
0x18034a976  lea     r8, aMobile; "Mobile"
0x18034a97d  mov     edx, esi; cchCount1
0x18034a97f  mov     rcx, rdi; lpString1
0x18034a982  call    cs:__imp_CompareStringOrdinal
0x18034a988  cmp     eax, r14d
0x18034a98b  jnz     short loc_18034A994
0x18034a98d  mov     eax, 8
0x18034a992  jmp     short loc_18034AA04
0x18034a994  mov     r9d, esi; cchCount2
0x18034a997  mov     [rsp+38h+bIgnoreCase], r15d; bIgnoreCase
0x18034a99c  lea     r8, aServer; "Server"
0x18034a9a3  mov     edx, esi; cchCount1
0x18034a9a5  mov     rcx, rdi; lpString1
0x18034a9a8  call    cs:__imp_CompareStringOrdinal
0x18034a9ae  cmp     eax, r14d
0x18034a9b1  jnz     short loc_18034A9BA
0x18034a9b3  mov     eax, 6
0x18034a9b8  jmp     short loc_18034AA04
0x18034a9ba  mov     r9d, esi; cchCount2
0x18034a9bd  mov     [rsp+38h+bIgnoreCase], r15d; bIgnoreCase
0x18034a9c2  lea     r8, aServersolution; "ServerSolution"
0x18034a9c9  mov     edx, esi; cchCount1
0x18034a9cb  mov     rcx, rdi; lpString1
0x18034a9ce  call    cs:__imp_CompareStringOrdinal
0x18034a9d4  cmp     eax, r14d
0x18034a9d7  jnz     short loc_18034A9E0
0x18034a9d9  mov     eax, 7
0x18034a9de  jmp     short loc_18034AA04
0x18034a9e0  mov     r9d, esi; cchCount2
0x18034a9e3  mov     [rsp+38h+bIgnoreCase], r15d; int
0x18034a9e8  lea     r8, aLongtermservic; "LongTermServicingBranch"
0x18034a9ef  mov     edx, esi; cchCount1
0x18034a9f1  mov     rcx, rdi; lpString1
0x18034a9f4  call    cs:__imp_CompareStringOrdinal
0x18034a9fa  cmp     eax, r14d
0x18034a9fd  jnz     short loc_18034AA2F
0x18034a9ff  mov     eax, 0Ah
0x18034aa04  lea     rcx, [rbx+28h]
0x18034aa08  mov     dword ptr [rbp+arg_0], eax
0x18034aa0b  mov     rdx, [rcx+8]
0x18034aa0f  cmp     rdx, [rcx+10h]
0x18034aa13  jz      short loc_18034AA1E
0x18034aa15  mov     [rdx], eax
0x18034aa17  add     qword ptr [rcx+8], 4
0x18034aa1c  jmp     short loc_18034AA27
0x18034aa1e  lea     r8, [rbp+arg_0]
0x18034aa22  call    ??$_Emplace_reallocate@AEBW4CollectionSKU@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@?$vector@W4CollectionSKU@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@V?$allocator@W4CollectionSKU@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@@std@@AEAAPEAW4CollectionSKU@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@QEAW423456@AEBW423456@@Z; std::vector<WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionSKU>::_Emplace_reallocate<WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionSKU const &>(WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionSKU * const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionSKU const &)
0x18034aa27  mov     [rbx+3], r15b
0x18034aa2b  xor     eax, eax
0x18034aa2d  jmp     short loc_18034AA4E
0x18034aa2f  mov     rcx, [rbp+30h]; this
0x18034aa33  lea     r8, aShellcommonShe; "shellcommon\\shell\\tiles\\curatedtilec"...
0x18034aa3a  mov     ebx, 0C00CE225h
0x18034aa3f  mov     edx, 0ADh; void *
0x18034aa44  mov     r9d, ebx; char *
0x18034aa47  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18034aa4c  mov     eax, ebx
0x18034aa4e  add     rsp, 38h
0x18034aa52  pop     r15
0x18034aa54  pop     r14
0x18034aa56  pop     rdi
0x18034aa57  pop     rsi
0x18034aa58  pop     rbx
0x18034aa59  pop     rbp
0x18034aa5a  retn
```
