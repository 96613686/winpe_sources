# UpdateRegistryItem(_REG_CHANGE *)

- ea: `0x14007e750`
- end: `0x14007eb7c`
- name: `?UpdateRegistryItem@@YAXPEAU_REG_CHANGE@@@Z`
- size: `1068`
- prototype: `void __fastcall(struct _REG_CHANGE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14007e078`

## callees

- `0x14001a520`
- `0x140027310`
- `0x140053720`
- `0x14007e750`
- `0x14009cc60`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14007e9a2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14007e9a2`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x14007e799`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x14007e987`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x14007e799`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x14007e987`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14007e93d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14007eb21`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14007e93d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14007eb21`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14007e869`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14007e869`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14007e8a3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14007e8f0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14007e8a3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14007e8f0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14007eb56`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14007eb56`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14007e7e7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14007e830`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14007eadf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14007eb34`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14007eb42`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14007e7e7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14007e830`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14007eadf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14007eb34`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14007eb42`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14007e7b2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14007e801`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14007e8bf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14007ea5e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14007e7b2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14007e801`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14007e8bf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14007ea5e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x14007e7d1`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x14007e81f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x14007e7d1`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x14007e81f`

## pseudocode

```c
void __fastcall UpdateRegistryItem(struct _REG_CHANGE *a1)
{
  const wchar_t *v2; // rcx
  wchar_t *v3; // rsi
  WCHAR *v4; // rax
  WCHAR *v5; // rax
  const WCHAR *v6; // rdx
  LSTATUS v7; // eax
  BYTE *v8; // rax
  HKEY v9; // rcx
  BYTE *v10; // rdi
  const BYTE *v11; // rcx
  __int64 v12; // r15
  __int64 v13; // r15
  int v14; // r13d
  _WORD *v15; // r12
  wchar_t *v16; // r14
  _WORD *v17; // rdx
  __int64 v18; // rax
  unsigned int v19; // eax
  __int64 v20; // rcx
  SIZE_T v21; // r12
  unsigned __int16 *v22; // r14
  unsigned __int64 v23; // r12
  DWORD nSize; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  DWORD Type; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v27; // [rsp+48h] [rbp-B8h]
  BYTE Data[256]; // [rsp+50h] [rbp-B0h] BYREF

  v2 = (const wchar_t *)*((_QWORD *)a1 + 1);
  hKey = 0;
  Type = 0;
  nSize = 0;
  v27 = 0;
  v3 = wcschr(v2, 0x25u);
  if ( !v3 )
  {
LABEL_9:
    if ( RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
           0,
           0x2001Fu,
           &hKey) )
    {
      return;
    }
    v6 = *(const WCHAR **)a1;
    nSize = 256;
    v7 = RegQueryValueExW(hKey, v6, 0, &Type, Data, &nSize);
    if ( v7 )
    {
      if ( (unsigned int)(v7 - 2) <= 1 )
      {
        if ( *((_DWORD *)a1 + 4) <= 1u )
        {
          v11 = (const BYTE *)*((_QWORD *)a1 + 1);
          v12 = -1;
          do
            ++v12;
          while ( *(_WORD *)&v11[2 * v12] );
          RegSetValueExW(hKey, *(LPCWSTR *)a1, 0, 1u, v11, 2 * v12 + 2);
        }
        goto LABEL_56;
      }
      v8 = (BYTE *)LocalAlloc(0, nSize);
      v9 = hKey;
      v10 = v8;
      if ( !v8 )
      {
LABEL_57:
        RegCloseKey(v9);
        return;
      }
      if ( RegQueryValueExW(hKey, *(LPCWSTR *)a1, 0, &Type, v8, &nSize) )
        goto LABEL_52;
    }
    else
    {
      v10 = Data;
    }
    v13 = -1;
    v14 = 0;
    v15 = v10;
    *(_WORD *)&v10[2 * ((unsigned __int64)nSize >> 1) - 2] = 0;
    v16 = (wchar_t *)v10;
    while ( v16 && *v16 )
    {
      v16 = wcschr(v16, 0x2Cu);
      if ( v16 )
        *v16 = 0;
      if ( (unsigned int)_o__wcsicmp(v15, *((_QWORD *)a1 + 1)) )
        goto LABEL_36;
      if ( *((_DWORD *)a1 + 4) <= 1u )
        goto LABEL_52;
      if ( *((_DWORD *)a1 + 4) != 2 )
      {
LABEL_36:
        if ( !v16 )
          break;
        *v16++ = 44;
        v15 = v16;
      }
      else
      {
        if ( v16 )
        {
          v17 = v16 + 1;
          v18 = -1;
          do
            ++v18;
          while ( v17[v18] );
          v19 = v18 + 1;
          if ( v19 >= (unsigned int)((__int64)&v10[2 * ((unsigned __int64)nSize >> 1) - (_QWORD)v16 - 2] >> 1) )
            v19 = (__int64)&v10[2 * ((unsigned __int64)nSize >> 1) - (_QWORD)v16 - 2] >> 1;
          memmove_0(v15, v17, 2LL * v19);
        }
        else
        {
          *v15 = 0;
        }
        v14 = 1;
      }
    }
    if ( *((_DWORD *)a1 + 4) > 1u )
      goto LABEL_49;
    v20 = -1;
    do
      ++v20;
    while ( *(_WORD *)(*((_QWORD *)a1 + 1) + 2 * v20) );
    v21 = nSize + 4LL + 2 * v20;
    v22 = (unsigned __int16 *)LocalAlloc(0, v21);
    if ( v22 )
    {
      v23 = v21 >> 1;
      *v22 = 0;
      if ( *((_DWORD *)a1 + 4) == 1 )
      {
        StringCchCopyW(v22, v23, *((const unsigned __int16 **)a1 + 1));
        StringCchCatW(v22, v23, L",");
      }
      StringCchCatW(v22, v23, (const unsigned __int16 *)v10);
      if ( !*((_DWORD *)a1 + 4) )
      {
        StringCchCatW(v22, v23, L",");
        StringCchCatW(v22, v23, *((const unsigned __int16 **)a1 + 1));
      }
      if ( v10 != Data )
        LocalFree(v10);
      v10 = (BYTE *)v22;
    }
    else
    {
LABEL_49:
      if ( !v14 )
        goto LABEL_52;
    }
    do
      ++v13;
    while ( *(_WORD *)&v10[2 * v13] );
    RegSetValueExW(hKey, *(LPCWSTR *)a1, 0, 1u, v10, 2 * v13 + 2);
LABEL_52:
    if ( v10 != Data )
      LocalFree(v10);
    if ( v3 )
    {
      LocalFree(v3);
      *((_QWORD *)a1 + 1) = v27;
    }
LABEL_56:
    v9 = hKey;
    goto LABEL_57;
  }
  v4 = (WCHAR *)LocalAlloc(0, 0x208u);
  v3 = v4;
  if ( !v4 )
    return;
  nSize = ExpandEnvironmentStringsW(*((LPCWSTR *)a1 + 1), v4, 0x104u);
  if ( nSize - 1 <= 0x103 )
  {
LABEL_8:
    v27 = *((_QWORD *)a1 + 1);
    *((_QWORD *)a1 + 1) = v3;
    goto LABEL_9;
  }
  LocalFree(v3);
  if ( nSize )
  {
    v5 = (WCHAR *)LocalAlloc(0, 2LL * (nSize + 1));
    v3 = v5;
    if ( v5 )
    {
      nSize = ExpandEnvironmentStringsW(*((LPCWSTR *)a1 + 1), v5, nSize);
      if ( !nSize )
      {
        LocalFree(v3);
        return;
      }
      goto LABEL_8;
    }
  }
}

```

