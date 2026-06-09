# CDevicePolicy::LoadPolicy(ushort const *,ushort const *)

- ea: `0x14003a988`
- end: `0x14003ad70`
- name: `?LoadPolicy@CDevicePolicy@@QEAAJPEBG0@Z`
- size: `1000`
- prototype: `__int64 __fastcall(CDevicePolicy *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400022a4`
- `0x140024004`
- `0x14007bab0`

## callees

- `0x1400065e0`
- `0x140006d70`
- `0x14000c780`
- `0x140015100`
- `0x14003a988`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14003ad46`
- `ADVAPI32!RegCloseKey` at `0x14003ad46`
- `ADVAPI32!RegOpenKeyExW` at `0x14003aa19`
- `ADVAPI32!RegOpenKeyExW` at `0x14003aa9d`
- `ADVAPI32!RegOpenKeyExW` at `0x14003aa19`
- `ADVAPI32!RegOpenKeyExW` at `0x14003aa9d`
- `ADVAPI32!RegGetValueW` at `0x14003ab01`
- `ADVAPI32!RegGetValueW` at `0x14003ab53`
- `ADVAPI32!RegGetValueW` at `0x14003aba5`
- `ADVAPI32!RegGetValueW` at `0x14003abf0`
- `ADVAPI32!RegGetValueW` at `0x14003ac42`
- `ADVAPI32!RegGetValueW` at `0x14003ac8f`
- `ADVAPI32!RegGetValueW` at `0x14003acf6`
- `ADVAPI32!RegGetValueW` at `0x14003ab01`
- `ADVAPI32!RegGetValueW` at `0x14003ab53`
- `ADVAPI32!RegGetValueW` at `0x14003aba5`
- `ADVAPI32!RegGetValueW` at `0x14003abf0`
- `ADVAPI32!RegGetValueW` at `0x14003ac42`
- `ADVAPI32!RegGetValueW` at `0x14003ac8f`
- `ADVAPI32!RegGetValueW` at `0x14003acf6`
- `ole32!CoTaskMemFree` at `0x14003ad07`
- `ole32!CoTaskMemFree` at `0x14003ad07`
- `ole32!CoTaskMemAlloc` at `0x14003acba`
- `ole32!CoTaskMemAlloc` at `0x14003acba`

## string_xrefs

- `0x14003aad3`: `AccessPrivateContent`

## pseudocode

```c
__int64 __fastcall CDevicePolicy::LoadPolicy(CDevicePolicy *this, char *a2, const unsigned __int16 *a3)
{
  signed int v4; // edi
  LPCWSTR v7; // rbx
  LSTATUS v8; // eax
  HKEY v9; // rcx
  LSTATUS ValueW; // eax
  HKEY v11; // rcx
  LSTATUS v12; // eax
  HKEY v13; // rcx
  LSTATUS v14; // eax
  HKEY v15; // rcx
  LSTATUS v16; // eax
  HKEY v17; // rcx
  LSTATUS v18; // eax
  HKEY v19; // rcx
  LSTATUS v20; // eax
  void *pvData; // rax
  LSTATUS v22; // r14d
  DWORD pcbData; // [rsp+40h] [rbp-10h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-8h] BYREF
  LPCWSTR lpSubKey; // [rsp+98h] [rbp+48h] BYREF

  v4 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    (void **)&lpSubKey,
    a2);
  ATL::CSimpleStringT<unsigned short,0>::Append((__int64 *)&lpSubKey, L"\\");
  ATL::CSimpleStringT<unsigned short,0>::Append(
    (__int64 *)&lpSubKey,
    L"Software\\Microsoft\\MediaPlayer\\Preferences\\HME");
  ATL::CSimpleStringT<unsigned short,0>::Append((__int64 *)&lpSubKey, L"\\");
  ATL::CSimpleStringT<unsigned short,0>::Append((__int64 *)&lpSubKey, a3);
  v7 = lpSubKey;
  hkey = 0;
  if ( RegOpenKeyExW(HKEY_USERS, lpSubKey, 0, 0x20119u, &hkey) )
  {
    ATL::CSimpleStringT<unsigned short,0>::SetString(&lpSubKey, a2);
    ATL::CSimpleStringT<unsigned short,0>::Append((__int64 *)&lpSubKey, L"\\");
    ATL::CSimpleStringT<unsigned short,0>::Append(
      (__int64 *)&lpSubKey,
      L"Software\\Microsoft\\MediaPlayer\\Preferences\\HME");
    ATL::CSimpleStringT<unsigned short,0>::Append((__int64 *)&lpSubKey, L"\\Default");
    v7 = lpSubKey;
    v8 = RegOpenKeyExW(HKEY_USERS, lpSubKey, 0, 0x20119u, &hkey);
    v4 = v8;
    if ( v8 )
    {
      if ( v8 > 0 )
        v4 = (unsigned __int16)v8 | 0x80070000;
      if ( v4 < 0 )
      {
        v4 = 0;
        *(_DWORD *)this = 1;
        goto LABEL_43;
      }
    }
    else
    {
      v4 = 0;
    }
  }
  v9 = hkey;
  *(_DWORD *)this = 0;
  LODWORD(lpSubKey) = 0;
  pcbData = 4;
  ValueW = RegGetValueW(v9, 0, L"AccessPrivateContent", 0x10u, 0, &lpSubKey, &pcbData);
  if ( ValueW > 0 )
  {
    v4 = (unsigned __int16)ValueW | 0x80070000;
  }
  else if ( ValueW )
  {
    v4 = ValueW;
  }
  if ( v4 >= 0 )
  {
    v11 = hkey;
    *((_DWORD *)this + 1) = (_DWORD)lpSubKey != 0;
    v12 = RegGetValueW(v11, 0, L"ZeroStars", 0x10u, 0, &lpSubKey, &pcbData);
    if ( v12 > 0 )
    {
      v4 = (unsigned __int16)v12 | 0x80070000;
    }
    else if ( v12 )
    {
      v4 = v12;
    }
    else
    {
      v13 = hkey;
      *((_DWORD *)this + 4) = (_DWORD)lpSubKey != 0;
      v14 = RegGetValueW(v13, 0, L"MinStars", 0x10u, 0, &lpSubKey, &pcbData);
      if ( v14 > 0 )
      {
        v4 = (unsigned __int16)v14 | 0x80070000;
      }
      else if ( v14 )
      {
        v4 = v14;
      }
      else
      {
        v15 = hkey;
        *((_DWORD *)this + 3) = (_DWORD)lpSubKey;
        v16 = RegGetValueW(v15, 0, L"AllStars", 0x10u, 0, &lpSubKey, &pcbData);
        if ( v16 > 0 )
        {
          v4 = (unsigned __int16)v16 | 0x80070000;
        }
        else if ( v16 )
        {
          v4 = v16;
        }
        else
        {
          v17 = hkey;
          *((_DWORD *)this + 2) = (_DWORD)lpSubKey != 0;
          v18 = RegGetValueW(v17, 0, L"AllParentalRatings", 0x10u, 0, &lpSubKey, &pcbData);
          if ( v18 > 0 )
          {
            v4 = (unsigned __int16)v18 | 0x80070000;
          }
          else if ( v18 )
          {
            v4 = v18;
          }
          else
          {
            v19 = hkey;
            *((_DWORD *)this + 5) = (_DWORD)lpSubKey != 0;
            v20 = RegGetValueW(v19, 0, L"ParentalRatingData", 8u, 0, 0, &pcbData);
            if ( v20 > 0 )
            {
              v4 = (unsigned __int16)v20 | 0x80070000;
            }
            else if ( v20 )
            {
              v4 = v20;
            }
          }
        }
      }
    }
  }
  if ( !*((_DWORD *)this + 5) && v4 >= 0 )
  {
    pvData = CoTaskMemAlloc(pcbData);
    *((_QWORD *)this + 4) = pvData;
    if ( pvData )
    {
      v22 = RegGetValueW(hkey, 0, L"ParentalRatingData", 8u, 0, pvData, &pcbData);
      if ( v22 )
      {
        CoTaskMemFree(*((LPVOID *)this + 4));
        *((_QWORD *)this + 4) = 0;
        if ( v22 > 0 )
          v4 = (unsigned __int16)v22 | 0x80070000;
        else
          v4 = v22;
      }
      else
      {
        *((_DWORD *)this + 6) = pcbData / 0xC;
      }
    }
    else
    {
      v4 = -2147024882;
    }
  }
