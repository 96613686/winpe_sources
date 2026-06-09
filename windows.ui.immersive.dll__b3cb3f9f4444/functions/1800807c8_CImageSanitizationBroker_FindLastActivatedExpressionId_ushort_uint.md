# CImageSanitizationBroker::_FindLastActivatedExpressionId(ushort *,uint)

- ea: `0x1800807c8`
- end: `0x1800809f4`
- name: `?_FindLastActivatedExpressionId@CImageSanitizationBroker@@AEAAJPEAGI@Z`
- size: `556`
- prototype: `int(CImageSanitizationBroker *__hidden this, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180038940`

## callees

- `0x1800162f0`
- `0x180032908`
- `0x180054130`
- `0x1800807c8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180080877`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180080877`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800809c1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800809c1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180080815`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180080815`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18008095f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18008095f`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180080987`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180080987`
- `api-ms-win-shcore-registry-l1-1-0!SHEnumKeyExW` at `0x1800808d9`
- `api-ms-win-shcore-registry-l1-1-0!SHEnumKeyExW` at `0x1800808d9`

## pseudocode

```c
__int64 __fastcall CImageSanitizationBroker::_FindLastActivatedExpressionId(
        CImageSanitizationBroker *this,
        unsigned __int16 *a2)
{
  LSTATUS v3; // eax
  signed int v4; // ebx
  LSTATUS v5; // eax
  DWORD i; // edi
  LSTATUS v7; // eax
  bool v8; // sf
  LSTATUS ValueW; // eax
  bool v10; // sf
  HKEY hKey; // [rsp+60h] [rbp-59h] BYREF
  DWORD cSubKeys; // [rsp+68h] [rbp-51h] BYREF
  unsigned int v14; // [rsp+6Ch] [rbp-4Dh] BYREF
  DWORD pcbData; // [rsp+70h] [rbp-49h] BYREF
  DWORD pcchName; // [rsp+74h] [rbp-45h] BYREF
  FILETIME pvData; // [rsp+78h] [rbp-41h] BYREF
  FILETIME FileTime1; // [rsp+80h] [rbp-39h] BYREF
  WCHAR pszName[32]; // [rsp+90h] [rbp-29h] BYREF

  hKey = 0;
  v3 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Accent",
         0,
         0x20019u,
         &hKey);
  v4 = v3;
  if ( v3 > 0 )
    v4 = (unsigned __int16)v3 | 0x80070000;
  if ( v4 < 0 )
    goto LABEL_25;
  cSubKeys = 0;
  v5 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
  v4 = v5;
  if ( v5 > 0 )
    v4 = (unsigned __int16)v5 | 0x80070000;
  if ( v4 >= 0 )
  {
    v4 = -2147023728;
    FileTime1 = 0;
    for ( i = 0; ((int)(v4 + 0x80000000) < 0 || v4 == -2147023728) && i < cSubKeys; ++i )
    {
      pcchName = 32;
      v7 = SHEnumKeyExW(hKey, i, pszName, &pcchName);
      v8 = v7 < 0;
      if ( v7 > 0 )
        v8 = 1;
      if ( !v8 )
      {
        v14 = 0;
        pvData = 0;
        if ( (int)SHRegGetDWORD(hKey, pszName, L"HEALS", &v14) >= 0 && (v14 & 0x140) == 0 )
        {
          pcbData = 8;
          ValueW = RegGetValueW(hKey, pszName, L"LastActivated", 8u, 0, &pvData, &pcbData);
          v10 = ValueW < 0;
          if ( ValueW > 0 )
            v10 = 1;
          if ( !v10 && pcbData == 8 && CompareFileTime(&FileTime1, &pvData) < 0 )
          {
            v4 = StringCchCopyW(a2, 0x20u, pszName);
            if ( v4 >= 0 )
              FileTime1 = pvData;
          }
        }
      }
    }
  }
  RegCloseKey(hKey);
  if ( v4 < 0 )
LABEL_25:
    *a2 = 0;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800807c8  push    rbp
0x1800807ca  push    rbx
0x1800807cb  push    rsi
0x1800807cc  push    rdi
0x1800807cd  push    r14
0x1800807cf  push    r15
0x1800807d1  lea     rbp, [rsp-2Fh]
0x1800807d6  sub     rsp, 0E8h
0x1800807dd  mov     rax, cs:__security_cookie
0x1800807e4  xor     rax, rsp
0x1800807e7  mov     [rbp+57h+var_40], rax
0x1800807eb  mov     rsi, rdx
0x1800807ee  lea     rax, [rbp+57h+hKey]
0x1800807f2  xor     r14d, r14d
0x1800807f5  mov     [rsp+110h+phkResult], rax; phkResult
0x1800807fa  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180080801  mov     [rbp+57h+hKey], r14
0x180080805  mov     r9d, 20019h; samDesired
0x18008080b  xor     r8d, r8d; ulOptions
0x18008080e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180080815  call    cs:__imp_RegOpenKeyExW
0x18008081c  nop     dword ptr [rax+rax+00h]
0x180080821  mov     ebx, eax
0x180080823  mov     r15d, 80070000h
0x180080829  test    eax, eax
0x18008082b  jle     short loc_180080833
0x18008082d  movzx   ebx, ax
0x180080830  or      ebx, r15d
0x180080833  test    ebx, ebx
0x180080835  js      loc_1800809D1
0x18008083b  mov     rcx, [rbp+57h+hKey]; hKey
0x18008083f  lea     rax, [rbp+57h+cSubKeys]
0x180080843  mov     [rsp+110h+lpftLastWriteTime], r14; lpftLastWriteTime
0x180080848  xor     r9d, r9d; lpReserved
0x18008084b  mov     [rsp+110h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x180080850  xor     r8d, r8d; lpcchClass
0x180080853  mov     [rsp+110h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x180080858  xor     edx, edx; lpClass
0x18008085a  mov     [rsp+110h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x18008085f  mov     [rsp+110h+lpcValues], r14; lpcValues
0x180080864  mov     [rsp+110h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x180080869  mov     [rsp+110h+lpcbMaxSubKeyLen], r14; lpcbMaxSubKeyLen
0x18008086e  mov     [rsp+110h+phkResult], rax; lpcSubKeys
0x180080873  mov     [rbp+57h+cSubKeys], r14d
0x180080877  call    cs:__imp_RegQueryInfoKeyW
0x18008087e  nop     dword ptr [rax+rax+00h]
0x180080883  mov     ebx, eax
0x180080885  test    eax, eax
0x180080887  jle     short loc_18008088F
0x180080889  movzx   ebx, ax
0x18008088c  or      ebx, r15d
0x18008088f  test    ebx, ebx
0x180080891  js      loc_1800809BD
0x180080897  mov     ebx, 80070490h
0x18008089c  mov     qword ptr [rbp+57h+FileTime1.dwLowDateTime], r14
0x1800808a0  mov     edi, r14d
0x1800808a3  mov     ecx, 80000000h
0x1800808a8  lea     eax, [rbx+rcx]
0x1800808ab  test    ecx, eax
0x1800808ad  jnz     short loc_1800808BB
0x1800808af  cmp     ebx, 80070490h
0x1800808b5  jnz     loc_1800809BD
0x1800808bb  cmp     edi, [rbp+57h+cSubKeys]
0x1800808be  jnb     loc_1800809BD
0x1800808c4  mov     rcx, [rbp+57h+hKey]; hkey
0x1800808c8  lea     r9, [rbp+57h+pcchName]; pcchName
0x1800808cc  lea     r8, [rbp+57h+pszName]; pszName
0x1800808d0  mov     [rbp+57h+pcchName], 20h ; ' '
0x1800808d7  mov     edx, edi; dwIndex
0x1800808d9  call    cs:__imp_SHEnumKeyExW
0x1800808e0  nop     dword ptr [rax+rax+00h]
0x1800808e5  test    eax, eax
0x1800808e7  jle     short loc_1800808F1
0x1800808e9  movzx   eax, ax
0x1800808ec  or      eax, r15d
0x1800808ef  test    eax, eax
0x1800808f1  js      loc_1800809B6
0x1800808f7  mov     rcx, [rbp+57h+hKey]; HKEY
0x1800808fb  lea     r9, [rbp+57h+var_A4]; unsigned int *
0x1800808ff  lea     r8, aHeals; "HEALS"
0x180080906  mov     [rbp+57h+var_A4], r14d
0x18008090a  lea     rdx, [rbp+57h+pszName]; unsigned __int16 *
0x18008090e  mov     [rbp+57h+pvData], r14
0x180080912  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180080917  test    eax, eax
0x180080919  js      loc_1800809B6
0x18008091f  test    [rbp+57h+var_A4], 140h
0x180080926  jnz     loc_1800809B6
0x18008092c  mov     rcx, [rbp+57h+hKey]; hkey
0x180080930  lea     rax, [rbp+57h+pcbData]
0x180080934  mov     [rsp+110h+lpcbMaxClassLen], rax; pcbData
0x180080939  lea     r8, aLastactivated; "LastActivated"
0x180080940  lea     rax, [rbp+57h+pvData]
0x180080944  mov     [rbp+57h+pcbData], 8
0x18008094b  mov     [rsp+110h+lpcbMaxSubKeyLen], rax; pvData
0x180080950  lea     rdx, [rbp+57h+pszName]; lpSubKey
0x180080954  mov     r9d, 8; dwFlags
0x18008095a  mov     [rsp+110h+phkResult], r14; pdwType
0x18008095f  call    cs:__imp_RegGetValueW
0x180080966  nop     dword ptr [rax+rax+00h]
0x18008096b  test    eax, eax
0x18008096d  jle     short loc_180080977
0x18008096f  movzx   eax, ax
0x180080972  or      eax, r15d
0x180080975  test    eax, eax
0x180080977  js      short loc_1800809B6
0x180080979  cmp     [rbp+57h+pcbData], 8
0x18008097d  jnz     short loc_1800809B6
0x18008097f  lea     rdx, [rbp+57h+pvData]; lpFileTime2
0x180080983  lea     rcx, [rbp+57h+FileTime1]; lpFileTime1
0x180080987  call    cs:__imp_CompareFileTime
0x18008098e  nop     dword ptr [rax+rax+00h]
0x180080993  test    eax, eax
0x180080995  jns     short loc_1800809B6
0x180080997  lea     r8, [rbp+57h+pszName]; unsigned __int16 *
0x18008099b  mov     edx, 20h ; ' '; unsigned __int64
0x1800809a0  mov     rcx, rsi; unsigned __int16 *
0x1800809a3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800809a8  mov     ebx, eax
0x1800809aa  test    eax, eax
0x1800809ac  js      short loc_1800809B6
0x1800809ae  mov     rax, [rbp+57h+pvData]
0x1800809b2  mov     qword ptr [rbp+57h+FileTime1.dwLowDateTime], rax
0x1800809b6  inc     edi
0x1800809b8  jmp     loc_1800808A3
0x1800809bd  mov     rcx, [rbp+57h+hKey]; hKey
0x1800809c1  call    cs:__imp_RegCloseKey
0x1800809c8  nop     dword ptr [rax+rax+00h]
0x1800809cd  test    ebx, ebx
0x1800809cf  jns     short loc_1800809D5
0x1800809d1  mov     [rsi], r14w
0x1800809d5  mov     eax, ebx
0x1800809d7  mov     rcx, [rbp+57h+var_40]
0x1800809db  xor     rcx, rsp; StackCookie
0x1800809de  call    __security_check_cookie
0x1800809e3  add     rsp, 0E8h
0x1800809ea  pop     r15
0x1800809ec  pop     r14
0x1800809ee  pop     rdi
0x1800809ef  pop     rsi
0x1800809f0  pop     rbx
0x1800809f1  pop     rbp
0x1800809f2  retn
```