## disassembly

```asm
0x14007e750  push    rbp
0x14007e752  push    rbx
0x14007e753  push    rsi
0x14007e754  push    rdi
0x14007e755  push    r12
0x14007e757  push    r13
0x14007e759  push    r14
0x14007e75b  push    r15
0x14007e75d  lea     rbp, [rsp-68h]
0x14007e762  sub     rsp, 168h
0x14007e769  mov     rax, cs:__security_cookie
0x14007e770  xor     rax, rsp
0x14007e773  mov     [rbp+0A0h+var_50], rax
0x14007e777  xor     r14d, r14d
0x14007e77a  mov     rbx, rcx
0x14007e77d  mov     rcx, [rcx+8]; Str
0x14007e781  mov     [rsp+1A0h+hKey], r14
0x14007e786  mov     [rsp+1A0h+Type], r14d
0x14007e78b  lea     edx, [r14+25h]; Ch
0x14007e78f  mov     [rsp+1A0h+nSize], r14d
0x14007e794  mov     [rsp+1A0h+var_158], r14
0x14007e799  call    cs:__imp_wcschr
0x14007e79f  mov     rsi, rax
0x14007e7a2  test    rax, rax
0x14007e7a5  jz      loc_14007E848
0x14007e7ab  mov     edx, 208h; uBytes
0x14007e7b0  xor     ecx, ecx; uFlags
0x14007e7b2  call    cs:__imp_LocalAlloc
0x14007e7b8  mov     rsi, rax
0x14007e7bb  test    rax, rax
0x14007e7be  jz      loc_14007EB5C
0x14007e7c4  mov     rcx, [rbx+8]; lpSrc
0x14007e7c8  mov     r8d, 104h; nSize
0x14007e7ce  mov     rdx, rax; lpDst
0x14007e7d1  call    cs:__imp_ExpandEnvironmentStringsW
0x14007e7d7  mov     [rsp+1A0h+nSize], eax
0x14007e7db  dec     eax
0x14007e7dd  cmp     eax, 103h
0x14007e7e2  jbe     short loc_14007E83B
0x14007e7e4  mov     rcx, rsi; hMem
0x14007e7e7  call    cs:__imp_LocalFree
0x14007e7ed  mov     eax, [rsp+1A0h+nSize]
0x14007e7f1  test    eax, eax
0x14007e7f3  jz      loc_14007EB5C
0x14007e7f9  lea     edx, [rax+1]
0x14007e7fc  xor     ecx, ecx; uFlags
0x14007e7fe  add     rdx, rdx; uBytes
0x14007e801  call    cs:__imp_LocalAlloc
0x14007e807  mov     rsi, rax
0x14007e80a  test    rax, rax
0x14007e80d  jz      loc_14007EB5C
0x14007e813  mov     r8d, [rsp+1A0h+nSize]; nSize
0x14007e818  mov     rdx, rax; lpDst
0x14007e81b  mov     rcx, [rbx+8]; lpSrc
0x14007e81f  call    cs:__imp_ExpandEnvironmentStringsW
0x14007e825  mov     [rsp+1A0h+nSize], eax
0x14007e829  test    eax, eax
0x14007e82b  jnz     short loc_14007E83B
0x14007e82d  mov     rcx, rsi; hMem
0x14007e830  call    cs:__imp_LocalFree
0x14007e836  jmp     loc_14007EB5C
0x14007e83b  mov     rax, [rbx+8]
0x14007e83f  mov     [rsp+1A0h+var_158], rax
0x14007e844  mov     [rbx+8], rsi
0x14007e848  lea     rax, [rsp+1A0h+hKey]
0x14007e84d  mov     r9d, 2001Fh; samDesired
0x14007e853  xor     r8d, r8d; ulOptions
0x14007e856  mov     [rsp+1A0h+phkResult], rax; phkResult
0x14007e85b  lea     rdx, aSoftwareMicros_48; "Software\\Microsoft\\Windows NT\\Curren"...
0x14007e862  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14007e869  call    cs:__imp_RegOpenKeyExW
0x14007e86f  test    eax, eax
0x14007e871  jnz     loc_14007EB5C
0x14007e877  mov     rdx, [rbx]; lpValueName
0x14007e87a  lea     rax, [rsp+1A0h+nSize]
0x14007e87f  mov     rcx, [rsp+1A0h+hKey]; hKey
0x14007e884  lea     r9, [rsp+1A0h+Type]; lpType
0x14007e889  mov     [rsp+1A0h+lpcbData], rax; lpcbData
0x14007e88e  xor     r8d, r8d; lpReserved
0x14007e891  lea     rax, [rsp+1A0h+Data]
0x14007e896  mov     [rsp+1A0h+nSize], 100h
0x14007e89e  mov     [rsp+1A0h+phkResult], rax; lpData
0x14007e8a3  call    cs:__imp_RegQueryValueExW
0x14007e8a9  test    eax, eax
0x14007e8ab  jz      loc_14007E948
0x14007e8b1  add     eax, 0FFFFFFFEh
0x14007e8b4  cmp     eax, 1
0x14007e8b7  jbe     short loc_14007E8FF
0x14007e8b9  mov     edx, [rsp+1A0h+nSize]; uBytes
0x14007e8bd  xor     ecx, ecx; uFlags
0x14007e8bf  call    cs:__imp_LocalAlloc
0x14007e8c5  mov     rcx, [rsp+1A0h+hKey]; hKey
0x14007e8ca  mov     rdi, rax
0x14007e8cd  test    rax, rax
0x14007e8d0  jz      loc_14007EB56
0x14007e8d6  mov     rdx, [rbx]; lpValueName
0x14007e8d9  lea     rax, [rsp+1A0h+nSize]
0x14007e8de  mov     [rsp+1A0h+lpcbData], rax; lpcbData
0x14007e8e3  lea     r9, [rsp+1A0h+Type]; lpType
0x14007e8e8  xor     r8d, r8d; lpReserved
0x14007e8eb  mov     [rsp+1A0h+phkResult], rdi; lpData
0x14007e8f0  call    cs:__imp_RegQueryValueExW
0x14007e8f6  test    eax, eax
0x14007e8f8  jz      short loc_14007E94D
0x14007e8fa  jmp     loc_14007EB27
0x14007e8ff  cmp     dword ptr [rbx+10h], 1
0x14007e903  ja      loc_14007EB51
0x14007e909  mov     rcx, [rbx+8]
0x14007e90d  or      r15, 0FFFFFFFFFFFFFFFFh
0x14007e911  inc     r15
0x14007e914  cmp     [rcx+r15*2], r14w
0x14007e919  jnz     short loc_14007E911
0x14007e91b  mov     rdx, [rbx]; lpValueName
0x14007e91e  lea     eax, ds:2[r15*2]
0x14007e926  mov     dword ptr [rsp+1A0h+lpcbData], eax; cbData
0x14007e92a  mov     r9d, 1; dwType
0x14007e930  mov     [rsp+1A0h+phkResult], rcx; lpData
0x14007e935  xor     r8d, r8d; Reserved
0x14007e938  mov     rcx, [rsp+1A0h+hKey]; hKey
0x14007e93d  call    cs:__imp_RegSetValueExW
0x14007e943  jmp     loc_14007EB51
0x14007e948  lea     rdi, [rsp+1A0h+Data]
0x14007e94d  mov     ecx, [rsp+1A0h+nSize]
0x14007e951  or      r15, 0FFFFFFFFFFFFFFFFh
0x14007e955  shr     rcx, 1
0x14007e958  mov     r13d, r14d
0x14007e95b  mov     r12, rdi
0x14007e95e  xor     r8d, r8d
0x14007e961  mov     [rdi+rcx*2-2], r14w
0x14007e967  mov     r14, rdi
0x14007e96a  mov     eax, 2Ch ; ','
0x14007e96f  test    r14, r14
0x14007e972  jz      loc_14007EA31
0x14007e978  cmp     [r14], r8w
0x14007e97c  jz      loc_14007EA31
0x14007e982  mov     edx, eax; Ch
0x14007e984  mov     rcx, r14; Str
0x14007e987  call    cs:__imp_wcschr
0x14007e98d  mov     r14, rax
0x14007e990  xor     eax, eax
0x14007e992  test    r14, r14
0x14007e995  jz      short loc_14007E99B
0x14007e997  mov     [r14], ax
0x14007e99b  mov     rdx, [rbx+8]
0x14007e99f  mov     rcx, r12
0x14007e9a2  call    cs:__imp__o__wcsicmp
0x14007e9a8  xor     r8d, r8d
0x14007e9ab  test    eax, eax
0x14007e9ad  jnz     short loc_14007EA17
0x14007e9af  cmp     dword ptr [rbx+10h], 1
0x14007e9b3  jbe     loc_14007EB27
0x14007e9b9  cmp     dword ptr [rbx+10h], 2
0x14007e9bd  jnz     short loc_14007EA17
0x14007e9bf  test    r14, r14
0x14007e9c2  jz      short loc_14007EA07
0x14007e9c4  mov     eax, [rsp+1A0h+nSize]
0x14007e9c8  lea     rdx, [r14+2]; Src
0x14007e9cc  shr     rax, 1
0x14007e9cf  lea     rcx, [rax+rax]
0x14007e9d3  mov     rax, r15
0x14007e9d6  sub     rcx, r14
0x14007e9d9  add     rcx, 0FFFFFFFFFFFFFFFEh
0x14007e9dd  add     rcx, rdi
0x14007e9e0  sar     rcx, 1
0x14007e9e3  inc     rax
0x14007e9e6  cmp     [rdx+rax*2], r8w
0x14007e9eb  jnz     short loc_14007E9E3
0x14007e9ed  inc     eax
0x14007e9ef  cmp     eax, ecx
0x14007e9f1  cmovnb  eax, ecx
0x14007e9f4  mov     rcx, r12; void *
0x14007e9f7  mov     r8d, eax
0x14007e9fa  add     r8, r8; Size
0x14007e9fd  call    memmove_0
0x14007ea02  xor     r8d, r8d
0x14007ea05  jmp     short loc_14007EA0C
0x14007ea07  mov     [r12], r8w
0x14007ea0c  mov     r13d, 1
0x14007ea12  jmp     loc_14007E96A
0x14007ea17  mov     eax, 2Ch ; ','
0x14007ea1c  test    r14, r14
0x14007ea1f  jz      short loc_14007EA31
0x14007ea21  mov     [r14], ax
0x14007ea25  add     r14, 2
0x14007ea29  mov     r12, r14
0x14007ea2c  jmp     loc_14007E96F
0x14007ea31  cmp     dword ptr [rbx+10h], 1
0x14007ea35  ja      loc_14007EAED
0x14007ea3b  mov     rax, [rbx+8]
0x14007ea3f  mov     rcx, r15
0x14007ea42  inc     rcx
0x14007ea45  cmp     [rax+rcx*2], r8w
0x14007ea4a  jnz     short loc_14007EA42
0x14007ea4c  mov     r12d, [rsp+1A0h+nSize]
0x14007ea51  add     r12, 4
0x14007ea55  lea     r12, [r12+rcx*2]
0x14007ea59  xor     ecx, ecx; uFlags
0x14007ea5b  mov     rdx, r12; uBytes
0x14007ea5e  call    cs:__imp_LocalAlloc
0x14007ea64  mov     r14, rax
0x14007ea67  xor     eax, eax
0x14007ea69  test    r14, r14
0x14007ea6c  jz      short loc_14007EAED
0x14007ea6e  shr     r12, 1
0x14007ea71  mov     [r14], ax
0x14007ea75  cmp     dword ptr [rbx+10h], 1
0x14007ea79  jnz     short loc_14007EA9C
0x14007ea7b  mov     r8, [rbx+8]; unsigned __int16 *
0x14007ea7f  mov     rdx, r12; unsigned __int64
0x14007ea82  mov     rcx, r14; unsigned __int16 *
0x14007ea85  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14007ea8a  lea     r8, Delimiter; ","
0x14007ea91  mov     rdx, r12; unsigned __int64
0x14007ea94  mov     rcx, r14; unsigned __int16 *
0x14007ea97  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14007ea9c  mov     r8, rdi; unsigned __int16 *
0x14007ea9f  mov     rdx, r12; unsigned __int64
0x14007eaa2  mov     rcx, r14; unsigned __int16 *
0x14007eaa5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14007eaaa  xor     eax, eax
0x14007eaac  cmp     [rbx+10h], eax
0x14007eaaf  jnz     short loc_14007EAD2
0x14007eab1  lea     r8, Delimiter; ","
0x14007eab8  mov     rdx, r12; unsigned __int64
0x14007eabb  mov     rcx, r14; unsigned __int16 *
0x14007eabe  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14007eac3  mov     r8, [rbx+8]; unsigned __int16 *
0x14007eac7  mov     rdx, r12; unsigned __int64
0x14007eaca  mov     rcx, r14; unsigned __int16 *
0x14007eacd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14007ead2  lea     rax, [rsp+1A0h+Data]
0x14007ead7  cmp     rdi, rax
0x14007eada  jz      short loc_14007EAE5
0x14007eadc  mov     rcx, rdi; hMem
0x14007eadf  call    cs:__imp_LocalFree
0x14007eae5  mov     rdi, r14
0x14007eae8  xor     r14d, r14d
0x14007eaeb  jmp     short loc_14007EAF5
0x14007eaed  xor     r14d, r14d
0x14007eaf0  test    r13d, r13d
0x14007eaf3  jz      short loc_14007EB27
0x14007eaf5  inc     r15
0x14007eaf8  cmp     [rdi+r15*2], r14w
0x14007eafd  jnz     short loc_14007EAF5
0x14007eaff  mov     rdx, [rbx]; lpValueName
0x14007eb02  lea     eax, ds:2[r15*2]
0x14007eb0a  mov     rcx, [rsp+1A0h+hKey]; hKey
0x14007eb0f  mov     r9d, 1; dwType
0x14007eb15  mov     dword ptr [rsp+1A0h+lpcbData], eax; cbData
0x14007eb19  xor     r8d, r8d; Reserved
0x14007eb1c  mov     [rsp+1A0h+phkResult], rdi; lpData
0x14007eb21  call    cs:__imp_RegSetValueExW
0x14007eb27  lea     rax, [rsp+1A0h+Data]
0x14007eb2c  cmp     rdi, rax
0x14007eb2f  jz      short loc_14007EB3A
0x14007eb31  mov     rcx, rdi; hMem
0x14007eb34  call    cs:__imp_LocalFree
0x14007eb3a  test    rsi, rsi
0x14007eb3d  jz      short loc_14007EB51
0x14007eb3f  mov     rcx, rsi; hMem
0x14007eb42  call    cs:__imp_LocalFree
0x14007eb48  mov     rax, [rsp+1A0h+var_158]
0x14007eb4d  mov     [rbx+8], rax
0x14007eb51  mov     rcx, [rsp+1A0h+hKey]; hKey
0x14007eb56  call    cs:__imp_RegCloseKey
0x14007eb5c  mov     rcx, [rbp+0A0h+var_50]
0x14007eb60  xor     rcx, rsp; StackCookie
0x14007eb63  call    __security_check_cookie
0x14007eb68  add     rsp, 168h
0x14007eb6f  pop     r15
0x14007eb71  pop     r14
0x14007eb73  pop     r13
0x14007eb75  pop     r12
0x14007eb77  pop     rdi
0x14007eb78  pop     rsi
0x14007eb79  pop     rbx
0x14007eb7a  pop     rbp
0x14007eb7b  retn
```
