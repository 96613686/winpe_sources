# ShadowAdminAccount::QueryShadowAdminAccountFromRegistry(void * *)

- ea: `0x180092ca8`
- end: `0x180092e66`
- name: `?QueryShadowAdminAccountFromRegistry@ShadowAdminAccount@@AEAAJPEAPEAX@Z`
- size: `446`
- prototype: `__int64 __fastcall(ShadowAdminAccount *__hidden this, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180091c80`

## callees

- `0x180023760`
- `0x180027e24`
- `0x1800372ac`
- `0x180092ca8`
- `0x1800ad05c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092d78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092d78`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180092cf5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180092cf5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180092e29`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180092e29`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180092e06`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180092e10`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180092e1a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180092e06`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180092e10`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180092e1a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180092d6e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180092d6e`

## pseudocode

```c
__int64 __fastcall ShadowAdminAccount::QueryShadowAdminAccountFromRegistry(ShadowAdminAccount *this, void **a2)
{
  void *v2; // rdi
  const WCHAR *v4; // rdx
  LSTATUS v5; // eax
  unsigned __int16 *v6; // rdx
  unsigned int v7; // ebx
  int RegistryStringValue; // eax
  DWORD LastError; // eax
  int v10; // eax
  void *v12; // [rsp+60h] [rbp+28h] BYREF
  PSID Sid; // [rsp+68h] [rbp+30h] BYREF
  LPCWSTR StringSid; // [rsp+70h] [rbp+38h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+40h] BYREF

  v2 = 0;
  hKey = 0;
  *a2 = 0;
  StringSid = 0;
  v4 = (const WCHAR *)*((_QWORD *)this + 12);
  Sid = 0;
  v12 = 0;
  v5 = RegOpenKeyExW((HKEY)SampKey, v4, 0, 0x20019u, &hKey);
  if ( v5 == 2 )
  {
    v7 = -1073741772;
    goto LABEL_19;
  }
  if ( v5 )
    goto LABEL_4;
  RegistryStringValue = SampQueryRegistryStringValue(hKey, v6, (unsigned __int16 **)&StringSid);
  v7 = RegistryStringValue;
  if ( RegistryStringValue >= 0 )
  {
    if ( !ConvertStringSidToSidW(StringSid, &Sid) )
    {
      LastError = GetLastError();
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x400) != 0
        && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
      {
        WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 32, WPP_99473abb2ee73b6c7cc9b39fb0106789_Traceguids, LastError);
      }
LABEL_4:
      v7 = -1073741801;
      goto LABEL_19;
    }
    v10 = SampCopySid(&v12, Sid);
    v7 = v10;
    if ( v10 >= 0 )
    {
      *a2 = v12;
    }
    else
    {
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x400) != 0
        && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
      {
        WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 33, WPP_99473abb2ee73b6c7cc9b39fb0106789_Traceguids, (unsigned int)v10);
      }
      v2 = v12;
    }
  }
  else if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x400) != 0
         && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control[3].Buffer,
      31,
      WPP_99473abb2ee73b6c7cc9b39fb0106789_Traceguids,
      (unsigned int)RegistryStringValue);
  }
LABEL_19:
  LocalFree(v2);
  LocalFree(Sid);
  LocalFree((HLOCAL)StringSid);
  if ( hKey )
    RegCloseKey(hKey);
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 34, WPP_99473abb2ee73b6c7cc9b39fb0106789_Traceguids, v7, v7);
  return v7;
}

