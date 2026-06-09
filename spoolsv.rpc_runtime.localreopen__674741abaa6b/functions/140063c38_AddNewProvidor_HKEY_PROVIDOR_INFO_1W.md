# AddNewProvidor(HKEY__ *,_PROVIDOR_INFO_1W *)

- ea: `0x140063c38`
- end: `0x140063fda`
- name: `?AddNewProvidor@@YAKPEAUHKEY__@@PEAU_PROVIDOR_INFO_1W@@@Z`
- size: `930`
- prototype: `unsigned int __fastcall(HKEY hKey, struct _PROVIDOR_INFO_1W *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1400647d0`

## callees

- `0x140004790`
- `0x1400177c4`
- `0x140063c38`
- `0x140068ff8`
- `0x14006914c`
- `0x14006b70c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140063f64`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140063f81`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140063f9e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140063f64`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140063f81`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140063f9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140063cac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140063cac`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140063f45`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140063f45`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x140063f04`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x140063f04`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140063d2c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140063d2c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140063dc6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140063e21`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140063dc6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140063e21`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140063d79`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140063e74`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140063f37`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140063d79`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140063e74`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140063f37`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140063d93`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140063fb3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140063d93`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140063fb3`
- `KERNELBASE!lstrcmpiW` at `0x140063cd9`
- `KERNELBASE!lstrcmpiW` at `0x140063cd9`

## pseudocode

```c
__int64 __fastcall AddNewProvidor(HKEY hKey, struct _PROVIDOR_INFO_1W *a2)
{
  LPWSTR pName; // rcx
  DWORD v5; // r13d
  BYTE *v6; // rdi
  BYTE *v7; // r12
  LPWSTR pDLLName; // rax
  unsigned __int16 *v9; // r15
  DWORD LastError; // ebx
  struct _PROVIDOR *i; // rbx
  const BYTE *v12; // rcx
  __int64 v13; // rax
  LSTATUS v14; // eax
  const BYTE *appended; // rax
  struct _PROVIDOR *v16; // rax
  struct _PROVIDOR **v17; // rcx
  int v19; // [rsp+50h] [rbp-20h]
  HKEY hKeya; // [rsp+58h] [rbp-18h] BYREF
  struct _PROVIDOR *v21; // [rsp+60h] [rbp-10h]
  DWORD cbData; // [rsp+B8h] [rbp+48h] BYREF
  DWORD v23; // [rsp+C0h] [rbp+50h] BYREF
  DWORD dwDisposition; // [rsp+C8h] [rbp+58h] BYREF

  pName = a2->pName;
  v19 = 0;
  v5 = 0;
  cbData = 0;
  v6 = 0;
  v23 = 0;
  v7 = 0;
  dwDisposition = 0;
  hKeya = 0;
  if ( !pName || (pDLLName = a2->pDLLName) == 0 || !*pName || !*pDLLName )
  {
    v9 = 0;
    LastError = 87;
    goto LABEL_27;
  }
  v9 = (unsigned __int16 *)DllAllocSplMem(0x26Au);
  if ( !v9 )
    goto LABEL_6;
  v21 = 0;
  for ( i = pLocalProvidor; i; i = *(struct _PROVIDOR **)i )
  {
    if ( !lstrcmpiW(*((LPCWSTR *)i + 1), a2->pDLLName) )
    {
      LastError = 0;
      goto LABEL_39;
    }
    v21 = i;
  }
  LastError = RegCreateKeyExW(hKey, a2->pName, 0, 0, 0, 0x3001Fu, 0, &hKeya, &dwDisposition);
  if ( !LastError )
  {
    v12 = (const BYTE *)a2->pDLLName;
    v13 = -1;
    do
      ++v13;
    while ( *(_WORD *)&v12[2 * v13] );
    LastError = RegSetValueExW(hKeya, L"Name", 0, 1u, v12, 2 * v13 + 2);
    if ( !LastError )
    {
      RegCloseKey(hKeya);
      hKeya = 0;
      cbData = 0;
      v14 = RegQueryValueExW(hKey, L"Order", 0, 0, 0, &cbData);
      LastError = v14;
      if ( v14 )
      {
        if ( v14 != 2 )
          goto LABEL_27;
      }
      else
      {
        v5 = cbData;
        if ( !cbData || (v6 = (BYTE *)DllAllocSplMem(cbData)) == 0 )
        {
LABEL_6:
          LastError = GetLastError();
          goto LABEL_27;
        }
        LastError = RegQueryValueExW(hKey, L"Order", 0, 0, v6, &cbData);
        if ( LastError )
          goto LABEL_27;
      }
      appended = (const BYTE *)AppendOrderEntry((unsigned __int16 *)v6, cbData, a2->pName, &v23);
      v7 = (BYTE *)appended;
      if ( appended )
      {
        v23 = RegSetValueExW(hKey, L"Order", 0, 7u, appended, v23);
        LastError = v23;
        if ( !v23 )
        {
          v19 = 1;
          StringCchPrintfW(v9, 0x135u, L"%ws\\%ws", L"System\\CurrentControlSet\\Control\\Print\\Providers", a2->pName);
          v16 = InitializeProvidor(a2->pDLLName, v9, &v23);
          LastError = v23;
          if ( v16 )
          {
            v17 = (struct _PROVIDOR **)v21;
            *(_QWORD *)v16 = 0;
            *v17 = v16;
          }
        }
      }
    }
  }
LABEL_27:
  if ( !LastError )
    goto LABEL_34;
  if ( dwDisposition == 1 )
  {
    DeleteSubKeyTree(hKey, a2->pName);
    RegDeleteKeyExW(hKey, a2->pName, 0, 0);
  }
  if ( v19 )
  {
    if ( !v6 )
    {
      RegDeleteValueW(hKey, L"Order");
      goto LABEL_36;
    }
    RegSetValueExW(hKey, L"Order", 0, 7u, v6, v5);
  }
  else
  {
LABEL_34:
    if ( !v6 )
      goto LABEL_36;
  }
  HeapFree(g_hSpoolssHeap, 0, v6);
LABEL_36:
  if ( v7 )
    HeapFree(g_hSpoolssHeap, 0, v7);
  if ( v9 )
LABEL_39:
    HeapFree(g_hSpoolssHeap, 0, v9);
  if ( hKeya )
    RegCloseKey(hKeya);
  return LastError;
}

