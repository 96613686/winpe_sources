# CProtMgrNameSpace::LookupClsIDFromReg(ushort const *,_GUID *,ulong *,ulong *,ulong)

- ea: `0x1800490d0`
- end: `0x180049784`
- name: `?LookupClsIDFromReg@CProtMgrNameSpace@@UEAAJPEBGPEAU_GUID@@PEAK2K@Z`
- size: `1716`
- prototype: `int(CProtMgrNameSpace *__hidden this, const unsigned __int16 *, struct _GUID *, unsigned int *, unsigned int *, unsigned int)`
- caller_count: `8`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001d540`
- `0x18001eaa0`
- `0x18001fca0`
- `0x18002d6a0`
- `0x180047af0`
- `0x180048100`
- `0x180048854`
- `0x180048dd0`

## callees

- `0x1800490d0`
- `0x18004978c`
- `0x18005e270`
- `0x1800846f0`
- `0x180128660`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180049196`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800491af`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180049196`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800491af`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrA` at `0x18004917c`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrA` at `0x18004917c`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18004915f`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18004915f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExA` at `0x180049623`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExA` at `0x180049623`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180049241`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180049443`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180049699`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180049241`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180049443`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180049699`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800496db`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800496db`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004948d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180049717`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004973f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180049769`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004948d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180049717`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004973f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180049769`

## string_xrefs