```

## disassembly

```asm
0x180092ca8  push    rbp
0x180092caa  push    rbx
0x180092cab  push    rsi
0x180092cac  push    rdi
0x180092cad  mov     rbp, rsp
0x180092cb0  sub     rsp, 38h
0x180092cb4  xor     edi, edi
0x180092cb6  mov     [rbp+hKey], 0
0x180092cbe  mov     [rdx], rdi
0x180092cc1  lea     rax, [rbp+hKey]
0x180092cc5  mov     rsi, rdx
0x180092cc8  mov     [rbp+StringSid], 0
0x180092cd0  mov     rdx, [rcx+60h]; lpSubKey
0x180092cd4  mov     r9d, 20019h; samDesired
0x180092cda  mov     rcx, cs:SampKey; hKey
0x180092ce1  xor     r8d, r8d; ulOptions
0x180092ce4  mov     [rbp+Sid], 0
0x180092cec  mov     [rbp+arg_0], rdi
0x180092cf0  mov     [rsp+38h+phkResult], rax; phkResult
0x180092cf5  call    cs:__imp_RegOpenKeyExW
0x180092cfb  cmp     eax, 2
0x180092cfe  jnz     short loc_180092D0A
0x180092d00  mov     ebx, 0C0000034h
0x180092d05  jmp     loc_180092E03
0x180092d0a  test    eax, eax
0x180092d0c  jz      short loc_180092D18
0x180092d0e  mov     ebx, 0C0000017h
0x180092d13  jmp     loc_180092E03
0x180092d18  mov     rcx, [rbp+hKey]; hKey
0x180092d1c  lea     r8, [rbp+StringSid]; unsigned __int16 **
0x180092d20  call    ?SampQueryRegistryStringValue@@YAJPEAUHKEY__@@PEAGPEAPEAG@Z; SampQueryRegistryStringValue(HKEY__ *,ushort *,ushort * *)
0x180092d25  mov     ebx, eax
0x180092d27  test    eax, eax
0x180092d29  jns     short loc_180092D66
0x180092d2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180092d32  test    dword ptr [rcx+44h], 400h
0x180092d39  jz      loc_180092E03
0x180092d3f  cmp     byte ptr [rcx+41h], 2
0x180092d43  jb      loc_180092E03
0x180092d49  mov     rcx, [rcx+38h]
0x180092d4d  lea     r8, WPP_99473abb2ee73b6c7cc9b39fb0106789_Traceguids
0x180092d54  mov     edx, 1Fh
0x180092d59  mov     r9d, eax
0x180092d5c  call    WPP_SF_d
0x180092d61  jmp     loc_180092E03
0x180092d66  mov     rcx, [rbp+StringSid]; StringSid
0x180092d6a  lea     rdx, [rbp+Sid]; Sid
0x180092d6e  call    cs:__imp_ConvertStringSidToSidW
0x180092d74  test    eax, eax
0x180092d76  jnz     short loc_180092DB5
0x180092d78  call    cs:__imp_GetLastError
0x180092d7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180092d85  test    dword ptr [rcx+44h], 400h
0x180092d8c  jz      short loc_180092D0E
0x180092d8e  cmp     byte ptr [rcx+41h], 2
0x180092d92  jb      loc_180092D0E
0x180092d98  mov     rcx, [rcx+38h]
0x180092d9c  lea     r8, WPP_99473abb2ee73b6c7cc9b39fb0106789_Traceguids
0x180092da3  mov     edx, 20h ; ' '
0x180092da8  mov     r9d, eax
0x180092dab  call    WPP_SF_d
0x180092db0  jmp     loc_180092D0E
0x180092db5  mov     rdx, [rbp+Sid]; void *
0x180092db9  lea     rcx, [rbp+arg_0]; void **
0x180092dbd  call    ?SampCopySid@@YAJPEAPEAXPEAX@Z; SampCopySid(void * *,void *)
0x180092dc2  mov     ebx, eax
0x180092dc4  test    eax, eax
0x180092dc6  jns     short loc_180092DFC
0x180092dc8  mov     rcx, cs:WPP_GLOBAL_Control
0x180092dcf  test    dword ptr [rcx+44h], 400h
0x180092dd6  jz      short loc_180092DF6
0x180092dd8  cmp     byte ptr [rcx+41h], 2
0x180092ddc  jb      short loc_180092DF6
0x180092dde  mov     rcx, [rcx+38h]
0x180092de2  lea     r8, WPP_99473abb2ee73b6c7cc9b39fb0106789_Traceguids
0x180092de9  mov     edx, 21h ; '!'
0x180092dee  mov     r9d, eax
0x180092df1  call    WPP_SF_d
0x180092df6  mov     rdi, [rbp+arg_0]
0x180092dfa  jmp     short loc_180092E03
0x180092dfc  mov     rax, [rbp+arg_0]
0x180092e00  mov     [rsi], rax
0x180092e03  mov     rcx, rdi; hMem
0x180092e06  call    cs:__imp_LocalFree
0x180092e0c  mov     rcx, [rbp+Sid]; hMem
0x180092e10  call    cs:__imp_LocalFree
0x180092e16  mov     rcx, [rbp+StringSid]; hMem
0x180092e1a  call    cs:__imp_LocalFree
0x180092e20  mov     rcx, [rbp+hKey]; hKey
0x180092e24  test    rcx, rcx
0x180092e27  jz      short loc_180092E2F
0x180092e29  call    cs:__imp_RegCloseKey
0x180092e2f  mov     rcx, cs:WPP_GLOBAL_Control
0x180092e36  test    dword ptr [rcx+44h], 20000h
0x180092e3d  jz      short loc_180092E5B
0x180092e3f  mov     rcx, [rcx+38h]
0x180092e43  lea     r8, WPP_99473abb2ee73b6c7cc9b39fb0106789_Traceguids
0x180092e4a  mov     edx, 22h ; '"'
0x180092e4f  mov     dword ptr [rsp+38h+phkResult], ebx
0x180092e53  mov     r9d, ebx
0x180092e56  call    WPP_SF_Dd
0x180092e5b  mov     eax, ebx
0x180092e5d  add     rsp, 38h
0x180092e61  pop     rdi
0x180092e62  pop     rsi
0x180092e63  pop     rbx
0x180092e64  pop     rbp
0x180092e65  retn
```
