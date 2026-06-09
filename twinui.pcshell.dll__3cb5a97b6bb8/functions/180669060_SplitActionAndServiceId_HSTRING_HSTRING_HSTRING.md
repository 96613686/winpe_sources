# SplitActionAndServiceId(HSTRING__ *,HSTRING__ * *,HSTRING__ * *)

- ea: `0x180669060`
- end: `0x180669134`
- name: `?SplitActionAndServiceId@@YAJPEAUHSTRING__@@PEAPEAU1@1@Z`
- size: `212`
- prototype: `__int64 __fastcall(HSTRING string, HSTRING *, HSTRING *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1806697d0`

## callees

- `0x180669060`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x1806690a9`
- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x1806690a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1806690f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1806690f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1806690c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1806690e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18066910f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180669119`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1806690c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1806690e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18066910f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180669119`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180669099`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180669099`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x1806690d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x1806690d9`

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
0x180669060  mov     [rsp-18h+arg_0], rbx
0x180669065  mov     [rsp-18h+arg_18], rsi
0x18066906a  mov     [rsp-18h+length], r8
0x18066906f  push    rbp
0x180669070  push    rdi
0x180669071  push    r14
0x180669073  mov     rbp, rsp
0x180669076  sub     rsp, 20h
0x18066907a  mov     rbx, rdx
0x18066907d  mov     rsi, rcx
0x180669080  test    rdx, rdx
0x180669083  jz      short loc_18066908C
0x180669085  mov     qword ptr [rdx], 0
0x18066908c  xor     edi, edi
0x18066908e  lea     rdx, [rbp+length]; length
0x180669092  mov     [rbp+string], rdi
0x180669096  mov     dword ptr [rbp+length], edi
0x180669099  call    cs:__imp_WindowsGetStringRawBuffer
0x18066909f  mov     rcx, rax; String
0x1806690a2  lea     rdx, ?c_szActionServiceDelimiter@@3QBGB; "+"
0x1806690a9  call    cs:__imp_wcscspn
0x1806690af  mov     r14, rax
0x1806690b2  test    rbx, rbx
0x1806690b5  jz      short loc_18066910D
0x1806690b7  mov     eax, dword ptr [rbp+length]
0x1806690ba  mov     rcx, [rbp+string]; string
0x1806690be  cmp     r14, rax
0x1806690c1  jnb     short loc_1806690E1
0x1806690c3  call    cs:__imp_WindowsDeleteString
0x1806690c9  mov     r8d, r14d; length
0x1806690cc  mov     [rbp+string], rdi
0x1806690d0  lea     r9, [rbp+string]; newString
0x1806690d4  xor     edx, edx; startIndex
0x1806690d6  mov     rcx, rsi; string
0x1806690d9  call    cs:__imp_WindowsSubstringWithSpecifiedLength
0x1806690df  jmp     short loc_1806690F8
0x1806690e1  call    cs:__imp_WindowsDeleteString
0x1806690e7  lea     rdx, [rbp+string]; newString
0x1806690eb  mov     [rbp+string], rdi
0x1806690ef  mov     rcx, rsi; string
0x1806690f2  call    cs:__imp_WindowsDuplicateString
0x1806690f8  mov     edi, eax
0x1806690fa  test    eax, eax
0x1806690fc  js      short loc_18066910D
0x1806690fe  mov     rax, [rbp+string]
0x180669102  mov     [rbx], rax
0x180669105  mov     [rbp+string], 0
0x18066910d  xor     ecx, ecx; string
0x18066910f  call    cs:__imp_WindowsDeleteString
0x180669115  mov     rcx, [rbp+string]; string
0x180669119  call    cs:__imp_WindowsDeleteString
0x18066911f  mov     rbx, [rsp+20h+arg_0]
0x180669124  mov     eax, edi
0x180669126  mov     rsi, [rsp+20h+arg_18]
0x18066912b  add     rsp, 20h
0x18066912f  pop     r14
0x180669131  pop     rdi
0x180669132  pop     rbp
0x180669133  retn
```
