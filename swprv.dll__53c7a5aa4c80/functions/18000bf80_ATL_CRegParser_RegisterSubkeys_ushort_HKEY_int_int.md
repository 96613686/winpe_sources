# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x18000bf80`
- end: `0x18000c559`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1497`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x18000bb2c`
- `0x18000bf80`

## callees

- `0x180001580`
- `0x18000869c`
- `0x180008e8c`
- `0x180008efc`
- `0x1800095a8`
- `0x1800096c4`
- `0x180009cec`
- `0x18000a4a0`
- `0x18000a8f0`
- `0x18000b618`
- `0x18000ba18`
- `0x18000bf80`
- `0x18000c9a0`
- `0x18000ca70`
- `0x180041990`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000c386`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000c386`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000c1d5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000c1d5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000c287`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000c287`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000bffb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000c00e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000c0e2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000c111`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000bffb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000c00e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000c0e2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000c111`

## string_xrefs

- `0x18000c004`: `ForceRemove`
- `0x18000c0d8`: `NoRemove`
- `0x18000bff1`: `Delete`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::RegisterSubkeys(
        ATL::CRegParser *this,
        unsigned __int16 *a2,
        HKEY a3,
        int a4,
        int a5)
{
  int v5; // r15d
  unsigned __int16 *v7; // rdi
  ATL::CRegParser *v8; // rsi
  int Token; // eax
  int v10; // ebx
  int v11; // r14d
  ATL::CRegParser *v12; // rcx
  int v13; // eax
  int v14; // r12d
  unsigned int v15; // eax
  LSTATUS v16; // ecx
  __int64 v17; // rax
  int v18; // r14d
  int v19; // r15d
  int v20; // eax
  ATL::CRegParser *v21; // rcx
  __int64 v22; // rax
  int HasSubKeys; // r14d
  LSTATUS v24; // eax
  __int64 dwOptions; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v29; // [rsp+60h] [rbp-A0h]
  __int64 v30; // [rsp+68h] [rbp-98h]
  HKEY v31[3]; // [rsp+70h] [rbp-90h] BYREF
  DWORD dwDisposition; // [rsp+88h] [rbp-78h] BYREF
  HKEY phkResult; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v34[264]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR ValueName[4096]; // [rsp+2B0h] [rbp+1B0h] BYREF

  v5 = a4;
  v7 = a2;
  v8 = this;
  memset(v31, 0, sizeof(v31));
LABEL_2:
  Token = ATL::CRegParser::NextToken(this, a2);
  while ( 2 )
  {
    v10 = Token;
    if ( Token < 0 )
      goto LABEL_79;
    while ( 1 )
    {
      if ( *v7 == 125 )
        goto LABEL_79;
      v11 = lstrcmpiW(v7, L"Delete");
      if ( !lstrcmpiW(v7, L"ForceRemove") || !v11 )
      {
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_79;
        if ( v5 )
        {
          hKey = 0;
          v29 = 0;
          v30 = 0;
          if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
          {
            ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_78:
            v10 = -2147352567;
            goto LABEL_79;
          }
          if ( (unsigned int)ATL::CRegParser::CanForceRemoveKey(v12, v7) )
          {
            hKey = a3;
            ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)&hKey, v7);
            hKey = 0;
          }
          if ( !v11 )
          {
            v10 = ATL::CRegParser::NextToken(v8, v7);
            if ( v10 < 0 )
              goto LABEL_81;
            v13 = ATL::CRegParser::SkipAssignment(v8, v7);
            v10 = v13;
            goto LABEL_15;
          }
          ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
        }
      }
      v14 = 1;
      if ( !lstrcmpiW(v7, L"NoRemove") )
      {
        v14 = 0;
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_79;
      }
      if ( !lstrcmpiW(v7, L"Val") )
        break;
      if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
        goto LABEL_78;
      if ( v5 )
      {
        if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v31, a3, v7, 0x2001Fu) )
        {
          if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v31, a3, v7, 0x20019u) )
          {
            dwDisposition = 0;
            phkResult = 0;
            v16 = RegCreateKeyExW(a3, v7, 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition);
            if ( v16 )
              goto LABEL_65;
            v16 = ATL::CRegKey::Close((ATL::CRegKey *)v31);
            v31[0] = phkResult;
            if ( v16 )
              goto LABEL_65;
          }
        }
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_79;
        if ( *v7 == 61 )
        {
          v10 = ATL::CRegParser::AddValue(v8, v31, 0, v7);
          if ( v10 < 0 )
            goto LABEL_79;
        }
