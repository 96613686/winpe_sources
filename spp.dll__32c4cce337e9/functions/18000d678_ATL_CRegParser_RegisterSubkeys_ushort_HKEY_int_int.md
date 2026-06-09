# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x18000d678`
- end: `0x18000dc0f`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1431`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x18000d27c`
- `0x18000d678`

## callees

- `0x18000316c`
- `0x18000454c`
- `0x180004c08`
- `0x180005de4`
- `0x180006080`
- `0x18000805c`
- `0x18000c65c`
- `0x18000ccc4`
- `0x18000ce4c`
- `0x18000d168`
- `0x18000d678`
- `0x18000f760`
- `0x18000f830`
- `0x180035bd0`
- `0x180035c60`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x18000da39`
- `msvcrt!wcsncpy_s` at `0x18000da39`
- `KERNEL32!lstrcmpiW` at `0x18000d6ec`
- `KERNEL32!lstrcmpiW` at `0x18000d6ff`
- `KERNEL32!lstrcmpiW` at `0x18000d7d0`
- `KERNEL32!lstrcmpiW` at `0x18000d7ff`
- `KERNEL32!lstrcmpiW` at `0x18000d6ec`
- `KERNEL32!lstrcmpiW` at `0x18000d6ff`
- `KERNEL32!lstrcmpiW` at `0x18000d7d0`
- `KERNEL32!lstrcmpiW` at `0x18000d7ff`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000d8c7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000d8c7`

## string_xrefs

