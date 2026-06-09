# CUwfManagement::GetCurrentOverlayConfig(_UWF_CONFIG_OVERLAY_TYPE *,ulong *)

- ea: `0x180015bb4`
- end: `0x180015d69`
- name: `?GetCurrentOverlayConfig@CUwfManagement@@AEAAJPEAW4_UWF_CONFIG_OVERLAY_TYPE@@PEAK@Z`
- size: `437`
- prototype: `__int64 __fastcall(CUwfManagement *this, enum _UWF_CONFIG_OVERLAY_TYPE *, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180014c1c`

## callees

- `0x18000d5f0`
- `0x18000de30`
- `0x18000de90`
- `0x18000e0f0`
- `0x180015bb4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180015c4b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180015cd3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180015c4b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180015cd3`

## string_xrefs

- `0x180015d33`: `OverlayMaximumSize`
- `0x180015bdc`: `SYSTEM\CurrentControlSet\Services\UWFVOL\Parameters\Static`
- `0x180015c79`: `Copy0`
- `0x180015c72`: `Copy1`

## pseudocode

```c
__int64 __fastcall CUwfManagement::GetCurrentOverlayConfig(
        CUwfManagement *this,
        enum _UWF_CONFIG_OVERLAY_TYPE *a2,
        unsigned int *a3)
{
  signed int DWORDValue; // ebx
  LSTATUS v6; // eax
  const unsigned __int16 *v7; // rdx
  LSTATUS v8; // eax
  BYTE lpData[8]; // [rsp+30h] [rbp-20h] BYREF
  HKEY v11; // [rsp+38h] [rbp-18h] BYREF
  HKEY hKey[2]; // [rsp+40h] [rbp-10h] BYREF
  CUwfManagement *Type; // [rsp+70h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+78h] [rbp+28h] BYREF
  int Data; // [rsp+88h] [rbp+38h] BYREF

  Type = this;
  *(_DWORD *)a2 = 0;
  hKey[0] = 0;
  v11 = 0;
  Data = 0;
  *(_DWORD *)lpData = 0;
  DWORDValue = CUwfRegKey::Open(
                 hKey,
                 HKEY_LOCAL_MACHINE,
                 L"SYSTEM\\CurrentControlSet\\Services\\UWFVOL\\Parameters\\Static",
                 0x20019u);
  if ( DWORDValue < 0 )
    goto LABEL_25;
  LODWORD(Type) = 0;
  cbData = 4;
  v6 = RegQueryValueExW(hKey[0], L"CurrentSettings", 0, (LPDWORD)&Type, (LPBYTE)&Data, &cbData);
  DWORDValue = v6;
  if ( v6 )
  {
    if ( v6 > 0 )
      DWORDValue = (unsigned __int16)v6 | 0x80070000;
    if ( DWORDValue < 0 )
      goto LABEL_25;
  }
  else
  {
    if ( (_DWORD)Type != 4 )
      goto LABEL_15;
    if ( cbData != 4 )
      goto LABEL_17;
  }
  v7 = L"Copy0";
  if ( Data )
    v7 = L"Copy1";
  DWORDValue = CUwfRegKey::OpenSubKey((CUwfRegKey *)hKey, v7, 0x20019u, (struct CUwfRegKey *)&v11);
  if ( DWORDValue >= 0 )
  {
    LODWORD(Type) = 0;
    cbData = 4;
    v8 = RegQueryValueExW(v11, L"OverlayType", 0, (LPDWORD)&Type, lpData, &cbData);
    DWORDValue = v8;
    if ( v8 )
    {
      if ( v8 > 0 )
        DWORDValue = (unsigned __int16)v8 | 0x80070000;
      if ( DWORDValue < 0 )
        goto LABEL_25;
LABEL_20:
      if ( *(_DWORD *)lpData )
      {
        if ( *(_DWORD *)lpData == 1 )
          *(_DWORD *)a2 = 1;
      }
      else
      {
        *(_DWORD *)a2 = 0;
      }
      DWORDValue = CUwfRegKey::QueryDWORDValue((CUwfRegKey *)&v11, L"OverlayMaximumSize", a3);
      goto LABEL_25;
    }
    if ( (_DWORD)Type == 4 )
    {
      if ( cbData == 4 )
        goto LABEL_20;
LABEL_17:
      DWORDValue = -2147024883;
      goto LABEL_25;
    }
LABEL_15:
    DWORDValue = -2147023267;
  }
LABEL_25:
  CUwfRegKey::Close(&v11);
  CUwfRegKey::Close(hKey);
  return (unsigned int)DWORDValue;
}

```

## disassembly

