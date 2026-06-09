# CActivatableClassData::GetIdentifierStringForLogging(HSTRING__ * *)

- ea: `0x1800706e0`
- end: `0x180070853`
- name: `?GetIdentifierStringForLogging@CActivatableClassData@@UEAAXPEAPEAUHSTRING__@@@Z`
- size: `371`
- prototype: `void(CActivatableClassData *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800706e0`
- `0x180091a10`
- `0x1800b7ac0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x18007077e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x1800707b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x18007077e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x1800707b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180070739`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180070739`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007075b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180070792`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800707e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800707fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180070812`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180070820`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007075b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180070792`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800707e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800707fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180070812`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180070820`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800707cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800707cc`

## pseudocode

```c
void __fastcall CActivatableClassData::GetIdentifierStringForLogging(CActivatableClassData *this, HSTRING *a2)
{
  HRESULT v4; // eax
  int v5; // edx
  unsigned int v6; // r8d
  HSTRING v7; // rcx
  HSTRING v8; // rdx
  HSTRING v9; // [rsp+20h] [rbp-40h] BYREF
  HSTRING newString; // [rsp+28h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-30h] BYREF
  HSTRING string; // [rsp+48h] [rbp-18h] BYREF

  *a2 = 0;
  newString = 0;
  v9 = 0;
  string = 0;
  v4 = WindowsCreateStringReference(L"!", 1u, &hstringHeader, &string);
  if ( v4 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v4, v5, v6);
    JUMPOUT(0x180070852LL);
  }
  if ( !*((_QWORD *)this + 25)
    || (WindowsDeleteString(newString),
        v7 = (HSTRING)*((_QWORD *)this + 25),
        newString = 0,
        WindowsConcatString(v7, string, &newString) >= 0) )
  {
    WindowsDeleteString(v9);
    v8 = (HSTRING)*((_QWORD *)this + 24);
    v9 = 0;
    if ( WindowsConcatString(newString, v8, &v9) >= 0 )
      WindowsDuplicateString(v9, a2);
  }
  string = 0;
  WindowsDeleteString(v9);
  v9 = 0;
  WindowsDeleteString(newString);
  newString = 0;
  WindowsDeleteString(0);
  WindowsDeleteString(0);
}

```

## disassembly

```asm
0x1800706e0  mov     [rsp-8+arg_10], rbx
0x1800706e5  mov     [rsp-8+arg_18], rdi
0x1800706ea  push    rbp
0x1800706eb  mov     rbp, rsp
0x1800706ee  sub     rsp, 60h
0x1800706f2  mov     rax, cs:__security_cookie
0x1800706f9  xor     rax, rsp
0x1800706fc  mov     [rbp+var_10], rax
0x180070700  mov     rdi, rdx
0x180070703  mov     qword ptr [rdx], 0
0x18007070a  mov     rbx, rcx
0x18007070d  mov     [rbp+newString], 0
0x180070715  mov     edx, 1; length
0x18007071a  mov     [rbp+var_40], 0
0x180070722  lea     rcx, sourceString; "!"
0x180070729  mov     [rbp+string], 0
0x180070731  lea     r9, [rbp+string]; string
0x180070735  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180070739  call    cs:__imp_WindowsCreateStringReference
0x180070740  nop     dword ptr [rax+rax+00h]
0x180070745  test    eax, eax
0x180070747  js      loc_18007084B
0x18007074d  cmp     qword ptr [rbx+0C8h], 0
0x180070755  jz      short loc_18007078E
0x180070757  mov     rcx, [rbp+newString]; string
0x18007075b  call    cs:__imp_WindowsDeleteString
0x180070762  nop     dword ptr [rax+rax+00h]
0x180070767  mov     rdx, [rbp+string]; string2
0x18007076b  lea     r8, [rbp+newString]; newString
0x18007076f  mov     rcx, [rbx+0C8h]; string1
0x180070776  mov     [rbp+newString], 0
0x18007077e  call    cs:__imp_WindowsConcatString
0x180070785  nop     dword ptr [rax+rax+00h]
0x18007078a  test    eax, eax
0x18007078c  js      short loc_1800707D8
0x18007078e  mov     rcx, [rbp+var_40]; string
0x180070792  call    cs:__imp_WindowsDeleteString
0x180070799  nop     dword ptr [rax+rax+00h]
0x18007079e  mov     rdx, [rbx+0C0h]; string2
0x1800707a5  lea     r8, [rbp+var_40]; newString
0x1800707a9  mov     rcx, [rbp+newString]; string1
0x1800707ad  mov     [rbp+var_40], 0
0x1800707b5  call    cs:__imp_WindowsConcatString
0x1800707bc  nop     dword ptr [rax+rax+00h]
0x1800707c1  test    eax, eax
0x1800707c3  js      short loc_1800707D8
0x1800707c5  mov     rcx, [rbp+var_40]; string
0x1800707c9  mov     rdx, rdi; newString
0x1800707cc  call    cs:__imp_WindowsDuplicateString
0x1800707d3  nop     dword ptr [rax+rax+00h]
0x1800707d8  mov     rcx, [rbp+var_40]; string
0x1800707dc  mov     [rbp+string], 0
0x1800707e4  call    cs:__imp_WindowsDeleteString
0x1800707eb  nop     dword ptr [rax+rax+00h]
0x1800707f0  mov     rcx, [rbp+newString]; string
0x1800707f4  mov     [rbp+var_40], 0
0x1800707fc  call    cs:__imp_WindowsDeleteString
0x180070803  nop     dword ptr [rax+rax+00h]
0x180070808  xor     ecx, ecx; string
0x18007080a  mov     [rbp+newString], 0
0x180070812  call    cs:__imp_WindowsDeleteString
0x180070819  nop     dword ptr [rax+rax+00h]
0x18007081e  xor     ecx, ecx; string
0x180070820  call    cs:__imp_WindowsDeleteString
0x180070827  nop     dword ptr [rax+rax+00h]
0x18007082c  mov     rcx, [rbp+var_10]
0x180070830  xor     rcx, rsp; StackCookie
0x180070833  call    __security_check_cookie
0x180070838  lea     r11, [rsp+60h+var_s0]
0x18007083d  mov     rbx, [r11+20h]
0x180070841  mov     rdi, [r11+28h]
0x180070845  mov     rsp, r11
0x180070848  pop     rbp
0x180070849  retn
0x18007084b  mov     ecx, eax; this
0x18007084d  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
