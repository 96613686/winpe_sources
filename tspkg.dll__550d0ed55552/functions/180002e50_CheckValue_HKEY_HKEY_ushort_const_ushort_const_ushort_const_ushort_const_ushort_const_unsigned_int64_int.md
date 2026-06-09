# CheckValue(HKEY__ *,HKEY__ *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,unsigned __int64,int *)

- ea: `0x180002e50`
- end: `0x1800032b5`
- name: `?CheckValue@@YAJPEAUHKEY__@@0PEBG1111_KPEAH@Z`
- size: `1125`
- prototype: `__int64 __fastcall(HKEY, HKEY hKey, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int64, int *)`
- caller_count: `3`
- callee_count: `12`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800021b4`
- `0x1800022e0`
- `0x180002570`

## callees

- `0x180002e50`
- `0x180007c40`
- `0x1800090e0`
- `0x18000a208`
- `0x18000b550`
- `0x18000b92c`
- `0x18000bde4`
- `0x18000c180`
- `0x18000c18c`
- `0x18001b9ac`
- `0x18001ba34`
- `0x18001bbdc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003284`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003294`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003284`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003294`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800030fe`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800030fe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002f28`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003077`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002f28`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003077`
- `LSASRV!LsaIFree_LSAPR_POLICY_INFORMATION` at `0x180002fd9`
- `LSASRV!LsaIFree_LSAPR_POLICY_INFORMATION` at `0x180002fe3`
- `LSASRV!LsaIFree_LSAPR_POLICY_INFORMATION` at `0x180002fd9`
- `LSASRV!LsaIFree_LSAPR_POLICY_INFORMATION` at `0x180002fe3`
- `LSASRV!LsaIQueryInformationPolicyTrusted` at `0x180002fb9`
- `LSASRV!LsaIQueryInformationPolicyTrusted` at `0x180002fb9`

## pseudocode

```c
__int64 __fastcall CheckValue(
        HKEY a1,
        HKEY hKey,
        wchar_t *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        const unsigned __int16 *a6,
        wchar_t *a7,
        unsigned __int64 a8,
        int *a9)
{
  wchar_t *v12; // r14
  int v14; // ebx
  LSTATUS v15; // eax
  int v16; // ebx
  BOOL v17; // edi
  unsigned __int64 v18; // rdx
  __int64 v19; // rdi
  LSTATUS v20; // eax
  HKEY v21; // rbx
  BYTE *lpData; // rdi
  unsigned __int64 v23; // r15
  LSTATUS v24; // ecx
  wchar_t *v25; // r14
  unsigned int v26; // r14d
  int v27; // eax
  unsigned int NextValue; // eax
  DWORD Type[2]; // [rsp+48h] [rbp-C0h] BYREF
  DWORD cchValueName[2]; // [rsp+50h] [rbp-B8h] BYREF
  wchar_t *String2; // [rsp+58h] [rbp-B0h]
  HKEY phkResult; // [rsp+60h] [rbp-A8h] BYREF
  HKEY hKeya; // [rsp+68h] [rbp-A0h] BYREF
  unsigned __int64 v35; // [rsp+70h] [rbp-98h] BYREF
  wchar_t Destination[256]; // [rsp+78h] [rbp-90h] BYREF
  WCHAR ValueName[256]; // [rsp+278h] [rbp+170h] BYREF

  *(_QWORD *)cchValueName = a6;
  v12 = a3;
  String2 = a7;
  *a9 = 0;
  v35 = 0;
  phkResult = 0;
  hKeya = 0;
  Type[0] = 0;
  Type[1] = 0;
  if ( a1 && a3 )
  {
    v14 = IsPolicyDisabled(a1, a3, (int *)Type);
    if ( v14 < 0 )
      goto LABEL_61;
    if ( Type[0] )
      goto LABEL_60;
    v15 = RegOpenKeyExW(a1, v12, 0, 0x20019u, &phkResult);
    v14 = v15;
    if ( v15 != 2 )
    {
      if ( v15 > 0 )
        v14 = (unsigned __int16)v15 | 0x80070000;
      if ( v14 < 0 )
        goto LABEL_61;
      v14 = QueryForMatch(phkResult, String2, a8, a9);
      if ( v14 < 0 )
        goto LABEL_61;
      if ( *a9 )
        goto LABEL_61;
      if ( !*(_QWORD *)cchValueName )
        goto LABEL_61;
      v14 = CheckConcatDefault(a1, *(const unsigned __int16 **)cchValueName, (int *)&Type[1]);
      if ( v14 < 0 || !Type[1] )
        goto LABEL_61;
    }
  }
  *(_QWORD *)cchValueName = 0;
  v16 = LsaIQueryInformationPolicyTrusted(12, cchValueName);
  if ( v16 < 0 )
  {
    LsaIFree_LSAPR_POLICY_INFORMATION(12, *(_QWORD *)cchValueName);
    v17 = 0;
    v14 = v16 | 0x10000000;
    if ( v14 < 0 )
      goto LABEL_61;
  }
  else
  {
    v17 = *(_QWORD *)(*(_QWORD *)cchValueName + 64LL) != 0;
    LsaIFree_LSAPR_POLICY_INFORMATION(12, *(_QWORD *)cchValueName);
    v14 = 0;
  }
  if ( !v17 )
    a5 = a4;
  if ( hKey && v12 )
  {
    if ( v17 )
    {
      v19 = -1;
      do
        ++v19;
      while ( v12[v19] );
      o_wcsncpy_s_0(Destination, 256, v12, v19);
      wcsncat_s(Destination, 256 - v19, L"Domain", 6u);
      v12 = Destination;
    }
    v20 = RegOpenKeyExW(hKey, v12, 0, 0x20019u, &hKeya);
    if ( !v20 )
    {
      v21 = hKeya;
      lpData = (BYTE *)operator new(0x800u, (const struct std::nothrow_t *)&std::nothrow);
      if ( !lpData )
      {
        v14 = -2147024882;
        goto LABEL_61;
      }
      cchValueName[0] = 256;
      Type[1] = 0;
      v23 = 1024;
      Type[0] = 2046;
      v24 = RegEnumValueW(v21, 0, ValueName, cchValueName, 0, &Type[1], lpData, Type);
      if ( v24 )
        goto LABEL_33;
      if ( Type[1] != 1 || (unsigned __int64)Type[0] >> 1 >= 0x400 )
      {
        v24 = 13;
        goto LABEL_37;
      }
      v23 = (unsigned __int64)Type[0] >> 1;
      *(_WORD *)&lpData[2 * v23] = 0;
      if ( !v23 )
      {
LABEL_33:
        if ( v24 )
          goto LABEL_37;
      }
      else
      {
        --v23;
      }
      v25 = String2;
      if ( !String2 )
      {
        *a9 = 1;
        operator delete(lpData);
        v14 = 0;
LABEL_48:
        if ( *a9 )
          goto LABEL_61;
        goto LABEL_55;
      }
LABEL_37:
      v26 = 0;
      while ( !v24 )
      {
        v27 = CompareValue(String2, a8, (const unsigned __int16 *)lpData, v23);
        *a9 = v27;
        if ( v27 )
        {
          operator delete(lpData);
          v14 = 0;
LABEL_47:
          v25 = String2;
          goto LABEL_48;
        }
        ++v26;
        *(_QWORD *)cchValueName = 1024;
        NextValue = GetNextValue(v21, v26, (unsigned __int16 *)lpData, (unsigned __int64 *)cchValueName);
        v23 = *(_QWORD *)cchValueName;
        v24 = NextValue;
      }
      v14 = 0;
      if ( v24 != 259 )
        v14 = v24;
      if ( v14 > 0 )
        v14 = (unsigned __int16)v14 | 0x80070000;
      operator delete(lpData);
      if ( v14 >= 0 )
        goto LABEL_47;
      goto LABEL_61;
    }
    if ( v20 != 2 )
    {
      if ( v20 > 0 )
        v14 = (unsigned __int16)v20 | 0x80070000;
      else
        v14 = v20;
      goto LABEL_61;
    }
  }
  v25 = String2;
LABEL_55:
  if ( !a5 )
  {
LABEL_60:
    v14 = 0;
    goto LABEL_61;
  }
  if ( !v25 )
  {
    *a9 = 1;
    goto LABEL_61;
  }
  v14 = StringCchLengthW(a5, v18, &v35);
  if ( v14 >= 0 )
  {
    *a9 = CompareValue(v25, a8, a5, v35);
    goto LABEL_60;
  }
LABEL_61:
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKeya )
    RegCloseKey(hKeya);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180002e50  mov     r11, rsp
