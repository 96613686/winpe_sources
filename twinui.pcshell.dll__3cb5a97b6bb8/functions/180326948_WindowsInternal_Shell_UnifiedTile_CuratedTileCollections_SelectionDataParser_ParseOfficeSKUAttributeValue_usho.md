# WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::SelectionDataParser::ParseOfficeSKUAttributeValue(ushort const *,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::SelectionData &)

- ea: `0x180326948`
- end: `0x180326b37`
- name: `?ParseOfficeSKUAttributeValue@SelectionDataParser@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@AEAAJPEBGAEAUSelectionData@2345@@Z`
- size: `495`
- prototype: `int(WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::SelectionDataParser *__hidden this, const unsigned __int16 *, struct WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::SelectionData *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180326910`

## callees

- `0x1800237c8`
- `0x180204d38`
- `0x180326948`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180326984`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1803269c7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180326a04`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180326a3f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180326a68`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180326aa4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180326aca`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180326984`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1803269c7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180326a04`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180326a3f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180326a68`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180326aa4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180326aca`

## string_xrefs

- `0x180326b09`: `shellcommon\shell\tiles\curatedtilecollections\collectioninitialization\helpers\selectiondataparser.cpp`

## pseudocode

```c
__int64 __fastcall WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::SelectionDataParser::ParseOfficeSKUAttributeValue(
        WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::SelectionDataParser *this,
        const unsigned __int16 *a2,
        struct WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::SelectionData *a3)
{
  char *v5; // rcx
  int *v6; // rdx
  int v7; // eax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::SelectionDataParser *v11; // [rsp+50h] [rbp+20h] BYREF

  v11 = this;
  if ( CompareStringOrdinal(a2, -1, L"None", -1, 1) == 2 )
  {
    v5 = (char *)a3 + 64;
    LODWORD(v11) = 0;
    v6 = (int *)*((_QWORD *)a3 + 9);
    if ( v6 != *((int **)a3 + 10) )
    {
      *v6 = 0;
LABEL_21:
      *((_QWORD *)v5 + 1) += 4LL;
LABEL_23:
      *((_BYTE *)a3 + 4) = 1;
      return 0;
    }
    goto LABEL_22;
  }
  if ( CompareStringOrdinal(a2, -1, L"DownloadOffice", -1, 1) == 2 )
  {
    v5 = (char *)a3 + 64;
    LODWORD(v11) = 1;
    v6 = (int *)*((_QWORD *)a3 + 9);
    if ( v6 != *((int **)a3 + 10) )
    {
      *v6 = 1;
      goto LABEL_21;
    }
LABEL_22:
    std::vector<enum WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionSKU>::_Emplace_reallocate<enum WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionSKU const &>(
      v5,
      v6,
      &v11);
    goto LABEL_23;
  }
  if ( CompareStringOrdinal(a2, -1, L"Mobile", -1, 1) == 2 )
  {
    v5 = (char *)a3 + 64;
    LODWORD(v11) = 2;
    v6 = (int *)*((_QWORD *)a3 + 9);
    if ( v6 != *((int **)a3 + 10) )
    {
      *v6 = 2;
      goto LABEL_21;
    }
    goto LABEL_22;
  }
  if ( CompareStringOrdinal(a2, -1, L"Desktop", -1, 1) == 2 )
  {
    v7 = 3;
    goto LABEL_19;
  }
  if ( CompareStringOrdinal(a2, -1, L"Desktop2016", -1, 1) == 2 )
  {
    v5 = (char *)a3 + 64;
    LODWORD(v11) = 4;
    v6 = (int *)*((_QWORD *)a3 + 9);
    if ( v6 != *((int **)a3 + 10) )
    {
      *v6 = 4;
      goto LABEL_21;
    }
    goto LABEL_22;
  }
  if ( CompareStringOrdinal(a2, -1, L"DesktopBridge", -1, 1) == 2 )
  {
    v7 = 5;
    goto LABEL_19;
  }
  if ( CompareStringOrdinal(a2, -1, L"DesktopBridgeSubscription", -1, 1) == 2 )
  {
    v7 = 6;
LABEL_19:
    v5 = (char *)a3 + 64;
    LODWORD(v11) = v7;
    v6 = (int *)*((_QWORD *)a3 + 9);
    if ( v6 != *((int **)a3 + 10) )
    {
      *v6 = v7;
      goto LABEL_21;
    }
    goto LABEL_22;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xD3,
    (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitialization\\helpers\\selectiondataparser.cpp",
    (const char *)0xC00CE225LL,
    bIgnoreCase);
  return 3222069797LL;
}

```

