# UserManagerTokenAndShellHandler::TryGetDefaultAccountUser(Windows::System::IUser * *)

- ea: `0x180008630`
- end: `0x1800088e2`
- name: `?TryGetDefaultAccountUser@UserManagerTokenAndShellHandler@@QEAAJPEAPEAUIUser@System@Windows@@@Z`
- size: `690`
- prototype: `__int64 __fastcall(UserManagerTokenAndShellHandler *__hidden this, struct Windows::System::IUser **)`
- caller_count: `4`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180042b80`
- `0x18007bc10`
- `0x18007c550`
- `0x18007e570`

## callees

- `0x180006130`
- `0x180007920`
- `0x180008630`
- `0x1800088e8`
- `0x18000890c`
- `0x180008b10`
- `0x18000a4a0`
- `0x180014e9c`
- `0x180015960`
- `0x180024828`
- `0x18006f1c9`
- `0x1800de450`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockShared` at `0x18000868b`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockShared` at `0x18000868b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800086d0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180008763`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800087c7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800086d0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180008763`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800087c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800088a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800088a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800086db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000876e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800087d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180008877`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800086db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000876e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800087d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180008877`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008809`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008809`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800086ee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008781`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800087e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800086ee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008781`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800087e5`
- `ntdll!RtlEqualSid` at `0x1800088c7`
- `ntdll!RtlEqualSid` at `0x1800088c7`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800088ae`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800088ae`

## string_xrefs

- `0x1800086b6`: `onecore\ds\security\umstartup\usermgr\lib\usermgrtokenandshellhandler.cpp`
- `0x1800087ad`: `onecore\ds\security\umstartup\usermgr\lib\usermgrtokenandshellhandler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall UserManagerTokenAndShellHandler::TryGetDefaultAccountUser(
        UserManagerTokenAndShellHandler *this,
        struct Windows::System::IUser **a2)
{
  unsigned __int64 v2; // rbp
  RTL_SRWLOCK *v4; // rbx
  const char *v6; // r9
  void *v7; // rcx
  char *v8; // rcx
  _QWORD *v9; // rcx
  __int64 result; // rax
  void *v11; // rcx
  void *v12; // rcx
  __int64 v13; // rsi
  void (__fastcall *v14)(__int64, unsigned __int64); // rdi
  const WCHAR *StringRawBuffer; // rax
  int v16; // [rsp+20h] [rbp-20h]
  HSTRING string; // [rsp+40h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+228h]

