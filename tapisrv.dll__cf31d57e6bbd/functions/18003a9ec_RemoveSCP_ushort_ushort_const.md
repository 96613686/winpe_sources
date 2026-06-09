# RemoveSCP(ushort *,ushort const *)

- ea: `0x18003a9ec`
- end: `0x18003ac21`
- name: `?RemoveSCP@@YAJPEAGPEBG@Z`
- size: `565`
- prototype: `__int64 __fastcall(unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180032ad0`
- `0x18003a938`

## callees

- `0x180001600`
- `0x18001c740`
- `0x18001c854`
- `0x180039080`
- `0x1800390e4`
- `0x18003a9ec`
- `0x18003ad1c`
- `0x18003dc84`
- `0x180040010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003ab8f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003ab8f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ab9a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ab9a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ab7d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ab7d`
- `KERNEL32!GetLastError` at `0x18003aaa7`
- `KERNEL32!GetLastError` at `0x18003aaa7`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18003abf3`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18003abf3`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18003aa58`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18003aa58`
- `ACTIVEDS!__imp_ADsGetObject` at `0x18003ab0b`
- `ACTIVEDS!__imp_ADsGetObject` at `0x18003ab0b`
- `Secur32!GetComputerObjectNameW` at `0x18003aa9d`
- `Secur32!GetComputerObjectNameW` at `0x18003aa9d`

## string_xrefs

- `0x18003aba5`: `RegOpenKeyEx failed, error 0x%x`
- `0x18003abbe`: `Failed (%x) to bind Computer Object.`
- `0x18003ab38`: `Failed (%x) to Delete Tapisrv Object.`
- `0x18003aa3e`: `RemoveSCP %S %S`

## pseudocode

```c
__int64 __fastcall RemoveSCP(unsigned __int16 *a1, const unsigned __int16 *a2)
{
  int v4; // edi
  int v5; // r14d
  int Object; // ebx
  int v7; // edx
  __int64 v8; // rcx
  unsigned int v9; // r11d
  int v10; // eax
  LSTATUS v11; // eax
  ULONG nSize; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  void *ppObject; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR NameBuffer[264]; // [rsp+260h] [rbp+160h] BYREF

  nSize = 0;
  hKey = 0;
  ppObject = 0;
  v4 = 0;
  v5 = 0;
  TRACELogPrint(524290, "RemoveSCP %S %S", a1, a2);
  Object = CoInitializeEx(0, 0);
  if ( Object >= 0 )
  {
    v4 = 1;
    if ( (unsigned int)IsCurrentLocalSystem() )
    {
      Object = ImpersonateLocalSystem(v8, v7);
      if ( Object )
        goto LABEL_18;
      v5 = 1;
    }
    nSize = 260;
    if ( !GetComputerObjectNameW(NameFullyQualifiedDN, NameBuffer, &nSize) )
      goto LABEL_6;
    Object = StringCbCopyW(pszDest, 0x208u, L"LDAP://");
    if ( Object < 0
      || (Object = StringCbCatW(pszDest, v9, NameBuffer), Object < 0)
      || (Object = ADsGetObject(pszDest, &IID_IDirectoryObject, &ppObject), Object < 0) )
    {
      TRACELogPrint(65538, "Failed (%x) to bind Computer Object.", Object);
    }
    else
    {
      v10 = (*(__int64 (__fastcall **)(void *, unsigned __int16 *))(*(_QWORD *)ppObject + 56LL))(ppObject, a1);
      Object = v10;
      if ( v10 >= 0 )
      {
        if ( a2 )
        {
          v11 = RegOpenKeyExW(
                  HKEY_LOCAL_MACHINE,
                  L"Software\\Microsoft\\Windows\\CurrentVersion\\Telephony",
                  0,
                  0x20007u,
                  &hKey);
          if ( v11 )
          {
            TRACELogPrint(65538, "RegOpenKeyEx failed, error 0x%x", v11);
LABEL_6:
            Object = GetLastError() | 0x10000000;
            goto LABEL_18;
          }
          RegDeleteValueW(hKey, a2);
          RegCloseKey(hKey);
        }
      }
      else
      {
        TRACELogPrint(65538, "Failed (%x) to Delete Tapisrv Object.", v10);
        if ( (_WORD)Object == 8240 )
          Object = -23;
      }
    }
  }
LABEL_18:
  if ( ppObject )
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppObject + 16LL))(ppObject);
  if ( v5 )
    RevertLocalSystemImp();
  if ( v4 )
    CoUninitialize();
  return (unsigned int)Object;
}

```

