# SHPinDllOfCLSID

- ea: `0x180002bb0`
- end: `0x180002e65`
- name: `SHPinDllOfCLSID`
- size: `693`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180024830`

## callees

- `0x180002bb0`
- `0x180003400`
- `0x1800035f0`
- `0x18000fb88`
- `0x180012550`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180002e33`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180002e33`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002e41`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002e41`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002de8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002de8`
- `api-ms-win-shcore-registry-l1-1-0!SHQueryValueExW` at `0x180002e1d`
- `api-ms-win-shcore-registry-l1-1-0!SHQueryValueExW` at `0x180002e1d`

## string_xrefs

- `0x180002c7a`: `CLSID\`

## pseudocode

```c
HMODULE __fastcall SHPinDllOfCLSID(__int64 a1)
{
  HMODULE Library; // rbx
  int v2; // eax
  __int64 v3; // r11
  unsigned __int64 v4; // rdi
  __int64 v5; // rdx
  WCHAR *v6; // rax
  __int64 v7; // r8
  const wchar_t *v8; // r9
  __int64 v9; // r10
  WCHAR *v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rdx
  WCHAR *v13; // rcx
  __int64 v14; // rdx
  WCHAR *v15; // rax
  __int64 v16; // r8
  WCHAR *v17; // r9
  __int64 v18; // rcx
  WCHAR *v19; // rax
  __int64 v20; // rdx
  WCHAR *v21; // rcx
  __int64 v22; // rdx
  WCHAR *v23; // rax
  __int64 v24; // r8
  WCHAR *v25; // rax
  const wchar_t *v26; // rcx
  __int64 i; // r11
  WCHAR *v28; // rdx
  HKEY hkey; // [rsp+30h] [rbp-D0h] BYREF
  DWORD pcbData; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR SubKey[168]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v33[80]; // [rsp+190h] [rbp+90h] BYREF
  WCHAR pvData[264]; // [rsp+1E0h] [rbp+E0h] BYREF

  Library = 0;
  if ( (int)SHStringFromGUIDW(a1, v33, 39) >= 0 )
  {
    pcbData = 0;
    v2 = SHIsCurrentAppElevated(&pcbData);
    v3 = 167;
    if ( v2 < 0 || pcbData )
    {
      v4 = -2147483646;
      if ( (int)StringCchCopyW(SubKey, 0xA7u, L"Software\\Classes\\") < 0 )
        return Library;
    }
    else
    {
      v4 = 0xFFFFFFFF80000000uLL;
      SubKey[0] = 0;
    }
    v5 = v3;
    v6 = SubKey;
    do
    {
      if ( !*v6 )
        break;
      ++v6;
      --v5;
    }
    while ( v5 );
    v7 = (v3 - v5) & -(__int64)(v5 != 0);
    if ( v5 )
    {
      v8 = L"CLSID\\";
      v9 = 2147483646;
      v10 = &SubKey[v7];
      v11 = 2147483646;
      v12 = v3 - v7;
      if ( v3 != v7 )
      {
        do
        {
          if ( !v11 )
            break;
          if ( !*v8 )
            break;
          *v10++ = *v8++;
          --v11;
          --v12;
        }
        while ( v12 );
      }
      v13 = v10 - 1;
      if ( v12 )
        v13 = v10;
      *v13 = 0;
      if ( v12 )
      {
        v14 = v3;
        v15 = SubKey;
        do
        {
          if ( !*v15 )
            break;
          ++v15;
          --v14;
        }
        while ( v14 );
        v16 = (v3 - v14) & -(__int64)(v14 != 0);
        if ( v14 )
        {
          v17 = (WCHAR *)v33;
          v18 = 2147483646;
          v19 = &SubKey[v16];
          v20 = v3 - v16;
          if ( v3 != v16 )
          {
            do
            {
              if ( !v18 )
                break;
              if ( !*v17 )
                break;
              *v19++ = *v17++;
              --v18;
              --v20;
            }
            while ( v20 );
          }
          v21 = v19 - 1;
          if ( v20 )
            v21 = v19;
          *v21 = 0;
          if ( v20 )
          {
            v22 = v3;
            v23 = SubKey;
            do
            {
              if ( !*v23 )
                break;
              ++v23;
              --v22;
            }
            while ( v22 );
            v24 = (v3 - v22) & -(__int64)(v22 != 0);
            if ( v22 )
            {
              v25 = &SubKey[v24];
              v26 = L"\\InProcServer32";
              for ( i = v3 - v24; i; --i )
              {
                if ( !v9 )
                  break;
                if ( !*v26 )
                  break;
                *v25++ = *v26++;
                --v9;
              }
              v28 = v25 - 1;
              if ( i )
                v28 = v25;
              *v28 = 0;
              if ( i )
              {
                hkey = 0;
                if ( !RegOpenKeyExW((HKEY)v4, SubKey, 0, 1u, &hkey) )
                {
                  pcbData = 520;
                  if ( !SHQueryValueExW(hkey, 0, 0, 0, pvData, &pcbData) )
                    Library = LoadLibraryExW(pvData, 0, 0);
                  RegCloseKey(hkey);
                }
              }
            }
          }
        }
      }
    }
  }
  return Library;
}

