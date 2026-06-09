# CExtensionStateManager::_Initialize(ushort const *,HSTRING__ *)

- ea: `0x18007e6ac`
- end: `0x18007e779`
- name: `?_Initialize@CExtensionStateManager@@AEAAJPEBGPEAUHSTRING__@@@Z`
- size: `205`
- prototype: `int(CExtensionStateManager *__hidden this, const unsigned __int16 *, HSTRING)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180078b94`

## callees

- `0x180018180`
- `0x180078998`
- `0x18007e6ac`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007e6ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007e6ea`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18007e74a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18007e74a`

## pseudocode

```c
__int64 __fastcall CExtensionStateManager::_Initialize(
        CExtensionStateManager *this,
        const unsigned __int16 *a2,
        HSTRING a3)
{
  HKEY *phkResult; // rdi
  signed int v4; // ebx
  PCWSTR StringRawBuffer; // rax
  LSTATUS Key; // eax
  LPCWSTR lpSubKey[5]; // [rsp+50h] [rbp-28h] BYREF

  phkResult = (HKEY *)((char *)this + 16);
  if ( *((_QWORD *)this + 2) )
  {
    return (unsigned int)-2147418113;
  }
  else
  {
    memset(lpSubKey, 0, 24);
    StringRawBuffer = WindowsGetStringRawBuffer(a3, 0);
    v4 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::ConcatFormat(
           lpSubKey,
           L"%s\\%s",
           L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\AppContract",
           StringRawBuffer);
    if ( v4 >= 0 )
    {
      Key = RegCreateKeyExW(HKEY_CURRENT_USER, lpSubKey[0], 0, 0, 0, 0xF003Fu, 0, phkResult, 0);
      v4 = Key;
      if ( Key > 0 )
        v4 = (unsigned __int16)Key | 0x80070000;
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)lpSubKey);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18007e6ac  mov     [rsp+arg_8], rbx
0x18007e6b1  push    rdi
0x18007e6b2  sub     rsp, 70h
0x18007e6b6  lea     rdi, [rcx+10h]
0x18007e6ba  cmp     qword ptr [rdi], 0
0x18007e6be  jz      short loc_18007E6CA
0x18007e6c0  mov     ebx, 8000FFFFh
0x18007e6c5  jmp     loc_18007E769
0x18007e6ca  xor     edx, edx; length
0x18007e6cc  mov     [rsp+78h+lpSubKey], 0
0x18007e6d5  mov     rcx, r8; string
0x18007e6d8  mov     [rsp+78h+var_20], 0
0x18007e6e1  mov     [rsp+78h+var_18], 0
0x18007e6ea  call    cs:__imp_WindowsGetStringRawBuffer
0x18007e6f0  mov     r9, rax
0x18007e6f3  lea     r8, aSoftwareMicros_4; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18007e6fa  lea     rdx, aSS; "%s\\%s"
0x18007e701  lea     rcx, [rsp+78h+lpSubKey]
0x18007e706  call    ?ConcatFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::ConcatFormat(ushort const *,...)
0x18007e70b  mov     ebx, eax
0x18007e70d  test    eax, eax
0x18007e70f  js      short loc_18007E75F
0x18007e711  mov     rdx, [rsp+78h+lpSubKey]; lpSubKey
0x18007e716  xor     r9d, r9d; lpClass
0x18007e719  mov     [rsp+78h+lpdwDisposition], 0; lpdwDisposition
0x18007e722  xor     r8d, r8d; Reserved
0x18007e725  mov     [rsp+78h+phkResult], rdi; phkResult
0x18007e72a  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18007e731  mov     [rsp+78h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18007e73a  mov     [rsp+78h+samDesired], 0F003Fh; samDesired
0x18007e742  mov     [rsp+78h+dwOptions], 0; dwOptions
0x18007e74a  call    cs:__imp_RegCreateKeyExW
0x18007e750  mov     ebx, eax
0x18007e752  test    eax, eax
0x18007e754  jle     short loc_18007E75F
0x18007e756  movzx   ebx, ax
0x18007e759  or      ebx, 80070000h
0x18007e75f  lea     rcx, [rsp+78h+lpSubKey]
0x18007e764  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18007e769  mov     eax, ebx
0x18007e76b  mov     rbx, [rsp+78h+arg_8]
0x18007e773  add     rsp, 70h
0x18007e777  pop     rdi
0x18007e778  retn
```
