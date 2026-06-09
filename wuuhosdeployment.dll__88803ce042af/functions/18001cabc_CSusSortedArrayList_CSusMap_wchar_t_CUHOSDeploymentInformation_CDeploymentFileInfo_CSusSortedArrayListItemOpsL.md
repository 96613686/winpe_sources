# CSusSortedArrayList<CSusMap<wchar_t *,CUHOSDeploymentInformation::CDeploymentFileInfo *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpSusFree<CUHOSDeploymentInformation::CDeploymentFileInfo *>>::_tagMapEntry,CSusMap<wchar_t *,CUHOSDeploymentInformation::CDeploymentFileInfo *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpSusFree<CUHOSDeploymentInformation::CDeploymentFileInfo *>>::CMapEntryOps>::InternalCompare(CSusMap<wchar_t *,CUHOSDeploymentInformation::CDeploymentFileInfo *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpSusFree<CUHOSDeploymentInformation::CDeploymentFileInfo *>>::_tagMapEntry const &,ulong)

- ea: `0x18001cabc`
- end: `0x18001cb24`
- name: `?InternalCompare@?$CSusSortedArrayList@U_tagMapEntry@?$CSusMap@PEA_WPEAVCDeploymentFileInfo@CUHOSDeploymentInformation@@VCSusSortedArrayListItemOpsLPWSTR@@V?$CSusArrayListItemOpSusFree@PEAVCDeploymentFileInfo@CUHOSDeploymentInformation@@@@@@VCMapEntryOps@2@@@IEBAHAEBU_tagMapEntry@?$CSusMap@PEA_WPEAVCDeploymentFileInfo@CUHOSDeploymentInformation@@VCSusSortedArrayListItemOpsLPWSTR@@V?$CSusArrayListItemOpSusFree@PEAVCDeploymentFileInfo@CUHOSDeploymentInformation@@@@@@K@Z`
- size: `104`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001c614`
- `0x18001c9b8`
- `0x18003de00`

## callees

- `0x18001cabc`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001caf4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001caf4`

## pseudocode

```c
__int64 __fastcall CSusSortedArrayList<CSusMap<wchar_t *,CUHOSDeploymentInformation::CDeploymentFileInfo *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpSusFree<CUHOSDeploymentInformation::CDeploymentFileInfo *>>::_tagMapEntry,CSusMap<wchar_t *,CUHOSDeploymentInformation::CDeploymentFileInfo *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpSusFree<CUHOSDeploymentInformation::CDeploymentFileInfo *>>::CMapEntryOps>::InternalCompare(
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
0x18001cabc  sub     rsp, 38h
0x18001cac0  mov     rax, [rcx+8]
0x18001cac4  mov     r8d, r8d
0x18001cac7  add     r8, r8
0x18001caca  mov     rcx, [rax+r8*8+8]
0x18001cacf  mov     r8, [rdx+8]; lpString1
0x18001cad3  cmp     r8, rcx
0x18001cad6  jnz     short loc_18001CADC
0x18001cad8  xor     eax, eax
0x18001cada  jmp     short loc_18001CB1F
0x18001cadc  or      r9d, 0FFFFFFFFh; cchCount1
0x18001cae0  mov     [rsp+38h+cchCount2], 0FFFFFFFFh; cchCount2
0x18001cae8  mov     [rsp+38h+lpString2], rcx; lpString2
0x18001caed  lea     edx, [r9+2]; dwCmpFlags
0x18001caf1  lea     ecx, [rdx+7Eh]; Locale
0x18001caf4  call    cs:__imp_CompareStringW
0x18001cafa  mov     ecx, eax
0x18001cafc  xor     eax, eax
0x18001cafe  test    ecx, ecx
0x18001cb00  jz      short loc_18001CB1A
0x18001cb02  sub     ecx, 1
0x18001cb05  jz      short loc_18001CB15
0x18001cb07  sub     ecx, 1
0x18001cb0a  jz      short loc_18001CB1F
0x18001cb0c  cmp     ecx, 1
0x18001cb0f  jnz     short loc_18001CB1A
0x18001cb11  mov     eax, ecx
0x18001cb13  jmp     short loc_18001CB1F
0x18001cb15  or      eax, 0FFFFFFFFh
0x18001cb18  jmp     short loc_18001CB1F
0x18001cb1a  mov     eax, 0FFFFFFFEh
0x18001cb1f  add     rsp, 38h
0x18001cb23  retn
```
