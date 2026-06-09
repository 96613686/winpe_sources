# Validate_CSusMap_wchar_t___IDeploymentProgress___CSusSortedArrayListItemOpsLPWSTR_CSusArrayListItemOpInterfacePtr_IDeploymentProgress_____::_tagMapEntry_CSusMap_wchar_t___IDeploymentProgress___CSusSortedArrayListItemOpsLPWSTR_CSusArrayListItemOpInterfacePtr_IDeploymentProgress_____::CMapEntryOps_

- ea: `0x14001a118`
- end: `0x14001a217`
- name: `Validate_CSusMap_wchar_t___IDeploymentProgress___CSusSortedArrayListItemOpsLPWSTR_CSusArrayListItemOpInterfacePtr_IDeploymentProgress_____::_tagMapEntry_CSusMap_wchar_t___IDeploymentProgress___CSusSortedArrayListItemOpsLPWSTR_CSusArrayListItemOpInterfacePtr_IDeploymentProgress_____::CMapEntryOps_`
- size: `255`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140019bf4`

## callees

- `0x14001a118`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14001a169`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14001a1b6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14001a169`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14001a1b6`

## pseudocode

```c
__int64 __fastcall Validate_CSusMap_wchar_t___IDeploymentProgress___CSusSortedArrayListItemOpsLPWSTR_CSusArrayListItemOpInterfacePtr_IDeploymentProgress_____::_tagMapEntry_CSusMap_wchar_t___IDeploymentProgress___CSusSortedArrayListItemOpsLPWSTR_CSusArrayListItemOpInterfacePtr_IDeploymentProgress_____::CMapEntryOps_(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  PCNZWCH *v3; // rsi
  int v5; // ebx
  const WCHAR *lpString2; // rax
  int v7; // edi
  int v8; // eax
  int v9; // eax
  int v10; // eax
  const WCHAR *v11; // r8
  int v12; // eax
  int v13; // eax
  int v14; // eax

  v3 = (PCNZWCH *)(a2 + 8);
  v5 = 1;
  if ( !a1 )
  {
LABEL_8:
    v7 = 1;
    goto LABEL_11;
  }
  lpString2 = *(const WCHAR **)(a1 + 8);
  if ( *v3 == lpString2 )
  {
LABEL_3:
    v7 = 0;
    goto LABEL_11;
  }
  v8 = CompareStringW(0x7Fu, 1u, *v3, -1, lpString2, -1);
  if ( v8 )
  {
    v9 = v8 - 1;
    if ( !v9 )
    {
      v7 = -1;
      goto LABEL_11;
    }
    v10 = v9 - 1;
    if ( !v10 )
      goto LABEL_3;
    if ( v10 == 1 )
      goto LABEL_8;
  }
  v7 = -2;
LABEL_11:
  if ( !a3 )
    goto LABEL_19;
  v11 = *(const WCHAR **)(a3 + 8);
  if ( v11 == *v3 )
    goto LABEL_13;
  v12 = CompareStringW(0x7Fu, 1u, v11, -1, *v3, -1);
  if ( !v12 )
  {
LABEL_18:
    v5 = -2;
    goto LABEL_19;
  }
  v13 = v12 - 1;
  if ( v13 )
  {
    v14 = v13 - 1;
    if ( !v14 )
    {
LABEL_13:
      v5 = 0;
      goto LABEL_19;
    }
    if ( v14 != 1 )
      goto LABEL_18;
  }
  else
  {
    v5 = -1;
  }
LABEL_19:
  if ( v7 > 0 )
  {
    if ( v5 > 0 )
      return 0;
    return v5 != 0 ? -2145120257 : -2145124333;
  }
  if ( v7 )
    return v5 != 0 ? -2145120257 : -2145124333;
  return 2149842963LL;
}

```

## disassembly

