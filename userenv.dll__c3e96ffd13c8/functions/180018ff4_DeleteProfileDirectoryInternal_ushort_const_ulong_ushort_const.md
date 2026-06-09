# DeleteProfileDirectoryInternal(ushort const *,ulong,ushort const *)

- ea: `0x180018ff4`
- end: `0x1800191f4`
- name: `?DeleteProfileDirectoryInternal@@YAJPEBGK0@Z`
- size: `512`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, unsigned int, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800144b0`
- `0x1800144c0`

## callees

- `0x180002418`
- `0x1800072a0`
- `0x1800078a0`
- `0x180007a7c`
- `0x18000814c`
- `0x180008314`
- `0x180009cb8`
- `0x18000ccf4`
- `0x18000d9b0`
- `0x1800124b0`
- `0x180013394`
- `0x180018b24`
- `0x180018ff4`
- `0x180019304`
- `0x18001992c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019134`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019134`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180019129`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180019129`

## string_xrefs

- `0x18001918c`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`
- `0x180019029`: `DeleteUserProfileDirectory`

## pseudocode

```c
__int64 __fastcall DeleteProfileDirectoryInternal(LPCWSTR lpFileName, unsigned int a2, const unsigned __int16 *a3)
{
  __int64 v5; // r14
  signed int LastError; // ebx
  int LongProfilePathNameInternal; // eax
  wil::details::in1diag3 *v8; // rcx
  __int64 v9; // rdx
  __int64 *CanRecurseIntoDirectory; // rbx
  DWORD FileAttributesW; // eax
  unsigned __int64 v12; // r9
  int v14; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v15; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v16; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v17; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v18[8]; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v19[42]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v19);
  v19[0] = &UserenvTelemetry::DeleteUserProfileDirectory::`vftable';
  UserenvTelemetry::DeleteUserProfileDirectory::StartActivity((UserenvTelemetry::DeleteUserProfileDirectory *)v19);
  v15 = 0;
  v17 = 0;
  v5 = -1;
  v16 = -1;
  if ( !lpFileName || (int)StringCchLengthW(lpFileName, 0x104u, 0) < 0 )
  {
    LastError = -2147024809;
    goto LABEL_24;
  }
  LongProfilePathNameInternal = GetLongProfilePathNameInternal(lpFileName, &v15, &v17);
  LastError = LongProfilePathNameInternal;
  v8 = retaddr;
  if ( LongProfilePathNameInternal >= 0 )
  {
    CanRecurseIntoDirectory = (__int64 *)wil::TryCreateFileCanRecurseIntoDirectory(v18, v15, 0);
    if ( &v16 != CanRecurseIntoDirectory )
    {
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &v16,
        *CanRecurseIntoDirectory);
      *CanRecurseIntoDirectory = -1;
      v5 = v16;
    }
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v18);
    if ( (unsigned __int64)(v5 - 1) > 0xFFFFFFFFFFFFFFFDuLL
      || (LongProfilePathNameInternal = _Delnode_Recurse(v15, v17, a2),
          LastError = LongProfilePathNameInternal,
          v8 = retaddr,
          LongProfilePathNameInternal >= 0) )
    {
      FileAttributesW = GetFileAttributesW(lpFileName);
      if ( FileAttributesW == -1 )
      {
        LastError = GetLastError();
        if ( (unsigned int)(LastError - 2) <= 1 )
        {
          LastError = 0;
          goto LABEL_22;
        }
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v8 = retaddr;
        if ( LastError >= 0 )
          goto LABEL_22;
        v12 = (unsigned int)LastError;
        v9 = 3600;
        goto LABEL_21;
      }
      LongProfilePathNameInternal = _TryBestToDelete(lpFileName, FileAttributesW, a2);
      LastError = LongProfilePathNameInternal;
      v8 = retaddr;
      if ( LongProfilePathNameInternal >= 0 )
        goto LABEL_22;
      v9 = 3605;
    }
    else
    {
      v9 = 3583;
    }
  }
  else
  {
    v9 = 3570;
  }
  v12 = (unsigned int)LongProfilePathNameInternal;
LABEL_21:
  wil::details::in1diag3::_Log_Hr(
    v8,
    (void *)v9,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
    (const char *)v12,
    v14);
LABEL_22:
  if ( v15 )
    Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Free(v15);
LABEL_24:
  wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v19);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v16);
  UserenvTelemetry::DeleteUserProfileDirectory::~DeleteUserProfileDirectory((UserenvTelemetry::DeleteUserProfileDirectory *)v19);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180018ff4  mov     [rsp-8+arg_10], rbx
0x180018ff9  mov     [rsp-8+arg_18], rsi
0x180018ffe  push    rbp
0x180018fff  push    r14
0x180019001  push    r15
0x180019003  lea     rbp, [rsp-0B0h]
0x18001900b  sub     rsp, 1B0h
0x180019012  mov     rax, cs:__security_cookie
0x180019019  xor     rax, rsp
0x18001901c  mov     [rbp+0C0h+var_20], rax
0x180019023  mov     r15d, edx
0x180019026  mov     rsi, rcx
0x180019029  lea     rdx, aDeleteuserprof; "DeleteUserProfileDirectory"
0x180019030  lea     rcx, [rsp+1C0h+var_170]; struct wil::details::IFailureCallback *
0x180019035  call    ??0?$ActivityBase@VProfileAPILogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18001903a  lea     rax, ??_7DeleteUserProfileDirectory@UserenvTelemetry@@6B@; const UserenvTelemetry::DeleteUserProfileDirectory::`vftable'
0x180019041  mov     [rsp+1C0h+var_170], rax
0x180019046  lea     rcx, [rsp+1C0h+var_170]; this
0x18001904b  call    ?StartActivity@DeleteUserProfileDirectory@UserenvTelemetry@@QEAAXXZ; UserenvTelemetry::DeleteUserProfileDirectory::StartActivity(void)
0x180019050  nop
0x180019051  mov     [rsp+1C0h+var_190], 0
0x18001905a  mov     [rsp+1C0h+var_180], 0
0x180019063  or      r14, 0FFFFFFFFFFFFFFFFh
0x180019067  mov     [rsp+1C0h+var_188], r14
0x18001906c  test    rsi, rsi
0x18001906f  jnz     short loc_18001907B
0x180019071  mov     ebx, 80070057h
0x180019076  jmp     loc_1800191AA
0x18001907b  xor     r8d, r8d; unsigned __int64 *
0x18001907e  mov     edx, 104h; unsigned __int64
0x180019083  mov     rcx, rsi; unsigned __int16 *
0x180019086  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18001908b  test    eax, eax
0x18001908d  js      short loc_180019071
0x18001908f  lea     r8, [rsp+1C0h+var_180]; unsigned __int64 *
0x180019094  lea     rdx, [rsp+1C0h+var_190]; unsigned __int16 **
0x180019099  mov     rcx, rsi; unsigned __int16 *
0x18001909c  call    ?GetLongProfilePathNameInternal@@YAJPEBGPEAPEAGPEA_K@Z; GetLongProfilePathNameInternal(ushort const *,ushort * *,unsigned __int64 *)
0x1800190a1  mov     ebx, eax
0x1800190a3  mov     rcx, [rbp+0C8h]
0x1800190aa  test    eax, eax
0x1800190ac  jns     short loc_1800190B8
0x1800190ae  mov     edx, 0DF2h
0x1800190b3  jmp     loc_180019189
0x1800190b8  xor     r8d, r8d
0x1800190bb  mov     rdx, [rsp+1C0h+var_190]
0x1800190c0  lea     rcx, [rsp+1C0h+var_178]
0x1800190c5  call    ?TryCreateFileCanRecurseIntoDirectory@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@PEBGPEAU_WIN32_FIND_DATAW@@KK@Z; wil::TryCreateFileCanRecurseIntoDirectory(ushort const *,_WIN32_FIND_DATAW *,ulong,ulong)
0x1800190ca  mov     rbx, rax
0x1800190cd  lea     rax, [rsp+1C0h+var_188]
0x1800190d2  cmp     rax, rbx
0x1800190d5  jz      short loc_1800190EC
0x1800190d7  mov     rdx, [rbx]
0x1800190da  lea     rcx, [rsp+1C0h+var_188]
0x1800190df  call    ?reset@?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800190e4  mov     [rbx], r14
0x1800190e7  mov     r14, [rsp+1C0h+var_188]
0x1800190ec  lea     rcx, [rsp+1C0h+var_178]
0x1800190f1  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800190f6  lea     rax, [r14-1]
0x1800190fa  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800190fe  ja      short loc_180019126
0x180019100  mov     r8d, r15d; unsigned int
0x180019103  mov     rdx, [rsp+1C0h+var_180]; unsigned __int64
0x180019108  mov     rcx, [rsp+1C0h+var_190]; unsigned __int16 *
0x18001910d  call    ?_Delnode_Recurse@@YAJPEAG_KK@Z; _Delnode_Recurse(ushort *,unsigned __int64,ulong)
0x180019112  mov     ebx, eax
0x180019114  mov     rcx, [rbp+0C8h]
0x18001911b  test    eax, eax
0x18001911d  jns     short loc_180019126
0x18001911f  mov     edx, 0DFFh
0x180019124  jmp     short loc_180019189
0x180019126  mov     rcx, rsi; lpFileName
0x180019129  call    cs:__imp_GetFileAttributesW
0x18001912f  cmp     eax, 0FFFFFFFFh
0x180019132  jnz     short loc_18001916A
0x180019134  call    cs:__imp_GetLastError
0x18001913a  mov     ebx, eax
0x18001913c  add     eax, 0FFFFFFFEh
0x18001913f  cmp     eax, 1
0x180019142  jbe     short loc_180019166
0x180019144  test    ebx, ebx
0x180019146  jle     short loc_180019151
0x180019148  movzx   ebx, bx
0x18001914b  or      ebx, 80070000h
0x180019151  mov     rcx, [rbp+0C8h]
0x180019158  test    ebx, ebx
0x18001915a  jns     short loc_180019198
0x18001915c  mov     r9d, ebx
0x18001915f  mov     edx, 0E10h
0x180019164  jmp     short loc_18001918C
0x180019166  xor     ebx, ebx
0x180019168  jmp     short loc_180019198
0x18001916a  mov     r8d, r15d; unsigned int
0x18001916d  mov     edx, eax; unsigned int
0x18001916f  mov     rcx, rsi; lpFileName
0x180019172  call    ?_TryBestToDelete@@YAJPEBGKK@Z; _TryBestToDelete(ushort const *,ulong,ulong)
0x180019177  mov     ebx, eax
0x180019179  mov     rcx, [rbp+0C8h]; this
0x180019180  test    eax, eax
0x180019182  jns     short loc_180019198
0x180019184  mov     edx, 0E15h; void *
0x180019189  mov     r9d, eax; char *
0x18001918c  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x180019193  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180019198  cmp     [rsp+1C0h+var_190], 0
0x18001919e  jz      short loc_1800191AA
0x1800191a0  mov     rcx, [rsp+1C0h+var_190]
0x1800191a5  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x1800191aa  lea     rcx, [rsp+1C0h+var_170]
0x1800191af  call    ?Stop@?$ActivityBase@VProfileAPILogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800191b4  nop
0x1800191b5  lea     rcx, [rsp+1C0h+var_188]
0x1800191ba  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800191bf  nop
0x1800191c0  lea     rcx, [rsp+1C0h+var_170]; this
0x1800191c5  call    ??1DeleteUserProfileDirectory@UserenvTelemetry@@QEAA@XZ; UserenvTelemetry::DeleteUserProfileDirectory::~DeleteUserProfileDirectory(void)
0x1800191ca  mov     eax, ebx
0x1800191cc  mov     rcx, [rbp+0C0h+var_20]
0x1800191d3  xor     rcx, rsp; StackCookie
0x1800191d6  call    __security_check_cookie
0x1800191db  lea     r11, [rsp+1C0h+var_10]
0x1800191e3  mov     rbx, [r11+30h]
0x1800191e7  mov     rsi, [r11+38h]
0x1800191eb  mov     rsp, r11
0x1800191ee  pop     r15
0x1800191f0  pop     r14
0x1800191f2  pop     rbp
0x1800191f3  retn
```
