# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x18001ae58`
- end: `0x18001b431`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1497`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x18001aa9c`
- `0x18001ae58`

## callees

- `0x1800034b0`
- `0x1800166ec`
- `0x180016efc`
- `0x180016f6c`
- `0x1800172e8`
- `0x180017414`
- `0x1800195c4`
- `0x180019918`
- `0x180019d40`
- `0x180019ea0`
- `0x18001a988`
- `0x18001ae58`
- `0x18001b8bc`
- `0x18001b98c`
- `0x1800ff490`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18001b25e`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18001b25e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001b0ad`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001b0ad`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001b15f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001b15f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001aed3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001aee6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001afba`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001afe9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001aed3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001aee6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001afba`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001afe9`

## string_xrefs

- `0x18001aedc`: `ForceRemove`
- `0x18001afb0`: `NoRemove`
- `0x18001aec9`: `Delete`

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
0x18001ae58  push    rbp
0x18001ae5a  push    rbx
0x18001ae5b  push    rsi
0x18001ae5c  push    rdi
0x18001ae5d  push    r12
0x18001ae5f  push    r13
0x18001ae61  push    r14
0x18001ae63  push    r15
0x18001ae65  lea     rbp, [rsp-21C8h]
0x18001ae6d  mov     eax, 22C8h
0x18001ae72  call    _alloca_probe
0x18001ae77  sub     rsp, rax
0x18001ae7a  mov     rax, cs:__security_cookie
0x18001ae81  xor     rax, rsp
0x18001ae84  mov     [rbp+2200h+var_50], rax
0x18001ae8b  mov     r15d, r9d
0x18001ae8e  mov     [rsp+2300h+var_22B0], r9d
0x18001ae93  mov     r13, r8
0x18001ae96  mov     rdi, rdx
0x18001ae99  mov     rsi, rcx
0x18001ae9c  xor     r14d, r14d
0x18001ae9f  mov     [rsp+2300h+var_2290], r14
0x18001aea4  mov     [rsp+2300h+var_2288], r14
0x18001aea9  mov     [rbp+2200h+var_2280], r14
0x18001aead  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001aeb2  test    eax, eax
0x18001aeb4  mov     ebx, eax
0x18001aeb6  js      loc_18001B3E5
0x18001aebc  xor     r12d, r12d
0x18001aebf  cmp     word ptr [rdi], 7Dh ; '}'
0x18001aec3  jz      loc_18001B3E5
0x18001aec9  lea     rdx, aDelete; "Delete"
0x18001aed0  mov     rcx, rdi; lpString1
0x18001aed3  call    cs:__imp_lstrcmpiW
0x18001aed9  mov     r14d, eax
0x18001aedc  lea     rdx, aForceremove; "ForceRemove"
0x18001aee3  mov     rcx, rdi; lpString1
0x18001aee6  call    cs:__imp_lstrcmpiW
0x18001aeec  test    eax, eax
0x18001aeee  jz      short loc_18001AEF9
0x18001aef0  test    r14d, r14d
0x18001aef3  jnz     loc_18001AFAA
0x18001aef9  mov     rdx, rdi; unsigned __int16 *
0x18001aefc  mov     rcx, rsi; this
0x18001aeff  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001af04  mov     ebx, eax
0x18001af06  test    eax, eax
0x18001af08  js      loc_18001B3E5
0x18001af0e  test    r15d, r15d
0x18001af11  jz      loc_18001AFAA
0x18001af17  mov     [rsp+2300h+hKey], r12
0x18001af1c  mov     [rsp+2300h+var_22A0], r12
0x18001af21  mov     [rsp+2300h+var_2298], r12
0x18001af26  mov     edx, 5Ch ; '\'; unsigned __int16
0x18001af2b  mov     rcx, rdi; lpsz
0x18001af2e  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18001af33  test    rax, rax
0x18001af36  jnz     loc_18001B3D6
0x18001af3c  mov     rdx, rdi; unsigned __int16 *
0x18001af3f  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x18001af44  test    eax, eax
0x18001af46  jz      short loc_18001AF5F
0x18001af48  mov     [rsp+2300h+hKey], r13
0x18001af4d  mov     rdx, rdi; unsigned __int16 *
0x18001af50  lea     rcx, [rsp+2300h+hKey]; this
0x18001af55  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18001af5a  mov     [rsp+2300h+hKey], r12
0x18001af5f  test    r14d, r14d
0x18001af62  jnz     short loc_18001AFA0
0x18001af64  mov     rdx, rdi; unsigned __int16 *
0x18001af67  mov     rcx, rsi; this
0x18001af6a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001af6f  mov     ebx, eax
0x18001af71  xor     r14d, r14d
0x18001af74  test    eax, eax
0x18001af76  js      loc_18001B41D
0x18001af7c  mov     rdx, rdi; unsigned __int16 *
0x18001af7f  mov     rcx, rsi; this
0x18001af82  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18001af87  mov     ebx, eax
0x18001af89  test    eax, eax
0x18001af8b  lea     rcx, [rsp+2300h+hKey]; this
0x18001af90  js      loc_18001B422
0x18001af96  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001af9b  jmp     loc_18001B1C4
0x18001afa0  lea     rcx, [rsp+2300h+hKey]; this
0x18001afa5  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001afaa  mov     r12d, 1
0x18001afb0  lea     rdx, aNoremove; "NoRemove"
0x18001afb7  mov     rcx, rdi; lpString1
0x18001afba  call    cs:__imp_lstrcmpiW
0x18001afc0  xor     r14d, r14d
0x18001afc3  test    eax, eax
0x18001afc5  jnz     short loc_18001AFDF
0x18001afc7  mov     r12d, r14d
0x18001afca  mov     rdx, rdi; unsigned __int16 *
0x18001afcd  mov     rcx, rsi; this
0x18001afd0  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001afd5  mov     ebx, eax
0x18001afd7  test    eax, eax
0x18001afd9  js      loc_18001B3E5
0x18001afdf  lea     rdx, aVal; "Val"
0x18001afe6  mov     rcx, rdi; lpString1
0x18001afe9  call    cs:__imp_lstrcmpiW
0x18001afef  test    eax, eax
0x18001aff1  jnz     loc_18001B0D8
0x18001aff7  lea     rdx, [rbp+2200h+ValueName]; unsigned __int16 *
0x18001affe  mov     rcx, rsi; this
0x18001b001  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001b006  mov     ebx, eax
0x18001b008  test    eax, eax
0x18001b00a  js      loc_18001B3E5
0x18001b010  mov     rdx, rdi; unsigned __int16 *
0x18001b013  mov     rcx, rsi; this
0x18001b016  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001b01b  mov     ebx, eax
0x18001b01d  test    eax, eax
0x18001b01f  js      loc_18001B3E5
0x18001b025  cmp     word ptr [rdi], 3Dh ; '='
0x18001b029  jnz     loc_18001B3E0
0x18001b02f  test    r15d, r15d
0x18001b032  jz      short loc_18001B066
0x18001b034  mov     [rsp+2300h+var_22A0], r14
0x18001b039  mov     [rsp+2300h+var_2298], r14
0x18001b03e  mov     [rsp+2300h+hKey], r13
0x18001b043  mov     r9, rdi; unsigned __int16 *
0x18001b046  lea     r8, [rbp+2200h+ValueName]; unsigned __int16 *
0x18001b04d  lea     rdx, [rsp+2300h+hKey]; struct ATL::CRegKey *
0x18001b052  mov     rcx, rsi; this
0x18001b055  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18001b05a  mov     ebx, eax
0x18001b05c  mov     [rsp+2300h+hKey], r14
0x18001b061  jmp     loc_18001AF89
0x18001b066  cmp     [rbp+2200h+arg_20], r14d
0x18001b06d  jnz     short loc_18001B0C8
0x18001b06f  test    r12d, r12d
0x18001b072  jz      short loc_18001B0C8
0x18001b074  mov     [rsp+2300h+hKey], r14
0x18001b079  mov     [rsp+2300h+var_22A0], r14
0x18001b07e  mov     [rsp+2300h+var_2298], r14
0x18001b083  mov     r9d, 20006h; unsigned int
0x18001b089  xor     r8d, r8d; lpSubKey
0x18001b08c  mov     rdx, r13; hKey
0x18001b08f  lea     rcx, [rsp+2300h+hKey]; this
0x18001b094  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18001b099  test    eax, eax
0x18001b09b  jnz     loc_18001B414
0x18001b0a1  lea     rdx, [rbp+2200h+ValueName]; lpValueName
0x18001b0a8  mov     rcx, [rsp+2300h+hKey]; hKey
0x18001b0ad  call    cs:__imp_RegDeleteValueW
0x18001b0b3  test    eax, 0FFFFFFFDh
0x18001b0b8  jnz     loc_18001B414
0x18001b0be  lea     rcx, [rsp+2300h+hKey]; this
0x18001b0c3  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001b0c8  mov     rdx, rdi; unsigned __int16 *
0x18001b0cb  mov     rcx, rsi; this
0x18001b0ce  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18001b0d3  jmp     loc_18001AEB2
0x18001b0d8  mov     edx, 5Ch ; '\'; unsigned __int16
0x18001b0dd  mov     rcx, rdi; lpsz
0x18001b0e0  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18001b0e5  test    rax, rax
0x18001b0e8  jnz     loc_18001B3E0
0x18001b0ee  test    r15d, r15d
0x18001b0f1  jz      loc_18001B213
0x18001b0f7  mov     ebx, 2001Fh
0x18001b0fc  mov     r9d, ebx; unsigned int
0x18001b0ff  mov     r8, rdi; lpSubKey
0x18001b102  mov     rdx, r13; hKey
0x18001b105  lea     rcx, [rsp+2300h+var_2290]; this
0x18001b10a  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18001b10f  test    eax, eax
0x18001b111  jz      short loc_18001B18C
0x18001b113  lea     r9d, [rbx-6]; unsigned int
0x18001b117  mov     r8, rdi; lpSubKey
0x18001b11a  mov     rdx, r13; hKey
0x18001b11d  lea     rcx, [rsp+2300h+var_2290]; this
0x18001b122  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18001b127  test    eax, eax
0x18001b129  jz      short loc_18001B18C
0x18001b12b  mov     [rbp+2200h+dwDisposition], r14d
0x18001b12f  mov     [rbp+2200h+var_2270], r14
0x18001b133  lea     rax, [rbp+2200h+dwDisposition]
0x18001b137  mov     [rsp+2300h+lpdwDisposition], rax; lpdwDisposition
0x18001b13c  lea     rax, [rbp+2200h+var_2270]
0x18001b140  mov     [rsp+2300h+phkResult], rax; phkResult
0x18001b145  mov     [rsp+2300h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18001b14a  mov     [rsp+2300h+samDesired], ebx; samDesired
0x18001b14e  mov     dword ptr [rsp+2300h+dwOptions], r14d; dwOptions
0x18001b153  xor     r9d, r9d; lpClass
0x18001b156  xor     r8d, r8d; Reserved
0x18001b159  mov     rdx, rdi; lpSubKey
0x18001b15c  mov     rcx, r13; hKey
0x18001b15f  call    cs:__imp_RegCreateKeyExW
0x18001b165  mov     ecx, eax
0x18001b167  test    eax, eax
0x18001b169  jnz     loc_18001B313
0x18001b16f  lea     rcx, [rsp+2300h+var_2290]; this
0x18001b174  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001b179  mov     ecx, eax
0x18001b17b  mov     rax, [rbp+2200h+var_2270]
0x18001b17f  mov     [rsp+2300h+var_2290], rax
0x18001b184  test    ecx, ecx
0x18001b186  jnz     loc_18001B313
0x18001b18c  mov     rdx, rdi; unsigned __int16 *
0x18001b18f  mov     rcx, rsi; this
0x18001b192  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001b197  mov     ebx, eax
0x18001b199  test    eax, eax
0x18001b19b  js      loc_18001B3E5
0x18001b1a1  cmp     word ptr [rdi], 3Dh ; '='
0x18001b1a5  jnz     short loc_18001B1C4
0x18001b1a7  mov     r9, rdi; unsigned __int16 *
0x18001b1aa  xor     r8d, r8d; unsigned __int16 *
0x18001b1ad  lea     rdx, [rsp+2300h+var_2290]; struct ATL::CRegKey *
0x18001b1b2  mov     rcx, rsi; this
0x18001b1b5  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18001b1ba  mov     ebx, eax
0x18001b1bc  test    eax, eax
0x18001b1be  js      loc_18001B3E5
0x18001b1c4  cmp     word ptr [rdi], 7Bh ; '{'
0x18001b1c8  jnz     loc_18001AEBC
0x18001b1ce  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001b1d2  inc     rax
0x18001b1d5  cmp     [rdi+rax*2], r14w
0x18001b1da  jnz     short loc_18001B1D2
0x18001b1dc  cmp     rax, 1
0x18001b1e0  jnz     loc_18001AEBC
0x18001b1e6  mov     dword ptr [rsp+2300h+dwOptions], r14d; int
0x18001b1eb  mov     r9d, r15d; int
0x18001b1ee  mov     r8, [rsp+2300h+var_2290]; HKEY
0x18001b1f3  mov     rdx, rdi; unsigned __int16 *
0x18001b1f6  mov     rcx, rsi; this
0x18001b1f9  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18001b1fe  mov     ebx, eax
0x18001b200  test    eax, eax
0x18001b202  js      loc_18001B3E5
0x18001b208  mov     rdx, rdi
0x18001b20b  mov     rcx, rsi
0x18001b20e  jmp     loc_18001AEAD
0x18001b213  cmp     [rbp+2200h+arg_20], r14d
0x18001b21a  jnz     short loc_18001B237
0x18001b21c  mov     r9d, 20019h; unsigned int
0x18001b222  mov     r8, rdi; lpSubKey
0x18001b225  mov     rdx, r13; hKey
0x18001b228  lea     rcx, [rsp+2300h+var_2290]; this
0x18001b22d  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18001b232  mov     r14d, eax
0x18001b235  jmp     short loc_18001B23D
0x18001b237  mov     r14d, 2
0x18001b23d  mov     r15d, 1
0x18001b243  test    r14d, r14d
0x18001b246  cmovz   r15d, [rbp+2200h+arg_20]
0x18001b24e  or      r9, 0FFFFFFFFFFFFFFFFh
0x18001b252  mov     r8, rdi
0x18001b255  mov     edx, 104h
0x18001b25a  lea     rcx, [rbp+2200h+var_2260]
0x18001b25e  call    cs:__imp__o_wcsncpy_s
0x18001b264  mov     ecx, eax; int
0x18001b266  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18001b26b  mov     rdx, rdi; unsigned __int16 *
0x18001b26e  mov     rcx, rsi; this
0x18001b271  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001b276  mov     ebx, eax
0x18001b278  test    eax, eax
0x18001b27a  js      loc_18001B3E5
0x18001b280  mov     rdx, rdi; unsigned __int16 *
0x18001b283  mov     rcx, rsi; this
0x18001b286  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18001b28b  mov     ebx, eax
0x18001b28d  xor     ecx, ecx
0x18001b28f  test    eax, eax
0x18001b291  js      loc_18001B3E5
0x18001b297  cmp     word ptr [rdi], 7Bh ; '{'
0x18001b29b  jnz     short loc_18001B2EC
0x18001b29d  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001b2a1  inc     rax
0x18001b2a4  cmp     [rdi+rax*2], cx
0x18001b2a8  jnz     short loc_18001B2A1
0x18001b2aa  cmp     rax, 1
0x18001b2ae  jnz     short loc_18001B2EC
0x18001b2b0  mov     dword ptr [rsp+2300h+dwOptions], r15d; int
0x18001b2b5  xor     r9d, r9d; int
0x18001b2b8  mov     r8, [rsp+2300h+var_2290]; HKEY
0x18001b2bd  mov     rdx, rdi; unsigned __int16 *
0x18001b2c0  mov     rcx, rsi; this
0x18001b2c3  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18001b2c8  mov     ebx, eax
0x18001b2ca  test    eax, eax
0x18001b2cc  jns     short loc_18001B2D7
0x18001b2ce  test    r15d, r15d
0x18001b2d1  jz      loc_18001B3E5
0x18001b2d7  mov     rdx, rdi; unsigned __int16 *
0x18001b2da  mov     rcx, rsi; this
0x18001b2dd  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001b2e2  mov     ebx, eax
0x18001b2e4  test    eax, eax
0x18001b2e6  js      loc_18001B3E5
0x18001b2ec  cmp     r14d, 2
0x18001b2f0  mov     r15d, [rsp+2300h+var_22B0]
  ... truncated ...
```
