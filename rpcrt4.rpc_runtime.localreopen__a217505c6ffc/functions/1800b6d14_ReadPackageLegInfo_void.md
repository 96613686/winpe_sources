# ReadPackageLegInfo(void)

- ea: `0x1800b6d14`
- end: `0x1800b701e`
- name: `?ReadPackageLegInfo@@YAHXZ`
- size: `778`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800a0c5c`

## callees

- `0x180023020`
- `0x180023a40`
- `0x18006d460`
- `0x1800a87e0`
- `0x1800aa300`
- `0x1800b6d14`
- `0x1800ceda0`
- `0x1800d7010`

## import_xrefs

- `ntdll!wcstoul` at `0x1800b6fb4`
- `ntdll!wcstoul` at `0x1800b6fb4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800b6d83`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800b6d83`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b6df3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b6f1c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b6df3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b6f1c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b6dc6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b6f0a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b6dc6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b6f0a`

## string_xrefs

- `0x1800b6d75`: `Software\Microsoft\Rpc\SecurityService`

## pseudocode

```c
__int64 ReadPackageLegInfo(void)
{
  unsigned int v1; // ebx
  char *pvData; // rdi
  LSTATUS ValueW; // eax
  __int64 v4; // rdx
  unsigned __int64 v5; // rbx
  unsigned __int64 v6; // rcx
  __int64 v7; // rcx
  unsigned __int64 v8; // rcx
  void *v9; // rsp
  void *v10; // rsp
  char *v11; // rax
  LSTATUS v12; // esi
  int v13; // esi
  char *v14; // rcx
  char *v15; // rdx
  int v16; // eax
  _DWORD *v17; // r15
  int v18; // r14d
  const wchar_t *i; // rcx
  wchar_t *v20; // rax
  __int64 v21; // rcx
  __int64 v22; // [rsp+0h] [rbp-40h] BYREF
  DWORD pcbData; // [rsp+40h] [rbp+0h] BYREF
  HKEY hkey; // [rsp+48h] [rbp+8h] BYREF
  wchar_t *EndPtr; // [rsp+50h] [rbp+10h] BYREF
  struct MUTEX *v26; // [rsp+58h] [rbp+18h] BYREF

  pcbData = 0;
  hkey = 0;
  v26 = 0;
  if ( FourLeggedPackages )
    return 1;
  InsureSecuritySupportLoaded(&v26);
  if ( !RegOpenKeyExA(HKEY_LOCAL_MACHINE, "Software\\Microsoft\\Rpc\\SecurityService", 0, 0x20019u, &hkey) )
  {
    pvData = 0;
    ValueW = RegGetValueW(hkey, 0, L"Four-legged packages", 0x20u, 0, 0, &pcbData);
    if ( ValueW == 2 )
    {
LABEL_6:
      v1 = 1;
LABEL_7:
      FourLeggedPackages = &NullPackageList;
      goto LABEL_8;
    }
    if ( ValueW )
      goto LABEL_15;
    if ( pcbData > 0xFA0 )
      goto LABEL_6;
    v5 = pcbData;
    if ( !pcbData )
      goto LABEL_49;
    if ( pcbData > (unsigned __int64)g_ulMaxStackAllocSize )
      goto LABEL_49;
    v6 = pcbData + g_ulAdditionalProbeSize + 8;
    if ( v6 < pcbData || !(unsigned int)VerifyStackAvailable(v6, v4) )
      goto LABEL_49;
    v7 = v5 + 23;
    if ( v5 + 23 <= v5 + 8 )
      v7 = 0xFFFFFFFFFFFFFF0LL;
    v8 = v7 & 0xFFFFFFFFFFFFFFF0uLL;
    v9 = alloca(v8);
    v10 = alloca(v8);
    pvData = (char *)&pcbData;
    if ( &v22 == (__int64 *)-64LL || (pcbData = 1801679955, (pvData = (char *)&hkey) == 0) )
    {
LABEL_49:
      if ( v5 + 8 >= v5 )
      {
        v11 = (char *)((__int64 (*)(void))g_pfnAllocate)();
        pvData = v11;
        if ( v11 )
        {
          *(_DWORD *)v11 = 1885431112;
          pvData = v11 + 8;
        }
      }
    }
    if ( !pvData )
      goto LABEL_15;
    v12 = RegGetValueW(hkey, 0, L"Four-legged packages", 0x20u, 0, pvData, &pcbData);
    RegCloseKey(hkey);
    hkey = 0;
    v1 = 1;
    if ( (unsigned int)(v12 - 1011) <= 1 )
      goto LABEL_7;
    if ( v12 )
    {
      v1 = 0;
LABEL_11:
      if ( *((_DWORD *)pvData - 2) == 1885431112 )
        ((void (*)(void))g_pfnFree)();
      return v1;
    }
    v13 = 0;
    v14 = pvData;
    v15 = &pvData[2 * pcbData];
    if ( pvData < v15 )
    {
      do
      {
        v16 = v13 + 1;
        if ( *(_WORD *)v14 )
          v16 = v13;
        v14 += 2;
        v13 = v16;
      }
      while ( v14 < v15 );
    }
    v17 = AllocWrapper(saturated_mul(v13, 4u));
    if ( v17 )
    {
      EndPtr = 0;
      v18 = 0;
      for ( i = (const wchar_t *)pvData; v18 < v13; i = v20 + 1 )
      {
        v17[v18] = wcstoul(i, &EndPtr, 10);
        v20 = EndPtr;
        if ( *EndPtr )
        {
          --v18;
          v21 = -1;
          do
            ++v21;
          while ( EndPtr[v21] );
          v20 = &EndPtr[v21];
          EndPtr = v20;
        }
        ++v18;
      }
      if ( FourLeggedPackages && FourLeggedPackages != &NullPackageList )
        FreeWrapper(FourLeggedPackages);
      FourLeggedPackages = v17;
    }
    else
    {
LABEL_15:
      v1 = 0;
    }
LABEL_8:
    if ( hkey )
      RegCloseKey(hkey);
    if ( !pvData )
      return v1;
    goto LABEL_11;
  }
  return 0;
}

