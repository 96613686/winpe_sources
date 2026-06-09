# SipRegisterServer(void)

- ea: `0x180009cc8`
- end: `0x180009e84`
- name: `?SipRegisterServer@@YAJXZ`
- size: `444`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180006df0`

## callees

- `0x180009cc8`
- `0x18000d17e`
- `0x18000d1c0`

## import_xrefs

- `msvcrt!strcpy_s` at `0x180009d4e`
- `msvcrt!strcpy_s` at `0x180009d4e`
- `KERNEL32!GetLastError` at `0x180009d7e`
- `KERNEL32!GetLastError` at `0x180009d7e`
- `KERNEL32!GetModuleFileNameA` at `0x180009d2e`
- `KERNEL32!GetModuleFileNameA` at `0x180009d2e`
- `KERNEL32!GetModuleHandleA` at `0x180009d1b`
- `KERNEL32!GetModuleHandleA` at `0x180009d1b`
- `KERNEL32!MultiByteToWideChar` at `0x180009d74`
- `KERNEL32!MultiByteToWideChar` at `0x180009d74`
- `CRYPT32!CryptSIPAddProvider` at `0x180009e1e`
- `CRYPT32!CryptSIPAddProvider` at `0x180009e3d`
- `CRYPT32!CryptSIPAddProvider` at `0x180009e5c`
- `CRYPT32!CryptSIPAddProvider` at `0x180009e1e`
- `CRYPT32!CryptSIPAddProvider` at `0x180009e3d`
- `CRYPT32!CryptSIPAddProvider` at `0x180009e5c`

## string_xrefs

- `0x180009cfa`: `wshext.dll`
- `0x180009dda`: `CreateIndirectData`
- `0x180009df2`: `RemoveSignedDataMsg`

## pseudocode

```c
signed int SipRegisterServer(void)
{
  HMODULE ModuleHandleA; // rax
  signed int result; // eax
  SIP_ADD_NEWPROVIDER psNewProv; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v3; // [rsp+88h] [rbp-78h]
  CHAR ModuleName[16]; // [rsp+90h] [rbp-70h] BYREF
  CHAR Filename[260]; // [rsp+A0h] [rbp-60h] BYREF
  char v6; // [rsp+1A4h] [rbp+A4h]
  WCHAR WideCharStr[264]; // [rsp+1B0h] [rbp+B0h] BYREF

  memset_0(&psNewProv, 0, 0x60u);
  strcpy(ModuleName, "wshext.dll");
  v6 = 0;
  ModuleHandleA = GetModuleHandleA(ModuleName);
  if ( !GetModuleFileNameA(ModuleHandleA, Filename, 0x105u) || v6 )
    strcpy_s(Filename, 0x105u, ModuleName);
  if ( MultiByteToWideChar(0, 0, Filename, -1, WideCharStr, 261) )
  {
    *(_QWORD *)&psNewProv.cbStruct = 96;
    v3 = 0;
    psNewProv.pwszMagicNumber = 0;
    psNewProv.pwszDLLFileName = WideCharStr;
    psNewProv.pwszGetFuncName = L"GetSignedDataMsg";
    psNewProv.pwszPutFuncName = L"PutSignedDataMsg";
    psNewProv.pwszCreateFuncName = L"CreateIndirectData";
    psNewProv.pwszVerifyFuncName = L"VerifyIndirectData";
    psNewProv.pwszRemoveFuncName = L"RemoveSignedDataMsg";
    psNewProv.pwszIsFunctionNameFmt2 = L"IsFileSupportedName";
    psNewProv.pgSubject = (GUID *)&OID_VBSSIP;
    psNewProv.pwszIsFunctionName = 0;
    if ( CryptSIPAddProvider(&psNewProv) )
    {
      psNewProv.pgSubject = (GUID *)&OID_JSSIP;
      if ( CryptSIPAddProvider(&psNewProv) )
      {
        psNewProv.pgSubject = (GUID *)&OID_WSFSIP;
        if ( CryptSIPAddProvider(&psNewProv) )
          return 0;
      }
    }
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180009cc8  push    rbp
0x180009cca  lea     rbp, [rsp-2D0h]
0x180009cd2  sub     rsp, 3D0h
0x180009cd9  mov     rax, cs:__security_cookie
0x180009ce0  xor     rax, rsp
0x180009ce3  mov     [rbp+2D0h+var_10], rax
0x180009cea  xor     edx, edx; Val
0x180009cec  lea     rcx, [rsp+3D0h+psNewProv]; void *
0x180009cf1  lea     r8d, [rdx+60h]; Size
0x180009cf5  call    memset_0
0x180009cfa  movsd   xmm0, qword ptr cs:aWshextDll_0; "wshext.dll"
0x180009d02  lea     rcx, [rbp+2D0h+ModuleName]; lpModuleName
0x180009d06  mov     eax, dword ptr cs:aWshextDll_0+7; "dll"
0x180009d0c  movsd   qword ptr [rbp+2D0h+ModuleName], xmm0
0x180009d11  mov     dword ptr [rbp+2D0h+ModuleName+7], eax
0x180009d14  mov     [rbp+2D0h+var_22C], 0
0x180009d1b  call    cs:__imp_GetModuleHandleA
0x180009d21  mov     r8d, 105h; nSize
0x180009d27  lea     rdx, [rbp+2D0h+Filename]; lpFilename
0x180009d2b  mov     rcx, rax; hModule
0x180009d2e  call    cs:__imp_GetModuleFileNameA
0x180009d34  test    eax, eax
0x180009d36  jz      short loc_180009D41
0x180009d38  cmp     [rbp+2D0h+var_22C], 0
0x180009d3f  jz      short loc_180009D54
0x180009d41  lea     r8, [rbp+2D0h+ModuleName]; Source
0x180009d45  mov     edx, 105h; SizeInBytes
0x180009d4a  lea     rcx, [rbp+2D0h+Filename]; Destination
0x180009d4e  call    cs:__imp_strcpy_s
0x180009d54  lea     rax, [rbp+2D0h+WideCharStr]
0x180009d5b  mov     [rsp+3D0h+cchWideChar], 105h; cchWideChar
0x180009d63  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180009d67  mov     [rsp+3D0h+lpWideCharStr], rax; lpWideCharStr
0x180009d6c  lea     r8, [rbp+2D0h+Filename]; lpMultiByteStr
0x180009d70  xor     edx, edx; dwFlags
0x180009d72  xor     ecx, ecx; CodePage
0x180009d74  call    cs:__imp_MultiByteToWideChar
0x180009d7a  test    eax, eax
0x180009d7c  jnz     short loc_180009D99
0x180009d7e  call    cs:__imp_GetLastError
0x180009d84  test    eax, eax
0x180009d86  jle     loc_180009E6C
0x180009d8c  movzx   eax, ax
0x180009d8f  or      eax, 80070000h
0x180009d94  jmp     loc_180009E6C
0x180009d99  xor     eax, eax
0x180009d9b  mov     qword ptr [rsp+3D0h+psNewProv.cbStruct], 60h ; '`'
0x180009da4  mov     [rbp+2D0h+var_348], rax
0x180009da8  lea     rcx, [rsp+3D0h+psNewProv]; psNewProv
0x180009dad  lea     rax, [rbp+2D0h+WideCharStr]
0x180009db4  mov     [rsp+3D0h+psNewProv.pwszMagicNumber], 0
0x180009dbd  mov     [rsp+3D0h+psNewProv.pwszDLLFileName], rax
0x180009dc2  lea     rax, aGetsigneddatam_0; "GetSignedDataMsg"
0x180009dc9  mov     [rsp+3D0h+psNewProv.pwszGetFuncName], rax
0x180009dce  lea     rax, aPutsigneddatam_0; "PutSignedDataMsg"
0x180009dd5  mov     [rsp+3D0h+psNewProv.pwszPutFuncName], rax
0x180009dda  lea     rax, aCreateindirect_0; "CreateIndirectData"
0x180009de1  mov     [rsp+3D0h+psNewProv.pwszCreateFuncName], rax
0x180009de6  lea     rax, aVerifyindirect_0; "VerifyIndirectData"
0x180009ded  mov     [rsp+3D0h+psNewProv.pwszVerifyFuncName], rax
0x180009df2  lea     rax, aRemovesignedda_0; "RemoveSignedDataMsg"
0x180009df9  mov     [rsp+3D0h+psNewProv.pwszRemoveFuncName], rax
0x180009dfe  lea     rax, aIsfilesupporte_0; "IsFileSupportedName"
0x180009e05  mov     [rbp+2D0h+psNewProv.pwszIsFunctionNameFmt2], rax
0x180009e09  lea     rax, OID_VBSSIP
0x180009e10  mov     [rsp+3D0h+psNewProv.pgSubject], rax
0x180009e15  mov     [rsp+3D0h+psNewProv.pwszIsFunctionName], 0
0x180009e1e  call    cs:__imp_CryptSIPAddProvider
0x180009e24  test    eax, eax
0x180009e26  jz      loc_180009D7E
0x180009e2c  lea     rax, OID_JSSIP
0x180009e33  lea     rcx, [rsp+3D0h+psNewProv]; psNewProv
0x180009e38  mov     [rsp+3D0h+psNewProv.pgSubject], rax
0x180009e3d  call    cs:__imp_CryptSIPAddProvider
0x180009e43  test    eax, eax
0x180009e45  jz      loc_180009D7E
0x180009e4b  lea     rax, OID_WSFSIP
0x180009e52  lea     rcx, [rsp+3D0h+psNewProv]; psNewProv
0x180009e57  mov     [rsp+3D0h+psNewProv.pgSubject], rax
0x180009e5c  call    cs:__imp_CryptSIPAddProvider
0x180009e62  test    eax, eax
0x180009e64  jz      loc_180009D7E
0x180009e6a  xor     eax, eax
0x180009e6c  mov     rcx, [rbp+2D0h+var_10]
0x180009e73  xor     rcx, rsp; StackCookie
0x180009e76  call    __security_check_cookie
0x180009e7b  add     rsp, 3D0h
0x180009e82  pop     rbp
0x180009e83  retn
```