LABEL_43:
  if ( hkey )
    RegCloseKey(hkey);
  ATL::CStringData::Release((ATL::CStringData *)(v7 - 12));
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14003a988  mov     [rsp-28h+arg_0], rbx
0x14003a98d  mov     [rsp-28h+arg_8], rsi
0x14003a992  push    rbp
0x14003a993  push    rdi
0x14003a994  push    r12
0x14003a996  push    r14
0x14003a998  push    r15
0x14003a99a  mov     rbp, rsp
0x14003a99d  sub     rsp, 50h
0x14003a9a1  mov     rsi, rcx
0x14003a9a4  xor     r15d, r15d
0x14003a9a7  lea     rcx, [rbp+lpSubKey]
0x14003a9ab  mov     edi, r15d
0x14003a9ae  mov     rbx, r8
0x14003a9b1  mov     r14, rdx
0x14003a9b4  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x14003a9b9  lea     rdx, asc_1400A283C; "\\"
0x14003a9c0  lea     rcx, [rbp+lpSubKey]
0x14003a9c4  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x14003a9c9  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\MediaPlayer\\Prefe"...
0x14003a9d0  lea     rcx, [rbp+lpSubKey]
0x14003a9d4  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x14003a9d9  lea     rdx, asc_1400A283C; "\\"
0x14003a9e0  lea     rcx, [rbp+lpSubKey]
0x14003a9e4  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x14003a9e9  mov     rdx, rbx
0x14003a9ec  lea     rcx, [rbp+lpSubKey]
0x14003a9f0  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x14003a9f5  mov     rbx, [rbp+lpSubKey]
0x14003a9f9  lea     rax, [rbp+hkey]
0x14003a9fd  mov     rdx, rbx; lpSubKey
0x14003aa00  mov     [rsp+50h+phkResult], rax; phkResult
0x14003aa05  mov     r9d, 20119h; samDesired
0x14003aa0b  mov     [rbp+hkey], r15
0x14003aa0f  xor     r8d, r8d; ulOptions
0x14003aa12  mov     rcx, 0FFFFFFFF80000003h; hKey
0x14003aa19  call    cs:__imp_RegOpenKeyExW
0x14003aa1f  mov     r12d, 80070000h
0x14003aa25  test    eax, eax
0x14003aa27  jz      loc_14003AAC6
0x14003aa2d  jg      short loc_14003AA33
0x14003aa2f  mov     edi, eax
0x14003aa31  jmp     short loc_14003AA39
0x14003aa33  movzx   edi, ax
0x14003aa36  or      edi, r12d
0x14003aa39  test    edi, edi
0x14003aa3b  jns     loc_14003AAC6
0x14003aa41  mov     rdx, r14
0x14003aa44  lea     rcx, [rbp+lpSubKey]
0x14003aa48  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x14003aa4d  lea     rdx, asc_1400A283C; "\\"
0x14003aa54  lea     rcx, [rbp+lpSubKey]
0x14003aa58  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x14003aa5d  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\MediaPlayer\\Prefe"...
0x14003aa64  lea     rcx, [rbp+lpSubKey]
0x14003aa68  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x14003aa6d  lea     rdx, aDefault; "\\Default"
0x14003aa74  lea     rcx, [rbp+lpSubKey]
0x14003aa78  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x14003aa7d  mov     rbx, [rbp+lpSubKey]
0x14003aa81  lea     rax, [rbp+hkey]
0x14003aa85  mov     rdx, rbx; lpSubKey
0x14003aa88  mov     [rsp+50h+phkResult], rax; phkResult
0x14003aa8d  mov     r9d, 20119h; samDesired
0x14003aa93  xor     r8d, r8d; ulOptions
0x14003aa96  mov     rcx, 0FFFFFFFF80000003h; hKey
0x14003aa9d  call    cs:__imp_RegOpenKeyExW
0x14003aaa3  mov     edi, eax
0x14003aaa5  test    eax, eax
0x14003aaa7  jz      short loc_14003AAC3
0x14003aaa9  jle     short loc_14003AAB1
0x14003aaab  movzx   edi, ax
0x14003aaae  or      edi, r12d
0x14003aab1  test    edi, edi
0x14003aab3  jns     short loc_14003AAC6
0x14003aab5  mov     edi, r15d
0x14003aab8  mov     dword ptr [rsi], 1
0x14003aabe  jmp     loc_14003AD3D
0x14003aac3  mov     edi, r15d
0x14003aac6  mov     rcx, [rbp+hkey]; hkey
0x14003aaca  lea     rax, [rbp+var_10]
0x14003aace  mov     [rsp+50h+pcbData], rax; pcbData
0x14003aad3  lea     r8, Value; "AccessPrivateContent"
0x14003aada  lea     rax, [rbp+lpSubKey]
0x14003aade  mov     [rsi], r15d
0x14003aae1  mov     [rsp+50h+pvData], rax; pvData
0x14003aae6  mov     r14d, 10h
0x14003aaec  mov     r9d, r14d; dwFlags
0x14003aaef  mov     [rsp+50h+phkResult], r15; pdwType
0x14003aaf4  xor     edx, edx; lpSubKey
0x14003aaf6  mov     dword ptr [rbp+lpSubKey], r15d
0x14003aafa  mov     [rbp+var_10], 4
0x14003ab01  call    cs:__imp_RegGetValueW
0x14003ab07  test    eax, eax
0x14003ab09  jg      short loc_14003AB11
0x14003ab0b  jz      short loc_14003AB17
0x14003ab0d  mov     edi, eax
0x14003ab0f  jmp     short loc_14003AB17
0x14003ab11  movzx   edi, ax
0x14003ab14  or      edi, r12d
0x14003ab17  test    edi, edi
0x14003ab19  js      loc_14003ACA5
0x14003ab1f  cmp     dword ptr [rbp+lpSubKey], r15d
0x14003ab23  lea     r8, aZerostars; "ZeroStars"
0x14003ab2a  mov     rcx, [rbp+hkey]; hkey
0x14003ab2e  mov     eax, r15d
0x14003ab31  setnz   al
0x14003ab34  mov     r9d, r14d; dwFlags
0x14003ab37  mov     [rsi+4], eax
0x14003ab3a  xor     edx, edx; lpSubKey
0x14003ab3c  lea     rax, [rbp+var_10]
0x14003ab40  mov     [rsp+50h+pcbData], rax; pcbData
0x14003ab45  lea     rax, [rbp+lpSubKey]
0x14003ab49  mov     [rsp+50h+pvData], rax; pvData
0x14003ab4e  mov     [rsp+50h+phkResult], r15; pdwType
0x14003ab53  call    cs:__imp_RegGetValueW
0x14003ab59  test    eax, eax
0x14003ab5b  jg      short loc_14003AB63
0x14003ab5d  jz      short loc_14003AB71
0x14003ab5f  mov     edi, eax
0x14003ab61  jmp     short loc_14003AB69
0x14003ab63  movzx   edi, ax
0x14003ab66  or      edi, r12d
0x14003ab69  test    edi, edi
0x14003ab6b  js      loc_14003ACA5
0x14003ab71  cmp     dword ptr [rbp+lpSubKey], r15d
0x14003ab75  lea     r8, aMinstars; "MinStars"
0x14003ab7c  mov     rcx, [rbp+hkey]; hkey
0x14003ab80  mov     eax, r15d
0x14003ab83  setnz   al
0x14003ab86  mov     r9d, r14d; dwFlags
0x14003ab89  mov     [rsi+10h], eax
0x14003ab8c  xor     edx, edx; lpSubKey
0x14003ab8e  lea     rax, [rbp+var_10]
0x14003ab92  mov     [rsp+50h+pcbData], rax; pcbData
0x14003ab97  lea     rax, [rbp+lpSubKey]
0x14003ab9b  mov     [rsp+50h+pvData], rax; pvData
0x14003aba0  mov     [rsp+50h+phkResult], r15; pdwType
0x14003aba5  call    cs:__imp_RegGetValueW
0x14003abab  test    eax, eax
0x14003abad  jg      short loc_14003ABB5
0x14003abaf  jz      short loc_14003ABC3
0x14003abb1  mov     edi, eax
0x14003abb3  jmp     short loc_14003ABBB
0x14003abb5  movzx   edi, ax
0x14003abb8  or      edi, r12d
0x14003abbb  test    edi, edi
0x14003abbd  js      loc_14003ACA5
0x14003abc3  mov     eax, dword ptr [rbp+lpSubKey]
0x14003abc6  lea     r8, aAllstars; "AllStars"
0x14003abcd  mov     rcx, [rbp+hkey]; hkey
0x14003abd1  mov     r9d, r14d; dwFlags
0x14003abd4  mov     [rsi+0Ch], eax
0x14003abd7  xor     edx, edx; lpSubKey
0x14003abd9  lea     rax, [rbp+var_10]
0x14003abdd  mov     [rsp+50h+pcbData], rax; pcbData
0x14003abe2  lea     rax, [rbp+lpSubKey]
0x14003abe6  mov     [rsp+50h+pvData], rax; pvData
0x14003abeb  mov     [rsp+50h+phkResult], r15; pdwType
0x14003abf0  call    cs:__imp_RegGetValueW
0x14003abf6  test    eax, eax
0x14003abf8  jg      short loc_14003AC00
0x14003abfa  jz      short loc_14003AC0E
0x14003abfc  mov     edi, eax
0x14003abfe  jmp     short loc_14003AC06
0x14003ac00  movzx   edi, ax
0x14003ac03  or      edi, r12d
0x14003ac06  test    edi, edi
0x14003ac08  js      loc_14003ACA5
0x14003ac0e  cmp     dword ptr [rbp+lpSubKey], r15d
0x14003ac12  lea     r8, aAllparentalrat; "AllParentalRatings"
0x14003ac19  mov     rcx, [rbp+hkey]; hkey
0x14003ac1d  mov     eax, r15d
0x14003ac20  setnz   al
0x14003ac23  mov     r9d, r14d; dwFlags
0x14003ac26  mov     [rsi+8], eax
0x14003ac29  xor     edx, edx; lpSubKey
0x14003ac2b  lea     rax, [rbp+var_10]
0x14003ac2f  mov     [rsp+50h+pcbData], rax; pcbData
0x14003ac34  lea     rax, [rbp+lpSubKey]
0x14003ac38  mov     [rsp+50h+pvData], rax; pvData
0x14003ac3d  mov     [rsp+50h+phkResult], r15; pdwType
0x14003ac42  call    cs:__imp_RegGetValueW
0x14003ac48  test    eax, eax
0x14003ac4a  jg      short loc_14003AC52
0x14003ac4c  jz      short loc_14003AC5C
0x14003ac4e  mov     edi, eax
0x14003ac50  jmp     short loc_14003AC58
0x14003ac52  movzx   edi, ax
0x14003ac55  or      edi, r12d
0x14003ac58  test    edi, edi
0x14003ac5a  js      short loc_14003ACA5
0x14003ac5c  cmp     dword ptr [rbp+lpSubKey], r15d
0x14003ac60  lea     r8, aParentalrating; "ParentalRatingData"
0x14003ac67  mov     rcx, [rbp+hkey]; hkey
0x14003ac6b  mov     eax, r15d
0x14003ac6e  setnz   al
0x14003ac71  mov     r9d, 8; dwFlags
0x14003ac77  mov     [rsi+14h], eax
0x14003ac7a  xor     edx, edx; lpSubKey
0x14003ac7c  lea     rax, [rbp+var_10]
0x14003ac80  mov     [rsp+50h+pcbData], rax; pcbData
0x14003ac85  mov     [rsp+50h+pvData], r15; pvData
0x14003ac8a  mov     [rsp+50h+phkResult], r15; pdwType
0x14003ac8f  call    cs:__imp_RegGetValueW
0x14003ac95  test    eax, eax
0x14003ac97  jg      short loc_14003AC9F
0x14003ac99  jz      short loc_14003ACA5
0x14003ac9b  mov     edi, eax
0x14003ac9d  jmp     short loc_14003ACA5
0x14003ac9f  movzx   edi, ax
0x14003aca2  or      edi, r12d
0x14003aca5  cmp     [rsi+14h], r15d
0x14003aca9  jnz     loc_14003AD3D
0x14003acaf  test    edi, edi
0x14003acb1  js      loc_14003AD3D
0x14003acb7  mov     ecx, [rbp+var_10]; cb
0x14003acba  call    cs:__imp_CoTaskMemAlloc
0x14003acc0  mov     [rsi+20h], rax
0x14003acc4  test    rax, rax
0x14003acc7  jnz     short loc_14003ACD0
0x14003acc9  mov     edi, 8007000Eh
0x14003acce  jmp     short loc_14003AD3D
0x14003acd0  lea     rcx, [rbp+var_10]
0x14003acd4  mov     r9d, 8; dwFlags
0x14003acda  mov     [rsp+50h+pcbData], rcx; pcbData
0x14003acdf  lea     r8, aParentalrating; "ParentalRatingData"
0x14003ace6  mov     rcx, [rbp+hkey]; hkey
0x14003acea  xor     edx, edx; lpSubKey
0x14003acec  mov     [rsp+50h+pvData], rax; pvData
0x14003acf1  mov     [rsp+50h+phkResult], r15; pdwType
0x14003acf6  call    cs:__imp_RegGetValueW
0x14003acfc  mov     r14d, eax
0x14003acff  test    eax, eax
0x14003ad01  jz      short loc_14003AD26
0x14003ad03  mov     rcx, [rsi+20h]; pv
0x14003ad07  call    cs:__imp_CoTaskMemFree
0x14003ad0d  mov     [rsi+20h], r15
0x14003ad11  test    r14d, r14d
0x14003ad14  jg      short loc_14003AD1B
0x14003ad16  mov     edi, r14d
0x14003ad19  jmp     short loc_14003AD22
0x14003ad1b  movzx   edi, r14w
0x14003ad1f  or      edi, r12d
0x14003ad22  test    edi, edi
0x14003ad24  js      short loc_14003AD3D
0x14003ad26  mov     ecx, [rbp+var_10]
0x14003ad29  mov     rax, 0AAAAAAAAAAAAAAABh
0x14003ad33  mul     rcx
0x14003ad36  shr     rdx, 3
0x14003ad3a  mov     [rsi+18h], edx
0x14003ad3d  mov     rcx, [rbp+hkey]; hKey
0x14003ad41  test    rcx, rcx
0x14003ad44  jz      short loc_14003AD4C
0x14003ad46  call    cs:__imp_RegCloseKey
0x14003ad4c  lea     rcx, [rbx-18h]; this
0x14003ad50  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14003ad55  lea     r11, [rsp+50h+var_s0]
0x14003ad5a  mov     eax, edi
0x14003ad5c  mov     rbx, [r11+30h]
0x14003ad60  mov     rsi, [r11+38h]
0x14003ad64  mov     rsp, r11
0x14003ad67  pop     r15
0x14003ad69  pop     r14
0x14003ad6b  pop     r12
0x14003ad6d  pop     rdi
0x14003ad6e  pop     rbp
0x14003ad6f  retn
```
