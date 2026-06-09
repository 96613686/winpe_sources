# SplitActionAndServiceId(HSTRING__ *,HSTRING__ * *,HSTRING__ * *)

- ea: `0x180075560`
- end: `0x180075634`
- name: `?SplitActionAndServiceId@@YAJPEAUHSTRING__@@PEAPEAU1@1@Z`
- size: `212`
- prototype: `__int64 __fastcall(HSTRING string, HSTRING *, HSTRING *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180075d70`

## callees

- `0x180075560`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x1800755a9`
- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x1800755a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800755c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800755e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007560f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180075619`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800755c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800755e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007560f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180075619`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800755f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800755f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180075599`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180075599`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x1800755d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x1800755d9`

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
0x180075560  mov     [rsp-18h+arg_0], rbx
0x180075565  mov     [rsp-18h+arg_18], rsi
0x18007556a  mov     [rsp-18h+length], r8
0x18007556f  push    rbp
0x180075570  push    rdi
0x180075571  push    r14
0x180075573  mov     rbp, rsp
0x180075576  sub     rsp, 20h
0x18007557a  mov     rbx, rdx
0x18007557d  mov     rsi, rcx
0x180075580  test    rdx, rdx
0x180075583  jz      short loc_18007558C
0x180075585  mov     qword ptr [rdx], 0
0x18007558c  xor     edi, edi
0x18007558e  lea     rdx, [rbp+length]; length
0x180075592  mov     [rbp+string], rdi
0x180075596  mov     dword ptr [rbp+length], edi
0x180075599  call    cs:__imp_WindowsGetStringRawBuffer
0x18007559f  mov     rcx, rax; String
0x1800755a2  lea     rdx, ?c_szActionServiceDelimiter@@3QBGB; "+"
0x1800755a9  call    cs:__imp_wcscspn
0x1800755af  mov     r14, rax
0x1800755b2  test    rbx, rbx
0x1800755b5  jz      short loc_18007560D
0x1800755b7  mov     eax, dword ptr [rbp+length]
0x1800755ba  mov     rcx, [rbp+string]; string
0x1800755be  cmp     r14, rax
0x1800755c1  jnb     short loc_1800755E1
0x1800755c3  call    cs:__imp_WindowsDeleteString
0x1800755c9  mov     r8d, r14d; length
0x1800755cc  mov     [rbp+string], rdi
0x1800755d0  lea     r9, [rbp+string]; newString
0x1800755d4  xor     edx, edx; startIndex
0x1800755d6  mov     rcx, rsi; string
0x1800755d9  call    cs:__imp_WindowsSubstringWithSpecifiedLength
0x1800755df  jmp     short loc_1800755F8
0x1800755e1  call    cs:__imp_WindowsDeleteString
0x1800755e7  lea     rdx, [rbp+string]; newString
0x1800755eb  mov     [rbp+string], rdi
0x1800755ef  mov     rcx, rsi; string
0x1800755f2  call    cs:__imp_WindowsDuplicateString
0x1800755f8  mov     edi, eax
0x1800755fa  test    eax, eax
0x1800755fc  js      short loc_18007560D
0x1800755fe  mov     rax, [rbp+string]
0x180075602  mov     [rbx], rax
0x180075605  mov     [rbp+string], 0
0x18007560d  xor     ecx, ecx; string
0x18007560f  call    cs:__imp_WindowsDeleteString
0x180075615  mov     rcx, [rbp+string]; string
0x180075619  call    cs:__imp_WindowsDeleteString
0x18007561f  mov     rbx, [rsp+20h+arg_0]
0x180075624  mov     eax, edi
0x180075626  mov     rsi, [rsp+20h+arg_18]
0x18007562b  add     rsp, 20h
0x18007562f  pop     r14
0x180075631  pop     rdi
0x180075632  pop     rbp
0x180075633  retn
```
