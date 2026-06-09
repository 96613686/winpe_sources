# CUwfStaticVolumeConfiguration::CompareEssentialValues(CUwfStaticVolumeConfiguration &,bool *)

- ea: `0x18000630c`
- end: `0x180006584`
- name: `?CompareEssentialValues@CUwfStaticVolumeConfiguration@@AEAAJAEAV1@PEA_N@Z`
- size: `632`
- prototype: `__int64 __fastcall(CUwfStaticVolumeConfiguration *__hidden this, struct CUwfStaticVolumeConfiguration *, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180006290`

## callees

- `0x18000630c`
- `0x18000e0f0`
- `0x18000e170`
- `0x18000e320`
- `0x180011b20`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180006541`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000654a`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180006554`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000655d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180006541`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000654a`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180006554`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000655d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180006435`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000648c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180006435`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000648c`

## pseudocode

```c
__int64 __fastcall CUwfStaticVolumeConfiguration::CompareEssentialValues(
        CUwfStaticVolumeConfiguration *this,
        struct CUwfStaticVolumeConfiguration *a2,
        bool *a3)
{
  CUwfRegKey *v3; // r13
  void *v6; // r14
  struct _MULTISZ *v7; // rsi
  signed int SzValue; // ebx
  CUwfRegKey *v9; // r15
  unsigned __int16 *v10; // rax
  int v11; // r8d
  int v12; // ecx
  HKEY v13; // rcx
  LSTATUS v14; // eax
  HKEY v15; // rcx
  bool v16; // r12
  LSTATUS v17; // eax
  DWORD Type; // [rsp+30h] [rbp-30h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-2Ch] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-28h] BYREF
  struct _MULTISZ *v22; // [rsp+40h] [rbp-20h] BYREF
  unsigned __int16 *v23; // [rsp+48h] [rbp-18h] BYREF
  struct _MULTISZ *v24; // [rsp+50h] [rbp-10h] BYREF
  unsigned int v25; // [rsp+B0h] [rbp+50h] BYREF
  unsigned int v26; // [rsp+B8h] [rbp+58h] BYREF

  *a3 = 1;
  v3 = (CUwfStaticVolumeConfiguration *)((char *)this + 16);
  v23 = 0;
  *(_QWORD *)Data = 0;
  v26 = 0;
  v25 = 0;
  v24 = 0;
  v22 = 0;
  v6 = 0;
  v7 = 0;
  SzValue = CUwfRegKey::QuerySzValue((CUwfStaticVolumeConfiguration *)((char *)this + 16), L"VolumeName", &v23);
  if ( SzValue < 0 )
    goto LABEL_33;
  v9 = (struct CUwfStaticVolumeConfiguration *)((char *)a2 + 16);
  SzValue = CUwfRegKey::QuerySzValue(v9, L"VolumeName", (unsigned __int16 **)Data);
  v6 = *(void **)Data;
  if ( SzValue < 0 )
    goto LABEL_33;
  v10 = v23;
  do
  {
    v11 = *(unsigned __int16 *)((char *)v10 + *(_QWORD *)Data - (_QWORD)v23);
    v12 = *v10 - v11;
    if ( v12 )
      break;
    ++v10;
  }
  while ( v11 );
  if ( v12 )
    goto LABEL_32;
  SzValue = CUwfRegKey::QueryDWORDValue(v3, L"Binding", &v26);
  if ( SzValue < 0 )
    goto LABEL_33;
  SzValue = CUwfRegKey::QueryDWORDValue(v9, L"Binding", &v25);
  if ( SzValue < 0 )
    goto LABEL_33;
  if ( v26 != v25 )
  {
LABEL_32:
    *a3 = 0;
    goto LABEL_33;
  }
  v13 = *(HKEY *)v3;
  *(_DWORD *)Data = 0;
  Type = 0;
  cbData = 4;
  v14 = RegQueryValueExW(v13, L"VolumeEnabled", 0, &Type, Data, &cbData);
  SzValue = v14;
  if ( v14 )
  {
    if ( v14 > 0 )
      SzValue = (unsigned __int16)v14 | 0x80070000;
    if ( SzValue < 0 )
      goto LABEL_33;
  }
  else
  {
    if ( Type != 4 )
    {
      SzValue = -2147023267;
      goto LABEL_33;
    }
    if ( cbData != 4 )
    {
      SzValue = -2147024883;
      goto LABEL_33;
    }
  }
  v15 = *(HKEY *)v9;
  v16 = *(_DWORD *)Data != 0;
  Type = 0;
  *(_DWORD *)Data = 0;
  cbData = 4;
  v17 = RegQueryValueExW(v15, L"VolumeEnabled", 0, (LPDWORD)Data, (LPBYTE)&Type, &cbData);
  SzValue = v17;
  if ( v17 )
  {
    if ( v17 > 0 )
      SzValue = (unsigned __int16)v17 | 0x80070000;
    if ( SzValue < 0 )
      goto LABEL_33;
  }
  else
  {
    if ( *(_DWORD *)Data != 4 )
    {
      SzValue = -2147023267;
      goto LABEL_33;
    }
    if ( cbData != 4 )
    {
      SzValue = -2147024883;
      goto LABEL_33;
    }
  }
  if ( v16 != (Type != 0) )
    *a3 = 0;
  SzValue = CUwfRegKey::QueryMultiSzValue(v3, L"FileExceptionsUserDefined", &v24);
  if ( SzValue >= 0 )
  {
    SzValue = CUwfRegKey::QueryMultiSzValue(v9, L"FileExceptionsUserDefined", &v22);
    v7 = v22;
    if ( SzValue >= 0 )
    {
      if ( (unsigned int)MultiSzCompare(v24, v22) )
        goto LABEL_32;
    }
  }
LABEL_33:
  operator delete[](v23);
  operator delete[](v6);
  operator delete[](v24);
  operator delete[](v7);
  if ( SzValue < 0 )
    *a3 = 0;
  return (unsigned int)SzValue;
}