```asm
0x14001a118  mov     rax, rsp
0x14001a11b  mov     [rax+8], rbx
0x14001a11f  mov     [rax+10h], rbp
0x14001a123  mov     [rax+18h], rsi
0x14001a127  mov     [rax+20h], rdi
0x14001a12b  push    r14
0x14001a12d  sub     rsp, 30h
0x14001a131  or      r14d, 0FFFFFFFFh
0x14001a135  lea     rsi, [rdx+8]
0x14001a139  mov     rbp, r8
0x14001a13c  lea     ebx, [r14+2]
0x14001a140  test    rcx, rcx
0x14001a143  jz      short loc_14001A17F
0x14001a145  mov     rax, [rcx+8]
0x14001a149  cmp     [rsi], rax
0x14001a14c  jnz     short loc_14001A152
0x14001a14e  xor     edi, edi
0x14001a150  jmp     short loc_14001A18D
0x14001a152  mov     r8, [rsi]; lpString1
0x14001a155  mov     r9d, r14d; cchCount1
0x14001a158  mov     [rsp+38h+cchCount2], r14d; cchCount2
0x14001a15d  mov     edx, ebx; dwCmpFlags
0x14001a15f  mov     ecx, 7Fh; Locale
0x14001a164  mov     [rsp+38h+lpString2], rax; lpString2
0x14001a169  call    cs:__imp_CompareStringW
0x14001a16f  test    eax, eax
0x14001a171  jz      short loc_14001A188
0x14001a173  sub     eax, ebx
0x14001a175  jz      short loc_14001A183
0x14001a177  sub     eax, ebx
0x14001a179  jz      short loc_14001A14E
0x14001a17b  cmp     eax, ebx
0x14001a17d  jnz     short loc_14001A188
0x14001a17f  mov     edi, ebx
0x14001a181  jmp     short loc_14001A18D
0x14001a183  mov     edi, r14d
0x14001a186  jmp     short loc_14001A18D
0x14001a188  mov     edi, 0FFFFFFFEh
0x14001a18d  test    rbp, rbp
0x14001a190  jz      short loc_14001A1D4
0x14001a192  mov     rax, [rsi]
0x14001a195  mov     r8, [rbp+8]; lpString1
0x14001a199  cmp     r8, rax
0x14001a19c  jnz     short loc_14001A1A2
0x14001a19e  xor     ebx, ebx
0x14001a1a0  jmp     short loc_14001A1D4
0x14001a1a2  mov     [rsp+38h+cchCount2], r14d; cchCount2
0x14001a1a7  mov     r9d, r14d; cchCount1
0x14001a1aa  mov     edx, ebx; dwCmpFlags
0x14001a1ac  mov     [rsp+38h+lpString2], rax; lpString2
0x14001a1b1  mov     ecx, 7Fh; Locale
0x14001a1b6  call    cs:__imp_CompareStringW
0x14001a1bc  test    eax, eax
0x14001a1be  jz      short loc_14001A1CF
0x14001a1c0  sub     eax, 1
0x14001a1c3  jz      short loc_14001A1E0
0x14001a1c5  sub     eax, 1
0x14001a1c8  jz      short loc_14001A19E
0x14001a1ca  cmp     eax, 1
0x14001a1cd  jz      short loc_14001A1D4
0x14001a1cf  mov     ebx, 0FFFFFFFEh
0x14001a1d4  test    edi, edi
0x14001a1d6  jle     short loc_14001A1E5
0x14001a1d8  test    ebx, ebx
0x14001a1da  jle     short loc_14001A1E7
0x14001a1dc  xor     eax, eax
0x14001a1de  jmp     short loc_14001A1FC
0x14001a1e0  mov     ebx, r14d
0x14001a1e3  jmp     short loc_14001A1D4
0x14001a1e5  jz      short loc_14001A1F7
0x14001a1e7  neg     ebx
0x14001a1e9  sbb     eax, eax
0x14001a1eb  and     eax, 0FECh
0x14001a1f0  add     eax, 80240013h
0x14001a1f5  jmp     short loc_14001A1FC
0x14001a1f7  mov     eax, 80240013h
0x14001a1fc  mov     rbx, [rsp+38h+arg_0]
0x14001a201  mov     rbp, [rsp+38h+arg_8]
0x14001a206  mov     rsi, [rsp+38h+arg_10]
0x14001a20b  mov     rdi, [rsp+38h+arg_18]
0x14001a210  add     rsp, 30h
0x14001a214  pop     r14
0x14001a216  retn
```
