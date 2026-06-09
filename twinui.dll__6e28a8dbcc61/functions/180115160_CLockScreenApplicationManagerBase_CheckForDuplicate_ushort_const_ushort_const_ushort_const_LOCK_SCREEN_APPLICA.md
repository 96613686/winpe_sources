# CLockScreenApplicationManagerBase::_CheckForDuplicate(ushort const *,ushort const *,ushort const *,LOCK_SCREEN_APPLICATION_CAPABILITIES,uint *)

- ea: `0x180115160`
- end: `0x180115468`
- name: `?_CheckForDuplicate@CLockScreenApplicationManagerBase@@IEAAJPEBG00W4LOCK_SCREEN_APPLICATION_CAPABILITIES@@PEAI@Z`
- size: `776`
- prototype: `__int64 __fastcall(__int64, __int64, const WCHAR *, const WCHAR *, int, _DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180371b38`

## callees

- `0x18004719c`
- `0x180115160`
- `0x18013d330`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18011532c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180115357`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801153e0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18011540a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18011532c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180115357`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801153e0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18011540a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801153a3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801153a3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18011542d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18011542d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180115218`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180115218`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180115294`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180115294`
- `api-ms-win-shcore-registry-l1-1-0!SHEnumKeyExW` at `0x1801152f8`
- `api-ms-win-shcore-registry-l1-1-0!SHEnumKeyExW` at `0x1801152f8`

## pseudocode

