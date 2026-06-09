# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x18002a62c`
- end: `0x18002ac05`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1497`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x18002a25c`
- `0x18002a62c`

## callees

- `0x1800257c8`
- `0x180025f74`
- `0x180025fe4`
- `0x1800268e8`
- `0x180026a40`
- `0x1800277bc`
- `0x1800283c8`
- `0x180029ac0`
- `0x180029c20`
- `0x18002a148`
- `0x18002a62c`
- `0x18002c110`
- `0x18002c1e0`
- `0x180055030`
- `0x1800550f0`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x18002aa32`
- `msvcrt!wcsncpy_s` at `0x18002aa32`
- `ADVAPI32!RegCreateKeyExW` at `0x18002a933`
- `ADVAPI32!RegCreateKeyExW` at `0x18002a933`
- `ADVAPI32!RegDeleteValueW` at `0x18002a881`
- `ADVAPI32!RegDeleteValueW` at `0x18002a881`
- `KERNEL32!lstrcmpiW` at `0x18002a6a7`
- `KERNEL32!lstrcmpiW` at `0x18002a6ba`
- `KERNEL32!lstrcmpiW` at `0x18002a78e`
- `KERNEL32!lstrcmpiW` at `0x18002a7bd`
- `KERNEL32!lstrcmpiW` at `0x18002a6a7`
- `KERNEL32!lstrcmpiW` at `0x18002a6ba`
- `KERNEL32!lstrcmpiW` at `0x18002a78e`
- `KERNEL32!lstrcmpiW` at `0x18002a7bd`

## string_xrefs

- `0x18002a6b0`: `ForceRemove`
- `0x18002a784`: `NoRemove`
- `0x18002a69d`: `Delete`

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
  errno_t v20; // eax
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
  wchar_t Destination[264]; // [rsp+A0h] [rbp-60h] BYREF
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
        v20 = wcsncpy_s(Destination, 0x104u, v7, 0xFFFFFFFFFFFFFFFFuLL);
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
            if ( ATL::CRegParser::CanForceRemoveKey(v21, Destination) && v14 )
              ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v30, Destination);
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
              v15 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&hKey, Destination);
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
0x18002a62c  push    rbp
0x18002a62e  push    rbx
0x18002a62f  push    rsi
0x18002a630  push    rdi
0x18002a631  push    r12
0x18002a633  push    r13
0x18002a635  push    r14
0x18002a637  push    r15
0x18002a639  lea     rbp, [rsp-21C8h]
0x18002a641  mov     eax, 22C8h
0x18002a646  call    _alloca_probe
0x18002a64b  sub     rsp, rax
0x18002a64e  mov     rax, cs:__security_cookie
0x18002a655  xor     rax, rsp
0x18002a658  mov     [rbp+2200h+var_50], rax
0x18002a65f  mov     r15d, r9d
0x18002a662  mov     [rsp+2300h+var_22B0], r9d
0x18002a667  mov     r13, r8
0x18002a66a  mov     rdi, rdx
0x18002a66d  mov     rsi, rcx
0x18002a670  xor     r14d, r14d
0x18002a673  mov     [rsp+2300h+var_2290], r14
0x18002a678  mov     [rsp+2300h+var_2288], r14
0x18002a67d  mov     [rbp+2200h+var_2280], r14
0x18002a681  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002a686  test    eax, eax
0x18002a688  mov     ebx, eax
0x18002a68a  js      loc_18002ABB9
0x18002a690  xor     r12d, r12d
0x18002a693  cmp     word ptr [rdi], 7Dh ; '}'
0x18002a697  jz      loc_18002ABB9
0x18002a69d  lea     rdx, String2; "Delete"
0x18002a6a4  mov     rcx, rdi; lpString1
0x18002a6a7  call    cs:__imp_lstrcmpiW
0x18002a6ad  mov     r14d, eax
0x18002a6b0  lea     rdx, aForceremove; "ForceRemove"
0x18002a6b7  mov     rcx, rdi; lpString1
0x18002a6ba  call    cs:__imp_lstrcmpiW
0x18002a6c0  test    eax, eax
0x18002a6c2  jz      short loc_18002A6CD
0x18002a6c4  test    r14d, r14d
0x18002a6c7  jnz     loc_18002A77E
0x18002a6cd  mov     rdx, rdi; unsigned __int16 *
0x18002a6d0  mov     rcx, rsi; this
0x18002a6d3  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002a6d8  mov     ebx, eax
0x18002a6da  test    eax, eax
0x18002a6dc  js      loc_18002ABB9
0x18002a6e2  test    r15d, r15d
0x18002a6e5  jz      loc_18002A77E
0x18002a6eb  mov     [rsp+2300h+hKey], r12
0x18002a6f0  mov     [rsp+2300h+var_22A0], r12
0x18002a6f5  mov     [rsp+2300h+var_2298], r12
0x18002a6fa  mov     edx, 5Ch ; '\'; unsigned __int16
0x18002a6ff  mov     rcx, rdi; lpsz
0x18002a702  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18002a707  test    rax, rax
0x18002a70a  jnz     loc_18002ABAA
0x18002a710  mov     rdx, rdi; unsigned __int16 *
0x18002a713  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x18002a718  test    eax, eax
0x18002a71a  jz      short loc_18002A733
0x18002a71c  mov     [rsp+2300h+hKey], r13
0x18002a721  mov     rdx, rdi; unsigned __int16 *
0x18002a724  lea     rcx, [rsp+2300h+hKey]; this
0x18002a729  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18002a72e  mov     [rsp+2300h+hKey], r12
0x18002a733  test    r14d, r14d
0x18002a736  jnz     short loc_18002A774
0x18002a738  mov     rdx, rdi; unsigned __int16 *
0x18002a73b  mov     rcx, rsi; this
0x18002a73e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002a743  mov     ebx, eax
0x18002a745  xor     r14d, r14d
0x18002a748  test    eax, eax
0x18002a74a  js      loc_18002ABF1
0x18002a750  mov     rdx, rdi; unsigned __int16 *
0x18002a753  mov     rcx, rsi; this
0x18002a756  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18002a75b  mov     ebx, eax
0x18002a75d  test    eax, eax
0x18002a75f  lea     rcx, [rsp+2300h+hKey]; this
0x18002a764  js      loc_18002ABF6
0x18002a76a  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18002a76f  jmp     loc_18002A998
0x18002a774  lea     rcx, [rsp+2300h+hKey]; this
0x18002a779  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18002a77e  mov     r12d, 1
0x18002a784  lea     rdx, aNoremove; "NoRemove"
0x18002a78b  mov     rcx, rdi; lpString1
0x18002a78e  call    cs:__imp_lstrcmpiW
0x18002a794  xor     r14d, r14d
0x18002a797  test    eax, eax
0x18002a799  jnz     short loc_18002A7B3
0x18002a79b  mov     r12d, r14d
0x18002a79e  mov     rdx, rdi; unsigned __int16 *
0x18002a7a1  mov     rcx, rsi; this
0x18002a7a4  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002a7a9  mov     ebx, eax
0x18002a7ab  test    eax, eax
0x18002a7ad  js      loc_18002ABB9
0x18002a7b3  lea     rdx, aVal; "Val"
0x18002a7ba  mov     rcx, rdi; lpString1
0x18002a7bd  call    cs:__imp_lstrcmpiW
0x18002a7c3  test    eax, eax
0x18002a7c5  jnz     loc_18002A8AC
0x18002a7cb  lea     rdx, [rbp+2200h+ValueName]; unsigned __int16 *
0x18002a7d2  mov     rcx, rsi; this
0x18002a7d5  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002a7da  mov     ebx, eax
0x18002a7dc  test    eax, eax
0x18002a7de  js      loc_18002ABB9
0x18002a7e4  mov     rdx, rdi; unsigned __int16 *
0x18002a7e7  mov     rcx, rsi; this
0x18002a7ea  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002a7ef  mov     ebx, eax
0x18002a7f1  test    eax, eax
0x18002a7f3  js      loc_18002ABB9
0x18002a7f9  cmp     word ptr [rdi], 3Dh ; '='
0x18002a7fd  jnz     loc_18002ABB4
0x18002a803  test    r15d, r15d
0x18002a806  jz      short loc_18002A83A
0x18002a808  mov     [rsp+2300h+var_22A0], r14
0x18002a80d  mov     [rsp+2300h+var_2298], r14
0x18002a812  mov     [rsp+2300h+hKey], r13
0x18002a817  mov     r9, rdi; unsigned __int16 *
0x18002a81a  lea     r8, [rbp+2200h+ValueName]; unsigned __int16 *
0x18002a821  lea     rdx, [rsp+2300h+hKey]; struct ATL::CRegKey *
0x18002a826  mov     rcx, rsi; this
0x18002a829  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18002a82e  mov     ebx, eax
0x18002a830  mov     [rsp+2300h+hKey], r14
0x18002a835  jmp     loc_18002A75D
0x18002a83a  cmp     [rbp+2200h+arg_20], r14d
0x18002a841  jnz     short loc_18002A89C
0x18002a843  test    r12d, r12d
0x18002a846  jz      short loc_18002A89C
0x18002a848  mov     [rsp+2300h+hKey], r14
0x18002a84d  mov     [rsp+2300h+var_22A0], r14
0x18002a852  mov     [rsp+2300h+var_2298], r14
0x18002a857  mov     r9d, 20006h; unsigned int
0x18002a85d  xor     r8d, r8d; lpSubKey
0x18002a860  mov     rdx, r13; hKey
0x18002a863  lea     rcx, [rsp+2300h+hKey]; this
0x18002a868  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18002a86d  test    eax, eax
0x18002a86f  jnz     loc_18002ABE8
0x18002a875  lea     rdx, [rbp+2200h+ValueName]; lpValueName
0x18002a87c  mov     rcx, [rsp+2300h+hKey]; hKey
0x18002a881  call    cs:__imp_RegDeleteValueW
0x18002a887  test    eax, 0FFFFFFFDh
0x18002a88c  jnz     loc_18002ABE8
0x18002a892  lea     rcx, [rsp+2300h+hKey]; this
0x18002a897  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18002a89c  mov     rdx, rdi; unsigned __int16 *
0x18002a89f  mov     rcx, rsi; this
0x18002a8a2  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18002a8a7  jmp     loc_18002A686
0x18002a8ac  mov     edx, 5Ch ; '\'; unsigned __int16
0x18002a8b1  mov     rcx, rdi; lpsz
0x18002a8b4  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18002a8b9  test    rax, rax
0x18002a8bc  jnz     loc_18002ABB4
0x18002a8c2  test    r15d, r15d
0x18002a8c5  jz      loc_18002A9E7
0x18002a8cb  mov     ebx, 2001Fh
0x18002a8d0  mov     r9d, ebx; unsigned int
0x18002a8d3  mov     r8, rdi; lpSubKey
0x18002a8d6  mov     rdx, r13; hKey
0x18002a8d9  lea     rcx, [rsp+2300h+var_2290]; this
0x18002a8de  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18002a8e3  test    eax, eax
0x18002a8e5  jz      short loc_18002A960
0x18002a8e7  lea     r9d, [rbx-6]; unsigned int
0x18002a8eb  mov     r8, rdi; lpSubKey
0x18002a8ee  mov     rdx, r13; hKey
0x18002a8f1  lea     rcx, [rsp+2300h+var_2290]; this
0x18002a8f6  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18002a8fb  test    eax, eax
0x18002a8fd  jz      short loc_18002A960
0x18002a8ff  mov     [rbp+2200h+dwDisposition], r14d
0x18002a903  mov     [rbp+2200h+var_2270], r14
0x18002a907  lea     rax, [rbp+2200h+dwDisposition]
0x18002a90b  mov     [rsp+2300h+lpdwDisposition], rax; lpdwDisposition
0x18002a910  lea     rax, [rbp+2200h+var_2270]
0x18002a914  mov     [rsp+2300h+phkResult], rax; phkResult
0x18002a919  mov     [rsp+2300h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18002a91e  mov     [rsp+2300h+samDesired], ebx; samDesired
0x18002a922  mov     [rsp+2300h+dwOptions], r14d; dwOptions
0x18002a927  xor     r9d, r9d; lpClass
0x18002a92a  xor     r8d, r8d; Reserved
0x18002a92d  mov     rdx, rdi; lpSubKey
0x18002a930  mov     rcx, r13; hKey
0x18002a933  call    cs:__imp_RegCreateKeyExW
0x18002a939  mov     ecx, eax
0x18002a93b  test    eax, eax
0x18002a93d  jnz     loc_18002AAE7
0x18002a943  lea     rcx, [rsp+2300h+var_2290]; this
0x18002a948  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18002a94d  mov     ecx, eax
0x18002a94f  mov     rax, [rbp+2200h+var_2270]
0x18002a953  mov     [rsp+2300h+var_2290], rax
0x18002a958  test    ecx, ecx
0x18002a95a  jnz     loc_18002AAE7
0x18002a960  mov     rdx, rdi; unsigned __int16 *
0x18002a963  mov     rcx, rsi; this
0x18002a966  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002a96b  mov     ebx, eax
0x18002a96d  test    eax, eax
0x18002a96f  js      loc_18002ABB9
0x18002a975  cmp     word ptr [rdi], 3Dh ; '='
0x18002a979  jnz     short loc_18002A998
0x18002a97b  mov     r9, rdi; unsigned __int16 *
0x18002a97e  xor     r8d, r8d; unsigned __int16 *
0x18002a981  lea     rdx, [rsp+2300h+var_2290]; struct ATL::CRegKey *
0x18002a986  mov     rcx, rsi; this
0x18002a989  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18002a98e  mov     ebx, eax
0x18002a990  test    eax, eax
0x18002a992  js      loc_18002ABB9
0x18002a998  cmp     word ptr [rdi], 7Bh ; '{'
0x18002a99c  jnz     loc_18002A690
0x18002a9a2  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002a9a6  inc     rax
0x18002a9a9  cmp     [rdi+rax*2], r14w
0x18002a9ae  jnz     short loc_18002A9A6
0x18002a9b0  cmp     rax, 1
0x18002a9b4  jnz     loc_18002A690
0x18002a9ba  mov     [rsp+2300h+dwOptions], r14d; int
0x18002a9bf  mov     r9d, r15d; int
0x18002a9c2  mov     r8, [rsp+2300h+var_2290]; HKEY
0x18002a9c7  mov     rdx, rdi; unsigned __int16 *
0x18002a9ca  mov     rcx, rsi; this
0x18002a9cd  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18002a9d2  mov     ebx, eax
0x18002a9d4  test    eax, eax
0x18002a9d6  js      loc_18002ABB9
0x18002a9dc  mov     rdx, rdi
0x18002a9df  mov     rcx, rsi
0x18002a9e2  jmp     loc_18002A681
0x18002a9e7  cmp     [rbp+2200h+arg_20], r14d
0x18002a9ee  jnz     short loc_18002AA0B
0x18002a9f0  mov     r9d, 20019h; unsigned int
0x18002a9f6  mov     r8, rdi; lpSubKey
0x18002a9f9  mov     rdx, r13; hKey
0x18002a9fc  lea     rcx, [rsp+2300h+var_2290]; this
0x18002aa01  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18002aa06  mov     r14d, eax
0x18002aa09  jmp     short loc_18002AA11
0x18002aa0b  mov     r14d, 2
0x18002aa11  mov     r15d, 1
0x18002aa17  test    r14d, r14d
0x18002aa1a  cmovz   r15d, [rbp+2200h+arg_20]
0x18002aa22  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18002aa26  mov     r8, rdi; Source
0x18002aa29  mov     edx, 104h; SizeInWords
0x18002aa2e  lea     rcx, [rbp+2200h+Destination]; Destination
0x18002aa32  call    cs:__imp_wcsncpy_s
0x18002aa38  mov     ecx, eax; int
0x18002aa3a  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18002aa3f  mov     rdx, rdi; unsigned __int16 *
0x18002aa42  mov     rcx, rsi; this
0x18002aa45  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002aa4a  mov     ebx, eax
0x18002aa4c  test    eax, eax
0x18002aa4e  js      loc_18002ABB9
0x18002aa54  mov     rdx, rdi; unsigned __int16 *
0x18002aa57  mov     rcx, rsi; this
0x18002aa5a  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18002aa5f  mov     ebx, eax
0x18002aa61  xor     ecx, ecx
0x18002aa63  test    eax, eax
0x18002aa65  js      loc_18002ABB9
0x18002aa6b  cmp     word ptr [rdi], 7Bh ; '{'
0x18002aa6f  jnz     short loc_18002AAC0
0x18002aa71  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002aa75  inc     rax
0x18002aa78  cmp     [rdi+rax*2], cx
0x18002aa7c  jnz     short loc_18002AA75
0x18002aa7e  cmp     rax, 1
0x18002aa82  jnz     short loc_18002AAC0
0x18002aa84  mov     [rsp+2300h+dwOptions], r15d; int
0x18002aa89  xor     r9d, r9d; int
0x18002aa8c  mov     r8, [rsp+2300h+var_2290]; HKEY
0x18002aa91  mov     rdx, rdi; unsigned __int16 *
0x18002aa94  mov     rcx, rsi; this
0x18002aa97  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18002aa9c  mov     ebx, eax
0x18002aa9e  test    eax, eax
0x18002aaa0  jns     short loc_18002AAAB
0x18002aaa2  test    r15d, r15d
0x18002aaa5  jz      loc_18002ABB9
0x18002aaab  mov     rdx, rdi; unsigned __int16 *
0x18002aaae  mov     rcx, rsi; this
0x18002aab1  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002aab6  mov     ebx, eax
0x18002aab8  test    eax, eax
0x18002aaba  js      loc_18002ABB9
0x18002aac0  cmp     r14d, 2
0x18002aac4  mov     r15d, [rsp+2300h+var_22B0]
  ... truncated ...
```
