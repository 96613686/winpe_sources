# CWshShell::RegRead(ushort *,tagVARIANT *)

- ea: `0x1800023e0`
- end: `0x180002a5a`
- name: `?RegRead@CWshShell@@UEAAJPEAGPEAUtagVARIANT@@@Z`
- size: `1658`
- prototype: `int(CWshShell *__hidden this, unsigned __int16 *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x1800023e0`
- `0x180005d20`
- `0x180010206`
- `0x180010250`
- `0x1800102e0`

## import_xrefs

- `msvcrt!_mbsnbcmp` at `0x1800024d6`
- `msvcrt!_mbsnbcmp` at `0x1800024d6`
- `msvcrt!_mbsrchr` at `0x1800024fc`
- `msvcrt!_mbsrchr` at `0x1800024fc`
- `OLEAUT32!__imp_SysAllocString` at `0x1800027d0`
- `OLEAUT32!__imp_SysAllocString` at `0x1800027d0`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180002670`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800028df`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180002670`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800028df`
- `OLEAUT32!__imp_VariantInit` at `0x180002632`
- `OLEAUT32!__imp_VariantInit` at `0x18000291f`
- `OLEAUT32!__imp_VariantInit` at `0x180002a15`
- `OLEAUT32!__imp_VariantInit` at `0x180002632`
- `OLEAUT32!__imp_VariantInit` at `0x18000291f`
- `OLEAUT32!__imp_VariantInit` at `0x180002a15`
- `OLEAUT32!__imp_VariantClear` at `0x180002946`
- `OLEAUT32!__imp_VariantClear` at `0x180002946`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18000288b`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800029dc`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18000288b`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800029dc`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180002987`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180002998`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180002a4d`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180002987`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180002998`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180002a4d`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180002939`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180002a31`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180002939`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180002a31`
- `ADVAPI32!RegOpenKeyExA` at `0x18000257f`
- `ADVAPI32!RegOpenKeyExA` at `0x18000257f`
- `ADVAPI32!RegQueryValueExA` at `0x1800025b6`
- `ADVAPI32!RegQueryValueExA` at `0x180002614`
- `ADVAPI32!RegQueryValueExA` at `0x1800025b6`
- `ADVAPI32!RegQueryValueExA` at `0x180002614`
- `ADVAPI32!RegCloseKey` at `0x180002620`
- `ADVAPI32!RegCloseKey` at `0x18000276c`
- `ADVAPI32!RegCloseKey` at `0x1800027eb`
- `ADVAPI32!RegCloseKey` at `0x180002804`
- `ADVAPI32!RegCloseKey` at `0x180002620`
- `ADVAPI32!RegCloseKey` at `0x18000276c`
- `ADVAPI32!RegCloseKey` at `0x1800027eb`
- `ADVAPI32!RegCloseKey` at `0x180002804`
- `KERNEL32!WideCharToMultiByte` at `0x180002443`
- `KERNEL32!WideCharToMultiByte` at `0x18000249b`
- `KERNEL32!WideCharToMultiByte` at `0x180002443`
- `KERNEL32!WideCharToMultiByte` at `0x18000249b`
- `KERNEL32!MultiByteToWideChar` at `0x18000265b`
- `KERNEL32!MultiByteToWideChar` at `0x18000271b`
- `KERNEL32!MultiByteToWideChar` at `0x1800028c9`
- `KERNEL32!MultiByteToWideChar` at `0x180002908`
- `KERNEL32!MultiByteToWideChar` at `0x18000265b`
- `KERNEL32!MultiByteToWideChar` at `0x18000271b`
- `KERNEL32!MultiByteToWideChar` at `0x1800028c9`
- `KERNEL32!MultiByteToWideChar` at `0x180002908`

## string_xrefs

- `0x180002698`: `WshShell.RegRead`
- `0x1800026e5`: `WshShell.RegRead`
- `0x180002750`: `WshShell.RegRead`
- `0x180002780`: `WshShell.RegRead`

## pseudocode

