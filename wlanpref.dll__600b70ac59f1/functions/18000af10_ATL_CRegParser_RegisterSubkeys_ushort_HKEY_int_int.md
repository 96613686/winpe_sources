# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x18000af10`
- end: `0x18000b4e9`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1497`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x18000ab4c`
- `0x18000af10`

## callees

- `0x18000434c`
- `0x180004c00`
- `0x180004c70`
- `0x1800054e8`
- `0x180005814`
- `0x180007534`
- `0x180007ec8`
- `0x1800085e0`
- `0x180009034`
- `0x18000a8e8`
- `0x18000af10`
- `0x18000b9cc`
- `0x18000bbb8`
- `0x18002d840`
- `0x18002d900`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x18000b316`
- `msvcrt!wcsncpy_s` at `0x18000b316`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000b217`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000b217`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000b165`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000b165`
- `KERNEL32!lstrcmpiW` at `0x18000af8b`
- `KERNEL32!lstrcmpiW` at `0x18000af9e`
- `KERNEL32!lstrcmpiW` at `0x18000b072`
- `KERNEL32!lstrcmpiW` at `0x18000b0a1`
- `KERNEL32!lstrcmpiW` at `0x18000af8b`
- `KERNEL32!lstrcmpiW` at `0x18000af9e`
- `KERNEL32!lstrcmpiW` at `0x18000b072`
- `KERNEL32!lstrcmpiW` at `0x18000b0a1`

## string_xrefs

- `0x18000af94`: `ForceRemove`
- `0x18000b068`: `NoRemove`
- `0x18000af81`: `Delete`

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
0x18000af10  push    rbp
0x18000af12  push    rbx
0x18000af13  push    rsi
0x18000af14  push    rdi
0x18000af15  push    r12
0x18000af17  push    r13
0x18000af19  push    r14
0x18000af1b  push    r15
0x18000af1d  lea     rbp, [rsp-21C8h]
0x18000af25  mov     eax, 22C8h
0x18000af2a  call    _alloca_probe
0x18000af2f  sub     rsp, rax
0x18000af32  mov     rax, cs:__security_cookie
0x18000af39  xor     rax, rsp
0x18000af3c  mov     [rbp+2200h+var_50], rax
0x18000af43  mov     r15d, r9d
0x18000af46  mov     [rsp+2300h+var_22B0], r9d
0x18000af4b  mov     r13, r8
0x18000af4e  mov     rdi, rdx
0x18000af51  mov     rsi, rcx
0x18000af54  xor     r14d, r14d
0x18000af57  mov     [rsp+2300h+var_2290], r14
0x18000af5c  mov     [rsp+2300h+var_2288], r14
0x18000af61  mov     [rbp+2200h+var_2280], r14
0x18000af65  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000af6a  test    eax, eax
0x18000af6c  mov     ebx, eax
0x18000af6e  js      loc_18000B49D
0x18000af74  xor     r12d, r12d
0x18000af77  cmp     word ptr [rdi], 7Dh ; '}'
0x18000af7b  jz      loc_18000B49D
0x18000af81  lea     rdx, String2; "Delete"
0x18000af88  mov     rcx, rdi; lpString1
0x18000af8b  call    cs:__imp_lstrcmpiW
0x18000af91  mov     r14d, eax
0x18000af94  lea     rdx, aForceremove; "ForceRemove"
0x18000af9b  mov     rcx, rdi; lpString1
0x18000af9e  call    cs:__imp_lstrcmpiW
0x18000afa4  test    eax, eax
0x18000afa6  jz      short loc_18000AFB1
0x18000afa8  test    r14d, r14d
0x18000afab  jnz     loc_18000B062
0x18000afb1  mov     rdx, rdi; unsigned __int16 *
0x18000afb4  mov     rcx, rsi; this
0x18000afb7  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000afbc  mov     ebx, eax
0x18000afbe  test    eax, eax
0x18000afc0  js      loc_18000B49D
0x18000afc6  test    r15d, r15d
0x18000afc9  jz      loc_18000B062
0x18000afcf  mov     [rsp+2300h+hKey], r12
0x18000afd4  mov     [rsp+2300h+var_22A0], r12
0x18000afd9  mov     [rsp+2300h+var_2298], r12
0x18000afde  mov     edx, 5Ch ; '\'; unsigned __int16
0x18000afe3  mov     rcx, rdi; lpsz
0x18000afe6  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18000afeb  test    rax, rax
0x18000afee  jnz     loc_18000B48E
0x18000aff4  mov     rdx, rdi; unsigned __int16 *
0x18000aff7  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x18000affc  test    eax, eax
0x18000affe  jz      short loc_18000B017
0x18000b000  mov     [rsp+2300h+hKey], r13
0x18000b005  mov     rdx, rdi; unsigned __int16 *
0x18000b008  lea     rcx, [rsp+2300h+hKey]; this
0x18000b00d  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18000b012  mov     [rsp+2300h+hKey], r12
0x18000b017  test    r14d, r14d
0x18000b01a  jnz     short loc_18000B058
0x18000b01c  mov     rdx, rdi; unsigned __int16 *
0x18000b01f  mov     rcx, rsi; this
0x18000b022  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000b027  mov     ebx, eax
0x18000b029  xor     r14d, r14d
0x18000b02c  test    eax, eax
0x18000b02e  js      loc_18000B4D5
0x18000b034  mov     rdx, rdi; unsigned __int16 *
0x18000b037  mov     rcx, rsi; this
0x18000b03a  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18000b03f  mov     ebx, eax
0x18000b041  test    eax, eax
0x18000b043  lea     rcx, [rsp+2300h+hKey]; this
0x18000b048  js      loc_18000B4DA
0x18000b04e  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000b053  jmp     loc_18000B27C
0x18000b058  lea     rcx, [rsp+2300h+hKey]; this
0x18000b05d  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000b062  mov     r12d, 1
0x18000b068  lea     rdx, aNoremove; "NoRemove"
0x18000b06f  mov     rcx, rdi; lpString1
0x18000b072  call    cs:__imp_lstrcmpiW
0x18000b078  xor     r14d, r14d
0x18000b07b  test    eax, eax
0x18000b07d  jnz     short loc_18000B097
0x18000b07f  mov     r12d, r14d
0x18000b082  mov     rdx, rdi; unsigned __int16 *
0x18000b085  mov     rcx, rsi; this
0x18000b088  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000b08d  mov     ebx, eax
0x18000b08f  test    eax, eax
0x18000b091  js      loc_18000B49D
0x18000b097  lea     rdx, aVal; "Val"
0x18000b09e  mov     rcx, rdi; lpString1
0x18000b0a1  call    cs:__imp_lstrcmpiW
0x18000b0a7  test    eax, eax
0x18000b0a9  jnz     loc_18000B190
0x18000b0af  lea     rdx, [rbp+2200h+ValueName]; unsigned __int16 *
0x18000b0b6  mov     rcx, rsi; this
0x18000b0b9  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000b0be  mov     ebx, eax
0x18000b0c0  test    eax, eax
0x18000b0c2  js      loc_18000B49D
0x18000b0c8  mov     rdx, rdi; unsigned __int16 *
0x18000b0cb  mov     rcx, rsi; this
0x18000b0ce  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000b0d3  mov     ebx, eax
0x18000b0d5  test    eax, eax
0x18000b0d7  js      loc_18000B49D
0x18000b0dd  cmp     word ptr [rdi], 3Dh ; '='
0x18000b0e1  jnz     loc_18000B498
0x18000b0e7  test    r15d, r15d
0x18000b0ea  jz      short loc_18000B11E
0x18000b0ec  mov     [rsp+2300h+var_22A0], r14
0x18000b0f1  mov     [rsp+2300h+var_2298], r14
0x18000b0f6  mov     [rsp+2300h+hKey], r13
0x18000b0fb  mov     r9, rdi; unsigned __int16 *
0x18000b0fe  lea     r8, [rbp+2200h+ValueName]; unsigned __int16 *
0x18000b105  lea     rdx, [rsp+2300h+hKey]; struct ATL::CRegKey *
0x18000b10a  mov     rcx, rsi; this
0x18000b10d  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18000b112  mov     ebx, eax
0x18000b114  mov     [rsp+2300h+hKey], r14
0x18000b119  jmp     loc_18000B041
0x18000b11e  cmp     [rbp+2200h+arg_20], r14d
0x18000b125  jnz     short loc_18000B180
0x18000b127  test    r12d, r12d
0x18000b12a  jz      short loc_18000B180
0x18000b12c  mov     [rsp+2300h+hKey], r14
0x18000b131  mov     [rsp+2300h+var_22A0], r14
0x18000b136  mov     [rsp+2300h+var_2298], r14
0x18000b13b  mov     r9d, 20006h; unsigned int
0x18000b141  xor     r8d, r8d; lpSubKey
0x18000b144  mov     rdx, r13; hKey
0x18000b147  lea     rcx, [rsp+2300h+hKey]; this
0x18000b14c  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000b151  test    eax, eax
0x18000b153  jnz     loc_18000B4CC
0x18000b159  lea     rdx, [rbp+2200h+ValueName]; lpValueName
0x18000b160  mov     rcx, [rsp+2300h+hKey]; hKey
0x18000b165  call    cs:__imp_RegDeleteValueW
0x18000b16b  test    eax, 0FFFFFFFDh
0x18000b170  jnz     loc_18000B4CC
0x18000b176  lea     rcx, [rsp+2300h+hKey]; this
0x18000b17b  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000b180  mov     rdx, rdi; unsigned __int16 *
0x18000b183  mov     rcx, rsi; this
0x18000b186  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18000b18b  jmp     loc_18000AF6A
0x18000b190  mov     edx, 5Ch ; '\'; unsigned __int16
0x18000b195  mov     rcx, rdi; lpsz
0x18000b198  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18000b19d  test    rax, rax
0x18000b1a0  jnz     loc_18000B498
0x18000b1a6  test    r15d, r15d
0x18000b1a9  jz      loc_18000B2CB
0x18000b1af  mov     ebx, 2001Fh
0x18000b1b4  mov     r9d, ebx; unsigned int
0x18000b1b7  mov     r8, rdi; lpSubKey
0x18000b1ba  mov     rdx, r13; hKey
0x18000b1bd  lea     rcx, [rsp+2300h+var_2290]; this
0x18000b1c2  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000b1c7  test    eax, eax
0x18000b1c9  jz      short loc_18000B244
0x18000b1cb  lea     r9d, [rbx-6]; unsigned int
0x18000b1cf  mov     r8, rdi; lpSubKey
0x18000b1d2  mov     rdx, r13; hKey
0x18000b1d5  lea     rcx, [rsp+2300h+var_2290]; this
0x18000b1da  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000b1df  test    eax, eax
0x18000b1e1  jz      short loc_18000B244
0x18000b1e3  mov     [rbp+2200h+dwDisposition], r14d
0x18000b1e7  mov     [rbp+2200h+var_2270], r14
0x18000b1eb  lea     rax, [rbp+2200h+dwDisposition]
0x18000b1ef  mov     [rsp+2300h+lpdwDisposition], rax; lpdwDisposition
0x18000b1f4  lea     rax, [rbp+2200h+var_2270]
0x18000b1f8  mov     [rsp+2300h+phkResult], rax; phkResult
0x18000b1fd  mov     [rsp+2300h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18000b202  mov     [rsp+2300h+samDesired], ebx; samDesired
0x18000b206  mov     [rsp+2300h+dwOptions], r14d; dwOptions
0x18000b20b  xor     r9d, r9d; lpClass
0x18000b20e  xor     r8d, r8d; Reserved
0x18000b211  mov     rdx, rdi; lpSubKey
0x18000b214  mov     rcx, r13; hKey
0x18000b217  call    cs:__imp_RegCreateKeyExW
0x18000b21d  mov     ecx, eax
0x18000b21f  test    eax, eax
0x18000b221  jnz     loc_18000B3CB
0x18000b227  lea     rcx, [rsp+2300h+var_2290]; this
0x18000b22c  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000b231  mov     ecx, eax
0x18000b233  mov     rax, [rbp+2200h+var_2270]
0x18000b237  mov     [rsp+2300h+var_2290], rax
0x18000b23c  test    ecx, ecx
0x18000b23e  jnz     loc_18000B3CB
0x18000b244  mov     rdx, rdi; unsigned __int16 *
0x18000b247  mov     rcx, rsi; this
0x18000b24a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000b24f  mov     ebx, eax
0x18000b251  test    eax, eax
0x18000b253  js      loc_18000B49D
0x18000b259  cmp     word ptr [rdi], 3Dh ; '='
0x18000b25d  jnz     short loc_18000B27C
0x18000b25f  mov     r9, rdi; unsigned __int16 *
0x18000b262  xor     r8d, r8d; unsigned __int16 *
0x18000b265  lea     rdx, [rsp+2300h+var_2290]; struct ATL::CRegKey *
0x18000b26a  mov     rcx, rsi; this
0x18000b26d  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18000b272  mov     ebx, eax
0x18000b274  test    eax, eax
0x18000b276  js      loc_18000B49D
0x18000b27c  cmp     word ptr [rdi], 7Bh ; '{'
0x18000b280  jnz     loc_18000AF74
0x18000b286  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b28a  inc     rax
0x18000b28d  cmp     [rdi+rax*2], r14w
0x18000b292  jnz     short loc_18000B28A
0x18000b294  cmp     rax, 1
0x18000b298  jnz     loc_18000AF74
0x18000b29e  mov     [rsp+2300h+dwOptions], r14d; int
0x18000b2a3  mov     r9d, r15d; int
0x18000b2a6  mov     r8, [rsp+2300h+var_2290]; HKEY
0x18000b2ab  mov     rdx, rdi; unsigned __int16 *
0x18000b2ae  mov     rcx, rsi; this
0x18000b2b1  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000b2b6  mov     ebx, eax
0x18000b2b8  test    eax, eax
0x18000b2ba  js      loc_18000B49D
0x18000b2c0  mov     rdx, rdi
0x18000b2c3  mov     rcx, rsi
0x18000b2c6  jmp     loc_18000AF65
0x18000b2cb  cmp     [rbp+2200h+arg_20], r14d
0x18000b2d2  jnz     short loc_18000B2EF
0x18000b2d4  mov     r9d, 20019h; unsigned int
0x18000b2da  mov     r8, rdi; lpSubKey
0x18000b2dd  mov     rdx, r13; hKey
0x18000b2e0  lea     rcx, [rsp+2300h+var_2290]; this
0x18000b2e5  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000b2ea  mov     r14d, eax
0x18000b2ed  jmp     short loc_18000B2F5
0x18000b2ef  mov     r14d, 2
0x18000b2f5  mov     r15d, 1
0x18000b2fb  test    r14d, r14d
0x18000b2fe  cmovz   r15d, [rbp+2200h+arg_20]
0x18000b306  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18000b30a  mov     r8, rdi; Source
0x18000b30d  mov     edx, 104h; SizeInWords
0x18000b312  lea     rcx, [rbp+2200h+Destination]; Destination
0x18000b316  call    cs:__imp_wcsncpy_s
0x18000b31c  mov     ecx, eax; int
0x18000b31e  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000b323  mov     rdx, rdi; unsigned __int16 *
0x18000b326  mov     rcx, rsi; this
0x18000b329  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000b32e  mov     ebx, eax
0x18000b330  test    eax, eax
0x18000b332  js      loc_18000B49D
0x18000b338  mov     rdx, rdi; unsigned __int16 *
0x18000b33b  mov     rcx, rsi; this
0x18000b33e  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18000b343  mov     ebx, eax
0x18000b345  xor     ecx, ecx
0x18000b347  test    eax, eax
0x18000b349  js      loc_18000B49D
0x18000b34f  cmp     word ptr [rdi], 7Bh ; '{'
0x18000b353  jnz     short loc_18000B3A4
0x18000b355  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b359  inc     rax
0x18000b35c  cmp     [rdi+rax*2], cx
0x18000b360  jnz     short loc_18000B359
0x18000b362  cmp     rax, 1
0x18000b366  jnz     short loc_18000B3A4
0x18000b368  mov     [rsp+2300h+dwOptions], r15d; int
0x18000b36d  xor     r9d, r9d; int
0x18000b370  mov     r8, [rsp+2300h+var_2290]; HKEY
0x18000b375  mov     rdx, rdi; unsigned __int16 *
0x18000b378  mov     rcx, rsi; this
0x18000b37b  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000b380  mov     ebx, eax
0x18000b382  test    eax, eax
0x18000b384  jns     short loc_18000B38F
0x18000b386  test    r15d, r15d
0x18000b389  jz      loc_18000B49D
0x18000b38f  mov     rdx, rdi; unsigned __int16 *
0x18000b392  mov     rcx, rsi; this
0x18000b395  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000b39a  mov     ebx, eax
0x18000b39c  test    eax, eax
0x18000b39e  js      loc_18000B49D
0x18000b3a4  cmp     r14d, 2
0x18000b3a8  mov     r15d, [rsp+2300h+var_22B0]
  ... truncated ...
```
