# IsCOMWizardComponent(_GUID const *,ushort *,_GUID const *)

- ea: `0x18000db74`
- end: `0x18000de87`
- name: `?IsCOMWizardComponent@@YAHPEBU_GUID@@PEAG0@Z`
- size: `787`
- prototype: `__int64 __fastcall(const struct _GUID *, unsigned __int16 *, const struct _GUID *)`
- caller_count: `5`
- callee_count: `12`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000db74`
- `0x180015df0`
- `0x18001c220`
- `0x18001d200`
- `0x18002841c`

## callees

- `0x180004370`
- `0x18000ae04`
- `0x18000ae90`
- `0x18000d8b8`
- `0x18000db74`
- `0x18000e0f0`
- `0x18000e1f4`
- `0x18000e444`
- `0x18000e8dc`
- `0x180032a02`
- `0x180032a30`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000dc1a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000dc1a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000dc36`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000dc36`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000dd31`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000dd31`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000ddb0`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000ddb0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ddfd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ddfd`
- `USERENV!ExpandEnvironmentStringsForUserW` at `0x18000dbc4`
- `USERENV!ExpandEnvironmentStringsForUserW` at `0x18000dbc4`

## string_xrefs

- `0x18000dc2c`: `DllGetClassObject`
- `0x18000ddd2`: `xwizards.dll`

## pseudocode

```c
__int64 __fastcall IsCOMWizardComponent(const struct _GUID *a1, unsigned __int16 *a2, const struct _GUID *a3)
{
  char v6; // al
  unsigned int v8; // ebx
  HMODULE Library; // rax
  int v10; // r8d
  HMODULE v11; // rsi
  FARPROC ProcAddress; // rax
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  PVOID *v15; // rcx
  char LastErrorHRESULT; // al
  unsigned __int16 *v17; // rsi
  PVOID v18; // rcx
  const char *v19; // rax
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v21; // [rsp+38h] [rbp-C8h] BYREF
  OLECHAR sz[40]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Dest[264]; // [rsp+90h] [rbp-70h] BYREF

  if ( !a2 )
  {
    memset_0(sz, 0, sizeof(sz));
    pv = 0;
    StringFromGUID2(a1, sz, 40);
    if ( (unsigned int)HrVerifyCOMRegistration(sz, (unsigned __int16 **const)&pv) )
    {
      v8 = 0;
    }
    else
    {
      v17 = (unsigned __int16 *)pv;
      if ( wcsistr((const unsigned __int16 *)pv, L"xwizards.dll") )
        v8 = 0;
      else
        v8 = IsCOMWizardComponent(a1, v17, a3);
      CoTaskMemFree(v17);
    }
    goto LABEL_35;
  }
  if ( ExpandEnvironmentStringsForUserW(0, a2, Dest, 0x105u) )
  {
    v8 = 0;
    Library = LoadLibraryExW(Dest, 0, 0);
    v11 = Library;
    if ( !Library )
    {
      v15 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v8;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
LABEL_36:
        if ( v15 != &WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)v15 + 28) & 0x10) != 0 )
          {
            v18 = v15[2];
            v19 = "is";
            if ( !v8 )
              v19 = "is NOT";
            WPP_SF_Ss((_DWORD)v18, (unsigned int)"is NOT", v10, (_DWORD)a2, (__int64)v19);
            v15 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 0x10) != 0 )
            WPP_SF_d(v15[2], 130, &WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids, v8);
        }
        return v8;
      }
      LastErrorHRESULT = GetLastErrorHRESULT();
      WPP_SF_SSD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        128,
        (unsigned int)&WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids,
        (_DWORD)a2,
        (__int64)Dest,
        LastErrorHRESULT);
