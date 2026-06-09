# I_RpcGetPortAllocationData

- ea: `0x1800b5f00`
- end: `0x1800b64da`
- name: `I_RpcGetPortAllocationData`
- size: `1498`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180023020`
- `0x180023a40`
- `0x18006d460`
- `0x1800aa300`
- `0x1800b5f00`
- `0x1800ceda0`
- `0x1800d7010`

## import_xrefs

- `ntdll!wcschr` at `0x1800b6356`
- `ntdll!wcschr` at `0x1800b6356`
- `ntdll!wcstol` at `0x1800b6200`
- `ntdll!wcstol` at `0x1800b623c`
- `ntdll!wcstol` at `0x1800b6200`
- `ntdll!wcstol` at `0x1800b623c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b5f68`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b5f68`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b6180`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b64b0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b6180`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b64b0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b5fb6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b6034`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b6162`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b5fb6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b6034`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b6162`

## pseudocode

```c
void __fastcall I_RpcGetPortAllocationData(__int64 a1)
{
  _WORD *v1; // r12
  __int64 v3; // rdi
  int v4; // eax
  __int64 v5; // rdx
  __int16 v6; // cx
  const wchar_t *v7; // r13
  unsigned __int64 v8; // rsi
  DWORD *p_pcbData; // rdi
  unsigned __int64 v10; // rcx
  __int64 v11; // rcx
  unsigned __int64 v12; // rcx
  void *v13; // rsp
  void *v14; // rsp
  DWORD *v15; // rax
  HKEY v16; // rcx
  LSTATUS ValueW; // r14d
  _WORD *v18; // rsi
  _WORD *v19; // rdx
  __int64 v20; // r8
  unsigned int v21; // eax
  int v22; // eax
  __int16 v23; // r12
  _WORD *v24; // rax
  _QWORD *v25; // rcx
  _WORD *v26; // r12
  int v27; // r11d
  unsigned __int16 *v28; // r8
  unsigned int v29; // r9d
  unsigned __int16 v30; // r10
  unsigned __int16 v31; // ax
  _QWORD *v32; // r13
  unsigned int v33; // edi
  _WORD *v34; // rax
  __int16 v35; // cx
  int v36; // edi
  _WORD *v37; // rax
  _QWORD *v38; // rcx
  _QWORD *v39; // rcx
  __int64 v40; // [rsp+0h] [rbp-40h] BYREF
  DWORD pcbData; // [rsp+40h] [rbp+0h] BYREF
  int pvData; // [rsp+44h] [rbp+4h] BYREF
  _QWORD *v43; // [rsp+48h] [rbp+8h] BYREF
  HKEY hkey; // [rsp+50h] [rbp+10h] BYREF
  wchar_t *EndPtr; // [rsp+58h] [rbp+18h] BYREF

  v1 = 0;
  *(_DWORD *)(a1 + 8) = 3;
  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  hkey = 0;
  pcbData = 0;
  pvData = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Rpc\\Internet", 0, 0x20019u, &hkey) )
  {
    *(_DWORD *)a1 = 1;
    return;
  }
  pcbData = 4;
  if ( RegGetValueW(hkey, 0, L"UseInternetPorts", 2u, 0, &pvData, &pcbData) )
    goto LABEL_109;
  v3 = 0x80100000001LL;
  if ( (_WORD)pvData == 89 )
    goto LABEL_8;
  if ( (unsigned __int16)(pvData - 78) > 0x2Bu || !_bittest64(&v3, (unsigned __int16)(pvData - 78)) )
    goto LABEL_109;
  v4 = 2;
  if ( (_WORD)pvData == 121 )
LABEL_8:
    v4 = 1;
  *(_DWORD *)(a1 + 8) = v4;
  pcbData = 4;
  if ( !RegGetValueW(hkey, 0, L"PortsInternetAvailable", 2u, 0, &pvData, &pcbData) )
  {
    v6 = pvData;
    if ( (_WORD)pvData == 89 )
    {
LABEL_14:
      pvData = 1;
LABEL_15:
      pcbData = 1;
      v7 = 0;
      while ( 1 )
      {
        if ( v7 && *((_DWORD *)v7 - 2) == 1885431112 )
          ((void (*)(void))g_pfnFree)();
        v8 = pcbData;
        p_pcbData = 0;
        if ( !pcbData )
          goto LABEL_113;
        if ( pcbData > (unsigned __int64)g_ulMaxStackAllocSize )
          goto LABEL_113;
        v10 = pcbData + g_ulAdditionalProbeSize + 8;
        if ( v10 < pcbData || !(unsigned int)VerifyStackAvailable(v10, v5) )
          goto LABEL_113;
        v11 = v8 + 23;
        if ( v8 + 23 <= v8 + 8 )
          v11 = 0xFFFFFFFFFFFFFF0LL;
        v12 = v11 & 0xFFFFFFFFFFFFFFF0uLL;
        v13 = alloca(v12);
        v14 = alloca(v12);
        p_pcbData = &pcbData;
        if ( &v40 == (__int64 *)-64LL || (pcbData = 1801679955, (p_pcbData = (DWORD *)&v43) == 0) )
        {
LABEL_113:
          if ( v8 + 8 >= v8 )
          {
            v15 = (DWORD *)((__int64 (*)(void))g_pfnAllocate)();
            p_pcbData = v15;
            if ( v15 )
            {
              *v15 = 1885431112;
              p_pcbData = v15 + 2;
            }
          }
        }
        v16 = hkey;
        if ( !p_pcbData )
          goto LABEL_110;
        v7 = (const wchar_t *)p_pcbData;
        ValueW = RegGetValueW(hkey, 0, L"Ports", 0x20u, 0, p_pcbData, &pcbData);
        if ( ValueW != 234 )
        {
          RegCloseKey(hkey);
          if ( ValueW )
          {
            if ( *(p_pcbData - 2) == 1885431112 )
              ((void (*)(void))g_pfnFree)();
          }
          else
          {
            v18 = 0;
            v19 = (_WORD *)(pcbData >> 1);
            v20 = 87;
            if ( (unsigned int)v19 < 2
              || *((_WORD *)p_pcbData + (unsigned int)((_DWORD)v19 - 1))
              || *((_WORD *)p_pcbData + (unsigned int)((_DWORD)v19 - 2)) )
            {
              ValueW = 87;
            }
            else
            {
              while ( *v7 )
              {
                EndPtr = 0;
                v21 = wcstol(v7, &EndPtr, 10);
                LODWORD(v43) = v21;
                if ( v21 > 0xFFFF )
                  goto LABEL_78;
                if ( *EndPtr )
                {
                  if ( *EndPtr != 45 )
                  {
LABEL_78:
                    ValueW = 87;
                    break;
                  }
                  v22 = wcstol(EndPtr + 1, &EndPtr, 10);
                  v23 = v22;
                  if ( (unsigned int)v22 > 0xFFFF || v22 < (int)v43 )
                  {
                    v1 = 0;
                    ValueW = 87;
                    break;
                  }
                }
                else
                {
                  v23 = v21;
                }
                v24 = AllocWrapper(0x10u);
                v19 = v24;
                if ( !v24 )
                {
                  ValueW = 14;
                  v1 = 0;
                  break;
                }
                *(_QWORD *)v24 = 0;
                v24[5] = (_WORD)v43;
                v24[4] = v23;
LABEL_49:
                v25 = 0;
                v26 = v18;
                v43 = 0;
                while ( 1 )
                {
                  if ( !v18 )
                  {
                    v18 = v19;
                    goto LABEL_70;
                  }
                  v27 = (unsigned __int16)v26[4];
                  v28 = v26 + 5;
                  v29 = (unsigned __int16)v19[5];
                  if ( v29 <= v27 + 1 )
                  {
                    v30 = *v28;
                    if ( (unsigned __int16)v19[4] >= *v28 - 1 )
                    {
                      if ( (unsigned __int16)v29 < v30 )
                        v30 = v19[5];
                      *v28 = v30;
                      v31 = v19[4];
                      if ( (unsigned __int16)v27 > v31 )
                        v31 = v27;
                      v26[4] = v31;
                      FreeWrapper(v19);
                      v19 = v26;
                      if ( v43 )
                        *v43 = *(_QWORD *)v26;
                      if ( v18 == v26 )
                        v18 = *(_WORD **)v18;
                      goto LABEL_49;
                    }
                    v25 = v43;
                  }
                  if ( (unsigned __int16)v29 < *v28 )
                    break;
                  v25 = v26;
                  v26 = *(_WORD **)v26;
                  v43 = v25;
                  if ( !v26 )
                  {
                    *v25 = v19;
                    goto LABEL_70;
                  }
                }
                if ( v25 )
                  *v25 = v19;
                else
                  v18 = v19;
                *(_QWORD *)v19 = v26;
LABEL_70:
                v1 = 0;
                v7 = wcschr(v7, 0) + 1;
              }
            }
            if ( *(p_pcbData - 2) == 1885431112 )
              ((void (__fastcall *)(DWORD *, _WORD *, __int64))g_pfnFree)(p_pcbData - 2, v19, v20);
            if ( !v18 )
              ValueW = 87;
            if ( pvData == 1 )
              *(_QWORD *)(a1 + 16) = v18;
            else
              *(_QWORD *)(a1 + 24) = v18;
            if ( ValueW )
              goto LABEL_114;
            v32 = 0;
            v33 = 1025;
            while ( v18 )
            {
              LODWORD(v43) = (unsigned __int16)v18[5];
              if ( v33 < (unsigned int)v43 )
              {
                v34 = AllocWrapper(0x10u);
                if ( !v34 )
                  goto LABEL_97;
                v35 = (_WORD)v43 - 1;
                *(_QWORD *)v34 = 0;
                v34[5] = v33;
                v34[4] = v35;
                if ( v1 )
                  *v32 = v34;
                else
                  v1 = v34;
                v32 = v34;
              }
              v36 = (unsigned __int16)v18[4];
              v18 = *(_WORD **)v18;
              v33 = v36 + 1;
              if ( v33 < 0x401 )
                v33 = 1025;
            }
            if ( v33 >= 0xFFFF )
              goto LABEL_98;
            v37 = AllocWrapper(0x10u);
            if ( !v37 )
            {
LABEL_97:
              ValueW = 14;
              goto LABEL_98;
            }
            v37[5] = v33;
            v37[4] = -1;
            *(_QWORD *)v37 = 0;
            if ( v32 )
              *v32 = v37;
            else
              v1 = v37;
LABEL_98:
            if ( pvData == 1 )
              *(_QWORD *)(a1 + 24) = v1;
            else
              *(_QWORD *)(a1 + 16) = v1;
            if ( ValueW )
            {
LABEL_114:
              while ( 1 )
              {
                v38 = *(_QWORD **)(a1 + 16);
                if ( !v38 )
                  break;
                *(_QWORD *)(a1 + 16) = *v38;
                FreeWrapper(v38);
              }
              while ( 1 )
              {
                v39 = *(_QWORD **)(a1 + 24);
                if ( !v39 )
                  break;
                *(_QWORD *)(a1 + 24) = *v39;
                FreeWrapper(v39);
              }
            }
            else
            {
              *(_DWORD *)a1 = 1;
              *(_DWORD *)(a1 + 4) = 1;
            }
          }
          return;
        }
      }
    }
    if ( (unsigned __int16)(pvData - 78) <= 0x2Bu && _bittest64(&v3, (unsigned __int16)(pvData - 78)) )
    {
      pvData = 2;
      if ( v6 != 121 )
        goto LABEL_15;
      goto LABEL_14;
    }
  }
LABEL_109:
  v16 = hkey;
LABEL_110:
  RegCloseKey(v16);
}

```

