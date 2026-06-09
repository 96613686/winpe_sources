# Windows::Internal::String::_InitializeHelper(ushort const *)

- ea: `0x18000ef50`
- end: `0x18000efc6`
- name: `?_InitializeHelper@String@Internal@Windows@@AEAAJPEBG@Z`
- size: `118`
- prototype: `int(Windows::Internal::String *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001cfac`

## callees

- `0x18000ef50`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000ef91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000ef91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000efa8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000efa8`

## pseudocode

```c
HRESULT __fastcall Windows::Internal::String::_InitializeHelper(HSTRING *this, const unsigned __int16 *a2)
{
  unsigned __int64 v3; // rdx
  HRESULT result; // eax
  HRESULT v6; // ebx
  HSTRING v7; // rcx
  HSTRING string; // [rsp+40h] [rbp+18h] BYREF

  string = 0;
  v3 = -1;
  do
    ++v3;
  while ( a2[v3] );
  if ( v3 > 0xFFFFFFFF )
    return -2147024362;
  result = WindowsCreateString(a2, v3, &string);
  v6 = result;
  if ( result >= 0 )
  {
    v7 = *this;
    *this = string;
    WindowsDeleteString(v7);
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x18000ef50  push    rdi
0x18000ef52  sub     rsp, 20h
0x18000ef56  mov     rax, rdx
0x18000ef59  mov     [rsp+28h+string], 0
0x18000ef62  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x18000ef69  mov     rdi, rcx
0x18000ef6c  nop     dword ptr [rax+00h]
0x18000ef70  inc     rdx; length
0x18000ef73  cmp     word ptr [rax+rdx*2], 0
0x18000ef78  jnz     short loc_18000EF70
0x18000ef7a  mov     ecx, 0FFFFFFFFh
0x18000ef7f  cmp     rdx, rcx
0x18000ef82  ja      short loc_18000EFBB
0x18000ef84  lea     r8, [rsp+28h+string]; string
0x18000ef89  mov     [rsp+28h+arg_0], rbx
0x18000ef8e  mov     rcx, rax; sourceString
0x18000ef91  call    cs:__imp_WindowsCreateString
0x18000ef97  mov     ebx, eax
0x18000ef99  test    eax, eax
0x18000ef9b  js      short loc_18000EFB0
0x18000ef9d  mov     rdx, [rsp+28h+string]
0x18000efa2  mov     rcx, [rdi]; string
0x18000efa5  mov     [rdi], rdx
0x18000efa8  call    cs:__imp_WindowsDeleteString
0x18000efae  mov     eax, ebx
0x18000efb0  mov     rbx, [rsp+28h+arg_0]
0x18000efb5  add     rsp, 20h
0x18000efb9  pop     rdi
0x18000efba  retn
0x18000efbb  mov     eax, 80070216h
0x18000efc0  add     rsp, 20h
0x18000efc4  pop     rdi
0x18000efc5  retn
```