```c
__int64 __fastcall CWshShell::RegRead(CWshShell *this, unsigned __int16 *a2, struct tagVARIANT *a3)
{
  int v5; // eax
  unsigned __int64 cbMultiByte; // rdx
  __int64 v7; // rax
  void *v8; // rsp
  char **i; // rdi
  const unsigned __int8 *v10; // rdx
  __int64 v11; // rax
  __int64 v12; // rsi
  HKEY v13; // rdi
  CHAR *v14; // r14
  unsigned __int8 *v15; // rax
  unsigned __int8 *v16; // r13
  size_t v17; // r12
  __int64 v18; // rcx
  void *v19; // rsp
  void *v20; // rsp
  LSTATUS v21; // eax
  signed int v22; // esi
  LSTATUS v23; // esi
  unsigned __int64 v24; // rcx
  unsigned __int64 v25; // rcx
  void *v26; // rsp
  void *v27; // rsp
  CHAR *v28; // rsi
  LSTATUS v29; // r14d
  int v30; // eax
  int v31; // edi
  WCHAR *v32; // rax
  SAFEARRAY *v33; // rbx
  BSTR v35; // rax
  signed int v36; // edi
  CHAR *j; // rax
  __int64 v38; // rcx
  int v39; // ecx
  int v40; // eax
  int v41; // r13d
  WCHAR *v42; // rax
  LONGLONG v43; // r12
  HRESULT v44; // r12d
  __int64 v45; // rax
  int v46; // r14d
  int v47; // eax
  HRESULT v48; // edi
  _BYTE v49[32]; // [rsp+0h] [rbp-40h] BYREF
  CHAR MultiByteStr[4]; // [rsp+40h] [rbp+0h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp+8h] BYREF
  DWORD Type; // [rsp+50h] [rbp+10h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+58h] [rbp+18h] BYREF
  VARIANTARG pvarg; // [rsp+60h] [rbp+20h] BYREF

  if ( !a2 || !a3 )
    return 2147500035LL;
  v5 = WideCharToMultiByte(0, 0, a2, -1, 0, 0, 0, 0);
  cbMultiByte = v5;
  if ( !v5 )
    goto LABEL_37;
  v7 = v5 + 15LL;
  if ( cbMultiByte + 15 < cbMultiByte )
    v7 = 0xFFFFFFFFFFFFFF0LL;
  v8 = alloca(v7 & 0xFFFFFFFFFFFFFFF0uLL);
  WideCharToMultiByte(0, 0, a2, -1, MultiByteStr, cbMultiByte, 0, 0);
  if ( !MultiByteStr )
  {
LABEL_37:
    Signal_Exception(&IID_IWshEnvironment, L"WshShell.RegRead", 0x100Eu, a2);
    return 2147942487LL;
  }
  for ( i = &off_1800184C0; ; i += 2 )
  {
    v10 = (const unsigned __int8 *)*i;
    if ( !*i )
      goto LABEL_31;
    v11 = -1;
    do
      ++v11;
    while ( v10[v11] );
    v12 = (int)v11;
    if ( !_mbsnbcmp((const unsigned __int8 *)MultiByteStr, v10, (int)v11) )
      break;
  }
  v13 = (HKEY)i[1];
  if ( !v13 )
  {
LABEL_31:
    v22 = -2147024893;
    goto LABEL_32;
  }
  v14 = &MultiByteStr[v12];
  v15 = _mbsrchr((const unsigned __int8 *)&MultiByteStr[v12], 0x5Cu);
  v16 = v15;
  if ( !v15 )
    goto LABEL_19;
  v17 = (int)v15 - (int)v14;
  v18 = v17 + 16;
  if ( v17 + 16 <= v17 + 1 )
    v18 = 0xFFFFFFFFFFFFFF0LL;
  v19 = alloca(v18 & 0xFFFFFFFFFFFFFFF0uLL);
  v20 = alloca(v18 & 0xFFFFFFFFFFFFFFF0uLL);
  if ( v49 == (_BYTE *)-64LL )
  {
    v22 = -2147024882;
    goto LABEL_32;
  }
  memcpy_0(MultiByteStr, v14, v17);
  MultiByteStr[v17] = 0;
  phkResult = 0;
  v14 = (CHAR *)(v16 + 1);
  v21 = RegOpenKeyExA(v13, MultiByteStr, 0, 1u, &phkResult);
  v22 = v21;
  if ( !v21 )
  {
    v13 = phkResult;
    goto LABEL_19;
  }
  v13 = 0;
  if ( v21 > 0 )
    v22 = (unsigned __int16)v21 | 0x80070000;
  if ( v22 < 0 )
  {
LABEL_32:
    Signal_Exception(&IID_IWshEnvironment, L"WshShell.RegRead", 0x100Eu, a2);
    return (unsigned int)v22;
  }
LABEL_19:
  *(_DWORD *)MultiByteStr = 0;
  Type = 0;
  v23 = RegQueryValueExA(v13, v14, 0, &Type, 0, (LPDWORD)MultiByteStr);
  if ( v23 )
  {
    if ( v14 && *v14 )
    {
      Signal_Exception(&IID_IWshEnvironment, L"WshShell.RegRead", 0x100Fu, a2);
      RegCloseKey(v13);
      if ( v23 > 0 )
        return (unsigned __int16)v23 | 0x80070000;
    }
    else
    {
      v35 = SysAllocString(&psz);
      if ( !v35 )
      {
LABEL_52:
        RegCloseKey(v13);
        return 2147942414LL;
      }
      a3->vt = 8;
      a3->llVal = (LONGLONG)v35;
      v23 = 0;
      RegCloseKey(v13);
    }
    return (unsigned int)v23;
  }
  v24 = *(unsigned int *)MultiByteStr + 15LL;
  if ( v24 <= *(unsigned int *)MultiByteStr )
    v24 = 0xFFFFFFFFFFFFFF0LL;
  v25 = v24 & 0xFFFFFFFFFFFFFFF0uLL;
  v26 = alloca(v25);
  v27 = alloca(v25);
  v28 = MultiByteStr;
  if ( v49 == (_BYTE *)-64LL )
    goto LABEL_52;
  v29 = RegQueryValueExA(v13, v14, 0, &Type, (LPBYTE)MultiByteStr, (LPDWORD)MultiByteStr);
  RegCloseKey(v13);
  if ( !v29 )
  {
    VariantInit(a3);
    switch ( Type )
    {
      case 2u:
      case 1u:
        v30 = MultiByteToWideChar(0, 0, MultiByteStr, -1, 0, 0);
        v31 = v30;
        if ( !v30 )
        {
          a3->vt = 8;
          a3->llVal = 0;
          return 0;
        }
        v32 = SysAllocStringLen(0, v30 - 1);
        v33 = (SAFEARRAY *)v32;
        if ( v32 )
          MultiByteToWideChar(0, 0, MultiByteStr, -1, v32, v31);
        a3->vt = 8;
        goto LABEL_29;
      case 3u:
        rgsabound.cElements = *(_DWORD *)MultiByteStr;
        rgsabound.lLbound = 0;
        v33 = SafeArrayCreate(0xCu, 1u, &rgsabound);
        if ( v33 )
        {
          v46 = *(_DWORD *)MultiByteStr;
          v47 = 0;
          LODWORD(phkResult) = 0;
          while ( v47 < v46 )
          {
            memset(&pvarg, 0, sizeof(pvarg));
            VariantInit(&pvarg);
            pvarg.bVal = *v28;
            pvarg.vt = 17;
            v48 = SafeArrayPutElement(v33, (LONG *)&phkResult, &pvarg);
            if ( v48 < 0 )
            {
              SafeArrayDestroy(v33);
              return (unsigned int)v48;
            }
            ++v28;
            v47 = (_DWORD)phkResult + 1;
            LODWORD(phkResult) = (_DWORD)phkResult + 1;
          }
          goto LABEL_77;
        }
        break;
      case 4u:
        a3->vt = 3;
        a3->lVal = *(_DWORD *)MultiByteStr;
        return 0;
      case 7u:
        v36 = 0;
        for ( j = MultiByteStr; *j; j += v38 + 1 )
        {
          ++v36;
          v38 = -1;
          do
            ++v38;
          while ( j[v38] );
        }
        rgsabound.lLbound = 0;
        rgsabound.cElements = v36;
        v33 = SafeArrayCreate(0xCu, 1u, &rgsabound);
        if ( v33 )
        {
          LODWORD(phkResult) = 0;
          v39 = 0;
          while ( v39 < v36 )
          {
            v40 = MultiByteToWideChar(0, 0, v28, -1, 0, 0);
            v41 = v40;
            if ( !v40 || (v42 = SysAllocStringLen(0, v40 - 1), (v43 = (LONGLONG)v42) == 0) )
            {
              SafeArrayDestroy(v33);
              return 2147942414LL;
            }
            MultiByteToWideChar(0, 0, v28, -1, v42, v41);
            memset(&pvarg, 0, sizeof(pvarg));
            VariantInit(&pvarg);
            pvarg.vt = 8;
            pvarg.llVal = v43;
            v44 = SafeArrayPutElement(v33, (LONG *)&phkResult, &pvarg);
            VariantClear(&pvarg);
            if ( v44 < 0 )
            {
              SafeArrayDestroy(v33);
              return (unsigned int)v44;
            }
            if ( v28 )
            {
              v45 = -1;
              do
                ++v45;
              while ( v28[v45] );
            }
            else
            {
              v45 = 0;
            }
            v28 += v45 + 1;
            v39 = (_DWORD)phkResult + 1;
            LODWORD(phkResult) = (_DWORD)phkResult + 1;
          }
LABEL_77:
          a3->vt = 8204;
LABEL_29:
          a3->llVal = (LONGLONG)v33;
          return 0;
        }
        break;
      default:
        return 2147614725LL;
    }
    return 2147942414LL;
  }
  Signal_Exception(&IID_IWshEnvironment, L"WshShell.RegRead", 0x100Fu, a2);
  if ( v29 > 0 )
    return (unsigned __int16)v29 | 0x80070000;
  return (unsigned int)v29;
}

```

