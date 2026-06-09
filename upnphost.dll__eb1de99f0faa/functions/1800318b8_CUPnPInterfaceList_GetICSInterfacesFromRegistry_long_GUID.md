# CUPnPInterfaceList::GetICSInterfacesFromRegistry(long *,_GUID * *)

- ea: `0x1800318b8`
- end: `0x180031a87`
- name: `?GetICSInterfacesFromRegistry@CUPnPInterfaceList@@AEAAJPEAJPEAPEAU_GUID@@@Z`
- size: `463`
- prototype: `__int64 __fastcall(CUPnPInterfaceList *this, int *, struct _GUID **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003177c`

## callees

- `0x1800318b8`
- `0x180052948`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180031a32`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180031a66`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180031a32`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180031a66`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180031927`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800319df`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180031927`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800319df`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031a43`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031a43`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180031996`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180031996`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800319ca`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180031a0c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800319ca`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180031a0c`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180031915`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180031959`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180031915`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180031959`

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
0x1800318b8  mov     r11, rsp
0x1800318bb  mov     [r11+10h], rbx
0x1800318bf  mov     [r11+18h], rsi
0x1800318c3  mov     [r11+8], rcx
0x1800318c7  push    rbp
0x1800318c8  push    rdi
0x1800318c9  push    r12
0x1800318cb  push    r14
0x1800318cd  push    r15
0x1800318cf  mov     rbp, rsp
0x1800318d2  sub     rsp, 40h
0x1800318d6  mov     r15, r8
0x1800318d9  mov     [rbp+hKey], 0
0x1800318e1  mov     r12, rdx
0x1800318e4  mov     [rbp+cbData], 0
0x1800318eb  lea     rax, [rbp+Size]
0x1800318ef  mov     [rbp+Type], 0
0x1800318f6  xor     r8d, r8d
0x1800318f9  mov     [r11-48h], rax
0x1800318fd  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\UPnP Control Point"
0x180031904  mov     dword ptr [rbp+Size], 0
0x18003190b  xor     r9d, r9d
0x18003190e  lea     rcx, aUpnpcontrolpoi; "UPnPControlPoint"
0x180031915  call    cs:__imp_GetPersistedRegistryLocationW
0x18003191b  mov     edi, eax
0x18003191d  cmp     eax, 0EAh
0x180031922  jnz     short loc_180031963
0x180031924  mov     ecx, dword ptr [rbp+Size]; Size
0x180031927  call    cs:__imp_malloc
0x18003192d  mov     rsi, rax
0x180031930  test    rax, rax
0x180031933  jz      loc_180031A55
0x180031939  mov     r9d, dword ptr [rbp+Size]
0x18003193d  lea     rax, [rbp+Size]
0x180031941  xor     ebx, ebx
0x180031943  mov     [rsp+40h+phkResult], rax
0x180031948  mov     r8, rsi
0x18003194b  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\UPnP Control Point"
0x180031952  lea     rcx, aUpnpcontrolpoi; "UPnPControlPoint"
0x180031959  call    cs:__imp_GetPersistedRegistryLocationW
0x18003195f  mov     edi, eax
0x180031961  jmp     short loc_18003196A
0x180031963  xor     esi, esi
0x180031965  mov     ebx, 8000FFFFh
0x18003196a  test    edi, edi
0x18003196c  jnz     loc_180031A4F
0x180031972  test    ebx, ebx
0x180031974  jnz     loc_180031A5E
0x18003197a  lea     rax, [rbp+hKey]
0x18003197e  mov     r9d, 20019h; samDesired
0x180031984  xor     r8d, r8d; ulOptions
0x180031987  mov     [rsp+40h+phkResult], rax; phkResult
0x18003198c  mov     rdx, rsi; lpSubKey
0x18003198f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180031996  call    cs:__imp_RegOpenKeyExW
0x18003199c  mov     edi, eax
0x18003199e  test    eax, eax
0x1800319a0  jnz     loc_180031A4D
0x1800319a6  mov     rcx, [rbp+hKey]; hKey
0x1800319aa  lea     rax, [rbp+cbData]
0x1800319ae  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800319b3  lea     r9, [rbp+Type]; lpType
0x1800319b7  xor     r8d, r8d; lpReserved
0x1800319ba  mov     [rsp+40h+phkResult], 0; lpData
0x1800319c3  lea     rdx, aAllowedinterfa; "AllowedInterfaces"
0x1800319ca  call    cs:__imp_RegQueryValueExW
0x1800319d0  mov     edi, eax
0x1800319d2  test    eax, eax
0x1800319d4  jnz     short loc_180031A3F
0x1800319d6  cmp     [rbp+Type], 7
0x1800319da  jnz     short loc_180031A3A
0x1800319dc  mov     ecx, [rbp+cbData]; Size
0x1800319df  call    cs:__imp_malloc
0x1800319e5  mov     r14, rax
0x1800319e8  test    rax, rax
0x1800319eb  jz      short loc_180031A3F
0x1800319ed  mov     rcx, [rbp+hKey]; hKey
0x1800319f1  lea     rax, [rbp+cbData]
0x1800319f5  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800319fa  lea     rdx, aAllowedinterfa; "AllowedInterfaces"
0x180031a01  xor     r9d, r9d; lpType
0x180031a04  mov     [rsp+40h+phkResult], r14; lpData
0x180031a09  xor     r8d, r8d; lpReserved
0x180031a0c  call    cs:__imp_RegQueryValueExW
0x180031a12  mov     edi, eax
0x180031a14  test    eax, eax
0x180031a16  jnz     short loc_180031A2F
0x180031a18  mov     eax, [rbp+cbData]
0x180031a1b  mov     r9, r14; unsigned __int16 *
0x180031a1e  mov     r8, r15; struct _GUID **
0x180031a21  mov     dword ptr [rsp+40h+phkResult], eax; unsigned int
0x180031a25  mov     rdx, r12; int *
0x180031a28  call    ?MultistringToGuids@CUPnPInterfaceList@@AEAAJPEAJPEAPEAU_GUID@@PEAGK@Z; CUPnPInterfaceList::MultistringToGuids(long *,_GUID * *,ushort *,ulong)
0x180031a2d  mov     ebx, eax
0x180031a2f  mov     rcx, r14; Block
0x180031a32  call    cs:__imp_free
0x180031a38  jmp     short loc_180031A3F
0x180031a3a  mov     ebx, 80070057h
0x180031a3f  mov     rcx, [rbp+hKey]; hKey
0x180031a43  call    cs:__imp_RegCloseKey
0x180031a49  test    edi, edi
0x180031a4b  jz      short loc_180031A5E
0x180031a4d  test    edi, edi
0x180031a4f  jg      short loc_180031A55
0x180031a51  mov     ebx, edi
0x180031a53  jmp     short loc_180031A5E
0x180031a55  movzx   ebx, di
0x180031a58  or      ebx, 80070000h
0x180031a5e  test    rsi, rsi
0x180031a61  jz      short loc_180031A6C
0x180031a63  mov     rcx, rsi; Block
0x180031a66  call    cs:__imp_free
0x180031a6c  lea     r11, [rsp+40h+var_s0]
0x180031a71  mov     eax, ebx
0x180031a73  mov     rbx, [r11+38h]
0x180031a77  mov     rsi, [r11+40h]
0x180031a7b  mov     rsp, r11
0x180031a7e  pop     r15
0x180031a80  pop     r14
0x180031a82  pop     r12
0x180031a84  pop     rdi
0x180031a85  pop     rbp
0x180031a86  retn
```
