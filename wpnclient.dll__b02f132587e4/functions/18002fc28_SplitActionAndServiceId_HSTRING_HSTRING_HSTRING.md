# SplitActionAndServiceId(HSTRING__ *,HSTRING__ * *,HSTRING__ * *)

- ea: `0x18002fc28`
- end: `0x18002fcfc`
- name: `?SplitActionAndServiceId@@YAJPEAUHSTRING__@@PEAPEAU1@1@Z`
- size: `212`
- prototype: `__int64 __fastcall(HSTRING string, HSTRING *, HSTRING *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180030560`

## callees

- `0x18002fc28`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x18002fc71`
- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x18002fc71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x18002fca1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x18002fca1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002fc61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002fc61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18002fcba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18002fcba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002fc8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002fca9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002fcd7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002fce1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002fc8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002fca9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002fcd7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002fce1`

## pseudocode

```c
__int64 __fastcall SplitActionAndServiceId(HSTRING string, HSTRING *a2, HSTRING *a3)
{
  unsigned int v5; // edi
  const wchar_t *StringRawBuffer; // rax
  size_t v7; // r14
  HRESULT v8; // eax
  HSTRING stringa; // [rsp+48h] [rbp+28h] BYREF
  HSTRING *length; // [rsp+50h] [rbp+30h] BYREF

  length = a3;
  if ( a2 )
    *a2 = 0;
  v5 = 0;
  stringa = 0;
  LODWORD(length) = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(string, (UINT32 *)&length);
  v7 = wcscspn(StringRawBuffer, L"+");
  if ( a2 )
  {
    if ( v7 >= (unsigned int)length )
    {
      WindowsDeleteString(stringa);
      stringa = 0;
      v8 = WindowsDuplicateString(string, &stringa);
    }
    else
    {
      WindowsDeleteString(stringa);
      stringa = 0;
      v8 = WindowsSubstringWithSpecifiedLength(string, 0, v7, &stringa);
    }
    v5 = v8;
    if ( v8 >= 0 )
    {
      *a2 = stringa;
      stringa = 0;
    }
  }
  WindowsDeleteString(0);
  WindowsDeleteString(stringa);
  return v5;
}

```

## disassembly

```asm
0x18002fc28  mov     [rsp-18h+arg_0], rbx
0x18002fc2d  mov     [rsp-18h+arg_18], rsi
0x18002fc32  mov     [rsp-18h+length], r8
0x18002fc37  push    rbp
0x18002fc38  push    rdi
0x18002fc39  push    r14
0x18002fc3b  mov     rbp, rsp
0x18002fc3e  sub     rsp, 20h
0x18002fc42  mov     rbx, rdx
0x18002fc45  mov     rsi, rcx
0x18002fc48  test    rdx, rdx
0x18002fc4b  jz      short loc_18002FC54
0x18002fc4d  mov     qword ptr [rdx], 0
0x18002fc54  xor     edi, edi
0x18002fc56  lea     rdx, [rbp+length]; length
0x18002fc5a  mov     [rbp+string], rdi
0x18002fc5e  mov     dword ptr [rbp+length], edi
0x18002fc61  call    cs:__imp_WindowsGetStringRawBuffer
0x18002fc67  mov     rcx, rax; String
0x18002fc6a  lea     rdx, ?c_szActionServiceDelimiter@@3QBGB; "+"
0x18002fc71  call    cs:__imp_wcscspn
0x18002fc77  mov     r14, rax
0x18002fc7a  test    rbx, rbx
0x18002fc7d  jz      short loc_18002FCD5
0x18002fc7f  mov     eax, dword ptr [rbp+length]
0x18002fc82  mov     rcx, [rbp+string]; string
0x18002fc86  cmp     r14, rax
0x18002fc89  jnb     short loc_18002FCA9
0x18002fc8b  call    cs:__imp_WindowsDeleteString
0x18002fc91  mov     r8d, r14d; length
0x18002fc94  mov     [rbp+string], rdi
0x18002fc98  lea     r9, [rbp+string]; newString
0x18002fc9c  xor     edx, edx; startIndex
0x18002fc9e  mov     rcx, rsi; string
0x18002fca1  call    cs:__imp_WindowsSubstringWithSpecifiedLength
0x18002fca7  jmp     short loc_18002FCC0
0x18002fca9  call    cs:__imp_WindowsDeleteString
0x18002fcaf  lea     rdx, [rbp+string]; newString
0x18002fcb3  mov     [rbp+string], rdi
0x18002fcb7  mov     rcx, rsi; string
0x18002fcba  call    cs:__imp_WindowsDuplicateString
0x18002fcc0  mov     edi, eax
0x18002fcc2  test    eax, eax
0x18002fcc4  js      short loc_18002FCD5
0x18002fcc6  mov     rax, [rbp+string]
0x18002fcca  mov     [rbx], rax
0x18002fccd  mov     [rbp+string], 0
0x18002fcd5  xor     ecx, ecx; string
0x18002fcd7  call    cs:__imp_WindowsDeleteString
0x18002fcdd  mov     rcx, [rbp+string]; string
0x18002fce1  call    cs:__imp_WindowsDeleteString
0x18002fce7  mov     rbx, [rsp+20h+arg_0]
0x18002fcec  mov     eax, edi
0x18002fcee  mov     rsi, [rsp+20h+arg_18]
0x18002fcf3  add     rsp, 20h
0x18002fcf7  pop     r14
0x18002fcf9  pop     rdi
0x18002fcfa  pop     rbp
0x18002fcfb  retn
```
