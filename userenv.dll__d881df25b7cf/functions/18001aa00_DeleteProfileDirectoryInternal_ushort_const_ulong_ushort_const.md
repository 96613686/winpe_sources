# DeleteProfileDirectoryInternal(ushort const *,ulong,ushort const *)

- ea: `0x18001aa00`
- end: `0x18001ac0d`
- name: `?DeleteProfileDirectoryInternal@@YAJPEBGK0@Z`
- size: `525`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, unsigned int, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180015660`
- `0x180015670`

## callees

- `0x180002468`
- `0x1800070c8`
- `0x180007834`
- `0x180007a44`
- `0x180007f80`
- `0x180008940`
- `0x18000a638`
- `0x18000d9d4`
- `0x18000e640`
- `0x180013494`
- `0x180014440`
- `0x18001a4dc`
- `0x18001aa00`
- `0x18001adcc`
- `0x18001b3b4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ab46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ab46`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001ab35`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001ab35`

## string_xrefs

- `0x18001aba4`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`
- `0x18001aa35`: `DeleteUserProfileDirectory`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DeleteProfileDirectoryInternal(
        unsigned __int16 *lpFileName,
        unsigned int a2,
        const unsigned __int16 *a3)
{
  __int64 v5; // r14
  signed int LastError; // ebx
  int LongProfilePathNameInternal; // eax
  wil::details::in1diag3 *v8; // rcx
  __int64 v9; // rdx
  __int64 *v10; // rbx
  DWORD FileAttributesW; // eax
  unsigned __int64 v12; // r9
  int v14; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v15; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v16; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v17; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v18; // [rsp+48h] [rbp-B8h] BYREF
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
    v10 = wil::TryCreateFileCanRecurseIntoDirectory(&v18, v15, 0);
    if ( &v16 != v10 )
    {
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &v16,
        *v10);
      *v10 = -1;
      v5 = v16;
    }
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v18);
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
        v9 = 3604;
        goto LABEL_21;
      }
      LongProfilePathNameInternal = _TryBestToDelete(lpFileName, FileAttributesW, a2);
      LastError = LongProfilePathNameInternal;
      v8 = retaddr;
      if ( LongProfilePathNameInternal >= 0 )
        goto LABEL_22;
      v9 = 3609;
    }
    else
    {
      v9 = 3587;
    }
  }
  else
  {
    v9 = 3574;
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
0x18001aa00  mov     [rsp-8+arg_10], rbx
0x18001aa05  mov     [rsp-8+arg_18], rsi
0x18001aa0a  push    rbp
0x18001aa0b  push    r14
0x18001aa0d  push    r15
0x18001aa0f  lea     rbp, [rsp-0B0h]
0x18001aa17  sub     rsp, 1B0h
0x18001aa1e  mov     rax, cs:__security_cookie
0x18001aa25  xor     rax, rsp
0x18001aa28  mov     [rbp+0C0h+var_20], rax
0x18001aa2f  mov     r15d, edx
0x18001aa32  mov     rsi, rcx
0x18001aa35  lea     rdx, aDeleteuserprof; "DeleteUserProfileDirectory"
0x18001aa3c  lea     rcx, [rsp+1C0h+var_170]; struct wil::details::IFailureCallback *
0x18001aa41  call    ??0?$ActivityBase@VProfileAPILogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18001aa46  lea     rax, ??_7DeleteUserProfileDirectory@UserenvTelemetry@@6B@; const UserenvTelemetry::DeleteUserProfileDirectory::`vftable'
0x18001aa4d  mov     [rsp+1C0h+var_170], rax
0x18001aa52  lea     rcx, [rsp+1C0h+var_170]; this
0x18001aa57  call    ?StartActivity@DeleteUserProfileDirectory@UserenvTelemetry@@QEAAXXZ; UserenvTelemetry::DeleteUserProfileDirectory::StartActivity(void)
0x18001aa5c  nop
0x18001aa5d  mov     [rsp+1C0h+var_190], 0
0x18001aa66  mov     [rsp+1C0h+var_180], 0
0x18001aa6f  or      r14, 0FFFFFFFFFFFFFFFFh
0x18001aa73  mov     [rsp+1C0h+var_188], r14
0x18001aa78  test    rsi, rsi
0x18001aa7b  jnz     short loc_18001AA87
0x18001aa7d  mov     ebx, 80070057h
0x18001aa82  jmp     loc_18001ABC2
0x18001aa87  xor     r8d, r8d; unsigned __int64 *
0x18001aa8a  mov     edx, 104h; unsigned __int64
0x18001aa8f  mov     rcx, rsi; unsigned __int16 *
0x18001aa92  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18001aa97  test    eax, eax
0x18001aa99  js      short loc_18001AA7D
0x18001aa9b  lea     r8, [rsp+1C0h+var_180]; unsigned __int64 *
0x18001aaa0  lea     rdx, [rsp+1C0h+var_190]; unsigned __int16 **
0x18001aaa5  mov     rcx, rsi; unsigned __int16 *
0x18001aaa8  call    ?GetLongProfilePathNameInternal@@YAJPEBGPEAPEAGPEA_K@Z; GetLongProfilePathNameInternal(ushort const *,ushort * *,unsigned __int64 *)
0x18001aaad  mov     ebx, eax
0x18001aaaf  mov     rcx, [rbp+0C8h]
0x18001aab6  test    eax, eax
0x18001aab8  jns     short loc_18001AAC4
0x18001aaba  mov     edx, 0DF6h
0x18001aabf  jmp     loc_18001ABA1
0x18001aac4  xor     r8d, r8d
0x18001aac7  mov     rdx, [rsp+1C0h+var_190]
0x18001aacc  lea     rcx, [rsp+1C0h+var_178]
0x18001aad1  call    ?TryCreateFileCanRecurseIntoDirectory@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@PEBGPEAU_WIN32_FIND_DATAW@@KK@Z; wil::TryCreateFileCanRecurseIntoDirectory(ushort const *,_WIN32_FIND_DATAW *,ulong,ulong)
0x18001aad6  mov     rbx, rax
0x18001aad9  lea     rax, [rsp+1C0h+var_188]
0x18001aade  cmp     rax, rbx
0x18001aae1  jz      short loc_18001AAF8
0x18001aae3  mov     rdx, [rbx]
0x18001aae6  lea     rcx, [rsp+1C0h+var_188]
0x18001aaeb  call    ?reset@?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18001aaf0  mov     [rbx], r14
0x18001aaf3  mov     r14, [rsp+1C0h+var_188]
0x18001aaf8  lea     rcx, [rsp+1C0h+var_178]
0x18001aafd  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001ab02  lea     rax, [r14-1]
0x18001ab06  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001ab0a  ja      short loc_18001AB32
0x18001ab0c  mov     r8d, r15d; unsigned int
0x18001ab0f  mov     rdx, [rsp+1C0h+var_180]; unsigned __int64
0x18001ab14  mov     rcx, [rsp+1C0h+var_190]; unsigned __int16 *
0x18001ab19  call    ?_Delnode_Recurse@@YAJPEAG_KK@Z; _Delnode_Recurse(ushort *,unsigned __int64,ulong)
0x18001ab1e  mov     ebx, eax
0x18001ab20  mov     rcx, [rbp+0C8h]
0x18001ab27  test    eax, eax
0x18001ab29  jns     short loc_18001AB32
0x18001ab2b  mov     edx, 0E03h
0x18001ab30  jmp     short loc_18001ABA1
0x18001ab32  mov     rcx, rsi; lpFileName
0x18001ab35  call    cs:__imp_GetFileAttributesW
0x18001ab3c  nop     dword ptr [rax+rax+00h]
0x18001ab41  cmp     eax, 0FFFFFFFFh
0x18001ab44  jnz     short loc_18001AB82
0x18001ab46  call    cs:__imp_GetLastError
0x18001ab4d  nop     dword ptr [rax+rax+00h]
0x18001ab52  mov     ebx, eax
0x18001ab54  add     eax, 0FFFFFFFEh
0x18001ab57  cmp     eax, 1
0x18001ab5a  jbe     short loc_18001AB7E
0x18001ab5c  test    ebx, ebx
0x18001ab5e  jle     short loc_18001AB69
0x18001ab60  movzx   ebx, bx
0x18001ab63  or      ebx, 80070000h
0x18001ab69  mov     rcx, [rbp+0C8h]
0x18001ab70  test    ebx, ebx
0x18001ab72  jns     short loc_18001ABB0
0x18001ab74  mov     r9d, ebx
0x18001ab77  mov     edx, 0E14h
0x18001ab7c  jmp     short loc_18001ABA4
0x18001ab7e  xor     ebx, ebx
0x18001ab80  jmp     short loc_18001ABB0
0x18001ab82  mov     r8d, r15d; unsigned int
0x18001ab85  mov     edx, eax; unsigned int
0x18001ab87  mov     rcx, rsi; lpFileName
0x18001ab8a  call    ?_TryBestToDelete@@YAJPEBGKK@Z; _TryBestToDelete(ushort const *,ulong,ulong)
0x18001ab8f  mov     ebx, eax
0x18001ab91  mov     rcx, [rbp+0C8h]; this
0x18001ab98  test    eax, eax
0x18001ab9a  jns     short loc_18001ABB0
0x18001ab9c  mov     edx, 0E19h; void *
0x18001aba1  mov     r9d, eax; char *
0x18001aba4  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x18001abab  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001abb0  cmp     [rsp+1C0h+var_190], 0
0x18001abb6  jz      short loc_18001ABC2
0x18001abb8  mov     rcx, [rsp+1C0h+var_190]
0x18001abbd  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x18001abc2  lea     rcx, [rsp+1C0h+var_170]
0x18001abc7  call    ?Stop@?$ActivityBase@VProfileAPILogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18001abcc  nop
0x18001abcd  lea     rcx, [rsp+1C0h+var_188]
0x18001abd2  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001abd7  nop
0x18001abd8  lea     rcx, [rsp+1C0h+var_170]; this
0x18001abdd  call    ??1DeleteUserProfileDirectory@UserenvTelemetry@@QEAA@XZ; UserenvTelemetry::DeleteUserProfileDirectory::~DeleteUserProfileDirectory(void)
0x18001abe2  mov     eax, ebx
0x18001abe4  mov     rcx, [rbp+0C0h+var_20]
0x18001abeb  xor     rcx, rsp; StackCookie
0x18001abee  call    __security_check_cookie
0x18001abf3  lea     r11, [rsp+1C0h+var_10]
0x18001abfb  mov     rbx, [r11+30h]
0x18001abff  mov     rsi, [r11+38h]
0x18001ac03  mov     rsp, r11
0x18001ac06  pop     r15
0x18001ac08  pop     r14
0x18001ac0a  pop     rbp
0x18001ac0b  retn
```
