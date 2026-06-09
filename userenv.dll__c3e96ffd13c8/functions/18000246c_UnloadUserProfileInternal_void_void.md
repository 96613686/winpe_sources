# UnloadUserProfileInternal(void *,void *)

- ea: `0x18000246c`
- end: `0x18000259d`
- name: `?UnloadUserProfileInternal@@YAJPEAX0@Z`
- size: `305`
- prototype: `__int64 __fastcall(char *TokenHandle, HKEY hKey)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180002440`

## callees

- `0x18000246c`
- `0x180003380`
- `0x180003f60`
- `0x180004fe0`
- `0x18000584c`
- `0x180005868`
- `0x1800059a4`
- `0x18000cea0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800024a8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800024a8`

## string_xrefs

- `0x18000257c`: `onecore\ds\security\gina\profile\userenv\dll\profrpc.cpp`

## pseudocode

```c
__int64 __fastcall UnloadUserProfileInternal(char *TokenHandle, HKEY hKey)
{
  int SidString; // eax
  int v5; // edi
  int UnloadUserProfileClient; // ebx
  LPCWCH lpString1; // [rsp+20h] [rbp-29h] BYREF
  __int64 v8; // [rsp+28h] [rbp-21h]
  __int64 v9; // [rsp+30h] [rbp-19h]
  __int64 (__fastcall **v10)(); // [rsp+40h] [rbp-9h] BYREF
  _QWORD v11[3]; // [rsp+48h] [rbp-1h] BYREF
  int v12; // [rsp+60h] [rbp+17h]
  __int64 v13; // [rsp+68h] [rbp+1Fh]
  char v14; // [rsp+70h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  if ( (unsigned __int64)(TokenHandle - 1) > 0xFFFFFFFFFFFFFFFDuLL
    || (unsigned __int64)hKey - 1 > 0xFFFFFFFFFFFFFFFDuLL
    || RegCloseKey(hKey) )
  {
    return 2147942406LL;
  }
  lpString1 = 0;
  v8 = 0;
  v9 = 0;
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpString1);
  v8 = -1;
  v9 = -1;
  SidString = GetSidString(TokenHandle, (unsigned __int16 **)&lpString1);
  v5 = SidString;
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
      UnloadUserProfileClient = v5;
    }
    else
    {
      v10 = &off_18001D008;
      v11[0] = 0;
      v11[1] = &v10;
      v11[2] = 0;
      v12 = 0;
      v13 = 0;
      v14 = 0;
      wil::details::ThreadFailureCallbackHolder::StartWatching((wil::details::ThreadFailureCallbackHolder *)v11);
      if ( (unsigned int)IsServiceSid(lpString1)
        || (UnloadUserProfileClient = _LoadUnloadUserProfileClient(1, TokenHandle, 0), UnloadUserProfileClient >= 0) )
      {
        wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v11);
        UnloadUserProfileClient = 0;
      }
      else
      {
        wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v11);
      }
    }
  }
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpString1);
  return (unsigned int)UnloadUserProfileClient;
}

```

## disassembly

```asm
0x18000246c  push    rbp
0x18000246e  push    rbx
0x18000246f  push    rsi
0x180002470  push    rdi
0x180002471  lea     rbp, [rsp-3Fh]
0x180002476  sub     rsp, 88h
0x18000247d  mov     rsi, rcx
0x180002480  lea     rax, [rcx-1]
0x180002484  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180002488  jbe     short loc_18000249B
0x18000248a  mov     eax, 80070006h
0x18000248f  add     rsp, 88h
0x180002496  pop     rdi
0x180002497  pop     rsi
0x180002498  pop     rbx
0x180002499  pop     rbp
0x18000249a  retn
0x18000249b  lea     rax, [rdx-1]
0x18000249f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800024a3  ja      short loc_18000248A
0x1800024a5  mov     rcx, rdx; hKey
0x1800024a8  call    cs:__imp_RegCloseKey
0x1800024ae  test    eax, eax
0x1800024b0  jnz     short loc_18000248A
0x1800024b2  mov     [rbp+57h+lpString1], 0
0x1800024ba  mov     [rbp+57h+var_78], 0
0x1800024c2  mov     [rbp+57h+var_70], 0
0x1800024ca  lea     rcx, [rbp+57h+lpString1]
0x1800024ce  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800024d3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800024d7  mov     [rbp+57h+var_78], rax
0x1800024db  mov     [rbp+57h+var_70], rax
0x1800024df  lea     rdx, [rbp+57h+lpString1]; unsigned __int16 **
0x1800024e3  mov     rcx, rsi; TokenHandle
0x1800024e6  call    ?GetSidString@@YAJPEAXPEAPEAG@Z; GetSidString(void *,ushort * *)
0x1800024eb  mov     edi, eax
0x1800024ed  mov     ebx, 80070006h
0x1800024f2  cmp     eax, ebx
0x1800024f4  jz      short loc_180002565
0x1800024f6  test    eax, eax
0x1800024f8  js      short loc_180002575
0x1800024fa  lea     rax, off_18001D008
0x180002501  mov     [rbp+57h+var_60], rax
0x180002505  mov     [rbp+57h+var_58], 0
0x18000250d  lea     rax, [rbp+57h+var_60]
0x180002511  mov     [rbp+57h+var_50], rax
0x180002515  mov     [rbp+57h+var_48], 0
0x18000251d  mov     [rbp+57h+var_40], 0
0x180002524  mov     [rbp+57h+var_38], 0
0x18000252c  mov     [rbp+57h+var_30], 0
0x180002530  lea     rcx, [rbp+57h+var_58]; this
0x180002534  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180002539  nop
0x18000253a  mov     rcx, [rbp+57h+lpString1]; lpString1
0x18000253e  call    ?IsServiceSid@@YAHPEBG@Z; IsServiceSid(ushort const *)
0x180002543  test    eax, eax
0x180002545  jnz     short loc_18000255A
0x180002547  xor     r8d, r8d; struct _PROFILEINFOW *
0x18000254a  mov     rdx, rsi; void *
0x18000254d  mov     cl, 1; bool
0x18000254f  call    ?_LoadUnloadUserProfileClient@@YAJ_NPEAXPEAU_PROFILEINFOW@@@Z; _LoadUnloadUserProfileClient(bool,void *,_PROFILEINFOW *)
0x180002554  mov     ebx, eax
0x180002556  test    eax, eax
0x180002558  js      short loc_180002591
0x18000255a  lea     rcx, [rbp+57h+var_58]; this
0x18000255e  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180002563  xor     ebx, ebx
0x180002565  lea     rcx, [rbp+57h+lpString1]
0x180002569  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18000256e  mov     eax, ebx
0x180002570  jmp     loc_18000248F
0x180002575  mov     rcx, [rbp+5Fh]; this
0x180002579  mov     r9d, edi; char *
0x18000257c  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\u"...
0x180002583  mov     edx, 154h; void *
0x180002588  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000258d  mov     ebx, edi
0x18000258f  jmp     short loc_180002565
0x180002591  lea     rcx, [rbp+57h+var_58]; this
0x180002595  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x18000259a  jmp     short loc_180002565
```