## disassembly

```asm
0x1800b5f00  push    rbp
0x1800b5f02  push    rbx
0x1800b5f03  push    rsi
0x1800b5f04  push    rdi
0x1800b5f05  push    r12
0x1800b5f07  push    r13
0x1800b5f09  push    r14
0x1800b5f0b  push    r15
0x1800b5f0d  sub     rsp, 78h
0x1800b5f11  lea     rbp, [rsp+40h]
0x1800b5f16  mov     rax, cs:__security_cookie
0x1800b5f1d  xor     rax, rbp
0x1800b5f20  mov     [rbp+70h+var_50], rax
0x1800b5f24  xor     r12d, r12d
0x1800b5f27  mov     dword ptr [rcx+8], 3
0x1800b5f2e  mov     [rcx], r12
0x1800b5f31  lea     rax, [rbp+70h+hkey]
0x1800b5f35  mov     [rcx+10h], r12
0x1800b5f39  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Rpc\\Internet"
0x1800b5f40  mov     [rcx+18h], r12
0x1800b5f44  mov     rbx, rcx
0x1800b5f47  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800b5f4e  mov     [rbp+70h+hkey], r12
0x1800b5f52  mov     r9d, 20019h; samDesired
0x1800b5f58  mov     [rbp+70h+var_70], r12d
0x1800b5f5c  xor     r8d, r8d; ulOptions
0x1800b5f5f  mov     [rbp+70h+var_6C], r12d
0x1800b5f63  mov     [rsp+0B0h+phkResult], rax; phkResult
0x1800b5f68  call    cs:__imp_RegOpenKeyExW
0x1800b5f6f  nop     dword ptr [rax+rax+00h]
0x1800b5f74  test    eax, eax
0x1800b5f76  jz      short loc_1800B5F83
0x1800b5f78  mov     dword ptr [rbx], 1
0x1800b5f7e  jmp     loc_1800B64BC
0x1800b5f83  mov     rcx, [rbp+70h+hkey]; hkey
0x1800b5f87  lea     rax, [rbp+70h+var_70]
0x1800b5f8b  mov     [rsp+0B0h+pcbData], rax; pcbData
0x1800b5f90  lea     r8, aUseinternetpor; "UseInternetPorts"
0x1800b5f97  mov     esi, 4
0x1800b5f9c  lea     rax, [rbp+70h+var_6C]
0x1800b5fa0  mov     [rsp+0B0h+pvData], rax; pvData
0x1800b5fa5  xor     edx, edx; lpSubKey
0x1800b5fa7  mov     [rbp+70h+var_70], esi
0x1800b5faa  mov     [rsp+0B0h+phkResult], r12; pdwType
0x1800b5faf  lea     r14d, [rsi-2]
0x1800b5fb3  mov     r9d, r14d; dwFlags
0x1800b5fb6  call    cs:__imp_RegGetValueW
0x1800b5fbd  nop     dword ptr [rax+rax+00h]
0x1800b5fc2  test    eax, eax
0x1800b5fc4  jnz     loc_1800B64AC
0x1800b5fca  mov     ecx, [rbp+70h+var_6C]
0x1800b5fcd  lea     r15d, [rsi-3]
0x1800b5fd1  mov     rdi, 80100000001h
0x1800b5fdb  cmp     cx, 59h ; 'Y'
0x1800b5fdf  jz      short loc_1800B6004
0x1800b5fe1  lea     eax, [rcx-4Eh]
0x1800b5fe4  cmp     ax, 2Bh ; '+'
0x1800b5fe8  ja      loc_1800B64AC
0x1800b5fee  movzx   eax, ax
0x1800b5ff1  bt      rdi, rax
0x1800b5ff5  jnb     loc_1800B64AC
0x1800b5ffb  mov     eax, r14d
0x1800b5ffe  cmp     cx, 79h ; 'y'
0x1800b6002  jnz     short loc_1800B6007
0x1800b6004  mov     eax, r15d
0x1800b6007  mov     [rbx+8], eax
0x1800b600a  lea     r8, aPortsinterneta; "PortsInternetAvailable"
0x1800b6011  mov     rcx, [rbp+70h+hkey]; hkey
0x1800b6015  lea     rax, [rbp+70h+var_70]
0x1800b6019  mov     [rsp+0B0h+pcbData], rax; pcbData
0x1800b601e  mov     r9d, r14d; dwFlags
0x1800b6021  lea     rax, [rbp+70h+var_6C]
0x1800b6025  mov     [rbp+70h+var_70], esi
0x1800b6028  mov     [rsp+0B0h+pvData], rax; pvData
0x1800b602d  xor     edx, edx; lpSubKey
0x1800b602f  mov     [rsp+0B0h+phkResult], r12; pdwType
0x1800b6034  call    cs:__imp_RegGetValueW
0x1800b603b  nop     dword ptr [rax+rax+00h]
0x1800b6040  test    eax, eax
0x1800b6042  jnz     loc_1800B64AC
0x1800b6048  mov     ecx, [rbp+70h+var_6C]
0x1800b604b  cmp     cx, 59h ; 'Y'
0x1800b604f  jz      short loc_1800B6075
0x1800b6051  lea     eax, [rcx-4Eh]
0x1800b6054  cmp     ax, 2Bh ; '+'
0x1800b6058  ja      loc_1800B64AC
0x1800b605e  movzx   eax, ax
0x1800b6061  bt      rdi, rax
0x1800b6065  jnb     loc_1800B64AC
0x1800b606b  mov     [rbp+70h+var_6C], r14d
0x1800b606f  cmp     cx, 79h ; 'y'
0x1800b6073  jnz     short loc_1800B6079
0x1800b6075  mov     [rbp+70h+var_6C], r15d
0x1800b6079  mov     [rbp+70h+var_70], r15d
0x1800b607d  mov     r13, r12
0x1800b6080  test    r13, r13
0x1800b6083  jz      short loc_1800B609D
0x1800b6085  lea     rcx, [r13-8]
0x1800b6089  cmp     dword ptr [rcx], 70616548h
0x1800b608f  jnz     short loc_1800B609D
0x1800b6091  mov     rax, cs:g_pfnFree
0x1800b6098  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b609d  mov     esi, [rbp+70h+var_70]
0x1800b60a0  mov     rdi, r12
0x1800b60a3  test    rsi, rsi
0x1800b60a6  jz      short loc_1800B6109
0x1800b60a8  cmp     rsi, cs:g_ulMaxStackAllocSize
0x1800b60af  ja      short loc_1800B6109
0x1800b60b1  mov     rcx, cs:g_ulAdditionalProbeSize
0x1800b60b8  add     rcx, 8
0x1800b60bc  add     rcx, rsi
0x1800b60bf  cmp     rcx, rsi
0x1800b60c2  jb      short loc_1800B6109
0x1800b60c4  call    VerifyStackAvailable
0x1800b60c9  test    eax, eax
0x1800b60cb  jz      short loc_1800B6109
0x1800b60cd  lea     rax, [rsi+8]
0x1800b60d1  lea     rcx, [rax+0Fh]
0x1800b60d5  cmp     rcx, rax
0x1800b60d8  ja      short loc_1800B60E4
0x1800b60da  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800b60e4  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800b60e8  mov     rax, rcx
0x1800b60eb  call    __chkstk_0
0x1800b60f0  sub     rsp, rcx
0x1800b60f3  lea     rdi, [rsp+0B0h+var_70]
0x1800b60f8  test    rdi, rdi
0x1800b60fb  jz      short loc_1800B6109
0x1800b60fd  mov     dword ptr [rdi], 6B637453h
0x1800b6103  add     rdi, 8
0x1800b6107  jnz     short loc_1800B6130
0x1800b6109  lea     rcx, [rsi+8]
0x1800b610d  cmp     rcx, rsi
0x1800b6110  jb      short loc_1800B6130
0x1800b6112  mov     rax, cs:g_pfnAllocate
0x1800b6119  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b611e  mov     rdi, rax
0x1800b6121  test    rax, rax
0x1800b6124  jz      short loc_1800B6130
0x1800b6126  mov     dword ptr [rax], 70616548h
0x1800b612c  add     rdi, 8
0x1800b6130  mov     rcx, [rbp+70h+hkey]; hkey
0x1800b6134  test    rdi, rdi
0x1800b6137  jz      loc_1800B64B0
0x1800b613d  lea     rax, [rbp+70h+var_70]
0x1800b6141  mov     r9d, 20h ; ' '; dwFlags
0x1800b6147  mov     [rsp+0B0h+pcbData], rax; pcbData
0x1800b614c  lea     r8, aPorts; "Ports"
0x1800b6153  mov     [rsp+0B0h+pvData], rdi; pvData
0x1800b6158  xor     edx, edx; lpSubKey
0x1800b615a  mov     [rsp+0B0h+phkResult], r12; pdwType
0x1800b615f  mov     r13, rdi
0x1800b6162  call    cs:__imp_RegGetValueW
0x1800b6169  nop     dword ptr [rax+rax+00h]
0x1800b616e  mov     r14d, eax
0x1800b6171  cmp     eax, 0EAh
0x1800b6176  jz      loc_1800B6080
0x1800b617c  mov     rcx, [rbp+70h+hkey]; hKey
0x1800b6180  call    cs:__imp_RegCloseKey
0x1800b6187  nop     dword ptr [rax+rax+00h]
0x1800b618c  test    r14d, r14d
0x1800b618f  jz      short loc_1800B61B2
0x1800b6191  lea     rcx, [rdi-8]
0x1800b6195  cmp     dword ptr [rcx], 70616548h
0x1800b619b  jnz     loc_1800B64BC
0x1800b61a1  mov     rax, cs:g_pfnFree
0x1800b61a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b61ad  jmp     loc_1800B64BC
0x1800b61b2  mov     edx, [rbp+70h+var_70]
0x1800b61b5  mov     rsi, r12
0x1800b61b8  shr     edx, 1
0x1800b61ba  mov     r8d, 57h ; 'W'
0x1800b61c0  cmp     edx, 2
0x1800b61c3  jnb     short loc_1800B61D0
0x1800b61c5  mov     r14d, r8d
0x1800b61c8  mov     r13d, r8d
0x1800b61cb  jmp     loc_1800B637D
0x1800b61d0  lea     eax, [rdx-1]
0x1800b61d3  cmp     [rdi+rax*2], r12w
0x1800b61d8  jnz     short loc_1800B61C5
0x1800b61da  lea     eax, [rdx-2]
0x1800b61dd  cmp     [rdi+rax*2], r12w
0x1800b61e2  jnz     short loc_1800B61C5
0x1800b61e4  cmp     [r13+0], r12w
0x1800b61e9  jz      loc_1800B6377
0x1800b61ef  mov     r8d, 0Ah; Radix
0x1800b61f5  mov     [rbp+70h+EndPtr], r12
0x1800b61f9  lea     rdx, [rbp+70h+EndPtr]; EndPtr
0x1800b61fd  mov     rcx, r13; String
0x1800b6200  call    cs:__imp_wcstol
0x1800b6207  nop     dword ptr [rax+rax+00h]
0x1800b620c  mov     dword ptr [rbp+70h+var_68], eax
0x1800b620f  cmp     eax, 0FFFFh
0x1800b6214  ja      loc_1800B63A8
0x1800b621a  mov     rcx, [rbp+70h+EndPtr]
0x1800b621e  cmp     [rcx], r12w
0x1800b6222  jz      short loc_1800B6268
0x1800b6224  cmp     word ptr [rcx], 2Dh ; '-'
0x1800b6228  jnz     loc_1800B63A8
0x1800b622e  add     rcx, 2; String
0x1800b6232  lea     rdx, [rbp+70h+EndPtr]; EndPtr
0x1800b6236  mov     r8d, 0Ah; Radix
0x1800b623c  call    cs:__imp_wcstol
0x1800b6243  nop     dword ptr [rax+rax+00h]
0x1800b6248  mov     r12d, eax
0x1800b624b  cmp     eax, 0FFFFh
0x1800b6250  ja      short loc_1800B6257
0x1800b6252  cmp     eax, dword ptr [rbp+70h+var_68]
0x1800b6255  jge     short loc_1800B626B
0x1800b6257  mov     r13d, 57h ; 'W'
0x1800b625d  xor     r12d, r12d
0x1800b6260  mov     r14d, r13d
0x1800b6263  jmp     loc_1800B637D
0x1800b6268  mov     r12d, eax
0x1800b626b  mov     ecx, 10h; dwBytes
0x1800b6270  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x1800b6275  mov     rdx, rax
0x1800b6278  test    rax, rax
0x1800b627b  jz      loc_1800B636E
0x1800b6281  mov     qword ptr [rax], 0
0x1800b6288  mov     eax, dword ptr [rbp+70h+var_68]
0x1800b628b  mov     [rdx+0Ah], ax
0x1800b628f  mov     [rdx+8], r12w
0x1800b6294  xor     ecx, ecx
0x1800b6296  mov     r12, rsi
0x1800b6299  mov     [rbp+70h+var_68], rcx
0x1800b629d  test    rsi, rsi
0x1800b62a0  jz      loc_1800B634E
0x1800b62a6  movzx   r11d, word ptr [r12+8]
0x1800b62ac  lea     r8, [r12+0Ah]
0x1800b62b1  movzx   r9d, word ptr [rdx+0Ah]
0x1800b62b6  lea     eax, [r15+r11]
0x1800b62ba  cmp     r9d, eax
0x1800b62bd  ja      short loc_1800B631D
0x1800b62bf  movzx   r10d, word ptr [r8]
0x1800b62c3  movzx   eax, word ptr [rdx+8]
0x1800b62c7  mov     ecx, r10d
0x1800b62ca  sub     ecx, r15d
0x1800b62cd  cmp     eax, ecx
0x1800b62cf  jl      short loc_1800B6319
0x1800b62d1  cmp     r9w, r10w
0x1800b62d5  mov     rcx, rdx; lpMem
0x1800b62d8  cmovb   r10w, r9w
0x1800b62dd  mov     [r8], r10w
0x1800b62e1  movzx   eax, word ptr [rdx+8]
0x1800b62e5  cmp     r11w, ax
0x1800b62e9  cmova   ax, r11w
0x1800b62ee  mov     [r12+8], ax
0x1800b62f4  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x1800b62f9  mov     rcx, [rbp+70h+var_68]
0x1800b62fd  mov     rdx, r12
0x1800b6300  test    rcx, rcx
0x1800b6303  jz      short loc_1800B630C
0x1800b6305  mov     rax, [r12]
0x1800b6309  mov     [rcx], rax
0x1800b630c  cmp     rsi, r12
0x1800b630f  jnz     short loc_1800B6294
0x1800b6311  mov     rsi, [rsi]
0x1800b6314  jmp     loc_1800B6294
0x1800b6319  mov     rcx, [rbp+70h+var_68]
0x1800b631d  cmp     r9w, [r8]
0x1800b6321  jb      short loc_1800B633C
0x1800b6323  mov     rcx, r12
0x1800b6326  mov     r12, [r12]
0x1800b632a  mov     [rbp+70h+var_68], rcx
0x1800b632e  test    r12, r12
0x1800b6331  jnz     loc_1800B629D
0x1800b6337  mov     [rcx], rdx
0x1800b633a  jmp     short loc_1800B6351
0x1800b633c  test    rcx, rcx
0x1800b633f  jz      short loc_1800B6346
0x1800b6341  mov     [rcx], rdx
0x1800b6344  jmp     short loc_1800B6349
0x1800b6346  mov     rsi, rdx
0x1800b6349  mov     [rdx], r12
0x1800b634c  jmp     short loc_1800B6351
0x1800b634e  mov     rsi, rdx
0x1800b6351  xor     edx, edx; Ch
0x1800b6353  mov     rcx, r13; Str
0x1800b6356  call    cs:__imp_wcschr
0x1800b635d  nop     dword ptr [rax+rax+00h]
0x1800b6362  xor     r12d, r12d
0x1800b6365  lea     r13, [rax+2]
0x1800b6369  jmp     loc_1800B61E4
0x1800b636e  mov     r14d, 0Eh
0x1800b6374  xor     r12d, r12d
0x1800b6377  mov     r13d, 57h ; 'W'
0x1800b637d  lea     rcx, [rdi-8]
0x1800b6381  cmp     dword ptr [rcx], 70616548h
0x1800b6387  jnz     short loc_1800B6395
0x1800b6389  mov     rax, cs:g_pfnFree
0x1800b6390  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6395  test    rsi, rsi
0x1800b6398  cmovz   r14d, r13d
0x1800b639c  cmp     [rbp+70h+var_6C], r15d
0x1800b63a0  jnz     short loc_1800B63B3
0x1800b63a2  mov     [rbx+10h], rsi
0x1800b63a6  jmp     short loc_1800B63B7
0x1800b63a8  mov     r13d, 57h ; 'W'
0x1800b63ae  mov     r14d, r13d
  ... truncated ...
```