  v2 = (unsigned __int64)&string & 0xFFFFFFFFFFFFFFE0uLL;
  *(_QWORD *)(((unsigned __int64)&string & 0xFFFFFFFFFFFFFFE0uLL) + 0x18) = 0;
  *(_QWORD *)(((unsigned __int64)&string & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) = 0;
  *(_QWORD *)(((unsigned __int64)&string & 0xFFFFFFFFFFFFFFE0uLL) + 8) = 0;
  *(_QWORD *)((unsigned __int64)&string & 0xFFFFFFFFFFFFFFE0uLL) = 0;
  memset_0((void *)(((unsigned __int64)&string & 0xFFFFFFFFFFFFFFE0uLL) + 64), 0, 0x1A0u);
  v4 = &SRWLock;
  if ( !TryAcquireSRWLockShared(&SRWLock) )
    v4 = 0;
  try
  {
    *(_QWORD *)(((unsigned __int64)&string & 0xFFFFFFFFFFFFFFE0uLL) + 0x20) = v4;
    if ( qword_180148230 )
    {
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        v2 + 16,
        0);
      GetCallerToken2((PHANDLE)(v2 + 16));
      GetCallerInformationFromToken(
        *(HANDLE *)(((unsigned __int64)&string & 0xFFFFFFFFFFFFFFE0uLL) + 0x10),
        (struct _BASIC_CALLER_INFORMATION *)(v2 + 64),
        0);
      if ( *(_BYTE *)(((unsigned __int64)&string & 0xFFFFFFFFFFFFFFE0uLL) + 0x42)
        && *(_BYTE *)(((unsigned __int64)&string & 0xFFFFFFFFFFFFFFE0uLL) + 0x40) )
      {
        goto LABEL_13;
      }
      if ( *(_BYTE *)(((unsigned __int64)&string & 0xFFFFFFFFFFFFFFE0uLL) + 0x41)
        && *(_BYTE *)(((unsigned __int64)&string & 0xFFFFFFFFFFFFFFE0uLL) + 0x4C) )
      {
        goto LABEL_13;
      }
      Microsoft::WRL::ComPtr<Windows::System::IUser>::As<Windows::System::Internal::Implementation::IUserInternal>(
        (__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))&qword_180148230,
        (__int64 *)(v2 + 24));
      v13 = *(_QWORD *)(((unsigned __int64)&string & 0xFFFFFFFFFFFFFFE0uLL) + 0x18);
      v14 = *(void (__fastcall **)(__int64, unsigned __int64))(*(_QWORD *)v13 + 72LL);
      WindowsDeleteString(*(HSTRING *)v2);
      *(_QWORD *)v2 = 0;
      v14(v13, (unsigned __int64)&string & 0xFFFFFFFFFFFFFFE0uLL);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        v2 + 8,
        0);
      StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)v2, 0);
      if ( !ConvertStringSidToSidW(StringRawBuffer, (PSID *)(v2 + 8)) )
        goto LABEL_18;
      if ( RtlEqualSid(
             *(PSID *)(((unsigned __int64)&string & 0xFFFFFFFFFFFFFFE0uLL) + 0xB8),
             *(PSID *)(((unsigned __int64)&string & 0xFFFFFFFFFFFFFFE0uLL) + 8)) )
      {
LABEL_13:
        Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&qword_180148230);
        *a2 = (struct Windows::System::IUser *)qword_180148230;
        if ( v4 )
          ReleaseSRWLockShared(v4);
        WindowsDeleteString(*(HSTRING *)v2);
        *(_QWORD *)v2 = 0;
        v11 = *(void **)(((unsigned __int64)&string & 0xFFFFFFFFFFFFFFE0uLL) + 8);
        if ( v11 )
          LocalFree(v11);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v2 + 16);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v2 + 24);
        result = 0;
      }
      else
      {
LABEL_18:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5AF,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrtokenandshellhandler.cpp",
          (const char *)0x80070005LL,
          v16);
        if ( v4 )
          ReleaseSRWLockShared(v4);
        WindowsDeleteString(*(HSTRING *)v2);
        *(_QWORD *)v2 = 0;
        v12 = *(void **)(((unsigned __int64)&string & 0xFFFFFFFFFFFFFFE0uLL) + 8);
        if ( v12 )
          LocalFree(v12);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v2 + 16);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v2 + 24);
        result = 2147942405LL;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x598,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrtokenandshellhandler.cpp",
        (const char *)0x80A2030BLL,
        v16);
      if ( v4 )
        ReleaseSRWLockShared(v4);
      WindowsDeleteString(*(HSTRING *)v2);
      *(_QWORD *)v2 = 0;
      v7 = *(void **)(((unsigned __int64)&string & 0xFFFFFFFFFFFFFFE0uLL) + 8);
      if ( v7 )
        LocalFree(v7);
      v8 = *(char **)(((unsigned __int64)&string & 0xFFFFFFFFFFFFFFE0uLL) + 0x10);
      if ( (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(v8);
      v9 = *(_QWORD **)(((unsigned __int64)&string & 0xFFFFFFFFFFFFFFE0uLL) + 0x18);
      if ( v9 )
      {
        *(_QWORD *)(((unsigned __int64)&string & 0xFFFFFFFFFFFFFFE0uLL) + 0x18) = 0;
        (*(void (__fastcall **)(_QWORD *, _QWORD))(*v9 + 16LL))(v9, *v9);
      }
      result = 2158101259LL;
    }
  }
  catch ( ... )
  {
    *(_DWORD *)((unsigned __int64)&string & 0xFFFFFFFFFFFFFFE0uLL) = wil::details::in1diag3::Return_CaughtException(
                                                                       retaddr,
                                                                       (void *)0x5B3,
                                                                       (unsigned int)"onecore\\ds\\security\\umstartup\\u"
                                                                                     "sermgr\\lib\\usermgrtokenandshellhandler.cpp",
                                                                       v6);
    return *(unsigned int *)((unsigned __int64)&string & 0xFFFFFFFFFFFFFFE0uLL);
  }
  return result;
}