```c
__int64 __fastcall CLockScreenApplicationManagerBase::_CheckForDuplicate(
        __int64 a1,
        __int64 a2,
        const WCHAR *a3,
        const WCHAR *a4,
        int a5,
        _DWORD *a6)
{
  const wchar_t *v8; // rax
  signed int v9; // ebx
  LSTATUS v10; // eax
  LSTATUS v11; // eax
  DWORD v12; // edi
  unsigned int v13; // eax
  LSTATUS v14; // eax
  LSTATUS ValueW; // eax
  bool v16; // sf
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  DWORD pcchName; // [rsp+70h] [rbp-90h] BYREF
  DWORD pcbData[3]; // [rsp+74h] [rbp-8Ch] BYREF
  WCHAR pszName[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR pvData[264]; // [rsp+290h] [rbp+190h] BYREF
  WCHAR SubKey[264]; // [rsp+4A0h] [rbp+3A0h] BYREF

  if ( a5 == 1 )
  {
    v8 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\Notifications\\Tile";
  }
  else
  {
    v8 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\Notifications\\Badge";
    if ( a5 != 2 )
      v8 = L"BadKey";
  }
  v9 = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", a2, v8);
  if ( v9 >= 0 )
  {
    hKey = 0;
    v10 = RegOpenKeyExW(HKEY_USERS, SubKey, 0, 0x20019u, &hKey);
    v9 = v10;
    if ( v10 > 0 )
      v9 = (unsigned __int16)v10 | 0x80070000;
    if ( v9 < 0 )
    {
      if ( v9 == -2147024894 )
        return 0;
    }
    else
    {
      cSubKeys = 0;
      v11 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
      v9 = v11;
      if ( v11 > 0 )
        v9 = (unsigned __int16)v11 | 0x80070000;
      if ( v9 >= 0 )
      {
        v12 = 0;
        while ( v12 < cSubKeys )
        {
          if ( a5 == 1 )
          {
            v13 = 1;
          }
          else
          {
            v13 = 0;
            if ( a5 == 2 )
              v13 = 7;
          }
          if ( v12 >= v13 )
            break;
          pcchName = 260;
          v14 = SHEnumKeyExW(hKey, v12, pszName, &pcchName);
          v9 = v14;
          if ( v14 > 0 )
            v9 = (unsigned __int16)v14 | 0x80070000;
          if ( v9 < 0 )
            goto LABEL_33;
          if ( CompareStringOrdinal(pszName, -1, a3, -1, 1) == 2
            || a4 && CompareStringOrdinal(pszName, -1, a4, -1, 1) == 2 )
          {
            goto LABEL_32;
          }
          pcbData[0] = 520;
          ValueW = RegGetValueW(hKey, pszName, L"ParentAppId", 2u, 0, pvData, pcbData);
          v16 = ValueW < 0;
          if ( ValueW )
          {
            pvData[0] = 0;
            v16 = ValueW < 0;
            if ( ValueW > 0 )
              v16 = 1;
          }
          if ( !v16
            && (CompareStringOrdinal(pvData, -1, a3, -1, 1) == 2
             || a4 && CompareStringOrdinal(pvData, -1, a4, -1, 1) == 2) )
          {
LABEL_32:
            ++*a6;
            ++v12;
          }
          else
          {
LABEL_33:
            ++v12;
            if ( v9 < 0 )
              break;
          }
        }
      }
      RegCloseKey(hKey);
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180115160  mov     [rsp-8+arg_0], rbx
0x180115165  push    rbp
0x180115166  push    rsi
0x180115167  push    rdi
0x180115168  push    r12
0x18011516a  push    r15
0x18011516c  lea     rbp, [rsp-5C0h]
0x180115174  sub     rsp, 6C0h
0x18011517b  mov     rax, cs:__security_cookie
0x180115182  xor     rax, rsp
0x180115185  mov     [rbp+5E0h+var_30], rax
0x18011518c  cmp     [rbp+5E0h+arg_20], 1
0x180115193  mov     r15, r9
0x180115196  mov     rsi, [rbp+5E0h+arg_28]
0x18011519d  mov     r12, r8
0x1801151a0  jnz     short loc_1801151AB
0x1801151a2  lea     rax, aSoftwareMicros_59; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1801151a9  jmp     short loc_1801151C4
0x1801151ab  cmp     [rbp+5E0h+arg_20], 2
0x1801151b2  lea     rax, aSoftwareMicros_78; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1801151b9  lea     rcx, aBadkey; "BadKey"
0x1801151c0  cmovnz  rax, rcx
0x1801151c4  mov     r9, rdx
0x1801151c7  mov     [rsp+6E0h+phkResult], rax
0x1801151cc  mov     edx, 104h; unsigned __int64
0x1801151d1  lea     r8, aSS_2; "%s\\%s"
0x1801151d8  lea     rcx, [rbp+5E0h+SubKey]; unsigned __int16 *
0x1801151df  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801151e4  mov     ebx, eax
0x1801151e6  test    eax, eax
0x1801151e8  js      loc_180115440
0x1801151ee  lea     rax, [rsp+6E0h+hKey]
0x1801151f3  mov     [rsp+6E0h+hKey], 0
0x1801151fc  mov     r9d, 20019h; samDesired
0x180115202  mov     [rsp+6E0h+phkResult], rax; phkResult
0x180115207  xor     r8d, r8d; ulOptions
0x18011520a  lea     rdx, [rbp+5E0h+SubKey]; lpSubKey
0x180115211  mov     rcx, 0FFFFFFFF80000003h; hKey
0x180115218  call    cs:__imp_RegOpenKeyExW
0x18011521e  mov     ebx, eax
0x180115220  mov     edi, 80070000h
0x180115225  test    eax, eax
0x180115227  jle     short loc_18011522E
0x180115229  movzx   ebx, ax
0x18011522c  or      ebx, edi
0x18011522e  test    ebx, ebx
0x180115230  js      loc_180115435
0x180115236  mov     rcx, [rsp+6E0h+hKey]; hKey
0x18011523b  lea     rax, [rsp+6E0h+cSubKeys]
0x180115240  mov     [rsp+6E0h+lpftLastWriteTime], 0; lpftLastWriteTime
0x180115249  xor     r9d, r9d; lpReserved
0x18011524c  mov     [rsp+6E0h+lpcbSecurityDescriptor], 0; lpcbSecurityDescriptor
0x180115255  xor     r8d, r8d; lpcchClass
0x180115258  mov     [rsp+6E0h+lpcbMaxValueLen], 0; lpcbMaxValueLen
0x180115261  xor     edx, edx; lpClass
0x180115263  mov     [rsp+6E0h+lpcbMaxValueNameLen], 0; lpcbMaxValueNameLen
0x18011526c  mov     [rsp+6E0h+lpcValues], 0; lpcValues
0x180115275  mov     [rsp+6E0h+lpcbMaxClassLen], 0; lpcbMaxClassLen
0x18011527e  mov     [rsp+6E0h+lpcbMaxSubKeyLen], 0; lpcbMaxSubKeyLen
0x180115287  mov     [rsp+6E0h+phkResult], rax; lpcSubKeys
0x18011528c  mov     [rsp+6E0h+cSubKeys], 0
0x180115294  call    cs:__imp_RegQueryInfoKeyW
0x18011529a  mov     ebx, eax
0x18011529c  test    eax, eax
0x18011529e  jle     short loc_1801152A5
0x1801152a0  movzx   ebx, ax
0x1801152a3  or      ebx, edi
0x1801152a5  test    ebx, ebx
0x1801152a7  js      loc_180115428
0x1801152ad  xor     edi, edi
0x1801152af  cmp     edi, [rsp+6E0h+cSubKeys]
0x1801152b3  jnb     loc_180115428
0x1801152b9  cmp     [rbp+5E0h+arg_20], 1
0x1801152c0  jnz     short loc_1801152C9
0x1801152c2  mov     eax, 1
0x1801152c7  jmp     short loc_1801152D8
0x1801152c9  xor     eax, eax
0x1801152cb  cmp     [rbp+5E0h+arg_20], 2
0x1801152d2  lea     ecx, [rax+7]
0x1801152d5  cmovz   eax, ecx
0x1801152d8  cmp     edi, eax
0x1801152da  jnb     loc_180115428
0x1801152e0  mov     rcx, [rsp+6E0h+hKey]; hkey
0x1801152e5  lea     r9, [rsp+6E0h+pcchName]; pcchName
0x1801152ea  lea     r8, [rbp+5E0h+pszName]; pszName
0x1801152ee  mov     [rsp+6E0h+pcchName], 104h
0x1801152f6  mov     edx, edi; dwIndex
0x1801152f8  call    cs:__imp_SHEnumKeyExW
0x1801152fe  mov     ebx, eax
0x180115300  test    eax, eax
0x180115302  jle     short loc_18011530D
0x180115304  movzx   ebx, ax
0x180115307  or      ebx, 80070000h
0x18011530d  test    ebx, ebx
0x18011530f  js      loc_18011541E
0x180115315  or      eax, 0FFFFFFFFh
0x180115318  mov     dword ptr [rsp+6E0h+phkResult], 1; bIgnoreCase
0x180115320  mov     r9d, eax; cchCount2
0x180115323  lea     rcx, [rbp+5E0h+pszName]; lpString1
0x180115327  mov     edx, eax; cchCount1
0x180115329  mov     r8, r12; lpString2
0x18011532c  call    cs:__imp_CompareStringOrdinal
0x180115332  cmp     eax, 2
0x180115335  jz      loc_180115415
0x18011533b  test    r15, r15
0x18011533e  jz      short loc_180115366
0x180115340  or      eax, 0FFFFFFFFh
0x180115343  mov     dword ptr [rsp+6E0h+phkResult], 1; bIgnoreCase
0x18011534b  mov     r9d, eax; cchCount2
0x18011534e  lea     rcx, [rbp+5E0h+pszName]; lpString1
0x180115352  mov     edx, eax; cchCount1
0x180115354  mov     r8, r15; lpString2
0x180115357  call    cs:__imp_CompareStringOrdinal
0x18011535d  cmp     eax, 2
0x180115360  jz      loc_180115415
0x180115366  mov     rcx, [rsp+6E0h+hKey]; hkey
0x18011536b  lea     rax, [rsp+6E0h+pcbData]
0x180115370  mov     [rsp+6E0h+lpcbMaxClassLen], rax; pcbData
0x180115375  lea     r8, aParentappid; "ParentAppId"
0x18011537c  lea     rax, [rbp+5E0h+pvData]
0x180115383  mov     [rsp+6E0h+pcbData], 208h
0x18011538b  mov     [rsp+6E0h+lpcbMaxSubKeyLen], rax; pvData
0x180115390  lea     rdx, [rbp+5E0h+pszName]; lpSubKey
0x180115394  mov     r9d, 2; dwFlags
0x18011539a  mov     [rsp+6E0h+phkResult], 0; pdwType
0x1801153a3  call    cs:__imp_RegGetValueW
0x1801153a9  test    eax, eax
0x1801153ab  jz      short loc_1801153C4
0x1801153ad  xor     ecx, ecx
0x1801153af  mov     [rbp+5E0h+pvData], cx
0x1801153b6  test    eax, eax
0x1801153b8  jle     short loc_1801153C4
0x1801153ba  movzx   eax, ax
0x1801153bd  or      eax, 80070000h
0x1801153c2  test    eax, eax
0x1801153c4  js      short loc_18011541E
0x1801153c6  or      eax, 0FFFFFFFFh
0x1801153c9  mov     dword ptr [rsp+6E0h+phkResult], 1; bIgnoreCase
0x1801153d1  mov     r9d, eax; cchCount2
0x1801153d4  lea     rcx, [rbp+5E0h+pvData]; lpString1
0x1801153db  mov     edx, eax; cchCount1
0x1801153dd  mov     r8, r12; lpString2
0x1801153e0  call    cs:__imp_CompareStringOrdinal
0x1801153e6  cmp     eax, 2
0x1801153e9  jz      short loc_180115415
0x1801153eb  test    r15, r15
0x1801153ee  jz      short loc_18011541E
0x1801153f0  or      eax, 0FFFFFFFFh
0x1801153f3  mov     dword ptr [rsp+6E0h+phkResult], 1; bIgnoreCase
0x1801153fb  mov     r9d, eax; cchCount2
0x1801153fe  lea     rcx, [rbp+5E0h+pvData]; lpString1
0x180115405  mov     edx, eax; cchCount1
0x180115407  mov     r8, r15; lpString2
0x18011540a  call    cs:__imp_CompareStringOrdinal
0x180115410  cmp     eax, 2
0x180115413  jnz     short loc_18011541E
0x180115415  inc     dword ptr [rsi]
0x180115417  inc     edi
0x180115419  jmp     loc_1801152AF
0x18011541e  inc     edi
0x180115420  test    ebx, ebx
0x180115422  jns     loc_1801152AF
0x180115428  mov     rcx, [rsp+6E0h+hKey]; hKey
0x18011542d  call    cs:__imp_RegCloseKey
0x180115433  jmp     short loc_180115440
0x180115435  xor     eax, eax
0x180115437  cmp     ebx, 80070002h
0x18011543d  cmovz   ebx, eax
0x180115440  mov     eax, ebx
0x180115442  mov     rcx, [rbp+5E0h+var_30]
0x180115449  xor     rcx, rsp; StackCookie
0x18011544c  call    __security_check_cookie
0x180115451  mov     rbx, [rsp+6E0h+arg_0]
0x180115459  add     rsp, 6C0h
0x180115460  pop     r15
0x180115462  pop     r12
0x180115464  pop     rdi
0x180115465  pop     rsi
0x180115466  pop     rbp
0x180115467  retn
```
