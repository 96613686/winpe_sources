# CUwfStaticVolumeConfiguration::CompareOptionalValues(CUwfStaticVolumeConfiguration &,bool *)

- ea: `0x18000658c`
- end: `0x180006a35`
- name: `?CompareOptionalValues@CUwfStaticVolumeConfiguration@@AEAAJAEAV1@PEA_N@Z`
- size: `1193`
- prototype: `__int64 __fastcall(CUwfStaticVolumeConfiguration *__hidden this, struct CUwfStaticVolumeConfiguration *, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180006290`

## callees

- `0x18000658c`
- `0x18000e0f0`
- `0x18000e2a0`
- `0x18000e320`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x1800069ee`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800069f8`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180006a02`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180006a0b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800069ee`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800069f8`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180006a02`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180006a0b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800067fc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180006883`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800067fc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180006883`

## pseudocode

```c
__int64 __fastcall CUwfStaticVolumeConfiguration::CompareOptionalValues(
        CUwfStaticVolumeConfiguration *this,
        struct CUwfStaticVolumeConfiguration *a2,
        bool *a3)
{
  CUwfRegKey *v3; // r12
  unsigned __int16 *v6; // r13
  signed int v7; // ebx
  int v8; // edi
  CUwfRegKey *v9; // r15
  int v10; // eax
  unsigned __int16 *v11; // rax
  int v12; // ecx
  int v13; // edx
  int v14; // edi
  int v15; // eax
  int v16; // edi
  int v17; // eax
  int v18; // edi
  int v19; // eax
  HKEY v20; // rcx
  LSTATUS v21; // eax
  int v22; // edi
  int v23; // r14d
  HKEY v24; // rcx
  LSTATUS v25; // eax
  DWORD v26; // eax
  int v27; // edi
  int v28; // eax
  int v29; // edi
  int v30; // eax
  unsigned __int16 *v31; // rax
  int v32; // r8d
  int v33; // ecx
  DWORD Type; // [rsp+30h] [rbp-50h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-4Ch] BYREF
  BYTE Data[4]; // [rsp+38h] [rbp-48h] BYREF
  unsigned int v38; // [rsp+3Ch] [rbp-44h] BYREF
  unsigned int v39; // [rsp+40h] [rbp-40h] BYREF
  unsigned int v40; // [rsp+44h] [rbp-3Ch] BYREF
  unsigned int v41; // [rsp+48h] [rbp-38h] BYREF
  unsigned __int16 *v42; // [rsp+50h] [rbp-30h] BYREF
  unsigned __int16 *v43; // [rsp+58h] [rbp-28h] BYREF
  unsigned __int16 *v44; // [rsp+60h] [rbp-20h] BYREF
  unsigned __int16 *v45; // [rsp+68h] [rbp-18h] BYREF
  unsigned __int64 v46; // [rsp+70h] [rbp-10h] BYREF
  unsigned __int64 v47; // [rsp+78h] [rbp-8h] BYREF
  unsigned int v48; // [rsp+D0h] [rbp+50h] BYREF
  unsigned int v49; // [rsp+D8h] [rbp+58h] BYREF

  *a3 = 1;
  v3 = (CUwfStaticVolumeConfiguration *)((char *)this + 16);
  v43 = 0;
  v44 = 0;
  v49 = 0;
  v48 = 0;
  v39 = 0;
  v38 = 0;
  v41 = 0;
  v6 = 0;
  v40 = 0;
  v47 = 0;
  v46 = 0;
  v45 = 0;
  v42 = 0;
  v7 = CUwfRegKey::QuerySzValue((CUwfStaticVolumeConfiguration *)((char *)this + 16), L"DriveLetter", &v43);
  v8 = v7 == -2147024894;
  if ( (int)(v7 + 0x80000000) >= 0 && v7 != -2147024894 )
    goto LABEL_77;
  v9 = (struct CUwfStaticVolumeConfiguration *)((char *)a2 + 16);
  v10 = CUwfRegKey::QuerySzValue((struct CUwfStaticVolumeConfiguration *)((char *)a2 + 16), L"DriveLetter", &v44);
  v7 = v10;
  if ( v10 == -2147024894 )
  {
    ++v8;
    v7 = 0;
  }
  else if ( v10 < 0 )
  {
    goto LABEL_77;
  }
  if ( v8 == 1 )
    goto LABEL_76;
  if ( !v8 )
  {
    v11 = v43;
    do
    {
      v12 = *(unsigned __int16 *)((char *)v11 + (char *)v44 - (char *)v43);
      v13 = *v11 - v12;
      if ( v13 )
        break;
      ++v11;
    }
    while ( v12 );
    if ( v13 )
      goto LABEL_76;
  }
  v7 = CUwfRegKey::QueryDWORDValue(v3, L"DiskNumber", &v49);
  v14 = v7 == -2147024894;
  if ( (int)(v7 + 0x80000000) >= 0 && v7 != -2147024894 )
    goto LABEL_77;
  v15 = CUwfRegKey::QueryDWORDValue(v9, L"DiskNumber", &v48);
  v7 = v15;
  if ( v15 == -2147024894 )
  {
    ++v14;
    v7 = 0;
  }
  else if ( v15 < 0 )
  {
    goto LABEL_77;
  }
  if ( v14 == 1 || v49 != v48 )
    goto LABEL_76;
  v7 = CUwfRegKey::QueryDWORDValue(v3, L"DiskSignature", &v39);
  v16 = v7 == -2147024894;
  if ( (int)(v7 + 0x80000000) >= 0 && v7 != -2147024894 )
    goto LABEL_77;
  v17 = CUwfRegKey::QueryDWORDValue(v9, L"DiskSignature", &v38);
  v7 = v17;
  if ( v17 == -2147024894 )
  {
    ++v16;
    v7 = 0;
  }
  else if ( v17 < 0 )
  {
    goto LABEL_77;
  }
  if ( v16 == 1 || v39 != v38 )
    goto LABEL_76;
  v7 = CUwfRegKey::QueryDWORDValue(v3, L"PartitionNumber", &v41);
  v18 = v7 == -2147024894;
  if ( (int)(v7 + 0x80000000) >= 0 && v7 != -2147024894 )
    goto LABEL_77;
  v19 = CUwfRegKey::QueryDWORDValue(v9, L"PartitionNumber", &v40);
  v7 = v19;
  if ( v19 == -2147024894 )
  {
    ++v18;
    v7 = 0;
  }
  else if ( v19 < 0 )
  {
    goto LABEL_77;
  }
  if ( v18 == 1 || v41 != v40 )
  {
LABEL_76:
    *a3 = 0;
    goto LABEL_77;
  }
  v20 = *(HKEY *)v3;
  *(_DWORD *)Data = 0;
  Type = 0;
  cbData = 4;
  v21 = RegQueryValueExW(v20, L"PartitionStyle", 0, &Type, Data, &cbData);
  v7 = v21;
  if ( !v21 )
  {
    if ( Type != 4 )
      goto LABEL_40;
    if ( cbData != 4 )
      goto LABEL_42;
    goto LABEL_43;
  }
  if ( v21 > 0 )
    v7 = (unsigned __int16)v21 | 0x80070000;
  if ( v7 >= 0 )
  {
LABEL_43:
    v23 = *(_DWORD *)Data;
    v22 = 0;
    goto LABEL_44;
  }
  v22 = v7 == -2147024894;
  if ( v7 != -2147024894 )
    goto LABEL_77;
  v23 = 0;
LABEL_44:
  v24 = *(HKEY *)v9;
  Type = 0;
  *(_DWORD *)Data = 0;
  cbData = 4;
  v25 = RegQueryValueExW(v24, L"PartitionStyle", 0, (LPDWORD)Data, (LPBYTE)&Type, &cbData);
  v7 = v25;
  if ( !v25 )
  {
    if ( *(_DWORD *)Data == 4 )
    {
      v7 = 0;
      if ( cbData == 4 )
        goto LABEL_52;
LABEL_42:
      v7 = -2147024883;
      goto LABEL_77;
    }
LABEL_40:
    v7 = -2147023267;
    goto LABEL_77;
  }
  if ( v25 > 0 )
    v7 = (unsigned __int16)v25 | 0x80070000;
  if ( v7 < 0 )
  {
    if ( v7 != -2147024894 )
      goto LABEL_77;
    ++v22;
    v7 = 0;
    v26 = 0;
    goto LABEL_53;
  }
LABEL_52:
  v26 = Type;
LABEL_53:
  if ( v22 == 1 || v23 != v26 )
    goto LABEL_76;
  v7 = CUwfRegKey::QueryQWORDValue(v3, L"PartitionOffset", &v47);
  v27 = v7 == -2147024894;
  if ( (int)(v7 + 0x80000000) >= 0 && v7 != -2147024894 )
    goto LABEL_77;
  v28 = CUwfRegKey::QueryQWORDValue(v9, L"PartitionOffset", &v46);
  v7 = v28;
  if ( v28 == -2147024894 )
  {
    ++v27;
    v7 = 0;
  }
  else if ( v28 < 0 )
  {
    goto LABEL_77;
  }
  if ( v27 == 1 || v47 != v46 )
    goto LABEL_76;
  v7 = CUwfRegKey::QuerySzValue(v3, L"PartitionGuid", &v45);
  v29 = v7 == -2147024894;
  if ( (int)(v7 + 0x80000000) < 0 || v7 == -2147024894 )
  {
    v30 = CUwfRegKey::QuerySzValue(v9, L"PartitionGuid", &v42);
    v7 = v30;
    if ( v30 == -2147024894 )
    {
      ++v29;
      v7 = 0;
    }
    else if ( v30 < 0 )
    {
      v6 = v42;
      goto LABEL_77;
    }
    v6 = v42;
    if ( v29 == 1 )
      goto LABEL_74;
    if ( v29 )
      goto LABEL_73;
    v31 = v45;
    do
    {
      v32 = *(unsigned __int16 *)((char *)v31 + (char *)v42 - (char *)v45);
      v33 = *v31 - v32;
      if ( v33 )
        break;
      ++v31;
    }
    while ( v32 );
    if ( v33 )
LABEL_74:
      *a3 = 0;
    else
LABEL_73:
      v7 = 0;
  }
LABEL_77:
  operator delete[](v43);
  operator delete[](v44);
  operator delete[](v45);
  operator delete[](v6);
  if ( v7 < 0 )
    *a3 = 0;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000658c  mov     [rsp-38h+arg_0], rbx
0x180006591  push    rbp
0x180006592  push    rsi
0x180006593  push    rdi
0x180006594  push    r12
0x180006596  push    r13
0x180006598  push    r14
0x18000659a  push    r15
0x18000659c  mov     rbp, rsp
0x18000659f  sub     rsp, 80h
0x1800065a6  xor     edi, edi
0x1800065a8  mov     byte ptr [r8], 1
0x1800065ac  lea     r12, [rcx+10h]
0x1800065b0  mov     [rbp+var_28], rdi
0x1800065b4  mov     rsi, r8
0x1800065b7  mov     [rbp+var_20], rdi
0x1800065bb  mov     r14, rdx
0x1800065be  mov     [rbp+arg_18], edi
0x1800065c1  mov     rcx, r12; this
0x1800065c4  mov     [rbp+arg_10], edi
0x1800065c7  lea     r8, [rbp+var_28]; unsigned __int16 **
0x1800065cb  mov     [rbp+var_40], edi
0x1800065ce  lea     rdx, aDriveletter; "DriveLetter"
0x1800065d5  mov     [rbp+var_44], edi
0x1800065d8  mov     [rbp+var_38], edi
0x1800065db  mov     r13d, edi
0x1800065de  mov     [rbp+var_3C], edi
0x1800065e1  mov     [rbp+var_8], rdi
0x1800065e5  mov     [rbp+var_10], rdi
0x1800065e9  mov     [rbp+var_18], rdi
0x1800065ed  mov     [rbp+var_30], rdi
0x1800065f1  call    ?QuerySzValue@CUwfRegKey@@QEAAJPEBGPEAPEAG@Z; CUwfRegKey::QuerySzValue(ushort const *,ushort * *)
0x1800065f6  mov     ebx, eax
0x1800065f8  mov     edx, 80000000h
0x1800065fd  mov     ecx, 80070002h
0x180006602  cmp     eax, ecx
0x180006604  setz    dil
0x180006608  add     eax, edx
0x18000660a  test    edx, eax
0x18000660c  jnz     short loc_180006616
0x18000660e  cmp     ebx, ecx
0x180006610  jnz     loc_1800069EA
0x180006616  lea     r15, [r14+10h]
0x18000661a  mov     rcx, r15; this
0x18000661d  lea     r8, [rbp+var_20]; unsigned __int16 **
0x180006621  lea     rdx, aDriveletter; "DriveLetter"
0x180006628  call    ?QuerySzValue@CUwfRegKey@@QEAAJPEBGPEAPEAG@Z; CUwfRegKey::QuerySzValue(ushort const *,ushort * *)
0x18000662d  mov     ebx, eax
0x18000662f  mov     r14d, 80070002h
0x180006635  cmp     eax, r14d
0x180006638  jnz     short loc_180006640
0x18000663a  inc     edi
0x18000663c  xor     ebx, ebx
0x18000663e  jmp     short loc_180006648
0x180006640  test    eax, eax
0x180006642  js      loc_1800069EA
0x180006648  cmp     edi, 1
0x18000664b  jz      loc_1800069E7
0x180006651  test    edi, edi
0x180006653  jnz     short loc_18000667C
0x180006655  mov     rax, [rbp+var_28]
0x180006659  mov     r8, [rbp+var_20]
0x18000665d  sub     r8, rax
0x180006660  movzx   edx, word ptr [rax]
0x180006663  movzx   ecx, word ptr [rax+r8]
0x180006668  sub     edx, ecx
0x18000666a  jnz     short loc_180006674
0x18000666c  add     rax, 2
0x180006670  test    ecx, ecx
0x180006672  jnz     short loc_180006660
0x180006674  test    edx, edx
0x180006676  jnz     loc_1800069E7
0x18000667c  lea     r8, [rbp+arg_18]; unsigned int *
0x180006680  mov     rcx, r12; this
0x180006683  lea     rdx, aDisknumber; "DiskNumber"
0x18000668a  call    ?QueryDWORDValue@CUwfRegKey@@QEAAJPEBGPEAK@Z; CUwfRegKey::QueryDWORDValue(ushort const *,ulong *)
0x18000668f  mov     ebx, eax
0x180006691  xor     edi, edi
0x180006693  mov     ecx, 80000000h
0x180006698  cmp     eax, r14d
0x18000669b  setz    dil
0x18000669f  add     eax, ecx
0x1800066a1  test    ecx, eax
0x1800066a3  jnz     short loc_1800066AE
0x1800066a5  cmp     ebx, r14d
0x1800066a8  jnz     loc_1800069EA
0x1800066ae  lea     r8, [rbp+arg_10]; unsigned int *
0x1800066b2  mov     rcx, r15; this
0x1800066b5  lea     rdx, aDisknumber; "DiskNumber"
0x1800066bc  call    ?QueryDWORDValue@CUwfRegKey@@QEAAJPEBGPEAK@Z; CUwfRegKey::QueryDWORDValue(ushort const *,ulong *)
0x1800066c1  mov     ebx, eax
0x1800066c3  cmp     eax, r14d
0x1800066c6  jnz     short loc_1800066CE
0x1800066c8  inc     edi
0x1800066ca  xor     ebx, ebx
0x1800066cc  jmp     short loc_1800066D6
0x1800066ce  test    eax, eax
0x1800066d0  js      loc_1800069EA
0x1800066d6  cmp     edi, 1
0x1800066d9  jz      loc_1800069E7
0x1800066df  mov     eax, [rbp+arg_10]
0x1800066e2  cmp     [rbp+arg_18], eax
0x1800066e5  jnz     loc_1800069E7
0x1800066eb  lea     r8, [rbp+var_40]; unsigned int *
0x1800066ef  mov     rcx, r12; this
0x1800066f2  lea     rdx, aDisksignature; "DiskSignature"
0x1800066f9  call    ?QueryDWORDValue@CUwfRegKey@@QEAAJPEBGPEAK@Z; CUwfRegKey::QueryDWORDValue(ushort const *,ulong *)
0x1800066fe  mov     ebx, eax
0x180006700  xor     edi, edi
0x180006702  mov     ecx, 80000000h
0x180006707  cmp     eax, r14d
0x18000670a  setz    dil
0x18000670e  add     eax, ecx
0x180006710  test    ecx, eax
0x180006712  jnz     short loc_18000671D
0x180006714  cmp     ebx, r14d
0x180006717  jnz     loc_1800069EA
0x18000671d  lea     r8, [rbp+var_44]; unsigned int *
0x180006721  mov     rcx, r15; this
0x180006724  lea     rdx, aDisksignature; "DiskSignature"
0x18000672b  call    ?QueryDWORDValue@CUwfRegKey@@QEAAJPEBGPEAK@Z; CUwfRegKey::QueryDWORDValue(ushort const *,ulong *)
0x180006730  mov     ebx, eax
0x180006732  cmp     eax, r14d
0x180006735  jnz     short loc_18000673D
0x180006737  inc     edi
0x180006739  xor     ebx, ebx
0x18000673b  jmp     short loc_180006745
0x18000673d  test    eax, eax
0x18000673f  js      loc_1800069EA
0x180006745  cmp     edi, 1
0x180006748  jz      loc_1800069E7
0x18000674e  mov     eax, [rbp+var_44]
0x180006751  cmp     [rbp+var_40], eax
0x180006754  jnz     loc_1800069E7
0x18000675a  lea     r8, [rbp+var_38]; unsigned int *
0x18000675e  mov     rcx, r12; this
0x180006761  lea     rdx, aPartitionnumbe; "PartitionNumber"
0x180006768  call    ?QueryDWORDValue@CUwfRegKey@@QEAAJPEBGPEAK@Z; CUwfRegKey::QueryDWORDValue(ushort const *,ulong *)
0x18000676d  mov     ebx, eax
0x18000676f  xor     edi, edi
0x180006771  mov     ecx, 80000000h
0x180006776  cmp     eax, r14d
0x180006779  setz    dil
0x18000677d  add     eax, ecx
0x18000677f  test    ecx, eax
0x180006781  jnz     short loc_18000678C
0x180006783  cmp     ebx, r14d
0x180006786  jnz     loc_1800069EA
0x18000678c  lea     r8, [rbp+var_3C]; unsigned int *
0x180006790  mov     rcx, r15; this
0x180006793  lea     rdx, aPartitionnumbe; "PartitionNumber"
0x18000679a  call    ?QueryDWORDValue@CUwfRegKey@@QEAAJPEBGPEAK@Z; CUwfRegKey::QueryDWORDValue(ushort const *,ulong *)
0x18000679f  mov     ebx, eax
0x1800067a1  cmp     eax, r14d
0x1800067a4  jnz     short loc_1800067AC
0x1800067a6  inc     edi
0x1800067a8  xor     ebx, ebx
0x1800067aa  jmp     short loc_1800067B4
0x1800067ac  test    eax, eax
0x1800067ae  js      loc_1800069EA
0x1800067b4  cmp     edi, 1
0x1800067b7  jz      loc_1800069E7
0x1800067bd  mov     eax, [rbp+var_3C]
0x1800067c0  cmp     [rbp+var_38], eax
0x1800067c3  jnz     loc_1800069E7
0x1800067c9  mov     rcx, [r12]; hKey
0x1800067cd  lea     rax, [rbp+cbData]
0x1800067d1  mov     [rsp+80h+lpcbData], rax; lpcbData
0x1800067d6  lea     r9, [rbp+Type]; lpType
0x1800067da  lea     rax, [rbp+Data]
0x1800067de  mov     dword ptr [rbp+Data], r13d
0x1800067e2  xor     r8d, r8d; lpReserved
0x1800067e5  mov     [rsp+80h+lpData], rax; lpData
0x1800067ea  lea     rdx, aPartitionstyle; "PartitionStyle"
0x1800067f1  mov     [rbp+Type], r13d
0x1800067f5  mov     [rbp+cbData], 4
0x1800067fc  call    cs:__imp_RegQueryValueExW
0x180006802  mov     ebx, eax
0x180006804  test    eax, eax
0x180006806  jz      short loc_18000682B
0x180006808  jle     short loc_180006813
0x18000680a  movzx   ebx, ax
0x18000680d  or      ebx, 80070000h
0x180006813  test    ebx, ebx
0x180006815  jns     short loc_18000684B
0x180006817  xor     edi, edi
0x180006819  cmp     ebx, r14d
0x18000681c  setz    dil
0x180006820  jnz     loc_1800069EA
0x180006826  xor     r14d, r14d
0x180006829  jmp     short loc_180006851
0x18000682b  cmp     [rbp+Type], 4
0x18000682f  jz      short loc_18000683B
0x180006831  mov     ebx, 8007065Dh
0x180006836  jmp     loc_1800069EA
0x18000683b  cmp     [rbp+cbData], 4
0x18000683f  jz      short loc_18000684B
0x180006841  mov     ebx, 8007000Dh
0x180006846  jmp     loc_1800069EA
0x18000684b  mov     r14d, dword ptr [rbp+Data]
0x18000684f  xor     edi, edi
0x180006851  mov     rcx, [r15]; hKey
0x180006854  lea     rax, [rbp+cbData]
0x180006858  mov     [rsp+80h+lpcbData], rax; lpcbData
0x18000685d  lea     r9, [rbp+Data]; lpType
0x180006861  lea     rax, [rbp+Type]
0x180006865  mov     [rbp+Type], r13d
0x180006869  xor     r8d, r8d; lpReserved
0x18000686c  mov     [rsp+80h+lpData], rax; lpData
0x180006871  lea     rdx, aPartitionstyle; "PartitionStyle"
0x180006878  mov     dword ptr [rbp+Data], r13d
0x18000687c  mov     [rbp+cbData], 4
0x180006883  call    cs:__imp_RegQueryValueExW
0x180006889  mov     ebx, eax
0x18000688b  test    eax, eax
0x18000688d  jz      short loc_1800068B3
0x18000688f  jle     short loc_18000689A
0x180006891  movzx   ebx, ax
0x180006894  or      ebx, 80070000h
0x18000689a  test    ebx, ebx
0x18000689c  jns     short loc_1800068C9
0x18000689e  mov     ecx, 80070002h
0x1800068a3  cmp     ebx, ecx
0x1800068a5  jnz     loc_1800069EA
0x1800068ab  inc     edi
0x1800068ad  xor     ebx, ebx
0x1800068af  xor     eax, eax
0x1800068b1  jmp     short loc_1800068CC
0x1800068b3  cmp     dword ptr [rbp+Data], 4
0x1800068b7  jnz     loc_180006831
0x1800068bd  xor     ebx, ebx
0x1800068bf  cmp     [rbp+cbData], 4
0x1800068c3  jnz     loc_180006841
0x1800068c9  mov     eax, [rbp+Type]
0x1800068cc  cmp     edi, 1
0x1800068cf  jz      loc_1800069E7
0x1800068d5  cmp     r14d, eax
0x1800068d8  jnz     loc_1800069E7
0x1800068de  lea     r8, [rbp+var_8]; unsigned __int64 *
0x1800068e2  mov     rcx, r12; this
0x1800068e5  lea     rdx, aPartitionoffse; "PartitionOffset"
0x1800068ec  call    ?QueryQWORDValue@CUwfRegKey@@QEAAJPEBGPEA_K@Z; CUwfRegKey::QueryQWORDValue(ushort const *,unsigned __int64 *)
0x1800068f1  mov     ebx, eax
0x1800068f3  xor     edi, edi
0x1800068f5  mov     ecx, 80000000h
0x1800068fa  mov     r14d, 80070002h
0x180006900  cmp     eax, r14d
0x180006903  setz    dil
0x180006907  add     eax, ecx
0x180006909  test    ecx, eax
0x18000690b  jnz     short loc_180006916
0x18000690d  cmp     ebx, r14d
0x180006910  jnz     loc_1800069EA
0x180006916  lea     r8, [rbp+var_10]; unsigned __int64 *
0x18000691a  mov     rcx, r15; this
0x18000691d  lea     rdx, aPartitionoffse; "PartitionOffset"
0x180006924  call    ?QueryQWORDValue@CUwfRegKey@@QEAAJPEBGPEA_K@Z; CUwfRegKey::QueryQWORDValue(ushort const *,unsigned __int64 *)
0x180006929  mov     ebx, eax
0x18000692b  cmp     eax, r14d
0x18000692e  jnz     short loc_180006936
0x180006930  inc     edi
0x180006932  xor     ebx, ebx
0x180006934  jmp     short loc_18000693E
0x180006936  test    eax, eax
0x180006938  js      loc_1800069EA
0x18000693e  cmp     edi, 1
0x180006941  jz      loc_1800069E7
0x180006947  mov     rax, [rbp+var_10]
0x18000694b  cmp     [rbp+var_8], rax
0x18000694f  jnz     loc_1800069E7
0x180006955  lea     r8, [rbp+var_18]; unsigned __int16 **
0x180006959  mov     rcx, r12; this
0x18000695c  lea     rdx, aPartitionguid; "PartitionGuid"
0x180006963  call    ?QuerySzValue@CUwfRegKey@@QEAAJPEBGPEAPEAG@Z; CUwfRegKey::QuerySzValue(ushort const *,ushort * *)
0x180006968  mov     ebx, eax
0x18000696a  xor     edi, edi
0x18000696c  mov     ecx, 80000000h
0x180006971  cmp     eax, r14d
0x180006974  setz    dil
0x180006978  add     eax, ecx
0x18000697a  test    ecx, eax
0x18000697c  jnz     short loc_180006983
0x18000697e  cmp     ebx, r14d
0x180006981  jnz     short loc_1800069EA
0x180006983  lea     r8, [rbp+var_30]; unsigned __int16 **
0x180006987  mov     rcx, r15; this
0x18000698a  lea     rdx, aPartitionguid; "PartitionGuid"
0x180006991  call    ?QuerySzValue@CUwfRegKey@@QEAAJPEBGPEAPEAG@Z; CUwfRegKey::QuerySzValue(ushort const *,ushort * *)
0x180006996  mov     ebx, eax
0x180006998  cmp     eax, r14d
0x18000699b  jnz     short loc_1800069A3
0x18000699d  inc     edi
0x18000699f  xor     ebx, ebx
0x1800069a1  jmp     short loc_1800069A7
0x1800069a3  test    eax, eax
0x1800069a5  js      short loc_1800069E1
0x1800069a7  mov     r13, [rbp+var_30]
0x1800069ab  cmp     edi, 1
0x1800069ae  jz      short loc_1800069DC
0x1800069b0  test    edi, edi
  ... truncated ...
```
