# CDFPositionAtLastMember(CRYPTCATCDF_ *)

- ea: `0x18003b498`
- end: `0x18003b4d2`
- name: `?CDFPositionAtLastMember@@YAHPEAUCRYPTCATCDF_@@@Z`
- size: `58`
- prototype: `__int64 __fastcall(struct CRYPTCATCDF_ *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18002ddbc`
- `0x18003b904`

## callees

- `0x18003b3d0`
- `0x18003b498`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18003b4bd`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18003b4bd`

## pseudocode

```c
__int64 __fastcall CDFPositionAtLastMember(struct CRYPTCATCDF_ *a1)
{
  LONG dwLastMemberOffset; // edx

  dwLastMemberOffset = a1->dwLastMemberOffset;
  if ( dwLastMemberOffset )
    return SetFilePointer(a1->hFile, dwLastMemberOffset, 0, 0) != -1;
  else
    return CDFPositionAtGroupTag(a1, L"[CatalogFiles]");
}

```

## disassembly

```asm
0x18003b498  sub     rsp, 28h
0x18003b49c  mov     edx, [rcx+14h]; lDistanceToMove
0x18003b49f  test    edx, edx
0x18003b4a1  jnz     short loc_18003B4B3
0x18003b4a3  lea     rdx, Buf2; "[CatalogFiles]"
0x18003b4aa  add     rsp, 28h
0x18003b4ae  jmp     ?CDFPositionAtGroupTag@@YAHPEAUCRYPTCATCDF_@@PEBG@Z; CDFPositionAtGroupTag(CRYPTCATCDF_ *,ushort const *)
0x18003b4b3  mov     rcx, [rcx+8]; hFile
0x18003b4b7  xor     r9d, r9d; dwMoveMethod
0x18003b4ba  xor     r8d, r8d; lpDistanceToMoveHigh
0x18003b4bd  call    cs:__imp_SetFilePointer
0x18003b4c3  xor     ecx, ecx
0x18003b4c5  cmp     eax, 0FFFFFFFFh
0x18003b4c8  setnz   cl
0x18003b4cb  mov     eax, ecx
0x18003b4cd  add     rsp, 28h
0x18003b4d1  retn
```
