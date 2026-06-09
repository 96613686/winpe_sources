# CProtMgrNameSpace::LookupClsIDFromReg(ushort const *,_GUID *,ulong *,ulong *,ulong)

- ea: `0x1800197a0`
- end: `0x180019e05`
- name: `?LookupClsIDFromReg@CProtMgrNameSpace@@UEAAJPEBGPEAU_GUID@@PEAK2K@Z`
- size: `1637`
- prototype: `__int64 __fastcall(CProtMgrNameSpace *this, const unsigned __int16 *, struct _GUID *, unsigned int *)`
- caller_count: `8`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800151d0`
- `0x180016640`
- `0x180017620`
- `0x180018e90`
- `0x1800194d0`
- `0x180019f10`
- `0x18001a4d0`
- `0x1800265e0`

## callees

- `0x1800197a0`
- `0x18001ac8c`
- `0x18007f150`
- `0x180086ed0`
- `0x18011baa0`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18001985a`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18001986d`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18001985a`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18001986d`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrA` at `0x180019846`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrA` at `0x180019846`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001982f`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001982f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExA` at `0x180019cc8`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExA` at `0x180019cc8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800198f9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180019af4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180019d38`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800198f9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180019af4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180019d38`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180019d74`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180019d74`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019b38`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019daa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019dcc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019df0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019b38`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019daa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019dcc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019df0`

## string_xrefs

