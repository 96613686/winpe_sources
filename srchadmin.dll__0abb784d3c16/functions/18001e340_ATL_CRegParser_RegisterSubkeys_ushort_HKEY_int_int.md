# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x18001e340`
- end: `0x18001e919`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1497`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x18001e01c`
- `0x18001e340`

## callees

- `0x180005cc0`
- `0x180012f8c`
- `0x18001b08c`
- `0x18001b8e0`
- `0x18001b8f8`
- `0x18001ba14`
- `0x18001c77c`
- `0x18001cd64`
- `0x18001d3b0`
- `0x18001d510`
- `0x18001df08`
- `0x18001e340`
- `0x18001eef4`
- `0x18001efc4`
- `0x180030350`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18001e746`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18001e746`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001e647`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001e647`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001e595`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001e595`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001e3bb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001e3ce`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001e4a2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001e4d1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001e3bb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001e3ce`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001e4a2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001e4d1`

## string_xrefs

- `0x18001e3c4`: `ForceRemove`
- `0x18001e498`: `NoRemove`
- `0x18001e3b1`: `Delete`

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
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v28; // [rsp+60h] [rbp-A0h]
  __int64 v29; // [rsp+68h] [rbp-98h]
  HKEY v30[3]; // [rsp+70h] [rbp-90h] BYREF
  DWORD dwDisposition; // [rsp+88h] [rbp-78h] BYREF
  HKEY phkResult; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v33[264]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR ValueName[4096]; // [rsp+2B0h] [rbp+1B0h] BYREF

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
          v28 = 0;
          v29 = 0;
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
        if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v30, a3, v7, 0x2001Fu) )
        {
          if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v30, a3, v7, 0x20019u) )
          {
            dwDisposition = 0;
            phkResult = 0;
            v16 = RegCreateKeyExW(a3, v7, 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition);
            if ( v16 )
              goto LABEL_65;
            v16 = ATL::CRegKey::Close((ATL::CRegKey *)v30);
            v30[0] = phkResult;
            if ( v16 )
              goto LABEL_65;
          }
        }
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_79;
        if ( *v7 == 61 )
        {
          v10 = ATL::CRegParser::AddValue(v8, v30, 0, v7);
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
            v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v30[0], v5, 0);
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
          v18 = ATL::CRegKey::Open((ATL::CRegKey *)v30, a3, v7, 0x20019u);
        v19 = 1;
        if ( !v18 )
          v19 = a5;
        v20 = _o_wcsncpy_s(v33, 260, v7, -1);
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
            v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v30[0], 0, v19);
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
          else if ( a5 && ATL::CRegParser::HasSubKeys(v21, v30[0]) )
          {
            if ( (unsigned int)ATL::CRegParser::CanForceRemoveKey(v21, v33) && v14 )
              ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v30, v33);
          }
          else
          {
            HasSubKeys = ATL::CRegParser::HasSubKeys(v21, v30[0]);
            v24 = ATL::CRegKey::Close((ATL::CRegKey *)v30);
            if ( v24 )
            {
              v16 = v24;
              goto LABEL_65;
            }
            if ( v14 && !HasSubKeys )
            {
              v28 = 0;
              v29 = 0;
              hKey = a3;
              v15 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&hKey, v33);
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
      v28 = 0;
      v29 = 0;
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
    v28 = 0;
    v29 = 0;
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
  ATL::CRegKey::Close((ATL::CRegKey *)v30);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18001e340  push    rbp
0x18001e342  push    rbx
0x18001e343  push    rsi
0x18001e344  push    rdi
0x18001e345  push    r12
0x18001e347  push    r13
0x18001e349  push    r14
0x18001e34b  push    r15
0x18001e34d  lea     rbp, [rsp-21C8h]
0x18001e355  mov     eax, 22C8h
0x18001e35a  call    _alloca_probe
0x18001e35f  sub     rsp, rax
0x18001e362  mov     rax, cs:__security_cookie
0x18001e369  xor     rax, rsp
0x18001e36c  mov     [rbp+2200h+var_50], rax
0x18001e373  mov     r15d, r9d
0x18001e376  mov     [rsp+2300h+var_22B0], r9d
0x18001e37b  mov     r13, r8
0x18001e37e  mov     rdi, rdx
0x18001e381  mov     rsi, rcx
0x18001e384  xor     r14d, r14d
0x18001e387  mov     [rsp+2300h+var_2290], r14
0x18001e38c  mov     [rsp+2300h+var_2288], r14
0x18001e391  mov     [rbp+2200h+var_2280], r14
0x18001e395  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001e39a  test    eax, eax
0x18001e39c  mov     ebx, eax
0x18001e39e  js      loc_18001E8CD
0x18001e3a4  xor     r12d, r12d
0x18001e3a7  cmp     word ptr [rdi], 7Dh ; '}'
0x18001e3ab  jz      loc_18001E8CD
0x18001e3b1  lea     rdx, aDelete; "Delete"
0x18001e3b8  mov     rcx, rdi; lpString1
0x18001e3bb  call    cs:__imp_lstrcmpiW
0x18001e3c1  mov     r14d, eax
0x18001e3c4  lea     rdx, aForceremove; "ForceRemove"
0x18001e3cb  mov     rcx, rdi; lpString1
0x18001e3ce  call    cs:__imp_lstrcmpiW
0x18001e3d4  test    eax, eax
0x18001e3d6  jz      short loc_18001E3E1
0x18001e3d8  test    r14d, r14d
0x18001e3db  jnz     loc_18001E492
0x18001e3e1  mov     rdx, rdi; unsigned __int16 *
0x18001e3e4  mov     rcx, rsi; this
0x18001e3e7  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001e3ec  mov     ebx, eax
0x18001e3ee  test    eax, eax
0x18001e3f0  js      loc_18001E8CD
0x18001e3f6  test    r15d, r15d
0x18001e3f9  jz      loc_18001E492
0x18001e3ff  mov     [rsp+2300h+hKey], r12
0x18001e404  mov     [rsp+2300h+var_22A0], r12
0x18001e409  mov     [rsp+2300h+var_2298], r12
0x18001e40e  mov     edx, 5Ch ; '\'; unsigned __int16
0x18001e413  mov     rcx, rdi; lpsz
0x18001e416  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18001e41b  test    rax, rax
0x18001e41e  jnz     loc_18001E8BE
0x18001e424  mov     rdx, rdi; unsigned __int16 *
0x18001e427  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x18001e42c  test    eax, eax
0x18001e42e  jz      short loc_18001E447
0x18001e430  mov     [rsp+2300h+hKey], r13
0x18001e435  mov     rdx, rdi; unsigned __int16 *
0x18001e438  lea     rcx, [rsp+2300h+hKey]; this
0x18001e43d  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18001e442  mov     [rsp+2300h+hKey], r12
0x18001e447  test    r14d, r14d
0x18001e44a  jnz     short loc_18001E488
0x18001e44c  mov     rdx, rdi; unsigned __int16 *
0x18001e44f  mov     rcx, rsi; this
0x18001e452  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001e457  mov     ebx, eax
0x18001e459  xor     r14d, r14d
0x18001e45c  test    eax, eax
0x18001e45e  js      loc_18001E905
0x18001e464  mov     rdx, rdi; unsigned __int16 *
0x18001e467  mov     rcx, rsi; this
0x18001e46a  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18001e46f  mov     ebx, eax
0x18001e471  test    eax, eax
0x18001e473  lea     rcx, [rsp+2300h+hKey]; this
0x18001e478  js      loc_18001E90A
0x18001e47e  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001e483  jmp     loc_18001E6AC
0x18001e488  lea     rcx, [rsp+2300h+hKey]; this
0x18001e48d  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001e492  mov     r12d, 1
0x18001e498  lea     rdx, aNoremove; "NoRemove"
0x18001e49f  mov     rcx, rdi; lpString1
0x18001e4a2  call    cs:__imp_lstrcmpiW
0x18001e4a8  xor     r14d, r14d
0x18001e4ab  test    eax, eax
0x18001e4ad  jnz     short loc_18001E4C7
0x18001e4af  mov     r12d, r14d
0x18001e4b2  mov     rdx, rdi; unsigned __int16 *
0x18001e4b5  mov     rcx, rsi; this
0x18001e4b8  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001e4bd  mov     ebx, eax
0x18001e4bf  test    eax, eax
0x18001e4c1  js      loc_18001E8CD
0x18001e4c7  lea     rdx, aVal; "Val"
0x18001e4ce  mov     rcx, rdi; lpString1
0x18001e4d1  call    cs:__imp_lstrcmpiW
0x18001e4d7  test    eax, eax
0x18001e4d9  jnz     loc_18001E5C0
0x18001e4df  lea     rdx, [rbp+2200h+ValueName]; unsigned __int16 *
0x18001e4e6  mov     rcx, rsi; this
0x18001e4e9  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001e4ee  mov     ebx, eax
0x18001e4f0  test    eax, eax
0x18001e4f2  js      loc_18001E8CD
0x18001e4f8  mov     rdx, rdi; unsigned __int16 *
0x18001e4fb  mov     rcx, rsi; this
0x18001e4fe  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001e503  mov     ebx, eax
0x18001e505  test    eax, eax
0x18001e507  js      loc_18001E8CD
0x18001e50d  cmp     word ptr [rdi], 3Dh ; '='
0x18001e511  jnz     loc_18001E8C8
0x18001e517  test    r15d, r15d
0x18001e51a  jz      short loc_18001E54E
0x18001e51c  mov     [rsp+2300h+var_22A0], r14
0x18001e521  mov     [rsp+2300h+var_2298], r14
0x18001e526  mov     [rsp+2300h+hKey], r13
0x18001e52b  mov     r9, rdi; unsigned __int16 *
0x18001e52e  lea     r8, [rbp+2200h+ValueName]; unsigned __int16 *
0x18001e535  lea     rdx, [rsp+2300h+hKey]; struct ATL::CRegKey *
0x18001e53a  mov     rcx, rsi; this
0x18001e53d  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18001e542  mov     ebx, eax
0x18001e544  mov     [rsp+2300h+hKey], r14
0x18001e549  jmp     loc_18001E471
0x18001e54e  cmp     [rbp+2200h+arg_20], r14d
0x18001e555  jnz     short loc_18001E5B0
0x18001e557  test    r12d, r12d
0x18001e55a  jz      short loc_18001E5B0
0x18001e55c  mov     [rsp+2300h+hKey], r14
0x18001e561  mov     [rsp+2300h+var_22A0], r14
0x18001e566  mov     [rsp+2300h+var_2298], r14
0x18001e56b  mov     r9d, 20006h; unsigned int
0x18001e571  xor     r8d, r8d; lpSubKey
0x18001e574  mov     rdx, r13; hKey
0x18001e577  lea     rcx, [rsp+2300h+hKey]; this
0x18001e57c  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18001e581  test    eax, eax
0x18001e583  jnz     loc_18001E8FC
0x18001e589  lea     rdx, [rbp+2200h+ValueName]; lpValueName
0x18001e590  mov     rcx, [rsp+2300h+hKey]; hKey
0x18001e595  call    cs:__imp_RegDeleteValueW
0x18001e59b  test    eax, 0FFFFFFFDh
0x18001e5a0  jnz     loc_18001E8FC
0x18001e5a6  lea     rcx, [rsp+2300h+hKey]; this
0x18001e5ab  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001e5b0  mov     rdx, rdi; unsigned __int16 *
0x18001e5b3  mov     rcx, rsi; this
0x18001e5b6  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18001e5bb  jmp     loc_18001E39A
0x18001e5c0  mov     edx, 5Ch ; '\'; unsigned __int16
0x18001e5c5  mov     rcx, rdi; lpsz
0x18001e5c8  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18001e5cd  test    rax, rax
0x18001e5d0  jnz     loc_18001E8C8
0x18001e5d6  test    r15d, r15d
0x18001e5d9  jz      loc_18001E6FB
0x18001e5df  mov     ebx, 2001Fh
0x18001e5e4  mov     r9d, ebx; unsigned int
0x18001e5e7  mov     r8, rdi; lpSubKey
0x18001e5ea  mov     rdx, r13; hKey
0x18001e5ed  lea     rcx, [rsp+2300h+var_2290]; this
0x18001e5f2  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18001e5f7  test    eax, eax
0x18001e5f9  jz      short loc_18001E674
0x18001e5fb  lea     r9d, [rbx-6]; unsigned int
0x18001e5ff  mov     r8, rdi; lpSubKey
0x18001e602  mov     rdx, r13; hKey
0x18001e605  lea     rcx, [rsp+2300h+var_2290]; this
0x18001e60a  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18001e60f  test    eax, eax
0x18001e611  jz      short loc_18001E674
0x18001e613  mov     [rbp+2200h+dwDisposition], r14d
0x18001e617  mov     [rbp+2200h+var_2270], r14
0x18001e61b  lea     rax, [rbp+2200h+dwDisposition]
0x18001e61f  mov     [rsp+2300h+lpdwDisposition], rax; lpdwDisposition
0x18001e624  lea     rax, [rbp+2200h+var_2270]
0x18001e628  mov     [rsp+2300h+phkResult], rax; phkResult
0x18001e62d  mov     [rsp+2300h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18001e632  mov     [rsp+2300h+samDesired], ebx; samDesired
0x18001e636  mov     [rsp+2300h+dwOptions], r14d; dwOptions
0x18001e63b  xor     r9d, r9d; lpClass
0x18001e63e  xor     r8d, r8d; Reserved
0x18001e641  mov     rdx, rdi; lpSubKey
0x18001e644  mov     rcx, r13; hKey
0x18001e647  call    cs:__imp_RegCreateKeyExW
0x18001e64d  mov     ecx, eax
0x18001e64f  test    eax, eax
0x18001e651  jnz     loc_18001E7FB
0x18001e657  lea     rcx, [rsp+2300h+var_2290]; this
0x18001e65c  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001e661  mov     ecx, eax
0x18001e663  mov     rax, [rbp+2200h+var_2270]
0x18001e667  mov     [rsp+2300h+var_2290], rax
0x18001e66c  test    ecx, ecx
0x18001e66e  jnz     loc_18001E7FB
0x18001e674  mov     rdx, rdi; unsigned __int16 *
0x18001e677  mov     rcx, rsi; this
0x18001e67a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001e67f  mov     ebx, eax
0x18001e681  test    eax, eax
0x18001e683  js      loc_18001E8CD
0x18001e689  cmp     word ptr [rdi], 3Dh ; '='
0x18001e68d  jnz     short loc_18001E6AC
0x18001e68f  mov     r9, rdi; unsigned __int16 *
0x18001e692  xor     r8d, r8d; unsigned __int16 *
0x18001e695  lea     rdx, [rsp+2300h+var_2290]; struct ATL::CRegKey *
0x18001e69a  mov     rcx, rsi; this
0x18001e69d  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18001e6a2  mov     ebx, eax
0x18001e6a4  test    eax, eax
0x18001e6a6  js      loc_18001E8CD
0x18001e6ac  cmp     word ptr [rdi], 7Bh ; '{'
0x18001e6b0  jnz     loc_18001E3A4
0x18001e6b6  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001e6ba  inc     rax
0x18001e6bd  cmp     [rdi+rax*2], r14w
0x18001e6c2  jnz     short loc_18001E6BA
0x18001e6c4  cmp     rax, 1
0x18001e6c8  jnz     loc_18001E3A4
0x18001e6ce  mov     [rsp+2300h+dwOptions], r14d; int
0x18001e6d3  mov     r9d, r15d; int
0x18001e6d6  mov     r8, [rsp+2300h+var_2290]; HKEY
0x18001e6db  mov     rdx, rdi; unsigned __int16 *
0x18001e6de  mov     rcx, rsi; this
0x18001e6e1  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18001e6e6  mov     ebx, eax
0x18001e6e8  test    eax, eax
0x18001e6ea  js      loc_18001E8CD
0x18001e6f0  mov     rdx, rdi
0x18001e6f3  mov     rcx, rsi
0x18001e6f6  jmp     loc_18001E395
0x18001e6fb  cmp     [rbp+2200h+arg_20], r14d
0x18001e702  jnz     short loc_18001E71F
0x18001e704  mov     r9d, 20019h; unsigned int
0x18001e70a  mov     r8, rdi; lpSubKey
0x18001e70d  mov     rdx, r13; hKey
0x18001e710  lea     rcx, [rsp+2300h+var_2290]; this
0x18001e715  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18001e71a  mov     r14d, eax
0x18001e71d  jmp     short loc_18001E725
0x18001e71f  mov     r14d, 2
0x18001e725  mov     r15d, 1
0x18001e72b  test    r14d, r14d
0x18001e72e  cmovz   r15d, [rbp+2200h+arg_20]
0x18001e736  or      r9, 0FFFFFFFFFFFFFFFFh
0x18001e73a  mov     r8, rdi
0x18001e73d  mov     edx, 104h
0x18001e742  lea     rcx, [rbp+2200h+var_2260]
0x18001e746  call    cs:__imp__o_wcsncpy_s
0x18001e74c  mov     ecx, eax; int
0x18001e74e  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18001e753  mov     rdx, rdi; unsigned __int16 *
0x18001e756  mov     rcx, rsi; this
0x18001e759  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001e75e  mov     ebx, eax
0x18001e760  test    eax, eax
0x18001e762  js      loc_18001E8CD
0x18001e768  mov     rdx, rdi; unsigned __int16 *
0x18001e76b  mov     rcx, rsi; this
0x18001e76e  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18001e773  mov     ebx, eax
0x18001e775  xor     ecx, ecx
0x18001e777  test    eax, eax
0x18001e779  js      loc_18001E8CD
0x18001e77f  cmp     word ptr [rdi], 7Bh ; '{'
0x18001e783  jnz     short loc_18001E7D4
0x18001e785  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001e789  inc     rax
0x18001e78c  cmp     [rdi+rax*2], cx
0x18001e790  jnz     short loc_18001E789
0x18001e792  cmp     rax, 1
0x18001e796  jnz     short loc_18001E7D4
0x18001e798  mov     [rsp+2300h+dwOptions], r15d; int
0x18001e79d  xor     r9d, r9d; int
0x18001e7a0  mov     r8, [rsp+2300h+var_2290]; HKEY
0x18001e7a5  mov     rdx, rdi; unsigned __int16 *
0x18001e7a8  mov     rcx, rsi; this
0x18001e7ab  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18001e7b0  mov     ebx, eax
0x18001e7b2  test    eax, eax
0x18001e7b4  jns     short loc_18001E7BF
0x18001e7b6  test    r15d, r15d
0x18001e7b9  jz      loc_18001E8CD
0x18001e7bf  mov     rdx, rdi; unsigned __int16 *
0x18001e7c2  mov     rcx, rsi; this
0x18001e7c5  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001e7ca  mov     ebx, eax
0x18001e7cc  test    eax, eax
0x18001e7ce  js      loc_18001E8CD
0x18001e7d4  cmp     r14d, 2
0x18001e7d8  mov     r15d, [rsp+2300h+var_22B0]
  ... truncated ...
```
