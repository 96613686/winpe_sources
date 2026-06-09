# TraceVerifyDirectoryPathA(x)

- ea: `0x100049a9`
- end: `0x10004ab0`
- name: `_TraceVerifyDirectoryPathA@4`
- size: `263`
- prototype: `int __thiscall(char *String1)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x10006fd6`

## callees

- `0x10002c90`
- `0x10002e2f`
- `0x10003c20`
- `0x100049a9`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__strnicmp` at `0x10004a66`
- `api-ms-win-crt-private-l1-1-0!_o__strnicmp` at `0x10004a85`
- `api-ms-win-crt-private-l1-1-0!_o__strnicmp` at `0x10004a66`
- `api-ms-win-crt-private-l1-1-0!_o__strnicmp` at `0x10004a85`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryA` at `0x100049e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryA` at `0x100049e3`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesA` at `0x10004a33`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesA` at `0x10004a33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x100049ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x100049ed`

## pseudocode

```c
HRESULT __thiscall TraceVerifyDirectoryPathA(char *String1)
{
  HRESULT result; // eax
  DWORD FileAttributesA; // eax
  size_t v4; // esi
  size_t v5; // esi
  size_t v6; // [esp+0h] [ebp-118h]
  size_t v7; // [esp+0h] [ebp-118h]
  size_t v8; // [esp+0h] [ebp-118h]
  const char *v9; // [esp+4h] [ebp-114h]
  size_t *v10; // [esp+4h] [ebp-114h]
  size_t *v11; // [esp+4h] [ebp-114h]
  char v12[4]; // [esp+8h] [ebp-110h] BYREF
  char psz[4]; // [esp+Ch] [ebp-10Ch] BYREF
  CHAR Buffer[260]; // [esp+10h] [ebp-108h] BYREF

  *(_DWORD *)v12 = 0;
  *(_DWORD *)psz = 0;
  if ( !GetWindowsDirectoryA(Buffer, 0x104u) )
    return GetLastError();
  result = StringCchCatA((STRSAFE_LPSTR)"\\Tracing\\", v6, v9);
  if ( result < 0 )
    return (unsigned __int16)result;
  result = StringCchLengthA(psz, v7, v10);
  if ( result < 0 )
    return (unsigned __int16)result;
  FileAttributesA = GetFileAttributesA(Buffer);
  if ( FileAttributesA != -1 && (FileAttributesA & 0x400) != 0 )
    return 161;
  result = StringCchLengthA(v12, v8, v11);
  if ( result < 0 )
    return (unsigned __int16)result;
  v4 = *(_DWORD *)psz;
  if ( __strnicmp(String1, Buffer, *(size_t *)psz) )
  {
    v5 = v4 - 1;
    if ( *(_DWORD *)v12 == v5 )
      return __strnicmp(String1, Buffer, v5) != 0 ? 0xA1 : 0;
    return 161;
  }
  return 0;
}

```

## disassembly

```asm
0x100049a9  mov     edi, edi
0x100049ab  push    ebp
0x100049ac  mov     ebp, esp
0x100049ae  sub     esp, 110h
0x100049b4  mov     eax, ___security_cookie
0x100049b9  xor     eax, ebp
0x100049bb  mov     [ebp+var_4], eax
0x100049be  push    esi; pcchLength
0x100049bf  push    edi; cchMax
0x100049c0  mov     esi, 104h
0x100049c5  mov     dword ptr [ebp+var_110], 0
0x100049cf  push    esi; uSize
0x100049d0  lea     eax, [ebp+Buffer]
0x100049d6  mov     dword ptr [ebp+psz], 0
0x100049e0  push    eax; lpBuffer
0x100049e1  mov     edi, ecx
0x100049e3  call    ds:__imp__GetWindowsDirectoryA@8; GetWindowsDirectoryA(x,x)
0x100049e9  test    eax, eax
0x100049eb  jnz     short loc_100049F8
0x100049ed  call    ds:__imp__GetLastError@0; GetLastError()
0x100049f3  jmp     loc_10004AA2
0x100049f8  push    offset aTracing_0; "\\Tracing\\"
0x100049fd  mov     edx, esi
0x100049ff  lea     ecx, [ebp+Buffer]
0x10004a05  call    _StringCchCatA@12; StringCchCatA(x,x,x)
0x10004a0a  test    eax, eax
0x10004a0c  jns     short loc_10004A16
0x10004a0e  movzx   eax, ax
0x10004a11  jmp     loc_10004AA2
0x10004a16  lea     eax, [ebp+psz]
0x10004a1c  push    eax; psz
0x10004a1d  lea     ecx, [ebp+Buffer]
0x10004a23  call    _StringCchLengthA@12; StringCchLengthA(x,x,x)
0x10004a28  test    eax, eax
0x10004a2a  js      short loc_10004A0E
0x10004a2c  lea     eax, [ebp+Buffer]
0x10004a32  push    eax; lpFileName
0x10004a33  call    ds:__imp__GetFileAttributesA@4; GetFileAttributesA(x)
0x10004a39  cmp     eax, 0FFFFFFFFh
0x10004a3c  jz      short loc_10004A45
0x10004a3e  test    eax, 400h
0x10004a43  jnz     short loc_10004A99
0x10004a45  lea     eax, [ebp+var_110]
0x10004a4b  mov     ecx, edi
0x10004a4d  push    eax; psz
0x10004a4e  call    _StringCchLengthA@12; StringCchLengthA(x,x,x)
0x10004a53  test    eax, eax
0x10004a55  js      short loc_10004A0E
0x10004a57  mov     esi, dword ptr [ebp+psz]
0x10004a5d  lea     eax, [ebp+Buffer]
0x10004a63  push    esi; MaxCount
0x10004a64  push    eax; String2
0x10004a65  push    edi; String1
0x10004a66  call    ds:__imp___strnicmp
0x10004a6c  add     esp, 0Ch
0x10004a6f  test    eax, eax
0x10004a71  jz      short loc_10004AA0
0x10004a73  dec     esi
0x10004a74  cmp     dword ptr [ebp+var_110], esi
0x10004a7a  jnz     short loc_10004A99
0x10004a7c  push    esi; MaxCount
0x10004a7d  lea     eax, [ebp+Buffer]
0x10004a83  push    eax; String2
0x10004a84  push    edi; String1
0x10004a85  call    ds:__imp___strnicmp
0x10004a8b  add     esp, 0Ch
0x10004a8e  neg     eax
0x10004a90  sbb     eax, eax
0x10004a92  and     eax, 0A1h
0x10004a97  jmp     short loc_10004AA2
0x10004a99  mov     eax, 0A1h
0x10004a9e  jmp     short loc_10004AA2
0x10004aa0  xor     eax, eax
0x10004aa2  mov     ecx, [ebp+var_4]
0x10004aa5  pop     edi
0x10004aa6  xor     ecx, ebp; StackCookie
0x10004aa8  pop     esi
0x10004aa9  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10004aae  leave
0x10004aaf  retn
```
