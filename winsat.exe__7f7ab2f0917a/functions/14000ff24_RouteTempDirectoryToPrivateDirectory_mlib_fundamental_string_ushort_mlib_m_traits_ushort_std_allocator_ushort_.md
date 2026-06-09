# RouteTempDirectoryToPrivateDirectory(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x14000ff24`
- end: `0x14001009d`
- name: `?RouteTempDirectoryToPrivateDirectory@@YAHAEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@0@Z`
- size: `377`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001a54c`

## callees

- `0x14000a750`
- `0x14000ff24`
- `0x140016264`
- `0x140113220`

## import_xrefs

- `KERNEL32!GetTempPath2W` at `0x14000ffa3`
- `KERNEL32!GetTempPath2W` at `0x14000ffa3`
- `KERNEL32!GetLastError` at `0x14000ffdd`
- `KERNEL32!GetLastError` at `0x14000ffdd`
- `KERNEL32!SetEnvironmentVariableW` at `0x140010046`
- `KERNEL32!SetEnvironmentVariableW` at `0x140010046`
- `KERNEL32!CreateDirectoryW` at `0x14000ffd3`
- `KERNEL32!CreateDirectoryW` at `0x140010059`
- `KERNEL32!CreateDirectoryW` at `0x14000ffd3`
- `KERNEL32!CreateDirectoryW` at `0x140010059`
- `SHLWAPI!PathAppendW` at `0x14000ffbc`
- `SHLWAPI!PathAppendW` at `0x140010022`
- `SHLWAPI!PathAppendW` at `0x14000ffbc`
- `SHLWAPI!PathAppendW` at `0x140010022`
- `RPCRT4!UuidToStringW` at `0x14001000f`
- `RPCRT4!UuidToStringW` at `0x14001000f`
- `RPCRT4!RpcStringFreeW` at `0x140010073`
- `RPCRT4!RpcStringFreeW` at `0x140010073`
- `RPCRT4!UuidCreate` at `0x14000fffb`
- `RPCRT4!UuidCreate` at `0x14000fffb`

## pseudocode

```c
__int64 __fastcall RouteTempDirectoryToPrivateDirectory(__int64 a1, __int64 a2)
{
  unsigned int v4; // ebx
  __int64 v5; // r8
  __int64 v6; // r8
  RPC_WSTR StringUuid; // [rsp+20h] [rbp-E0h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+28h] [rbp-D8h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v11; // [rsp+60h] [rbp-A0h]
  UUID Uuid; // [rsp+68h] [rbp-98h] BYREF
  WCHAR pszPath[264]; // [rsp+80h] [rbp-80h] BYREF

  StringUuid = 0;
  v11 = 0;
  v4 = 53;
  Uuid = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  if ( !(unsigned int)BuildSystemAndAdminSecurityAttributes(pSecurityDescriptor, &SecurityAttributes)
    && (unsigned int)GetTempPath2W(260, pszPath)
    && PathAppendW(pszPath, L"WinSAT")
    && (CreateDirectoryW(pszPath, &SecurityAttributes) || GetLastError() == 183) )
  {
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::assign(
      a2,
      (__int64)pszPath,
      v5);
    if ( !UuidCreate(&Uuid) && !UuidToStringW(&Uuid, &StringUuid) )
    {
      if ( PathAppendW(pszPath, StringUuid) )
      {
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::assign(
          a1,
          (__int64)pszPath,
          v6);
        if ( SetEnvironmentVariableW(L"TMP", *(LPCWSTR *)(*(_QWORD *)a1 + 24LL)) )
        {
          if ( CreateDirectoryW(pszPath, &SecurityAttributes) )
            v4 = 0;
        }
      }
    }
  }
  if ( StringUuid )
    RpcStringFreeW(&StringUuid);
  return v4;
}

