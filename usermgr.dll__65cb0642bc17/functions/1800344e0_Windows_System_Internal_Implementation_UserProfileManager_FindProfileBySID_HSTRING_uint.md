# Windows::System::Internal::Implementation::UserProfileManager::FindProfileBySID(HSTRING__ *,uint *)

- ea: `0x1800344e0`
- end: `0x1800346b2`
- name: `?FindProfileBySID@UserProfileManager@Implementation@Internal@System@Windows@@UEAAJPEAUHSTRING__@@PEAI@Z`
- size: `466`
- prototype: `int(Windows::System::Internal::Implementation::UserProfileManager *__hidden this, HSTRING, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x1800088e8`
- `0x18000ce48`
- `0x180025cd4`
- `0x1800344e0`
- `0x1800346b8`
- `0x1800ec010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18003459e`
- `msvcrt!_wcsicmp` at `0x18003459e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180034637`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180034637`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180034510`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180034510`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180034584`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180034592`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180034584`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180034592`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180034555`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800345c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180034629`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180034692`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180034555`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800345c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180034629`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180034692`

## string_xrefs

- `0x18003467e`: `onecore\ds\security\umstartup\usermgr\lib\knownusermanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::System::Internal::Implementation::UserProfileManager::FindProfileBySID(
        Windows::System::Internal::Implementation::UserProfileManager *this,
        HSTRING a2,
        unsigned int *a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // r14
  __int64 *v7; // rbx
  int v8; // eax
  unsigned int v9; // edi
  __int64 v10; // rsi
  __int64 (__fastcall *v11)(__int64, HSTRING *); // rdi
  const wchar_t *StringRawBuffer; // rdi
  const wchar_t *v13; // rax
  __int64 v14; // rcx
  __int64 *i; // rax
  __int64 *v16; // rcx
  __int64 v17; // rcx
  __int64 v19; // rdx
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+38h]
  HSTRING string; // [rsp+60h] [rbp+40h] BYREF
  __int64 v23; // [rsp+70h] [rbp+50h] BYREF
  struct _RTL_CRITICAL_SECTION *v24; // [rsp+78h] [rbp+58h] BYREF

  v23 = 0;
  *a3 = 0;
  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 64);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  v24 = v6;
  v7 = (__int64 *)**((_QWORD **)this + 13);
  while ( 1 )
  {
    if ( v7 == *((__int64 **)this + 13) )
      goto LABEL_19;
    string = 0;
    v8 = Microsoft::WRL::ComPtr<Windows::System::Internal::IUserProfile>::As<Windows::System::Internal::IUserProfile2>(
           (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))v7 + 5,
           (__int64)&v23);
    v9 = v8;
    if ( v8 < 0 )
    {
      v19 = 376;
      goto LABEL_26;
    }
    v10 = v23;
    v11 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v23 + 56LL);
    WindowsDeleteString(string);
    string = 0;
    v8 = v11(v10, &string);
    v9 = v8;
    if ( v8 < 0 )
    {
      v19 = 377;
LABEL_26:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\knownusermanager.cpp",
        (const char *)(unsigned int)v8,
        savedregs);
      WindowsDeleteString(string);
      string = 0;
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v24);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
      return v9;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v13 = WindowsGetStringRawBuffer(a2, 0);
    if ( !_wcsicmp(v13, StringRawBuffer) )
      break;
    v14 = v23;
    if ( v23 )
    {
      v23 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    WindowsDeleteString(string);
    if ( !*((_BYTE *)v7 + 25) )
    {
      i = (__int64 *)v7[2];
      if ( *((_BYTE *)i + 25) )
      {
        for ( i = (__int64 *)v7[1]; !*((_BYTE *)i + 25) && v7 == (__int64 *)i[2]; i = (__int64 *)i[1] )
          v7 = i;
LABEL_17:
        v7 = i;
      }
      else
      {
        v16 = (__int64 *)*i;
        if ( *(_BYTE *)(*i + 25) )
          goto LABEL_17;
        do
        {
          v7 = v16;
          v16 = (__int64 *)*v16;
        }
        while ( !*((_BYTE *)v16 + 25) );
      }
    }
  }
  *a3 = *((_DWORD *)v7 + 8);
  WindowsDeleteString(string);
LABEL_19:
  if ( v6 )
    LeaveCriticalSection(v6);
  v17 = v23;
  if ( v23 )
  {
    v23 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  }
  return 0;
}

