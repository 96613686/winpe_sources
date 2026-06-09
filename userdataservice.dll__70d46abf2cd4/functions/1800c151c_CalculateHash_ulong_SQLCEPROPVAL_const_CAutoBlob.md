# CalculateHash(ulong,_SQLCEPROPVAL const *,CAutoBlob &)

- ea: `0x1800c151c`
- end: `0x1800c18cd`
- name: `?CalculateHash@@YAJKPEBU_SQLCEPROPVAL@@AEAVCAutoBlob@@@Z`
- size: `945`
- prototype: `int(unsigned int, const struct _SQLCEPROPVAL *, struct CAutoBlob *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800c2a9c`

## callees

- `0x180008f0c`
- `0x180049f80`
- `0x180075f98`
- `0x1800977ac`
- `0x1800977b8`
- `0x1800c0f34`
- `0x1800c0f60`
- `0x1800c151c`
- `0x1800c3c70`
- `0x1800c4740`
- `0x1800c4788`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1579`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c15e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1780`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c17d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c182e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1579`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c15e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1780`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c17d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c182e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c153c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c153c`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x1800c156f`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x1800c156f`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x1800c15da`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x1800c15da`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x1800c172c`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x1800c172c`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x1800c17ca`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x1800c1824`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x1800c17ca`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x1800c1824`

## string_xrefs

- `0x1800c1594`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callfavorite.cpp`
- `0x1800c1601`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callfavorite.cpp`
- `0x1800c16f3`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callfavorite.cpp`
- `0x1800c174a`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callfavorite.cpp`
- `0x1800c184b`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callfavorite.cpp`

## pseudocode

