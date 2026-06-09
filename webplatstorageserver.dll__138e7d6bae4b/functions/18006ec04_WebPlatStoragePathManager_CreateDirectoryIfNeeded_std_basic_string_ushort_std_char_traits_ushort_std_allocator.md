# WebPlatStoragePathManager::CreateDirectoryIfNeeded(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,bool)

- ea: `0x18006ec04`
- end: `0x18006ed0c`
- name: `?CreateDirectoryIfNeeded@WebPlatStoragePathManager@@CAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z`
- size: `264`
- prototype: `int __fastcall(_QWORD *pszPath, char)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800376e0`
- `0x18005b970`

## callees

- `0x18001c800`
- `0x18003ccf8`
- `0x180066010`
- `0x18006ec04`
- `0x18006ed14`
- `0x18006eda4`
- `0x180080fb0`

## import_xrefs

- `api-ms-win-shell-shellfolders-l1-1-0!SHCreateDirectoryExW` at `0x18006ec37`
- `api-ms-win-shell-shellfolders-l1-1-0!SHCreateDirectoryExW` at `0x18006ec37`
- `ext-ms-win-security-efswrt-l1-1-1!ProtectFileToEnterpriseIdentity` at `0x18006ecbb`
- `ext-ms-win-security-efswrt-l1-1-1!ProtectFileToEnterpriseIdentity` at `0x18006ecbb`

## string_xrefs

- `0x18006ec6b`: `onecoreuap\inetcore\webplatstorageserver\clientmanager\webplatstoragepathmanager.cxx`
- `0x18006eccd`: `onecoreuap\inetcore\webplatstorageserver\clientmanager\webplatstoragepathmanager.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
int __fastcall WebPlatStoragePathManager::CreateDirectoryIfNeeded(_QWORD *pszPath, char a2)
{
  _QWORD *v3; // rbx
  const WCHAR *v4; // rdx
  int result; // eax
  _QWORD *v6; // rdx
  int v7; // eax
  void *TokenHandle; // [rsp+20h] [rbp-38h] BYREF
  _QWORD v9[4]; // [rsp+28h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v3 = pszPath;
  if ( pszPath[3] <= 7u )
    v4 = (const WCHAR *)pszPath;
  else
    v4 = (const WCHAR *)*pszPath;
  result = SHCreateDirectoryExW(0, v4, 0);
  if ( result > 0 )
    result = (unsigned __int16)result | 0x80070000;
  if ( result != -2147024713 && result != -2147024816 )
  {
    if ( result < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE3,
        (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\clientmanager\\webplatstoragepathmanager.cxx",
        (const char *)(unsigned int)result,
        (int)TokenHandle);
    if ( a2 )
    {
      WebPlatStoragePathManager::GetCallerThreadToken(&TokenHandle);
      WebPlatStoragePathManager::SrpGetEnterpriseIdsHelper(v9, TokenHandle);
      v6 = v9;
      if ( v9[3] > 7u )
        v6 = (_QWORD *)v9[0];
      if ( v3[3] > 7u )
        v3 = (_QWORD *)*v3;
      v7 = ProtectFileToEnterpriseIdentity(v3, v6);
      if ( v7 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xE9,
          (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\clientmanager\\webplatstoragepathmanager.cxx",
          (const char *)(unsigned int)v7,
          (int)TokenHandle);
      std::wstring::~wstring(v9);
      return wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18006ec04  mov     [rsp+arg_8], rbx
0x18006ec09  push    rdi
0x18006ec0a  sub     rsp, 50h
0x18006ec0e  mov     rax, cs:__security_cookie
0x18006ec15  xor     rax, rsp
0x18006ec18  mov     [rsp+58h+var_10], rax
0x18006ec1d  mov     dil, dl
0x18006ec20  mov     rbx, rcx
0x18006ec23  cmp     qword ptr [rcx+18h], 7
0x18006ec28  jbe     short loc_18006EC2F
0x18006ec2a  mov     rdx, [rcx]
0x18006ec2d  jmp     short loc_18006EC32
0x18006ec2f  mov     rdx, rbx; pszPath
0x18006ec32  xor     r8d, r8d; psa
0x18006ec35  xor     ecx, ecx; hwnd
0x18006ec37  call    cs:__imp_SHCreateDirectoryExW
0x18006ec3d  test    eax, eax
0x18006ec3f  jle     short loc_18006EC49
0x18006ec41  movzx   eax, ax
0x18006ec44  or      eax, 80070000h
0x18006ec49  cmp     eax, 800700B7h
0x18006ec4e  jz      loc_18006ECF4
0x18006ec54  cmp     eax, 80070050h
0x18006ec59  jz      loc_18006ECF4
0x18006ec5f  mov     rcx, [rsp+58h]; this
0x18006ec64  test    eax, eax
0x18006ec66  jns     short loc_18006EC7D
0x18006ec68  mov     r9d, eax; char *
0x18006ec6b  lea     r8, aOnecoreuapInet_31; "onecoreuap\\inetcore\\webplatstorageser"...
0x18006ec72  mov     edx, 0E3h; void *
0x18006ec77  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006ec7d  test    dil, dil
0x18006ec80  jz      short loc_18006ECF4
0x18006ec82  lea     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x18006ec87  call    ?GetCallerThreadToken@WebPlatStoragePathManager@@CA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; WebPlatStoragePathManager::GetCallerThreadToken(void)
0x18006ec8c  nop
0x18006ec8d  mov     rdx, [rsp+58h+TokenHandle]
0x18006ec92  lea     rcx, [rsp+58h+var_30]
0x18006ec97  call    ?SrpGetEnterpriseIdsHelper@WebPlatStoragePathManager@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; WebPlatStoragePathManager::SrpGetEnterpriseIdsHelper(void *)
0x18006ec9c  nop
0x18006ec9d  lea     rdx, [rsp+58h+var_30]
0x18006eca2  cmp     [rsp+58h+var_18], 7
0x18006eca8  cmova   rdx, [rsp+58h+var_30]
0x18006ecae  cmp     qword ptr [rbx+18h], 7
0x18006ecb3  jbe     short loc_18006ECB8
0x18006ecb5  mov     rbx, [rbx]
0x18006ecb8  mov     rcx, rbx
0x18006ecbb  call    cs:__imp_ProtectFileToEnterpriseIdentity
0x18006ecc1  mov     rcx, [rsp+58h]; this
0x18006ecc6  test    eax, eax
0x18006ecc8  jns     short loc_18006ECDF
0x18006ecca  mov     r9d, eax; char *
0x18006eccd  lea     r8, aOnecoreuapInet_31; "onecoreuap\\inetcore\\webplatstorageser"...
0x18006ecd4  mov     edx, 0E9h; void *
0x18006ecd9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006ecdf  lea     rcx, [rsp+58h+var_30]; void *
0x18006ece4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006ece9  nop
0x18006ecea  lea     rcx, [rsp+58h+TokenHandle]
0x18006ecef  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18006ecf4  mov     rcx, [rsp+58h+var_10]
0x18006ecf9  xor     rcx, rsp; StackCookie
0x18006ecfc  call    __security_check_cookie
0x18006ed01  mov     rbx, [rsp+58h+arg_8]
0x18006ed06  add     rsp, 50h
0x18006ed0a  pop     rdi
0x18006ed0b  retn
```
