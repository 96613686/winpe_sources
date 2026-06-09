# CliMain::ProcessCliCommand(wchar_t const *)

- ea: `0x180008e40`
- end: `0x180008ef5`
- name: `?ProcessCliCommand@CliMain@@SAJPEB_W@Z`
- size: `181`
- prototype: `__int64 __fastcall(const wchar_t *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800021a0`

## callees

- `0x1800084bc`
- `0x180008e40`
- `0x18000bc40`
- `0x180010310`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180008ebe`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180008ebe`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180008e5c`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180008e5c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008eb7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008eb7`

## string_xrefs

- `0x180008ee2`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall CliMain::ProcessCliCommand(const wchar_t *a1)
{
  HRESULT v2; // eax
  unsigned int v3; // ebx
  HLOCAL v4; // rcx
  const char *v5; // r9
  __int64 result; // rax
  int v7; // [rsp+20h] [rbp-48h]
  HLOCAL hMem[2]; // [rsp+28h] [rbp-40h] BYREF
  __int128 v9; // [rsp+38h] [rbp-30h]
  __int64 v10; // [rsp+48h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v2 = CoInitializeEx(0, 0);
  try
  {
    if ( v2 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1284,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
        (const char *)(unsigned int)v2,
        v7);
    v9 = 0;
    v10 = 0;
    hMem[1] = 0;
    hMem[0] = &CommandImpl::`vftable';
    v3 = CommandImpl::RunCommand((CommandImpl *)hMem, a1);
    v4 = hMem[1];
    hMem[1] = 0;
    if ( v4 )
      LocalFree(v4);
    CoUninitialize();
    result = v3;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xC,
                           (unsigned int)"C:\\__w\\1\\s\\src\\updatecli\\libs\\main\\CliMain.cpp",
                           v5);
  }
  return result;
}

```

## disassembly

```asm
0x180008e40  push    rbx
0x180008e42  sub     rsp, 60h
0x180008e46  mov     rax, cs:__security_cookie
0x180008e4d  xor     rax, rsp
0x180008e50  mov     [rsp+68h+var_18], rax
0x180008e55  mov     rbx, rcx
0x180008e58  xor     edx, edx; dwCoInit
0x180008e5a  xor     ecx, ecx; pvReserved
0x180008e5c  call    cs:__imp_CoInitializeEx
0x180008e62  mov     rcx, [rsp+68h]; this
0x180008e67  test    eax, eax
0x180008e69  js      short loc_180008EDF
0x180008e6b  mov     byte ptr [rsp+68h+var_48], 1
0x180008e70  xorps   xmm0, xmm0
0x180008e73  xor     eax, eax
0x180008e75  movups  xmmword ptr [rsp+68h+hMem], xmm0
0x180008e7a  movups  [rsp+68h+var_30], xmm0
0x180008e7f  mov     [rsp+68h+var_20], rax
0x180008e84  mov     [rsp+68h+hMem+8], rax
0x180008e89  lea     rax, ??_7CommandImpl@@6B@; const CommandImpl::`vftable'
0x180008e90  mov     [rsp+68h+hMem], rax
0x180008e95  mov     rdx, rbx; wchar_t *
0x180008e98  lea     rcx, [rsp+68h+hMem]; this
0x180008e9d  call    ?RunCommand@CommandImpl@@QEAAJPEB_W@Z; CommandImpl::RunCommand(wchar_t const *)
0x180008ea2  mov     ebx, eax
0x180008ea4  mov     rcx, [rsp+68h+hMem+8]; hMem
0x180008ea9  mov     [rsp+68h+hMem+8], 0
0x180008eb2  test    rcx, rcx
0x180008eb5  jz      short loc_180008EBE
0x180008eb7  call    cs:__imp_LocalFree
0x180008ebd  nop
0x180008ebe  call    cs:__imp_CoUninitialize
0x180008ec4  mov     eax, ebx
0x180008ec6  jmp     short loc_180008ECC
0x180008ec8  mov     eax, [rsp+68h+var_44]
0x180008ecc  mov     rcx, [rsp+68h+var_18]
0x180008ed1  xor     rcx, rsp; StackCookie
0x180008ed4  call    __security_check_cookie
0x180008ed9  add     rsp, 60h
0x180008edd  pop     rbx
0x180008ede  retn
0x180008edf  mov     r9d, eax; char *
0x180008ee2  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x180008ee9  mov     edx, 1284h; void *
0x180008eee  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
