# CUwfStaticConfiguration::set_OverlayType(_UWF_CONFIG_OVERLAY_TYPE)

- ea: `0x18000c300`
- end: `0x18000c4e4`
- name: `?set_OverlayType@CUwfStaticConfiguration@@QEAAJW4_UWF_CONFIG_OVERLAY_TYPE@@@Z`
- size: `484`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x1800176f0`
- `0x180017890`

## callees

- `0x180006bb0`
- `0x180007250`
- `0x1800098d0`
- `0x18000a150`
- `0x18000c190`
- `0x18000c300`
- `0x18000e0f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c3ba`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c462`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c3ba`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c462`

## string_xrefs

- `0x18000c349`: `OverlayMaximumSize`

## pseudocode

```c
__int64 __fastcall CUwfStaticConfiguration::set_OverlayType(__int64 a1, unsigned int a2)
{
  int DWORDValue; // edx
  HKEY v6; // rcx
  LSTATUS v7; // eax
  char v8; // dl
  int v9; // eax
  HKEY v10; // rcx
  LSTATUS v11; // eax
  int updated; // eax
  BYTE Data[16]; // [rsp+30h] [rbp-10h] BYREF
  DWORD v14; // [rsp+60h] [rbp+20h] BYREF
  DWORD Type; // [rsp+70h] [rbp+30h] BYREF
  DWORD cbData; // [rsp+78h] [rbp+38h] BYREF

  if ( *(_BYTE *)(a1 + 9) )
  {
    DWORDValue = -2147024891;
LABEL_3:
    *(_DWORD *)(*(_QWORD *)(a1 + 32) + 16LL) = DWORDValue;
    return (unsigned int)DWORDValue;
  }
  if ( a2 == 1 )
  {
    v14 = 0;
    DWORDValue = CUwfRegKey::QueryDWORDValue((HKEY *)(a1 + 16), L"OverlayMaximumSize", (BYTE *)&v14);
    if ( DWORDValue < 0 )
      goto LABEL_3;
    DWORDValue = CUwfStaticConfiguration::CreateOverlayFile((CUwfStaticConfiguration *)a1, v14);
    if ( DWORDValue < 0 )
      goto LABEL_3;
    DWORDValue = CUwfStaticConfiguration::SetOverlayFileSize((CUwfStaticConfiguration *)a1, v14);
    if ( DWORDValue < 0 )
      goto LABEL_3;
    v6 = *(HKEY *)(a1 + 16);
    *(_DWORD *)Data = 0;
    Type = 0;
    cbData = 4;
    v7 = RegQueryValueExW(v6, L"OverlayFlags", 0, &Type, Data, &cbData);
    DWORDValue = v7;
    if ( v7 )
    {
      if ( v7 > 0 )
        DWORDValue = (unsigned __int16)v7 | 0x80070000;
      if ( DWORDValue < 0 )
        goto LABEL_3;
      goto LABEL_13;
    }
    if ( Type != 4 )
    {
LABEL_15:
      DWORDValue = -2147023267;
      goto LABEL_3;
    }
    if ( cbData == 4 )
    {
LABEL_13:
      v8 = Data[0] | 1;
      goto LABEL_30;
    }
LABEL_17:
    DWORDValue = -2147024883;
    goto LABEL_3;
  }
  if ( a2 )
    goto LABEL_31;
  v9 = CUwfStaticConfiguration::DeleteOverlayFile((CUwfConfiguration **)a1);
  DWORDValue = v9;
  if ( v9 < 0 )
  {
    if ( v9 != -2147024894 )
      goto LABEL_3;
    *(_DWORD *)(*(_QWORD *)(a1 + 32) + 16LL) = 0;
  }
  v10 = *(HKEY *)(a1 + 16);
  cbData = 0;
  v14 = 0;
  Type = 4;
  v11 = RegQueryValueExW(v10, L"OverlayFlags", 0, &v14, (LPBYTE)&cbData, &Type);
  DWORDValue = v11;
  if ( v11 )
  {
    if ( v11 > 0 )
      DWORDValue = (unsigned __int16)v11 | 0x80070000;
    if ( DWORDValue < 0 )
      goto LABEL_3;
  }
  else
  {
    if ( v14 != 4 )
      goto LABEL_15;
    if ( Type != 4 )
      goto LABEL_17;
  }
  v8 = cbData & 0xFC;
LABEL_30:
  DWORDValue = CUwfStaticConfiguration::set_OverlayFlags((CUwfStaticConfiguration *)a1, v8);
  if ( DWORDValue < 0 )
    goto LABEL_3;
LABEL_31:
  updated = CUwfConfiguration::UpdateDWORDValue(
              *(CUwfConfiguration **)(a1 + 32),
              (struct CUwfRegKey *)(a1 + 16),
              L"OverlayType",
              a2,
              1);
  DWORDValue = updated;
  if ( updated < 0 )
    goto LABEL_3;
  if ( updated == 1 )
    return 0;
  return (unsigned int)DWORDValue;
}

```