```c
__int64 __fastcall CalculateHash(DWORD a1, const struct _SQLCEPROPVAL *a2, HLOCAL *a3)
{
  unsigned __int64 *v5; // rax
  signed int LastError; // eax
  unsigned int v7; // ebx
  unsigned __int64 *v9; // rax
  signed int v10; // eax
  __int64 v11; // r9
  int v12; // r14d
  unsigned int i; // r15d
  unsigned int v14; // ecx
  unsigned int v15; // ecx
  unsigned int v16; // ecx
  unsigned int v17; // ecx
  unsigned int v18; // ecx
  __int64 v19; // rcx
  DWORD v20; // r8d
  const unsigned __int16 *v21; // rcx
  int v22; // eax
  __int64 v23; // r11
  unsigned int v24; // edi
  const BYTE *v25; // rdx
  unsigned int v26; // ecx
  unsigned int v27; // ecx
  unsigned int v28; // ecx
  unsigned int v29; // ecx
  signed int v30; // eax
  signed int v31; // eax
  BYTE *v32; // rax
  unsigned __int8 *v33; // rbx
  signed int v34; // eax
  __int64 v35; // r9
  __int64 v36; // rdx
  HCRYPTPROV hProv[2]; // [rsp+30h] [rbp-10h] BYREF
  DWORD pbData; // [rsp+80h] [rbp+40h] BYREF
  unsigned __int64 pdwDataLen; // [rsp+90h] [rbp+50h] BYREF
  HCRYPTHASH hHash; // [rsp+98h] [rbp+58h] BYREF

  pbData = a1;
  LocalFree(a3[1]);
  a3[1] = 0;
  *(_DWORD *)a3 = 0;
  hProv[0] = 0;
  v5 = tlx::replace<unsigned __int64,void (*)(unsigned __int64),&void _CloseCryptConext(unsigned __int64),0>(hProv);
  if ( !CryptAcquireContextW(v5, 0, 0, 1u, 0xF0000000) )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    Log_HREvent(
      v7,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callfavorite.cpp",
      173);
    goto LABEL_5;
  }
  hHash = 0;
  v9 = tlx::replace<unsigned __int64,void (*)(unsigned __int64),&void _CloseCryptHash(unsigned __int64),0>(&hHash);
  if ( !CryptCreateHash(hProv[0], 0x8004u, 0, 0, v9) )
  {
    v10 = GetLastError();
    v7 = v10;
    if ( v10 > 0 )
      v7 = (unsigned __int16)v10 | 0x80070000;
    v11 = 182;
    goto LABEL_12;
  }
  v12 = 0;
  for ( i = 0; i < 3; ++i )
  {
    if ( (*((_WORD *)a2 + 12 * i + 3) & 0x300) != 0 )
      continue;
    v14 = *((unsigned __int16 *)a2 + 12 * i);
    if ( v14 > 0x1F )
    {
      v26 = v14 - 64;
      if ( v26 )
      {
        v27 = v26 - 1;
        if ( v27 && (v28 = v27 - 35) != 0 && (v29 = v28 - 1) != 0 )
        {
          v19 = v29 - 1;
          if ( (_DWORD)v19 )
          {
            if ( (_DWORD)v19 != 1 )
            {
LABEL_38:
              Log_AssertionEvent_2(
                v19,
                "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callfavorite.cpp",
                261);
              continue;
            }
            goto LABEL_39;
          }
LABEL_25:
          v20 = 4;
LABEL_43:
          v25 = (const BYTE *)a2 + 24 * i + 8;
        }
        else
        {
LABEL_39:
          v20 = *((_DWORD *)a2 + 6 * i + 2);
          if ( !v20 )
            continue;
          v25 = (const BYTE *)*((_QWORD *)a2 + 3 * i + 2);
          if ( !v25 )
            continue;
        }
LABEL_44:
        if ( !CryptHashData(hHash, v25, v20, 0) )
        {
          v30 = GetLastError();
          v7 = v30;
          if ( v30 > 0 )
            v7 = (unsigned __int16)v30 | 0x80070000;
          v11 = 267;
          goto LABEL_12;
        }
        v12 = 1;
        continue;
      }
LABEL_42:
      v20 = 8;
      goto LABEL_43;
    }
    if ( v14 != 31 )
    {
      v15 = v14 - 2;
      if ( v15 )
      {
        v16 = v15 - 1;
        if ( !v16 )
          goto LABEL_25;
        v17 = v16 - 2;
        if ( !v17 )
          goto LABEL_42;
        v18 = v17 - 6;
        if ( !v18 )
          goto LABEL_25;
        v19 = v18 - 7;
        if ( (_DWORD)v19 )
        {
          if ( (_DWORD)v19 != 1 )
            goto LABEL_38;
          goto LABEL_25;
        }
      }
      v20 = 2;
      goto LABEL_43;
    }
    v21 = (const unsigned __int16 *)*((_QWORD *)a2 + 3 * i + 1);
    if ( v21 && *v21 )
    {
      pdwDataLen = 0;
      v22 = StringCbLengthW(v21, 0xFFFFFFFE, &pdwDataLen);
      v24 = v22;
      if ( v22 < 0 )
      {
        Log_HREvent(
          (unsigned int)v22,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callfavorite.cpp",
          236);
LABEL_48:
        if ( hHash )
          _CloseCryptHash(hHash);
        if ( hProv[0] )
          _CloseCryptConext(hProv[0]);
        return v24;
      }
      v20 = pdwDataLen;
      if ( (_DWORD)pdwDataLen )
      {
        v25 = (const BYTE *)*((_QWORD *)a2 + v23 + 1);
        goto LABEL_44;
      }
    }
  }
  if ( !v12 )
    goto LABEL_71;
  pbData = 0;
  LODWORD(pdwDataLen) = 4;
  if ( CryptGetHashParam(hHash, 4u, (BYTE *)&pbData, (DWORD *)&pdwDataLen, 0) )
  {
    if ( pbData )
    {
      v32 = (BYTE *)operator new[](pbData);
      v33 = v32;
      if ( !v32 )
      {
        v11 = 286;
        v7 = -2147024882;
        goto LABEL_12;
      }
      if ( !CryptGetHashParam(hHash, 2u, v32, &pbData, 0) )
      {
        v34 = GetLastError();
        v24 = v34;
        if ( v34 > 0 )
          v24 = (unsigned __int16)v34 | 0x80070000;
        v35 = 293;
        v36 = 0;
        goto LABEL_67;
      }
      v24 = CAutoBlob::Set((CAutoBlob *)a3, pbData, v33);
      if ( (v24 & 0x80000000) != 0 )
      {
        v35 = 295;
        v36 = 1;
LABEL_67:
        Log_HREvent(
          v24,
          v36,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callfavorite.cpp",
          v35);
        operator delete(v33);
        goto LABEL_48;
      }
      operator delete(v33);
    }
LABEL_71:
    if ( hHash )
      _CloseCryptHash(hHash);
    if ( hProv[0] )
      _CloseCryptConext(hProv[0]);
    return 0;
  }
  v31 = GetLastError();
  v7 = v31;
  if ( v31 > 0 )
    v7 = (unsigned __int16)v31 | 0x80070000;
  v11 = 281;
LABEL_12:
  Log_HREvent(
    v7,
    0,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callfavorite.cpp",
    v11);
  if ( hHash )
    _CloseCryptHash(hHash);
LABEL_5:
  if ( hProv[0] )
    _CloseCryptConext(hProv[0]);
  return v7;
}

```

