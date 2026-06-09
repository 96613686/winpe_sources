# AssocMakeApplicationByKeyW

- ea: `0x18001fa90`
- end: `0x18001fd2e`
- name: `AssocMakeApplicationByKeyW`
- size: `670`
- prototype: `__int64 __fastcall(char, HKEY, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18001f9e0`

## callees

- `0x180008150`
- `0x1800085b0`
- `0x180012550`
- `0x18001f2a0`
- `0x18001f368`
- `0x18001f454`
- `0x18001f554`
- `0x18001f5d0`
- `0x18001fa90`
- `0x18002094c`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001fc8e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001fcbd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001fc8e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001fcbd`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18001fb9e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18001fb9e`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpW` at `0x18001fb8c`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpW` at `0x18001fb8c`

## pseudocode

```c
__int64 __fastcall AssocMakeApplicationByKeyW(char a1, HKEY a2, const unsigned __int16 *a3)
{
  int v3; // r13d
  unsigned int v6; // r14d
  HRESULT v8; // ebx
  const WCHAR *FileNameW; // rsi
  int IsMSIPerUserInstall; // r12d
  unsigned int v11; // r8d
  void *ppv; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  CLSID clsid; // [rsp+60h] [rbp-A0h] BYREF
  void *v15; // [rsp+70h] [rbp-90h] BYREF
  int v16; // [rsp+78h] [rbp-88h]
  int v17; // [rsp+7Ch] [rbp-84h]
  const WCHAR *v18; // [rsp+80h] [rbp-80h]
  int v19; // [rsp+88h] [rbp-78h]
  int v20; // [rsp+8Ch] [rbp-74h]
  DWORD pcchOut; // [rsp+90h] [rbp-70h] BYREF
  int v22[3]; // [rsp+94h] [rbp-6Ch] BYREF
  WCHAR psz1[264]; // [rsp+A0h] [rbp-60h] BYREF

  ppv = 0;
  v3 = a1 & 0x40;
  v6 = v3 != 0 ? 0x40 : 0;
  clsid = CLSID_QueryAssociations;
  AssocCreate(&clsid, &GUID_c46ca590_3c3f_11d2_bee6_0000f805ca57, &ppv);
  if ( !ppv )
    return 2147942414LL;
  v8 = -2147023741;
  if ( (*(int (__fastcall **)(void *, _QWORD, _QWORD, HKEY, _QWORD))(*(_QWORD *)ppv + 24LL))(ppv, 0, 0, a2, 0) >= 0 )
  {
    v22[0] = 260;
    if ( (*(int (__fastcall **)(void *, _QWORD, __int64, const unsigned __int16 *, WCHAR *, int *))(*(_QWORD *)ppv + 32LL))(
           ppv,
           v6,
           2,
           a3,
           psz1,
           v22) >= 0
      && StrCmpW(psz1, L"%1") )
    {
      FileNameW = PathFindFileNameW(psz1);
      IsMSIPerUserInstall = _IsMSIPerUserInstall((struct IQueryAssociations *)ppv, v6, a3);
      hKey = 0;
      pcchOut = 0;
      v8 = AssocQueryStringW(v6 | 2, ASSOCSTR_COMMAND, FileNameW, a3, 0, &pcchOut);
      if ( v8 < 0 && (int)_AssocCreateAppKey(FileNameW, IsMSIPerUserInstall, v11, &hKey) >= 0 )
      {
        v15 = ppv;
        v16 = v3 != 0 ? 0x40 : 0;
        v17 = 0;
        v18 = FileNameW;
        v19 = IsMSIPerUserInstall;
        v20 = 0;
        if ( a3 )
        {
          if ( (unsigned int)_AllowExeVerb(a3, (const struct QUERYEXECB *)&v15) )
          {
            *(_QWORD *)&clsid.Data1 = 0;
            if ( _AssocOpenRegKey(a2, L"shell", 0x20019u, (HKEY *)&clsid, 0) < 0 )
            {
              v8 = -2147418113;
            }
            else
            {
              v8 = _AssocCopyVerb(*(HKEY *)&clsid.Data1, hKey, a3);
              RegCloseKey(*(HKEY *)&clsid.Data1);
            }
          }
        }
        else
        {
          v8 = AssocCopyVerbs(a2, hKey, _AllowExeVerb, &v15);
        }
        RegCloseKey(hKey);
      }
      if ( v3 )
      {
        if ( v8 >= 0 )
          AssocQueryStringW(v6 | 2, ASSOCSTR_FRIENDLYAPPNAME, FileNameW, 0, 0, &pcchOut);
      }
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001fa90  mov     [rsp-8+arg_0], rbx
0x18001fa95  push    rbp
0x18001fa96  push    rsi
0x18001fa97  push    rdi
0x18001fa98  push    r12
0x18001fa9a  push    r13
0x18001fa9c  push    r14
0x18001fa9e  push    r15
0x18001faa0  lea     rbp, [rsp-1C0h]
0x18001faa8  sub     rsp, 2C0h
0x18001faaf  mov     rax, cs:__security_cookie
0x18001fab6  xor     rax, rsp
0x18001fab9  mov     [rbp+1F0h+var_40], rax
0x18001fac0  movups  xmm0, xmmword ptr cs:CLSID_QueryAssociations.Data1
0x18001fac7  mov     r13d, ecx
0x18001faca  mov     [rsp+2F0h+ppv], 0
0x18001fad3  and     r13d, 40h
0x18001fad7  lea     rcx, [rsp+2F0h+clsid]; clsid
0x18001fadc  mov     eax, r13d
0x18001fadf  mov     rdi, r8
0x18001fae2  neg     eax
0x18001fae4  lea     r8, [rsp+2F0h+ppv]; ppv
0x18001fae9  mov     r15, rdx
0x18001faec  lea     rdx, _GUID_c46ca590_3c3f_11d2_bee6_0000f805ca57; riid
0x18001faf3  sbb     r14d, r14d
0x18001faf6  and     r14d, 40h
0x18001fafa  movdqu  xmmword ptr [rsp+2F0h+clsid.Data1], xmm0
0x18001fb00  call    AssocCreate
0x18001fb05  mov     rcx, [rsp+2F0h+ppv]
0x18001fb0a  test    rcx, rcx
0x18001fb0d  jnz     short loc_18001FB19
0x18001fb0f  mov     eax, 8007000Eh
0x18001fb14  jmp     loc_18001FD04
0x18001fb19  mov     rax, [rcx]
0x18001fb1c  mov     r9, r15
0x18001fb1f  xor     r8d, r8d
0x18001fb22  mov     [rsp+2F0h+pszOut], 0
0x18001fb2b  xor     edx, edx
0x18001fb2d  mov     ebx, 80070483h
0x18001fb32  mov     rax, [rax+18h]
0x18001fb36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb3b  test    eax, eax
0x18001fb3d  js      loc_18001FD02
0x18001fb43  mov     rcx, [rsp+2F0h+ppv]
0x18001fb48  lea     rdx, [rbp+1F0h+var_25C]
0x18001fb4c  mov     [rsp+2F0h+pcchOut], rdx
0x18001fb51  mov     r9, rdi
0x18001fb54  lea     rdx, [rbp+1F0h+psz1]
0x18001fb58  mov     [rbp+1F0h+var_25C], 104h
0x18001fb5f  mov     [rsp+2F0h+pszOut], rdx
0x18001fb64  mov     r8d, 2
0x18001fb6a  mov     rax, [rcx]
0x18001fb6d  mov     edx, r14d
0x18001fb70  mov     rax, [rax+20h]
0x18001fb74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb79  test    eax, eax
0x18001fb7b  js      loc_18001FCF1
0x18001fb81  lea     rdx, a1_0; "%1"
0x18001fb88  lea     rcx, [rbp+1F0h+psz1]; psz1
0x18001fb8c  call    cs:__imp_StrCmpW
0x18001fb92  test    eax, eax
0x18001fb94  jz      loc_18001FCF1
0x18001fb9a  lea     rcx, [rbp+1F0h+psz1]; pszPath
0x18001fb9e  call    cs:__imp_PathFindFileNameW
0x18001fba4  mov     rcx, [rsp+2F0h+ppv]; struct IQueryAssociations *
0x18001fba9  mov     r8, rdi; unsigned __int16 *
0x18001fbac  mov     edx, r14d; unsigned int
0x18001fbaf  mov     rsi, rax
0x18001fbb2  call    ?_IsMSIPerUserInstall@@YAHPEAUIQueryAssociations@@KPEBG@Z; _IsMSIPerUserInstall(IQueryAssociations *,ulong,ushort const *)
0x18001fbb7  xor     edx, edx
0x18001fbb9  lea     rcx, [rbp+1F0h+var_260]
0x18001fbbd  mov     r12d, eax
0x18001fbc0  mov     [rsp+2F0h+pcchOut], rcx; pcchOut
0x18001fbc5  mov     eax, r14d
0x18001fbc8  mov     [rsp+2F0h+hKey], rdx
0x18001fbcd  or      eax, 2
0x18001fbd0  mov     [rbp+1F0h+var_260], edx
0x18001fbd3  mov     [rsp+2F0h+pszOut], rdx; pszOut
0x18001fbd8  mov     ecx, eax; flags
0x18001fbda  mov     r9, rdi; pszExtra
0x18001fbdd  mov     [rsp+2F0h+flags], eax
0x18001fbe1  mov     r8, rsi; pszAssoc
0x18001fbe4  mov     edx, 1; str
0x18001fbe9  call    AssocQueryStringW
0x18001fbee  mov     ebx, eax
0x18001fbf0  test    eax, eax
0x18001fbf2  jns     loc_18001FCC3
0x18001fbf8  lea     r9, [rsp+2F0h+hKey]; HKEY *
0x18001fbfd  mov     edx, r12d; int
0x18001fc00  mov     rcx, rsi; pszPath
0x18001fc03  call    ?_AssocCreateAppKey@@YAJPEBGHKPEAPEAUHKEY__@@@Z; _AssocCreateAppKey(ushort const *,int,ulong,HKEY__ * *)
0x18001fc08  test    eax, eax
0x18001fc0a  js      loc_18001FCC3
0x18001fc10  mov     rcx, [rsp+2F0h+ppv]
0x18001fc15  xor     eax, eax
0x18001fc17  mov     [rsp+2F0h+var_280], rcx
0x18001fc1c  mov     [rsp+2F0h+var_278], r14d
0x18001fc21  mov     [rsp+2F0h+var_274], eax
0x18001fc25  mov     [rbp+1F0h+var_270], rsi
0x18001fc29  mov     [rbp+1F0h+var_268], r12d
0x18001fc2d  mov     [rbp+1F0h+var_264], eax
0x18001fc30  test    rdi, rdi
0x18001fc33  jz      short loc_18001FC9D
0x18001fc35  lea     rdx, [rsp+2F0h+var_280]; struct QUERYEXECB *
0x18001fc3a  mov     rcx, rdi; unsigned __int16 *
0x18001fc3d  call    ?_AllowExeVerb@@YAHPEBGPEBUQUERYEXECB@@@Z; _AllowExeVerb(ushort const *,QUERYEXECB const *)
0x18001fc42  test    eax, eax
0x18001fc44  jz      short loc_18001FCB8
0x18001fc46  lea     r9, [rsp+2F0h+clsid]; HKEY *
0x18001fc4b  mov     qword ptr [rsp+2F0h+clsid.Data1], 0
0x18001fc54  mov     r8d, 20019h; unsigned int
0x18001fc5a  mov     dword ptr [rsp+2F0h+pszOut], 0; int
0x18001fc62  lea     rdx, aShell; "shell"
0x18001fc69  mov     rcx, r15; HKEY
0x18001fc6c  call    ?_AssocOpenRegKey@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@H@Z; _AssocOpenRegKey(HKEY__ *,ushort const *,ulong,HKEY__ * *,int)
0x18001fc71  test    eax, eax
0x18001fc73  js      short loc_18001FC96
0x18001fc75  mov     rdx, [rsp+2F0h+hKey]; hKey
0x18001fc7a  mov     r8, rdi; pszSrcSubKey
0x18001fc7d  mov     rcx, qword ptr [rsp+2F0h+clsid.Data1]; hkeySrc
0x18001fc82  call    ?_AssocCopyVerb@@YAJPEAUHKEY__@@0PEBG@Z; _AssocCopyVerb(HKEY__ *,HKEY__ *,ushort const *)
0x18001fc87  mov     rcx, qword ptr [rsp+2F0h+clsid.Data1]; hKey
0x18001fc8c  mov     ebx, eax
0x18001fc8e  call    cs:__imp_RegCloseKey
0x18001fc94  jmp     short loc_18001FCB8
0x18001fc96  mov     ebx, 8000FFFFh
0x18001fc9b  jmp     short loc_18001FCB8
0x18001fc9d  mov     rdx, [rsp+2F0h+hKey]
0x18001fca2  lea     r9, [rsp+2F0h+var_280]
0x18001fca7  lea     r8, ?_AllowExeVerb@@YAHPEBGPEBUQUERYEXECB@@@Z; _AllowExeVerb(ushort const *,QUERYEXECB const *)
0x18001fcae  mov     rcx, r15
0x18001fcb1  call    _AssocCopyVerbs
0x18001fcb6  mov     ebx, eax
0x18001fcb8  mov     rcx, [rsp+2F0h+hKey]; hKey
0x18001fcbd  call    cs:__imp_RegCloseKey
0x18001fcc3  test    r13d, r13d
0x18001fcc6  jz      short loc_18001FCF1
0x18001fcc8  test    ebx, ebx
0x18001fcca  js      short loc_18001FCF1
0x18001fccc  mov     ecx, [rsp+2F0h+flags]; flags
0x18001fcd0  lea     rax, [rbp+1F0h+var_260]
0x18001fcd4  xor     r9d, r9d; pszExtra
0x18001fcd7  mov     [rsp+2F0h+pcchOut], rax; pcchOut
0x18001fcdc  mov     r8, rsi; pszAssoc
0x18001fcdf  mov     [rsp+2F0h+pszOut], 0; pszOut
0x18001fce8  lea     edx, [r9+4]; str
0x18001fcec  call    AssocQueryStringW
0x18001fcf1  mov     rcx, [rsp+2F0h+ppv]
0x18001fcf6  mov     rax, [rcx]
0x18001fcf9  mov     rax, [rax+10h]
0x18001fcfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd02  mov     eax, ebx
0x18001fd04  mov     rcx, [rbp+1F0h+var_40]
0x18001fd0b  xor     rcx, rsp; StackCookie
0x18001fd0e  call    __security_check_cookie
0x18001fd13  mov     rbx, [rsp+2F0h+arg_0]
0x18001fd1b  add     rsp, 2C0h
0x18001fd22  pop     r15
0x18001fd24  pop     r14
0x18001fd26  pop     r13
0x18001fd28  pop     r12
0x18001fd2a  pop     rdi
0x18001fd2b  pop     rsi
0x18001fd2c  pop     rbp
0x18001fd2d  retn
```
