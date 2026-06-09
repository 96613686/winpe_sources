# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x180019fa0`
- end: `0x18001a53e`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1438`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180019c9c`
- `0x180019fa0`

## callees

- `0x180018528`
- `0x180018b24`
- `0x180018b70`
- `0x180018d04`
- `0x180018e94`
- `0x180018ec0`
- `0x1800191ec`
- `0x1800194ec`
- `0x180019720`
- `0x180019898`
- `0x180019b88`
- `0x180019fa0`
- `0x18001a778`
- `0x18001a8e0`
- `0x180028f60`
- `0x180028ff0`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x18001a361`
- `msvcrt!wcsncpy_s` at `0x18001a361`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001a1ef`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001a1ef`
- `KERNEL32!lstrcmpiW` at `0x18001a014`
- `KERNEL32!lstrcmpiW` at `0x18001a027`
- `KERNEL32!lstrcmpiW` at `0x18001a0f8`
- `KERNEL32!lstrcmpiW` at `0x18001a127`
- `KERNEL32!lstrcmpiW` at `0x18001a014`
- `KERNEL32!lstrcmpiW` at `0x18001a027`
- `KERNEL32!lstrcmpiW` at `0x18001a0f8`
- `KERNEL32!lstrcmpiW` at `0x18001a127`

## string_xrefs

- `0x18001a01a`: `ForceRemove`
- `0x18001a0e8`: `NoRemove`
- `0x18001a00a`: `Delete`

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
  LSTATUS v15; // eax
  unsigned __int16 *v16; // r9
  unsigned int v17; // ebx
  __int64 v18; // rax
  unsigned int v19; // r14d
  int v20; // r15d
  errno_t v21; // eax
  int v22; // eax
  ATL::CRegParser *v23; // rcx
  __int64 v24; // rax
  int HasSubKeys; // r15d
  unsigned int v26; // r14d
  unsigned int v28; // ecx
  unsigned int v29; // [rsp+20h] [rbp-E0h]
  unsigned int v30; // [rsp+28h] [rbp-D8h]
  struct _SECURITY_ATTRIBUTES *v31; // [rsp+30h] [rbp-D0h]
  unsigned int *v32; // [rsp+38h] [rbp-C8h]
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v35; // [rsp+50h] [rbp-B0h]
  __int64 v36; // [rsp+58h] [rbp-A8h]
  HKEY v37[4]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t Destination[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR ValueName[4096]; // [rsp+290h] [rbp+190h] BYREF

  memset(v37, 0, 24);
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
            v35 = 0;
            v36 = 0;
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
            v35 = 0;
            v36 = 0;
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
          v35 = 0;
          v36 = 0;
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
          v19 = ATL::CRegKey::Open((ATL::CRegKey *)v37, a3, v7, 0x20019u);
        v20 = 1;
        if ( !v19 )
          v20 = a5;
        v21 = wcsncpy_s(Destination, 0x104u, v7, 0xFFFFFFFFFFFFFFFFuLL);
        ATL::AtlCrtErrorCheck(v21);
        v10 = ATL::CRegParser::NextToken(i, v7);
        if ( v10 < 0 )
          goto LABEL_79;
        v22 = ATL::CRegParser::SkipAssignment(i, v7);
        v23 = 0;
        v10 = v22;
        if ( v22 < 0 )
          goto LABEL_79;
        if ( *v7 == 123 )
        {
          v24 = -1;
          do
            ++v24;
          while ( v7[v24] );
          if ( v24 == 1 )
          {
            v10 = ATL::CRegParser::RegisterSubkeys(i, v7, v37[0], 0, v20);
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
          else if ( a5 && ATL::CRegParser::HasSubKeys(v23, v37[0]) )
          {
            if ( ATL::CRegParser::CanForceRemoveKey(v23, Destination) && v14 )
              ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v37, Destination);
          }
          else
          {
            HasSubKeys = ATL::CRegParser::HasSubKeys(v23, v37[0]);
            v26 = ATL::CRegKey::Close((ATL::CRegKey *)v37);
            if ( v26 )
            {
              ATL::CRegKey::Close((ATL::CRegKey *)v37);
              v28 = v26;
              return ATL::AtlHresultFromWin32(v28);
            }
            if ( v14 && !HasSubKeys )
            {
              v35 = 0;
              v36 = 0;
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
      if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v37, a3, v7, 0x2001Fu) )
      {
        if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v37, a3, v7, 0x20019u) )
        {
          v17 = ATL::CRegKey::Create((ATL::CRegKey *)v37, a3, v7, v16, v29, v30, v31, v32);
          if ( v17 )
          {
            ATL::CRegKey::Close((ATL::CRegKey *)v37);
            v28 = v17;
            return ATL::AtlHresultFromWin32(v28);
          }
        }
      }
      v10 = ATL::CRegParser::NextToken(i, v7);
      if ( v10 < 0 )
        goto LABEL_79;
      if ( *v7 == 61 )
      {
        v10 = ATL::CRegParser::AddValue(i, v37, 0, v7);
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
    v10 = ATL::CRegParser::RegisterSubkeys(i, v7, v37[0], v5, 0);
    if ( v10 < 0 )
      break;
    a2 = v7;
  }
LABEL_79:
  ATL::CRegKey::Close((ATL::CRegKey *)v37);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180019fa0  push    rbp
0x180019fa2  push    rbx
0x180019fa3  push    rsi
0x180019fa4  push    rdi
0x180019fa5  push    r12
0x180019fa7  push    r13
0x180019fa9  push    r14
0x180019fab  push    r15
0x180019fad  lea     rbp, [rsp-21A8h]
0x180019fb5  mov     eax, 22A8h
0x180019fba  call    _alloca_probe
0x180019fbf  sub     rsp, rax
0x180019fc2  mov     rax, cs:__security_cookie
0x180019fc9  xor     rax, rsp
0x180019fcc  mov     [rbp+21E0h+var_50], rax
0x180019fd3  xor     r12d, r12d
0x180019fd6  mov     [rsp+22E0h+var_22A0], r9d
0x180019fdb  mov     [rsp+22E0h+var_2280], r12
0x180019fe0  mov     r15d, r9d
0x180019fe3  mov     [rsp+22E0h+var_2278], r12
0x180019fe8  mov     r13, r8
0x180019feb  mov     [rsp+22E0h+var_2270], r12
0x180019ff0  mov     rdi, rdx
0x180019ff3  mov     rsi, rcx
0x180019ff6  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180019ffb  mov     ebx, eax
0x180019ffd  test    eax, eax
0x180019fff  js      loc_18001A4D8
0x18001a005  jmp     loc_18001A45C
0x18001a00a  lea     rdx, String2; "Delete"
0x18001a011  mov     rcx, rdi; lpString1
0x18001a014  call    cs:__imp_lstrcmpiW
0x18001a01a  lea     rdx, aForceremove; "ForceRemove"
0x18001a021  mov     rcx, rdi; lpString1
0x18001a024  mov     r14d, eax
0x18001a027  call    cs:__imp_lstrcmpiW
0x18001a02d  test    eax, eax
0x18001a02f  jz      short loc_18001A03A
0x18001a031  test    r14d, r14d
0x18001a034  jnz     loc_18001A0E8
0x18001a03a  mov     rdx, rdi; unsigned __int16 *
0x18001a03d  mov     rcx, rsi; this
0x18001a040  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001a045  mov     ebx, eax
0x18001a047  test    eax, eax
0x18001a049  js      loc_18001A4D8
0x18001a04f  test    r15d, r15d
0x18001a052  jz      loc_18001A0E8
0x18001a058  mov     edx, 5Ch ; '\'; unsigned __int16
0x18001a05d  mov     [rsp+22E0h+hKey], r12
0x18001a062  mov     rcx, rdi; lpsz
0x18001a065  mov     [rsp+22E0h+var_2290], r12
0x18001a06a  mov     [rsp+22E0h+var_2288], r12
0x18001a06f  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18001a074  test    rax, rax
0x18001a077  jnz     loc_18001A4C9
0x18001a07d  mov     rdx, rdi; unsigned __int16 *
0x18001a080  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x18001a085  test    eax, eax
0x18001a087  jz      short loc_18001A0A0
0x18001a089  mov     rdx, rdi; unsigned __int16 *
0x18001a08c  mov     [rsp+22E0h+hKey], r13
0x18001a091  lea     rcx, [rsp+22E0h+hKey]; this
0x18001a096  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18001a09b  mov     [rsp+22E0h+hKey], r12
0x18001a0a0  test    r14d, r14d
0x18001a0a3  jnz     short loc_18001A0DE
0x18001a0a5  mov     rdx, rdi; unsigned __int16 *
0x18001a0a8  mov     rcx, rsi; this
0x18001a0ab  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001a0b0  mov     ebx, eax
0x18001a0b2  test    eax, eax
0x18001a0b4  js      loc_18001A510
0x18001a0ba  mov     rdx, rdi; unsigned __int16 *
0x18001a0bd  mov     rcx, rsi; this
0x18001a0c0  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18001a0c5  lea     rcx, [rsp+22E0h+hKey]; this
0x18001a0ca  mov     ebx, eax
0x18001a0cc  test    eax, eax
0x18001a0ce  js      loc_18001A515
0x18001a0d4  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001a0d9  jmp     loc_18001A2C7
0x18001a0de  lea     rcx, [rsp+22E0h+hKey]; this
0x18001a0e3  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001a0e8  lea     rdx, aNoremove; "NoRemove"
0x18001a0ef  mov     rcx, rdi; lpString1
0x18001a0f2  mov     r12d, 1
0x18001a0f8  call    cs:__imp_lstrcmpiW
0x18001a0fe  xor     r14d, r14d
0x18001a101  test    eax, eax
0x18001a103  jnz     short loc_18001A11D
0x18001a105  mov     rdx, rdi; unsigned __int16 *
0x18001a108  mov     rcx, rsi; this
0x18001a10b  mov     r12d, r14d
0x18001a10e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001a113  mov     ebx, eax
0x18001a115  test    eax, eax
0x18001a117  js      loc_18001A4D8
0x18001a11d  lea     rdx, aVal; "Val"
0x18001a124  mov     rcx, rdi; lpString1
0x18001a127  call    cs:__imp_lstrcmpiW
0x18001a12d  test    eax, eax
0x18001a12f  jnz     loc_18001A21F
0x18001a135  lea     rdx, [rbp+21E0h+ValueName]; unsigned __int16 *
0x18001a13c  mov     rcx, rsi; this
0x18001a13f  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001a144  mov     ebx, eax
0x18001a146  test    eax, eax
0x18001a148  js      loc_18001A4D8
0x18001a14e  mov     rdx, rdi; unsigned __int16 *
0x18001a151  mov     rcx, rsi; this
0x18001a154  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001a159  mov     ebx, eax
0x18001a15b  test    eax, eax
0x18001a15d  js      loc_18001A4D8
0x18001a163  cmp     word ptr [rdi], 3Dh ; '='
0x18001a167  jnz     loc_18001A4D3
0x18001a16d  test    r15d, r15d
0x18001a170  jz      short loc_18001A1A5
0x18001a172  xor     r12d, r12d
0x18001a175  mov     [rsp+22E0h+hKey], r13
0x18001a17a  mov     r9, rdi; unsigned __int16 *
0x18001a17d  mov     [rsp+22E0h+var_2290], r12
0x18001a182  lea     r8, [rbp+21E0h+ValueName]; unsigned __int16 *
0x18001a189  mov     [rsp+22E0h+var_2288], r12
0x18001a18e  lea     rdx, [rsp+22E0h+hKey]; struct ATL::CRegKey *
0x18001a193  mov     rcx, rsi; this
0x18001a196  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18001a19b  mov     [rsp+22E0h+hKey], r12
0x18001a1a0  jmp     loc_18001A0C5
0x18001a1a5  cmp     [rbp+21E0h+arg_20], r14d
0x18001a1ac  jnz     short loc_18001A20C
0x18001a1ae  test    r12d, r12d
0x18001a1b1  jz      short loc_18001A20C
0x18001a1b3  xor     r12d, r12d
0x18001a1b6  lea     rcx, [rsp+22E0h+hKey]; this
0x18001a1bb  mov     r9d, 20006h; unsigned int
0x18001a1c1  mov     [rsp+22E0h+hKey], r12
0x18001a1c6  xor     r8d, r8d; lpSubKey
0x18001a1c9  mov     [rsp+22E0h+var_2290], r12
0x18001a1ce  mov     rdx, r13; hKey
0x18001a1d1  mov     [rsp+22E0h+var_2288], r12
0x18001a1d6  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18001a1db  test    eax, eax
0x18001a1dd  jnz     loc_18001A507
0x18001a1e3  mov     rcx, [rsp+22E0h+hKey]; hKey
0x18001a1e8  lea     rdx, [rbp+21E0h+ValueName]; lpValueName
0x18001a1ef  call    cs:__imp_RegDeleteValueW
0x18001a1f5  test    eax, 0FFFFFFFDh
0x18001a1fa  jnz     loc_18001A507
0x18001a200  lea     rcx, [rsp+22E0h+hKey]; this
0x18001a205  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001a20a  jmp     short loc_18001A20F
0x18001a20c  xor     r12d, r12d
0x18001a20f  mov     rdx, rdi; unsigned __int16 *
0x18001a212  mov     rcx, rsi; this
0x18001a215  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18001a21a  jmp     loc_180019FFB
0x18001a21f  mov     edx, 5Ch ; '\'; unsigned __int16
0x18001a224  mov     rcx, rdi; lpsz
0x18001a227  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18001a22c  test    rax, rax
0x18001a22f  jnz     loc_18001A4D3
0x18001a235  test    r15d, r15d
0x18001a238  jz      loc_18001A316
0x18001a23e  mov     r9d, 2001Fh; unsigned int
0x18001a244  lea     rcx, [rsp+22E0h+var_2280]; this
0x18001a249  mov     r8, rdi; lpSubKey
0x18001a24c  mov     rdx, r13; hKey
0x18001a24f  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18001a254  xor     r12d, r12d
0x18001a257  test    eax, eax
0x18001a259  jz      short loc_18001A28F
0x18001a25b  mov     r9d, 20019h; unsigned int
0x18001a261  lea     rcx, [rsp+22E0h+var_2280]; this
0x18001a266  mov     r8, rdi; lpSubKey
0x18001a269  mov     rdx, r13; hKey
0x18001a26c  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18001a271  test    eax, eax
0x18001a273  jz      short loc_18001A28F
0x18001a275  mov     r8, rdi; lpSubKey
0x18001a278  lea     rcx, [rsp+22E0h+var_2280]; this
0x18001a27d  mov     rdx, r13; hKey
0x18001a280  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x18001a285  mov     ebx, eax
0x18001a287  test    eax, eax
0x18001a289  jnz     loc_18001A51C
0x18001a28f  mov     rdx, rdi; unsigned __int16 *
0x18001a292  mov     rcx, rsi; this
0x18001a295  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001a29a  mov     ebx, eax
0x18001a29c  test    eax, eax
0x18001a29e  js      loc_18001A4D8
0x18001a2a4  cmp     word ptr [rdi], 3Dh ; '='
0x18001a2a8  jnz     short loc_18001A2C7
0x18001a2aa  mov     r9, rdi; unsigned __int16 *
0x18001a2ad  lea     rdx, [rsp+22E0h+var_2280]; struct ATL::CRegKey *
0x18001a2b2  xor     r8d, r8d; unsigned __int16 *
0x18001a2b5  mov     rcx, rsi; this
0x18001a2b8  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18001a2bd  mov     ebx, eax
0x18001a2bf  test    eax, eax
0x18001a2c1  js      loc_18001A4D8
0x18001a2c7  cmp     word ptr [rdi], 7Bh ; '{'
0x18001a2cb  jnz     loc_18001A45C
0x18001a2d1  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001a2d5  inc     rax
0x18001a2d8  cmp     [rdi+rax*2], r12w
0x18001a2dd  jnz     short loc_18001A2D5
0x18001a2df  cmp     rax, 1
0x18001a2e3  jnz     loc_18001A45C
0x18001a2e9  mov     r8, [rsp+22E0h+var_2280]; HKEY
0x18001a2ee  mov     r9d, r15d; int
0x18001a2f1  mov     rdx, rdi; unsigned __int16 *
0x18001a2f4  mov     [rsp+22E0h+var_22C0], r12d; int
0x18001a2f9  mov     rcx, rsi; this
0x18001a2fc  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18001a301  mov     ebx, eax
0x18001a303  test    eax, eax
0x18001a305  js      loc_18001A4D8
0x18001a30b  mov     rdx, rdi
0x18001a30e  mov     rcx, rsi
0x18001a311  jmp     loc_180019FF6
0x18001a316  cmp     [rbp+21E0h+arg_20], r14d
0x18001a31d  jnz     short loc_18001A33A
0x18001a31f  mov     r9d, 20019h; unsigned int
0x18001a325  lea     rcx, [rsp+22E0h+var_2280]; this
0x18001a32a  mov     r8, rdi; lpSubKey
0x18001a32d  mov     rdx, r13; hKey
0x18001a330  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18001a335  mov     r14d, eax
0x18001a338  jmp     short loc_18001A340
0x18001a33a  mov     r14d, 2
0x18001a340  test    r14d, r14d
0x18001a343  lea     rcx, [rbp+21E0h+Destination]; Destination
0x18001a347  mov     r15d, 1
0x18001a34d  mov     r8, rdi; Source
0x18001a350  cmovz   r15d, [rbp+21E0h+arg_20]
0x18001a358  mov     edx, 104h; SizeInWords
0x18001a35d  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18001a361  call    cs:__imp_wcsncpy_s
0x18001a367  mov     ecx, eax; int
0x18001a369  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18001a36e  mov     rdx, rdi; unsigned __int16 *
0x18001a371  mov     rcx, rsi; this
0x18001a374  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001a379  mov     ebx, eax
0x18001a37b  test    eax, eax
0x18001a37d  js      loc_18001A4D8
0x18001a383  mov     rdx, rdi; unsigned __int16 *
0x18001a386  mov     rcx, rsi; this
0x18001a389  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18001a38e  xor     ecx, ecx; this
0x18001a390  mov     ebx, eax
0x18001a392  test    eax, eax
0x18001a394  js      loc_18001A4D8
0x18001a39a  cmp     word ptr [rdi], 7Bh ; '{'
0x18001a39e  jnz     short loc_18001A3F4
0x18001a3a0  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001a3a4  inc     rax
0x18001a3a7  cmp     [rdi+rax*2], cx
0x18001a3ab  jnz     short loc_18001A3A4
0x18001a3ad  cmp     rax, 1
0x18001a3b1  jnz     short loc_18001A3F4
0x18001a3b3  mov     r8, [rsp+22E0h+var_2280]; HKEY
0x18001a3b8  xor     r9d, r9d; int
0x18001a3bb  mov     rdx, rdi; unsigned __int16 *
0x18001a3be  mov     [rsp+22E0h+var_22C0], r15d; int
0x18001a3c3  mov     rcx, rsi; this
0x18001a3c6  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18001a3cb  mov     ebx, eax
0x18001a3cd  test    eax, eax
0x18001a3cf  jns     short loc_18001A3DA
0x18001a3d1  test    r15d, r15d
0x18001a3d4  jz      loc_18001A4D8
0x18001a3da  mov     rdx, rdi; unsigned __int16 *
0x18001a3dd  mov     rcx, rsi; this
0x18001a3e0  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001a3e5  xor     r15d, r15d
0x18001a3e8  mov     ebx, eax
0x18001a3ea  test    eax, eax
0x18001a3ec  js      loc_18001A4D8
0x18001a3f2  jmp     short loc_18001A3F7
0x18001a3f4  xor     r15d, r15d
0x18001a3f7  cmp     r14d, 2
0x18001a3fb  jz      short loc_18001A454
0x18001a3fd  test    r14d, r14d
0x18001a400  jz      short loc_18001A41D
0x18001a402  xor     r12d, r12d
0x18001a405  cmp     [rbp+21E0h+arg_20], r12d
0x18001a40c  jnz     short loc_18001A457
0x18001a40e  mov     ecx, r14d; unsigned int
0x18001a411  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18001a416  mov     ebx, eax
0x18001a418  jmp     loc_18001A4D8
0x18001a41d  cmp     [rbp+21E0h+arg_20], r15d
0x18001a424  jz      short loc_18001A468
0x18001a426  mov     rdx, [rsp+22E0h+var_2280]; HKEY
0x18001a42b  call    ?HasSubKeys@CRegParser@ATL@@IEAAHPEAUHKEY__@@@Z; ATL::CRegParser::HasSubKeys(HKEY__ *)
0x18001a430  test    eax, eax
  ... truncated ...
```
