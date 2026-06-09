# _ReadPolicies(void *,ulong *,_tagEASPolicy * *)

- ea: `0x180010840`
- end: `0x180010ceb`
- name: `?_ReadPolicies@@YAJPEAXPEAKPEAPEAU_tagEASPolicy@@@Z`
- size: `1195`
- prototype: `__int64 __fastcall(HKEY hKey, unsigned int *, struct _tagEASPolicy **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010230`

## callees

- `0x180010840`
- `0x180027c58`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800109d1`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800109d1`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800108ca`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800108ca`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800109b4`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800109b4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800108f5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010929`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010943`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800108f5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010929`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010943`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010a64`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010a6d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010acb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010c22`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010a64`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010a6d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010acb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010c22`

## string_xrefs

- `0x180010b1e`: `onecore\ds\security\eas\policyengine\common.cpp`
- `0x180010b64`: `onecore\ds\security\eas\policyengine\common.cpp`
- `0x180010bab`: `onecore\ds\security\eas\policyengine\common.cpp`
- `0x180010bf0`: `onecore\ds\security\eas\policyengine\common.cpp`
- `0x180010c74`: `onecore\ds\security\eas\policyengine\common.cpp`
- `0x180010cab`: `onecore\ds\security\eas\policyengine\common.cpp`

## pseudocode

```c
__int64 __fastcall _ReadPolicies(HKEY hKey, unsigned int *a2, struct _tagEASPolicy **a3)
{
  unsigned int v4; // esi
  LSTATUS v5; // eax
  unsigned int v6; // ebx
  struct _tagEASPolicy *v7; // r14
  HLOCAL v8; // r15
  BYTE *v9; // r13
  unsigned int v10; // ebx
  DWORD v11; // edi
  __int64 v12; // xmm6_8
  LSTATUS v13; // eax
  int v14; // ecx
  __int128 v15; // xmm0
  __int64 v16; // rax
  unsigned int i; // eax
  __int16 *v18; // rdx
  __int16 v19; // cx
  LPDWORD lpcSubKeys; // [rsp+28h] [rbp-69h]
  LPDWORD lpcSubKeysa; // [rsp+28h] [rbp-69h]
  DWORD cbMaxValueLen; // [rsp+68h] [rbp-29h] BYREF
  DWORD cchValueName; // [rsp+6Ch] [rbp-25h] BYREF
  DWORD cbData; // [rsp+70h] [rbp-21h] BYREF
  DWORD Type; // [rsp+74h] [rbp-1Dh] BYREF
  __int128 v27; // [rsp+78h] [rbp-19h]
  __int64 v28; // [rsp+88h] [rbp-9h]
  DWORD cbMaxValueNameLen; // [rsp+F8h] [rbp+67h] BYREF
  unsigned int *v30; // [rsp+100h] [rbp+6Fh]
  struct _tagEASPolicy **v31; // [rsp+108h] [rbp+77h]
  DWORD cValues; // [rsp+110h] [rbp+7Fh] BYREF

  v31 = a3;
  v30 = a2;
  cValues = 0;
  cbMaxValueNameLen = 0;
  cbMaxValueLen = 0;
  v28 = 0;
  *a2 = 0;
  *a3 = 0;
  v27 = 0;
  if ( !hKey )
    return 0;
  v4 = 0;
  v5 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0);
  v6 = v5;
  if ( v5 )
  {
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0xC0070000;
    LODWORD(lpcSubKeys) = 496;
    DbgPrintfW(
      1u,
      L"(0x%08x) %ws:%u : %ws:%ws\n",
      v6,
      L"onecore\\ds\\security\\eas\\policyengine\\common.cpp",
      lpcSubKeys,
      L"RegQueryInfoKey",
      &Annotation);
    return v6;
  }
  if ( !cValues )
    return 0;
  v7 = (struct _tagEASPolicy *)LocalAlloc(0, 32LL * cValues);
  if ( !v7 )
  {
    LODWORD(lpcSubKeys) = 510;
    DbgPrintfW(
      1u,
      L"(0x%08x) %ws:%u : %ws:%ws\n",
      3221225495LL,
      L"onecore\\ds\\security\\eas\\policyengine\\common.cpp",
      lpcSubKeys,
      L"LocalAlloc",
      &Annotation);
    return 3221225495LL;
  }
  v8 = LocalAlloc(0x40u, 2LL * ++cbMaxValueNameLen);
  if ( !v8 )
  {
    v4 = -1073741801;
    LODWORD(lpcSubKeys) = 519;
    DbgPrintfW(
      1u,
      L"(0x%08x) %ws:%u : %ws:%ws\n",
      3221225495LL,
      L"onecore\\ds\\security\\eas\\policyengine\\common.cpp",
      lpcSubKeys,
      L"LocalAlloc",
      &Annotation);
    goto LABEL_29;
  }
  v9 = (BYTE *)LocalAlloc(0x40u, cbMaxValueLen);
  if ( !v9 )
  {
    v4 = -1073741801;
    LODWORD(lpcSubKeys) = 527;
    DbgPrintfW(
      1u,
      L"(0x%08x) %ws:%u : %ws:%ws\n",
      3221225495LL,
      L"onecore\\ds\\security\\eas\\policyengine\\common.cpp",
      lpcSubKeys,
      L"LocalAlloc",
      &Annotation);
    LocalFree(v8);
    goto LABEL_29;
  }
  v10 = 0;
  v11 = 0;
  v12 = v28;
  while ( 1 )
  {
    if ( v11 >= cValues )
    {
      *v30 = v10;
      *v31 = v7;
      v7 = 0;
      goto LABEL_22;
    }
    cchValueName = cbMaxValueNameLen;
    cbData = cbMaxValueLen;
    Type = 0;
    LOWORD(v27) = 0;
    v13 = RegEnumValueW(hKey, v11, (LPWSTR)v8, &cchValueName, 0, &Type, v9, &cbData);
    v4 = v13;
    if ( v13 )
      break;
    v4 = 0;
    *((_WORD *)v8 + cchValueName) = 0;
    v14 = _o__wtoi(v8);
    if ( v14 <= 0 )
    {
      LODWORD(lpcSubKeysa) = 560;
      DbgPrintfW(
        1u,
        L"(0x%08x) %ws:%u : %ws:%ws\n",
        3221225485LL,
        L"onecore\\ds\\security\\eas\\policyengine\\common.cpp",
        lpcSubKeysa,
        L"Invalid policy id",
        v8);
      goto LABEL_17;
    }
    if ( cbData )
    {
      if ( Type != 4 )
      {
        LODWORD(lpcSubKeysa) = 433;
        DbgPrintfW(
          1u,
          L"(0x%08x) %ws:%u : %ws:%ws\n",
          2147942487LL,
          L"onecore\\ds\\security\\eas\\policyengine\\common.cpp",
          lpcSubKeysa,
          L"invalid type",
          &Annotation);
        goto LABEL_17;
      }
      LOWORD(v27) = 19;
      DWORD2(v27) = *(_DWORD *)v9;
    }
    if ( v14 == 5 || v14 == 8 )
    {
      LOWORD(v27) = 11;
      if ( DWORD2(v27) )
        WORD4(v27) = -1;
      else
        WORD4(v27) = 0;
    }
    v15 = v27;
    v16 = 32LL * v10;
    LOWORD(v27) = 0;
    ++v10;
    *(_OWORD *)((char *)v7 + v16 + 8) = v15;
    *(_DWORD *)((char *)v7 + v16) = v14;
    *(_QWORD *)((char *)v7 + v16 + 24) = v12;
LABEL_17:
    ++v11;
  }
  if ( v13 > 0 )
    v4 = (unsigned __int16)v13 | 0xC0070000;
  LODWORD(lpcSubKeysa) = 552;
  DbgPrintfW(
    1u,
    L"(0x%08x) %ws:%u : %ws:%ws\n",
    v4,
    L"onecore\\ds\\security\\eas\\policyengine\\common.cpp",
    lpcSubKeysa,
    L"RegEnumValue",
    &Annotation);
