# ComputeMaximumNumberOfNodes(_HCLUSTER *,ulong *)

- ea: `0x180042640`
- end: `0x1800427e1`
- name: `?ComputeMaximumNumberOfNodes@@YAKPEAU_HCLUSTER@@PEAK@Z`
- size: `417`
- prototype: `unsigned int __fastcall(HCLUSTER hCluster, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002fad0`

## callees

- `0x180002ae0`
- `0x180042640`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004268e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004270c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042774`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004268e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004270c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042774`
- `CLUSAPI!CloseClusterNode` at `0x18004277f`
- `CLUSAPI!CloseClusterNode` at `0x18004277f`
- `CLUSAPI!ClusterRegQueryValue` at `0x18004275a`
- `CLUSAPI!ClusterRegQueryValue` at `0x18004275a`
- `CLUSAPI!ClusterRegCloseKey` at `0x18004276c`
- `CLUSAPI!ClusterRegCloseKey` at `0x18004276c`
- `CLUSAPI!ClusterEnum` at `0x1800426e7`
- `CLUSAPI!ClusterEnum` at `0x1800426e7`
- `CLUSAPI!ClusterOpenEnum` at `0x18004267e`
- `CLUSAPI!ClusterOpenEnum` at `0x18004267e`
- `CLUSAPI!ClusterGetEnumCount` at `0x1800426a1`
- `CLUSAPI!ClusterGetEnumCount` at `0x1800426a1`
- `CLUSAPI!OpenClusterNode` at `0x1800426fe`
- `CLUSAPI!OpenClusterNode` at `0x1800426fe`
- `CLUSAPI!GetClusterNodeKey` at `0x18004271e`
- `CLUSAPI!GetClusterNodeKey` at `0x18004271e`
- `CLUSAPI!ClusterCloseEnum` at `0x18004279c`
- `CLUSAPI!ClusterCloseEnum` at `0x18004279c`

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
0x180042640  mov     [rsp-8+arg_10], rbx
0x180042645  push    rbp
0x180042646  push    rsi
0x180042647  push    rdi
0x180042648  push    r12
0x18004264a  push    r13
0x18004264c  push    r14
0x18004264e  push    r15
0x180042650  lea     rbp, [rsp-27h]
0x180042655  sub     rsp, 0F0h
0x18004265c  mov     rax, cs:__security_cookie
0x180042663  xor     rax, rsp
0x180042666  mov     [rbp+57h+var_40], rax
0x18004266a  mov     r12, rdx
0x18004266d  mov     [rbp+57h+var_D0], rdx
0x180042671  mov     edx, 1; dwType
0x180042676  mov     [rsp+120h+var_D8], rcx
0x18004267b  mov     r15, rcx
0x18004267e  call    cs:__imp_ClusterOpenEnum
0x180042684  xor     esi, esi
0x180042686  mov     r14, rax
0x180042689  test    rax, rax
0x18004268c  jnz     short loc_180042699
0x18004268e  call    cs:__imp_GetLastError
0x180042694  jmp     loc_1800427BA
0x180042699  mov     rcx, r14; hEnum
0x18004269c  mov     ebx, esi
0x18004269e  or      edi, 0FFFFFFFFh
0x1800426a1  call    cs:__imp_ClusterGetEnumCount
0x1800426a7  mov     [rsp+120h+cchName], esi
0x1800426ab  mov     r13d, eax
0x1800426ae  mov     [rsp+120h+dwType], esi
0x1800426b2  mov     [rsp+120h+dwValueType], esi
0x1800426b6  test    eax, eax
0x1800426b8  jz      loc_180042799
0x1800426be  cmp     edi, 0FFFFFFFFh
0x1800426c1  jnz     loc_180042795
0x1800426c7  lea     rax, [rsp+120h+cchName]
0x1800426cc  mov     [rsp+120h+cchName], 40h ; '@'
0x1800426d4  lea     r9, [rbp+57h+szName]; lpszName
0x1800426d8  mov     [rsp+120h+lpcchName], rax; lpcchName
0x1800426dd  lea     r8, [rsp+120h+dwType]; lpdwType
0x1800426e2  mov     edx, esi; dwIndex
0x1800426e4  mov     rcx, r14; hEnum
0x1800426e7  call    cs:__imp_ClusterEnum
0x1800426ed  mov     ebx, eax
0x1800426ef  test    eax, eax
0x1800426f1  jnz     loc_180042795
0x1800426f7  lea     rdx, [rbp+57h+szName]; lpszNodeName
0x1800426fb  mov     rcx, r15; hCluster
0x1800426fe  call    cs:__imp_OpenClusterNode
0x180042704  mov     r15, rax
0x180042707  test    rax, rax
0x18004270a  jnz     short loc_180042716
0x18004270c  call    cs:__imp_GetLastError
0x180042712  mov     ebx, eax
0x180042714  jmp     short loc_180042785
0x180042716  mov     edx, 1; samDesired
0x18004271b  mov     rcx, r15; hNode
0x18004271e  call    cs:__imp_GetClusterNodeKey
0x180042724  mov     r12, rax
0x180042727  test    rax, rax
0x18004272a  jz      short loc_180042774
0x18004272c  lea     rax, [rsp+120h+cbData]
0x180042731  mov     dword ptr [rsp+120h+Data], 0
0x180042739  lea     r9, [rsp+120h+Data]; lpData
0x18004273e  mov     [rsp+120h+lpcchName], rax; lpcbData
0x180042743  lea     r8, [rsp+120h+dwValueType]; lpdwValueType
0x180042748  mov     [rsp+120h+cbData], 4
0x180042750  lea     rdx, ValueName; "MaxLicensedNodes"
0x180042757  mov     rcx, r12; hKey
0x18004275a  call    cs:__imp_ClusterRegQueryValue
0x180042760  test    eax, eax
0x180042762  mov     rcx, r12; hKey
0x180042765  mov     ebx, eax
0x180042767  cmovz   edi, dword ptr [rsp+120h+Data]
0x18004276c  call    cs:__imp_ClusterRegCloseKey
0x180042772  jmp     short loc_18004277C
0x180042774  call    cs:__imp_GetLastError
0x18004277a  mov     ebx, eax
0x18004277c  mov     rcx, r15; hNode
0x18004277f  call    cs:__imp_CloseClusterNode
0x180042785  mov     r15, [rsp+120h+var_D8]
0x18004278a  inc     esi
0x18004278c  cmp     esi, r13d
0x18004278f  jb      loc_1800426BE
0x180042795  mov     r12, [rbp+57h+var_D0]
0x180042799  mov     rcx, r14; hEnum
0x18004279c  call    cs:__imp_ClusterCloseEnum
0x1800427a2  cmp     edi, 0FFFFFFFFh
0x1800427a5  jnz     short loc_1800427B2
0x1800427a7  test    ebx, ebx
0x1800427a9  jnz     short loc_1800427B8
0x1800427ab  mov     ebx, 2
0x1800427b0  jmp     short loc_1800427B8
0x1800427b2  xor     ebx, ebx
0x1800427b4  mov     [r12], edi
0x1800427b8  mov     eax, ebx
0x1800427ba  mov     rcx, [rbp+57h+var_40]
0x1800427be  xor     rcx, rsp; StackCookie
0x1800427c1  call    __security_check_cookie
0x1800427c6  mov     rbx, [rsp+120h+arg_10]
0x1800427ce  add     rsp, 0F0h
0x1800427d5  pop     r15
0x1800427d7  pop     r14
0x1800427d9  pop     r13
0x1800427db  pop     r12
0x1800427dd  pop     rdi
0x1800427de  pop     rsi
0x1800427df  pop     rbp
0x1800427e0  retn
```