- `0x18000d6f2`: `ForceRemove`
- `0x18000d7c0`: `NoRemove`
- `0x18000d6e2`: `Delete`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterSubkeys(
        ATL::CRegParser *this,
        unsigned __int16 *a2,
        HKEY a3,
        int a4,
        int a5)
{
  int v5; // r15d
  unsigned __int16 *v7; // rdi
  ATL::CRegParser *i; // rsi
  int Token; // eax
  int v10; // ebx
  int v11; // r14d
  ATL::CRegParser *v12; // rcx
  int v13; // eax
  int v14; // r12d
  unsigned int v15; // eax
  unsigned __int16 *v16; // r9
  unsigned int v17; // ebx
  __int64 v18; // rax
  unsigned int v19; // r14d
  int v20; // r15d
  int v21; // eax
  ATL::CRegParser *v22; // rcx
  __int64 v23; // rax
  int HasSubKeys; // r15d
  unsigned int v25; // r14d
  unsigned int v27; // ecx
  unsigned int v28; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v31; // [rsp+50h] [rbp-B0h]
  __int64 v32; // [rsp+58h] [rbp-A8h]
  HKEY v33[4]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t Destination[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR ValueName[4096]; // [rsp+290h] [rbp+190h] BYREF

  memset(v33, 0, 24);
  v5 = a4;
  v7 = a2;
  for ( i = this; ; this = i )
  {
    Token = ATL::CRegParser::NextToken(this, a2);
LABEL_3:
    v10 = Token;
    if ( Token < 0 )
      break;
    while ( 1 )
    {
      while ( 1 )
      {
        if ( *v7 == 125 )
          goto LABEL_79;
        v11 = lstrcmpiW(v7, L"Delete");
        if ( !lstrcmpiW(v7, L"ForceRemove") || !v11 )
        {
          v10 = ATL::CRegParser::NextToken(i, v7);
          if ( v10 < 0 )
            goto LABEL_79;
          if ( v5 )
          {
            hKey = 0;
            v31 = 0;
            v32 = 0;
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
              v10 = ATL::CRegParser::NextToken(i, v7);
              if ( v10 < 0 )
                goto LABEL_81;
              v13 = ATL::CRegParser::SkipAssignment(i, v7);
LABEL_15:
              v10 = v13;
              if ( v13 < 0 )
                goto LABEL_81;
              ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
              goto LABEL_40;
            }
            ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
          }
        }
        v14 = 1;
        if ( !lstrcmpiW(v7, L"NoRemove") )
        {
          v14 = 0;
          v10 = ATL::CRegParser::NextToken(i, v7);
          if ( v10 < 0 )
            goto LABEL_79;
        }
        if ( !lstrcmpiW(v7, L"Val") )
        {
          v10 = ATL::CRegParser::NextToken(i, ValueName);
          if ( v10 < 0 )
            goto LABEL_79;
          v10 = ATL::CRegParser::NextToken(i, v7);
          if ( v10 < 0 )
            goto LABEL_79;
          if ( *v7 != 61 )
            goto LABEL_78;
          if ( !v5 )
          {
            if ( a5 || !v14 )
              goto LABEL_31;
            hKey = 0;
            v31 = 0;
            v32 = 0;
            v15 = ATL::CRegKey::Open((ATL::CRegKey *)&hKey, a3, 0, 0x20006u);
            if ( !v15 )
            {
              v15 = RegDeleteValueW(hKey, ValueName);
              if ( (v15 & 0xFFFFFFFD) == 0 )
              {
                ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_31:
                Token = ATL::CRegParser::SkipAssignment(i, v7);
                goto LABEL_3;
              }
            }
LABEL_80:
            v10 = ATL::AtlHresultFromWin32(v15);
LABEL_81:
            ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
            goto LABEL_79;
          }
          hKey = a3;
          v31 = 0;
          v32 = 0;
          v13 = ATL::CRegParser::AddValue(i, &hKey, ValueName, v7);
          hKey = 0;
          goto LABEL_15;
        }
        if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
          goto LABEL_78;
        if ( v5 )
          break;
        if ( a5 )
          v19 = 2;
        else
          v19 = ATL::CRegKey::Open((ATL::CRegKey *)v33, a3, v7, 0x20019u);
        v20 = 1;
        if ( !v19 )
          v20 = a5;
        wcsncpy_s(Destination, 0x104u, v7, 0xFFFFFFFFFFFFFFFFuLL);
        v10 = ATL::CRegParser::NextToken(i, v7);
        if ( v10 < 0 )
          goto LABEL_79;
        v21 = ATL::CRegParser::SkipAssignment(i, v7);
        v22 = 0;
        v10 = v21;
        if ( v21 < 0 )
          goto LABEL_79;
        if ( *v7 == 123 )
        {
          v23 = -1;
          do
            ++v23;
          while ( v7[v23] );
          if ( v23 == 1 )
          {
            v10 = ATL::CRegParser::RegisterSubkeys(i, v7, v33[0], 0, v20);
            if ( v10 < 0 && !v20 )
              goto LABEL_79;
            v10 = ATL::CRegParser::NextToken(i, v7);
            if ( v10 < 0 )
              goto LABEL_79;
          }
        }
        if ( v19 != 2 )
        {
          if ( v19 )
          {
            if ( !a5 )
            {
              v10 = ATL::AtlHresultFromWin32(v19);
              goto LABEL_79;
            }
          }
          else if ( a5 && ATL::CRegParser::HasSubKeys(v22, v33[0]) )
          {
            if ( (unsigned int)ATL::CRegParser::CanForceRemoveKey(v22, Destination) && v14 )
              ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v33, Destination);
          }
          else
          {
            HasSubKeys = ATL::CRegParser::HasSubKeys(v22, v33[0]);
            v25 = ATL::CRegKey::Close((ATL::CRegKey *)v33);
            if ( v25 )
            {
              ATL::CRegKey::Close((ATL::CRegKey *)v33);
              v27 = v25;
              return ATL::AtlHresultFromWin32(v27);
            }
            if ( v14 && !HasSubKeys )
            {
              v31 = 0;
              v32 = 0;
              hKey = a3;
              v15 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&hKey, Destination);
              hKey = 0;
              if ( v15 )
                goto LABEL_80;
              ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
            }
          }
        }
        v5 = a4;
      }
      if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v33, a3, v7, 0x2001Fu) )
      {
        if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v33, a3, v7, 0x20019u) )
        {
          v17 = ATL::CRegKey::Create((ATL::CRegKey *)v33, a3, v7, v16, v28);
          if ( v17 )
          {
            ATL::CRegKey::Close((ATL::CRegKey *)v33);
            v27 = v17;
            return ATL::AtlHresultFromWin32(v27);
          }
        }
      }
      v10 = ATL::CRegParser::NextToken(i, v7);
      if ( v10 < 0 )
        goto LABEL_79;
      if ( *v7 == 61 )
      {
        v10 = ATL::CRegParser::AddValue(i, v33, 0, v7);
        if ( v10 < 0 )
          goto LABEL_79;
      }
