# ComputeMaximumNumberOfNodes(_HCLUSTER *,ulong *)

- ea: `0x180080fac`
- end: `0x180081199`
- name: `?ComputeMaximumNumberOfNodes@@YAKPEAU_HCLUSTER@@PEAK@Z`
- size: `493`
- prototype: `unsigned int __fastcall(HCLUSTER hCluster, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180034950`

## callees

- `0x180002ad0`
- `0x180080fac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081000`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081096`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081119`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081000`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081096`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081119`
- `CLUSAPI!CloseClusterNode` at `0x18008112a`
- `CLUSAPI!CloseClusterNode` at `0x18008112a`
- `CLUSAPI!GetClusterNodeKey` at `0x1800810b1`
- `CLUSAPI!GetClusterNodeKey` at `0x1800810b1`
- `CLUSAPI!OpenClusterNode` at `0x180081082`
- `CLUSAPI!OpenClusterNode` at `0x180081082`
- `CLUSAPI!ClusterGetEnumCount` at `0x180081019`
- `CLUSAPI!ClusterGetEnumCount` at `0x180081019`
- `CLUSAPI!ClusterCloseEnum` at `0x18008114d`
- `CLUSAPI!ClusterCloseEnum` at `0x18008114d`
- `CLUSAPI!ClusterEnum` at `0x180081065`
- `CLUSAPI!ClusterEnum` at `0x180081065`
- `CLUSAPI!ClusterOpenEnum` at `0x180080fea`
- `CLUSAPI!ClusterOpenEnum` at `0x180080fea`
- `CLUSAPI!ClusterRegCloseKey` at `0x18008110b`
- `CLUSAPI!ClusterRegCloseKey` at `0x18008110b`
- `CLUSAPI!ClusterRegQueryValue` at `0x1800810f3`
- `CLUSAPI!ClusterRegQueryValue` at `0x1800810f3`

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
0x180080fac  mov     [rsp-8+arg_10], rbx
0x180080fb1  push    rbp
0x180080fb2  push    rsi
0x180080fb3  push    rdi
0x180080fb4  push    r12
0x180080fb6  push    r13
0x180080fb8  push    r14
0x180080fba  push    r15
0x180080fbc  lea     rbp, [rsp-27h]
0x180080fc1  sub     rsp, 0F0h
0x180080fc8  mov     rax, cs:__security_cookie
0x180080fcf  xor     rax, rsp
0x180080fd2  mov     [rbp+57h+var_40], rax
0x180080fd6  mov     r12, rdx
0x180080fd9  mov     [rbp+57h+var_D0], rdx
0x180080fdd  mov     edx, 1; dwType
0x180080fe2  mov     [rsp+120h+var_D8], rcx
0x180080fe7  mov     r15, rcx
0x180080fea  call    cs:__imp_ClusterOpenEnum
0x180080ff1  nop     dword ptr [rax+rax+00h]
0x180080ff6  xor     esi, esi
0x180080ff8  mov     r14, rax
0x180080ffb  test    rax, rax
0x180080ffe  jnz     short loc_180081011
0x180081000  call    cs:__imp_GetLastError
0x180081007  nop     dword ptr [rax+rax+00h]
0x18008100c  jmp     loc_180081171
0x180081011  mov     rcx, r14; hEnum
0x180081014  mov     ebx, esi
0x180081016  or      edi, 0FFFFFFFFh
0x180081019  call    cs:__imp_ClusterGetEnumCount
0x180081020  nop     dword ptr [rax+rax+00h]
0x180081025  mov     [rsp+120h+cchName], esi
0x180081029  mov     r13d, eax
0x18008102c  mov     [rsp+120h+dwType], esi
0x180081030  mov     [rsp+120h+dwValueType], esi
0x180081034  test    eax, eax
0x180081036  jz      loc_18008114A
0x18008103c  cmp     edi, 0FFFFFFFFh
0x18008103f  jnz     loc_180081146
0x180081045  lea     rax, [rsp+120h+cchName]
0x18008104a  mov     [rsp+120h+cchName], 40h ; '@'
0x180081052  lea     r9, [rbp+57h+szName]; lpszName
0x180081056  mov     [rsp+120h+lpcchName], rax; lpcchName
0x18008105b  lea     r8, [rsp+120h+dwType]; lpdwType
0x180081060  mov     edx, esi; dwIndex
0x180081062  mov     rcx, r14; hEnum
0x180081065  call    cs:__imp_ClusterEnum
0x18008106c  nop     dword ptr [rax+rax+00h]
0x180081071  mov     ebx, eax
0x180081073  test    eax, eax
0x180081075  jnz     loc_180081146
0x18008107b  lea     rdx, [rbp+57h+szName]; lpszNodeName
0x18008107f  mov     rcx, r15; hCluster
0x180081082  call    cs:__imp_OpenClusterNode
0x180081089  nop     dword ptr [rax+rax+00h]
0x18008108e  mov     r15, rax
0x180081091  test    rax, rax
0x180081094  jnz     short loc_1800810A9
0x180081096  call    cs:__imp_GetLastError
0x18008109d  nop     dword ptr [rax+rax+00h]
0x1800810a2  mov     ebx, eax
0x1800810a4  jmp     loc_180081136
0x1800810a9  mov     edx, 1; samDesired
0x1800810ae  mov     rcx, r15; hNode
0x1800810b1  call    cs:__imp_GetClusterNodeKey
0x1800810b8  nop     dword ptr [rax+rax+00h]
0x1800810bd  mov     r12, rax
0x1800810c0  test    rax, rax
0x1800810c3  jz      short loc_180081119
0x1800810c5  lea     rax, [rsp+120h+cbData]
0x1800810ca  mov     dword ptr [rsp+120h+Data], 0
0x1800810d2  lea     r9, [rsp+120h+Data]; lpData
0x1800810d7  mov     [rsp+120h+lpcchName], rax; lpcbData
0x1800810dc  lea     r8, [rsp+120h+dwValueType]; lpdwValueType
0x1800810e1  mov     [rsp+120h+cbData], 4
0x1800810e9  lea     rdx, ValueName; "MaxLicensedNodes"
0x1800810f0  mov     rcx, r12; hKey
0x1800810f3  call    cs:__imp_ClusterRegQueryValue
0x1800810fa  nop     dword ptr [rax+rax+00h]
0x1800810ff  test    eax, eax
0x180081101  mov     rcx, r12; hKey
0x180081104  mov     ebx, eax
0x180081106  cmovz   edi, dword ptr [rsp+120h+Data]
0x18008110b  call    cs:__imp_ClusterRegCloseKey
0x180081112  nop     dword ptr [rax+rax+00h]
0x180081117  jmp     short loc_180081127
0x180081119  call    cs:__imp_GetLastError
0x180081120  nop     dword ptr [rax+rax+00h]
0x180081125  mov     ebx, eax
0x180081127  mov     rcx, r15; hNode
0x18008112a  call    cs:__imp_CloseClusterNode
0x180081131  nop     dword ptr [rax+rax+00h]
0x180081136  mov     r15, [rsp+120h+var_D8]
0x18008113b  inc     esi
0x18008113d  cmp     esi, r13d
0x180081140  jb      loc_18008103C
0x180081146  mov     r12, [rbp+57h+var_D0]
0x18008114a  mov     rcx, r14; hEnum
0x18008114d  call    cs:__imp_ClusterCloseEnum
0x180081154  nop     dword ptr [rax+rax+00h]
0x180081159  cmp     edi, 0FFFFFFFFh
0x18008115c  jnz     short loc_180081169
0x18008115e  test    ebx, ebx
0x180081160  jnz     short loc_18008116F
0x180081162  mov     ebx, 2
0x180081167  jmp     short loc_18008116F
0x180081169  xor     ebx, ebx
0x18008116b  mov     [r12], edi
0x18008116f  mov     eax, ebx
0x180081171  mov     rcx, [rbp+57h+var_40]
0x180081175  xor     rcx, rsp; StackCookie
0x180081178  call    __security_check_cookie
0x18008117d  mov     rbx, [rsp+120h+arg_10]
0x180081185  add     rsp, 0F0h
0x18008118c  pop     r15
0x18008118e  pop     r14
0x180081190  pop     r13
0x180081192  pop     r12
0x180081194  pop     rdi
0x180081195  pop     rsi
0x180081196  pop     rbp
0x180081197  retn
```
