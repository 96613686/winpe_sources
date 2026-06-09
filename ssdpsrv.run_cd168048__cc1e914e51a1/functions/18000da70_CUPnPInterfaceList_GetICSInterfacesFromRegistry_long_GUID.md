# CUPnPInterfaceList::GetICSInterfacesFromRegistry(long *,_GUID * *)

- ea: `0x18000da70`
- end: `0x18000dc7c`
- name: `?GetICSInterfacesFromRegistry@CUPnPInterfaceList@@AEAAJPEAJPEAPEAU_GUID@@@Z`
- size: `524`
- prototype: `int(CUPnPInterfaceList *__hidden this, int *, struct _GUID **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d920`

## callees

- `0x18000da70`
- `0x180035adc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000dc14`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000dc54`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000dc14`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000dc54`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000dae5`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000dbb5`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000dae5`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000dbb5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000db9a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000dbe8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000db9a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000dbe8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000dc2b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000dc2b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000db60`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000db60`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18000dacd`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18000db1d`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18000dacd`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18000db1d`

## pseudocode

```c
__int64 __fastcall CUPnPInterfaceList::GetICSInterfacesFromRegistry(
        CUPnPInterfaceList *this,
        int *a2,
        struct _GUID **a3)
{
  LSTATUS PersistedRegistryLocationW; // edi
  WCHAR *v6; // rsi
  unsigned int v7; // ebx
  bool v8; // cc
  BYTE *v9; // r14
  CUPnPInterfaceList *v10; // rcx
  DWORD Type; // [rsp+30h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-8h] BYREF
  unsigned int Size; // [rsp+70h] [rbp+30h] BYREF
  int Size_4; // [rsp+74h] [rbp+34h]
  DWORD cbData; // [rsp+88h] [rbp+48h] BYREF

  Size_4 = HIDWORD(this);
  hKey = 0;
  cbData = 0;
  Type = 0;
  Size = 0;
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                 L"UPnPControlPoint",
                                 L"SOFTWARE\\Microsoft\\UPnP Control Point",
                                 0,
                                 0,
                                 &Size);
  if ( PersistedRegistryLocationW == 234 )
  {
    v6 = (WCHAR *)malloc(Size);
    if ( !v6 )
    {
LABEL_19:
      v7 = (unsigned __int16)PersistedRegistryLocationW | 0x80070000;
      goto LABEL_20;
    }
    v7 = 0;
    PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                   L"UPnPControlPoint",
                                   L"SOFTWARE\\Microsoft\\UPnP Control Point",
                                   v6,
                                   Size,
                                   &Size);
  }
  else
  {
    v6 = 0;
    v7 = -2147418113;
  }
  v8 = PersistedRegistryLocationW <= 0;
  if ( PersistedRegistryLocationW )
  {
LABEL_17:
    if ( v8 )
    {
      v7 = PersistedRegistryLocationW;
      goto LABEL_20;
    }
    goto LABEL_19;
  }
  if ( !v7 )
  {
    PersistedRegistryLocationW = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v6, 0, 0x20019u, &hKey);
    if ( PersistedRegistryLocationW )
      goto LABEL_16;
    PersistedRegistryLocationW = RegQueryValueExW(hKey, L"AllowedInterfaces", 0, &Type, 0, &cbData);
    if ( !PersistedRegistryLocationW )
    {
      if ( Type == 7 )
      {
        v9 = (BYTE *)malloc(cbData);
        if ( v9 )
        {
          PersistedRegistryLocationW = RegQueryValueExW(hKey, L"AllowedInterfaces", 0, 0, v9, &cbData);
          if ( !PersistedRegistryLocationW )
            v7 = CUPnPInterfaceList::MultistringToGuids(v10, a2, a3, (unsigned __int16 *)v9, cbData);
          free(v9);
        }
      }
      else
      {
        v7 = -2147024809;
      }
    }
    RegCloseKey(hKey);
    if ( PersistedRegistryLocationW )
    {
LABEL_16:
      v8 = PersistedRegistryLocationW <= 0;
      goto LABEL_17;
    }
  }
LABEL_20:
  if ( v6 )
    free(v6);
  return v7;
}

```

