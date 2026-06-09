# SecpLoadIdpCache

- ea: `0x18001f940`
- end: `0x18001fb4b`
- name: `SecpLoadIdpCache`
- size: `523`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180010efc`
- `0x180011080`

## callees

- `0x180010dc0`
- `0x18001f6fc`
- `0x18001f89c`
- `0x18001f940`
- `0x18001fb54`
- `0x18004fa50`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18001faa5`
- `ntdll!RtlInitUnicodeString` at `0x18001faa5`
- `ntdll!RtlGUIDFromString` at `0x18001fab5`
- `ntdll!RtlGUIDFromString` at `0x18001fab5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001fb15`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001fb15`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001f980`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001f980`

## pseudocode

```c
__int64 __fastcall SecpLoadIdpCache(__int64 **a1)
{
  __int64 *v2; // rax
  __int64 v3; // r9
  __int64 *v4; // rbx
  unsigned int v5; // edi
  DWORD v6; // r14d
  unsigned int v7; // eax
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rcx
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  int v15; // [rsp+38h] [rbp-C8h] BYREF
  _DWORD v16[5]; // [rsp+3Ch] [rbp-C4h] BYREF
  GUID Guid; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR SourceString[72]; // [rsp+60h] [rbp-A0h] BYREF

  hKey = 0;
  Guid = 0;
  v2 = (__int64 *)LocalAlloc(0x40u, 0x18u);
  v4 = v2;
  if ( v2 )
  {
    v6 = 0;
    *((_DWORD *)v2 + 4) = 1;
    SourceString[64] = 0;
    while ( 1 )
    {
      do
      {
        *(_QWORD *)&v16[1] = 0;
        v16[0] = 0;
        v15 = 0;
        v7 = EnumIdProviderHelper(&hKey, v6++, SourceString, v3, &v15, &Guid);
        v5 = v7;
      }
      while ( v15 );
      if ( v7 == 259 )
        break;
      if ( v7 )
        goto LABEL_26;
      if ( !(unsigned int)SecpReadIdpCacheEntry(hKey, SourceString, (__int128 *)&Guid, &v16[1], v16) )
      {
        v8 = *(_QWORD *)&v16[1];
        *(_QWORD *)(*(_QWORD *)&v16[1] + 24LL) = v4;
        v9 = v4[1];
        if ( v9 )
        {
          *(_QWORD *)(v9 + 16) = v8;
          v4[1] = v8;
        }
        else
        {
          v4[1] = v8;
          *v4 = v8;
        }
      }
    }
    v5 = 0;
    if ( !hKey )
      goto LABEL_30;
    if ( (unsigned int)QueryRegValueHelper(
                         (_DWORD)hKey,
                         (unsigned int)L"DefaultProvider",
                         1,
                         1,
                         (__int64)SourceString,
                         128) )
      goto LABEL_24;
    *(_OWORD *)&v16[1] = 0;
    RtlInitUnicodeString((PUNICODE_STRING)&v16[1], SourceString);
    if ( RtlGUIDFromString((PUNICODE_STRING)&v16[1], &Guid) < 0 )
      goto LABEL_24;
    v10 = *v4;
    v11 = 0;
    while ( v10 )
    {
      if ( (*(_BYTE *)(v10 + 64) & 1) != 0 )
      {
        v12 = *(_QWORD *)(v10 + 48) - *(_QWORD *)&Guid.Data1;
        if ( !v12 )
          v12 = *(_QWORD *)(v10 + 56) - *(_QWORD *)Guid.Data4;
        if ( !v12 )
          goto LABEL_25;
        v11 = v10;
      }
      v10 = *(_QWORD *)(v10 + 16);
    }
    if ( !v11 )
    {
LABEL_24:
      v10 = *v4;
      if ( *v4 )
LABEL_25:
        *(_DWORD *)(v10 + 8) = 1;
    }
    else
    {
      *(_DWORD *)(v11 + 8) = 1;
    }
LABEL_26:
    if ( hKey )
      RegCloseKey(hKey);
    if ( !v5 )
    {
LABEL_30:
      *a1 = v4;
      return v5;
    }
  }
  else
  {
    v5 = 8;
  }
  SecpReleaseIdpCache(v4);
  return v5;
}

