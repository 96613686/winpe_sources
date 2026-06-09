# ComputeMaximumNumberOfNodes(_HCLUSTER *,ulong *)

- ea: `0x180043d5c`
- end: `0x180043f49`
- name: `?ComputeMaximumNumberOfNodes@@YAKPEAU_HCLUSTER@@PEAK@Z`
- size: `493`
- prototype: `unsigned int __fastcall(HCLUSTER hCluster, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180030ad0`

## callees

- `0x180002b50`
- `0x180043d5c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043db0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043e46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043ec9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043db0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043e46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043ec9`
- `CLUSAPI!CloseClusterNode` at `0x180043eda`
- `CLUSAPI!CloseClusterNode` at `0x180043eda`
- `CLUSAPI!ClusterRegQueryValue` at `0x180043ea3`
- `CLUSAPI!ClusterRegQueryValue` at `0x180043ea3`
- `CLUSAPI!ClusterRegCloseKey` at `0x180043ebb`
- `CLUSAPI!ClusterRegCloseKey` at `0x180043ebb`
- `CLUSAPI!ClusterEnum` at `0x180043e15`
- `CLUSAPI!ClusterEnum` at `0x180043e15`
- `CLUSAPI!ClusterOpenEnum` at `0x180043d9a`
- `CLUSAPI!ClusterOpenEnum` at `0x180043d9a`
- `CLUSAPI!ClusterGetEnumCount` at `0x180043dc9`
- `CLUSAPI!ClusterGetEnumCount` at `0x180043dc9`
- `CLUSAPI!OpenClusterNode` at `0x180043e32`
- `CLUSAPI!OpenClusterNode` at `0x180043e32`
- `CLUSAPI!GetClusterNodeKey` at `0x180043e61`
- `CLUSAPI!GetClusterNodeKey` at `0x180043e61`
- `CLUSAPI!ClusterCloseEnum` at `0x180043efd`
- `CLUSAPI!ClusterCloseEnum` at `0x180043efd`

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
0x180043d5c  mov     [rsp-8+arg_10], rbx
0x180043d61  push    rbp
0x180043d62  push    rsi
0x180043d63  push    rdi
0x180043d64  push    r12
0x180043d66  push    r13
0x180043d68  push    r14
0x180043d6a  push    r15
0x180043d6c  lea     rbp, [rsp-27h]
0x180043d71  sub     rsp, 0F0h
0x180043d78  mov     rax, cs:__security_cookie
0x180043d7f  xor     rax, rsp
0x180043d82  mov     [rbp+57h+var_40], rax
0x180043d86  mov     r12, rdx
0x180043d89  mov     [rbp+57h+var_D0], rdx
0x180043d8d  mov     edx, 1; dwType
0x180043d92  mov     [rsp+120h+var_D8], rcx
0x180043d97  mov     r15, rcx
0x180043d9a  call    cs:__imp_ClusterOpenEnum
0x180043da1  nop     dword ptr [rax+rax+00h]
0x180043da6  xor     esi, esi
0x180043da8  mov     r14, rax
0x180043dab  test    rax, rax
0x180043dae  jnz     short loc_180043DC1
0x180043db0  call    cs:__imp_GetLastError
0x180043db7  nop     dword ptr [rax+rax+00h]
0x180043dbc  jmp     loc_180043F21
0x180043dc1  mov     rcx, r14; hEnum
0x180043dc4  mov     ebx, esi
0x180043dc6  or      edi, 0FFFFFFFFh
0x180043dc9  call    cs:__imp_ClusterGetEnumCount
0x180043dd0  nop     dword ptr [rax+rax+00h]
0x180043dd5  mov     [rsp+120h+cchName], esi
0x180043dd9  mov     r13d, eax
0x180043ddc  mov     [rsp+120h+dwType], esi
0x180043de0  mov     [rsp+120h+dwValueType], esi
0x180043de4  test    eax, eax
0x180043de6  jz      loc_180043EFA
0x180043dec  cmp     edi, 0FFFFFFFFh
0x180043def  jnz     loc_180043EF6
0x180043df5  lea     rax, [rsp+120h+cchName]
0x180043dfa  mov     [rsp+120h+cchName], 40h ; '@'
0x180043e02  lea     r9, [rbp+57h+szName]; lpszName
0x180043e06  mov     [rsp+120h+lpcchName], rax; lpcchName
0x180043e0b  lea     r8, [rsp+120h+dwType]; lpdwType
0x180043e10  mov     edx, esi; dwIndex
0x180043e12  mov     rcx, r14; hEnum
0x180043e15  call    cs:__imp_ClusterEnum
0x180043e1c  nop     dword ptr [rax+rax+00h]
0x180043e21  mov     ebx, eax
0x180043e23  test    eax, eax
0x180043e25  jnz     loc_180043EF6
0x180043e2b  lea     rdx, [rbp+57h+szName]; lpszNodeName
0x180043e2f  mov     rcx, r15; hCluster
0x180043e32  call    cs:__imp_OpenClusterNode
0x180043e39  nop     dword ptr [rax+rax+00h]
0x180043e3e  mov     r15, rax
0x180043e41  test    rax, rax
0x180043e44  jnz     short loc_180043E59
0x180043e46  call    cs:__imp_GetLastError
0x180043e4d  nop     dword ptr [rax+rax+00h]
0x180043e52  mov     ebx, eax
0x180043e54  jmp     loc_180043EE6
0x180043e59  mov     edx, 1; samDesired
0x180043e5e  mov     rcx, r15; hNode
0x180043e61  call    cs:__imp_GetClusterNodeKey
0x180043e68  nop     dword ptr [rax+rax+00h]
0x180043e6d  mov     r12, rax
0x180043e70  test    rax, rax
0x180043e73  jz      short loc_180043EC9
0x180043e75  lea     rax, [rsp+120h+cbData]
0x180043e7a  mov     dword ptr [rsp+120h+Data], 0
0x180043e82  lea     r9, [rsp+120h+Data]; lpData
0x180043e87  mov     [rsp+120h+lpcchName], rax; lpcbData
0x180043e8c  lea     r8, [rsp+120h+dwValueType]; lpdwValueType
0x180043e91  mov     [rsp+120h+cbData], 4
0x180043e99  lea     rdx, ValueName; "MaxLicensedNodes"
0x180043ea0  mov     rcx, r12; hKey
0x180043ea3  call    cs:__imp_ClusterRegQueryValue
0x180043eaa  nop     dword ptr [rax+rax+00h]
0x180043eaf  test    eax, eax
0x180043eb1  mov     rcx, r12; hKey
0x180043eb4  mov     ebx, eax
0x180043eb6  cmovz   edi, dword ptr [rsp+120h+Data]
0x180043ebb  call    cs:__imp_ClusterRegCloseKey
0x180043ec2  nop     dword ptr [rax+rax+00h]
0x180043ec7  jmp     short loc_180043ED7
0x180043ec9  call    cs:__imp_GetLastError
0x180043ed0  nop     dword ptr [rax+rax+00h]
0x180043ed5  mov     ebx, eax
0x180043ed7  mov     rcx, r15; hNode
0x180043eda  call    cs:__imp_CloseClusterNode
0x180043ee1  nop     dword ptr [rax+rax+00h]
0x180043ee6  mov     r15, [rsp+120h+var_D8]
0x180043eeb  inc     esi
0x180043eed  cmp     esi, r13d
0x180043ef0  jb      loc_180043DEC
0x180043ef6  mov     r12, [rbp+57h+var_D0]
0x180043efa  mov     rcx, r14; hEnum
0x180043efd  call    cs:__imp_ClusterCloseEnum
0x180043f04  nop     dword ptr [rax+rax+00h]
0x180043f09  cmp     edi, 0FFFFFFFFh
0x180043f0c  jnz     short loc_180043F19
0x180043f0e  test    ebx, ebx
0x180043f10  jnz     short loc_180043F1F
0x180043f12  mov     ebx, 2
0x180043f17  jmp     short loc_180043F1F
0x180043f19  xor     ebx, ebx
0x180043f1b  mov     [r12], edi
0x180043f1f  mov     eax, ebx
0x180043f21  mov     rcx, [rbp+57h+var_40]
0x180043f25  xor     rcx, rsp; StackCookie
0x180043f28  call    __security_check_cookie
0x180043f2d  mov     rbx, [rsp+120h+arg_10]
0x180043f35  add     rsp, 0F0h
0x180043f3c  pop     r15
0x180043f3e  pop     r14
0x180043f40  pop     r13
0x180043f42  pop     r12
0x180043f44  pop     rdi
0x180043f45  pop     rsi
0x180043f46  pop     rbp
0x180043f47  retn
```
