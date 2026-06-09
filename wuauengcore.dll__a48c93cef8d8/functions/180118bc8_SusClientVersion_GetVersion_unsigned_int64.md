# SusClientVersion::GetVersion(unsigned __int64 *)

- ea: `0x180118bc8`
- end: `0x180118f23`
- name: `?GetVersion@SusClientVersion@@SAJPEA_K@Z`
- size: `859`
- prototype: `__int64 __fastcall(unsigned __int64 *)`
- caller_count: `7`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001c5a0`
- `0x18006ee20`
- `0x1800c2704`
- `0x18013cba0`
- `0x180166170`
- `0x1801a9b4c`
- `0x1801e7248`

## callees

- `0x18000def4`
- `0x18003baf4`
- `0x180113ae8`
- `0x1801176a4`
- `0x180118398`
- `0x180118bc8`
- `0x18012b618`
- `0x180238960`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180118c87`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180118cb4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180118ce5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180118d26`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180118d5a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180118d87`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180118c87`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180118cb4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180118ce5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180118d26`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180118d5a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180118d87`

## string_xrefs

- `0x180118c48`: `wuapicore.dll`
- `0x180118cf8`: `wuapicore.dll`
- `0x180118ead`: `wuapicore.dll`
- `0x180118c5a`: `wuauengcore.dll`
- `0x180118d34`: `wuauengcore.dll`
- `0x180118c07`: `C:\__w\1\s\src\Client\lib\util\MachineConfigInfo.cpp`
- `0x180118e12`: `C:\__w\1\s\src\Client\lib\util\MachineConfigInfo.cpp`
- `0x180118ed8`: `C:\__w\1\s\src\Client\lib\util\MachineConfigInfo.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SusClientVersion::GetVersion(unsigned __int64 *a1)
{
  int FileVersion; // ebx
  int v2; // edi
  unsigned __int64 v3; // rax
  unsigned int v4; // r12d
  const WCHAR **v5; // rsi
  const WCHAR *v6; // r8
  int v7; // eax
  int v8; // eax
  int v9; // eax
  int v10; // eax
  const WCHAR *v11; // r8
  int v12; // eax
  const WCHAR *v13; // r8
  wchar_t *v14; // r14
  int v15; // eax
  unsigned __int64 v16; // rax
  int lpString2; // [rsp+20h] [rbp-60h]
  int lpString2a; // [rsp+20h] [rbp-60h]
  unsigned __int64 v21; // [rsp+68h] [rbp-18h] BYREF
  void *lpMem; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  if ( !a1 )
  {
    FileVersion = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x20,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\MachineConfigInfo.cpp",
      (const char *)0x80004003LL,
      lpString2);
    return (unsigned int)FileVersion;
  }
  v21 = 0;
  v2 = 0;
  lpMem = 0;
  v3 = SusClientVersion::m_CachedVersion;
  *a1 = SusClientVersion::m_CachedVersion;
  if ( v3 )
  {
LABEL_39:
    FileVersion = 0;
    goto LABEL_40;
  }
  v4 = 0;
  v5 = (const WCHAR **)off_1802943C0;
  do
  {
    v6 = *v5;
    if ( *v5 == L"wuapicore.dll" )
      goto LABEL_14;
    if ( v6 )
    {
      v7 = CompareStringW(0x7Fu, 1u, v6, -1, L"wuapicore.dll", -1);
      v6 = *v5;
      if ( v7 == 2 )
        goto LABEL_14;
    }
    if ( v6 == L"wuauengcore.dll" )
      goto LABEL_14;
    if ( v6 )
    {
      v8 = CompareStringW(0x7Fu, 1u, v6, -1, L"wuauengcore.dll", -1);
      v6 = *v5;
      if ( v8 == 2 )
        goto LABEL_14;
    }
    if ( v6 == L"wuaucltcore.exe" )
      goto LABEL_14;
    if ( !v6 )
      goto LABEL_26;
    v9 = CompareStringW(0x7Fu, 1u, v6, -1, L"wuaucltcore.exe", -1);
    v6 = *v5;
    if ( v9 == 2 )
LABEL_14:
      v2 |= 9u;
    if ( v6 != L"wuapicore.dll" )
    {
      if ( !v6 )
        goto LABEL_26;
      v10 = CompareStringW(0x7Fu, 1u, v6, -1, L"wuapicore.dll", -1);
      v11 = *v5;
      if ( v10 != 2 )
      {
        if ( v11 == L"wuauengcore.dll" )
          goto LABEL_25;
        if ( v11 )
        {
          v12 = CompareStringW(0x7Fu, 1u, v11, -1, L"wuauengcore.dll", -1);
          v13 = *v5;
          if ( v12 == 2 )
          {
LABEL_25:
            v14 = L"wu.core.wuaueng";
            goto LABEL_28;
          }
          if ( v13 == L"wuaucltcore.exe" || v13 && CompareStringW(0x7Fu, 1u, v13, -1, L"wuaucltcore.exe", -1) == 2 )
          {
            v14 = (wchar_t *)L"wu.wuaucltcore";
            goto LABEL_28;
          }
        }
LABEL_26:
        v14 = L"wu";
        goto LABEL_28;
      }
    }
    v14 = L"wu.core.wuapi";
LABEL_28:
    if ( lpMem )
    {
      SusFree(lpMem);
      lpMem = 0;
    }
    v15 = UndockedModuleLoader::Load_0(v14, 0, 0, (__int64)&lpMem);
    FileVersion = v15;
    if ( v15 >= 0 )
    {
      FileVersion = GetFileVersion(lpMem, &v21);
      if ( FileVersion >= 0 )
      {
        WUTrace(0, 0, 32, 5, 0, L"   ClientVersion: %ws = %hu.%hu.%hu.%hu");
        if ( SusClientVersion::m_CachedVersion < v21 )
          SusClientVersion::m_CachedVersion = v21;
      }
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x58,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\MachineConfigInfo.cpp",
        (const char *)(unsigned int)v15,
        lpString2a);
    }
    ++v4;
    ++v5;
  }
  while ( v4 < 3 );
  v16 = SusClientVersion::m_CachedVersion;
  *a1 = SusClientVersion::m_CachedVersion;
  if ( v16 )
    goto LABEL_39;
  if ( FileVersion < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x79,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\MachineConfigInfo.cpp",
      (const char *)(unsigned int)FileVersion,
      lpString2a);