```

## disassembly

```asm
0x18001f940  push    rbp
0x18001f942  push    rbx
0x18001f943  push    rdi
0x18001f944  push    r13
0x18001f946  push    r14
0x18001f948  push    r15
0x18001f94a  lea     rbp, [rsp-8]
0x18001f94f  sub     rsp, 108h
0x18001f956  mov     rax, cs:__security_cookie
0x18001f95d  xor     rax, rsp
0x18001f960  mov     [rbp+30h+var_40], rax
0x18001f964  mov     edx, 18h; uBytes
0x18001f969  mov     [rsp+130h+hKey], 0
0x18001f972  mov     r15, rcx
0x18001f975  xorps   xmm0, xmm0
0x18001f978  movups  xmmword ptr [rsp+130h+Guid.Data1], xmm0
0x18001f97d  lea     ecx, [rdx+28h]; uFlags
0x18001f980  call    cs:__imp_LocalAlloc
0x18001f986  mov     rbx, rax
0x18001f989  test    rax, rax
0x18001f98c  jnz     short loc_18001F996
0x18001f98e  lea     edi, [rax+8]
0x18001f991  jmp     loc_18001FB1F
0x18001f996  mov     r13d, 1
0x18001f99c  xor     r14d, r14d
0x18001f99f  mov     [rax+10h], r13d
0x18001f9a3  xor     eax, eax
0x18001f9a5  mov     [rbp+30h+var_50], ax
0x18001f9a9  lea     rax, [rsp+130h+Guid]
0x18001f9ae  mov     qword ptr [rsp+130h+var_F4+4], 0
0x18001f9b7  mov     [rsp+130h+var_108], rax
0x18001f9bc  lea     r8, [rsp+130h+SourceString]
0x18001f9c1  lea     rax, [rsp+130h+var_F8]
0x18001f9c6  mov     dword ptr [rsp+130h+var_F4], 0
0x18001f9ce  mov     edx, r14d
0x18001f9d1  mov     [rsp+130h+var_110], rax
0x18001f9d6  lea     rcx, [rsp+130h+hKey]
0x18001f9db  mov     [rsp+130h+var_F8], 0
0x18001f9e3  call    EnumIdProviderHelper
0x18001f9e8  add     r14d, r13d
0x18001f9eb  mov     edi, eax
0x18001f9ed  cmp     [rsp+130h+var_F8], 0
0x18001f9f2  jnz     short loc_18001F9A9
0x18001f9f4  cmp     eax, 103h
0x18001f9f9  jz      short loc_18001FA59
0x18001f9fb  test    eax, eax
0x18001f9fd  jnz     loc_18001FB08
0x18001fa03  mov     rcx, [rsp+130h+hKey]; hKey
0x18001fa08  lea     rax, [rsp+130h+var_F4]
0x18001fa0d  lea     r9, [rsp+130h+var_F4+4]
0x18001fa12  mov     [rsp+130h+var_110], rax; __int64
0x18001fa17  lea     r8, [rsp+130h+Guid]
0x18001fa1c  lea     rdx, [rsp+130h+SourceString]; lpSubKey
0x18001fa21  call    SecpReadIdpCacheEntry
0x18001fa26  test    eax, eax
0x18001fa28  jnz     loc_18001F9A9
0x18001fa2e  mov     rax, qword ptr [rsp+130h+var_F4+4]
0x18001fa33  mov     [rax+18h], rbx
0x18001fa37  mov     rcx, [rbx+8]
0x18001fa3b  test    rcx, rcx
0x18001fa3e  jz      short loc_18001FA4D
0x18001fa40  mov     [rcx+10h], rax
0x18001fa44  mov     [rbx+8], rax
0x18001fa48  jmp     loc_18001F9A9
0x18001fa4d  mov     [rbx+8], rax
0x18001fa51  mov     [rbx], rax
0x18001fa54  jmp     loc_18001F9A9
0x18001fa59  xor     edi, edi
0x18001fa5b  cmp     [rsp+130h+hKey], rdi
0x18001fa60  jz      loc_18001FB29
0x18001fa66  mov     rcx, [rsp+130h+hKey]
0x18001fa6b  lea     rax, [rsp+130h+SourceString]
0x18001fa70  mov     dword ptr [rsp+130h+var_108], 80h
0x18001fa78  lea     rdx, aDefaultprovide; "DefaultProvider"
0x18001fa7f  mov     r9d, r13d
0x18001fa82  mov     [rsp+130h+var_110], rax
0x18001fa87  mov     r8d, r13d
0x18001fa8a  call    QueryRegValueHelper
0x18001fa8f  test    eax, eax
0x18001fa91  jnz     short loc_18001FAFC
0x18001fa93  xorps   xmm0, xmm0
0x18001fa96  lea     rdx, [rsp+130h+SourceString]; SourceString
0x18001fa9b  lea     rcx, [rsp+130h+var_F4+4]; DestinationString
0x18001faa0  movups  xmmword ptr [rsp+130h+var_F4+4], xmm0
0x18001faa5  call    cs:__imp_RtlInitUnicodeString
0x18001faab  lea     rdx, [rsp+130h+Guid]; Guid
0x18001fab0  lea     rcx, [rsp+130h+var_F4+4]; GuidString
0x18001fab5  call    cs:__imp_RtlGUIDFromString
0x18001fabb  test    eax, eax
0x18001fabd  js      short loc_18001FAFC
0x18001fabf  mov     rax, [rbx]
0x18001fac2  xor     ecx, ecx
0x18001fac4  test    rax, rax
0x18001fac7  jz      short loc_18001FAF1
0x18001fac9  test    [rax+40h], r13b
0x18001facd  jz      short loc_18001FAEB
0x18001facf  mov     rcx, [rax+30h]
0x18001fad3  sub     rcx, qword ptr [rsp+130h+Guid.Data1]
0x18001fad8  jnz     short loc_18001FAE3
0x18001fada  mov     rcx, [rax+38h]
0x18001fade  sub     rcx, qword ptr [rsp+130h+Guid.Data4]
0x18001fae3  test    rcx, rcx
0x18001fae6  jz      short loc_18001FB04
0x18001fae8  mov     rcx, rax
0x18001faeb  mov     rax, [rax+10h]
0x18001faef  jmp     short loc_18001FAC4
0x18001faf1  test    rcx, rcx
0x18001faf4  jz      short loc_18001FAFC
0x18001faf6  mov     [rcx+8], r13d
0x18001fafa  jmp     short loc_18001FB08
0x18001fafc  mov     rax, [rbx]
0x18001faff  test    rax, rax
0x18001fb02  jz      short loc_18001FB08
0x18001fb04  mov     [rax+8], r13d
0x18001fb08  cmp     [rsp+130h+hKey], 0
0x18001fb0e  jz      short loc_18001FB1B
0x18001fb10  mov     rcx, [rsp+130h+hKey]; hKey
0x18001fb15  call    cs:__imp_RegCloseKey
0x18001fb1b  test    edi, edi
0x18001fb1d  jz      short loc_18001FB29
0x18001fb1f  mov     rcx, rbx; hMem
0x18001fb22  call    SecpReleaseIdpCache
0x18001fb27  jmp     short loc_18001FB2C
0x18001fb29  mov     [r15], rbx
0x18001fb2c  mov     eax, edi
0x18001fb2e  mov     rcx, [rbp+30h+var_40]
0x18001fb32  xor     rcx, rsp; StackCookie
0x18001fb35  call    __security_check_cookie
0x18001fb3a  add     rsp, 108h
0x18001fb41  pop     r15
0x18001fb43  pop     r14
0x18001fb45  pop     r13
0x18001fb47  pop     rdi
0x18001fb48  pop     rbx
0x18001fb49  pop     rbp
0x18001fb4a  retn
```