LABEL_22:
  LocalFree(v8);
  LocalFree(v9);
  if ( v7 )
  {
    for ( i = 0; i < v10; ++i )
    {
      v18 = (__int16 *)((char *)v7 + 32 * i + 8);
      if ( v18 )
      {
        v19 = *v18;
        if ( (unsigned __int16)*v18 >= 2u && (v19 == 11 || v19 == 19) )
          *v18 = 0;
      }
    }
LABEL_29:
    LocalFree(v7);
  }
  return v4;
}

```

## disassembly

```asm
0x180010840  mov     rax, rsp
0x180010843  mov     [rax+18h], r8
0x180010847  mov     [rax+10h], rdx
0x18001084b  push    rbp
0x18001084c  push    rsi
0x18001084d  push    r12
0x18001084f  lea     rbp, [rax-5Fh]
0x180010853  sub     rsp, 0D0h
0x18001085a  xor     r9d, r9d; lpReserved
0x18001085d  mov     r12, rcx
0x180010860  xor     ecx, ecx
0x180010862  mov     [rbp+57h+cValues], r9d
0x180010866  mov     [rbp+57h+cbMaxValueNameLen], r9d
0x18001086a  xorps   xmm0, xmm0
0x18001086d  mov     [rbp+57h+cbMaxValueLen], r9d
0x180010871  mov     [rbp+57h+var_60], rcx
0x180010875  mov     [rdx], r9d
0x180010878  mov     [r8], r9
0x18001087b  movups  [rbp+57h+var_70], xmm0
0x18001087f  test    r12, r12
0x180010882  jz      loc_180010AFF
0x180010888  xor     esi, esi
0x18001088a  mov     [rax-20h], rbx
0x18001088e  mov     [rsp+58h], rsi; lpftLastWriteTime
0x180010893  lea     rax, [rbp+57h+cbMaxValueLen]
0x180010897  mov     [rsp+0E0h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x18001089c  xor     r8d, r8d; lpcchClass
0x18001089f  mov     [rsp+0E0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x1800108a4  xor     edx, edx; lpClass
0x1800108a6  lea     rax, [rbp+57h+cbMaxValueNameLen]
0x1800108aa  mov     rcx, r12; hKey
0x1800108ad  mov     [rsp+0E0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x1800108b2  lea     rax, [rbp+57h+cValues]
0x1800108b6  mov     [rsp+0E0h+lpcValues], rax; lpcValues
0x1800108bb  mov     [rsp+0E0h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x1800108c0  mov     [rsp+0E0h+lpcbMaxSubKeyLen], rsi; lpcbMaxSubKeyLen
0x1800108c5  mov     [rsp+0E0h+lpcSubKeys], rsi; lpcSubKeys
0x1800108ca  call    cs:__imp_RegQueryInfoKeyW
0x1800108d0  mov     ebx, eax
0x1800108d2  test    eax, eax
0x1800108d4  jnz     loc_180010B04
0x1800108da  mov     eax, [rbp+57h+cValues]
0x1800108dd  test    eax, eax
0x1800108df  jz      loc_180010B4E
0x1800108e5  mov     edx, eax
0x1800108e7  mov     [rsp+0E0h+var_30], r14
0x1800108ef  shl     rdx, 5; uBytes
0x1800108f3  xor     ecx, ecx; uFlags
0x1800108f5  call    cs:__imp_LocalAlloc
0x1800108fb  mov     r14, rax
0x1800108fe  test    rax, rax
0x180010901  jz      loc_180010B52
0x180010907  mov     eax, [rbp+57h+cbMaxValueNameLen]
0x18001090a  mov     ecx, 40h ; '@'; uFlags
0x18001090f  inc     eax
0x180010911  mov     [rsp+0E0h+var_28], r13
0x180010919  mov     edx, eax
0x18001091b  add     rdx, rdx; uBytes
0x18001091e  mov     [rsp+0E0h+var_38], r15
0x180010926  mov     [rbp+57h+cbMaxValueNameLen], eax
0x180010929  call    cs:__imp_LocalAlloc
0x18001092f  mov     r15, rax
0x180010932  test    rax, rax
0x180010935  jz      loc_180010B9A
0x18001093b  mov     edx, [rbp+57h+cbMaxValueLen]; uBytes
0x18001093e  mov     ecx, 40h ; '@'; uFlags
0x180010943  call    cs:__imp_LocalAlloc
0x180010949  mov     r13, rax
0x18001094c  test    rax, rax
0x18001094f  jz      loc_180010BDF
0x180010955  mov     [rsp+0E0h+var_20], rdi
0x18001095d  mov     ebx, esi
0x18001095f  movaps  [rsp+0E0h+var_58+8], xmm6
0x180010967  mov     edi, esi
0x180010969  movsd   xmm6, [rbp+57h+var_60]
0x18001096e  xchg    ax, ax
0x180010970  cmp     edi, [rbp+57h+cValues]
0x180010973  jnb     loc_180010A51
0x180010979  mov     eax, [rbp+57h+cbMaxValueNameLen]
0x18001097c  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x180010980  mov     [rbp+57h+cchValueName], eax
0x180010983  mov     r8, r15; lpValueName
0x180010986  mov     eax, [rbp+57h+cbMaxValueLen]
0x180010989  mov     edx, edi; dwIndex
0x18001098b  mov     [rbp+57h+cbData], eax
0x18001098e  mov     rcx, r12; hKey
0x180010991  lea     rax, [rbp+57h+cbData]
0x180010995  mov     [rbp+57h+Type], esi
0x180010998  mov     [rsp+0E0h+lpcValues], rax; lpcbData
0x18001099d  lea     rax, [rbp+57h+Type]
0x1800109a1  mov     [rsp+0E0h+lpcbMaxClassLen], r13; lpData
0x1800109a6  mov     [rsp+0E0h+lpcbMaxSubKeyLen], rax; lpType
0x1800109ab  mov     [rsp+0E0h+lpcSubKeys], rsi; lpReserved
0x1800109b0  mov     word ptr [rbp+57h+var_70], si
0x1800109b4  call    cs:__imp_RegEnumValueW
0x1800109ba  mov     esi, eax
0x1800109bc  test    eax, eax
0x1800109be  jnz     loc_180010C91
0x1800109c4  mov     ecx, [rbp+57h+cchValueName]
0x1800109c7  xor     esi, esi
0x1800109c9  mov     [r15+rcx*2], si
0x1800109ce  mov     rcx, r15
0x1800109d1  call    cs:__imp__o__wtoi
0x1800109d7  mov     ecx, eax
0x1800109d9  test    eax, eax
0x1800109db  jle     loc_180010C2D
0x1800109e1  cmp     [rbp+57h+cbData], esi
0x1800109e4  jz      short loc_180010A00
0x1800109e6  cmp     [rbp+57h+Type], 4
0x1800109ea  jnz     loc_180010C4E
0x1800109f0  mov     eax, 13h
0x1800109f5  mov     word ptr [rbp+57h+var_70], ax
0x1800109f9  mov     eax, [r13+0]
0x1800109fd  mov     dword ptr [rbp+57h+var_70+8], eax
0x180010a00  cmp     ecx, 5
0x180010a03  jz      short loc_180010A32
0x180010a05  cmp     ecx, 8
0x180010a08  jz      short loc_180010A32
0x180010a0a  movups  xmm0, [rbp+57h+var_70]
0x180010a0e  mov     eax, ebx
0x180010a10  shl     rax, 5
0x180010a14  mov     word ptr [rbp+57h+var_70], si
0x180010a18  inc     ebx
0x180010a1a  movups  xmmword ptr [rax+r14+8], xmm0
0x180010a20  mov     [rax+r14], ecx
0x180010a24  movsd   qword ptr [rax+r14+18h], xmm6
0x180010a2b  inc     edi
0x180010a2d  jmp     loc_180010970
0x180010a32  mov     eax, 0Bh
0x180010a37  mov     word ptr [rbp+57h+var_70], ax
0x180010a3b  cmp     dword ptr [rbp+57h+var_70+8], esi
0x180010a3e  jz      short loc_180010A4B
0x180010a40  mov     eax, 0FFFFFFFFh
0x180010a45  mov     word ptr [rbp+57h+var_70+8], ax
0x180010a49  jmp     short loc_180010A0A
0x180010a4b  mov     word ptr [rbp+57h+var_70+8], si
0x180010a4f  jmp     short loc_180010A0A
0x180010a51  mov     rax, [rbp+57h+arg_8]
0x180010a55  mov     [rax], ebx
0x180010a57  mov     rax, [rbp+57h+arg_10]
0x180010a5b  mov     [rax], r14
0x180010a5e  mov     r14, rsi
0x180010a61  mov     rcx, r15; hMem
0x180010a64  call    cs:__imp_LocalFree
0x180010a6a  mov     rcx, r13; hMem
0x180010a6d  call    cs:__imp_LocalFree
0x180010a73  movaps  xmm6, [rsp+0E0h+var_58+8]
0x180010a7b  mov     rdi, [rsp+0E0h+var_20]
0x180010a83  test    r14, r14
0x180010a86  jz      short loc_180010AD1
0x180010a88  xor     r9d, r9d
0x180010a8b  mov     eax, r9d
0x180010a8e  test    ebx, ebx
0x180010a90  jz      short loc_180010AC8
0x180010a92  lea     r8, [r14+8]
0x180010a96  nop     word ptr [rax+rax+00000000h]
0x180010aa0  mov     edx, eax
0x180010aa2  shl     rdx, 5
0x180010aa6  add     rdx, r8
0x180010aa9  jz      short loc_180010AC2
0x180010aab  movzx   ecx, word ptr [rdx]
0x180010aae  cmp     cx, 2
0x180010ab2  jb      short loc_180010AC2
0x180010ab4  cmp     cx, 0Bh
0x180010ab8  jnz     loc_180010CDC
0x180010abe  mov     [rdx], r9w
0x180010ac2  inc     eax
0x180010ac4  cmp     eax, ebx
0x180010ac6  jb      short loc_180010AA0
0x180010ac8  mov     rcx, r14; hMem
0x180010acb  call    cs:__imp_LocalFree
0x180010ad1  mov     r13, [rsp+0E0h+var_28]
0x180010ad9  mov     eax, esi
0x180010adb  mov     r15, [rsp+0E0h+var_38]
0x180010ae3  mov     r14, [rsp+0E0h+var_30]
0x180010aeb  mov     rbx, [rsp+0C8h]
0x180010af3  add     rsp, 0D0h
0x180010afa  pop     r12
0x180010afc  pop     rsi
0x180010afd  pop     rbp
0x180010afe  retn
0x180010aff  mov     eax, r9d
0x180010b02  jmp     short loc_180010AF3
0x180010b04  jle     short loc_180010B0F
0x180010b06  movzx   ebx, ax
0x180010b09  or      ebx, 0C0070000h
0x180010b0f  lea     rax, Annotation
0x180010b16  mov     r8d, ebx
0x180010b19  mov     [rsp+0E0h+lpcbMaxClassLen], rax
0x180010b1e  lea     r9, aOnecoreDsSecur; "onecore\\ds\\security\\eas\\policyengin"...
0x180010b25  lea     rax, aRegqueryinfoke; "RegQueryInfoKey"
0x180010b2c  mov     ecx, 1; unsigned int
0x180010b31  mov     [rsp+0E0h+lpcbMaxSubKeyLen], rax
0x180010b36  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x180010b3d  mov     dword ptr [rsp+0E0h+lpcSubKeys], 1F0h
0x180010b45  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x180010b4a  mov     eax, ebx
0x180010b4c  jmp     short loc_180010AEB
0x180010b4e  mov     eax, esi
0x180010b50  jmp     short loc_180010AEB
0x180010b52  lea     rax, Annotation
0x180010b59  mov     r8d, 0C0000017h
0x180010b5f  mov     [rsp+0E0h+lpcbMaxClassLen], rax
0x180010b64  lea     r9, aOnecoreDsSecur; "onecore\\ds\\security\\eas\\policyengin"...
0x180010b6b  lea     rax, aLocalalloc; "LocalAlloc"
0x180010b72  mov     ecx, 1; unsigned int
0x180010b77  mov     [rsp+0E0h+lpcbMaxSubKeyLen], rax
0x180010b7c  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x180010b83  mov     dword ptr [rsp+0E0h+lpcSubKeys], 1FEh
0x180010b8b  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x180010b90  mov     eax, 0C0000017h
0x180010b95  jmp     loc_180010AE3
0x180010b9a  lea     rax, Annotation
0x180010ba1  mov     esi, 0C0000017h
0x180010ba6  mov     [rsp+0E0h+lpcbMaxClassLen], rax
0x180010bab  lea     r9, aOnecoreDsSecur; "onecore\\ds\\security\\eas\\policyengin"...
0x180010bb2  lea     rax, aLocalalloc; "LocalAlloc"
0x180010bb9  mov     r8d, esi
0x180010bbc  mov     [rsp+0E0h+lpcbMaxSubKeyLen], rax
0x180010bc1  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x180010bc8  mov     ecx, 1; unsigned int
0x180010bcd  mov     dword ptr [rsp+0E0h+lpcSubKeys], 207h
0x180010bd5  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x180010bda  jmp     loc_180010AC8
0x180010bdf  lea     rax, Annotation
0x180010be6  mov     esi, 0C0000017h
0x180010beb  mov     [rsp+0E0h+lpcbMaxClassLen], rax
0x180010bf0  lea     r9, aOnecoreDsSecur; "onecore\\ds\\security\\eas\\policyengin"...
0x180010bf7  lea     rax, aLocalalloc; "LocalAlloc"
0x180010bfe  mov     r8d, esi
0x180010c01  mov     [rsp+0E0h+lpcbMaxSubKeyLen], rax
0x180010c06  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x180010c0d  mov     ecx, 1; unsigned int
0x180010c12  mov     dword ptr [rsp+0E0h+lpcSubKeys], 20Fh
0x180010c1a  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x180010c1f  mov     rcx, r15; hMem
0x180010c22  call    cs:__imp_LocalFree
0x180010c28  jmp     loc_180010AC8
0x180010c2d  mov     [rsp+0E0h+lpcbMaxClassLen], r15
0x180010c32  lea     rax, aInvalidPolicyI; "Invalid policy id"
0x180010c39  mov     [rsp+0E0h+lpcbMaxSubKeyLen], rax
0x180010c3e  mov     r8d, 0C000000Dh
0x180010c44  mov     dword ptr [rsp+0E0h+lpcSubKeys], 230h
0x180010c4c  jmp     short loc_180010C74
0x180010c4e  lea     rax, Annotation
0x180010c55  mov     r8d, 80070057h
0x180010c5b  mov     [rsp+0E0h+lpcbMaxClassLen], rax
0x180010c60  lea     rax, aInvalidType; "invalid type"
0x180010c67  mov     [rsp+0E0h+lpcbMaxSubKeyLen], rax
0x180010c6c  mov     dword ptr [rsp+0E0h+lpcSubKeys], 1B1h
0x180010c74  lea     r9, aOnecoreDsSecur; "onecore\\ds\\security\\eas\\policyengin"...
0x180010c7b  mov     ecx, 1; unsigned int
0x180010c80  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x180010c87  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x180010c8c  jmp     loc_180010A2B
0x180010c91  jle     short loc_180010C9C
0x180010c93  movzx   esi, ax
0x180010c96  or      esi, 0C0070000h
0x180010c9c  lea     rax, Annotation
0x180010ca3  mov     r8d, esi
0x180010ca6  mov     [rsp+0E0h+lpcbMaxClassLen], rax
0x180010cab  lea     r9, aOnecoreDsSecur; "onecore\\ds\\security\\eas\\policyengin"...
0x180010cb2  lea     rax, aRegenumvalue; "RegEnumValue"
0x180010cb9  mov     ecx, 1; unsigned int
0x180010cbe  mov     [rsp+0E0h+lpcbMaxSubKeyLen], rax
0x180010cc3  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x180010cca  mov     dword ptr [rsp+0E0h+lpcSubKeys], 228h
0x180010cd2  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x180010cd7  jmp     loc_180010A61
0x180010cdc  cmp     cx, 13h
0x180010ce0  jnz     loc_180010AC2
0x180010ce6  jmp     loc_180010ABE
```