```

## disassembly

```asm
0x1800b6d14  push    rbp
0x1800b6d16  push    rbx
0x1800b6d17  push    rsi
0x1800b6d18  push    rdi
0x1800b6d19  push    r12
0x1800b6d1b  push    r13
0x1800b6d1d  push    r14
0x1800b6d1f  push    r15
0x1800b6d21  sub     rsp, 78h
0x1800b6d25  lea     rbp, [rsp+40h]
0x1800b6d2a  mov     rax, cs:__security_cookie
0x1800b6d31  xor     rax, rbp
0x1800b6d34  mov     [rbp+70h+var_50], rax
0x1800b6d38  xor     r12d, r12d
0x1800b6d3b  cmp     cs:?FourLeggedPackages@@3PEAKEA, r12; ulong * FourLeggedPackages
0x1800b6d42  mov     [rbp+70h+var_70], r12d
0x1800b6d46  mov     [rbp+70h+hkey], r12
0x1800b6d4a  mov     [rbp+70h+var_58], r12
0x1800b6d4e  jz      short loc_1800B6D5A
0x1800b6d50  lea     eax, [r12+1]
0x1800b6d55  jmp     loc_1800B6E1E
0x1800b6d5a  lea     rcx, [rbp+70h+var_58]; struct MUTEX **
0x1800b6d5e  call    ?InsureSecuritySupportLoaded@@YAJPEAPEAVMUTEX@@@Z; InsureSecuritySupportLoaded(MUTEX * *)
0x1800b6d63  lea     rax, [rbp+70h+hkey]
0x1800b6d67  mov     r9d, 20019h; samDesired
0x1800b6d6d  xor     r8d, r8d; ulOptions
0x1800b6d70  mov     [rsp+0B0h+phkResult], rax; phkResult
0x1800b6d75  lea     rdx, SubKey; "Software\\Microsoft\\Rpc\\SecurityServi"...
0x1800b6d7c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800b6d83  call    cs:__imp_RegOpenKeyExA
0x1800b6d8a  nop     dword ptr [rax+rax+00h]
0x1800b6d8f  test    eax, eax
0x1800b6d91  jz      short loc_1800B6D9B
0x1800b6d93  mov     ebx, r12d
0x1800b6d96  jmp     loc_1800B6E1C
0x1800b6d9b  mov     rcx, [rbp+70h+hkey]; hkey
0x1800b6d9f  lea     rax, [rbp+70h+var_70]
0x1800b6da3  mov     [rsp+0B0h+pcbData], rax; pcbData
0x1800b6da8  lea     r8, aFourLeggedPack; "Four-legged packages"
0x1800b6daf  mov     esi, 20h ; ' '
0x1800b6db4  mov     [rsp+0B0h+pvData], r12; pvData
0x1800b6db9  mov     r9d, esi; dwFlags
0x1800b6dbc  mov     [rsp+0B0h+phkResult], r12; pdwType
0x1800b6dc1  xor     edx, edx; lpSubKey
0x1800b6dc3  mov     rdi, r12
0x1800b6dc6  call    cs:__imp_RegGetValueW
0x1800b6dcd  nop     dword ptr [rax+rax+00h]
0x1800b6dd2  cmp     eax, 2
0x1800b6dd5  jnz     short loc_1800B6E3C
0x1800b6dd7  mov     ebx, 1
0x1800b6ddc  lea     rax, ?NullPackageList@@3PAKA; ulong near * NullPackageList
0x1800b6de3  mov     cs:?FourLeggedPackages@@3PEAKEA, rax; ulong * FourLeggedPackages
0x1800b6dea  mov     rcx, [rbp+70h+hkey]; hKey
0x1800b6dee  test    rcx, rcx
0x1800b6df1  jz      short loc_1800B6DFF
0x1800b6df3  call    cs:__imp_RegCloseKey
0x1800b6dfa  nop     dword ptr [rax+rax+00h]
0x1800b6dff  test    rdi, rdi
0x1800b6e02  jz      short loc_1800B6E1C
0x1800b6e04  lea     rcx, [rdi-8]
0x1800b6e08  cmp     dword ptr [rcx], 70616548h
0x1800b6e0e  jnz     short loc_1800B6E1C
0x1800b6e10  mov     rax, cs:g_pfnFree
0x1800b6e17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6e1c  mov     eax, ebx
0x1800b6e1e  mov     rcx, [rbp+70h+var_50]
0x1800b6e22  xor     rcx, rbp; StackCookie
0x1800b6e25  call    __security_check_cookie
0x1800b6e2a  lea     rsp, [rbp+38h]
0x1800b6e2e  pop     r15
0x1800b6e30  pop     r14
0x1800b6e32  pop     r13
0x1800b6e34  pop     r12
0x1800b6e36  pop     rdi
0x1800b6e37  pop     rsi
0x1800b6e38  pop     rbx
0x1800b6e39  pop     rbp
0x1800b6e3a  retn
0x1800b6e3c  test    eax, eax
0x1800b6e3e  jz      short loc_1800B6E45
0x1800b6e40  mov     ebx, r12d
0x1800b6e43  jmp     short loc_1800B6DEA
0x1800b6e45  cmp     [rbp+70h+var_70], 0FA0h
0x1800b6e4c  ja      short loc_1800B6DD7
0x1800b6e4e  mov     ebx, [rbp+70h+var_70]
0x1800b6e51  test    rbx, rbx
0x1800b6e54  jz      short loc_1800B6EB7
0x1800b6e56  cmp     rbx, cs:g_ulMaxStackAllocSize
0x1800b6e5d  ja      short loc_1800B6EB7
0x1800b6e5f  mov     rcx, cs:g_ulAdditionalProbeSize
0x1800b6e66  add     rcx, 8
0x1800b6e6a  add     rcx, rbx
0x1800b6e6d  cmp     rcx, rbx
0x1800b6e70  jb      short loc_1800B6EB7
0x1800b6e72  call    VerifyStackAvailable
0x1800b6e77  test    eax, eax
0x1800b6e79  jz      short loc_1800B6EB7
0x1800b6e7b  lea     rax, [rbx+8]
0x1800b6e7f  lea     rcx, [rax+0Fh]
0x1800b6e83  cmp     rcx, rax
0x1800b6e86  ja      short loc_1800B6E92
0x1800b6e88  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800b6e92  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800b6e96  mov     rax, rcx
0x1800b6e99  call    __chkstk_0
0x1800b6e9e  sub     rsp, rcx
0x1800b6ea1  lea     rdi, [rsp+0B0h+var_70]
0x1800b6ea6  test    rdi, rdi
0x1800b6ea9  jz      short loc_1800B6EB7
0x1800b6eab  mov     dword ptr [rdi], 6B637453h
0x1800b6eb1  add     rdi, 8
0x1800b6eb5  jnz     short loc_1800B6EDE
0x1800b6eb7  lea     rcx, [rbx+8]
0x1800b6ebb  cmp     rcx, rbx
0x1800b6ebe  jb      short loc_1800B6EDE
0x1800b6ec0  mov     rax, cs:g_pfnAllocate
0x1800b6ec7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6ecc  mov     rdi, rax
0x1800b6ecf  test    rax, rax
0x1800b6ed2  jz      short loc_1800B6EDE
0x1800b6ed4  mov     dword ptr [rax], 70616548h
0x1800b6eda  add     rdi, 8
0x1800b6ede  test    rdi, rdi
0x1800b6ee1  jz      loc_1800B6E40
0x1800b6ee7  mov     rcx, [rbp+70h+hkey]; hkey
0x1800b6eeb  lea     rax, [rbp+70h+var_70]
0x1800b6eef  mov     [rsp+0B0h+pcbData], rax; pcbData
0x1800b6ef4  lea     r8, aFourLeggedPack; "Four-legged packages"
0x1800b6efb  mov     [rsp+0B0h+pvData], rdi; pvData
0x1800b6f00  mov     r9d, esi; dwFlags
0x1800b6f03  xor     edx, edx; lpSubKey
0x1800b6f05  mov     [rsp+0B0h+phkResult], r12; pdwType
0x1800b6f0a  call    cs:__imp_RegGetValueW
0x1800b6f11  nop     dword ptr [rax+rax+00h]
0x1800b6f16  mov     rcx, [rbp+70h+hkey]; hKey
0x1800b6f1a  mov     esi, eax
0x1800b6f1c  call    cs:__imp_RegCloseKey
0x1800b6f23  nop     dword ptr [rax+rax+00h]
0x1800b6f28  lea     ecx, [rsi-3F3h]
0x1800b6f2e  mov     [rbp+70h+hkey], r12
0x1800b6f32  mov     ebx, 1
0x1800b6f37  cmp     ecx, ebx
0x1800b6f39  jbe     loc_1800B6DDC
0x1800b6f3f  test    esi, esi
0x1800b6f41  jz      short loc_1800B6F4B
0x1800b6f43  mov     ebx, r12d
0x1800b6f46  jmp     loc_1800B6E04
0x1800b6f4b  mov     eax, [rbp+70h+var_70]
0x1800b6f4e  mov     esi, r12d
0x1800b6f51  mov     rcx, rdi
0x1800b6f54  lea     rdx, [rdi+rax*2]
0x1800b6f58  cmp     rdi, rdx
0x1800b6f5b  jnb     short loc_1800B6F72
0x1800b6f5d  cmp     [rcx], r12w
0x1800b6f61  lea     eax, [rsi+1]
0x1800b6f64  cmovnz  eax, esi
0x1800b6f67  add     rcx, 2
0x1800b6f6b  mov     esi, eax
0x1800b6f6d  cmp     rcx, rdx
0x1800b6f70  jb      short loc_1800B6F5D
0x1800b6f72  movsxd  rcx, esi
0x1800b6f75  mov     eax, 4
0x1800b6f7a  mul     rcx
0x1800b6f7d  mov     r13, 0FFFFFFFFFFFFFFFFh
0x1800b6f84  cmovb   rax, r13
0x1800b6f88  mov     rcx, rax; dwBytes
0x1800b6f8b  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x1800b6f90  mov     r15, rax
0x1800b6f93  test    rax, rax
0x1800b6f96  jz      loc_1800B6E40
0x1800b6f9c  mov     [rbp+70h+EndPtr], r12
0x1800b6fa0  mov     r14d, r12d
0x1800b6fa3  mov     rcx, rdi; String
0x1800b6fa6  test    esi, esi
0x1800b6fa8  jle     short loc_1800B6FF5
0x1800b6faa  mov     r8d, 0Ah; Radix
0x1800b6fb0  lea     rdx, [rbp+70h+EndPtr]; EndPtr
0x1800b6fb4  call    cs:__imp_wcstoul
0x1800b6fbb  nop     dword ptr [rax+rax+00h]
0x1800b6fc0  movsxd  rcx, r14d
0x1800b6fc3  mov     [r15+rcx*4], eax
0x1800b6fc7  mov     rax, [rbp+70h+EndPtr]
0x1800b6fcb  cmp     [rax], r12w
0x1800b6fcf  jz      short loc_1800B6FE9
0x1800b6fd1  sub     r14d, ebx
0x1800b6fd4  mov     rcx, r13
0x1800b6fd7  inc     rcx
0x1800b6fda  cmp     [rax+rcx*2], r12w
0x1800b6fdf  jnz     short loc_1800B6FD7
0x1800b6fe1  lea     rax, [rax+rcx*2]
0x1800b6fe5  mov     [rbp+70h+EndPtr], rax
0x1800b6fe9  add     r14d, ebx
0x1800b6fec  lea     rcx, [rax+2]
0x1800b6ff0  cmp     r14d, esi
0x1800b6ff3  jl      short loc_1800B6FAA
0x1800b6ff5  mov     rcx, cs:?FourLeggedPackages@@3PEAKEA; lpMem
0x1800b6ffc  test    rcx, rcx
0x1800b6fff  jz      short loc_1800B7012
0x1800b7001  lea     rax, ?NullPackageList@@3PAKA; ulong near * NullPackageList
0x1800b7008  cmp     rcx, rax
0x1800b700b  jz      short loc_1800B7012
0x1800b700d  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x1800b7012  mov     cs:?FourLeggedPackages@@3PEAKEA, r15; ulong * FourLeggedPackages
0x1800b7019  jmp     loc_1800B6DEA
```
