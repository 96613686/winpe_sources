# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x18001a0e0`
- end: `0x18001a67a`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1434`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, registry_config`

## callers

- `0x180019cfc`
- `0x18001a0e0`

## callees

- `0x18000e234`
- `0x180016224`
- `0x180016a1c`
- `0x180016a8c`
- `0x180017200`
- `0x1800173a4`
- `0x1800173d0`
- `0x1800186d0`
- `0x180018d58`
- `0x180019370`
- `0x180019be8`
- `0x18001a0e0`
- `0x18001ab28`
- `0x18001abf8`
- `0x18002dec0`
- `0x18002df80`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x18001a4a7`
- `msvcrt!wcsncpy_s` at `0x18001a4a7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001a33f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001a33f`
- `KERNEL32!lstrcmpiW` at `0x18001a165`
- `KERNEL32!lstrcmpiW` at `0x18001a178`
- `KERNEL32!lstrcmpiW` at `0x18001a24c`
- `KERNEL32!lstrcmpiW` at `0x18001a27b`
- `KERNEL32!lstrcmpiW` at `0x18001a165`
- `KERNEL32!lstrcmpiW` at `0x18001a178`
- `KERNEL32!lstrcmpiW` at `0x18001a24c`
- `KERNEL32!lstrcmpiW` at `0x18001a27b`

## string_xrefs

- `0x18001a16e`: `ForceRemove`
- `0x18001a242`: `NoRemove`
- `0x18001a15b`: `Delete`

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
  unsigned __int16 *v16; // r9
  unsigned int v17; // eax
  __int64 v18; // rax
  int v19; // r14d
  int v20; // r15d
  errno_t v21; // eax
  ATL::CRegParser *v22; // rcx
  __int64 v23; // rax
  unsigned int v24; // ecx
  int HasSubKeys; // r14d
  unsigned int v27; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v30; // [rsp+50h] [rbp-B0h]
  __int64 v31; // [rsp+58h] [rbp-A8h]
  HKEY v32[4]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t Destination[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR ValueName[4096]; // [rsp+290h] [rbp+190h] BYREF

  v32[3] = HKEY_DYN_DATA|0x7FFFFFF8LL;
  v5 = a4;
  v7 = a2;
  v8 = this;
  memset(v32, 0, 24);
LABEL_2:
  Token = ATL::CRegParser::NextToken(this, a2);
  while ( 2 )
  {
    v10 = Token;
    if ( Token < 0 )
      goto LABEL_78;
    while ( 1 )
    {
      while ( 1 )
      {
        if ( *v7 == 125 )
          goto LABEL_78;
        v11 = lstrcmpiW(v7, L"Delete");
        if ( lstrcmpiW(v7, L"ForceRemove") )
        {
          if ( v11 )
            break;
        }
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_78;
        if ( !v5 )
          break;
        hKey = 0;
        v30 = 0;
        v31 = 0;
        if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
        {
          ATL::CRegKey::Close(&hKey);
LABEL_77:
          v10 = -2147352567;
          goto LABEL_78;
        }
        if ( (unsigned int)ATL::CRegParser::CanForceRemoveKey(v12, v7) )
        {
          hKey = a3;
          ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)&hKey, v7);
          hKey = 0;
        }
        if ( v11 )
        {
          ATL::CRegKey::Close(&hKey);
          break;
        }
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_80;
        v13 = ATL::CRegParser::SkipAssignment(v8, v7);
        v10 = v13;
LABEL_15:
        if ( v13 < 0 )
          goto LABEL_80;
        ATL::CRegKey::Close(&hKey);
LABEL_40:
        if ( *v7 == 123 )
        {
          v18 = -1;
          do
            ++v18;
          while ( v7[v18] );
          if ( v18 == 1 )
          {
            v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v32[0], v5, 0);
            if ( v10 < 0 )
              goto LABEL_78;
            a2 = v7;
            this = v8;
            goto LABEL_2;
          }
        }
      }
      v14 = 1;
      if ( !lstrcmpiW(v7, L"NoRemove") )
      {
        v14 = 0;
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_78;
      }
      if ( !lstrcmpiW(v7, L"Val") )
        break;
      if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
        goto LABEL_77;
      if ( v5 )
      {
        if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v32, a3, v7, 0x2001Fu)
          || !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v32, a3, v7, 0x20019u)
          || (v17 = ATL::CRegKey::Create(v32, a3, v7, v16, v27)) == 0 )
        {
          v10 = ATL::CRegParser::NextToken(v8, v7);
          if ( v10 < 0 )
            goto LABEL_78;
          if ( *v7 == 61 )
          {
            v10 = ATL::CRegParser::AddValue(v8, v32, 0, v7);
            if ( v10 < 0 )
              goto LABEL_78;
          }
          goto LABEL_40;
        }
LABEL_81:
        v24 = v17;
LABEL_64:
        v10 = ATL::AtlHresultFromWin32(v24);
        goto LABEL_78;
      }
      if ( a5 )
        v19 = 2;
      else
        v19 = ATL::CRegKey::Open((ATL::CRegKey *)v32, a3, v7, 0x20019u);
      v20 = 1;
      if ( !v19 )
        v20 = a5;
      v21 = wcsncpy_s(Destination, 0x104u, v7, 0xFFFFFFFFFFFFFFFFuLL);
      ATL::AtlCrtErrorCheck(v21);
      v10 = ATL::CRegParser::NextToken(v8, v7);
      if ( v10 < 0 )
        goto LABEL_78;
      v10 = ATL::CRegParser::SkipAssignment(v8, v7);
      v22 = 0;
      if ( v10 < 0 )
        goto LABEL_78;
      if ( *v7 == 123 )
      {
        v23 = -1;
        do
          ++v23;
        while ( v7[v23] );
        if ( v23 == 1 )
        {
          v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v32[0], 0, v20);
          if ( v10 < 0 && !v20 )
            goto LABEL_78;
          v10 = ATL::CRegParser::NextToken(v8, v7);
          if ( v10 < 0 )
            goto LABEL_78;
        }
      }
      v5 = a4;
      if ( v19 != 2 )
      {
        if ( v19 )
        {
          if ( !a5 )
          {
            v24 = v19;
            goto LABEL_64;
          }
        }
        else if ( a5 && ATL::CRegParser::HasSubKeys(v22, v32[0]) )
        {
          if ( (unsigned int)ATL::CRegParser::CanForceRemoveKey(v22, Destination) && v14 )
            ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v32, Destination);
        }
        else
        {
          HasSubKeys = ATL::CRegParser::HasSubKeys(v22, v32[0]);
          v17 = ATL::CRegKey::Close(v32);
          if ( v17 )
            goto LABEL_81;
          if ( v14 && !HasSubKeys )
          {
            v30 = 0;
            v31 = 0;
            hKey = a3;
            v15 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&hKey, Destination);
            hKey = 0;
            if ( v15 )
              goto LABEL_79;
            ATL::CRegKey::Close(&hKey);
          }
        }
      }
    }
    v10 = ATL::CRegParser::NextToken(v8, ValueName);
    if ( v10 < 0 )
      goto LABEL_78;
    v10 = ATL::CRegParser::NextToken(v8, v7);
    if ( v10 < 0 )
      goto LABEL_78;
    if ( *v7 != 61 )
      goto LABEL_77;
    if ( v5 )
    {
      v30 = 0;
      v31 = 0;
      hKey = a3;
      v13 = ATL::CRegParser::AddValue(v8, &hKey, ValueName, v7);
      v10 = v13;
      hKey = 0;
      goto LABEL_15;
    }
    if ( a5 || !v14 )
      goto LABEL_31;
    hKey = 0;
    v30 = 0;
    v31 = 0;
    v15 = ATL::CRegKey::Open((ATL::CRegKey *)&hKey, a3, 0, 0x20006u);
    if ( !v15 )
    {
      v15 = RegDeleteValueW(hKey, ValueName);
      if ( (v15 & 0xFFFFFFFD) == 0 )
      {
        ATL::CRegKey::Close(&hKey);
LABEL_31:
        Token = ATL::CRegParser::SkipAssignment(v8, v7);
        continue;
      }
    }
    break;
  }
LABEL_79:
  v10 = ATL::AtlHresultFromWin32(v15);
LABEL_80:
  ATL::CRegKey::Close(&hKey);
LABEL_78:
  ATL::CRegKey::Close(v32);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18001a0e0  push    rbp
0x18001a0e2  push    rbx
0x18001a0e3  push    rsi
0x18001a0e4  push    rdi
0x18001a0e5  push    r12
0x18001a0e7  push    r13
0x18001a0e9  push    r14
0x18001a0eb  push    r15
0x18001a0ed  lea     rbp, [rsp-21A8h]
0x18001a0f5  mov     eax, 22A8h
0x18001a0fa  call    _alloca_probe
0x18001a0ff  sub     rsp, rax
0x18001a102  mov     [rsp+22E0h+var_2268], 0FFFFFFFFFFFFFFFEh
0x18001a10b  mov     rax, cs:__security_cookie
0x18001a112  xor     rax, rsp
0x18001a115  mov     [rbp+21E0h+var_50], rax
0x18001a11c  mov     r15d, r9d
0x18001a11f  mov     [rsp+22E0h+var_22A0], r9d
0x18001a124  mov     r13, r8
0x18001a127  mov     rdi, rdx
0x18001a12a  mov     rsi, rcx
0x18001a12d  xor     r14d, r14d
0x18001a130  mov     [rsp+22E0h+var_2280], r14
0x18001a135  mov     [rsp+22E0h+var_2278], r14
0x18001a13a  mov     [rsp+22E0h+var_2270], r14
0x18001a13f  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001a144  test    eax, eax
0x18001a146  mov     ebx, eax
0x18001a148  js      loc_18001A62E
0x18001a14e  xor     r12d, r12d
0x18001a151  cmp     word ptr [rdi], 7Dh ; '}'
0x18001a155  jz      loc_18001A62E
0x18001a15b  lea     rdx, aDelete; "Delete"
0x18001a162  mov     rcx, rdi; lpString1
0x18001a165  call    cs:__imp_lstrcmpiW
0x18001a16b  mov     r14d, eax
0x18001a16e  lea     rdx, aForceremove; "ForceRemove"
0x18001a175  mov     rcx, rdi; lpString1
0x18001a178  call    cs:__imp_lstrcmpiW
0x18001a17e  test    eax, eax
0x18001a180  jz      short loc_18001A18B
0x18001a182  test    r14d, r14d
0x18001a185  jnz     loc_18001A23C
0x18001a18b  mov     rdx, rdi; unsigned __int16 *
0x18001a18e  mov     rcx, rsi; this
0x18001a191  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001a196  mov     ebx, eax
0x18001a198  test    eax, eax
0x18001a19a  js      loc_18001A62E
0x18001a1a0  test    r15d, r15d
0x18001a1a3  jz      loc_18001A23C
0x18001a1a9  mov     [rsp+22E0h+hKey], r12
0x18001a1ae  mov     [rsp+22E0h+var_2290], r12
0x18001a1b3  mov     [rsp+22E0h+var_2288], r12
0x18001a1b8  mov     edx, 5Ch ; '\'; unsigned __int16
0x18001a1bd  mov     rcx, rdi; lpsz
0x18001a1c0  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18001a1c5  test    rax, rax
0x18001a1c8  jnz     loc_18001A61F
0x18001a1ce  mov     rdx, rdi; unsigned __int16 *
0x18001a1d1  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x18001a1d6  test    eax, eax
0x18001a1d8  jz      short loc_18001A1F1
0x18001a1da  mov     [rsp+22E0h+hKey], r13
0x18001a1df  mov     rdx, rdi; unsigned __int16 *
0x18001a1e2  lea     rcx, [rsp+22E0h+hKey]; this
0x18001a1e7  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18001a1ec  mov     [rsp+22E0h+hKey], r12
0x18001a1f1  test    r14d, r14d
0x18001a1f4  jnz     short loc_18001A232
0x18001a1f6  mov     rdx, rdi; unsigned __int16 *
0x18001a1f9  mov     rcx, rsi; this
0x18001a1fc  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001a201  mov     ebx, eax
0x18001a203  xor     r14d, r14d
0x18001a206  test    eax, eax
0x18001a208  js      loc_18001A666
0x18001a20e  mov     rdx, rdi; unsigned __int16 *
0x18001a211  mov     rcx, rsi; this
0x18001a214  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18001a219  mov     ebx, eax
0x18001a21b  test    eax, eax
0x18001a21d  lea     rcx, [rsp+22E0h+hKey]; this
0x18001a222  js      loc_18001A66B
0x18001a228  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001a22d  jmp     loc_18001A40D
0x18001a232  lea     rcx, [rsp+22E0h+hKey]; this
0x18001a237  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001a23c  mov     r12d, 1
0x18001a242  lea     rdx, aNoremove; "NoRemove"
0x18001a249  mov     rcx, rdi; lpString1
0x18001a24c  call    cs:__imp_lstrcmpiW
0x18001a252  xor     r14d, r14d
0x18001a255  test    eax, eax
0x18001a257  jnz     short loc_18001A271
0x18001a259  mov     r12d, r14d
0x18001a25c  mov     rdx, rdi; unsigned __int16 *
0x18001a25f  mov     rcx, rsi; this
0x18001a262  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001a267  mov     ebx, eax
0x18001a269  test    eax, eax
0x18001a26b  js      loc_18001A62E
0x18001a271  lea     rdx, aVal; "Val"
0x18001a278  mov     rcx, rdi; lpString1
0x18001a27b  call    cs:__imp_lstrcmpiW
0x18001a281  test    eax, eax
0x18001a283  jnz     loc_18001A36A
0x18001a289  lea     rdx, [rbp+21E0h+ValueName]; unsigned __int16 *
0x18001a290  mov     rcx, rsi; this
0x18001a293  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001a298  mov     ebx, eax
0x18001a29a  test    eax, eax
0x18001a29c  js      loc_18001A62E
0x18001a2a2  mov     rdx, rdi; unsigned __int16 *
0x18001a2a5  mov     rcx, rsi; this
0x18001a2a8  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001a2ad  mov     ebx, eax
0x18001a2af  test    eax, eax
0x18001a2b1  js      loc_18001A62E
0x18001a2b7  cmp     word ptr [rdi], 3Dh ; '='
0x18001a2bb  jnz     loc_18001A629
0x18001a2c1  test    r15d, r15d
0x18001a2c4  jz      short loc_18001A2F8
0x18001a2c6  mov     [rsp+22E0h+var_2290], r14
0x18001a2cb  mov     [rsp+22E0h+var_2288], r14
0x18001a2d0  mov     [rsp+22E0h+hKey], r13
0x18001a2d5  mov     r9, rdi; unsigned __int16 *
0x18001a2d8  lea     r8, [rbp+21E0h+ValueName]; unsigned __int16 *
0x18001a2df  lea     rdx, [rsp+22E0h+hKey]; struct ATL::CRegKey *
0x18001a2e4  mov     rcx, rsi; this
0x18001a2e7  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18001a2ec  mov     ebx, eax
0x18001a2ee  mov     [rsp+22E0h+hKey], r14
0x18001a2f3  jmp     loc_18001A21B
0x18001a2f8  cmp     [rbp+21E0h+arg_20], r14d
0x18001a2ff  jnz     short loc_18001A35A
0x18001a301  test    r12d, r12d
0x18001a304  jz      short loc_18001A35A
0x18001a306  mov     [rsp+22E0h+hKey], r14
0x18001a30b  mov     [rsp+22E0h+var_2290], r14
0x18001a310  mov     [rsp+22E0h+var_2288], r14
0x18001a315  mov     r9d, 20006h; unsigned int
0x18001a31b  xor     r8d, r8d; lpSubKey
0x18001a31e  mov     rdx, r13; hKey
0x18001a321  lea     rcx, [rsp+22E0h+hKey]; this
0x18001a326  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18001a32b  test    eax, eax
0x18001a32d  jnz     loc_18001A65D
0x18001a333  lea     rdx, [rbp+21E0h+ValueName]; lpValueName
0x18001a33a  mov     rcx, [rsp+22E0h+hKey]; hKey
0x18001a33f  call    cs:__imp_RegDeleteValueW
0x18001a345  test    eax, 0FFFFFFFDh
0x18001a34a  jnz     loc_18001A65D
0x18001a350  lea     rcx, [rsp+22E0h+hKey]; this
0x18001a355  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001a35a  mov     rdx, rdi; unsigned __int16 *
0x18001a35d  mov     rcx, rsi; this
0x18001a360  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18001a365  jmp     loc_18001A144
0x18001a36a  mov     edx, 5Ch ; '\'; unsigned __int16
0x18001a36f  mov     rcx, rdi; lpsz
0x18001a372  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18001a377  test    rax, rax
0x18001a37a  jnz     loc_18001A629
0x18001a380  test    r15d, r15d
0x18001a383  jz      loc_18001A45C
0x18001a389  mov     r9d, 2001Fh; unsigned int
0x18001a38f  mov     r8, rdi; lpSubKey
0x18001a392  mov     rdx, r13; hKey
0x18001a395  lea     rcx, [rsp+22E0h+var_2280]; this
0x18001a39a  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18001a39f  test    eax, eax
0x18001a3a1  jz      short loc_18001A3D5
0x18001a3a3  mov     r9d, 20019h; unsigned int
0x18001a3a9  mov     r8, rdi; lpSubKey
0x18001a3ac  mov     rdx, r13; hKey
0x18001a3af  lea     rcx, [rsp+22E0h+var_2280]; this
0x18001a3b4  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18001a3b9  test    eax, eax
0x18001a3bb  jz      short loc_18001A3D5
0x18001a3bd  mov     r8, rdi; lpSubKey
0x18001a3c0  mov     rdx, r13; hKey
0x18001a3c3  lea     rcx, [rsp+22E0h+var_2280]; this
0x18001a3c8  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x18001a3cd  test    eax, eax
0x18001a3cf  jnz     loc_18001A672
0x18001a3d5  mov     rdx, rdi; unsigned __int16 *
0x18001a3d8  mov     rcx, rsi; this
0x18001a3db  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001a3e0  mov     ebx, eax
0x18001a3e2  test    eax, eax
0x18001a3e4  js      loc_18001A62E
0x18001a3ea  cmp     word ptr [rdi], 3Dh ; '='
0x18001a3ee  jnz     short loc_18001A40D
0x18001a3f0  mov     r9, rdi; unsigned __int16 *
0x18001a3f3  xor     r8d, r8d; unsigned __int16 *
0x18001a3f6  lea     rdx, [rsp+22E0h+var_2280]; struct ATL::CRegKey *
0x18001a3fb  mov     rcx, rsi; this
0x18001a3fe  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18001a403  mov     ebx, eax
0x18001a405  test    eax, eax
0x18001a407  js      loc_18001A62E
0x18001a40d  cmp     word ptr [rdi], 7Bh ; '{'
0x18001a411  jnz     loc_18001A14E
0x18001a417  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001a41b  inc     rax
0x18001a41e  cmp     [rdi+rax*2], r14w
0x18001a423  jnz     short loc_18001A41B
0x18001a425  cmp     rax, 1
0x18001a429  jnz     loc_18001A14E
0x18001a42f  mov     [rsp+22E0h+var_22C0], r14d; int
0x18001a434  mov     r9d, r15d; int
0x18001a437  mov     r8, [rsp+22E0h+var_2280]; HKEY
0x18001a43c  mov     rdx, rdi; unsigned __int16 *
0x18001a43f  mov     rcx, rsi; this
0x18001a442  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18001a447  mov     ebx, eax
0x18001a449  test    eax, eax
0x18001a44b  js      loc_18001A62E
0x18001a451  mov     rdx, rdi
0x18001a454  mov     rcx, rsi
0x18001a457  jmp     loc_18001A13F
0x18001a45c  cmp     [rbp+21E0h+arg_20], r14d
0x18001a463  jnz     short loc_18001A480
0x18001a465  mov     r9d, 20019h; unsigned int
0x18001a46b  mov     r8, rdi; lpSubKey
0x18001a46e  mov     rdx, r13; hKey
0x18001a471  lea     rcx, [rsp+22E0h+var_2280]; this
0x18001a476  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18001a47b  mov     r14d, eax
0x18001a47e  jmp     short loc_18001A486
0x18001a480  mov     r14d, 2
0x18001a486  mov     r15d, 1
0x18001a48c  test    r14d, r14d
0x18001a48f  cmovz   r15d, [rbp+21E0h+arg_20]
0x18001a497  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18001a49b  mov     r8, rdi; Source
0x18001a49e  mov     edx, 104h; SizeInWords
0x18001a4a3  lea     rcx, [rbp+21E0h+Destination]; Destination
0x18001a4a7  call    cs:__imp_wcsncpy_s
0x18001a4ad  mov     ecx, eax; int
0x18001a4af  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18001a4b4  mov     rdx, rdi; unsigned __int16 *
0x18001a4b7  mov     rcx, rsi; this
0x18001a4ba  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001a4bf  mov     ebx, eax
0x18001a4c1  test    eax, eax
0x18001a4c3  js      loc_18001A62E
0x18001a4c9  mov     rdx, rdi; unsigned __int16 *
0x18001a4cc  mov     rcx, rsi; this
0x18001a4cf  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18001a4d4  mov     ebx, eax
0x18001a4d6  xor     ecx, ecx
0x18001a4d8  test    eax, eax
0x18001a4da  js      loc_18001A62E
0x18001a4e0  cmp     word ptr [rdi], 7Bh ; '{'
0x18001a4e4  jnz     short loc_18001A535
0x18001a4e6  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001a4ea  inc     rax
0x18001a4ed  cmp     [rdi+rax*2], cx
0x18001a4f1  jnz     short loc_18001A4EA
0x18001a4f3  cmp     rax, 1
0x18001a4f7  jnz     short loc_18001A535
0x18001a4f9  mov     [rsp+22E0h+var_22C0], r15d; int
0x18001a4fe  xor     r9d, r9d; int
0x18001a501  mov     r8, [rsp+22E0h+var_2280]; HKEY
0x18001a506  mov     rdx, rdi; unsigned __int16 *
0x18001a509  mov     rcx, rsi; this
0x18001a50c  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18001a511  mov     ebx, eax
0x18001a513  test    eax, eax
0x18001a515  jns     short loc_18001A520
0x18001a517  test    r15d, r15d
0x18001a51a  jz      loc_18001A62E
0x18001a520  mov     rdx, rdi; unsigned __int16 *
0x18001a523  mov     rcx, rsi; this
0x18001a526  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001a52b  mov     ebx, eax
0x18001a52d  test    eax, eax
0x18001a52f  js      loc_18001A62E
0x18001a535  cmp     r14d, 2
0x18001a539  mov     r15d, [rsp+22E0h+var_22A0]
0x18001a53e  jz      loc_18001A14E
0x18001a544  test    r14d, r14d
0x18001a547  jz      short loc_18001A568
0x18001a549  xor     r12d, r12d
0x18001a54c  cmp     [rbp+21E0h+arg_20], r12d
0x18001a553  jnz     loc_18001A151
0x18001a559  mov     ecx, r14d; unsigned int
0x18001a55c  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18001a561  mov     ebx, eax
0x18001a563  jmp     loc_18001A62E
0x18001a568  xor     r14d, r14d
0x18001a56b  cmp     [rbp+21E0h+arg_20], r14d
0x18001a572  jz      short loc_18001A5B2
0x18001a574  mov     rdx, [rsp+22E0h+var_2280]; HKEY
0x18001a579  call    ?HasSubKeys@CRegParser@ATL@@IEAAHPEAUHKEY__@@@Z; ATL::CRegParser::HasSubKeys(HKEY__ *)
0x18001a57e  test    eax, eax
0x18001a580  jz      short loc_18001A5B2
0x18001a582  lea     rdx, [rbp+21E0h+Destination]; unsigned __int16 *
  ... truncated ...
```