## disassembly

```asm
0x18000da70  mov     r11, rsp
0x18000da73  mov     [r11+10h], rbx
0x18000da77  mov     [r11+18h], rsi
0x18000da7b  mov     [r11+8], rcx
0x18000da7f  push    rbp
0x18000da80  push    rdi
0x18000da81  push    r12
0x18000da83  push    r14
0x18000da85  push    r15
0x18000da87  mov     rbp, rsp
0x18000da8a  sub     rsp, 40h
0x18000da8e  mov     r15, r8
0x18000da91  mov     [rbp+hKey], 0
0x18000da99  mov     r12, rdx
0x18000da9c  mov     [rbp+cbData], 0
0x18000daa3  lea     rax, [rbp+Size]
0x18000daa7  mov     [rbp+Type], 0
0x18000daae  xor     r8d, r8d
0x18000dab1  mov     [r11-48h], rax
0x18000dab5  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\UPnP Control Point"
0x18000dabc  mov     dword ptr [rbp+Size], 0
0x18000dac3  xor     r9d, r9d
0x18000dac6  lea     rcx, aUpnpcontrolpoi; "UPnPControlPoint"
0x18000dacd  call    cs:__imp_GetPersistedRegistryLocationW
0x18000dad4  nop     dword ptr [rax+rax+00h]
0x18000dad9  mov     edi, eax
0x18000dadb  cmp     eax, 0EAh
0x18000dae0  jnz     short loc_18000DB2D
0x18000dae2  mov     ecx, dword ptr [rbp+Size]; Size
0x18000dae5  call    cs:__imp_malloc
0x18000daec  nop     dword ptr [rax+rax+00h]
0x18000daf1  mov     rsi, rax
0x18000daf4  test    rax, rax
0x18000daf7  jz      loc_18000DC43
0x18000dafd  mov     r9d, dword ptr [rbp+Size]
0x18000db01  lea     rax, [rbp+Size]
0x18000db05  xor     ebx, ebx
0x18000db07  mov     [rsp+40h+phkResult], rax
0x18000db0c  mov     r8, rsi
0x18000db0f  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\UPnP Control Point"
0x18000db16  lea     rcx, aUpnpcontrolpoi; "UPnPControlPoint"
0x18000db1d  call    cs:__imp_GetPersistedRegistryLocationW
0x18000db24  nop     dword ptr [rax+rax+00h]
0x18000db29  mov     edi, eax
0x18000db2b  jmp     short loc_18000DB34
0x18000db2d  xor     esi, esi
0x18000db2f  mov     ebx, 8000FFFFh
0x18000db34  test    edi, edi
0x18000db36  jnz     loc_18000DC3D
0x18000db3c  test    ebx, ebx
0x18000db3e  jnz     loc_18000DC4C
0x18000db44  lea     rax, [rbp+hKey]
0x18000db48  mov     r9d, 20019h; samDesired
0x18000db4e  xor     r8d, r8d; ulOptions
0x18000db51  mov     [rsp+40h+phkResult], rax; phkResult
0x18000db56  mov     rdx, rsi; lpSubKey
0x18000db59  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000db60  call    cs:__imp_RegOpenKeyExW
0x18000db67  nop     dword ptr [rax+rax+00h]
0x18000db6c  mov     edi, eax
0x18000db6e  test    eax, eax
0x18000db70  jnz     loc_18000DC3B
0x18000db76  mov     rcx, [rbp+hKey]; hKey
0x18000db7a  lea     rax, [rbp+cbData]
0x18000db7e  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18000db83  lea     r9, [rbp+Type]; lpType
0x18000db87  xor     r8d, r8d; lpReserved
0x18000db8a  mov     [rsp+40h+phkResult], 0; lpData
0x18000db93  lea     rdx, aAllowedinterfa; "AllowedInterfaces"
0x18000db9a  call    cs:__imp_RegQueryValueExW
0x18000dba1  nop     dword ptr [rax+rax+00h]
0x18000dba6  mov     edi, eax
0x18000dba8  test    eax, eax
0x18000dbaa  jnz     short loc_18000DC27
0x18000dbac  cmp     [rbp+Type], 7
0x18000dbb0  jnz     short loc_18000DC22
0x18000dbb2  mov     ecx, [rbp+cbData]; Size
0x18000dbb5  call    cs:__imp_malloc
0x18000dbbc  nop     dword ptr [rax+rax+00h]
0x18000dbc1  mov     r14, rax
0x18000dbc4  test    rax, rax
0x18000dbc7  jz      short loc_18000DC27
0x18000dbc9  mov     rcx, [rbp+hKey]; hKey
0x18000dbcd  lea     rax, [rbp+cbData]
0x18000dbd1  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18000dbd6  lea     rdx, aAllowedinterfa; "AllowedInterfaces"
0x18000dbdd  xor     r9d, r9d; lpType
0x18000dbe0  mov     [rsp+40h+phkResult], r14; lpData
0x18000dbe5  xor     r8d, r8d; lpReserved
0x18000dbe8  call    cs:__imp_RegQueryValueExW
0x18000dbef  nop     dword ptr [rax+rax+00h]
0x18000dbf4  mov     edi, eax
0x18000dbf6  test    eax, eax
0x18000dbf8  jnz     short loc_18000DC11
0x18000dbfa  mov     eax, [rbp+cbData]
0x18000dbfd  mov     r9, r14; unsigned __int16 *
0x18000dc00  mov     r8, r15; struct _GUID **
0x18000dc03  mov     dword ptr [rsp+40h+phkResult], eax; unsigned int
0x18000dc07  mov     rdx, r12; int *
0x18000dc0a  call    ?MultistringToGuids@CUPnPInterfaceList@@AEAAJPEAJPEAPEAU_GUID@@PEAGK@Z; CUPnPInterfaceList::MultistringToGuids(long *,_GUID * *,ushort *,ulong)
0x18000dc0f  mov     ebx, eax
0x18000dc11  mov     rcx, r14; Block
0x18000dc14  call    cs:__imp_free
0x18000dc1b  nop     dword ptr [rax+rax+00h]
0x18000dc20  jmp     short loc_18000DC27
0x18000dc22  mov     ebx, 80070057h
0x18000dc27  mov     rcx, [rbp+hKey]; hKey
0x18000dc2b  call    cs:__imp_RegCloseKey
0x18000dc32  nop     dword ptr [rax+rax+00h]
0x18000dc37  test    edi, edi
0x18000dc39  jz      short loc_18000DC4C
0x18000dc3b  test    edi, edi
0x18000dc3d  jg      short loc_18000DC43
0x18000dc3f  mov     ebx, edi
0x18000dc41  jmp     short loc_18000DC4C
0x18000dc43  movzx   ebx, di
0x18000dc46  or      ebx, 80070000h
0x18000dc4c  test    rsi, rsi
0x18000dc4f  jz      short loc_18000DC60
0x18000dc51  mov     rcx, rsi; Block
0x18000dc54  call    cs:__imp_free
0x18000dc5b  nop     dword ptr [rax+rax+00h]
0x18000dc60  lea     r11, [rsp+40h+var_s0]
0x18000dc65  mov     eax, ebx
0x18000dc67  mov     rbx, [r11+38h]
0x18000dc6b  mov     rsi, [r11+40h]
0x18000dc6f  mov     rsp, r11
0x18000dc72  pop     r15
0x18000dc74  pop     r14
0x18000dc76  pop     r12
0x18000dc78  pop     rdi
0x18000dc79  pop     rbp
0x18000dc7a  retn
```
