# SplitActionAndServiceId(HSTRING__ *,HSTRING__ * *,HSTRING__ * *)

- ea: `0x1801c31f0`
- end: `0x1801c32c4`
- name: `?SplitActionAndServiceId@@YAJPEAUHSTRING__@@PEAPEAU1@1@Z`
- size: `212`
- prototype: `__int64 __fastcall(HSTRING string, HSTRING *, HSTRING *)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1801c26a0`
- `0x180364e10`

## callees

- `0x1801c31f0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x1801c3239`
- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x1801c3239`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c3253`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c3271`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c329f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c32a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c3253`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c3271`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c329f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c32a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1801c3282`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1801c3282`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801c3229`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801c3229`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x1801c3269`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x1801c3269`

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
0x1801c31f0  mov     [rsp-18h+arg_0], rbx
0x1801c31f5  mov     [rsp-18h+arg_18], rsi
0x1801c31fa  mov     [rsp-18h+length], r8
0x1801c31ff  push    rbp
0x1801c3200  push    rdi
0x1801c3201  push    r14
0x1801c3203  mov     rbp, rsp
0x1801c3206  sub     rsp, 20h
0x1801c320a  mov     rbx, rdx
0x1801c320d  mov     rsi, rcx
0x1801c3210  test    rdx, rdx
0x1801c3213  jz      short loc_1801C321C
0x1801c3215  mov     qword ptr [rdx], 0
0x1801c321c  xor     edi, edi
0x1801c321e  lea     rdx, [rbp+length]; length
0x1801c3222  mov     [rbp+string], rdi
0x1801c3226  mov     dword ptr [rbp+length], edi
0x1801c3229  call    cs:__imp_WindowsGetStringRawBuffer
0x1801c322f  mov     rcx, rax; String
0x1801c3232  lea     rdx, ?c_szActionServiceDelimiter@@3QBGB; Control
0x1801c3239  call    cs:__imp_wcscspn
0x1801c323f  mov     r14, rax
0x1801c3242  test    rbx, rbx
0x1801c3245  jz      short loc_1801C329D
0x1801c3247  mov     eax, dword ptr [rbp+length]
0x1801c324a  mov     rcx, [rbp+string]; string
0x1801c324e  cmp     r14, rax
0x1801c3251  jnb     short loc_1801C3271
0x1801c3253  call    cs:__imp_WindowsDeleteString
0x1801c3259  mov     r8d, r14d; length
0x1801c325c  mov     [rbp+string], rdi
0x1801c3260  lea     r9, [rbp+string]; newString
0x1801c3264  xor     edx, edx; startIndex
0x1801c3266  mov     rcx, rsi; string
0x1801c3269  call    cs:__imp_WindowsSubstringWithSpecifiedLength
0x1801c326f  jmp     short loc_1801C3288
0x1801c3271  call    cs:__imp_WindowsDeleteString
0x1801c3277  lea     rdx, [rbp+string]; newString
0x1801c327b  mov     [rbp+string], rdi
0x1801c327f  mov     rcx, rsi; string
0x1801c3282  call    cs:__imp_WindowsDuplicateString
0x1801c3288  mov     edi, eax
0x1801c328a  test    eax, eax
0x1801c328c  js      short loc_1801C329D
0x1801c328e  mov     rax, [rbp+string]
0x1801c3292  mov     [rbx], rax
0x1801c3295  mov     [rbp+string], 0
0x1801c329d  xor     ecx, ecx; string
0x1801c329f  call    cs:__imp_WindowsDeleteString
0x1801c32a5  mov     rcx, [rbp+string]; string
0x1801c32a9  call    cs:__imp_WindowsDeleteString
0x1801c32af  mov     rbx, [rsp+20h+arg_0]
0x1801c32b4  mov     eax, edi
0x1801c32b6  mov     rsi, [rsp+20h+arg_18]
0x1801c32bb  add     rsp, 20h
0x1801c32bf  pop     r14
0x1801c32c1  pop     rdi
0x1801c32c2  pop     rbp
0x1801c32c3  retn
```
