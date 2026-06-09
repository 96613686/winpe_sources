# ConvertOneLocation

- ea: `0x18003e9a4`
- end: `0x18003ee1c`
- name: `ConvertOneLocation`
- size: `1144`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18003e510`

## callees

- `0x180001600`
- `0x18003e9a4`
- `0x18003f10c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__itow` at `0x18003ed4b`
- `api-ms-win-crt-private-l1-1-0!_o__itow` at `0x18003ed4b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003eda9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003edb9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003edc9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003eda9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003edb9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003edc9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003edd8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003edd8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003eae5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003eae5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003eb6b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003eb6b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003ea11`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003ea5b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003ea98`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003ebad`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003ebfc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003ecc6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003ed15`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003ea11`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003ea5b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003ea98`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003ebad`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003ebfc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003ecc6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003ed15`
- `KERNEL32!GlobalAlloc` at `0x18003ebcb`
- `KERNEL32!GlobalAlloc` at `0x18003ece4`
- `KERNEL32!GlobalAlloc` at `0x18003ebcb`
- `KERNEL32!GlobalAlloc` at `0x18003ece4`
- `KERNEL32!GlobalFree` at `0x18003ede6`
- `KERNEL32!GlobalFree` at `0x18003edf4`
- `KERNEL32!GlobalFree` at `0x18003ede6`
- `KERNEL32!GlobalFree` at `0x18003edf4`

## pseudocode

