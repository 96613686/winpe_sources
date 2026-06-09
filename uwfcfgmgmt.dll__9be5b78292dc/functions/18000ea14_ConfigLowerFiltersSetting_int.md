# ConfigLowerFiltersSetting(int)

- ea: `0x18000ea14`
- end: `0x18000edbd`
- name: `?ConfigLowerFiltersSetting@@YAJH@Z`
- size: `937`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000f258`
- `0x180019a30`

## callees

- `0x180001384`
- `0x180002692`
- `0x18000d5f0`
- `0x18000de30`
- `0x18000e4d0`
- `0x18000ea14`
- `0x18000f610`
- `0x180011a30`
- `0x180011b90`
- `0x180011c40`
- `0x180013100`
- `0x180013310`
- `0x1800139f0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000eb72`
- `msvcrt!_wcsicmp` at `0x18000eb72`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000eb34`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000ed8b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000ed94`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000eb34`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000ed8b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000ed94`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000ea95`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000eb09`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000ea95`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000eb09`

## pseudocode

```c
__int64 __fastcall ConfigLowerFiltersSetting(int a1)
{
  __int64 v2; // rdi
  struct _MULTISZ *v3; // r14
  signed int v4; // ebx
  LSTATUS ValueW; // eax
  bool v6; // cc
  void *pvData; // rsi
  _DWORD *v8; // rsi
  unsigned int v9; // ebx
  _QWORD *v10; // r9
  __int64 v11; // rax
  _WORD *v12; // rcx
  int v13; // r15d
  _DWORD *v14; // rcx
  unsigned int v15; // r9d
  unsigned int v16; // edx
  __int64 v17; // r8
  __int64 v18; // rcx
  unsigned int v19; // ebx
  __int64 v20; // rax
  __int64 v21; // r15
  __int64 v22; // rax
  int v23; // eax
  int v24; // eax
  _QWORD v26[2]; // [rsp+40h] [rbp-20h] BYREF
  char v27; // [rsp+50h] [rbp-10h]
  int v28; // [rsp+58h] [rbp-8h]
  DWORD pcbData; // [rsp+A8h] [rbp+48h] BYREF
  DWORD pdwType; // [rsp+B0h] [rbp+50h] BYREF
  HKEY hkey; // [rsp+B8h] [rbp+58h] BYREF

  hkey = 0;
  v2 = 0;
  v3 = 0;
  v4 = CUwfRegKey::Open(
         &hkey,
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Control\\Class\\{71A27CDD-812A-11D0-BEC7-08002BE2092F}",
         0x2001Fu);
  if ( v4 < 0 )
    goto LABEL_49;
  pdwType = 0;
  pcbData = 0;
  ValueW = RegGetValueW(hkey, 0, L"LowerFilters", 0x20u, &pdwType, 0, &pcbData);
  v4 = ValueW;
  v6 = ValueW <= 0;
  if ( ValueW )
  {
    pvData = 0;
LABEL_4:
    if ( !v6 )
      v4 = (unsigned __int16)ValueW | 0x80070000;
    goto LABEL_11;
  }
  pvData = operator new[](saturated_mul((unsigned __int64)pcbData >> 1, 2u));
  if ( !pvData )
  {
    v4 = -2147024882;
    goto LABEL_11;
  }
  ValueW = RegGetValueW(hkey, 0, L"LowerFilters", 0x20u, &pdwType, pvData, &pcbData);
  v4 = ValueW;
  v6 = ValueW <= 0;
  if ( ValueW )
    goto LABEL_4;
  v4 = -2147024882;
  v2 = MultiSzAlloc(pvData);
  if ( v2 )
    v4 = 0;
LABEL_11:
  operator delete[](pvData);
  if ( v4 < 0 )
    goto LABEL_49;
  if ( !v2 )
  {
LABEL_13:
    v4 = -2147467261;
    goto LABEL_49;
  }
  v8 = (_DWORD *)(v2 + 24);
  v9 = 0;
  if ( *(_DWORD *)(v2 + 24) )
  {
    while ( _wcsicmp(*(const wchar_t **)(*(_QWORD *)(v2 + 16) + 8LL * v9), L"uwfvol") )
    {
      if ( ++v9 >= *v8 )
        goto LABEL_31;
    }
    pcbData = 0;
    v4 = MultiSzFind((wchar_t *)L"uwfvol");
    if ( v4 < 0 )
      goto LABEL_49;
    v10 = *(_QWORD **)(v2 + 16);
    v11 = -1;
    v12 = (_WORD *)v10[pcbData];
    do
      ++v11;
    while ( v12[v11] );
    v13 = v11 + 1;
    if ( pcbData == *v8 - 1 )
    {
      *v12 = 0;
      v14 = (_DWORD *)(v2 + 8);
    }
    else
    {
      memmove_0(
        v12,
        (const void *)v10[pcbData + 1],
        2LL * (*(_DWORD *)(v2 + 8) - (unsigned int)(((__int64)v12 - *v10) >> 1) - v13));
      v15 = 1;
      v16 = 0;
      **(_QWORD **)(v2 + 16) = *(_QWORD *)v2;
      if ( *(_DWORD *)(v2 + 8) )
      {
        do
        {
          v14 = (_DWORD *)(v2 + 8);
          if ( v15 >= *v8 - 1 )
            break;
          v17 = v16 + 1;
          if ( !*(_WORD *)(*(_QWORD *)v2 + 2LL * v16) )
          {
            v18 = v15++;
            *(_QWORD *)(*(_QWORD *)(v2 + 16) + 8 * v18) = *(_QWORD *)v2 + 2 * v17;
          }
          ++v16;
          v14 = (_DWORD *)(v2 + 8);
        }
        while ( (unsigned int)v17 < *(_DWORD *)(v2 + 8) );
      }
      else
      {
        v14 = (_DWORD *)(v2 + 8);
      }
    }
    --*v8;
    *v14 -= v13;
  }
LABEL_31:
  if ( a1 )
  {
    v3 = (struct _MULTISZ *)MultiSzAlloc(L"uwfvol");
    if ( !v3 )
    {
LABEL_33:
      v4 = -2147024882;
      goto LABEL_49;
    }
    v19 = 0;
    if ( *v8 )
    {
      do
      {
        v20 = *(_QWORD *)(v2 + 16);
        v21 = *(_QWORD *)(v20 + 8LL * v19);
        if ( !v21 )
          goto LABEL_13;
        if ( (int)MultiSzFind(*(wchar_t **)(v20 + 8LL * v19)) >= 0 )
        {
          v4 = -2147024713;
          goto LABEL_49;
        }
        v22 = MultiSzReAlloc(v3, v21);
        if ( !v22 )
          goto LABEL_33;
        v3 = (struct _MULTISZ *)v22;
      }
      while ( ++v19 < *v8 );
    }
    v4 = CUwfRegKey::SetMultiSzValue((CUwfRegKey *)&hkey, L"LowerFilters", v3);
    if ( v4 < 0 )
      goto LABEL_49;
    v23 = FixupLowerFiltersSetting();
  }
  else
  {
    v23 = CUwfRegKey::SetMultiSzValue((CUwfRegKey *)&hkey, L"LowerFilters", (struct _MULTISZ *const)v2);
  }
  v4 = v23;
  if ( v23 >= 0 )
  {
    v26[1] = -1;
    v26[0] = &CUwfRegDevice::`vftable';
    v27 = 0;
    v28 = -2147019873;
    v24 = CDevice::Initialize((CDevice *)v26, L"\\\\.\\UwfregControl");
    v28 = v24;
    v4 = v24;
    if ( v24 == -2147024894 )
    {
      v4 = 0;
    }
    else if ( v24 >= 0 )
    {
      v4 = CUwfRegDevice::CommitRegistryValue(
             (CUwfRegDevice *)v26,
             L"HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Control\\Class\\{71A27CDD-812A-11D0-BEC7-08002BE2092F}",
             L"LowerFilters");
    }
    v26[0] = &CDevice::`vftable';
    CDevice::Close((CDevice *)v26);
  }
LABEL_49:
  operator delete[](v3);
  operator delete[]((void *)v2);
  CUwfRegKey::Close(&hkey);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000ea14  mov     [rsp-38h+arg_0], rbx
0x18000ea19  push    rbp
0x18000ea1a  push    rsi
0x18000ea1b  push    rdi
0x18000ea1c  push    r12
0x18000ea1e  push    r13
0x18000ea20  push    r14
0x18000ea22  push    r15
0x18000ea24  mov     rbp, rsp
0x18000ea27  sub     rsp, 60h
0x18000ea2b  xor     r13d, r13d
0x18000ea2e  lea     r8, aSystemCurrentc_8; "SYSTEM\\CurrentControlSet\\Control\\Cla"...
0x18000ea35  mov     r12d, ecx
0x18000ea38  mov     [rbp+hkey], r13
0x18000ea3c  lea     rcx, [rbp+hkey]; phkResult
0x18000ea40  mov     r9d, 2001Fh; samDesired
0x18000ea46  mov     rdx, 0FFFFFFFF80000002h; hKey
0x18000ea4d  mov     edi, r13d
0x18000ea50  mov     r14d, r13d
0x18000ea53  call    ?Open@CUwfRegKey@@QEAAJPEAUHKEY__@@PEBGK@Z; CUwfRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000ea58  mov     ebx, eax
0x18000ea5a  test    eax, eax
0x18000ea5c  js      loc_18000ED88
0x18000ea62  mov     rcx, [rbp+hkey]; hkey
0x18000ea66  lea     rax, [rbp+arg_8]
0x18000ea6a  mov     [rsp+60h+pcbData], rax; pcbData
0x18000ea6f  lea     r15d, [r13+20h]
0x18000ea73  lea     rax, [rbp+arg_10]
0x18000ea77  mov     [rsp+60h+pvData], r13; pvData
0x18000ea7c  mov     r9d, r15d; dwFlags
0x18000ea7f  mov     [rsp+60h+pdwType], rax; pdwType
0x18000ea84  lea     r8, aLowerfilters; "LowerFilters"
0x18000ea8b  mov     [rbp+arg_10], r13d
0x18000ea8f  xor     edx, edx; lpSubKey
0x18000ea91  mov     [rbp+arg_8], r13d
0x18000ea95  call    cs:__imp_RegGetValueW
0x18000ea9b  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000ea9f  mov     ebx, eax
0x18000eaa1  test    eax, eax
0x18000eaa3  jz      short loc_18000EAB9
0x18000eaa5  mov     esi, r13d
0x18000eaa8  jle     loc_18000EB31
0x18000eaae  movzx   ebx, ax
0x18000eab1  or      ebx, 80070000h
0x18000eab7  jmp     short loc_18000EB31
0x18000eab9  mov     ecx, [rbp+arg_8]
0x18000eabc  mov     eax, 2
0x18000eac1  shr     rcx, 1
0x18000eac4  mul     rcx
0x18000eac7  cmovb   rax, r8
0x18000eacb  mov     rcx, rax; unsigned __int64
0x18000eace  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000ead3  mov     rsi, rax
0x18000ead6  test    rax, rax
0x18000ead9  jnz     short loc_18000EAE2
0x18000eadb  mov     ebx, 8007000Eh
0x18000eae0  jmp     short loc_18000EB31
0x18000eae2  mov     rcx, [rbp+hkey]; hkey
0x18000eae6  lea     rax, [rbp+arg_8]
0x18000eaea  mov     [rsp+60h+pcbData], rax; pcbData
0x18000eaef  lea     r8, aLowerfilters; "LowerFilters"
0x18000eaf6  lea     rax, [rbp+arg_10]
0x18000eafa  mov     [rsp+60h+pvData], rsi; pvData
0x18000eaff  mov     r9d, r15d; dwFlags
0x18000eb02  mov     [rsp+60h+pdwType], rax; pdwType
0x18000eb07  xor     edx, edx; lpSubKey
0x18000eb09  call    cs:__imp_RegGetValueW
0x18000eb0f  mov     ebx, eax
0x18000eb11  test    eax, eax
0x18000eb13  jnz     short loc_18000EAA8
0x18000eb15  mov     edx, [rbp+arg_8]
0x18000eb18  mov     rcx, rsi; Src
0x18000eb1b  shr     edx, 1
0x18000eb1d  call    MultiSzAlloc
0x18000eb22  test    rax, rax
0x18000eb25  mov     ebx, 8007000Eh
0x18000eb2a  mov     rdi, rax
0x18000eb2d  cmovnz  ebx, r13d
0x18000eb31  mov     rcx, rsi
0x18000eb34  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000eb3a  test    ebx, ebx
0x18000eb3c  js      loc_18000ED88
0x18000eb42  test    rdi, rdi
0x18000eb45  jnz     short loc_18000EB51
0x18000eb47  mov     ebx, 80004003h
0x18000eb4c  jmp     loc_18000ED88
0x18000eb51  lea     rsi, [rdi+18h]
0x18000eb55  mov     ebx, r13d
0x18000eb58  cmp     [rsi], r13d
0x18000eb5b  jbe     loc_18000EC5C
0x18000eb61  mov     rcx, [rdi+10h]
0x18000eb65  lea     rdx, aUwfvol_0; "uwfvol"
0x18000eb6c  mov     eax, ebx
0x18000eb6e  mov     rcx, [rcx+rax*8]; String1
0x18000eb72  call    cs:__imp__wcsicmp
0x18000eb78  test    eax, eax
0x18000eb7a  jz      short loc_18000EB87
0x18000eb7c  inc     ebx
0x18000eb7e  cmp     ebx, [rsi]
0x18000eb80  jb      short loc_18000EB61
0x18000eb82  jmp     loc_18000EC5C
0x18000eb87  lea     r9, [rbp+arg_8]
0x18000eb8b  mov     [rbp+arg_8], r13d
0x18000eb8f  xor     r8d, r8d
0x18000eb92  lea     rcx, aUwfvol_0; "uwfvol"
0x18000eb99  mov     rdx, rdi
0x18000eb9c  call    MultiSzFind
0x18000eba1  mov     ebx, eax
0x18000eba3  test    eax, eax
0x18000eba5  js      loc_18000ED88
0x18000ebab  mov     r9, [rdi+10h]
0x18000ebaf  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000ebb3  mov     edx, [rbp+arg_8]
0x18000ebb6  mov     rcx, [r9+rdx*8]; void *
0x18000ebba  inc     rax
0x18000ebbd  cmp     [rcx+rax*2], r13w
0x18000ebc2  jnz     short loc_18000EBBA
0x18000ebc4  lea     r15d, [rax+1]
0x18000ebc8  mov     eax, [rsi]
0x18000ebca  dec     eax
0x18000ebcc  cmp     edx, eax
0x18000ebce  jnz     short loc_18000EBDA
0x18000ebd0  mov     [rcx], r13w
0x18000ebd4  lea     rcx, [rdi+8]
0x18000ebd8  jmp     short loc_18000EC57
0x18000ebda  mov     r8, rcx
0x18000ebdd  lea     rbx, [rdi+8]
0x18000ebe1  sub     r8, [r9]
0x18000ebe4  mov     eax, [rbx]
0x18000ebe6  sar     r8, 1
0x18000ebe9  sub     eax, r8d
0x18000ebec  sub     eax, r15d
0x18000ebef  mov     r8d, eax
0x18000ebf2  lea     eax, [rdx+1]
0x18000ebf5  add     r8, r8; Size
0x18000ebf8  mov     rdx, [r9+rax*8]; Src
0x18000ebfc  call    memmove_0
0x18000ec01  mov     rcx, [rdi+10h]
0x18000ec05  mov     r9d, 1
0x18000ec0b  mov     rax, [rdi]
0x18000ec0e  mov     edx, r13d
0x18000ec11  mov     [rcx], rax
0x18000ec14  cmp     [rbx], r13d
0x18000ec17  jbe     short loc_18000EC54
0x18000ec19  mov     eax, [rsi]
0x18000ec1b  mov     rcx, rbx
0x18000ec1e  dec     eax
0x18000ec20  cmp     r9d, eax
0x18000ec23  jnb     short loc_18000EC57
0x18000ec25  mov     r10, [rdi]
0x18000ec28  lea     r8d, [rdx+1]
0x18000ec2c  mov     ecx, edx
0x18000ec2e  cmp     r13w, [r10+rcx*2]
0x18000ec33  jnz     short loc_18000EC47
0x18000ec35  mov     rax, [rdi+10h]
0x18000ec39  lea     rdx, [r10+r8*2]
0x18000ec3d  mov     ecx, r9d
0x18000ec40  inc     r9d
0x18000ec43  mov     [rax+rcx*8], rdx
0x18000ec47  mov     edx, r8d
0x18000ec4a  mov     rcx, rbx
0x18000ec4d  cmp     edx, [rdi+8]
0x18000ec50  jb      short loc_18000EC19
0x18000ec52  jmp     short loc_18000EC57
0x18000ec54  mov     rcx, rbx
0x18000ec57  dec     dword ptr [rsi]
0x18000ec59  sub     [rcx], r15d
0x18000ec5c  test    r12d, r12d
0x18000ec5f  jz      loc_18000ECFF
0x18000ec65  mov     edx, 8
0x18000ec6a  lea     rcx, aUwfvol; "uwfvol"
0x18000ec71  call    MultiSzAlloc
0x18000ec76  mov     r14, rax
0x18000ec79  test    rax, rax
0x18000ec7c  jnz     short loc_18000EC88
0x18000ec7e  mov     ebx, 8007000Eh
0x18000ec83  jmp     loc_18000ED88
0x18000ec88  mov     ebx, r13d
0x18000ec8b  cmp     [rsi], r13d
0x18000ec8e  jbe     short loc_18000ECD1
0x18000ec90  mov     rax, [rdi+10h]
0x18000ec94  mov     ecx, ebx
0x18000ec96  mov     r15, [rax+rcx*8]
0x18000ec9a  test    r15, r15
0x18000ec9d  jz      loc_18000EB47
0x18000eca3  xor     r9d, r9d
0x18000eca6  xor     r8d, r8d
0x18000eca9  mov     rdx, r14
0x18000ecac  mov     rcx, r15; String2
0x18000ecaf  call    MultiSzFind
0x18000ecb4  test    eax, eax
0x18000ecb6  jns     short loc_18000ECF5
0x18000ecb8  mov     rdx, r15
0x18000ecbb  mov     rcx, r14
0x18000ecbe  call    MultiSzReAlloc
0x18000ecc3  test    rax, rax
0x18000ecc6  jz      short loc_18000EC7E
0x18000ecc8  mov     r14, rax
0x18000eccb  inc     ebx
0x18000eccd  cmp     ebx, [rsi]
0x18000eccf  jb      short loc_18000EC90
0x18000ecd1  mov     r8, r14; struct _MULTISZ *
0x18000ecd4  lea     rdx, aLowerfilters; "LowerFilters"
0x18000ecdb  lea     rcx, [rbp+hkey]; this
0x18000ecdf  call    ?SetMultiSzValue@CUwfRegKey@@QEAAJPEBGQEAU_MULTISZ@@@Z; CUwfRegKey::SetMultiSzValue(ushort const *,_MULTISZ * const)
0x18000ece4  mov     ebx, eax
0x18000ece6  test    eax, eax
0x18000ece8  js      loc_18000ED88
0x18000ecee  call    ?FixupLowerFiltersSetting@@YAJXZ; FixupLowerFiltersSetting(void)
0x18000ecf3  jmp     short loc_18000ED12
0x18000ecf5  mov     ebx, 800700B7h
0x18000ecfa  jmp     loc_18000ED88
0x18000ecff  mov     r8, rdi; struct _MULTISZ *
0x18000ed02  lea     rdx, aLowerfilters; "LowerFilters"
0x18000ed09  lea     rcx, [rbp+hkey]; this
0x18000ed0d  call    ?SetMultiSzValue@CUwfRegKey@@QEAAJPEBGQEAU_MULTISZ@@@Z; CUwfRegKey::SetMultiSzValue(ushort const *,_MULTISZ * const)
0x18000ed12  mov     ebx, eax
0x18000ed14  test    eax, eax
0x18000ed16  js      short loc_18000ED88
0x18000ed18  lea     rax, ??_7CUwfRegDevice@@6B@; const CUwfRegDevice::`vftable'
0x18000ed1f  mov     [rbp+var_18], 0FFFFFFFFFFFFFFFFh
0x18000ed27  lea     rdx, FileName; "\\\\.\\UwfregControl"
0x18000ed2e  mov     [rbp+var_20], rax
0x18000ed32  lea     rcx, [rbp+var_20]; this
0x18000ed36  mov     [rbp+var_10], r13b
0x18000ed3a  mov     [rbp+var_8], 8007139Fh
0x18000ed41  call    ?Initialize@CDevice@@QEAAJPEBG@Z; CDevice::Initialize(ushort const *)
0x18000ed46  mov     [rbp+var_8], eax
0x18000ed49  mov     ebx, eax
0x18000ed4b  cmp     eax, 80070002h
0x18000ed50  jnz     short loc_18000ED57
0x18000ed52  mov     ebx, r13d
0x18000ed55  jmp     short loc_18000ED74
0x18000ed57  lea     rcx, [rbp+var_20]; this
0x18000ed5b  test    eax, eax
0x18000ed5d  js      short loc_18000ED78
0x18000ed5f  lea     r8, aLowerfilters; "LowerFilters"
0x18000ed66  lea     rdx, aHkeyLocalMachi_3; "HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentCont"...
0x18000ed6d  call    ?CommitRegistryValue@CUwfRegDevice@@QEAAJPEBG0@Z; CUwfRegDevice::CommitRegistryValue(ushort const *,ushort const *)
0x18000ed72  mov     ebx, eax
0x18000ed74  lea     rcx, [rbp+var_20]; this
0x18000ed78  lea     rax, ??_7CDevice@@6B@; const CDevice::`vftable'
0x18000ed7f  mov     [rbp+var_20], rax
0x18000ed83  call    ?Close@CDevice@@QEAAXXZ; CDevice::Close(void)
0x18000ed88  mov     rcx, r14
0x18000ed8b  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000ed91  mov     rcx, rdi
0x18000ed94  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000ed9a  lea     rcx, [rbp+hkey]; this
0x18000ed9e  call    ?Close@CUwfRegKey@@QEAAJXZ; CUwfRegKey::Close(void)
0x18000eda3  mov     eax, ebx
0x18000eda5  mov     rbx, [rsp+60h+arg_0]
0x18000edad  add     rsp, 60h
0x18000edb1  pop     r15
0x18000edb3  pop     r14
0x18000edb5  pop     r13
0x18000edb7  pop     r12
0x18000edb9  pop     rdi
0x18000edba  pop     rsi
0x18000edbb  pop     rbp
0x18000edbc  retn
```
