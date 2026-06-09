# CUPnPInterfaceList::GetICSInterfacesFromRegistry(long *,_GUID * *)

- ea: `0x1800335b0`
- end: `0x1800337bc`
- name: `?GetICSInterfacesFromRegistry@CUPnPInterfaceList@@AEAAJPEAJPEAPEAU_GUID@@@Z`
- size: `524`
- prototype: `int(CUPnPInterfaceList *__hidden this, int *, struct _GUID **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180033460`

## callees

- `0x1800335b0`
- `0x180056258`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180033754`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180033794`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180033754`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180033794`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180033625`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800336f5`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180033625`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800336f5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003376b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003376b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800336a0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800336a0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800336da`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180033728`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800336da`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180033728`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18003360d`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18003365d`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18003360d`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18003365d`

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
0x1800335b0  mov     r11, rsp
0x1800335b3  mov     [r11+10h], rbx
0x1800335b7  mov     [r11+18h], rsi
0x1800335bb  mov     [r11+8], rcx
0x1800335bf  push    rbp
0x1800335c0  push    rdi
0x1800335c1  push    r12
0x1800335c3  push    r14
0x1800335c5  push    r15
0x1800335c7  mov     rbp, rsp
0x1800335ca  sub     rsp, 40h
0x1800335ce  mov     r15, r8
0x1800335d1  mov     [rbp+hKey], 0
0x1800335d9  mov     r12, rdx
0x1800335dc  mov     [rbp+cbData], 0
0x1800335e3  lea     rax, [rbp+Size]
0x1800335e7  mov     [rbp+Type], 0
0x1800335ee  xor     r8d, r8d
0x1800335f1  mov     [r11-48h], rax
0x1800335f5  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\UPnP Control Point"
0x1800335fc  mov     dword ptr [rbp+Size], 0
0x180033603  xor     r9d, r9d
0x180033606  lea     rcx, aUpnpcontrolpoi; "UPnPControlPoint"
0x18003360d  call    cs:__imp_GetPersistedRegistryLocationW
0x180033614  nop     dword ptr [rax+rax+00h]
0x180033619  mov     edi, eax
0x18003361b  cmp     eax, 0EAh
0x180033620  jnz     short loc_18003366D
0x180033622  mov     ecx, dword ptr [rbp+Size]; Size
0x180033625  call    cs:__imp_malloc
0x18003362c  nop     dword ptr [rax+rax+00h]
0x180033631  mov     rsi, rax
0x180033634  test    rax, rax
0x180033637  jz      loc_180033783
0x18003363d  mov     r9d, dword ptr [rbp+Size]
0x180033641  lea     rax, [rbp+Size]
0x180033645  xor     ebx, ebx
0x180033647  mov     [rsp+40h+phkResult], rax
0x18003364c  mov     r8, rsi
0x18003364f  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\UPnP Control Point"
0x180033656  lea     rcx, aUpnpcontrolpoi; "UPnPControlPoint"
0x18003365d  call    cs:__imp_GetPersistedRegistryLocationW
0x180033664  nop     dword ptr [rax+rax+00h]
0x180033669  mov     edi, eax
0x18003366b  jmp     short loc_180033674
0x18003366d  xor     esi, esi
0x18003366f  mov     ebx, 8000FFFFh
0x180033674  test    edi, edi
0x180033676  jnz     loc_18003377D
0x18003367c  test    ebx, ebx
0x18003367e  jnz     loc_18003378C
0x180033684  lea     rax, [rbp+hKey]
0x180033688  mov     r9d, 20019h; samDesired
0x18003368e  xor     r8d, r8d; ulOptions
0x180033691  mov     [rsp+40h+phkResult], rax; phkResult
0x180033696  mov     rdx, rsi; lpSubKey
0x180033699  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800336a0  call    cs:__imp_RegOpenKeyExW
0x1800336a7  nop     dword ptr [rax+rax+00h]
0x1800336ac  mov     edi, eax
0x1800336ae  test    eax, eax
0x1800336b0  jnz     loc_18003377B
0x1800336b6  mov     rcx, [rbp+hKey]; hKey
0x1800336ba  lea     rax, [rbp+cbData]
0x1800336be  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800336c3  lea     r9, [rbp+Type]; lpType
0x1800336c7  xor     r8d, r8d; lpReserved
0x1800336ca  mov     [rsp+40h+phkResult], 0; lpData
0x1800336d3  lea     rdx, aAllowedinterfa; "AllowedInterfaces"
0x1800336da  call    cs:__imp_RegQueryValueExW
0x1800336e1  nop     dword ptr [rax+rax+00h]
0x1800336e6  mov     edi, eax
0x1800336e8  test    eax, eax
0x1800336ea  jnz     short loc_180033767
0x1800336ec  cmp     [rbp+Type], 7
0x1800336f0  jnz     short loc_180033762
0x1800336f2  mov     ecx, [rbp+cbData]; Size
0x1800336f5  call    cs:__imp_malloc
0x1800336fc  nop     dword ptr [rax+rax+00h]
0x180033701  mov     r14, rax
0x180033704  test    rax, rax
0x180033707  jz      short loc_180033767
0x180033709  mov     rcx, [rbp+hKey]; hKey
0x18003370d  lea     rax, [rbp+cbData]
0x180033711  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180033716  lea     rdx, aAllowedinterfa; "AllowedInterfaces"
0x18003371d  xor     r9d, r9d; lpType
0x180033720  mov     [rsp+40h+phkResult], r14; lpData
0x180033725  xor     r8d, r8d; lpReserved
0x180033728  call    cs:__imp_RegQueryValueExW
0x18003372f  nop     dword ptr [rax+rax+00h]
0x180033734  mov     edi, eax
0x180033736  test    eax, eax
0x180033738  jnz     short loc_180033751
0x18003373a  mov     eax, [rbp+cbData]
0x18003373d  mov     r9, r14; unsigned __int16 *
0x180033740  mov     r8, r15; struct _GUID **
0x180033743  mov     dword ptr [rsp+40h+phkResult], eax; unsigned int
0x180033747  mov     rdx, r12; int *
0x18003374a  call    ?MultistringToGuids@CUPnPInterfaceList@@AEAAJPEAJPEAPEAU_GUID@@PEAGK@Z; CUPnPInterfaceList::MultistringToGuids(long *,_GUID * *,ushort *,ulong)
0x18003374f  mov     ebx, eax
0x180033751  mov     rcx, r14; Block
0x180033754  call    cs:__imp_free
0x18003375b  nop     dword ptr [rax+rax+00h]
0x180033760  jmp     short loc_180033767
0x180033762  mov     ebx, 80070057h
0x180033767  mov     rcx, [rbp+hKey]; hKey
0x18003376b  call    cs:__imp_RegCloseKey
0x180033772  nop     dword ptr [rax+rax+00h]
0x180033777  test    edi, edi
0x180033779  jz      short loc_18003378C
0x18003377b  test    edi, edi
0x18003377d  jg      short loc_180033783
0x18003377f  mov     ebx, edi
0x180033781  jmp     short loc_18003378C
0x180033783  movzx   ebx, di
0x180033786  or      ebx, 80070000h
0x18003378c  test    rsi, rsi
0x18003378f  jz      short loc_1800337A0
0x180033791  mov     rcx, rsi; Block
0x180033794  call    cs:__imp_free
0x18003379b  nop     dword ptr [rax+rax+00h]
0x1800337a0  lea     r11, [rsp+40h+var_s0]
0x1800337a5  mov     eax, ebx
0x1800337a7  mov     rbx, [r11+38h]
0x1800337ab  mov     rsi, [r11+40h]
0x1800337af  mov     rsp, r11
0x1800337b2  pop     r15
0x1800337b4  pop     r14
0x1800337b6  pop     r12
0x1800337b8  pop     rdi
0x1800337b9  pop     rbp
0x1800337ba  retn
```