```

## disassembly

```asm
0x180008630  push    rbp
0x180008632  push    rbx
0x180008633  push    rsi
0x180008634  push    rdi
0x180008635  push    r14
0x180008637  push    r15
0x180008639  sub     rsp, 238h
0x180008640  lea     rbp, [rsp+40h]
0x180008645  and     rbp, 0FFFFFFFFFFFFFFE0h
0x180008649  mov     rax, cs:__security_cookie
0x180008650  xor     rax, rsp
0x180008653  mov     [rbp+220h+var_40], rax
0x18000865a  mov     r14, rdx
0x18000865d  xor     r15d, r15d
0x180008660  mov     [rbp+220h+var_208], r15
0x180008664  mov     [rbp+220h+hObject], r15
0x180008668  mov     [rbp+220h+hMem], r15
0x18000866c  mov     [rbp+220h+string], r15
0x180008670  xor     edx, edx; Val
0x180008672  mov     r8d, 1A0h; Size
0x180008678  lea     rcx, [rbp+220h+var_1E0]; void *
0x18000867c  call    memset_0
0x180008681  lea     rbx, SRWLock
0x180008688  mov     rcx, rbx; SRWLock
0x18000868b  call    cs:__imp_TryAcquireSRWLockShared
0x180008691  test    al, al
0x180008693  cmovz   rbx, r15
0x180008697  mov     [rbp+220h+var_200], rbx
0x18000869b  cmp     cs:qword_180148230, r15
0x1800086a2  jnz     loc_180008814
0x1800086a8  mov     rcx, [rsp+268h]; this
0x1800086b0  mov     r9d, 80A2030Bh; char *
0x1800086b6  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\umstartup\\userm"...
0x1800086bd  mov     edx, 598h; void *
0x1800086c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800086c7  nop
0x1800086c8  test    rbx, rbx
0x1800086cb  jz      short loc_1800086D7
0x1800086cd  mov     rcx, rbx; SRWLock
0x1800086d0  call    cs:__imp_ReleaseSRWLockShared
0x1800086d6  nop
0x1800086d7  mov     rcx, [rbp+220h+string]; string
0x1800086db  call    cs:__imp_WindowsDeleteString
0x1800086e1  mov     [rbp+220h+string], r15
0x1800086e5  mov     rcx, [rbp+220h+hMem]; hMem
0x1800086e9  test    rcx, rcx
0x1800086ec  jz      short loc_1800086F5
0x1800086ee  call    cs:__imp_LocalFree
0x1800086f4  nop
0x1800086f5  mov     rcx, [rbp+220h+hObject]; hObject
0x1800086f9  lea     rax, [rcx-1]
0x1800086fd  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180008701  jbe     loc_180008809
0x180008707  mov     rcx, [rbp+220h+var_208]
0x18000870b  test    rcx, rcx
0x18000870e  jz      short loc_180008721
0x180008710  mov     [rbp+220h+var_208], r15
0x180008714  mov     rdx, [rcx]
0x180008717  mov     rax, [rdx+10h]
0x18000871b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008720  nop
0x180008721  mov     eax, 80A2030Bh
0x180008726  mov     rcx, [rbp+220h+var_40]
0x18000872d  xor     rcx, rsp; StackCookie
0x180008730  call    __security_check_cookie
0x180008735  add     rsp, 238h
0x18000873c  pop     r15
0x18000873e  pop     r14
0x180008740  pop     rdi
0x180008741  pop     rsi
0x180008742  pop     rbx
0x180008743  pop     rbp
0x180008744  retn
0x180008745  lea     rcx, qword_180148230
0x18000874c  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180008751  mov     rax, cs:qword_180148230
0x180008758  mov     [r14], rax
0x18000875b  test    rbx, rbx
0x18000875e  jz      short loc_18000876A
0x180008760  mov     rcx, rbx; SRWLock
0x180008763  call    cs:__imp_ReleaseSRWLockShared
0x180008769  nop
0x18000876a  mov     rcx, [rbp+220h+string]; string
0x18000876e  call    cs:__imp_WindowsDeleteString
0x180008774  mov     [rbp+220h+string], r15
0x180008778  mov     rcx, [rbp+220h+hMem]; hMem
0x18000877c  test    rcx, rcx
0x18000877f  jz      short loc_180008788
0x180008781  call    cs:__imp_LocalFree
0x180008787  nop
0x180008788  lea     rcx, [rbp+220h+hObject]
0x18000878c  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180008791  nop
0x180008792  lea     rcx, [rbp+220h+var_208]
0x180008796  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18000879b  xor     eax, eax
0x18000879d  jmp     short loc_180008726
0x18000879f  mov     rcx, [rsp+268h]; this
0x1800087a7  mov     r9d, 80070005h; char *
0x1800087ad  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\umstartup\\userm"...
0x1800087b4  mov     edx, 5AFh; void *
0x1800087b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800087be  nop
0x1800087bf  test    rbx, rbx
0x1800087c2  jz      short loc_1800087CE
0x1800087c4  mov     rcx, rbx; SRWLock
0x1800087c7  call    cs:__imp_ReleaseSRWLockShared
0x1800087cd  nop
0x1800087ce  mov     rcx, [rbp+220h+string]; string
0x1800087d2  call    cs:__imp_WindowsDeleteString
0x1800087d8  mov     [rbp+220h+string], r15
0x1800087dc  mov     rcx, [rbp+220h+hMem]; hMem
0x1800087e0  test    rcx, rcx
0x1800087e3  jz      short loc_1800087EC
0x1800087e5  call    cs:__imp_LocalFree
0x1800087eb  nop
0x1800087ec  lea     rcx, [rbp+220h+hObject]
0x1800087f0  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800087f5  nop
0x1800087f6  lea     rcx, [rbp+220h+var_208]
0x1800087fa  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800087ff  mov     eax, 80070005h
0x180008804  jmp     loc_180008726
0x180008809  call    cs:__imp_CloseHandle
0x18000880f  jmp     loc_180008707
0x180008814  xor     edx, edx
0x180008816  lea     rcx, [rbp+220h+hObject]
0x18000881a  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18000881f  lea     rcx, [rbp+220h+hObject]; TokenHandle
0x180008823  call    ?GetCallerToken2@@YAJPEAPEAX@Z; GetCallerToken2(void * *)
0x180008828  xor     r8d, r8d; struct _EXTENDED_CALLER_INFORMATION *
0x18000882b  lea     rdx, [rbp+220h+var_1E0]; struct _BASIC_CALLER_INFORMATION *
0x18000882f  mov     rcx, [rbp+220h+hObject]; ClientToken
0x180008833  call    ?GetCallerInformationFromToken@@YAJPEAXPEAU_BASIC_CALLER_INFORMATION@@PEAU_EXTENDED_CALLER_INFORMATION@@@Z; GetCallerInformationFromToken(void *,_BASIC_CALLER_INFORMATION *,_EXTENDED_CALLER_INFORMATION *)
0x180008838  cmp     [rbp+220h+var_1DE], 0
0x18000883c  jz      short loc_180008848
0x18000883e  cmp     [rbp+220h+var_1E0], 0
0x180008842  jnz     loc_180008745
0x180008848  cmp     [rbp+220h+var_1DF], 0
0x18000884c  jz      short loc_180008858
0x18000884e  cmp     [rbp+220h+var_1D4], 0
0x180008852  jnz     loc_180008745
0x180008858  lea     rdx, [rbp+220h+var_208]
0x18000885c  lea     rcx, qword_180148230
0x180008863  call    ??$As@UIUserInternal@Implementation@Internal@System@Windows@@@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIUserInternal@Implementation@Internal@System@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::System::IUser>::As<Windows::System::Internal::Implementation::IUserInternal>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::Implementation::IUserInternal>>)
0x180008868  mov     rsi, [rbp+220h+var_208]
0x18000886c  mov     rax, [rsi]
0x18000886f  mov     rdi, [rax+48h]
0x180008873  mov     rcx, [rbp+220h+string]; string
0x180008877  call    cs:__imp_WindowsDeleteString
0x18000887d  mov     [rbp+220h+string], r15
0x180008881  lea     rdx, [rbp+220h+string]
0x180008885  mov     rcx, rsi
0x180008888  mov     rax, rdi
0x18000888b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008890  xor     edx, edx
0x180008892  lea     rcx, [rbp+220h+hMem]
0x180008896  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AJPEAX@Z$1?CamFreeBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18000889b  xor     edx, edx; length
0x18000889d  mov     rcx, [rbp+220h+string]; string
0x1800088a1  call    cs:__imp_WindowsGetStringRawBuffer
0x1800088a7  lea     rdx, [rbp+220h+hMem]; Sid
0x1800088ab  mov     rcx, rax; StringSid
0x1800088ae  call    cs:__imp_ConvertStringSidToSidW
0x1800088b4  test    eax, eax
0x1800088b6  jz      loc_18000879F
0x1800088bc  mov     rdx, [rbp+220h+hMem]; Sid2
0x1800088c0  mov     rcx, [rbp+220h+Sid1]; Sid1
0x1800088c7  call    cs:__imp_RtlEqualSid
0x1800088cd  test    al, al
0x1800088cf  jz      loc_18000879F
0x1800088d5  jmp     loc_180008745
0x1800088da  mov     eax, dword ptr [rbp+220h+string]
0x1800088dd  jmp     loc_180008726
```
