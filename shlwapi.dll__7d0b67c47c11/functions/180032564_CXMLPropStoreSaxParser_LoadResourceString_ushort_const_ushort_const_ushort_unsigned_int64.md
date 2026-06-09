# CXMLPropStoreSaxParser::_LoadResourceString(ushort const *,ushort const *,ushort *,unsigned __int64)

- ea: `0x180032564`
- end: `0x180032667`
- name: `?_LoadResourceString@CXMLPropStoreSaxParser@@AEAAJPEBG0PEAG_K@Z`
- size: `259`
- prototype: `int(CXMLPropStoreSaxParser *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180031a28`

## callees

- `0x18000eaf0`
- `0x18002e7d0`
- `0x180031018`
- `0x180031454`
- `0x180032564`

## import_xrefs

- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x18003262b`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x180032654`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x18003262b`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x180032654`
- `api-ms-win-core-localization-l1-2-0!SetThreadPreferredUILanguages` at `0x180032605`
- `api-ms-win-core-localization-l1-2-0!SetThreadPreferredUILanguages` at `0x180032605`
- `MrmCoreR!ResourceManagerQueueGetString` at `0x1800325a6`
- `MrmCoreR!ResourceManagerQueueGetString` at `0x1800325a6`

## pseudocode

```c
__int64 __fastcall CXMLPropStoreSaxParser::_LoadResourceString(
        CXMLPropStoreSaxParser *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int64 cchOutBuf)
{
  HRESULT Error; // ebx
  const WCHAR *v10; // rdx
  PCZZWSTR pwszLanguagesBuffer; // [rsp+30h] [rbp-48h] BYREF
  __int64 v13; // [rsp+38h] [rbp-40h]
  __int64 v14; // [rsp+40h] [rbp-38h]

  if ( !a3 )
    return (unsigned int)SHLoadIndirectString(a2, a4, cchOutBuf, 0);
  if ( a2[1] == 123 )
    return (unsigned int)ResourceManagerQueueGetString(a2, L"Language");
  pwszLanguagesBuffer = 0;
  v13 = 0;
  v14 = 0;
  Error = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
            &pwszLanguagesBuffer,
            L"%s ");
  if ( Error >= 0 )
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(&pwszLanguagesBuffer);
    v10 = pwszLanguagesBuffer;
    pwszLanguagesBuffer[v13 - 1] = 0;
    if ( SetThreadPreferredUILanguages(8u, v10, 0) || (Error = ResultFromKnownLastError(), Error >= 0) )
      Error = SHLoadIndirectString(a2, a4, cchOutBuf, 0);
  }
  *((_BYTE *)this + 124) = 1;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&pwszLanguagesBuffer);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180032564  push    rbx
0x180032566  push    rbp
0x180032567  push    rsi
0x180032568  push    rdi
0x180032569  sub     rsp, 58h
0x18003256d  mov     rsi, r9
0x180032570  mov     rdi, rdx
0x180032573  mov     rbp, rcx
0x180032576  test    r8, r8
0x180032579  jz      loc_180032643
0x18003257f  cmp     word ptr [rdx+2], 7Bh ; '{'
0x180032584  jnz     short loc_1800325B1
0x180032586  mov     rax, qword ptr [rsp+78h+cchOutBuf]
0x18003258e  lea     rdx, aLanguage; "Language"
0x180032595  mov     [rsp+78h+var_50], 0
0x18003259e  mov     rcx, rdi
0x1800325a1  mov     [rsp+78h+var_58], rax
0x1800325a6  call    cs:__imp_ResourceManagerQueueGetString
0x1800325ac  jmp     loc_18003265A
0x1800325b1  lea     rdx, aS; "%s "
0x1800325b8  mov     [rsp+78h+pwszLanguagesBuffer], 0
0x1800325c1  lea     rcx, [rsp+78h+pwszLanguagesBuffer]
0x1800325c6  mov     [rsp+78h+var_40], 0
0x1800325cf  mov     [rsp+78h+var_38], 0
0x1800325d8  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1800325dd  mov     ebx, eax
0x1800325df  test    eax, eax
0x1800325e1  js      short loc_180032633
0x1800325e3  lea     rcx, [rsp+78h+pwszLanguagesBuffer]
0x1800325e8  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x1800325ed  mov     rdx, [rsp+78h+pwszLanguagesBuffer]; pwszLanguagesBuffer
0x1800325f2  xor     ecx, ecx
0x1800325f4  mov     rax, [rsp+78h+var_40]
0x1800325f9  xor     r8d, r8d; pulNumLanguages
0x1800325fc  mov     [rdx+rax*2-2], cx
0x180032601  lea     ecx, [r8+8]; dwFlags
0x180032605  call    cs:__imp_SetThreadPreferredUILanguages
0x18003260b  test    eax, eax
0x18003260d  jnz     short loc_18003261A
0x18003260f  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180032614  mov     ebx, eax
0x180032616  test    eax, eax
0x180032618  js      short loc_180032633
0x18003261a  mov     r8d, [rsp+78h+cchOutBuf]; cchOutBuf
0x180032622  xor     r9d, r9d; ppvReserved
0x180032625  mov     rdx, rsi; pszOutBuf
0x180032628  mov     rcx, rdi; pszSource
0x18003262b  call    cs:__imp_SHLoadIndirectString
0x180032631  mov     ebx, eax
0x180032633  lea     rcx, [rsp+78h+pwszLanguagesBuffer]
0x180032638  mov     byte ptr [rbp+7Ch], 1
0x18003263c  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180032641  jmp     short loc_18003265C
0x180032643  mov     r8d, [rsp+78h+cchOutBuf]; cchOutBuf
0x18003264b  xor     r9d, r9d; ppvReserved
0x18003264e  mov     rdx, rsi; pszOutBuf
0x180032651  mov     rcx, rdi; pszSource
0x180032654  call    cs:__imp_SHLoadIndirectString
0x18003265a  mov     ebx, eax
0x18003265c  mov     eax, ebx
0x18003265e  add     rsp, 58h
0x180032662  pop     rdi
0x180032663  pop     rsi
0x180032664  pop     rbp
0x180032665  pop     rbx
0x180032666  retn
```
