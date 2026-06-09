# CInstClassFactory::Init(void)

- ea: `0x18001faa8`
- end: `0x18001fb81`
- name: `?Init@CInstClassFactory@@QEAAJXZ`
- size: `217`
- prototype: `__int64 __fastcall(CInstClassFactory *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001f650`

## callees

- `0x180005540`
- `0x180005560`
- `0x180008320`
- `0x18000bf78`
- `0x18001faa8`

## import_xrefs

- `SHLWAPI!__imp_SHStringFromGUIDW` at `0x18001fad9`
- `SHLWAPI!__imp_SHStringFromGUIDW` at `0x18001fad9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001fb1a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001fb1a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001fb4e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001fb4e`

## string_xrefs

- `0x18001fae9`: `CLSID\%s\Instance`

## pseudocode

```c
LSTATUS __fastcall CInstClassFactory::Init(CInstClassFactory *this)
{
  LSTATUS result; // eax
  HKEY *phkResult; // rbx
  HKEY v4; // rdi
  _BYTE v5[16]; // [rsp+30h] [rbp-278h] BYREF
  _BYTE v6[80]; // [rsp+40h] [rbp-268h] BYREF
  WCHAR SubKey[256]; // [rsp+90h] [rbp-218h] BYREF

  SHStringFromGUIDW((char *)this + 40, v6, 39);
  result = StringCchPrintfW(SubKey, 0xFFu, L"CLSID\\%s\\Instance", v6);
  if ( result >= 0 )
  {
    phkResult = (HKEY *)((char *)this + 32);
    v4 = *phkResult;
    if ( *phkResult )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)v5);
      RegCloseKey(v4);
      wil::last_error_context::~last_error_context((wil::last_error_context *)v5);
    }
    *phkResult = 0;
    result = RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0x20019u, phkResult);
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18001faa8  mov     [rsp+arg_8], rbx
0x18001faad  push    rdi
0x18001faae  sub     rsp, 2A0h
0x18001fab5  mov     rax, cs:__security_cookie
0x18001fabc  xor     rax, rsp
0x18001fabf  mov     [rsp+2A8h+var_18], rax
0x18001fac7  mov     rbx, rcx
0x18001faca  lea     rdx, [rsp+2A8h+var_268]
0x18001facf  add     rcx, 28h ; '('
0x18001fad3  mov     r8d, 27h ; '''
0x18001fad9  call    cs:__imp_SHStringFromGUIDW
0x18001fadf  lea     r9, [rsp+2A8h+var_268]
0x18001fae4  mov     edx, 0FFh; unsigned __int64
0x18001fae9  lea     r8, aClsidSInstance; "CLSID\\%s\\Instance"
0x18001faf0  lea     rcx, [rsp+2A8h+SubKey]; unsigned __int16 *
0x18001faf8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001fafd  test    eax, eax
0x18001faff  js      short loc_18001FB60
0x18001fb01  add     rbx, 20h ; ' '
0x18001fb05  mov     rdi, [rbx]
0x18001fb08  test    rdi, rdi
0x18001fb0b  jz      short loc_18001FB2A
0x18001fb0d  lea     rcx, [rsp+2A8h+var_278]; this
0x18001fb12  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001fb17  mov     rcx, rdi; hKey
0x18001fb1a  call    cs:__imp_RegCloseKey
0x18001fb20  lea     rcx, [rsp+2A8h+var_278]; this
0x18001fb25  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001fb2a  mov     r9d, 20019h; samDesired
0x18001fb30  mov     qword ptr [rbx], 0
0x18001fb37  xor     r8d, r8d; ulOptions
0x18001fb3a  mov     [rsp+2A8h+phkResult], rbx; phkResult
0x18001fb3f  lea     rdx, [rsp+2A8h+SubKey]; lpSubKey
0x18001fb47  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18001fb4e  call    cs:__imp_RegOpenKeyExW
0x18001fb54  test    eax, eax
0x18001fb56  jle     short loc_18001FB60
0x18001fb58  movzx   eax, ax
0x18001fb5b  or      eax, 80070000h
0x18001fb60  mov     rcx, [rsp+2A8h+var_18]
0x18001fb68  xor     rcx, rsp; StackCookie
0x18001fb6b  call    __security_check_cookie
0x18001fb70  mov     rbx, [rsp+2A8h+arg_8]
0x18001fb78  add     rsp, 2A0h
0x18001fb7f  pop     rdi
0x18001fb80  retn
```
