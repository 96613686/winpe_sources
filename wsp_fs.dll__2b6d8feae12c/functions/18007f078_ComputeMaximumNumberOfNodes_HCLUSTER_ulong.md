# ComputeMaximumNumberOfNodes(_HCLUSTER *,ulong *)

- ea: `0x18007f078`
- end: `0x18007f219`
- name: `?ComputeMaximumNumberOfNodes@@YAKPEAU_HCLUSTER@@PEAK@Z`
- size: `417`
- prototype: `unsigned int __fastcall(HCLUSTER hCluster, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180033840`

## callees

- `0x180002a70`
- `0x18007f078`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f0c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f144`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f1ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f0c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f144`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f1ac`
- `CLUSAPI!CloseClusterNode` at `0x18007f1b7`
- `CLUSAPI!CloseClusterNode` at `0x18007f1b7`
- `CLUSAPI!GetClusterNodeKey` at `0x18007f156`
- `CLUSAPI!GetClusterNodeKey` at `0x18007f156`
- `CLUSAPI!OpenClusterNode` at `0x18007f136`
- `CLUSAPI!OpenClusterNode` at `0x18007f136`
- `CLUSAPI!ClusterGetEnumCount` at `0x18007f0d9`
- `CLUSAPI!ClusterGetEnumCount` at `0x18007f0d9`
- `CLUSAPI!ClusterCloseEnum` at `0x18007f1d4`
- `CLUSAPI!ClusterCloseEnum` at `0x18007f1d4`
- `CLUSAPI!ClusterEnum` at `0x18007f11f`
- `CLUSAPI!ClusterEnum` at `0x18007f11f`
- `CLUSAPI!ClusterOpenEnum` at `0x18007f0b6`
- `CLUSAPI!ClusterOpenEnum` at `0x18007f0b6`
- `CLUSAPI!ClusterRegCloseKey` at `0x18007f1a4`
- `CLUSAPI!ClusterRegCloseKey` at `0x18007f1a4`
- `CLUSAPI!ClusterRegQueryValue` at `0x18007f192`
- `CLUSAPI!ClusterRegQueryValue` at `0x18007f192`

## pseudocode

```c
DWORD __fastcall ComputeMaximumNumberOfNodes(HCLUSTER hCluster, unsigned int *a2)
{
  unsigned int *v2; // r12
  struct _HCLUSTER *v3; // r15
  struct _HCLUSENUM *v4; // rax
  DWORD v5; // esi
  struct _HCLUSENUM *v6; // r14
  DWORD LastError; // ebx
  int v9; // edi
  DWORD EnumCount; // r13d
  struct _HNODE *v11; // rax
  struct _HNODE *v12; // r15
  HKEY ClusterNodeKey; // r12
  DWORD cchName; // [rsp+30h] [rbp-99h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-95h] BYREF
  DWORD dwType; // [rsp+38h] [rbp-91h] BYREF
  DWORD cbData; // [rsp+3Ch] [rbp-8Dh] BYREF
  DWORD dwValueType; // [rsp+40h] [rbp-89h] BYREF
  HCLUSTER v19; // [rsp+48h] [rbp-81h]
  unsigned int *v20; // [rsp+50h] [rbp-79h]
  WCHAR szName[64]; // [rsp+60h] [rbp-69h] BYREF

  v2 = a2;
  v20 = a2;
  v19 = hCluster;
  v3 = hCluster;
  v4 = ClusterOpenEnum(hCluster, 1u);
  v5 = 0;
  v6 = v4;
  if ( !v4 )
    return GetLastError();
  LastError = 0;
  v9 = -1;
  cchName = 0;
  EnumCount = ClusterGetEnumCount(v4);
  dwType = 0;
  dwValueType = 0;
  if ( EnumCount )
  {
    do
    {
      if ( v9 != -1 )
        break;
      cchName = 64;
      LastError = ClusterEnum(v6, v5, &dwType, szName, &cchName);
      if ( LastError )
        break;
      v11 = OpenClusterNode(v3, szName);
      v12 = v11;
      if ( v11 )
      {
        ClusterNodeKey = GetClusterNodeKey(v11, 1u);
        if ( ClusterNodeKey )
        {
          *(_DWORD *)Data = 0;
          cbData = 4;
          LastError = ClusterRegQueryValue(ClusterNodeKey, L"MaxLicensedNodes", &dwValueType, Data, &cbData);
          if ( !LastError )
            v9 = *(_DWORD *)Data;
          ClusterRegCloseKey(ClusterNodeKey);
        }
        else
        {
          LastError = GetLastError();
        }
        CloseClusterNode(v12);
      }
      else
      {
        LastError = GetLastError();
      }
      v3 = v19;
      ++v5;
    }
    while ( v5 < EnumCount );
    v2 = v20;
  }
  ClusterCloseEnum(v6);
  if ( v9 == -1 )
  {
    if ( !LastError )
      return 2;
  }
  else
  {
    LastError = 0;
    *v2 = v9;
  }
  return LastError;
}

