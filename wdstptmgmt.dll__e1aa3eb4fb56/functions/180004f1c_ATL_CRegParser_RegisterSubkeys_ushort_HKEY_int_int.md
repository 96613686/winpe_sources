# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x180004f1c`
- end: `0x18000551a`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1534`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x180004b10`
- `0x180004f1c`

## callees

- `0x18000304c`
- `0x1800037ac`
- `0x180003820`
- `0x180003fdc`
- `0x1800041b0`
- `0x1800041e0`
- `0x18000448c`
- `0x180004594`
- `0x180004754`
- `0x180004a08`
- `0x180004f1c`
- `0x180005578`
- `0x180005658`
- `0x18001e9f0`
- `0x18001eab0`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x18000534c`
- `msvcrt!wcsncpy_s` at `0x18000534c`
- `KERNEL32!lstrcmpiW` at `0x180004f95`
- `KERNEL32!lstrcmpiW` at `0x180004fae`
- `KERNEL32!lstrcmpiW` at `0x180005082`
- `KERNEL32!lstrcmpiW` at `0x1800050b7`
- `KERNEL32!lstrcmpiW` at `0x180004f95`
- `KERNEL32!lstrcmpiW` at `0x180004fae`
- `KERNEL32!lstrcmpiW` at `0x180005082`
- `KERNEL32!lstrcmpiW` at `0x1800050b7`
- `ADVAPI32!RegCreateKeyExW` at `0x18000524b`
- `ADVAPI32!RegCreateKeyExW` at `0x18000524b`
- `ADVAPI32!RegDeleteValueW` at `0x180005181`
- `ADVAPI32!RegDeleteValueW` at `0x180005181`

## string_xrefs

- `0x180004fa4`: `ForceRemove`
- `0x180005078`: `NoRemove`
- `0x180004f8b`: `Delete`

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
  int v10; // r12d
  int v11; // r14d
  int v12; // ebx
  ATL::CRegParser *v13; // rcx
  int v14; // eax
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
    v12 = Token;
    if ( Token < 0 )
      goto LABEL_81;
    while ( 1 )
    {
      if ( *v7 == 125 )
        goto LABEL_81;
      v10 = 1;
      v11 = lstrcmpiW(v7, L"Delete");
      if ( !lstrcmpiW(v7, L"ForceRemove") || !v11 )
      {
        v12 = ATL::CRegParser::NextToken(v8, v7);
        if ( v12 < 0 )
          goto LABEL_81;
        if ( v5 )
        {
          hKey = 0;
          v28 = 0;
          v29 = 0;
          if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
          {
            ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_80:
            v12 = -2147352567;
            goto LABEL_81;
          }
          if ( ATL::CRegParser::CanForceRemoveKey(v13, v7) )
          {
            hKey = a3;
            ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)&hKey, v7);
            hKey = 0;
          }
          if ( !v11 )
          {
            v12 = ATL::CRegParser::NextToken(v8, v7);
            if ( v12 < 0 )
              goto LABEL_83;
            v14 = ATL::CRegParser::SkipAssignment(v8, v7);
            v12 = v14;
            goto LABEL_14;
          }
          ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
        }
      }
      if ( !lstrcmpiW(v7, L"NoRemove") )
      {
        v10 = 0;
        v12 = ATL::CRegParser::NextToken(v8, v7);
        if ( v12 < 0 )
          goto LABEL_81;
      }
      if ( !lstrcmpiW(v7, L"Val") )
        break;
      if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
        goto LABEL_80;
      if ( v5 )
      {
        if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v30, a3, v7, 0x2001Fu)
          && (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v30, a3, v7, 0x20019u) )
        {
          dwDisposition = 0;
          phkResult = 0;
          v16 = RegCreateKeyExW(a3, v7, 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition);
          if ( !v16 )
          {
            v16 = ATL::CRegKey::Close((ATL::CRegKey *)v30);
            v30[0] = phkResult;
          }
          if ( v16 )
            goto LABEL_67;
        }
        v12 = ATL::CRegParser::NextToken(v8, v7);
        if ( v12 < 0 )
          goto LABEL_81;
        if ( *v7 == 61 )
        {
          v12 = ATL::CRegParser::AddValue(v8, v30, 0, v7);
          if ( v12 < 0 )
            goto LABEL_81;
        }
LABEL_43:
        if ( *v7 == 123 )
        {
          v17 = -1;
          do
            ++v17;
          while ( v7[v17] );
          if ( v17 == 1 )
          {
            v12 = ATL::CRegParser::RegisterSubkeys(v8, v7, v30[0], v5, 0);
            if ( v12 < 0 )
              goto LABEL_81;
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
        v12 = ATL::CRegParser::NextToken(v8, v7);
        if ( v12 < 0 )
          goto LABEL_81;
        v12 = ATL::CRegParser::SkipAssignment(v8, v7);
        v21 = 0;
        if ( v12 < 0 )
          goto LABEL_81;
        if ( *v7 == 123 )
        {
          v22 = -1;
          do
            ++v22;
          while ( v7[v22] );
          if ( v22 == 1 )
          {
            v12 = ATL::CRegParser::RegisterSubkeys(v8, v7, v30[0], 0, v19);
            if ( v12 < 0 && !v19 )
              goto LABEL_81;
            v12 = ATL::CRegParser::NextToken(v8, v7);
            v21 = 0;
            if ( v12 < 0 )
              goto LABEL_81;
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
LABEL_67:
              v12 = ATL::AtlHresultFromWin32(v16);
              goto LABEL_81;
            }
          }
          else if ( a5 && ATL::CRegParser::HasSubKeys(0, v30[0]) )
          {
            if ( ATL::CRegParser::CanForceRemoveKey(v21, Destination) && v10 )
              ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v30, Destination);
          }
          else
          {
            HasSubKeys = ATL::CRegParser::HasSubKeys(v21, v30[0]);
            v24 = ATL::CRegKey::Close((ATL::CRegKey *)v30);
            if ( v24 )
            {
              v16 = v24;
              goto LABEL_67;
            }
            if ( v10 && !HasSubKeys )
            {
              v28 = 0;
              v29 = 0;
              hKey = a3;
              v15 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&hKey, Destination);
              hKey = 0;
              if ( v15 )
                goto LABEL_82;
              ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
            }
            v5 = a4;
          }
        }
      }
    }
    v12 = ATL::CRegParser::NextToken(v8, ValueName);
    if ( v12 < 0 )
      goto LABEL_81;
    v12 = ATL::CRegParser::NextToken(v8, v7);
    if ( v12 < 0 )
      goto LABEL_81;
    if ( *v7 != 61 )
      goto LABEL_80;
    if ( v5 )
    {
      v28 = 0;
      v29 = 0;
      hKey = a3;
      v14 = ATL::CRegParser::AddValue(v8, &hKey, ValueName, v7);
      v12 = v14;
      hKey = 0;
LABEL_14:
      if ( v14 < 0 )
        goto LABEL_83;
      ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
      goto LABEL_43;
    }
    if ( a5 || !v10 )
      goto LABEL_30;
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
LABEL_30:
        Token = ATL::CRegParser::SkipAssignment(v8, v7);
        continue;
      }
    }
    break;
  }
LABEL_82:
  v12 = ATL::AtlHresultFromWin32(v15);
LABEL_83:
  ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_81:
  ATL::CRegKey::Close((ATL::CRegKey *)v30);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180004f1c  push    rbp
0x180004f1e  push    rbx
0x180004f1f  push    rsi
0x180004f20  push    rdi
0x180004f21  push    r12
0x180004f23  push    r13
0x180004f25  push    r14
0x180004f27  push    r15
0x180004f29  lea     rbp, [rsp-21C8h]
0x180004f31  mov     eax, 22C8h
0x180004f36  call    _alloca_probe
0x180004f3b  sub     rsp, rax
0x180004f3e  mov     rax, cs:__security_cookie
0x180004f45  xor     rax, rsp
0x180004f48  mov     [rbp+2200h+var_50], rax
0x180004f4f  mov     r15d, r9d
0x180004f52  mov     [rsp+2300h+var_22B0], r9d
0x180004f57  mov     r13, r8
0x180004f5a  mov     rdi, rdx
0x180004f5d  mov     rsi, rcx
0x180004f60  xor     r14d, r14d
0x180004f63  mov     [rsp+2300h+var_2290], r14
0x180004f68  mov     [rsp+2300h+var_2288], r14
0x180004f6d  mov     [rbp+2200h+var_2280], r14
0x180004f71  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004f76  jmp     loc_1800051AD
0x180004f7b  cmp     word ptr [rdi], 7Dh ; '}'
0x180004f7f  jz      loc_1800054CD
0x180004f85  mov     r12d, 1
0x180004f8b  lea     rdx, String2; "Delete"
0x180004f92  mov     rcx, rdi; lpString1
0x180004f95  call    cs:__imp_lstrcmpiW
0x180004f9c  nop     dword ptr [rax+rax+00h]
0x180004fa1  mov     r14d, eax
0x180004fa4  lea     rdx, aForceremove; "ForceRemove"
0x180004fab  mov     rcx, rdi; lpString1
0x180004fae  call    cs:__imp_lstrcmpiW
0x180004fb5  nop     dword ptr [rax+rax+00h]
0x180004fba  test    eax, eax
0x180004fbc  jz      short loc_180004FC7
0x180004fbe  test    r14d, r14d
0x180004fc1  jnz     loc_180005078
0x180004fc7  mov     rdx, rdi; unsigned __int16 *
0x180004fca  mov     rcx, rsi; this
0x180004fcd  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004fd2  mov     ebx, eax
0x180004fd4  test    eax, eax
0x180004fd6  js      loc_1800054CD
0x180004fdc  xor     ebx, ebx
0x180004fde  test    r15d, r15d
0x180004fe1  jz      loc_180005078
0x180004fe7  mov     [rsp+2300h+hKey], rbx
0x180004fec  mov     [rsp+2300h+var_22A0], rbx
0x180004ff1  mov     [rsp+2300h+var_2298], rbx
0x180004ff6  lea     edx, [rbx+5Ch]; unsigned __int16
0x180004ff9  mov     rcx, rdi; lpsz
0x180004ffc  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180005001  test    rax, rax
0x180005004  jnz     loc_1800054BE
0x18000500a  mov     rdx, rdi; unsigned __int16 *
0x18000500d  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x180005012  test    eax, eax
0x180005014  jz      short loc_18000502D
0x180005016  mov     [rsp+2300h+hKey], r13
0x18000501b  mov     rdx, rdi; unsigned __int16 *
0x18000501e  lea     rcx, [rsp+2300h+hKey]; this
0x180005023  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180005028  mov     [rsp+2300h+hKey], rbx
0x18000502d  test    r14d, r14d
0x180005030  jnz     short loc_18000506E
0x180005032  mov     rdx, rdi; unsigned __int16 *
0x180005035  mov     rcx, rsi; this
0x180005038  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000503d  mov     ebx, eax
0x18000503f  xor     r14d, r14d
0x180005042  test    eax, eax
0x180005044  js      loc_180005506
0x18000504a  mov     rdx, rdi; unsigned __int16 *
0x18000504d  mov     rcx, rsi; this
0x180005050  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180005055  mov     ebx, eax
0x180005057  test    eax, eax
0x180005059  lea     rcx, [rsp+2300h+hKey]; this
0x18000505e  js      loc_18000550B
0x180005064  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180005069  jmp     loc_1800052B2
0x18000506e  lea     rcx, [rsp+2300h+hKey]; this
0x180005073  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180005078  lea     rdx, aNoremove; "NoRemove"
0x18000507f  mov     rcx, rdi; lpString1
0x180005082  call    cs:__imp_lstrcmpiW
0x180005089  nop     dword ptr [rax+rax+00h]
0x18000508e  xor     r14d, r14d
0x180005091  test    eax, eax
0x180005093  jnz     short loc_1800050AD
0x180005095  mov     r12d, r14d
0x180005098  mov     rdx, rdi; unsigned __int16 *
0x18000509b  mov     rcx, rsi; this
0x18000509e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800050a3  mov     ebx, eax
0x1800050a5  test    eax, eax
0x1800050a7  js      loc_1800054CD
0x1800050ad  lea     rdx, aVal; "Val"
0x1800050b4  mov     rcx, rdi; lpString1
0x1800050b7  call    cs:__imp_lstrcmpiW
0x1800050be  nop     dword ptr [rax+rax+00h]
0x1800050c3  test    eax, eax
0x1800050c5  jnz     loc_1800051BC
0x1800050cb  lea     rdx, [rbp+2200h+ValueName]; unsigned __int16 *
0x1800050d2  mov     rcx, rsi; this
0x1800050d5  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800050da  mov     ebx, eax
0x1800050dc  test    eax, eax
0x1800050de  js      loc_1800054CD
0x1800050e4  mov     rdx, rdi; unsigned __int16 *
0x1800050e7  mov     rcx, rsi; this
0x1800050ea  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800050ef  mov     ebx, eax
0x1800050f1  test    eax, eax
0x1800050f3  js      loc_1800054CD
0x1800050f9  cmp     word ptr [rdi], 3Dh ; '='
0x1800050fd  jnz     loc_1800054C8
0x180005103  test    r15d, r15d
0x180005106  jz      short loc_18000513A
0x180005108  mov     [rsp+2300h+var_22A0], r14
0x18000510d  mov     [rsp+2300h+var_2298], r14
0x180005112  mov     [rsp+2300h+hKey], r13
0x180005117  mov     r9, rdi; unsigned __int16 *
0x18000511a  lea     r8, [rbp+2200h+ValueName]; unsigned __int16 *
0x180005121  lea     rdx, [rsp+2300h+hKey]; struct CRegKey *
0x180005126  mov     rcx, rsi; this
0x180005129  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18000512e  mov     ebx, eax
0x180005130  mov     [rsp+2300h+hKey], r14
0x180005135  jmp     loc_180005057
0x18000513a  cmp     [rbp+2200h+arg_20], r14d
0x180005141  jnz     short loc_1800051A2
0x180005143  test    r12d, r12d
0x180005146  jz      short loc_1800051A2
0x180005148  mov     [rsp+2300h+hKey], r14
0x18000514d  mov     [rsp+2300h+var_22A0], r14
0x180005152  mov     [rsp+2300h+var_2298], r14
0x180005157  mov     r9d, 20006h; unsigned int
0x18000515d  xor     r8d, r8d; lpSubKey
0x180005160  mov     rdx, r13; hKey
0x180005163  lea     rcx, [rsp+2300h+hKey]; this
0x180005168  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000516d  test    eax, eax
0x18000516f  jnz     loc_1800054FD
0x180005175  lea     rdx, [rbp+2200h+ValueName]; lpValueName
0x18000517c  mov     rcx, [rsp+2300h+hKey]; hKey
0x180005181  call    cs:__imp_RegDeleteValueW
0x180005188  nop     dword ptr [rax+rax+00h]
0x18000518d  test    eax, 0FFFFFFFDh
0x180005192  jnz     loc_1800054FD
0x180005198  lea     rcx, [rsp+2300h+hKey]; this
0x18000519d  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800051a2  mov     rdx, rdi; unsigned __int16 *
0x1800051a5  mov     rcx, rsi; this
0x1800051a8  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1800051ad  mov     ebx, eax
0x1800051af  test    eax, eax
0x1800051b1  jns     loc_180004F7B
0x1800051b7  jmp     loc_1800054CD
0x1800051bc  mov     edx, 5Ch ; '\'; unsigned __int16
0x1800051c1  mov     rcx, rdi; lpsz
0x1800051c4  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x1800051c9  test    rax, rax
0x1800051cc  jnz     loc_1800054C8
0x1800051d2  test    r15d, r15d
0x1800051d5  jz      loc_180005301
0x1800051db  mov     r9d, 2001Fh; unsigned int
0x1800051e1  mov     r8, rdi; lpSubKey
0x1800051e4  mov     rdx, r13; hKey
0x1800051e7  lea     rcx, [rsp+2300h+var_2290]; this
0x1800051ec  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800051f1  test    eax, eax
0x1800051f3  jz      loc_18000527A
0x1800051f9  mov     r9d, 20019h; unsigned int
0x1800051ff  mov     r8, rdi; lpSubKey
0x180005202  mov     rdx, r13; hKey
0x180005205  lea     rcx, [rsp+2300h+var_2290]; this
0x18000520a  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000520f  test    eax, eax
0x180005211  jz      short loc_18000527A
0x180005213  mov     [rbp+2200h+dwDisposition], r14d
0x180005217  mov     [rbp+2200h+var_2270], r14
0x18000521b  lea     rax, [rbp+2200h+dwDisposition]
0x18000521f  mov     [rsp+2300h+lpdwDisposition], rax; lpdwDisposition
0x180005224  lea     rax, [rbp+2200h+var_2270]
0x180005228  mov     [rsp+2300h+phkResult], rax; phkResult
0x18000522d  mov     [rsp+2300h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180005232  mov     [rsp+2300h+samDesired], 2001Fh; samDesired
0x18000523a  mov     [rsp+2300h+dwOptions], r14d; dwOptions
0x18000523f  xor     r9d, r9d; lpClass
0x180005242  xor     r8d, r8d; Reserved
0x180005245  mov     rdx, rdi; lpSubKey
0x180005248  mov     rcx, r13; hKey
0x18000524b  call    cs:__imp_RegCreateKeyExW
0x180005252  nop     dword ptr [rax+rax+00h]
0x180005257  mov     ecx, eax
0x180005259  test    eax, eax
0x18000525b  jnz     short loc_180005272
0x18000525d  lea     rcx, [rsp+2300h+var_2290]; this
0x180005262  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180005267  mov     ecx, eax
0x180005269  mov     rax, [rbp+2200h+var_2270]
0x18000526d  mov     [rsp+2300h+var_2290], rax
0x180005272  test    ecx, ecx
0x180005274  jnz     loc_180005405
0x18000527a  mov     rdx, rdi; unsigned __int16 *
0x18000527d  mov     rcx, rsi; this
0x180005280  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180005285  mov     ebx, eax
0x180005287  test    eax, eax
0x180005289  js      loc_1800054CD
0x18000528f  cmp     word ptr [rdi], 3Dh ; '='
0x180005293  jnz     short loc_1800052B2
0x180005295  mov     r9, rdi; unsigned __int16 *
0x180005298  xor     r8d, r8d; unsigned __int16 *
0x18000529b  lea     rdx, [rsp+2300h+var_2290]; struct CRegKey *
0x1800052a0  mov     rcx, rsi; this
0x1800052a3  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x1800052a8  mov     ebx, eax
0x1800052aa  test    eax, eax
0x1800052ac  js      loc_1800054CD
0x1800052b2  cmp     word ptr [rdi], 7Bh ; '{'
0x1800052b6  jnz     loc_180004F7B
0x1800052bc  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800052c0  inc     rax
0x1800052c3  cmp     [rdi+rax*2], r14w
0x1800052c8  jnz     short loc_1800052C0
0x1800052ca  cmp     rax, 1
0x1800052ce  jnz     loc_180004F7B
0x1800052d4  mov     [rsp+2300h+dwOptions], r14d; int
0x1800052d9  mov     r9d, r15d; int
0x1800052dc  mov     r8, [rsp+2300h+var_2290]; HKEY
0x1800052e1  mov     rdx, rdi; unsigned __int16 *
0x1800052e4  mov     rcx, rsi; this
0x1800052e7  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800052ec  mov     ebx, eax
0x1800052ee  test    eax, eax
0x1800052f0  js      loc_1800054CD
0x1800052f6  mov     rdx, rdi
0x1800052f9  mov     rcx, rsi
0x1800052fc  jmp     loc_180004F71
0x180005301  cmp     [rbp+2200h+arg_20], r14d
0x180005308  jnz     short loc_180005325
0x18000530a  mov     r9d, 20019h; unsigned int
0x180005310  mov     r8, rdi; lpSubKey
0x180005313  mov     rdx, r13; hKey
0x180005316  lea     rcx, [rsp+2300h+var_2290]; this
0x18000531b  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180005320  mov     r14d, eax
0x180005323  jmp     short loc_18000532B
0x180005325  mov     r14d, 2
0x18000532b  mov     r15d, 1
0x180005331  test    r14d, r14d
0x180005334  cmovz   r15d, [rbp+2200h+arg_20]
0x18000533c  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180005340  mov     r8, rdi; Source
0x180005343  mov     edx, 104h; SizeInWords
0x180005348  lea     rcx, [rbp+2200h+Destination]; Destination
0x18000534c  call    cs:__imp_wcsncpy_s
0x180005353  nop     dword ptr [rax+rax+00h]
0x180005358  mov     ecx, eax; int
0x18000535a  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000535f  mov     rdx, rdi; unsigned __int16 *
0x180005362  mov     rcx, rsi; this
0x180005365  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000536a  mov     ebx, eax
0x18000536c  test    eax, eax
0x18000536e  js      loc_1800054CD
0x180005374  mov     rdx, rdi; unsigned __int16 *
0x180005377  mov     rcx, rsi; this
0x18000537a  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18000537f  mov     ebx, eax
0x180005381  xor     ecx, ecx
0x180005383  test    eax, eax
0x180005385  js      loc_1800054CD
0x18000538b  cmp     word ptr [rdi], 7Bh ; '{'
0x18000538f  jnz     short loc_1800053E2
0x180005391  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005395  inc     rax
0x180005398  cmp     [rdi+rax*2], cx
0x18000539c  jnz     short loc_180005395
0x18000539e  cmp     rax, 1
0x1800053a2  jnz     short loc_1800053E2
0x1800053a4  mov     [rsp+2300h+dwOptions], r15d; int
0x1800053a9  xor     r9d, r9d; int
0x1800053ac  mov     r8, [rsp+2300h+var_2290]; HKEY
0x1800053b1  mov     rdx, rdi; unsigned __int16 *
0x1800053b4  mov     rcx, rsi; this
0x1800053b7  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800053bc  mov     ebx, eax
0x1800053be  test    eax, eax
0x1800053c0  jns     short loc_1800053CB
0x1800053c2  test    r15d, r15d
0x1800053c5  jz      loc_1800054CD
0x1800053cb  mov     rdx, rdi; unsigned __int16 *
  ... truncated ...
```
