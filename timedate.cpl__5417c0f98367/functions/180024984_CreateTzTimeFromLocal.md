# CreateTzTimeFromLocal

- ea: `0x180024984`
- end: `0x180024bb2`
- name: `CreateTzTimeFromLocal`
- size: `558`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18000dff4`
- `0x18000e7a0`
- `0x18001c3fc`

## callees

- `0x180024910`
- `0x180024984`
- `0x1800255a4`
- `0x180025638`
- `0x180025f48`
- `0x180026514`
- `0x180026854`
- `0x180026884`
- `0x180028f2e`
- `0x180028f60`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024ada`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024ada`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180024a07`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180024a07`

## pseudocode

```c
__int64 __fastcall CreateTzTimeFromLocal(__int64 a1, const SYSTEMTIME *a2, __int64 a3, _OWORD *a4)
{
  _OWORD *v4; // rbx
  int TimeZoneId; // edi
  size_t v7; // rdx
  size_t *v8; // r8
  int v9; // r8d
  __int64 v10; // rsi
  wchar_t *v11; // rax
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  int v20; // eax
  struct _FILETIME FileTime; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t v24[128]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v25[16]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v26[16]; // [rsp+170h] [rbp+70h] BYREF
  wchar_t pszDest[128]; // [rsp+180h] [rbp+80h] BYREF

  v4 = a4;
  TimeZoneId = -2147024809;
  if ( a4 )
  {
    memset_0(a4, 0, 0x114u);
    if ( StringCchLengthW(L"SystemDefaultTimeZone", v7, v8) >= 0 )
    {
      FileTime = 0;
      if ( a2 )
      {
        if ( SystemTimeToFileTime(a2, &FileTime) )
        {
          memset_0(pszDest, 0, sizeof(pszDest));
          TimeZoneId = ExtractTimeZoneId(L"SystemDefaultTimeZone", pszDest);
          if ( TimeZoneId >= 0 )
          {
            FileTime = 0;
            TimeZoneId = GetTimeZonesRoot((HKEY *)&FileTime);
            if ( TimeZoneId >= 0 )
            {
              hKey = 0;
              TimeZoneId = GetTimeZoneKey(*(HKEY *)&FileTime, pszDest, &hKey);
              if ( TimeZoneId >= 0 )
              {
                memset_0(v24, 0, 0x114u);
                TimeZoneId = GetOffsetAtLocalTime((_DWORD)hKey, (_DWORD)a2, v9, 0, (__int64)v26, (__int64)v25, 0);
                RegCloseKey(hKey);
                if ( TimeZoneId >= 0 )
                {
                  v10 = 2;
                  if ( StringCchCopyW(v24, 0x80u, pszDest) >= 0 )
                  {
                    v11 = v24;
                    do
                    {
                      v12 = *((_OWORD *)v11 + 1);
                      *v4 = *(_OWORD *)v11;
                      v13 = *((_OWORD *)v11 + 2);
                      v4[1] = v12;
                      v14 = *((_OWORD *)v11 + 3);
                      v4[2] = v13;
                      v15 = *((_OWORD *)v11 + 4);
                      v4[3] = v14;
                      v16 = *((_OWORD *)v11 + 5);
                      v4[4] = v15;
                      v17 = *((_OWORD *)v11 + 6);
                      v4[5] = v16;
                      v18 = *((_OWORD *)v11 + 7);
                      v11 += 64;
                      v4[6] = v17;
                      v4[7] = v18;
                      v4 += 8;
                      --v10;
                    }
                    while ( v10 );
                    v19 = *(_OWORD *)v11;
                    v20 = *((_DWORD *)v11 + 4);
                    *v4 = v19;
                    *((_DWORD *)v4 + 4) = v20;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  return (unsigned int)TimeZoneId;
}

```

## disassembly

```asm
0x180024984  mov     [rsp-8+arg_0], rbx
0x180024989  mov     [rsp-8+arg_10], rsi
0x18002498e  push    rbp
0x18002498f  push    rdi
0x180024990  push    r15
0x180024992  lea     rbp, [rsp-190h]
0x18002499a  sub     rsp, 290h
0x1800249a1  mov     rax, cs:__security_cookie
0x1800249a8  xor     rax, rsp
0x1800249ab  mov     [rbp+1A0h+var_20], rax
0x1800249b2  mov     rbx, r9
0x1800249b5  mov     rsi, rdx
0x1800249b8  mov     edi, 80070057h
0x1800249bd  test    r9, r9
0x1800249c0  jz      loc_180024B89
0x1800249c6  mov     r15d, 114h
0x1800249cc  xor     edx, edx; Val
0x1800249ce  mov     r8d, r15d; Size
0x1800249d1  mov     rcx, rbx; void *
0x1800249d4  call    memset_0
0x1800249d9  lea     rcx, aSystemdefaultt; "SystemDefaultTimeZone"
0x1800249e0  call    StringCchLengthW
0x1800249e5  test    eax, eax
0x1800249e7  js      loc_180024B89
0x1800249ed  mov     qword ptr [rsp+2A0h+FileTime.dwLowDateTime], 0
0x1800249f6  test    rsi, rsi
0x1800249f9  jz      loc_180024B89
0x1800249ff  lea     rdx, [rsp+2A0h+FileTime]; lpFileTime
0x180024a04  mov     rcx, rsi; lpSystemTime
0x180024a07  call    cs:__imp_SystemTimeToFileTime
0x180024a0d  test    eax, eax
0x180024a0f  jz      loc_180024B89
0x180024a15  xor     edx, edx; Val
0x180024a17  lea     r8d, [r15-14h]; Size
0x180024a1b  lea     rcx, [rbp+1A0h+pszDest]; void *
0x180024a22  call    memset_0
0x180024a27  lea     r9, [rsp+2A0h+var_260]
0x180024a2c  mov     [rsp+2A0h+var_260], 0
0x180024a34  lea     rdx, [rbp+1A0h+pszDest]; pszDest
0x180024a3b  lea     rcx, aSystemdefaultt; "SystemDefaultTimeZone"
0x180024a42  call    ExtractTimeZoneId
0x180024a47  mov     edi, eax
0x180024a49  test    eax, eax
0x180024a4b  js      loc_180024B89
0x180024a51  lea     rcx, [rsp+2A0h+FileTime]
0x180024a56  mov     qword ptr [rsp+2A0h+FileTime.dwLowDateTime], 0
0x180024a5f  call    GetTimeZonesRoot
0x180024a64  mov     edi, eax
0x180024a66  test    eax, eax
0x180024a68  js      loc_180024B89
0x180024a6e  mov     rcx, qword ptr [rsp+2A0h+FileTime.dwLowDateTime]
0x180024a73  lea     r8, [rsp+2A0h+hKey]
0x180024a78  lea     rdx, [rbp+1A0h+pszDest]
0x180024a7f  mov     [rsp+2A0h+hKey], 0
0x180024a88  call    GetTimeZoneKey
0x180024a8d  mov     edi, eax
0x180024a8f  test    eax, eax
0x180024a91  js      loc_180024B89
0x180024a97  mov     r8d, r15d; Size
0x180024a9a  lea     rcx, [rsp+2A0h+var_240]; void *
0x180024a9f  xor     edx, edx; Val
0x180024aa1  call    memset_0
0x180024aa6  mov     r9d, [rsp+2A0h+var_260]
0x180024aab  lea     rax, [rbp+1A0h+var_140]
0x180024aaf  mov     rcx, [rsp+2A0h+hKey]
0x180024ab4  mov     rdx, rsi
0x180024ab7  mov     [rsp+2A0h+var_270], 0
0x180024ac0  mov     [rsp+2A0h+var_278], rax
0x180024ac5  lea     rax, [rbp+1A0h+var_130]
0x180024ac9  mov     [rsp+2A0h+var_280], rax
0x180024ace  call    GetOffsetAtLocalTime
0x180024ad3  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180024ad8  mov     edi, eax
0x180024ada  call    cs:__imp_RegCloseKey
0x180024ae0  test    edi, edi
0x180024ae2  js      loc_180024B89
0x180024ae8  mov     esi, 2
0x180024aed  lea     r15d, [rsi+7Eh]
0x180024af1  test    byte ptr [rsp+2A0h+var_260], sil
0x180024af6  jz      short loc_180024B16
0x180024af8  lea     r8, pszSrc; "_dstoff"
0x180024aff  mov     edx, r15d; cchDest
0x180024b02  lea     rcx, [rbp+1A0h+pszDest]; pszDest
0x180024b09  call    StringCchCatW
0x180024b0e  test    eax, eax
0x180024b10  jns     short loc_180024B16
0x180024b12  mov     edi, eax
0x180024b14  jmp     short loc_180024B89
0x180024b16  lea     r8, [rbp+1A0h+pszDest]; pszSrc
0x180024b1d  mov     rdx, r15; cchDest
0x180024b20  lea     rcx, [rsp+2A0h+var_240]; pszDest
0x180024b25  call    StringCchCopyW
0x180024b2a  test    eax, eax
0x180024b2c  js      short loc_180024B89
0x180024b2e  lea     rax, [rsp+2A0h+var_240]
0x180024b33  movups  xmm0, xmmword ptr [rax]
0x180024b36  movups  xmm1, xmmword ptr [rax+10h]
0x180024b3a  movups  xmmword ptr [rbx], xmm0
0x180024b3d  movups  xmm0, xmmword ptr [rax+20h]
0x180024b41  movups  xmmword ptr [rbx+10h], xmm1
0x180024b45  movups  xmm1, xmmword ptr [rax+30h]
0x180024b49  movups  xmmword ptr [rbx+20h], xmm0
0x180024b4d  movups  xmm0, xmmword ptr [rax+40h]
0x180024b51  movups  xmmword ptr [rbx+30h], xmm1
0x180024b55  movups  xmm1, xmmword ptr [rax+50h]
0x180024b59  movups  xmmword ptr [rbx+40h], xmm0
0x180024b5d  movups  xmm0, xmmword ptr [rax+60h]
0x180024b61  movups  xmmword ptr [rbx+50h], xmm1
0x180024b65  movups  xmm1, xmmword ptr [rax+70h]
0x180024b69  add     rax, r15
0x180024b6c  movups  xmmword ptr [rbx+60h], xmm0
0x180024b70  movups  xmmword ptr [rbx+70h], xmm1
0x180024b74  add     rbx, r15
0x180024b77  sub     rsi, 1
0x180024b7b  jnz     short loc_180024B33
0x180024b7d  movups  xmm0, xmmword ptr [rax]
0x180024b80  mov     eax, [rax+10h]
0x180024b83  movups  xmmword ptr [rbx], xmm0
0x180024b86  mov     [rbx+10h], eax
0x180024b89  mov     eax, edi
0x180024b8b  mov     rcx, [rbp+1A0h+var_20]
0x180024b92  xor     rcx, rsp; StackCookie
0x180024b95  call    __security_check_cookie
0x180024b9a  lea     r11, [rsp+2A0h+var_10]
0x180024ba2  mov     rbx, [r11+20h]
0x180024ba6  mov     rsi, [r11+30h]
0x180024baa  mov     rsp, r11
0x180024bad  pop     r15
0x180024baf  pop     rdi
0x180024bb0  pop     rbp
0x180024bb1  retn
```
