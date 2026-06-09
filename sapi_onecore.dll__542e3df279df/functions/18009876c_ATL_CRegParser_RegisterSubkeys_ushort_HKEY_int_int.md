# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x18009876c`
- end: `0x180098d45`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1497`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x1800983a0`
- `0x18009876c`

## callees

- `0x180079e30`
- `0x180089570`
- `0x180089f28`
- `0x180089f98`
- `0x18008a6d8`
- `0x18008a968`
- `0x180092fc8`
- `0x18009406c`
- `0x180094abc`
- `0x18009505c`
- `0x18009828c`
- `0x18009876c`
- `0x18009c2f0`
- `0x18009f6b4`
- `0x18027b320`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180098b72`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180098b72`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800989c1`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800989c1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180098a73`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180098a73`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800987e7`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800987fa`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800988ce`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800988fd`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800987e7`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800987fa`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800988ce`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800988fd`

## string_xrefs

- `0x1800987f0`: `ForceRemove`
- `0x1800988c4`: `NoRemove`
- `0x1800987dd`: `Delete`

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
0x18009876c  push    rbp
0x18009876e  push    rbx
0x18009876f  push    rsi
0x180098770  push    rdi
0x180098771  push    r12
0x180098773  push    r13
0x180098775  push    r14
0x180098777  push    r15
0x180098779  lea     rbp, [rsp-21C8h]
0x180098781  mov     eax, 22C8h
0x180098786  call    _alloca_probe
0x18009878b  sub     rsp, rax
0x18009878e  mov     rax, cs:__security_cookie
0x180098795  xor     rax, rsp
0x180098798  mov     [rbp+2200h+var_50], rax
0x18009879f  mov     r15d, r9d
0x1800987a2  mov     [rsp+2300h+var_22B0], r9d
0x1800987a7  mov     r13, r8
0x1800987aa  mov     rdi, rdx
0x1800987ad  mov     rsi, rcx
0x1800987b0  xor     r14d, r14d
0x1800987b3  mov     [rsp+2300h+var_2290], r14
0x1800987b8  mov     [rsp+2300h+var_2288], r14
0x1800987bd  mov     [rbp+2200h+var_2280], r14
0x1800987c1  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800987c6  test    eax, eax
0x1800987c8  mov     ebx, eax
0x1800987ca  js      loc_180098CF9
0x1800987d0  xor     r12d, r12d
0x1800987d3  cmp     word ptr [rdi], 7Dh ; '}'
0x1800987d7  jz      loc_180098CF9
0x1800987dd  lea     rdx, aDelete; "Delete"
0x1800987e4  mov     rcx, rdi; lpString1
0x1800987e7  call    cs:__imp_lstrcmpiW
0x1800987ed  mov     r14d, eax
0x1800987f0  lea     rdx, aForceremove; "ForceRemove"
0x1800987f7  mov     rcx, rdi; lpString1
0x1800987fa  call    cs:__imp_lstrcmpiW
0x180098800  test    eax, eax
0x180098802  jz      short loc_18009880D
0x180098804  test    r14d, r14d
0x180098807  jnz     loc_1800988BE
0x18009880d  mov     rdx, rdi; unsigned __int16 *
0x180098810  mov     rcx, rsi; this
0x180098813  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180098818  mov     ebx, eax
0x18009881a  test    eax, eax
0x18009881c  js      loc_180098CF9
0x180098822  test    r15d, r15d
0x180098825  jz      loc_1800988BE
0x18009882b  mov     [rsp+2300h+hKey], r12
0x180098830  mov     [rsp+2300h+var_22A0], r12
0x180098835  mov     [rsp+2300h+var_2298], r12
0x18009883a  mov     edx, 5Ch ; '\'; unsigned __int16
0x18009883f  mov     rcx, rdi; lpsz
0x180098842  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180098847  test    rax, rax
0x18009884a  jnz     loc_180098CEA
0x180098850  mov     rdx, rdi; unsigned __int16 *
0x180098853  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x180098858  test    eax, eax
0x18009885a  jz      short loc_180098873
0x18009885c  mov     [rsp+2300h+hKey], r13
0x180098861  mov     rdx, rdi; unsigned __int16 *
0x180098864  lea     rcx, [rsp+2300h+hKey]; this
0x180098869  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18009886e  mov     [rsp+2300h+hKey], r12
0x180098873  test    r14d, r14d
0x180098876  jnz     short loc_1800988B4
0x180098878  mov     rdx, rdi; unsigned __int16 *
0x18009887b  mov     rcx, rsi; this
0x18009887e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180098883  mov     ebx, eax
0x180098885  xor     r14d, r14d
0x180098888  test    eax, eax
0x18009888a  js      loc_180098D31
0x180098890  mov     rdx, rdi; unsigned __int16 *
0x180098893  mov     rcx, rsi; this
0x180098896  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18009889b  mov     ebx, eax
0x18009889d  test    eax, eax
0x18009889f  lea     rcx, [rsp+2300h+hKey]; this
0x1800988a4  js      loc_180098D36
0x1800988aa  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800988af  jmp     loc_180098AD8
0x1800988b4  lea     rcx, [rsp+2300h+hKey]; this
0x1800988b9  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800988be  mov     r12d, 1
0x1800988c4  lea     rdx, aNoremove; "NoRemove"
0x1800988cb  mov     rcx, rdi; lpString1
0x1800988ce  call    cs:__imp_lstrcmpiW
0x1800988d4  xor     r14d, r14d
0x1800988d7  test    eax, eax
0x1800988d9  jnz     short loc_1800988F3
0x1800988db  mov     r12d, r14d
0x1800988de  mov     rdx, rdi; unsigned __int16 *
0x1800988e1  mov     rcx, rsi; this
0x1800988e4  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800988e9  mov     ebx, eax
0x1800988eb  test    eax, eax
0x1800988ed  js      loc_180098CF9
0x1800988f3  lea     rdx, aVal_0; "Val"
0x1800988fa  mov     rcx, rdi; lpString1
0x1800988fd  call    cs:__imp_lstrcmpiW
0x180098903  test    eax, eax
0x180098905  jnz     loc_1800989EC
0x18009890b  lea     rdx, [rbp+2200h+ValueName]; unsigned __int16 *
0x180098912  mov     rcx, rsi; this
0x180098915  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18009891a  mov     ebx, eax
0x18009891c  test    eax, eax
0x18009891e  js      loc_180098CF9
0x180098924  mov     rdx, rdi; unsigned __int16 *
0x180098927  mov     rcx, rsi; this
0x18009892a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18009892f  mov     ebx, eax
0x180098931  test    eax, eax
0x180098933  js      loc_180098CF9
0x180098939  cmp     word ptr [rdi], 3Dh ; '='
0x18009893d  jnz     loc_180098CF4
0x180098943  test    r15d, r15d
0x180098946  jz      short loc_18009897A
0x180098948  mov     [rsp+2300h+var_22A0], r14
0x18009894d  mov     [rsp+2300h+var_2298], r14
0x180098952  mov     [rsp+2300h+hKey], r13
0x180098957  mov     r9, rdi; unsigned __int16 *
0x18009895a  lea     r8, [rbp+2200h+ValueName]; unsigned __int16 *
0x180098961  lea     rdx, [rsp+2300h+hKey]; struct ATL::CRegKey *
0x180098966  mov     rcx, rsi; this
0x180098969  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18009896e  mov     ebx, eax
0x180098970  mov     [rsp+2300h+hKey], r14
0x180098975  jmp     loc_18009889D
0x18009897a  cmp     [rbp+2200h+arg_20], r14d
0x180098981  jnz     short loc_1800989DC
0x180098983  test    r12d, r12d
0x180098986  jz      short loc_1800989DC
0x180098988  mov     [rsp+2300h+hKey], r14
0x18009898d  mov     [rsp+2300h+var_22A0], r14
0x180098992  mov     [rsp+2300h+var_2298], r14
0x180098997  mov     r9d, 20006h; unsigned int
0x18009899d  xor     r8d, r8d; lpSubKey
0x1800989a0  mov     rdx, r13; hKey
0x1800989a3  lea     rcx, [rsp+2300h+hKey]; this
0x1800989a8  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800989ad  test    eax, eax
0x1800989af  jnz     loc_180098D28
0x1800989b5  lea     rdx, [rbp+2200h+ValueName]; lpValueName
0x1800989bc  mov     rcx, [rsp+2300h+hKey]; hKey
0x1800989c1  call    cs:__imp_RegDeleteValueW
0x1800989c7  test    eax, 0FFFFFFFDh
0x1800989cc  jnz     loc_180098D28
0x1800989d2  lea     rcx, [rsp+2300h+hKey]; this
0x1800989d7  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800989dc  mov     rdx, rdi; unsigned __int16 *
0x1800989df  mov     rcx, rsi; this
0x1800989e2  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1800989e7  jmp     loc_1800987C6
0x1800989ec  mov     edx, 5Ch ; '\'; unsigned __int16
0x1800989f1  mov     rcx, rdi; lpsz
0x1800989f4  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x1800989f9  test    rax, rax
0x1800989fc  jnz     loc_180098CF4
0x180098a02  test    r15d, r15d
0x180098a05  jz      loc_180098B27
0x180098a0b  mov     ebx, 2001Fh
0x180098a10  mov     r9d, ebx; unsigned int
0x180098a13  mov     r8, rdi; lpSubKey
0x180098a16  mov     rdx, r13; hKey
0x180098a19  lea     rcx, [rsp+2300h+var_2290]; this
0x180098a1e  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180098a23  test    eax, eax
0x180098a25  jz      short loc_180098AA0
0x180098a27  lea     r9d, [rbx-6]; unsigned int
0x180098a2b  mov     r8, rdi; lpSubKey
0x180098a2e  mov     rdx, r13; hKey
0x180098a31  lea     rcx, [rsp+2300h+var_2290]; this
0x180098a36  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180098a3b  test    eax, eax
0x180098a3d  jz      short loc_180098AA0
0x180098a3f  mov     [rbp+2200h+dwDisposition], r14d
0x180098a43  mov     [rbp+2200h+var_2270], r14
0x180098a47  lea     rax, [rbp+2200h+dwDisposition]
0x180098a4b  mov     [rsp+2300h+lpdwDisposition], rax; lpdwDisposition
0x180098a50  lea     rax, [rbp+2200h+var_2270]
0x180098a54  mov     [rsp+2300h+phkResult], rax; phkResult
0x180098a59  mov     [rsp+2300h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180098a5e  mov     [rsp+2300h+samDesired], ebx; samDesired
0x180098a62  mov     dword ptr [rsp+2300h+dwOptions], r14d; dwOptions
0x180098a67  xor     r9d, r9d; lpClass
0x180098a6a  xor     r8d, r8d; Reserved
0x180098a6d  mov     rdx, rdi; lpSubKey
0x180098a70  mov     rcx, r13; hKey
0x180098a73  call    cs:__imp_RegCreateKeyExW
0x180098a79  mov     ecx, eax
0x180098a7b  test    eax, eax
0x180098a7d  jnz     loc_180098C27
0x180098a83  lea     rcx, [rsp+2300h+var_2290]; this
0x180098a88  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180098a8d  mov     ecx, eax
0x180098a8f  mov     rax, [rbp+2200h+var_2270]
0x180098a93  mov     [rsp+2300h+var_2290], rax
0x180098a98  test    ecx, ecx
0x180098a9a  jnz     loc_180098C27
0x180098aa0  mov     rdx, rdi; unsigned __int16 *
0x180098aa3  mov     rcx, rsi; this
0x180098aa6  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180098aab  mov     ebx, eax
0x180098aad  test    eax, eax
0x180098aaf  js      loc_180098CF9
0x180098ab5  cmp     word ptr [rdi], 3Dh ; '='
0x180098ab9  jnz     short loc_180098AD8
0x180098abb  mov     r9, rdi; unsigned __int16 *
0x180098abe  xor     r8d, r8d; unsigned __int16 *
0x180098ac1  lea     rdx, [rsp+2300h+var_2290]; struct ATL::CRegKey *
0x180098ac6  mov     rcx, rsi; this
0x180098ac9  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180098ace  mov     ebx, eax
0x180098ad0  test    eax, eax
0x180098ad2  js      loc_180098CF9
0x180098ad8  cmp     word ptr [rdi], 7Bh ; '{'
0x180098adc  jnz     loc_1800987D0
0x180098ae2  or      rax, 0FFFFFFFFFFFFFFFFh
0x180098ae6  inc     rax
0x180098ae9  cmp     [rdi+rax*2], r14w
0x180098aee  jnz     short loc_180098AE6
0x180098af0  cmp     rax, 1
0x180098af4  jnz     loc_1800987D0
0x180098afa  mov     dword ptr [rsp+2300h+dwOptions], r14d; int
0x180098aff  mov     r9d, r15d; int
0x180098b02  mov     r8, [rsp+2300h+var_2290]; HKEY
0x180098b07  mov     rdx, rdi; unsigned __int16 *
0x180098b0a  mov     rcx, rsi; this
0x180098b0d  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180098b12  mov     ebx, eax
0x180098b14  test    eax, eax
0x180098b16  js      loc_180098CF9
0x180098b1c  mov     rdx, rdi
0x180098b1f  mov     rcx, rsi
0x180098b22  jmp     loc_1800987C1
0x180098b27  cmp     [rbp+2200h+arg_20], r14d
0x180098b2e  jnz     short loc_180098B4B
0x180098b30  mov     r9d, 20019h; unsigned int
0x180098b36  mov     r8, rdi; lpSubKey
0x180098b39  mov     rdx, r13; hKey
0x180098b3c  lea     rcx, [rsp+2300h+var_2290]; this
0x180098b41  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180098b46  mov     r14d, eax
0x180098b49  jmp     short loc_180098B51
0x180098b4b  mov     r14d, 2
0x180098b51  mov     r15d, 1
0x180098b57  test    r14d, r14d
0x180098b5a  cmovz   r15d, [rbp+2200h+arg_20]
0x180098b62  or      r9, 0FFFFFFFFFFFFFFFFh
0x180098b66  mov     r8, rdi
0x180098b69  mov     edx, 104h
0x180098b6e  lea     rcx, [rbp+2200h+var_2260]
0x180098b72  call    cs:__imp__o_wcsncpy_s
0x180098b78  mov     ecx, eax; int
0x180098b7a  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180098b7f  mov     rdx, rdi; unsigned __int16 *
0x180098b82  mov     rcx, rsi; this
0x180098b85  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180098b8a  mov     ebx, eax
0x180098b8c  test    eax, eax
0x180098b8e  js      loc_180098CF9
0x180098b94  mov     rdx, rdi; unsigned __int16 *
0x180098b97  mov     rcx, rsi; this
0x180098b9a  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180098b9f  mov     ebx, eax
0x180098ba1  xor     ecx, ecx
0x180098ba3  test    eax, eax
0x180098ba5  js      loc_180098CF9
0x180098bab  cmp     word ptr [rdi], 7Bh ; '{'
0x180098baf  jnz     short loc_180098C00
0x180098bb1  or      rax, 0FFFFFFFFFFFFFFFFh
0x180098bb5  inc     rax
0x180098bb8  cmp     [rdi+rax*2], cx
0x180098bbc  jnz     short loc_180098BB5
0x180098bbe  cmp     rax, 1
0x180098bc2  jnz     short loc_180098C00
0x180098bc4  mov     dword ptr [rsp+2300h+dwOptions], r15d; int
0x180098bc9  xor     r9d, r9d; int
0x180098bcc  mov     r8, [rsp+2300h+var_2290]; HKEY
0x180098bd1  mov     rdx, rdi; unsigned __int16 *
0x180098bd4  mov     rcx, rsi; this
0x180098bd7  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180098bdc  mov     ebx, eax
0x180098bde  test    eax, eax
0x180098be0  jns     short loc_180098BEB
0x180098be2  test    r15d, r15d
0x180098be5  jz      loc_180098CF9
0x180098beb  mov     rdx, rdi; unsigned __int16 *
0x180098bee  mov     rcx, rsi; this
0x180098bf1  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180098bf6  mov     ebx, eax
0x180098bf8  test    eax, eax
0x180098bfa  js      loc_180098CF9
0x180098c00  cmp     r14d, 2
0x180098c04  mov     r15d, [rsp+2300h+var_22B0]
  ... truncated ...
```