```

## disassembly

```asm
0x14000ff24  mov     [rsp-8+arg_10], rbx
0x14000ff29  push    rbp
0x14000ff2a  push    rsi
0x14000ff2b  push    rdi
0x14000ff2c  lea     rbp, [rsp-1A0h]
0x14000ff34  sub     rsp, 2A0h
0x14000ff3b  mov     rax, cs:__security_cookie
0x14000ff42  xor     rax, rsp
0x14000ff45  mov     [rbp+1B0h+var_20], rax
0x14000ff4c  xorps   xmm0, xmm0
0x14000ff4f  mov     [rsp+2B0h+StringUuid], 0
0x14000ff58  xor     eax, eax
0x14000ff5a  mov     rsi, rdx
0x14000ff5d  mov     rdi, rcx
0x14000ff60  mov     [rsp+2B0h+var_250], rax
0x14000ff65  lea     rdx, [rsp+2B0h+SecurityAttributes]; struct _SECURITY_ATTRIBUTES *
0x14000ff6a  mov     qword ptr [rsp+2B0h+SecurityAttributes.bInheritHandle], rax
0x14000ff6f  lea     rcx, [rsp+2B0h+pSecurityDescriptor]; pSecurityDescriptor
0x14000ff74  mov     ebx, 35h ; '5'
0x14000ff79  movups  xmmword ptr [rsp+2B0h+Uuid.Data1], xmm0
0x14000ff7e  movups  [rsp+2B0h+pSecurityDescriptor], xmm0
0x14000ff83  movups  [rsp+2B0h+var_260], xmm0
0x14000ff88  movups  xmmword ptr [rsp+2B0h+SecurityAttributes.nLength], xmm0
0x14000ff8d  call    ?BuildSystemAndAdminSecurityAttributes@@YAHPEAU_SECURITY_DESCRIPTOR@@PEAU_SECURITY_ATTRIBUTES@@@Z; BuildSystemAndAdminSecurityAttributes(_SECURITY_DESCRIPTOR *,_SECURITY_ATTRIBUTES *)
0x14000ff92  test    eax, eax
0x14000ff94  jnz     loc_140010066
0x14000ff9a  lea     rdx, [rbp+1B0h+pszPath]
0x14000ff9e  mov     ecx, 104h
0x14000ffa3  call    cs:__imp_GetTempPath2W
0x14000ffa9  test    eax, eax
0x14000ffab  jz      loc_140010066
0x14000ffb1  lea     rdx, pszMore; "WinSAT"
0x14000ffb8  lea     rcx, [rbp+1B0h+pszPath]; pszPath
0x14000ffbc  call    cs:__imp_PathAppendW
0x14000ffc2  test    eax, eax
0x14000ffc4  jz      loc_140010066
0x14000ffca  lea     rdx, [rsp+2B0h+SecurityAttributes]; lpSecurityAttributes
0x14000ffcf  lea     rcx, [rbp+1B0h+pszPath]; lpPathName
0x14000ffd3  call    cs:__imp_CreateDirectoryW
0x14000ffd9  test    eax, eax
0x14000ffdb  jnz     short loc_14000FFEA
0x14000ffdd  call    cs:__imp_GetLastError
0x14000ffe3  cmp     eax, 0B7h
0x14000ffe8  jnz     short loc_140010066
0x14000ffea  lea     rdx, [rbp+1B0h+pszPath]
0x14000ffee  mov     rcx, rsi
0x14000fff1  call    ?assign@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAAEAV12@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::assign(ushort const *)
0x14000fff6  lea     rcx, [rsp+2B0h+Uuid]; Uuid
0x14000fffb  call    cs:__imp_UuidCreate
0x140010001  test    eax, eax
0x140010003  jnz     short loc_140010066
0x140010005  lea     rdx, [rsp+2B0h+StringUuid]; StringUuid
0x14001000a  lea     rcx, [rsp+2B0h+Uuid]; Uuid
0x14001000f  call    cs:__imp_UuidToStringW
0x140010015  test    eax, eax
0x140010017  jnz     short loc_140010066
0x140010019  mov     rdx, [rsp+2B0h+StringUuid]; pszMore
0x14001001e  lea     rcx, [rbp+1B0h+pszPath]; pszPath
0x140010022  call    cs:__imp_PathAppendW
0x140010028  test    eax, eax
0x14001002a  jz      short loc_140010066
0x14001002c  lea     rdx, [rbp+1B0h+pszPath]
0x140010030  mov     rcx, rdi
0x140010033  call    ?assign@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAAEAV12@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::assign(ushort const *)
0x140010038  mov     rdx, [rdi]
0x14001003b  lea     rcx, aTmp; "TMP"
0x140010042  mov     rdx, [rdx+18h]; lpValue
0x140010046  call    cs:__imp_SetEnvironmentVariableW
0x14001004c  test    eax, eax
0x14001004e  jz      short loc_140010066
0x140010050  lea     rdx, [rsp+2B0h+SecurityAttributes]; lpSecurityAttributes
0x140010055  lea     rcx, [rbp+1B0h+pszPath]; lpPathName
0x140010059  call    cs:__imp_CreateDirectoryW
0x14001005f  xor     ecx, ecx
0x140010061  test    eax, eax
0x140010063  cmovnz  ebx, ecx
0x140010066  cmp     [rsp+2B0h+StringUuid], 0
0x14001006c  jz      short loc_140010079
0x14001006e  lea     rcx, [rsp+2B0h+StringUuid]; String
0x140010073  call    cs:__imp_RpcStringFreeW
0x140010079  mov     eax, ebx
0x14001007b  mov     rcx, [rbp+1B0h+var_20]
0x140010082  xor     rcx, rsp; StackCookie
0x140010085  call    __security_check_cookie
0x14001008a  mov     rbx, [rsp+2B0h+arg_10]
0x140010092  add     rsp, 2A0h
0x140010099  pop     rdi
0x14001009a  pop     rsi
0x14001009b  pop     rbp
0x14001009c  retn
```
