# Windows::Internal::String::_InitializeHelper(ushort const *)

- ea: `0x18002f68c`
- end: `0x18002f703`
- name: `?_InitializeHelper@String@Internal@Windows@@AEAAJPEBG@Z`
- size: `119`
- prototype: `__int64 __fastcall(Windows::Internal::String *__hidden this, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18002b96c`
- `0x180030020`
- `0x1800303b0`
- `0x180030d00`

## callees

- `0x18002f2b0`
- `0x18002f68c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002f6eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002f6eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002f6d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002f6d4`

## pseudocode

```c
__int64 __fastcall Windows::Internal::String::_InitializeHelper(HSTRING *this, const unsigned __int16 *a2)
{
  unsigned __int64 v3; // rcx
  HRESULT v4; // ebx
  const WCHAR *v5; // r9
  HSTRING v6; // rcx
  UINT32 length; // [rsp+40h] [rbp+18h] BYREF
  HSTRING string; // [rsp+48h] [rbp+20h] BYREF

  length = 0;
  v3 = -1;
  string = 0;
  do
    ++v3;
  while ( a2[v3] );
  v4 = ULongLongToUInt(v3, &length);
  if ( v4 >= 0 )
  {
    v4 = WindowsCreateString(v5, length, &string);
    if ( v4 >= 0 )
    {
      v6 = *this;
      *this = string;
      WindowsDeleteString(v6);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18002f68c  mov     rax, rsp
0x18002f68f  mov     [rax+8], rbx
0x18002f693  mov     [rax+10h], rsi
0x18002f697  push    rdi
0x18002f698  sub     rsp, 20h
0x18002f69c  xor     esi, esi
0x18002f69e  mov     rdi, rcx
0x18002f6a1  mov     [rax+18h], esi
0x18002f6a4  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002f6a8  mov     [rax+20h], rsi
0x18002f6ac  mov     r9, rdx
0x18002f6af  inc     rcx; unsigned __int64
0x18002f6b2  cmp     [rdx+rcx*2], si
0x18002f6b6  jnz     short loc_18002F6AF
0x18002f6b8  lea     rdx, [rsp+28h+length]; unsigned int *
0x18002f6bd  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18002f6c2  mov     ebx, eax
0x18002f6c4  test    eax, eax
0x18002f6c6  js      short loc_18002F6F1
0x18002f6c8  mov     edx, [rsp+28h+length]; length
0x18002f6cc  lea     r8, [rsp+28h+string]; string
0x18002f6d1  mov     rcx, r9; sourceString
0x18002f6d4  call    cs:__imp_WindowsCreateString
0x18002f6da  mov     ebx, eax
0x18002f6dc  test    eax, eax
0x18002f6de  js      short loc_18002F6F1
0x18002f6e0  mov     rax, [rsp+28h+string]
0x18002f6e5  mov     rcx, [rdi]; string
0x18002f6e8  mov     [rdi], rax
0x18002f6eb  call    cs:__imp_WindowsDeleteString
0x18002f6f1  mov     rsi, [rsp+28h+arg_8]
0x18002f6f6  mov     eax, ebx
0x18002f6f8  mov     rbx, [rsp+28h+arg_0]
0x18002f6fd  add     rsp, 20h
0x18002f701  pop     rdi
0x18002f702  retn
```
