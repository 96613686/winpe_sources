# CUPnPInterfaceList::GetICSInterfacesFromRegistry(long *,_GUID * *)

- ea: `0x18000bf80`
- end: `0x18000c14f`
- name: `?GetICSInterfacesFromRegistry@CUPnPInterfaceList@@AEAAJPEAJPEAPEAU_GUID@@@Z`
- size: `463`
- prototype: `__int64 __fastcall(CUPnPInterfaceList *this, int *, struct _GUID **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000be44`

## callees

- `0x18000bf80`
- `0x18003309c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c0fa`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c12e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c0fa`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c12e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000bfef`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000c0a7`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000bfef`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000c0a7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c092`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c0d4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c092`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c0d4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c10b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c10b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c05e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c05e`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18000bfdd`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18000c021`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18000bfdd`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18000c021`

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
0x18000bf80  mov     r11, rsp
0x18000bf83  mov     [r11+10h], rbx
0x18000bf87  mov     [r11+18h], rsi
0x18000bf8b  mov     [r11+8], rcx
0x18000bf8f  push    rbp
0x18000bf90  push    rdi
0x18000bf91  push    r12
0x18000bf93  push    r14
0x18000bf95  push    r15
0x18000bf97  mov     rbp, rsp
0x18000bf9a  sub     rsp, 40h
0x18000bf9e  mov     r15, r8
0x18000bfa1  mov     [rbp+hKey], 0
0x18000bfa9  mov     r12, rdx
0x18000bfac  mov     [rbp+cbData], 0
0x18000bfb3  lea     rax, [rbp+Size]
0x18000bfb7  mov     [rbp+Type], 0
0x18000bfbe  xor     r8d, r8d
0x18000bfc1  mov     [r11-48h], rax
0x18000bfc5  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\UPnP Control Point"
0x18000bfcc  mov     dword ptr [rbp+Size], 0
0x18000bfd3  xor     r9d, r9d
0x18000bfd6  lea     rcx, aUpnpcontrolpoi; "UPnPControlPoint"
0x18000bfdd  call    cs:__imp_GetPersistedRegistryLocationW
0x18000bfe3  mov     edi, eax
0x18000bfe5  cmp     eax, 0EAh
0x18000bfea  jnz     short loc_18000C02B
0x18000bfec  mov     ecx, dword ptr [rbp+Size]; Size
0x18000bfef  call    cs:__imp_malloc
0x18000bff5  mov     rsi, rax
0x18000bff8  test    rax, rax
0x18000bffb  jz      loc_18000C11D
0x18000c001  mov     r9d, dword ptr [rbp+Size]
0x18000c005  lea     rax, [rbp+Size]
0x18000c009  xor     ebx, ebx
0x18000c00b  mov     [rsp+40h+phkResult], rax
0x18000c010  mov     r8, rsi
0x18000c013  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\UPnP Control Point"
0x18000c01a  lea     rcx, aUpnpcontrolpoi; "UPnPControlPoint"
0x18000c021  call    cs:__imp_GetPersistedRegistryLocationW
0x18000c027  mov     edi, eax
0x18000c029  jmp     short loc_18000C032
0x18000c02b  xor     esi, esi
0x18000c02d  mov     ebx, 8000FFFFh
0x18000c032  test    edi, edi
0x18000c034  jnz     loc_18000C117
0x18000c03a  test    ebx, ebx
0x18000c03c  jnz     loc_18000C126
0x18000c042  lea     rax, [rbp+hKey]
0x18000c046  mov     r9d, 20019h; samDesired
0x18000c04c  xor     r8d, r8d; ulOptions
0x18000c04f  mov     [rsp+40h+phkResult], rax; phkResult
0x18000c054  mov     rdx, rsi; lpSubKey
0x18000c057  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000c05e  call    cs:__imp_RegOpenKeyExW
0x18000c064  mov     edi, eax
0x18000c066  test    eax, eax
0x18000c068  jnz     loc_18000C115
0x18000c06e  mov     rcx, [rbp+hKey]; hKey
0x18000c072  lea     rax, [rbp+cbData]
0x18000c076  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18000c07b  lea     r9, [rbp+Type]; lpType
0x18000c07f  xor     r8d, r8d; lpReserved
0x18000c082  mov     [rsp+40h+phkResult], 0; lpData
0x18000c08b  lea     rdx, aAllowedinterfa; "AllowedInterfaces"
0x18000c092  call    cs:__imp_RegQueryValueExW
0x18000c098  mov     edi, eax
0x18000c09a  test    eax, eax
0x18000c09c  jnz     short loc_18000C107
0x18000c09e  cmp     [rbp+Type], 7
0x18000c0a2  jnz     short loc_18000C102
0x18000c0a4  mov     ecx, [rbp+cbData]; Size
0x18000c0a7  call    cs:__imp_malloc
0x18000c0ad  mov     r14, rax
0x18000c0b0  test    rax, rax
0x18000c0b3  jz      short loc_18000C107
0x18000c0b5  mov     rcx, [rbp+hKey]; hKey
0x18000c0b9  lea     rax, [rbp+cbData]
0x18000c0bd  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18000c0c2  lea     rdx, aAllowedinterfa; "AllowedInterfaces"
0x18000c0c9  xor     r9d, r9d; lpType
0x18000c0cc  mov     [rsp+40h+phkResult], r14; lpData
0x18000c0d1  xor     r8d, r8d; lpReserved
0x18000c0d4  call    cs:__imp_RegQueryValueExW
0x18000c0da  mov     edi, eax
0x18000c0dc  test    eax, eax
0x18000c0de  jnz     short loc_18000C0F7
0x18000c0e0  mov     eax, [rbp+cbData]
0x18000c0e3  mov     r9, r14; unsigned __int16 *
0x18000c0e6  mov     r8, r15; struct _GUID **
0x18000c0e9  mov     dword ptr [rsp+40h+phkResult], eax; unsigned int
0x18000c0ed  mov     rdx, r12; int *
0x18000c0f0  call    ?MultistringToGuids@CUPnPInterfaceList@@AEAAJPEAJPEAPEAU_GUID@@PEAGK@Z; CUPnPInterfaceList::MultistringToGuids(long *,_GUID * *,ushort *,ulong)
0x18000c0f5  mov     ebx, eax
0x18000c0f7  mov     rcx, r14; Block
0x18000c0fa  call    cs:__imp_free
0x18000c100  jmp     short loc_18000C107
0x18000c102  mov     ebx, 80070057h
0x18000c107  mov     rcx, [rbp+hKey]; hKey
0x18000c10b  call    cs:__imp_RegCloseKey
0x18000c111  test    edi, edi
0x18000c113  jz      short loc_18000C126
0x18000c115  test    edi, edi
0x18000c117  jg      short loc_18000C11D
0x18000c119  mov     ebx, edi
0x18000c11b  jmp     short loc_18000C126
0x18000c11d  movzx   ebx, di
0x18000c120  or      ebx, 80070000h
0x18000c126  test    rsi, rsi
0x18000c129  jz      short loc_18000C134
0x18000c12b  mov     rcx, rsi; Block
0x18000c12e  call    cs:__imp_free
0x18000c134  lea     r11, [rsp+40h+var_s0]
0x18000c139  mov     eax, ebx
0x18000c13b  mov     rbx, [r11+38h]
0x18000c13f  mov     rsi, [r11+40h]
0x18000c143  mov     rsp, r11
0x18000c146  pop     r15
0x18000c148  pop     r14
0x18000c14a  pop     r12
0x18000c14c  pop     rdi
0x18000c14d  pop     rbp
0x18000c14e  retn
```