- `0x1800491c8`: `PROTOCOLS\Name-Space Handler\`
- `0x1800496d4`: `CLSID`

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
0x1800490d0  mov     [rsp-8+arg_0], rbx
0x1800490d5  push    rbp
0x1800490d6  push    rsi
0x1800490d7  push    rdi
0x1800490d8  push    r12
0x1800490da  push    r13
0x1800490dc  push    r14
0x1800490de  push    r15
0x1800490e0  lea     rbp, [rsp-2D0h]
0x1800490e8  sub     rsp, 3D0h
0x1800490ef  mov     rax, cs:__security_cookie
0x1800490f6  xor     rax, rsp
0x1800490f9  mov     [rbp+300h+var_40], rax
0x180049100  xor     r14d, r14d
0x180049103  mov     [rbp+300h+var_380], r9
0x180049107  mov     [rbp+300h+var_378], r8
0x18004910b  mov     rsi, r9
0x18004910e  mov     [rsp+400h+Type], r14d
0x180049113  mov     rdi, r8
0x180049116  mov     [rsp+400h+phkResult], r14
0x18004911b  mov     rbx, rdx
0x18004911e  test    rdx, rdx
0x180049121  jz      loc_18004977A
0x180049127  test    r8, r8
0x18004912a  jz      loc_18004977A
0x180049130  test    r9, r9
0x180049133  jz      loc_18004977A
0x180049139  mov     [rsp+400h+lpUsedDefaultChar], r14; lpUsedDefaultChar
0x18004913e  lea     rax, [rbp+300h+MultiByteStr]
0x180049142  mov     [rsp+400h+lpDefaultChar], r14; lpDefaultChar
0x180049147  mov     r8, rdx; lpWideCharStr
0x18004914a  mov     [rsp+400h+cbMultiByte], 20h ; ' '; cbMultiByte
0x180049152  or      r9d, 0FFFFFFFFh; cchWideChar
0x180049156  xor     edx, edx; dwFlags
0x180049158  mov     [rsp+400h+lpMultiByteStr], rax; lpMultiByteStr
0x18004915d  xor     ecx, ecx; CodePage
0x18004915f  call    cs:__imp_WideCharToMultiByte
0x180049166  nop     dword ptr [rax+rax+00h]
0x18004916b  test    eax, eax
0x18004916d  jz      loc_180049282
0x180049173  mov     edx, 3Ah ; ':'; wMatch
0x180049178  lea     rcx, [rbp+300h+MultiByteStr]; pszStart
0x18004917c  call    cs:__imp_StrChrA
0x180049183  nop     dword ptr [rax+rax+00h]
0x180049188  test    rax, rax
0x18004918b  jnz     loc_180049571
0x180049191  mov     ecx, 10000019h
0x180049196  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18004919d  nop     dword ptr [rax+rax+00h]
0x1800491a2  test    al, al
0x1800491a4  jnz     loc_180049551
0x1800491aa  mov     ecx, 2000000Dh
0x1800491af  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1800491b6  nop     dword ptr [rax+rax+00h]
0x1800491bb  test    al, al
0x1800491bd  jnz     loc_180049551
0x1800491c3  mov     edi, 100h
0x1800491c8  lea     r8, aProtocolsNameS; "PROTOCOLS\\Name-Space Handler\\"
0x1800491cf  mov     [rsp+400h+cchName], edi
0x1800491d3  lea     rdx, [rbp+300h+SubKey]
0x1800491d7  mov     ecx, edi
0x1800491d9  mov     r12d, 800C000Dh
0x1800491df  mov     eax, 7FFFFFFEh
0x1800491e4  mov     r9, r14
0x1800491e7  mov     esi, 1
0x1800491ec  test    rax, rax
0x1800491ef  jz      short loc_18004920D
0x1800491f1  mov     r10b, [r8]
0x1800491f4  test    r10b, r10b
0x1800491f7  jz      short loc_18004920D
0x1800491f9  mov     [rdx], r10b
0x1800491fc  add     r8, rsi
0x1800491ff  add     rdx, rsi
0x180049202  sub     rax, rsi
0x180049205  add     r9, rsi
0x180049208  sub     rcx, rsi
0x18004920b  jnz     short loc_1800491EC
0x18004920d  test    rcx, rcx
0x180049210  lea     rax, [rdx-1]
0x180049214  lea     rbx, [r9-1]
0x180049218  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18004921f  cmovnz  rax, rdx
0x180049223  cmovnz  rbx, r9
0x180049227  mov     r9d, 20019h; samDesired
0x18004922d  lea     rdx, [rbp+300h+SubKey]; lpSubKey
0x180049231  xor     r8d, r8d; ulOptions
0x180049234  mov     [rax], r14b
0x180049237  lea     rax, [rsp+400h+phkResult]
0x18004923c  mov     [rsp+400h+lpMultiByteStr], rax; phkResult
0x180049241  call    cs:__imp_RegOpenKeyExA
0x180049248  nop     dword ptr [rax+rax+00h]
0x18004924d  cmp     [rsp+400h+phkResult], r14
0x180049252  jnz     short loc_18004928B
0x180049254  mov     eax, r12d
0x180049257  mov     rcx, [rbp+300h+var_40]
0x18004925e  xor     rcx, rsp; StackCookie
0x180049261  call    __security_check_cookie
0x180049266  mov     rbx, [rsp+400h+arg_0]
0x18004926e  add     rsp, 3D0h
0x180049275  pop     r15
0x180049277  pop     r14
0x180049279  pop     r13
0x18004927b  pop     r12
0x18004927d  pop     rdi
0x18004927e  pop     rsi
0x18004927f  pop     rbp
0x180049280  retn
0x180049282  mov     [rbp+300h+MultiByteStr], r14b
0x180049286  jmp     loc_180049173
0x18004928b  lea     rdx, [rbp+300h+SubKey]
0x18004928f  mov     [rsp+400h+var_3B8], r14
0x180049294  add     rdx, rbx
0x180049297  mov     r15, rdi
0x18004929a  mov     eax, 2
0x18004929f  mov     [rbp+300h+var_370], rdx
0x1800492a3  sub     r15, rbx
0x1800492a6  mov     [rsp+400h+var_3B0], eax
0x1800492aa  mov     ebx, r14d
0x1800492ad  mov     r13d, r14d
0x1800492b0  mov     r9d, 80070057h
0x1800492b6  mov     [rdx], r14b
0x1800492b9  mov     r11, rdx
0x1800492bc  mov     rdi, r15
0x1800492bf  cmp     eax, 2
0x1800492c2  jnz     loc_1800494B1
0x1800492c8  lea     rax, [r15-1]
0x1800492cc  mov     r8d, 7FFFFFFEh
0x1800492d2  cmp     rax, r8
0x1800492d5  ja      loc_1800495C2
0x1800492db  mov     rcx, r15
0x1800492de  mov     rax, rdx
0x1800492e1  cmp     [rax], r14b
0x1800492e4  jnz     loc_180049579
0x1800492ea  mov     rax, rcx
0x1800492ed  neg     rax
0x1800492f0  sbb     ebx, ebx
0x1800492f2  not     ebx
0x1800492f4  and     ebx, r9d
0x1800492f7  test    rcx, rcx
0x1800492fa  jz      loc_18004958A
0x180049300  mov     rax, r15
0x180049303  sub     rax, rcx
0x180049306  test    rcx, rcx
0x180049309  jz      short loc_180049375
0x18004930b  sub     rdi, rax
0x18004930e  lea     r11, [rdx+rax]
0x180049312  cmp     rdi, rsi
0x180049315  jbe     loc_180049592
0x18004931b  mov     rax, r8
0x18004931e  lea     rcx, [rbp+300h+MultiByteStr]
0x180049322  mov     r8, r11
0x180049325  mov     rdx, rdi
0x180049328  mov     r10, r14
0x18004932b  test    rax, rax
0x18004932e  jz      short loc_18004934C
0x180049330  mov     r9b, [rcx]
0x180049333  test    r9b, r9b
0x180049336  jz      short loc_18004934C
0x180049338  mov     [r8], r9b
0x18004933b  add     rcx, rsi
0x18004933e  add     r8, rsi
0x180049341  sub     rax, rsi
0x180049344  add     r10, rsi
0x180049347  sub     rdx, rsi
0x18004934a  jnz     short loc_18004932B
0x18004934c  test    rdx, rdx
0x18004934f  lea     rcx, [r10-1]
0x180049353  lea     rax, [r8-1]
0x180049357  cmovnz  rax, r8
0x18004935b  cmovnz  rcx, r10
0x18004935f  neg     rdx
0x180049362  sbb     ebx, ebx
0x180049364  add     r11, rcx
0x180049367  not     ebx
0x180049369  mov     [rax], r14b
0x18004936c  and     ebx, 8007007Ah
0x180049372  sub     rdi, rcx
0x180049375  test    ebx, ebx
0x180049377  js      loc_180049488
0x18004937d  lea     rax, [rdi-1]
0x180049381  mov     edx, 7FFFFFFEh
0x180049386  cmp     rax, rdx
0x180049389  ja      loc_180049488
0x18004938f  mov     rax, rdi
0x180049392  mov     rcx, r11
0x180049395  cmp     [rcx], r14b
0x180049398  jnz     loc_1800495CA
0x18004939e  mov     rcx, rdi
0x1800493a1  sub     rcx, rax
0x1800493a4  test    rax, rax
0x1800493a7  jz      loc_180049488
0x1800493ad  sub     rdi, rcx
0x1800493b0  lea     rsi, [rcx+r11]
0x1800493b4  cmp     rdi, 1
0x1800493b8  jbe     loc_1800495DE
0x1800493be  mov     rax, rdx
0x1800493c1  lea     rcx, asc_18013A808; "\\"
0x1800493c8  mov     rdx, rdi
0x1800493cb  mov     r8, rsi
0x1800493ce  mov     r10, r14
0x1800493d1  test    rax, rax
0x1800493d4  jz      short loc_1800493F3
0x1800493d6  mov     r9b, [rcx]
0x1800493d9  test    r9b, r9b
0x1800493dc  jz      short loc_1800493F3
0x1800493de  mov     [r8], r9b
0x1800493e1  inc     rcx
0x1800493e4  inc     r8
0x1800493e7  dec     rax
0x1800493ea  inc     r10
0x1800493ed  sub     rdx, 1
0x1800493f1  jnz     short loc_1800493D1
0x1800493f3  test    rdx, rdx
0x1800493f6  lea     rcx, [r10-1]
0x1800493fa  lea     rax, [r8-1]
0x1800493fe  cmovnz  rax, r8
0x180049402  cmovnz  rcx, r10
0x180049406  neg     rdx
0x180049409  sbb     ebx, ebx
0x18004940b  add     rsi, rcx
0x18004940e  not     ebx
0x180049410  mov     [rax], r14b
0x180049413  and     ebx, 8007007Ah
0x180049419  sub     rdi, rcx
0x18004941c  mov     [rsp+400h+var_390], rdi
0x180049421  test    ebx, ebx
0x180049423  js      short loc_180049488
0x180049425  lea     rax, [rsp+400h+var_3B8]
0x18004942a  mov     r9d, 20019h; samDesired
0x180049430  xor     r8d, r8d; ulOptions
0x180049433  mov     [rsp+400h+lpMultiByteStr], rax; phkResult
0x180049438  lea     rdx, [rbp+300h+SubKey]; lpSubKey
0x18004943c  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180049443  call    cs:__imp_RegOpenKeyExA
0x18004944a  nop     dword ptr [rax+rax+00h]
0x18004944f  test    eax, eax
0x180049451  jz      loc_180049567
0x180049457  mov     rcx, r14; hKey
0x18004945a  mov     [rsp+400h+var_3B8], rcx
0x18004945f  test    rcx, rcx
0x180049462  jnz     loc_1800495F1
0x180049468  mov     eax, [rsp+400h+var_3B0]
0x18004946c  mov     esi, 1
0x180049471  mov     rdx, [rbp+300h+var_370]
0x180049475  add     eax, 0FFFFFFFFh
0x180049478  mov     [rsp+400h+var_3B0], eax
0x18004947c  mov     r9d, 80070057h
0x180049482  jnz     loc_1800492B6
0x180049488  mov     rcx, [rsp+400h+phkResult]; hKey
0x18004948d  call    cs:__imp_RegCloseKey
0x180049494  nop     dword ptr [rax+rax+00h]
0x180049499  test    r13d, r13d
0x18004949c  jz      loc_180049254
0x1800494a2  mov     rax, [rbp+300h+var_380]
0x1800494a6  mov     r12d, r14d
0x1800494a9  mov     [rax], r13d
0x1800494ac  jmp     loc_180049254
0x1800494b1  cmp     eax, esi
0x1800494b3  jnz     loc_180049375
0x1800494b9  lea     rax, [r15-1]
0x1800494bd  mov     r8d, 7FFFFFFEh
0x1800494c3  cmp     rax, r8
0x1800494c6  ja      loc_1800495C2
0x1800494cc  mov     rcx, r15
0x1800494cf  mov     rax, rdx
0x1800494d2  cmp     [rax], r14b
0x1800494d5  jnz     loc_1800495A9
0x1800494db  mov     rax, rcx
0x1800494de  neg     rax
0x1800494e1  sbb     ebx, ebx
0x1800494e3  not     ebx
0x1800494e5  and     ebx, r9d
0x1800494e8  test    rcx, rcx
0x1800494eb  jz      loc_1800495BA
0x1800494f1  mov     rax, r15
0x1800494f4  sub     rax, rcx
0x1800494f7  test    rcx, rcx
0x1800494fa  jz      loc_180049375
0x180049500  sub     rdi, rax
0x180049503  lea     r11, [rdx+rax]
0x180049507  cmp     rdi, rsi
0x18004950a  jbe     loc_18004959F
0x180049510  mov     rax, r8
0x180049513  lea     rcx, asc_18013A80C; "*"
0x18004951a  mov     r8, r11
0x18004951d  mov     rdx, rdi
0x180049520  mov     r10, r14
0x180049523  test    rax, rax
0x180049526  jz      loc_18004934C
0x18004952c  mov     r9b, [rcx]
0x18004952f  test    r9b, r9b
0x180049532  jz      loc_18004934C
0x180049538  mov     [r8], r9b
0x18004953b  add     rcx, rsi
0x18004953e  add     r8, rsi
0x180049541  sub     rax, rsi
0x180049544  add     r10, rsi
0x180049547  sub     rdx, rsi
0x18004954a  jnz     short loc_180049523
0x18004954c  jmp     loc_18004934C
  ... truncated ...
```
