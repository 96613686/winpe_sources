# AddNewProvidor(HKEY__ *,_PROVIDOR_INFO_1W *)

- ea: `0x14005dfe4`
- end: `0x14005e32b`
- name: `?AddNewProvidor@@YAKPEAUHKEY__@@PEAU_PROVIDOR_INFO_1W@@@Z`
- size: `839`
- prototype: `unsigned int __fastcall(HKEY hKey, struct _PROVIDOR_INFO_1W *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x14005ead0`

## callees

- `0x1400041c0`
- `0x1400163ec`
- `0x14005dfe4`
- `0x140062f40`
- `0x140063090`
- `0x14006533c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14005e2ce`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14005e2e5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14005e2fc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14005e2ce`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14005e2e5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14005e2fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005e058`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005e058`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x14005e2b5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x14005e2b5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x14005e280`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x14005e280`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14005e0cc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14005e0cc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14005e154`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14005e1a9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14005e154`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14005e1a9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14005e113`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14005e1f6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14005e2ad`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14005e113`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14005e1f6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14005e2ad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005e127`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005e30b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005e127`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005e30b`
- `KERNELBASE!lstrcmpiW` at `0x14005e07f`
- `KERNELBASE!lstrcmpiW` at `0x14005e07f`

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
0x14005dfe4  mov     [rsp-38h+arg_0], rbx
0x14005dfe9  push    rbp
0x14005dfea  push    rsi
0x14005dfeb  push    rdi
0x14005dfec  push    r12
0x14005dfee  push    r13
0x14005dff0  push    r14
0x14005dff2  push    r15
0x14005dff4  mov     rbp, rsp
0x14005dff7  sub     rsp, 70h
0x14005dffb  xor     ebx, ebx
0x14005dffd  mov     r14, rcx
0x14005e000  mov     rcx, [rdx]
0x14005e003  mov     rsi, rdx
0x14005e006  mov     [rbp+var_20], ebx
0x14005e009  mov     r13d, ebx
0x14005e00c  mov     [rbp+cbData], ebx
0x14005e00f  mov     edi, ebx
0x14005e011  mov     [rbp+arg_10], ebx
0x14005e014  mov     r12d, ebx
0x14005e017  mov     [rbp+dwDisposition], ebx
0x14005e01a  mov     [rbp+hKey], rbx
0x14005e01e  test    rcx, rcx
0x14005e021  jz      loc_14005E257
0x14005e027  mov     rax, [rdx+10h]
0x14005e02b  test    rax, rax
0x14005e02e  jz      loc_14005E257
0x14005e034  cmp     [rcx], bx
0x14005e037  jz      loc_14005E257
0x14005e03d  cmp     [rax], bx
0x14005e040  jz      loc_14005E257
0x14005e046  mov     ecx, 26Ah; dwBytes
0x14005e04b  call    DllAllocSplMem
0x14005e050  mov     r15, rax
0x14005e053  test    rax, rax
0x14005e056  jnz     short loc_14005E065
0x14005e058  call    cs:__imp_GetLastError
0x14005e05e  mov     ebx, eax
0x14005e060  jmp     loc_14005E25F
0x14005e065  mov     [rbp+var_10], rbx
0x14005e069  xor     ecx, ecx
0x14005e06b  mov     rbx, cs:?pLocalProvidor@@3PEAU_PROVIDOR@@EA; _PROVIDOR * pLocalProvidor
0x14005e072  test    rbx, rbx
0x14005e075  jz      short loc_14005E09D
0x14005e077  mov     rdx, [rsi+10h]; lpString2
0x14005e07b  mov     rcx, [rbx+8]; lpString1
0x14005e07f  call    cs:__imp_lstrcmpiW
0x14005e085  xor     ecx, ecx
0x14005e087  test    eax, eax
0x14005e089  jz      short loc_14005E094
0x14005e08b  mov     [rbp+var_10], rbx
0x14005e08f  mov     rbx, [rbx]
0x14005e092  jmp     short loc_14005E072
0x14005e094  xor     esi, esi
0x14005e096  mov     ebx, esi
0x14005e098  jmp     loc_14005E2F0
0x14005e09d  mov     rdx, [rsi]; lpSubKey
0x14005e0a0  lea     rax, [rbp+dwDisposition]
0x14005e0a4  mov     [rsp+70h+lpdwDisposition], rax; lpdwDisposition
0x14005e0a9  xor     r9d, r9d; lpClass
0x14005e0ac  lea     rax, [rbp+hKey]
0x14005e0b0  xor     r8d, r8d; Reserved
0x14005e0b3  mov     [rsp+70h+phkResult], rax; phkResult
0x14005e0b8  mov     [rsp+70h+lpSecurityAttributes], rcx; lpSecurityAttributes
0x14005e0bd  mov     [rsp+70h+samDesired], 3001Fh; samDesired
0x14005e0c5  mov     [rsp+70h+dwOptions], ecx; dwOptions
0x14005e0c9  mov     rcx, r14; hKey
0x14005e0cc  call    cs:__imp_RegCreateKeyExW
0x14005e0d2  xor     edx, edx
0x14005e0d4  mov     ebx, eax
0x14005e0d6  test    eax, eax
0x14005e0d8  jnz     loc_14005E25F
0x14005e0de  mov     rcx, [rsi+10h]
0x14005e0e2  or      rax, 0FFFFFFFFFFFFFFFFh
0x14005e0e6  inc     rax
0x14005e0e9  cmp     [rcx+rax*2], dx
0x14005e0ed  jnz     short loc_14005E0E6
0x14005e0ef  lea     eax, ds:2[rax*2]
0x14005e0f6  mov     r9d, 1; dwType
0x14005e0fc  mov     [rsp+70h+samDesired], eax; cbData
0x14005e100  lea     rdx, aName; "Name"
0x14005e107  mov     qword ptr [rsp+70h+dwOptions], rcx; lpData
0x14005e10c  xor     r8d, r8d; Reserved
0x14005e10f  mov     rcx, [rbp+hKey]; hKey
0x14005e113  call    cs:__imp_RegSetValueExW
0x14005e119  mov     ebx, eax
0x14005e11b  test    eax, eax
0x14005e11d  jnz     loc_14005E25F
0x14005e123  mov     rcx, [rbp+hKey]; hKey
0x14005e127  call    cs:__imp_RegCloseKey
0x14005e12d  xor     ecx, ecx
0x14005e12f  lea     rax, [rbp+cbData]
0x14005e133  mov     qword ptr [rsp+70h+samDesired], rax; lpcbData
0x14005e138  lea     rdx, szOrder; "Order"
0x14005e13f  mov     qword ptr [rsp+70h+dwOptions], rcx; lpData
0x14005e144  xor     r9d, r9d; lpType
0x14005e147  mov     [rbp+hKey], rcx
0x14005e14b  xor     r8d, r8d; lpReserved
0x14005e14e  mov     [rbp+cbData], ecx
0x14005e151  mov     rcx, r14; hKey
0x14005e154  call    cs:__imp_RegQueryValueExW
0x14005e15a  mov     ebx, eax
0x14005e15c  test    eax, eax
0x14005e15e  jz      short loc_14005E16A
0x14005e160  cmp     eax, 2
0x14005e163  jz      short loc_14005E1B9
0x14005e165  jmp     loc_14005E25F
0x14005e16a  mov     r13d, [rbp+cbData]
0x14005e16e  test    r13d, r13d
0x14005e171  jz      loc_14005E058
0x14005e177  mov     ecx, r13d; dwBytes
0x14005e17a  call    DllAllocSplMem
0x14005e17f  mov     rdi, rax
0x14005e182  test    rax, rax
0x14005e185  jz      loc_14005E058
0x14005e18b  lea     rax, [rbp+cbData]
0x14005e18f  xor     r9d, r9d; lpType
0x14005e192  mov     qword ptr [rsp+70h+samDesired], rax; lpcbData
0x14005e197  lea     rdx, szOrder; "Order"
0x14005e19e  xor     r8d, r8d; lpReserved
0x14005e1a1  mov     qword ptr [rsp+70h+dwOptions], rdi; lpData
0x14005e1a6  mov     rcx, r14; hKey
0x14005e1a9  call    cs:__imp_RegQueryValueExW
0x14005e1af  mov     ebx, eax
0x14005e1b1  test    eax, eax
0x14005e1b3  jnz     loc_14005E25F
0x14005e1b9  mov     r8, [rsi]; unsigned __int16 *
0x14005e1bc  lea     r9, [rbp+arg_10]; unsigned int *
0x14005e1c0  mov     edx, [rbp+cbData]; unsigned int
0x14005e1c3  mov     rcx, rdi; unsigned __int16 *
0x14005e1c6  call    ?AppendOrderEntry@@YAPEAGPEAGK0PEAK@Z; AppendOrderEntry(ushort *,ulong,ushort *,ulong *)
0x14005e1cb  mov     r12, rax
0x14005e1ce  test    rax, rax
0x14005e1d1  jz      loc_14005E25F
0x14005e1d7  mov     ecx, [rbp+arg_10]
0x14005e1da  lea     rdx, szOrder; "Order"
0x14005e1e1  mov     [rsp+70h+samDesired], ecx; cbData
0x14005e1e5  mov     r9d, 7; dwType
0x14005e1eb  mov     rcx, r14; hKey
0x14005e1ee  mov     qword ptr [rsp+70h+dwOptions], rax; lpData
0x14005e1f3  xor     r8d, r8d; Reserved
0x14005e1f6  call    cs:__imp_RegSetValueExW
0x14005e1fc  mov     [rbp+arg_10], eax
0x14005e1ff  mov     ebx, eax
0x14005e201  test    eax, eax
0x14005e203  jnz     short loc_14005E25F
0x14005e205  mov     rax, [rsi]
0x14005e208  lea     r9, szRegistryProvidors; "System\\CurrentControlSet\\Control\\Pri"...
0x14005e20f  lea     r8, aWsWs; "%ws\\%ws"
0x14005e216  mov     qword ptr [rsp+70h+dwOptions], rax
0x14005e21b  mov     edx, 135h; unsigned __int64
0x14005e220  mov     [rbp+var_20], 1
0x14005e227  mov     rcx, r15; unsigned __int16 *
0x14005e22a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14005e22f  mov     rcx, [rsi+10h]; unsigned __int16 *
0x14005e233  lea     r8, [rbp+arg_10]; unsigned int *
0x14005e237  mov     rdx, r15; unsigned __int16 *
0x14005e23a  call    ?InitializeProvidor@@YAPEAU_PROVIDOR@@PEAG0PEAK@Z; InitializeProvidor(ushort *,ushort *,ulong *)
0x14005e23f  mov     ebx, [rbp+arg_10]
0x14005e242  test    rax, rax
0x14005e245  jz      short loc_14005E25F
0x14005e247  mov     rcx, [rbp+var_10]
0x14005e24b  mov     qword ptr [rax], 0
0x14005e252  mov     [rcx], rax
0x14005e255  jmp     short loc_14005E25F
0x14005e257  mov     r15, rbx
0x14005e25a  mov     ebx, 57h ; 'W'
0x14005e25f  test    ebx, ebx
0x14005e261  jz      short loc_14005E2BD
0x14005e263  cmp     [rbp+dwDisposition], 1
0x14005e267  jnz     short loc_14005E286
0x14005e269  mov     rdx, [rsi]; lpSubKey
0x14005e26c  mov     rcx, r14; hKey
0x14005e26f  call    ?DeleteSubKeyTree@@YAHPEAUHKEY__@@PEAG@Z; DeleteSubKeyTree(HKEY__ *,ushort *)
0x14005e274  mov     rdx, [rsi]; lpSubKey
0x14005e277  xor     r9d, r9d; Reserved
0x14005e27a  xor     r8d, r8d; samDesired
0x14005e27d  mov     rcx, r14; hKey
0x14005e280  call    cs:__imp_RegDeleteKeyExW
0x14005e286  xor     esi, esi
0x14005e288  cmp     [rbp+var_20], esi
0x14005e28b  jz      short loc_14005E2BD
0x14005e28d  lea     rdx, szOrder; "Order"
0x14005e294  mov     rcx, r14; hKey
0x14005e297  test    rdi, rdi
0x14005e29a  jz      short loc_14005E2B5
0x14005e29c  mov     [rsp+70h+samDesired], r13d; cbData
0x14005e2a1  lea     r9d, [rsi+7]; dwType
0x14005e2a5  xor     r8d, r8d; Reserved
0x14005e2a8  mov     qword ptr [rsp+70h+dwOptions], rdi; lpData
0x14005e2ad  call    cs:__imp_RegSetValueExW
0x14005e2b3  jmp     short loc_14005E2C2
0x14005e2b5  call    cs:__imp_RegDeleteValueW
0x14005e2bb  jmp     short loc_14005E2D4
0x14005e2bd  test    rdi, rdi
0x14005e2c0  jz      short loc_14005E2D4
0x14005e2c2  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x14005e2c9  mov     r8, rdi; lpMem
0x14005e2cc  xor     edx, edx; dwFlags
0x14005e2ce  call    cs:__imp_HeapFree
0x14005e2d4  test    r12, r12
0x14005e2d7  jz      short loc_14005E2EB
0x14005e2d9  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x14005e2e0  mov     r8, r12; lpMem
0x14005e2e3  xor     edx, edx; dwFlags
0x14005e2e5  call    cs:__imp_HeapFree
0x14005e2eb  test    r15, r15
0x14005e2ee  jz      short loc_14005E302
0x14005e2f0  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x14005e2f7  mov     r8, r15; lpMem
0x14005e2fa  xor     edx, edx; dwFlags
0x14005e2fc  call    cs:__imp_HeapFree
0x14005e302  mov     rcx, [rbp+hKey]; hKey
0x14005e306  test    rcx, rcx
0x14005e309  jz      short loc_14005E311
0x14005e30b  call    cs:__imp_RegCloseKey
0x14005e311  mov     eax, ebx
0x14005e313  mov     rbx, [rsp+70h+arg_0]
0x14005e31b  add     rsp, 70h
0x14005e31f  pop     r15
0x14005e321  pop     r14
0x14005e323  pop     r13
0x14005e325  pop     r12
0x14005e327  pop     rdi
0x14005e328  pop     rsi
0x14005e329  pop     rbp
0x14005e32a  retn
```
