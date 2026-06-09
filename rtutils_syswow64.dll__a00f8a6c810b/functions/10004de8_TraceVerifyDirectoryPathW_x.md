# TraceVerifyDirectoryPathW(x)

- ea: `0x10004de8`
- end: `0x10004eef`
- name: `_TraceVerifyDirectoryPathW@4`
- size: `263`
- prototype: `HRESULT __thiscall(void *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x10007954`

## callees

- `0x100036b5`
- `0x10003754`
- `0x10003c20`
- `0x10004de8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x10004ea5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x10004ec4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x10004ea5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x10004ec4`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x10004e22`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x10004e22`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x10004e72`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x10004e72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10004e2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10004e2c`

## pseudocode

```c
HRESULT __thiscall TraceVerifyDirectoryPathW(void *this)
{
  HRESULT result; // eax
  DWORD FileAttributesW; // eax
  int v4; // esi
  int v5; // esi
  size_t v6; // [esp+0h] [ebp-21Ch]
  size_t v7; // [esp+0h] [ebp-21Ch]
  size_t v8; // [esp+0h] [ebp-21Ch]
  const wchar_t *v9; // [esp+4h] [ebp-218h]
  size_t *v10; // [esp+4h] [ebp-218h]
  size_t *v11; // [esp+4h] [ebp-218h]
  wchar_t v12[2]; // [esp+8h] [ebp-214h] BYREF
  wchar_t psz[2]; // [esp+Ch] [ebp-210h] BYREF
  WCHAR Buffer[260]; // [esp+10h] [ebp-20Ch] BYREF

  *(_DWORD *)v12 = 0;
  *(_DWORD *)psz = 0;
  if ( !GetWindowsDirectoryW(Buffer, 0x104u) )
    return GetLastError();
  result = StringCchCatW((STRSAFE_LPWSTR)L"\\Tracing\\", v6, v9);
  if ( result < 0 )
    return (unsigned __int16)result;
  result = StringCchLengthW(psz, v7, v10);
  if ( result < 0 )
    return (unsigned __int16)result;
  FileAttributesW = GetFileAttributesW(Buffer);
  if ( FileAttributesW != -1 && (FileAttributesW & 0x400) != 0 )
    return 161;
  result = StringCchLengthW(v12, v8, v11);
  if ( result < 0 )
    return (unsigned __int16)result;
  v4 = *(_DWORD *)psz;
  if ( __o__wcsnicmp(this, Buffer, *(_DWORD *)psz) )
  {
    v5 = v4 - 1;
    if ( *(_DWORD *)v12 == v5 )
      return __o__wcsnicmp(this, Buffer, v5) != 0 ? 0xA1 : 0;
    return 161;
  }
  return 0;
}

```

## disassembly

```asm
0x10004de8  mov     edi, edi
0x10004dea  push    ebp
0x10004deb  mov     ebp, esp
0x10004ded  sub     esp, 214h
0x10004df3  mov     eax, ___security_cookie
0x10004df8  xor     eax, ebp
0x10004dfa  mov     [ebp+var_4], eax
0x10004dfd  push    esi; pcchLength
0x10004dfe  push    edi; cchMax
0x10004dff  mov     esi, 104h
0x10004e04  mov     dword ptr [ebp+var_214], 0
0x10004e0e  push    esi; uSize
0x10004e0f  lea     eax, [ebp+Buffer]
0x10004e15  mov     dword ptr [ebp+psz], 0
0x10004e1f  push    eax; lpBuffer
0x10004e20  mov     edi, ecx
0x10004e22  call    ds:__imp__GetWindowsDirectoryW@8; GetWindowsDirectoryW(x,x)
0x10004e28  test    eax, eax
0x10004e2a  jnz     short loc_10004E37
0x10004e2c  call    ds:__imp__GetLastError@0; GetLastError()
0x10004e32  jmp     loc_10004EE1
0x10004e37  push    offset aTracing; "\\Tracing\\"
0x10004e3c  mov     edx, esi
0x10004e3e  lea     ecx, [ebp+Buffer]
0x10004e44  call    _StringCchCatW@12; StringCchCatW(x,x,x)
0x10004e49  test    eax, eax
0x10004e4b  jns     short loc_10004E55
0x10004e4d  movzx   eax, ax
0x10004e50  jmp     loc_10004EE1
0x10004e55  lea     eax, [ebp+psz]
0x10004e5b  push    eax; psz
0x10004e5c  lea     ecx, [ebp+Buffer]
0x10004e62  call    _StringCchLengthW@12; StringCchLengthW(x,x,x)
0x10004e67  test    eax, eax
0x10004e69  js      short loc_10004E4D
0x10004e6b  lea     eax, [ebp+Buffer]
0x10004e71  push    eax; lpFileName
0x10004e72  call    ds:__imp__GetFileAttributesW@4; GetFileAttributesW(x)
0x10004e78  cmp     eax, 0FFFFFFFFh
0x10004e7b  jz      short loc_10004E84
0x10004e7d  test    eax, 400h
0x10004e82  jnz     short loc_10004ED8
0x10004e84  lea     eax, [ebp+var_214]
0x10004e8a  mov     ecx, edi
0x10004e8c  push    eax; psz
0x10004e8d  call    _StringCchLengthW@12; StringCchLengthW(x,x,x)
0x10004e92  test    eax, eax
0x10004e94  js      short loc_10004E4D
0x10004e96  mov     esi, dword ptr [ebp+psz]
0x10004e9c  lea     eax, [ebp+Buffer]
0x10004ea2  push    esi
0x10004ea3  push    eax
0x10004ea4  push    edi
0x10004ea5  call    ds:__imp___o__wcsnicmp
0x10004eab  add     esp, 0Ch
0x10004eae  test    eax, eax
0x10004eb0  jz      short loc_10004EDF
0x10004eb2  dec     esi
0x10004eb3  cmp     dword ptr [ebp+var_214], esi
0x10004eb9  jnz     short loc_10004ED8
0x10004ebb  push    esi
0x10004ebc  lea     eax, [ebp+Buffer]
0x10004ec2  push    eax
0x10004ec3  push    edi
0x10004ec4  call    ds:__imp___o__wcsnicmp
0x10004eca  add     esp, 0Ch
0x10004ecd  neg     eax
0x10004ecf  sbb     eax, eax
0x10004ed1  and     eax, 0A1h
0x10004ed6  jmp     short loc_10004EE1
0x10004ed8  mov     eax, 0A1h
0x10004edd  jmp     short loc_10004EE1
0x10004edf  xor     eax, eax
0x10004ee1  mov     ecx, [ebp+var_4]
0x10004ee4  pop     edi
0x10004ee5  xor     ecx, ebp; StackCookie
0x10004ee7  pop     esi
0x10004ee8  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10004eed  leave
0x10004eee  retn
```