## disassembly

```asm
0x1800023e0  push    rbp
0x1800023e2  push    rbx
0x1800023e3  push    rsi
0x1800023e4  push    rdi
0x1800023e5  push    r12
0x1800023e7  push    r13
0x1800023e9  push    r14
0x1800023eb  push    r15
0x1800023ed  sub     rsp, 88h
0x1800023f4  lea     rbp, [rsp+40h]
0x1800023f9  mov     rax, cs:__security_cookie
0x180002400  xor     rax, rbp
0x180002403  mov     [rbp+80h+var_48], rax
0x180002407  mov     r15, r8
0x18000240a  mov     rbx, rdx
0x18000240d  test    rdx, rdx
0x180002410  jz      loc_18000272F
0x180002416  test    r8, r8
0x180002419  jz      loc_18000272F
0x18000241f  xor     r12d, r12d
0x180002422  mov     r8, rdx; lpWideCharStr
0x180002425  mov     [rsp+0C0h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x18000242a  mov     r9d, 0FFFFFFFFh; cchWideChar
0x180002430  mov     [rsp+0C0h+lpDefaultChar], r12; lpDefaultChar
0x180002435  xor     edx, edx; dwFlags
0x180002437  mov     [rsp+0C0h+cbMultiByte], r12d; cbMultiByte
0x18000243c  xor     ecx, ecx; CodePage
0x18000243e  mov     [rsp+0C0h+lpMultiByteStr], r12; lpMultiByteStr
0x180002443  call    cs:__imp_WideCharToMultiByte
0x180002449  movsxd  rdx, eax
0x18000244c  test    eax, eax
0x18000244e  jz      loc_1800026E2
0x180002454  lea     rax, [rdx+0Fh]
0x180002458  mov     r8, 0FFFFFFFFFFFFFF0h
0x180002462  cmp     rax, rdx
0x180002465  ja      short loc_18000246A
0x180002467  mov     rax, r8
0x18000246a  and     rax, 0FFFFFFFFFFFFFFF0h
0x18000246e  call    _alloca_probe
0x180002473  sub     rsp, rax
0x180002476  mov     r9d, 0FFFFFFFFh; cchWideChar
0x18000247c  mov     r8, rbx; lpWideCharStr
0x18000247f  xor     ecx, ecx; CodePage
0x180002481  mov     [rsp+0C0h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x180002486  lea     r14, [rsp+0C0h+MultiByteStr]
0x18000248b  mov     [rsp+0C0h+lpDefaultChar], r12; lpDefaultChar
0x180002490  mov     [rsp+0C0h+cbMultiByte], edx; cbMultiByte
0x180002494  xor     edx, edx; dwFlags
0x180002496  mov     [rsp+0C0h+lpMultiByteStr], r14; lpMultiByteStr
0x18000249b  call    cs:__imp_WideCharToMultiByte
0x1800024a1  test    r14, r14
0x1800024a4  jz      loc_1800026E2
0x1800024aa  lea     rdi, off_1800184C0; "HKCU\\"
0x1800024b1  mov     rdx, [rdi]; Str2
0x1800024b4  test    rdx, rdx
0x1800024b7  jz      loc_180002690
0x1800024bd  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800024c4  inc     rax
0x1800024c7  cmp     [rdx+rax], r12b
0x1800024cb  jnz     short loc_1800024C4
0x1800024cd  movsxd  rsi, eax
0x1800024d0  mov     rcx, r14; Str1
0x1800024d3  mov     r8, rsi; MaxCount
0x1800024d6  call    cs:__imp__mbsnbcmp
0x1800024dc  test    eax, eax
0x1800024de  jnz     loc_180002726
0x1800024e4  mov     rdi, [rdi+8]
0x1800024e8  test    rdi, rdi
0x1800024eb  jz      loc_180002690
0x1800024f1  add     r14, rsi
0x1800024f4  mov     edx, 5Ch ; '\'; C
0x1800024f9  mov     rcx, r14; String
0x1800024fc  call    cs:__imp__mbsrchr
0x180002502  mov     r13, rax
0x180002505  test    rax, rax
0x180002508  jz      loc_180002593
0x18000250e  sub     eax, r14d
0x180002511  movsxd  r12, eax
0x180002514  lea     rax, [r12+1]
0x180002519  lea     rcx, [rax+0Fh]
0x18000251d  cmp     rcx, rax
0x180002520  ja      short loc_18000252C
0x180002522  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18000252c  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180002530  mov     rax, rcx
0x180002533  call    _alloca_probe
0x180002538  sub     rsp, rcx
0x18000253b  lea     rsi, [rsp+0C0h+MultiByteStr]
0x180002540  test    rsi, rsi
0x180002543  jz      loc_1800027A6
0x180002549  mov     r8, r12; Size
0x18000254c  mov     rdx, r14; Src
0x18000254f  mov     rcx, rsi; void *
0x180002552  call    memcpy_0
0x180002557  mov     byte ptr [r12+rsi], 0
0x18000255c  lea     rax, [rbp+80h+phkResult]
0x180002560  xor     r12d, r12d
0x180002563  mov     [rsp+0C0h+lpMultiByteStr], rax; phkResult
0x180002568  mov     r9d, 1; samDesired
0x18000256e  mov     [rbp+80h+phkResult], r12
0x180002572  xor     r8d, r8d; ulOptions
0x180002575  lea     r14, [r13+1]
0x180002579  mov     rdx, rsi; lpSubKey
0x18000257c  mov     rcx, rdi; hKey
0x18000257f  call    cs:__imp_RegOpenKeyExA
0x180002585  mov     esi, eax
0x180002587  test    eax, eax
0x180002589  jnz     loc_1800026D0
0x18000258f  mov     rdi, [rbp+80h+phkResult]
0x180002593  lea     rax, [rbp+80h+MultiByteStr]
0x180002597  mov     dword ptr [rbp+80h+MultiByteStr], r12d
0x18000259b  mov     qword ptr [rsp+0C0h+cbMultiByte], rax; lpcbData
0x1800025a0  lea     r9, [rbp+80h+Type]; lpType
0x1800025a4  xor     r8d, r8d; lpReserved
0x1800025a7  mov     [rsp+0C0h+lpMultiByteStr], r12; lpData
0x1800025ac  mov     rdx, r14; lpValueName
0x1800025af  mov     [rbp+80h+Type], r12d
0x1800025b3  mov     rcx, rdi; hKey
0x1800025b6  call    cs:__imp_RegQueryValueExA
0x1800025bc  mov     esi, eax
0x1800025be  test    eax, eax
0x1800025c0  jnz     loc_1800027BE
0x1800025c6  mov     eax, dword ptr [rbp+80h+MultiByteStr]
0x1800025c9  lea     rcx, [rax+0Fh]
0x1800025cd  cmp     rcx, rax
0x1800025d0  ja      short loc_1800025DC
0x1800025d2  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800025dc  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800025e0  mov     rax, rcx
0x1800025e3  call    _alloca_probe
0x1800025e8  sub     rsp, rcx
0x1800025eb  lea     rsi, [rsp+0C0h+MultiByteStr]
0x1800025f0  test    rsi, rsi
0x1800025f3  jz      loc_180002801
0x1800025f9  lea     rax, [rbp+80h+MultiByteStr]
0x1800025fd  xor     r8d, r8d; lpReserved
0x180002600  mov     qword ptr [rsp+0C0h+cbMultiByte], rax; lpcbData
0x180002605  lea     r9, [rbp+80h+Type]; lpType
0x180002609  mov     rdx, r14; lpValueName
0x18000260c  mov     [rsp+0C0h+lpMultiByteStr], rsi; lpData
0x180002611  mov     rcx, rdi; hKey
0x180002614  call    cs:__imp_RegQueryValueExA
0x18000261a  mov     rcx, rdi; hKey
0x18000261d  mov     r14d, eax
0x180002620  call    cs:__imp_RegCloseKey
0x180002626  test    r14d, r14d
0x180002629  jnz     loc_18000277D
0x18000262f  mov     rcx, r15; pvarg
0x180002632  call    cs:__imp_VariantInit
0x180002638  mov     eax, [rbp+80h+Type]
0x18000263b  cmp     eax, 2
0x18000263e  jnz     loc_180002824
0x180002644  mov     [rsp+0C0h+cbMultiByte], r12d; cchWideChar
0x180002649  mov     r9d, 0FFFFFFFFh; cbMultiByte
0x18000264f  mov     r8, rsi; lpMultiByteStr
0x180002652  mov     [rsp+0C0h+lpMultiByteStr], r12; lpWideCharStr
0x180002657  xor     edx, edx; dwFlags
0x180002659  xor     ecx, ecx; CodePage
0x18000265b  call    cs:__imp_MultiByteToWideChar
0x180002661  mov     edi, eax
0x180002663  test    eax, eax
0x180002665  jz      loc_180002739
0x18000266b  lea     edx, [rax-1]; ui
0x18000266e  xor     ecx, ecx; strIn
0x180002670  call    cs:__imp_SysAllocStringLen
0x180002676  mov     rbx, rax
0x180002679  test    rax, rax
0x18000267c  jnz     loc_180002705
0x180002682  mov     word ptr [r15], 8
0x180002688  mov     [r15+8], rbx
0x18000268c  xor     eax, eax
0x18000268e  jmp     short loc_1800026B3
0x180002690  mov     esi, 80070003h
0x180002695  mov     r9, rbx
0x180002698  lea     rdx, aWshshellRegrea; "WshShell.RegRead"
0x18000269f  mov     r8d, 100Eh; unsigned int
0x1800026a5  lea     rcx, IID_IWshEnvironment; struct _GUID *
0x1800026ac  call    ?Signal_Exception@@YAJAEBU_GUID@@PEBGIZZ; Signal_Exception(_GUID const &,ushort const *,uint,...)
0x1800026b1  mov     eax, esi
0x1800026b3  mov     rcx, [rbp+80h+var_48]
0x1800026b7  xor     rcx, rbp; StackCookie
0x1800026ba  call    __security_check_cookie
0x1800026bf  lea     rsp, [rbp+48h]
0x1800026c3  pop     r15
0x1800026c5  pop     r14
0x1800026c7  pop     r13
0x1800026c9  pop     r12
0x1800026cb  pop     rdi
0x1800026cc  pop     rsi
0x1800026cd  pop     rbx
0x1800026ce  pop     rbp
0x1800026cf  retn
0x1800026d0  mov     rdi, r12
0x1800026d3  jg      loc_1800027B0
0x1800026d9  test    esi, esi
0x1800026db  js      short loc_180002695
0x1800026dd  jmp     loc_180002593
0x1800026e2  mov     r9, rbx
0x1800026e5  lea     rdx, aWshshellRegrea; "WshShell.RegRead"
0x1800026ec  mov     r8d, 100Eh; unsigned int
0x1800026f2  lea     rcx, IID_IWshEnvironment; struct _GUID *
0x1800026f9  call    ?Signal_Exception@@YAJAEBU_GUID@@PEBGIZZ; Signal_Exception(_GUID const &,ushort const *,uint,...)
0x1800026fe  mov     eax, 80070057h
0x180002703  jmp     short loc_1800026B3
0x180002705  mov     [rsp+0C0h+cbMultiByte], edi; cchWideChar
0x180002709  mov     r9d, 0FFFFFFFFh; cbMultiByte
0x18000270f  mov     r8, rsi; lpMultiByteStr
0x180002712  mov     [rsp+0C0h+lpMultiByteStr], rax; lpWideCharStr
0x180002717  xor     edx, edx; dwFlags
0x180002719  xor     ecx, ecx; CodePage
0x18000271b  call    cs:__imp_MultiByteToWideChar
0x180002721  jmp     loc_180002682
0x180002726  add     rdi, 10h
0x18000272a  jmp     loc_1800024B1
0x18000272f  mov     eax, 80004003h
0x180002734  jmp     loc_1800026B3
0x180002739  mov     rbx, r12
0x18000273c  mov     word ptr [r15], 8
0x180002742  mov     [r15+8], rbx
0x180002746  xor     eax, eax
0x180002748  jmp     loc_1800026B3
0x18000274d  mov     r9, rbx
0x180002750  lea     rdx, aWshshellRegrea; "WshShell.RegRead"
0x180002757  mov     r8d, 100Fh; unsigned int
0x18000275d  lea     rcx, IID_IWshEnvironment; struct _GUID *
0x180002764  call    ?Signal_Exception@@YAJAEBU_GUID@@PEBGIZZ; Signal_Exception(_GUID const &,ushort const *,uint,...)
0x180002769  mov     rcx, rdi; hKey
0x18000276c  call    cs:__imp_RegCloseKey
0x180002772  test    esi, esi
0x180002774  jg      short loc_1800027F3
0x180002776  mov     eax, esi
0x180002778  jmp     loc_1800026B3
0x18000277d  mov     r9, rbx
0x180002780  lea     rdx, aWshshellRegrea; "WshShell.RegRead"
0x180002787  mov     r8d, 100Fh; unsigned int
0x18000278d  lea     rcx, IID_IWshEnvironment; struct _GUID *
0x180002794  call    ?Signal_Exception@@YAJAEBU_GUID@@PEBGIZZ; Signal_Exception(_GUID const &,ushort const *,uint,...)
0x180002799  test    r14d, r14d
0x18000279c  jg      short loc_180002814
0x18000279e  mov     eax, r14d
0x1800027a1  jmp     loc_1800026B3
0x1800027a6  mov     esi, 8007000Eh
0x1800027ab  jmp     loc_180002695
0x1800027b0  movzx   esi, ax
0x1800027b3  or      esi, 80070000h
0x1800027b9  jmp     loc_1800026D9
0x1800027be  test    r14, r14
0x1800027c1  jz      short loc_1800027C9
0x1800027c3  cmp     byte ptr [r14], 0
0x1800027c7  jnz     short loc_18000274D
0x1800027c9  lea     rcx, psz; psz
0x1800027d0  call    cs:__imp_SysAllocString
0x1800027d6  test    rax, rax
0x1800027d9  jz      short loc_180002801
0x1800027db  mov     rcx, rdi; hKey
0x1800027de  mov     word ptr [r15], 8
0x1800027e4  mov     [r15+8], rax
0x1800027e8  mov     esi, r12d
0x1800027eb  call    cs:__imp_RegCloseKey
0x1800027f1  jmp     short loc_180002776
0x1800027f3  movzx   esi, si
0x1800027f6  or      esi, 80070000h
0x1800027fc  jmp     loc_180002776
0x180002801  mov     rcx, rdi; hKey
0x180002804  call    cs:__imp_RegCloseKey
0x18000280a  mov     eax, 8007000Eh
0x18000280f  jmp     loc_1800026B3
0x180002814  movzx   r14d, r14w
0x180002818  or      r14d, 80070000h
0x18000281f  jmp     loc_18000279E
0x180002824  sub     eax, 1
0x180002827  jz      loc_180002644
0x18000282d  sub     eax, 2
0x180002830  jz      loc_1800029C4
0x180002836  sub     eax, 1
0x180002839  jz      loc_1800029B3
0x18000283f  cmp     eax, 3
0x180002842  jz      short loc_18000284E
0x180002844  mov     eax, 80020005h
0x180002849  jmp     loc_1800026B3
0x18000284e  cmp     byte ptr [rsi], 0
0x180002851  mov     edi, r12d
0x180002854  mov     rax, rsi
0x180002857  jz      short loc_180002876
0x180002859  inc     edi
0x18000285b  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180002862  inc     rcx
0x180002865  cmp     byte ptr [rax+rcx], 0
0x180002869  jnz     short loc_180002862
0x18000286b  inc     rax
0x18000286e  add     rax, rcx
0x180002871  cmp     byte ptr [rax], 0
0x180002874  jnz     short loc_180002859
0x180002876  mov     ecx, 0Ch; vt
0x18000287b  mov     [rbp+80h+rgsabound.lLbound], r12d
0x18000287f  lea     r8, [rbp+80h+rgsabound]; rgsabound
0x180002883  mov     [rbp+80h+rgsabound.cElements], edi
0x180002886  mov     edx, 1; cDims
0x18000288b  call    cs:__imp_SafeArrayCreate
0x180002891  mov     rbx, rax
  ... truncated ...
```