```c
__int64 __fastcall ConvertOneLocation(HKEY hKey)
{
  unsigned __int64 i; // rsi
  BYTE *v3; // r12
  BYTE *v4; // r13
  unsigned int AreaCodeRule; // ebx
  int v6; // r15d
  __int16 v7; // ax
  BYTE *v8; // rcx
  BYTE *v9; // r8
  __int16 v10; // ax
  _WORD *v11; // rdx
  int *v12; // r14
  DWORD Type; // [rsp+50h] [rbp-49h] BYREF
  DWORD cbData; // [rsp+54h] [rbp-45h] BYREF
  DWORD lpcbData; // [rsp+58h] [rbp-41h] BYREF
  BYTE Data[4]; // [rsp+5Ch] [rbp-3Dh] BYREF
  DWORD dwDisposition; // [rsp+60h] [rbp-39h] BYREF
  BYTE v19[4]; // [rsp+64h] [rbp-35h] BYREF
  HKEY hKeya; // [rsp+68h] [rbp-31h] BYREF
  BYTE lpData[32]; // [rsp+70h] [rbp-29h] BYREF
  wchar_t Buffer[12]; // [rsp+90h] [rbp-9h] BYREF

  LODWORD(i) = 0;
  *(_DWORD *)Data = 0;
  *(_DWORD *)v19 = 0;
  Type = 0;
  cbData = 4;
  lpcbData = 0;
  v3 = 0;
  dwDisposition = 0;
  v4 = 0;
  hKeya = 0;
  AreaCodeRule = RegQueryValueExW(hKey, L"Flags", 0, &Type, Data, &cbData);
  if ( !AreaCodeRule )
  {
    if ( Type != 4 )
    {
LABEL_3:
      AreaCodeRule = 13;
      goto LABEL_44;
    }
    cbData = 32;
    AreaCodeRule = RegQueryValueExW(hKey, L"AreaCode", 0, &Type, lpData, &cbData);
    if ( !AreaCodeRule )
    {
      if ( Type != 1 )
        goto LABEL_3;
      cbData = 4;
      AreaCodeRule = RegQueryValueExW(hKey, L"Country", 0, &Type, v19, &cbData);
      if ( !AreaCodeRule )
      {
        if ( Type != 4 )
          goto LABEL_3;
        AreaCodeRule = RegCreateKeyExW(hKey, L"AreaCodeRules", 0, 0, 0, 0x20006u, 0, &hKeya, &dwDisposition);
        if ( !AreaCodeRule )
        {
          if ( dwDisposition != 1 )
            goto LABEL_3;
          v6 = 0;
          if ( (Data[0] & 8) == 0
            || (AreaCodeRule = CreateAreaCodeRule(hKeya, (BYTE *)&dword_18004C2D4, 4u, 3u)) == 0
            && (*(_DWORD *)Data &= ~8u,
                v6 = 1,
                cbData = 4,
                (AreaCodeRule = RegSetValueExW(hKey, L"Flags", 0, 4u, Data, 4u)) == 0) )
          {
            if ( *(_DWORD *)v19 != 1 && (unsigned int)(*(_DWORD *)v19 - 100) > 0x63 )
              goto LABEL_43;
            if ( RegQueryValueExW(hKey, L"TollList", 0, 0, 0, &lpcbData) )
              goto LABEL_33;
            v3 = (BYTE *)GlobalAlloc(0x40u, lpcbData + 2LL);
            if ( !v3 )
              goto LABEL_42;
            AreaCodeRule = RegQueryValueExW(hKey, L"TollList", 0, &Type, v3, &lpcbData);
            if ( AreaCodeRule )
              goto LABEL_44;
            if ( Type != 1 )
              goto LABEL_3;
            v7 = *(_WORD *)v3;
            v8 = v3;
            while ( v7 == 44 )
            {
              v8 += 2;
              lpcbData -= 2;
              v7 = *(_WORD *)v8;
            }
            if ( !v7 )
            {
LABEL_33:
              if ( !RegQueryValueExW(hKey, L"NoPrefAC", 0, 0, 0, &cbData) && cbData )
              {
                v4 = (BYTE *)GlobalAlloc(0x40u, cbData);
                if ( v4 )
                {
                  AreaCodeRule = RegQueryValueExW(hKey, L"NoPrefAC", 0, &Type, v4, &cbData);
                  if ( AreaCodeRule )
                    goto LABEL_44;
                  if ( Type != 3 )
                    goto LABEL_3;
                  v12 = (int *)v4;
                  for ( i = (unsigned __int64)cbData >> 2; i; --i )
                  {
                    _itow(*v12, Buffer, 10);
                    AreaCodeRule = CreateAreaCodeRule(hKeya, (BYTE *)&dword_18004C2D4, 4u, 3u);
                    if ( AreaCodeRule )
                      goto LABEL_44;
                    ++v6;
                    ++v12;
                  }
                  goto LABEL_43;
                }
LABEL_42:
                AreaCodeRule = 14;
                goto LABEL_44;
              }
LABEL_43:
              AreaCodeRule = i;
              RegDeleteValueW(hKey, L"TollList");
              RegDeleteValueW(hKey, L"NoPrefAC");
              RegDeleteValueW(hKey, L"ID");
              goto LABEL_44;
            }
            v9 = v8;
            if ( *(_WORD *)v8 )
            {
              do
              {
                v10 = *(_WORD *)v8;
                do
                {
                  if ( v10 == 44 )
                    break;
                  v8 += 2;
                  v10 = *(_WORD *)v8;
                }
                while ( *(_WORD *)v8 );
                v11 = v8 + 2;
                if ( *(_WORD *)v8 )
                {
                  *(_WORD *)v8 = 0;
                }
                else
                {
                  *v11 = 0;
                  lpcbData += 2;
                }
                v8 += 2;
              }
              while ( *v11 );
            }
            AreaCodeRule = CreateAreaCodeRule(hKeya, v9, lpcbData, 6u);
            if ( !AreaCodeRule )
            {
              ++v6;
              goto LABEL_33;
            }
          }
        }
      }
    }
  }
LABEL_44:
  if ( hKeya )
    RegCloseKey(hKeya);
  if ( v3 )
    GlobalFree(v3);
  if ( v4 )
    GlobalFree(v4);
  return AreaCodeRule;
}

```

## disassembly

