# CDesktopAppXFileTypeExecuteCommand::InitializeTypeSpecificStrings(IPropertyBag *)

- ea: `0x1800f3e90`
- end: `0x1800f3f85`
- name: `?InitializeTypeSpecificStrings@CDesktopAppXFileTypeExecuteCommand@@MEAAXPEAUIPropertyBag@@@Z`
- size: `245`
- prototype: `void __fastcall(CDesktopAppXFileTypeExecuteCommand *__hidden this, struct IPropertyBag *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18005cdc4`
- `0x1800f3e90`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f3ee8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f3f23`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f3f5a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f3ee8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f3f23`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f3f5a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f3ec8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f3f06`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f3f3d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f3ec8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f3f06`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f3f3d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f3f74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f3f74`

## pseudocode

```c
void __fastcall CDesktopAppXFileTypeExecuteCommand::InitializeTypeSpecificStrings(
        CDesktopAppXFileTypeExecuteCommand *this,
        struct IPropertyBag *a2)
{
  const WCHAR *StringRawBuffer; // rax
  const WCHAR *v4; // rax
  const WCHAR *v5; // rax
  HSTRING string; // [rsp+50h] [rbp+18h] BYREF

  string = 0;
  LaunchExecuteCommandBase::TryReadStringWithSizeLimit(
    this,
    a2,
    L"MultiSelectModel",
    0xAu,
    (struct Microsoft::WRL::Wrappers::HString *)&string);
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  if ( CompareStringOrdinal(L"single", -1, StringRawBuffer, -1, 1) == 2 )
  {
    *((_DWORD *)this + 64) = 0;
  }
  else
  {
    v4 = WindowsGetStringRawBuffer(string, 0);
    if ( CompareStringOrdinal(L"player", -1, v4, -1, 1) == 2 )
    {
      *((_DWORD *)this + 64) = 2;
    }
    else
    {
      v5 = WindowsGetStringRawBuffer(string, 0);
      if ( CompareStringOrdinal(L"document", -1, v5, -1, 1) == 2 )
        *((_DWORD *)this + 64) = 1;
    }
  }
  WindowsDeleteString(string);
}

```

## disassembly

```asm
0x1800f3e90  mov     r11, rsp
0x1800f3e93  mov     [r11+8], rbx
0x1800f3e97  push    rdi
0x1800f3e98  sub     rsp, 30h
0x1800f3e9c  lea     rax, [r11+18h]
0x1800f3ea0  mov     qword ptr [r11+18h], 0
0x1800f3ea8  mov     r9d, 0Ah; unsigned __int64
0x1800f3eae  mov     [r11-18h], rax
0x1800f3eb2  lea     r8, aMultiselectmod; "MultiSelectModel"
0x1800f3eb9  mov     rbx, rcx
0x1800f3ebc  call    ?TryReadStringWithSizeLimit@LaunchExecuteCommandBase@@IEAA_NPEAUIPropertyBag@@PEBG_KAEAVHString@Wrappers@WRL@Microsoft@@@Z; LaunchExecuteCommandBase::TryReadStringWithSizeLimit(IPropertyBag *,ushort const *,unsigned __int64,Microsoft::WRL::Wrappers::HString &)
0x1800f3ec1  mov     rcx, [rsp+38h+string]; string
0x1800f3ec6  xor     edx, edx; length
0x1800f3ec8  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f3ece  or      edi, 0FFFFFFFFh
0x1800f3ed1  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x1800f3ed9  mov     r9d, edi; cchCount2
0x1800f3edc  lea     rcx, aSingle; "single"
0x1800f3ee3  mov     r8, rax; lpString2
0x1800f3ee6  mov     edx, edi; cchCount1
0x1800f3ee8  call    cs:__imp_CompareStringOrdinal
0x1800f3eee  cmp     eax, 2
0x1800f3ef1  jnz     short loc_1800F3EFF
0x1800f3ef3  mov     dword ptr [rbx+100h], 0
0x1800f3efd  jmp     short loc_1800F3F6F
0x1800f3eff  mov     rcx, [rsp+38h+string]; string
0x1800f3f04  xor     edx, edx; length
0x1800f3f06  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f3f0c  mov     r9d, edi; cchCount2
0x1800f3f0f  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x1800f3f17  mov     r8, rax; lpString2
0x1800f3f1a  lea     rcx, aPlayer; "player"
0x1800f3f21  mov     edx, edi; cchCount1
0x1800f3f23  call    cs:__imp_CompareStringOrdinal
0x1800f3f29  cmp     eax, 2
0x1800f3f2c  jnz     short loc_1800F3F36
0x1800f3f2e  mov     [rbx+100h], eax
0x1800f3f34  jmp     short loc_1800F3F6F
0x1800f3f36  mov     rcx, [rsp+38h+string]; string
0x1800f3f3b  xor     edx, edx; length
0x1800f3f3d  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f3f43  mov     r9d, edi; cchCount2
0x1800f3f46  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x1800f3f4e  mov     r8, rax; lpString2
0x1800f3f51  lea     rcx, aDocument; "document"
0x1800f3f58  mov     edx, edi; cchCount1
0x1800f3f5a  call    cs:__imp_CompareStringOrdinal
0x1800f3f60  cmp     eax, 2
0x1800f3f63  jnz     short loc_1800F3F6F
0x1800f3f65  mov     dword ptr [rbx+100h], 1
0x1800f3f6f  mov     rcx, [rsp+38h+string]; string
0x1800f3f74  call    cs:__imp_WindowsDeleteString
0x1800f3f7a  mov     rbx, [rsp+38h+arg_0]
0x1800f3f7f  add     rsp, 30h
0x1800f3f83  pop     rdi
0x1800f3f84  retn
```