LABEL_41:
        if ( *v7 == 123 )
        {
          v17 = -1;
          do
            ++v17;
          while ( v7[v17] );
          if ( v17 == 1 )
          {
            v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v31[0], v5, 0);
            if ( v10 < 0 )
              goto LABEL_79;
            a2 = v7;
            this = v8;
            goto LABEL_2;
          }
        }
      }
      else
      {
        if ( a5 )
          v18 = 2;
        else
          v18 = ATL::CRegKey::Open((ATL::CRegKey *)v31, a3, v7, 0x20019u);
        v19 = 1;
        if ( !v18 )
          v19 = a5;
        v20 = _o_wcsncpy_s(v34, 260, v7, -1, dwOptions);
        ATL::AtlCrtErrorCheck(v20);
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_79;
        v10 = ATL::CRegParser::SkipAssignment(v8, v7);
        v21 = 0;
        if ( v10 < 0 )
          goto LABEL_79;
        if ( *v7 == 123 )
        {
          v22 = -1;
          do
            ++v22;
          while ( v7[v22] );
          if ( v22 == 1 )
          {
            v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v31[0], 0, v19);
            if ( v10 < 0 && !v19 )
              goto LABEL_79;
            v10 = ATL::CRegParser::NextToken(v8, v7);
            if ( v10 < 0 )
              goto LABEL_79;
          }
        }
        v5 = a4;
        if ( v18 != 2 )
        {
          if ( v18 )
          {
            if ( !a5 )
            {
              v16 = v18;
LABEL_65:
              v10 = ATL::AtlHresultFromWin32(v16);
              goto LABEL_79;
            }
          }
          else if ( a5 && ATL::CRegParser::HasSubKeys(v21, v31[0]) )
          {
            if ( (unsigned int)ATL::CRegParser::CanForceRemoveKey(v21, v34) && v14 )
              ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v31, v34);
          }
          else
          {
            HasSubKeys = ATL::CRegParser::HasSubKeys(v21, v31[0]);
            v24 = ATL::CRegKey::Close((ATL::CRegKey *)v31);
            if ( v24 )
            {
              v16 = v24;
              goto LABEL_65;
            }
            if ( v14 && !HasSubKeys )
            {
              v29 = 0;
              v30 = 0;
              hKey = a3;
              v15 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&hKey, v34);
              hKey = 0;
              if ( v15 )
                goto LABEL_80;
              ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
            }
          }
        }
      }
    }
    v10 = ATL::CRegParser::NextToken(v8, ValueName);
    if ( v10 < 0 )
      goto LABEL_79;
    v10 = ATL::CRegParser::NextToken(v8, v7);
    if ( v10 < 0 )
      goto LABEL_79;
    if ( *v7 != 61 )
      goto LABEL_78;
    if ( v5 )
    {
      v29 = 0;
      v30 = 0;
      hKey = a3;
      v13 = ATL::CRegParser::AddValue(v8, &hKey, ValueName, v7);
      v10 = v13;
      hKey = 0;
LABEL_15:
      if ( v13 < 0 )
        goto LABEL_81;
      ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
      goto LABEL_41;
    }
    if ( a5 || !v14 )
      goto LABEL_31;
    hKey = 0;
    v29 = 0;
    v30 = 0;
    v15 = ATL::CRegKey::Open((ATL::CRegKey *)&hKey, a3, 0, 0x20006u);
    if ( !v15 )
    {
      v15 = RegDeleteValueW(hKey, ValueName);
      if ( (v15 & 0xFFFFFFFD) == 0 )
      {
        ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_31:
        Token = ATL::CRegParser::SkipAssignment(v8, v7);
        continue;
      }
    }
    break;
  }