```

## disassembly

```asm
0x1800344e0  mov     [rsp-38h+arg_8], rbx
0x1800344e5  push    rbp
0x1800344e6  push    rsi
0x1800344e7  push    rdi
0x1800344e8  push    r12
0x1800344ea  push    r13
0x1800344ec  push    r14
0x1800344ee  push    r15; int
0x1800344f0  mov     rbp, rsp
0x1800344f3  sub     rsp, 20h
0x1800344f7  mov     r12, r8
0x1800344fa  mov     r13, rdx
0x1800344fd  mov     r15, rcx
0x180034500  xor     esi, esi
0x180034502  mov     [rbp+arg_10], rsi
0x180034506  mov     [r8], esi
0x180034509  lea     r14, [rcx+40h]
0x18003450d  mov     rcx, r14; lpCriticalSection
0x180034510  call    cs:__imp_EnterCriticalSection
0x180034516  mov     [rbp+arg_18], r14
0x18003451a  mov     rbx, [r15+68h]
0x18003451e  mov     rbx, [rbx]
0x180034521  cmp     rbx, [r15+68h]
0x180034525  jz      loc_18003462F
0x18003452b  mov     [rbp+string], rsi
0x18003452f  lea     rcx, [rbx+28h]
0x180034533  lea     rdx, [rbp+arg_10]
0x180034537  call    ??$As@UIUserProfile2@Internal@System@Windows@@@?$ComPtr@UIUserProfile@Internal@System@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIUserProfile2@Internal@System@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::System::Internal::IUserProfile>::As<Windows::System::Internal::IUserProfile2>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::IUserProfile2>>)
0x18003453c  mov     edi, eax
0x18003453e  test    eax, eax
0x180034540  js      loc_180034676
0x180034546  mov     rsi, [rbp+arg_10]
0x18003454a  mov     rax, [rsi]
0x18003454d  mov     rdi, [rax+38h]
0x180034551  mov     rcx, [rbp+string]; string
0x180034555  call    cs:__imp_WindowsDeleteString
0x18003455b  mov     [rbp+string], 0
0x180034563  lea     rdx, [rbp+string]
0x180034567  mov     rcx, rsi
0x18003456a  mov     rax, rdi
0x18003456d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034572  mov     edi, eax
0x180034574  xor     esi, esi
0x180034576  test    eax, eax
0x180034578  js      loc_18003466F
0x18003457e  xor     edx, edx; length
0x180034580  mov     rcx, [rbp+string]; string
0x180034584  call    cs:__imp_WindowsGetStringRawBuffer
0x18003458a  mov     rdi, rax
0x18003458d  xor     edx, edx; length
0x18003458f  mov     rcx, r13; string
0x180034592  call    cs:__imp_WindowsGetStringRawBuffer
0x180034598  mov     rdx, rdi; String2
0x18003459b  mov     rcx, rax; String1
0x18003459e  call    cs:__imp__wcsicmp
0x1800345a4  test    eax, eax
0x1800345a6  jz      short loc_18003461E
0x1800345a8  mov     rcx, [rbp+arg_10]
0x1800345ac  test    rcx, rcx
0x1800345af  jz      short loc_1800345C2
0x1800345b1  mov     [rbp+arg_10], rsi
0x1800345b5  mov     rax, [rcx]
0x1800345b8  mov     rax, [rax+10h]
0x1800345bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800345c1  nop
0x1800345c2  mov     rcx, [rbp+string]; string
0x1800345c6  call    cs:__imp_WindowsDeleteString
0x1800345cc  cmp     [rbx+19h], sil
0x1800345d0  jnz     loc_180034521
0x1800345d6  mov     rax, [rbx+10h]
0x1800345da  cmp     [rax+19h], sil
0x1800345de  jnz     short loc_1800345FD
0x1800345e0  mov     rcx, [rax]
0x1800345e3  cmp     [rcx+19h], sil
0x1800345e7  jnz     short loc_180034616
0x1800345e9  mov     rbx, rcx
0x1800345ec  mov     rax, [rcx]
0x1800345ef  mov     rcx, rax
0x1800345f2  cmp     [rax+19h], sil
0x1800345f6  jz      short loc_1800345E9
0x1800345f8  jmp     loc_180034521
0x1800345fd  mov     rax, [rbx+8]
0x180034601  jmp     short loc_180034610
0x180034603  cmp     rbx, [rax+10h]
0x180034607  jnz     short loc_180034616
0x180034609  mov     rbx, rax
0x18003460c  mov     rax, [rax+8]
0x180034610  cmp     [rax+19h], sil
0x180034614  jz      short loc_180034603
0x180034616  mov     rbx, rax
0x180034619  jmp     loc_180034521
0x18003461e  mov     eax, [rbx+20h]
0x180034621  mov     [r12], eax
0x180034625  mov     rcx, [rbp+string]; string
0x180034629  call    cs:__imp_WindowsDeleteString
0x18003462f  test    r14, r14
0x180034632  jz      short loc_18003463E
0x180034634  mov     rcx, r14; lpCriticalSection
0x180034637  call    cs:__imp_LeaveCriticalSection
0x18003463d  nop
0x18003463e  mov     rcx, [rbp+arg_10]
0x180034642  test    rcx, rcx
0x180034645  jz      short loc_180034658
0x180034647  mov     [rbp+arg_10], rsi
0x18003464b  mov     rax, [rcx]
0x18003464e  mov     rax, [rax+10h]
0x180034652  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034657  nop
0x180034658  xor     eax, eax
0x18003465a  mov     rbx, [rsp+20h+arg_8]
0x18003465f  add     rsp, 20h
0x180034663  pop     r15
0x180034665  pop     r14
0x180034667  pop     r13
0x180034669  pop     r12
0x18003466b  pop     rdi
0x18003466c  pop     rsi
0x18003466d  pop     rbp
0x18003466e  retn
0x18003466f  mov     edx, 179h
0x180034674  jmp     short loc_18003467B
0x180034676  mov     edx, 178h; void *
0x18003467b  mov     r9d, eax; char *
0x18003467e  lea     r8, aOnecoreDsSecur_60; "onecore\\ds\\security\\umstartup\\userm"...
0x180034685  mov     rcx, [rbp+38h]; this
0x180034689  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003468e  mov     rcx, [rbp+string]; string
0x180034692  call    cs:__imp_WindowsDeleteString
0x180034698  mov     [rbp+string], rsi
0x18003469c  lea     rcx, [rbp+arg_18]
0x1800346a0  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x1800346a5  lea     rcx, [rbp+arg_10]
0x1800346a9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800346ae  mov     eax, edi
0x1800346b0  jmp     short loc_18003465A
```