## disassembly

```asm
0x180326948  mov     rax, rsp
0x18032694b  mov     [rax+10h], rbx
0x18032694f  mov     [rax+18h], rsi
0x180326953  mov     [rax+8], rcx
0x180326957  push    rbp
0x180326958  push    rdi
0x180326959  push    r14
0x18032695b  mov     rbp, rsp
0x18032695e  sub     rsp, 30h
0x180326962  mov     rdi, rdx
0x180326965  or      esi, 0FFFFFFFFh
0x180326968  mov     rbx, r8
0x18032696b  mov     r14d, 1
0x180326971  mov     r9d, esi; cchCount2
0x180326974  mov     [rax-28h], r14d
0x180326978  mov     edx, esi; cchCount1
0x18032697a  lea     r8, aNone; "None"
0x180326981  mov     rcx, rdi; lpString1
0x180326984  call    cs:__imp_CompareStringOrdinal
0x18032698a  cmp     eax, 2
0x18032698d  jnz     short loc_1803269B3
0x18032698f  lea     rcx, [rbx+40h]
0x180326993  mov     dword ptr [rbp+arg_0], 0
0x18032699a  mov     rdx, [rcx+8]
0x18032699e  cmp     rdx, [rcx+10h]
0x1803269a2  jz      loc_180326AF4
0x1803269a8  mov     dword ptr [rdx], 0
0x1803269ae  jmp     loc_180326AED
0x1803269b3  mov     r9d, esi; cchCount2
0x1803269b6  mov     [rsp+30h+bIgnoreCase], r14d; bIgnoreCase
0x1803269bb  lea     r8, aDownloadoffice; "DownloadOffice"
0x1803269c2  mov     edx, esi; cchCount1
0x1803269c4  mov     rcx, rdi; lpString1
0x1803269c7  call    cs:__imp_CompareStringOrdinal
0x1803269cd  cmp     eax, 2
0x1803269d0  jnz     short loc_1803269F0
0x1803269d2  lea     rcx, [rbx+40h]
0x1803269d6  mov     dword ptr [rbp+arg_0], r14d
0x1803269da  mov     rdx, [rcx+8]
0x1803269de  cmp     rdx, [rcx+10h]
0x1803269e2  jz      loc_180326AF4
0x1803269e8  mov     [rdx], r14d
0x1803269eb  jmp     loc_180326AED
0x1803269f0  mov     r9d, esi; cchCount2
0x1803269f3  mov     [rsp+30h+bIgnoreCase], r14d; bIgnoreCase
0x1803269f8  lea     r8, aMobile; "Mobile"
0x1803269ff  mov     edx, esi; cchCount1
0x180326a01  mov     rcx, rdi; lpString1
0x180326a04  call    cs:__imp_CompareStringOrdinal
0x180326a0a  cmp     eax, 2
0x180326a0d  jnz     short loc_180326A2B
0x180326a0f  lea     rcx, [rbx+40h]
0x180326a13  mov     dword ptr [rbp+arg_0], eax
0x180326a16  mov     rdx, [rcx+8]
0x180326a1a  cmp     rdx, [rcx+10h]
0x180326a1e  jz      loc_180326AF4
0x180326a24  mov     [rdx], eax
0x180326a26  jmp     loc_180326AED
0x180326a2b  mov     r9d, esi; cchCount2
0x180326a2e  mov     [rsp+30h+bIgnoreCase], r14d; bIgnoreCase
0x180326a33  lea     r8, aDesktop; "Desktop"
0x180326a3a  mov     edx, esi; cchCount1
0x180326a3c  mov     rcx, rdi; lpString1
0x180326a3f  call    cs:__imp_CompareStringOrdinal
0x180326a45  cmp     eax, 2
0x180326a48  jnz     short loc_180326A54
0x180326a4a  mov     eax, 3
0x180326a4f  jmp     loc_180326ADA
0x180326a54  mov     r9d, esi; cchCount2
0x180326a57  mov     [rsp+30h+bIgnoreCase], r14d; bIgnoreCase
0x180326a5c  lea     r8, aDesktop2016; "Desktop2016"
0x180326a63  mov     edx, esi; cchCount1
0x180326a65  mov     rcx, rdi; lpString1
0x180326a68  call    cs:__imp_CompareStringOrdinal
0x180326a6e  cmp     eax, 2
0x180326a71  jnz     short loc_180326A90
0x180326a73  lea     rcx, [rbx+40h]
0x180326a77  mov     dword ptr [rbp+arg_0], 4
0x180326a7e  mov     rdx, [rcx+8]
0x180326a82  cmp     rdx, [rcx+10h]
0x180326a86  jz      short loc_180326AF4
0x180326a88  mov     dword ptr [rdx], 4
0x180326a8e  jmp     short loc_180326AED
0x180326a90  mov     r9d, esi; cchCount2
0x180326a93  mov     [rsp+30h+bIgnoreCase], r14d; bIgnoreCase
0x180326a98  lea     r8, aDesktopbridge; "DesktopBridge"
0x180326a9f  mov     edx, esi; cchCount1
0x180326aa1  mov     rcx, rdi; lpString1
0x180326aa4  call    cs:__imp_CompareStringOrdinal
0x180326aaa  cmp     eax, 2
0x180326aad  jnz     short loc_180326AB6
0x180326aaf  mov     eax, 5
0x180326ab4  jmp     short loc_180326ADA
0x180326ab6  mov     r9d, esi; cchCount2
0x180326ab9  mov     [rsp+30h+bIgnoreCase], r14d; int
0x180326abe  lea     r8, aDesktopbridges; "DesktopBridgeSubscription"
0x180326ac5  mov     edx, esi; cchCount1
0x180326ac7  mov     rcx, rdi; lpString1
0x180326aca  call    cs:__imp_CompareStringOrdinal
0x180326ad0  cmp     eax, 2
0x180326ad3  jnz     short loc_180326B05
0x180326ad5  mov     eax, 6
0x180326ada  lea     rcx, [rbx+40h]
0x180326ade  mov     dword ptr [rbp+arg_0], eax
0x180326ae1  mov     rdx, [rcx+8]
0x180326ae5  cmp     rdx, [rcx+10h]
0x180326ae9  jz      short loc_180326AF4
0x180326aeb  mov     [rdx], eax
0x180326aed  add     qword ptr [rcx+8], 4
0x180326af2  jmp     short loc_180326AFD
0x180326af4  lea     r8, [rbp+arg_0]
0x180326af8  call    ??$_Emplace_reallocate@AEBW4CollectionSKU@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@?$vector@W4CollectionSKU@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@V?$allocator@W4CollectionSKU@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@@std@@AEAAPEAW4CollectionSKU@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@QEAW423456@AEBW423456@@Z; std::vector<WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionSKU>::_Emplace_reallocate<WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionSKU const &>(WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionSKU * const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionSKU const &)
0x180326afd  mov     [rbx+4], r14b
0x180326b01  xor     eax, eax
0x180326b03  jmp     short loc_180326B24
0x180326b05  mov     rcx, [rbp+18h]; this
0x180326b09  lea     r8, aShellcommonShe; "shellcommon\\shell\\tiles\\curatedtilec"...
0x180326b10  mov     ebx, 0C00CE225h
0x180326b15  mov     edx, 0D3h; void *
0x180326b1a  mov     r9d, ebx; char *
0x180326b1d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180326b22  mov     eax, ebx
0x180326b24  mov     rbx, [rsp+30h+arg_8]
0x180326b29  mov     rsi, [rsp+30h+arg_10]
0x180326b2e  add     rsp, 30h
0x180326b32  pop     r14
0x180326b34  pop     rdi
0x180326b35  pop     rbp
0x180326b36  retn
```
