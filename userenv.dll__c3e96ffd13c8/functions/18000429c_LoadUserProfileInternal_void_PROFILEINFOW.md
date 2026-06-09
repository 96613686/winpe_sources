# LoadUserProfileInternal(void *,_PROFILEINFOW *)

- ea: `0x18000429c`
- end: `0x1800044ff`
- name: `?LoadUserProfileInternal@@YAJPEAXPEAU_PROFILEINFOW@@@Z`
- size: `611`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, struct _PROFILEINFOW *)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180004540`
- `0x180005ff0`

## callees

- `0x180003f60`
- `0x18000429c`
- `0x180004508`
- `0x180004fe0`
- `0x18000584c`
- `0x180005868`
- `0x1800059a4`
- `0x18000ce7c`
- `0x18000cea0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000449c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000449c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800043d5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800043f9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180004419`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800043d5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800043f9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180004419`
- `profapi!__imp_LoadProfileBasic` at `0x18000446f`
- `profapi!__imp_LoadProfileBasic` at `0x18000446f`

## string_xrefs

- `0x1800044c9`: `onecore\ds\security\gina\profile\userenv\dll\profrpc.cpp`
- `0x1800044e6`: `onecore\ds\security\gina\profile\userenv\dll\profrpc.cpp`

## pseudocode

```c
__int64 __fastcall LoadUserProfileInternal(HANDLE TokenHandle, struct _PROFILEINFOW *a2)
{
  int SidString; // ebx
  LPWSTR lpUserName; // rcx
  int ProfileBasic; // eax
  unsigned int v7; // eax
  int bIgnoreCase; // [rsp+28h] [rbp-29h]
  unsigned int bIgnoreCasea; // [rsp+28h] [rbp-29h]
  LPCWCH lpString1; // [rsp+38h] [rbp-19h] BYREF
  __int64 v11; // [rsp+40h] [rbp-11h]
  __int64 v12; // [rsp+48h] [rbp-9h]
  __int64 (__fastcall **v13)(); // [rsp+58h] [rbp+7h] BYREF
  _QWORD v14[3]; // [rsp+60h] [rbp+Fh] BYREF
  int v15; // [rsp+78h] [rbp+27h]
  __int64 v16; // [rsp+80h] [rbp+2Fh]
  char v17; // [rsp+88h] [rbp+37h]
  struct _PROFILEINFOW **v18; // [rsp+90h] [rbp+3Fh]
  wil::details::in1diag3 *retaddr; // [rsp+B0h] [rbp+5Fh]
  struct _PROFILEINFOW *v20; // [rsp+C0h] [rbp+6Fh] BYREF

  v20 = a2;
  if ( (((unsigned __int64)TokenHandle + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    return 2147942406LL;
  if ( !a2 )
    return 2147942487LL;
  if ( a2->dwSize != 56 )
    return 2147942487LL;
  lpUserName = a2->lpUserName;
  if ( !lpUserName
    || !*lpUserName
    || (a2->dwFlags & 2) != 0
    || !(unsigned int)_ShorterThanMaxPath(lpUserName)
    || !(unsigned int)_ShorterThanMaxPath(v20->lpProfilePath)
    || !(unsigned int)_ShorterThanMaxPath(v20->lpDefaultPath)
    || !(unsigned int)_ShorterThanMaxPath(v20->lpServerName)
    || !(unsigned int)_ShorterThanMaxPath(v20->lpPolicyPath) )
  {
    return 2147942487LL;
  }
  lpString1 = 0;
  v11 = 0;
  v12 = 0;
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpString1);
  v11 = -1;
  v12 = -1;
  SidString = GetSidString(TokenHandle, (unsigned __int16 **)&lpString1);
  if ( SidString >= 0 )
  {
    v13 = off_18001D000;
    v14[0] = 0;
    v14[1] = &v13;
    v14[2] = 0;
    v15 = 0;
    v16 = 0;
    v17 = 0;
    wil::details::ThreadFailureCallbackHolder::StartWatching((wil::details::ThreadFailureCallbackHolder *)v14);
    v18 = &v20;
    if ( CompareStringOrdinal(lpString1, -1, L"S-1-5-18", -1, 1) != 2 )
    {
      if ( CompareStringOrdinal(lpString1, -1, L"S-1-5-19", -1, 1) == 2
        || CompareStringOrdinal(lpString1, -1, L"S-1-5-20", -1, 1) == 2 )
      {
        ProfileBasic = LoadProfileBasic(TokenHandle, 0);
        SidString = ProfileBasic;
        if ( ProfileBasic < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x129,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\dll\\profrpc.cpp",
            (const char *)(unsigned int)ProfileBasic,
            bIgnoreCase);
          goto LABEL_16;
        }
      }
      else
      {
        SidString = _LoadUnloadUserProfileClient(0, TokenHandle, v20);
        if ( SidString < 0 )
        {
LABEL_16:
          wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v14);
          goto LABEL_24;
        }
      }
    }
    v7 = RegOpenKeyExW(HKEY_USERS, lpString1, 0, 0xF003Fu, (PHKEY)&v20->hProfile);
    if ( !v7 )
    {
      wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v14);
      SidString = 0;
      goto LABEL_24;
    }
    SidString = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x137,
                  (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\dll\\profrpc.cpp",
                  (const char *)v7,
                  bIgnoreCasea);
    goto LABEL_16;
  }
LABEL_24:
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpString1);
  return (unsigned int)SidString;
}

```

