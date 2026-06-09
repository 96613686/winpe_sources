# HrRegisterOrUnregisterWithCOM(ushort * const,int)

- ea: `0x18000f010`
- end: `0x18000f230`
- name: `?HrRegisterOrUnregisterWithCOM@@YAJQEAGH@Z`
- size: `544`
- prototype: `__int64 __fastcall(LPCWSTR lpSrc, int)`
- caller_count: `4`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007b28`
- `0x18000c5c8`
- `0x18000ca6c`
- `0x18000daac`

## callees

- `0x180003b90`
- `0x180007820`
- `0x18000abbc`
- `0x18000f010`
- `0x180012800`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f0cd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f11c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f131`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f0cd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f11c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f131`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000f0a6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000f0a6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000f199`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000f199`
- `USERENV!ExpandEnvironmentStringsForUserW` at `0x18000f049`
- `USERENV!ExpandEnvironmentStringsForUserW` at `0x18000f049`

## string_xrefs

- `0x18000f0b8`: `DllRegisterServer`
- `0x18000f0c6`: `DllUnregisterServer`
- `0x18000f110`: `DllCanUnloadNow`
- `0x18000f127`: `DllGetClassObject`

## pseudocode

```c
__int64 __fastcall HrRegisterOrUnregisterWithCOM(LPCWSTR lpSrc, int a2)
{
  int v3; // esi
  unsigned int LastErrorHRESULT; // eax
  unsigned int v5; // edi
  HMODULE Library; // rax
  HMODULE v7; // rsi
  const CHAR *v8; // rdx
  __int64 (*ProcAddress)(void); // rax
  unsigned int v10; // eax
  _QWORD *v11; // rcx
  int v12; // edx
  unsigned int v13; // eax
  PVOID *v14; // rcx
  WCHAR Dest[264]; // [rsp+30h] [rbp-228h] BYREF

  v3 = (int)lpSrc;
  if ( !ExpandEnvironmentStringsForUserW(0, lpSrc, Dest, 0x105u) )
  {
    LastErrorHRESULT = GetLastErrorHRESULT();
    v5 = LastErrorHRESULT;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        62,
        (unsigned int)&WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids,
        v3,
        LastErrorHRESULT);
    return v5;
  }
  Library = LoadLibraryExW(Dest, 0, 0);
  v7 = Library;
  if ( Library )
  {
    v8 = "DllRegisterServer";
    if ( !a2 )
      v8 = "DllUnregisterServer";
    ProcAddress = GetProcAddress(Library, v8);
    if ( ProcAddress )
    {
      v10 = ProcAddress();
      v5 = v10;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          63,
          (unsigned int)&WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids,
          (unsigned int)Dest,
          v10);
      goto LABEL_21;
    }
    v5 = GetLastErrorHRESULT();
    if ( GetProcAddress(v7, "DllCanUnloadNow") && GetProcAddress(v7, "DllGetClassObject") )
    {
      v5 = 1;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_21;
      v12 = 64;
    }
    else
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_21;
      v12 = 65;
    }
    WPP_SF_SD(v11[2], v12, (unsigned int)&WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids, (unsigned int)Dest, v5);
LABEL_21:
    FreeLibrary(v7);
    goto LABEL_25;
  }
  v13 = GetLastErrorHRESULT();
  v5 = v13;
  v14 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v5;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    goto LABEL_26;
  WPP_SF_SD(
    *((_QWORD *)WPP_GLOBAL_Control + 2),
    66,
    (unsigned int)&WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids,
    (unsigned int)Dest,
    v13);
LABEL_25:
  v14 = (PVOID *)WPP_GLOBAL_Control;