LABEL_35:
      v15 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_36;
    }
    ProcAddress = GetProcAddress(Library, "DllGetClassObject");
    if ( ProcAddress )
    {
      v21 = 0;
      if ( ((int (__fastcall *)(const struct _GUID *, GUID *, __int64 *))ProcAddress)(a1, &IID_IClassFactory, &v21) >= 0 )
      {
        if ( a3 )
        {
          pv = 0;
          if ( (*(int (__fastcall **)(__int64, _QWORD, const struct _GUID *, LPVOID *))(*(_QWORD *)v21 + 24LL))(
                 v21,
                 0,
                 a3,
                 &pv) < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 125, &WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids, a2);
          }
          else
          {
            v8 = 1;
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
          }
        }
        else
        {
          v8 = 1;
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
        goto LABEL_25;
      }
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      {
LABEL_25:
        FreeLibrary(v11);
        goto LABEL_35;
      }
      v14 = 126;
    }
    else
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_25;
      v14 = 127;
    }
    WPP_SF_S(v13[2], v14, &WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids, a2);
    goto LABEL_25;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v6 = GetLastErrorHRESULT();
    WPP_SF_SD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      124,
      (unsigned int)&WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids,
      (_DWORD)a2,
      v6);
  }
  return 0;
}

```

## disassembly

```asm
0x18000db74  push    rbp
0x18000db76  push    rbx
0x18000db77  push    rsi
0x18000db78  push    rdi
0x18000db79  push    r13
0x18000db7b  push    r14
0x18000db7d  push    r15
0x18000db7f  lea     rbp, [rsp-1B0h]
0x18000db87  sub     rsp, 2B0h
0x18000db8e  mov     rax, cs:__security_cookie
0x18000db95  xor     rax, rsp
0x18000db98  mov     [rbp+1E0h+var_40], rax
0x18000db9f  lea     r13, WPP_GLOBAL_Control
0x18000dba6  mov     r14, r8
0x18000dba9  mov     rdi, rdx
0x18000dbac  mov     r15, rcx
0x18000dbaf  test    rdx, rdx
0x18000dbb2  jz      loc_18000DD89
0x18000dbb8  mov     r9d, 105h; dwSize
0x18000dbbe  lea     r8, [rbp+1E0h+Dest]; lpDest
0x18000dbc2  xor     ecx, ecx; hToken
0x18000dbc4  call    cs:__imp_ExpandEnvironmentStringsForUserW
0x18000dbca  test    eax, eax
0x18000dbcc  jnz     short loc_18000DC0F
0x18000dbce  mov     rax, cs:WPP_GLOBAL_Control
0x18000dbd5  cmp     rax, r13
0x18000dbd8  jz      short loc_18000DC08
0x18000dbda  test    byte ptr [rax+1Ch], 4
0x18000dbde  jz      short loc_18000DC08
0x18000dbe0  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x18000dbe5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dbec  lea     r8, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x18000dbf3  mov     edx, 7Ch ; '|'
0x18000dbf8  mov     dword ptr [rsp+2E0h+var_2C0], eax
0x18000dbfc  mov     r9, rdi
0x18000dbff  mov     rcx, [rcx+10h]
0x18000dc03  call    WPP_SF_SD
0x18000dc08  xor     eax, eax
0x18000dc0a  jmp     loc_18000DE66
0x18000dc0f  xor     r8d, r8d; dwFlags
0x18000dc12  lea     rcx, [rbp+1E0h+Dest]; lpLibFileName
0x18000dc16  xor     edx, edx; hFile
0x18000dc18  xor     ebx, ebx
0x18000dc1a  call    cs:__imp_LoadLibraryExW
0x18000dc20  mov     rsi, rax
0x18000dc23  test    rax, rax
0x18000dc26  jz      loc_18000DD3C
0x18000dc2c  lea     rdx, aDllgetclassobj_0; "DllGetClassObject"
0x18000dc33  mov     rcx, rax; hModule
0x18000dc36  call    cs:__imp_GetProcAddress
0x18000dc3c  test    rax, rax
0x18000dc3f  jz      loc_18000DD04
0x18000dc45  lea     r8, [rsp+2E0h+var_2A8]
0x18000dc4a  mov     [rsp+2E0h+var_2A8], rbx
0x18000dc4f  lea     rdx, IID_IClassFactory
0x18000dc56  mov     rcx, r15
0x18000dc59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc5e  test    eax, eax
0x18000dc60  js      loc_18000DCEB
0x18000dc66  test    r14, r14
0x18000dc69  jz      short loc_18000DCD3
0x18000dc6b  mov     rcx, [rsp+2E0h+var_2A8]
0x18000dc70  lea     r9, [rsp+2E0h+pv]
0x18000dc75  mov     [rsp+2E0h+pv], rbx
0x18000dc7a  mov     r8, r14
0x18000dc7d  xor     edx, edx
0x18000dc7f  mov     rax, [rcx]
0x18000dc82  mov     rax, [rax+18h]
0x18000dc86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc8b  test    eax, eax
0x18000dc8d  js      short loc_18000DCA7
0x18000dc8f  mov     rcx, [rsp+2E0h+pv]
0x18000dc94  mov     ebx, 1
0x18000dc99  mov     rax, [rcx]
0x18000dc9c  mov     rax, [rax+10h]
0x18000dca0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dca5  jmp     short loc_18000DCD8
0x18000dca7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dcae  cmp     rcx, r13
0x18000dcb1  jz      short loc_18000DCD8
0x18000dcb3  test    byte ptr [rcx+1Ch], 10h
0x18000dcb7  jz      short loc_18000DCD8
0x18000dcb9  mov     rcx, [rcx+10h]
0x18000dcbd  lea     r8, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x18000dcc4  mov     edx, 7Dh ; '}'
0x18000dcc9  mov     r9, rdi
0x18000dccc  call    WPP_SF_S
0x18000dcd1  jmp     short loc_18000DCD8
0x18000dcd3  mov     ebx, 1
0x18000dcd8  mov     rcx, [rsp+2E0h+var_2A8]
0x18000dcdd  mov     rax, [rcx]
0x18000dce0  mov     rax, [rax+10h]
0x18000dce4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dce9  jmp     short loc_18000DD2E
0x18000dceb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dcf2  cmp     rcx, r13
0x18000dcf5  jz      short loc_18000DD2E
0x18000dcf7  test    byte ptr [rcx+1Ch], 10h
0x18000dcfb  jz      short loc_18000DD2E
0x18000dcfd  mov     edx, 7Eh ; '~'
0x18000dd02  jmp     short loc_18000DD1B
0x18000dd04  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dd0b  cmp     rcx, r13
0x18000dd0e  jz      short loc_18000DD2E
0x18000dd10  test    byte ptr [rcx+1Ch], 10h
0x18000dd14  jz      short loc_18000DD2E
0x18000dd16  mov     edx, 7Fh
0x18000dd1b  mov     rcx, [rcx+10h]
0x18000dd1f  lea     r8, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x18000dd26  mov     r9, rdi
0x18000dd29  call    WPP_SF_S
0x18000dd2e  mov     rcx, rsi; hLibModule
0x18000dd31  call    cs:__imp_FreeLibrary
0x18000dd37  jmp     loc_18000DE03
0x18000dd3c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dd43  cmp     rcx, r13
0x18000dd46  jz      loc_18000DE64
0x18000dd4c  test    byte ptr [rcx+1Ch], 4
0x18000dd50  jz      loc_18000DE0A
0x18000dd56  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x18000dd5b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dd62  lea     r8, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x18000dd69  mov     [rsp+2E0h+var_2B8], eax
0x18000dd6d  mov     edx, 80h
0x18000dd72  lea     rax, [rbp+1E0h+Dest]
0x18000dd76  mov     r9, rdi
0x18000dd79  mov     [rsp+2E0h+var_2C0], rax
0x18000dd7e  mov     rcx, [rcx+10h]
0x18000dd82  call    WPP_SF_SSD
0x18000dd87  jmp     short loc_18000DE03
0x18000dd89  mov     r8d, 50h ; 'P'; Size
0x18000dd8f  lea     rcx, [rsp+2E0h+sz]; void *
0x18000dd94  call    memset_0
0x18000dd99  mov     r8d, 28h ; '('; cchMax
0x18000dd9f  mov     [rsp+2E0h+pv], 0
0x18000dda8  lea     rdx, [rsp+2E0h+sz]; lpsz
0x18000ddad  mov     rcx, r15; rguid
0x18000ddb0  call    cs:__imp_StringFromGUID2
0x18000ddb6  lea     rdx, [rsp+2E0h+pv]; unsigned __int16 **
0x18000ddbb  lea     rcx, [rsp+2E0h+sz]; unsigned __int16 *
0x18000ddc0  call    ?HrVerifyCOMRegistration@@YAJQEAGQEAPEAG@Z; HrVerifyCOMRegistration(ushort * const,ushort * * const)
0x18000ddc5  test    eax, eax
0x18000ddc7  jz      short loc_18000DDCD
0x18000ddc9  xor     ebx, ebx
0x18000ddcb  jmp     short loc_18000DE03
0x18000ddcd  mov     rsi, [rsp+2E0h+pv]
0x18000ddd2  lea     rdx, aXwizardsDll_0; "xwizards.dll"
0x18000ddd9  mov     rcx, rsi; unsigned __int16 *
0x18000dddc  call    ?wcsistr@@YAPEAGPEBG0@Z; wcsistr(ushort const *,ushort const *)
0x18000dde1  test    rax, rax
0x18000dde4  jz      short loc_18000DDEA
0x18000dde6  xor     ebx, ebx
0x18000dde8  jmp     short loc_18000DDFA
0x18000ddea  mov     r8, r14; struct _GUID *
0x18000dded  mov     rdx, rsi; unsigned __int16 *
0x18000ddf0  mov     rcx, r15; struct _GUID *
0x18000ddf3  call    ?IsCOMWizardComponent@@YAHPEBU_GUID@@PEAG0@Z; IsCOMWizardComponent(_GUID const *,ushort *,_GUID const *)
0x18000ddf8  mov     ebx, eax
0x18000ddfa  mov     rcx, rsi; pv
0x18000ddfd  call    cs:__imp_CoTaskMemFree
0x18000de03  mov     rcx, cs:WPP_GLOBAL_Control
0x18000de0a  cmp     rcx, r13
0x18000de0d  jz      short loc_18000DE64
0x18000de0f  test    byte ptr [rcx+1Ch], 10h
0x18000de13  jz      short loc_18000DE41
0x18000de15  mov     rcx, [rcx+10h]
0x18000de19  lea     rdx, aIsNot; "is NOT"
0x18000de20  test    ebx, ebx
0x18000de22  lea     rax, aIs; "is"
0x18000de29  mov     r9, rdi
0x18000de2c  cmovz   rax, rdx
0x18000de30  mov     [rsp+2E0h+var_2C0], rax
0x18000de35  call    WPP_SF_Ss
0x18000de3a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000de41  cmp     rcx, r13
0x18000de44  jz      short loc_18000DE64
0x18000de46  test    byte ptr [rcx+1Ch], 10h
0x18000de4a  jz      short loc_18000DE64
0x18000de4c  mov     rcx, [rcx+10h]
0x18000de50  lea     r8, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x18000de57  mov     edx, 82h
0x18000de5c  mov     r9d, ebx
0x18000de5f  call    WPP_SF_d
0x18000de64  mov     eax, ebx
0x18000de66  mov     rcx, [rbp+1E0h+var_40]
0x18000de6d  xor     rcx, rsp; StackCookie
0x18000de70  call    __security_check_cookie
0x18000de75  add     rsp, 2B0h
0x18000de7c  pop     r15
0x18000de7e  pop     r14
0x18000de80  pop     r13
0x18000de82  pop     rdi
0x18000de83  pop     rsi
0x18000de84  pop     rbx
0x18000de85  pop     rbp
0x18000de86  retn
```