## disassembly

```asm
0x18000429c  mov     rax, rsp
0x18000429f  mov     [rax+8], rbx
0x1800042a3  mov     [rax+18h], rdi
0x1800042a7  mov     [rax+10h], rdx
0x1800042ab  push    rbp
0x1800042ac  push    r14
0x1800042ae  push    r15
0x1800042b0  lea     rbp, [rax-5Fh]
0x1800042b4  sub     rsp, 90h
0x1800042bb  mov     rdi, rcx
0x1800042be  lea     rax, [rcx+1]
0x1800042c2  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800042c8  jnz     loc_180004443
0x1800042ce  mov     eax, 80070006h
0x1800042d3  jmp     short loc_1800042EF
0x1800042d5  cmp     [rcx], r14w
0x1800042d9  jz      short loc_1800042EA
0x1800042db  test    byte ptr [rdx+4], 2
0x1800042df  jnz     short loc_1800042EA
0x1800042e1  call    ?_ShorterThanMaxPath@@YAHPEBG@Z; _ShorterThanMaxPath(ushort const *)
0x1800042e6  test    eax, eax
0x1800042e8  jnz     short loc_180004308
0x1800042ea  mov     eax, 80070057h
0x1800042ef  lea     r11, [rsp+0A0h+var_10]
0x1800042f7  mov     rbx, [r11+20h]
0x1800042fb  mov     rdi, [r11+30h]
0x1800042ff  mov     rsp, r11
0x180004302  pop     r15
0x180004304  pop     r14
0x180004306  pop     rbp
0x180004307  retn
0x180004308  mov     rcx, [rbp+57h+arg_8]
0x18000430c  mov     rcx, [rcx+10h]; unsigned __int16 *
0x180004310  call    ?_ShorterThanMaxPath@@YAHPEBG@Z; _ShorterThanMaxPath(ushort const *)
0x180004315  test    eax, eax
0x180004317  jz      short loc_1800042EA
0x180004319  mov     rcx, [rbp+57h+arg_8]
0x18000431d  mov     rcx, [rcx+18h]; unsigned __int16 *
0x180004321  call    ?_ShorterThanMaxPath@@YAHPEBG@Z; _ShorterThanMaxPath(ushort const *)
0x180004326  test    eax, eax
0x180004328  jz      short loc_1800042EA
0x18000432a  mov     rcx, [rbp+57h+arg_8]
0x18000432e  mov     rcx, [rcx+20h]; unsigned __int16 *
0x180004332  call    ?_ShorterThanMaxPath@@YAHPEBG@Z; _ShorterThanMaxPath(ushort const *)
0x180004337  test    eax, eax
0x180004339  jz      short loc_1800042EA
0x18000433b  mov     rcx, [rbp+57h+arg_8]
0x18000433f  mov     rcx, [rcx+28h]; unsigned __int16 *
0x180004343  call    ?_ShorterThanMaxPath@@YAHPEBG@Z; _ShorterThanMaxPath(ushort const *)
0x180004348  test    eax, eax
0x18000434a  jz      short loc_1800042EA
0x18000434c  mov     [rbp+57h+lpString1], r14
0x180004350  mov     [rbp+57h+var_68], r14
0x180004354  mov     [rbp+57h+var_60], r14
0x180004358  lea     rcx, [rbp+57h+lpString1]
0x18000435c  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180004361  or      r15, 0FFFFFFFFFFFFFFFFh
0x180004365  mov     [rbp+57h+var_68], r15
0x180004369  mov     [rbp+57h+var_60], r15
0x18000436d  lea     rdx, [rbp+57h+lpString1]; unsigned __int16 **
0x180004371  mov     rcx, rdi; TokenHandle
0x180004374  call    ?GetSidString@@YAJPEAXPEAPEAG@Z; GetSidString(void *,ushort * *)
0x180004379  mov     ebx, eax
0x18000437b  test    eax, eax
0x18000437d  js      loc_1800044B2
0x180004383  lea     rax, off_18001D000
0x18000438a  mov     [rbp+57h+var_50], rax
0x18000438e  mov     [rbp+57h+var_48], r14
0x180004392  lea     rax, [rbp+57h+var_50]
0x180004396  mov     [rbp+57h+var_40], rax
0x18000439a  mov     [rbp+57h+var_38], r14
0x18000439e  mov     [rbp+57h+var_30], r14d
0x1800043a2  mov     [rbp+57h+var_28], r14
0x1800043a6  mov     [rbp+57h+var_20], r14b
0x1800043aa  lea     rcx, [rbp+57h+var_48]; this
0x1800043ae  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x1800043b3  nop
0x1800043b4  lea     rax, [rbp+57h+arg_8]
0x1800043b8  mov     [rbp+57h+var_18], rax
0x1800043bc  lea     ebx, [r15+2]
0x1800043c0  mov     [rsp+0A0h+bIgnoreCase], ebx; bIgnoreCase
0x1800043c4  mov     r9d, r15d; cchCount2
0x1800043c7  lea     r8, String2; "S-1-5-18"
0x1800043ce  mov     edx, r15d; cchCount1
0x1800043d1  mov     rcx, [rbp+57h+lpString1]; lpString1
0x1800043d5  call    cs:__imp_CompareStringOrdinal
0x1800043db  cmp     eax, 2
0x1800043de  jz      loc_18000447B
0x1800043e4  mov     [rsp+0A0h+bIgnoreCase], ebx; int
0x1800043e8  mov     r9d, r15d; cchCount2
0x1800043eb  lea     r8, aS1519; "S-1-5-19"
0x1800043f2  mov     edx, r15d; cchCount1
0x1800043f5  mov     rcx, [rbp+57h+lpString1]; lpString1
0x1800043f9  call    cs:__imp_CompareStringOrdinal
0x1800043ff  cmp     eax, 2
0x180004402  jz      short loc_18000446A
0x180004404  mov     [rsp+0A0h+bIgnoreCase], ebx; bIgnoreCase
0x180004408  mov     r9d, r15d; cchCount2
0x18000440b  lea     r8, aS1520; "S-1-5-20"
0x180004412  mov     edx, r15d; cchCount1
0x180004415  mov     rcx, [rbp+57h+lpString1]; lpString1
0x180004419  call    cs:__imp_CompareStringOrdinal
0x18000441f  cmp     eax, 2
0x180004422  jz      short loc_18000446A
0x180004424  mov     r8, [rbp+57h+arg_8]; struct _PROFILEINFOW *
0x180004428  mov     rdx, rdi; void *
0x18000442b  xor     ecx, ecx; bool
0x18000442d  call    ?_LoadUnloadUserProfileClient@@YAJ_NPEAXPEAU_PROFILEINFOW@@@Z; _LoadUnloadUserProfileClient(bool,void *,_PROFILEINFOW *)
0x180004432  mov     ebx, eax
0x180004434  test    eax, eax
0x180004436  jns     short loc_18000447B
0x180004438  lea     rcx, [rbp+57h+var_48]; this
0x18000443c  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180004441  jmp     short loc_1800044B2
0x180004443  xor     r14d, r14d
0x180004446  test    rdx, rdx
0x180004449  jz      loc_1800042EA
0x18000444f  cmp     dword ptr [rdx], 38h ; '8'
0x180004452  jnz     loc_1800042EA
0x180004458  mov     rcx, [rdx+8]; unsigned __int16 *
0x18000445c  test    rcx, rcx
0x18000445f  jz      loc_1800042EA
0x180004465  jmp     loc_1800042D5
0x18000446a  xor     edx, edx
0x18000446c  mov     rcx, rdi
0x18000446f  call    cs:__imp_LoadProfileBasic
0x180004475  mov     ebx, eax
0x180004477  test    eax, eax
0x180004479  js      short loc_1800044C2
0x18000447b  mov     rax, [rbp+57h+arg_8]
0x18000447f  add     rax, 30h ; '0'
0x180004483  mov     qword ptr [rsp+0A0h+bIgnoreCase], rax; unsigned int
0x180004488  mov     r9d, 0F003Fh; samDesired
0x18000448e  xor     r8d, r8d; ulOptions
0x180004491  mov     rdx, [rbp+57h+lpString1]; lpSubKey
0x180004495  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18000449c  call    cs:__imp_RegOpenKeyExW
0x1800044a2  test    eax, eax
0x1800044a4  jnz     short loc_1800044DF
0x1800044a6  lea     rcx, [rbp+57h+var_48]; this
0x1800044aa  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x1800044af  mov     ebx, r14d
0x1800044b2  lea     rcx, [rbp+57h+lpString1]
0x1800044b6  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800044bb  mov     eax, ebx
0x1800044bd  jmp     loc_1800042EF
0x1800044c2  mov     rcx, [rbp+5Fh]; this
0x1800044c6  mov     r9d, eax; char *
0x1800044c9  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\u"...
0x1800044d0  mov     edx, 129h; void *
0x1800044d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800044da  jmp     loc_180004438
0x1800044df  mov     rcx, [rbp+5Fh]; this
0x1800044e3  mov     r9d, eax; char *
0x1800044e6  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\u"...
0x1800044ed  mov     edx, 137h; void *
0x1800044f2  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800044f7  mov     ebx, eax
0x1800044f9  jmp     loc_180004438
```
