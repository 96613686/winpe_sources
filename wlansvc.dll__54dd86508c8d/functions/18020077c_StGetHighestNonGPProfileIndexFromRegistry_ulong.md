# StGetHighestNonGPProfileIndexFromRegistry(ulong *)

- ea: `0x18020077c`
- end: `0x180200d2d`
- name: `?StGetHighestNonGPProfileIndexFromRegistry@@YAKPEAK@Z`
- size: `1457`
- prototype: `unsigned int __fastcall(unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180200d34`

## callees

- `0x18000aa0c`
- `0x180011530`
- `0x18007018c`
- `0x180106340`
- `0x180107330`
- `0x18020077c`
- `0x18020234c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180200ae4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180200ae4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1802008f5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180200a03`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180200aa6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1802008f5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180200a03`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180200aa6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180200af6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180200b57`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180200cc4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180200af6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180200b57`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180200cc4`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18020097c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180200a7d`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18020097c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180200a7d`
- `RPCRT4!UuidFromStringW` at `0x1802009bf`
- `RPCRT4!UuidFromStringW` at `0x1802009bf`

## pseudocode

```c
__int64 __fastcall StGetHighestNonGPProfileIndexFromRegistry(unsigned int *a1)
{
  PVOID *v2; // rcx
  unsigned int v3; // ebx
  unsigned int RegistryRoot; // eax
  unsigned int v5; // eax
  unsigned int v6; // esi
  DWORD i; // r14d
  unsigned int v8; // eax
  unsigned int ProfileRegKeyRootPath; // eax
  unsigned __int64 v10; // r8
  unsigned int v11; // eax
  bool v12; // zf
  DWORD j; // edi
  unsigned int v14; // eax
  unsigned int v15; // eax
  __int64 v16; // rdx
  BYTE Data[4]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchName; // [rsp+44h] [rbp-BCh] BYREF
  DWORD v20; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cbData; // [rsp+4Ch] [rbp-B4h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  HKEY v23; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  UUID Uuid; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 StringUuid[8]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v27; // [rsp+90h] [rbp-70h]
  __int128 v28; // [rsp+A0h] [rbp-60h]
  __int128 v29; // [rsp+B0h] [rbp-50h]
  __int64 v30; // [rsp+C0h] [rbp-40h]
  WCHAR Name; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v32; // [rsp+D2h] [rbp-2Eh]
  __int128 v33; // [rsp+E2h] [rbp-1Eh]
  __int128 v34; // [rsp+F2h] [rbp-Eh]
  __int128 v35; // [rsp+102h] [rbp+2h]
  __int64 v36; // [rsp+112h] [rbp+12h]
  WCHAR v37[40]; // [rsp+120h] [rbp+20h] BYREF
  WCHAR SubKey[264]; // [rsp+170h] [rbp+70h] BYREF

  hKey = 0;
  phkResult = 0;
  v23 = 0;
  memset_0(&Name, 0, 0x4Eu);
  memset_0(StringUuid, 0, 0x4Au);
  cchName = 39;
  memset_0(v37, 0, 0x4Eu);
  v20 = 39;
  Uuid = 0;
  *(_DWORD *)Data = 0;
  cbData = 4;
  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 101, &WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a1 )
  {
    v3 = 87;
    goto LABEL_79;
  }
  *a1 = 0;
  memset_0(SubKey, 0, 0x208u);
  RegistryRoot = StpGetRegistryRoot(
                   (unsigned int)SubKey,
                   260,
                   (unsigned int)L"Software\\Microsoft\\Wlansvc",
                   (unsigned int)L"Interfaces",
                   0);
  v3 = RegistryRoot;
  if ( !RegistryRoot )
  {
    v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 9u, &hKey);
    v3 = v5;
    if ( v5 )
    {
      v2 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105)
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 103, &WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids, v5);
        v2 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v3 == 2 )
        v3 = 0;
      goto LABEL_79;
    }
    v6 = 0;
    for ( i = 0; ; ++i )
    {
      cchName = 39;
      v8 = RegEnumKeyExW(hKey, i, &Name, &cchName, 0, 0, 0, 0);
      v3 = v8;
      if ( v8 )
      {
        v2 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 105)
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 104, &WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids, v8);
          v2 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v3 == 259 )
          v3 = 0;
        goto LABEL_74;
      }
      *(_OWORD *)StringUuid = v32;
      v27 = v33;
      v28 = v34;
      v30 = v36;
      v29 = v35;
      ProfileRegKeyRootPath = UuidFromStringW(StringUuid, &Uuid);
      v3 = ProfileRegKeyRootPath;
      if ( ProfileRegKeyRootPath )
        break;
      ProfileRegKeyRootPath = StpGetProfileRegKeyRootPath(&Uuid, SubKey, v10);
      v3 = ProfileRegKeyRootPath;
      if ( ProfileRegKeyRootPath )
      {
        v2 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 105)
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
        {
          v16 = 106;
LABEL_67:
          WPP_SF_d(v2[12], v16, &WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids, ProfileRegKeyRootPath);
          v2 = (PVOID *)WPP_GLOBAL_Control;
          goto LABEL_74;
        }
        goto LABEL_74;
      }
      v11 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 9u, &phkResult);
      v3 = v11;
      if ( v11 )
      {
        v2 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 105)
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 107, &WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids, v11);
          v2 = (PVOID *)WPP_GLOBAL_Control;
        }
        v12 = v3 == 2;
      }
      else
      {
        for ( j = 0; ; ++j )
        {
          v20 = 39;
          v14 = RegEnumKeyExW(phkResult, j, v37, &v20, 0, 0, 0, 0);
          v3 = v14;
          if ( v14 )
            break;
          v15 = RegOpenKeyExW(phkResult, v37, 0, 1u, &v23);
          v3 = v15;
          if ( v15 )
          {
            v2 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && *((_BYTE *)WPP_GLOBAL_Control + 105)
              && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 109, &WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids, v15);
              v2 = (PVOID *)WPP_GLOBAL_Control;
            }
            goto LABEL_40;
          }
          cbData = 4;
          v3 = RegQueryValueExW(v23, L"ProfileIndex", 0, 0, Data, &cbData);
          if ( v23 )
            RegCloseKey(v23);
          if ( v3 )
          {
            v2 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && *((_BYTE *)WPP_GLOBAL_Control + 105)
              && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 110, &WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids, v3);
              v2 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( v3 != 2 )
              goto LABEL_40;
          }
          else if ( *(_DWORD *)Data > v6 )
          {
            v6 = *(_DWORD *)Data;
          }
        }
        v2 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 105)
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 108, &WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids, v14);
          v2 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v3 == 259 )
          v3 = 0;
LABEL_40:
        if ( phkResult )
        {
          RegCloseKey(phkResult);
          v2 = (PVOID *)WPP_GLOBAL_Control;
        }
        v12 = v3 == 0;
      }
      if ( !v12 )
        goto LABEL_74;
    }
    v2 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105)
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      v16 = 105;
      goto LABEL_67;
    }
LABEL_74:
    if ( hKey )
    {
      RegCloseKey(hKey);
      v2 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v3 )
      goto LABEL_79;
    *a1 = v6;
    goto LABEL_78;
  }
  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v3;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 105) && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 102, &WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids, RegistryRoot);
LABEL_78:
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_79:
  if ( v2 != &WPP_GLOBAL_Control && *((_BYTE *)v2 + 105) >= 4u && (*((_BYTE *)v2 + 108) & 1) != 0 )
    WPP_SF_d(v2[12], 111, &WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x18020077c  push    rbp
0x18020077e  push    rbx
0x18020077f  push    rsi
0x180200780  push    rdi
0x180200781  push    r12
0x180200783  push    r13
0x180200785  push    r14
0x180200787  push    r15
0x180200789  lea     rbp, [rsp-298h]
0x180200791  sub     rsp, 398h
0x180200798  mov     rax, cs:__security_cookie
0x18020079f  xor     rax, rsp
0x1802007a2  mov     [rbp+2D0h+var_50], rax
0x1802007a9  xor     r12d, r12d
0x1802007ac  mov     r15, rcx
0x1802007af  xor     edx, edx; Val
0x1802007b1  mov     [rsp+3D0h+hKey], r12
0x1802007b6  lea     rcx, [rbp+2D0h+Name]; void *
0x1802007ba  mov     [rsp+3D0h+var_380], r12
0x1802007bf  mov     [rsp+3D0h+var_378], r12
0x1802007c4  lea     ebx, [r12+4Eh]
0x1802007c9  mov     r8d, ebx; Size
0x1802007cc  call    memset_0
0x1802007d1  xor     edx, edx; Val
0x1802007d3  lea     r8d, [r12+4Ah]; Size
0x1802007d8  lea     rcx, [rbp+2D0h+StringUuid]; void *
0x1802007dc  call    memset_0
0x1802007e1  lea     edi, [rbx-27h]
0x1802007e4  mov     r8d, ebx; Size
0x1802007e7  xor     edx, edx; Val
0x1802007e9  mov     [rsp+3D0h+cchName], edi
0x1802007ed  lea     rcx, [rbp+2D0h+var_2B0]; void *
0x1802007f1  call    memset_0
0x1802007f6  xorps   xmm0, xmm0
0x1802007f9  mov     [rsp+3D0h+var_388], edi
0x1802007fd  movups  xmmword ptr [rsp+3D0h+Uuid.Data1], xmm0
0x180200802  mov     dword ptr [rsp+3D0h+Data], r12d
0x180200807  mov     [rsp+3D0h+cbData], 4
0x18020080f  mov     rcx, cs:WPP_GLOBAL_Control
0x180200816  lea     rdi, WPP_GLOBAL_Control
0x18020081d  lea     r13d, [r12+1]
0x180200822  cmp     rcx, rdi
0x180200825  jz      short loc_18020084D
0x180200827  cmp     byte ptr [rcx+69h], 4
0x18020082b  jb      short loc_18020084D
0x18020082d  test    [rcx+6Ch], r13b
0x180200831  jz      short loc_18020084D
0x180200833  mov     rcx, [rcx+60h]
0x180200837  lea     edx, [rbx+17h]
0x18020083a  lea     r8, WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids
0x180200841  call    WPP_SF_
0x180200846  mov     rcx, cs:WPP_GLOBAL_Control
0x18020084d  test    r15, r15
0x180200850  jnz     short loc_18020085B
0x180200852  lea     ebx, [r15+57h]
0x180200856  jmp     loc_180200CDF
0x18020085b  xor     edx, edx; Val
0x18020085d  mov     [r15], r12d
0x180200860  mov     r8d, 208h; Size
0x180200866  lea     rcx, [rbp+2D0h+SubKey]; void *
0x18020086a  call    memset_0
0x18020086f  lea     r9, aInterfaces; "Interfaces"
0x180200876  mov     dword ptr [rsp+3D0h+phkResult], r12d
0x18020087b  lea     r8, aSoftwareMicros_13; "Software\\Microsoft\\Wlansvc"
0x180200882  mov     edx, 104h
0x180200887  lea     rcx, [rbp+2D0h+SubKey]
0x18020088b  call    _StpGetRegistryRoot
0x180200890  mov     ebx, eax
0x180200892  test    eax, eax
0x180200894  jz      short loc_1802008D7
0x180200896  mov     rcx, cs:WPP_GLOBAL_Control
0x18020089d  cmp     rcx, rdi
0x1802008a0  jz      loc_180200D08
0x1802008a6  cmp     [rcx+69h], r13b
0x1802008aa  jb      loc_180200CDF
0x1802008b0  test    [rcx+6Ch], r13b
0x1802008b4  jz      loc_180200CDF
0x1802008ba  mov     rcx, [rcx+60h]
0x1802008be  lea     r8, WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids
0x1802008c5  mov     edx, 66h ; 'f'
0x1802008ca  mov     r9d, eax
0x1802008cd  call    WPP_SF_d
0x1802008d2  jmp     loc_180200CD8
0x1802008d7  lea     rax, [rsp+3D0h+hKey]
0x1802008dc  mov     r9d, 9; samDesired
0x1802008e2  xor     r8d, r8d; ulOptions
0x1802008e5  mov     [rsp+3D0h+phkResult], rax; phkResult
0x1802008ea  lea     rdx, [rbp+2D0h+SubKey]; lpSubKey
0x1802008ee  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1802008f5  call    cs:__imp_RegOpenKeyExW
0x1802008fb  mov     ebx, eax
0x1802008fd  test    eax, eax
0x1802008ff  jz      short loc_180200949
0x180200901  mov     rcx, cs:WPP_GLOBAL_Control
0x180200908  cmp     rcx, rdi
0x18020090b  jz      short loc_180200938
0x18020090d  cmp     [rcx+69h], r13b
0x180200911  jb      short loc_180200938
0x180200913  test    [rcx+6Ch], r13b
0x180200917  jz      short loc_180200938
0x180200919  mov     rcx, [rcx+60h]
0x18020091d  lea     r8, WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids
0x180200924  mov     edx, 67h ; 'g'
0x180200929  mov     r9d, eax
0x18020092c  call    WPP_SF_d
0x180200931  mov     rcx, cs:WPP_GLOBAL_Control
0x180200938  cmp     ebx, 2
0x18020093b  jnz     loc_180200CDF
0x180200941  mov     ebx, r12d
0x180200944  jmp     loc_180200CDF
0x180200949  mov     esi, r12d
0x18020094c  mov     r14d, r12d
0x18020094f  mov     rcx, [rsp+3D0h+hKey]; hKey
0x180200954  lea     r9, [rsp+3D0h+cchName]; lpcchName
0x180200959  mov     [rsp+3D0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x18020095e  lea     r8, [rbp+2D0h+Name]; lpName
0x180200962  mov     [rsp+3D0h+lpcchClass], r12; lpcchClass
0x180200967  mov     edx, r14d; dwIndex
0x18020096a  mov     [rsp+3D0h+lpClass], r12; lpClass
0x18020096f  mov     [rsp+3D0h+phkResult], r12; lpReserved
0x180200974  mov     [rsp+3D0h+cchName], 27h ; '''
0x18020097c  call    cs:__imp_RegEnumKeyExW
0x180200982  mov     ebx, eax
0x180200984  test    eax, eax
0x180200986  jnz     loc_180200C76
0x18020098c  movups  xmm0, [rbp+2D0h+var_2FE]
0x180200990  lea     rdx, [rsp+3D0h+Uuid]; Uuid
0x180200995  movups  xmm1, [rbp+2D0h+var_2EE]
0x180200999  lea     rcx, [rbp+2D0h+StringUuid]; StringUuid
0x18020099d  movaps  xmmword ptr [rbp+2D0h+StringUuid], xmm0
0x1802009a1  movups  xmm0, [rbp+2D0h+var_2DE]
0x1802009a5  movaps  [rbp+2D0h+var_340], xmm1
0x1802009a9  movups  xmm1, [rbp+2D0h+var_2CE]
0x1802009ad  movaps  [rbp+2D0h+var_330], xmm0
0x1802009b1  movsd   xmm0, [rbp+2D0h+var_2BE]
0x1802009b6  movsd   [rbp+2D0h+var_310], xmm0
0x1802009bb  movaps  [rbp+2D0h+var_320], xmm1
0x1802009bf  call    cs:__imp_UuidFromStringW
0x1802009c5  mov     ebx, eax
0x1802009c7  test    eax, eax
0x1802009c9  jnz     loc_180200C3D
0x1802009cf  lea     rdx, [rbp+2D0h+SubKey]; unsigned __int16 *
0x1802009d3  lea     rcx, [rsp+3D0h+Uuid]; rguid
0x1802009d8  call    ?StpGetProfileRegKeyRootPath@@YAKPEBU_GUID@@PEAG_K@Z; StpGetProfileRegKeyRootPath(_GUID const *,ushort *,unsigned __int64)
0x1802009dd  mov     ebx, eax
0x1802009df  test    eax, eax
0x1802009e1  jnz     loc_180200C12
0x1802009e7  lea     rax, [rsp+3D0h+var_380]
0x1802009ec  xor     r8d, r8d; ulOptions
0x1802009ef  lea     r9d, [rbx+9]; samDesired
0x1802009f3  mov     [rsp+3D0h+phkResult], rax; phkResult
0x1802009f8  lea     rdx, [rbp+2D0h+SubKey]; lpSubKey
0x1802009fc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180200a03  call    cs:__imp_RegOpenKeyExW
0x180200a09  mov     ebx, eax
0x180200a0b  test    eax, eax
0x180200a0d  jz      short loc_180200A4E
0x180200a0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180200a16  cmp     rcx, rdi
0x180200a19  jz      short loc_180200A46
0x180200a1b  cmp     [rcx+69h], r13b
0x180200a1f  jb      short loc_180200A46
0x180200a21  test    [rcx+6Ch], r13b
0x180200a25  jz      short loc_180200A46
0x180200a27  mov     rcx, [rcx+60h]
0x180200a2b  lea     r8, WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids
0x180200a32  mov     edx, 6Bh ; 'k'
0x180200a37  mov     r9d, eax
0x180200a3a  call    WPP_SF_d
0x180200a3f  mov     rcx, cs:WPP_GLOBAL_Control
0x180200a46  cmp     ebx, 2
0x180200a49  jmp     loc_180200B66
0x180200a4e  mov     edi, r12d
0x180200a51  mov     rcx, [rsp+3D0h+var_380]; hKey
0x180200a56  lea     r9, [rsp+3D0h+var_388]; lpcchName
0x180200a5b  mov     [rsp+3D0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180200a60  lea     r8, [rbp+2D0h+var_2B0]; lpName
0x180200a64  mov     [rsp+3D0h+lpcchClass], r12; lpcchClass
0x180200a69  mov     edx, edi; dwIndex
0x180200a6b  mov     [rsp+3D0h+lpClass], r12; lpClass
0x180200a70  mov     [rsp+3D0h+phkResult], r12; lpReserved
0x180200a75  mov     [rsp+3D0h+var_388], 27h ; '''
0x180200a7d  call    cs:__imp_RegEnumKeyExW
0x180200a83  mov     ebx, eax
0x180200a85  test    eax, eax
0x180200a87  jnz     loc_180200BC5
0x180200a8d  mov     rcx, [rsp+3D0h+var_380]; hKey
0x180200a92  lea     rax, [rsp+3D0h+var_378]
0x180200a97  mov     r9d, r13d; samDesired
0x180200a9a  mov     [rsp+3D0h+phkResult], rax; phkResult
0x180200a9f  xor     r8d, r8d; ulOptions
0x180200aa2  lea     rdx, [rbp+2D0h+var_2B0]; lpSubKey
0x180200aa6  call    cs:__imp_RegOpenKeyExW
0x180200aac  mov     ebx, eax
0x180200aae  test    eax, eax
0x180200ab0  jnz     loc_180200B85
0x180200ab6  mov     rcx, [rsp+3D0h+var_378]; hKey
0x180200abb  lea     rax, [rsp+3D0h+cbData]
0x180200ac0  mov     [rsp+3D0h+lpClass], rax; lpcbData
0x180200ac5  lea     rdx, ValueName; "ProfileIndex"
0x180200acc  lea     rax, [rsp+3D0h+Data]
0x180200ad1  mov     [rsp+3D0h+cbData], 4
0x180200ad9  xor     r9d, r9d; lpType
0x180200adc  mov     [rsp+3D0h+phkResult], rax; lpData
0x180200ae1  xor     r8d, r8d; lpReserved
0x180200ae4  call    cs:__imp_RegQueryValueExW
0x180200aea  mov     rcx, [rsp+3D0h+var_378]; hKey
0x180200aef  mov     ebx, eax
0x180200af1  test    rcx, rcx
0x180200af4  jz      short loc_180200AFC
0x180200af6  call    cs:__imp_RegCloseKey
0x180200afc  test    ebx, ebx
0x180200afe  jz      short loc_180200B74
0x180200b00  mov     rcx, cs:WPP_GLOBAL_Control
0x180200b07  lea     rax, WPP_GLOBAL_Control
0x180200b0e  cmp     rcx, rax
0x180200b11  jz      short loc_180200B3E
0x180200b13  cmp     [rcx+69h], r13b
0x180200b17  jb      short loc_180200B3E
0x180200b19  test    [rcx+6Ch], r13b
0x180200b1d  jz      short loc_180200B3E
0x180200b1f  mov     rcx, [rcx+60h]
0x180200b23  lea     r8, WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids
0x180200b2a  mov     edx, 6Eh ; 'n'
0x180200b2f  mov     r9d, ebx
0x180200b32  call    WPP_SF_d
0x180200b37  mov     rcx, cs:WPP_GLOBAL_Control
0x180200b3e  cmp     ebx, 2
0x180200b41  jz      short loc_180200B7D
0x180200b43  lea     rdi, WPP_GLOBAL_Control
0x180200b4a  mov     rax, [rsp+3D0h+var_380]
0x180200b4f  test    rax, rax
0x180200b52  jz      short loc_180200B64
0x180200b54  mov     rcx, rax; hKey
0x180200b57  call    cs:__imp_RegCloseKey
0x180200b5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180200b64  test    ebx, ebx
0x180200b66  jnz     loc_180200CB7
0x180200b6c  add     r14d, r13d
0x180200b6f  jmp     loc_18020094F
0x180200b74  cmp     dword ptr [rsp+3D0h+Data], esi
0x180200b78  cmova   esi, dword ptr [rsp+3D0h+Data]
0x180200b7d  add     edi, r13d
0x180200b80  jmp     loc_180200A51
0x180200b85  mov     rcx, cs:WPP_GLOBAL_Control
0x180200b8c  lea     rdi, WPP_GLOBAL_Control
0x180200b93  cmp     rcx, rdi
0x180200b96  jz      short loc_180200B4A
0x180200b98  cmp     [rcx+69h], r13b
0x180200b9c  jb      short loc_180200B4A
0x180200b9e  test    [rcx+6Ch], r13b
0x180200ba2  jz      short loc_180200B4A
0x180200ba4  mov     rcx, [rcx+60h]
0x180200ba8  lea     r8, WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids
0x180200baf  mov     edx, 6Dh ; 'm'
0x180200bb4  mov     r9d, eax
0x180200bb7  call    WPP_SF_d
0x180200bbc  mov     rcx, cs:WPP_GLOBAL_Control
0x180200bc3  jmp     short loc_180200B4A
0x180200bc5  mov     rcx, cs:WPP_GLOBAL_Control
0x180200bcc  lea     rdi, WPP_GLOBAL_Control
0x180200bd3  cmp     rcx, rdi
0x180200bd6  jz      short loc_180200C03
0x180200bd8  cmp     [rcx+69h], r13b
0x180200bdc  jb      short loc_180200C03
0x180200bde  test    [rcx+6Ch], r13b
0x180200be2  jz      short loc_180200C03
0x180200be4  mov     rcx, [rcx+60h]
0x180200be8  lea     r8, WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids
0x180200bef  mov     edx, 6Ch ; 'l'
0x180200bf4  mov     r9d, ebx
0x180200bf7  call    WPP_SF_d
0x180200bfc  mov     rcx, cs:WPP_GLOBAL_Control
0x180200c03  cmp     ebx, 103h
0x180200c09  cmovz   ebx, r12d
0x180200c0d  jmp     loc_180200B4A
0x180200c12  mov     rcx, cs:WPP_GLOBAL_Control
0x180200c19  cmp     rcx, rdi
0x180200c1c  jz      loc_180200CB7
0x180200c22  cmp     [rcx+69h], r13b
0x180200c26  jb      loc_180200CB7
0x180200c2c  test    [rcx+6Ch], r13b
0x180200c30  jz      loc_180200CB7
0x180200c36  mov     edx, 6Ah ; 'j'
0x180200c3b  jmp     short loc_180200C5A
0x180200c3d  mov     rcx, cs:WPP_GLOBAL_Control
0x180200c44  cmp     rcx, rdi
0x180200c47  jz      short loc_180200CB7
0x180200c49  cmp     [rcx+69h], r13b
0x180200c4d  jb      short loc_180200CB7
0x180200c4f  test    [rcx+6Ch], r13b
0x180200c53  jz      short loc_180200CB7
0x180200c55  mov     edx, 69h ; 'i'
0x180200c5a  mov     rcx, [rcx+60h]
0x180200c5e  lea     r8, WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids
0x180200c65  mov     r9d, eax
0x180200c68  call    WPP_SF_d
0x180200c6d  mov     rcx, cs:WPP_GLOBAL_Control
0x180200c74  jmp     short loc_180200CB7
0x180200c76  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
