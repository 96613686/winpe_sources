# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x18004b974`
- end: `0x18004bf78`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1540`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x18004b600`
- `0x18004b974`

## callees

- `0x180033f60`
- `0x180041cb0`
- `0x180042294`
- `0x180042308`
- `0x180042474`
- `0x1800426c0`
- `0x180043130`
- `0x180048394`
- `0x18004a138`
- `0x18004aa2c`
- `0x18004b108`
- `0x18004b974`
- `0x18004d3f0`
- `0x18004fe74`
- `0x1800cae70`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18004bd9e`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18004bd9e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004bc99`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004bc99`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18004bbe1`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18004bbe1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18004b9ef`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18004ba08`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18004bae2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18004bb17`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18004b9ef`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18004ba08`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18004bae2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18004bb17`

## string_xrefs

- `0x18004b9fe`: `ForceRemove`
- `0x18004bad8`: `NoRemove`
- `0x18004b9e5`: `Delete`

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
0x18004b974  push    rbp
0x18004b976  push    rbx
0x18004b977  push    rsi
0x18004b978  push    rdi
0x18004b979  push    r12
0x18004b97b  push    r13
0x18004b97d  push    r14
0x18004b97f  push    r15
0x18004b981  lea     rbp, [rsp-21C8h]
0x18004b989  mov     eax, 22C8h
0x18004b98e  call    _alloca_probe
0x18004b993  sub     rsp, rax
0x18004b996  mov     rax, cs:__security_cookie
0x18004b99d  xor     rax, rsp
0x18004b9a0  mov     [rbp+2200h+var_50], rax
0x18004b9a7  mov     r15d, r9d
0x18004b9aa  mov     [rsp+2300h+var_22B0], r9d
0x18004b9af  mov     r13, r8
0x18004b9b2  mov     rdi, rdx
0x18004b9b5  mov     rsi, rcx
0x18004b9b8  xor     r14d, r14d
0x18004b9bb  mov     [rsp+2300h+var_2290], r14
0x18004b9c0  mov     [rsp+2300h+var_2288], r14
0x18004b9c5  mov     [rbp+2200h+var_2280], r14
0x18004b9c9  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18004b9ce  test    eax, eax
0x18004b9d0  mov     ebx, eax
0x18004b9d2  js      loc_18004BF2B
0x18004b9d8  xor     r12d, r12d
0x18004b9db  cmp     word ptr [rdi], 7Dh ; '}'
0x18004b9df  jz      loc_18004BF2B
0x18004b9e5  lea     rdx, String2; "Delete"
0x18004b9ec  mov     rcx, rdi; lpString1
0x18004b9ef  call    cs:__imp_lstrcmpiW
0x18004b9f6  nop     dword ptr [rax+rax+00h]
0x18004b9fb  mov     r14d, eax
0x18004b9fe  lea     rdx, aForceremove; "ForceRemove"
0x18004ba05  mov     rcx, rdi; lpString1
0x18004ba08  call    cs:__imp_lstrcmpiW
0x18004ba0f  nop     dword ptr [rax+rax+00h]
0x18004ba14  test    eax, eax
0x18004ba16  jz      short loc_18004BA21
0x18004ba18  test    r14d, r14d
0x18004ba1b  jnz     loc_18004BAD2
0x18004ba21  mov     rdx, rdi; unsigned __int16 *
0x18004ba24  mov     rcx, rsi; this
0x18004ba27  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18004ba2c  mov     ebx, eax
0x18004ba2e  test    eax, eax
0x18004ba30  js      loc_18004BF2B
0x18004ba36  test    r15d, r15d
0x18004ba39  jz      loc_18004BAD2
0x18004ba3f  mov     [rsp+2300h+hKey], r12
0x18004ba44  mov     [rsp+2300h+var_22A0], r12
0x18004ba49  mov     [rsp+2300h+var_2298], r12
0x18004ba4e  mov     edx, 5Ch ; '\'; unsigned __int16
0x18004ba53  mov     rcx, rdi; lpsz
0x18004ba56  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18004ba5b  test    rax, rax
0x18004ba5e  jnz     loc_18004BF1C
0x18004ba64  mov     rdx, rdi; unsigned __int16 *
0x18004ba67  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x18004ba6c  test    eax, eax
0x18004ba6e  jz      short loc_18004BA87
0x18004ba70  mov     [rsp+2300h+hKey], r13
0x18004ba75  mov     rdx, rdi; unsigned __int16 *
0x18004ba78  lea     rcx, [rsp+2300h+hKey]; this
0x18004ba7d  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18004ba82  mov     [rsp+2300h+hKey], r12
0x18004ba87  test    r14d, r14d
0x18004ba8a  jnz     short loc_18004BAC8
0x18004ba8c  mov     rdx, rdi; unsigned __int16 *
0x18004ba8f  mov     rcx, rsi; this
0x18004ba92  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18004ba97  mov     ebx, eax
0x18004ba99  xor     r14d, r14d
0x18004ba9c  test    eax, eax
0x18004ba9e  js      loc_18004BF64
0x18004baa4  mov     rdx, rdi; unsigned __int16 *
0x18004baa7  mov     rcx, rsi; this
0x18004baaa  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18004baaf  mov     ebx, eax
0x18004bab1  test    eax, eax
0x18004bab3  lea     rcx, [rsp+2300h+hKey]; this
0x18004bab8  js      loc_18004BF69
0x18004babe  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18004bac3  jmp     loc_18004BD04
0x18004bac8  lea     rcx, [rsp+2300h+hKey]; this
0x18004bacd  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18004bad2  mov     r12d, 1
0x18004bad8  lea     rdx, aNoremove; "NoRemove"
0x18004badf  mov     rcx, rdi; lpString1
0x18004bae2  call    cs:__imp_lstrcmpiW
0x18004bae9  nop     dword ptr [rax+rax+00h]
0x18004baee  xor     r14d, r14d
0x18004baf1  test    eax, eax
0x18004baf3  jnz     short loc_18004BB0D
0x18004baf5  mov     r12d, r14d
0x18004baf8  mov     rdx, rdi; unsigned __int16 *
0x18004bafb  mov     rcx, rsi; this
0x18004bafe  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18004bb03  mov     ebx, eax
0x18004bb05  test    eax, eax
0x18004bb07  js      loc_18004BF2B
0x18004bb0d  lea     rdx, aVal; "Val"
0x18004bb14  mov     rcx, rdi; lpString1
0x18004bb17  call    cs:__imp_lstrcmpiW
0x18004bb1e  nop     dword ptr [rax+rax+00h]
0x18004bb23  test    eax, eax
0x18004bb25  jnz     loc_18004BC12
0x18004bb2b  lea     rdx, [rbp+2200h+ValueName]; unsigned __int16 *
0x18004bb32  mov     rcx, rsi; this
0x18004bb35  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18004bb3a  mov     ebx, eax
0x18004bb3c  test    eax, eax
0x18004bb3e  js      loc_18004BF2B
0x18004bb44  mov     rdx, rdi; unsigned __int16 *
0x18004bb47  mov     rcx, rsi; this
0x18004bb4a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18004bb4f  mov     ebx, eax
0x18004bb51  test    eax, eax
0x18004bb53  js      loc_18004BF2B
0x18004bb59  cmp     word ptr [rdi], 3Dh ; '='
0x18004bb5d  jnz     loc_18004BF26
0x18004bb63  test    r15d, r15d
0x18004bb66  jz      short loc_18004BB9A
0x18004bb68  mov     [rsp+2300h+var_22A0], r14
0x18004bb6d  mov     [rsp+2300h+var_2298], r14
0x18004bb72  mov     [rsp+2300h+hKey], r13
0x18004bb77  mov     r9, rdi; unsigned __int16 *
0x18004bb7a  lea     r8, [rbp+2200h+ValueName]; unsigned __int16 *
0x18004bb81  lea     rdx, [rsp+2300h+hKey]; struct ATL::CRegKey *
0x18004bb86  mov     rcx, rsi; this
0x18004bb89  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18004bb8e  mov     ebx, eax
0x18004bb90  mov     [rsp+2300h+hKey], r14
0x18004bb95  jmp     loc_18004BAB1
0x18004bb9a  cmp     [rbp+2200h+arg_20], r14d
0x18004bba1  jnz     short loc_18004BC02
0x18004bba3  test    r12d, r12d
0x18004bba6  jz      short loc_18004BC02
0x18004bba8  mov     [rsp+2300h+hKey], r14
0x18004bbad  mov     [rsp+2300h+var_22A0], r14
0x18004bbb2  mov     [rsp+2300h+var_2298], r14
0x18004bbb7  mov     r9d, 20006h; unsigned int
0x18004bbbd  xor     r8d, r8d; lpSubKey
0x18004bbc0  mov     rdx, r13; hKey
0x18004bbc3  lea     rcx, [rsp+2300h+hKey]; this
0x18004bbc8  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18004bbcd  test    eax, eax
0x18004bbcf  jnz     loc_18004BF5B
0x18004bbd5  lea     rdx, [rbp+2200h+ValueName]; lpValueName
0x18004bbdc  mov     rcx, [rsp+2300h+hKey]; hKey
0x18004bbe1  call    cs:__imp_RegDeleteValueW
0x18004bbe8  nop     dword ptr [rax+rax+00h]
0x18004bbed  test    eax, 0FFFFFFFDh
0x18004bbf2  jnz     loc_18004BF5B
0x18004bbf8  lea     rcx, [rsp+2300h+hKey]; this
0x18004bbfd  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18004bc02  mov     rdx, rdi; unsigned __int16 *
0x18004bc05  mov     rcx, rsi; this
0x18004bc08  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18004bc0d  jmp     loc_18004B9CE
0x18004bc12  mov     edx, 5Ch ; '\'; unsigned __int16
0x18004bc17  mov     rcx, rdi; lpsz
0x18004bc1a  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18004bc1f  test    rax, rax
0x18004bc22  jnz     loc_18004BF26
0x18004bc28  test    r15d, r15d
0x18004bc2b  jz      loc_18004BD53
0x18004bc31  mov     ebx, 2001Fh
0x18004bc36  mov     r9d, ebx; unsigned int
0x18004bc39  mov     r8, rdi; lpSubKey
0x18004bc3c  mov     rdx, r13; hKey
0x18004bc3f  lea     rcx, [rsp+2300h+var_2290]; this
0x18004bc44  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18004bc49  test    eax, eax
0x18004bc4b  jz      short loc_18004BCCC
0x18004bc4d  lea     r9d, [rbx-6]; unsigned int
0x18004bc51  mov     r8, rdi; lpSubKey
0x18004bc54  mov     rdx, r13; hKey
0x18004bc57  lea     rcx, [rsp+2300h+var_2290]; this
0x18004bc5c  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18004bc61  test    eax, eax
0x18004bc63  jz      short loc_18004BCCC
0x18004bc65  mov     [rbp+2200h+dwDisposition], r14d
0x18004bc69  mov     [rbp+2200h+var_2270], r14
0x18004bc6d  lea     rax, [rbp+2200h+dwDisposition]
0x18004bc71  mov     [rsp+2300h+lpdwDisposition], rax; lpdwDisposition
0x18004bc76  lea     rax, [rbp+2200h+var_2270]
0x18004bc7a  mov     [rsp+2300h+phkResult], rax; phkResult
0x18004bc7f  mov     [rsp+2300h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18004bc84  mov     [rsp+2300h+samDesired], ebx; samDesired
0x18004bc88  mov     dword ptr [rsp+2300h+dwOptions], r14d; dwOptions
0x18004bc8d  xor     r9d, r9d; lpClass
0x18004bc90  xor     r8d, r8d; Reserved
0x18004bc93  mov     rdx, rdi; lpSubKey
0x18004bc96  mov     rcx, r13; hKey
0x18004bc99  call    cs:__imp_RegCreateKeyExW
0x18004bca0  nop     dword ptr [rax+rax+00h]
0x18004bca5  mov     ecx, eax
0x18004bca7  test    eax, eax
0x18004bca9  jnz     loc_18004BE59
0x18004bcaf  lea     rcx, [rsp+2300h+var_2290]; this
0x18004bcb4  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18004bcb9  mov     ecx, eax
0x18004bcbb  mov     rax, [rbp+2200h+var_2270]
0x18004bcbf  mov     [rsp+2300h+var_2290], rax
0x18004bcc4  test    ecx, ecx
0x18004bcc6  jnz     loc_18004BE59
0x18004bccc  mov     rdx, rdi; unsigned __int16 *
0x18004bccf  mov     rcx, rsi; this
0x18004bcd2  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18004bcd7  mov     ebx, eax
0x18004bcd9  test    eax, eax
0x18004bcdb  js      loc_18004BF2B
0x18004bce1  cmp     word ptr [rdi], 3Dh ; '='
0x18004bce5  jnz     short loc_18004BD04
0x18004bce7  mov     r9, rdi; unsigned __int16 *
0x18004bcea  xor     r8d, r8d; unsigned __int16 *
0x18004bced  lea     rdx, [rsp+2300h+var_2290]; struct ATL::CRegKey *
0x18004bcf2  mov     rcx, rsi; this
0x18004bcf5  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18004bcfa  mov     ebx, eax
0x18004bcfc  test    eax, eax
0x18004bcfe  js      loc_18004BF2B
0x18004bd04  cmp     word ptr [rdi], 7Bh ; '{'
0x18004bd08  jnz     loc_18004B9D8
0x18004bd0e  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004bd12  inc     rax
0x18004bd15  cmp     [rdi+rax*2], r14w
0x18004bd1a  jnz     short loc_18004BD12
0x18004bd1c  cmp     rax, 1
0x18004bd20  jnz     loc_18004B9D8
0x18004bd26  mov     dword ptr [rsp+2300h+dwOptions], r14d; int
0x18004bd2b  mov     r9d, r15d; int
0x18004bd2e  mov     r8, [rsp+2300h+var_2290]; HKEY
0x18004bd33  mov     rdx, rdi; unsigned __int16 *
0x18004bd36  mov     rcx, rsi; this
0x18004bd39  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18004bd3e  mov     ebx, eax
0x18004bd40  test    eax, eax
0x18004bd42  js      loc_18004BF2B
0x18004bd48  mov     rdx, rdi
0x18004bd4b  mov     rcx, rsi
0x18004bd4e  jmp     loc_18004B9C9
0x18004bd53  cmp     [rbp+2200h+arg_20], r14d
0x18004bd5a  jnz     short loc_18004BD77
0x18004bd5c  mov     r9d, 20019h; unsigned int
0x18004bd62  mov     r8, rdi; lpSubKey
0x18004bd65  mov     rdx, r13; hKey
0x18004bd68  lea     rcx, [rsp+2300h+var_2290]; this
0x18004bd6d  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18004bd72  mov     r14d, eax
0x18004bd75  jmp     short loc_18004BD7D
0x18004bd77  mov     r14d, 2
0x18004bd7d  mov     r15d, 1
0x18004bd83  test    r14d, r14d
0x18004bd86  cmovz   r15d, [rbp+2200h+arg_20]
0x18004bd8e  or      r9, 0FFFFFFFFFFFFFFFFh
0x18004bd92  mov     r8, rdi
0x18004bd95  mov     edx, 104h
0x18004bd9a  lea     rcx, [rbp+2200h+var_2260]
0x18004bd9e  call    cs:__imp__o_wcsncpy_s
0x18004bda5  nop     dword ptr [rax+rax+00h]
0x18004bdaa  mov     ecx, eax; int
0x18004bdac  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18004bdb1  mov     rdx, rdi; unsigned __int16 *
0x18004bdb4  mov     rcx, rsi; this
0x18004bdb7  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18004bdbc  mov     ebx, eax
0x18004bdbe  test    eax, eax
0x18004bdc0  js      loc_18004BF2B
0x18004bdc6  mov     rdx, rdi; unsigned __int16 *
0x18004bdc9  mov     rcx, rsi; this
0x18004bdcc  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18004bdd1  mov     ebx, eax
0x18004bdd3  xor     ecx, ecx
0x18004bdd5  test    eax, eax
0x18004bdd7  js      loc_18004BF2B
0x18004bddd  cmp     word ptr [rdi], 7Bh ; '{'
0x18004bde1  jnz     short loc_18004BE32
0x18004bde3  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004bde7  inc     rax
0x18004bdea  cmp     [rdi+rax*2], cx
0x18004bdee  jnz     short loc_18004BDE7
0x18004bdf0  cmp     rax, 1
0x18004bdf4  jnz     short loc_18004BE32
0x18004bdf6  mov     dword ptr [rsp+2300h+dwOptions], r15d; int
0x18004bdfb  xor     r9d, r9d; int
0x18004bdfe  mov     r8, [rsp+2300h+var_2290]; HKEY
0x18004be03  mov     rdx, rdi; unsigned __int16 *
0x18004be06  mov     rcx, rsi; this
0x18004be09  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18004be0e  mov     ebx, eax
0x18004be10  test    eax, eax
0x18004be12  jns     short loc_18004BE1D
0x18004be14  test    r15d, r15d
0x18004be17  jz      loc_18004BF2B
0x18004be1d  mov     rdx, rdi; unsigned __int16 *
  ... truncated ...
```