```

## disassembly

```asm
0x140063c38  mov     [rsp-38h+arg_0], rbx
0x140063c3d  push    rbp
0x140063c3e  push    rsi
0x140063c3f  push    rdi
0x140063c40  push    r12
0x140063c42  push    r13
0x140063c44  push    r14
0x140063c46  push    r15
0x140063c48  mov     rbp, rsp
0x140063c4b  sub     rsp, 70h
0x140063c4f  xor     ebx, ebx
0x140063c51  mov     r14, rcx
0x140063c54  mov     rcx, [rdx]
0x140063c57  mov     rsi, rdx
0x140063c5a  mov     [rbp+var_20], ebx
0x140063c5d  mov     r13d, ebx
0x140063c60  mov     [rbp+cbData], ebx
0x140063c63  mov     edi, ebx
0x140063c65  mov     [rbp+arg_10], ebx
0x140063c68  mov     r12d, ebx
0x140063c6b  mov     [rbp+dwDisposition], ebx
0x140063c6e  mov     [rbp+hKey], rbx
0x140063c72  test    rcx, rcx
0x140063c75  jz      loc_140063EDB
0x140063c7b  mov     rax, [rdx+10h]
0x140063c7f  test    rax, rax
0x140063c82  jz      loc_140063EDB
0x140063c88  cmp     [rcx], bx
0x140063c8b  jz      loc_140063EDB
0x140063c91  cmp     [rax], bx
0x140063c94  jz      loc_140063EDB
0x140063c9a  mov     ecx, 26Ah; dwBytes
0x140063c9f  call    DllAllocSplMem
0x140063ca4  mov     r15, rax
0x140063ca7  test    rax, rax
0x140063caa  jnz     short loc_140063CBF
0x140063cac  call    cs:__imp_GetLastError
0x140063cb3  nop     dword ptr [rax+rax+00h]
0x140063cb8  mov     ebx, eax
0x140063cba  jmp     loc_140063EE3
0x140063cbf  mov     [rbp+var_10], rbx
0x140063cc3  xor     ecx, ecx
0x140063cc5  mov     rbx, cs:?pLocalProvidor@@3PEAU_PROVIDOR@@EA; _PROVIDOR * pLocalProvidor
0x140063ccc  test    rbx, rbx
0x140063ccf  jz      short loc_140063CFD
0x140063cd1  mov     rdx, [rsi+10h]; lpString2
0x140063cd5  mov     rcx, [rbx+8]; lpString1
0x140063cd9  call    cs:__imp_lstrcmpiW
0x140063ce0  nop     dword ptr [rax+rax+00h]
0x140063ce5  xor     ecx, ecx
0x140063ce7  test    eax, eax
0x140063ce9  jz      short loc_140063CF4
0x140063ceb  mov     [rbp+var_10], rbx
0x140063cef  mov     rbx, [rbx]
0x140063cf2  jmp     short loc_140063CCC
0x140063cf4  xor     esi, esi
0x140063cf6  mov     ebx, esi
0x140063cf8  jmp     loc_140063F92
0x140063cfd  mov     rdx, [rsi]; lpSubKey
0x140063d00  lea     rax, [rbp+dwDisposition]
0x140063d04  mov     [rsp+70h+lpdwDisposition], rax; lpdwDisposition
0x140063d09  xor     r9d, r9d; lpClass
0x140063d0c  lea     rax, [rbp+hKey]
0x140063d10  xor     r8d, r8d; Reserved
0x140063d13  mov     [rsp+70h+phkResult], rax; phkResult
0x140063d18  mov     [rsp+70h+lpSecurityAttributes], rcx; lpSecurityAttributes
0x140063d1d  mov     [rsp+70h+samDesired], 3001Fh; samDesired
0x140063d25  mov     [rsp+70h+dwOptions], ecx; dwOptions
0x140063d29  mov     rcx, r14; hKey
0x140063d2c  call    cs:__imp_RegCreateKeyExW
0x140063d33  nop     dword ptr [rax+rax+00h]
0x140063d38  xor     edx, edx
0x140063d3a  mov     ebx, eax
0x140063d3c  test    eax, eax
0x140063d3e  jnz     loc_140063EE3
0x140063d44  mov     rcx, [rsi+10h]
0x140063d48  or      rax, 0FFFFFFFFFFFFFFFFh
0x140063d4c  inc     rax
0x140063d4f  cmp     [rcx+rax*2], dx
0x140063d53  jnz     short loc_140063D4C
0x140063d55  lea     eax, ds:2[rax*2]
0x140063d5c  mov     r9d, 1; dwType
0x140063d62  mov     [rsp+70h+samDesired], eax; cbData
0x140063d66  lea     rdx, aName; "Name"
0x140063d6d  mov     qword ptr [rsp+70h+dwOptions], rcx; lpData
0x140063d72  xor     r8d, r8d; Reserved
0x140063d75  mov     rcx, [rbp+hKey]; hKey
0x140063d79  call    cs:__imp_RegSetValueExW
0x140063d80  nop     dword ptr [rax+rax+00h]
0x140063d85  mov     ebx, eax
0x140063d87  test    eax, eax
0x140063d89  jnz     loc_140063EE3
0x140063d8f  mov     rcx, [rbp+hKey]; hKey
0x140063d93  call    cs:__imp_RegCloseKey
0x140063d9a  nop     dword ptr [rax+rax+00h]
0x140063d9f  xor     ecx, ecx
0x140063da1  lea     rax, [rbp+cbData]
0x140063da5  mov     qword ptr [rsp+70h+samDesired], rax; lpcbData
0x140063daa  lea     rdx, szOrder; "Order"
0x140063db1  mov     qword ptr [rsp+70h+dwOptions], rcx; lpData
0x140063db6  xor     r9d, r9d; lpType
0x140063db9  mov     [rbp+hKey], rcx
0x140063dbd  xor     r8d, r8d; lpReserved
0x140063dc0  mov     [rbp+cbData], ecx
0x140063dc3  mov     rcx, r14; hKey
0x140063dc6  call    cs:__imp_RegQueryValueExW
0x140063dcd  nop     dword ptr [rax+rax+00h]
0x140063dd2  mov     ebx, eax
0x140063dd4  test    eax, eax
0x140063dd6  jz      short loc_140063DE2
0x140063dd8  cmp     eax, 2
0x140063ddb  jz      short loc_140063E37
0x140063ddd  jmp     loc_140063EE3
0x140063de2  mov     r13d, [rbp+cbData]
0x140063de6  test    r13d, r13d
0x140063de9  jz      loc_140063CAC
0x140063def  mov     ecx, r13d; dwBytes
0x140063df2  call    DllAllocSplMem
0x140063df7  mov     rdi, rax
0x140063dfa  test    rax, rax
0x140063dfd  jz      loc_140063CAC
0x140063e03  lea     rax, [rbp+cbData]
0x140063e07  xor     r9d, r9d; lpType
0x140063e0a  mov     qword ptr [rsp+70h+samDesired], rax; lpcbData
0x140063e0f  lea     rdx, szOrder; "Order"
0x140063e16  xor     r8d, r8d; lpReserved
0x140063e19  mov     qword ptr [rsp+70h+dwOptions], rdi; lpData
0x140063e1e  mov     rcx, r14; hKey
0x140063e21  call    cs:__imp_RegQueryValueExW
0x140063e28  nop     dword ptr [rax+rax+00h]
0x140063e2d  mov     ebx, eax
0x140063e2f  test    eax, eax
0x140063e31  jnz     loc_140063EE3
0x140063e37  mov     r8, [rsi]; unsigned __int16 *
0x140063e3a  lea     r9, [rbp+arg_10]; unsigned int *
0x140063e3e  mov     edx, [rbp+cbData]; unsigned int
0x140063e41  mov     rcx, rdi; unsigned __int16 *
0x140063e44  call    ?AppendOrderEntry@@YAPEAGPEAGK0PEAK@Z; AppendOrderEntry(ushort *,ulong,ushort *,ulong *)
0x140063e49  mov     r12, rax
0x140063e4c  test    rax, rax
0x140063e4f  jz      loc_140063EE3
0x140063e55  mov     ecx, [rbp+arg_10]
0x140063e58  lea     rdx, szOrder; "Order"
0x140063e5f  mov     [rsp+70h+samDesired], ecx; cbData
0x140063e63  mov     r9d, 7; dwType
0x140063e69  mov     rcx, r14; hKey
0x140063e6c  mov     qword ptr [rsp+70h+dwOptions], rax; lpData
0x140063e71  xor     r8d, r8d; Reserved
0x140063e74  call    cs:__imp_RegSetValueExW
0x140063e7b  nop     dword ptr [rax+rax+00h]
0x140063e80  mov     [rbp+arg_10], eax
0x140063e83  mov     ebx, eax
0x140063e85  test    eax, eax
0x140063e87  jnz     short loc_140063EE3
0x140063e89  mov     rax, [rsi]
0x140063e8c  lea     r9, szRegistryProvidors; "System\\CurrentControlSet\\Control\\Pri"...
0x140063e93  lea     r8, aWsWs; "%ws\\%ws"
0x140063e9a  mov     qword ptr [rsp+70h+dwOptions], rax
0x140063e9f  mov     edx, 135h; unsigned __int64
0x140063ea4  mov     [rbp+var_20], 1
0x140063eab  mov     rcx, r15; unsigned __int16 *
0x140063eae  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140063eb3  mov     rcx, [rsi+10h]; unsigned __int16 *
0x140063eb7  lea     r8, [rbp+arg_10]; unsigned int *
0x140063ebb  mov     rdx, r15; unsigned __int16 *
0x140063ebe  call    ?InitializeProvidor@@YAPEAU_PROVIDOR@@PEAG0PEAK@Z; InitializeProvidor(ushort *,ushort *,ulong *)
0x140063ec3  mov     ebx, [rbp+arg_10]
0x140063ec6  test    rax, rax
0x140063ec9  jz      short loc_140063EE3
0x140063ecb  mov     rcx, [rbp+var_10]
0x140063ecf  mov     qword ptr [rax], 0
0x140063ed6  mov     [rcx], rax
0x140063ed9  jmp     short loc_140063EE3
0x140063edb  mov     r15, rbx
0x140063ede  mov     ebx, 57h ; 'W'
0x140063ee3  test    ebx, ebx
0x140063ee5  jz      short loc_140063F53
0x140063ee7  cmp     [rbp+dwDisposition], 1
0x140063eeb  jnz     short loc_140063F10
0x140063eed  mov     rdx, [rsi]; lpSubKey
0x140063ef0  mov     rcx, r14; hKey
0x140063ef3  call    ?DeleteSubKeyTree@@YAHPEAUHKEY__@@PEAG@Z; DeleteSubKeyTree(HKEY__ *,ushort *)
0x140063ef8  mov     rdx, [rsi]; lpSubKey
0x140063efb  xor     r9d, r9d; Reserved
0x140063efe  xor     r8d, r8d; samDesired
0x140063f01  mov     rcx, r14; hKey
0x140063f04  call    cs:__imp_RegDeleteKeyExW
0x140063f0b  nop     dword ptr [rax+rax+00h]
0x140063f10  xor     esi, esi
0x140063f12  cmp     [rbp+var_20], esi
0x140063f15  jz      short loc_140063F53
0x140063f17  lea     rdx, szOrder; "Order"
0x140063f1e  mov     rcx, r14; hKey
0x140063f21  test    rdi, rdi
0x140063f24  jz      short loc_140063F45
0x140063f26  mov     [rsp+70h+samDesired], r13d; cbData
0x140063f2b  lea     r9d, [rsi+7]; dwType
0x140063f2f  xor     r8d, r8d; Reserved
0x140063f32  mov     qword ptr [rsp+70h+dwOptions], rdi; lpData
0x140063f37  call    cs:__imp_RegSetValueExW
0x140063f3e  nop     dword ptr [rax+rax+00h]
0x140063f43  jmp     short loc_140063F58
0x140063f45  call    cs:__imp_RegDeleteValueW
0x140063f4c  nop     dword ptr [rax+rax+00h]
0x140063f51  jmp     short loc_140063F70
0x140063f53  test    rdi, rdi
0x140063f56  jz      short loc_140063F70
0x140063f58  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x140063f5f  mov     r8, rdi; lpMem
0x140063f62  xor     edx, edx; dwFlags
0x140063f64  call    cs:__imp_HeapFree
0x140063f6b  nop     dword ptr [rax+rax+00h]
0x140063f70  test    r12, r12
0x140063f73  jz      short loc_140063F8D
0x140063f75  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x140063f7c  mov     r8, r12; lpMem
0x140063f7f  xor     edx, edx; dwFlags
0x140063f81  call    cs:__imp_HeapFree
0x140063f88  nop     dword ptr [rax+rax+00h]
0x140063f8d  test    r15, r15
0x140063f90  jz      short loc_140063FAA
0x140063f92  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x140063f99  mov     r8, r15; lpMem
0x140063f9c  xor     edx, edx; dwFlags
0x140063f9e  call    cs:__imp_HeapFree
0x140063fa5  nop     dword ptr [rax+rax+00h]
0x140063faa  mov     rcx, [rbp+hKey]; hKey
0x140063fae  test    rcx, rcx
0x140063fb1  jz      short loc_140063FBF
0x140063fb3  call    cs:__imp_RegCloseKey
0x140063fba  nop     dword ptr [rax+rax+00h]
0x140063fbf  mov     eax, ebx
0x140063fc1  mov     rbx, [rsp+70h+arg_0]
0x140063fc9  add     rsp, 70h
0x140063fcd  pop     r15
0x140063fcf  pop     r14
0x140063fd1  pop     r13
0x140063fd3  pop     r12
0x140063fd5  pop     rdi
0x140063fd6  pop     rsi
0x140063fd7  pop     rbp
0x140063fd8  retn
```
