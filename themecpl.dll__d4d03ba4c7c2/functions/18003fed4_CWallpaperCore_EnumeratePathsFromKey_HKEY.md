# CWallpaperCore::_EnumeratePathsFromKey(HKEY__ *)

- ea: `0x18003fed4`
- end: `0x1800405c0`
- name: `?_EnumeratePathsFromKey@CWallpaperCore@@AEAAJPEAUHKEY__@@@Z`
- size: `1772`
- prototype: `int(CWallpaperCore *__hidden this, HKEY)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180041c00`

## callees

- `0x180002280`
- `0x180002650`
- `0x18000268c`
- `0x18003fed4`
- `0x18004f490`
- `0x180054e70`
- `0x180054f64`
- `0x180054fb4`
- `0x18005501c`
- `0x180055074`

## import_xrefs

- `PROPSYS!PSGetPropertyKeyFromName` at `0x180040118`
- `PROPSYS!PSGetPropertyKeyFromName` at `0x180040118`
- `SHELL32!__imp_SHILCreateFromPath` at `0x1800403d4`
- `SHELL32!__imp_SHILCreateFromPath` at `0x1800403d4`
- `SHLWAPI!__imp_SHLoadIndirectString` at `0x1800401b7`
- `SHLWAPI!__imp_SHLoadIndirectString` at `0x1800401b7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003ff9c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003ff9c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800404aa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800404bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800404cc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040587`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800404aa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800404bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800404cc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040587`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ff35`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004008d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180040308`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180040340`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ff35`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004008d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180040308`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180040340`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180040265`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18004056e`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180040265`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18004056e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800400e2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004017d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800400e2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004017d`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180040385`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180040459`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180040385`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180040459`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800403b0`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800403b0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWallpaperCore::_EnumeratePathsFromKey(CWallpaperCore *this, HKEY a2)
{
  CWallpaperCore *v2; // r13
  signed int v3; // esi
  signed int v4; // edi
  DWORD v5; // r12d
  DWORD i; // edx
  char v7; // r15
  struct _DPA *v8; // rcx
  signed int v9; // eax
  WCHAR *Ptr; // rbx
  char v11; // r14
  char *v12; // rax
  __int64 v13; // rcx
  WCHAR *v14; // r8
  __int64 v15; // rdx
  WCHAR *v16; // rax
  WCHAR v17; // r9
  WCHAR *v18; // rcx
  __int64 v19; // rdx
  LSTATUS ValueW; // eax
  bool v21; // sf
  LSTATUS v22; // eax
  bool v23; // sf
  __int64 v24; // rcx
  WCHAR *v25; // r8
  __int64 v26; // rdx
  WCHAR *v27; // rax
  WCHAR v28; // r9
  WCHAR *v29; // rcx
  __int64 v30; // rcx
  WCHAR *v31; // r8
  __int64 v32; // rdx
  WCHAR *v33; // rax
  WCHAR v34; // r9
  WCHAR *v35; // rcx
  struct _DPA *v36; // rax
  _DWORD *v37; // rax
  struct _DPA *v38; // rcx
  DWORD cchValueName; // [rsp+40h] [rbp-C0h] BYREF
  DWORD v41; // [rsp+44h] [rbp-BCh] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  HKEY v44; // [rsp+58h] [rbp-A8h] BYREF
  DWORD cchName; // [rsp+60h] [rbp-A0h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-98h] BYREF
  LPITEMIDLIST ppidl; // [rsp+70h] [rbp-90h] BYREF
  CWallpaperCore *v48; // [rsp+78h] [rbp-88h]
  PROPERTYKEY ppropkey; // [rsp+80h] [rbp-80h] BYREF
  WCHAR pszName[264]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR String2[264]; // [rsp+2B0h] [rbp+1B0h] BYREF
  WCHAR pszOutBuf[264]; // [rsp+4C0h] [rbp+3C0h] BYREF
  WCHAR Dst[264]; // [rsp+6D0h] [rbp+5D0h] BYREF

  v2 = this;
  v48 = this;
  v3 = 0;
  v4 = 0;
  hKey = 0;
  if ( !RegOpenKeyExW(
          a2,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Wallpapers\\KnownFolders",
          0,
          0x20019u,
          &hKey) )
  {
    v5 = 0;
    v41 = 260;
    for ( i = 0; ; i = v5 )
    {
      if ( RegEnumKeyExW(hKey, i, String2, &v41, 0, 0, 0, 0) || v4 < 0 )
      {
        RegCloseKey(hKey);
        return (unsigned int)v4;
      }
      v7 = 0;
      while ( 1 )
      {
        v8 = (struct _DPA *)*((_QWORD *)v2 + 12);
        v9 = 0;
        if ( v8 )
          v9 = *(_DWORD *)v8;
        if ( v3 >= v9 )
          break;
        Ptr = (WCHAR *)DPA_GetPtr(v8, v3);
        if ( CompareStringOrdinal(Ptr + 10, -1, String2, -1, 1) == 2 )
        {
          v11 = 1;
          v3 = 0;
          goto LABEL_19;
        }
        ++v3;
      }
      v12 = (char *)operator new(0x440u, (const struct std::nothrow_t *)&std::nothrow);
      Ptr = (WCHAR *)v12;
      ppidl = (LPITEMIDLIST)v12;
      v3 = 0;
      if ( !v12 )
      {
        Ptr = 0;
        v4 = -2147024882;
        goto LABEL_75;
      }
      *((_QWORD *)v12 + 133) = 0;
      v7 = 1;
      *((_WORD *)v12 + 530) = 0;
      *(PROPERTYKEY *)v12 = PKEY_ItemFolderPathDisplay;
      v13 = 2147483646;
      v14 = String2;
      v15 = 260;
      v16 = (WCHAR *)(v12 + 20);
      v11 = 0;
      do
      {
        if ( !v13 )
          break;
        v17 = *v14;
        if ( !*v14 )
          break;
        ++v14;
        *v16++ = v17;
        --v13;
        --v15;
      }
      while ( v15 );
      v18 = v16 - 1;
      if ( v15 )
        v18 = v16;
      *v18 = 0;
      v19 = -v15;
      v4 = v19 == 0 ? 0x8007007A : 0;
      if ( v19 )
      {
LABEL_19:
        hkey = 0;
        if ( !RegOpenKeyExW(hKey, String2, 0, 0x20019u, &hkey) )
        {
          if ( !*((_BYTE *)Ptr + 1061) )
          {
            cchValueName = 520;
            ValueW = RegGetValueW(hkey, 0, L"GROUPBY", 2u, 0, pszName, &cchValueName);
            v21 = ValueW < 0;
            if ( ValueW )
            {
              pszName[0] = 0;
              if ( ValueW > 0 )
                v21 = 1;
            }
            if ( !v21 )
            {
              memset(&ppropkey, 0, sizeof(ppropkey));
              if ( PSGetPropertyKeyFromName(pszName, &ppropkey) >= 0 )
              {
                *(PROPERTYKEY *)Ptr = ppropkey;
                *((_BYTE *)Ptr + 1061) = 1;
              }
            }
          }
          if ( *((_BYTE *)Ptr + 1060) )
            goto LABEL_41;
          cchValueName = 520;
          v22 = RegGetValueW(hkey, 0, L"NAME", 2u, 0, pszName, &cchValueName);
          v23 = v22 < 0;
          if ( v22 )
          {
            pszName[0] = 0;
            if ( v22 > 0 )
              v23 = 1;
          }
          if ( v23 || SHLoadIndirectString(pszName, pszOutBuf, 0x104u, 0) < 0 )
            goto LABEL_41;
          v24 = 2147483646;
          v25 = pszOutBuf;
          v26 = 260;
          v27 = Ptr + 270;
          do
          {
            if ( !v24 )
              break;
            v28 = *v25;
            if ( !*v25 )
              break;
            ++v25;
            *v27++ = v28;
            --v24;
            --v26;
          }
          while ( v26 );
          v29 = v27 - 1;
          if ( v26 )
            v29 = v27;
          *v29 = 0;
          v4 = v26 == 0 ? 0x8007007A : 0;
          if ( v26 )
          {
            *((_BYTE *)Ptr + 1060) = 1;
LABEL_41:
            if ( v4 >= 0 )
            {
              cchName = 260;
              if ( !RegEnumKeyExW(hkey, 0, pszName, &cchName, 0, 0, 0, 0) )
              {
                if ( *((_BYTE *)Ptr + 1060) || v11 )
                  goto LABEL_52;
                v30 = 2147483646;
                v31 = pszName;
                v32 = 260;
                v33 = Ptr + 270;
                do
                {
                  if ( !v30 )
                    break;
                  v34 = *v31;
                  if ( !*v31 )
                    break;
                  ++v31;
                  *v33++ = v34;
                  --v30;
                  --v32;
                }
                while ( v32 );
                v35 = v33 - 1;
                if ( v32 )
                  v35 = v33;
                *v35 = 0;
                v4 = v32 == 0 ? 0x8007007A : 0;
                if ( v32 )
                {
LABEL_52:
                  phkResult = 0;
                  if ( !RegOpenKeyExW(hkey, pszName, 0, 0x20019u, &phkResult) )
                  {
                    v44 = 0;
                    if ( !RegOpenKeyExW(phkResult, L"MergeFolders", 0, 0x20019u, &v44) )
                    {
                      cchValueName = 260;
                      if ( !RegEnumValueW(v44, 0, pszOutBuf, &cchValueName, 0, 0, 0, 0) )
                      {
                        while ( 1 )
                        {
                          if ( !ExpandEnvironmentStringsW(pszOutBuf, Dst, 0x104u) )
                            goto LABEL_64;
                          ppidl = 0;
                          if ( SHILCreateFromPath(Dst, &ppidl, 0) < 0 )
                            goto LABEL_64;
                          v36 = (struct _DPA *)*((_QWORD *)Ptr + 133);
                          if ( !v36 )
                            break;
                          if ( v4 >= 0 )
                            goto LABEL_62;
LABEL_64:
                          ++v3;
                          cchValueName = 260;
                          if ( RegEnumValueW(v44, v3, pszOutBuf, &cchValueName, 0, 0, 0, 0) )
                          {
                            v2 = v48;
                            goto LABEL_66;
                          }
                        }
                        v36 = DPA_Create(1);
                        *((_QWORD *)Ptr + 133) = v36;
                        if ( !v36 )
                        {
                          v4 = -2147024882;
                          goto LABEL_64;
                        }
                        v4 = 0;
LABEL_62:
                        DPA_InsertPtr(v36, 0x7FFFFFFF, ppidl);
                        goto LABEL_64;
                      }
LABEL_66:
                      v3 = 0;
                      if ( !v11 )
                      {
                        v37 = (_DWORD *)*((_QWORD *)Ptr + 133);
                        if ( v37 )
                        {
                          if ( *v37 && DPA_InsertPtr(*((HDPA *)v2 + 12), 0x7FFFFFFF, Ptr) != -1 )
                            v7 = 0;
                        }
                      }
                      RegCloseKey(v44);
                    }
                    RegCloseKey(phkResult);
                  }
                }
              }
            }
          }
          RegCloseKey(hkey);
        }
      }
LABEL_75:
      v41 = 260;
      ++v5;
      if ( v7 && Ptr )
      {
        if ( *((_QWORD *)Ptr + 133) )
        {
          if ( !IsProcessShutdownInProgress() )
          {
            v38 = (struct _DPA *)*((_QWORD *)Ptr + 133);
            if ( v38 )
            {
              DPA_DestroyCallback(
                v38,
                CDPA_Base<_ITEMIDLIST_ABSOLUTE,CTContainer_PolicyCoTaskMem>::_StandardDestroyCB,
                0);
              *((_QWORD *)Ptr + 133) = 0;
              DPA_Destroy(0);
              *((_QWORD *)Ptr + 133) = 0;
            }
          }
        }
        operator delete(Ptr, (const struct std::nothrow_t *)0x440);
      }
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18003fed4  mov     [rsp-8+arg_10], rbx
0x18003fed9  push    rbp
0x18003feda  push    rsi
0x18003fedb  push    rdi
0x18003fedc  push    r12
0x18003fede  push    r13
0x18003fee0  push    r14
0x18003fee2  push    r15
0x18003fee4  lea     rbp, [rsp-7F0h]
0x18003feec  sub     rsp, 8F0h
0x18003fef3  mov     rax, cs:__security_cookie
0x18003fefa  xor     rax, rsp
0x18003fefd  mov     [rbp+820h+var_40], rax
0x18003ff04  mov     rax, rdx
0x18003ff07  mov     r13, rcx
0x18003ff0a  mov     [rsp+920h+var_8A8], rcx
0x18003ff0f  xor     esi, esi
0x18003ff11  mov     edi, esi
0x18003ff13  mov     [rsp+920h+hKey], rsi
0x18003ff18  lea     rcx, [rsp+920h+hKey]
0x18003ff1d  mov     [rsp+920h+phkResult], rcx; phkResult
0x18003ff22  mov     r9d, 20019h; samDesired
0x18003ff28  xor     r8d, r8d; ulOptions
0x18003ff2b  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18003ff32  mov     rcx, rax; hKey
0x18003ff35  call    cs:__imp_RegOpenKeyExW
0x18003ff3c  nop     dword ptr [rax+rax+00h]
0x18003ff41  test    eax, eax
0x18003ff43  jnz     loc_180040593
0x18003ff49  mov     r12d, esi
0x18003ff4c  mov     [rsp+920h+var_8DC], 104h
0x18003ff54  xor     edx, edx
0x18003ff56  jmp     loc_180040549
0x18003ff5b  test    edi, edi
0x18003ff5d  js      loc_180040582
0x18003ff63  mov     r15b, sil
0x18003ff66  mov     rcx, [r13+60h]; hdpa
0x18003ff6a  xor     eax, eax
0x18003ff6c  test    rcx, rcx
0x18003ff6f  jz      short loc_18003FF73
0x18003ff71  mov     eax, [rcx]
0x18003ff73  cmp     esi, eax
0x18003ff75  jge     short loc_18003FFBB
0x18003ff77  movsxd  rdx, esi; i
0x18003ff7a  call    DPA_GetPtr
0x18003ff7f  mov     rbx, rax
0x18003ff82  lea     rcx, [rax+14h]; lpString1
0x18003ff86  mov     dword ptr [rsp+920h+phkResult], 1; bIgnoreCase
0x18003ff8e  or      r9d, 0FFFFFFFFh; cchCount2
0x18003ff92  lea     r8, [rbp+820h+String2]; lpString2
0x18003ff99  or      edx, r9d; cchCount1
0x18003ff9c  call    cs:__imp_CompareStringOrdinal
0x18003ffa3  nop     dword ptr [rax+rax+00h]
0x18003ffa8  cmp     eax, 2
0x18003ffab  jz      short loc_18003FFB1
0x18003ffad  inc     esi
0x18003ffaf  jmp     short loc_18003FF66
0x18003ffb1  mov     r14b, 1
0x18003ffb4  xor     esi, esi
0x18003ffb6  jmp     loc_180040069
0x18003ffbb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003ffc2  mov     ecx, 440h; unsigned __int64
0x18003ffc7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003ffcc  mov     rbx, rax
0x18003ffcf  mov     [rsp+920h+ppidl], rax
0x18003ffd4  xor     esi, esi
0x18003ffd6  test    rax, rax
0x18003ffd9  jz      loc_1800404DA
0x18003ffdf  mov     [rax+428h], rsi
0x18003ffe6  test    rax, rax
0x18003ffe9  jz      loc_1800404DD
0x18003ffef  mov     r15b, 1
0x18003fff2  mov     [rax+424h], si
0x18003fff9  movups  xmm0, xmmword ptr cs:PKEY_ItemFolderPathDisplay.fmtid.Data1
0x180040000  movups  xmmword ptr [rax], xmm0
0x180040003  mov     eax, cs:PKEY_ItemFolderPathDisplay.pid
0x180040009  mov     [rbx+10h], eax
0x18004000c  mov     ecx, 7FFFFFFEh
0x180040011  lea     r8, [rbp+820h+String2]
0x180040018  mov     edx, 104h
0x18004001d  lea     rax, [rbx+14h]
0x180040021  mov     r14b, sil
0x180040024  test    rcx, rcx
0x180040027  jz      short loc_180040048
0x180040029  movzx   r9d, word ptr [r8]
0x18004002d  test    r9w, r9w
0x180040031  jz      short loc_180040048
0x180040033  add     r8, 2
0x180040037  mov     [rax], r9w
0x18004003b  add     rax, 2
0x18004003f  dec     rcx
0x180040042  sub     rdx, 1
0x180040046  jnz     short loc_180040024
0x180040048  lea     rcx, [rax-2]
0x18004004c  test    rdx, rdx
0x18004004f  cmovnz  rcx, rax
0x180040053  mov     [rcx], si
0x180040056  neg     rdx
0x180040059  sbb     edi, edi
0x18004005b  not     edi
0x18004005d  and     edi, 8007007Ah
0x180040063  jl      loc_1800404E2
0x180040069  mov     [rsp+920h+hkey], rsi
0x18004006e  lea     rax, [rsp+920h+hkey]
0x180040073  mov     [rsp+920h+phkResult], rax; phkResult
0x180040078  mov     r9d, 20019h; samDesired
0x18004007e  xor     r8d, r8d; ulOptions
0x180040081  lea     rdx, [rbp+820h+String2]; lpSubKey
0x180040088  mov     rcx, [rsp+920h+hKey]; hKey
0x18004008d  call    cs:__imp_RegOpenKeyExW
0x180040094  nop     dword ptr [rax+rax+00h]
0x180040099  test    eax, eax
0x18004009b  jnz     loc_1800404E2
0x1800400a1  cmp     [rbx+425h], sil
0x1800400a8  jnz     loc_18004013C
0x1800400ae  mov     [rsp+920h+cchValueName], 208h
0x1800400b6  lea     rax, [rsp+920h+cchValueName]
0x1800400bb  mov     [rsp+920h+pcbData], rax; pcbData
0x1800400c0  lea     rax, [rbp+820h+pszName]
0x1800400c4  mov     [rsp+920h+pvData], rax; pvData
0x1800400c9  mov     [rsp+920h+phkResult], rsi; pdwType
0x1800400ce  mov     r9d, 2; dwFlags
0x1800400d4  lea     r8, aGroupby; "GROUPBY"
0x1800400db  xor     edx, edx; lpSubKey
0x1800400dd  mov     rcx, [rsp+920h+hkey]; hkey
0x1800400e2  call    cs:__imp_RegGetValueW
0x1800400e9  nop     dword ptr [rax+rax+00h]
0x1800400ee  test    eax, eax
0x1800400f0  jz      short loc_180040102
0x1800400f2  mov     [rbp+820h+pszName], si
0x1800400f6  jle     short loc_180040102
0x1800400f8  movzx   eax, ax
0x1800400fb  or      eax, 80070000h
0x180040100  test    eax, eax
0x180040102  js      short loc_18004013C
0x180040104  xorps   xmm0, xmm0
0x180040107  xor     eax, eax
0x180040109  movups  xmmword ptr [rbp+820h+ppropkey.fmtid.Data1], xmm0
0x18004010d  mov     [rbp+820h+ppropkey.pid], eax
0x180040110  lea     rdx, [rbp+820h+ppropkey]; ppropkey
0x180040114  lea     rcx, [rbp+820h+pszName]; pszName
0x180040118  call    cs:__imp_PSGetPropertyKeyFromName
0x18004011f  nop     dword ptr [rax+rax+00h]
0x180040124  test    eax, eax
0x180040126  js      short loc_18004013C
0x180040128  movups  xmm0, xmmword ptr [rbp+820h+ppropkey.fmtid.Data1]
0x18004012c  movups  xmmword ptr [rbx], xmm0
0x18004012f  mov     eax, [rbp+820h+ppropkey.pid]
0x180040132  mov     [rbx+10h], eax
0x180040135  mov     byte ptr [rbx+425h], 1
0x18004013c  cmp     [rbx+424h], sil
0x180040143  jnz     loc_180040231
0x180040149  mov     [rsp+920h+cchValueName], 208h
0x180040151  lea     rax, [rsp+920h+cchValueName]
0x180040156  mov     [rsp+920h+pcbData], rax; pcbData
0x18004015b  lea     rax, [rbp+820h+pszName]
0x18004015f  mov     [rsp+920h+pvData], rax; pvData
0x180040164  mov     [rsp+920h+phkResult], rsi; pdwType
0x180040169  mov     r9d, 2; dwFlags
0x18004016f  lea     r8, aName_0; "NAME"
0x180040176  xor     edx, edx; lpSubKey
0x180040178  mov     rcx, [rsp+920h+hkey]; hkey
0x18004017d  call    cs:__imp_RegGetValueW
0x180040184  nop     dword ptr [rax+rax+00h]
0x180040189  test    eax, eax
0x18004018b  jz      short loc_18004019D
0x18004018d  mov     [rbp+820h+pszName], si
0x180040191  jle     short loc_18004019D
0x180040193  movzx   eax, ax
0x180040196  or      eax, 80070000h
0x18004019b  test    eax, eax
0x18004019d  js      loc_180040231
0x1800401a3  xor     r9d, r9d; ppvReserved
0x1800401a6  mov     r8d, 104h; cchOutBuf
0x1800401ac  lea     rdx, [rbp+820h+pszOutBuf]; pszOutBuf
0x1800401b3  lea     rcx, [rbp+820h+pszName]; pszSource
0x1800401b7  call    cs:__imp_SHLoadIndirectString
0x1800401be  nop     dword ptr [rax+rax+00h]
0x1800401c3  test    eax, eax
0x1800401c5  js      short loc_180040231
0x1800401c7  mov     ecx, 7FFFFFFEh
0x1800401cc  lea     r8, [rbp+820h+pszOutBuf]
0x1800401d3  mov     edx, 104h
0x1800401d8  lea     rax, [rbx+21Ch]
0x1800401df  test    rcx, rcx
0x1800401e2  jz      short loc_180040203
0x1800401e4  movzx   r9d, word ptr [r8]
0x1800401e8  test    r9w, r9w
0x1800401ec  jz      short loc_180040203
0x1800401ee  add     r8, 2
0x1800401f2  mov     [rax], r9w
0x1800401f6  add     rax, 2
0x1800401fa  dec     rcx
0x1800401fd  sub     rdx, 1
0x180040201  jnz     short loc_1800401DF
0x180040203  lea     rcx, [rax-2]
0x180040207  test    rdx, rdx
0x18004020a  cmovnz  rcx, rax
0x18004020e  mov     [rcx], si
0x180040211  mov     rax, rdx
0x180040214  neg     rax
0x180040217  sbb     edi, edi
0x180040219  not     edi
0x18004021b  and     edi, 8007007Ah
0x180040221  test    rdx, rdx
0x180040224  jz      loc_1800404C7
0x18004022a  mov     byte ptr [rbx+424h], 1
0x180040231  test    edi, edi
0x180040233  js      loc_1800404C7
0x180040239  mov     [rsp+920h+cchName], 104h
0x180040241  mov     [rsp+920h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x180040246  mov     [rsp+920h+pcbData], rsi; lpcchClass
0x18004024b  mov     [rsp+920h+pvData], rsi; lpClass
0x180040250  mov     [rsp+920h+phkResult], rsi; lpReserved
0x180040255  lea     r9, [rsp+920h+cchName]; lpcchName
0x18004025a  lea     r8, [rbp+820h+pszName]; lpName
0x18004025e  xor     edx, edx; dwIndex
0x180040260  mov     rcx, [rsp+920h+hkey]; hKey
0x180040265  call    cs:__imp_RegEnumKeyExW
0x18004026c  nop     dword ptr [rax+rax+00h]
0x180040271  test    eax, eax
0x180040273  jnz     loc_1800404C7
0x180040279  cmp     [rbx+424h], sil
0x180040280  jnz     short loc_1800402E7
0x180040282  test    r14b, r14b
0x180040285  jnz     short loc_1800402E7
0x180040287  mov     ecx, 7FFFFFFEh
0x18004028c  lea     r8, [rbp+820h+pszName]
0x180040290  mov     edx, 104h
0x180040295  lea     rax, [rbx+21Ch]
0x18004029c  test    rcx, rcx
0x18004029f  jz      short loc_1800402C0
0x1800402a1  movzx   r9d, word ptr [r8]
0x1800402a5  test    r9w, r9w
0x1800402a9  jz      short loc_1800402C0
0x1800402ab  add     r8, 2
0x1800402af  mov     [rax], r9w
0x1800402b3  add     rax, 2
0x1800402b7  dec     rcx
0x1800402ba  sub     rdx, 1
0x1800402be  jnz     short loc_18004029C
0x1800402c0  lea     rcx, [rax-2]
0x1800402c4  test    rdx, rdx
0x1800402c7  cmovnz  rcx, rax
0x1800402cb  mov     [rcx], si
0x1800402ce  mov     rax, rdx
0x1800402d1  neg     rax
0x1800402d4  sbb     edi, edi
0x1800402d6  not     edi
0x1800402d8  and     edi, 8007007Ah
0x1800402de  test    rdx, rdx
0x1800402e1  jz      loc_1800404C7
0x1800402e7  mov     [rsp+920h+var_8B8], rsi
0x1800402ec  lea     rax, [rsp+920h+var_8B8]
0x1800402f1  mov     [rsp+920h+phkResult], rax; phkResult
0x1800402f6  mov     r9d, 20019h; samDesired
0x1800402fc  xor     r8d, r8d; ulOptions
0x1800402ff  lea     rdx, [rbp+820h+pszName]; lpSubKey
0x180040303  mov     rcx, [rsp+920h+hkey]; hKey
0x180040308  call    cs:__imp_RegOpenKeyExW
0x18004030f  nop     dword ptr [rax+rax+00h]
0x180040314  test    eax, eax
0x180040316  jnz     loc_1800404C7
0x18004031c  mov     [rsp+920h+var_8C8], rsi
0x180040321  lea     rax, [rsp+920h+var_8C8]
0x180040326  mov     [rsp+920h+phkResult], rax; phkResult
0x18004032b  mov     r9d, 20019h; samDesired
0x180040331  xor     r8d, r8d; ulOptions
0x180040334  lea     rdx, aMergefolders; "MergeFolders"
0x18004033b  mov     rcx, [rsp+920h+var_8B8]; hKey
0x180040340  call    cs:__imp_RegOpenKeyExW
0x180040347  nop     dword ptr [rax+rax+00h]
0x18004034c  test    eax, eax
0x18004034e  jnz     loc_1800404B6
0x180040354  mov     [rsp+920h+cchValueName], 104h
0x18004035c  xor     eax, eax
0x18004035e  mov     [rsp+920h+lpftLastWriteTime], rax; lpcbData
0x180040363  mov     [rsp+920h+pcbData], rax; lpData
0x180040368  mov     [rsp+920h+pvData], rax; lpType
0x18004036d  mov     [rsp+920h+phkResult], rax; lpReserved
0x180040372  lea     r9, [rsp+920h+cchValueName]; lpcchValueName
0x180040377  lea     r8, [rbp+820h+pszOutBuf]; lpValueName
0x18004037e  xor     edx, edx; dwIndex
0x180040380  mov     rcx, [rsp+920h+var_8C8]; hKey
0x180040385  call    cs:__imp_RegEnumValueW
0x18004038c  nop     dword ptr [rax+rax+00h]
0x180040391  test    eax, eax
0x180040393  jnz     loc_180040472
0x180040399  xor     r13d, r13d
0x18004039c  mov     r8d, 104h; nSize
0x1800403a2  lea     rdx, [rbp+820h+Dst]; lpDst
0x1800403a9  lea     rcx, [rbp+820h+pszOutBuf]; lpSrc
0x1800403b0  call    cs:__imp_ExpandEnvironmentStringsW
0x1800403b7  nop     dword ptr [rax+rax+00h]
0x1800403bc  test    eax, eax
0x1800403be  jz      short loc_180040428
0x1800403c0  mov     [rsp+920h+ppidl], r13
0x1800403c5  xor     r8d, r8d; rgfInOut
0x1800403c8  lea     rdx, [rsp+920h+ppidl]; ppidl
0x1800403cd  lea     rcx, [rbp+820h+Dst]; pszPath
  ... truncated ...
```