0x180002e53  push    rbp
0x180002e54  push    rbx
0x180002e55  lea     rbp, [r11-3C8h]
0x180002e5c  sub     rsp, 4B8h
0x180002e63  mov     rax, cs:__security_cookie
0x180002e6a  xor     rax, rsp
0x180002e6d  mov     [rbp+3C0h+var_50], rax
0x180002e74  mov     rax, [rbp+3C0h+arg_28]
0x180002e7b  mov     [r11-18h], rsi
0x180002e7f  mov     rsi, [rbp+3C0h+arg_20]
0x180002e86  mov     [r11-20h], rdi
0x180002e8a  mov     rdi, rcx
0x180002e8d  mov     [r11-28h], r12
0x180002e91  mov     r12, r9
0x180002e94  mov     [r11-30h], r13
0x180002e98  mov     r13, [rbp+3C0h+arg_40]
0x180002e9f  mov     qword ptr [rsp+4C0h+cchValueName], rax
0x180002ea4  mov     rax, [rbp+3C0h+arg_30]
0x180002eab  mov     [r11-38h], r14
0x180002eaf  mov     r14, r8
0x180002eb2  mov     [rsp+4C0h+String2], rax
0x180002eb7  xor     eax, eax
0x180002eb9  mov     [r11-40h], r15
0x180002ebd  mov     r15, rdx
0x180002ec0  mov     [r13+0], eax
0x180002ec4  mov     [rsp+4C0h+var_458], rax
0x180002ec9  mov     [rsp+4C0h+var_468], rax
0x180002ece  mov     [rsp+4C0h+hKey], rax
0x180002ed3  mov     [rsp+4C0h+Type], eax
0x180002ed7  mov     [rsp+4C0h+Type+4], eax
0x180002edb  test    rcx, rcx
0x180002ede  jz      loc_180002FAA
0x180002ee4  test    r8, r8
0x180002ee7  jz      loc_180002FAA
0x180002eed  lea     r8, [rsp+4C0h+Type]; int *
0x180002ef2  mov     rdx, r14; unsigned __int16 *
0x180002ef5  call    ?IsPolicyDisabled@@YAJPEAUHKEY__@@PEBGPEAH@Z; IsPolicyDisabled(HKEY__ *,ushort const *,int *)
0x180002efa  mov     ebx, eax
0x180002efc  test    eax, eax
0x180002efe  js      loc_18000324A
0x180002f04  cmp     [rsp+4C0h+Type], 0
0x180002f09  jnz     loc_180003248
0x180002f0f  lea     rax, [rsp+4C0h+var_468]
0x180002f14  mov     r9d, 20019h; samDesired
0x180002f1a  xor     r8d, r8d; ulOptions
0x180002f1d  mov     [rsp+4C0h+phkResult], rax; phkResult
0x180002f22  mov     rdx, r14; lpSubKey
0x180002f25  mov     rcx, rdi; hKey
0x180002f28  call    cs:__imp_RegOpenKeyExW
0x180002f2e  mov     ebx, eax
0x180002f30  cmp     eax, 2
0x180002f33  jz      short loc_180002FA8
0x180002f35  test    eax, eax
0x180002f37  jle     short loc_180002F42
0x180002f39  movzx   ebx, ax
0x180002f3c  or      ebx, 80070000h
0x180002f42  test    ebx, ebx
0x180002f44  js      loc_18000324A
0x180002f4a  mov     r8, [rbp+3C0h+arg_38]; unsigned __int64
0x180002f51  mov     r9, r13; int *
0x180002f54  mov     rdx, [rsp+4C0h+String2]; String2
0x180002f59  mov     rcx, [rsp+4C0h+var_468]; HKEY
0x180002f5e  call    ?QueryForMatch@@YAJPEAUHKEY__@@PEBG_KPEAH@Z; QueryForMatch(HKEY__ *,ushort const *,unsigned __int64,int *)
0x180002f63  mov     ebx, eax
0x180002f65  test    eax, eax
0x180002f67  js      loc_18000324A
0x180002f6d  cmp     dword ptr [r13+0], 0
0x180002f72  jnz     loc_18000324A
0x180002f78  mov     rdx, qword ptr [rsp+4C0h+cchValueName]; unsigned __int16 *
0x180002f7d  test    rdx, rdx
0x180002f80  jz      loc_18000324A
0x180002f86  lea     r8, [rsp+4C0h+Type+4]; int *
0x180002f8b  mov     rcx, rdi; HKEY
0x180002f8e  call    ?CheckConcatDefault@@YAJPEAUHKEY__@@PEBGPEAH@Z; CheckConcatDefault(HKEY__ *,ushort const *,int *)
0x180002f93  mov     ebx, eax
0x180002f95  test    eax, eax
0x180002f97  js      loc_18000324A
0x180002f9d  cmp     [rsp+4C0h+Type+4], 0
0x180002fa2  jz      loc_18000324A
0x180002fa8  xor     eax, eax
0x180002faa  lea     rdx, [rsp+4C0h+cchValueName]
0x180002faf  mov     qword ptr [rsp+4C0h+cchValueName], rax
0x180002fb4  mov     ecx, 0Ch
0x180002fb9  call    cs:__imp_LsaIQueryInformationPolicyTrusted
0x180002fbf  mov     ebx, eax
0x180002fc1  mov     rdx, qword ptr [rsp+4C0h+cchValueName]
0x180002fc6  mov     ecx, 0Ch
0x180002fcb  test    eax, eax
0x180002fcd  js      short loc_180002FE3
0x180002fcf  xor     edi, edi
0x180002fd1  cmp     [rdx+40h], rdi
0x180002fd5  setnz   dil
0x180002fd9  call    cs:__imp_LsaIFree_LSAPR_POLICY_INFORMATION
0x180002fdf  xor     ebx, ebx
0x180002fe1  jmp     short loc_180002FF7
0x180002fe3  call    cs:__imp_LsaIFree_LSAPR_POLICY_INFORMATION
0x180002fe9  xor     edi, edi
0x180002feb  or      ebx, 10000000h
0x180002ff1  js      loc_18000324A
0x180002ff7  test    edi, edi
0x180002ff9  cmovz   rsi, r12
0x180002ffd  test    r15, r15
0x180003000  jz      loc_180003201
0x180003006  test    r14, r14
0x180003009  jz      loc_180003201
0x18000300f  test    edi, edi
0x180003011  jz      short loc_18000305E
0x180003013  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18000301a  inc     rdi
0x18000301d  cmp     word ptr [r14+rdi*2], 0
0x180003023  jnz     short loc_18000301A
0x180003025  mov     r9, rdi
0x180003028  lea     rcx, [rsp+4C0h+Destination]
0x18000302d  mov     r8, r14
0x180003030  mov     edx, 100h
0x180003035  call    _o_wcsncpy_s_0
0x18000303a  mov     edx, 100h
0x18000303f  lea     r8, aDomain; "Domain"
0x180003046  sub     rdx, rdi; SizeInWords
0x180003049  lea     rcx, [rsp+4C0h+Destination]; Destination
0x18000304e  mov     r9d, 6; MaxCount
0x180003054  call    wcsncat_s
0x180003059  lea     r14, [rsp+4C0h+Destination]
0x18000305e  lea     rax, [rsp+4C0h+hKey]
0x180003063  mov     r9d, 20019h; samDesired
0x180003069  xor     r8d, r8d; ulOptions
0x18000306c  mov     [rsp+4C0h+phkResult], rax; phkResult
0x180003071  mov     rdx, r14; lpSubKey
0x180003074  mov     rcx, r15; hKey
0x180003077  call    cs:__imp_RegOpenKeyExW
0x18000307d  test    eax, eax
0x18000307f  jnz     loc_1800031E7
0x180003085  mov     rbx, [rsp+4C0h+hKey]
0x18000308a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180003091  mov     ecx, 800h; unsigned __int64
0x180003096  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000309b  mov     rdi, rax
0x18000309e  test    rax, rax
0x1800030a1  jnz     short loc_1800030AD
0x1800030a3  mov     ebx, 8007000Eh
0x1800030a8  jmp     loc_18000324A
0x1800030ad  lea     rax, [rsp+4C0h+Type]
0x1800030b2  mov     [rsp+4C0h+cchValueName], 100h
0x1800030ba  mov     [rsp+4C0h+lpcbData], rax; lpcbData
0x1800030bf  lea     r9, [rsp+4C0h+cchValueName]; lpcchValueName
0x1800030c4  lea     rax, [rsp+4C0h+Type+4]
0x1800030c9  mov     [rsp+4C0h+lpData], rdi; lpData
0x1800030ce  mov     [rsp+4C0h+lpType], rax; lpType
0x1800030d3  lea     r8, [rbp+3C0h+ValueName]; lpValueName
0x1800030da  xor     edx, edx; dwIndex
0x1800030dc  mov     [rsp+4C0h+phkResult], 0; lpReserved
0x1800030e5  mov     rcx, rbx; hKey
0x1800030e8  mov     [rsp+4C0h+Type+4], 0
0x1800030f0  mov     r15d, 400h
0x1800030f6  mov     [rsp+4C0h+Type], 7FEh
0x1800030fe  call    cs:__imp_RegEnumValueW
0x180003104  mov     ecx, eax
0x180003106  test    eax, eax
0x180003108  jnz     short loc_180003131
0x18000310a  cmp     [rsp+4C0h+Type+4], 1
0x18000310f  jnz     short loc_180003156
0x180003111  mov     eax, [rsp+4C0h+Type]
0x180003115  shr     rax, 1
0x180003118  cmp     rax, r15
0x18000311b  jnb     short loc_180003156
0x18000311d  mov     r15, rax
0x180003120  xor     eax, eax
0x180003122  mov     [rdi+r15*2], ax
0x180003127  test    r15, r15
0x18000312a  jz      short loc_180003131
0x18000312c  dec     r15
0x18000312f  jmp     short loc_180003135
0x180003131  test    ecx, ecx
0x180003133  jnz     short loc_18000315B
0x180003135  mov     r14, [rsp+4C0h+String2]
0x18000313a  test    r14, r14
0x18000313d  jnz     short loc_18000315B
0x18000313f  mov     rcx, rdi; Block
0x180003142  mov     dword ptr [r13+0], 1
0x18000314a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000314f  xor     ebx, ebx
0x180003151  jmp     loc_1800031DE
0x180003156  mov     ecx, 0Dh
0x18000315b  xor     r14d, r14d
0x18000315e  test    ecx, ecx
0x180003160  jnz     short loc_1800031B5
0x180003162  mov     rdx, [rbp+3C0h+arg_38]; unsigned __int64
0x180003169  mov     r9, r15; unsigned __int64
0x18000316c  mov     rcx, [rsp+4C0h+String2]; String2
0x180003171  mov     r8, rdi; unsigned __int16 *
0x180003174  call    ?CompareValue@@YAHPEBG_K01@Z; CompareValue(ushort const *,unsigned __int64,ushort const *,unsigned __int64)
0x180003179  mov     [r13+0], eax
0x18000317d  test    eax, eax
0x18000317f  jnz     short loc_1800031A9
0x180003181  inc     r14d
0x180003184  mov     qword ptr [rsp+4C0h+cchValueName], 400h
0x18000318d  mov     edx, r14d; unsigned int
0x180003190  lea     r9, [rsp+4C0h+cchValueName]; unsigned __int64 *
0x180003195  mov     r8, rdi; unsigned __int16 *
0x180003198  mov     rcx, rbx; HKEY
0x18000319b  call    ?GetNextValue@@YAKPEAUHKEY__@@KPEAGPEA_K@Z; GetNextValue(HKEY__ *,ulong,ushort *,unsigned __int64 *)
0x1800031a0  mov     r15, qword ptr [rsp+4C0h+cchValueName]
0x1800031a5  mov     ecx, eax
0x1800031a7  jmp     short loc_18000315E
0x1800031a9  mov     rcx, rdi; Block
0x1800031ac  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800031b1  xor     ebx, ebx
0x1800031b3  jmp     short loc_1800031D9
0x1800031b5  xor     ebx, ebx
0x1800031b7  cmp     ecx, 103h
0x1800031bd  cmovnz  ebx, ecx
0x1800031c0  test    ebx, ebx
0x1800031c2  jle     short loc_1800031CD
0x1800031c4  movzx   ebx, bx
0x1800031c7  or      ebx, 80070000h
0x1800031cd  mov     rcx, rdi; Block
0x1800031d0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800031d5  test    ebx, ebx
0x1800031d7  js      short loc_18000324A
0x1800031d9  mov     r14, [rsp+4C0h+String2]
0x1800031de  cmp     dword ptr [r13+0], 0
0x1800031e3  jz      short loc_180003206
0x1800031e5  jmp     short loc_18000324A
0x1800031e7  cmp     eax, 2
0x1800031ea  jz      short loc_180003201
0x1800031ec  test    eax, eax
0x1800031ee  jg      short loc_1800031F4
0x1800031f0  mov     ebx, eax
0x1800031f2  jmp     short loc_1800031FD
0x1800031f4  movzx   ebx, ax
0x1800031f7  or      ebx, 80070000h
0x1800031fd  test    ebx, ebx
0x1800031ff  js      short loc_18000324A
0x180003201  mov     r14, [rsp+4C0h+String2]
0x180003206  test    rsi, rsi
0x180003209  jz      short loc_180003248
0x18000320b  test    r14, r14
0x18000320e  jnz     short loc_18000321A
0x180003210  mov     dword ptr [r13+0], 1
0x180003218  jmp     short loc_18000324A
0x18000321a  lea     r8, [rsp+4C0h+var_458]; unsigned __int64 *
0x18000321f  mov     rcx, rsi; unsigned __int16 *
0x180003222  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180003227  mov     ebx, eax
0x180003229  test    eax, eax
0x18000322b  js      short loc_18000324A
0x18000322d  mov     r9, [rsp+4C0h+var_458]; unsigned __int64
0x180003232  mov     r8, rsi; unsigned __int16 *
0x180003235  mov     rdx, [rbp+3C0h+arg_38]; unsigned __int64
0x18000323c  mov     rcx, r14; String2
0x18000323f  call    ?CompareValue@@YAHPEBG_K01@Z; CompareValue(ushort const *,unsigned __int64,ushort const *,unsigned __int64)
0x180003244  mov     [r13+0], eax
0x180003248  xor     ebx, ebx
0x18000324a  mov     rcx, [rsp+4C0h+var_468]; hKey
0x18000324f  mov     r15, [rsp+4C0h+var_38]
0x180003257  mov     r14, [rsp+4C0h+var_30]
0x18000325f  mov     r13, [rsp+4C0h+var_28]
0x180003267  mov     r12, [rsp+4C0h+var_20]
0x18000326f  mov     rdi, [rsp+4C0h+var_18]
0x180003277  mov     rsi, [rsp+4B0h]
0x18000327f  test    rcx, rcx
0x180003282  jz      short loc_18000328A
0x180003284  call    cs:__imp_RegCloseKey
0x18000328a  mov     rcx, [rsp+4C0h+hKey]; hKey
0x18000328f  test    rcx, rcx
0x180003292  jz      short loc_18000329A
0x180003294  call    cs:__imp_RegCloseKey
0x18000329a  mov     eax, ebx
0x18000329c  mov     rcx, [rbp+3C0h+var_50]
0x1800032a3  xor     rcx, rsp; StackCookie
0x1800032a6  call    __security_check_cookie
0x1800032ab  add     rsp, 4B8h
0x1800032b2  pop     rbx
0x1800032b3  pop     rbp
0x1800032b4  retn
```
