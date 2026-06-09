# CPolicyDisableList::Init(void)

- ea: `0x1800e7334`
- end: `0x1800e74bd`
- name: `?Init@CPolicyDisableList@@QEAAJXZ`
- size: `393`
- prototype: `__int64 __fastcall(CPolicyDisableList *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800e6e4c`
- `0x1801944c4`

## callees

- `0x1800e7334`
- `0x1801710e4`
- `0x180188d90`
- `0x18018e778`
- `0x1801b9afc`
- `0x1801b9c34`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800e744d`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800e744d`
- `api-ms-win-core-com-l1-1-0!CLSIDFromProgID` at `0x1800e7461`
- `api-ms-win-core-com-l1-1-0!CLSIDFromProgID` at `0x1800e7461`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800e73d6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800e73d6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e749a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e749a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800e7412`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800e7412`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800e737b`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800e737b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPolicyDisableList::Init(CPolicyDisableList *this)
{
  HKEY *phkResult; // rbx
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8
  const wchar_t *v6; // rcx
  bool v7; // al
  wchar_t *v8; // rdx
  LSTATUS v9; // eax
  unsigned int v10; // ebx
  GUID *v11; // rax
  GUID *v12; // rdi
  HRESULT v13; // eax
  BYTE Data[4]; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  struct CSearchRegistryRedirectHelper *v18; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t v19[264]; // [rsp+50h] [rbp-B0h] BYREF

  hKey = 0;
  phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
  v18 = 0;
  v7 = (unsigned __int8)RtlIsStateSeparationEnabled(v4, v3, v5)
    && GetSearchRegistryRedirect(v6, &v18)
    && (int)CSearchRegistryRedirectHelper::MapRegistryKeyPath(
              (const wchar_t *)v18,
              L"SOFTWARE\\Policies\\Microsoft\\Windows\\Windows Search",
              v19) >= 0;
  v8 = v19;
  if ( !v7 )
    v8 = (wchar_t *)L"SOFTWARE\\Policies\\Microsoft\\Windows\\Windows Search";
  RegOpenKeyExW(HKEY_LOCAL_MACHINE, v8, 0, 0x20019u, phkResult);
  cbData = 4;
  *(_DWORD *)Data = 0;
  v9 = RegQueryValueExW(hKey, L"AllowOCR", 0, 0, Data, &cbData);
  v10 = v9;
  if ( v9 )
  {
    if ( v9 > 0 )
      v10 = (unsigned __int16)v9 | 0x80070000;
  }
  else if ( *(_DWORD *)Data )
  {
    if ( *(_DWORD *)Data == 1 )
      *((_DWORD *)this + 3) = 1;
  }
  else
  {
    v11 = (GUID *)operator new[](0x10u, (const struct std::nothrow_t *)&std::nothrow);
    v12 = v11;
    if ( v11 )
    {
      *v11 = 0;
      v13 = CLSIDFromString(L"{4D144E38-5812-4F6D-A82A-C60A8F7E68D6}", v11);
      if ( v13 < 0 )
        v13 = CLSIDFromProgID(L"{4D144E38-5812-4F6D-A82A-C60A8F7E68D6}", v12);
      *((_DWORD *)this + 2) = v13 >= 0;
      *(_QWORD *)this = v12;
    }
    else
    {
      v10 = -2147024888;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v10;
}

```

## disassembly