LABEL_26:
  if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 0x10) != 0 )
    WPP_SF_D(v14[2], 67, &WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x18000f010  mov     [rsp+arg_8], rbx
0x18000f015  mov     [rsp+arg_10], rsi
0x18000f01a  push    rdi
0x18000f01b  sub     rsp, 250h
0x18000f022  mov     rax, cs:__security_cookie
0x18000f029  xor     rax, rsp
0x18000f02c  mov     [rsp+258h+var_18], rax
0x18000f034  mov     ebx, edx
0x18000f036  lea     r8, [rsp+258h+Dest]; lpDest
0x18000f03b  mov     rdx, rcx; lpSrc
0x18000f03e  mov     rsi, rcx
0x18000f041  xor     ecx, ecx; hToken
0x18000f043  mov     r9d, 105h; dwSize
0x18000f049  call    cs:__imp_ExpandEnvironmentStringsForUserW
0x18000f04f  test    eax, eax
0x18000f051  jnz     short loc_18000F09C
0x18000f053  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x18000f058  mov     edi, eax
0x18000f05a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f061  lea     rbx, WPP_GLOBAL_Control
0x18000f068  cmp     rcx, rbx
0x18000f06b  jz      loc_18000F209
0x18000f071  test    byte ptr [rcx+1Ch], 4
0x18000f075  jz      loc_18000F209
0x18000f07b  mov     rcx, [rcx+10h]
0x18000f07f  lea     r8, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x18000f086  mov     edx, 3Eh ; '>'
0x18000f08b  mov     [rsp+258h+var_238], eax
0x18000f08f  mov     r9, rsi
0x18000f092  call    WPP_SF_SD
0x18000f097  jmp     loc_18000F209
0x18000f09c  xor     r8d, r8d; dwFlags
0x18000f09f  lea     rcx, [rsp+258h+Dest]; lpLibFileName
0x18000f0a4  xor     edx, edx; hFile
0x18000f0a6  call    cs:__imp_LoadLibraryExW
0x18000f0ac  mov     rsi, rax
0x18000f0af  test    rax, rax
0x18000f0b2  jz      loc_18000F1A1
0x18000f0b8  lea     rdx, aDllregisterser; "DllRegisterServer"
0x18000f0bf  mov     rcx, rax; hModule
0x18000f0c2  test    ebx, ebx
0x18000f0c4  jnz     short loc_18000F0CD
0x18000f0c6  lea     rdx, aDllunregisters; "DllUnregisterServer"
0x18000f0cd  call    cs:__imp_GetProcAddress
0x18000f0d3  test    rax, rax
0x18000f0d6  jz      short loc_18000F10B
0x18000f0d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0dd  mov     edi, eax
0x18000f0df  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f0e6  lea     rbx, WPP_GLOBAL_Control
0x18000f0ed  cmp     rcx, rbx
0x18000f0f0  jz      loc_18000F196
0x18000f0f6  test    byte ptr [rcx+1Ch], 10h
0x18000f0fa  jz      loc_18000F196
0x18000f100  mov     edx, 3Fh ; '?'
0x18000f105  mov     [rsp+258h+var_238], eax
0x18000f109  jmp     short loc_18000F181
0x18000f10b  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x18000f110  lea     rdx, aDllcanunloadno_0; "DllCanUnloadNow"
0x18000f117  mov     rcx, rsi; hModule
0x18000f11a  mov     edi, eax
0x18000f11c  call    cs:__imp_GetProcAddress
0x18000f122  test    rax, rax
0x18000f125  jz      short loc_18000F15F
0x18000f127  lea     rdx, aDllgetclassobj_0; "DllGetClassObject"
0x18000f12e  mov     rcx, rsi; hModule
0x18000f131  call    cs:__imp_GetProcAddress
0x18000f137  test    rax, rax
0x18000f13a  jz      short loc_18000F15F
0x18000f13c  mov     edi, 1
0x18000f141  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f148  lea     rbx, WPP_GLOBAL_Control
0x18000f14f  cmp     rcx, rbx
0x18000f152  jz      short loc_18000F196
0x18000f154  test    byte ptr [rcx+1Ch], 10h
0x18000f158  jz      short loc_18000F196
0x18000f15a  lea     edx, [rdi+3Fh]
0x18000f15d  jmp     short loc_18000F17D
0x18000f15f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f166  lea     rbx, WPP_GLOBAL_Control
0x18000f16d  cmp     rcx, rbx
0x18000f170  jz      short loc_18000F196
0x18000f172  test    byte ptr [rcx+1Ch], 4
0x18000f176  jz      short loc_18000F196
0x18000f178  mov     edx, 41h ; 'A'
0x18000f17d  mov     [rsp+258h+var_238], edi
0x18000f181  mov     rcx, [rcx+10h]
0x18000f185  lea     r9, [rsp+258h+Dest]
0x18000f18a  lea     r8, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x18000f191  call    WPP_SF_SD
0x18000f196  mov     rcx, rsi; hLibModule
0x18000f199  call    cs:__imp_FreeLibrary
0x18000f19f  jmp     short loc_18000F1DF
0x18000f1a1  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x18000f1a6  mov     edi, eax
0x18000f1a8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f1af  lea     rbx, WPP_GLOBAL_Control
0x18000f1b6  cmp     rcx, rbx
0x18000f1b9  jz      short loc_18000F209
0x18000f1bb  test    byte ptr [rcx+1Ch], 4
0x18000f1bf  jz      short loc_18000F1E6
0x18000f1c1  mov     rcx, [rcx+10h]
0x18000f1c5  lea     r9, [rsp+258h+Dest]
0x18000f1ca  mov     edx, 42h ; 'B'
0x18000f1cf  mov     [rsp+258h+var_238], eax
0x18000f1d3  lea     r8, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x18000f1da  call    WPP_SF_SD
0x18000f1df  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f1e6  cmp     rcx, rbx
0x18000f1e9  jz      short loc_18000F209
0x18000f1eb  test    byte ptr [rcx+1Ch], 10h
0x18000f1ef  jz      short loc_18000F209
0x18000f1f1  mov     rcx, [rcx+10h]
0x18000f1f5  lea     r8, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x18000f1fc  mov     edx, 43h ; 'C'
0x18000f201  mov     r9d, edi
0x18000f204  call    WPP_SF_D
0x18000f209  mov     eax, edi
0x18000f20b  mov     rcx, [rsp+258h+var_18]
0x18000f213  xor     rcx, rsp; StackCookie
0x18000f216  call    __security_check_cookie
0x18000f21b  lea     r11, [rsp+258h+var_8]
0x18000f223  mov     rbx, [r11+18h]
0x18000f227  mov     rsi, [r11+20h]
0x18000f22b  mov     rsp, r11
0x18000f22e  pop     rdi
0x18000f22f  retn
```