LABEL_80:
  v10 = ATL::AtlHresultFromWin32(v15);
LABEL_81:
  ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_79:
  ATL::CRegKey::Close((ATL::CRegKey *)v31);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000bf80  push    rbp
0x18000bf82  push    rbx
0x18000bf83  push    rsi
0x18000bf84  push    rdi
0x18000bf85  push    r12
0x18000bf87  push    r13
0x18000bf89  push    r14
0x18000bf8b  push    r15
0x18000bf8d  lea     rbp, [rsp-21C8h]
0x18000bf95  mov     eax, 22C8h
0x18000bf9a  call    _alloca_probe
0x18000bf9f  sub     rsp, rax
0x18000bfa2  mov     rax, cs:__security_cookie
0x18000bfa9  xor     rax, rsp
0x18000bfac  mov     [rbp+2200h+var_50], rax
0x18000bfb3  mov     r15d, r9d
0x18000bfb6  mov     [rsp+2300h+var_22B0], r9d
0x18000bfbb  mov     r13, r8
0x18000bfbe  mov     rdi, rdx
0x18000bfc1  mov     rsi, rcx
0x18000bfc4  xor     r14d, r14d
0x18000bfc7  mov     [rsp+2300h+var_2290], r14
0x18000bfcc  mov     [rsp+2300h+var_2288], r14
0x18000bfd1  mov     [rbp+2200h+var_2280], r14
0x18000bfd5  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000bfda  test    eax, eax
0x18000bfdc  mov     ebx, eax
0x18000bfde  js      loc_18000C50D
0x18000bfe4  xor     r12d, r12d
0x18000bfe7  cmp     word ptr [rdi], 7Dh ; '}'
0x18000bfeb  jz      loc_18000C50D
0x18000bff1  lea     rdx, String2; "Delete"
0x18000bff8  mov     rcx, rdi; lpString1
0x18000bffb  call    cs:__imp_lstrcmpiW
0x18000c001  mov     r14d, eax
0x18000c004  lea     rdx, aForceremove; "ForceRemove"
0x18000c00b  mov     rcx, rdi; lpString1
0x18000c00e  call    cs:__imp_lstrcmpiW
0x18000c014  test    eax, eax
0x18000c016  jz      short loc_18000C021
0x18000c018  test    r14d, r14d
0x18000c01b  jnz     loc_18000C0D2
0x18000c021  mov     rdx, rdi; unsigned __int16 *
0x18000c024  mov     rcx, rsi; this
0x18000c027  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000c02c  mov     ebx, eax
0x18000c02e  test    eax, eax
0x18000c030  js      loc_18000C50D
0x18000c036  test    r15d, r15d
0x18000c039  jz      loc_18000C0D2
0x18000c03f  mov     [rsp+2300h+hKey], r12
0x18000c044  mov     [rsp+2300h+var_22A0], r12
0x18000c049  mov     [rsp+2300h+var_2298], r12
0x18000c04e  mov     edx, 5Ch ; '\'; unsigned __int16
0x18000c053  mov     rcx, rdi; lpsz
0x18000c056  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18000c05b  test    rax, rax
0x18000c05e  jnz     loc_18000C4FE
0x18000c064  mov     rdx, rdi; unsigned __int16 *
0x18000c067  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x18000c06c  test    eax, eax
0x18000c06e  jz      short loc_18000C087
0x18000c070  mov     [rsp+2300h+hKey], r13
0x18000c075  mov     rdx, rdi; unsigned __int16 *
0x18000c078  lea     rcx, [rsp+2300h+hKey]; this
0x18000c07d  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18000c082  mov     [rsp+2300h+hKey], r12
0x18000c087  test    r14d, r14d
0x18000c08a  jnz     short loc_18000C0C8
0x18000c08c  mov     rdx, rdi; unsigned __int16 *
0x18000c08f  mov     rcx, rsi; this
0x18000c092  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000c097  mov     ebx, eax
0x18000c099  xor     r14d, r14d
0x18000c09c  test    eax, eax
0x18000c09e  js      loc_18000C545
0x18000c0a4  mov     rdx, rdi; unsigned __int16 *
0x18000c0a7  mov     rcx, rsi; this
0x18000c0aa  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18000c0af  mov     ebx, eax
0x18000c0b1  test    eax, eax
0x18000c0b3  lea     rcx, [rsp+2300h+hKey]; this
0x18000c0b8  js      loc_18000C54A
0x18000c0be  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000c0c3  jmp     loc_18000C2EC
0x18000c0c8  lea     rcx, [rsp+2300h+hKey]; this
0x18000c0cd  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000c0d2  mov     r12d, 1
0x18000c0d8  lea     rdx, aNoremove; "NoRemove"
0x18000c0df  mov     rcx, rdi; lpString1
0x18000c0e2  call    cs:__imp_lstrcmpiW
0x18000c0e8  xor     r14d, r14d
0x18000c0eb  test    eax, eax
0x18000c0ed  jnz     short loc_18000C107
0x18000c0ef  mov     r12d, r14d
0x18000c0f2  mov     rdx, rdi; unsigned __int16 *
0x18000c0f5  mov     rcx, rsi; this
0x18000c0f8  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000c0fd  mov     ebx, eax
0x18000c0ff  test    eax, eax
0x18000c101  js      loc_18000C50D
0x18000c107  lea     rdx, aVal; "Val"
0x18000c10e  mov     rcx, rdi; lpString1
0x18000c111  call    cs:__imp_lstrcmpiW
0x18000c117  test    eax, eax
0x18000c119  jnz     loc_18000C200
0x18000c11f  lea     rdx, [rbp+2200h+ValueName]; unsigned __int16 *
0x18000c126  mov     rcx, rsi; this
0x18000c129  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000c12e  mov     ebx, eax
0x18000c130  test    eax, eax
0x18000c132  js      loc_18000C50D
0x18000c138  mov     rdx, rdi; unsigned __int16 *
0x18000c13b  mov     rcx, rsi; this
0x18000c13e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000c143  mov     ebx, eax
0x18000c145  test    eax, eax
0x18000c147  js      loc_18000C50D
0x18000c14d  cmp     word ptr [rdi], 3Dh ; '='
0x18000c151  jnz     loc_18000C508
0x18000c157  test    r15d, r15d
0x18000c15a  jz      short loc_18000C18E
0x18000c15c  mov     [rsp+2300h+var_22A0], r14
0x18000c161  mov     [rsp+2300h+var_2298], r14
0x18000c166  mov     [rsp+2300h+hKey], r13
0x18000c16b  mov     r9, rdi; unsigned __int16 *
0x18000c16e  lea     r8, [rbp+2200h+ValueName]; unsigned __int16 *
0x18000c175  lea     rdx, [rsp+2300h+hKey]; struct ATL::CRegKey *
0x18000c17a  mov     rcx, rsi; this
0x18000c17d  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18000c182  mov     ebx, eax
0x18000c184  mov     [rsp+2300h+hKey], r14
0x18000c189  jmp     loc_18000C0B1
0x18000c18e  cmp     [rbp+2200h+arg_20], r14d
0x18000c195  jnz     short loc_18000C1F0
0x18000c197  test    r12d, r12d
0x18000c19a  jz      short loc_18000C1F0
0x18000c19c  mov     [rsp+2300h+hKey], r14
0x18000c1a1  mov     [rsp+2300h+var_22A0], r14
0x18000c1a6  mov     [rsp+2300h+var_2298], r14
0x18000c1ab  mov     r9d, 20006h; unsigned int
0x18000c1b1  xor     r8d, r8d; lpSubKey
0x18000c1b4  mov     rdx, r13; hKey
0x18000c1b7  lea     rcx, [rsp+2300h+hKey]; this
0x18000c1bc  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000c1c1  test    eax, eax
0x18000c1c3  jnz     loc_18000C53C
0x18000c1c9  lea     rdx, [rbp+2200h+ValueName]; lpValueName
0x18000c1d0  mov     rcx, [rsp+2300h+hKey]; hKey
0x18000c1d5  call    cs:__imp_RegDeleteValueW
0x18000c1db  test    eax, 0FFFFFFFDh
0x18000c1e0  jnz     loc_18000C53C
0x18000c1e6  lea     rcx, [rsp+2300h+hKey]; this
0x18000c1eb  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000c1f0  mov     rdx, rdi; unsigned __int16 *
0x18000c1f3  mov     rcx, rsi; this
0x18000c1f6  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18000c1fb  jmp     loc_18000BFDA
0x18000c200  mov     edx, 5Ch ; '\'; unsigned __int16
0x18000c205  mov     rcx, rdi; lpsz
0x18000c208  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18000c20d  test    rax, rax
0x18000c210  jnz     loc_18000C508
0x18000c216  test    r15d, r15d
0x18000c219  jz      loc_18000C33B
0x18000c21f  mov     ebx, 2001Fh
0x18000c224  mov     r9d, ebx; unsigned int
0x18000c227  mov     r8, rdi; lpSubKey
0x18000c22a  mov     rdx, r13; hKey
0x18000c22d  lea     rcx, [rsp+2300h+var_2290]; this
0x18000c232  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000c237  test    eax, eax
0x18000c239  jz      short loc_18000C2B4
0x18000c23b  lea     r9d, [rbx-6]; unsigned int
0x18000c23f  mov     r8, rdi; lpSubKey
0x18000c242  mov     rdx, r13; hKey
0x18000c245  lea     rcx, [rsp+2300h+var_2290]; this
0x18000c24a  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000c24f  test    eax, eax
0x18000c251  jz      short loc_18000C2B4
0x18000c253  mov     [rbp+2200h+dwDisposition], r14d
0x18000c257  mov     [rbp+2200h+var_2270], r14
0x18000c25b  lea     rax, [rbp+2200h+dwDisposition]
0x18000c25f  mov     [rsp+2300h+lpdwDisposition], rax; lpdwDisposition
0x18000c264  lea     rax, [rbp+2200h+var_2270]
0x18000c268  mov     [rsp+2300h+phkResult], rax; phkResult
0x18000c26d  mov     [rsp+2300h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18000c272  mov     [rsp+2300h+samDesired], ebx; samDesired
0x18000c276  mov     dword ptr [rsp+2300h+dwOptions], r14d; dwOptions
0x18000c27b  xor     r9d, r9d; lpClass
0x18000c27e  xor     r8d, r8d; Reserved
0x18000c281  mov     rdx, rdi; lpSubKey
0x18000c284  mov     rcx, r13; hKey
0x18000c287  call    cs:__imp_RegCreateKeyExW
0x18000c28d  mov     ecx, eax
0x18000c28f  test    eax, eax
0x18000c291  jnz     loc_18000C43B
0x18000c297  lea     rcx, [rsp+2300h+var_2290]; this
0x18000c29c  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000c2a1  mov     ecx, eax
0x18000c2a3  mov     rax, [rbp+2200h+var_2270]
0x18000c2a7  mov     [rsp+2300h+var_2290], rax
0x18000c2ac  test    ecx, ecx
0x18000c2ae  jnz     loc_18000C43B
0x18000c2b4  mov     rdx, rdi; unsigned __int16 *
0x18000c2b7  mov     rcx, rsi; this
0x18000c2ba  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000c2bf  mov     ebx, eax
0x18000c2c1  test    eax, eax
0x18000c2c3  js      loc_18000C50D
0x18000c2c9  cmp     word ptr [rdi], 3Dh ; '='
0x18000c2cd  jnz     short loc_18000C2EC
0x18000c2cf  mov     r9, rdi; unsigned __int16 *
0x18000c2d2  xor     r8d, r8d; unsigned __int16 *
0x18000c2d5  lea     rdx, [rsp+2300h+var_2290]; struct ATL::CRegKey *
0x18000c2da  mov     rcx, rsi; this
0x18000c2dd  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18000c2e2  mov     ebx, eax
0x18000c2e4  test    eax, eax
0x18000c2e6  js      loc_18000C50D
0x18000c2ec  cmp     word ptr [rdi], 7Bh ; '{'
0x18000c2f0  jnz     loc_18000BFE4
0x18000c2f6  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c2fa  inc     rax
0x18000c2fd  cmp     [rdi+rax*2], r14w
0x18000c302  jnz     short loc_18000C2FA
0x18000c304  cmp     rax, 1
0x18000c308  jnz     loc_18000BFE4
0x18000c30e  mov     dword ptr [rsp+2300h+dwOptions], r14d; int
0x18000c313  mov     r9d, r15d; int
0x18000c316  mov     r8, [rsp+2300h+var_2290]; HKEY
0x18000c31b  mov     rdx, rdi; unsigned __int16 *
0x18000c31e  mov     rcx, rsi; this
0x18000c321  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000c326  mov     ebx, eax
0x18000c328  test    eax, eax
0x18000c32a  js      loc_18000C50D
0x18000c330  mov     rdx, rdi
0x18000c333  mov     rcx, rsi
0x18000c336  jmp     loc_18000BFD5
0x18000c33b  cmp     [rbp+2200h+arg_20], r14d
0x18000c342  jnz     short loc_18000C35F
0x18000c344  mov     r9d, 20019h; unsigned int
0x18000c34a  mov     r8, rdi; lpSubKey
0x18000c34d  mov     rdx, r13; hKey
0x18000c350  lea     rcx, [rsp+2300h+var_2290]; this
0x18000c355  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000c35a  mov     r14d, eax
0x18000c35d  jmp     short loc_18000C365
0x18000c35f  mov     r14d, 2
0x18000c365  mov     r15d, 1
0x18000c36b  test    r14d, r14d
0x18000c36e  cmovz   r15d, [rbp+2200h+arg_20]
0x18000c376  or      r9, 0FFFFFFFFFFFFFFFFh
0x18000c37a  mov     r8, rdi
0x18000c37d  mov     edx, 104h
0x18000c382  lea     rcx, [rbp+2200h+var_2260]
0x18000c386  call    cs:__imp__o_wcsncpy_s
0x18000c38c  mov     ecx, eax; int
0x18000c38e  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000c393  mov     rdx, rdi; unsigned __int16 *
0x18000c396  mov     rcx, rsi; this
0x18000c399  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000c39e  mov     ebx, eax
0x18000c3a0  test    eax, eax
0x18000c3a2  js      loc_18000C50D
0x18000c3a8  mov     rdx, rdi; unsigned __int16 *
0x18000c3ab  mov     rcx, rsi; this
0x18000c3ae  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18000c3b3  mov     ebx, eax
0x18000c3b5  xor     ecx, ecx
0x18000c3b7  test    eax, eax
0x18000c3b9  js      loc_18000C50D
0x18000c3bf  cmp     word ptr [rdi], 7Bh ; '{'
0x18000c3c3  jnz     short loc_18000C414
0x18000c3c5  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c3c9  inc     rax
0x18000c3cc  cmp     [rdi+rax*2], cx
0x18000c3d0  jnz     short loc_18000C3C9
0x18000c3d2  cmp     rax, 1
0x18000c3d6  jnz     short loc_18000C414
0x18000c3d8  mov     dword ptr [rsp+2300h+dwOptions], r15d; int
0x18000c3dd  xor     r9d, r9d; int
0x18000c3e0  mov     r8, [rsp+2300h+var_2290]; HKEY
0x18000c3e5  mov     rdx, rdi; unsigned __int16 *
0x18000c3e8  mov     rcx, rsi; this
0x18000c3eb  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000c3f0  mov     ebx, eax
0x18000c3f2  test    eax, eax
0x18000c3f4  jns     short loc_18000C3FF
0x18000c3f6  test    r15d, r15d
0x18000c3f9  jz      loc_18000C50D
0x18000c3ff  mov     rdx, rdi; unsigned __int16 *
0x18000c402  mov     rcx, rsi; this
0x18000c405  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000c40a  mov     ebx, eax
0x18000c40c  test    eax, eax
0x18000c40e  js      loc_18000C50D
0x18000c414  cmp     r14d, 2
0x18000c418  mov     r15d, [rsp+2300h+var_22B0]
  ... truncated ...
```
