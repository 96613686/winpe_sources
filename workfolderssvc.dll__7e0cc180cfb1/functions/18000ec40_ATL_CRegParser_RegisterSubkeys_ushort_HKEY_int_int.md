# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x18000ec40`
- end: `0x18000f22f`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1519`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x18000e74c`
- `0x18000ec40`

## callees

- `0x180002ab0`
- `0x180009fbc`
- `0x18000a754`
- `0x18000a7c4`
- `0x18000a9a8`
- `0x18000ae68`
- `0x18000b0c8`
- `0x18000cbc8`
- `0x18000dd70`
- `0x18000e2d8`
- `0x18000e638`
- `0x18000ec40`
- `0x18000ff08`
- `0x180010330`
- `0x180124400`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000f044`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000f044`
- `KERNEL32!lstrcmpiW` at `0x18000ecbc`
- `KERNEL32!lstrcmpiW` at `0x18000eccf`
- `KERNEL32!lstrcmpiW` at `0x18000eda1`
- `KERNEL32!lstrcmpiW` at `0x18000edd0`
- `KERNEL32!lstrcmpiW` at `0x18000ecbc`
- `KERNEL32!lstrcmpiW` at `0x18000eccf`
- `KERNEL32!lstrcmpiW` at `0x18000eda1`
- `KERNEL32!lstrcmpiW` at `0x18000edd0`
- `ADVAPI32!RegCreateKeyExW` at `0x18000ef45`
- `ADVAPI32!RegCreateKeyExW` at `0x18000ef45`
- `ADVAPI32!RegDeleteValueW` at `0x18000ee92`
- `ADVAPI32!RegDeleteValueW` at `0x18000ee92`

## string_xrefs

- `0x18000ecc5`: `ForceRemove`
- `0x18000ed97`: `NoRemove`
- `0x18000ecb2`: `Delete`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
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
  HKEY *v14; // rcx
  int v15; // r12d
  LSTATUS v16; // eax
  LSTATUS v17; // ecx
  __int64 v18; // rax
  int v19; // r14d
  int v20; // r15d
  int v21; // eax
  ATL::CRegParser *v22; // rcx
  __int64 v23; // rax
  int HasSubKeys; // r14d
  LSTATUS v25; // eax
  unsigned int v26; // eax
  __int64 dwOptions; // [rsp+20h] [rbp-E0h]
  HKEY v30[3]; // [rsp+58h] [rbp-A8h] BYREF
  DWORD dwDisposition; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v32[3]; // [rsp+78h] [rbp-88h] BYREF
  HKEY phkResult; // [rsp+90h] [rbp-70h] BYREF
  HKEY v34[3]; // [rsp+98h] [rbp-68h] BYREF
  HKEY hKey[3]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v36[3]; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int16 v37[264]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR ValueName[4096]; // [rsp+2F0h] [rbp+1F0h] BYREF

  v5 = a4;
  v7 = a2;
  v8 = this;
  memset(v30, 0, sizeof(v30));
LABEL_2:
  Token = ATL::CRegParser::NextToken(this, a2);
  while ( 2 )
  {
    v10 = Token;
    if ( Token < 0 )
      goto LABEL_80;
    while ( 1 )
    {
      if ( *v7 == 125 )
        goto LABEL_80;
      v11 = lstrcmpiW(v7, L"Delete");
      if ( !lstrcmpiW(v7, L"ForceRemove") || !v11 )
      {
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_80;
        if ( v5 )
        {
          memset(v32, 0, sizeof(v32));
          if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
          {
            ATL::CRegKey::Close((ATL::CRegKey *)v32);
LABEL_79:
            v10 = -2147352567;
            goto LABEL_80;
          }
          if ( ATL::CRegParser::CanForceRemoveKey(v12, v7) )
          {
            v32[0] = a3;
            ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v32, v7);
            v32[0] = 0;
          }
          if ( !v11 )
          {
            v10 = ATL::CRegParser::NextToken(v8, v7);
            if ( v10 < 0 )
            {
              v14 = (HKEY *)v32;
              goto LABEL_82;
            }
            v13 = ATL::CRegParser::SkipAssignment(v8, v7);
            v10 = v13;
            v14 = (HKEY *)v32;
            goto LABEL_15;
          }
          ATL::CRegKey::Close((ATL::CRegKey *)v32);
        }
      }
      v15 = 1;
      if ( !lstrcmpiW(v7, L"NoRemove") )
      {
        v15 = 0;
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_80;
      }
      if ( !lstrcmpiW(v7, L"Val") )
        break;
      if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
        goto LABEL_79;
      if ( v5 )
      {
        if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v30, a3, v7, 0x2001Fu) )
        {
          if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v30, a3, v7, 0x20019u) )
          {
            dwDisposition = 0;
            phkResult = 0;
            v17 = RegCreateKeyExW(a3, v7, 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition);
            if ( v17 )
              goto LABEL_65;
            v17 = ATL::CRegKey::Close((ATL::CRegKey *)v30);
            v30[0] = phkResult;
            if ( v17 )
              goto LABEL_65;
          }
        }
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_80;
        if ( *v7 == 61 )
        {
          v10 = ATL::CRegParser::AddValue(v8, v30, 0, v7);
          if ( v10 < 0 )
            goto LABEL_80;
        }
