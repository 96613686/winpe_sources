# CBrokeredLauncher::CLaunchHelper::IsAumIdForPackageFamily(ushort const *,ushort const *,bool)

- ea: `0x180058c70`
- end: `0x180058dbd`
- name: `?IsAumIdForPackageFamily@CLaunchHelper@CBrokeredLauncher@@AEAA_NPEBG0_N@Z`
- size: `333`
- prototype: `bool(CBrokeredLauncher::CLaunchHelper *__hidden this, const unsigned __int16 *, const unsigned __int16 *, bool)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18005886c`

## callees

- `0x180058c70`
- `0x180058dc4`
- `0x18008a030`
- `0x1800aae88`
- `0x1800e9678`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180058cc4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180058ce7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180058d77`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180058daf`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180058cc4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180058ce7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180058d77`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180058daf`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x180058d2d`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x180058d2d`

## string_xrefs

- `0x180058d44`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`

## pseudocode

```c
char __fastcall CBrokeredLauncher::CLaunchHelper::IsAumIdForPackageFamily(
        CBrokeredLauncher::CLaunchHelper *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        char a4)
{
  unsigned int v8; // eax
  unsigned int bIgnoreCase; // [rsp+20h] [rbp-168h]
  UINT32 packageRelativeApplicationIdLength; // [rsp+30h] [rbp-158h] BYREF
  UINT32 packageFamilyNameLength[3]; // [rsp+34h] [rbp-154h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+40h] [rbp-148h] BYREF
  WCHAR packageRelativeApplicationId[72]; // [rsp+D0h] [rbp-B8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+0h]

  if ( IsBrowserReplacementFeaturePresent()
    && a4
    && (CompareStringOrdinal(a2, -1, L"MSEdge", -1, 1) == 2
     || CompareStringOrdinal(a2, -1, L"Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe!MSEDGE", -1, 1) == 2) )
  {
    LauncherDesktopProvider::RedirectedEdgePfnLaunch();
    return 1;
  }
  packageFamilyNameLength[0] = 65;
  packageRelativeApplicationIdLength = 66;
  v8 = ParseApplicationUserModelId(
         a2,
         packageFamilyNameLength,
         packageFamilyName,
         &packageRelativeApplicationIdLength,
         packageRelativeApplicationId);
  if ( v8 == 87 )
    return 0;
  if ( v8 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0xA62,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
      (const char *)v8,
      bIgnoreCase);
  if ( a4 )
    return CompareStringOrdinal(packageFamilyName, -1, L"Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe", -1, 1) == 2;
  return CompareStringOrdinal(packageFamilyName, -1, a3, -1, 1) == 2;
}

```

## disassembly

```asm
0x180058c70  mov     [rsp+arg_0], rbx
0x180058c75  push    rsi
0x180058c76  push    rdi
0x180058c77  push    r14
0x180058c79  sub     rsp, 170h
0x180058c80  mov     rax, cs:__security_cookie
0x180058c87  xor     rax, rsp
0x180058c8a  mov     [rsp+188h+var_28], rax
0x180058c92  mov     bl, r9b
0x180058c95  mov     rsi, r8
0x180058c98  mov     rdi, rdx
0x180058c9b  call    ?IsBrowserReplacementFeaturePresent@@YA_NXZ; IsBrowserReplacementFeaturePresent(void)
0x180058ca0  or      r14d, 0FFFFFFFFh
0x180058ca4  test    al, al
0x180058ca6  jz      short loc_180058CFE
0x180058ca8  test    bl, bl
0x180058caa  jz      short loc_180058CFE
0x180058cac  mov     r9d, r14d; cchCount2
0x180058caf  mov     [rsp+188h+bIgnoreCase], 1; bIgnoreCase
0x180058cb7  lea     r8, aMsedge; "MSEdge"
0x180058cbe  mov     edx, r14d; cchCount1
0x180058cc1  mov     rcx, rdi; lpString1
0x180058cc4  call    cs:__imp_CompareStringOrdinal
0x180058cca  cmp     eax, 2
0x180058ccd  jz      short loc_180058CF2
0x180058ccf  mov     r9d, r14d; cchCount2
0x180058cd2  mov     [rsp+188h+bIgnoreCase], 1; bIgnoreCase
0x180058cda  lea     r8, aMicrosoftMicro_1; "Microsoft.MicrosoftEdge.Stable_8wekyb3d"...
0x180058ce1  mov     edx, r14d; cchCount1
0x180058ce4  mov     rcx, rdi; lpString1
0x180058ce7  call    cs:__imp_CompareStringOrdinal
0x180058ced  cmp     eax, 2
0x180058cf0  jnz     short loc_180058CFE
0x180058cf2  call    ?RedirectedEdgePfnLaunch@LauncherDesktopProvider@@SAXXZ; LauncherDesktopProvider::RedirectedEdgePfnLaunch(void)
0x180058cf7  mov     al, 1
0x180058cf9  jmp     loc_180058D88
0x180058cfe  lea     rax, [rsp+188h+packageRelativeApplicationId]
0x180058d06  mov     [rsp+188h+packageFamilyNameLength], 41h ; 'A'
0x180058d0e  lea     r9, [rsp+188h+packageRelativeApplicationIdLength]; packageRelativeApplicationIdLength
0x180058d13  mov     qword ptr [rsp+188h+bIgnoreCase], rax; unsigned int
0x180058d18  lea     r8, [rsp+188h+packageFamilyName]; packageFamilyName
0x180058d1d  mov     [rsp+188h+packageRelativeApplicationIdLength], 42h ; 'B'
0x180058d25  lea     rdx, [rsp+188h+packageFamilyNameLength]; packageFamilyNameLength
0x180058d2a  mov     rcx, rdi; applicationUserModelId
0x180058d2d  call    cs:__imp_ParseApplicationUserModelId
0x180058d33  cmp     eax, 57h ; 'W'
0x180058d36  jz      short loc_180058D86
0x180058d38  test    eax, eax
0x180058d3a  jz      short loc_180058D59
0x180058d3c  mov     rcx, [rsp+188h]; this
0x180058d44  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x180058d4b  mov     r9d, eax; char *
0x180058d4e  mov     edx, 0A62h; void *
0x180058d53  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180058d59  mov     [rsp+188h+bIgnoreCase], 1; bIgnoreCase
0x180058d61  mov     r9d, r14d; cchCount2
0x180058d64  lea     rcx, [rsp+188h+packageFamilyName]; lpString1
0x180058d69  mov     edx, r14d; cchCount1
0x180058d6c  test    bl, bl
0x180058d6e  jz      short loc_180058DAC
0x180058d70  lea     r8, aMicrosoftMicro_0; "Microsoft.MicrosoftEdge.Stable_8wekyb3d"...
0x180058d77  call    cs:__imp_CompareStringOrdinal
0x180058d7d  cmp     eax, 2
0x180058d80  jz      loc_180058CF7
0x180058d86  xor     al, al
0x180058d88  mov     rcx, [rsp+188h+var_28]
0x180058d90  xor     rcx, rsp; StackCookie
0x180058d93  call    __security_check_cookie
0x180058d98  mov     rbx, [rsp+188h+arg_0]
0x180058da0  add     rsp, 170h
0x180058da7  pop     r14
0x180058da9  pop     rdi
0x180058daa  pop     rsi
0x180058dab  retn
0x180058dac  mov     r8, rsi; lpString2
0x180058daf  call    cs:__imp_CompareStringOrdinal
0x180058db5  cmp     eax, 2
0x180058db8  setz    al
0x180058dbb  jmp     short loc_180058D88
```