LABEL_40:
  if ( lpMem )
    SusFree(lpMem);
  return (unsigned int)FileVersion;
}

```

## disassembly

```asm
0x180118bc8  mov     [rsp-28h+arg_8], rbx
0x180118bcd  mov     [rsp-28h+arg_10], rsi
0x180118bd2  push    rbp
0x180118bd3  push    rdi
0x180118bd4  push    r12
0x180118bd6  push    r14
0x180118bd8  push    r15
0x180118bda  mov     rbp, rsp
0x180118bdd  sub     rsp, 80h
0x180118be4  mov     rax, cs:__security_cookie
0x180118beb  xor     rax, rsp
0x180118bee  mov     [rbp+var_8], rax
0x180118bf2  mov     [rbp+var_20], rcx
0x180118bf6  test    rcx, rcx
0x180118bf9  jnz     short loc_180118C1D
0x180118bfb  mov     rcx, [rbp+28h]; this
0x180118bff  mov     ebx, 80004003h
0x180118c04  mov     r9d, ebx; char *
0x180118c07  lea     r8, aCW1SSrcClientL_37; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180118c0e  mov     edx, 20h ; ' '; void *
0x180118c13  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180118c18  jmp     loc_180118EF9
0x180118c1d  mov     [rbp+var_18], 0
0x180118c25  xor     edi, edi
0x180118c27  mov     [rbp+lpMem], rdi
0x180118c2b  mov     rax, cs:?m_CachedVersion@SusClientVersion@@2_KA; unsigned __int64 SusClientVersion::m_CachedVersion
0x180118c32  mov     [rcx], rax
0x180118c35  test    rax, rax
0x180118c38  jnz     loc_180118EE9
0x180118c3e  xor     r12d, r12d
0x180118c41  lea     rsi, off_1802943C0; "wuapicore.dll"
0x180118c48  lea     rax, ?c_szWuapiCoreDll@@3QB_WB; "wuapicore.dll"
0x180118c4f  or      r14d, 0FFFFFFFFh
0x180118c53  lea     r15, ?c_szWuaucltCoreExe@@3QB_WB; "wuaucltcore.exe"
0x180118c5a  lea     rbx, ?c_szWuauengCoreDll@@3QB_WB; "wuauengcore.dll"
0x180118c61  mov     r8, [rsi]; lpString1
0x180118c64  cmp     r8, rax
0x180118c67  jz      loc_180118CF3
0x180118c6d  test    r8, r8
0x180118c70  jz      short loc_180118C95
0x180118c72  mov     [rsp+80h+cchCount2], r14d; cchCount2
0x180118c77  mov     [rsp+80h+lpString2], rax; lpString2
0x180118c7c  mov     r9d, r14d; cchCount1
0x180118c7f  mov     edx, 1; dwCmpFlags
0x180118c84  lea     ecx, [rdx+7Eh]; Locale
0x180118c87  call    cs:__imp_CompareStringW
0x180118c8d  mov     r8, [rsi]; lpString1
0x180118c90  cmp     eax, 2
0x180118c93  jz      short loc_180118CF3
0x180118c95  cmp     r8, rbx
0x180118c98  jz      short loc_180118CF3
0x180118c9a  test    r8, r8
0x180118c9d  jz      short loc_180118CC2
0x180118c9f  mov     [rsp+80h+cchCount2], r14d; cchCount2
0x180118ca4  mov     [rsp+80h+lpString2], rbx; lpString2
0x180118ca9  mov     r9d, r14d; cchCount1
0x180118cac  mov     edx, 1; dwCmpFlags
0x180118cb1  lea     ecx, [rdx+7Eh]; Locale
0x180118cb4  call    cs:__imp_CompareStringW
0x180118cba  mov     r8, [rsi]; lpString1
0x180118cbd  cmp     eax, 2
0x180118cc0  jz      short loc_180118CF3
0x180118cc2  cmp     r8, r15
0x180118cc5  jz      short loc_180118CF3
0x180118cc7  test    r8, r8
0x180118cca  jz      loc_180118DA6
0x180118cd0  mov     [rsp+80h+cchCount2], r14d; cchCount2
0x180118cd5  mov     [rsp+80h+lpString2], r15; lpString2
0x180118cda  mov     r9d, r14d; cchCount1
0x180118cdd  mov     edx, 1; dwCmpFlags
0x180118ce2  lea     ecx, [rdx+7Eh]; Locale
0x180118ce5  call    cs:__imp_CompareStringW
0x180118ceb  mov     r8, [rsi]; lpString1
0x180118cee  cmp     eax, 2
0x180118cf1  jnz     short loc_180118CF6
0x180118cf3  or      edi, 9
0x180118cf6  mov     ebx, edi
0x180118cf8  lea     rax, ?c_szWuapiCoreDll@@3QB_WB; "wuapicore.dll"
0x180118cff  cmp     r8, rax
0x180118d02  jz      loc_180118DAF
0x180118d08  test    r8, r8
0x180118d0b  jz      loc_180118DA6
0x180118d11  mov     [rsp+80h+cchCount2], r14d; cchCount2
0x180118d16  mov     [rsp+80h+lpString2], rax; lpString2
0x180118d1b  mov     r9d, r14d; cchCount1
0x180118d1e  mov     edx, 1; dwCmpFlags
0x180118d23  lea     ecx, [rdx+7Eh]; Locale
0x180118d26  call    cs:__imp_CompareStringW
0x180118d2c  mov     r8, [rsi]; lpString1
0x180118d2f  cmp     eax, 2
0x180118d32  jz      short loc_180118DAF
0x180118d34  lea     rax, ?c_szWuauengCoreDll@@3QB_WB; "wuauengcore.dll"
0x180118d3b  cmp     r8, rax
0x180118d3e  jz      short loc_180118D9D
0x180118d40  test    r8, r8
0x180118d43  jz      short loc_180118DA6
0x180118d45  mov     [rsp+80h+cchCount2], r14d; cchCount2
0x180118d4a  mov     [rsp+80h+lpString2], rax; lpString2
0x180118d4f  mov     r9d, r14d; cchCount1
0x180118d52  mov     edx, 1; dwCmpFlags
0x180118d57  lea     ecx, [rdx+7Eh]; Locale
0x180118d5a  call    cs:__imp_CompareStringW
0x180118d60  mov     r8, [rsi]; lpString1
0x180118d63  cmp     eax, 2
0x180118d66  jz      short loc_180118D9D
0x180118d68  cmp     r8, r15
0x180118d6b  jz      short loc_180118D92
0x180118d6d  test    r8, r8
0x180118d70  jz      short loc_180118DA6
0x180118d72  mov     [rsp+80h+cchCount2], r14d; cchCount2
0x180118d77  mov     [rsp+80h+lpString2], r15; lpString2
0x180118d7c  mov     r9d, r14d; cchCount1
0x180118d7f  mov     edx, 1; dwCmpFlags
0x180118d84  lea     ecx, [rdx+7Eh]; Locale
0x180118d87  call    cs:__imp_CompareStringW
0x180118d8d  cmp     eax, 2
0x180118d90  jnz     short loc_180118DA6
0x180118d92  lea     r14, aWuWuaucltcore; "wu.wuaucltcore"
0x180118d99  mov     edi, ebx
0x180118d9b  jmp     short loc_180118DB6
0x180118d9d  lea     r14, aWuCoreWuaueng; "wu.core.wuaueng"
0x180118da4  jmp     short loc_180118DB6
0x180118da6  lea     r14, aWu; "wu"
0x180118dad  jmp     short loc_180118DB6
0x180118daf  lea     r14, aWuCoreWuapi; "wu.core.wuapi"
0x180118db6  mov     rcx, [rbp+lpMem]; lpMem
0x180118dba  test    rcx, rcx
0x180118dbd  jz      short loc_180118DCC
0x180118dbf  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180118dc4  mov     [rbp+lpMem], 0
0x180118dcc  mov     [rsp+80h+var_48], 0
0x180118dd5  lea     rax, [rbp+lpMem]
0x180118dd9  mov     [rsp+80h+var_50], rax; __int64
0x180118dde  mov     qword ptr [rsp+80h+cchCount2], 0; int
0x180118de7  mov     [rsp+80h+lpString2], 0; int
0x180118df0  lea     r9, ?m_spUusSession@SusClientVersion@@0V?$unique_ptr@USession@uus@@U?$default_delete@USession@uus@@@wistd@@@wistd@@A; wistd::unique_ptr<uus::Session,wistd::default_delete<uus::Session>> SusClientVersion::m_spUusSession
0x180118df7  mov     r8d, edi
0x180118dfa  mov     rdx, [rsi]
0x180118dfd  mov     rcx, r14; wchar_t *
0x180118e00  call    UndockedModuleLoader__Load_0
0x180118e05  mov     ebx, eax
0x180118e07  mov     rcx, [rbp+28h]; this
0x180118e0b  test    eax, eax
0x180118e0d  jns     short loc_180118E25
0x180118e0f  mov     r9d, eax; char *
0x180118e12  lea     r8, aCW1SSrcClientL_37; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180118e19  mov     edx, 58h ; 'X'; void *
0x180118e1e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180118e23  jmp     short loc_180118E9C
0x180118e25  lea     rdx, [rbp+var_18]
0x180118e29  mov     rcx, [rbp+lpMem]
0x180118e2d  call    ?GetFileVersion@@YAJPEB_WPEA_KW4GetFileVersionFlag@@@Z; GetFileVersion(wchar_t const *,unsigned __int64 *,GetFileVersionFlag)
0x180118e32  mov     ebx, eax
0x180118e34  test    eax, eax
0x180118e36  js      short loc_180118E9C
0x180118e38  movzx   eax, word ptr [rbp+var_18]
0x180118e3c  movzx   ecx, word ptr [rbp+var_18+2]
0x180118e40  movzx   edx, word ptr [rbp+var_18+4]
0x180118e44  movzx   r8d, word ptr [rbp+var_18+6]
0x180118e49  mov     [rsp+80h+var_30], eax
0x180118e4d  mov     [rsp+80h+var_38], ecx
0x180118e51  mov     [rsp+80h+var_40], edx
0x180118e55  mov     dword ptr [rsp+80h+var_48], r8d
0x180118e5a  mov     rax, [rsi]
0x180118e5d  mov     [rsp+80h+var_50], rax
0x180118e62  lea     rax, aClientversionW; "   ClientVersion: %ws = %hu.%hu.%hu.%hu"
0x180118e69  mov     qword ptr [rsp+80h+cchCount2], rax
0x180118e6e  mov     [rsp+80h+lpString2], 0; int
0x180118e77  xor     edx, edx
0x180118e79  xor     ecx, ecx
0x180118e7b  lea     r9d, [rdx+5]
0x180118e7f  lea     r8d, [rdx+20h]
0x180118e83  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180118e88  mov     rax, [rbp+var_18]
0x180118e8c  cmp     cs:?m_CachedVersion@SusClientVersion@@2_KA, rax; unsigned __int64 SusClientVersion::m_CachedVersion
0x180118e93  jnb     short loc_180118E9C
0x180118e95  mov     cs:?m_CachedVersion@SusClientVersion@@2_KA, rax; unsigned __int64 SusClientVersion::m_CachedVersion
0x180118e9c  inc     r12d
0x180118e9f  add     rsi, 8
0x180118ea3  cmp     r12d, 3
0x180118ea7  mov     r14d, 0FFFFFFFFh
0x180118ead  lea     rax, ?c_szWuapiCoreDll@@3QB_WB; "wuapicore.dll"
0x180118eb4  jb      loc_180118C5A
0x180118eba  mov     rax, cs:?m_CachedVersion@SusClientVersion@@2_KA; unsigned __int64 SusClientVersion::m_CachedVersion
0x180118ec1  mov     r15, [rbp+var_20]
0x180118ec5  mov     [r15], rax
0x180118ec8  test    rax, rax
0x180118ecb  jnz     short loc_180118EE9
0x180118ecd  test    ebx, ebx
0x180118ecf  jns     short loc_180118EEB
0x180118ed1  mov     rcx, [rbp+28h]; this
0x180118ed5  mov     r9d, ebx; char *
0x180118ed8  lea     r8, aCW1SSrcClientL_37; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180118edf  lea     edx, [rax+79h]; void *
0x180118ee2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180118ee7  jmp     short loc_180118EEB
0x180118ee9  xor     ebx, ebx
0x180118eeb  mov     rcx, [rbp+lpMem]; lpMem
0x180118eef  test    rcx, rcx
0x180118ef2  jz      short loc_180118EF9
0x180118ef4  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180118ef9  mov     eax, ebx
0x180118efb  mov     rcx, [rbp+var_8]
0x180118eff  xor     rcx, rsp; StackCookie
0x180118f02  call    __security_check_cookie
0x180118f07  lea     r11, [rsp+80h+var_s0]
0x180118f0f  mov     rbx, [r11+38h]
0x180118f13  mov     rsi, [r11+40h]
0x180118f17  mov     rsp, r11
0x180118f1a  pop     r15
0x180118f1c  pop     r14
0x180118f1e  pop     r12
0x180118f20  pop     rdi
0x180118f21  pop     rbp
0x180118f22  retn
```