```asm
0x180015bb4  mov     [rsp-18h+arg_10], rbx
0x180015bb9  mov     [rsp-18h+Type], rcx
0x180015bbe  push    rbp
0x180015bbf  push    rsi
0x180015bc0  push    rdi
0x180015bc1  mov     rbp, rsp
0x180015bc4  sub     rsp, 50h
0x180015bc8  mov     rsi, r8
0x180015bcb  mov     dword ptr [rdx], 0
0x180015bd1  mov     rdi, rdx
0x180015bd4  mov     [rbp+hKey], 0
0x180015bdc  lea     r8, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\UW"...
0x180015be3  mov     [rbp+var_18], 0
0x180015beb  mov     rdx, 0FFFFFFFF80000002h; hKey
0x180015bf2  mov     [rbp+Data], 0
0x180015bf9  mov     r9d, 20019h; samDesired
0x180015bff  mov     dword ptr [rbp+var_20], 0
0x180015c06  lea     rcx, [rbp+hKey]; phkResult
0x180015c0a  call    ?Open@CUwfRegKey@@QEAAJPEAUHKEY__@@PEBGK@Z; CUwfRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180015c0f  mov     ebx, eax
0x180015c11  test    eax, eax
0x180015c13  js      loc_180015D45
0x180015c19  mov     rcx, [rbp+hKey]; hKey
0x180015c1d  lea     rax, [rbp+cbData]
0x180015c21  mov     [rsp+50h+lpcbData], rax; lpcbData
0x180015c26  lea     r9, [rbp+Type]; lpType
0x180015c2a  lea     rax, [rbp+Data]
0x180015c2e  mov     dword ptr [rbp+Type], 0
0x180015c35  xor     r8d, r8d; lpReserved
0x180015c38  mov     [rsp+50h+lpData], rax; lpData
0x180015c3d  lea     rdx, aCurrentsetting; "CurrentSettings"
0x180015c44  mov     [rbp+cbData], 4
0x180015c4b  call    cs:__imp_RegQueryValueExW
0x180015c51  mov     ebx, eax
0x180015c53  test    eax, eax
0x180015c55  jz      loc_180015CF0
0x180015c5b  jle     short loc_180015C66
0x180015c5d  movzx   ebx, ax
0x180015c60  or      ebx, 80070000h
0x180015c66  test    ebx, ebx
0x180015c68  js      loc_180015D45
0x180015c6e  cmp     [rbp+Data], 0
0x180015c72  lea     rax, aCopy1; "Copy1"
0x180015c79  lea     rdx, aCopy0; "Copy0"
0x180015c80  mov     r8d, 20019h; unsigned int
0x180015c86  cmovnz  rdx, rax; unsigned __int16 *
0x180015c8a  lea     r9, [rbp+var_18]; struct CUwfRegKey *
0x180015c8e  lea     rcx, [rbp+hKey]; this
0x180015c92  call    ?OpenSubKey@CUwfRegKey@@QEAAJPEBGKAEAV1@@Z; CUwfRegKey::OpenSubKey(ushort const *,ulong,CUwfRegKey &)
0x180015c97  mov     ebx, eax
0x180015c99  test    eax, eax
0x180015c9b  js      loc_180015D45
0x180015ca1  mov     rcx, [rbp+var_18]; hKey
0x180015ca5  lea     rax, [rbp+cbData]
0x180015ca9  mov     [rsp+50h+lpcbData], rax; lpcbData
0x180015cae  lea     r9, [rbp+Type]; lpType
0x180015cb2  lea     rax, [rbp+var_20]
0x180015cb6  mov     dword ptr [rbp+Type], 0
0x180015cbd  xor     r8d, r8d; lpReserved
0x180015cc0  mov     [rsp+50h+lpData], rax; lpData
0x180015cc5  lea     rdx, aOverlaytype; "OverlayType"
0x180015ccc  mov     [rbp+cbData], 4
0x180015cd3  call    cs:__imp_RegQueryValueExW
0x180015cd9  mov     ebx, eax
0x180015cdb  test    eax, eax
0x180015cdd  jz      short loc_180015D0E
0x180015cdf  jle     short loc_180015CEA
0x180015ce1  movzx   ebx, ax
0x180015ce4  or      ebx, 80070000h
0x180015cea  test    ebx, ebx
0x180015cec  jns     short loc_180015D1A
0x180015cee  jmp     short loc_180015D45
0x180015cf0  cmp     dword ptr [rbp+Type], 4
0x180015cf4  jz      short loc_180015CFD
0x180015cf6  mov     ebx, 8007065Dh
0x180015cfb  jmp     short loc_180015D45
0x180015cfd  cmp     [rbp+cbData], 4
0x180015d01  jz      loc_180015C6E
0x180015d07  mov     ebx, 8007000Dh
0x180015d0c  jmp     short loc_180015D45
0x180015d0e  cmp     dword ptr [rbp+Type], 4
0x180015d12  jnz     short loc_180015CF6
0x180015d14  cmp     [rbp+cbData], 4
0x180015d18  jnz     short loc_180015D07
0x180015d1a  mov     eax, dword ptr [rbp+var_20]
0x180015d1d  test    eax, eax
0x180015d1f  jz      short loc_180015D2A
0x180015d21  cmp     eax, 1
0x180015d24  jnz     short loc_180015D30
0x180015d26  mov     [rdi], eax
0x180015d28  jmp     short loc_180015D30
0x180015d2a  mov     dword ptr [rdi], 0
0x180015d30  mov     r8, rsi; unsigned int *
0x180015d33  lea     rdx, aOverlaymaximum; "OverlayMaximumSize"
0x180015d3a  lea     rcx, [rbp+var_18]; this
0x180015d3e  call    ?QueryDWORDValue@CUwfRegKey@@QEAAJPEBGPEAK@Z; CUwfRegKey::QueryDWORDValue(ushort const *,ulong *)
0x180015d43  mov     ebx, eax
0x180015d45  lea     rcx, [rbp+var_18]; this
0x180015d49  call    ?Close@CUwfRegKey@@QEAAJXZ; CUwfRegKey::Close(void)
0x180015d4e  lea     rcx, [rbp+hKey]; this
0x180015d52  call    ?Close@CUwfRegKey@@QEAAJXZ; CUwfRegKey::Close(void)
0x180015d57  mov     eax, ebx
0x180015d59  mov     rbx, [rsp+50h+arg_10]
0x180015d61  add     rsp, 50h
0x180015d65  pop     rdi
0x180015d66  pop     rsi
0x180015d67  pop     rbp
0x180015d68  retn
```
