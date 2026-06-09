# LoadUserProfileInternal(void *,_PROFILEINFOW *)

- ea: `0x1800046ac`
- end: `0x18000492e`
- name: `?LoadUserProfileInternal@@YAJPEAXPEAU_PROFILEINFOW@@@Z`
- size: `642`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, struct _PROFILEINFOW *)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180004ab0`
- `0x1800084f0`

## callees

- `0x1800040b0`
- `0x1800046ac`
- `0x180004934`
- `0x1800056b0`
- `0x180005ff4`
- `0x180006010`
- `0x180006160`
- `0x18000dae0`
- `0x18000db08`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800048c5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800048c5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800047e6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180004810`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180004836`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800047e6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180004810`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180004836`
- `profapi!__imp_LoadProfileBasic` at `0x180004892`
- `profapi!__imp_LoadProfileBasic` at `0x180004892`

## string_xrefs

- `0x1800048f8`: `onecore\ds\security\gina\profile\userenv\dll\profrpc.cpp`
- `0x180004915`: `onecore\ds\security\gina\profile\userenv\dll\profrpc.cpp`

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
    v13 = off_18001E000;
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
0x1800046ac  mov     rax, rsp
0x1800046af  mov     [rax+8], rbx
0x1800046b3  mov     [rax+18h], rdi
0x1800046b7  mov     [rax+10h], rdx
0x1800046bb  push    rbp
0x1800046bc  push    r14
0x1800046be  push    r15
0x1800046c0  lea     rbp, [rax-5Fh]
0x1800046c4  sub     rsp, 90h
0x1800046cb  mov     rdi, rcx
0x1800046ce  lea     rax, [rcx+1]
0x1800046d2  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800046d8  jnz     loc_180004866
0x1800046de  mov     eax, 80070006h
0x1800046e3  jmp     short loc_1800046FF
0x1800046e5  cmp     [rcx], r14w
0x1800046e9  jz      short loc_1800046FA
0x1800046eb  test    byte ptr [rdx+4], 2
0x1800046ef  jnz     short loc_1800046FA
0x1800046f1  call    ?_ShorterThanMaxPath@@YAHPEBG@Z; _ShorterThanMaxPath(ushort const *)
0x1800046f6  test    eax, eax
0x1800046f8  jnz     short loc_180004719
0x1800046fa  mov     eax, 80070057h
0x1800046ff  lea     r11, [rsp+0A0h+var_10]
0x180004707  mov     rbx, [r11+20h]
0x18000470b  mov     rdi, [r11+30h]
0x18000470f  mov     rsp, r11
0x180004712  pop     r15
0x180004714  pop     r14
0x180004716  pop     rbp
0x180004717  retn
0x180004719  mov     rcx, [rbp+57h+arg_8]
0x18000471d  mov     rcx, [rcx+10h]; unsigned __int16 *
0x180004721  call    ?_ShorterThanMaxPath@@YAHPEBG@Z; _ShorterThanMaxPath(ushort const *)
0x180004726  test    eax, eax
0x180004728  jz      short loc_1800046FA
0x18000472a  mov     rcx, [rbp+57h+arg_8]
0x18000472e  mov     rcx, [rcx+18h]; unsigned __int16 *
0x180004732  call    ?_ShorterThanMaxPath@@YAHPEBG@Z; _ShorterThanMaxPath(ushort const *)
0x180004737  test    eax, eax
0x180004739  jz      short loc_1800046FA
0x18000473b  mov     rcx, [rbp+57h+arg_8]
0x18000473f  mov     rcx, [rcx+20h]; unsigned __int16 *
0x180004743  call    ?_ShorterThanMaxPath@@YAHPEBG@Z; _ShorterThanMaxPath(ushort const *)
0x180004748  test    eax, eax
0x18000474a  jz      short loc_1800046FA
0x18000474c  mov     rcx, [rbp+57h+arg_8]
0x180004750  mov     rcx, [rcx+28h]; unsigned __int16 *
0x180004754  call    ?_ShorterThanMaxPath@@YAHPEBG@Z; _ShorterThanMaxPath(ushort const *)
0x180004759  test    eax, eax
0x18000475b  jz      short loc_1800046FA
0x18000475d  mov     [rbp+57h+lpString1], r14
0x180004761  mov     [rbp+57h+var_68], r14
0x180004765  mov     [rbp+57h+var_60], r14
0x180004769  lea     rcx, [rbp+57h+lpString1]
0x18000476d  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180004772  or      r15, 0FFFFFFFFFFFFFFFFh
0x180004776  mov     [rbp+57h+var_68], r15
0x18000477a  mov     [rbp+57h+var_60], r15
0x18000477e  lea     rdx, [rbp+57h+lpString1]; unsigned __int16 **
0x180004782  mov     rcx, rdi; TokenHandle
0x180004785  call    ?GetSidString@@YAJPEAXPEAPEAG@Z; GetSidString(void *,ushort * *)
0x18000478a  mov     ebx, eax
0x18000478c  test    eax, eax
0x18000478e  js      loc_1800048E1
0x180004794  lea     rax, off_18001E000
0x18000479b  mov     [rbp+57h+var_50], rax
0x18000479f  mov     [rbp+57h+var_48], r14
0x1800047a3  lea     rax, [rbp+57h+var_50]
0x1800047a7  mov     [rbp+57h+var_40], rax
0x1800047ab  mov     [rbp+57h+var_38], r14
0x1800047af  mov     [rbp+57h+var_30], r14d
0x1800047b3  mov     [rbp+57h+var_28], r14
0x1800047b7  mov     [rbp+57h+var_20], r14b
0x1800047bb  lea     rcx, [rbp+57h+var_48]; this
0x1800047bf  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x1800047c4  nop
0x1800047c5  lea     rax, [rbp+57h+arg_8]
0x1800047c9  mov     [rbp+57h+var_18], rax
0x1800047cd  lea     ebx, [r15+2]
0x1800047d1  mov     [rsp+0A0h+bIgnoreCase], ebx; bIgnoreCase
0x1800047d5  mov     r9d, r15d; cchCount2
0x1800047d8  lea     r8, String2; "S-1-5-18"
0x1800047df  mov     edx, r15d; cchCount1
0x1800047e2  mov     rcx, [rbp+57h+lpString1]; lpString1
0x1800047e6  call    cs:__imp_CompareStringOrdinal
0x1800047ed  nop     dword ptr [rax+rax+00h]
0x1800047f2  cmp     eax, 2
0x1800047f5  jz      loc_1800048A4
0x1800047fb  mov     [rsp+0A0h+bIgnoreCase], ebx; int
0x1800047ff  mov     r9d, r15d; cchCount2
0x180004802  lea     r8, aS1519; "S-1-5-19"
0x180004809  mov     edx, r15d; cchCount1
0x18000480c  mov     rcx, [rbp+57h+lpString1]; lpString1
0x180004810  call    cs:__imp_CompareStringOrdinal
0x180004817  nop     dword ptr [rax+rax+00h]
0x18000481c  cmp     eax, 2
0x18000481f  jz      short loc_18000488D
0x180004821  mov     [rsp+0A0h+bIgnoreCase], ebx; bIgnoreCase
0x180004825  mov     r9d, r15d; cchCount2
0x180004828  lea     r8, aS1520; "S-1-5-20"
0x18000482f  mov     edx, r15d; cchCount1
0x180004832  mov     rcx, [rbp+57h+lpString1]; lpString1
0x180004836  call    cs:__imp_CompareStringOrdinal
0x18000483d  nop     dword ptr [rax+rax+00h]
0x180004842  cmp     eax, 2
0x180004845  jz      short loc_18000488D
0x180004847  mov     r8, [rbp+57h+arg_8]; struct _PROFILEINFOW *
0x18000484b  mov     rdx, rdi; void *
0x18000484e  xor     ecx, ecx; bool
0x180004850  call    ?_LoadUnloadUserProfileClient@@YAJ_NPEAXPEAU_PROFILEINFOW@@@Z; _LoadUnloadUserProfileClient(bool,void *,_PROFILEINFOW *)
0x180004855  mov     ebx, eax
0x180004857  test    eax, eax
0x180004859  jns     short loc_1800048A4
0x18000485b  lea     rcx, [rbp+57h+var_48]; this
0x18000485f  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180004864  jmp     short loc_1800048E1
0x180004866  xor     r14d, r14d
0x180004869  test    rdx, rdx
0x18000486c  jz      loc_1800046FA
0x180004872  cmp     dword ptr [rdx], 38h ; '8'
0x180004875  jnz     loc_1800046FA
0x18000487b  mov     rcx, [rdx+8]; unsigned __int16 *
0x18000487f  test    rcx, rcx
0x180004882  jz      loc_1800046FA
0x180004888  jmp     loc_1800046E5
0x18000488d  xor     edx, edx
0x18000488f  mov     rcx, rdi
0x180004892  call    cs:__imp_LoadProfileBasic
0x180004899  nop     dword ptr [rax+rax+00h]
0x18000489e  mov     ebx, eax
0x1800048a0  test    eax, eax
0x1800048a2  js      short loc_1800048F1
0x1800048a4  mov     rax, [rbp+57h+arg_8]
0x1800048a8  add     rax, 30h ; '0'
0x1800048ac  mov     qword ptr [rsp+0A0h+bIgnoreCase], rax; unsigned int
0x1800048b1  mov     r9d, 0F003Fh; samDesired
0x1800048b7  xor     r8d, r8d; ulOptions
0x1800048ba  mov     rdx, [rbp+57h+lpString1]; lpSubKey
0x1800048be  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1800048c5  call    cs:__imp_RegOpenKeyExW
0x1800048cc  nop     dword ptr [rax+rax+00h]
0x1800048d1  test    eax, eax
0x1800048d3  jnz     short loc_18000490E
0x1800048d5  lea     rcx, [rbp+57h+var_48]; this
0x1800048d9  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x1800048de  mov     ebx, r14d
0x1800048e1  lea     rcx, [rbp+57h+lpString1]
0x1800048e5  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800048ea  mov     eax, ebx
0x1800048ec  jmp     loc_1800046FF
0x1800048f1  mov     rcx, [rbp+5Fh]; this
0x1800048f5  mov     r9d, eax; char *
0x1800048f8  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\u"...
0x1800048ff  mov     edx, 129h; void *
0x180004904  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004909  jmp     loc_18000485B
0x18000490e  mov     rcx, [rbp+5Fh]; this
0x180004912  mov     r9d, eax; char *
0x180004915  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\u"...
0x18000491c  mov     edx, 137h; void *
0x180004921  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180004926  mov     ebx, eax
0x180004928  jmp     loc_18000485B
```