```asm
0x18003e9a4  push    rbp
0x18003e9a6  push    rbx
0x18003e9a7  push    rsi
0x18003e9a8  push    rdi
0x18003e9a9  push    r12
0x18003e9ab  push    r13
0x18003e9ad  push    r14
0x18003e9af  push    r15
0x18003e9b1  lea     rbp, [rsp-1Fh]
0x18003e9b6  sub     rsp, 0B8h
0x18003e9bd  mov     rax, cs:__security_cookie
0x18003e9c4  xor     rax, rsp
0x18003e9c7  mov     [rbp+57h+var_48], rax
0x18003e9cb  xor     esi, esi
0x18003e9cd  lea     rax, [rbp+57h+cbData]
0x18003e9d1  mov     [rsp+0F0h+lpcbData], rax; lpcbData
0x18003e9d6  lea     r9, [rbp+57h+Type]; lpType
0x18003e9da  lea     rax, [rbp+57h+Data]
0x18003e9de  mov     dword ptr [rbp+57h+Data], esi
0x18003e9e1  xor     r8d, r8d; lpReserved
0x18003e9e4  mov     dword ptr [rbp+57h+var_8C], esi
0x18003e9e7  lea     r14d, [rsi+4]
0x18003e9eb  mov     [rbp+57h+Type], esi
0x18003e9ee  lea     rdx, aFlags; "Flags"
0x18003e9f5  mov     [rbp+57h+cbData], r14d
0x18003e9f9  mov     rdi, rcx
0x18003e9fc  mov     [rbp+57h+var_98], esi
0x18003e9ff  mov     r12d, esi
0x18003ea02  mov     [rbp+57h+dwDisposition], esi
0x18003ea05  mov     r13d, esi
0x18003ea08  mov     [rbp+57h+hKey], rsi
0x18003ea0c  mov     [rsp+0F0h+lpData], rax; lpData
0x18003ea11  call    cs:__imp_RegQueryValueExW
0x18003ea17  mov     ebx, eax
0x18003ea19  test    eax, eax
0x18003ea1b  jnz     loc_18003EDCF
0x18003ea21  cmp     [rbp+57h+Type], r14d
0x18003ea25  jz      short loc_18003EA31
0x18003ea27  mov     ebx, 0Dh
0x18003ea2c  jmp     loc_18003EDCF
0x18003ea31  lea     rax, [rbp+57h+cbData]
0x18003ea35  mov     [rbp+57h+cbData], 20h ; ' '
0x18003ea3c  mov     [rsp+0F0h+lpcbData], rax; lpcbData
0x18003ea41  lea     r9, [rbp+57h+Type]; lpType
0x18003ea45  lea     rax, [rbp+57h+var_80]
0x18003ea49  xor     r8d, r8d; lpReserved
0x18003ea4c  lea     rdx, aAreacode; "AreaCode"
0x18003ea53  mov     [rsp+0F0h+lpData], rax; lpData
0x18003ea58  mov     rcx, rdi; hKey
0x18003ea5b  call    cs:__imp_RegQueryValueExW
0x18003ea61  mov     ebx, eax
0x18003ea63  test    eax, eax
0x18003ea65  jnz     loc_18003EDCF
0x18003ea6b  cmp     [rbp+57h+Type], 1
0x18003ea6f  jnz     short loc_18003EA27
0x18003ea71  lea     rax, [rbp+57h+cbData]
0x18003ea75  mov     [rbp+57h+cbData], r14d
0x18003ea79  mov     [rsp+0F0h+lpcbData], rax; lpcbData
0x18003ea7e  lea     r9, [rbp+57h+Type]; lpType
0x18003ea82  lea     rax, [rbp+57h+var_8C]
0x18003ea86  xor     r8d, r8d; lpReserved
0x18003ea89  lea     rdx, aCountry; "Country"
0x18003ea90  mov     [rsp+0F0h+lpData], rax; lpData
0x18003ea95  mov     rcx, rdi; hKey
0x18003ea98  call    cs:__imp_RegQueryValueExW
0x18003ea9e  mov     ebx, eax
0x18003eaa0  test    eax, eax
0x18003eaa2  jnz     loc_18003EDCF
0x18003eaa8  cmp     [rbp+57h+Type], r14d
0x18003eaac  jnz     loc_18003EA27
0x18003eab2  lea     rax, [rbp+57h+dwDisposition]
0x18003eab6  xor     r9d, r9d; lpClass
0x18003eab9  mov     [rsp+0F0h+lpdwDisposition], rax; lpdwDisposition
0x18003eabe  lea     rdx, aAreacoderules; "AreaCodeRules"
0x18003eac5  lea     rax, [rbp+57h+hKey]
0x18003eac9  xor     r8d, r8d; Reserved
0x18003eacc  mov     [rsp+0F0h+phkResult], rax; phkResult
0x18003ead1  mov     rcx, rdi; hKey
0x18003ead4  mov     [rsp+0F0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18003ead9  mov     dword ptr [rsp+0F0h+lpcbData], 20006h; samDesired
0x18003eae1  mov     dword ptr [rsp+0F0h+lpData], esi; dwOptions
0x18003eae5  call    cs:__imp_RegCreateKeyExW
0x18003eaeb  mov     ebx, eax
0x18003eaed  test    eax, eax
0x18003eaef  jnz     loc_18003EDCF
0x18003eaf5  cmp     [rbp+57h+dwDisposition], 1
0x18003eaf9  jnz     loc_18003EA27
0x18003eaff  test    [rbp+57h+Data], 8
0x18003eb03  lea     rax, dword_18004C2D4
0x18003eb0a  mov     r15d, esi
0x18003eb0d  jz      short loc_18003EB7B
0x18003eb0f  mov     rcx, [rbp+57h+hKey]; hKey
0x18003eb13  lea     r9, qword_18004C218
0x18003eb1a  mov     dword ptr [rsp+0F0h+lpSecurityAttributes], 3; Data
0x18003eb22  lea     r8, [rbp+57h+var_80]
0x18003eb26  mov     dword ptr [rsp+0F0h+lpcbData], r14d; cbData
0x18003eb2b  xor     edx, edx
0x18003eb2d  mov     [rsp+0F0h+lpData], rax; lpData
0x18003eb32  call    CreateAreaCodeRule
0x18003eb37  mov     ebx, eax
0x18003eb39  test    eax, eax
0x18003eb3b  jnz     loc_18003EDCF
0x18003eb41  and     dword ptr [rbp+57h+Data], 0FFFFFFF7h
0x18003eb45  lea     r15d, [rax+1]
0x18003eb49  lea     rax, [rbp+57h+Data]
0x18003eb4d  mov     dword ptr [rsp+0F0h+lpcbData], r14d; cbData
0x18003eb52  mov     r9d, r14d; dwType
0x18003eb55  mov     [rsp+0F0h+lpData], rax; lpData
0x18003eb5a  xor     r8d, r8d; Reserved
0x18003eb5d  mov     [rbp+57h+cbData], r14d
0x18003eb61  lea     rdx, aFlags; "Flags"
0x18003eb68  mov     rcx, rdi; hKey
0x18003eb6b  call    cs:__imp_RegSetValueExW
0x18003eb71  mov     ebx, eax
0x18003eb73  test    eax, eax
0x18003eb75  jnz     loc_18003EDCF
0x18003eb7b  mov     eax, dword ptr [rbp+57h+var_8C]
0x18003eb7e  cmp     eax, 1
0x18003eb81  jz      short loc_18003EB8F
0x18003eb83  add     eax, 0FFFFFF9Ch
0x18003eb86  cmp     eax, 63h ; 'c'
0x18003eb89  ja      loc_18003ED9D
0x18003eb8f  lea     rax, [rbp+57h+var_98]
0x18003eb93  xor     r9d, r9d; lpType
0x18003eb96  mov     [rsp+0F0h+lpcbData], rax; lpcbData
0x18003eb9b  lea     rdx, aTolllist; "TollList"
0x18003eba2  xor     r8d, r8d; lpReserved
0x18003eba5  mov     [rsp+0F0h+lpData], rsi; lpData
0x18003ebaa  mov     rcx, rdi; hKey
0x18003ebad  call    cs:__imp_RegQueryValueExW
0x18003ebb3  mov     r14d, 40h ; '@'
0x18003ebb9  test    eax, eax
0x18003ebbb  jnz     loc_18003ECA8
0x18003ebc1  mov     edx, [rbp+57h+var_98]
0x18003ebc4  mov     ecx, r14d; uFlags
0x18003ebc7  add     rdx, 2; dwBytes
0x18003ebcb  call    cs:__imp_GlobalAlloc
0x18003ebd1  mov     r12, rax
0x18003ebd4  test    rax, rax
0x18003ebd7  jz      loc_18003ED96
0x18003ebdd  lea     rax, [rbp+57h+var_98]
0x18003ebe1  xor     r8d, r8d; lpReserved
0x18003ebe4  mov     [rsp+0F0h+lpcbData], rax; lpcbData
0x18003ebe9  lea     r9, [rbp+57h+Type]; lpType
0x18003ebed  lea     rdx, aTolllist; "TollList"
0x18003ebf4  mov     [rsp+0F0h+lpData], r12; lpData
0x18003ebf9  mov     rcx, rdi; hKey
0x18003ebfc  call    cs:__imp_RegQueryValueExW
0x18003ec02  mov     ebx, eax
0x18003ec04  test    eax, eax
0x18003ec06  jnz     loc_18003EDCF
0x18003ec0c  cmp     [rbp+57h+Type], 1
0x18003ec10  jnz     loc_18003EA27
0x18003ec16  movzx   eax, word ptr [r12]
0x18003ec1b  mov     rcx, r12
0x18003ec1e  jmp     short loc_18003EC2B
0x18003ec20  add     rcx, 2
0x18003ec24  add     [rbp+57h+var_98], 0FFFFFFFEh
0x18003ec28  movzx   eax, word ptr [rcx]
0x18003ec2b  cmp     ax, 2Ch ; ','
0x18003ec2f  jz      short loc_18003EC20
0x18003ec31  test    ax, ax
0x18003ec34  jz      short loc_18003ECA8
0x18003ec36  mov     r8, rcx
0x18003ec39  cmp     [rcx], si
0x18003ec3c  jz      short loc_18003EC70
0x18003ec3e  movzx   eax, word ptr [rcx]
0x18003ec41  cmp     ax, 2Ch ; ','
0x18003ec45  jz      short loc_18003EC53
0x18003ec47  add     rcx, 2
0x18003ec4b  movzx   eax, word ptr [rcx]
0x18003ec4e  test    ax, ax
0x18003ec51  jnz     short loc_18003EC41
0x18003ec53  lea     rdx, [rcx+2]
0x18003ec57  cmp     [rcx], si
0x18003ec5a  jnz     short loc_18003EC65
0x18003ec5c  mov     [rdx], si
0x18003ec5f  add     [rbp+57h+var_98], 2
0x18003ec63  jmp     short loc_18003EC68
0x18003ec65  mov     [rcx], si
0x18003ec68  mov     rcx, rdx
0x18003ec6b  cmp     [rdx], si
0x18003ec6e  jnz     short loc_18003EC3E
0x18003ec70  mov     eax, [rbp+57h+var_98]
0x18003ec73  lea     r9, a1_0; "1"
0x18003ec7a  mov     rcx, [rbp+57h+hKey]; hKey
0x18003ec7e  mov     edx, r15d
0x18003ec81  mov     dword ptr [rsp+0F0h+lpSecurityAttributes], 6; Data
0x18003ec89  mov     dword ptr [rsp+0F0h+lpcbData], eax; cbData
0x18003ec8d  mov     [rsp+0F0h+lpData], r8; lpData
0x18003ec92  lea     r8, [rbp+57h+var_80]
0x18003ec96  call    CreateAreaCodeRule
0x18003ec9b  mov     ebx, eax
0x18003ec9d  test    eax, eax
0x18003ec9f  jnz     loc_18003EDCF
0x18003eca5  inc     r15d
0x18003eca8  lea     rax, [rbp+57h+cbData]
0x18003ecac  xor     r9d, r9d; lpType
0x18003ecaf  mov     [rsp+0F0h+lpcbData], rax; lpcbData
0x18003ecb4  lea     rdx, aNoprefac; "NoPrefAC"
0x18003ecbb  xor     r8d, r8d; lpReserved
0x18003ecbe  mov     [rsp+0F0h+lpData], rsi; lpData
0x18003ecc3  mov     rcx, rdi; hKey
0x18003ecc6  call    cs:__imp_RegQueryValueExW
0x18003eccc  test    eax, eax
0x18003ecce  jnz     loc_18003ED9D
0x18003ecd4  mov     eax, [rbp+57h+cbData]
0x18003ecd7  test    eax, eax
0x18003ecd9  jz      loc_18003ED9D
0x18003ecdf  mov     edx, eax; dwBytes
0x18003ece1  mov     ecx, r14d; uFlags
0x18003ece4  call    cs:__imp_GlobalAlloc
0x18003ecea  mov     r13, rax
0x18003eced  test    rax, rax
0x18003ecf0  jz      loc_18003ED96
0x18003ecf6  lea     rax, [rbp+57h+cbData]
0x18003ecfa  xor     r8d, r8d; lpReserved
0x18003ecfd  mov     [rsp+0F0h+lpcbData], rax; lpcbData
0x18003ed02  lea     r9, [rbp+57h+Type]; lpType
0x18003ed06  lea     rdx, aNoprefac; "NoPrefAC"
0x18003ed0d  mov     [rsp+0F0h+lpData], r13; lpData
0x18003ed12  mov     rcx, rdi; hKey
0x18003ed15  call    cs:__imp_RegQueryValueExW
0x18003ed1b  mov     ebx, eax
0x18003ed1d  test    eax, eax
0x18003ed1f  jnz     loc_18003EDCF
0x18003ed25  cmp     [rbp+57h+Type], 3
0x18003ed29  jnz     loc_18003EA27
0x18003ed2f  mov     esi, [rbp+57h+cbData]
0x18003ed32  mov     r14, r13
0x18003ed35  shr     rsi, 2
0x18003ed39  test    rsi, rsi
0x18003ed3c  jz      short loc_18003ED9D
0x18003ed3e  mov     ecx, [r14]; Value
0x18003ed41  lea     rdx, [rbp+57h+Buffer]; Buffer
0x18003ed45  mov     r8d, 0Ah; Radix
0x18003ed4b  call    cs:__imp__itow
0x18003ed51  mov     rcx, [rbp+57h+hKey]; hKey
0x18003ed55  lea     rax, dword_18004C2D4
0x18003ed5c  mov     dword ptr [rsp+0F0h+lpSecurityAttributes], 3; Data
0x18003ed64  lea     r9, qword_18004C218
0x18003ed6b  mov     dword ptr [rsp+0F0h+lpcbData], 4; cbData
0x18003ed73  lea     r8, [rbp+57h+Buffer]
0x18003ed77  mov     edx, r15d
0x18003ed7a  mov     [rsp+0F0h+lpData], rax; lpData
0x18003ed7f  call    CreateAreaCodeRule
0x18003ed84  mov     ebx, eax
0x18003ed86  test    eax, eax
0x18003ed88  jnz     short loc_18003EDCF
0x18003ed8a  dec     rsi
0x18003ed8d  inc     r15d
0x18003ed90  add     r14, 4
0x18003ed94  jmp     short loc_18003ED39
0x18003ed96  mov     ebx, 0Eh
0x18003ed9b  jmp     short loc_18003EDCF
0x18003ed9d  lea     rdx, aTolllist; "TollList"
0x18003eda4  mov     rcx, rdi; hKey
0x18003eda7  mov     ebx, esi
0x18003eda9  call    cs:__imp_RegDeleteValueW
0x18003edaf  lea     rdx, aNoprefac; "NoPrefAC"
0x18003edb6  mov     rcx, rdi; hKey
0x18003edb9  call    cs:__imp_RegDeleteValueW
0x18003edbf  lea     rdx, aId; "ID"
0x18003edc6  mov     rcx, rdi; hKey
0x18003edc9  call    cs:__imp_RegDeleteValueW
0x18003edcf  mov     rcx, [rbp+57h+hKey]; hKey
0x18003edd3  test    rcx, rcx
0x18003edd6  jz      short loc_18003EDDE
0x18003edd8  call    cs:__imp_RegCloseKey
0x18003edde  test    r12, r12
0x18003ede1  jz      short loc_18003EDEC
0x18003ede3  mov     rcx, r12; hMem
0x18003ede6  call    cs:__imp_GlobalFree
0x18003edec  test    r13, r13
0x18003edef  jz      short loc_18003EDFA
0x18003edf1  mov     rcx, r13; hMem
0x18003edf4  call    cs:__imp_GlobalFree
0x18003edfa  mov     eax, ebx
0x18003edfc  mov     rcx, [rbp+57h+var_48]
0x18003ee00  xor     rcx, rsp; StackCookie
0x18003ee03  call    __security_check_cookie
0x18003ee08  add     rsp, 0B8h
0x18003ee0f  pop     r15
0x18003ee11  pop     r14
0x18003ee13  pop     r13
0x18003ee15  pop     r12
0x18003ee17  pop     rdi
0x18003ee18  pop     rsi
0x18003ee19  pop     rbx
0x18003ee1a  pop     rbp
0x18003ee1b  retn
```