## disassembly

```asm
0x18003a9ec  mov     [rsp-8+arg_10], rbx
0x18003a9f1  push    rbp
0x18003a9f2  push    rsi
0x18003a9f3  push    rdi
0x18003a9f4  push    r14
0x18003a9f6  push    r15
0x18003a9f8  lea     rbp, [rsp-380h]
0x18003aa00  sub     rsp, 480h
0x18003aa07  mov     rax, cs:__security_cookie
0x18003aa0e  xor     rax, rsp
0x18003aa11  mov     [rbp+3A0h+var_30], rax
0x18003aa18  mov     rsi, rdx
0x18003aa1b  mov     [rsp+4A0h+nSize], 0
0x18003aa23  mov     r15, rcx
0x18003aa26  mov     [rsp+4A0h+hKey], 0
0x18003aa2f  mov     r9, rdx
0x18003aa32  mov     [rsp+4A0h+ppObject], 0
0x18003aa3b  mov     r8, rcx
0x18003aa3e  lea     rdx, aRemovescpSS; "RemoveSCP %S %S"
0x18003aa45  mov     ecx, 80002h
0x18003aa4a  xor     edi, edi
0x18003aa4c  xor     r14d, r14d
0x18003aa4f  call    TRACELogPrint
0x18003aa54  xor     edx, edx; dwCoInit
0x18003aa56  xor     ecx, ecx; pvReserved
0x18003aa58  call    cs:__imp_CoInitializeEx
0x18003aa5e  mov     ebx, eax
0x18003aa60  test    eax, eax
0x18003aa62  js      loc_18003ABCF
0x18003aa68  lea     edi, [r14+1]
0x18003aa6c  call    ?IsCurrentLocalSystem@@YAJXZ; IsCurrentLocalSystem(void)
0x18003aa71  test    eax, eax
0x18003aa73  jz      short loc_18003AA87
0x18003aa75  call    ?ImpersonateLocalSystem@@YAJXZ; ImpersonateLocalSystem(void)
0x18003aa7a  mov     ebx, eax
0x18003aa7c  test    eax, eax
0x18003aa7e  jnz     loc_18003ABCF
0x18003aa84  mov     r14d, edi
0x18003aa87  lea     r8, [rsp+4A0h+nSize]; nSize
0x18003aa8c  mov     [rsp+4A0h+nSize], 104h
0x18003aa94  lea     rdx, [rbp+3A0h+NameBuffer]; lpNameBuffer
0x18003aa9b  mov     ecx, edi; NameFormat
0x18003aa9d  call    cs:__imp_GetComputerObjectNameW
0x18003aaa3  test    al, al
0x18003aaa5  jnz     short loc_18003AAB8
0x18003aaa7  call    cs:__imp_GetLastError
0x18003aaad  mov     ebx, eax
0x18003aaaf  bts     ebx, 1Ch
0x18003aab3  jmp     loc_18003ABCF
0x18003aab8  mov     r11d, 208h
0x18003aabe  lea     r8, aLdap; "LDAP://"
0x18003aac5  mov     edx, r11d; cbDest
0x18003aac8  lea     rcx, [rsp+4A0h+pszDest]; pszDest
0x18003aacd  call    StringCbCopyW
0x18003aad2  mov     ebx, eax
0x18003aad4  test    eax, eax
0x18003aad6  js      loc_18003ABBB
0x18003aadc  lea     r8, [rbp+3A0h+NameBuffer]; pszSrc
0x18003aae3  mov     edx, r11d; cbDest
0x18003aae6  lea     rcx, [rsp+4A0h+pszDest]; pszDest
0x18003aaeb  call    StringCbCatW
0x18003aaf0  mov     ebx, eax
0x18003aaf2  test    eax, eax
0x18003aaf4  js      loc_18003ABBB
0x18003aafa  lea     r8, [rsp+4A0h+ppObject]; ppObject
0x18003aaff  lea     rdx, IID_IDirectoryObject; riid
0x18003ab06  lea     rcx, [rsp+4A0h+pszDest]; lpszPathName
0x18003ab0b  call    cs:__imp_ADsGetObject
0x18003ab11  mov     ebx, eax
0x18003ab13  test    eax, eax
0x18003ab15  js      loc_18003ABBB
0x18003ab1b  mov     rcx, [rsp+4A0h+ppObject]
0x18003ab20  mov     rdx, r15
0x18003ab23  mov     rax, [rcx]
0x18003ab26  mov     rax, [rax+38h]
0x18003ab2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ab2f  mov     ebx, eax
0x18003ab31  test    eax, eax
0x18003ab33  jns     short loc_18003AB57
0x18003ab35  mov     r8d, eax
0x18003ab38  lea     rdx, aFailedXToDelet; "Failed (%x) to Delete Tapisrv Object."
0x18003ab3f  mov     ecx, 10002h
0x18003ab44  call    TRACELogPrint
0x18003ab49  cmp     bx, 2030h
0x18003ab4e  jnz     short loc_18003ABCF
0x18003ab50  mov     ebx, 0FFFFFFE9h
0x18003ab55  jmp     short loc_18003ABCF
0x18003ab57  test    rsi, rsi
0x18003ab5a  jz      short loc_18003ABCF
0x18003ab5c  lea     rax, [rsp+4A0h+hKey]
0x18003ab61  mov     r9d, 20007h; samDesired
0x18003ab67  xor     r8d, r8d; ulOptions
0x18003ab6a  mov     [rsp+4A0h+phkResult], rax; phkResult
0x18003ab6f  lea     rdx, gszRegKeyTelephony; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18003ab76  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003ab7d  call    cs:__imp_RegOpenKeyExW
0x18003ab83  test    eax, eax
0x18003ab85  jnz     short loc_18003ABA2
0x18003ab87  mov     rcx, [rsp+4A0h+hKey]; hKey
0x18003ab8c  mov     rdx, rsi; lpValueName
0x18003ab8f  call    cs:__imp_RegDeleteValueW
0x18003ab95  mov     rcx, [rsp+4A0h+hKey]; hKey
0x18003ab9a  call    cs:__imp_RegCloseKey
0x18003aba0  jmp     short loc_18003ABCF
0x18003aba2  mov     r8d, eax
0x18003aba5  lea     rdx, aRegopenkeyexFa; "RegOpenKeyEx failed, error 0x%x"
0x18003abac  mov     ecx, 10002h
0x18003abb1  call    TRACELogPrint
0x18003abb6  jmp     loc_18003AAA7
0x18003abbb  mov     r8d, ebx
0x18003abbe  lea     rdx, aFailedXToBindC; "Failed (%x) to bind Computer Object."
0x18003abc5  mov     ecx, 10002h
0x18003abca  call    TRACELogPrint
0x18003abcf  mov     rcx, [rsp+4A0h+ppObject]
0x18003abd4  test    rcx, rcx
0x18003abd7  jz      short loc_18003ABE5
0x18003abd9  mov     rax, [rcx]
0x18003abdc  mov     rax, [rax+10h]
0x18003abe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003abe5  test    r14d, r14d
0x18003abe8  jz      short loc_18003ABEF
0x18003abea  call    ?RevertLocalSystemImp@@YAJXZ; RevertLocalSystemImp(void)
0x18003abef  test    edi, edi
0x18003abf1  jz      short loc_18003ABF9
0x18003abf3  call    cs:__imp_CoUninitialize
0x18003abf9  mov     eax, ebx
0x18003abfb  mov     rcx, [rbp+3A0h+var_30]
0x18003ac02  xor     rcx, rsp; StackCookie
0x18003ac05  call    __security_check_cookie
0x18003ac0a  mov     rbx, [rsp+4A0h+arg_10]
0x18003ac12  add     rsp, 480h
0x18003ac19  pop     r15
0x18003ac1b  pop     r14
0x18003ac1d  pop     rdi
0x18003ac1e  pop     rsi
0x18003ac1f  pop     rbp
0x18003ac20  retn
```
