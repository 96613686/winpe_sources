# CSusSortedArrayList<CSusMap<wchar_t *,IDeploymentProgress *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentProgress *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentProgress *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentProgress *>>::CMapEntryOps>::InternalCompare(CSusMap<wchar_t *,IDeploymentProgress *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentProgress *>>::_tagMapEntry const &,ulong)

- ea: `0x14001a06c`
- end: `0x14001a0d4`
- name: `?InternalCompare@?$CSusSortedArrayList@U_tagMapEntry@?$CSusMap@PEA_WPEAUIDeploymentProgress@@VCSusSortedArrayListItemOpsLPWSTR@@V?$CSusArrayListItemOpInterfacePtr@PEAUIDeploymentProgress@@@@@@VCMapEntryOps@2@@@IEBAHAEBU_tagMapEntry@?$CSusMap@PEA_WPEAUIDeploymentProgress@@VCSusSortedArrayListItemOpsLPWSTR@@V?$CSusArrayListItemOpInterfacePtr@PEAUIDeploymentProgress@@@@@@K@Z`
- size: `104`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140019bf4`
- `0x140019f64`

## callees

- `0x14001a06c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14001a0a4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14001a0a4`

## pseudocode

```c
__int64 __fastcall CSusSortedArrayList<CSusMap<wchar_t *,IDeploymentProgress *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentProgress *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentProgress *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentProgress *>>::CMapEntryOps>::InternalCompare(
        __int64 a1,
        __int64 a2,
        unsigned int a3)
{
  const WCHAR *lpString2; // rcx
  const WCHAR *v4; // r8
  __int64 result; // rax
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx

  lpString2 = *(const WCHAR **)(*(_QWORD *)(a1 + 8) + 16LL * a3 + 8);
  v4 = *(const WCHAR **)(a2 + 8);
  if ( v4 == lpString2 )
    return 0;
  v6 = CompareStringW(0x7Fu, 1u, v4, -1, lpString2, -1);
  result = 0;
  if ( v6 )
  {
    v7 = v6 - 1;
    if ( !v7 )
      return 0xFFFFFFFFLL;
    v8 = v7 - 1;
    if ( !v8 )
      return result;
    if ( v8 == 1 )
      return 1;
  }
  return 4294967294LL;
}

```

## disassembly

```asm
0x14001a06c  sub     rsp, 38h
0x14001a070  mov     rax, [rcx+8]
0x14001a074  mov     r8d, r8d
0x14001a077  add     r8, r8
0x14001a07a  mov     rcx, [rax+r8*8+8]
0x14001a07f  mov     r8, [rdx+8]; lpString1
0x14001a083  cmp     r8, rcx
0x14001a086  jnz     short loc_14001A08C
0x14001a088  xor     eax, eax
0x14001a08a  jmp     short loc_14001A0CF
0x14001a08c  or      r9d, 0FFFFFFFFh; cchCount1
0x14001a090  mov     [rsp+38h+cchCount2], 0FFFFFFFFh; cchCount2
0x14001a098  mov     [rsp+38h+lpString2], rcx; lpString2
0x14001a09d  lea     edx, [r9+2]; dwCmpFlags
0x14001a0a1  lea     ecx, [rdx+7Eh]; Locale
0x14001a0a4  call    cs:__imp_CompareStringW
0x14001a0aa  mov     ecx, eax
0x14001a0ac  xor     eax, eax
0x14001a0ae  test    ecx, ecx
0x14001a0b0  jz      short loc_14001A0CA
0x14001a0b2  sub     ecx, 1
0x14001a0b5  jz      short loc_14001A0C5
0x14001a0b7  sub     ecx, 1
0x14001a0ba  jz      short loc_14001A0CF
0x14001a0bc  cmp     ecx, 1
0x14001a0bf  jnz     short loc_14001A0CA
0x14001a0c1  mov     eax, ecx
0x14001a0c3  jmp     short loc_14001A0CF
0x14001a0c5  or      eax, 0FFFFFFFFh
0x14001a0c8  jmp     short loc_14001A0CF
0x14001a0ca  mov     eax, 0FFFFFFFEh
0x14001a0cf  add     rsp, 38h
0x14001a0d3  retn
```