- `0x180019880`: `PROTOCOLS\Name-Space Handler\`
- `0x180019d6d`: `CLSID`

## pseudocode

```c
__int64 __fastcall CProtMgrNameSpace::LookupClsIDFromReg(
        CProtMgrNameSpace *this,
        const unsigned __int16 *a2,
        struct _GUID *a3,
        unsigned int *a4)
{
  DWORD v4; // r14d
  PSTR v8; // rax
  const CHAR *v9; // r8
  CHAR *v10; // rdx
  __int64 v11; // rcx
  unsigned int v12; // r12d
  __int64 v13; // rax
  __int64 v14; // r9
  CHAR *v15; // rax
  __int64 v16; // rbx
  CHAR *v18; // rdx
  int v19; // eax
  __int64 v20; // r15
  signed int v21; // ebx
  unsigned int v22; // r13d
  CHAR *v23; // r11
  __int64 v24; // rdi
  __int64 v25; // rcx
  CHAR *v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  CHAR *v29; // rcx
  CHAR *v30; // r8
  __int64 v31; // rdx
  __int64 v32; // r10
  __int64 v33; // rcx
  CHAR *v34; // rax
  __int64 v35; // rax
  CHAR *v36; // rcx
  __int64 v37; // rcx
  unsigned __int64 v38; // rdi
  char *v39; // rsi
  __int64 v40; // rax
  const CHAR *v41; // rcx
  unsigned __int64 v42; // rdx
  char *v43; // r8
  __int64 v44; // r10
  __int64 v45; // rcx
  char *v46; // rax
  HKEY v47; // rcx
  bool v48; // zf
  __int64 v49; // rcx
  CHAR *v50; // rax
  __int64 v51; // rax
  __int64 v52; // rax
  const char *v53; // rcx
  HKEY v54; // rcx
  unsigned int cbMultiByte; // [rsp+28h] [rbp-D8h]
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY v57; // [rsp+48h] [rbp-B8h] BYREF
  int v58; // [rsp+50h] [rbp-B0h]
  DWORD cbData; // [rsp+54h] [rbp-ACh] BYREF
  DWORD Type; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int64 v63; // [rsp+70h] [rbp-90h] BYREF
  char *i; // [rsp+78h] [rbp-88h] BYREF
  unsigned int *v65; // [rsp+80h] [rbp-80h]
  struct _GUID *v66; // [rsp+88h] [rbp-78h]
  CHAR *v67; // [rsp+90h] [rbp-70h]
  CHAR MultiByteStr[40]; // [rsp+98h] [rbp-68h] BYREF
  CHAR SubKey[256]; // [rsp+C0h] [rbp-40h] BYREF
  BYTE Data[256]; // [rsp+1C0h] [rbp+C0h] BYREF
  CHAR Name[256]; // [rsp+2C0h] [rbp+1C0h] BYREF

  v4 = 0;
  v65 = a4;
  v66 = a3;
  Type = 0;
  phkResult = 0;
  if ( a2 && a3 && a4 )
  {
    if ( !WideCharToMultiByte(0, 0, a2, -1, MultiByteStr, 32, 0, 0) )
      MultiByteStr[0] = 0;
    v8 = StrChrA(MultiByteStr, 0x3Au);
    if ( v8 )
      *v8 = 0;
    if ( (unsigned __int8)IEConfiguration_GetBool(268435481) || (unsigned __int8)IEConfiguration_GetBool(536870925) )
      return (unsigned int)GetKnownImmersiveNameSpaceClsID(a2, a3, a4);
    v9 = "PROTOCOLS\\Name-Space Handler\\";
    cchName = 256;
    v10 = SubKey;
    v11 = 256;
    v12 = -2146697203;
    v13 = 2147483646;
    v14 = 0;
    do
    {
      if ( !v13 )
        break;
      if ( !*v9 )
        break;
      *v10++ = *v9++;
      --v13;
      ++v14;
      --v11;
    }
    while ( v11 );
    v15 = v10 - 1;
    v16 = v14 - 1;
    if ( v11 )
    {
      v15 = v10;
      v16 = v14;
    }
    *v15 = 0;
    RegOpenKeyExA(HKEY_CLASSES_ROOT, SubKey, 0, 0x20019u, &phkResult);
    if ( !phkResult )
      return v12;
    v57 = 0;
    v18 = &SubKey[v16];
    v19 = 2;
    v67 = &SubKey[v16];
    v20 = 256 - v16;
    v58 = 2;
    v21 = 0;
    v22 = 0;
    while ( 1 )
    {
      *v18 = 0;
      v23 = v18;
      v24 = v20;
      if ( v19 != 2 )
        break;
      if ( (unsigned __int64)(v20 - 1) > 0x7FFFFFFE )
        goto LABEL_78;
      v25 = v20;
      v26 = v18;
      do
      {
        if ( !*v26 )
          break;
        ++v26;
        --v25;
      }
      while ( v25 );
      v21 = v25 == 0 ? 0x80070057 : 0;
      if ( v25 )
        v27 = v20 - v25;
      else
        v27 = 0;
      if ( v25 )
      {
        v24 = v20 - v27;
        v23 = &v18[v27];
        if ( (unsigned __int64)(v20 - v27) > 1 )
        {
          v28 = 2147483646;
          v29 = MultiByteStr;
          v30 = v23;
          v31 = v24;
          v32 = 0;
          do
          {
            if ( !v28 )
              break;
            if ( !*v29 )
              break;
            *v30++ = *v29++;
            --v28;
            ++v32;
            --v31;
          }
          while ( v31 );
LABEL_31:
          v33 = v32 - 1;
          v34 = v30 - 1;
          if ( v31 )
          {
            v34 = v30;
            v33 = v32;
          }
          v23 += v33;
          *v34 = 0;
          v21 = v31 == 0 ? 0x8007007A : 0;
          v24 -= v33;
          goto LABEL_34;
        }
        v21 = 0;
        if ( MultiByteStr[0] )
          goto LABEL_74;
      }
LABEL_34:
      if ( v21 >= 0 && (unsigned __int64)(v24 - 1) <= 0x7FFFFFFE )
      {
        v35 = v24;
        v36 = v23;
        do
        {
          if ( !*v36 )
          {
            v37 = v24 - v35;
            goto LABEL_39;
          }
          ++v36;
          --v35;
        }
        while ( v35 );
        v37 = 0;
LABEL_39:
        if ( v35 )
        {
          v38 = v24 - v37;
          v39 = &v23[v37];
          if ( v38 <= 1 )
          {
            if ( !v23 )
              goto LABEL_53;
            v21 = -2147024774;
          }
          else
          {
            v40 = 2147483646;
            v41 = "\\";
            v42 = v38;
            v43 = v39;
            v44 = 0;
            do
            {
              if ( !v40 )
                break;
              if ( !*v41 )
                break;
              *v43++ = *v41++;
              --v40;
              ++v44;
              --v42;
            }
            while ( v42 );
            v45 = v44 - 1;
            v46 = v43 - 1;
            if ( v42 )
            {
              v46 = v43;
              v45 = v44;
            }
            v39 += v45;
            *v46 = 0;
            v21 = v42 == 0 ? 0x8007007A : 0;
            v38 -= v45;
          }
          v63 = v38;
          if ( v21 >= 0 )
          {
            if ( RegOpenKeyExA(HKEY_CLASSES_ROOT, SubKey, 0, 0x20019u, &v57) )
            {
              v47 = 0;
              v57 = 0;
            }
            else
            {
              v47 = v57;
            }
            if ( v47 )
            {
              for ( i = v39; ; v39 = i )
              {
                cchName = 256;
                if ( RegEnumKeyExA(v47, v4, Name, &cchName, 0, 0, 0, 0) || v22 >= *v65 )
                  break;
                hKey = 0;
                *v39 = 0;
                v21 = StringCchCatExA(v39, v38, Name, &i, &v63, cbMultiByte);
                if ( v21 < 0 )
                {
                  RegCloseKey(v57);
                  v4 = 0;
                  v54 = 0;
                  v57 = 0;
                  goto LABEL_95;
                }
                if ( !RegOpenKeyExA(HKEY_CLASSES_ROOT, SubKey, 0, 1u, &hKey) )
                {
                  cbData = 256;
                  if ( !RegQueryValueExA(hKey, "CLSID", 0, &Type, Data, &cbData) )
                  {
                    Data[255] = 0;
                    v12 = CLSIDFromStringA((LPCCH)Data, &v66[v22]);
                    if ( !v12 )
                      ++v22;
                  }
                  RegCloseKey(hKey);
                }
                v47 = v57;
                ++v4;
                v38 = v63;
              }
              v54 = v57;
              v4 = 0;
LABEL_95:
              if ( v54 )
                RegCloseKey(v54);
            }
            v18 = v67;
            v48 = v58 == 1;
            v19 = --v58;
            if ( !v48 )
              continue;
          }
        }
      }
LABEL_53:
      RegCloseKey(phkResult);
      if ( v22 )
      {
        v12 = 0;
        *v65 = v22;
      }
      return v12;
    }
    if ( v19 != 1 )
      goto LABEL_34;
    if ( (unsigned __int64)(v20 - 1) <= 0x7FFFFFFE )
    {
      v49 = v20;
      v50 = v18;
      do
      {
        if ( !*v50 )
          break;
        ++v50;
        --v49;
      }
      while ( v49 );
      v21 = v49 == 0 ? 0x80070057 : 0;
      if ( v49 )
        v51 = v20 - v49;
      else
        v51 = 0;
      if ( !v49 )
        goto LABEL_34;
      v24 = v20 - v51;
      v23 = &v18[v51];
      if ( (unsigned __int64)(v20 - v51) > 1 )
      {
        v52 = 2147483646;
        v53 = "*";
        v30 = v23;
        v31 = v24;
        v32 = 0;
        do
        {
          if ( !v52 )
            break;
          if ( !*v53 )
            break;
          *v30++ = *v53++;
          --v52;
          ++v32;
          --v31;
        }
        while ( v31 );
        goto LABEL_31;
      }
LABEL_74:
      v21 = -2147024774;
      goto LABEL_34;
    }
LABEL_78:
    v21 = -2147024809;
    goto LABEL_34;
  }
  return 2148270093LL;
}

