# UnloadUserProfileInternal(void *,void *)

- ea: `0x180004968`
- end: `0x180004aa0`
- name: `?UnloadUserProfileInternal@@YAJPEAX0@Z`
- size: `312`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, HKEY hKey)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180004af0`

## callees

- `0x1800033e0`
- `0x1800040b0`
- `0x180004968`
- `0x1800056b0`
- `0x180005ff4`
- `0x180006010`
- `0x180006160`
- `0x18000db08`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800049a5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800049a5`

## string_xrefs

- `0x180004a7f`: `onecore\ds\security\gina\profile\userenv\dll\profrpc.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall UnloadUserProfileInternal(char *TokenHandle, HKEY hKey)
{
  int SidString; // eax
  __int64 v5; // rdx
  int v6; // edi
  int UnloadUserProfileClient; // ebx
  LPCWCH lpString1; // [rsp+20h] [rbp-29h] BYREF
  __int64 v9; // [rsp+28h] [rbp-21h]
  __int64 v10; // [rsp+30h] [rbp-19h]
  __int64 (__fastcall **v11)(); // [rsp+40h] [rbp-9h] BYREF
  _QWORD v12[3]; // [rsp+48h] [rbp-1h] BYREF
  int v13; // [rsp+60h] [rbp+17h]
  __int64 v14; // [rsp+68h] [rbp+1Fh]
  char v15; // [rsp+70h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  if ( (unsigned __int64)(TokenHandle - 1) > 0xFFFFFFFFFFFFFFFDuLL
    || (unsigned __int64)hKey - 1 > 0xFFFFFFFFFFFFFFFDuLL
    || RegCloseKey(hKey) )
  {
    return 2147942406LL;
  }
  lpString1 = 0;
  v9 = 0;
  v10 = 0;
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpString1);
  v9 = -1;
  v10 = -1;
  SidString = GetSidString(TokenHandle, (unsigned __int16 **)&lpString1);
  v6 = SidString;
  UnloadUserProfileClient = -2147024890;
  if ( SidString != -2147024890 )
  {
    if ( SidString < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x154,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\dll\\profrpc.cpp",
        (const char *)(unsigned int)SidString,
        (int)lpString1);
      UnloadUserProfileClient = v6;
    }
    else
    {
      v11 = &off_18001E008;
      v12[0] = 0;
      v12[1] = &v11;
      v12[2] = 0;
      v13 = 0;
      v14 = 0;
      v15 = 0;
      wil::details::ThreadFailureCallbackHolder::StartWatching((wil::details::ThreadFailureCallbackHolder *)v12, v5);
      if ( IsServiceSid(lpString1)
        || (UnloadUserProfileClient = _LoadUnloadUserProfileClient(1, TokenHandle, 0), UnloadUserProfileClient >= 0) )
      {
        wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v12);
        UnloadUserProfileClient = 0;
      }
      else
      {
        wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v12);
      }
    }
  }
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpString1);
  return (unsigned int)UnloadUserProfileClient;
}

```

## disassembly

```asm
0x180004968  push    rbp
0x18000496a  push    rbx
0x18000496b  push    rsi
0x18000496c  push    rdi
0x18000496d  lea     rbp, [rsp-3Fh]
0x180004972  sub     rsp, 88h
0x180004979  mov     rsi, rcx
0x18000497c  lea     rax, [rcx-1]
0x180004980  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180004984  jbe     short loc_180004998
0x180004986  mov     eax, 80070006h
0x18000498b  add     rsp, 88h
0x180004992  pop     rdi
0x180004993  pop     rsi
0x180004994  pop     rbx
0x180004995  pop     rbp
0x180004996  retn
0x180004998  lea     rax, [rdx-1]
0x18000499c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800049a0  ja      short loc_180004986
0x1800049a2  mov     rcx, rdx; hKey
0x1800049a5  call    cs:__imp_RegCloseKey
0x1800049ac  nop     dword ptr [rax+rax+00h]
0x1800049b1  test    eax, eax
0x1800049b3  jnz     short loc_180004986
0x1800049b5  mov     [rbp+57h+lpString1], 0
0x1800049bd  mov     [rbp+57h+var_78], 0
0x1800049c5  mov     [rbp+57h+var_70], 0
0x1800049cd  lea     rcx, [rbp+57h+lpString1]
0x1800049d1  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800049d6  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800049da  mov     [rbp+57h+var_78], rax
0x1800049de  mov     [rbp+57h+var_70], rax
0x1800049e2  lea     rdx, [rbp+57h+lpString1]; unsigned __int16 **
0x1800049e6  mov     rcx, rsi; TokenHandle
0x1800049e9  call    ?GetSidString@@YAJPEAXPEAPEAG@Z; GetSidString(void *,ushort * *)
0x1800049ee  mov     edi, eax
0x1800049f0  mov     ebx, 80070006h
0x1800049f5  cmp     eax, ebx
0x1800049f7  jz      short loc_180004A68
0x1800049f9  test    eax, eax
0x1800049fb  js      short loc_180004A78
0x1800049fd  lea     rax, off_18001E008
0x180004a04  mov     [rbp+57h+var_60], rax
0x180004a08  mov     [rbp+57h+var_58], 0
0x180004a10  lea     rax, [rbp+57h+var_60]
0x180004a14  mov     [rbp+57h+var_50], rax
0x180004a18  mov     [rbp+57h+var_48], 0
0x180004a20  mov     [rbp+57h+var_40], 0
0x180004a27  mov     [rbp+57h+var_38], 0
0x180004a2f  mov     [rbp+57h+var_30], 0
0x180004a33  lea     rcx, [rbp+57h+var_58]; this
0x180004a37  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180004a3c  nop
0x180004a3d  mov     rcx, [rbp+57h+lpString1]; lpString1
0x180004a41  call    ?IsServiceSid@@YAHPEBG@Z; IsServiceSid(ushort const *)
0x180004a46  test    eax, eax
0x180004a48  jnz     short loc_180004A5D
0x180004a4a  xor     r8d, r8d; struct _PROFILEINFOW *
0x180004a4d  mov     rdx, rsi; void *
0x180004a50  mov     cl, 1; bool
0x180004a52  call    ?_LoadUnloadUserProfileClient@@YAJ_NPEAXPEAU_PROFILEINFOW@@@Z; _LoadUnloadUserProfileClient(bool,void *,_PROFILEINFOW *)
0x180004a57  mov     ebx, eax
0x180004a59  test    eax, eax
0x180004a5b  js      short loc_180004A94
0x180004a5d  lea     rcx, [rbp+57h+var_58]; this
0x180004a61  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180004a66  xor     ebx, ebx
0x180004a68  lea     rcx, [rbp+57h+lpString1]
0x180004a6c  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180004a71  mov     eax, ebx
0x180004a73  jmp     loc_18000498B
0x180004a78  mov     rcx, [rbp+5Fh]; this
0x180004a7c  mov     r9d, edi; char *
0x180004a7f  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\u"...
0x180004a86  mov     edx, 154h; void *
0x180004a8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004a90  mov     ebx, edi
0x180004a92  jmp     short loc_180004A68
0x180004a94  lea     rcx, [rbp+57h+var_58]; this
0x180004a98  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180004a9d  jmp     short loc_180004A68
```