```

## disassembly

```asm
0x18007f078  mov     [rsp-8+arg_10], rbx
0x18007f07d  push    rbp
0x18007f07e  push    rsi
0x18007f07f  push    rdi
0x18007f080  push    r12
0x18007f082  push    r13
0x18007f084  push    r14
0x18007f086  push    r15
0x18007f088  lea     rbp, [rsp-27h]
0x18007f08d  sub     rsp, 0F0h
0x18007f094  mov     rax, cs:__security_cookie
0x18007f09b  xor     rax, rsp
0x18007f09e  mov     [rbp+57h+var_40], rax
0x18007f0a2  mov     r12, rdx
0x18007f0a5  mov     [rbp+57h+var_D0], rdx
0x18007f0a9  mov     edx, 1; dwType
0x18007f0ae  mov     [rsp+120h+var_D8], rcx
0x18007f0b3  mov     r15, rcx
0x18007f0b6  call    cs:__imp_ClusterOpenEnum
0x18007f0bc  xor     esi, esi
0x18007f0be  mov     r14, rax
0x18007f0c1  test    rax, rax
0x18007f0c4  jnz     short loc_18007F0D1
0x18007f0c6  call    cs:__imp_GetLastError
0x18007f0cc  jmp     loc_18007F1F2
0x18007f0d1  mov     rcx, r14; hEnum
0x18007f0d4  mov     ebx, esi
0x18007f0d6  or      edi, 0FFFFFFFFh
0x18007f0d9  call    cs:__imp_ClusterGetEnumCount
0x18007f0df  mov     [rsp+120h+cchName], esi
0x18007f0e3  mov     r13d, eax
0x18007f0e6  mov     [rsp+120h+dwType], esi
0x18007f0ea  mov     [rsp+120h+dwValueType], esi
0x18007f0ee  test    eax, eax
0x18007f0f0  jz      loc_18007F1D1
0x18007f0f6  cmp     edi, 0FFFFFFFFh
0x18007f0f9  jnz     loc_18007F1CD
0x18007f0ff  lea     rax, [rsp+120h+cchName]
0x18007f104  mov     [rsp+120h+cchName], 40h ; '@'
0x18007f10c  lea     r9, [rbp+57h+szName]; lpszName
0x18007f110  mov     [rsp+120h+lpcchName], rax; lpcchName
0x18007f115  lea     r8, [rsp+120h+dwType]; lpdwType
0x18007f11a  mov     edx, esi; dwIndex
0x18007f11c  mov     rcx, r14; hEnum
0x18007f11f  call    cs:__imp_ClusterEnum
0x18007f125  mov     ebx, eax
0x18007f127  test    eax, eax
0x18007f129  jnz     loc_18007F1CD
0x18007f12f  lea     rdx, [rbp+57h+szName]; lpszNodeName
0x18007f133  mov     rcx, r15; hCluster
0x18007f136  call    cs:__imp_OpenClusterNode
0x18007f13c  mov     r15, rax
0x18007f13f  test    rax, rax
0x18007f142  jnz     short loc_18007F14E
0x18007f144  call    cs:__imp_GetLastError
0x18007f14a  mov     ebx, eax
0x18007f14c  jmp     short loc_18007F1BD
0x18007f14e  mov     edx, 1; samDesired
0x18007f153  mov     rcx, r15; hNode
0x18007f156  call    cs:__imp_GetClusterNodeKey
0x18007f15c  mov     r12, rax
0x18007f15f  test    rax, rax
0x18007f162  jz      short loc_18007F1AC
0x18007f164  lea     rax, [rsp+120h+cbData]
0x18007f169  mov     dword ptr [rsp+120h+Data], 0
0x18007f171  lea     r9, [rsp+120h+Data]; lpData
0x18007f176  mov     [rsp+120h+lpcchName], rax; lpcbData
0x18007f17b  lea     r8, [rsp+120h+dwValueType]; lpdwValueType
0x18007f180  mov     [rsp+120h+cbData], 4
0x18007f188  lea     rdx, ValueName; "MaxLicensedNodes"
0x18007f18f  mov     rcx, r12; hKey
0x18007f192  call    cs:__imp_ClusterRegQueryValue
0x18007f198  test    eax, eax
0x18007f19a  mov     rcx, r12; hKey
0x18007f19d  mov     ebx, eax
0x18007f19f  cmovz   edi, dword ptr [rsp+120h+Data]
0x18007f1a4  call    cs:__imp_ClusterRegCloseKey
0x18007f1aa  jmp     short loc_18007F1B4
0x18007f1ac  call    cs:__imp_GetLastError
0x18007f1b2  mov     ebx, eax
0x18007f1b4  mov     rcx, r15; hNode
0x18007f1b7  call    cs:__imp_CloseClusterNode
0x18007f1bd  mov     r15, [rsp+120h+var_D8]
0x18007f1c2  inc     esi
0x18007f1c4  cmp     esi, r13d
0x18007f1c7  jb      loc_18007F0F6
0x18007f1cd  mov     r12, [rbp+57h+var_D0]
0x18007f1d1  mov     rcx, r14; hEnum
0x18007f1d4  call    cs:__imp_ClusterCloseEnum
0x18007f1da  cmp     edi, 0FFFFFFFFh
0x18007f1dd  jnz     short loc_18007F1EA
0x18007f1df  test    ebx, ebx
0x18007f1e1  jnz     short loc_18007F1F0
0x18007f1e3  mov     ebx, 2
0x18007f1e8  jmp     short loc_18007F1F0
0x18007f1ea  xor     ebx, ebx
0x18007f1ec  mov     [r12], edi
0x18007f1f0  mov     eax, ebx
0x18007f1f2  mov     rcx, [rbp+57h+var_40]
0x18007f1f6  xor     rcx, rsp; StackCookie
0x18007f1f9  call    __security_check_cookie
0x18007f1fe  mov     rbx, [rsp+120h+arg_10]
0x18007f206  add     rsp, 0F0h
0x18007f20d  pop     r15
0x18007f20f  pop     r14
0x18007f211  pop     r13
0x18007f213  pop     r12
0x18007f215  pop     rdi
0x18007f216  pop     rsi
0x18007f217  pop     rbp
0x18007f218  retn
```
