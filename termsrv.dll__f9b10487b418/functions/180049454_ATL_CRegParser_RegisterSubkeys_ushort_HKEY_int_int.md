# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x180049454`
- end: `0x180049a2d`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1497`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x180049120`
- `0x180049454`

## callees

- `0x1800321f0`
- `0x18003fa30`
- `0x1800400b4`
- `0x180040124`
- `0x180040294`
- `0x1800404c0`
- `0x180040f10`
- `0x180045f94`
- `0x180047cd8`
- `0x18004859c`
- `0x180048c30`
- `0x180049454`
- `0x18004ade0`
- `0x18004d834`
- `0x1800c4da0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18004985a`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18004985a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004975b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004975b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800496a9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800496a9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800494cf`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800494e2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800495b6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800495e5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800494cf`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800494e2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800495b6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800495e5`

## string_xrefs

- `0x1800494d8`: `ForceRemove`
- `0x1800495ac`: `NoRemove`
- `0x1800494c5`: `Delete`

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
  LSTATUS v15; // eax
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
          if ( ATL::CRegParser::CanForceRemoveKey(v12, v7) )
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
            if ( ATL::CRegParser::CanForceRemoveKey(v21, v34) && v14 )
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
0x180049454  push    rbp
0x180049456  push    rbx
0x180049457  push    rsi
0x180049458  push    rdi
0x180049459  push    r12
0x18004945b  push    r13
0x18004945d  push    r14
0x18004945f  push    r15
0x180049461  lea     rbp, [rsp-21C8h]
0x180049469  mov     eax, 22C8h
0x18004946e  call    _alloca_probe
0x180049473  sub     rsp, rax
0x180049476  mov     rax, cs:__security_cookie
0x18004947d  xor     rax, rsp
0x180049480  mov     [rbp+2200h+var_50], rax
0x180049487  mov     r15d, r9d
0x18004948a  mov     [rsp+2300h+var_22B0], r9d
0x18004948f  mov     r13, r8
0x180049492  mov     rdi, rdx
0x180049495  mov     rsi, rcx
0x180049498  xor     r14d, r14d
0x18004949b  mov     [rsp+2300h+var_2290], r14
0x1800494a0  mov     [rsp+2300h+var_2288], r14
0x1800494a5  mov     [rbp+2200h+var_2280], r14
0x1800494a9  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800494ae  test    eax, eax
0x1800494b0  mov     ebx, eax
0x1800494b2  js      loc_1800499E1
0x1800494b8  xor     r12d, r12d
0x1800494bb  cmp     word ptr [rdi], 7Dh ; '}'
0x1800494bf  jz      loc_1800499E1
0x1800494c5  lea     rdx, String2; "Delete"
0x1800494cc  mov     rcx, rdi; lpString1
0x1800494cf  call    cs:__imp_lstrcmpiW
0x1800494d5  mov     r14d, eax
0x1800494d8  lea     rdx, aForceremove; "ForceRemove"
0x1800494df  mov     rcx, rdi; lpString1
0x1800494e2  call    cs:__imp_lstrcmpiW
0x1800494e8  test    eax, eax
0x1800494ea  jz      short loc_1800494F5
0x1800494ec  test    r14d, r14d
0x1800494ef  jnz     loc_1800495A6
0x1800494f5  mov     rdx, rdi; unsigned __int16 *
0x1800494f8  mov     rcx, rsi; this
0x1800494fb  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180049500  mov     ebx, eax
0x180049502  test    eax, eax
0x180049504  js      loc_1800499E1
0x18004950a  test    r15d, r15d
0x18004950d  jz      loc_1800495A6
0x180049513  mov     [rsp+2300h+hKey], r12
0x180049518  mov     [rsp+2300h+var_22A0], r12
0x18004951d  mov     [rsp+2300h+var_2298], r12
0x180049522  mov     edx, 5Ch ; '\'; unsigned __int16
0x180049527  mov     rcx, rdi; lpsz
0x18004952a  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18004952f  test    rax, rax
0x180049532  jnz     loc_1800499D2
0x180049538  mov     rdx, rdi; unsigned __int16 *
0x18004953b  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x180049540  test    eax, eax
0x180049542  jz      short loc_18004955B
0x180049544  mov     [rsp+2300h+hKey], r13
0x180049549  mov     rdx, rdi; unsigned __int16 *
0x18004954c  lea     rcx, [rsp+2300h+hKey]; this
0x180049551  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180049556  mov     [rsp+2300h+hKey], r12
0x18004955b  test    r14d, r14d
0x18004955e  jnz     short loc_18004959C
0x180049560  mov     rdx, rdi; unsigned __int16 *
0x180049563  mov     rcx, rsi; this
0x180049566  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18004956b  mov     ebx, eax
0x18004956d  xor     r14d, r14d
0x180049570  test    eax, eax
0x180049572  js      loc_180049A19
0x180049578  mov     rdx, rdi; unsigned __int16 *
0x18004957b  mov     rcx, rsi; this
0x18004957e  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180049583  mov     ebx, eax
0x180049585  test    eax, eax
0x180049587  lea     rcx, [rsp+2300h+hKey]; this
0x18004958c  js      loc_180049A1E
0x180049592  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180049597  jmp     loc_1800497C0
0x18004959c  lea     rcx, [rsp+2300h+hKey]; this
0x1800495a1  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800495a6  mov     r12d, 1
0x1800495ac  lea     rdx, aNoremove; "NoRemove"
0x1800495b3  mov     rcx, rdi; lpString1
0x1800495b6  call    cs:__imp_lstrcmpiW
0x1800495bc  xor     r14d, r14d
0x1800495bf  test    eax, eax
0x1800495c1  jnz     short loc_1800495DB
0x1800495c3  mov     r12d, r14d
0x1800495c6  mov     rdx, rdi; unsigned __int16 *
0x1800495c9  mov     rcx, rsi; this
0x1800495cc  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800495d1  mov     ebx, eax
0x1800495d3  test    eax, eax
0x1800495d5  js      loc_1800499E1
0x1800495db  lea     rdx, aVal; "Val"
0x1800495e2  mov     rcx, rdi; lpString1
0x1800495e5  call    cs:__imp_lstrcmpiW
0x1800495eb  test    eax, eax
0x1800495ed  jnz     loc_1800496D4
0x1800495f3  lea     rdx, [rbp+2200h+ValueName]; unsigned __int16 *
0x1800495fa  mov     rcx, rsi; this
0x1800495fd  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180049602  mov     ebx, eax
0x180049604  test    eax, eax
0x180049606  js      loc_1800499E1
0x18004960c  mov     rdx, rdi; unsigned __int16 *
0x18004960f  mov     rcx, rsi; this
0x180049612  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180049617  mov     ebx, eax
0x180049619  test    eax, eax
0x18004961b  js      loc_1800499E1
0x180049621  cmp     word ptr [rdi], 3Dh ; '='
0x180049625  jnz     loc_1800499DC
0x18004962b  test    r15d, r15d
0x18004962e  jz      short loc_180049662
0x180049630  mov     [rsp+2300h+var_22A0], r14
0x180049635  mov     [rsp+2300h+var_2298], r14
0x18004963a  mov     [rsp+2300h+hKey], r13
0x18004963f  mov     r9, rdi; unsigned __int16 *
0x180049642  lea     r8, [rbp+2200h+ValueName]; unsigned __int16 *
0x180049649  lea     rdx, [rsp+2300h+hKey]; struct ATL::CRegKey *
0x18004964e  mov     rcx, rsi; this
0x180049651  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180049656  mov     ebx, eax
0x180049658  mov     [rsp+2300h+hKey], r14
0x18004965d  jmp     loc_180049585
0x180049662  cmp     [rbp+2200h+arg_20], r14d
0x180049669  jnz     short loc_1800496C4
0x18004966b  test    r12d, r12d
0x18004966e  jz      short loc_1800496C4
0x180049670  mov     [rsp+2300h+hKey], r14
0x180049675  mov     [rsp+2300h+var_22A0], r14
0x18004967a  mov     [rsp+2300h+var_2298], r14
0x18004967f  mov     r9d, 20006h; unsigned int
0x180049685  xor     r8d, r8d; lpSubKey
0x180049688  mov     rdx, r13; hKey
0x18004968b  lea     rcx, [rsp+2300h+hKey]; this
0x180049690  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180049695  test    eax, eax
0x180049697  jnz     loc_180049A10
0x18004969d  lea     rdx, [rbp+2200h+ValueName]; lpValueName
0x1800496a4  mov     rcx, [rsp+2300h+hKey]; hKey
0x1800496a9  call    cs:__imp_RegDeleteValueW
0x1800496af  test    eax, 0FFFFFFFDh
0x1800496b4  jnz     loc_180049A10
0x1800496ba  lea     rcx, [rsp+2300h+hKey]; this
0x1800496bf  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800496c4  mov     rdx, rdi; unsigned __int16 *
0x1800496c7  mov     rcx, rsi; this
0x1800496ca  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1800496cf  jmp     loc_1800494AE
0x1800496d4  mov     edx, 5Ch ; '\'; unsigned __int16
0x1800496d9  mov     rcx, rdi; lpsz
0x1800496dc  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x1800496e1  test    rax, rax
0x1800496e4  jnz     loc_1800499DC
0x1800496ea  test    r15d, r15d
0x1800496ed  jz      loc_18004980F
0x1800496f3  mov     ebx, 2001Fh
0x1800496f8  mov     r9d, ebx; unsigned int
0x1800496fb  mov     r8, rdi; lpSubKey
0x1800496fe  mov     rdx, r13; hKey
0x180049701  lea     rcx, [rsp+2300h+var_2290]; this
0x180049706  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18004970b  test    eax, eax
0x18004970d  jz      short loc_180049788
0x18004970f  lea     r9d, [rbx-6]; unsigned int
0x180049713  mov     r8, rdi; lpSubKey
0x180049716  mov     rdx, r13; hKey
0x180049719  lea     rcx, [rsp+2300h+var_2290]; this
0x18004971e  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180049723  test    eax, eax
0x180049725  jz      short loc_180049788
0x180049727  mov     [rbp+2200h+dwDisposition], r14d
0x18004972b  mov     [rbp+2200h+var_2270], r14
0x18004972f  lea     rax, [rbp+2200h+dwDisposition]
0x180049733  mov     [rsp+2300h+lpdwDisposition], rax; lpdwDisposition
0x180049738  lea     rax, [rbp+2200h+var_2270]
0x18004973c  mov     [rsp+2300h+phkResult], rax; phkResult
0x180049741  mov     [rsp+2300h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180049746  mov     [rsp+2300h+samDesired], ebx; samDesired
0x18004974a  mov     dword ptr [rsp+2300h+dwOptions], r14d; dwOptions
0x18004974f  xor     r9d, r9d; lpClass
0x180049752  xor     r8d, r8d; Reserved
0x180049755  mov     rdx, rdi; lpSubKey
0x180049758  mov     rcx, r13; hKey
0x18004975b  call    cs:__imp_RegCreateKeyExW
0x180049761  mov     ecx, eax
0x180049763  test    eax, eax
0x180049765  jnz     loc_18004990F
0x18004976b  lea     rcx, [rsp+2300h+var_2290]; this
0x180049770  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180049775  mov     ecx, eax
0x180049777  mov     rax, [rbp+2200h+var_2270]
0x18004977b  mov     [rsp+2300h+var_2290], rax
0x180049780  test    ecx, ecx
0x180049782  jnz     loc_18004990F
0x180049788  mov     rdx, rdi; unsigned __int16 *
0x18004978b  mov     rcx, rsi; this
0x18004978e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180049793  mov     ebx, eax
0x180049795  test    eax, eax
0x180049797  js      loc_1800499E1
0x18004979d  cmp     word ptr [rdi], 3Dh ; '='
0x1800497a1  jnz     short loc_1800497C0
0x1800497a3  mov     r9, rdi; unsigned __int16 *
0x1800497a6  xor     r8d, r8d; unsigned __int16 *
0x1800497a9  lea     rdx, [rsp+2300h+var_2290]; struct ATL::CRegKey *
0x1800497ae  mov     rcx, rsi; this
0x1800497b1  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x1800497b6  mov     ebx, eax
0x1800497b8  test    eax, eax
0x1800497ba  js      loc_1800499E1
0x1800497c0  cmp     word ptr [rdi], 7Bh ; '{'
0x1800497c4  jnz     loc_1800494B8
0x1800497ca  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800497ce  inc     rax
0x1800497d1  cmp     [rdi+rax*2], r14w
0x1800497d6  jnz     short loc_1800497CE
0x1800497d8  cmp     rax, 1
0x1800497dc  jnz     loc_1800494B8
0x1800497e2  mov     dword ptr [rsp+2300h+dwOptions], r14d; int
0x1800497e7  mov     r9d, r15d; int
0x1800497ea  mov     r8, [rsp+2300h+var_2290]; HKEY
0x1800497ef  mov     rdx, rdi; unsigned __int16 *
0x1800497f2  mov     rcx, rsi; this
0x1800497f5  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800497fa  mov     ebx, eax
0x1800497fc  test    eax, eax
0x1800497fe  js      loc_1800499E1
0x180049804  mov     rdx, rdi
0x180049807  mov     rcx, rsi
0x18004980a  jmp     loc_1800494A9
0x18004980f  cmp     [rbp+2200h+arg_20], r14d
0x180049816  jnz     short loc_180049833
0x180049818  mov     r9d, 20019h; unsigned int
0x18004981e  mov     r8, rdi; lpSubKey
0x180049821  mov     rdx, r13; hKey
0x180049824  lea     rcx, [rsp+2300h+var_2290]; this
0x180049829  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18004982e  mov     r14d, eax
0x180049831  jmp     short loc_180049839
0x180049833  mov     r14d, 2
0x180049839  mov     r15d, 1
0x18004983f  test    r14d, r14d
0x180049842  cmovz   r15d, [rbp+2200h+arg_20]
0x18004984a  or      r9, 0FFFFFFFFFFFFFFFFh
0x18004984e  mov     r8, rdi
0x180049851  mov     edx, 104h
0x180049856  lea     rcx, [rbp+2200h+var_2260]
0x18004985a  call    cs:__imp__o_wcsncpy_s
0x180049860  mov     ecx, eax; int
0x180049862  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180049867  mov     rdx, rdi; unsigned __int16 *
0x18004986a  mov     rcx, rsi; this
0x18004986d  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180049872  mov     ebx, eax
0x180049874  test    eax, eax
0x180049876  js      loc_1800499E1
0x18004987c  mov     rdx, rdi; unsigned __int16 *
0x18004987f  mov     rcx, rsi; this
0x180049882  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180049887  mov     ebx, eax
0x180049889  xor     ecx, ecx
0x18004988b  test    eax, eax
0x18004988d  js      loc_1800499E1
0x180049893  cmp     word ptr [rdi], 7Bh ; '{'
0x180049897  jnz     short loc_1800498E8
0x180049899  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004989d  inc     rax
0x1800498a0  cmp     [rdi+rax*2], cx
0x1800498a4  jnz     short loc_18004989D
0x1800498a6  cmp     rax, 1
0x1800498aa  jnz     short loc_1800498E8
0x1800498ac  mov     dword ptr [rsp+2300h+dwOptions], r15d; int
0x1800498b1  xor     r9d, r9d; int
0x1800498b4  mov     r8, [rsp+2300h+var_2290]; HKEY
0x1800498b9  mov     rdx, rdi; unsigned __int16 *
0x1800498bc  mov     rcx, rsi; this
0x1800498bf  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800498c4  mov     ebx, eax
0x1800498c6  test    eax, eax
0x1800498c8  jns     short loc_1800498D3
0x1800498ca  test    r15d, r15d
0x1800498cd  jz      loc_1800499E1
0x1800498d3  mov     rdx, rdi; unsigned __int16 *
0x1800498d6  mov     rcx, rsi; this
0x1800498d9  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800498de  mov     ebx, eax
0x1800498e0  test    eax, eax
0x1800498e2  js      loc_1800499E1
0x1800498e8  cmp     r14d, 2
0x1800498ec  mov     r15d, [rsp+2300h+var_22B0]
  ... truncated ...
```