```asm
0x1800e7334  push    rbp
0x1800e7336  push    rbx
0x1800e7337  push    rsi
0x1800e7338  push    rdi
0x1800e7339  lea     rbp, [rsp-178h]
0x1800e7341  sub     rsp, 278h
0x1800e7348  mov     rax, cs:__security_cookie
0x1800e734f  xor     rax, rsp
0x1800e7352  mov     [rbp+190h+var_30], rax
0x1800e7359  mov     rsi, rcx
0x1800e735c  mov     [rsp+290h+hKey], 0
0x1800e7365  lea     rcx, [rsp+290h+hKey]
0x1800e736a  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1800e736f  mov     rbx, rax
0x1800e7372  mov     [rsp+290h+var_250], 0
0x1800e737b  call    cs:__imp_RtlIsStateSeparationEnabled
0x1800e7381  lea     rdi, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x1800e7388  test    al, al
0x1800e738a  jz      short loc_1800E73B4
0x1800e738c  lea     rdx, [rsp+290h+var_250]; struct CSearchRegistryRedirectHelper **
0x1800e7391  call    ?GetSearchRegistryRedirect@@YA_NPEB_WPEAPEAVCSearchRegistryRedirectHelper@@@Z; GetSearchRegistryRedirect(wchar_t const *,CSearchRegistryRedirectHelper * *)
0x1800e7396  test    al, al
0x1800e7398  jz      short loc_1800E73B4
0x1800e739a  lea     r8, [rsp+290h+var_240]; wchar_t *
0x1800e739f  mov     rdx, rdi; wchar_t *
0x1800e73a2  mov     rcx, [rsp+290h+var_250]; this
0x1800e73a7  call    ?MapRegistryKeyPath@CSearchRegistryRedirectHelper@@QEAAJPEB_WPEA_WK@Z; CSearchRegistryRedirectHelper::MapRegistryKeyPath(wchar_t const *,wchar_t *,ulong)
0x1800e73ac  test    eax, eax
0x1800e73ae  js      short loc_1800E73B4
0x1800e73b0  mov     al, 1
0x1800e73b2  jmp     short loc_1800E73B6
0x1800e73b4  xor     al, al
0x1800e73b6  lea     rdx, [rsp+290h+var_240]
0x1800e73bb  test    al, al
0x1800e73bd  cmovz   rdx, rdi; lpSubKey
0x1800e73c1  mov     [rsp+290h+phkResult], rbx; phkResult
0x1800e73c6  mov     r9d, 20019h; samDesired
0x1800e73cc  xor     r8d, r8d; ulOptions
0x1800e73cf  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800e73d6  call    cs:__imp_RegOpenKeyExW
0x1800e73dc  mov     [rsp+290h+cbData], 4
0x1800e73e4  mov     dword ptr [rsp+290h+Data], 0
0x1800e73ec  lea     rax, [rsp+290h+cbData]
0x1800e73f1  mov     [rsp+290h+lpcbData], rax; lpcbData
0x1800e73f6  lea     rax, [rsp+290h+Data]
0x1800e73fb  mov     [rsp+290h+phkResult], rax; lpData
0x1800e7400  xor     r9d, r9d; lpType
0x1800e7403  xor     r8d, r8d; lpReserved
0x1800e7406  lea     rdx, aAllowocr; "AllowOCR"
0x1800e740d  mov     rcx, [rsp+290h+hKey]; hKey
0x1800e7412  call    cs:__imp_RegQueryValueExW
0x1800e7418  mov     ebx, eax
0x1800e741a  test    eax, eax
0x1800e741c  jnz     short loc_1800E7485
0x1800e741e  mov     eax, dword ptr [rsp+290h+Data]
0x1800e7422  test    eax, eax
0x1800e7424  jnz     short loc_1800E747B
0x1800e7426  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800e742d  lea     ecx, [rbx+10h]; unsigned __int64
0x1800e7430  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800e7435  mov     rdi, rax
0x1800e7438  test    rax, rax
0x1800e743b  jz      short loc_1800E7474
0x1800e743d  xorps   xmm0, xmm0
0x1800e7440  movups  xmmword ptr [rax], xmm0
0x1800e7443  mov     rdx, rax; pclsid
0x1800e7446  lea     rcx, szProgID; "{4D144E38-5812-4F6D-A82A-C60A8F7E68D6}"
0x1800e744d  call    cs:__imp_CLSIDFromString
0x1800e7453  test    eax, eax
0x1800e7455  jns     short loc_1800E7467
0x1800e7457  mov     rdx, rdi; lpclsid
0x1800e745a  lea     rcx, szProgID; "{4D144E38-5812-4F6D-A82A-C60A8F7E68D6}"
0x1800e7461  call    cs:__imp_CLSIDFromProgID
0x1800e7467  not     eax
0x1800e7469  shr     eax, 1Fh
0x1800e746c  mov     [rsi+8], eax
0x1800e746f  mov     [rsi], rdi
0x1800e7472  jmp     short loc_1800E7490
0x1800e7474  mov     ebx, 80070008h
0x1800e7479  jmp     short loc_1800E7490
0x1800e747b  cmp     eax, 1
0x1800e747e  jnz     short loc_1800E7490
0x1800e7480  mov     [rsi+0Ch], eax
0x1800e7483  jmp     short loc_1800E7490
0x1800e7485  jle     short loc_1800E7490
0x1800e7487  movzx   ebx, ax
0x1800e748a  or      ebx, 80070000h
0x1800e7490  mov     rcx, [rsp+290h+hKey]; hKey
0x1800e7495  test    rcx, rcx
0x1800e7498  jz      short loc_1800E74A0
0x1800e749a  call    cs:__imp_RegCloseKey
0x1800e74a0  mov     eax, ebx
0x1800e74a2  mov     rcx, [rbp+190h+var_30]
0x1800e74a9  xor     rcx, rsp; StackCookie
0x1800e74ac  call    __security_check_cookie
0x1800e74b1  add     rsp, 278h
0x1800e74b8  pop     rdi
0x1800e74b9  pop     rsi
0x1800e74ba  pop     rbx
0x1800e74bb  pop     rbp
0x1800e74bc  retn
```