```

## disassembly

```asm
0x180002bb0  push    rbp
0x180002bb2  push    rbx
0x180002bb3  push    rsi
0x180002bb4  push    rdi
0x180002bb5  lea     rbp, [rsp-308h]
0x180002bbd  sub     rsp, 408h
0x180002bc4  mov     rax, cs:__security_cookie
0x180002bcb  xor     rax, rsp
0x180002bce  mov     [rbp+320h+var_30], rax
0x180002bd5  xor     esi, esi
0x180002bd7  lea     rdx, [rbp+320h+var_290]
0x180002bde  mov     ebx, esi
0x180002be0  lea     r8d, [rsi+27h]
0x180002be4  call    SHStringFromGUIDW
0x180002be9  test    eax, eax
0x180002beb  js      loc_180002E47
0x180002bf1  lea     rcx, [rsp+420h+var_3E8]
0x180002bf6  mov     [rsp+420h+var_3E8], esi
0x180002bfa  call    SHIsCurrentAppElevated
0x180002bff  mov     r11d, 0A7h
0x180002c05  test    eax, eax
0x180002c07  js      short loc_180002C1D
0x180002c09  cmp     [rsp+420h+var_3E8], esi
0x180002c0d  jnz     short loc_180002C1D
0x180002c0f  mov     rdi, 0FFFFFFFF80000000h
0x180002c16  mov     [rsp+420h+SubKey], si
0x180002c1b  jmp     short loc_180002C40
0x180002c1d  lea     r8, aSoftwareClasse_2; "Software\\Classes\\"
0x180002c24  mov     rdx, r11; unsigned __int64
0x180002c27  lea     rcx, [rsp+420h+SubKey]; unsigned __int16 *
0x180002c2c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180002c31  mov     rdi, 0FFFFFFFF80000002h
0x180002c38  test    eax, eax
0x180002c3a  js      loc_180002E47
0x180002c40  mov     rdx, r11
0x180002c43  lea     rax, [rsp+420h+SubKey]
0x180002c48  cmp     [rax], si
0x180002c4b  jz      short loc_180002C57
0x180002c4d  add     rax, 2
0x180002c51  sub     rdx, 1
0x180002c55  jnz     short loc_180002C48
0x180002c57  mov     rcx, r11
0x180002c5a  mov     rax, rdx
0x180002c5d  sub     rcx, rdx
0x180002c60  neg     rax
0x180002c63  sbb     r8, r8
0x180002c66  and     r8, rcx
0x180002c69  test    rdx, rdx
0x180002c6c  jz      loc_180002E47
0x180002c72  mov     rdx, r11
0x180002c75  lea     rax, [rsp+420h+SubKey]
0x180002c7a  lea     r9, aClsid; "CLSID\\"
0x180002c81  mov     r10d, 7FFFFFFEh
0x180002c87  lea     rax, [rax+r8*2]
0x180002c8b  mov     ecx, r10d
0x180002c8e  sub     rdx, r8
0x180002c91  jz      short loc_180002CB7
0x180002c93  test    rcx, rcx
0x180002c96  jz      short loc_180002CB7
0x180002c98  movzx   r8d, word ptr [r9]
0x180002c9c  test    r8w, r8w
0x180002ca0  jz      short loc_180002CB7
0x180002ca2  mov     [rax], r8w
0x180002ca6  add     r9, 2
0x180002caa  add     rax, 2
0x180002cae  dec     rcx
0x180002cb1  sub     rdx, 1
0x180002cb5  jnz     short loc_180002C93
0x180002cb7  test    rdx, rdx
0x180002cba  lea     rcx, [rax-2]
0x180002cbe  cmovnz  rcx, rax
0x180002cc2  mov     [rcx], si
0x180002cc5  jz      loc_180002E47
0x180002ccb  mov     rdx, r11
0x180002cce  lea     rax, [rsp+420h+SubKey]
0x180002cd3  cmp     [rax], si
0x180002cd6  jz      short loc_180002CE2
0x180002cd8  add     rax, 2
0x180002cdc  sub     rdx, 1
0x180002ce0  jnz     short loc_180002CD3
0x180002ce2  mov     rcx, r11
0x180002ce5  mov     rax, rdx
0x180002ce8  sub     rcx, rdx
0x180002ceb  neg     rax
0x180002cee  sbb     r8, r8
0x180002cf1  and     r8, rcx
0x180002cf4  test    rdx, rdx
0x180002cf7  jz      loc_180002E47
0x180002cfd  mov     rdx, r11
0x180002d00  lea     rax, [rsp+420h+SubKey]
0x180002d05  lea     r9, [rbp+320h+var_290]
0x180002d0c  mov     rcx, r10
0x180002d0f  lea     rax, [rax+r8*2]
0x180002d13  sub     rdx, r8
0x180002d16  jz      short loc_180002D3C
0x180002d18  test    rcx, rcx
0x180002d1b  jz      short loc_180002D3C
0x180002d1d  movzx   r8d, word ptr [r9]
0x180002d21  test    r8w, r8w
0x180002d25  jz      short loc_180002D3C
0x180002d27  mov     [rax], r8w
0x180002d2b  add     r9, 2
0x180002d2f  add     rax, 2
0x180002d33  dec     rcx
0x180002d36  sub     rdx, 1
0x180002d3a  jnz     short loc_180002D18
0x180002d3c  test    rdx, rdx
0x180002d3f  lea     rcx, [rax-2]
0x180002d43  cmovnz  rcx, rax
0x180002d47  mov     [rcx], si
0x180002d4a  jz      loc_180002E47
0x180002d50  mov     rdx, r11
0x180002d53  lea     rax, [rsp+420h+SubKey]
0x180002d58  cmp     [rax], si
0x180002d5b  jz      short loc_180002D67
0x180002d5d  add     rax, 2
0x180002d61  sub     rdx, 1
0x180002d65  jnz     short loc_180002D58
0x180002d67  mov     rcx, r11
0x180002d6a  mov     rax, rdx
0x180002d6d  sub     rcx, rdx
0x180002d70  neg     rax
0x180002d73  sbb     r8, r8
0x180002d76  and     r8, rcx
0x180002d79  test    rdx, rdx
0x180002d7c  jz      loc_180002E47
0x180002d82  lea     rax, [rsp+420h+SubKey]
0x180002d87  lea     rax, [rax+r8*2]
0x180002d8b  lea     rcx, aInprocserver32; "\\InProcServer32"
0x180002d92  sub     r11, r8
0x180002d95  jz      short loc_180002DB8
0x180002d97  test    r10, r10
0x180002d9a  jz      short loc_180002DB8
0x180002d9c  movzx   edx, word ptr [rcx]
0x180002d9f  test    dx, dx
0x180002da2  jz      short loc_180002DB8
0x180002da4  mov     [rax], dx
0x180002da7  add     rcx, 2
0x180002dab  add     rax, 2
0x180002daf  dec     r10
0x180002db2  sub     r11, 1
0x180002db6  jnz     short loc_180002D97
0x180002db8  test    r11, r11
0x180002dbb  lea     rdx, [rax-2]
0x180002dbf  cmovnz  rdx, rax
0x180002dc3  mov     [rdx], si
0x180002dc6  jz      short loc_180002E47
0x180002dc8  lea     rax, [rsp+420h+hkey]
0x180002dcd  mov     [rsp+420h+hkey], rsi
0x180002dd2  mov     r9d, 1; samDesired
0x180002dd8  mov     [rsp+420h+phkResult], rax; phkResult
0x180002ddd  xor     r8d, r8d; ulOptions
0x180002de0  lea     rdx, [rsp+420h+SubKey]; lpSubKey
0x180002de5  mov     rcx, rdi; hKey
0x180002de8  call    cs:__imp_RegOpenKeyExW
0x180002dee  test    eax, eax
0x180002df0  jnz     short loc_180002E47
0x180002df2  mov     rcx, [rsp+420h+hkey]; hkey
0x180002df7  lea     rax, [rsp+420h+var_3E8]
0x180002dfc  mov     [rsp+420h+pcbData], rax; pcbData
0x180002e01  xor     r9d, r9d; pdwType
0x180002e04  lea     rax, [rbp+320h+pvData]
0x180002e0b  mov     [rsp+420h+var_3E8], 208h
0x180002e13  xor     r8d, r8d; pdwReserved
0x180002e16  mov     [rsp+420h+phkResult], rax; pvData
0x180002e1b  xor     edx, edx; pszValue
0x180002e1d  call    cs:__imp_SHQueryValueExW
0x180002e23  test    eax, eax
0x180002e25  jnz     short loc_180002E3C
0x180002e27  xor     r8d, r8d; dwFlags
0x180002e2a  lea     rcx, [rbp+320h+pvData]; lpLibFileName
0x180002e31  xor     edx, edx; hFile
0x180002e33  call    cs:__imp_LoadLibraryExW
0x180002e39  mov     rbx, rax
0x180002e3c  mov     rcx, [rsp+420h+hkey]; hKey
0x180002e41  call    cs:__imp_RegCloseKey
0x180002e47  mov     rax, rbx
0x180002e4a  mov     rcx, [rbp+320h+var_30]
0x180002e51  xor     rcx, rsp; StackCookie
0x180002e54  call    __security_check_cookie
0x180002e59  add     rsp, 408h
0x180002e60  pop     rdi
0x180002e61  pop     rsi
0x180002e62  pop     rbx
0x180002e63  pop     rbp
0x180002e64  retn
```