LABEL_41:
        if ( *v7 == 123 )
        {
          v18 = -1;
          do
            ++v18;
          while ( v7[v18] );
          if ( v18 == 1 )
          {
            v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v30[0], v5, 0);
            if ( v10 < 0 )
              goto LABEL_80;
            a2 = v7;
            this = v8;
            goto LABEL_2;
          }
        }
      }
      else
      {
        if ( a5 )
          v19 = 2;
        else
          v19 = ATL::CRegKey::Open((ATL::CRegKey *)v30, a3, v7, 0x20019u);
        v20 = 1;
        if ( !v19 )
          v20 = a5;
        v21 = _o_wcsncpy_s(v37, 260, v7, -1, dwOptions);
        ATL::AtlCrtErrorCheck(v21);
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_80;
        v10 = ATL::CRegParser::SkipAssignment(v8, v7);
        v22 = 0;
        if ( v10 < 0 )
          goto LABEL_80;
        if ( *v7 == 123 )
        {
          v23 = -1;
          do
            ++v23;
          while ( v7[v23] );
          if ( v23 == 1 )
          {
            v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v30[0], 0, v20);
            if ( v10 < 0 && !v20 )
              goto LABEL_80;
            v10 = ATL::CRegParser::NextToken(v8, v7);
            if ( v10 < 0 )
              goto LABEL_80;
          }
        }
        v5 = a4;
        if ( v19 != 2 )
        {
          if ( v19 )
          {
            if ( !a5 )
            {
              v17 = v19;
LABEL_65:
              v10 = ATL::AtlHresultFromWin32(v17);
              goto LABEL_80;
            }
          }
          else if ( a5 && ATL::CRegParser::HasSubKeys(v22, v30[0]) )
          {
            if ( ATL::CRegParser::CanForceRemoveKey(v22, v37) && v15 )
              ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v30, v37);
          }
          else
          {
            HasSubKeys = ATL::CRegParser::HasSubKeys(v22, v30[0]);
            v25 = ATL::CRegKey::Close((ATL::CRegKey *)v30);
            if ( v25 )
            {
              v17 = v25;
              goto LABEL_65;
            }
            if ( v15 && !HasSubKeys )
            {
              v36[1] = 0;
              v36[2] = 0;
              v36[0] = a3;
              v26 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v36, v37);
              v36[0] = 0;
              if ( v26 )
              {
                v10 = ATL::AtlHresultFromWin32(v26);
                v14 = (HKEY *)v36;
                goto LABEL_82;
              }
              ATL::CRegKey::Close((ATL::CRegKey *)v36);
              v5 = a4;
            }
          }
        }
      }
    }
    v10 = ATL::CRegParser::NextToken(v8, ValueName);
    if ( v10 < 0 )
      goto LABEL_80;
    v10 = ATL::CRegParser::NextToken(v8, v7);
    if ( v10 < 0 )
      goto LABEL_80;
    if ( *v7 != 61 )
      goto LABEL_79;
    if ( v5 )
    {
      v34[1] = 0;
      v34[2] = 0;
      v34[0] = a3;
      v13 = ATL::CRegParser::AddValue(v8, v34, ValueName, v7);
      v10 = v13;
      v34[0] = 0;
      v14 = v34;
LABEL_15:
      if ( v13 < 0 )
        goto LABEL_82;
      ATL::CRegKey::Close((ATL::CRegKey *)v14);
      goto LABEL_41;
    }
    if ( a5 || !v15 )
      goto LABEL_31;
    memset(hKey, 0, sizeof(hKey));
    v16 = ATL::CRegKey::Open((ATL::CRegKey *)hKey, a3, 0, 0x20006u);
    if ( !v16 )
    {
      v16 = RegDeleteValueW(hKey[0], ValueName);
      if ( (v16 & 0xFFFFFFFD) == 0 )
      {
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
LABEL_31:
        Token = ATL::CRegParser::SkipAssignment(v8, v7);
        continue;
      }
    }
    break;
  }
  v10 = ATL::AtlHresultFromWin32(v16);
  v14 = hKey;