## disassembly

```asm
0x18000c300  mov     [rsp-18h+arg_8], rbx
0x18000c305  push    rbp
0x18000c306  push    rsi
0x18000c307  push    rdi
0x18000c308  mov     rbp, rsp
0x18000c30b  sub     rsp, 40h
0x18000c30f  cmp     byte ptr [rcx+9], 0
0x18000c313  mov     edi, edx
0x18000c315  mov     rbx, rcx
0x18000c318  jz      short loc_18000C335
0x18000c31a  mov     edx, 80070005h
0x18000c31f  mov     rax, [rbx+20h]
0x18000c323  mov     [rax+10h], edx
0x18000c326  mov     rbx, [rsp+40h+arg_8]
0x18000c32b  mov     eax, edx
0x18000c32d  add     rsp, 40h
0x18000c331  pop     rdi
0x18000c332  pop     rsi
0x18000c333  pop     rbp
0x18000c334  retn
0x18000c335  cmp     edi, 1
0x18000c338  jnz     loc_18000C404
0x18000c33e  lea     r8, [rbp+arg_0]; unsigned int *
0x18000c342  mov     [rbp+arg_0], 0
0x18000c349  lea     rdx, aOverlaymaximum; "OverlayMaximumSize"
0x18000c350  add     rcx, 10h; this
0x18000c354  call    ?QueryDWORDValue@CUwfRegKey@@QEAAJPEBGPEAK@Z; CUwfRegKey::QueryDWORDValue(ushort const *,ulong *)
0x18000c359  mov     edx, eax
0x18000c35b  test    eax, eax
0x18000c35d  js      short loc_18000C31F
0x18000c35f  mov     edx, [rbp+arg_0]; unsigned int
0x18000c362  mov     rcx, rbx; this
0x18000c365  call    ?CreateOverlayFile@CUwfStaticConfiguration@@QEAAJK@Z; CUwfStaticConfiguration::CreateOverlayFile(ulong)
0x18000c36a  mov     edx, eax
0x18000c36c  test    eax, eax
0x18000c36e  js      short loc_18000C31F
0x18000c370  mov     edx, [rbp+arg_0]; unsigned int
0x18000c373  mov     rcx, rbx; this
0x18000c376  call    ?SetOverlayFileSize@CUwfStaticConfiguration@@QEAAJK@Z; CUwfStaticConfiguration::SetOverlayFileSize(ulong)
0x18000c37b  mov     edx, eax
0x18000c37d  test    eax, eax
0x18000c37f  js      short loc_18000C31F
0x18000c381  mov     rcx, [rbx+10h]; hKey
0x18000c385  lea     rax, [rbp+cbData]
0x18000c389  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18000c38e  lea     r9, [rbp+Type]; lpType
0x18000c392  lea     rax, [rbp+Data]
0x18000c396  mov     dword ptr [rbp+Data], 0
0x18000c39d  xor     r8d, r8d; lpReserved
0x18000c3a0  mov     [rsp+40h+lpData], rax; lpData
0x18000c3a5  lea     rdx, aOverlayflags; "OverlayFlags"
0x18000c3ac  mov     [rbp+Type], 0
0x18000c3b3  mov     [rbp+cbData], 4
0x18000c3ba  call    cs:__imp_RegQueryValueExW
0x18000c3c0  mov     edx, eax
0x18000c3c2  test    eax, eax
0x18000c3c4  jz      short loc_18000C3E4
0x18000c3c6  jle     short loc_18000C3D1
0x18000c3c8  movzx   edx, ax
0x18000c3cb  or      edx, 80070000h
0x18000c3d1  test    edx, edx
0x18000c3d3  js      loc_18000C31F
0x18000c3d9  mov     edx, dword ptr [rbp+Data]
0x18000c3dc  or      edx, 1
0x18000c3df  jmp     loc_18000C49C
0x18000c3e4  cmp     [rbp+Type], 4
0x18000c3e8  jz      short loc_18000C3F4
0x18000c3ea  mov     edx, 8007065Dh
0x18000c3ef  jmp     loc_18000C31F
0x18000c3f4  cmp     [rbp+cbData], 4
0x18000c3f8  jz      short loc_18000C3D9
0x18000c3fa  mov     edx, 8007000Dh
0x18000c3ff  jmp     loc_18000C31F
0x18000c404  test    edi, edi
0x18000c406  jnz     loc_18000C4AE
0x18000c40c  call    ?DeleteOverlayFile@CUwfStaticConfiguration@@QEAAJXZ; CUwfStaticConfiguration::DeleteOverlayFile(void)
0x18000c411  mov     edx, eax
0x18000c413  test    eax, eax
0x18000c415  jns     short loc_18000C429
0x18000c417  cmp     eax, 80070002h
0x18000c41c  jnz     loc_18000C31F
0x18000c422  mov     rax, [rbx+20h]
0x18000c426  mov     [rax+10h], edi
0x18000c429  mov     rcx, [rbx+10h]; hKey
0x18000c42d  lea     rax, [rbp+Type]
0x18000c431  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18000c436  lea     r9, [rbp+arg_0]; lpType
0x18000c43a  lea     rax, [rbp+cbData]
0x18000c43e  mov     [rbp+cbData], 0
0x18000c445  xor     r8d, r8d; lpReserved
0x18000c448  mov     [rsp+40h+lpData], rax; lpData
0x18000c44d  lea     rdx, aOverlayflags; "OverlayFlags"
0x18000c454  mov     [rbp+arg_0], 0
0x18000c45b  mov     [rbp+Type], 4
0x18000c462  call    cs:__imp_RegQueryValueExW
0x18000c468  mov     edx, eax
0x18000c46a  test    eax, eax
0x18000c46c  jz      short loc_18000C482
0x18000c46e  jle     short loc_18000C479
0x18000c470  movzx   edx, ax
0x18000c473  or      edx, 80070000h
0x18000c479  test    edx, edx
0x18000c47b  jns     short loc_18000C496
0x18000c47d  jmp     loc_18000C31F
0x18000c482  cmp     [rbp+arg_0], 4
0x18000c486  jnz     loc_18000C3EA
0x18000c48c  cmp     [rbp+Type], 4
0x18000c490  jnz     loc_18000C3FA
0x18000c496  mov     edx, [rbp+cbData]
0x18000c499  and     edx, 0FFFFFFFCh; unsigned int
0x18000c49c  mov     rcx, rbx; this
0x18000c49f  call    ?set_OverlayFlags@CUwfStaticConfiguration@@QEAAJK@Z; CUwfStaticConfiguration::set_OverlayFlags(ulong)
0x18000c4a4  mov     edx, eax
0x18000c4a6  test    eax, eax
0x18000c4a8  js      loc_18000C31F
0x18000c4ae  mov     rcx, [rbx+20h]; this
0x18000c4b2  lea     rdx, [rbx+10h]; struct CUwfRegKey *
0x18000c4b6  mov     r9d, edi; unsigned int
0x18000c4b9  mov     byte ptr [rsp+40h+lpData], 1; bool
0x18000c4be  lea     r8, aOverlaytype; "OverlayType"
0x18000c4c5  call    ?UpdateDWORDValue@CUwfConfiguration@@QEAAJAEAVCUwfRegKey@@PEBGK_N@Z; CUwfConfiguration::UpdateDWORDValue(CUwfRegKey &,ushort const *,ulong,bool)
0x18000c4ca  mov     edx, eax
0x18000c4cc  test    eax, eax
0x18000c4ce  js      loc_18000C31F
0x18000c4d4  cmp     eax, 1
0x18000c4d7  jnz     loc_18000C326
0x18000c4dd  xor     edx, edx
0x18000c4df  jmp     loc_18000C326
```
