# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x140034e1c`
- end: `0x14003540b`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1519`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x14003494c`
- `0x140034e1c`

## callees

- `0x140030e7c`
- `0x140031410`
- `0x1400314e0`
- `0x140031a80`
- `0x140031c24`
- `0x140032e6c`
- `0x1400331d8`
- `0x140033db0`
- `0x140033f10`
- `0x140034838`
- `0x140034e1c`
- `0x140035dac`
- `0x140035f3c`
- `0x140052e80`
- `0x140052f40`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x140035220`
- `msvcrt!wcsncpy_s` at `0x140035220`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x14003506e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x14003506e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140035121`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140035121`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140034e98`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140034eab`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140034f7d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140034fac`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140034e98`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140034eab`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140034f7d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140034fac`

## string_xrefs

- `0x140034ea1`: `ForceRemove`
- `0x140034f73`: `NoRemove`
- `0x140034e8e`: `Delete`

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
  errno_t v21; // eax
  ATL::CRegParser *v22; // rcx
  __int64 v23; // rax
  int HasSubKeys; // r14d
  LSTATUS v25; // eax
  unsigned int v26; // eax
  HKEY v29[3]; // [rsp+58h] [rbp-A8h] BYREF
  DWORD dwDisposition; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v31[3]; // [rsp+78h] [rbp-88h] BYREF
  HKEY phkResult; // [rsp+90h] [rbp-70h] BYREF
  HKEY v33[3]; // [rsp+98h] [rbp-68h] BYREF
  HKEY hKey[3]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v35[3]; // [rsp+C8h] [rbp-38h] BYREF
  wchar_t Destination[264]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR ValueName[4096]; // [rsp+2F0h] [rbp+1F0h] BYREF

  v5 = a4;
  v7 = a2;
  v8 = this;
  memset(v29, 0, sizeof(v29));
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
          memset(v31, 0, sizeof(v31));
          if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
          {
            ATL::CRegKey::Close((ATL::CRegKey *)v31);
LABEL_79:
            v10 = -2147352567;
            goto LABEL_80;
          }
          if ( (unsigned int)ATL::CRegParser::CanForceRemoveKey(v12, v7) )
          {
            v31[0] = a3;
            ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v31, v7);
            v31[0] = 0;
          }
          if ( !v11 )
          {
            v10 = ATL::CRegParser::NextToken(v8, v7);
            if ( v10 < 0 )
            {
              v14 = (HKEY *)v31;
              goto LABEL_82;
            }
            v13 = ATL::CRegParser::SkipAssignment(v8, v7);
            v10 = v13;
            v14 = (HKEY *)v31;
            goto LABEL_15;
          }
          ATL::CRegKey::Close((ATL::CRegKey *)v31);
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
        if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v29, a3, v7, 0x2001Fu) )
        {
          if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v29, a3, v7, 0x20019u) )
          {
            dwDisposition = 0;
            phkResult = 0;
            v17 = RegCreateKeyExW(a3, v7, 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition);
            if ( v17 )
              goto LABEL_65;
            v17 = ATL::CRegKey::Close((ATL::CRegKey *)v29);
            v29[0] = phkResult;
            if ( v17 )
              goto LABEL_65;
          }
        }
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_80;
        if ( *v7 == 61 )
        {
          v10 = ATL::CRegParser::AddValue(v8, v29, 0, v7);
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
            v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v29[0], v5, 0);
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
          v19 = ATL::CRegKey::Open((ATL::CRegKey *)v29, a3, v7, 0x20019u);
        v20 = 1;
        if ( !v19 )
          v20 = a5;
        v21 = wcsncpy_s(Destination, 0x104u, v7, 0xFFFFFFFFFFFFFFFFuLL);
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
            v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v29[0], 0, v20);
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
          else if ( a5 && ATL::CRegParser::HasSubKeys(v22, v29[0]) )
          {
            if ( (unsigned int)ATL::CRegParser::CanForceRemoveKey(v22, Destination) && v15 )
              ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v29, Destination);
          }
          else
          {
            HasSubKeys = ATL::CRegParser::HasSubKeys(v22, v29[0]);
            v25 = ATL::CRegKey::Close((ATL::CRegKey *)v29);
            if ( v25 )
            {
              v17 = v25;
              goto LABEL_65;
            }
            if ( v15 && !HasSubKeys )
            {
              v35[1] = 0;
              v35[2] = 0;
              v35[0] = a3;
              v26 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v35, Destination);
              v35[0] = 0;
              if ( v26 )
              {
                v10 = ATL::AtlHresultFromWin32(v26);
                v14 = (HKEY *)v35;
                goto LABEL_82;
              }
              ATL::CRegKey::Close((ATL::CRegKey *)v35);
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
      v33[1] = 0;
      v33[2] = 0;
      v33[0] = a3;
      v13 = ATL::CRegParser::AddValue(v8, v33, ValueName, v7);
      v10 = v13;
      v33[0] = 0;
      v14 = v33;
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
  ATL::CRegKey::Close((ATL::CRegKey *)v29);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140034e1c  push    rbp
0x140034e1e  push    rbx
0x140034e1f  push    rsi
0x140034e20  push    rdi
0x140034e21  push    r12
0x140034e23  push    r13
0x140034e25  push    r14
0x140034e27  push    r15
0x140034e29  lea     rbp, [rsp-2208h]
0x140034e31  mov     eax, 2308h
0x140034e36  call    _alloca_probe
0x140034e3b  sub     rsp, rax
0x140034e3e  mov     rax, cs:__security_cookie
0x140034e45  xor     rax, rsp
0x140034e48  mov     [rbp+2240h+var_50], rax
0x140034e4f  mov     r15d, r9d
0x140034e52  mov     [rsp+2340h+var_22F0], r9d
0x140034e57  mov     r13, r8
0x140034e5a  mov     rdi, rdx
0x140034e5d  mov     rsi, rcx
0x140034e60  xor     r14d, r14d
0x140034e63  mov     [rsp+2340h+var_22E8], r14
0x140034e68  mov     [rsp+2340h+var_22E0], r14
0x140034e6d  mov     [rsp+2340h+var_22D8], r14
0x140034e72  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140034e77  test    eax, eax
0x140034e79  mov     ebx, eax
0x140034e7b  js      loc_1400353B1
0x140034e81  xor     r12d, r12d
0x140034e84  cmp     word ptr [rdi], 7Dh ; '}'
0x140034e88  jz      loc_1400353B1
0x140034e8e  lea     rdx, aDelete; "Delete"
0x140034e95  mov     rcx, rdi; lpString1
0x140034e98  call    cs:__imp_lstrcmpiW
0x140034e9e  mov     r14d, eax
0x140034ea1  lea     rdx, aForceremove; "ForceRemove"
0x140034ea8  mov     rcx, rdi; lpString1
0x140034eab  call    cs:__imp_lstrcmpiW
0x140034eb1  test    eax, eax
0x140034eb3  jz      short loc_140034EBE
0x140034eb5  test    r14d, r14d
0x140034eb8  jnz     loc_140034F6D
0x140034ebe  mov     rdx, rdi; unsigned __int16 *
0x140034ec1  mov     rcx, rsi; this
0x140034ec4  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140034ec9  mov     ebx, eax
0x140034ecb  test    eax, eax
0x140034ecd  js      loc_1400353B1
0x140034ed3  test    r15d, r15d
0x140034ed6  jz      loc_140034F6D
0x140034edc  mov     [rsp+2340h+var_22C8], r12
0x140034ee1  mov     [rbp+2240h+var_22C0], r12
0x140034ee5  mov     [rbp+2240h+var_22B8], r12
0x140034ee9  mov     edx, 5Ch ; '\'; unsigned __int16
0x140034eee  mov     rcx, rdi; lpsz
0x140034ef1  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x140034ef6  test    rax, rax
0x140034ef9  jnz     loc_1400353A2
0x140034eff  mov     rdx, rdi; unsigned __int16 *
0x140034f02  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x140034f07  test    eax, eax
0x140034f09  jz      short loc_140034F22
0x140034f0b  mov     [rsp+2340h+var_22C8], r13
0x140034f10  mov     rdx, rdi; unsigned __int16 *
0x140034f13  lea     rcx, [rsp+2340h+var_22C8]; this
0x140034f18  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x140034f1d  mov     [rsp+2340h+var_22C8], r12
0x140034f22  test    r14d, r14d
0x140034f25  jnz     short loc_140034F63
0x140034f27  mov     rdx, rdi; unsigned __int16 *
0x140034f2a  mov     rcx, rsi; this
0x140034f2d  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140034f32  mov     ebx, eax
0x140034f34  xor     r14d, r14d
0x140034f37  test    eax, eax
0x140034f39  js      loc_14003539B
0x140034f3f  mov     rdx, rdi; unsigned __int16 *
0x140034f42  mov     rcx, rsi; this
0x140034f45  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x140034f4a  mov     ebx, eax
0x140034f4c  lea     rcx, [rsp+2340h+var_22C8]; this
0x140034f51  test    eax, eax
0x140034f53  js      loc_1400353ED
0x140034f59  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x140034f5e  jmp     loc_140035186
0x140034f63  lea     rcx, [rsp+2340h+var_22C8]; this
0x140034f68  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x140034f6d  mov     r12d, 1
0x140034f73  lea     rdx, aNoremove; "NoRemove"
0x140034f7a  mov     rcx, rdi; lpString1
0x140034f7d  call    cs:__imp_lstrcmpiW
0x140034f83  xor     r14d, r14d
0x140034f86  test    eax, eax
0x140034f88  jnz     short loc_140034FA2
0x140034f8a  mov     r12d, r14d
0x140034f8d  mov     rdx, rdi; unsigned __int16 *
0x140034f90  mov     rcx, rsi; this
0x140034f93  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140034f98  mov     ebx, eax
0x140034f9a  test    eax, eax
0x140034f9c  js      loc_1400353B1
0x140034fa2  lea     rdx, aVal; "Val"
0x140034fa9  mov     rcx, rdi; lpString1
0x140034fac  call    cs:__imp_lstrcmpiW
0x140034fb2  test    eax, eax
0x140034fb4  jnz     loc_140035098
0x140034fba  lea     rdx, [rbp+2240h+ValueName]; unsigned __int16 *
0x140034fc1  mov     rcx, rsi; this
0x140034fc4  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140034fc9  mov     ebx, eax
0x140034fcb  test    eax, eax
0x140034fcd  js      loc_1400353B1
0x140034fd3  mov     rdx, rdi; unsigned __int16 *
0x140034fd6  mov     rcx, rsi; this
0x140034fd9  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140034fde  mov     ebx, eax
0x140034fe0  test    eax, eax
0x140034fe2  js      loc_1400353B1
0x140034fe8  cmp     word ptr [rdi], 3Dh ; '='
0x140034fec  jnz     loc_1400353AC
0x140034ff2  test    r15d, r15d
0x140034ff5  jz      short loc_14003502C
0x140034ff7  mov     [rbp+2240h+var_22A8], r14
0x140034ffb  mov     [rbp+2240h+var_22A0], r14
0x140034fff  mov     [rbp+2240h+var_2298], r14
0x140035003  mov     [rbp+2240h+var_22A8], r13
0x140035007  mov     r9, rdi; unsigned __int16 *
0x14003500a  lea     r8, [rbp+2240h+ValueName]; unsigned __int16 *
0x140035011  lea     rdx, [rbp+2240h+var_22A8]; struct ATL::CRegKey *
0x140035015  mov     rcx, rsi; this
0x140035018  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x14003501d  mov     ebx, eax
0x14003501f  mov     [rbp+2240h+var_22A8], r14
0x140035023  lea     rcx, [rbp+2240h+var_22A8]
0x140035027  jmp     loc_140034F51
0x14003502c  cmp     [rbp+2240h+arg_20], r14d
0x140035033  jnz     short loc_140035088
0x140035035  test    r12d, r12d
0x140035038  jz      short loc_140035088
0x14003503a  mov     [rbp+2240h+hKey], r14
0x14003503e  mov     [rbp+2240h+var_2288], r14
0x140035042  mov     [rbp+2240h+var_2280], r14
0x140035046  mov     r9d, 20006h; unsigned int
0x14003504c  xor     r8d, r8d; lpSubKey
0x14003504f  mov     rdx, r13; hKey
0x140035052  lea     rcx, [rbp+2240h+hKey]; this
0x140035056  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x14003505b  test    eax, eax
0x14003505d  jnz     loc_1400353E0
0x140035063  lea     rdx, [rbp+2240h+ValueName]; lpValueName
0x14003506a  mov     rcx, [rbp+2240h+hKey]; hKey
0x14003506e  call    cs:__imp_RegDeleteValueW
0x140035074  test    eax, 0FFFFFFFDh
0x140035079  jnz     loc_1400353E0
0x14003507f  lea     rcx, [rbp+2240h+hKey]; this
0x140035083  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x140035088  mov     rdx, rdi; unsigned __int16 *
0x14003508b  mov     rcx, rsi; this
0x14003508e  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x140035093  jmp     loc_140034E77
0x140035098  mov     edx, 5Ch ; '\'; unsigned __int16
0x14003509d  mov     rcx, rdi; lpsz
0x1400350a0  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x1400350a5  test    rax, rax
0x1400350a8  jnz     loc_1400353AC
0x1400350ae  test    r15d, r15d
0x1400350b1  jz      loc_1400351D5
0x1400350b7  mov     ebx, 2001Fh
0x1400350bc  mov     r9d, ebx; unsigned int
0x1400350bf  mov     r8, rdi; lpSubKey
0x1400350c2  mov     rdx, r13; hKey
0x1400350c5  lea     rcx, [rsp+2340h+var_22E8]; this
0x1400350ca  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1400350cf  test    eax, eax
0x1400350d1  jz      short loc_14003514E
0x1400350d3  lea     r9d, [rbx-6]; unsigned int
0x1400350d7  mov     r8, rdi; lpSubKey
0x1400350da  mov     rdx, r13; hKey
0x1400350dd  lea     rcx, [rsp+2340h+var_22E8]; this
0x1400350e2  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1400350e7  test    eax, eax
0x1400350e9  jz      short loc_14003514E
0x1400350eb  mov     [rsp+2340h+dwDisposition], r14d
0x1400350f0  mov     [rbp+2240h+var_22B0], r14
0x1400350f4  lea     rax, [rsp+2340h+dwDisposition]
0x1400350f9  mov     [rsp+2340h+lpdwDisposition], rax; lpdwDisposition
0x1400350fe  lea     rax, [rbp+2240h+var_22B0]
0x140035102  mov     [rsp+2340h+phkResult], rax; phkResult
0x140035107  mov     [rsp+2340h+lpSecurityAttributes], r14; lpSecurityAttributes
0x14003510c  mov     [rsp+2340h+samDesired], ebx; samDesired
0x140035110  mov     [rsp+2340h+dwOptions], r14d; dwOptions
0x140035115  xor     r9d, r9d; lpClass
0x140035118  xor     r8d, r8d; Reserved
0x14003511b  mov     rdx, rdi; lpSubKey
0x14003511e  mov     rcx, r13; hKey
0x140035121  call    cs:__imp_RegCreateKeyExW
0x140035127  mov     ecx, eax
0x140035129  test    eax, eax
0x14003512b  jnz     loc_1400352D5
0x140035131  lea     rcx, [rsp+2340h+var_22E8]; this
0x140035136  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x14003513b  mov     ecx, eax
0x14003513d  mov     rax, [rbp+2240h+var_22B0]
0x140035141  mov     [rsp+2340h+var_22E8], rax
0x140035146  test    ecx, ecx
0x140035148  jnz     loc_1400352D5
0x14003514e  mov     rdx, rdi; unsigned __int16 *
0x140035151  mov     rcx, rsi; this
0x140035154  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140035159  mov     ebx, eax
0x14003515b  test    eax, eax
0x14003515d  js      loc_1400353B1
0x140035163  cmp     word ptr [rdi], 3Dh ; '='
0x140035167  jnz     short loc_140035186
0x140035169  mov     r9, rdi; unsigned __int16 *
0x14003516c  xor     r8d, r8d; unsigned __int16 *
0x14003516f  lea     rdx, [rsp+2340h+var_22E8]; struct ATL::CRegKey *
0x140035174  mov     rcx, rsi; this
0x140035177  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x14003517c  mov     ebx, eax
0x14003517e  test    eax, eax
0x140035180  js      loc_1400353B1
0x140035186  cmp     word ptr [rdi], 7Bh ; '{'
0x14003518a  jnz     loc_140034E81
0x140035190  or      rax, 0FFFFFFFFFFFFFFFFh
0x140035194  inc     rax
0x140035197  cmp     [rdi+rax*2], r14w
0x14003519c  jnz     short loc_140035194
0x14003519e  cmp     rax, 1
0x1400351a2  jnz     loc_140034E81
0x1400351a8  mov     [rsp+2340h+dwOptions], r14d; int
0x1400351ad  mov     r9d, r15d; int
0x1400351b0  mov     r8, [rsp+2340h+var_22E8]; HKEY
0x1400351b5  mov     rdx, rdi; unsigned __int16 *
0x1400351b8  mov     rcx, rsi; this
0x1400351bb  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1400351c0  mov     ebx, eax
0x1400351c2  test    eax, eax
0x1400351c4  js      loc_1400353B1
0x1400351ca  mov     rdx, rdi
0x1400351cd  mov     rcx, rsi
0x1400351d0  jmp     loc_140034E72
0x1400351d5  cmp     [rbp+2240h+arg_20], r14d
0x1400351dc  jnz     short loc_1400351F9
0x1400351de  mov     r9d, 20019h; unsigned int
0x1400351e4  mov     r8, rdi; lpSubKey
0x1400351e7  mov     rdx, r13; hKey
0x1400351ea  lea     rcx, [rsp+2340h+var_22E8]; this
0x1400351ef  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1400351f4  mov     r14d, eax
0x1400351f7  jmp     short loc_1400351FF
0x1400351f9  mov     r14d, 2
0x1400351ff  mov     r15d, 1
0x140035205  test    r14d, r14d
0x140035208  cmovz   r15d, [rbp+2240h+arg_20]
0x140035210  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140035214  mov     r8, rdi; Source
0x140035217  mov     edx, 104h; SizeInWords
0x14003521c  lea     rcx, [rbp+2240h+Destination]; Destination
0x140035220  call    cs:__imp_wcsncpy_s
0x140035226  mov     ecx, eax; int
0x140035228  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x14003522d  mov     rdx, rdi; unsigned __int16 *
0x140035230  mov     rcx, rsi; this
0x140035233  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140035238  mov     ebx, eax
0x14003523a  test    eax, eax
0x14003523c  js      loc_1400353B1
0x140035242  mov     rdx, rdi; unsigned __int16 *
0x140035245  mov     rcx, rsi; this
0x140035248  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x14003524d  mov     ebx, eax
0x14003524f  xor     ecx, ecx
0x140035251  test    eax, eax
0x140035253  js      loc_1400353B1
0x140035259  cmp     word ptr [rdi], 7Bh ; '{'
0x14003525d  jnz     short loc_1400352AE
0x14003525f  or      rax, 0FFFFFFFFFFFFFFFFh
0x140035263  inc     rax
0x140035266  cmp     [rdi+rax*2], cx
0x14003526a  jnz     short loc_140035263
0x14003526c  cmp     rax, 1
0x140035270  jnz     short loc_1400352AE
0x140035272  mov     [rsp+2340h+dwOptions], r15d; int
0x140035277  xor     r9d, r9d; int
0x14003527a  mov     r8, [rsp+2340h+var_22E8]; HKEY
0x14003527f  mov     rdx, rdi; unsigned __int16 *
0x140035282  mov     rcx, rsi; this
0x140035285  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x14003528a  mov     ebx, eax
0x14003528c  test    eax, eax
0x14003528e  jns     short loc_140035299
0x140035290  test    r15d, r15d
0x140035293  jz      loc_1400353B1
0x140035299  mov     rdx, rdi; unsigned __int16 *
0x14003529c  mov     rcx, rsi; this
0x14003529f  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1400352a4  mov     ebx, eax
0x1400352a6  test    eax, eax
0x1400352a8  js      loc_1400353B1
  ... truncated ...
```