LABEL_40:
      if ( *v7 == 123 )
      {
        v18 = -1;
        do
          ++v18;
        while ( v7[v18] );
        if ( v18 == 1 )
          break;
      }
    }
    v10 = ATL::CRegParser::RegisterSubkeys(i, v7, v33[0], v5, 0);
    if ( v10 < 0 )
      break;
    a2 = v7;
  }
LABEL_79:
  ATL::CRegKey::Close((ATL::CRegKey *)v33);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000d678  push    rbp
0x18000d67a  push    rbx
0x18000d67b  push    rsi
0x18000d67c  push    rdi
0x18000d67d  push    r12
0x18000d67f  push    r13
0x18000d681  push    r14
0x18000d683  push    r15
0x18000d685  lea     rbp, [rsp-21A8h]
0x18000d68d  mov     eax, 22A8h
0x18000d692  call    _alloca_probe
0x18000d697  sub     rsp, rax
0x18000d69a  mov     rax, cs:__security_cookie
0x18000d6a1  xor     rax, rsp
0x18000d6a4  mov     [rbp+21E0h+var_50], rax
0x18000d6ab  xor     r12d, r12d
0x18000d6ae  mov     [rsp+22E0h+var_22A0], r9d
0x18000d6b3  mov     [rsp+22E0h+var_2280], r12
0x18000d6b8  mov     r15d, r9d
0x18000d6bb  mov     [rsp+22E0h+var_2278], r12
0x18000d6c0  mov     r13, r8
0x18000d6c3  mov     [rsp+22E0h+var_2270], r12
0x18000d6c8  mov     rdi, rdx
0x18000d6cb  mov     rsi, rcx
0x18000d6ce  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000d6d3  mov     ebx, eax
0x18000d6d5  test    eax, eax
0x18000d6d7  js      loc_18000DBA9
0x18000d6dd  jmp     loc_18000DB2D
0x18000d6e2  lea     rdx, String2; "Delete"
0x18000d6e9  mov     rcx, rdi; lpString1
0x18000d6ec  call    cs:__imp_lstrcmpiW
0x18000d6f2  lea     rdx, aForceremove; "ForceRemove"
0x18000d6f9  mov     rcx, rdi; lpString1
0x18000d6fc  mov     r14d, eax
0x18000d6ff  call    cs:__imp_lstrcmpiW
0x18000d705  test    eax, eax
0x18000d707  jz      short loc_18000D712
0x18000d709  test    r14d, r14d
0x18000d70c  jnz     loc_18000D7C0
0x18000d712  mov     rdx, rdi; unsigned __int16 *
0x18000d715  mov     rcx, rsi; this
0x18000d718  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000d71d  mov     ebx, eax
0x18000d71f  test    eax, eax
0x18000d721  js      loc_18000DBA9
0x18000d727  test    r15d, r15d
0x18000d72a  jz      loc_18000D7C0
0x18000d730  mov     edx, 5Ch ; '\'; unsigned __int16
0x18000d735  mov     [rsp+22E0h+hKey], r12
0x18000d73a  mov     rcx, rdi; lpsz
0x18000d73d  mov     [rsp+22E0h+var_2290], r12
0x18000d742  mov     [rsp+22E0h+var_2288], r12
0x18000d747  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18000d74c  test    rax, rax
0x18000d74f  jnz     loc_18000DB9A
0x18000d755  mov     rdx, rdi; unsigned __int16 *
0x18000d758  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x18000d75d  test    eax, eax
0x18000d75f  jz      short loc_18000D778
0x18000d761  mov     rdx, rdi; unsigned __int16 *
0x18000d764  mov     [rsp+22E0h+hKey], r13
0x18000d769  lea     rcx, [rsp+22E0h+hKey]; this
0x18000d76e  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18000d773  mov     [rsp+22E0h+hKey], r12
0x18000d778  test    r14d, r14d
0x18000d77b  jnz     short loc_18000D7B6
0x18000d77d  mov     rdx, rdi; unsigned __int16 *
0x18000d780  mov     rcx, rsi; this
0x18000d783  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000d788  mov     ebx, eax
0x18000d78a  test    eax, eax
0x18000d78c  js      loc_18000DBE1
0x18000d792  mov     rdx, rdi; unsigned __int16 *
0x18000d795  mov     rcx, rsi; this
0x18000d798  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18000d79d  lea     rcx, [rsp+22E0h+hKey]; this
0x18000d7a2  mov     ebx, eax
0x18000d7a4  test    eax, eax
0x18000d7a6  js      loc_18000DBE6
0x18000d7ac  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000d7b1  jmp     loc_18000D99F
0x18000d7b6  lea     rcx, [rsp+22E0h+hKey]; this
0x18000d7bb  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000d7c0  lea     rdx, aNoremove; "NoRemove"
0x18000d7c7  mov     rcx, rdi; lpString1
0x18000d7ca  mov     r12d, 1
0x18000d7d0  call    cs:__imp_lstrcmpiW
0x18000d7d6  xor     r14d, r14d
0x18000d7d9  test    eax, eax
0x18000d7db  jnz     short loc_18000D7F5
0x18000d7dd  mov     rdx, rdi; unsigned __int16 *
0x18000d7e0  mov     rcx, rsi; this
0x18000d7e3  mov     r12d, r14d
0x18000d7e6  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000d7eb  mov     ebx, eax
0x18000d7ed  test    eax, eax
0x18000d7ef  js      loc_18000DBA9
0x18000d7f5  lea     rdx, aVal; "Val"
0x18000d7fc  mov     rcx, rdi; lpString1
0x18000d7ff  call    cs:__imp_lstrcmpiW
0x18000d805  test    eax, eax
0x18000d807  jnz     loc_18000D8F7
0x18000d80d  lea     rdx, [rbp+21E0h+ValueName]; unsigned __int16 *
0x18000d814  mov     rcx, rsi; this
0x18000d817  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000d81c  mov     ebx, eax
0x18000d81e  test    eax, eax
0x18000d820  js      loc_18000DBA9
0x18000d826  mov     rdx, rdi; unsigned __int16 *
0x18000d829  mov     rcx, rsi; this
0x18000d82c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000d831  mov     ebx, eax
0x18000d833  test    eax, eax
0x18000d835  js      loc_18000DBA9
0x18000d83b  cmp     word ptr [rdi], 3Dh ; '='
0x18000d83f  jnz     loc_18000DBA4
0x18000d845  test    r15d, r15d
0x18000d848  jz      short loc_18000D87D
0x18000d84a  xor     r12d, r12d
0x18000d84d  mov     [rsp+22E0h+hKey], r13
0x18000d852  mov     r9, rdi; unsigned __int16 *
0x18000d855  mov     [rsp+22E0h+var_2290], r12
0x18000d85a  lea     r8, [rbp+21E0h+ValueName]; unsigned __int16 *
0x18000d861  mov     [rsp+22E0h+var_2288], r12
0x18000d866  lea     rdx, [rsp+22E0h+hKey]; struct ATL::CRegKey *
0x18000d86b  mov     rcx, rsi; this
0x18000d86e  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18000d873  mov     [rsp+22E0h+hKey], r12
0x18000d878  jmp     loc_18000D79D
0x18000d87d  cmp     [rbp+21E0h+arg_20], r14d
0x18000d884  jnz     short loc_18000D8E4
0x18000d886  test    r12d, r12d
0x18000d889  jz      short loc_18000D8E4
0x18000d88b  xor     r12d, r12d
0x18000d88e  lea     rcx, [rsp+22E0h+hKey]; this
0x18000d893  mov     r9d, 20006h; unsigned int
0x18000d899  mov     [rsp+22E0h+hKey], r12
0x18000d89e  xor     r8d, r8d; lpSubKey
0x18000d8a1  mov     [rsp+22E0h+var_2290], r12
0x18000d8a6  mov     rdx, r13; hKey
0x18000d8a9  mov     [rsp+22E0h+var_2288], r12
0x18000d8ae  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000d8b3  test    eax, eax
0x18000d8b5  jnz     loc_18000DBD8
0x18000d8bb  mov     rcx, [rsp+22E0h+hKey]; hKey
0x18000d8c0  lea     rdx, [rbp+21E0h+ValueName]; lpValueName
0x18000d8c7  call    cs:__imp_RegDeleteValueW
0x18000d8cd  test    eax, 0FFFFFFFDh
0x18000d8d2  jnz     loc_18000DBD8
0x18000d8d8  lea     rcx, [rsp+22E0h+hKey]; this
0x18000d8dd  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000d8e2  jmp     short loc_18000D8E7
0x18000d8e4  xor     r12d, r12d
0x18000d8e7  mov     rdx, rdi; unsigned __int16 *
0x18000d8ea  mov     rcx, rsi; this
0x18000d8ed  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18000d8f2  jmp     loc_18000D6D3
0x18000d8f7  mov     edx, 5Ch ; '\'; unsigned __int16
0x18000d8fc  mov     rcx, rdi; lpsz
0x18000d8ff  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18000d904  test    rax, rax
0x18000d907  jnz     loc_18000DBA4
0x18000d90d  test    r15d, r15d
0x18000d910  jz      loc_18000D9EE
0x18000d916  mov     r9d, 2001Fh; unsigned int
0x18000d91c  lea     rcx, [rsp+22E0h+var_2280]; this
0x18000d921  mov     r8, rdi; lpSubKey
0x18000d924  mov     rdx, r13; hKey
0x18000d927  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000d92c  xor     r12d, r12d
0x18000d92f  test    eax, eax
0x18000d931  jz      short loc_18000D967
0x18000d933  mov     r9d, 20019h; unsigned int
0x18000d939  lea     rcx, [rsp+22E0h+var_2280]; this
0x18000d93e  mov     r8, rdi; lpSubKey
0x18000d941  mov     rdx, r13; hKey
0x18000d944  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000d949  test    eax, eax
0x18000d94b  jz      short loc_18000D967
0x18000d94d  mov     r8, rdi; lpSubKey
0x18000d950  lea     rcx, [rsp+22E0h+var_2280]; this
0x18000d955  mov     rdx, r13; hKey
0x18000d958  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x18000d95d  mov     ebx, eax
0x18000d95f  test    eax, eax
0x18000d961  jnz     loc_18000DBED
0x18000d967  mov     rdx, rdi; unsigned __int16 *
0x18000d96a  mov     rcx, rsi; this
0x18000d96d  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000d972  mov     ebx, eax
0x18000d974  test    eax, eax
0x18000d976  js      loc_18000DBA9
0x18000d97c  cmp     word ptr [rdi], 3Dh ; '='
0x18000d980  jnz     short loc_18000D99F
0x18000d982  mov     r9, rdi; unsigned __int16 *
0x18000d985  lea     rdx, [rsp+22E0h+var_2280]; struct ATL::CRegKey *
0x18000d98a  xor     r8d, r8d; unsigned __int16 *
0x18000d98d  mov     rcx, rsi; this
0x18000d990  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18000d995  mov     ebx, eax
0x18000d997  test    eax, eax
0x18000d999  js      loc_18000DBA9
0x18000d99f  cmp     word ptr [rdi], 7Bh ; '{'
0x18000d9a3  jnz     loc_18000DB2D
0x18000d9a9  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000d9ad  inc     rax
0x18000d9b0  cmp     [rdi+rax*2], r12w
0x18000d9b5  jnz     short loc_18000D9AD
0x18000d9b7  cmp     rax, 1
0x18000d9bb  jnz     loc_18000DB2D
0x18000d9c1  mov     r8, [rsp+22E0h+var_2280]; HKEY
0x18000d9c6  mov     r9d, r15d; int
0x18000d9c9  mov     rdx, rdi; unsigned __int16 *
0x18000d9cc  mov     [rsp+22E0h+var_22C0], r12d; int
0x18000d9d1  mov     rcx, rsi; this
0x18000d9d4  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000d9d9  mov     ebx, eax
0x18000d9db  test    eax, eax
0x18000d9dd  js      loc_18000DBA9
0x18000d9e3  mov     rdx, rdi
0x18000d9e6  mov     rcx, rsi
0x18000d9e9  jmp     loc_18000D6CE
0x18000d9ee  cmp     [rbp+21E0h+arg_20], r14d
0x18000d9f5  jnz     short loc_18000DA12
0x18000d9f7  mov     r9d, 20019h; unsigned int
0x18000d9fd  lea     rcx, [rsp+22E0h+var_2280]; this
0x18000da02  mov     r8, rdi; lpSubKey
0x18000da05  mov     rdx, r13; hKey
0x18000da08  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000da0d  mov     r14d, eax
0x18000da10  jmp     short loc_18000DA18
0x18000da12  mov     r14d, 2
0x18000da18  test    r14d, r14d
0x18000da1b  lea     rcx, [rbp+21E0h+Destination]; Destination
0x18000da1f  mov     r15d, 1
0x18000da25  mov     r8, rdi; Source
0x18000da28  cmovz   r15d, [rbp+21E0h+arg_20]
0x18000da30  mov     edx, 104h; SizeInWords
0x18000da35  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18000da39  call    cs:__imp_wcsncpy_s
0x18000da3f  mov     rdx, rdi; unsigned __int16 *
0x18000da42  mov     rcx, rsi; this
0x18000da45  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000da4a  mov     ebx, eax
0x18000da4c  test    eax, eax
0x18000da4e  js      loc_18000DBA9
0x18000da54  mov     rdx, rdi; unsigned __int16 *
0x18000da57  mov     rcx, rsi; this
0x18000da5a  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18000da5f  xor     ecx, ecx; this
0x18000da61  mov     ebx, eax
0x18000da63  test    eax, eax
0x18000da65  js      loc_18000DBA9
0x18000da6b  cmp     word ptr [rdi], 7Bh ; '{'
0x18000da6f  jnz     short loc_18000DAC5
0x18000da71  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000da75  inc     rax
0x18000da78  cmp     [rdi+rax*2], cx
0x18000da7c  jnz     short loc_18000DA75
0x18000da7e  cmp     rax, 1
0x18000da82  jnz     short loc_18000DAC5
0x18000da84  mov     r8, [rsp+22E0h+var_2280]; HKEY
0x18000da89  xor     r9d, r9d; int
0x18000da8c  mov     rdx, rdi; unsigned __int16 *
0x18000da8f  mov     [rsp+22E0h+var_22C0], r15d; int
0x18000da94  mov     rcx, rsi; this
0x18000da97  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000da9c  mov     ebx, eax
0x18000da9e  test    eax, eax
0x18000daa0  jns     short loc_18000DAAB
0x18000daa2  test    r15d, r15d
0x18000daa5  jz      loc_18000DBA9
0x18000daab  mov     rdx, rdi; unsigned __int16 *
0x18000daae  mov     rcx, rsi; this
0x18000dab1  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000dab6  xor     r15d, r15d
0x18000dab9  mov     ebx, eax
0x18000dabb  test    eax, eax
0x18000dabd  js      loc_18000DBA9
0x18000dac3  jmp     short loc_18000DAC8
0x18000dac5  xor     r15d, r15d
0x18000dac8  cmp     r14d, 2
0x18000dacc  jz      short loc_18000DB25
0x18000dace  test    r14d, r14d
0x18000dad1  jz      short loc_18000DAEE
0x18000dad3  xor     r12d, r12d
0x18000dad6  cmp     [rbp+21E0h+arg_20], r12d
0x18000dadd  jnz     short loc_18000DB28
0x18000dadf  mov     ecx, r14d; unsigned int
0x18000dae2  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18000dae7  mov     ebx, eax
0x18000dae9  jmp     loc_18000DBA9
0x18000daee  cmp     [rbp+21E0h+arg_20], r15d
0x18000daf5  jz      short loc_18000DB39
0x18000daf7  mov     rdx, [rsp+22E0h+var_2280]; HKEY
0x18000dafc  call    ?HasSubKeys@CRegParser@ATL@@IEAAHPEAUHKEY__@@@Z; ATL::CRegParser::HasSubKeys(HKEY__ *)
0x18000db01  test    eax, eax
0x18000db03  jz      short loc_18000DB39
0x18000db05  lea     rdx, [rbp+21E0h+Destination]; unsigned __int16 *
  ... truncated ...
```