```

## disassembly

```asm
0x1800197a0  mov     [rsp-8+arg_0], rbx
0x1800197a5  push    rbp
0x1800197a6  push    rsi
0x1800197a7  push    rdi
0x1800197a8  push    r12
0x1800197aa  push    r13
0x1800197ac  push    r14
0x1800197ae  push    r15
0x1800197b0  lea     rbp, [rsp-2D0h]
0x1800197b8  sub     rsp, 3D0h
0x1800197bf  mov     rax, cs:__security_cookie
0x1800197c6  xor     rax, rsp
0x1800197c9  mov     [rbp+300h+var_40], rax
0x1800197d0  xor     r14d, r14d
0x1800197d3  mov     [rbp+300h+var_380], r9
0x1800197d7  mov     [rbp+300h+var_378], r8
0x1800197db  mov     rsi, r9
0x1800197de  mov     [rsp+400h+Type], r14d
0x1800197e3  mov     rdi, r8
0x1800197e6  mov     [rsp+400h+phkResult], r14
0x1800197eb  mov     rbx, rdx
0x1800197ee  test    rdx, rdx
0x1800197f1  jz      loc_180019DFB
0x1800197f7  test    r8, r8
0x1800197fa  jz      loc_180019DFB
0x180019800  test    r9, r9
0x180019803  jz      loc_180019DFB
0x180019809  mov     [rsp+400h+lpUsedDefaultChar], r14; lpUsedDefaultChar
0x18001980e  lea     rax, [rbp+300h+MultiByteStr]
0x180019812  mov     [rsp+400h+lpDefaultChar], r14; lpDefaultChar
0x180019817  mov     r8, rdx; lpWideCharStr
0x18001981a  mov     [rsp+400h+cbMultiByte], 20h ; ' '; cbMultiByte
0x180019822  or      r9d, 0FFFFFFFFh; cchWideChar
0x180019826  xor     edx, edx; dwFlags
0x180019828  mov     [rsp+400h+lpMultiByteStr], rax; lpMultiByteStr
0x18001982d  xor     ecx, ecx; CodePage
0x18001982f  call    cs:__imp_WideCharToMultiByte
0x180019835  test    eax, eax
0x180019837  jz      loc_180019933
0x18001983d  mov     edx, 3Ah ; ':'; wMatch
0x180019842  lea     rcx, [rbp+300h+MultiByteStr]; pszStart
0x180019846  call    cs:__imp_StrChrA
0x18001984c  test    rax, rax
0x18001984f  jnz     loc_180019C16
0x180019855  mov     ecx, 10000019h
0x18001985a  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180019860  test    al, al
0x180019862  jnz     loc_180019BF6
0x180019868  mov     ecx, 2000000Dh
0x18001986d  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180019873  test    al, al
0x180019875  jnz     loc_180019BF6
0x18001987b  mov     edi, 100h
0x180019880  lea     r8, aProtocolsNameS; "PROTOCOLS\\Name-Space Handler\\"
0x180019887  mov     [rsp+400h+cchName], edi
0x18001988b  lea     rdx, [rbp+300h+SubKey]
0x18001988f  mov     ecx, edi
0x180019891  mov     r12d, 800C000Dh
0x180019897  mov     eax, 7FFFFFFEh
0x18001989c  mov     r9, r14
0x18001989f  mov     esi, 1
0x1800198a4  test    rax, rax
0x1800198a7  jz      short loc_1800198C5
0x1800198a9  mov     r10b, [r8]
0x1800198ac  test    r10b, r10b
0x1800198af  jz      short loc_1800198C5
0x1800198b1  mov     [rdx], r10b
0x1800198b4  add     r8, rsi
0x1800198b7  add     rdx, rsi
0x1800198ba  sub     rax, rsi
0x1800198bd  add     r9, rsi
0x1800198c0  sub     rcx, rsi
0x1800198c3  jnz     short loc_1800198A4
0x1800198c5  test    rcx, rcx
0x1800198c8  lea     rax, [rdx-1]
0x1800198cc  lea     rbx, [r9-1]
0x1800198d0  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800198d7  cmovnz  rax, rdx
0x1800198db  cmovnz  rbx, r9
0x1800198df  mov     r9d, 20019h; samDesired
0x1800198e5  lea     rdx, [rbp+300h+SubKey]; lpSubKey
0x1800198e9  xor     r8d, r8d; ulOptions
0x1800198ec  mov     [rax], r14b
0x1800198ef  lea     rax, [rsp+400h+phkResult]
0x1800198f4  mov     [rsp+400h+lpMultiByteStr], rax; phkResult
0x1800198f9  call    cs:__imp_RegOpenKeyExA
0x1800198ff  cmp     [rsp+400h+phkResult], r14
0x180019904  jnz     short loc_18001993C
0x180019906  mov     eax, r12d
0x180019909  mov     rcx, [rbp+300h+var_40]
0x180019910  xor     rcx, rsp; StackCookie
0x180019913  call    __security_check_cookie
0x180019918  mov     rbx, [rsp+400h+arg_0]
0x180019920  add     rsp, 3D0h
0x180019927  pop     r15
0x180019929  pop     r14
0x18001992b  pop     r13
0x18001992d  pop     r12
0x18001992f  pop     rdi
0x180019930  pop     rsi
0x180019931  pop     rbp
0x180019932  retn
0x180019933  mov     [rbp+300h+MultiByteStr], r14b
0x180019937  jmp     loc_18001983D
0x18001993c  lea     rdx, [rbp+300h+SubKey]
0x180019940  mov     [rsp+400h+var_3B8], r14
0x180019945  add     rdx, rbx
0x180019948  mov     r15, rdi
0x18001994b  mov     eax, 2
0x180019950  mov     [rbp+300h+var_370], rdx
0x180019954  sub     r15, rbx
0x180019957  mov     [rsp+400h+var_3B0], eax
0x18001995b  mov     ebx, r14d
0x18001995e  mov     r13d, r14d
0x180019961  mov     r9d, 80070057h
0x180019967  mov     [rdx], r14b
0x18001996a  mov     r11, rdx
0x18001996d  mov     rdi, r15
0x180019970  cmp     eax, 2
0x180019973  jnz     loc_180019B56
0x180019979  lea     rax, [r15-1]
0x18001997d  mov     r8d, 7FFFFFFEh
0x180019983  cmp     rax, r8
0x180019986  ja      loc_180019C67
0x18001998c  mov     rcx, r15
0x18001998f  mov     rax, rdx
0x180019992  cmp     [rax], r14b
0x180019995  jnz     loc_180019C1E
0x18001999b  mov     rax, rcx
0x18001999e  neg     rax
0x1800199a1  sbb     ebx, ebx
0x1800199a3  not     ebx
0x1800199a5  and     ebx, r9d
0x1800199a8  test    rcx, rcx
0x1800199ab  jz      loc_180019C2F
0x1800199b1  mov     rax, r15
0x1800199b4  sub     rax, rcx
0x1800199b7  test    rcx, rcx
0x1800199ba  jz      short loc_180019A26
0x1800199bc  sub     rdi, rax
0x1800199bf  lea     r11, [rdx+rax]
0x1800199c3  cmp     rdi, rsi
0x1800199c6  jbe     loc_180019C37
0x1800199cc  mov     rax, r8
0x1800199cf  lea     rcx, [rbp+300h+MultiByteStr]
0x1800199d3  mov     r8, r11
0x1800199d6  mov     rdx, rdi
0x1800199d9  mov     r10, r14
0x1800199dc  test    rax, rax
0x1800199df  jz      short loc_1800199FD
0x1800199e1  mov     r9b, [rcx]
0x1800199e4  test    r9b, r9b
0x1800199e7  jz      short loc_1800199FD
0x1800199e9  mov     [r8], r9b
0x1800199ec  add     rcx, rsi
0x1800199ef  add     r8, rsi
0x1800199f2  sub     rax, rsi
0x1800199f5  add     r10, rsi
0x1800199f8  sub     rdx, rsi
0x1800199fb  jnz     short loc_1800199DC
0x1800199fd  test    rdx, rdx
0x180019a00  lea     rcx, [r10-1]
0x180019a04  lea     rax, [r8-1]
0x180019a08  cmovnz  rax, r8
0x180019a0c  cmovnz  rcx, r10
0x180019a10  neg     rdx
0x180019a13  sbb     ebx, ebx
0x180019a15  add     r11, rcx
0x180019a18  not     ebx
0x180019a1a  mov     [rax], r14b
0x180019a1d  and     ebx, 8007007Ah
0x180019a23  sub     rdi, rcx
0x180019a26  test    ebx, ebx
0x180019a28  js      loc_180019B33
0x180019a2e  lea     rax, [rdi-1]
0x180019a32  mov     edx, 7FFFFFFEh
0x180019a37  cmp     rax, rdx
0x180019a3a  ja      loc_180019B33
0x180019a40  mov     rax, rdi
0x180019a43  mov     rcx, r11
0x180019a46  cmp     [rcx], r14b
0x180019a49  jnz     loc_180019C6F
0x180019a4f  mov     rcx, rdi
0x180019a52  sub     rcx, rax
0x180019a55  test    rax, rax
0x180019a58  jz      loc_180019B33
0x180019a5e  sub     rdi, rcx
0x180019a61  lea     rsi, [rcx+r11]
0x180019a65  cmp     rdi, 1
0x180019a69  jbe     loc_180019C83
0x180019a6f  mov     rax, rdx
0x180019a72  lea     rcx, asc_18012AFD0; "\\"
0x180019a79  mov     rdx, rdi
0x180019a7c  mov     r8, rsi
0x180019a7f  mov     r10, r14
0x180019a82  test    rax, rax
0x180019a85  jz      short loc_180019AA4
0x180019a87  mov     r9b, [rcx]
0x180019a8a  test    r9b, r9b
0x180019a8d  jz      short loc_180019AA4
0x180019a8f  mov     [r8], r9b
0x180019a92  inc     rcx
0x180019a95  inc     r8
0x180019a98  dec     rax
0x180019a9b  inc     r10
0x180019a9e  sub     rdx, 1
0x180019aa2  jnz     short loc_180019A82
0x180019aa4  test    rdx, rdx
0x180019aa7  lea     rcx, [r10-1]
0x180019aab  lea     rax, [r8-1]
0x180019aaf  cmovnz  rax, r8
0x180019ab3  cmovnz  rcx, r10
0x180019ab7  neg     rdx
0x180019aba  sbb     ebx, ebx
0x180019abc  add     rsi, rcx
0x180019abf  not     ebx
0x180019ac1  mov     [rax], r14b
0x180019ac4  and     ebx, 8007007Ah
0x180019aca  sub     rdi, rcx
0x180019acd  mov     [rsp+400h+var_390], rdi
0x180019ad2  test    ebx, ebx
0x180019ad4  js      short loc_180019B33
0x180019ad6  lea     rax, [rsp+400h+var_3B8]
0x180019adb  mov     r9d, 20019h; samDesired
0x180019ae1  xor     r8d, r8d; ulOptions
0x180019ae4  mov     [rsp+400h+lpMultiByteStr], rax; phkResult
0x180019ae9  lea     rdx, [rbp+300h+SubKey]; lpSubKey
0x180019aed  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180019af4  call    cs:__imp_RegOpenKeyExA
0x180019afa  test    eax, eax
0x180019afc  jz      loc_180019C0C
0x180019b02  mov     rcx, r14; hKey
0x180019b05  mov     [rsp+400h+var_3B8], rcx
0x180019b0a  test    rcx, rcx
0x180019b0d  jnz     loc_180019C96
0x180019b13  mov     eax, [rsp+400h+var_3B0]
0x180019b17  mov     esi, 1
0x180019b1c  mov     rdx, [rbp+300h+var_370]
0x180019b20  add     eax, 0FFFFFFFFh
0x180019b23  mov     [rsp+400h+var_3B0], eax
0x180019b27  mov     r9d, 80070057h
0x180019b2d  jnz     loc_180019967
0x180019b33  mov     rcx, [rsp+400h+phkResult]; hKey
0x180019b38  call    cs:__imp_RegCloseKey
0x180019b3e  test    r13d, r13d
0x180019b41  jz      loc_180019906
0x180019b47  mov     rax, [rbp+300h+var_380]
0x180019b4b  mov     r12d, r14d
0x180019b4e  mov     [rax], r13d
0x180019b51  jmp     loc_180019906
0x180019b56  cmp     eax, esi
0x180019b58  jnz     loc_180019A26
0x180019b5e  lea     rax, [r15-1]
0x180019b62  mov     r8d, 7FFFFFFEh
0x180019b68  cmp     rax, r8
0x180019b6b  ja      loc_180019C67
0x180019b71  mov     rcx, r15
0x180019b74  mov     rax, rdx
0x180019b77  cmp     [rax], r14b
0x180019b7a  jnz     loc_180019C4E
0x180019b80  mov     rax, rcx
0x180019b83  neg     rax
0x180019b86  sbb     ebx, ebx
0x180019b88  not     ebx
0x180019b8a  and     ebx, r9d
0x180019b8d  test    rcx, rcx
0x180019b90  jz      loc_180019C5F
0x180019b96  mov     rax, r15
0x180019b99  sub     rax, rcx
0x180019b9c  test    rcx, rcx
0x180019b9f  jz      loc_180019A26
0x180019ba5  sub     rdi, rax
0x180019ba8  lea     r11, [rdx+rax]
0x180019bac  cmp     rdi, rsi
0x180019baf  jbe     loc_180019C44
0x180019bb5  mov     rax, r8
0x180019bb8  lea     rcx, asc_18012AFD4; "*"
0x180019bbf  mov     r8, r11
0x180019bc2  mov     rdx, rdi
0x180019bc5  mov     r10, r14
0x180019bc8  test    rax, rax
0x180019bcb  jz      loc_1800199FD
0x180019bd1  mov     r9b, [rcx]
0x180019bd4  test    r9b, r9b
0x180019bd7  jz      loc_1800199FD
0x180019bdd  mov     [r8], r9b
0x180019be0  add     rcx, rsi
0x180019be3  add     r8, rsi
0x180019be6  sub     rax, rsi
0x180019be9  add     r10, rsi
0x180019bec  sub     rdx, rsi
0x180019bef  jnz     short loc_180019BC8
0x180019bf1  jmp     loc_1800199FD
0x180019bf6  mov     r8, rsi; unsigned int *
0x180019bf9  mov     rdx, rdi; struct _GUID *
0x180019bfc  mov     rcx, rbx; unsigned __int16 *
0x180019bff  call    ?GetKnownImmersiveNameSpaceClsID@@YAJPEBGPEAU_GUID@@PEAK@Z; GetKnownImmersiveNameSpaceClsID(ushort const *,_GUID *,ulong *)
0x180019c04  mov     r12d, eax
0x180019c07  jmp     loc_180019906
0x180019c0c  mov     rcx, [rsp+400h+var_3B8]
  ... truncated ...
```