## disassembly

```asm
0x1800c151c  mov     [rsp-38h+pbData], ecx
0x1800c1520  push    rbp
0x1800c1521  push    rbx
0x1800c1522  push    rdi
0x1800c1523  push    r12
0x1800c1525  push    r13
0x1800c1527  push    r14
0x1800c1529  push    r15
0x1800c152b  mov     rbp, rsp
0x1800c152e  sub     rsp, 40h
0x1800c1532  mov     rcx, [r8+8]; hMem
0x1800c1536  mov     r12, r8
0x1800c1539  mov     rbx, rdx
0x1800c153c  call    cs:__imp_LocalFree
0x1800c1542  xor     r13d, r13d
0x1800c1545  lea     rcx, [rbp+hProv]
0x1800c1549  mov     [r12+8], r13
0x1800c154e  mov     [r12], r13d
0x1800c1552  mov     [rbp+hProv], r13
0x1800c1556  call    ??$replace@_KP6AX_K@Z$1?_CloseCryptConext@@YAX_K@Z$0A@@tlx@@YAPEA_KAEAV?$auto_xxx@_KP6AX_K@Z$1?_CloseCryptConext@@YAX_K@Z$0A@@0@@Z; tlx::replace<unsigned __int64,void (*)(unsigned __int64),&_CloseCryptConext(unsigned __int64),0>(tlx::auto_xxx<unsigned __int64,void (*)(unsigned __int64),&_CloseCryptConext(unsigned __int64),0> &)
0x1800c155b  mov     rcx, rax; phProv
0x1800c155e  mov     [rsp+40h+dwFlags], 0F0000000h; dwFlags
0x1800c1566  lea     r9d, [r13+1]; dwProvType
0x1800c156a  xor     r8d, r8d; szProvider
0x1800c156d  xor     edx, edx; szContainer
0x1800c156f  call    cs:__imp_CryptAcquireContextW
0x1800c1575  test    eax, eax
0x1800c1577  jnz     short loc_1800C15B9
0x1800c1579  call    cs:__imp_GetLastError
0x1800c157f  mov     ebx, eax
0x1800c1581  test    eax, eax
0x1800c1583  jle     short loc_1800C158E
0x1800c1585  movzx   ebx, ax
0x1800c1588  or      ebx, 80070000h
0x1800c158e  mov     r9d, 0ADh
0x1800c1594  lea     r8, aOnecoreuapBase_20; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800c159b  xor     edx, edx
0x1800c159d  mov     ecx, ebx
0x1800c159f  call    Log_HREvent
0x1800c15a4  mov     rcx, [rbp+hProv]; unsigned __int64
0x1800c15a8  test    rcx, rcx
0x1800c15ab  jz      short loc_1800C15B2
0x1800c15ad  call    ?_CloseCryptConext@@YAX_K@Z; _CloseCryptConext(unsigned __int64)
0x1800c15b2  mov     eax, ebx
0x1800c15b4  jmp     loc_1800C18AD
0x1800c15b9  lea     rcx, [rbp+hHash]
0x1800c15bd  mov     [rbp+hHash], r13
0x1800c15c1  call    ??$replace@_KP6AX_K@Z$1?_CloseCryptHash@@YAX_K@Z$0A@@tlx@@YAPEA_KAEAV?$auto_xxx@_KP6AX_K@Z$1?_CloseCryptHash@@YAX_K@Z$0A@@0@@Z; tlx::replace<unsigned __int64,void (*)(unsigned __int64),&_CloseCryptHash(unsigned __int64),0>(tlx::auto_xxx<unsigned __int64,void (*)(unsigned __int64),&_CloseCryptHash(unsigned __int64),0> &)
0x1800c15c6  mov     rcx, [rbp+hProv]; hProv
0x1800c15ca  xor     r9d, r9d; dwFlags
0x1800c15cd  xor     r8d, r8d; hKey
0x1800c15d0  mov     qword ptr [rsp+40h+dwFlags], rax; phHash
0x1800c15d5  mov     edx, 8004h; Algid
0x1800c15da  call    cs:__imp_CryptCreateHash
0x1800c15e0  test    eax, eax
0x1800c15e2  jnz     short loc_1800C161F
0x1800c15e4  call    cs:__imp_GetLastError
0x1800c15ea  mov     ebx, eax
0x1800c15ec  test    eax, eax
0x1800c15ee  jle     short loc_1800C15F9
0x1800c15f0  movzx   ebx, ax
0x1800c15f3  or      ebx, 80070000h
0x1800c15f9  mov     r9d, 0B6h
0x1800c15ff  xor     edx, edx
0x1800c1601  lea     r8, aOnecoreuapBase_20; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800c1608  mov     ecx, ebx
0x1800c160a  call    Log_HREvent
0x1800c160f  mov     rcx, [rbp+hHash]; unsigned __int64
0x1800c1613  test    rcx, rcx
0x1800c1616  jz      short loc_1800C15A4
0x1800c1618  call    ?_CloseCryptHash@@YAX_K@Z; _CloseCryptHash(unsigned __int64)
0x1800c161d  jmp     short loc_1800C15A4
0x1800c161f  mov     r14d, r13d
0x1800c1622  mov     r15d, r13d
0x1800c1625  mov     edi, 2
0x1800c162a  cmp     r15d, 3
0x1800c162e  jnb     loc_1800C17A0
0x1800c1634  mov     eax, r15d
0x1800c1637  lea     r11, [rax+rax*2]
0x1800c163b  mov     eax, 300h
0x1800c1640  test    [rbx+r11*8+6], ax
0x1800c1646  jnz     loc_1800C173C
0x1800c164c  movzx   ecx, word ptr [rbx+r11*8]
0x1800c1651  cmp     ecx, 1Fh
0x1800c1654  ja      short loc_1800C16CF
0x1800c1656  jz      short loc_1800C168B
0x1800c1658  sub     ecx, edi
0x1800c165a  jz      short loc_1800C1683
0x1800c165c  sub     ecx, 1
0x1800c165f  jz      short loc_1800C1678
0x1800c1661  sub     ecx, edi
0x1800c1663  jz      loc_1800C1717
0x1800c1669  sub     ecx, 6
0x1800c166c  jz      short loc_1800C1678
0x1800c166e  sub     ecx, 7
0x1800c1671  jz      short loc_1800C1683
0x1800c1673  cmp     ecx, 1
0x1800c1676  jnz     short loc_1800C16ED
0x1800c1678  mov     r8d, 4
0x1800c167e  jmp     loc_1800C171D
0x1800c1683  mov     r8d, edi
0x1800c1686  jmp     loc_1800C171D
0x1800c168b  mov     rcx, [rbx+r11*8+8]; unsigned __int16 *
0x1800c1690  test    rcx, rcx
0x1800c1693  jz      loc_1800C173C
0x1800c1699  cmp     [rcx], r13w
0x1800c169d  jz      loc_1800C173C
0x1800c16a3  lea     r8, [rbp+pdwDataLen]; unsigned __int64 *
0x1800c16a7  mov     [rbp+pdwDataLen], r13
0x1800c16ab  mov     edx, 0FFFFFFFEh; unsigned __int64
0x1800c16b0  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800c16b5  mov     edi, eax
0x1800c16b7  test    eax, eax
0x1800c16b9  js      loc_1800C1744
0x1800c16bf  mov     r8d, dword ptr [rbp+pdwDataLen]
0x1800c16c3  test    r8d, r8d
0x1800c16c6  jz      short loc_1800C173C
0x1800c16c8  mov     rdx, [rbx+r11*8+8]
0x1800c16cd  jmp     short loc_1800C1725
0x1800c16cf  sub     ecx, 40h ; '@'
0x1800c16d2  jz      short loc_1800C1717
0x1800c16d4  sub     ecx, 1
0x1800c16d7  jz      short loc_1800C1701
0x1800c16d9  sub     ecx, 23h ; '#'
0x1800c16dc  jz      short loc_1800C1701
0x1800c16de  sub     ecx, 1
0x1800c16e1  jz      short loc_1800C1701
0x1800c16e3  sub     ecx, 1
0x1800c16e6  jz      short loc_1800C1678
0x1800c16e8  cmp     ecx, 1
0x1800c16eb  jz      short loc_1800C1701
0x1800c16ed  mov     r8d, 105h
0x1800c16f3  lea     rdx, aOnecoreuapBase_20; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800c16fa  call    Log_AssertionEvent_2
0x1800c16ff  jmp     short loc_1800C173C
0x1800c1701  mov     r8d, [rbx+r11*8+8]
0x1800c1706  test    r8d, r8d
0x1800c1709  jz      short loc_1800C173C
0x1800c170b  mov     rdx, [rbx+r11*8+10h]
0x1800c1710  test    rdx, rdx
0x1800c1713  jz      short loc_1800C173C
0x1800c1715  jmp     short loc_1800C1725
0x1800c1717  mov     r8d, 8; dwDataLen
0x1800c171d  lea     rdx, [rbx+8]
0x1800c1721  lea     rdx, [rdx+r11*8]; pbData
0x1800c1725  mov     rcx, [rbp+hHash]; hHash
0x1800c1729  xor     r9d, r9d; dwFlags
0x1800c172c  call    cs:__imp_CryptHashData
0x1800c1732  test    eax, eax
0x1800c1734  jz      short loc_1800C1780
0x1800c1736  mov     r14d, 1
0x1800c173c  inc     r15d
0x1800c173f  jmp     loc_1800C1625
0x1800c1744  mov     r9d, 0ECh
0x1800c174a  lea     r8, aOnecoreuapBase_20; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800c1751  mov     edx, 1
0x1800c1756  mov     ecx, edi
0x1800c1758  call    Log_HREvent
0x1800c175d  mov     rcx, [rbp+hHash]; unsigned __int64
0x1800c1761  test    rcx, rcx
0x1800c1764  jz      short loc_1800C176B
0x1800c1766  call    ?_CloseCryptHash@@YAX_K@Z; _CloseCryptHash(unsigned __int64)
0x1800c176b  mov     rcx, [rbp+hProv]; unsigned __int64
0x1800c176f  test    rcx, rcx
0x1800c1772  jz      short loc_1800C1779
0x1800c1774  call    ?_CloseCryptConext@@YAX_K@Z; _CloseCryptConext(unsigned __int64)
0x1800c1779  mov     eax, edi
0x1800c177b  jmp     loc_1800C18AD
0x1800c1780  call    cs:__imp_GetLastError
0x1800c1786  mov     ebx, eax
0x1800c1788  test    eax, eax
0x1800c178a  jle     short loc_1800C1795
0x1800c178c  movzx   ebx, ax
0x1800c178f  or      ebx, 80070000h
0x1800c1795  mov     r9d, 10Bh
0x1800c179b  jmp     loc_1800C15FF
0x1800c17a0  test    r14d, r14d
0x1800c17a3  jz      loc_1800C188F
0x1800c17a9  mov     rcx, [rbp+hHash]; hHash
0x1800c17ad  lea     r9, [rbp+pdwDataLen]; pdwDataLen
0x1800c17b1  lea     r8, [rbp+pbData]; pbData
0x1800c17b5  mov     [rbp+pbData], r13d
0x1800c17b9  mov     edx, 4; dwParam
0x1800c17be  mov     dword ptr [rbp+pdwDataLen], 4
0x1800c17c5  mov     [rsp+40h+dwFlags], r13d; dwFlags
0x1800c17ca  call    cs:__imp_CryptGetHashParam
0x1800c17d0  test    eax, eax
0x1800c17d2  jnz     short loc_1800C17F4
0x1800c17d4  call    cs:__imp_GetLastError
0x1800c17da  mov     ebx, eax
0x1800c17dc  test    eax, eax
0x1800c17de  jle     short loc_1800C17E9
0x1800c17e0  movzx   ebx, ax
0x1800c17e3  or      ebx, 80070000h
0x1800c17e9  mov     r9d, 119h
0x1800c17ef  jmp     loc_1800C15FF
0x1800c17f4  mov     eax, [rbp+pbData]
0x1800c17f7  test    eax, eax
0x1800c17f9  jz      loc_1800C188F
0x1800c17ff  mov     ecx, eax; unsigned __int64
0x1800c1801  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800c1806  mov     rbx, rax
0x1800c1809  test    rax, rax
0x1800c180c  jz      loc_1800C18BD
0x1800c1812  mov     rcx, [rbp+hHash]; hHash
0x1800c1816  lea     r9, [rbp+pbData]; pdwDataLen
0x1800c181a  mov     r8, rax; pbData
0x1800c181d  mov     [rsp+40h+dwFlags], r13d; dwFlags
0x1800c1822  mov     edx, edi; dwParam
0x1800c1824  call    cs:__imp_CryptGetHashParam
0x1800c182a  test    eax, eax
0x1800c182c  jnz     short loc_1800C1866
0x1800c182e  call    cs:__imp_GetLastError
0x1800c1834  mov     edi, eax
0x1800c1836  test    eax, eax
0x1800c1838  jle     short loc_1800C1843
0x1800c183a  movzx   edi, ax
0x1800c183d  or      edi, 80070000h
0x1800c1843  mov     r9d, 125h
0x1800c1849  xor     edx, edx
0x1800c184b  lea     r8, aOnecoreuapBase_20; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800c1852  mov     ecx, edi
0x1800c1854  call    Log_HREvent
0x1800c1859  mov     rcx, rbx; Block
0x1800c185c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800c1861  jmp     loc_1800C175D
0x1800c1866  mov     edx, [rbp+pbData]; unsigned int
0x1800c1869  mov     r8, rbx; unsigned __int8 *
0x1800c186c  mov     rcx, r12; this
0x1800c186f  call    ?Set@CAutoBlob@@QEAAJKQEBE@Z; CAutoBlob::Set(ulong,uchar const * const)
0x1800c1874  mov     edi, eax
0x1800c1876  test    eax, eax
0x1800c1878  jns     short loc_1800C1887
0x1800c187a  mov     r9d, 127h
0x1800c1880  mov     edx, 1
0x1800c1885  jmp     short loc_1800C184B
0x1800c1887  mov     rcx, rbx; Block
0x1800c188a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800c188f  mov     rcx, [rbp+hHash]; unsigned __int64
0x1800c1893  test    rcx, rcx
0x1800c1896  jz      short loc_1800C189D
0x1800c1898  call    ?_CloseCryptHash@@YAX_K@Z; _CloseCryptHash(unsigned __int64)
0x1800c189d  mov     rcx, [rbp+hProv]; unsigned __int64
0x1800c18a1  test    rcx, rcx
0x1800c18a4  jz      short loc_1800C18AB
0x1800c18a6  call    ?_CloseCryptConext@@YAX_K@Z; _CloseCryptConext(unsigned __int64)
0x1800c18ab  xor     eax, eax
0x1800c18ad  add     rsp, 40h
0x1800c18b1  pop     r15
0x1800c18b3  pop     r14
0x1800c18b5  pop     r13
0x1800c18b7  pop     r12
0x1800c18b9  pop     rdi
0x1800c18ba  pop     rbx
0x1800c18bb  pop     rbp
0x1800c18bc  retn
0x1800c18bd  mov     r9d, 11Eh
0x1800c18c3  mov     ebx, 8007000Eh
0x1800c18c8  jmp     loc_1800C15FF
```
