# Validate_CSusMap_wchar_t___CUHOSDeploymentInformation::CDeploymentFileInfo___CSusSortedArrayListItemOpsLPWSTR_CSusArrayListItemOpSusFree_CUHOSDeploymentInformation::CDeploymentFileInfo_____::_tagMapEntry_CSusMap_wchar_t___CUHOSDeploymentInformation::CDeploymentFileInfo___CSusSortedArrayListItemOpsLPWSTR_CSusArrayListItemOpSusFree_CUHOSDeploymentInformation::CDeploymentFileInfo_____::CMapEntryOps_

- ea: `0x18001cba4`
- end: `0x18001cca3`
- name: `Validate_CSusMap_wchar_t___CUHOSDeploymentInformation::CDeploymentFileInfo___CSusSortedArrayListItemOpsLPWSTR_CSusArrayListItemOpSusFree_CUHOSDeploymentInformation::CDeploymentFileInfo_____::_tagMapEntry_CSusMap_wchar_t___CUHOSDeploymentInformation::CDeploymentFileInfo___CSusSortedArrayListItemOpsLPWSTR_CSusArrayListItemOpSusFree_CUHOSDeploymentInformation::CDeploymentFileInfo_____::CMapEntryOps_`
- size: `255`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001c614`

## callees

- `0x18001cba4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001cbf5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001cc42`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001cbf5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001cc42`

## pseudocode

```c
__int64 __fastcall Validate_CSusMap_wchar_t___CUHOSDeploymentInformation::CDeploymentFileInfo___CSusSortedArrayListItemOpsLPWSTR_CSusArrayListItemOpSusFree_CUHOSDeploymentInformation::CDeploymentFileInfo_____::_tagMapEntry_CSusMap_wchar_t___CUHOSDeploymentInformation::CDeploymentFileInfo___CSusSortedArrayListItemOpsLPWSTR_CSusArrayListItemOpSusFree_CUHOSDeploymentInformation::CDeploymentFileInfo_____::CMapEntryOps_(
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
0x18001cba4  mov     rax, rsp
0x18001cba7  mov     [rax+8], rbx
0x18001cbab  mov     [rax+10h], rbp
0x18001cbaf  mov     [rax+18h], rsi
0x18001cbb3  mov     [rax+20h], rdi
0x18001cbb7  push    r14
0x18001cbb9  sub     rsp, 30h
0x18001cbbd  or      r14d, 0FFFFFFFFh
0x18001cbc1  lea     rsi, [rdx+8]
0x18001cbc5  mov     rbp, r8
0x18001cbc8  lea     ebx, [r14+2]
0x18001cbcc  test    rcx, rcx
0x18001cbcf  jz      short loc_18001CC0B
0x18001cbd1  mov     rax, [rcx+8]
0x18001cbd5  cmp     [rsi], rax
0x18001cbd8  jnz     short loc_18001CBDE
0x18001cbda  xor     edi, edi
0x18001cbdc  jmp     short loc_18001CC19
0x18001cbde  mov     r8, [rsi]; lpString1
0x18001cbe1  mov     r9d, r14d; cchCount1
0x18001cbe4  mov     [rsp+38h+cchCount2], r14d; cchCount2
0x18001cbe9  mov     edx, ebx; dwCmpFlags
0x18001cbeb  mov     ecx, 7Fh; Locale
0x18001cbf0  mov     [rsp+38h+lpString2], rax; lpString2
0x18001cbf5  call    cs:__imp_CompareStringW
0x18001cbfb  test    eax, eax
0x18001cbfd  jz      short loc_18001CC14
0x18001cbff  sub     eax, ebx
0x18001cc01  jz      short loc_18001CC0F
0x18001cc03  sub     eax, ebx
0x18001cc05  jz      short loc_18001CBDA
0x18001cc07  cmp     eax, ebx
0x18001cc09  jnz     short loc_18001CC14
0x18001cc0b  mov     edi, ebx
0x18001cc0d  jmp     short loc_18001CC19
0x18001cc0f  mov     edi, r14d
0x18001cc12  jmp     short loc_18001CC19
0x18001cc14  mov     edi, 0FFFFFFFEh
0x18001cc19  test    rbp, rbp
0x18001cc1c  jz      short loc_18001CC60
0x18001cc1e  mov     rax, [rsi]
0x18001cc21  mov     r8, [rbp+8]; lpString1
0x18001cc25  cmp     r8, rax
0x18001cc28  jnz     short loc_18001CC2E
0x18001cc2a  xor     ebx, ebx
0x18001cc2c  jmp     short loc_18001CC60
0x18001cc2e  mov     [rsp+38h+cchCount2], r14d; cchCount2
0x18001cc33  mov     r9d, r14d; cchCount1
0x18001cc36  mov     edx, ebx; dwCmpFlags
0x18001cc38  mov     [rsp+38h+lpString2], rax; lpString2
0x18001cc3d  mov     ecx, 7Fh; Locale
0x18001cc42  call    cs:__imp_CompareStringW
0x18001cc48  test    eax, eax
0x18001cc4a  jz      short loc_18001CC5B
0x18001cc4c  sub     eax, 1
0x18001cc4f  jz      short loc_18001CC6C
0x18001cc51  sub     eax, 1
0x18001cc54  jz      short loc_18001CC2A
0x18001cc56  cmp     eax, 1
0x18001cc59  jz      short loc_18001CC60
0x18001cc5b  mov     ebx, 0FFFFFFFEh
0x18001cc60  test    edi, edi
0x18001cc62  jle     short loc_18001CC71
0x18001cc64  test    ebx, ebx
0x18001cc66  jle     short loc_18001CC73
0x18001cc68  xor     eax, eax
0x18001cc6a  jmp     short loc_18001CC88
0x18001cc6c  mov     ebx, r14d
0x18001cc6f  jmp     short loc_18001CC60
0x18001cc71  jz      short loc_18001CC83
0x18001cc73  neg     ebx
0x18001cc75  sbb     eax, eax
0x18001cc77  and     eax, 0FECh
0x18001cc7c  add     eax, 80240013h
0x18001cc81  jmp     short loc_18001CC88
0x18001cc83  mov     eax, 80240013h
0x18001cc88  mov     rbx, [rsp+38h+arg_0]
0x18001cc8d  mov     rbp, [rsp+38h+arg_8]
0x18001cc92  mov     rsi, [rsp+38h+arg_10]
0x18001cc97  mov     rdi, [rsp+38h+arg_18]
0x18001cc9c  add     rsp, 30h
0x18001cca0  pop     r14
0x18001cca2  retn
```
