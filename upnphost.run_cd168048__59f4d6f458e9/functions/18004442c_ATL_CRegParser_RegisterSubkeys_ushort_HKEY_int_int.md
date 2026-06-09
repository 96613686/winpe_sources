# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x18004442c`
- end: `0x1800449ef`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1475`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180044058`
- `0x18004442c`

## callees

- `0x18003cb60`
- `0x180040088`
- `0x1800405e0`
- `0x180040654`
- `0x18004066c`
- `0x1800408b0`
- `0x180040948`
- `0x180041324`
- `0x180042504`
- `0x180042f30`
- `0x1800432f8`
- `0x180043f38`
- `0x18004442c`
- `0x180045748`
- `0x180045a2c`
- `0x180057c40`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18004480b`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18004480b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180044693`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180044693`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800444a0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800444b9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180044590`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800445c5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800444a0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800444b9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180044590`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800445c5`

## string_xrefs

- `0x1800444ac`: `ForceRemove`
- `0x180044580`: `NoRemove`
- `0x180044496`: `Delete`

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
  int v22; // eax
  ATL::CRegParser *v23; // rcx
  __int64 v24; // rax
  int HasSubKeys; // r15d
  unsigned int v26; // r14d
  unsigned int v28; // ecx
  __int64 v29; // [rsp+20h] [rbp-E0h]
  unsigned int v30; // [rsp+28h] [rbp-D8h]
  struct _SECURITY_ATTRIBUTES *v31; // [rsp+30h] [rbp-D0h]
  unsigned int *v32; // [rsp+38h] [rbp-C8h]
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v35; // [rsp+50h] [rbp-B0h]
  __int64 v36; // [rsp+58h] [rbp-A8h]
  HKEY v37[4]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v38[264]; // [rsp+80h] [rbp-80h] BYREF
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
        v21 = _o_wcsncpy_s(v38, 260, v7, -1, v29);
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
            if ( ATL::CRegParser::CanForceRemoveKey(v23, v38) && v14 )
              ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v37, v38);
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
              v15 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&hKey, v38);
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
0x18004442c  push    rbp
0x18004442e  push    rbx
0x18004442f  push    rsi
0x180044430  push    rdi
0x180044431  push    r12
0x180044433  push    r13
0x180044435  push    r14
0x180044437  push    r15
0x180044439  lea     rbp, [rsp-21A8h]
0x180044441  mov     eax, 22A8h
0x180044446  call    _alloca_probe
0x18004444b  sub     rsp, rax
0x18004444e  mov     rax, cs:__security_cookie
0x180044455  xor     rax, rsp
0x180044458  mov     [rbp+21E0h+var_50], rax
0x18004445f  xor     r12d, r12d
0x180044462  mov     [rsp+22E0h+var_22A0], r9d
0x180044467  mov     [rsp+22E0h+var_2280], r12
0x18004446c  mov     r15d, r9d
0x18004446f  mov     [rsp+22E0h+var_2278], r12
0x180044474  mov     r13, r8
0x180044477  mov     [rsp+22E0h+var_2270], r12
0x18004447c  mov     rdi, rdx
0x18004447f  mov     rsi, rcx
0x180044482  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180044487  mov     ebx, eax
0x180044489  test    eax, eax
0x18004448b  js      loc_180044988
0x180044491  jmp     loc_18004490C
0x180044496  lea     rdx, aDelete; "Delete"
0x18004449d  mov     rcx, rdi; lpString1
0x1800444a0  call    cs:__imp_lstrcmpiW
0x1800444a7  nop     dword ptr [rax+rax+00h]
0x1800444ac  lea     rdx, aForceremove; "ForceRemove"
0x1800444b3  mov     rcx, rdi; lpString1
0x1800444b6  mov     r14d, eax
0x1800444b9  call    cs:__imp_lstrcmpiW
0x1800444c0  nop     dword ptr [rax+rax+00h]
0x1800444c5  test    eax, eax
0x1800444c7  jz      short loc_1800444D2
0x1800444c9  test    r14d, r14d
0x1800444cc  jnz     loc_180044580
0x1800444d2  mov     rdx, rdi; unsigned __int16 *
0x1800444d5  mov     rcx, rsi; this
0x1800444d8  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800444dd  mov     ebx, eax
0x1800444df  test    eax, eax
0x1800444e1  js      loc_180044988
0x1800444e7  test    r15d, r15d
0x1800444ea  jz      loc_180044580
0x1800444f0  mov     edx, 5Ch ; '\'; unsigned __int16
0x1800444f5  mov     [rsp+22E0h+hKey], r12
0x1800444fa  mov     rcx, rdi; lpsz
0x1800444fd  mov     [rsp+22E0h+var_2290], r12
0x180044502  mov     [rsp+22E0h+var_2288], r12
0x180044507  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18004450c  test    rax, rax
0x18004450f  jnz     loc_180044979
0x180044515  mov     rdx, rdi; unsigned __int16 *
0x180044518  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x18004451d  test    eax, eax
0x18004451f  jz      short loc_180044538
0x180044521  mov     rdx, rdi; unsigned __int16 *
0x180044524  mov     [rsp+22E0h+hKey], r13
0x180044529  lea     rcx, [rsp+22E0h+hKey]; this
0x18004452e  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180044533  mov     [rsp+22E0h+hKey], r12
0x180044538  test    r14d, r14d
0x18004453b  jnz     short loc_180044576
0x18004453d  mov     rdx, rdi; unsigned __int16 *
0x180044540  mov     rcx, rsi; this
0x180044543  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180044548  mov     ebx, eax
0x18004454a  test    eax, eax
0x18004454c  js      loc_1800449C1
0x180044552  mov     rdx, rdi; unsigned __int16 *
0x180044555  mov     rcx, rsi; this
0x180044558  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18004455d  lea     rcx, [rsp+22E0h+hKey]; this
0x180044562  mov     ebx, eax
0x180044564  test    eax, eax
0x180044566  js      loc_1800449C6
0x18004456c  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180044571  jmp     loc_180044771
0x180044576  lea     rcx, [rsp+22E0h+hKey]; this
0x18004457b  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180044580  lea     rdx, aNoremove; "NoRemove"
0x180044587  mov     rcx, rdi; lpString1
0x18004458a  mov     r12d, 1
0x180044590  call    cs:__imp_lstrcmpiW
0x180044597  nop     dword ptr [rax+rax+00h]
0x18004459c  xor     r14d, r14d
0x18004459f  test    eax, eax
0x1800445a1  jnz     short loc_1800445BB
0x1800445a3  mov     rdx, rdi; unsigned __int16 *
0x1800445a6  mov     rcx, rsi; this
0x1800445a9  mov     r12d, r14d
0x1800445ac  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800445b1  mov     ebx, eax
0x1800445b3  test    eax, eax
0x1800445b5  js      loc_180044988
0x1800445bb  lea     rdx, aVal; "Val"
0x1800445c2  mov     rcx, rdi; lpString1
0x1800445c5  call    cs:__imp_lstrcmpiW
0x1800445cc  nop     dword ptr [rax+rax+00h]
0x1800445d1  test    eax, eax
0x1800445d3  jnz     loc_1800446C9
0x1800445d9  lea     rdx, [rbp+21E0h+ValueName]; unsigned __int16 *
0x1800445e0  mov     rcx, rsi; this
0x1800445e3  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800445e8  mov     ebx, eax
0x1800445ea  test    eax, eax
0x1800445ec  js      loc_180044988
0x1800445f2  mov     rdx, rdi; unsigned __int16 *
0x1800445f5  mov     rcx, rsi; this
0x1800445f8  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800445fd  mov     ebx, eax
0x1800445ff  test    eax, eax
0x180044601  js      loc_180044988
0x180044607  cmp     word ptr [rdi], 3Dh ; '='
0x18004460b  jnz     loc_180044983
0x180044611  test    r15d, r15d
0x180044614  jz      short loc_180044649
0x180044616  xor     r12d, r12d
0x180044619  mov     [rsp+22E0h+hKey], r13
0x18004461e  mov     r9, rdi; unsigned __int16 *
0x180044621  mov     [rsp+22E0h+var_2290], r12
0x180044626  lea     r8, [rbp+21E0h+ValueName]; unsigned __int16 *
0x18004462d  mov     [rsp+22E0h+var_2288], r12
0x180044632  lea     rdx, [rsp+22E0h+hKey]; struct ATL::CRegKey *
0x180044637  mov     rcx, rsi; this
0x18004463a  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18004463f  mov     [rsp+22E0h+hKey], r12
0x180044644  jmp     loc_18004455D
0x180044649  cmp     [rbp+21E0h+arg_20], r14d
0x180044650  jnz     short loc_1800446B6
0x180044652  test    r12d, r12d
0x180044655  jz      short loc_1800446B6
0x180044657  xor     r12d, r12d
0x18004465a  lea     rcx, [rsp+22E0h+hKey]; this
0x18004465f  mov     r9d, 20006h; unsigned int
0x180044665  mov     [rsp+22E0h+hKey], r12
0x18004466a  xor     r8d, r8d; lpSubKey
0x18004466d  mov     [rsp+22E0h+var_2290], r12
0x180044672  mov     rdx, r13; hKey
0x180044675  mov     [rsp+22E0h+var_2288], r12
0x18004467a  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18004467f  test    eax, eax
0x180044681  jnz     loc_1800449B8
0x180044687  mov     rcx, [rsp+22E0h+hKey]; hKey
0x18004468c  lea     rdx, [rbp+21E0h+ValueName]; lpValueName
0x180044693  call    cs:__imp_RegDeleteValueW
0x18004469a  nop     dword ptr [rax+rax+00h]
0x18004469f  test    eax, 0FFFFFFFDh
0x1800446a4  jnz     loc_1800449B8
0x1800446aa  lea     rcx, [rsp+22E0h+hKey]; this
0x1800446af  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800446b4  jmp     short loc_1800446B9
0x1800446b6  xor     r12d, r12d
0x1800446b9  mov     rdx, rdi; unsigned __int16 *
0x1800446bc  mov     rcx, rsi; this
0x1800446bf  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1800446c4  jmp     loc_180044487
0x1800446c9  mov     edx, 5Ch ; '\'; unsigned __int16
0x1800446ce  mov     rcx, rdi; lpsz
0x1800446d1  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x1800446d6  test    rax, rax
0x1800446d9  jnz     loc_180044983
0x1800446df  test    r15d, r15d
0x1800446e2  jz      loc_1800447C0
0x1800446e8  mov     r9d, 2001Fh; unsigned int
0x1800446ee  lea     rcx, [rsp+22E0h+var_2280]; this
0x1800446f3  mov     r8, rdi; lpSubKey
0x1800446f6  mov     rdx, r13; hKey
0x1800446f9  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800446fe  xor     r12d, r12d
0x180044701  test    eax, eax
0x180044703  jz      short loc_180044739
0x180044705  mov     r9d, 20019h; unsigned int
0x18004470b  lea     rcx, [rsp+22E0h+var_2280]; this
0x180044710  mov     r8, rdi; lpSubKey
0x180044713  mov     rdx, r13; hKey
0x180044716  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18004471b  test    eax, eax
0x18004471d  jz      short loc_180044739
0x18004471f  mov     r8, rdi; lpSubKey
0x180044722  lea     rcx, [rsp+22E0h+var_2280]; this
0x180044727  mov     rdx, r13; hKey
0x18004472a  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x18004472f  mov     ebx, eax
0x180044731  test    eax, eax
0x180044733  jnz     loc_1800449CD
0x180044739  mov     rdx, rdi; unsigned __int16 *
0x18004473c  mov     rcx, rsi; this
0x18004473f  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180044744  mov     ebx, eax
0x180044746  test    eax, eax
0x180044748  js      loc_180044988
0x18004474e  cmp     word ptr [rdi], 3Dh ; '='
0x180044752  jnz     short loc_180044771
0x180044754  mov     r9, rdi; unsigned __int16 *
0x180044757  lea     rdx, [rsp+22E0h+var_2280]; struct ATL::CRegKey *
0x18004475c  xor     r8d, r8d; unsigned __int16 *
0x18004475f  mov     rcx, rsi; this
0x180044762  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180044767  mov     ebx, eax
0x180044769  test    eax, eax
0x18004476b  js      loc_180044988
0x180044771  cmp     word ptr [rdi], 7Bh ; '{'
0x180044775  jnz     loc_18004490C
0x18004477b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004477f  inc     rax
0x180044782  cmp     [rdi+rax*2], r12w
0x180044787  jnz     short loc_18004477F
0x180044789  cmp     rax, 1
0x18004478d  jnz     loc_18004490C
0x180044793  mov     r8, [rsp+22E0h+var_2280]; HKEY
0x180044798  mov     r9d, r15d; int
0x18004479b  mov     rdx, rdi; unsigned __int16 *
0x18004479e  mov     dword ptr [rsp+22E0h+var_22C0], r12d; int
0x1800447a3  mov     rcx, rsi; this
0x1800447a6  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800447ab  mov     ebx, eax
0x1800447ad  test    eax, eax
0x1800447af  js      loc_180044988
0x1800447b5  mov     rdx, rdi
0x1800447b8  mov     rcx, rsi
0x1800447bb  jmp     loc_180044482
0x1800447c0  cmp     [rbp+21E0h+arg_20], r14d
0x1800447c7  jnz     short loc_1800447E4
0x1800447c9  mov     r9d, 20019h; unsigned int
0x1800447cf  lea     rcx, [rsp+22E0h+var_2280]; this
0x1800447d4  mov     r8, rdi; lpSubKey
0x1800447d7  mov     rdx, r13; hKey
0x1800447da  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800447df  mov     r14d, eax
0x1800447e2  jmp     short loc_1800447EA
0x1800447e4  mov     r14d, 2
0x1800447ea  test    r14d, r14d
0x1800447ed  lea     rcx, [rbp+21E0h+var_2260]
0x1800447f1  mov     r15d, 1
0x1800447f7  mov     r8, rdi
0x1800447fa  cmovz   r15d, [rbp+21E0h+arg_20]
0x180044802  mov     edx, 104h
0x180044807  or      r9, 0FFFFFFFFFFFFFFFFh
0x18004480b  call    cs:__imp__o_wcsncpy_s
0x180044812  nop     dword ptr [rax+rax+00h]
0x180044817  mov     ecx, eax; int
0x180044819  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18004481e  mov     rdx, rdi; unsigned __int16 *
0x180044821  mov     rcx, rsi; this
0x180044824  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180044829  mov     ebx, eax
0x18004482b  test    eax, eax
0x18004482d  js      loc_180044988
0x180044833  mov     rdx, rdi; unsigned __int16 *
0x180044836  mov     rcx, rsi; this
0x180044839  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18004483e  xor     ecx, ecx; this
0x180044840  mov     ebx, eax
0x180044842  test    eax, eax
0x180044844  js      loc_180044988
0x18004484a  cmp     word ptr [rdi], 7Bh ; '{'
0x18004484e  jnz     short loc_1800448A4
0x180044850  or      rax, 0FFFFFFFFFFFFFFFFh
0x180044854  inc     rax
0x180044857  cmp     [rdi+rax*2], cx
0x18004485b  jnz     short loc_180044854
0x18004485d  cmp     rax, 1
0x180044861  jnz     short loc_1800448A4
0x180044863  mov     r8, [rsp+22E0h+var_2280]; HKEY
0x180044868  xor     r9d, r9d; int
0x18004486b  mov     rdx, rdi; unsigned __int16 *
0x18004486e  mov     dword ptr [rsp+22E0h+var_22C0], r15d; int
0x180044873  mov     rcx, rsi; this
0x180044876  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18004487b  mov     ebx, eax
0x18004487d  test    eax, eax
0x18004487f  jns     short loc_18004488A
0x180044881  test    r15d, r15d
0x180044884  jz      loc_180044988
0x18004488a  mov     rdx, rdi; unsigned __int16 *
0x18004488d  mov     rcx, rsi; this
0x180044890  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180044895  xor     r15d, r15d
0x180044898  mov     ebx, eax
0x18004489a  test    eax, eax
0x18004489c  js      loc_180044988
0x1800448a2  jmp     short loc_1800448A7
0x1800448a4  xor     r15d, r15d
0x1800448a7  cmp     r14d, 2
0x1800448ab  jz      short loc_180044904
0x1800448ad  test    r14d, r14d
0x1800448b0  jz      short loc_1800448CD
0x1800448b2  xor     r12d, r12d
0x1800448b5  cmp     [rbp+21E0h+arg_20], r12d
0x1800448bc  jnz     short loc_180044907
0x1800448be  mov     ecx, r14d; unsigned int
0x1800448c1  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x1800448c6  mov     ebx, eax
  ... truncated ...
```
