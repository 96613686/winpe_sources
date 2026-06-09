# SdbpValidateAndApplyCompatFlags

- ea: `0x140017be4`
- end: `0x140017cee`
- name: `SdbpValidateAndApplyCompatFlags`
- size: `266`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140016198`
- `0x140017730`

## callees

- `0x14001008c`
- `0x140013738`
- `0x140014380`
- `0x140015a18`
- `0x140017be4`
- `0x140017cf4`

## string_xrefs

- `0x140017c2a`: `SdbpValidateAndApplyCompatFlags`
- `0x140017c78`: `SdbpValidateAndApplyCompatFlags`
- `0x140017ca8`: `SdbpValidateAndApplyCompatFlags`

## pseudocode

```c
__int64 __fastcall SdbpValidateAndApplyCompatFlags(__int64 a1, _DWORD *a2, char a3)
{
  unsigned int v4; // edi
  int v6; // eax

  v4 = 0;
  if ( *a2 == 1 )
  {
    *(_DWORD *)(a1 + 2608) |= 1u;
    goto LABEL_7;
  }
  if ( *a2 == 2 )
  {
LABEL_7:
    *(_DWORD *)(a1 + 2608) |= 2u;
    goto LABEL_8;
  }
  if ( *a2 != 3 && (a3 & 1) == 0 )
  {
    AslLogCallPrintf(
      1,
      "SdbpValidateAndApplyCompatFlags",
      981,
      "MajorVersion mismatch, MajorVersion [0x%lx] Expected 0x%lx",
      *a2,
      3);
    return v4;
  }
LABEL_8:
  if ( (unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline()
    && (v6 = SdbpValidateRootTagSizes(a1), v6 < 0) )
  {
    AslLogCallPrintf(
      1,
      "SdbpValidateAndApplyCompatFlags",
      992,
      "SdbpValidateRootTagSizes failed to validate SDB [%x]",
      v6);
  }
  else
  {
    if ( (unsigned int)SdbGetDatabaseID(a1, (void *)(a1 + 28)) )
      return 1;
    AslLogCallPrintf(1, "SdbpValidateAndApplyCompatFlags", 1005, "Failed to get the database ID");
    if ( (a3 & 8) == 0 && ((a3 & 4) == 0 || (unsigned int)SdbFindFirstTag(a1, 0, 28673)) )
      return 1;
  }
  return v4;
}

```

## disassembly

```asm
0x140017be4  mov     [rsp+arg_0], rbx
0x140017be9  mov     [rsp+arg_8], rsi
0x140017bee  push    rdi
0x140017bef  sub     rsp, 30h
0x140017bf3  mov     esi, r8d
0x140017bf6  xor     edi, edi
0x140017bf8  mov     r8d, [rdx]
0x140017bfb  mov     rbx, rcx
0x140017bfe  mov     eax, r8d
0x140017c01  sub     eax, 1
0x140017c04  jz      short loc_140017C44
0x140017c06  sub     eax, 1
0x140017c09  jz      short loc_140017C4B
0x140017c0b  cmp     eax, 1
0x140017c0e  jz      short loc_140017C52
0x140017c10  test    sil, 1
0x140017c14  jnz     short loc_140017C52
0x140017c16  mov     [rsp+38h+var_10], 3
0x140017c1e  lea     r9, aMajorversionMi; "MajorVersion mismatch, MajorVersion [0x"...
0x140017c25  mov     [rsp+38h+var_18], r8d
0x140017c2a  lea     rdx, aSdbpvalidatean; "SdbpValidateAndApplyCompatFlags"
0x140017c31  mov     r8d, 3D5h
0x140017c37  lea     ecx, [rdi+1]
0x140017c3a  call    AslLogCallPrintf
0x140017c3f  jmp     loc_140017CDC
0x140017c44  or      dword ptr [rcx+0A30h], 1
0x140017c4b  or      dword ptr [rcx+0A30h], 2
0x140017c52  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x140017c57  test    eax, eax
0x140017c59  jz      short loc_140017C8B
0x140017c5b  mov     rcx, rbx
0x140017c5e  call    SdbpValidateRootTagSizes
0x140017c63  test    eax, eax
0x140017c65  jns     short loc_140017C8B
0x140017c67  lea     r9, aSdbpvalidatero; "SdbpValidateRootTagSizes failed to vali"...
0x140017c6e  mov     [rsp+38h+var_18], eax
0x140017c72  mov     r8d, 3E0h
0x140017c78  lea     rdx, aSdbpvalidatean; "SdbpValidateAndApplyCompatFlags"
0x140017c7f  mov     ecx, 1
0x140017c84  call    AslLogCallPrintf
0x140017c89  jmp     short loc_140017CDC
0x140017c8b  lea     rdx, [rbx+1Ch]
0x140017c8f  mov     rcx, rbx
0x140017c92  call    SdbGetDatabaseID
0x140017c97  test    eax, eax
0x140017c99  jnz     short loc_140017CD7
0x140017c9b  lea     r9, aFailedToGetThe; "Failed to get the database ID"
0x140017ca2  mov     r8d, 3EDh
0x140017ca8  lea     rdx, aSdbpvalidatean; "SdbpValidateAndApplyCompatFlags"
0x140017caf  lea     ecx, [rax+1]
0x140017cb2  call    AslLogCallPrintf
0x140017cb7  test    sil, 8
0x140017cbb  jnz     short loc_140017CDC
0x140017cbd  test    sil, 4
0x140017cc1  jz      short loc_140017CD7
0x140017cc3  xor     edx, edx
0x140017cc5  mov     r8d, 7001h
0x140017ccb  mov     rcx, rbx
0x140017cce  call    SdbFindFirstTag
0x140017cd3  test    eax, eax
0x140017cd5  jz      short loc_140017CDC
0x140017cd7  mov     edi, 1
0x140017cdc  mov     rbx, [rsp+38h+arg_0]
0x140017ce1  mov     eax, edi
0x140017ce3  mov     rsi, [rsp+38h+arg_8]
0x140017ce8  add     rsp, 30h
0x140017cec  pop     rdi
0x140017ced  retn
```