LABEL_82:
  ATL::CRegKey::Close((ATL::CRegKey *)v14);
LABEL_80:
  ATL::CRegKey::Close((ATL::CRegKey *)v30);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000ec40  push    rbp
0x18000ec42  push    rbx
0x18000ec43  push    rsi
0x18000ec44  push    rdi
0x18000ec45  push    r12
0x18000ec47  push    r13
0x18000ec49  push    r14
0x18000ec4b  push    r15
0x18000ec4d  lea     rbp, [rsp-2208h]
0x18000ec55  mov     eax, 2308h
0x18000ec5a  call    _alloca_probe
0x18000ec5f  sub     rsp, rax
0x18000ec62  mov     rax, cs:__security_cookie
0x18000ec69  xor     rax, rsp
0x18000ec6c  mov     [rbp+2240h+var_50], rax
0x18000ec73  mov     r15d, r9d
0x18000ec76  mov     [rsp+2340h+var_22F0], r9d
0x18000ec7b  mov     r13, r8
0x18000ec7e  mov     rdi, rdx
0x18000ec81  mov     rsi, rcx
0x18000ec84  xor     r14d, r14d
0x18000ec87  mov     [rsp+2340h+var_22E8], r14
0x18000ec8c  mov     [rsp+2340h+var_22E0], r14
0x18000ec91  mov     [rsp+2340h+var_22D8], r14
0x18000ec96  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000ec9b  test    eax, eax
0x18000ec9d  mov     ebx, eax
0x18000ec9f  js      loc_18000F1D5
0x18000eca5  xor     r12d, r12d
0x18000eca8  cmp     word ptr [rdi], 7Dh ; '}'
0x18000ecac  jz      loc_18000F1D5
0x18000ecb2  lea     rdx, String2; "Delete"
0x18000ecb9  mov     rcx, rdi; lpString1
0x18000ecbc  call    cs:__imp_lstrcmpiW
0x18000ecc2  mov     r14d, eax
0x18000ecc5  lea     rdx, aForceremove; "ForceRemove"
0x18000eccc  mov     rcx, rdi; lpString1
0x18000eccf  call    cs:__imp_lstrcmpiW
0x18000ecd5  test    eax, eax
0x18000ecd7  jz      short loc_18000ECE2
0x18000ecd9  test    r14d, r14d
0x18000ecdc  jnz     loc_18000ED91
0x18000ece2  mov     rdx, rdi; unsigned __int16 *
0x18000ece5  mov     rcx, rsi; this
0x18000ece8  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000eced  mov     ebx, eax
0x18000ecef  test    eax, eax
0x18000ecf1  js      loc_18000F1D5
0x18000ecf7  test    r15d, r15d
0x18000ecfa  jz      loc_18000ED91
0x18000ed00  mov     [rsp+2340h+var_22C8], r12
0x18000ed05  mov     [rbp+2240h+var_22C0], r12
0x18000ed09  mov     [rbp+2240h+var_22B8], r12
0x18000ed0d  mov     edx, 5Ch ; '\'; unsigned __int16
0x18000ed12  mov     rcx, rdi; lpsz
0x18000ed15  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18000ed1a  test    rax, rax
0x18000ed1d  jnz     loc_18000F1C6
0x18000ed23  mov     rdx, rdi; unsigned __int16 *
0x18000ed26  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x18000ed2b  test    eax, eax
0x18000ed2d  jz      short loc_18000ED46
0x18000ed2f  mov     [rsp+2340h+var_22C8], r13
0x18000ed34  mov     rdx, rdi; unsigned __int16 *
0x18000ed37  lea     rcx, [rsp+2340h+var_22C8]; this
0x18000ed3c  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18000ed41  mov     [rsp+2340h+var_22C8], r12
0x18000ed46  test    r14d, r14d
0x18000ed49  jnz     short loc_18000ED87
0x18000ed4b  mov     rdx, rdi; unsigned __int16 *
0x18000ed4e  mov     rcx, rsi; this
0x18000ed51  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000ed56  mov     ebx, eax
0x18000ed58  xor     r14d, r14d
0x18000ed5b  test    eax, eax
0x18000ed5d  js      loc_18000F1BF
0x18000ed63  mov     rdx, rdi; unsigned __int16 *
0x18000ed66  mov     rcx, rsi; this
0x18000ed69  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18000ed6e  mov     ebx, eax
0x18000ed70  lea     rcx, [rsp+2340h+var_22C8]; this
0x18000ed75  test    eax, eax
0x18000ed77  js      loc_18000F211
0x18000ed7d  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000ed82  jmp     loc_18000EFAA
0x18000ed87  lea     rcx, [rsp+2340h+var_22C8]; this
0x18000ed8c  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000ed91  mov     r12d, 1
0x18000ed97  lea     rdx, aNoremove; "NoRemove"
0x18000ed9e  mov     rcx, rdi; lpString1
0x18000eda1  call    cs:__imp_lstrcmpiW
0x18000eda7  xor     r14d, r14d
0x18000edaa  test    eax, eax
0x18000edac  jnz     short loc_18000EDC6
0x18000edae  mov     r12d, r14d
0x18000edb1  mov     rdx, rdi; unsigned __int16 *
0x18000edb4  mov     rcx, rsi; this
0x18000edb7  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000edbc  mov     ebx, eax
0x18000edbe  test    eax, eax
0x18000edc0  js      loc_18000F1D5
0x18000edc6  lea     rdx, aVal; "Val"
0x18000edcd  mov     rcx, rdi; lpString1
0x18000edd0  call    cs:__imp_lstrcmpiW
0x18000edd6  test    eax, eax
0x18000edd8  jnz     loc_18000EEBC
0x18000edde  lea     rdx, [rbp+2240h+ValueName]; unsigned __int16 *
0x18000ede5  mov     rcx, rsi; this
0x18000ede8  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000eded  mov     ebx, eax
0x18000edef  test    eax, eax
0x18000edf1  js      loc_18000F1D5
0x18000edf7  mov     rdx, rdi; unsigned __int16 *
0x18000edfa  mov     rcx, rsi; this
0x18000edfd  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000ee02  mov     ebx, eax
0x18000ee04  test    eax, eax
0x18000ee06  js      loc_18000F1D5
0x18000ee0c  cmp     word ptr [rdi], 3Dh ; '='
0x18000ee10  jnz     loc_18000F1D0
0x18000ee16  test    r15d, r15d
0x18000ee19  jz      short loc_18000EE50
0x18000ee1b  mov     [rbp+2240h+var_22A8], r14
0x18000ee1f  mov     [rbp+2240h+var_22A0], r14
0x18000ee23  mov     [rbp+2240h+var_2298], r14
0x18000ee27  mov     [rbp+2240h+var_22A8], r13
0x18000ee2b  mov     r9, rdi; unsigned __int16 *
0x18000ee2e  lea     r8, [rbp+2240h+ValueName]; unsigned __int16 *
0x18000ee35  lea     rdx, [rbp+2240h+var_22A8]; struct ATL::CRegKey *
0x18000ee39  mov     rcx, rsi; this
0x18000ee3c  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18000ee41  mov     ebx, eax
0x18000ee43  mov     [rbp+2240h+var_22A8], r14
0x18000ee47  lea     rcx, [rbp+2240h+var_22A8]
0x18000ee4b  jmp     loc_18000ED75
0x18000ee50  cmp     [rbp+2240h+arg_20], r14d
0x18000ee57  jnz     short loc_18000EEAC
0x18000ee59  test    r12d, r12d
0x18000ee5c  jz      short loc_18000EEAC
0x18000ee5e  mov     [rbp+2240h+hKey], r14
0x18000ee62  mov     [rbp+2240h+var_2288], r14
0x18000ee66  mov     [rbp+2240h+var_2280], r14
0x18000ee6a  mov     r9d, 20006h; unsigned int
0x18000ee70  xor     r8d, r8d; lpSubKey
0x18000ee73  mov     rdx, r13; hKey
0x18000ee76  lea     rcx, [rbp+2240h+hKey]; this
0x18000ee7a  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000ee7f  test    eax, eax
0x18000ee81  jnz     loc_18000F204
0x18000ee87  lea     rdx, [rbp+2240h+ValueName]; lpValueName
0x18000ee8e  mov     rcx, [rbp+2240h+hKey]; hKey
0x18000ee92  call    cs:__imp_RegDeleteValueW
0x18000ee98  test    eax, 0FFFFFFFDh
0x18000ee9d  jnz     loc_18000F204
0x18000eea3  lea     rcx, [rbp+2240h+hKey]; this
0x18000eea7  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000eeac  mov     rdx, rdi; unsigned __int16 *
0x18000eeaf  mov     rcx, rsi; this
0x18000eeb2  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18000eeb7  jmp     loc_18000EC9B
0x18000eebc  mov     edx, 5Ch ; '\'; unsigned __int16
0x18000eec1  mov     rcx, rdi; lpsz
0x18000eec4  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18000eec9  test    rax, rax
0x18000eecc  jnz     loc_18000F1D0
0x18000eed2  test    r15d, r15d
0x18000eed5  jz      loc_18000EFF9
0x18000eedb  mov     ebx, 2001Fh
0x18000eee0  mov     r9d, ebx; unsigned int
0x18000eee3  mov     r8, rdi; lpSubKey
0x18000eee6  mov     rdx, r13; hKey
0x18000eee9  lea     rcx, [rsp+2340h+var_22E8]; this
0x18000eeee  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000eef3  test    eax, eax
0x18000eef5  jz      short loc_18000EF72
0x18000eef7  lea     r9d, [rbx-6]; unsigned int
0x18000eefb  mov     r8, rdi; lpSubKey
0x18000eefe  mov     rdx, r13; hKey
0x18000ef01  lea     rcx, [rsp+2340h+var_22E8]; this
0x18000ef06  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000ef0b  test    eax, eax
0x18000ef0d  jz      short loc_18000EF72
0x18000ef0f  mov     [rsp+2340h+dwDisposition], r14d
0x18000ef14  mov     [rbp+2240h+var_22B0], r14
0x18000ef18  lea     rax, [rsp+2340h+dwDisposition]
0x18000ef1d  mov     [rsp+2340h+lpdwDisposition], rax; lpdwDisposition
0x18000ef22  lea     rax, [rbp+2240h+var_22B0]
0x18000ef26  mov     [rsp+2340h+phkResult], rax; phkResult
0x18000ef2b  mov     [rsp+2340h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18000ef30  mov     [rsp+2340h+samDesired], ebx; samDesired
0x18000ef34  mov     dword ptr [rsp+2340h+dwOptions], r14d; dwOptions
0x18000ef39  xor     r9d, r9d; lpClass
0x18000ef3c  xor     r8d, r8d; Reserved
0x18000ef3f  mov     rdx, rdi; lpSubKey
0x18000ef42  mov     rcx, r13; hKey
0x18000ef45  call    cs:__imp_RegCreateKeyExW
0x18000ef4b  mov     ecx, eax
0x18000ef4d  test    eax, eax
0x18000ef4f  jnz     loc_18000F0F9
0x18000ef55  lea     rcx, [rsp+2340h+var_22E8]; this
0x18000ef5a  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000ef5f  mov     ecx, eax
0x18000ef61  mov     rax, [rbp+2240h+var_22B0]
0x18000ef65  mov     [rsp+2340h+var_22E8], rax
0x18000ef6a  test    ecx, ecx
0x18000ef6c  jnz     loc_18000F0F9
0x18000ef72  mov     rdx, rdi; unsigned __int16 *
0x18000ef75  mov     rcx, rsi; this
0x18000ef78  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000ef7d  mov     ebx, eax
0x18000ef7f  test    eax, eax
0x18000ef81  js      loc_18000F1D5
0x18000ef87  cmp     word ptr [rdi], 3Dh ; '='
0x18000ef8b  jnz     short loc_18000EFAA
0x18000ef8d  mov     r9, rdi; unsigned __int16 *
0x18000ef90  xor     r8d, r8d; unsigned __int16 *
0x18000ef93  lea     rdx, [rsp+2340h+var_22E8]; struct ATL::CRegKey *
0x18000ef98  mov     rcx, rsi; this
0x18000ef9b  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18000efa0  mov     ebx, eax
0x18000efa2  test    eax, eax
0x18000efa4  js      loc_18000F1D5
0x18000efaa  cmp     word ptr [rdi], 7Bh ; '{'
0x18000efae  jnz     loc_18000ECA5
0x18000efb4  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000efb8  inc     rax
0x18000efbb  cmp     [rdi+rax*2], r14w
0x18000efc0  jnz     short loc_18000EFB8
0x18000efc2  cmp     rax, 1
0x18000efc6  jnz     loc_18000ECA5
0x18000efcc  mov     dword ptr [rsp+2340h+dwOptions], r14d; int
0x18000efd1  mov     r9d, r15d; int
0x18000efd4  mov     r8, [rsp+2340h+var_22E8]; HKEY
0x18000efd9  mov     rdx, rdi; unsigned __int16 *
0x18000efdc  mov     rcx, rsi; this
0x18000efdf  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000efe4  mov     ebx, eax
0x18000efe6  test    eax, eax
0x18000efe8  js      loc_18000F1D5
0x18000efee  mov     rdx, rdi
0x18000eff1  mov     rcx, rsi
0x18000eff4  jmp     loc_18000EC96
0x18000eff9  cmp     [rbp+2240h+arg_20], r14d
0x18000f000  jnz     short loc_18000F01D
0x18000f002  mov     r9d, 20019h; unsigned int
0x18000f008  mov     r8, rdi; lpSubKey
0x18000f00b  mov     rdx, r13; hKey
0x18000f00e  lea     rcx, [rsp+2340h+var_22E8]; this
0x18000f013  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000f018  mov     r14d, eax
0x18000f01b  jmp     short loc_18000F023
0x18000f01d  mov     r14d, 2
0x18000f023  mov     r15d, 1
0x18000f029  test    r14d, r14d
0x18000f02c  cmovz   r15d, [rbp+2240h+arg_20]
0x18000f034  or      r9, 0FFFFFFFFFFFFFFFFh
0x18000f038  mov     r8, rdi
0x18000f03b  mov     edx, 104h
0x18000f040  lea     rcx, [rbp+2240h+var_2260]
0x18000f044  call    cs:__imp__o_wcsncpy_s
0x18000f04a  mov     ecx, eax; int
0x18000f04c  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000f051  mov     rdx, rdi; unsigned __int16 *
0x18000f054  mov     rcx, rsi; this
0x18000f057  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000f05c  mov     ebx, eax
0x18000f05e  test    eax, eax
0x18000f060  js      loc_18000F1D5
0x18000f066  mov     rdx, rdi; unsigned __int16 *
0x18000f069  mov     rcx, rsi; this
0x18000f06c  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18000f071  mov     ebx, eax
0x18000f073  xor     ecx, ecx
0x18000f075  test    eax, eax
0x18000f077  js      loc_18000F1D5
0x18000f07d  cmp     word ptr [rdi], 7Bh ; '{'
0x18000f081  jnz     short loc_18000F0D2
0x18000f083  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000f087  inc     rax
0x18000f08a  cmp     [rdi+rax*2], cx
0x18000f08e  jnz     short loc_18000F087
0x18000f090  cmp     rax, 1
0x18000f094  jnz     short loc_18000F0D2
0x18000f096  mov     dword ptr [rsp+2340h+dwOptions], r15d; int
0x18000f09b  xor     r9d, r9d; int
0x18000f09e  mov     r8, [rsp+2340h+var_22E8]; HKEY
0x18000f0a3  mov     rdx, rdi; unsigned __int16 *
0x18000f0a6  mov     rcx, rsi; this
0x18000f0a9  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000f0ae  mov     ebx, eax
0x18000f0b0  test    eax, eax
0x18000f0b2  jns     short loc_18000F0BD
0x18000f0b4  test    r15d, r15d
0x18000f0b7  jz      loc_18000F1D5
0x18000f0bd  mov     rdx, rdi; unsigned __int16 *
0x18000f0c0  mov     rcx, rsi; this
0x18000f0c3  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000f0c8  mov     ebx, eax
0x18000f0ca  test    eax, eax
0x18000f0cc  js      loc_18000F1D5
  ... truncated ...
```
