# SplitActionAndServiceId(HSTRING__ *,HSTRING__ * *,HSTRING__ * *)

- ea: `0x1800c674c`
- end: `0x1800c6820`
- name: `?SplitActionAndServiceId@@YAJPEAUHSTRING__@@PEAPEAU1@1@Z`
- size: `212`
- prototype: `__int64 __fastcall(HSTRING string, HSTRING *, HSTRING *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1800c7070`

## callees

- `0x1800c674c`

## import_xrefs

- `msvcrt!wcscspn` at `0x1800c6795`
- `msvcrt!wcscspn` at `0x1800c6795`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c6785`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c6785`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x1800c67c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x1800c67c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800c67de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800c67de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c67af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c67cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c67fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c6805`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c67af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c67cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c67fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c6805`

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
  v7 = wcscspn(StringRawBuffer, &c_szActionServiceDelimiter);
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
0x1800c674c  mov     [rsp-18h+arg_0], rbx
0x1800c6751  mov     [rsp-18h+arg_18], rsi
0x1800c6756  mov     [rsp-18h+length], r8
0x1800c675b  push    rbp
0x1800c675c  push    rdi
0x1800c675d  push    r14
0x1800c675f  mov     rbp, rsp
0x1800c6762  sub     rsp, 20h
0x1800c6766  mov     rbx, rdx
0x1800c6769  mov     rsi, rcx
0x1800c676c  test    rdx, rdx
0x1800c676f  jz      short loc_1800C6778
0x1800c6771  mov     qword ptr [rdx], 0
0x1800c6778  xor     edi, edi
0x1800c677a  lea     rdx, [rbp+length]; length
0x1800c677e  mov     [rbp+string], rdi
0x1800c6782  mov     dword ptr [rbp+length], edi
0x1800c6785  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c678b  mov     rcx, rax; String
0x1800c678e  lea     rdx, ?c_szActionServiceDelimiter@@3QBGB; Control
0x1800c6795  call    cs:__imp_wcscspn
0x1800c679b  mov     r14, rax
0x1800c679e  test    rbx, rbx
0x1800c67a1  jz      short loc_1800C67F9
0x1800c67a3  mov     eax, dword ptr [rbp+length]
0x1800c67a6  mov     rcx, [rbp+string]; string
0x1800c67aa  cmp     r14, rax
0x1800c67ad  jnb     short loc_1800C67CD
0x1800c67af  call    cs:__imp_WindowsDeleteString
0x1800c67b5  mov     r8d, r14d; length
0x1800c67b8  mov     [rbp+string], rdi
0x1800c67bc  lea     r9, [rbp+string]; newString
0x1800c67c0  xor     edx, edx; startIndex
0x1800c67c2  mov     rcx, rsi; string
0x1800c67c5  call    cs:__imp_WindowsSubstringWithSpecifiedLength
0x1800c67cb  jmp     short loc_1800C67E4
0x1800c67cd  call    cs:__imp_WindowsDeleteString
0x1800c67d3  lea     rdx, [rbp+string]; newString
0x1800c67d7  mov     [rbp+string], rdi
0x1800c67db  mov     rcx, rsi; string
0x1800c67de  call    cs:__imp_WindowsDuplicateString
0x1800c67e4  mov     edi, eax
0x1800c67e6  test    eax, eax
0x1800c67e8  js      short loc_1800C67F9
0x1800c67ea  mov     rax, [rbp+string]
0x1800c67ee  mov     [rbx], rax
0x1800c67f1  mov     [rbp+string], 0
0x1800c67f9  xor     ecx, ecx; string
0x1800c67fb  call    cs:__imp_WindowsDeleteString
0x1800c6801  mov     rcx, [rbp+string]; string
0x1800c6805  call    cs:__imp_WindowsDeleteString
0x1800c680b  mov     rbx, [rsp+20h+arg_0]
0x1800c6810  mov     eax, edi
0x1800c6812  mov     rsi, [rsp+20h+arg_18]
0x1800c6817  add     rsp, 20h
0x1800c681b  pop     r14
0x1800c681d  pop     rdi
0x1800c681e  pop     rbp
0x1800c681f  retn
```