```

## disassembly

```asm
0x18000630c  mov     [rsp-38h+arg_0], rbx
0x180006311  push    rbp
0x180006312  push    rsi
0x180006313  push    rdi
0x180006314  push    r12
0x180006316  push    r13
0x180006318  push    r14
0x18000631a  push    r15
0x18000631c  mov     rbp, rsp
0x18000631f  sub     rsp, 60h
0x180006323  xor     r12d, r12d
0x180006326  mov     byte ptr [r8], 1
0x18000632a  lea     r13, [rcx+10h]
0x18000632e  mov     [rbp+var_18], r12
0x180006332  mov     rdi, r8
0x180006335  mov     qword ptr [rbp+Data], r12
0x180006339  mov     r15, rdx
0x18000633c  mov     [rbp+arg_18], r12d
0x180006340  mov     rcx, r13; this
0x180006343  mov     [rbp+arg_10], r12d
0x180006347  lea     r8, [rbp+var_18]; unsigned __int16 **
0x18000634b  mov     [rbp+var_10], r12
0x18000634f  lea     rdx, aVolumename; "VolumeName"
0x180006356  mov     [rbp+var_20], r12
0x18000635a  mov     r14d, r12d
0x18000635d  mov     esi, r12d
0x180006360  call    ?QuerySzValue@CUwfRegKey@@QEAAJPEBGPEAPEAG@Z; CUwfRegKey::QuerySzValue(ushort const *,ushort * *)
0x180006365  mov     ebx, eax
0x180006367  test    eax, eax
0x180006369  js      loc_18000653D
0x18000636f  add     r15, 10h
0x180006373  lea     r8, [rbp+Data]; unsigned __int16 **
0x180006377  mov     rcx, r15; this
0x18000637a  lea     rdx, aVolumename; "VolumeName"
0x180006381  call    ?QuerySzValue@CUwfRegKey@@QEAAJPEBGPEAPEAG@Z; CUwfRegKey::QuerySzValue(ushort const *,ushort * *)
0x180006386  mov     ebx, eax
0x180006388  mov     r14, qword ptr [rbp+Data]
0x18000638c  test    eax, eax
0x18000638e  js      loc_18000653D
0x180006394  mov     rax, [rbp+var_18]
0x180006398  mov     rdx, r14
0x18000639b  sub     rdx, rax
0x18000639e  movzx   ecx, word ptr [rax]
0x1800063a1  movzx   r8d, word ptr [rax+rdx]
0x1800063a6  sub     ecx, r8d
0x1800063a9  jnz     short loc_1800063B4
0x1800063ab  add     rax, 2
0x1800063af  test    r8d, r8d
0x1800063b2  jnz     short loc_18000639E
0x1800063b4  test    ecx, ecx
0x1800063b6  jnz     loc_18000653A
0x1800063bc  lea     r8, [rbp+arg_18]; unsigned int *
0x1800063c0  mov     rcx, r13; this
0x1800063c3  lea     rdx, aBinding; "Binding"
0x1800063ca  call    ?QueryDWORDValue@CUwfRegKey@@QEAAJPEBGPEAK@Z; CUwfRegKey::QueryDWORDValue(ushort const *,ulong *)
0x1800063cf  mov     ebx, eax
0x1800063d1  test    eax, eax
0x1800063d3  js      loc_18000653D
0x1800063d9  lea     r8, [rbp+arg_10]; unsigned int *
0x1800063dd  mov     rcx, r15; this
0x1800063e0  lea     rdx, aBinding; "Binding"
0x1800063e7  call    ?QueryDWORDValue@CUwfRegKey@@QEAAJPEBGPEAK@Z; CUwfRegKey::QueryDWORDValue(ushort const *,ulong *)
0x1800063ec  mov     ebx, eax
0x1800063ee  test    eax, eax
0x1800063f0  js      loc_18000653D
0x1800063f6  mov     eax, [rbp+arg_10]
0x1800063f9  cmp     [rbp+arg_18], eax
0x1800063fc  jnz     loc_18000653A
0x180006402  mov     rcx, [r13+0]; hKey
0x180006406  lea     rax, [rbp+cbData]
0x18000640a  mov     [rsp+60h+lpcbData], rax; lpcbData
0x18000640f  lea     r9, [rbp+Type]; lpType
0x180006413  lea     rax, [rbp+Data]
0x180006417  mov     dword ptr [rbp+Data], r12d
0x18000641b  xor     r8d, r8d; lpReserved
0x18000641e  mov     [rsp+60h+lpData], rax; lpData
0x180006423  lea     rdx, ValueName; "VolumeEnabled"
0x18000642a  mov     [rbp+Type], r12d
0x18000642e  mov     [rbp+cbData], 4
0x180006435  call    cs:__imp_RegQueryValueExW
0x18000643b  mov     ebx, eax
0x18000643d  test    eax, eax
0x18000643f  jz      short loc_1800064BA
0x180006441  jle     short loc_18000644C
0x180006443  movzx   ebx, ax
0x180006446  or      ebx, 80070000h
0x18000644c  test    ebx, ebx
0x18000644e  js      loc_18000653D
0x180006454  cmp     dword ptr [rbp+Data], r12d
0x180006458  lea     rax, [rbp+cbData]
0x18000645c  mov     rcx, [r15]; hKey
0x18000645f  lea     r9, [rbp+Data]; lpType
0x180006463  mov     [rsp+60h+lpcbData], rax; lpcbData
0x180006468  lea     rdx, ValueName; "VolumeEnabled"
0x18000646f  setnz   r12b
0x180006473  mov     [rbp+Type], esi
0x180006476  lea     rax, [rbp+Type]
0x18000647a  mov     dword ptr [rbp+Data], esi
0x18000647d  xor     r8d, r8d; lpReserved
0x180006480  mov     [rsp+60h+lpData], rax; lpData
0x180006485  mov     [rbp+cbData], 4
0x18000648c  call    cs:__imp_RegQueryValueExW
0x180006492  mov     ebx, eax
0x180006494  test    eax, eax
0x180006496  jz      short loc_1800064D4
0x180006498  jle     short loc_1800064A3
0x18000649a  movzx   ebx, ax
0x18000649d  or      ebx, 80070000h
0x1800064a3  test    ebx, ebx
0x1800064a5  js      short loc_1800064EC
0x1800064a7  cmp     [rbp+Type], esi
0x1800064aa  setnz   al
0x1800064ad  cmp     r12b, al
0x1800064b0  jz      short loc_1800064F1
0x1800064b2  xor     r12d, r12d
0x1800064b5  mov     [rdi], r12b
0x1800064b8  jmp     short loc_1800064F4
0x1800064ba  cmp     [rbp+Type], 4
0x1800064be  jz      short loc_1800064C7
0x1800064c0  mov     ebx, 8007065Dh
0x1800064c5  jmp     short loc_18000653D
0x1800064c7  cmp     [rbp+cbData], 4
0x1800064cb  jz      short loc_180006454
0x1800064cd  mov     ebx, 8007000Dh
0x1800064d2  jmp     short loc_18000653D
0x1800064d4  cmp     dword ptr [rbp+Data], 4
0x1800064d8  jz      short loc_1800064E1
0x1800064da  mov     ebx, 8007065Dh
0x1800064df  jmp     short loc_1800064EC
0x1800064e1  cmp     [rbp+cbData], 4
0x1800064e5  jz      short loc_1800064A7
0x1800064e7  mov     ebx, 8007000Dh
0x1800064ec  xor     r12d, r12d
0x1800064ef  jmp     short loc_18000653D
0x1800064f1  xor     r12d, r12d
0x1800064f4  lea     r8, [rbp+var_10]; struct _MULTISZ **
0x1800064f8  mov     rcx, r13; this
0x1800064fb  lea     rdx, Value; "FileExceptionsUserDefined"
0x180006502  call    ?QueryMultiSzValue@CUwfRegKey@@QEAAJPEBGPEAPEAU_MULTISZ@@@Z; CUwfRegKey::QueryMultiSzValue(ushort const *,_MULTISZ * *)
0x180006507  mov     ebx, eax
0x180006509  test    eax, eax
0x18000650b  js      short loc_18000653D
0x18000650d  lea     r8, [rbp+var_20]; struct _MULTISZ **
0x180006511  mov     rcx, r15; this
0x180006514  lea     rdx, Value; "FileExceptionsUserDefined"
0x18000651b  call    ?QueryMultiSzValue@CUwfRegKey@@QEAAJPEBGPEAPEAU_MULTISZ@@@Z; CUwfRegKey::QueryMultiSzValue(ushort const *,_MULTISZ * *)
0x180006520  mov     ebx, eax
0x180006522  mov     rsi, [rbp+var_20]
0x180006526  test    eax, eax
0x180006528  js      short loc_18000653D
0x18000652a  mov     rcx, [rbp+var_10]
0x18000652e  mov     rdx, rsi
0x180006531  call    MultiSzCompare
0x180006536  test    eax, eax
0x180006538  jz      short loc_18000653D
0x18000653a  mov     [rdi], r12b
0x18000653d  mov     rcx, [rbp+var_18]
0x180006541  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180006547  mov     rcx, r14
0x18000654a  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180006550  mov     rcx, [rbp+var_10]
0x180006554  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000655a  mov     rcx, rsi
0x18000655d  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180006563  test    ebx, ebx
0x180006565  jns     short loc_18000656A
0x180006567  mov     [rdi], r12b
0x18000656a  mov     eax, ebx
0x18000656c  mov     rbx, [rsp+60h+arg_0]
0x180006574  add     rsp, 60h
0x180006578  pop     r15
0x18000657a  pop     r14
0x18000657c  pop     r13
0x18000657e  pop     r12
0x180006580  pop     rdi
0x180006581  pop     rsi
0x180006582  pop     rbp
0x180006583  retn
```
